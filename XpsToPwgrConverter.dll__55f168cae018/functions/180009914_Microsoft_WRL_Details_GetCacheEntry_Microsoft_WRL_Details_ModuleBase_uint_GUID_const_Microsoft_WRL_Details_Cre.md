# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180009914`
- end: `0x180009a9a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009b90`

## callees

- `0x180009914`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800099a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800099ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800099a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800099ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009964`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009964`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009976`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009a2b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009976`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180009a2b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009a1c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180009a1c`

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
0x180009914  mov     rax, rsp
0x180009917  push    rbx
0x180009918  push    rbp
0x180009919  push    rsi
0x18000991a  push    rdi
0x18000991b  push    r14
0x18000991d  push    r15
0x18000991f  sub     rsp, 38h
0x180009923  mov     rdi, r9
0x180009926  mov     r15, r8
0x180009929  mov     rbp, rdx
0x18000992c  mov     rsi, rcx
0x18000992f  mov     r14, [rsp+68h+Ptr]
0x180009937  mov     qword ptr [r14], 0
0x18000993e  mov     qword ptr [rax+28h], 0
0x180009946  mov     rax, [r9+18h]
0x18000994a  mov     r10, [rax]
0x18000994d  test    r10, r10
0x180009950  jz      short loc_1800099C0
0x180009952  mov     rax, [rcx]
0x180009955  mov     rax, [rax+38h]
0x180009959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000995e  mov     rbx, rax
0x180009961  mov     rcx, rax; SRWLock
0x180009964  call    cs:__imp_AcquireSRWLockShared
0x18000996a  mov     rcx, [rdi+18h]
0x18000996e  mov     rcx, [rcx]; Ptr
0x180009971  test    rcx, rcx
0x180009974  jz      short loc_1800099B2
0x180009976  call    cs:__imp_DecodePointer
0x18000997c  mov     r9, rax
0x18000997f  mov     [rsp+68h+Ptr], rax
0x180009987  mov     rcx, [rax]
0x18000998a  mov     rax, [rcx]
0x18000998d  mov     r8, r14
0x180009990  mov     rdx, r15
0x180009993  mov     rcx, r9
0x180009996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000999b  mov     edi, eax
0x18000999d  test    rbx, rbx
0x1800099a0  jz      short loc_1800099AB
0x1800099a2  mov     rcx, rbx; SRWLock
0x1800099a5  call    cs:__imp_ReleaseSRWLockShared
0x1800099ab  mov     eax, edi
0x1800099ad  jmp     loc_180009A8D
0x1800099b2  test    rbx, rbx
0x1800099b5  jz      short loc_1800099C0
0x1800099b7  mov     rcx, rbx; SRWLock
0x1800099ba  call    cs:__imp_ReleaseSRWLockShared
0x1800099c0  lea     r9, [rsp+68h+Ptr]
0x1800099c8  mov     r8, r15
0x1800099cb  mov     rdx, rdi
0x1800099ce  mov     rcx, rbp
0x1800099d1  mov     rax, [rdi]
0x1800099d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099d9  test    eax, eax
0x1800099db  js      loc_180009A8D
0x1800099e1  test    byte ptr [rbp+0], 4
0x1800099e5  jnz     loc_180009A80
0x1800099eb  mov     rax, [rsi]
0x1800099ee  mov     rcx, rsi
0x1800099f1  mov     rax, [rax+38h]
0x1800099f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099fa  mov     rsi, rax
0x1800099fd  mov     rcx, rax; SRWLock
0x180009a00  call    cs:__imp_AcquireSRWLockExclusive
0x180009a06  mov     rcx, [rdi+18h]
0x180009a0a  mov     rcx, [rcx]; Ptr
0x180009a0d  test    rcx, rcx
0x180009a10  jnz     short loc_180009A2B
0x180009a12  xor     ebx, ebx
0x180009a14  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180009a1c  call    cs:__imp_EncodePointer
0x180009a22  mov     rcx, [rdi+18h]
0x180009a26  mov     [rcx], rax
0x180009a29  jmp     short loc_180009A43
0x180009a2b  call    cs:__imp_DecodePointer
0x180009a31  mov     rbx, rax
0x180009a34  mov     rcx, [rax]
0x180009a37  mov     rax, [rcx+8]
0x180009a3b  mov     rcx, rbx
0x180009a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a43  test    rsi, rsi
0x180009a46  jz      short loc_180009A51
0x180009a48  mov     rcx, rsi; SRWLock
0x180009a4b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a51  test    rbx, rbx
0x180009a54  jz      short loc_180009A80
0x180009a56  mov     rcx, [rsp+68h+Ptr]
0x180009a5e  mov     rax, [rcx]
0x180009a61  mov     rax, [rax+10h]
0x180009a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a6a  mov     rcx, [rsp+68h+Ptr]
0x180009a72  mov     rax, [rcx]
0x180009a75  mov     rax, [rax+10h]
0x180009a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7e  jmp     short loc_180009A88
0x180009a80  mov     rbx, [rsp+68h+Ptr]
0x180009a88  mov     [r14], rbx
0x180009a8b  xor     eax, eax
0x180009a8d  add     rsp, 38h
0x180009a91  pop     r15
0x180009a93  pop     r14
0x180009a95  pop     rdi
0x180009a96  pop     rsi
0x180009a97  pop     rbp
0x180009a98  pop     rbx
0x180009a99  retn
```
