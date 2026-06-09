# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180005d34`
- end: `0x180005eba`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800062c0`
- `0x180006480`

## callees

- `0x180005d34`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005dc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005dda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005dc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005dda`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005d84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005d84`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005d96`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005e4b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005d96`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005e4b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005e3c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005e3c`

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
0x180005d34  mov     rax, rsp
0x180005d37  push    rbx
0x180005d38  push    rbp
0x180005d39  push    rsi
0x180005d3a  push    rdi
0x180005d3b  push    r14
0x180005d3d  push    r15
0x180005d3f  sub     rsp, 38h
0x180005d43  mov     rdi, r9
0x180005d46  mov     r15, r8
0x180005d49  mov     rbp, rdx
0x180005d4c  mov     rsi, rcx
0x180005d4f  mov     r14, [rsp+68h+Ptr]
0x180005d57  mov     qword ptr [r14], 0
0x180005d5e  mov     qword ptr [rax+28h], 0
0x180005d66  mov     rax, [r9+18h]
0x180005d6a  mov     r10, [rax]
0x180005d6d  test    r10, r10
0x180005d70  jz      short loc_180005DE0
0x180005d72  mov     rax, [rcx]
0x180005d75  mov     rax, [rax+38h]
0x180005d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d7e  mov     rbx, rax
0x180005d81  mov     rcx, rax; SRWLock
0x180005d84  call    cs:__imp_AcquireSRWLockShared
0x180005d8a  mov     rcx, [rdi+18h]
0x180005d8e  mov     rcx, [rcx]; Ptr
0x180005d91  test    rcx, rcx
0x180005d94  jz      short loc_180005DD2
0x180005d96  call    cs:__imp_DecodePointer
0x180005d9c  mov     r9, rax
0x180005d9f  mov     [rsp+68h+Ptr], rax
0x180005da7  mov     rcx, [rax]
0x180005daa  mov     rax, [rcx]
0x180005dad  mov     r8, r14
0x180005db0  mov     rdx, r15
0x180005db3  mov     rcx, r9
0x180005db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbb  mov     edi, eax
0x180005dbd  test    rbx, rbx
0x180005dc0  jz      short loc_180005DCB
0x180005dc2  mov     rcx, rbx; SRWLock
0x180005dc5  call    cs:__imp_ReleaseSRWLockShared
0x180005dcb  mov     eax, edi
0x180005dcd  jmp     loc_180005EAD
0x180005dd2  test    rbx, rbx
0x180005dd5  jz      short loc_180005DE0
0x180005dd7  mov     rcx, rbx; SRWLock
0x180005dda  call    cs:__imp_ReleaseSRWLockShared
0x180005de0  lea     r9, [rsp+68h+Ptr]
0x180005de8  mov     r8, r15
0x180005deb  mov     rdx, rdi
0x180005dee  mov     rcx, rbp
0x180005df1  mov     rax, [rdi]
0x180005df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df9  test    eax, eax
0x180005dfb  js      loc_180005EAD
0x180005e01  test    byte ptr [rbp+0], 4
0x180005e05  jnz     loc_180005EA0
0x180005e0b  mov     rax, [rsi]
0x180005e0e  mov     rcx, rsi
0x180005e11  mov     rax, [rax+38h]
0x180005e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1a  mov     rsi, rax
0x180005e1d  mov     rcx, rax; SRWLock
0x180005e20  call    cs:__imp_AcquireSRWLockExclusive
0x180005e26  mov     rcx, [rdi+18h]
0x180005e2a  mov     rcx, [rcx]; Ptr
0x180005e2d  test    rcx, rcx
0x180005e30  jnz     short loc_180005E4B
0x180005e32  xor     ebx, ebx
0x180005e34  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180005e3c  call    cs:__imp_EncodePointer
0x180005e42  mov     rcx, [rdi+18h]
0x180005e46  mov     [rcx], rax
0x180005e49  jmp     short loc_180005E63
0x180005e4b  call    cs:__imp_DecodePointer
0x180005e51  mov     rbx, rax
0x180005e54  mov     rcx, [rax]
0x180005e57  mov     rax, [rcx+8]
0x180005e5b  mov     rcx, rbx
0x180005e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e63  test    rsi, rsi
0x180005e66  jz      short loc_180005E71
0x180005e68  mov     rcx, rsi; SRWLock
0x180005e6b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e71  test    rbx, rbx
0x180005e74  jz      short loc_180005EA0
0x180005e76  mov     rcx, [rsp+68h+Ptr]
0x180005e7e  mov     rax, [rcx]
0x180005e81  mov     rax, [rax+10h]
0x180005e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8a  mov     rcx, [rsp+68h+Ptr]
0x180005e92  mov     rax, [rcx]
0x180005e95  mov     rax, [rax+10h]
0x180005e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e9e  jmp     short loc_180005EA8
0x180005ea0  mov     rbx, [rsp+68h+Ptr]
0x180005ea8  mov     [r14], rbx
0x180005eab  xor     eax, eax
0x180005ead  add     rsp, 38h
0x180005eb1  pop     r15
0x180005eb3  pop     r14
0x180005eb5  pop     rdi
0x180005eb6  pop     rsi
0x180005eb7  pop     rbp
0x180005eb8  pop     rbx
0x180005eb9  retn
```
