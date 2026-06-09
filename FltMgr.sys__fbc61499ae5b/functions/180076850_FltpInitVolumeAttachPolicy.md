# FltpInitVolumeAttachPolicy

- ea: `0x180076850`
- end: `0x18007695d`
- name: `FltpInitVolumeAttachPolicy`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180070c80`

## callees

- `0x180009f20`
- `0x18001f790`
- `0x180020580`
- `0x180076850`
- `0x180076970`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800768dd`
- `ntoskrnl!ZwClose` at `0x1800768dd`
- `ntoskrnl!FsRtlOpenFileSystemRegistryKeyFromFsGuid` at `0x18007688b`
- `ntoskrnl!FsRtlOpenFileSystemRegistryKeyFromFsGuid` at `0x18007688b`

## pseudocode

```c
__int64 __fastcall FltpInitVolumeAttachPolicy(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbp
  __int64 v4; // rdi
  __int64 result; // rax
  int v6; // edx
  int v7; // r8d
  HANDLE Handle; // [rsp+80h] [rbp+8h] BYREF

  v1 = a1 + 2152;
  Handle = 0;
  v2 = a1 + 2136;
  v4 = (unsigned int)FsRtlOpenFileSystemRegistryKeyFromFsGuid(a1 + 2136, a1 + 2152, 131097, 0, &Handle);
  if ( (int)FltpDbgStatus(v4, "minkernel\\fs\\filtermgr\\filter\\volumesup.c", 3262, 0) >= 0 )
  {
    FltiAttachPolicyInit(Handle, a1 + 2168);
    FltpLogEventInitAttachPolicy(a1);
  }
  if ( Handle )
    ZwClose(Handle);
  result = FltpDbgStatus((unsigned int)v4, "minkernel\\fs\\filtermgr\\filter\\volumesup.c", 3277, 0);
  if ( (int)result < 0 && (Microsoft_Windows_FilterManagerEnableBits & 4) != 0 )
    return McTemplateK0hzr0jjhzr4d_EtwWriteTransfer(
             *(_WORD *)(a1 + 176) >> 1,
             v6,
             v7,
             *(_WORD *)(a1 + 144) >> 1,
             *(_QWORD *)(a1 + 152),
             v2,
             v1,
             *(_WORD *)(a1 + 176) >> 1,
             *(_QWORD *)(a1 + 184),
             v4);
  return result;
}

```

## disassembly

```asm
0x180076850  mov     r11, rsp
0x180076853  push    rbx
0x180076854  push    rbp
0x180076855  push    rsi
0x180076856  push    rdi
0x180076857  sub     rsp, 58h
0x18007685b  lea     rsi, [rcx+868h]
0x180076862  mov     qword ptr [r11+8], 0
0x18007686a  lea     rbp, [rcx+858h]
0x180076871  mov     rbx, rcx
0x180076874  lea     rax, [r11+8]
0x180076878  mov     rdx, rsi
0x18007687b  mov     rcx, rbp
0x18007687e  mov     [r11-58h], rax
0x180076882  xor     r9d, r9d
0x180076885  mov     r8d, 20019h
0x18007688b  call    cs:__imp_FsRtlOpenFileSystemRegistryKeyFromFsGuid
0x180076892  nop     dword ptr [rax+rax+00h]
0x180076897  mov     r8d, 0CBEh
0x18007689d  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x1800768a4  mov     ecx, eax
0x1800768a6  xor     r9d, r9d
0x1800768a9  mov     edi, eax
0x1800768ab  call    FltpDbgStatus
0x1800768b0  test    eax, eax
0x1800768b2  js      short loc_1800768D0
0x1800768b4  mov     rcx, [rsp+78h+Handle]
0x1800768bc  lea     rdx, [rbx+878h]
0x1800768c3  call    FltiAttachPolicyInit
0x1800768c8  mov     rcx, rbx
0x1800768cb  call    FltpLogEventInitAttachPolicy
0x1800768d0  mov     rcx, [rsp+78h+Handle]; Handle
0x1800768d8  test    rcx, rcx
0x1800768db  jz      short loc_1800768E9
0x1800768dd  call    cs:__imp_ZwClose
0x1800768e4  nop     dword ptr [rax+rax+00h]
0x1800768e9  mov     r8d, 0CCDh
0x1800768ef  lea     rdx, aMinkernelFsFil_30; "minkernel\\fs\\filtermgr\\filter\\volum"...
0x1800768f6  xor     r9d, r9d
0x1800768f9  mov     ecx, edi
0x1800768fb  call    FltpDbgStatus
0x180076900  test    eax, eax
0x180076902  jns     short loc_180076953
0x180076904  test    cs:Microsoft_Windows_FilterManagerEnableBits, 4
0x18007690b  jz      short loc_180076953
0x18007690d  mov     rax, [rbx+0B8h]
0x180076914  movzx   ecx, word ptr [rbx+0B0h]
0x18007691b  movzx   r9d, word ptr [rbx+90h]
0x180076923  mov     [rsp+78h+var_30], edi
0x180076927  mov     [rsp+78h+var_38], rax
0x18007692c  mov     rax, [rbx+98h]
0x180076933  shr     cx, 1
0x180076936  mov     [rsp+78h+var_40], cx
0x18007693b  mov     [rsp+78h+var_48], rsi
0x180076940  mov     [rsp+78h+var_50], rbp
0x180076945  shr     r9w, 1
0x180076949  mov     [rsp+78h+var_58], rax
0x18007694e  call    McTemplateK0hzr0jjhzr4d_EtwWriteTransfer
0x180076953  add     rsp, 58h
0x180076957  pop     rdi
0x180076958  pop     rsi
0x180076959  pop     rbp
0x18007695a  pop     rbx
0x18007695b  retn
```
