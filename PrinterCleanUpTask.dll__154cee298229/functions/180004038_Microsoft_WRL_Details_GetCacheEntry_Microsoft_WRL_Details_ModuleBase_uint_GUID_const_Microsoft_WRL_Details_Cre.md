# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180004038`
- end: `0x1800041c7`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003510`

## callees

- `0x180004038`
- `0x180004838`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000409a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004153`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000409a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004153`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180004144`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180004144`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800040c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800040de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800040c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800040de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004178`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004178`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004088`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004088`

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
0x180004038  mov     rax, rsp
0x18000403b  push    rbx
0x18000403c  push    rbp
0x18000403d  push    rsi
0x18000403e  push    rdi
0x18000403f  push    r14
0x180004041  push    r15
0x180004043  sub     rsp, 38h
0x180004047  mov     rdi, r9
0x18000404a  mov     r15, r8
0x18000404d  mov     rbp, rdx
0x180004050  mov     rsi, rcx
0x180004053  mov     r14, [rsp+68h+Ptr]
0x18000405b  mov     qword ptr [r14], 0
0x180004062  mov     qword ptr [rax+28h], 0
0x18000406a  mov     rax, [r9+18h]
0x18000406e  mov     r10, [rax]
0x180004071  test    r10, r10
0x180004074  jz      short loc_1800040E4
0x180004076  mov     rax, [rcx]
0x180004079  mov     rax, [rax+38h]
0x18000407d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004082  mov     rbx, rax
0x180004085  mov     rcx, rax; SRWLock
0x180004088  call    cs:__imp_AcquireSRWLockShared
0x18000408e  mov     rcx, [rdi+18h]
0x180004092  mov     rcx, [rcx]; Ptr
0x180004095  test    rcx, rcx
0x180004098  jz      short loc_1800040D6
0x18000409a  call    cs:__imp_DecodePointer
0x1800040a0  mov     r9, rax
0x1800040a3  mov     [rsp+68h+Ptr], rax
0x1800040ab  mov     rcx, [rax]
0x1800040ae  mov     rax, [rcx]
0x1800040b1  mov     r8, r14
0x1800040b4  mov     rdx, r15
0x1800040b7  mov     rcx, r9
0x1800040ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040bf  mov     edi, eax
0x1800040c1  test    rbx, rbx
0x1800040c4  jz      short loc_1800040CF
0x1800040c6  mov     rcx, rbx; SRWLock
0x1800040c9  call    cs:__imp_ReleaseSRWLockShared
0x1800040cf  mov     eax, edi
0x1800040d1  jmp     loc_1800041BA
0x1800040d6  test    rbx, rbx
0x1800040d9  jz      short loc_1800040E4
0x1800040db  mov     rcx, rbx; SRWLock
0x1800040de  call    cs:__imp_ReleaseSRWLockShared
0x1800040e4  lea     r9, [rsp+68h+Ptr]
0x1800040ec  mov     r8, r15
0x1800040ef  mov     rdx, rdi
0x1800040f2  mov     rcx, rbp
0x1800040f5  mov     rax, [rdi]
0x1800040f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040fd  test    eax, eax
0x1800040ff  js      loc_1800041BA
0x180004105  test    byte ptr [rbp+0], 4
0x180004109  jnz     loc_1800041AD
0x18000410f  mov     rax, [rsi]
0x180004112  mov     rcx, rsi
0x180004115  mov     rax, [rax+38h]
0x180004119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000411e  mov     rdx, rax
0x180004121  lea     rcx, [rsp+68h+SRWLock]
0x180004129  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18000412e  mov     rax, [rdi+18h]
0x180004132  mov     rcx, [rax]; Ptr
0x180004135  test    rcx, rcx
0x180004138  jnz     short loc_180004153
0x18000413a  xor     ebx, ebx
0x18000413c  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180004144  call    cs:__imp_EncodePointer
0x18000414a  mov     rcx, [rdi+18h]
0x18000414e  mov     [rcx], rax
0x180004151  jmp     short loc_18000416B
0x180004153  call    cs:__imp_DecodePointer
0x180004159  mov     rbx, rax
0x18000415c  mov     rcx, [rax]
0x18000415f  mov     rax, [rcx+8]
0x180004163  mov     rcx, rbx
0x180004166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416b  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180004173  test    rcx, rcx
0x180004176  jz      short loc_18000417E
0x180004178  call    cs:__imp_ReleaseSRWLockExclusive
0x18000417e  test    rbx, rbx
0x180004181  jz      short loc_1800041AD
0x180004183  mov     rcx, [rsp+68h+Ptr]
0x18000418b  mov     rax, [rcx]
0x18000418e  mov     rax, [rax+10h]
0x180004192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004197  mov     rcx, [rsp+68h+Ptr]
0x18000419f  mov     rax, [rcx]
0x1800041a2  mov     rax, [rax+10h]
0x1800041a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ab  jmp     short loc_1800041B5
0x1800041ad  mov     rbx, [rsp+68h+Ptr]
0x1800041b5  mov     [r14], rbx
0x1800041b8  xor     eax, eax
0x1800041ba  add     rsp, 38h
0x1800041be  pop     r15
0x1800041c0  pop     r14
0x1800041c2  pop     rdi
0x1800041c3  pop     rsi
0x1800041c4  pop     rbp
0x1800041c5  pop     rbx
0x1800041c6  retn
```
