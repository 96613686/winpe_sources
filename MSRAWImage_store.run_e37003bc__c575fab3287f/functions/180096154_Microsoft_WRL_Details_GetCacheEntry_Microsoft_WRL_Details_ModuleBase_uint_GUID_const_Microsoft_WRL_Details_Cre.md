# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180096154`
- end: `0x18009630a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180095530`

## callees

- `0x180096154`
- `0x1800967d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18009627a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18009627a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800961c2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18009628f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800961c2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18009628f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800961f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180096213`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800961f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180096213`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800962b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800962b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800961aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800961aa`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        PSRWLOCK SRWLock)
{
  PSRWLOCK v5; // rsi
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  PVOID v13; // rbx
  __int64 v14; // rax
  void *v15; // rcx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v5 = SRWLock;
  Ptr = 0;
  SRWLock->Ptr = 0;
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
              v5);
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
    v14 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v14);
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
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
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
    v5->Ptr = v13;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180096154  mov     rax, rsp
0x180096157  mov     [rax+8], rbx
0x18009615b  mov     [rax+10h], rbp
0x18009615f  mov     [rax+18h], r8
0x180096163  push    rsi
0x180096164  push    rdi
0x180096165  push    r14
0x180096167  sub     rsp, 30h
0x18009616b  mov     rsi, [rsp+48h+SRWLock]
0x180096170  mov     rdi, r9
0x180096173  mov     qword ptr [rax+18h], 0
0x18009617b  mov     rbp, rdx
0x18009617e  mov     r14, rcx
0x180096181  mov     qword ptr [rsi], 0
0x180096188  mov     rax, [r9+18h]
0x18009618c  mov     r8, [rax]
0x18009618f  test    r8, r8
0x180096192  jz      loc_18009621F
0x180096198  mov     rax, [rcx]
0x18009619b  mov     rax, [rax+38h]
0x18009619f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800961a4  mov     rcx, rax; SRWLock
0x1800961a7  mov     rbx, rax
0x1800961aa  call    cs:__imp_AcquireSRWLockShared
0x1800961b1  nop     dword ptr [rax+rax+00h]
0x1800961b6  mov     rcx, [rdi+18h]
0x1800961ba  mov     rcx, [rcx]; Ptr
0x1800961bd  test    rcx, rcx
0x1800961c0  jz      short loc_18009620B
0x1800961c2  call    cs:__imp_DecodePointer
0x1800961c9  nop     dword ptr [rax+rax+00h]
0x1800961ce  mov     [rsp+48h+Ptr], rax
0x1800961d3  mov     r8, rsi
0x1800961d6  mov     r9, rax
0x1800961d9  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1800961e0  mov     rcx, [rax]
0x1800961e3  mov     rax, [rcx]
0x1800961e6  mov     rcx, r9
0x1800961e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800961ee  mov     edi, eax
0x1800961f0  test    rbx, rbx
0x1800961f3  jz      short loc_180096204
0x1800961f5  mov     rcx, rbx; SRWLock
0x1800961f8  call    cs:__imp_ReleaseSRWLockShared
0x1800961ff  nop     dword ptr [rax+rax+00h]
0x180096204  mov     eax, edi
0x180096206  jmp     loc_1800962F6
0x18009620b  test    rbx, rbx
0x18009620e  jz      short loc_18009621F
0x180096210  mov     rcx, rbx; SRWLock
0x180096213  call    cs:__imp_ReleaseSRWLockShared
0x18009621a  nop     dword ptr [rax+rax+00h]
0x18009621f  mov     rax, [rdi]
0x180096222  lea     r9, [rsp+48h+Ptr]
0x180096227  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x18009622e  mov     rdx, rdi
0x180096231  mov     rcx, rbp
0x180096234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096239  test    eax, eax
0x18009623b  js      loc_1800962F6
0x180096241  test    byte ptr [rbp+0], 4
0x180096245  jnz     loc_1800962EC
0x18009624b  mov     rax, [r14]
0x18009624e  mov     rcx, r14
0x180096251  xor     ebx, ebx
0x180096253  mov     rax, [rax+38h]
0x180096257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009625c  mov     rdx, rax
0x18009625f  lea     rcx, [rsp+48h+SRWLock]
0x180096264  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180096269  mov     rax, [rdi+18h]
0x18009626d  mov     rcx, [rax]; Ptr
0x180096270  test    rcx, rcx
0x180096273  jnz     short loc_18009628F
0x180096275  mov     rcx, [rsp+48h+Ptr]; Ptr
0x18009627a  call    cs:__imp_EncodePointer
0x180096281  nop     dword ptr [rax+rax+00h]
0x180096286  mov     rcx, [rdi+18h]
0x18009628a  mov     [rcx], rax
0x18009628d  jmp     short loc_1800962AD
0x18009628f  call    cs:__imp_DecodePointer
0x180096296  nop     dword ptr [rax+rax+00h]
0x18009629b  mov     rbx, rax
0x18009629e  mov     rcx, [rax]
0x1800962a1  mov     rax, [rcx+8]
0x1800962a5  mov     rcx, rbx
0x1800962a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800962ad  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x1800962b2  test    rcx, rcx
0x1800962b5  jz      short loc_1800962C3
0x1800962b7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800962be  nop     dword ptr [rax+rax+00h]
0x1800962c3  test    rbx, rbx
0x1800962c6  jz      short loc_1800962EC
0x1800962c8  mov     rcx, [rsp+48h+Ptr]
0x1800962cd  mov     rax, [rcx]
0x1800962d0  mov     rax, [rax+10h]
0x1800962d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800962d9  mov     rcx, [rsp+48h+Ptr]
0x1800962de  mov     rax, [rcx]
0x1800962e1  mov     rax, [rax+10h]
0x1800962e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800962ea  jmp     short loc_1800962F1
0x1800962ec  mov     rbx, [rsp+48h+Ptr]
0x1800962f1  mov     [rsi], rbx
0x1800962f4  xor     eax, eax
0x1800962f6  mov     rbx, [rsp+48h+arg_0]
0x1800962fb  mov     rbp, [rsp+48h+arg_8]
0x180096300  add     rsp, 30h
0x180096304  pop     r14
0x180096306  pop     rdi
0x180096307  pop     rsi
0x180096308  retn
```
