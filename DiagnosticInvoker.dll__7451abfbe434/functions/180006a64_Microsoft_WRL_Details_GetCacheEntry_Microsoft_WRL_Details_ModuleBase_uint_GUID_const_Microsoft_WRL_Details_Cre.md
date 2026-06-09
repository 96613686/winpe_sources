# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180006a64`
- end: `0x180006bea`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800068b0`
- `0x180006e20`

## callees

- `0x180006a64`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006ab4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006ab4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006af5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006b0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006af5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006b0a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006ac6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006b7b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006ac6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006b7b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180006b6c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180006b6c`

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
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID v16; // rbx

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
0x180006a64  mov     rax, rsp
0x180006a67  push    rbx
0x180006a68  push    rbp
0x180006a69  push    rsi
0x180006a6a  push    rdi
0x180006a6b  push    r14
0x180006a6d  push    r15
0x180006a6f  sub     rsp, 38h
0x180006a73  mov     rdi, r9
0x180006a76  mov     r15, r8
0x180006a79  mov     rbp, rdx
0x180006a7c  mov     rsi, rcx
0x180006a7f  mov     r14, [rsp+68h+Ptr]
0x180006a87  mov     qword ptr [r14], 0
0x180006a8e  mov     qword ptr [rax+28h], 0
0x180006a96  mov     rax, [r9+18h]
0x180006a9a  mov     r10, [rax]
0x180006a9d  test    r10, r10
0x180006aa0  jz      short loc_180006B10
0x180006aa2  mov     rax, [rcx]
0x180006aa5  mov     rax, [rax+38h]
0x180006aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aae  mov     rbx, rax
0x180006ab1  mov     rcx, rax; SRWLock
0x180006ab4  call    cs:__imp_AcquireSRWLockShared
0x180006aba  mov     rcx, [rdi+18h]
0x180006abe  mov     rcx, [rcx]; Ptr
0x180006ac1  test    rcx, rcx
0x180006ac4  jz      short loc_180006B02
0x180006ac6  call    cs:__imp_DecodePointer
0x180006acc  mov     r9, rax
0x180006acf  mov     [rsp+68h+Ptr], rax
0x180006ad7  mov     rcx, [rax]
0x180006ada  mov     rax, [rcx]
0x180006add  mov     r8, r14
0x180006ae0  mov     rdx, r15
0x180006ae3  mov     rcx, r9
0x180006ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aeb  mov     edi, eax
0x180006aed  test    rbx, rbx
0x180006af0  jz      short loc_180006AFB
0x180006af2  mov     rcx, rbx; SRWLock
0x180006af5  call    cs:__imp_ReleaseSRWLockShared
0x180006afb  mov     eax, edi
0x180006afd  jmp     loc_180006BDD
0x180006b02  test    rbx, rbx
0x180006b05  jz      short loc_180006B10
0x180006b07  mov     rcx, rbx; SRWLock
0x180006b0a  call    cs:__imp_ReleaseSRWLockShared
0x180006b10  lea     r9, [rsp+68h+Ptr]
0x180006b18  mov     r8, r15
0x180006b1b  mov     rdx, rdi
0x180006b1e  mov     rcx, rbp
0x180006b21  mov     rax, [rdi]
0x180006b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b29  test    eax, eax
0x180006b2b  js      loc_180006BDD
0x180006b31  test    byte ptr [rbp+0], 4
0x180006b35  jnz     loc_180006BD0
0x180006b3b  mov     rax, [rsi]
0x180006b3e  mov     rcx, rsi
0x180006b41  mov     rax, [rax+38h]
0x180006b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4a  mov     rsi, rax
0x180006b4d  mov     rcx, rax; SRWLock
0x180006b50  call    cs:__imp_AcquireSRWLockExclusive
0x180006b56  mov     rcx, [rdi+18h]
0x180006b5a  mov     rcx, [rcx]; Ptr
0x180006b5d  test    rcx, rcx
0x180006b60  jnz     short loc_180006B7B
0x180006b62  xor     ebx, ebx
0x180006b64  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180006b6c  call    cs:__imp_EncodePointer
0x180006b72  mov     rcx, [rdi+18h]
0x180006b76  mov     [rcx], rax
0x180006b79  jmp     short loc_180006B93
0x180006b7b  call    cs:__imp_DecodePointer
0x180006b81  mov     rbx, rax
0x180006b84  mov     rcx, [rax]
0x180006b87  mov     rax, [rcx+8]
0x180006b8b  mov     rcx, rbx
0x180006b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b93  test    rsi, rsi
0x180006b96  jz      short loc_180006BA1
0x180006b98  mov     rcx, rsi; SRWLock
0x180006b9b  call    cs:__imp_ReleaseSRWLockExclusive
0x180006ba1  test    rbx, rbx
0x180006ba4  jz      short loc_180006BD0
0x180006ba6  mov     rcx, [rsp+68h+Ptr]
0x180006bae  mov     rax, [rcx]
0x180006bb1  mov     rax, [rax+10h]
0x180006bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bba  mov     rcx, [rsp+68h+Ptr]
0x180006bc2  mov     rax, [rcx]
0x180006bc5  mov     rax, [rax+10h]
0x180006bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bce  jmp     short loc_180006BD8
0x180006bd0  mov     rbx, [rsp+68h+Ptr]
0x180006bd8  mov     [r14], rbx
0x180006bdb  xor     eax, eax
0x180006bdd  add     rsp, 38h
0x180006be1  pop     r15
0x180006be3  pop     r14
0x180006be5  pop     rdi
0x180006be6  pop     rsi
0x180006be7  pop     rbp
0x180006be8  pop     rbx
0x180006be9  retn
```
