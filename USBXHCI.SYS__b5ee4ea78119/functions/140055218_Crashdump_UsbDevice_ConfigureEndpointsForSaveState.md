# Crashdump_UsbDevice_ConfigureEndpointsForSaveState

- ea: `0x140055218`
- end: `0x1400552e9`
- name: `Crashdump_UsbDevice_ConfigureEndpointsForSaveState`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140051730`

## callees

- `0x14002338c`
- `0x140036068`
- `0x140053f98`
- `0x140055218`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400552ca`
- `ntoskrnl!DbgPrintEx` at `0x1400552ca`

## string_xrefs

- `0x1400552b9`: `XHCIDUMP: Crashdump_UsbDevice_ConfigureEndpointsForSaveState: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_UsbDevice_ConfigureEndpointsForSaveState(__int64 a1)
{
  int v2; // edi
  unsigned int i; // ebx
  __int64 DequeuePointer; // rax
  int v5; // edx
  __int64 v6; // r9
  int v7; // r10d
  __int64 *v8; // rcx
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF

  v10 = 0;
  v2 = -1073741823;
  for ( i = 1; i < 0x20; ++i )
  {
    if ( *(_QWORD *)(a1 + 8LL * i + 112) )
    {
      DequeuePointer = Endpoint_GetDequeuePointer(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL * i + 176), 1);
      v5 = *(unsigned __int8 *)(a1 + 56);
      *(_QWORD *)&v10 = DequeuePointer;
      HIDWORD(v10) = ((i & 0x1F | (v5 << 8)) << 16) | 0x4000;
      if ( (unsigned int)Endpoint_GetMaxPrimaryStreams(v6) )
        v7 = 0x10000;
      v8 = *(__int64 **)(a1 + 16);
      DWORD2(v10) = v7;
      v2 = Crashdump_Command_SendCommand(v8, (__int64)&v10, 0);
      if ( v2 < 0 )
        break;
    }
  }
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_UsbDevice_ConfigureEndpointsForSaveState: end 0x%X\n", v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140055218  mov     [rsp+arg_0], rbx
0x14005521d  mov     [rsp+arg_8], rsi
0x140055222  push    rdi
0x140055223  sub     rsp, 30h
0x140055227  xorps   xmm0, xmm0
0x14005522a  mov     rsi, rcx
0x14005522d  movups  [rsp+38h+var_18], xmm0
0x140055232  mov     edi, 0C0000001h
0x140055237  mov     ebx, 1
0x14005523c  mov     r9d, ebx
0x14005523f  cmp     qword ptr [rsi+r9*8+70h], 0
0x140055245  jz      short loc_1400552AF
0x140055247  mov     rax, [rsi+18h]
0x14005524b  xor     r10d, r10d
0x14005524e  mov     r9, [rax+r9*8+0B0h]
0x140055256  lea     edx, [r10+1]
0x14005525a  mov     rcx, r9
0x14005525d  call    Endpoint_GetDequeuePointer
0x140055262  movzx   edx, byte ptr [rsi+38h]
0x140055266  mov     rcx, r9
0x140055269  mov     qword ptr [rsp+38h+var_18], rax
0x14005526e  mov     eax, ebx
0x140055270  shl     edx, 8
0x140055273  and     eax, 1Fh
0x140055276  or      edx, eax
0x140055278  shl     edx, 10h
0x14005527b  bts     edx, 0Eh
0x14005527f  mov     dword ptr [rsp+38h+var_18+0Ch], edx
0x140055283  call    Endpoint_GetMaxPrimaryStreams
0x140055288  test    eax, eax
0x14005528a  lea     rdx, [rsp+38h+var_18]
0x14005528f  mov     ecx, 10000h
0x140055294  cmovnz  r10d, ecx
0x140055298  mov     rcx, [rsi+10h]
0x14005529c  xor     r8d, r8d
0x14005529f  mov     dword ptr [rsp+38h+var_18+8], r10d
0x1400552a4  call    Crashdump_Command_SendCommand
0x1400552a9  mov     edi, eax
0x1400552ab  test    eax, eax
0x1400552ad  js      short loc_1400552B6
0x1400552af  inc     ebx
0x1400552b1  cmp     ebx, 20h ; ' '
0x1400552b4  jb      short loc_14005523C
0x1400552b6  mov     r9d, edi
0x1400552b9  lea     r8, aXhcidumpCrashd_83; "XHCIDUMP: Crashdump_UsbDevice_Configure"...
0x1400552c0  mov     edx, 3; Level
0x1400552c5  mov     ecx, 93h; ComponentId
0x1400552ca  call    cs:__imp_DbgPrintEx
0x1400552d1  nop     dword ptr [rax+rax+00h]
0x1400552d6  mov     rbx, [rsp+38h+arg_0]
0x1400552db  mov     eax, edi
0x1400552dd  mov     rsi, [rsp+38h+arg_8]
0x1400552e2  add     rsp, 30h
0x1400552e6  pop     rdi
0x1400552e7  retn
```
