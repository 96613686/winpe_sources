# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000e5a0`
- end: `0x18000e72f`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014b48`

## callees

- `0x18000e5a0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000e6a0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000e6a0`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e605`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e6c9`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e605`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000e6c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e5ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e5ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e6e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e6e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e634`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e6fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e634`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000e6fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e683`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e683`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v5; // rdi
  RTL_SRWLOCK *v10; // rsi
  void *v11; // rcx
  unsigned int v12; // ebx
  __int64 result; // rax
  RTL_SRWLOCK *v14; // rbp
  void *v15; // rcx
  PVOID v16; // rsi

  v5 = Ptr;
  Ptr = 0;
  *v5 = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v10 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v10);
    v11 = **(void ***)a4[1].Data4;
    if ( v11 )
    {
      Ptr = DecodePointer(v11);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, _QWORD *))*Ptr)(Ptr, a3, v5);
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
      goto LABEL_14;
    v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockExclusive(v14);
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
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    if ( v16 )
    {
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
    }
    else
    {
LABEL_14:
      v16 = Ptr;
    }
    *v5 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e5a0  push    rbx
0x18000e5a2  push    rbp
0x18000e5a3  push    rsi
0x18000e5a4  push    rdi
0x18000e5a5  push    r12
0x18000e5a7  push    r14
0x18000e5a9  push    r15
0x18000e5ab  sub     rsp, 30h
0x18000e5af  mov     rdi, [rsp+68h+Ptr]
0x18000e5b7  xor     r12d, r12d
0x18000e5ba  mov     [rsp+68h+Ptr], r12
0x18000e5c2  mov     rbx, r9
0x18000e5c5  mov     rbp, r8
0x18000e5c8  mov     r15, rdx
0x18000e5cb  mov     r14, rcx
0x18000e5ce  mov     [rdi], r12
0x18000e5d1  mov     rax, [r9+18h]
0x18000e5d5  mov     r10, [rax]
0x18000e5d8  test    r10, r10
0x18000e5db  jz      short loc_18000E64B
0x18000e5dd  mov     rax, [rcx]
0x18000e5e0  mov     rax, [rax+38h]
0x18000e5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5e9  mov     rcx, rax; SRWLock
0x18000e5ec  mov     rsi, rax
0x18000e5ef  call    cs:__imp_AcquireSRWLockShared
0x18000e5f5  mov     rcx, [rbx+18h]
0x18000e5f9  mov     rcx, [rcx]; Ptr
0x18000e5fc  test    rcx, rcx
0x18000e5ff  jz      loc_18000E6EE
0x18000e605  call    cs:__imp_DecodePointer
0x18000e60b  mov     [rsp+68h+Ptr], rax
0x18000e613  mov     r8, rdi
0x18000e616  mov     r9, rax
0x18000e619  mov     rdx, rbp
0x18000e61c  mov     rcx, [rax]
0x18000e61f  mov     rax, [rcx]
0x18000e622  mov     rcx, r9
0x18000e625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e62a  mov     ebx, eax
0x18000e62c  test    rsi, rsi
0x18000e62f  jz      short loc_18000E63A
0x18000e631  mov     rcx, rsi; SRWLock
0x18000e634  call    cs:__imp_ReleaseSRWLockShared
0x18000e63a  mov     eax, ebx
0x18000e63c  add     rsp, 30h
0x18000e640  pop     r15
0x18000e642  pop     r14
0x18000e644  pop     r12
0x18000e646  pop     rdi
0x18000e647  pop     rsi
0x18000e648  pop     rbp
0x18000e649  pop     rbx
0x18000e64a  retn
0x18000e64b  mov     rax, [rbx]
0x18000e64e  lea     r9, [rsp+68h+Ptr]
0x18000e656  mov     r8, rbp
0x18000e659  mov     rdx, rbx
0x18000e65c  mov     rcx, r15
0x18000e65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e664  test    eax, eax
0x18000e666  js      short loc_18000E63C
0x18000e668  test    byte ptr [r15], 4
0x18000e66c  jnz     short loc_18000E6B7
0x18000e66e  mov     rax, [r14]
0x18000e671  mov     rcx, r14
0x18000e674  mov     rax, [rax+38h]
0x18000e678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e67d  mov     rcx, rax; SRWLock
0x18000e680  mov     rbp, rax
0x18000e683  call    cs:__imp_AcquireSRWLockExclusive
0x18000e689  mov     rcx, [rbx+18h]
0x18000e68d  mov     rcx, [rcx]; Ptr
0x18000e690  test    rcx, rcx
0x18000e693  jnz     short loc_18000E6C9
0x18000e695  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000e69d  mov     rsi, r12
0x18000e6a0  call    cs:__imp_EncodePointer
0x18000e6a6  mov     rcx, [rbx+18h]
0x18000e6aa  mov     [rcx], rax
0x18000e6ad  test    rbp, rbp
0x18000e6b0  jnz     short loc_18000E6E3
0x18000e6b2  test    rsi, rsi
0x18000e6b5  jnz     short loc_18000E705
0x18000e6b7  mov     rsi, [rsp+68h+Ptr]
0x18000e6bf  mov     [rdi], rsi
0x18000e6c2  xor     eax, eax
0x18000e6c4  jmp     loc_18000E63C
0x18000e6c9  call    cs:__imp_DecodePointer
0x18000e6cf  mov     rsi, rax
0x18000e6d2  mov     rcx, [rax]
0x18000e6d5  mov     rax, [rcx+8]
0x18000e6d9  mov     rcx, rsi
0x18000e6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6e1  jmp     short loc_18000E6AD
0x18000e6e3  mov     rcx, rbp; SRWLock
0x18000e6e6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e6ec  jmp     short loc_18000E6B2
0x18000e6ee  test    rsi, rsi
0x18000e6f1  jz      loc_18000E64B
0x18000e6f7  mov     rcx, rsi; SRWLock
0x18000e6fa  call    cs:__imp_ReleaseSRWLockShared
0x18000e700  jmp     loc_18000E64B
0x18000e705  mov     rcx, [rsp+68h+Ptr]
0x18000e70d  mov     rax, [rcx]
0x18000e710  mov     rax, [rax+10h]
0x18000e714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e719  mov     rcx, [rsp+68h+Ptr]
0x18000e721  mov     rax, [rcx]
0x18000e724  mov     rax, [rax+10h]
0x18000e728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e72d  jmp     short loc_18000E6BF
```
