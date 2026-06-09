# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180011844`
- end: `0x1800119d7`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, _QWORD *Ptr)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000dc38`

## callees

- `0x180011844`
- `0x180013bb4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011894`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011894`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180011953`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180011953`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800118a7`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180011962`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800118a7`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180011962`

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
0x180011844  mov     rax, rsp
0x180011847  push    rbx
0x180011848  push    rbp
0x180011849  push    rsi
0x18001184a  push    rdi
0x18001184b  push    r14
0x18001184d  push    r15
0x18001184f  sub     rsp, 38h
0x180011853  mov     rdi, r9
0x180011856  mov     r15, r8
0x180011859  mov     rbp, rdx
0x18001185c  mov     rsi, rcx
0x18001185f  mov     r14, [rsp+68h+Ptr]
0x180011867  mov     qword ptr [r14], 0
0x18001186e  mov     qword ptr [rax+28h], 0
0x180011876  mov     rax, [r9+18h]
0x18001187a  mov     r10, [rax]
0x18001187d  test    r10, r10
0x180011880  jz      short loc_1800118F3
0x180011882  mov     rax, [rcx]
0x180011885  mov     rax, [rax+38h]
0x180011889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001188e  mov     rbx, rax
0x180011891  mov     rcx, rax; SRWLock
0x180011894  call    cs:__imp_AcquireSRWLockShared
0x18001189a  nop
0x18001189b  mov     rcx, [rdi+18h]
0x18001189f  mov     rcx, [rcx]; Ptr
0x1800118a2  test    rcx, rcx
0x1800118a5  jz      short loc_1800118E4
0x1800118a7  call    cs:__imp_DecodePointer
0x1800118ad  mov     r9, rax
0x1800118b0  mov     [rsp+68h+Ptr], rax
0x1800118b8  mov     rcx, [rax]
0x1800118bb  mov     rax, [rcx]
0x1800118be  mov     r8, r14
0x1800118c1  mov     rdx, r15
0x1800118c4  mov     rcx, r9
0x1800118c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118cc  mov     edi, eax
0x1800118ce  test    rbx, rbx
0x1800118d1  jz      short loc_1800118DD
0x1800118d3  mov     rcx, rbx; SRWLock
0x1800118d6  call    cs:__imp_ReleaseSRWLockShared
0x1800118dc  nop
0x1800118dd  mov     eax, edi
0x1800118df  jmp     loc_1800119CA
0x1800118e4  test    rbx, rbx
0x1800118e7  jz      short loc_1800118F3
0x1800118e9  mov     rcx, rbx; SRWLock
0x1800118ec  call    cs:__imp_ReleaseSRWLockShared
0x1800118f2  nop
0x1800118f3  lea     r9, [rsp+68h+Ptr]
0x1800118fb  mov     r8, r15
0x1800118fe  mov     rdx, rdi
0x180011901  mov     rcx, rbp
0x180011904  mov     rax, [rdi]
0x180011907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001190c  test    eax, eax
0x18001190e  js      loc_1800119CA
0x180011914  test    byte ptr [rbp+0], 4
0x180011918  jnz     loc_1800119BD
0x18001191e  mov     rax, [rsi]
0x180011921  mov     rcx, rsi
0x180011924  mov     rax, [rax+38h]
0x180011928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001192d  mov     rdx, rax
0x180011930  lea     rcx, [rsp+68h+SRWLock]
0x180011938  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001193d  mov     rax, [rdi+18h]
0x180011941  mov     rcx, [rax]; Ptr
0x180011944  test    rcx, rcx
0x180011947  jnz     short loc_180011962
0x180011949  xor     ebx, ebx
0x18001194b  mov     rcx, [rsp+68h+Ptr]; Ptr
0x180011953  call    cs:__imp_EncodePointer
0x180011959  mov     rcx, [rdi+18h]
0x18001195d  mov     [rcx], rax
0x180011960  jmp     short loc_18001197A
0x180011962  call    cs:__imp_DecodePointer
0x180011968  mov     rbx, rax
0x18001196b  mov     rcx, [rax]
0x18001196e  mov     rax, [rcx+8]
0x180011972  mov     rcx, rbx
0x180011975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001197a  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180011982  test    rcx, rcx
0x180011985  jz      short loc_18001198E
0x180011987  call    cs:__imp_ReleaseSRWLockExclusive
0x18001198d  nop
0x18001198e  test    rbx, rbx
0x180011991  jz      short loc_1800119BD
0x180011993  mov     rcx, [rsp+68h+Ptr]
0x18001199b  mov     rax, [rcx]
0x18001199e  mov     rax, [rax+10h]
0x1800119a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119a7  mov     rcx, [rsp+68h+Ptr]
0x1800119af  mov     rax, [rcx]
0x1800119b2  mov     rax, [rax+10h]
0x1800119b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119bb  jmp     short loc_1800119C5
0x1800119bd  mov     rbx, [rsp+68h+Ptr]
0x1800119c5  mov     [r14], rbx
0x1800119c8  xor     eax, eax
0x1800119ca  add     rsp, 38h
0x1800119ce  pop     r15
0x1800119d0  pop     r14
0x1800119d2  pop     rdi
0x1800119d3  pop     rsi
0x1800119d4  pop     rbp
0x1800119d5  pop     rbx
0x1800119d6  retn
```
