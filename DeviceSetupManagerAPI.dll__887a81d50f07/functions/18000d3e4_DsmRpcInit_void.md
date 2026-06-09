# DsmRpcInit(void)

- ea: `0x18000d3e4`
- end: `0x18000d51c`
- name: `?DsmRpcInit@@YAJXZ`
- size: `312`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008f80`

## callees

- `0x1800092c0`
- `0x180009d20`
- `0x18000d3e4`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18000d4da`
- `RPCRT4!RpcStringFreeW` at `0x18000d4da`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d478`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d49b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d4be`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d478`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d49b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000d4be`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000d450`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000d450`

## pseudocode

```c
__int64 DsmRpcInit(void)
{
  RPC_STATUS v0; // eax
  signed int v1; // ebx
  RPC_STATUS v2; // eax
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  RPC_WSTR String; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids);
  String = 0;
  v0 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"DeviceSetupManager", 0, &String);
  v1 = v0;
  if ( !v0 )
    goto LABEL_8;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_8:
    v2 = RpcBindingFromStringBindingW(String, &DsmRpcNotify_v1_0_c_ifspec);
    v1 = v2;
    if ( !v2 )
      goto LABEL_12;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    if ( v1 >= 0 )
    {
LABEL_12:
      v3 = RpcBindingFromStringBindingW(String, &DsmRpcAdmin_v1_0_c_ifspec);
      v1 = v3;
      if ( !v3 )
        goto LABEL_16;
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      if ( v1 >= 0 )
      {
LABEL_16:
        v4 = RpcBindingFromStringBindingW(String, &DsmRpcControl_v1_0_c_ifspec);
        v1 = v4;
        if ( !v4 )
          goto LABEL_20;
        if ( v4 > 0 )
          v1 = (unsigned __int16)v4 | 0x80070000;
        if ( v1 >= 0 )
LABEL_20:
          RpcStringFreeW(&String);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000d3e4  mov     [rsp+arg_8], rbx
0x18000d3e9  mov     [rsp+arg_10], rsi
0x18000d3ee  push    rdi
0x18000d3ef  sub     rsp, 30h
0x18000d3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3fa  lea     rsi, WPP_GLOBAL_Control
0x18000d401  cmp     rcx, rsi
0x18000d404  jz      short loc_18000D421
0x18000d406  test    byte ptr [rcx+1Ch], 1
0x18000d40a  jz      short loc_18000D421
0x18000d40c  mov     rcx, [rcx+10h]
0x18000d410  lea     r8, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids
0x18000d417  mov     edx, 0Ah
0x18000d41c  call    WPP_SF_
0x18000d421  lea     rax, [rsp+38h+String]
0x18000d426  mov     [rsp+38h+String], 0
0x18000d42f  mov     [rsp+38h+StringBinding], rax; StringBinding
0x18000d434  lea     r9, Endpoint; "DeviceSetupManager"
0x18000d43b  xor     r8d, r8d; NetworkAddr
0x18000d43e  mov     [rsp+38h+Options], 0; Options
0x18000d447  lea     rdx, ProtSeq; "ncalrpc"
0x18000d44e  xor     ecx, ecx; ObjUuid
0x18000d450  call    cs:__imp_RpcStringBindingComposeW
0x18000d456  mov     ebx, eax
0x18000d458  mov     edi, 80070000h
0x18000d45d  test    eax, eax
0x18000d45f  jz      short loc_18000D46C
0x18000d461  jle     short loc_18000D468
0x18000d463  movzx   ebx, ax
0x18000d466  or      ebx, edi
0x18000d468  test    ebx, ebx
0x18000d46a  js      short loc_18000D4E0
0x18000d46c  mov     rcx, [rsp+38h+String]; StringBinding
0x18000d471  lea     rdx, DsmRpcNotify_v1_0_c_ifspec; Binding
0x18000d478  call    cs:__imp_RpcBindingFromStringBindingW
0x18000d47e  mov     ebx, eax
0x18000d480  test    eax, eax
0x18000d482  jz      short loc_18000D48F
0x18000d484  jle     short loc_18000D48B
0x18000d486  movzx   ebx, ax
0x18000d489  or      ebx, edi
0x18000d48b  test    ebx, ebx
0x18000d48d  js      short loc_18000D4E0
0x18000d48f  mov     rcx, [rsp+38h+String]; StringBinding
0x18000d494  lea     rdx, DsmRpcAdmin_v1_0_c_ifspec; Binding
0x18000d49b  call    cs:__imp_RpcBindingFromStringBindingW
0x18000d4a1  mov     ebx, eax
0x18000d4a3  test    eax, eax
0x18000d4a5  jz      short loc_18000D4B2
0x18000d4a7  jle     short loc_18000D4AE
0x18000d4a9  movzx   ebx, ax
0x18000d4ac  or      ebx, edi
0x18000d4ae  test    ebx, ebx
0x18000d4b0  js      short loc_18000D4E0
0x18000d4b2  mov     rcx, [rsp+38h+String]; StringBinding
0x18000d4b7  lea     rdx, DsmRpcControl_v1_0_c_ifspec; Binding
0x18000d4be  call    cs:__imp_RpcBindingFromStringBindingW
0x18000d4c4  mov     ebx, eax
0x18000d4c6  test    eax, eax
0x18000d4c8  jz      short loc_18000D4D5
0x18000d4ca  jle     short loc_18000D4D1
0x18000d4cc  movzx   ebx, ax
0x18000d4cf  or      ebx, edi
0x18000d4d1  test    ebx, ebx
0x18000d4d3  js      short loc_18000D4E0
0x18000d4d5  lea     rcx, [rsp+38h+String]; String
0x18000d4da  call    cs:__imp_RpcStringFreeW
0x18000d4e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4e7  cmp     rcx, rsi
0x18000d4ea  jz      short loc_18000D50A
0x18000d4ec  test    byte ptr [rcx+1Ch], 1
0x18000d4f0  jz      short loc_18000D50A
0x18000d4f2  mov     rcx, [rcx+10h]
0x18000d4f6  lea     r8, WPP_b8e3509543d83c1db711f9919e1dba96_Traceguids
0x18000d4fd  mov     edx, 0Bh
0x18000d502  mov     r9d, ebx
0x18000d505  call    WPP_SF_D
0x18000d50a  mov     rsi, [rsp+38h+arg_10]
0x18000d50f  mov     eax, ebx
0x18000d511  mov     rbx, [rsp+38h+arg_8]
0x18000d516  add     rsp, 30h
0x18000d51a  pop     rdi
0x18000d51b  retn
```
