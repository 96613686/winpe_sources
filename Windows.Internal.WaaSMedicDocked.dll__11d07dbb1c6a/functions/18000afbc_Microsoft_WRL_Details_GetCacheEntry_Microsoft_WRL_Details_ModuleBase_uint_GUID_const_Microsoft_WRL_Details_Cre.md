# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x18000afbc`
- end: `0x18000b140`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, const struct Microsoft::WRL::Details::CreatorMap *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ae44`

## callees

- `0x18000afbc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b0ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b0f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b065`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b065`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b00e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b00e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b0c5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b0c5`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b020`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0d4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b020`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0d4`

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
0x18000afbc  mov     rax, rsp
0x18000afbf  mov     [rax+8], rbx
0x18000afc3  mov     [rax+10h], rbp
0x18000afc7  mov     [rax+18h], r8
0x18000afcb  push    rsi
0x18000afcc  push    rdi
0x18000afcd  push    r14
0x18000afcf  sub     rsp, 30h
0x18000afd3  mov     rdi, r9
0x18000afd6  mov     rbp, rdx
0x18000afd9  mov     rsi, rcx
0x18000afdc  mov     r14, [rsp+48h+arg_20]
0x18000afe1  mov     qword ptr [r14], 0
0x18000afe8  mov     qword ptr [rax+18h], 0
0x18000aff0  mov     rax, [r9+18h]
0x18000aff4  mov     r8, [rax]
0x18000aff7  test    r8, r8
0x18000affa  jz      short loc_18000B06B
0x18000affc  mov     rax, [rcx]
0x18000afff  mov     rax, [rax+38h]
0x18000b003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b008  mov     rbx, rax
0x18000b00b  mov     rcx, rax; SRWLock
0x18000b00e  call    cs:__imp_AcquireSRWLockShared
0x18000b014  mov     rcx, [rdi+18h]
0x18000b018  mov     rcx, [rcx]; Ptr
0x18000b01b  test    rcx, rcx
0x18000b01e  jz      short loc_18000B05D
0x18000b020  call    cs:__imp_DecodePointer
0x18000b026  mov     r9, rax
0x18000b029  mov     [rsp+48h+Ptr], rax
0x18000b02e  mov     rcx, [rax]
0x18000b031  mov     rax, [rcx]
0x18000b034  mov     r8, r14
0x18000b037  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18000b03e  mov     rcx, r9
0x18000b041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b046  mov     edi, eax
0x18000b048  test    rbx, rbx
0x18000b04b  jz      short loc_18000B056
0x18000b04d  mov     rcx, rbx; SRWLock
0x18000b050  call    cs:__imp_ReleaseSRWLockShared
0x18000b056  mov     eax, edi
0x18000b058  jmp     loc_18000B12D
0x18000b05d  test    rbx, rbx
0x18000b060  jz      short loc_18000B06B
0x18000b062  mov     rcx, rbx; SRWLock
0x18000b065  call    cs:__imp_ReleaseSRWLockShared
0x18000b06b  lea     r9, [rsp+48h+Ptr]
0x18000b070  lea     r8, _GUID_00000035_0000_0000_c000_000000000046
0x18000b077  mov     rdx, rdi
0x18000b07a  mov     rcx, rbp
0x18000b07d  mov     rax, [rdi]
0x18000b080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b085  test    eax, eax
0x18000b087  js      loc_18000B12D
0x18000b08d  test    byte ptr [rbp+0], 4
0x18000b091  jnz     loc_18000B123
0x18000b097  mov     rax, [rsi]
0x18000b09a  mov     rcx, rsi
0x18000b09d  mov     rax, [rax+38h]
0x18000b0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0a6  mov     rsi, rax
0x18000b0a9  mov     rcx, rax; SRWLock
0x18000b0ac  call    cs:__imp_AcquireSRWLockExclusive
0x18000b0b2  mov     rcx, [rdi+18h]
0x18000b0b6  mov     rcx, [rcx]; Ptr
0x18000b0b9  test    rcx, rcx
0x18000b0bc  jnz     short loc_18000B0D4
0x18000b0be  xor     ebx, ebx
0x18000b0c0  mov     rcx, [rsp+48h+Ptr]; Ptr
0x18000b0c5  call    cs:__imp_EncodePointer
0x18000b0cb  mov     rcx, [rdi+18h]
0x18000b0cf  mov     [rcx], rax
0x18000b0d2  jmp     short loc_18000B0EC
0x18000b0d4  call    cs:__imp_DecodePointer
0x18000b0da  mov     rbx, rax
0x18000b0dd  mov     rcx, [rax]
0x18000b0e0  mov     rax, [rcx+8]
0x18000b0e4  mov     rcx, rbx
0x18000b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ec  test    rsi, rsi
0x18000b0ef  jz      short loc_18000B0FA
0x18000b0f1  mov     rcx, rsi; SRWLock
0x18000b0f4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b0fa  test    rbx, rbx
0x18000b0fd  jz      short loc_18000B123
0x18000b0ff  mov     rcx, [rsp+48h+Ptr]
0x18000b104  mov     rax, [rcx]
0x18000b107  mov     rax, [rax+10h]
0x18000b10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b110  mov     rcx, [rsp+48h+Ptr]
0x18000b115  mov     rax, [rcx]
0x18000b118  mov     rax, [rax+10h]
0x18000b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b121  jmp     short loc_18000B128
0x18000b123  mov     rbx, [rsp+48h+Ptr]
0x18000b128  mov     [r14], rbx
0x18000b12b  xor     eax, eax
0x18000b12d  mov     rbx, [rsp+48h+arg_0]
0x18000b132  mov     rbp, [rsp+48h+arg_8]
0x18000b137  add     rsp, 30h
0x18000b13b  pop     r14
0x18000b13d  pop     rdi
0x18000b13e  pop     rsi
0x18000b13f  retn
```
