# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180004674`
- end: `0x1800047fa`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800078e0`

## callees

- `0x180004674`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800046c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800046c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004705`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000471a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004705`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000471a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004760`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004760`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000477c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000477c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800046d6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000478b`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800046d6`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000478b`

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
0x180004674  mov     rax, rsp
0x180004677  push    rbx
0x180004678  push    rbp
0x180004679  push    rsi
0x18000467a  push    rdi
0x18000467b  push    r14
0x18000467d  push    r15
0x18000467f  sub     rsp, 38h
0x180004683  mov     rdi, r9
0x180004686  mov     r15, r8
0x180004689  mov     rbp, rdx
0x18000468c  mov     rsi, rcx
0x18000468f  mov     r14, [rsp+68h+Ptr]
0x180004697  mov     qword ptr [r14], 0
0x18000469e  mov     qword ptr [rax+28h], 0
0x1800046a6  mov     rax, [r9+18h]
0x1800046aa  mov     r10, [rax]
0x1800046ad  test    r10, r10
0x1800046b0  jz      short loc_180004720
0x1800046b2  mov     rax, [rcx]
0x1800046b5  mov     rax, [rax+38h]
0x1800046b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046be  mov     rbx, rax
0x1800046c1  mov     rcx, rax; SRWLock
0x1800046c4  call    cs:__imp_AcquireSRWLockShared
0x1800046ca  mov     rcx, [rdi+18h]
0x1800046ce  mov     rcx, [rcx]; Ptr
0x1800046d1  test    rcx, rcx
0x1800046d4  jz      short loc_180004712
0x1800046d6  call    cs:__imp_DecodePointer
0x1800046dc  mov     r9, rax
0x1800046df  mov     [rsp+68h+Ptr], rax
0x1800046e7  mov     rcx, [rax]
0x1800046ea  mov     rax, [rcx]
0x1800046ed  mov     r8, r14
0x1800046f0  mov     rdx, r15
0x1800046f3  mov     rcx, r9
0x1800046f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fb  mov     edi, eax
0x1800046fd  test    rbx, rbx
0x180004700  jz      short loc_18000470B
0x180004702  mov     rcx, rbx; SRWLock
0x180004705  call    cs:__imp_ReleaseSRWLockShared
0x18000470b  mov     eax, edi
0x18000470d  jmp     loc_1800047ED
0x180004712  test    rbx, rbx
0x180004715  jz      short loc_180004720
0x180004717  mov     rcx, rbx; SRWLock
0x18000471a  call    cs:__imp_ReleaseSRWLockShared
0x180004720  lea     r9, [rsp+68h+Ptr]
0x180004728  mov     r8, r15
0x18000472b  mov     rdx, rdi
0x18000472e  mov     rcx, rbp
0x180004731  mov     rax, [rdi]
0x180004734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004739  test    eax, eax
0x18000473b  js      loc_1800047ED
0x180004741  test    byte ptr [rbp+0], 4
0x180004745  jnz     loc_1800047E0
0x18000474b  mov     rax, [rsi]
0x18000474e  mov     rcx, rsi
0x180004751  mov     rax, [rax+38h]
0x180004755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000475a  mov     rsi, rax
0x18000475d  mov     rcx, rax; SRWLock
0x180004760  call    cs:__imp_AcquireSRWLockExclusive
0x180004766  mov     rcx, [rdi+18h]
0x18000476a  mov     rcx, [rcx]; Ptr
0x18000476d  test    rcx, rcx
0x180004770  jnz     short loc_18000478B
0x180004772  xor     ebx, ebx
0x180004774  mov     rcx, [rsp+68h+Ptr]; Ptr
0x18000477c  call    cs:__imp_EncodePointer
0x180004782  mov     rcx, [rdi+18h]
0x180004786  mov     [rcx], rax
0x180004789  jmp     short loc_1800047A3
0x18000478b  call    cs:__imp_DecodePointer
0x180004791  mov     rbx, rax
0x180004794  mov     rcx, [rax]
0x180004797  mov     rax, [rcx+8]
0x18000479b  mov     rcx, rbx
0x18000479e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a3  test    rsi, rsi
0x1800047a6  jz      short loc_1800047B1
0x1800047a8  mov     rcx, rsi; SRWLock
0x1800047ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800047b1  test    rbx, rbx
0x1800047b4  jz      short loc_1800047E0
0x1800047b6  mov     rcx, [rsp+68h+Ptr]
0x1800047be  mov     rax, [rcx]
0x1800047c1  mov     rax, [rax+10h]
0x1800047c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ca  mov     rcx, [rsp+68h+Ptr]
0x1800047d2  mov     rax, [rcx]
0x1800047d5  mov     rax, [rax+10h]
0x1800047d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047de  jmp     short loc_1800047E8
0x1800047e0  mov     rbx, [rsp+68h+Ptr]
0x1800047e8  mov     [r14], rbx
0x1800047eb  xor     eax, eax
0x1800047ed  add     rsp, 38h
0x1800047f1  pop     r15
0x1800047f3  pop     r14
0x1800047f5  pop     rdi
0x1800047f6  pop     rsi
0x1800047f7  pop     rbp
0x1800047f8  pop     rbx
0x1800047f9  retn
```
