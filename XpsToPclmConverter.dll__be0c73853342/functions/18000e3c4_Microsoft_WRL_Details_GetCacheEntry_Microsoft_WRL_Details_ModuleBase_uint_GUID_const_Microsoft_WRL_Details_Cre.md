# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000e3c4`
- end: `0x18000e553`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e220`

## callees

- `0x18000e3c4`
- `0x18000e5c8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e504`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e504`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e455`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e46a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e455`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e46a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e414`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e414`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e426`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e4df`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e426`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e4df`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000e4d0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000e4d0`

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
0x18000e3c4  mov     rax, rsp
0x18000e3c7  push    rbx
0x18000e3c8  push    rbp
0x18000e3c9  push    rsi
0x18000e3ca  push    rdi
0x18000e3cb  push    r14
0x18000e3cd  push    r15
0x18000e3cf  sub     rsp, 38h
0x18000e3d3  mov     rdi, r9
0x18000e3d6  mov     r15, r8
0x18000e3d9  mov     rbp, rdx
0x18000e3dc  mov     rsi, rcx
0x18000e3df  mov     r14, [rsp+68h+Ptr]
0x18000e3e7  mov     qword ptr [r14], 0
0x18000e3ee  mov     qword ptr [rax+28h], 0
0x18000e3f6  mov     rax, [r9+18h]
0x18000e3fa  mov     r10, [rax]
0x18000e3fd  test    r10, r10
0x18000e400  jz      short loc_18000E470
0x18000e402  mov     rax, [rcx]
0x18000e405  mov     rax, [rax+38h]
0x18000e409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e40e  mov     rbx, rax
0x18000e411  mov     rcx, rax; SRWLock
0x18000e414  call    cs:__imp_AcquireSRWLockShared
0x18000e41a  mov     rcx, [rdi+18h]
0x18000e41e  mov     rcx, [rcx]; Ptr
0x18000e421  test    rcx, rcx
0x18000e424  jz      short loc_18000E462
0x18000e426  call    cs:__imp_DecodePointer
0x18000e42c  mov     r9, rax
0x18000e42f  mov     [rsp+68h+Ptr], rax
0x18000e437  mov     rcx, [rax]
0x18000e43a  mov     rax, [rcx]
0x18000e43d  mov     r8, r14
0x18000e440  mov     rdx, r15
0x18000e443  mov     rcx, r9
0x18000e446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e44b  mov     edi, eax
0x18000e44d  test    rbx, rbx
0x18000e450  jz      short loc_18000E45B
0x18000e452  mov     rcx, rbx; SRWLock
0x18000e455  call    cs:__imp_ReleaseSRWLockShared
0x18000e45b  mov     eax, edi
0x18000e45d  jmp     loc_18000E546
0x18000e462  test    rbx, rbx
0x18000e465  jz      short loc_18000E470
0x18000e467  mov     rcx, rbx; SRWLock
0x18000e46a  call    cs:__imp_ReleaseSRWLockShared
0x18000e470  lea     r9, [rsp+68h+Ptr]
0x18000e478  mov     r8, r15
0x18000e47b  mov     rdx, rdi
0x18000e47e  mov     rcx, rbp
0x18000e481  mov     rax, [rdi]
0x18000e484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e489  test    eax, eax
0x18000e48b  js      loc_18000E546
0x18000e491  test    byte ptr [rbp+0], 4
0x18000e495  jnz     loc_18000E539
0x18000e49b  mov     rax, [rsi]
0x18000e49e  mov     rcx, rsi
0x18000e4a1  mov     rax, [rax+38h]
0x18000e4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4aa  mov     rdx, rax
0x18000e4ad  lea     rcx, [rsp+68h+SRWLock]
0x18000e4b5  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000e4ba  mov     rax, [rdi+18h]
0x18000e4be  mov     rcx, [rax]; Ptr
0x18000e4c1  test    rcx, rcx
0x18000e4c4  jnz     short loc_18000E4DF
0x18000e4c6  xor     ebx, ebx
0x18000e4c8  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000e4d0  call    cs:__imp_EncodePointer
0x18000e4d6  mov     rcx, [rdi+18h]
0x18000e4da  mov     [rcx], rax
0x18000e4dd  jmp     short loc_18000E4F7
0x18000e4df  call    cs:__imp_DecodePointer
0x18000e4e5  mov     rbx, rax
0x18000e4e8  mov     rcx, [rax]
0x18000e4eb  mov     rax, [rcx+8]
0x18000e4ef  mov     rcx, rbx
0x18000e4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4f7  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000e4ff  test    rcx, rcx
0x18000e502  jz      short loc_18000E50A
0x18000e504  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e50a  test    rbx, rbx
0x18000e50d  jz      short loc_18000E539
0x18000e50f  mov     rcx, [rsp+68h+Ptr]
0x18000e517  mov     rax, [rcx]
0x18000e51a  mov     rax, [rax+10h]
0x18000e51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e523  mov     rcx, [rsp+68h+Ptr]
0x18000e52b  mov     rax, [rcx]
0x18000e52e  mov     rax, [rax+10h]
0x18000e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e537  jmp     short loc_18000E541
0x18000e539  mov     rbx, [rsp+68h+Ptr]
0x18000e541  mov     [r14], rbx
0x18000e544  xor     eax, eax
0x18000e546  add     rsp, 38h
0x18000e54a  pop     r15
0x18000e54c  pop     r14
0x18000e54e  pop     rdi
0x18000e54f  pop     rsi
0x18000e550  pop     rbp
0x18000e551  pop     rbx
0x18000e552  retn
```
