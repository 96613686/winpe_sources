# ComUtils::ComLockableWrapper::Unlock(void)

- ea: `0x1800012c0`
- end: `0x180001343`
- name: `?Unlock@ComLockableWrapper@ComUtils@@QEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(ComUtils::ComLockableWrapper *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001edc`
- `0x1800020a8`
- `0x180006ca0`
- `0x180009820`
- `0x18000bb80`
- `0x18000c950`

## callees

- `0x1800011f0`
- `0x1800012c0`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoLockObjectExternal` at `0x180001318`
- `ole32!CoLockObjectExternal` at `0x180001318`

## pseudocode

```c
__int64 __fastcall ComUtils::ComLockableWrapper::Unlock(ComUtils::ComLockableWrapper *this)
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
        v2 = CoLockObjectExternal(pUnk, 0, 1);
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        *(_QWORD *)this = 0;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800012c0  mov     [rsp+arg_8], rbx
0x1800012c5  push    rdi
0x1800012c6  sub     rsp, 20h
0x1800012ca  mov     rdi, rcx
0x1800012cd  add     rcx, 8; this
0x1800012d1  call    ?VerifyCurrentApartmentType@ComApartmentVerifier@ComUtils@@QEAAJXZ; ComUtils::ComApartmentVerifier::VerifyCurrentApartmentType(void)
0x1800012d6  mov     ebx, eax
0x1800012d8  test    eax, eax
0x1800012da  js      short loc_180001336
0x1800012dc  mov     rcx, [rdi]
0x1800012df  mov     ebx, 8000000Eh
0x1800012e4  test    rcx, rcx
0x1800012e7  jz      short loc_180001336
0x1800012e9  and     [rsp+28h+pUnk], 0
0x1800012ef  lea     r8, [rsp+28h+pUnk]
0x1800012f4  mov     rax, [rcx]
0x1800012f7  lea     rdx, IID_IUnknown
0x1800012fe  mov     rax, [rax]
0x180001301  call    cs:__guard_dispatch_icall_fptr
0x180001307  mov     ebx, eax
0x180001309  test    eax, eax
0x18000130b  js      short loc_180001336
0x18000130d  mov     rcx, [rsp+28h+pUnk]; pUnk
0x180001312  xor     edx, edx; fLock
0x180001314  lea     r8d, [rdx+1]; fLastUnlockReleases
0x180001318  call    cs:__imp_CoLockObjectExternal
0x18000131e  mov     rcx, [rsp+28h+pUnk]
0x180001323  mov     ebx, eax
0x180001325  mov     rax, [rcx]
0x180001328  mov     rax, [rax+10h]
0x18000132c  call    cs:__guard_dispatch_icall_fptr
0x180001332  and     qword ptr [rdi], 0
0x180001336  mov     eax, ebx
0x180001338  mov     rbx, [rsp+28h+arg_8]
0x18000133d  add     rsp, 20h
0x180001341  pop     rdi
0x180001342  retn
```
