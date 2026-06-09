# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180008814`
- end: `0x1800089a3`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007d08`
- `0x180007e80`

## callees

- `0x180008814`
- `0x180008b08`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008864`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008864`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800088a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800088ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800088a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800088ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008954`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008954`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008876`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000892f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008876`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000892f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008920`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008920`

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
0x180008814  mov     rax, rsp
0x180008817  push    rbx
0x180008818  push    rbp
0x180008819  push    rsi
0x18000881a  push    rdi
0x18000881b  push    r14
0x18000881d  push    r15
0x18000881f  sub     rsp, 38h
0x180008823  mov     rdi, r9
0x180008826  mov     r15, r8
0x180008829  mov     rbp, rdx
0x18000882c  mov     rsi, rcx
0x18000882f  mov     r14, [rsp+68h+Ptr]
0x180008837  mov     qword ptr [r14], 0
0x18000883e  mov     qword ptr [rax+28h], 0
0x180008846  mov     rax, [r9+18h]
0x18000884a  mov     r10, [rax]
0x18000884d  test    r10, r10
0x180008850  jz      short loc_1800088C0
0x180008852  mov     rax, [rcx]
0x180008855  mov     rax, [rax+38h]
0x180008859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885e  mov     rbx, rax
0x180008861  mov     rcx, rax; SRWLock
0x180008864  call    cs:__imp_AcquireSRWLockShared
0x18000886a  mov     rcx, [rdi+18h]
0x18000886e  mov     rcx, [rcx]; Ptr
0x180008871  test    rcx, rcx
0x180008874  jz      short loc_1800088B2
0x180008876  call    cs:__imp_DecodePointer
0x18000887c  mov     r9, rax
0x18000887f  mov     [rsp+68h+Ptr], rax
0x180008887  mov     rcx, [rax]
0x18000888a  mov     rax, [rcx]
0x18000888d  mov     r8, r14
0x180008890  mov     rdx, r15
0x180008893  mov     rcx, r9
0x180008896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000889b  mov     edi, eax
0x18000889d  test    rbx, rbx
0x1800088a0  jz      short loc_1800088AB
0x1800088a2  mov     rcx, rbx; SRWLock
0x1800088a5  call    cs:__imp_ReleaseSRWLockShared
0x1800088ab  mov     eax, edi
0x1800088ad  jmp     loc_180008996
0x1800088b2  test    rbx, rbx
0x1800088b5  jz      short loc_1800088C0
0x1800088b7  mov     rcx, rbx; SRWLock
0x1800088ba  call    cs:__imp_ReleaseSRWLockShared
0x1800088c0  lea     r9, [rsp+68h+Ptr]
0x1800088c8  mov     r8, r15
0x1800088cb  mov     rdx, rdi
0x1800088ce  mov     rcx, rbp
0x1800088d1  mov     rax, [rdi]
0x1800088d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088d9  test    eax, eax
0x1800088db  js      loc_180008996
0x1800088e1  test    byte ptr [rbp+0], 4
0x1800088e5  jnz     loc_180008989
0x1800088eb  mov     rax, [rsi]
0x1800088ee  mov     rcx, rsi
0x1800088f1  mov     rax, [rax+38h]
0x1800088f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088fa  mov     rdx, rax
0x1800088fd  lea     rcx, [rsp+68h+SRWLock]
0x180008905  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000890a  mov     rax, [rdi+18h]
0x18000890e  mov     rcx, [rax]; Ptr
0x180008911  test    rcx, rcx
0x180008914  jnz     short loc_18000892F
0x180008916  xor     ebx, ebx
0x180008918  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180008920  call    cs:__imp_EncodePointer
0x180008926  mov     rcx, [rdi+18h]
0x18000892a  mov     [rcx], rax
0x18000892d  jmp     short loc_180008947
0x18000892f  call    cs:__imp_DecodePointer
0x180008935  mov     rbx, rax
0x180008938  mov     rcx, [rax]
0x18000893b  mov     rax, [rcx+8]
0x18000893f  mov     rcx, rbx
0x180008942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008947  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18000894f  test    rcx, rcx
0x180008952  jz      short loc_18000895A
0x180008954  call    cs:__imp_ReleaseSRWLockExclusive
0x18000895a  test    rbx, rbx
0x18000895d  jz      short loc_180008989
0x18000895f  mov     rcx, [rsp+68h+Ptr]
0x180008967  mov     rax, [rcx]
0x18000896a  mov     rax, [rax+10h]
0x18000896e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008973  mov     rcx, [rsp+68h+Ptr]
0x18000897b  mov     rax, [rcx]
0x18000897e  mov     rax, [rax+10h]
0x180008982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008987  jmp     short loc_180008991
0x180008989  mov     rbx, [rsp+68h+Ptr]
0x180008991  mov     [r14], rbx
0x180008994  xor     eax, eax
0x180008996  add     rsp, 38h
0x18000899a  pop     r15
0x18000899c  pop     r14
0x18000899e  pop     rdi
0x18000899f  pop     rsi
0x1800089a0  pop     rbp
0x1800089a1  pop     rbx
0x1800089a2  retn
```
