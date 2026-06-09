# ComUtils::ComLockableWrapper::Lock(void)

- ea: `0x180001240`
- end: `0x1800012c0`
- name: `?Lock@ComLockableWrapper@ComUtils@@QEAAJXZ`
- size: `128`
- prototype: `__int64 __fastcall(ComUtils::ComLockableWrapper *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006ba4`
- `0x180009820`
- `0x18000a444`
- `0x18000c8c0`

## callees

- `0x1800011f0`
- `0x180001240`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoLockObjectExternal` at `0x180001299`
- `ole32!CoLockObjectExternal` at `0x180001299`

## pseudocode

```c
__int64 __fastcall ComUtils::ComLockableWrapper::Lock(ComUtils::ComLockableWrapper *this)
{
  HRESULT v2; // ebx
  __int64 (__fastcall ***v3)(_QWORD, GUID *, LPUNKNOWN *); // rcx
  LPUNKNOWN pUnk; // [rsp+30h] [rbp+8h] BYREF

  v2 = ComUtils::ComApartmentVerifier::VerifyCurrentApartmentType((ComUtils::ComLockableWrapper *)((char *)this + 8));
  if ( v2 >= 0 )
  {
    v3 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *))this;
    v2 = -2147483634;
    if ( *(_QWORD *)this )
    {
      pUnk = 0;
      v2 = (**v3)(v3, &IID_IUnknown, &pUnk);
      if ( v2 >= 0 )
      {
        v2 = CoLockObjectExternal(pUnk, 1, 0);
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001240  mov     [rsp+arg_8], rbx
0x180001245  push    rdi
0x180001246  sub     rsp, 20h
0x18000124a  mov     rdi, rcx
0x18000124d  add     rcx, 8; this
0x180001251  call    ?VerifyCurrentApartmentType@ComApartmentVerifier@ComUtils@@QEAAJXZ; ComUtils::ComApartmentVerifier::VerifyCurrentApartmentType(void)
0x180001256  mov     ebx, eax
0x180001258  test    eax, eax
0x18000125a  js      short loc_1800012B3
0x18000125c  mov     rcx, [rdi]
0x18000125f  mov     ebx, 8000000Eh
0x180001264  test    rcx, rcx
0x180001267  jz      short loc_1800012B3
0x180001269  and     [rsp+28h+pUnk], 0
0x18000126f  lea     r8, [rsp+28h+pUnk]
0x180001274  mov     rax, [rcx]
0x180001277  lea     rdx, IID_IUnknown
0x18000127e  mov     rax, [rax]
0x180001281  call    cs:__guard_dispatch_icall_fptr
0x180001287  mov     ebx, eax
0x180001289  test    eax, eax
0x18000128b  js      short loc_1800012B3
0x18000128d  mov     rcx, [rsp+28h+pUnk]; pUnk
0x180001292  xor     r8d, r8d; fLastUnlockReleases
0x180001295  lea     edx, [r8+1]; fLock
0x180001299  call    cs:__imp_CoLockObjectExternal
0x18000129f  mov     rcx, [rsp+28h+pUnk]
0x1800012a4  mov     ebx, eax
0x1800012a6  mov     rax, [rcx]
0x1800012a9  mov     rax, [rax+10h]
0x1800012ad  call    cs:__guard_dispatch_icall_fptr
0x1800012b3  mov     eax, ebx
0x1800012b5  mov     rbx, [rsp+28h+arg_8]
0x1800012ba  add     rsp, 20h
0x1800012be  pop     rdi
0x1800012bf  retn
```
