# Broker::RpcScopedImpersonation::RpcScopedImpersonation(void)

- ea: `0x1800114f0`
- end: `0x18001156c`
- name: `??0RpcScopedImpersonation@Broker@@QEAA@XZ`
- size: `124`
- prototype: `Broker::RpcScopedImpersonation *__fastcall(Broker::RpcScopedImpersonation *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f680`

## callees

- `0x180005a50`
- `0x1800114f0`
- `0x18001d9ac`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800114fb`
- `RPCRT4!RpcImpersonateClient` at `0x1800114fb`

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
0x1800114f0  push    rbx
0x1800114f2  sub     rsp, 50h
0x1800114f6  mov     rbx, rcx
0x1800114f9  xor     ecx, ecx; BindingHandle
0x1800114fb  call    cs:__imp_RpcImpersonateClient
0x180011501  test    eax, eax
0x180011503  jnz     short loc_18001150E
0x180011505  mov     rax, rbx
0x180011508  add     rsp, 50h
0x18001150c  pop     rbx
0x18001150d  retn
0x18001150e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011515  test    byte ptr [rcx+1Ch], 8
0x180011519  jz      short loc_180011536
0x18001151b  cmp     byte ptr [rcx+19h], 2
0x18001151f  jb      short loc_180011536
0x180011521  mov     rcx, [rcx+10h]
0x180011525  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x18001152c  mov     edx, 0Ah
0x180011531  call    WPP_SF_
0x180011536  xorps   xmm0, xmm0
0x180011539  mov     [rsp+58h+var_20], 1
0x180011541  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180011548  mov     [rsp+58h+var_18], 5
0x180011550  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180011557  mov     [rsp+58h+pExceptionObject], rax
0x18001155c  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180011561  movups  [rsp+58h+var_30], xmm0
0x180011566  call    _CxxThrowException_0
```
