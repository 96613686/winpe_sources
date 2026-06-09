# CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)

- ea: `0x180029bf8`
- end: `0x180029cb4`
- name: `?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, const unsigned __int16 *, unsigned int *, struct IInternetSecurityManager **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800296f0`
- `0x180029760`
- `0x180029cbc`
- `0x180029d10`

## callees

- `0x180029bf8`
- `0x180030010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180029c3f`
- `ole32!CoCreateInstance` at `0x180029c3f`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::getZone(
        CImpIADOSecurity *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct IInternetSecurityManager **a4)
{
  HRESULT Instance; // esi
  unsigned int v9; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+54h] [rbp+Ch]
  struct IInternetSecurityManager *ppv; // [rsp+60h] [rbp+18h] BYREF

  v10 = HIDWORD(this);
  ppv = 0;
  v9 = 4;
  Instance = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IInternetSecurityManager *, const unsigned __int16 *, unsigned int *, _QWORD))ppv->lpVtbl->MapUrlToZone)(
                 ppv,
                 a2,
                 &v9,
                 0);
    if ( Instance < 0 )
      v9 = 4;
  }
  if ( a4 )
  {
    *a4 = ppv;
  }
  else if ( ppv )
  {
    ((void (__fastcall *)(struct IInternetSecurityManager *))ppv->lpVtbl->Release)(ppv);
  }
  if ( a3 )
    *a3 = v9;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180029bf8  mov     rax, rsp
0x180029bfb  mov     [rax+10h], rbx
0x180029bff  mov     [rax+8], rcx
0x180029c03  push    rbp
0x180029c04  push    rsi
0x180029c05  push    rdi
0x180029c06  sub     rsp, 30h
0x180029c0a  mov     rbp, rdx
0x180029c0d  mov     qword ptr [rax+18h], 0
0x180029c15  xor     edx, edx; pUnkOuter
0x180029c17  mov     dword ptr [rax+8], 4
0x180029c1e  mov     rdi, r9
0x180029c21  lea     rax, [rax+18h]
0x180029c25  mov     rbx, r8
0x180029c28  mov     [rsp+48h+ppv], rax; ppv
0x180029c2d  lea     r9, IID_IInternetSecurityManager; riid
0x180029c34  lea     r8d, [rdx+1]; dwClsContext
0x180029c38  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180029c3f  call    cs:__imp_CoCreateInstance
0x180029c45  mov     esi, eax
0x180029c47  test    eax, eax
0x180029c49  js      short loc_180029C75
0x180029c4b  mov     rcx, [rsp+48h+arg_10]
0x180029c50  lea     r8, [rsp+48h+arg_0]
0x180029c55  xor     r9d, r9d
0x180029c58  mov     rdx, rbp
0x180029c5b  mov     rax, [rcx]
0x180029c5e  mov     rax, [rax+28h]
0x180029c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c67  mov     esi, eax
0x180029c69  test    eax, eax
0x180029c6b  jns     short loc_180029C75
0x180029c6d  mov     [rsp+48h+arg_0], 4
0x180029c75  test    rdi, rdi
0x180029c78  jz      short loc_180029C84
0x180029c7a  mov     rax, [rsp+48h+arg_10]
0x180029c7f  mov     [rdi], rax
0x180029c82  jmp     short loc_180029C9A
0x180029c84  mov     rcx, [rsp+48h+arg_10]
0x180029c89  test    rcx, rcx
0x180029c8c  jz      short loc_180029C9A
0x180029c8e  mov     rax, [rcx]
0x180029c91  mov     rax, [rax+10h]
0x180029c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c9a  test    rbx, rbx
0x180029c9d  jz      short loc_180029CA5
0x180029c9f  mov     eax, [rsp+48h+arg_0]
0x180029ca3  mov     [rbx], eax
0x180029ca5  mov     rbx, [rsp+48h+arg_8]
0x180029caa  mov     eax, esi
0x180029cac  add     rsp, 30h
0x180029cb0  pop     rdi
0x180029cb1  pop     rsi
0x180029cb2  pop     rbp
0x180029cb3  retn
```
