# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180008b54`
- end: `0x180008ce3`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000797c`

## callees

- `0x180008b54`
- `0x180008f3c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008ba4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008be5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008bfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008be5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008bfa`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008c60`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008c60`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008bb6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008c6f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008bb6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008c6f`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v9; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  __int64 v14; // rax
  void *v15; // rcx
  PVOID v16; // rbx
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

  v9 = Ptr;
  *Ptr = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v9);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      return v12;
    }
    if ( v10 )
      ReleaseSRWLockShared(v10);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, _QWORD **))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v14 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v14);
    v15 = **(void ***)a4[1].Data4;
    if ( v15 )
    {
      v16 = DecodePointer(v15);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v16 + 8LL))(v16);
    }
    else
    {
      v16 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( !v16 )
    {
LABEL_17:
      v16 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
    }
    *v9 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008b54  mov     rax, rsp
0x180008b57  push    rbx
0x180008b58  push    rbp
0x180008b59  push    rsi
0x180008b5a  push    rdi
0x180008b5b  push    r14
0x180008b5d  push    r15
0x180008b5f  sub     rsp, 38h
0x180008b63  mov     rdi, r9
0x180008b66  mov     r15, r8
0x180008b69  mov     rbp, rdx
0x180008b6c  mov     rsi, rcx
0x180008b6f  mov     r14, [rsp+68h+Ptr]
0x180008b77  mov     qword ptr [r14], 0
0x180008b7e  mov     qword ptr [rax+28h], 0
0x180008b86  mov     rax, [r9+18h]
0x180008b8a  mov     r10, [rax]
0x180008b8d  test    r10, r10
0x180008b90  jz      short loc_180008C00
0x180008b92  mov     rax, [rcx]
0x180008b95  mov     rax, [rax+38h]
0x180008b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9e  mov     rbx, rax
0x180008ba1  mov     rcx, rax; SRWLock
0x180008ba4  call    cs:__imp_AcquireSRWLockShared
0x180008baa  mov     rcx, [rdi+18h]
0x180008bae  mov     rcx, [rcx]; Ptr
0x180008bb1  test    rcx, rcx
0x180008bb4  jz      short loc_180008BF2
0x180008bb6  call    cs:__imp_DecodePointer
0x180008bbc  mov     r9, rax
0x180008bbf  mov     [rsp+68h+Ptr], rax
0x180008bc7  mov     rcx, [rax]
0x180008bca  mov     rax, [rcx]
0x180008bcd  mov     r8, r14
0x180008bd0  mov     rdx, r15
0x180008bd3  mov     rcx, r9
0x180008bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bdb  mov     edi, eax
0x180008bdd  test    rbx, rbx
0x180008be0  jz      short loc_180008BEB
0x180008be2  mov     rcx, rbx; SRWLock
0x180008be5  call    cs:__imp_ReleaseSRWLockShared
0x180008beb  mov     eax, edi
0x180008bed  jmp     loc_180008CD6
0x180008bf2  test    rbx, rbx
0x180008bf5  jz      short loc_180008C00
0x180008bf7  mov     rcx, rbx; SRWLock
0x180008bfa  call    cs:__imp_ReleaseSRWLockShared
0x180008c00  lea     r9, [rsp+68h+Ptr]
0x180008c08  mov     r8, r15
0x180008c0b  mov     rdx, rdi
0x180008c0e  mov     rcx, rbp
0x180008c11  mov     rax, [rdi]
0x180008c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c19  test    eax, eax
0x180008c1b  js      loc_180008CD6
0x180008c21  test    byte ptr [rbp+0], 4
0x180008c25  jnz     loc_180008CC9
0x180008c2b  mov     rax, [rsi]
0x180008c2e  mov     rcx, rsi
0x180008c31  mov     rax, [rax+38h]
0x180008c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3a  mov     rdx, rax
0x180008c3d  lea     rcx, [rsp+68h+SRWLock]
0x180008c45  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180008c4a  mov     rax, [rdi+18h]
0x180008c4e  mov     rcx, [rax]; Ptr
0x180008c51  test    rcx, rcx
0x180008c54  jnz     short loc_180008C6F
0x180008c56  xor     ebx, ebx
0x180008c58  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180008c60  call    cs:__imp_EncodePointer
0x180008c66  mov     rcx, [rdi+18h]
0x180008c6a  mov     [rcx], rax
0x180008c6d  jmp     short loc_180008C87
0x180008c6f  call    cs:__imp_DecodePointer
0x180008c75  mov     rbx, rax
0x180008c78  mov     rcx, [rax]
0x180008c7b  mov     rax, [rcx+8]
0x180008c7f  mov     rcx, rbx
0x180008c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c87  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180008c8f  test    rcx, rcx
0x180008c92  jz      short loc_180008C9A
0x180008c94  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c9a  test    rbx, rbx
0x180008c9d  jz      short loc_180008CC9
0x180008c9f  mov     rcx, [rsp+68h+Ptr]
0x180008ca7  mov     rax, [rcx]
0x180008caa  mov     rax, [rax+10h]
0x180008cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb3  mov     rcx, [rsp+68h+Ptr]
0x180008cbb  mov     rax, [rcx]
0x180008cbe  mov     rax, [rax+10h]
0x180008cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc7  jmp     short loc_180008CD1
0x180008cc9  mov     rbx, [rsp+68h+Ptr]
0x180008cd1  mov     [r14], rbx
0x180008cd4  xor     eax, eax
0x180008cd6  add     rsp, 38h
0x180008cda  pop     r15
0x180008cdc  pop     r14
0x180008cde  pop     rdi
0x180008cdf  pop     rsi
0x180008ce0  pop     rbp
0x180008ce1  pop     rbx
0x180008ce2  retn
```
