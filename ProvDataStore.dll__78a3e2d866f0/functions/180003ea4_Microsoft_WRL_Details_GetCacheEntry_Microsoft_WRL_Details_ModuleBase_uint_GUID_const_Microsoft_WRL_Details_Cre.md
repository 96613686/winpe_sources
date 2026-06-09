# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180003ea4`
- end: `0x18000402a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800069f0`
- `0x180006bb0`

## callees

- `0x180003ea4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003f4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003f4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003f90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003f90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003fdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003fdb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003ef4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003ef4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003fac`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180003fac`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003f06`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003fbb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003f06`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180003fbb`

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
0x180003ea4  mov     rax, rsp
0x180003ea7  push    rbx
0x180003ea8  push    rbp
0x180003ea9  push    rsi
0x180003eaa  push    rdi
0x180003eab  push    r14
0x180003ead  push    r15
0x180003eaf  sub     rsp, 38h
0x180003eb3  mov     rdi, r9
0x180003eb6  mov     r15, r8
0x180003eb9  mov     rbp, rdx
0x180003ebc  mov     rsi, rcx
0x180003ebf  mov     r14, [rsp+68h+Ptr]
0x180003ec7  mov     qword ptr [r14], 0
0x180003ece  mov     qword ptr [rax+28h], 0
0x180003ed6  mov     rax, [r9+18h]
0x180003eda  mov     r10, [rax]
0x180003edd  test    r10, r10
0x180003ee0  jz      short loc_180003F50
0x180003ee2  mov     rax, [rcx]
0x180003ee5  mov     rax, [rax+38h]
0x180003ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eee  mov     rbx, rax
0x180003ef1  mov     rcx, rax; SRWLock
0x180003ef4  call    cs:__imp_AcquireSRWLockShared
0x180003efa  mov     rcx, [rdi+18h]
0x180003efe  mov     rcx, [rcx]; Ptr
0x180003f01  test    rcx, rcx
0x180003f04  jz      short loc_180003F42
0x180003f06  call    cs:__imp_DecodePointer
0x180003f0c  mov     r9, rax
0x180003f0f  mov     [rsp+68h+Ptr], rax
0x180003f17  mov     rcx, [rax]
0x180003f1a  mov     rax, [rcx]
0x180003f1d  mov     r8, r14
0x180003f20  mov     rdx, r15
0x180003f23  mov     rcx, r9
0x180003f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f2b  mov     edi, eax
0x180003f2d  test    rbx, rbx
0x180003f30  jz      short loc_180003F3B
0x180003f32  mov     rcx, rbx; SRWLock
0x180003f35  call    cs:__imp_ReleaseSRWLockShared
0x180003f3b  mov     eax, edi
0x180003f3d  jmp     loc_18000401D
0x180003f42  test    rbx, rbx
0x180003f45  jz      short loc_180003F50
0x180003f47  mov     rcx, rbx; SRWLock
0x180003f4a  call    cs:__imp_ReleaseSRWLockShared
0x180003f50  lea     r9, [rsp+68h+Ptr]
0x180003f58  mov     r8, r15
0x180003f5b  mov     rdx, rdi
0x180003f5e  mov     rcx, rbp
0x180003f61  mov     rax, [rdi]
0x180003f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f69  test    eax, eax
0x180003f6b  js      loc_18000401D
0x180003f71  test    byte ptr [rbp+0], 4
0x180003f75  jnz     loc_180004010
0x180003f7b  mov     rax, [rsi]
0x180003f7e  mov     rcx, rsi
0x180003f81  mov     rax, [rax+38h]
0x180003f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8a  mov     rsi, rax
0x180003f8d  mov     rcx, rax; SRWLock
0x180003f90  call    cs:__imp_AcquireSRWLockExclusive
0x180003f96  mov     rcx, [rdi+18h]
0x180003f9a  mov     rcx, [rcx]; Ptr
0x180003f9d  test    rcx, rcx
0x180003fa0  jnz     short loc_180003FBB
0x180003fa2  xor     ebx, ebx
0x180003fa4  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180003fac  call    cs:__imp_EncodePointer
0x180003fb2  mov     rcx, [rdi+18h]
0x180003fb6  mov     [rcx], rax
0x180003fb9  jmp     short loc_180003FD3
0x180003fbb  call    cs:__imp_DecodePointer
0x180003fc1  mov     rbx, rax
0x180003fc4  mov     rcx, [rax]
0x180003fc7  mov     rax, [rcx+8]
0x180003fcb  mov     rcx, rbx
0x180003fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd3  test    rsi, rsi
0x180003fd6  jz      short loc_180003FE1
0x180003fd8  mov     rcx, rsi; SRWLock
0x180003fdb  call    cs:__imp_ReleaseSRWLockExclusive
0x180003fe1  test    rbx, rbx
0x180003fe4  jz      short loc_180004010
0x180003fe6  mov     rcx, [rsp+68h+Ptr]
0x180003fee  mov     rax, [rcx]
0x180003ff1  mov     rax, [rax+10h]
0x180003ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ffa  mov     rcx, [rsp+68h+Ptr]
0x180004002  mov     rax, [rcx]
0x180004005  mov     rax, [rax+10h]
0x180004009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000400e  jmp     short loc_180004018
0x180004010  mov     rbx, [rsp+68h+Ptr]
0x180004018  mov     [r14], rbx
0x18000401b  xor     eax, eax
0x18000401d  add     rsp, 38h
0x180004021  pop     r15
0x180004023  pop     r14
0x180004025  pop     rdi
0x180004026  pop     rsi
0x180004027  pop     rbp
0x180004028  pop     rbx
0x180004029  retn
```
