# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000afe4`
- end: `0x18000b16a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b390`

## callees

- `0x18000afe4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b034`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b034`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b075`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b08a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b075`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b08a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b11b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b11b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b0ec`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b0ec`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b046`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0fb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b046`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0fb`

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
0x18000afe4  mov     rax, rsp
0x18000afe7  push    rbx
0x18000afe8  push    rbp
0x18000afe9  push    rsi
0x18000afea  push    rdi
0x18000afeb  push    r14
0x18000afed  push    r15
0x18000afef  sub     rsp, 38h
0x18000aff3  mov     rdi, r9
0x18000aff6  mov     r15, r8
0x18000aff9  mov     rbp, rdx
0x18000affc  mov     rsi, rcx
0x18000afff  mov     r14, [rsp+68h+Ptr]
0x18000b007  mov     qword ptr [r14], 0
0x18000b00e  mov     qword ptr [rax+28h], 0
0x18000b016  mov     rax, [r9+18h]
0x18000b01a  mov     r10, [rax]
0x18000b01d  test    r10, r10
0x18000b020  jz      short loc_18000B090
0x18000b022  mov     rax, [rcx]
0x18000b025  mov     rax, [rax+38h]
0x18000b029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02e  mov     rbx, rax
0x18000b031  mov     rcx, rax; SRWLock
0x18000b034  call    cs:__imp_AcquireSRWLockShared
0x18000b03a  mov     rcx, [rdi+18h]
0x18000b03e  mov     rcx, [rcx]; Ptr
0x18000b041  test    rcx, rcx
0x18000b044  jz      short loc_18000B082
0x18000b046  call    cs:__imp_DecodePointer
0x18000b04c  mov     r9, rax
0x18000b04f  mov     [rsp+68h+Ptr], rax
0x18000b057  mov     rcx, [rax]
0x18000b05a  mov     rax, [rcx]
0x18000b05d  mov     r8, r14
0x18000b060  mov     rdx, r15
0x18000b063  mov     rcx, r9
0x18000b066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b06b  mov     edi, eax
0x18000b06d  test    rbx, rbx
0x18000b070  jz      short loc_18000B07B
0x18000b072  mov     rcx, rbx; SRWLock
0x18000b075  call    cs:__imp_ReleaseSRWLockShared
0x18000b07b  mov     eax, edi
0x18000b07d  jmp     loc_18000B15D
0x18000b082  test    rbx, rbx
0x18000b085  jz      short loc_18000B090
0x18000b087  mov     rcx, rbx; SRWLock
0x18000b08a  call    cs:__imp_ReleaseSRWLockShared
0x18000b090  lea     r9, [rsp+68h+Ptr]
0x18000b098  mov     r8, r15
0x18000b09b  mov     rdx, rdi
0x18000b09e  mov     rcx, rbp
0x18000b0a1  mov     rax, [rdi]
0x18000b0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0a9  test    eax, eax
0x18000b0ab  js      loc_18000B15D
0x18000b0b1  test    byte ptr [rbp+0], 4
0x18000b0b5  jnz     loc_18000B150
0x18000b0bb  mov     rax, [rsi]
0x18000b0be  mov     rcx, rsi
0x18000b0c1  mov     rax, [rax+38h]
0x18000b0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ca  mov     rsi, rax
0x18000b0cd  mov     rcx, rax; SRWLock
0x18000b0d0  call    cs:__imp_AcquireSRWLockExclusive
0x18000b0d6  mov     rcx, [rdi+18h]
0x18000b0da  mov     rcx, [rcx]; Ptr
0x18000b0dd  test    rcx, rcx
0x18000b0e0  jnz     short loc_18000B0FB
0x18000b0e2  xor     ebx, ebx
0x18000b0e4  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000b0ec  call    cs:__imp_EncodePointer
0x18000b0f2  mov     rcx, [rdi+18h]
0x18000b0f6  mov     [rcx], rax
0x18000b0f9  jmp     short loc_18000B113
0x18000b0fb  call    cs:__imp_DecodePointer
0x18000b101  mov     rbx, rax
0x18000b104  mov     rcx, [rax]
0x18000b107  mov     rax, [rcx+8]
0x18000b10b  mov     rcx, rbx
0x18000b10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b113  test    rsi, rsi
0x18000b116  jz      short loc_18000B121
0x18000b118  mov     rcx, rsi; SRWLock
0x18000b11b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b121  test    rbx, rbx
0x18000b124  jz      short loc_18000B150
0x18000b126  mov     rcx, [rsp+68h+Ptr]
0x18000b12e  mov     rax, [rcx]
0x18000b131  mov     rax, [rax+10h]
0x18000b135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b13a  mov     rcx, [rsp+68h+Ptr]
0x18000b142  mov     rax, [rcx]
0x18000b145  mov     rax, [rax+10h]
0x18000b149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b14e  jmp     short loc_18000B158
0x18000b150  mov     rbx, [rsp+68h+Ptr]
0x18000b158  mov     [r14], rbx
0x18000b15b  xor     eax, eax
0x18000b15d  add     rsp, 38h
0x18000b161  pop     r15
0x18000b163  pop     r14
0x18000b165  pop     rdi
0x18000b166  pop     rsi
0x18000b167  pop     rbp
0x18000b168  pop     rbx
0x18000b169  retn
```
