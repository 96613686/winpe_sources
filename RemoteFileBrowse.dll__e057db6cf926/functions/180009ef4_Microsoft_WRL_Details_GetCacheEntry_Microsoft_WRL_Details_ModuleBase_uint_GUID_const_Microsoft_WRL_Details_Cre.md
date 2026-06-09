# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009ef4`
- end: `0x18000a07a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000afe0`

## callees

- `0x180009ef4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009f44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009f44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a02b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a02b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009fe0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009f9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009f9a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009ffc`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009ffc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009f56`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000a00b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009f56`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000a00b`

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
0x180009ef4  mov     rax, rsp
0x180009ef7  push    rbx
0x180009ef8  push    rbp
0x180009ef9  push    rsi
0x180009efa  push    rdi
0x180009efb  push    r14
0x180009efd  push    r15
0x180009eff  sub     rsp, 38h
0x180009f03  mov     rdi, r9
0x180009f06  mov     r15, r8
0x180009f09  mov     rbp, rdx
0x180009f0c  mov     rsi, rcx
0x180009f0f  mov     r14, [rsp+68h+Ptr]
0x180009f17  mov     qword ptr [r14], 0
0x180009f1e  mov     qword ptr [rax+28h], 0
0x180009f26  mov     rax, [r9+18h]
0x180009f2a  mov     r10, [rax]
0x180009f2d  test    r10, r10
0x180009f30  jz      short loc_180009FA0
0x180009f32  mov     rax, [rcx]
0x180009f35  mov     rax, [rax+38h]
0x180009f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3e  mov     rbx, rax
0x180009f41  mov     rcx, rax; SRWLock
0x180009f44  call    cs:__imp_AcquireSRWLockShared
0x180009f4a  mov     rcx, [rdi+18h]
0x180009f4e  mov     rcx, [rcx]; Ptr
0x180009f51  test    rcx, rcx
0x180009f54  jz      short loc_180009F92
0x180009f56  call    cs:__imp_DecodePointer
0x180009f5c  mov     r9, rax
0x180009f5f  mov     [rsp+68h+Ptr], rax
0x180009f67  mov     rcx, [rax]
0x180009f6a  mov     rax, [rcx]
0x180009f6d  mov     r8, r14
0x180009f70  mov     rdx, r15
0x180009f73  mov     rcx, r9
0x180009f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f7b  mov     edi, eax
0x180009f7d  test    rbx, rbx
0x180009f80  jz      short loc_180009F8B
0x180009f82  mov     rcx, rbx; SRWLock
0x180009f85  call    cs:__imp_ReleaseSRWLockShared
0x180009f8b  mov     eax, edi
0x180009f8d  jmp     loc_18000A06D
0x180009f92  test    rbx, rbx
0x180009f95  jz      short loc_180009FA0
0x180009f97  mov     rcx, rbx; SRWLock
0x180009f9a  call    cs:__imp_ReleaseSRWLockShared
0x180009fa0  lea     r9, [rsp+68h+Ptr]
0x180009fa8  mov     r8, r15
0x180009fab  mov     rdx, rdi
0x180009fae  mov     rcx, rbp
0x180009fb1  mov     rax, [rdi]
0x180009fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb9  test    eax, eax
0x180009fbb  js      loc_18000A06D
0x180009fc1  test    byte ptr [rbp+0], 4
0x180009fc5  jnz     loc_18000A060
0x180009fcb  mov     rax, [rsi]
0x180009fce  mov     rcx, rsi
0x180009fd1  mov     rax, [rax+38h]
0x180009fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fda  mov     rsi, rax
0x180009fdd  mov     rcx, rax; SRWLock
0x180009fe0  call    cs:__imp_AcquireSRWLockExclusive
0x180009fe6  mov     rcx, [rdi+18h]
0x180009fea  mov     rcx, [rcx]; Ptr
0x180009fed  test    rcx, rcx
0x180009ff0  jnz     short loc_18000A00B
0x180009ff2  xor     ebx, ebx
0x180009ff4  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180009ffc  call    cs:__imp_EncodePointer
0x18000a002  mov     rcx, [rdi+18h]
0x18000a006  mov     [rcx], rax
0x18000a009  jmp     short loc_18000A023
0x18000a00b  call    cs:__imp_DecodePointer
0x18000a011  mov     rbx, rax
0x18000a014  mov     rcx, [rax]
0x18000a017  mov     rax, [rcx+8]
0x18000a01b  mov     rcx, rbx
0x18000a01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a023  test    rsi, rsi
0x18000a026  jz      short loc_18000A031
0x18000a028  mov     rcx, rsi; SRWLock
0x18000a02b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a031  test    rbx, rbx
0x18000a034  jz      short loc_18000A060
0x18000a036  mov     rcx, [rsp+68h+Ptr]
0x18000a03e  mov     rax, [rcx]
0x18000a041  mov     rax, [rax+10h]
0x18000a045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a04a  mov     rcx, [rsp+68h+Ptr]
0x18000a052  mov     rax, [rcx]
0x18000a055  mov     rax, [rax+10h]
0x18000a059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a05e  jmp     short loc_18000A068
0x18000a060  mov     rbx, [rsp+68h+Ptr]
0x18000a068  mov     [r14], rbx
0x18000a06b  xor     eax, eax
0x18000a06d  add     rsp, 38h
0x18000a071  pop     r15
0x18000a073  pop     r14
0x18000a075  pop     rdi
0x18000a076  pop     rsi
0x18000a077  pop     rbp
0x18000a078  pop     rbx
0x18000a079  retn
```
