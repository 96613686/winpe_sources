# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000b158`
- end: `0x18000b2de`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b940`
- `0x18000bb00`

## callees

- `0x18000b158`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b244`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b28f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b28f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b1a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b1a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b1fe`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b1ba`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b26f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b1ba`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b26f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b260`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b260`

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
0x18000b158  mov     rax, rsp
0x18000b15b  push    rbx
0x18000b15c  push    rbp
0x18000b15d  push    rsi
0x18000b15e  push    rdi
0x18000b15f  push    r14
0x18000b161  push    r15
0x18000b163  sub     rsp, 38h
0x18000b167  mov     rdi, r9
0x18000b16a  mov     r15, r8
0x18000b16d  mov     rbp, rdx
0x18000b170  mov     rsi, rcx
0x18000b173  mov     r14, [rsp+68h+Ptr]
0x18000b17b  mov     qword ptr [r14], 0
0x18000b182  mov     qword ptr [rax+28h], 0
0x18000b18a  mov     rax, [r9+18h]
0x18000b18e  mov     r10, [rax]
0x18000b191  test    r10, r10
0x18000b194  jz      short loc_18000B204
0x18000b196  mov     rax, [rcx]
0x18000b199  mov     rax, [rax+38h]
0x18000b19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1a2  mov     rbx, rax
0x18000b1a5  mov     rcx, rax; SRWLock
0x18000b1a8  call    cs:__imp_AcquireSRWLockShared
0x18000b1ae  mov     rcx, [rdi+18h]
0x18000b1b2  mov     rcx, [rcx]; Ptr
0x18000b1b5  test    rcx, rcx
0x18000b1b8  jz      short loc_18000B1F6
0x18000b1ba  call    cs:__imp_DecodePointer
0x18000b1c0  mov     r9, rax
0x18000b1c3  mov     [rsp+68h+Ptr], rax
0x18000b1cb  mov     rcx, [rax]
0x18000b1ce  mov     rax, [rcx]
0x18000b1d1  mov     r8, r14
0x18000b1d4  mov     rdx, r15
0x18000b1d7  mov     rcx, r9
0x18000b1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1df  mov     edi, eax
0x18000b1e1  test    rbx, rbx
0x18000b1e4  jz      short loc_18000B1EF
0x18000b1e6  mov     rcx, rbx; SRWLock
0x18000b1e9  call    cs:__imp_ReleaseSRWLockShared
0x18000b1ef  mov     eax, edi
0x18000b1f1  jmp     loc_18000B2D1
0x18000b1f6  test    rbx, rbx
0x18000b1f9  jz      short loc_18000B204
0x18000b1fb  mov     rcx, rbx; SRWLock
0x18000b1fe  call    cs:__imp_ReleaseSRWLockShared
0x18000b204  lea     r9, [rsp+68h+Ptr]
0x18000b20c  mov     r8, r15
0x18000b20f  mov     rdx, rdi
0x18000b212  mov     rcx, rbp
0x18000b215  mov     rax, [rdi]
0x18000b218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b21d  test    eax, eax
0x18000b21f  js      loc_18000B2D1
0x18000b225  test    byte ptr [rbp+0], 4
0x18000b229  jnz     loc_18000B2C4
0x18000b22f  mov     rax, [rsi]
0x18000b232  mov     rcx, rsi
0x18000b235  mov     rax, [rax+38h]
0x18000b239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b23e  mov     rsi, rax
0x18000b241  mov     rcx, rax; SRWLock
0x18000b244  call    cs:__imp_AcquireSRWLockExclusive
0x18000b24a  mov     rcx, [rdi+18h]
0x18000b24e  mov     rcx, [rcx]; Ptr
0x18000b251  test    rcx, rcx
0x18000b254  jnz     short loc_18000B26F
0x18000b256  xor     ebx, ebx
0x18000b258  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000b260  call    cs:__imp_EncodePointer
0x18000b266  mov     rcx, [rdi+18h]
0x18000b26a  mov     [rcx], rax
0x18000b26d  jmp     short loc_18000B287
0x18000b26f  call    cs:__imp_DecodePointer
0x18000b275  mov     rbx, rax
0x18000b278  mov     rcx, [rax]
0x18000b27b  mov     rax, [rcx+8]
0x18000b27f  mov     rcx, rbx
0x18000b282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b287  test    rsi, rsi
0x18000b28a  jz      short loc_18000B295
0x18000b28c  mov     rcx, rsi; SRWLock
0x18000b28f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b295  test    rbx, rbx
0x18000b298  jz      short loc_18000B2C4
0x18000b29a  mov     rcx, [rsp+68h+Ptr]
0x18000b2a2  mov     rax, [rcx]
0x18000b2a5  mov     rax, [rax+10h]
0x18000b2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ae  mov     rcx, [rsp+68h+Ptr]
0x18000b2b6  mov     rax, [rcx]
0x18000b2b9  mov     rax, [rax+10h]
0x18000b2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c2  jmp     short loc_18000B2CC
0x18000b2c4  mov     rbx, [rsp+68h+Ptr]
0x18000b2cc  mov     [r14], rbx
0x18000b2cf  xor     eax, eax
0x18000b2d1  add     rsp, 38h
0x18000b2d5  pop     r15
0x18000b2d7  pop     r14
0x18000b2d9  pop     rdi
0x18000b2da  pop     rsi
0x18000b2db  pop     rbp
0x18000b2dc  pop     rbx
0x18000b2dd  retn
```
