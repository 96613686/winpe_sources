# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180004374`
- end: `0x1800044fa`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800073d0`

## callees

- `0x180004374`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800043c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800043c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004405`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000441a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004405`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000441a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004460`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004460`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800044ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800044ab`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800043d6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000448b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800043d6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000448b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000447c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000447c`

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
0x180004374  mov     rax, rsp
0x180004377  push    rbx
0x180004378  push    rbp
0x180004379  push    rsi
0x18000437a  push    rdi
0x18000437b  push    r14
0x18000437d  push    r15
0x18000437f  sub     rsp, 38h
0x180004383  mov     rdi, r9
0x180004386  mov     r15, r8
0x180004389  mov     rbp, rdx
0x18000438c  mov     rsi, rcx
0x18000438f  mov     r14, [rsp+68h+Ptr]
0x180004397  mov     qword ptr [r14], 0
0x18000439e  mov     qword ptr [rax+28h], 0
0x1800043a6  mov     rax, [r9+18h]
0x1800043aa  mov     r10, [rax]
0x1800043ad  test    r10, r10
0x1800043b0  jz      short loc_180004420
0x1800043b2  mov     rax, [rcx]
0x1800043b5  mov     rax, [rax+38h]
0x1800043b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043be  mov     rbx, rax
0x1800043c1  mov     rcx, rax; SRWLock
0x1800043c4  call    cs:__imp_AcquireSRWLockShared
0x1800043ca  mov     rcx, [rdi+18h]
0x1800043ce  mov     rcx, [rcx]; Ptr
0x1800043d1  test    rcx, rcx
0x1800043d4  jz      short loc_180004412
0x1800043d6  call    cs:__imp_DecodePointer
0x1800043dc  mov     r9, rax
0x1800043df  mov     [rsp+68h+Ptr], rax
0x1800043e7  mov     rcx, [rax]
0x1800043ea  mov     rax, [rcx]
0x1800043ed  mov     r8, r14
0x1800043f0  mov     rdx, r15
0x1800043f3  mov     rcx, r9
0x1800043f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fb  mov     edi, eax
0x1800043fd  test    rbx, rbx
0x180004400  jz      short loc_18000440B
0x180004402  mov     rcx, rbx; SRWLock
0x180004405  call    cs:__imp_ReleaseSRWLockShared
0x18000440b  mov     eax, edi
0x18000440d  jmp     loc_1800044ED
0x180004412  test    rbx, rbx
0x180004415  jz      short loc_180004420
0x180004417  mov     rcx, rbx; SRWLock
0x18000441a  call    cs:__imp_ReleaseSRWLockShared
0x180004420  lea     r9, [rsp+68h+Ptr]
0x180004428  mov     r8, r15
0x18000442b  mov     rdx, rdi
0x18000442e  mov     rcx, rbp
0x180004431  mov     rax, [rdi]
0x180004434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004439  test    eax, eax
0x18000443b  js      loc_1800044ED
0x180004441  test    byte ptr [rbp+0], 4
0x180004445  jnz     loc_1800044E0
0x18000444b  mov     rax, [rsi]
0x18000444e  mov     rcx, rsi
0x180004451  mov     rax, [rax+38h]
0x180004455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000445a  mov     rsi, rax
0x18000445d  mov     rcx, rax; SRWLock
0x180004460  call    cs:__imp_AcquireSRWLockExclusive
0x180004466  mov     rcx, [rdi+18h]
0x18000446a  mov     rcx, [rcx]; Ptr
0x18000446d  test    rcx, rcx
0x180004470  jnz     short loc_18000448B
0x180004472  xor     ebx, ebx
0x180004474  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000447c  call    cs:__imp_EncodePointer
0x180004482  mov     rcx, [rdi+18h]
0x180004486  mov     [rcx], rax
0x180004489  jmp     short loc_1800044A3
0x18000448b  call    cs:__imp_DecodePointer
0x180004491  mov     rbx, rax
0x180004494  mov     rcx, [rax]
0x180004497  mov     rax, [rcx+8]
0x18000449b  mov     rcx, rbx
0x18000449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a3  test    rsi, rsi
0x1800044a6  jz      short loc_1800044B1
0x1800044a8  mov     rcx, rsi; SRWLock
0x1800044ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800044b1  test    rbx, rbx
0x1800044b4  jz      short loc_1800044E0
0x1800044b6  mov     rcx, [rsp+68h+Ptr]
0x1800044be  mov     rax, [rcx]
0x1800044c1  mov     rax, [rax+10h]
0x1800044c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ca  mov     rcx, [rsp+68h+Ptr]
0x1800044d2  mov     rax, [rcx]
0x1800044d5  mov     rax, [rax+10h]
0x1800044d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044de  jmp     short loc_1800044E8
0x1800044e0  mov     rbx, [rsp+68h+Ptr]
0x1800044e8  mov     [r14], rbx
0x1800044eb  xor     eax, eax
0x1800044ed  add     rsp, 38h
0x1800044f1  pop     r15
0x1800044f3  pop     r14
0x1800044f5  pop     rdi
0x1800044f6  pop     rsi
0x1800044f7  pop     rbp
0x1800044f8  pop     rbx
0x1800044f9  retn
```
