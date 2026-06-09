# Broker::RpcScopedImpersonation::RpcScopedImpersonation(void)

- ea: `0x180004194`
- end: `0x180004210`
- name: `??0RpcScopedImpersonation@Broker@@QEAA@XZ`
- size: `124`
- prototype: `Broker::RpcScopedImpersonation *__fastcall(Broker::RpcScopedImpersonation *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004000`

## callees

- `0x180003840`
- `0x180004194`
- `0x180013978`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000419f`
- `RPCRT4!RpcImpersonateClient` at `0x18000419f`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
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
0x180004194  push    rbx
0x180004196  sub     rsp, 50h
0x18000419a  mov     rbx, rcx
0x18000419d  xor     ecx, ecx; BindingHandle
0x18000419f  call    cs:__imp_RpcImpersonateClient
0x1800041a5  test    eax, eax
0x1800041a7  jnz     short loc_1800041B2
0x1800041a9  mov     rax, rbx
0x1800041ac  add     rsp, 50h
0x1800041b0  pop     rbx
0x1800041b1  retn
0x1800041b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041b9  test    byte ptr [rcx+1Ch], 8
0x1800041bd  jz      short loc_1800041DA
0x1800041bf  cmp     byte ptr [rcx+19h], 2
0x1800041c3  jb      short loc_1800041DA
0x1800041c5  mov     rcx, [rcx+10h]
0x1800041c9  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800041d0  mov     edx, 0Ah
0x1800041d5  call    WPP_SF_
0x1800041da  xorps   xmm0, xmm0
0x1800041dd  mov     [rsp+58h+var_20], 1
0x1800041e5  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800041ec  mov     [rsp+58h+var_18], 5
0x1800041f4  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800041fb  mov     [rsp+58h+pExceptionObject], rax
0x180004200  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180004205  movups  [rsp+58h+var_30], xmm0
0x18000420a  call    _CxxThrowException_0
```
