# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x14000a0b8`
- end: `0x14000a23c`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006d90`

## callees

- `0x14000a0b8`
- `0x14000f010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a1a8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a1a8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a1f0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a1f0`
- `KERNEL32!AcquireSRWLockShared` at `0x14000a10a`
- `KERNEL32!AcquireSRWLockShared` at `0x14000a10a`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a14c`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a161`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a14c`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a161`
- `KERNEL32!DecodePointer` at `0x14000a11c`
- `KERNEL32!DecodePointer` at `0x14000a1d0`
- `KERNEL32!DecodePointer` at `0x14000a11c`
- `KERNEL32!DecodePointer` at `0x14000a1d0`
- `KERNEL32!EncodePointer` at `0x14000a1c1`
- `KERNEL32!EncodePointer` at `0x14000a1c1`

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
0x14000a0b8  mov     rax, rsp
0x14000a0bb  mov     [rax+8], rbx
0x14000a0bf  mov     [rax+10h], rbp
0x14000a0c3  mov     [rax+18h], r8
0x14000a0c7  push    rsi
0x14000a0c8  push    rdi
0x14000a0c9  push    r14
0x14000a0cb  sub     rsp, 30h
0x14000a0cf  mov     rdi, r9
0x14000a0d2  mov     rbp, rdx
0x14000a0d5  mov     rsi, rcx
0x14000a0d8  mov     r14, [rsp+48h+arg_20]
0x14000a0dd  mov     qword ptr [r14], 0
0x14000a0e4  mov     qword ptr [rax+18h], 0
0x14000a0ec  mov     rax, [r9+18h]
0x14000a0f0  mov     r8, [rax]
0x14000a0f3  test    r8, r8
0x14000a0f6  jz      short loc_14000A167
0x14000a0f8  mov     rax, [rcx]
0x14000a0fb  mov     rax, [rax+38h]
0x14000a0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a104  mov     rbx, rax
0x14000a107  mov     rcx, rax; SRWLock
0x14000a10a  call    cs:__imp_AcquireSRWLockShared
0x14000a110  mov     rcx, [rdi+18h]
0x14000a114  mov     rcx, [rcx]; Ptr
0x14000a117  test    rcx, rcx
0x14000a11a  jz      short loc_14000A159
0x14000a11c  call    cs:__imp_DecodePointer
0x14000a122  mov     r9, rax
0x14000a125  mov     [rsp+48h+Ptr], rax
0x14000a12a  mov     rcx, [rax]
0x14000a12d  mov     rax, [rcx]
0x14000a130  mov     r8, r14
0x14000a133  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x14000a13a  mov     rcx, r9
0x14000a13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a142  mov     edi, eax
0x14000a144  test    rbx, rbx
0x14000a147  jz      short loc_14000A152
0x14000a149  mov     rcx, rbx; SRWLock
0x14000a14c  call    cs:__imp_ReleaseSRWLockShared
0x14000a152  mov     eax, edi
0x14000a154  jmp     loc_14000A229
0x14000a159  test    rbx, rbx
0x14000a15c  jz      short loc_14000A167
0x14000a15e  mov     rcx, rbx; SRWLock
0x14000a161  call    cs:__imp_ReleaseSRWLockShared
0x14000a167  lea     r9, [rsp+48h+Ptr]
0x14000a16c  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x14000a173  mov     rdx, rdi
0x14000a176  mov     rcx, rbp
0x14000a179  mov     rax, [rdi]
0x14000a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a181  test    eax, eax
0x14000a183  js      loc_14000A229
0x14000a189  test    byte ptr [rbp+0], 4
0x14000a18d  jnz     loc_14000A21F
0x14000a193  mov     rax, [rsi]
0x14000a196  mov     rcx, rsi
0x14000a199  mov     rax, [rax+38h]
0x14000a19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1a2  mov     rsi, rax
0x14000a1a5  mov     rcx, rax; SRWLock
0x14000a1a8  call    cs:__imp_AcquireSRWLockExclusive
0x14000a1ae  mov     rcx, [rdi+18h]
0x14000a1b2  mov     rcx, [rcx]; Ptr
0x14000a1b5  test    rcx, rcx
0x14000a1b8  jnz     short loc_14000A1D0
0x14000a1ba  xor     ebx, ebx
0x14000a1bc  mov     rcx, [rsp+48h+Ptr]; Ptr
0x14000a1c1  call    cs:__imp_EncodePointer
0x14000a1c7  mov     rcx, [rdi+18h]
0x14000a1cb  mov     [rcx], rax
0x14000a1ce  jmp     short loc_14000A1E8
0x14000a1d0  call    cs:__imp_DecodePointer
0x14000a1d6  mov     rbx, rax
0x14000a1d9  mov     rcx, [rax]
0x14000a1dc  mov     rax, [rcx+8]
0x14000a1e0  mov     rcx, rbx
0x14000a1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1e8  test    rsi, rsi
0x14000a1eb  jz      short loc_14000A1F6
0x14000a1ed  mov     rcx, rsi; SRWLock
0x14000a1f0  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a1f6  test    rbx, rbx
0x14000a1f9  jz      short loc_14000A21F
0x14000a1fb  mov     rcx, [rsp+48h+Ptr]
0x14000a200  mov     rax, [rcx]
0x14000a203  mov     rax, [rax+10h]
0x14000a207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a20c  mov     rcx, [rsp+48h+Ptr]
0x14000a211  mov     rax, [rcx]
0x14000a214  mov     rax, [rax+10h]
0x14000a218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a21d  jmp     short loc_14000A224
0x14000a21f  mov     rbx, [rsp+48h+Ptr]
0x14000a224  mov     [r14], rbx
0x14000a227  xor     eax, eax
0x14000a229  mov     rbx, [rsp+48h+arg_0]
0x14000a22e  mov     rbp, [rsp+48h+arg_8]
0x14000a233  add     rsp, 30h
0x14000a237  pop     r14
0x14000a239  pop     rdi
0x14000a23a  pop     rsi
0x14000a23b  retn
```
