# Crashdump_Endpoint_StopEndpoint

- ea: `0x1400549fc`
- end: `0x140054b49`
- name: `Crashdump_Endpoint_StopEndpoint`
- size: `333`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140054554`
- `0x140054bf0`

## callees

- `0x140053f98`
- `0x1400549fc`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054a21`
- `ntoskrnl!DbgPrintEx` at `0x140054a5e`
- `ntoskrnl!DbgPrintEx` at `0x140054a7d`
- `ntoskrnl!DbgPrintEx` at `0x140054ada`
- `ntoskrnl!DbgPrintEx` at `0x140054b08`
- `ntoskrnl!DbgPrintEx` at `0x140054b2a`
- `ntoskrnl!DbgPrintEx` at `0x140054a21`
- `ntoskrnl!DbgPrintEx` at `0x140054a5e`
- `ntoskrnl!DbgPrintEx` at `0x140054a7d`
- `ntoskrnl!DbgPrintEx` at `0x140054ada`
- `ntoskrnl!DbgPrintEx` at `0x140054b08`
- `ntoskrnl!DbgPrintEx` at `0x140054b2a`

## string_xrefs

- `0x140054a0e`: `XHCIDUMP: Crashdump_Endpoint_StopEndpoint: begin\n`
- `0x140054acc`: `XHCIDUMP: Endpoint %u: stop endpoint command completion failure\n`
- `0x140054b1c`: `XHCIDUMP: Crashdump_Endpoint_StopEndpoint: end 0x%X\n`

## pseudocode

