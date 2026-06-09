# BfsAcquireNamedPipeMapping

- ea: `0x14000b338`
- end: `0x14000b41c`
- name: `BfsAcquireNamedPipeMapping`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001460`
- `0x140002a30`

## callees

- `0x1400013e0`
- `0x140001bc0`
- `0x14000b338`
- `0x14000b6e0`
- `0x140012bc8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b3b9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b3b9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b3ed`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b3ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b3a8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b3a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b3f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b3f9`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall BfsAcquireNamedPipeMapping(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const UNICODE_STRING *a4)
{
  ULONG_PTR v8; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v9; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v10; // rbx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = 0;
  BfsUpdateHash((__int64)a2, 4 * a2[1] + 8, &v12);
  BfsUpdateHash((__int64)a3, 4 * a3[1] + 8, &v12);
  BfsUpdateUnicodeStringHash(a4, &v12);
  v8 = BfsFinalHash(&v12);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  v9 = BfsLookupPipeMappingEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), v8, a2, a3, a4);
  v10 = v9;
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)&v9[1]);
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  return v10;
}

```

## disassembly

```asm
0x14000b338  mov     rax, rsp
0x14000b33b  mov     [rax+10h], rbx
0x14000b33f  mov     [rax+18h], rbp
0x14000b343  push    rsi
0x14000b344  push    rdi
0x14000b345  push    r14
0x14000b347  sub     rsp, 30h
0x14000b34b  mov     rbp, rdx
0x14000b34e  mov     qword ptr [rax+8], 0
0x14000b356  movzx   edx, byte ptr [rdx+1]
0x14000b35a  mov     rsi, r8
0x14000b35d  mov     r14, rcx
0x14000b360  lea     r8, [rax+8]
0x14000b364  mov     rcx, rbp
0x14000b367  mov     rdi, r9
0x14000b36a  lea     edx, ds:8[rdx*4]
0x14000b371  call    BfsUpdateHash
0x14000b376  movzx   edx, byte ptr [rsi+1]
0x14000b37a  lea     r8, [rsp+48h+arg_0]
0x14000b37f  mov     rcx, rsi
0x14000b382  lea     edx, ds:8[rdx*4]
0x14000b389  call    BfsUpdateHash
0x14000b38e  lea     rdx, [rsp+48h+arg_0]
0x14000b393  mov     rcx, rdi
0x14000b396  call    BfsUpdateUnicodeStringHash
0x14000b39b  lea     rcx, [rsp+48h+arg_0]
0x14000b3a0  call    BfsFinalHash
0x14000b3a5  mov     rbx, rax
0x14000b3a8  call    cs:__imp_KeEnterCriticalRegion
0x14000b3af  nop     dword ptr [rax+rax+00h]
0x14000b3b4  xor     edx, edx
0x14000b3b6  mov     rcx, r14
0x14000b3b9  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000b3c0  nop     dword ptr [rax+rax+00h]
0x14000b3c5  mov     rcx, [r14+8]; HashTable
0x14000b3c9  mov     r9, rsi
0x14000b3cc  mov     r8, rbp
0x14000b3cf  mov     [rsp+48h+String2], rdi; String2
0x14000b3d4  mov     rdx, rbx
0x14000b3d7  call    BfsLookupPipeMappingEntryHashTable
0x14000b3dc  mov     rbx, rax
0x14000b3df  test    rax, rax
0x14000b3e2  jz      short loc_14000B3E8
0x14000b3e4  lock inc dword ptr [rax+18h]
0x14000b3e8  xor     edx, edx
0x14000b3ea  mov     rcx, r14
0x14000b3ed  call    cs:__imp_ExReleasePushLockSharedEx
0x14000b3f4  nop     dword ptr [rax+rax+00h]
0x14000b3f9  call    cs:__imp_KeLeaveCriticalRegion
0x14000b400  nop     dword ptr [rax+rax+00h]
0x14000b405  mov     rbp, [rsp+48h+arg_10]
0x14000b40a  mov     rax, rbx
0x14000b40d  mov     rbx, [rsp+48h+arg_8]
0x14000b412  add     rsp, 30h
0x14000b416  pop     r14
0x14000b418  pop     rdi
0x14000b419  pop     rsi
0x14000b41a  retn
```
