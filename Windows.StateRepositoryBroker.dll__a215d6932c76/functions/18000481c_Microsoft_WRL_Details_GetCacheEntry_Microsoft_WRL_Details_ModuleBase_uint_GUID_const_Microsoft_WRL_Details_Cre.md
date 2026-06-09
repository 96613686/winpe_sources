# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000481c`
- end: `0x1800049ab`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002f58`
- `0x1800030d0`

## callees

- `0x18000481c`
- `0x1800053c8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000487e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004937`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000487e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004937`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180004928`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180004928`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800048ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800048c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800048ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800048c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000495c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000495c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000486c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000486c`

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
0x18000481c  mov     rax, rsp
0x18000481f  push    rbx
0x180004820  push    rbp
0x180004821  push    rsi
0x180004822  push    rdi
0x180004823  push    r14
0x180004825  push    r15
0x180004827  sub     rsp, 38h
0x18000482b  mov     rdi, r9
0x18000482e  mov     r15, r8
0x180004831  mov     rbp, rdx
0x180004834  mov     rsi, rcx
0x180004837  mov     r14, [rsp+68h+Ptr]
0x18000483f  mov     qword ptr [r14], 0
0x180004846  mov     qword ptr [rax+28h], 0
0x18000484e  mov     rax, [r9+18h]
0x180004852  mov     r10, [rax]
0x180004855  test    r10, r10
0x180004858  jz      short loc_1800048C8
0x18000485a  mov     rax, [rcx]
0x18000485d  mov     rax, [rax+38h]
0x180004861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004866  mov     rbx, rax
0x180004869  mov     rcx, rax; SRWLock
0x18000486c  call    cs:__imp_AcquireSRWLockShared
0x180004872  mov     rcx, [rdi+18h]
0x180004876  mov     rcx, [rcx]; Ptr
0x180004879  test    rcx, rcx
0x18000487c  jz      short loc_1800048BA
0x18000487e  call    cs:__imp_DecodePointer
0x180004884  mov     r9, rax
0x180004887  mov     [rsp+68h+Ptr], rax
0x18000488f  mov     rcx, [rax]
0x180004892  mov     rax, [rcx]
0x180004895  mov     r8, r14
0x180004898  mov     rdx, r15
0x18000489b  mov     rcx, r9
0x18000489e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a3  mov     edi, eax
0x1800048a5  test    rbx, rbx
0x1800048a8  jz      short loc_1800048B3
0x1800048aa  mov     rcx, rbx; SRWLock
0x1800048ad  call    cs:__imp_ReleaseSRWLockShared
0x1800048b3  mov     eax, edi
0x1800048b5  jmp     loc_18000499E
0x1800048ba  test    rbx, rbx
0x1800048bd  jz      short loc_1800048C8
0x1800048bf  mov     rcx, rbx; SRWLock
0x1800048c2  call    cs:__imp_ReleaseSRWLockShared
0x1800048c8  lea     r9, [rsp+68h+Ptr]
0x1800048d0  mov     r8, r15
0x1800048d3  mov     rdx, rdi
0x1800048d6  mov     rcx, rbp
0x1800048d9  mov     rax, [rdi]
0x1800048dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e1  test    eax, eax
0x1800048e3  js      loc_18000499E
0x1800048e9  test    byte ptr [rbp+0], 4
0x1800048ed  jnz     loc_180004991
0x1800048f3  mov     rax, [rsi]
0x1800048f6  mov     rcx, rsi
0x1800048f9  mov     rax, [rax+38h]
0x1800048fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004902  mov     rdx, rax
0x180004905  lea     rcx, [rsp+68h+SRWLock]
0x18000490d  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180004912  mov     rax, [rdi+18h]
0x180004916  mov     rcx, [rax]; Ptr
0x180004919  test    rcx, rcx
0x18000491c  jnz     short loc_180004937
0x18000491e  xor     ebx, ebx
0x180004920  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180004928  call    cs:__imp_EncodePointer
0x18000492e  mov     rcx, [rdi+18h]
0x180004932  mov     [rcx], rax
0x180004935  jmp     short loc_18000494F
0x180004937  call    cs:__imp_DecodePointer
0x18000493d  mov     rbx, rax
0x180004940  mov     rcx, [rax]
0x180004943  mov     rax, [rcx+8]
0x180004947  mov     rcx, rbx
0x18000494a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494f  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180004957  test    rcx, rcx
0x18000495a  jz      short loc_180004962
0x18000495c  call    cs:__imp_ReleaseSRWLockExclusive
0x180004962  test    rbx, rbx
0x180004965  jz      short loc_180004991
0x180004967  mov     rcx, [rsp+68h+Ptr]
0x18000496f  mov     rax, [rcx]
0x180004972  mov     rax, [rax+10h]
0x180004976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497b  mov     rcx, [rsp+68h+Ptr]
0x180004983  mov     rax, [rcx]
0x180004986  mov     rax, [rax+10h]
0x18000498a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000498f  jmp     short loc_180004999
0x180004991  mov     rbx, [rsp+68h+Ptr]
0x180004999  mov     [r14], rbx
0x18000499c  xor     eax, eax
0x18000499e  add     rsp, 38h
0x1800049a2  pop     r15
0x1800049a4  pop     r14
0x1800049a6  pop     rdi
0x1800049a7  pop     rsi
0x1800049a8  pop     rbp
0x1800049a9  pop     rbx
0x1800049aa  retn
```
