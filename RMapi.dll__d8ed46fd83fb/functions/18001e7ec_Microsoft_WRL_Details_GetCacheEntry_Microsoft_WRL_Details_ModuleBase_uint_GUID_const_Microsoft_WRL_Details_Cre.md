# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18001e7ec`
- end: `0x18001e98b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019888`

## callees

- `0x18000d2a0`
- `0x18001e7ec`
- `0x18001f2d0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e848`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e848`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e93a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e93a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e88a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e89f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e88a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e89f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e85a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e918`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e85a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e918`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001e909`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001e909`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  RTL_SRWLOCK *v8; // rbx
  void *v9; // rcx
  unsigned int v10; // edi
  __int64 result; // rax
  __int64 v12; // rax
  void *v13; // rcx
  PVOID v14; // rbx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-48h] BYREF
  PVOID Ptr; // [rsp+38h] [rbp-40h] BYREF

  *(_QWORD *)a5 = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v8 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *))(*(_QWORD *)this + 56LL))(
                          this,
                          a2,
                          a3);
    AcquireSRWLockShared(v8);
    v9 = **(void ***)a4[1].Data4;
    if ( v9 )
    {
      Ptr = DecodePointer(v9);
      v10 = (**(__int64 (__fastcall ***)(PVOID, GUID *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              &GUID_00000035_0000_0000_c000_000000000046,
              a5);
      if ( v8 )
        ReleaseSRWLockShared(v8);
      return v10;
    }
    if ( v8 )
      ReleaseSRWLockShared(v8);
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
    SRWLock = 0;
    v12 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v12);
    v13 = **(void ***)a4[1].Data4;
    if ( v13 )
    {
      v14 = DecodePointer(v13);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)v14 + 8LL))(v14);
    }
    else
    {
      v14 = 0;
      **(_QWORD **)a4[1].Data4 = EncodePointer(Ptr);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( !v14 )
    {
LABEL_17:
      v14 = Ptr;
    }
    else
    {
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
    }
    *(_QWORD *)a5 = v14;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001e7ec  push    rbx
0x18001e7ee  push    rbp
0x18001e7ef  push    rsi
0x18001e7f0  push    rdi
0x18001e7f1  push    r14
0x18001e7f3  sub     rsp, 50h
0x18001e7f7  mov     rax, cs:__security_cookie
0x18001e7fe  xor     rax, rsp
0x18001e801  mov     [rsp+78h+var_38], rax
0x18001e806  mov     rdi, r9
0x18001e809  mov     rbp, rdx
0x18001e80c  mov     rsi, rcx
0x18001e80f  mov     r14, [rsp+78h+arg_20]
0x18001e817  mov     qword ptr [r14], 0
0x18001e81e  mov     [rsp+78h+Ptr], 0
0x18001e827  mov     rax, [r9+18h]
0x18001e82b  mov     rcx, [rax]
0x18001e82e  test    rcx, rcx
0x18001e831  jz      short loc_18001E8A5
0x18001e833  mov     rax, [rsi]
0x18001e836  mov     rcx, rsi
0x18001e839  mov     rax, [rax+38h]
0x18001e83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e842  mov     rbx, rax
0x18001e845  mov     rcx, rax; SRWLock
0x18001e848  call    cs:__imp_AcquireSRWLockShared
0x18001e84e  mov     rcx, [rdi+18h]
0x18001e852  mov     rcx, [rcx]; Ptr
0x18001e855  test    rcx, rcx
0x18001e858  jz      short loc_18001E897
0x18001e85a  call    cs:__imp_DecodePointer
0x18001e860  mov     r9, rax
0x18001e863  mov     [rsp+78h+Ptr], rax
0x18001e868  mov     rcx, [rax]
0x18001e86b  mov     rax, [rcx]
0x18001e86e  mov     r8, r14
0x18001e871  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18001e878  mov     rcx, r9
0x18001e87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e880  mov     edi, eax
0x18001e882  test    rbx, rbx
0x18001e885  jz      short loc_18001E890
0x18001e887  mov     rcx, rbx; SRWLock
0x18001e88a  call    cs:__imp_ReleaseSRWLockShared
0x18001e890  mov     eax, edi
0x18001e892  jmp     loc_18001E973
0x18001e897  test    rbx, rbx
0x18001e89a  jz      short loc_18001E8A5
0x18001e89c  mov     rcx, rbx; SRWLock
0x18001e89f  call    cs:__imp_ReleaseSRWLockShared
0x18001e8a5  lea     r9, [rsp+78h+Ptr]
0x18001e8aa  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x18001e8b1  mov     rdx, rdi
0x18001e8b4  mov     rcx, rbp
0x18001e8b7  mov     rax, [rdi]
0x18001e8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8bf  test    eax, eax
0x18001e8c1  js      loc_18001E973
0x18001e8c7  test    byte ptr [rbp+0], 4
0x18001e8cb  jnz     loc_18001E969
0x18001e8d1  mov     [rsp+78h+SRWLock], 0
0x18001e8da  mov     rax, [rsi]
0x18001e8dd  mov     rcx, rsi
0x18001e8e0  mov     rax, [rax+38h]
0x18001e8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e9  mov     rdx, rax
0x18001e8ec  lea     rcx, [rsp+78h+SRWLock]
0x18001e8f1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001e8f6  mov     rax, [rdi+18h]
0x18001e8fa  mov     rcx, [rax]; Ptr
0x18001e8fd  test    rcx, rcx
0x18001e900  jnz     short loc_18001E918
0x18001e902  xor     ebx, ebx
0x18001e904  mov     rcx, [rsp+78h+Ptr]; Ptr
0x18001e909  call    cs:__imp_EncodePointer
0x18001e90f  mov     rcx, [rdi+18h]
0x18001e913  mov     [rcx], rax
0x18001e916  jmp     short loc_18001E930
0x18001e918  call    cs:__imp_DecodePointer
0x18001e91e  mov     rbx, rax
0x18001e921  mov     rcx, [rax]
0x18001e924  mov     rax, [rcx+8]
0x18001e928  mov     rcx, rbx
0x18001e92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e930  mov     rcx, [rsp+78h+SRWLock]; SRWLock
0x18001e935  test    rcx, rcx
0x18001e938  jz      short loc_18001E940
0x18001e93a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e940  test    rbx, rbx
0x18001e943  jz      short loc_18001E969
0x18001e945  mov     rcx, [rsp+78h+Ptr]
0x18001e94a  mov     rax, [rcx]
0x18001e94d  mov     rax, [rax+10h]
0x18001e951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e956  mov     rcx, [rsp+78h+Ptr]
0x18001e95b  mov     rax, [rcx]
0x18001e95e  mov     rax, [rax+10h]
0x18001e962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e967  jmp     short loc_18001E96E
0x18001e969  mov     rbx, [rsp+78h+Ptr]
0x18001e96e  mov     [r14], rbx
0x18001e971  xor     eax, eax
0x18001e973  mov     rcx, [rsp+78h+var_38]
0x18001e978  xor     rcx, rsp; StackCookie
0x18001e97b  call    __security_check_cookie
0x18001e980  add     rsp, 50h
0x18001e984  pop     r14
0x18001e986  pop     rdi
0x18001e987  pop     rsi
0x18001e988  pop     rbp
0x18001e989  pop     rbx
0x18001e98a  retn
```
