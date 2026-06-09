# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000c584`
- end: `0x18000c70a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c910`

## callees

- `0x18000c584`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c615`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c62a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c615`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c62a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c5d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c5d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c670`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c670`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c6bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c6bb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c5e6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c69b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c5e6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c69b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c68c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c68c`

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
0x18000c584  mov     rax, rsp
0x18000c587  push    rbx
0x18000c588  push    rbp
0x18000c589  push    rsi
0x18000c58a  push    rdi
0x18000c58b  push    r14
0x18000c58d  push    r15
0x18000c58f  sub     rsp, 38h
0x18000c593  mov     rdi, r9
0x18000c596  mov     r15, r8
0x18000c599  mov     rbp, rdx
0x18000c59c  mov     rsi, rcx
0x18000c59f  mov     r14, [rsp+68h+Ptr]
0x18000c5a7  mov     qword ptr [r14], 0
0x18000c5ae  mov     qword ptr [rax+28h], 0
0x18000c5b6  mov     rax, [r9+18h]
0x18000c5ba  mov     r10, [rax]
0x18000c5bd  test    r10, r10
0x18000c5c0  jz      short loc_18000C630
0x18000c5c2  mov     rax, [rcx]
0x18000c5c5  mov     rax, [rax+38h]
0x18000c5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ce  mov     rbx, rax
0x18000c5d1  mov     rcx, rax; SRWLock
0x18000c5d4  call    cs:__imp_AcquireSRWLockShared
0x18000c5da  mov     rcx, [rdi+18h]
0x18000c5de  mov     rcx, [rcx]; Ptr
0x18000c5e1  test    rcx, rcx
0x18000c5e4  jz      short loc_18000C622
0x18000c5e6  call    cs:__imp_DecodePointer
0x18000c5ec  mov     r9, rax
0x18000c5ef  mov     [rsp+68h+Ptr], rax
0x18000c5f7  mov     rcx, [rax]
0x18000c5fa  mov     rax, [rcx]
0x18000c5fd  mov     r8, r14
0x18000c600  mov     rdx, r15
0x18000c603  mov     rcx, r9
0x18000c606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c60b  mov     edi, eax
0x18000c60d  test    rbx, rbx
0x18000c610  jz      short loc_18000C61B
0x18000c612  mov     rcx, rbx; SRWLock
0x18000c615  call    cs:__imp_ReleaseSRWLockShared
0x18000c61b  mov     eax, edi
0x18000c61d  jmp     loc_18000C6FD
0x18000c622  test    rbx, rbx
0x18000c625  jz      short loc_18000C630
0x18000c627  mov     rcx, rbx; SRWLock
0x18000c62a  call    cs:__imp_ReleaseSRWLockShared
0x18000c630  lea     r9, [rsp+68h+Ptr]
0x18000c638  mov     r8, r15
0x18000c63b  mov     rdx, rdi
0x18000c63e  mov     rcx, rbp
0x18000c641  mov     rax, [rdi]
0x18000c644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c649  test    eax, eax
0x18000c64b  js      loc_18000C6FD
0x18000c651  test    byte ptr [rbp+0], 4
0x18000c655  jnz     loc_18000C6F0
0x18000c65b  mov     rax, [rsi]
0x18000c65e  mov     rcx, rsi
0x18000c661  mov     rax, [rax+38h]
0x18000c665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c66a  mov     rsi, rax
0x18000c66d  mov     rcx, rax; SRWLock
0x18000c670  call    cs:__imp_AcquireSRWLockExclusive
0x18000c676  mov     rcx, [rdi+18h]
0x18000c67a  mov     rcx, [rcx]; Ptr
0x18000c67d  test    rcx, rcx
0x18000c680  jnz     short loc_18000C69B
0x18000c682  xor     ebx, ebx
0x18000c684  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000c68c  call    cs:__imp_EncodePointer
0x18000c692  mov     rcx, [rdi+18h]
0x18000c696  mov     [rcx], rax
0x18000c699  jmp     short loc_18000C6B3
0x18000c69b  call    cs:__imp_DecodePointer
0x18000c6a1  mov     rbx, rax
0x18000c6a4  mov     rcx, [rax]
0x18000c6a7  mov     rax, [rcx+8]
0x18000c6ab  mov     rcx, rbx
0x18000c6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b3  test    rsi, rsi
0x18000c6b6  jz      short loc_18000C6C1
0x18000c6b8  mov     rcx, rsi; SRWLock
0x18000c6bb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c6c1  test    rbx, rbx
0x18000c6c4  jz      short loc_18000C6F0
0x18000c6c6  mov     rcx, [rsp+68h+Ptr]
0x18000c6ce  mov     rax, [rcx]
0x18000c6d1  mov     rax, [rax+10h]
0x18000c6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6da  mov     rcx, [rsp+68h+Ptr]
0x18000c6e2  mov     rax, [rcx]
0x18000c6e5  mov     rax, [rax+10h]
0x18000c6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ee  jmp     short loc_18000C6F8
0x18000c6f0  mov     rbx, [rsp+68h+Ptr]
0x18000c6f8  mov     [r14], rbx
0x18000c6fb  xor     eax, eax
0x18000c6fd  add     rsp, 38h
0x18000c701  pop     r15
0x18000c703  pop     r14
0x18000c705  pop     rdi
0x18000c706  pop     rsi
0x18000c707  pop     rbp
0x18000c708  pop     rbx
0x18000c709  retn
```