```c
__int64 __fastcall Crashdump_Endpoint_StopEndpoint(__int64 a1)
{
  __int64 v2; // r9
  int v3; // ebx
  __int64 v4; // rax
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF

  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Endpoint_StopEndpoint: begin\n");
  v2 = *(unsigned int *)(a1 + 32);
  if ( (**(_DWORD **)(a1 + 40) & 7) == 1 )
  {
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: Endpoint %u running, stopping now\n", v2);
    v4 = *(_QWORD *)(a1 + 24);
    v6 = 0;
    HIDWORD(v6) = ((*(_DWORD *)(a1 + 32) & 0x1F | (*(unsigned __int8 *)(v4 + 56) << 8)) << 16) | 0x3C00;
    v3 = Crashdump_Command_SendCommand(*(__int64 **)(a1 + 16), (__int64)&v6, 0);
    if ( v3 >= 0 )
    {
      if ( (**(_BYTE **)(a1 + 40) & 7) != 3 )
      {
        DbgPrintEx(0x93u, 1u, "XHCIDUMP: Endpoint %u: endpoint still not stopped\n", *(unsigned int *)(a1 + 32));
        goto LABEL_9;
      }
    }
    else
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Endpoint %u: stop endpoint command completion failure\n", *(_DWORD *)(a1 + 32));
    }
  }
  else
  {
    if ( (**(_DWORD **)(a1 + 40) & 7) != 3 )
    {
      DbgPrintEx(0x93u, 1u, "XHCIDUMP: Endpoint %u is in unknown state\n", v2);
LABEL_9:
      v3 = -1073741630;
      goto LABEL_10;
    }
    DbgPrintEx(0x93u, 3u, "XHCIDUMP: Endpoint %u is currently stopped\n", v2);
    v3 = 0;
  }
LABEL_10:
  DbgPrintEx(0x93u, 3u, "XHCIDUMP: Crashdump_Endpoint_StopEndpoint: end 0x%X\n", v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400549fc  mov     [rsp+arg_0], rbx
0x140054a01  mov     [rsp+arg_8], rsi
0x140054a06  push    rdi
0x140054a07  sub     rsp, 30h
0x140054a0b  mov     rdi, rcx
0x140054a0e  lea     r8, aXhcidumpCrashd_9; "XHCIDUMP: Crashdump_Endpoint_StopEndpoi"...
0x140054a15  mov     esi, 93h
0x140054a1a  mov     edx, 3; Level
0x140054a1f  mov     ecx, esi; ComponentId
0x140054a21  call    cs:__imp_DbgPrintEx
0x140054a28  nop     dword ptr [rax+rax+00h]
0x140054a2d  mov     rax, [rdi+28h]
0x140054a31  mov     ecx, esi; ComponentId
0x140054a33  mov     r9d, [rdi+20h]
0x140054a37  mov     edx, [rax]
0x140054a39  and     edx, 7
0x140054a3c  sub     edx, 1
0x140054a3f  jz      short loc_140054A71
0x140054a41  cmp     edx, 2
0x140054a44  jz      short loc_140054A52
0x140054a46  lea     r8, aXhcidumpEndpoi_5; "XHCIDUMP: Endpoint %u is in unknown sta"...
0x140054a4d  jmp     loc_140054B03
0x140054a52  lea     r8, aXhcidumpEndpoi_3; "XHCIDUMP: Endpoint %u is currently stop"...
0x140054a59  mov     edx, 3; Level
0x140054a5e  call    cs:__imp_DbgPrintEx
0x140054a65  nop     dword ptr [rax+rax+00h]
0x140054a6a  xor     ebx, ebx
0x140054a6c  jmp     loc_140054B19
0x140054a71  lea     r8, aXhcidumpEndpoi_4; "XHCIDUMP: Endpoint %u running, stopping"...
0x140054a78  mov     edx, 3; Level
0x140054a7d  call    cs:__imp_DbgPrintEx
0x140054a84  nop     dword ptr [rax+rax+00h]
0x140054a89  mov     rax, [rdi+18h]
0x140054a8d  lea     rdx, [rsp+38h+var_18]
0x140054a92  xorps   xmm0, xmm0
0x140054a95  xor     r8d, r8d
0x140054a98  movups  [rsp+38h+var_18], xmm0
0x140054a9d  movzx   ecx, byte ptr [rax+38h]
0x140054aa1  mov     eax, [rdi+20h]
0x140054aa4  shl     ecx, 8
0x140054aa7  and     eax, 1Fh
0x140054aaa  or      ecx, eax
0x140054aac  shl     ecx, 10h
0x140054aaf  or      ecx, 3C00h
0x140054ab5  mov     dword ptr [rsp+38h+var_18+0Ch], ecx
0x140054ab9  mov     rcx, [rdi+10h]
0x140054abd  call    Crashdump_Command_SendCommand
0x140054ac2  mov     ebx, eax
0x140054ac4  test    eax, eax
0x140054ac6  jns     short loc_140054AE8
0x140054ac8  mov     r9d, [rdi+20h]
0x140054acc  lea     r8, aXhcidumpEndpoi_1; "XHCIDUMP: Endpoint %u: stop endpoint co"...
0x140054ad3  mov     edx, 1; Level
0x140054ad8  mov     ecx, esi; ComponentId
0x140054ada  call    cs:__imp_DbgPrintEx
0x140054ae1  nop     dword ptr [rax+rax+00h]
0x140054ae6  jmp     short loc_140054B19
0x140054ae8  mov     rax, [rdi+28h]
0x140054aec  mov     ecx, [rax]
0x140054aee  and     ecx, 7
0x140054af1  cmp     cl, 3
0x140054af4  jz      short loc_140054B19
0x140054af6  mov     r9d, [rdi+20h]
0x140054afa  lea     r8, aXhcidumpEndpoi_2; "XHCIDUMP: Endpoint %u: endpoint still n"...
0x140054b01  mov     ecx, esi; ComponentId
0x140054b03  mov     edx, 1; Level
0x140054b08  call    cs:__imp_DbgPrintEx
0x140054b0f  nop     dword ptr [rax+rax+00h]
0x140054b14  mov     ebx, 0C00000C2h
0x140054b19  mov     r9d, ebx
0x140054b1c  lea     r8, aXhcidumpCrashd_60; "XHCIDUMP: Crashdump_Endpoint_StopEndpoi"...
0x140054b23  mov     edx, 3; Level
0x140054b28  mov     ecx, esi; ComponentId
0x140054b2a  call    cs:__imp_DbgPrintEx
0x140054b31  nop     dword ptr [rax+rax+00h]
0x140054b36  mov     rsi, [rsp+38h+arg_8]
0x140054b3b  mov     eax, ebx
0x140054b3d  mov     rbx, [rsp+38h+arg_0]
0x140054b42  add     rsp, 30h
0x140054b46  pop     rdi
0x140054b47  retn
```
