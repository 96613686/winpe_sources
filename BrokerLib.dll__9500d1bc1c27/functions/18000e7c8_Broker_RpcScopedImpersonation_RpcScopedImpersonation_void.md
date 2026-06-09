# Broker::RpcScopedImpersonation::RpcScopedImpersonation(void)

- ea: `0x18000e7c8`
- end: `0x18000e844`
- name: `??0RpcScopedImpersonation@Broker@@QEAA@XZ`
- size: `124`
- prototype: `__int64 __fastcall(Broker::RpcScopedImpersonation *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e628`

## callees

- `0x18000b3a4`
- `0x18000e7c8`
- `0x1800165da`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000e7d3`
- `RPCRT4!RpcImpersonateClient` at `0x18000e7d3`

## pseudocode

```c
Broker::RpcScopedImpersonation *__fastcall Broker::RpcScopedImpersonation::RpcScopedImpersonation(
        Broker::RpcScopedImpersonation *this)
{
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int128 v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+38h] [rbp-20h]
  int v6; // [rsp+40h] [rbp-18h]

  if ( RpcImpersonateClient(0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
    v5 = 1;
    v6 = 5;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v4 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18000e7c8  push    rbx
0x18000e7ca  sub     rsp, 50h
0x18000e7ce  mov     rbx, rcx
0x18000e7d1  xor     ecx, ecx; BindingHandle
0x18000e7d3  call    cs:__imp_RpcImpersonateClient
0x18000e7d9  test    eax, eax
0x18000e7db  jnz     short loc_18000E7E6
0x18000e7dd  mov     rax, rbx
0x18000e7e0  add     rsp, 50h
0x18000e7e4  pop     rbx
0x18000e7e5  retn
0x18000e7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7ed  test    byte ptr [rcx+1Ch], 8
0x18000e7f1  jz      short loc_18000E80E
0x18000e7f3  cmp     byte ptr [rcx+19h], 2
0x18000e7f7  jb      short loc_18000E80E
0x18000e7f9  mov     rcx, [rcx+10h]
0x18000e7fd  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18000e804  mov     edx, 0Ah
0x18000e809  call    WPP_SF_
0x18000e80e  xorps   xmm0, xmm0
0x18000e811  mov     [rsp+58h+var_20], 1
0x18000e819  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000e820  mov     [rsp+58h+var_18], 5
0x18000e828  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000e82f  mov     [rsp+58h+pExceptionObject], rax
0x18000e834  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000e839  movups  [rsp+58h+var_30], xmm0
0x18000e83e  call    _CxxThrowException_0
```
