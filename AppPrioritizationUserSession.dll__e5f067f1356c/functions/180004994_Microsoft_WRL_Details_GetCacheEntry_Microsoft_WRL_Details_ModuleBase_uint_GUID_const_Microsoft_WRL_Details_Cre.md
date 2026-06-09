# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180004994`
- end: `0x180004b26`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800073f0`
- `0x1800075b0`

## callees

- `0x180002650`
- `0x180004994`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800049f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800049f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004a8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ad3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004ad3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004a33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004a48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004a33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004a48`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004a07`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004ab3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004a07`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004ab3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180004aa4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180004aa4`

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

  *(_QWORD *)a5 = 0;
  Ptr = 0;
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
0x180004994  push    rbx
0x180004996  push    rbp
0x180004997  push    rsi
0x180004998  push    rdi
0x180004999  push    r14
0x18000499b  push    r15
0x18000499d  sub     rsp, 48h
0x1800049a1  mov     rax, cs:__security_cookie
0x1800049a8  xor     rax, rsp
0x1800049ab  mov     [rsp+78h+var_40], rax
0x1800049b0  mov     rsi, r9
0x1800049b3  mov     r15, r8
0x1800049b6  mov     rbp, rdx
0x1800049b9  mov     rdi, rcx
0x1800049bc  mov     r14, [rsp+78h+arg_20]
0x1800049c4  mov     qword ptr [r14], 0
0x1800049cb  mov     [rsp+78h+Ptr], 0
0x1800049d4  mov     rax, [r9+18h]
0x1800049d8  mov     rcx, [rax]
0x1800049db  test    rcx, rcx
0x1800049de  jz      short loc_180004A4E
0x1800049e0  mov     rax, [rdi]
0x1800049e3  mov     rcx, rdi
0x1800049e6  mov     rax, [rax+38h]
0x1800049ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ef  mov     rbx, rax
0x1800049f2  mov     rcx, rax; SRWLock
0x1800049f5  call    cs:__imp_AcquireSRWLockShared
0x1800049fb  mov     rcx, [rsi+18h]
0x1800049ff  mov     rcx, [rcx]; Ptr
0x180004a02  test    rcx, rcx
0x180004a05  jz      short loc_180004A40
0x180004a07  call    cs:__imp_DecodePointer
0x180004a0d  mov     r9, rax
0x180004a10  mov     [rsp+78h+Ptr], rax
0x180004a15  mov     rcx, [rax]
0x180004a18  mov     rax, [rcx]
0x180004a1b  mov     r8, r14
0x180004a1e  mov     rdx, r15
0x180004a21  mov     rcx, r9
0x180004a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a29  mov     edi, eax
0x180004a2b  test    rbx, rbx
0x180004a2e  jz      short loc_180004A39
0x180004a30  mov     rcx, rbx; SRWLock
0x180004a33  call    cs:__imp_ReleaseSRWLockShared
0x180004a39  mov     eax, edi
0x180004a3b  jmp     loc_180004B0C
0x180004a40  test    rbx, rbx
0x180004a43  jz      short loc_180004A4E
0x180004a45  mov     rcx, rbx; SRWLock
0x180004a48  call    cs:__imp_ReleaseSRWLockShared
0x180004a4e  lea     r9, [rsp+78h+Ptr]
0x180004a53  mov     r8, r15
0x180004a56  mov     rdx, rsi
0x180004a59  mov     rcx, rbp
0x180004a5c  mov     rax, [rsi]
0x180004a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a64  test    eax, eax
0x180004a66  js      loc_180004B0C
0x180004a6c  test    byte ptr [rbp+0], 4
0x180004a70  jnz     loc_180004B02
0x180004a76  mov     rax, [rdi]
0x180004a79  mov     rcx, rdi
0x180004a7c  mov     rax, [rax+38h]
0x180004a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a85  mov     rdi, rax
0x180004a88  mov     rcx, rax; SRWLock
0x180004a8b  call    cs:__imp_AcquireSRWLockExclusive
0x180004a91  mov     rcx, [rsi+18h]
0x180004a95  mov     rcx, [rcx]; Ptr
0x180004a98  test    rcx, rcx
0x180004a9b  jnz     short loc_180004AB3
0x180004a9d  xor     ebx, ebx
0x180004a9f  mov     rcx, [rsp+78h+Ptr]; Ptr
0x180004aa4  call    cs:__imp_EncodePointer
0x180004aaa  mov     rcx, [rsi+18h]
0x180004aae  mov     [rcx], rax
0x180004ab1  jmp     short loc_180004ACB
0x180004ab3  call    cs:__imp_DecodePointer
0x180004ab9  mov     rbx, rax
0x180004abc  mov     rcx, [rax]
0x180004abf  mov     rax, [rcx+8]
0x180004ac3  mov     rcx, rbx
0x180004ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004acb  test    rdi, rdi
0x180004ace  jz      short loc_180004AD9
0x180004ad0  mov     rcx, rdi; SRWLock
0x180004ad3  call    cs:__imp_ReleaseSRWLockExclusive
0x180004ad9  test    rbx, rbx
0x180004adc  jz      short loc_180004B02
0x180004ade  mov     rcx, [rsp+78h+Ptr]
0x180004ae3  mov     rax, [rcx]
0x180004ae6  mov     rax, [rax+10h]
0x180004aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aef  mov     rcx, [rsp+78h+Ptr]
0x180004af4  mov     rax, [rcx]
0x180004af7  mov     rax, [rax+10h]
0x180004afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b00  jmp     short loc_180004B07
0x180004b02  mov     rbx, [rsp+78h+Ptr]
0x180004b07  mov     [r14], rbx
0x180004b0a  xor     eax, eax
0x180004b0c  mov     rcx, [rsp+78h+var_40]
0x180004b11  xor     rcx, rsp; StackCookie
0x180004b14  call    __security_check_cookie
0x180004b19  add     rsp, 48h
0x180004b1d  pop     r15
0x180004b1f  pop     r14
0x180004b21  pop     rdi
0x180004b22  pop     rsi
0x180004b23  pop     rbp
0x180004b24  pop     rbx
0x180004b25  retn
```
