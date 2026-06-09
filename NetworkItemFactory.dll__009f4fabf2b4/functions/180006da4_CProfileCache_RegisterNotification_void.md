# CProfileCache::_RegisterNotification(void)

- ea: `0x180006da4`
- end: `0x180006eec`
- name: `?_RegisterNotification@CProfileCache@@AEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006240`

## callees

- `0x180006da4`
- `0x18000b010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x180006e17`
- `ole32!CoSetProxyBlanket` at `0x180006e7f`
- `ole32!CoSetProxyBlanket` at `0x180006e17`
- `ole32!CoSetProxyBlanket` at `0x180006e7f`

## pseudocode

```c
__int64 __fastcall CProfileCache::_RegisterNotification(CProfileCache *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, IUnknown **); // rcx
  HRESULT v3; // ebx
  HRESULT v4; // eax
  IUnknown *v5; // rcx
  IUnknown *v7; // [rsp+50h] [rbp+8h] BYREF
  IUnknown *pProxy; // [rsp+58h] [rbp+10h] BYREF

  pProxy = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*((_QWORD *)this + 1);
  *((_QWORD *)this + 10) = 0;
  v3 = (**v2)(v2, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, &pProxy);
  if ( v3 >= 0 )
  {
    v3 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
    if ( !v3 )
    {
      v7 = 0;
      v3 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl[1].AddRef)(
             pProxy,
             &IID_INotifyNetworkEventsPrivate,
             &v7);
      if ( !v3 )
      {
        v4 = CoSetProxyBlanket(v7, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
        v5 = v7;
        v3 = v4;
        if ( v4 >= 0 )
        {
          ((void (__fastcall *)(IUnknown *))v7->lpVtbl->AddRef)(v7);
          v5 = v7;
          *((_QWORD *)this + 10) = v7;
        }
        ((void (__fastcall *)(IUnknown *))v5->lpVtbl->Release)(v5);
      }
    }
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    if ( v3 >= 0 )
      return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, CProfileCache *, char *))(**((_QWORD **)this + 10) + 40LL))(
                             *((_QWORD *)this + 10),
                             this,
                             (char *)this + 88);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006da4  mov     [rsp+arg_10], rbx
0x180006da9  push    rdi
0x180006daa  sub     rsp, 40h
0x180006dae  mov     rdi, rcx
0x180006db1  mov     [rsp+48h+pProxy], 0
0x180006dba  mov     rcx, [rcx+8]
0x180006dbe  lea     r8, [rsp+48h+pProxy]
0x180006dc3  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x180006dca  mov     qword ptr [rdi+50h], 0
0x180006dd2  mov     rax, [rcx]
0x180006dd5  mov     rax, [rax]
0x180006dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ddd  mov     ebx, eax
0x180006ddf  test    eax, eax
0x180006de1  js      loc_180006EDF
0x180006de7  mov     rcx, [rsp+48h+pProxy]; pProxy
0x180006dec  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180006df0  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180006df8  xor     r8d, r8d; dwAuthzSvc
0x180006dfb  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x180006e04  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180006e07  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x180006e0f  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x180006e17  call    cs:__imp_CoSetProxyBlanket
0x180006e1d  mov     ebx, eax
0x180006e1f  test    eax, eax
0x180006e21  jnz     loc_180006EB1
0x180006e27  mov     rcx, [rsp+48h+pProxy]
0x180006e2c  lea     r8, [rsp+48h+arg_0]
0x180006e31  mov     [rsp+48h+arg_0], 0
0x180006e3a  lea     rdx, IID_INotifyNetworkEventsPrivate
0x180006e41  mov     rax, [rcx]
0x180006e44  mov     rax, [rax+20h]
0x180006e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e4d  mov     ebx, eax
0x180006e4f  test    eax, eax
0x180006e51  jnz     short loc_180006EB1
0x180006e53  mov     rcx, [rsp+48h+arg_0]; pProxy
0x180006e58  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180006e5c  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180006e64  xor     r8d, r8d; dwAuthzSvc
0x180006e67  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x180006e70  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180006e73  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x180006e7b  mov     [rsp+48h+dwAuthnLevel], eax; dwAuthnLevel
0x180006e7f  call    cs:__imp_CoSetProxyBlanket
0x180006e85  mov     rcx, [rsp+48h+arg_0]
0x180006e8a  mov     ebx, eax
0x180006e8c  test    eax, eax
0x180006e8e  js      short loc_180006EA5
0x180006e90  mov     rax, [rcx]
0x180006e93  mov     rax, [rax+8]
0x180006e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e9c  mov     rcx, [rsp+48h+arg_0]
0x180006ea1  mov     [rdi+50h], rcx
0x180006ea5  mov     rax, [rcx]
0x180006ea8  mov     rax, [rax+10h]
0x180006eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb1  mov     rcx, [rsp+48h+pProxy]
0x180006eb6  mov     rax, [rcx]
0x180006eb9  mov     rax, [rax+10h]
0x180006ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec2  test    ebx, ebx
0x180006ec4  js      short loc_180006EDF
0x180006ec6  mov     rcx, [rdi+50h]
0x180006eca  lea     r8, [rdi+58h]
0x180006ece  mov     rdx, rdi
0x180006ed1  mov     rax, [rcx]
0x180006ed4  mov     rax, [rax+28h]
0x180006ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006edd  mov     ebx, eax
0x180006edf  mov     eax, ebx
0x180006ee1  mov     rbx, [rsp+48h+arg_10]
0x180006ee6  add     rsp, 40h
0x180006eea  pop     rdi
0x180006eeb  retn
```
