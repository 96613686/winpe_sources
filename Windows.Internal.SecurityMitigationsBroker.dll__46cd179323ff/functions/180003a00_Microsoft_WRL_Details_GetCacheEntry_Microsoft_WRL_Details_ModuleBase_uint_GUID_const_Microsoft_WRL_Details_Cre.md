# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180003a00`
- end: `0x180003b86`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003850`
- `0x180004110`

## callees

- `0x180003a00`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003a62`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003b17`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003a62`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003b17`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003b08`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003b08`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003a50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003a50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003a91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003aa6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003a91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003aa6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003aec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003aec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b37`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        _QWORD *Ptr)
{
  _QWORD *v5; // r14
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rcx
  unsigned int v12; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v14; // rsi
  void *v15; // rcx
  PVOID v16; // rbx

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
    *v5 = v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003a00  mov     rax, rsp
0x180003a03  push    rbx
0x180003a04  push    rbp
0x180003a05  push    rsi
0x180003a06  push    rdi
0x180003a07  push    r14
0x180003a09  push    r15
0x180003a0b  sub     rsp, 38h
0x180003a0f  mov     r14, [rsp+68h+Ptr]
0x180003a17  mov     rdi, r9
0x180003a1a  mov     qword ptr [rax+28h], 0
0x180003a22  mov     r15, r8
0x180003a25  mov     rbp, rdx
0x180003a28  mov     rsi, rcx
0x180003a2b  mov     qword ptr [r14], 0
0x180003a32  mov     rax, [r9+18h]
0x180003a36  mov     r10, [rax]
0x180003a39  test    r10, r10
0x180003a3c  jz      short loc_180003AAC
0x180003a3e  mov     rax, [rcx]
0x180003a41  mov     rax, [rax+38h]
0x180003a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4a  mov     rcx, rax; SRWLock
0x180003a4d  mov     rbx, rax
0x180003a50  call    cs:__imp_AcquireSRWLockShared
0x180003a56  mov     rcx, [rdi+18h]
0x180003a5a  mov     rcx, [rcx]; Ptr
0x180003a5d  test    rcx, rcx
0x180003a60  jz      short loc_180003A9E
0x180003a62  call    cs:__imp_DecodePointer
0x180003a68  mov     [rsp+68h+Ptr], rax
0x180003a70  mov     r8, r14
0x180003a73  mov     r9, rax
0x180003a76  mov     rdx, r15
0x180003a79  mov     rcx, [rax]
0x180003a7c  mov     rax, [rcx]
0x180003a7f  mov     rcx, r9
0x180003a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a87  mov     edi, eax
0x180003a89  test    rbx, rbx
0x180003a8c  jz      short loc_180003A97
0x180003a8e  mov     rcx, rbx; SRWLock
0x180003a91  call    cs:__imp_ReleaseSRWLockShared
0x180003a97  mov     eax, edi
0x180003a99  jmp     loc_180003B79
0x180003a9e  test    rbx, rbx
0x180003aa1  jz      short loc_180003AAC
0x180003aa3  mov     rcx, rbx; SRWLock
0x180003aa6  call    cs:__imp_ReleaseSRWLockShared
0x180003aac  mov     rax, [rdi]
0x180003aaf  lea     r9, [rsp+68h+Ptr]
0x180003ab7  mov     r8, r15
0x180003aba  mov     rdx, rdi
0x180003abd  mov     rcx, rbp
0x180003ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac5  test    eax, eax
0x180003ac7  js      loc_180003B79
0x180003acd  test    byte ptr [rbp+0], 4
0x180003ad1  jnz     loc_180003B6C
0x180003ad7  mov     rax, [rsi]
0x180003ada  mov     rcx, rsi
0x180003add  mov     rax, [rax+38h]
0x180003ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae6  mov     rcx, rax; SRWLock
0x180003ae9  mov     rsi, rax
0x180003aec  call    cs:__imp_AcquireSRWLockExclusive
0x180003af2  mov     rcx, [rdi+18h]
0x180003af6  mov     rcx, [rcx]; Ptr
0x180003af9  test    rcx, rcx
0x180003afc  jnz     short loc_180003B17
0x180003afe  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180003b06  xor     ebx, ebx
0x180003b08  call    cs:__imp_EncodePointer
0x180003b0e  mov     rcx, [rdi+18h]
0x180003b12  mov     [rcx], rax
0x180003b15  jmp     short loc_180003B2F
0x180003b17  call    cs:__imp_DecodePointer
0x180003b1d  mov     rbx, rax
0x180003b20  mov     rcx, [rax]
0x180003b23  mov     rax, [rcx+8]
0x180003b27  mov     rcx, rbx
0x180003b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2f  test    rsi, rsi
0x180003b32  jz      short loc_180003B3D
0x180003b34  mov     rcx, rsi; SRWLock
0x180003b37  call    cs:__imp_ReleaseSRWLockExclusive
0x180003b3d  test    rbx, rbx
0x180003b40  jz      short loc_180003B6C
0x180003b42  mov     rcx, [rsp+68h+Ptr]
0x180003b4a  mov     rax, [rcx]
0x180003b4d  mov     rax, [rax+10h]
0x180003b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b56  mov     rcx, [rsp+68h+Ptr]
0x180003b5e  mov     rax, [rcx]
0x180003b61  mov     rax, [rax+10h]
0x180003b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b6a  jmp     short loc_180003B74
0x180003b6c  mov     rbx, [rsp+68h+Ptr]
0x180003b74  mov     [r14], rbx
0x180003b77  xor     eax, eax
0x180003b79  add     rsp, 38h
0x180003b7d  pop     r15
0x180003b7f  pop     r14
0x180003b81  pop     rdi
0x180003b82  pop     rsi
0x180003b83  pop     rbp
0x180003b84  pop     rbx
0x180003b85  retn
```
