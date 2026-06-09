# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180005ed8`
- end: `0x180006067`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000367c`
- `0x1800037f4`

## callees

- `0x180005ed8`
- `0x180007334`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005f28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005f28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006018`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006018`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005f69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005f7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005f69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005f7e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005fe4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180005fe4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005f3a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005ff3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005f3a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005ff3`

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
  __int64 v14; // rax
  void *v15; // rcx
  PVOID v16; // rbx
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

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
    v14 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v14);
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
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
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
0x180005ed8  mov     rax, rsp
0x180005edb  push    rbx
0x180005edc  push    rbp
0x180005edd  push    rsi
0x180005ede  push    rdi
0x180005edf  push    r14
0x180005ee1  push    r15
0x180005ee3  sub     rsp, 38h
0x180005ee7  mov     rdi, r9
0x180005eea  mov     r15, r8
0x180005eed  mov     rbp, rdx
0x180005ef0  mov     rsi, rcx
0x180005ef3  mov     r14, [rsp+68h+Ptr]
0x180005efb  mov     qword ptr [r14], 0
0x180005f02  mov     qword ptr [rax+28h], 0
0x180005f0a  mov     rax, [r9+18h]
0x180005f0e  mov     r10, [rax]
0x180005f11  test    r10, r10
0x180005f14  jz      short loc_180005F84
0x180005f16  mov     rax, [rcx]
0x180005f19  mov     rax, [rax+38h]
0x180005f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f22  mov     rbx, rax
0x180005f25  mov     rcx, rax; SRWLock
0x180005f28  call    cs:__imp_AcquireSRWLockShared
0x180005f2e  mov     rcx, [rdi+18h]
0x180005f32  mov     rcx, [rcx]; Ptr
0x180005f35  test    rcx, rcx
0x180005f38  jz      short loc_180005F76
0x180005f3a  call    cs:__imp_DecodePointer
0x180005f40  mov     r9, rax
0x180005f43  mov     [rsp+68h+Ptr], rax
0x180005f4b  mov     rcx, [rax]
0x180005f4e  mov     rax, [rcx]
0x180005f51  mov     r8, r14
0x180005f54  mov     rdx, r15
0x180005f57  mov     rcx, r9
0x180005f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5f  mov     edi, eax
0x180005f61  test    rbx, rbx
0x180005f64  jz      short loc_180005F6F
0x180005f66  mov     rcx, rbx; SRWLock
0x180005f69  call    cs:__imp_ReleaseSRWLockShared
0x180005f6f  mov     eax, edi
0x180005f71  jmp     loc_18000605A
0x180005f76  test    rbx, rbx
0x180005f79  jz      short loc_180005F84
0x180005f7b  mov     rcx, rbx; SRWLock
0x180005f7e  call    cs:__imp_ReleaseSRWLockShared
0x180005f84  lea     r9, [rsp+68h+Ptr]
0x180005f8c  mov     r8, r15
0x180005f8f  mov     rdx, rdi
0x180005f92  mov     rcx, rbp
0x180005f95  mov     rax, [rdi]
0x180005f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9d  test    eax, eax
0x180005f9f  js      loc_18000605A
0x180005fa5  test    byte ptr [rbp+0], 4
0x180005fa9  jnz     loc_18000604D
0x180005faf  mov     rax, [rsi]
0x180005fb2  mov     rcx, rsi
0x180005fb5  mov     rax, [rax+38h]
0x180005fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fbe  mov     rdx, rax
0x180005fc1  lea     rcx, [rsp+68h+SRWLock]
0x180005fc9  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180005fce  mov     rax, [rdi+18h]
0x180005fd2  mov     rcx, [rax]; Ptr
0x180005fd5  test    rcx, rcx
0x180005fd8  jnz     short loc_180005FF3
0x180005fda  xor     ebx, ebx
0x180005fdc  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180005fe4  call    cs:__imp_EncodePointer
0x180005fea  mov     rcx, [rdi+18h]
0x180005fee  mov     [rcx], rax
0x180005ff1  jmp     short loc_18000600B
0x180005ff3  call    cs:__imp_DecodePointer
0x180005ff9  mov     rbx, rax
0x180005ffc  mov     rcx, [rax]
0x180005fff  mov     rax, [rcx+8]
0x180006003  mov     rcx, rbx
0x180006006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600b  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180006013  test    rcx, rcx
0x180006016  jz      short loc_18000601E
0x180006018  call    cs:__imp_ReleaseSRWLockExclusive
0x18000601e  test    rbx, rbx
0x180006021  jz      short loc_18000604D
0x180006023  mov     rcx, [rsp+68h+Ptr]
0x18000602b  mov     rax, [rcx]
0x18000602e  mov     rax, [rax+10h]
0x180006032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006037  mov     rcx, [rsp+68h+Ptr]
0x18000603f  mov     rax, [rcx]
0x180006042  mov     rax, [rax+10h]
0x180006046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000604b  jmp     short loc_180006055
0x18000604d  mov     rbx, [rsp+68h+Ptr]
0x180006055  mov     [r14], rbx
0x180006058  xor     eax, eax
0x18000605a  add     rsp, 38h
0x18000605e  pop     r15
0x180006060  pop     r14
0x180006062  pop     rdi
0x180006063  pop     rsi
0x180006064  pop     rbp
0x180006065  pop     rbx
0x180006066  retn
```
