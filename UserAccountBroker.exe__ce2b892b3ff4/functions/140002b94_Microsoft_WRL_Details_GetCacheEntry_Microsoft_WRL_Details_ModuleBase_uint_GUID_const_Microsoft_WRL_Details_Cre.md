# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x140002b94`
- end: `0x140002d18`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001c40`

## callees

- `0x140002b94`
- `0x140007010`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x140002c9d`
- `KERNEL32!EncodePointer` at `0x140002c9d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140002ccc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140002ccc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140002c84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140002c84`
- `KERNEL32!ReleaseSRWLockShared` at `0x140002c28`
- `KERNEL32!ReleaseSRWLockShared` at `0x140002c3d`
- `KERNEL32!ReleaseSRWLockShared` at `0x140002c28`
- `KERNEL32!ReleaseSRWLockShared` at `0x140002c3d`
- `KERNEL32!DecodePointer` at `0x140002bf8`
- `KERNEL32!DecodePointer` at `0x140002cac`
- `KERNEL32!DecodePointer` at `0x140002bf8`
- `KERNEL32!DecodePointer` at `0x140002cac`
- `KERNEL32!AcquireSRWLockShared` at `0x140002be6`
- `KERNEL32!AcquireSRWLockShared` at `0x140002be6`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  const struct Microsoft::WRL::Details::CreatorMap *v5; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v5 = a5;
  Ptr = 0;
  *(_QWORD *)a5 = 0;
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
    *(_QWORD *)v5 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002b94  mov     rax, rsp
0x140002b97  mov     [rax+8], rbx
0x140002b9b  mov     [rax+10h], rbp
0x140002b9f  mov     [rax+18h], r8
0x140002ba3  push    rsi
0x140002ba4  push    rdi
0x140002ba5  push    r14
0x140002ba7  sub     rsp, 30h
0x140002bab  mov     r14, [rsp+48h+arg_20]
0x140002bb0  mov     rdi, r9
0x140002bb3  mov     qword ptr [rax+18h], 0
0x140002bbb  mov     rbp, rdx
0x140002bbe  mov     rsi, rcx
0x140002bc1  mov     qword ptr [r14], 0
0x140002bc8  mov     rax, [r9+18h]
0x140002bcc  mov     r8, [rax]
0x140002bcf  test    r8, r8
0x140002bd2  jz      short loc_140002C43
0x140002bd4  mov     rax, [rcx]
0x140002bd7  mov     rax, [rax+38h]
0x140002bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002be0  mov     rcx, rax; SRWLock
0x140002be3  mov     rbx, rax
0x140002be6  call    cs:__imp_AcquireSRWLockShared
0x140002bec  mov     rcx, [rdi+18h]
0x140002bf0  mov     rcx, [rcx]; Ptr
0x140002bf3  test    rcx, rcx
0x140002bf6  jz      short loc_140002C35
0x140002bf8  call    cs:__imp_DecodePointer
0x140002bfe  mov     [rsp+48h+Ptr], rax
0x140002c03  mov     r8, r14
0x140002c06  mov     r9, rax
0x140002c09  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x140002c10  mov     rcx, [rax]
0x140002c13  mov     rax, [rcx]
0x140002c16  mov     rcx, r9
0x140002c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c1e  mov     edi, eax
0x140002c20  test    rbx, rbx
0x140002c23  jz      short loc_140002C2E
0x140002c25  mov     rcx, rbx; SRWLock
0x140002c28  call    cs:__imp_ReleaseSRWLockShared
0x140002c2e  mov     eax, edi
0x140002c30  jmp     loc_140002D05
0x140002c35  test    rbx, rbx
0x140002c38  jz      short loc_140002C43
0x140002c3a  mov     rcx, rbx; SRWLock
0x140002c3d  call    cs:__imp_ReleaseSRWLockShared
0x140002c43  mov     rax, [rdi]
0x140002c46  lea     r9, [rsp+48h+Ptr]
0x140002c4b  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x140002c52  mov     rdx, rdi
0x140002c55  mov     rcx, rbp
0x140002c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c5d  test    eax, eax
0x140002c5f  js      loc_140002D05
0x140002c65  test    byte ptr [rbp+0], 4
0x140002c69  jnz     loc_140002CFB
0x140002c6f  mov     rax, [rsi]
0x140002c72  mov     rcx, rsi
0x140002c75  mov     rax, [rax+38h]
0x140002c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c7e  mov     rcx, rax; SRWLock
0x140002c81  mov     rsi, rax
0x140002c84  call    cs:__imp_AcquireSRWLockExclusive
0x140002c8a  mov     rcx, [rdi+18h]
0x140002c8e  mov     rcx, [rcx]; Ptr
0x140002c91  test    rcx, rcx
0x140002c94  jnz     short loc_140002CAC
0x140002c96  mov     rcx, [rsp+48h+Ptr]; Ptr
0x140002c9b  xor     ebx, ebx
0x140002c9d  call    cs:__imp_EncodePointer
0x140002ca3  mov     rcx, [rdi+18h]
0x140002ca7  mov     [rcx], rax
0x140002caa  jmp     short loc_140002CC4
0x140002cac  call    cs:__imp_DecodePointer
0x140002cb2  mov     rbx, rax
0x140002cb5  mov     rcx, [rax]
0x140002cb8  mov     rax, [rcx+8]
0x140002cbc  mov     rcx, rbx
0x140002cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cc4  test    rsi, rsi
0x140002cc7  jz      short loc_140002CD2
0x140002cc9  mov     rcx, rsi; SRWLock
0x140002ccc  call    cs:__imp_ReleaseSRWLockExclusive
0x140002cd2  test    rbx, rbx
0x140002cd5  jz      short loc_140002CFB
0x140002cd7  mov     rcx, [rsp+48h+Ptr]
0x140002cdc  mov     rax, [rcx]
0x140002cdf  mov     rax, [rax+10h]
0x140002ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ce8  mov     rcx, [rsp+48h+Ptr]
0x140002ced  mov     rax, [rcx]
0x140002cf0  mov     rax, [rax+10h]
0x140002cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cf9  jmp     short loc_140002D00
0x140002cfb  mov     rbx, [rsp+48h+Ptr]
0x140002d00  mov     [r14], rbx
0x140002d03  xor     eax, eax
0x140002d05  mov     rbx, [rsp+48h+arg_0]
0x140002d0a  mov     rbp, [rsp+48h+arg_8]
0x140002d0f  add     rsp, 30h
0x140002d13  pop     r14
0x140002d15  pop     rdi
0x140002d16  pop     rsi
0x140002d17  retn
```
