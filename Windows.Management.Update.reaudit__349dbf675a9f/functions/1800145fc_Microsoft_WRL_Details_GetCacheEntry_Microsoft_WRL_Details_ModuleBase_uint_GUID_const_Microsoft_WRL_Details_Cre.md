# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800145fc`
- end: `0x1800147af`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014464`

## callees

- `0x1800145fc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001475c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001475c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001464c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001464c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014704`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014704`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001469a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800146b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001469a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800146b5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180014721`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180014721`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014664`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014736`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014664`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180014736`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  const struct Microsoft::WRL::Details::CreatorMap *v8; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  PVOID v13; // rbx
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v8 = a5;
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
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              &GUID_00000035_0000_0000_c000_000000000046,
              v8);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return v11;
    }
    if ( v9 )
      ReleaseSRWLockShared(v9);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, GUID *, PVOID *))&a4->Data1)(
             a2,
             a4,
             &GUID_00000035_0000_0000_c000_000000000046,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v13 = 0;
    v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v14);
    v15 = **(void ***)a4[1].Data4;
    if ( v15 )
    {
      v13 = DecodePointer(v15);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v13 + 8LL))(v13);
    }
    else
    {
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    if ( !v13 )
    {
LABEL_17:
      v13 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    *(_QWORD *)v8 = v13;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800145fc  mov     rax, rsp
0x1800145ff  mov     [rax+8], rbx
0x180014603  mov     [rax+10h], rbp
0x180014607  mov     [rax+18h], r8
0x18001460b  push    rsi
0x18001460c  push    rdi
0x18001460d  push    r14
0x18001460f  sub     rsp, 30h
0x180014613  mov     rdi, r9
0x180014616  mov     rbp, rdx
0x180014619  mov     rsi, rcx
0x18001461c  mov     r14, [rsp+48h+arg_20]
0x180014621  and     qword ptr [r14], 0
0x180014625  and     qword ptr [rax+18h], 0
0x18001462a  mov     rax, [r9+18h]
0x18001462e  mov     r8, [rax]
0x180014631  test    r8, r8
0x180014634  jz      loc_1800146C1
0x18001463a  mov     rax, [rcx]
0x18001463d  mov     rax, [rax+38h]
0x180014641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014646  mov     rbx, rax
0x180014649  mov     rcx, rax; SRWLock
0x18001464c  call    cs:__imp_AcquireSRWLockShared
0x180014653  nop     dword ptr [rax+rax+00h]
0x180014658  mov     rcx, [rdi+18h]
0x18001465c  mov     rcx, [rcx]; Ptr
0x18001465f  test    rcx, rcx
0x180014662  jz      short loc_1800146AD
0x180014664  call    cs:__imp_DecodePointer
0x18001466b  nop     dword ptr [rax+rax+00h]
0x180014670  mov     r9, rax
0x180014673  mov     [rsp+48h+Ptr], rax
0x180014678  mov     rcx, [rax]
0x18001467b  mov     rax, [rcx]
0x18001467e  mov     r8, r14
0x180014681  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180014688  mov     rcx, r9
0x18001468b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014690  mov     edi, eax
0x180014692  test    rbx, rbx
0x180014695  jz      short loc_1800146A6
0x180014697  mov     rcx, rbx; SRWLock
0x18001469a  call    cs:__imp_ReleaseSRWLockShared
0x1800146a1  nop     dword ptr [rax+rax+00h]
0x1800146a6  mov     eax, edi
0x1800146a8  jmp     loc_18001479B
0x1800146ad  test    rbx, rbx
0x1800146b0  jz      short loc_1800146C1
0x1800146b2  mov     rcx, rbx; SRWLock
0x1800146b5  call    cs:__imp_ReleaseSRWLockShared
0x1800146bc  nop     dword ptr [rax+rax+00h]
0x1800146c1  lea     r9, [rsp+48h+Ptr]
0x1800146c6  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x1800146cd  mov     rdx, rdi
0x1800146d0  mov     rcx, rbp
0x1800146d3  mov     rax, [rdi]
0x1800146d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146db  test    eax, eax
0x1800146dd  js      loc_18001479B
0x1800146e3  test    byte ptr [rbp+0], 4
0x1800146e7  jnz     loc_180014791
0x1800146ed  xor     ebx, ebx
0x1800146ef  mov     rax, [rsi]
0x1800146f2  mov     rcx, rsi
0x1800146f5  mov     rax, [rax+38h]
0x1800146f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146fe  mov     rsi, rax
0x180014701  mov     rcx, rax; SRWLock
0x180014704  call    cs:__imp_AcquireSRWLockExclusive
0x18001470b  nop     dword ptr [rax+rax+00h]
0x180014710  mov     rcx, [rdi+18h]
0x180014714  mov     rcx, [rcx]; Ptr
0x180014717  test    rcx, rcx
0x18001471a  jnz     short loc_180014736
0x18001471c  mov     rcx, [rsp+48h+Ptr]; Ptr
0x180014721  call    cs:__imp_EncodePointer
0x180014728  nop     dword ptr [rax+rax+00h]
0x18001472d  mov     rcx, [rdi+18h]
0x180014731  mov     [rcx], rax
0x180014734  jmp     short loc_180014754
0x180014736  call    cs:__imp_DecodePointer
0x18001473d  nop     dword ptr [rax+rax+00h]
0x180014742  mov     rbx, rax
0x180014745  mov     rcx, [rax]
0x180014748  mov     rax, [rcx+8]
0x18001474c  mov     rcx, rbx
0x18001474f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014754  test    rsi, rsi
0x180014757  jz      short loc_180014768
0x180014759  mov     rcx, rsi; SRWLock
0x18001475c  call    cs:__imp_ReleaseSRWLockExclusive
0x180014763  nop     dword ptr [rax+rax+00h]
0x180014768  test    rbx, rbx
0x18001476b  jz      short loc_180014791
0x18001476d  mov     rcx, [rsp+48h+Ptr]
0x180014772  mov     rax, [rcx]
0x180014775  mov     rax, [rax+10h]
0x180014779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001477e  mov     rcx, [rsp+48h+Ptr]
0x180014783  mov     rax, [rcx]
0x180014786  mov     rax, [rax+10h]
0x18001478a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001478f  jmp     short loc_180014796
0x180014791  mov     rbx, [rsp+48h+Ptr]
0x180014796  mov     [r14], rbx
0x180014799  xor     eax, eax
0x18001479b  mov     rbx, [rsp+48h+arg_0]
0x1800147a0  mov     rbp, [rsp+48h+arg_8]
0x1800147a5  add     rsp, 30h
0x1800147a9  pop     r14
0x1800147ab  pop     rdi
0x1800147ac  pop     rsi
0x1800147ad  retn
```
