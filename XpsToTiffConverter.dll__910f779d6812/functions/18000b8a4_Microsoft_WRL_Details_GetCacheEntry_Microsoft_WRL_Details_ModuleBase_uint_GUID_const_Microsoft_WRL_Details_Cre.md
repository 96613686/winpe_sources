# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000b8a4`
- end: `0x18000ba2a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bb20`

## callees

- `0x18000b8a4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b990`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b8f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b8f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b94a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b94a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b906`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b9bb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b906`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b9bb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b9ac`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b9ac`

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
0x18000b8a4  mov     rax, rsp
0x18000b8a7  push    rbx
0x18000b8a8  push    rbp
0x18000b8a9  push    rsi
0x18000b8aa  push    rdi
0x18000b8ab  push    r14
0x18000b8ad  push    r15
0x18000b8af  sub     rsp, 38h
0x18000b8b3  mov     rdi, r9
0x18000b8b6  mov     r15, r8
0x18000b8b9  mov     rbp, rdx
0x18000b8bc  mov     rsi, rcx
0x18000b8bf  mov     r14, [rsp+68h+Ptr]
0x18000b8c7  mov     qword ptr [r14], 0
0x18000b8ce  mov     qword ptr [rax+28h], 0
0x18000b8d6  mov     rax, [r9+18h]
0x18000b8da  mov     r10, [rax]
0x18000b8dd  test    r10, r10
0x18000b8e0  jz      short loc_18000B950
0x18000b8e2  mov     rax, [rcx]
0x18000b8e5  mov     rax, [rax+38h]
0x18000b8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ee  mov     rbx, rax
0x18000b8f1  mov     rcx, rax; SRWLock
0x18000b8f4  call    cs:__imp_AcquireSRWLockShared
0x18000b8fa  mov     rcx, [rdi+18h]
0x18000b8fe  mov     rcx, [rcx]; Ptr
0x18000b901  test    rcx, rcx
0x18000b904  jz      short loc_18000B942
0x18000b906  call    cs:__imp_DecodePointer
0x18000b90c  mov     r9, rax
0x18000b90f  mov     [rsp+68h+Ptr], rax
0x18000b917  mov     rcx, [rax]
0x18000b91a  mov     rax, [rcx]
0x18000b91d  mov     r8, r14
0x18000b920  mov     rdx, r15
0x18000b923  mov     rcx, r9
0x18000b926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b92b  mov     edi, eax
0x18000b92d  test    rbx, rbx
0x18000b930  jz      short loc_18000B93B
0x18000b932  mov     rcx, rbx; SRWLock
0x18000b935  call    cs:__imp_ReleaseSRWLockShared
0x18000b93b  mov     eax, edi
0x18000b93d  jmp     loc_18000BA1D
0x18000b942  test    rbx, rbx
0x18000b945  jz      short loc_18000B950
0x18000b947  mov     rcx, rbx; SRWLock
0x18000b94a  call    cs:__imp_ReleaseSRWLockShared
0x18000b950  lea     r9, [rsp+68h+Ptr]
0x18000b958  mov     r8, r15
0x18000b95b  mov     rdx, rdi
0x18000b95e  mov     rcx, rbp
0x18000b961  mov     rax, [rdi]
0x18000b964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b969  test    eax, eax
0x18000b96b  js      loc_18000BA1D
0x18000b971  test    byte ptr [rbp+0], 4
0x18000b975  jnz     loc_18000BA10
0x18000b97b  mov     rax, [rsi]
0x18000b97e  mov     rcx, rsi
0x18000b981  mov     rax, [rax+38h]
0x18000b985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b98a  mov     rsi, rax
0x18000b98d  mov     rcx, rax; SRWLock
0x18000b990  call    cs:__imp_AcquireSRWLockExclusive
0x18000b996  mov     rcx, [rdi+18h]
0x18000b99a  mov     rcx, [rcx]; Ptr
0x18000b99d  test    rcx, rcx
0x18000b9a0  jnz     short loc_18000B9BB
0x18000b9a2  xor     ebx, ebx
0x18000b9a4  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000b9ac  call    cs:__imp_EncodePointer
0x18000b9b2  mov     rcx, [rdi+18h]
0x18000b9b6  mov     [rcx], rax
0x18000b9b9  jmp     short loc_18000B9D3
0x18000b9bb  call    cs:__imp_DecodePointer
0x18000b9c1  mov     rbx, rax
0x18000b9c4  mov     rcx, [rax]
0x18000b9c7  mov     rax, [rcx+8]
0x18000b9cb  mov     rcx, rbx
0x18000b9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d3  test    rsi, rsi
0x18000b9d6  jz      short loc_18000B9E1
0x18000b9d8  mov     rcx, rsi; SRWLock
0x18000b9db  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b9e1  test    rbx, rbx
0x18000b9e4  jz      short loc_18000BA10
0x18000b9e6  mov     rcx, [rsp+68h+Ptr]
0x18000b9ee  mov     rax, [rcx]
0x18000b9f1  mov     rax, [rax+10h]
0x18000b9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9fa  mov     rcx, [rsp+68h+Ptr]
0x18000ba02  mov     rax, [rcx]
0x18000ba05  mov     rax, [rax+10h]
0x18000ba09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba0e  jmp     short loc_18000BA18
0x18000ba10  mov     rbx, [rsp+68h+Ptr]
0x18000ba18  mov     [r14], rbx
0x18000ba1b  xor     eax, eax
0x18000ba1d  add     rsp, 38h
0x18000ba21  pop     r15
0x18000ba23  pop     r14
0x18000ba25  pop     rdi
0x18000ba26  pop     rsi
0x18000ba27  pop     rbp
0x18000ba28  pop     rbx
0x18000ba29  retn
```
