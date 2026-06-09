# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x1800139cc`
- end: `0x180013b50`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013854`

## callees

- `0x1800139cc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013a1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013a1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013a60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013a75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013a60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013a75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013abc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013abc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013b04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013b04`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013a30`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013ae4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013a30`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180013ae4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180013ad5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180013ad5`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  const struct Microsoft::WRL::Details::CreatorMap *v8; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v8 = a5;
  *(_QWORD *)a5 = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
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
    v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v13);
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
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
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
    *(_QWORD *)v8 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800139cc  mov     rax, rsp
0x1800139cf  mov     [rax+8], rbx
0x1800139d3  mov     [rax+10h], rbp
0x1800139d7  mov     [rax+18h], r8
0x1800139db  push    rsi
0x1800139dc  push    rdi
0x1800139dd  push    r14
0x1800139df  sub     rsp, 30h
0x1800139e3  mov     rdi, r9
0x1800139e6  mov     rbp, rdx
0x1800139e9  mov     rsi, rcx
0x1800139ec  mov     r14, [rsp+48h+arg_20]
0x1800139f1  mov     qword ptr [r14], 0
0x1800139f8  mov     qword ptr [rax+18h], 0
0x180013a00  mov     rax, [r9+18h]
0x180013a04  mov     r8, [rax]
0x180013a07  test    r8, r8
0x180013a0a  jz      short loc_180013A7B
0x180013a0c  mov     rax, [rcx]
0x180013a0f  mov     rax, [rax+38h]
0x180013a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a18  mov     rbx, rax
0x180013a1b  mov     rcx, rax; SRWLock
0x180013a1e  call    cs:__imp_AcquireSRWLockShared
0x180013a24  mov     rcx, [rdi+18h]
0x180013a28  mov     rcx, [rcx]; Ptr
0x180013a2b  test    rcx, rcx
0x180013a2e  jz      short loc_180013A6D
0x180013a30  call    cs:__imp_DecodePointer
0x180013a36  mov     r9, rax
0x180013a39  mov     [rsp+48h+Ptr], rax
0x180013a3e  mov     rcx, [rax]
0x180013a41  mov     rax, [rcx]
0x180013a44  mov     r8, r14
0x180013a47  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180013a4e  mov     rcx, r9
0x180013a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a56  mov     edi, eax
0x180013a58  test    rbx, rbx
0x180013a5b  jz      short loc_180013A66
0x180013a5d  mov     rcx, rbx; SRWLock
0x180013a60  call    cs:__imp_ReleaseSRWLockShared
0x180013a66  mov     eax, edi
0x180013a68  jmp     loc_180013B3D
0x180013a6d  test    rbx, rbx
0x180013a70  jz      short loc_180013A7B
0x180013a72  mov     rcx, rbx; SRWLock
0x180013a75  call    cs:__imp_ReleaseSRWLockShared
0x180013a7b  lea     r9, [rsp+48h+Ptr]
0x180013a80  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x180013a87  mov     rdx, rdi
0x180013a8a  mov     rcx, rbp
0x180013a8d  mov     rax, [rdi]
0x180013a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a95  test    eax, eax
0x180013a97  js      loc_180013B3D
0x180013a9d  test    byte ptr [rbp+0], 4
0x180013aa1  jnz     loc_180013B33
0x180013aa7  mov     rax, [rsi]
0x180013aaa  mov     rcx, rsi
0x180013aad  mov     rax, [rax+38h]
0x180013ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ab6  mov     rsi, rax
0x180013ab9  mov     rcx, rax; SRWLock
0x180013abc  call    cs:__imp_AcquireSRWLockExclusive
0x180013ac2  mov     rcx, [rdi+18h]
0x180013ac6  mov     rcx, [rcx]; Ptr
0x180013ac9  test    rcx, rcx
0x180013acc  jnz     short loc_180013AE4
0x180013ace  xor     ebx, ebx
0x180013ad0  mov     rcx, [rsp+48h+Ptr]; Ptr
0x180013ad5  call    cs:__imp_EncodePointer
0x180013adb  mov     rcx, [rdi+18h]
0x180013adf  mov     [rcx], rax
0x180013ae2  jmp     short loc_180013AFC
0x180013ae4  call    cs:__imp_DecodePointer
0x180013aea  mov     rbx, rax
0x180013aed  mov     rcx, [rax]
0x180013af0  mov     rax, [rcx+8]
0x180013af4  mov     rcx, rbx
0x180013af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013afc  test    rsi, rsi
0x180013aff  jz      short loc_180013B0A
0x180013b01  mov     rcx, rsi; SRWLock
0x180013b04  call    cs:__imp_ReleaseSRWLockExclusive
0x180013b0a  test    rbx, rbx
0x180013b0d  jz      short loc_180013B33
0x180013b0f  mov     rcx, [rsp+48h+Ptr]
0x180013b14  mov     rax, [rcx]
0x180013b17  mov     rax, [rax+10h]
0x180013b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b20  mov     rcx, [rsp+48h+Ptr]
0x180013b25  mov     rax, [rcx]
0x180013b28  mov     rax, [rax+10h]
0x180013b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b31  jmp     short loc_180013B38
0x180013b33  mov     rbx, [rsp+48h+Ptr]
0x180013b38  mov     [r14], rbx
0x180013b3b  xor     eax, eax
0x180013b3d  mov     rbx, [rsp+48h+arg_0]
0x180013b42  mov     rbp, [rsp+48h+arg_8]
0x180013b47  add     rsp, 30h
0x180013b4b  pop     r14
0x180013b4d  pop     rdi
0x180013b4e  pop     rsi
0x180013b4f  retn
```
