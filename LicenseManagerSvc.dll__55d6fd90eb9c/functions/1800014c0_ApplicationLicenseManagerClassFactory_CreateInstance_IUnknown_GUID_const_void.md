# ApplicationLicenseManagerClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800014c0`
- end: `0x180001543`
- name: `?CreateInstance@ApplicationLicenseManagerClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `131`
- prototype: `__int64 __fastcall(ApplicationLicenseManagerClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800014c0`
- `0x18000154c`
- `0x180018010`

## import_xrefs

- `LicenseManager!ServiceCreateApplicationLicenseManager` at `0x1800014ea`
- `LicenseManager!ServiceCreateApplicationLicenseManager` at `0x1800014ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplicationLicenseManagerClassFactory::CreateInstance(
        ApplicationLicenseManagerClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 (__fastcall ***v9)(_QWORD, const struct _GUID *, void **); // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
    return 2147746064LL;
  v9 = 0;
  Microsoft::WRL::ComPtr<IApplicationLicenseManager>::InternalRelease(&v9);
  v6 = ServiceCreateApplicationLicenseManager(&v9);
  if ( v6 >= 0 )
    v6 = (**v9)(v9, a3, a4);
  v7 = v9;
  if ( v9 )
  {
    v9 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v7)[2])(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800014c0  push    rbx
0x1800014c2  push    rbp
0x1800014c3  push    rsi
0x1800014c4  push    rdi
0x1800014c5  sub     rsp, 28h
0x1800014c9  mov     rdi, r9
0x1800014cc  mov     rsi, r8
0x1800014cf  test    rdx, rdx
0x1800014d2  jnz     short loc_180001535
0x1800014d4  xor     ebp, ebp
0x1800014d6  mov     [rsp+48h+arg_8], rbp
0x1800014db  lea     rcx, [rsp+48h+arg_8]
0x1800014e0  call    ?InternalRelease@?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IApplicationLicenseManager>::InternalRelease(void)
0x1800014e5  lea     rcx, [rsp+48h+arg_8]
0x1800014ea  call    cs:__imp_ServiceCreateApplicationLicenseManager
0x1800014f0  mov     ebx, eax
0x1800014f2  test    eax, eax
0x1800014f4  js      short loc_18000150E
0x1800014f6  mov     rcx, [rsp+48h+arg_8]
0x1800014fb  mov     rax, [rcx]
0x1800014fe  mov     r8, rdi
0x180001501  mov     rdx, rsi
0x180001504  mov     rax, [rax]
0x180001507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000150c  mov     ebx, eax
0x18000150e  mov     rcx, [rsp+48h+arg_8]
0x180001513  test    rcx, rcx
0x180001516  jz      short loc_18000152A
0x180001518  mov     [rsp+48h+arg_8], rbp
0x18000151d  mov     rax, [rcx]
0x180001520  mov     rax, [rax+10h]
0x180001524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001529  nop
0x18000152a  mov     eax, ebx
0x18000152c  add     rsp, 28h
0x180001530  pop     rdi
0x180001531  pop     rsi
0x180001532  pop     rbp
0x180001533  pop     rbx
0x180001534  retn
0x180001535  mov     eax, 80040110h
0x18000153a  add     rsp, 28h
0x18000153e  pop     rdi
0x18000153f  pop     rsi
0x180001540  pop     rbp
0x180001541  pop     rbx
0x180001542  retn
```
