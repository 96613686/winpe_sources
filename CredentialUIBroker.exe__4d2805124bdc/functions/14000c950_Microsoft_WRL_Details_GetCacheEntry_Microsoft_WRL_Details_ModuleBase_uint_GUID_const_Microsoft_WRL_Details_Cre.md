# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x14000c950`
- end: `0x14000cad7`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400053dc`

## callees

- `0x14000c950`
- `0x14000ed88`
- `0x14001f010`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x14000ca5a`
- `KERNEL32!EncodePointer` at `0x14000ca5a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ca8b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ca8b`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000c9e4`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000c9f9`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000c9e4`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000c9f9`
- `KERNEL32!DecodePointer` at `0x14000c9b4`
- `KERNEL32!DecodePointer` at `0x14000ca69`
- `KERNEL32!DecodePointer` at `0x14000c9b4`
- `KERNEL32!DecodePointer` at `0x14000ca69`
- `KERNEL32!AcquireSRWLockShared` at `0x14000c9a2`
- `KERNEL32!AcquireSRWLockShared` at `0x14000c9a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        PSRWLOCK SRWLock)
{
  PSRWLOCK v5; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  __int64 v13; // rax
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v5 = SRWLock;
  Ptr = 0;
  SRWLock->Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, PSRWLOCK))Ptr)(
              Ptr,
              &GUID_00000035_0000_0000_c000_000000000046,
              v5);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return v11;
    }
    if ( v9 )
      ReleaseSRWLockShared(v9);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, GUID *, PVOID *))&a4->Data1)(
             a2,
             a4,
             &GUID_00000035_0000_0000_c000_000000000046,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v13 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v13);
    v14 = **(void ***)a4[1].Data4;
    if ( v14 )
    {
      v15 = DecodePointer(v14);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v15 + 8LL))(v15);
    }
    else
    {
      v15 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( !v15 )
    {
LABEL_17:
      v15 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    v5->Ptr = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000c950  mov     rax, rsp
0x14000c953  mov     [rax+8], rbx
0x14000c957  mov     [rax+10h], rbp
0x14000c95b  mov     [rax+18h], r8
0x14000c95f  push    rsi
0x14000c960  push    rdi
0x14000c961  push    r14
0x14000c963  sub     rsp, 30h
0x14000c967  mov     r14, [rsp+48h+SRWLock]
0x14000c96c  mov     rdi, r9
0x14000c96f  mov     qword ptr [rax+18h], 0
0x14000c977  mov     rbp, rdx
0x14000c97a  mov     rsi, rcx
0x14000c97d  mov     qword ptr [r14], 0
0x14000c984  mov     rax, [r9+18h]
0x14000c988  mov     r8, [rax]
0x14000c98b  test    r8, r8
0x14000c98e  jz      short loc_14000C9FF
0x14000c990  mov     rax, [rcx]
0x14000c993  mov     rax, [rax+38h]
0x14000c997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c99c  mov     rcx, rax; SRWLock
0x14000c99f  mov     rbx, rax
0x14000c9a2  call    cs:__imp_AcquireSRWLockShared
0x14000c9a8  mov     rcx, [rdi+18h]
0x14000c9ac  mov     rcx, [rcx]; Ptr
0x14000c9af  test    rcx, rcx
0x14000c9b2  jz      short loc_14000C9F1
0x14000c9b4  call    cs:__imp_DecodePointer
0x14000c9ba  mov     [rsp+48h+Ptr], rax
0x14000c9bf  mov     r8, r14
0x14000c9c2  mov     r9, rax
0x14000c9c5  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x14000c9cc  mov     rcx, [rax]
0x14000c9cf  mov     rax, [rcx]
0x14000c9d2  mov     rcx, r9
0x14000c9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9da  mov     edi, eax
0x14000c9dc  test    rbx, rbx
0x14000c9df  jz      short loc_14000C9EA
0x14000c9e1  mov     rcx, rbx; SRWLock
0x14000c9e4  call    cs:__imp_ReleaseSRWLockShared
0x14000c9ea  mov     eax, edi
0x14000c9ec  jmp     loc_14000CAC4
0x14000c9f1  test    rbx, rbx
0x14000c9f4  jz      short loc_14000C9FF
0x14000c9f6  mov     rcx, rbx; SRWLock
0x14000c9f9  call    cs:__imp_ReleaseSRWLockShared
0x14000c9ff  mov     rax, [rdi]
0x14000ca02  lea     r9, [rsp+48h+Ptr]
0x14000ca07  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x14000ca0e  mov     rdx, rdi
0x14000ca11  mov     rcx, rbp
0x14000ca14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca19  test    eax, eax
0x14000ca1b  js      loc_14000CAC4
0x14000ca21  test    byte ptr [rbp+0], 4
0x14000ca25  jnz     loc_14000CABA
0x14000ca2b  mov     rax, [rsi]
0x14000ca2e  mov     rcx, rsi
0x14000ca31  mov     rax, [rax+38h]
0x14000ca35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca3a  mov     rdx, rax
0x14000ca3d  lea     rcx, [rsp+48h+SRWLock]
0x14000ca42  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x14000ca47  mov     rax, [rdi+18h]
0x14000ca4b  mov     rcx, [rax]; Ptr
0x14000ca4e  test    rcx, rcx
0x14000ca51  jnz     short loc_14000CA69
0x14000ca53  mov     rcx, [rsp+48h+Ptr]; Ptr
0x14000ca58  xor     ebx, ebx
0x14000ca5a  call    cs:__imp_EncodePointer
0x14000ca60  mov     rcx, [rdi+18h]
0x14000ca64  mov     [rcx], rax
0x14000ca67  jmp     short loc_14000CA81
0x14000ca69  call    cs:__imp_DecodePointer
0x14000ca6f  mov     rbx, rax
0x14000ca72  mov     rcx, [rax]
0x14000ca75  mov     rax, [rcx+8]
0x14000ca79  mov     rcx, rbx
0x14000ca7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca81  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x14000ca86  test    rcx, rcx
0x14000ca89  jz      short loc_14000CA91
0x14000ca8b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ca91  test    rbx, rbx
0x14000ca94  jz      short loc_14000CABA
0x14000ca96  mov     rcx, [rsp+48h+Ptr]
0x14000ca9b  mov     rax, [rcx]
0x14000ca9e  mov     rax, [rax+10h]
0x14000caa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000caa7  mov     rcx, [rsp+48h+Ptr]
0x14000caac  mov     rax, [rcx]
0x14000caaf  mov     rax, [rax+10h]
0x14000cab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cab8  jmp     short loc_14000CABF
0x14000caba  mov     rbx, [rsp+48h+Ptr]
0x14000cabf  mov     [r14], rbx
0x14000cac2  xor     eax, eax
0x14000cac4  mov     rbx, [rsp+48h+arg_0]
0x14000cac9  mov     rbp, [rsp+48h+arg_8]
0x14000cace  add     rsp, 30h
0x14000cad2  pop     r14
0x14000cad4  pop     rdi
0x14000cad5  pop     rsi
0x14000cad6  retn
```
