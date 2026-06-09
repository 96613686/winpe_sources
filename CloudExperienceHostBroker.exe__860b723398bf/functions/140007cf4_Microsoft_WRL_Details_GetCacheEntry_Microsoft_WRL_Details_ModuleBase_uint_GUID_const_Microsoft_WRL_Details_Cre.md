# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x140007cf4`
- end: `0x140007e7b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006478`

## callees

- `0x140007cf4`
- `0x140008124`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007d46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007d88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007d9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007d88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007d9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007e2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007e2f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x140007dfe`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x140007dfe`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140007d58`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140007e0d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140007d58`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x140007e0d`

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
0x140007cf4  mov     rax, rsp
0x140007cf7  mov     [rax+8], rbx
0x140007cfb  mov     [rax+10h], rbp
0x140007cff  mov     [rax+18h], r8
0x140007d03  push    rsi
0x140007d04  push    rdi
0x140007d05  push    r14
0x140007d07  sub     rsp, 30h
0x140007d0b  mov     rdi, r9
0x140007d0e  mov     rbp, rdx
0x140007d11  mov     rsi, rcx
0x140007d14  mov     r14, [rsp+48h+SRWLock]
0x140007d19  mov     qword ptr [r14], 0
0x140007d20  mov     qword ptr [rax+18h], 0
0x140007d28  mov     rax, [r9+18h]
0x140007d2c  mov     r8, [rax]
0x140007d2f  test    r8, r8
0x140007d32  jz      short loc_140007DA3
0x140007d34  mov     rax, [rcx]
0x140007d37  mov     rax, [rax+38h]
0x140007d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d40  mov     rbx, rax
0x140007d43  mov     rcx, rax; SRWLock
0x140007d46  call    cs:__imp_AcquireSRWLockShared
0x140007d4c  mov     rcx, [rdi+18h]
0x140007d50  mov     rcx, [rcx]; Ptr
0x140007d53  test    rcx, rcx
0x140007d56  jz      short loc_140007D95
0x140007d58  call    cs:__imp_DecodePointer
0x140007d5e  mov     r9, rax
0x140007d61  mov     [rsp+48h+Ptr], rax
0x140007d66  mov     rcx, [rax]
0x140007d69  mov     rax, [rcx]
0x140007d6c  mov     r8, r14
0x140007d6f  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x140007d76  mov     rcx, r9
0x140007d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d7e  mov     edi, eax
0x140007d80  test    rbx, rbx
0x140007d83  jz      short loc_140007D8E
0x140007d85  mov     rcx, rbx; SRWLock
0x140007d88  call    cs:__imp_ReleaseSRWLockShared
0x140007d8e  mov     eax, edi
0x140007d90  jmp     loc_140007E68
0x140007d95  test    rbx, rbx
0x140007d98  jz      short loc_140007DA3
0x140007d9a  mov     rcx, rbx; SRWLock
0x140007d9d  call    cs:__imp_ReleaseSRWLockShared
0x140007da3  lea     r9, [rsp+48h+Ptr]
0x140007da8  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x140007daf  mov     rdx, rdi
0x140007db2  mov     rcx, rbp
0x140007db5  mov     rax, [rdi]
0x140007db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dbd  test    eax, eax
0x140007dbf  js      loc_140007E68
0x140007dc5  test    byte ptr [rbp+0], 4
0x140007dc9  jnz     loc_140007E5E
0x140007dcf  mov     rax, [rsi]
0x140007dd2  mov     rcx, rsi
0x140007dd5  mov     rax, [rax+38h]
0x140007dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007dde  mov     rdx, rax
0x140007de1  lea     rcx, [rsp+48h+SRWLock]
0x140007de6  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x140007deb  mov     rax, [rdi+18h]
0x140007def  mov     rcx, [rax]; Ptr
0x140007df2  test    rcx, rcx
0x140007df5  jnz     short loc_140007E0D
0x140007df7  xor     ebx, ebx
0x140007df9  mov     rcx, [rsp+48h+Ptr]; Ptr
0x140007dfe  call    cs:__imp_EncodePointer
0x140007e04  mov     rcx, [rdi+18h]
0x140007e08  mov     [rcx], rax
0x140007e0b  jmp     short loc_140007E25
0x140007e0d  call    cs:__imp_DecodePointer
0x140007e13  mov     rbx, rax
0x140007e16  mov     rcx, [rax]
0x140007e19  mov     rax, [rcx+8]
0x140007e1d  mov     rcx, rbx
0x140007e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e25  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x140007e2a  test    rcx, rcx
0x140007e2d  jz      short loc_140007E35
0x140007e2f  call    cs:__imp_ReleaseSRWLockExclusive
0x140007e35  test    rbx, rbx
0x140007e38  jz      short loc_140007E5E
0x140007e3a  mov     rcx, [rsp+48h+Ptr]
0x140007e3f  mov     rax, [rcx]
0x140007e42  mov     rax, [rax+10h]
0x140007e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e4b  mov     rcx, [rsp+48h+Ptr]
0x140007e50  mov     rax, [rcx]
0x140007e53  mov     rax, [rax+10h]
0x140007e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e5c  jmp     short loc_140007E63
0x140007e5e  mov     rbx, [rsp+48h+Ptr]
0x140007e63  mov     [r14], rbx
0x140007e66  xor     eax, eax
0x140007e68  mov     rbx, [rsp+48h+arg_0]
0x140007e6d  mov     rbp, [rsp+48h+arg_8]
0x140007e72  add     rsp, 30h
0x140007e76  pop     r14
0x140007e78  pop     rdi
0x140007e79  pop     rsi
0x140007e7a  retn
```
