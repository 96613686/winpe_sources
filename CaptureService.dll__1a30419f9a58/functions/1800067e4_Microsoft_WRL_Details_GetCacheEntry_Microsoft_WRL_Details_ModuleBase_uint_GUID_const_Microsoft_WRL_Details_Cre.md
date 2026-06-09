# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800067e4`
- end: `0x18000696b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003f18`

## callees

- `0x1800067e4`
- `0x1800078b4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006836`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006836`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000691f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000691f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006878`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000688d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006878`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000688d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006848`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800068fd`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006848`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800068fd`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800068ee`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800068ee`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        PSRWLOCK SRWLock)
{
  PSRWLOCK v8; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  __int64 v13; // rax
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v8 = SRWLock;
  SRWLock->Ptr = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, PSRWLOCK))Ptr)(
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
    v13 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v13);
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
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
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
    v8->Ptr = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800067e4  mov     rax, rsp
0x1800067e7  mov     [rax+8], rbx
0x1800067eb  mov     [rax+10h], rbp
0x1800067ef  mov     [rax+18h], r8
0x1800067f3  push    rsi
0x1800067f4  push    rdi
0x1800067f5  push    r14
0x1800067f7  sub     rsp, 30h
0x1800067fb  mov     rdi, r9
0x1800067fe  mov     rbp, rdx
0x180006801  mov     rsi, rcx
0x180006804  mov     r14, [rsp+48h+SRWLock]
0x180006809  mov     qword ptr [r14], 0
0x180006810  mov     qword ptr [rax+18h], 0
0x180006818  mov     rax, [r9+18h]
0x18000681c  mov     r8, [rax]
0x18000681f  test    r8, r8
0x180006822  jz      short loc_180006893
0x180006824  mov     rax, [rcx]
0x180006827  mov     rax, [rax+38h]
0x18000682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006830  mov     rbx, rax
0x180006833  mov     rcx, rax; SRWLock
0x180006836  call    cs:__imp_AcquireSRWLockShared
0x18000683c  mov     rcx, [rdi+18h]
0x180006840  mov     rcx, [rcx]; Ptr
0x180006843  test    rcx, rcx
0x180006846  jz      short loc_180006885
0x180006848  call    cs:__imp_DecodePointer
0x18000684e  mov     r9, rax
0x180006851  mov     [rsp+48h+Ptr], rax
0x180006856  mov     rcx, [rax]
0x180006859  mov     rax, [rcx]
0x18000685c  mov     r8, r14
0x18000685f  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180006866  mov     rcx, r9
0x180006869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000686e  mov     edi, eax
0x180006870  test    rbx, rbx
0x180006873  jz      short loc_18000687E
0x180006875  mov     rcx, rbx; SRWLock
0x180006878  call    cs:__imp_ReleaseSRWLockShared
0x18000687e  mov     eax, edi
0x180006880  jmp     loc_180006958
0x180006885  test    rbx, rbx
0x180006888  jz      short loc_180006893
0x18000688a  mov     rcx, rbx; SRWLock
0x18000688d  call    cs:__imp_ReleaseSRWLockShared
0x180006893  lea     r9, [rsp+48h+Ptr]
0x180006898  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x18000689f  mov     rdx, rdi
0x1800068a2  mov     rcx, rbp
0x1800068a5  mov     rax, [rdi]
0x1800068a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ad  test    eax, eax
0x1800068af  js      loc_180006958
0x1800068b5  test    byte ptr [rbp+0], 4
0x1800068b9  jnz     loc_18000694E
0x1800068bf  mov     rax, [rsi]
0x1800068c2  mov     rcx, rsi
0x1800068c5  mov     rax, [rax+38h]
0x1800068c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ce  mov     rdx, rax
0x1800068d1  lea     rcx, [rsp+48h+SRWLock]
0x1800068d6  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800068db  mov     rax, [rdi+18h]
0x1800068df  mov     rcx, [rax]; Ptr
0x1800068e2  test    rcx, rcx
0x1800068e5  jnz     short loc_1800068FD
0x1800068e7  xor     ebx, ebx
0x1800068e9  mov     rcx, [rsp+48h+Ptr]; Ptr
0x1800068ee  call    cs:__imp_EncodePointer
0x1800068f4  mov     rcx, [rdi+18h]
0x1800068f8  mov     [rcx], rax
0x1800068fb  jmp     short loc_180006915
0x1800068fd  call    cs:__imp_DecodePointer
0x180006903  mov     rbx, rax
0x180006906  mov     rcx, [rax]
0x180006909  mov     rax, [rcx+8]
0x18000690d  mov     rcx, rbx
0x180006910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006915  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x18000691a  test    rcx, rcx
0x18000691d  jz      short loc_180006925
0x18000691f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006925  test    rbx, rbx
0x180006928  jz      short loc_18000694E
0x18000692a  mov     rcx, [rsp+48h+Ptr]
0x18000692f  mov     rax, [rcx]
0x180006932  mov     rax, [rax+10h]
0x180006936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693b  mov     rcx, [rsp+48h+Ptr]
0x180006940  mov     rax, [rcx]
0x180006943  mov     rax, [rax+10h]
0x180006947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694c  jmp     short loc_180006953
0x18000694e  mov     rbx, [rsp+48h+Ptr]
0x180006953  mov     [r14], rbx
0x180006956  xor     eax, eax
0x180006958  mov     rbx, [rsp+48h+arg_0]
0x18000695d  mov     rbp, [rsp+48h+arg_8]
0x180006962  add     rsp, 30h
0x180006966  pop     r14
0x180006968  pop     rdi
0x180006969  pop     rsi
0x18000696a  retn
```
