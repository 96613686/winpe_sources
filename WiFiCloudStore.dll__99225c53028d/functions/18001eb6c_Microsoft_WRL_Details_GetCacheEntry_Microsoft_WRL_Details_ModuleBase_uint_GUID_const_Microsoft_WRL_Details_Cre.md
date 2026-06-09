# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18001eb6c`
- end: `0x18001ecfb`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001eab8`
- `0x18002bb60`

## callees

- `0x18001eb6c`
- `0x18002c460`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ebfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ec12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ebfd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ec12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ecac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ecac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001ebbc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001ebbc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001ebce`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001ec87`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001ebce`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001ec87`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001ec78`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001ec78`

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
0x18001eb6c  mov     rax, rsp
0x18001eb6f  push    rbx
0x18001eb70  push    rbp
0x18001eb71  push    rsi
0x18001eb72  push    rdi
0x18001eb73  push    r14
0x18001eb75  push    r15
0x18001eb77  sub     rsp, 38h
0x18001eb7b  mov     rdi, r9
0x18001eb7e  mov     r15, r8
0x18001eb81  mov     rbp, rdx
0x18001eb84  mov     rsi, rcx
0x18001eb87  mov     r14, [rsp+68h+Ptr]
0x18001eb8f  mov     qword ptr [r14], 0
0x18001eb96  mov     qword ptr [rax+28h], 0
0x18001eb9e  mov     rax, [r9+18h]
0x18001eba2  mov     r10, [rax]
0x18001eba5  test    r10, r10
0x18001eba8  jz      short loc_18001EC18
0x18001ebaa  mov     rax, [rcx]
0x18001ebad  mov     rax, [rax+38h]
0x18001ebb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebb6  mov     rbx, rax
0x18001ebb9  mov     rcx, rax; SRWLock
0x18001ebbc  call    cs:__imp_AcquireSRWLockShared
0x18001ebc2  mov     rcx, [rdi+18h]
0x18001ebc6  mov     rcx, [rcx]; Ptr
0x18001ebc9  test    rcx, rcx
0x18001ebcc  jz      short loc_18001EC0A
0x18001ebce  call    cs:__imp_DecodePointer
0x18001ebd4  mov     r9, rax
0x18001ebd7  mov     [rsp+68h+Ptr], rax
0x18001ebdf  mov     rcx, [rax]
0x18001ebe2  mov     rax, [rcx]
0x18001ebe5  mov     r8, r14
0x18001ebe8  mov     rdx, r15
0x18001ebeb  mov     rcx, r9
0x18001ebee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebf3  mov     edi, eax
0x18001ebf5  test    rbx, rbx
0x18001ebf8  jz      short loc_18001EC03
0x18001ebfa  mov     rcx, rbx; SRWLock
0x18001ebfd  call    cs:__imp_ReleaseSRWLockShared
0x18001ec03  mov     eax, edi
0x18001ec05  jmp     loc_18001ECEE
0x18001ec0a  test    rbx, rbx
0x18001ec0d  jz      short loc_18001EC18
0x18001ec0f  mov     rcx, rbx; SRWLock
0x18001ec12  call    cs:__imp_ReleaseSRWLockShared
0x18001ec18  lea     r9, [rsp+68h+Ptr]
0x18001ec20  mov     r8, r15
0x18001ec23  mov     rdx, rdi
0x18001ec26  mov     rcx, rbp
0x18001ec29  mov     rax, [rdi]
0x18001ec2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec31  test    eax, eax
0x18001ec33  js      loc_18001ECEE
0x18001ec39  test    byte ptr [rbp+0], 4
0x18001ec3d  jnz     loc_18001ECE1
0x18001ec43  mov     rax, [rsi]
0x18001ec46  mov     rcx, rsi
0x18001ec49  mov     rax, [rax+38h]
0x18001ec4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec52  mov     rdx, rax
0x18001ec55  lea     rcx, [rsp+68h+SRWLock]
0x18001ec5d  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001ec62  mov     rax, [rdi+18h]
0x18001ec66  mov     rcx, [rax]; Ptr
0x18001ec69  test    rcx, rcx
0x18001ec6c  jnz     short loc_18001EC87
0x18001ec6e  xor     ebx, ebx
0x18001ec70  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18001ec78  call    cs:__imp_EncodePointer
0x18001ec7e  mov     rcx, [rdi+18h]
0x18001ec82  mov     [rcx], rax
0x18001ec85  jmp     short loc_18001EC9F
0x18001ec87  call    cs:__imp_DecodePointer
0x18001ec8d  mov     rbx, rax
0x18001ec90  mov     rcx, [rax]
0x18001ec93  mov     rax, [rcx+8]
0x18001ec97  mov     rcx, rbx
0x18001ec9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec9f  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18001eca7  test    rcx, rcx
0x18001ecaa  jz      short loc_18001ECB2
0x18001ecac  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ecb2  test    rbx, rbx
0x18001ecb5  jz      short loc_18001ECE1
0x18001ecb7  mov     rcx, [rsp+68h+Ptr]
0x18001ecbf  mov     rax, [rcx]
0x18001ecc2  mov     rax, [rax+10h]
0x18001ecc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eccb  mov     rcx, [rsp+68h+Ptr]
0x18001ecd3  mov     rax, [rcx]
0x18001ecd6  mov     rax, [rax+10h]
0x18001ecda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecdf  jmp     short loc_18001ECE9
0x18001ece1  mov     rbx, [rsp+68h+Ptr]
0x18001ece9  mov     [r14], rbx
0x18001ecec  xor     eax, eax
0x18001ecee  add     rsp, 38h
0x18001ecf2  pop     r15
0x18001ecf4  pop     r14
0x18001ecf6  pop     rdi
0x18001ecf7  pop     rsi
0x18001ecf8  pop     rbp
0x18001ecf9  pop     rbx
0x18001ecfa  retn
```
