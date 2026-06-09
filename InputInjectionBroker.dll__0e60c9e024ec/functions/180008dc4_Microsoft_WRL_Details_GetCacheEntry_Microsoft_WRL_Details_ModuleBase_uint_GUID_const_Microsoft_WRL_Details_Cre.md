# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180008dc4`
- end: `0x180008f4a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008c10`
- `0x180009130`

## callees

- `0x180008dc4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008e14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008e14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008efb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008efb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008eb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008eb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e6a`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008ecc`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180008ecc`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008e26`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008edb`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008e26`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180008edb`

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
0x180008dc4  mov     rax, rsp
0x180008dc7  push    rbx
0x180008dc8  push    rbp
0x180008dc9  push    rsi
0x180008dca  push    rdi
0x180008dcb  push    r14
0x180008dcd  push    r15
0x180008dcf  sub     rsp, 38h
0x180008dd3  mov     rdi, r9
0x180008dd6  mov     r15, r8
0x180008dd9  mov     rbp, rdx
0x180008ddc  mov     rsi, rcx
0x180008ddf  mov     r14, [rsp+68h+Ptr]
0x180008de7  mov     qword ptr [r14], 0
0x180008dee  mov     qword ptr [rax+28h], 0
0x180008df6  mov     rax, [r9+18h]
0x180008dfa  mov     r10, [rax]
0x180008dfd  test    r10, r10
0x180008e00  jz      short loc_180008E70
0x180008e02  mov     rax, [rcx]
0x180008e05  mov     rax, [rax+38h]
0x180008e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0e  mov     rbx, rax
0x180008e11  mov     rcx, rax; SRWLock
0x180008e14  call    cs:__imp_AcquireSRWLockShared
0x180008e1a  mov     rcx, [rdi+18h]
0x180008e1e  mov     rcx, [rcx]; Ptr
0x180008e21  test    rcx, rcx
0x180008e24  jz      short loc_180008E62
0x180008e26  call    cs:__imp_DecodePointer
0x180008e2c  mov     r9, rax
0x180008e2f  mov     [rsp+68h+Ptr], rax
0x180008e37  mov     rcx, [rax]
0x180008e3a  mov     rax, [rcx]
0x180008e3d  mov     r8, r14
0x180008e40  mov     rdx, r15
0x180008e43  mov     rcx, r9
0x180008e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e4b  mov     edi, eax
0x180008e4d  test    rbx, rbx
0x180008e50  jz      short loc_180008E5B
0x180008e52  mov     rcx, rbx; SRWLock
0x180008e55  call    cs:__imp_ReleaseSRWLockShared
0x180008e5b  mov     eax, edi
0x180008e5d  jmp     loc_180008F3D
0x180008e62  test    rbx, rbx
0x180008e65  jz      short loc_180008E70
0x180008e67  mov     rcx, rbx; SRWLock
0x180008e6a  call    cs:__imp_ReleaseSRWLockShared
0x180008e70  lea     r9, [rsp+68h+Ptr]
0x180008e78  mov     r8, r15
0x180008e7b  mov     rdx, rdi
0x180008e7e  mov     rcx, rbp
0x180008e81  mov     rax, [rdi]
0x180008e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e89  test    eax, eax
0x180008e8b  js      loc_180008F3D
0x180008e91  test    byte ptr [rbp+0], 4
0x180008e95  jnz     loc_180008F30
0x180008e9b  mov     rax, [rsi]
0x180008e9e  mov     rcx, rsi
0x180008ea1  mov     rax, [rax+38h]
0x180008ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eaa  mov     rsi, rax
0x180008ead  mov     rcx, rax; SRWLock
0x180008eb0  call    cs:__imp_AcquireSRWLockExclusive
0x180008eb6  mov     rcx, [rdi+18h]
0x180008eba  mov     rcx, [rcx]; Ptr
0x180008ebd  test    rcx, rcx
0x180008ec0  jnz     short loc_180008EDB
0x180008ec2  xor     ebx, ebx
0x180008ec4  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180008ecc  call    cs:__imp_EncodePointer
0x180008ed2  mov     rcx, [rdi+18h]
0x180008ed6  mov     [rcx], rax
0x180008ed9  jmp     short loc_180008EF3
0x180008edb  call    cs:__imp_DecodePointer
0x180008ee1  mov     rbx, rax
0x180008ee4  mov     rcx, [rax]
0x180008ee7  mov     rax, [rcx+8]
0x180008eeb  mov     rcx, rbx
0x180008eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef3  test    rsi, rsi
0x180008ef6  jz      short loc_180008F01
0x180008ef8  mov     rcx, rsi; SRWLock
0x180008efb  call    cs:__imp_ReleaseSRWLockExclusive
0x180008f01  test    rbx, rbx
0x180008f04  jz      short loc_180008F30
0x180008f06  mov     rcx, [rsp+68h+Ptr]
0x180008f0e  mov     rax, [rcx]
0x180008f11  mov     rax, [rax+10h]
0x180008f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f1a  mov     rcx, [rsp+68h+Ptr]
0x180008f22  mov     rax, [rcx]
0x180008f25  mov     rax, [rax+10h]
0x180008f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f2e  jmp     short loc_180008F38
0x180008f30  mov     rbx, [rsp+68h+Ptr]
0x180008f38  mov     [r14], rbx
0x180008f3b  xor     eax, eax
0x180008f3d  add     rsp, 38h
0x180008f41  pop     r15
0x180008f43  pop     r14
0x180008f45  pop     rdi
0x180008f46  pop     rsi
0x180008f47  pop     rbp
0x180008f48  pop     rbx
0x180008f49  retn
```
