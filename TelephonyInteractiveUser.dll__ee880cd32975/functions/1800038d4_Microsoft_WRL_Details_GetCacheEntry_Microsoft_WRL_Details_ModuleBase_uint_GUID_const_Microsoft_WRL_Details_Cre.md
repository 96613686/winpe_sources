# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800038d4`
- end: `0x180003a66`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004690`
- `0x180004840`

## callees

- `0x180001dc0`
- `0x1800038d4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800039e4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800039e4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003947`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800039f3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003947`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800039f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003a13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003a13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800039cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800039cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003973`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003988`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003973`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003988`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003935`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003935`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v13; // rdi
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+30h] [rbp-48h] BYREF

  Ptr = 0;
  *(_QWORD *)a5 = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, unsigned int *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              a3,
              a5);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return v11;
    }
    if ( v9 )
      ReleaseSRWLockShared(v9);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, PVOID *))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v13);
    v14 = **(void ***)a4[1].Data4;
    if ( v14 )
    {
      v15 = DecodePointer(v14);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v15 + 8LL))(v15);
    }
    else
    {
      v15 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    if ( !v15 )
    {
LABEL_17:
      v15 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    *(_QWORD *)a5 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800038d4  push    rbx
0x1800038d6  push    rbp
0x1800038d7  push    rsi
0x1800038d8  push    rdi
0x1800038d9  push    r14
0x1800038db  push    r15
0x1800038dd  sub     rsp, 48h
0x1800038e1  mov     rax, cs:__security_cookie
0x1800038e8  xor     rax, rsp
0x1800038eb  mov     [rsp+78h+var_40], rax
0x1800038f0  mov     r14, [rsp+78h+arg_20]
0x1800038f8  mov     rdi, rcx
0x1800038fb  mov     [rsp+78h+Ptr], 0
0x180003904  mov     rsi, r9
0x180003907  mov     r15, r8
0x18000390a  mov     rbp, rdx
0x18000390d  mov     qword ptr [r14], 0
0x180003914  mov     rax, [r9+18h]
0x180003918  mov     rcx, [rax]
0x18000391b  test    rcx, rcx
0x18000391e  jz      short loc_18000398E
0x180003920  mov     rax, [rdi]
0x180003923  mov     rcx, rdi
0x180003926  mov     rax, [rax+38h]
0x18000392a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000392f  mov     rcx, rax; SRWLock
0x180003932  mov     rbx, rax
0x180003935  call    cs:__imp_AcquireSRWLockShared
0x18000393b  mov     rcx, [rsi+18h]
0x18000393f  mov     rcx, [rcx]; Ptr
0x180003942  test    rcx, rcx
0x180003945  jz      short loc_180003980
0x180003947  call    cs:__imp_DecodePointer
0x18000394d  mov     [rsp+78h+Ptr], rax
0x180003952  mov     r8, r14
0x180003955  mov     r9, rax
0x180003958  mov     rdx, r15
0x18000395b  mov     rcx, [rax]
0x18000395e  mov     rax, [rcx]
0x180003961  mov     rcx, r9
0x180003964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003969  mov     edi, eax
0x18000396b  test    rbx, rbx
0x18000396e  jz      short loc_180003979
0x180003970  mov     rcx, rbx; SRWLock
0x180003973  call    cs:__imp_ReleaseSRWLockShared
0x180003979  mov     eax, edi
0x18000397b  jmp     loc_180003A4C
0x180003980  test    rbx, rbx
0x180003983  jz      short loc_18000398E
0x180003985  mov     rcx, rbx; SRWLock
0x180003988  call    cs:__imp_ReleaseSRWLockShared
0x18000398e  mov     rax, [rsi]
0x180003991  lea     r9, [rsp+78h+Ptr]
0x180003996  mov     r8, r15
0x180003999  mov     rdx, rsi
0x18000399c  mov     rcx, rbp
0x18000399f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a4  test    eax, eax
0x1800039a6  js      loc_180003A4C
0x1800039ac  test    byte ptr [rbp+0], 4
0x1800039b0  jnz     loc_180003A42
0x1800039b6  mov     rax, [rdi]
0x1800039b9  mov     rcx, rdi
0x1800039bc  mov     rax, [rax+38h]
0x1800039c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c5  mov     rcx, rax; SRWLock
0x1800039c8  mov     rdi, rax
0x1800039cb  call    cs:__imp_AcquireSRWLockExclusive
0x1800039d1  mov     rcx, [rsi+18h]
0x1800039d5  mov     rcx, [rcx]; Ptr
0x1800039d8  test    rcx, rcx
0x1800039db  jnz     short loc_1800039F3
0x1800039dd  mov     rcx, [rsp+78h+Ptr]; Ptr
0x1800039e2  xor     ebx, ebx
0x1800039e4  call    cs:__imp_EncodePointer
0x1800039ea  mov     rcx, [rsi+18h]
0x1800039ee  mov     [rcx], rax
0x1800039f1  jmp     short loc_180003A0B
0x1800039f3  call    cs:__imp_DecodePointer
0x1800039f9  mov     rbx, rax
0x1800039fc  mov     rcx, [rax]
0x1800039ff  mov     rax, [rcx+8]
0x180003a03  mov     rcx, rbx
0x180003a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0b  test    rdi, rdi
0x180003a0e  jz      short loc_180003A19
0x180003a10  mov     rcx, rdi; SRWLock
0x180003a13  call    cs:__imp_ReleaseSRWLockExclusive
0x180003a19  test    rbx, rbx
0x180003a1c  jz      short loc_180003A42
0x180003a1e  mov     rcx, [rsp+78h+Ptr]
0x180003a23  mov     rax, [rcx]
0x180003a26  mov     rax, [rax+10h]
0x180003a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a2f  mov     rcx, [rsp+78h+Ptr]
0x180003a34  mov     rax, [rcx]
0x180003a37  mov     rax, [rax+10h]
0x180003a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a40  jmp     short loc_180003A47
0x180003a42  mov     rbx, [rsp+78h+Ptr]
0x180003a47  mov     [r14], rbx
0x180003a4a  xor     eax, eax
0x180003a4c  mov     rcx, [rsp+78h+var_40]
0x180003a51  xor     rcx, rsp; StackCookie
0x180003a54  call    __security_check_cookie
0x180003a59  add     rsp, 48h
0x180003a5d  pop     r15
0x180003a5f  pop     r14
0x180003a61  pop     rdi
0x180003a62  pop     rsi
0x180003a63  pop     rbp
0x180003a64  pop     rbx
0x180003a65  retn
```
