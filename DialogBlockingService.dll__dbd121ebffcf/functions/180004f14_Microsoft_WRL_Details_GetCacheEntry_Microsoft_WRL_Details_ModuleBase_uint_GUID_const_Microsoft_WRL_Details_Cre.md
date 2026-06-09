# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180004f14`
- end: `0x180005098`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002250`

## callees

- `0x180004f14`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004fa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004fbd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004fa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004fbd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004f66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004f66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005004`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005004`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000504c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000504c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000501d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000501d`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004f78`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000502c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180004f78`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000502c`

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
  PVOID Ptr; // [rsp+60h] [rbp+18h] BYREF

  v8 = a5;
  *(_QWORD *)a5 = 0;
  Ptr = 0;
  if ( **(_QWORD **)a4[1].Data4 )
  {
    v9 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
    AcquireSRWLockShared(v9);
    v10 = **(void ***)a4[1].Data4;
    if ( v10 )
    {
      Ptr = DecodePointer(v10);
      v11 = (**(__int64 (__fastcall ***)(PVOID, GUID *, const struct Microsoft::WRL::Details::CreatorMap *))Ptr)(
              Ptr,
              &GUID_00000035_0000_0000_c000_000000000046,
              v8);
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
    v13 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
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
0x180004f14  mov     rax, rsp
0x180004f17  mov     [rax+8], rbx
0x180004f1b  mov     [rax+10h], rbp
0x180004f1f  mov     [rax+18h], r8
0x180004f23  push    rsi
0x180004f24  push    rdi
0x180004f25  push    r14
0x180004f27  sub     rsp, 30h
0x180004f2b  mov     rdi, r9
0x180004f2e  mov     rbp, rdx
0x180004f31  mov     rsi, rcx
0x180004f34  mov     r14, [rsp+48h+arg_20]
0x180004f39  mov     qword ptr [r14], 0
0x180004f40  mov     qword ptr [rax+18h], 0
0x180004f48  mov     rax, [r9+18h]
0x180004f4c  mov     r8, [rax]
0x180004f4f  test    r8, r8
0x180004f52  jz      short loc_180004FC3
0x180004f54  mov     rax, [rcx]
0x180004f57  mov     rax, [rax+38h]
0x180004f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f60  mov     rbx, rax
0x180004f63  mov     rcx, rax; SRWLock
0x180004f66  call    cs:__imp_AcquireSRWLockShared
0x180004f6c  mov     rcx, [rdi+18h]
0x180004f70  mov     rcx, [rcx]; Ptr
0x180004f73  test    rcx, rcx
0x180004f76  jz      short loc_180004FB5
0x180004f78  call    cs:__imp_DecodePointer
0x180004f7e  mov     r9, rax
0x180004f81  mov     [rsp+48h+Ptr], rax
0x180004f86  mov     rcx, [rax]
0x180004f89  mov     rax, [rcx]
0x180004f8c  mov     r8, r14
0x180004f8f  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180004f96  mov     rcx, r9
0x180004f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9e  mov     edi, eax
0x180004fa0  test    rbx, rbx
0x180004fa3  jz      short loc_180004FAE
0x180004fa5  mov     rcx, rbx; SRWLock
0x180004fa8  call    cs:__imp_ReleaseSRWLockShared
0x180004fae  mov     eax, edi
0x180004fb0  jmp     loc_180005085
0x180004fb5  test    rbx, rbx
0x180004fb8  jz      short loc_180004FC3
0x180004fba  mov     rcx, rbx; SRWLock
0x180004fbd  call    cs:__imp_ReleaseSRWLockShared
0x180004fc3  lea     r9, [rsp+48h+Ptr]
0x180004fc8  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x180004fcf  mov     rdx, rdi
0x180004fd2  mov     rcx, rbp
0x180004fd5  mov     rax, [rdi]
0x180004fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fdd  test    eax, eax
0x180004fdf  js      loc_180005085
0x180004fe5  test    byte ptr [rbp+0], 4
0x180004fe9  jnz     loc_18000507B
0x180004fef  mov     rax, [rsi]
0x180004ff2  mov     rcx, rsi
0x180004ff5  mov     rax, [rax+38h]
0x180004ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffe  mov     rsi, rax
0x180005001  mov     rcx, rax; SRWLock
0x180005004  call    cs:__imp_AcquireSRWLockExclusive
0x18000500a  mov     rcx, [rdi+18h]
0x18000500e  mov     rcx, [rcx]; Ptr
0x180005011  test    rcx, rcx
0x180005014  jnz     short loc_18000502C
0x180005016  xor     ebx, ebx
0x180005018  mov     rcx, [rsp+48h+Ptr]; Ptr
0x18000501d  call    cs:__imp_EncodePointer
0x180005023  mov     rcx, [rdi+18h]
0x180005027  mov     [rcx], rax
0x18000502a  jmp     short loc_180005044
0x18000502c  call    cs:__imp_DecodePointer
0x180005032  mov     rbx, rax
0x180005035  mov     rcx, [rax]
0x180005038  mov     rax, [rcx+8]
0x18000503c  mov     rcx, rbx
0x18000503f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005044  test    rsi, rsi
0x180005047  jz      short loc_180005052
0x180005049  mov     rcx, rsi; SRWLock
0x18000504c  call    cs:__imp_ReleaseSRWLockExclusive
0x180005052  test    rbx, rbx
0x180005055  jz      short loc_18000507B
0x180005057  mov     rcx, [rsp+48h+Ptr]
0x18000505c  mov     rax, [rcx]
0x18000505f  mov     rax, [rax+10h]
0x180005063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005068  mov     rcx, [rsp+48h+Ptr]
0x18000506d  mov     rax, [rcx]
0x180005070  mov     rax, [rax+10h]
0x180005074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005079  jmp     short loc_180005080
0x18000507b  mov     rbx, [rsp+48h+Ptr]
0x180005080  mov     [r14], rbx
0x180005083  xor     eax, eax
0x180005085  mov     rbx, [rsp+48h+arg_0]
0x18000508a  mov     rbp, [rsp+48h+arg_8]
0x18000508f  add     rsp, 30h
0x180005093  pop     r14
0x180005095  pop     rdi
0x180005096  pop     rsi
0x180005097  retn
```
