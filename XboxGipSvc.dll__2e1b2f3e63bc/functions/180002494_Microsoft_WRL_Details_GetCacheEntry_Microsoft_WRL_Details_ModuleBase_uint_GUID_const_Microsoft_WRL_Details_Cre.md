# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180002494`
- end: `0x18000261a`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002870`
- `0x180002d20`

## callees

- `0x180002494`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800024f6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800025ab`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800024f6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800025ab`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000259c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000259c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800024e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800024e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002525`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000253a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002525`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000253a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002580`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002580`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800025cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800025cb`

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
0x180002494  mov     rax, rsp
0x180002497  push    rbx
0x180002498  push    rbp
0x180002499  push    rsi
0x18000249a  push    rdi
0x18000249b  push    r14
0x18000249d  push    r15
0x18000249f  sub     rsp, 38h
0x1800024a3  mov     rdi, r9
0x1800024a6  mov     r15, r8
0x1800024a9  mov     rbp, rdx
0x1800024ac  mov     rsi, rcx
0x1800024af  mov     r14, [rsp+68h+Ptr]
0x1800024b7  mov     qword ptr [r14], 0
0x1800024be  mov     qword ptr [rax+28h], 0
0x1800024c6  mov     rax, [r9+18h]
0x1800024ca  mov     r10, [rax]
0x1800024cd  test    r10, r10
0x1800024d0  jz      short loc_180002540
0x1800024d2  mov     rax, [rcx]
0x1800024d5  mov     rax, [rax+38h]
0x1800024d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024de  mov     rbx, rax
0x1800024e1  mov     rcx, rax; SRWLock
0x1800024e4  call    cs:__imp_AcquireSRWLockShared
0x1800024ea  mov     rcx, [rdi+18h]
0x1800024ee  mov     rcx, [rcx]; Ptr
0x1800024f1  test    rcx, rcx
0x1800024f4  jz      short loc_180002532
0x1800024f6  call    cs:__imp_DecodePointer
0x1800024fc  mov     r9, rax
0x1800024ff  mov     [rsp+68h+Ptr], rax
0x180002507  mov     rcx, [rax]
0x18000250a  mov     rax, [rcx]
0x18000250d  mov     r8, r14
0x180002510  mov     rdx, r15
0x180002513  mov     rcx, r9
0x180002516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000251b  mov     edi, eax
0x18000251d  test    rbx, rbx
0x180002520  jz      short loc_18000252B
0x180002522  mov     rcx, rbx; SRWLock
0x180002525  call    cs:__imp_ReleaseSRWLockShared
0x18000252b  mov     eax, edi
0x18000252d  jmp     loc_18000260D
0x180002532  test    rbx, rbx
0x180002535  jz      short loc_180002540
0x180002537  mov     rcx, rbx; SRWLock
0x18000253a  call    cs:__imp_ReleaseSRWLockShared
0x180002540  lea     r9, [rsp+68h+Ptr]
0x180002548  mov     r8, r15
0x18000254b  mov     rdx, rdi
0x18000254e  mov     rcx, rbp
0x180002551  mov     rax, [rdi]
0x180002554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002559  test    eax, eax
0x18000255b  js      loc_18000260D
0x180002561  test    byte ptr [rbp+0], 4
0x180002565  jnz     loc_180002600
0x18000256b  mov     rax, [rsi]
0x18000256e  mov     rcx, rsi
0x180002571  mov     rax, [rax+38h]
0x180002575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257a  mov     rsi, rax
0x18000257d  mov     rcx, rax; SRWLock
0x180002580  call    cs:__imp_AcquireSRWLockExclusive
0x180002586  mov     rcx, [rdi+18h]
0x18000258a  mov     rcx, [rcx]; Ptr
0x18000258d  test    rcx, rcx
0x180002590  jnz     short loc_1800025AB
0x180002592  xor     ebx, ebx
0x180002594  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000259c  call    cs:__imp_EncodePointer
0x1800025a2  mov     rcx, [rdi+18h]
0x1800025a6  mov     [rcx], rax
0x1800025a9  jmp     short loc_1800025C3
0x1800025ab  call    cs:__imp_DecodePointer
0x1800025b1  mov     rbx, rax
0x1800025b4  mov     rcx, [rax]
0x1800025b7  mov     rax, [rcx+8]
0x1800025bb  mov     rcx, rbx
0x1800025be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c3  test    rsi, rsi
0x1800025c6  jz      short loc_1800025D1
0x1800025c8  mov     rcx, rsi; SRWLock
0x1800025cb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800025d1  test    rbx, rbx
0x1800025d4  jz      short loc_180002600
0x1800025d6  mov     rcx, [rsp+68h+Ptr]
0x1800025de  mov     rax, [rcx]
0x1800025e1  mov     rax, [rax+10h]
0x1800025e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ea  mov     rcx, [rsp+68h+Ptr]
0x1800025f2  mov     rax, [rcx]
0x1800025f5  mov     rax, [rax+10h]
0x1800025f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025fe  jmp     short loc_180002608
0x180002600  mov     rbx, [rsp+68h+Ptr]
0x180002608  mov     [r14], rbx
0x18000260b  xor     eax, eax
0x18000260d  add     rsp, 38h
0x180002611  pop     r15
0x180002613  pop     r14
0x180002615  pop     rdi
0x180002616  pop     rsi
0x180002617  pop     rbp
0x180002618  pop     rbx
0x180002619  retn
```
