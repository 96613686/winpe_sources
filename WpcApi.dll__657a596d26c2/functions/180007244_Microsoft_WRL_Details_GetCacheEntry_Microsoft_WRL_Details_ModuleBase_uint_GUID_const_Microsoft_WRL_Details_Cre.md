# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180007244`
- end: `0x1800073d2`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aea0`
- `0x18000b030`

## callees

- `0x180007244`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800072a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800072a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800072df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800072f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800072df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800072f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007386`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007386`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000733e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000733e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800072b3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007366`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800072b3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180007366`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180007357`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180007357`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetCacheEntry(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        unsigned int *a3,
        const struct _GUID *a4,
        const struct Microsoft::WRL::Details::CreatorMap *a5)
{
  const struct Microsoft::WRL::Details::CreatorMap *v8; // r14
  RTL_SRWLOCK *v9; // rbx
  void *v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  RTL_SRWLOCK *v13; // rsi
  void *v14; // rcx
  PVOID v15; // rbx
  PVOID Ptr; // [rsp+50h] [rbp+8h] BYREF

  v8 = a5;
  *(_QWORD *)a5 = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(void *))(WpcDesktop::OTS::ManagerDLL::InProcComServerModule + 56LL))(&WpcDesktop::OTS::ManagerDLL::InProcComServerModule);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, unsigned int *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              a3,
              v8);
      if ( v9 )
        ReleaseSRWLockShared(v9);
      return v11;
    }
    if ( v9 )
      ReleaseSRWLockShared(v9);
  }
  result = (*(__int64 (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, const struct _GUID *, unsigned int *, PVOID *))&a4->Data1)(
             a2,
             a4,
             a3,
             &Ptr);
  if ( (int)result >= 0 )
  {
    if ( (*(_BYTE *)a2 & 4) != 0 )
      goto LABEL_17;
    v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(void *))(WpcDesktop::OTS::ManagerDLL::InProcComServerModule + 56LL))(&WpcDesktop::OTS::ManagerDLL::InProcComServerModule);
    AcquireSRWLockExclusive(v13);
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
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
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
    *(_QWORD *)v8 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007244  mov     rax, rsp
0x180007247  mov     [rax+10h], rbx
0x18000724b  mov     [rax+18h], rbp
0x18000724f  mov     [rax+8], rcx
0x180007253  push    rsi
0x180007254  push    rdi
0x180007255  push    r14
0x180007257  sub     rsp, 30h
0x18000725b  mov     rdi, r9
0x18000725e  mov     rbp, r8
0x180007261  mov     rsi, rdx
0x180007264  mov     r14, [rsp+48h+arg_20]
0x180007269  mov     qword ptr [r14], 0
0x180007270  mov     qword ptr [rax+8], 0
0x180007278  mov     rax, [r9+18h]
0x18000727c  mov     rcx, [rax]
0x18000727f  test    rcx, rcx
0x180007282  jz      short loc_1800072FA
0x180007284  mov     rax, cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000728b  lea     rcx, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x180007292  mov     rax, [rax+38h]
0x180007296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000729b  mov     rbx, rax
0x18000729e  mov     rcx, rax; SRWLock
0x1800072a1  call    cs:__imp_AcquireSRWLockShared
0x1800072a7  mov     rcx, [rdi+18h]
0x1800072ab  mov     rcx, [rcx]; Ptr
0x1800072ae  test    rcx, rcx
0x1800072b1  jz      short loc_1800072EC
0x1800072b3  call    cs:__imp_DecodePointer
0x1800072b9  mov     r9, rax
0x1800072bc  mov     [rsp+48h+Ptr], rax
0x1800072c1  mov     rcx, [rax]
0x1800072c4  mov     rax, [rcx]
0x1800072c7  mov     r8, r14
0x1800072ca  mov     rdx, rbp
0x1800072cd  mov     rcx, r9
0x1800072d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d5  mov     edi, eax
0x1800072d7  test    rbx, rbx
0x1800072da  jz      short loc_1800072E5
0x1800072dc  mov     rcx, rbx; SRWLock
0x1800072df  call    cs:__imp_ReleaseSRWLockShared
0x1800072e5  mov     eax, edi
0x1800072e7  jmp     loc_1800073BF
0x1800072ec  test    rbx, rbx
0x1800072ef  jz      short loc_1800072FA
0x1800072f1  mov     rcx, rbx; SRWLock
0x1800072f4  call    cs:__imp_ReleaseSRWLockShared
0x1800072fa  lea     r9, [rsp+48h+Ptr]
0x1800072ff  mov     r8, rbp
0x180007302  mov     rdx, rdi
0x180007305  mov     rcx, rsi
0x180007308  mov     rax, [rdi]
0x18000730b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007310  test    eax, eax
0x180007312  js      loc_1800073BF
0x180007318  test    byte ptr [rsi], 4
0x18000731b  jnz     loc_1800073B5
0x180007321  mov     rax, cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x180007328  lea     rcx, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000732f  mov     rax, [rax+38h]
0x180007333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007338  mov     rsi, rax
0x18000733b  mov     rcx, rax; SRWLock
0x18000733e  call    cs:__imp_AcquireSRWLockExclusive
0x180007344  mov     rcx, [rdi+18h]
0x180007348  mov     rcx, [rcx]; Ptr
0x18000734b  test    rcx, rcx
0x18000734e  jnz     short loc_180007366
0x180007350  xor     ebx, ebx
0x180007352  mov     rcx, [rsp+48h+Ptr]; Ptr
0x180007357  call    cs:__imp_EncodePointer
0x18000735d  mov     rcx, [rdi+18h]
0x180007361  mov     [rcx], rax
0x180007364  jmp     short loc_18000737E
0x180007366  call    cs:__imp_DecodePointer
0x18000736c  mov     rbx, rax
0x18000736f  mov     rcx, [rax]
0x180007372  mov     rax, [rcx+8]
0x180007376  mov     rcx, rbx
0x180007379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000737e  test    rsi, rsi
0x180007381  jz      short loc_18000738C
0x180007383  mov     rcx, rsi; SRWLock
0x180007386  call    cs:__imp_ReleaseSRWLockExclusive
0x18000738c  test    rbx, rbx
0x18000738f  jz      short loc_1800073B5
0x180007391  mov     rcx, [rsp+48h+Ptr]
0x180007396  mov     rax, [rcx]
0x180007399  mov     rax, [rax+10h]
0x18000739d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073a2  mov     rcx, [rsp+48h+Ptr]
0x1800073a7  mov     rax, [rcx]
0x1800073aa  mov     rax, [rax+10h]
0x1800073ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b3  jmp     short loc_1800073BA
0x1800073b5  mov     rbx, [rsp+48h+Ptr]
0x1800073ba  mov     [r14], rbx
0x1800073bd  xor     eax, eax
0x1800073bf  mov     rbx, [rsp+48h+arg_8]
0x1800073c4  mov     rbp, [rsp+48h+arg_10]
0x1800073c9  add     rsp, 30h
0x1800073cd  pop     r14
0x1800073cf  pop     rdi
0x1800073d0  pop     rsi
0x1800073d1  retn
```
