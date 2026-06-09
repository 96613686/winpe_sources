# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180008df4`
- end: `0x180008f7b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004f50`

## callees

- `0x180008df4`
- `0x18000a2c0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008e46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008e46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008f2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008f2f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008e58`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008f0d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008e58`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008f0d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008efe`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008efe`

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
0x180008df4  mov     rax, rsp
0x180008df7  mov     [rax+8], rbx
0x180008dfb  mov     [rax+10h], rbp
0x180008dff  mov     [rax+18h], r8
0x180008e03  push    rsi
0x180008e04  push    rdi
0x180008e05  push    r14
0x180008e07  sub     rsp, 30h
0x180008e0b  mov     rdi, r9
0x180008e0e  mov     rbp, rdx
0x180008e11  mov     rsi, rcx
0x180008e14  mov     r14, [rsp+48h+SRWLock]
0x180008e19  mov     qword ptr [r14], 0
0x180008e20  mov     qword ptr [rax+18h], 0
0x180008e28  mov     rax, [r9+18h]
0x180008e2c  mov     r8, [rax]
0x180008e2f  test    r8, r8
0x180008e32  jz      short loc_180008EA3
0x180008e34  mov     rax, [rcx]
0x180008e37  mov     rax, [rax+38h]
0x180008e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e40  mov     rbx, rax
0x180008e43  mov     rcx, rax; SRWLock
0x180008e46  call    cs:__imp_AcquireSRWLockShared
0x180008e4c  mov     rcx, [rdi+18h]
0x180008e50  mov     rcx, [rcx]; Ptr
0x180008e53  test    rcx, rcx
0x180008e56  jz      short loc_180008E95
0x180008e58  call    cs:__imp_DecodePointer
0x180008e5e  mov     r9, rax
0x180008e61  mov     [rsp+48h+Ptr], rax
0x180008e66  mov     rcx, [rax]
0x180008e69  mov     rax, [rcx]
0x180008e6c  mov     r8, r14
0x180008e6f  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180008e76  mov     rcx, r9
0x180008e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e7e  mov     edi, eax
0x180008e80  test    rbx, rbx
0x180008e83  jz      short loc_180008E8E
0x180008e85  mov     rcx, rbx; SRWLock
0x180008e88  call    cs:__imp_ReleaseSRWLockShared
0x180008e8e  mov     eax, edi
0x180008e90  jmp     loc_180008F68
0x180008e95  test    rbx, rbx
0x180008e98  jz      short loc_180008EA3
0x180008e9a  mov     rcx, rbx; SRWLock
0x180008e9d  call    cs:__imp_ReleaseSRWLockShared
0x180008ea3  lea     r9, [rsp+48h+Ptr]
0x180008ea8  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x180008eaf  mov     rdx, rdi
0x180008eb2  mov     rcx, rbp
0x180008eb5  mov     rax, [rdi]
0x180008eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ebd  test    eax, eax
0x180008ebf  js      loc_180008F68
0x180008ec5  test    byte ptr [rbp+0], 4
0x180008ec9  jnz     loc_180008F5E
0x180008ecf  mov     rax, [rsi]
0x180008ed2  mov     rcx, rsi
0x180008ed5  mov     rax, [rax+38h]
0x180008ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ede  mov     rdx, rax
0x180008ee1  lea     rcx, [rsp+48h+SRWLock]
0x180008ee6  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180008eeb  mov     rax, [rdi+18h]
0x180008eef  mov     rcx, [rax]; Ptr
0x180008ef2  test    rcx, rcx
0x180008ef5  jnz     short loc_180008F0D
0x180008ef7  xor     ebx, ebx
0x180008ef9  mov     rcx, [rsp+48h+Ptr]; Ptr
0x180008efe  call    cs:__imp_EncodePointer
0x180008f04  mov     rcx, [rdi+18h]
0x180008f08  mov     [rcx], rax
0x180008f0b  jmp     short loc_180008F25
0x180008f0d  call    cs:__imp_DecodePointer
0x180008f13  mov     rbx, rax
0x180008f16  mov     rcx, [rax]
0x180008f19  mov     rax, [rcx+8]
0x180008f1d  mov     rcx, rbx
0x180008f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f25  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180008f2a  test    rcx, rcx
0x180008f2d  jz      short loc_180008F35
0x180008f2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008f35  test    rbx, rbx
0x180008f38  jz      short loc_180008F5E
0x180008f3a  mov     rcx, [rsp+48h+Ptr]
0x180008f3f  mov     rax, [rcx]
0x180008f42  mov     rax, [rax+10h]
0x180008f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4b  mov     rcx, [rsp+48h+Ptr]
0x180008f50  mov     rax, [rcx]
0x180008f53  mov     rax, [rax+10h]
0x180008f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f5c  jmp     short loc_180008F63
0x180008f5e  mov     rbx, [rsp+48h+Ptr]
0x180008f63  mov     [r14], rbx
0x180008f66  xor     eax, eax
0x180008f68  mov     rbx, [rsp+48h+arg_0]
0x180008f6d  mov     rbp, [rsp+48h+arg_8]
0x180008f72  add     rsp, 30h
0x180008f76  pop     r14
0x180008f78  pop     rdi
0x180008f79  pop     rsi
0x180008f7a  retn
```
