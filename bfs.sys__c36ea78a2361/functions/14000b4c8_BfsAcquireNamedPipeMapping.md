# BfsAcquireNamedPipeMapping

- ea: `0x14000b4c8`
- end: `0x14000b5ac`
- name: `BfsAcquireNamedPipeMapping`
- size: `228`
- prototype: `PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall(__int64, unsigned __int8 *, unsigned __int8 *, const UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002620`
- `0x140002d30`

## callees

- `0x1400013e0`
- `0x1400017b0`
- `0x14000b4c8`
- `0x14000b870`
- `0x140012d00`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b549`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b549`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b57d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b57d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b538`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b538`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b589`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b589`

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
  BfsUpdateHash(a2, 4 * (unsigned int)a2[1] + 8, &v12);
  BfsUpdateHash(a3, 4 * (unsigned int)a3[1] + 8, &v12);
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
0x14000b4c8  mov     rax, rsp
0x14000b4cb  mov     [rax+10h], rbx
0x14000b4cf  mov     [rax+18h], rbp
0x14000b4d3  push    rsi
0x14000b4d4  push    rdi
0x14000b4d5  push    r14
0x14000b4d7  sub     rsp, 30h
0x14000b4db  mov     rbp, rdx
0x14000b4de  mov     qword ptr [rax+8], 0
0x14000b4e6  movzx   edx, byte ptr [rdx+1]
0x14000b4ea  mov     rsi, r8
0x14000b4ed  mov     r14, rcx
0x14000b4f0  lea     r8, [rax+8]
0x14000b4f4  mov     rcx, rbp
0x14000b4f7  mov     rdi, r9
0x14000b4fa  lea     edx, ds:8[rdx*4]
0x14000b501  call    BfsUpdateHash
0x14000b506  movzx   edx, byte ptr [rsi+1]
0x14000b50a  lea     r8, [rsp+48h+arg_0]
0x14000b50f  mov     rcx, rsi
0x14000b512  lea     edx, ds:8[rdx*4]
0x14000b519  call    BfsUpdateHash
0x14000b51e  lea     rdx, [rsp+48h+arg_0]
0x14000b523  mov     rcx, rdi
0x14000b526  call    BfsUpdateUnicodeStringHash
0x14000b52b  lea     rcx, [rsp+48h+arg_0]
0x14000b530  call    BfsFinalHash
0x14000b535  mov     rbx, rax
0x14000b538  call    cs:__imp_KeEnterCriticalRegion
0x14000b53f  nop     dword ptr [rax+rax+00h]
0x14000b544  xor     edx, edx
0x14000b546  mov     rcx, r14
0x14000b549  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000b550  nop     dword ptr [rax+rax+00h]
0x14000b555  mov     rcx, [r14+8]; HashTable
0x14000b559  mov     r9, rsi
0x14000b55c  mov     r8, rbp
0x14000b55f  mov     [rsp+48h+String2], rdi; String2
0x14000b564  mov     rdx, rbx
0x14000b567  call    BfsLookupPipeMappingEntryHashTable
0x14000b56c  mov     rbx, rax
0x14000b56f  test    rax, rax
0x14000b572  jz      short loc_14000B578
0x14000b574  lock inc dword ptr [rax+18h]
0x14000b578  xor     edx, edx
0x14000b57a  mov     rcx, r14
0x14000b57d  call    cs:__imp_ExReleasePushLockSharedEx
0x14000b584  nop     dword ptr [rax+rax+00h]
0x14000b589  call    cs:__imp_KeLeaveCriticalRegion
0x14000b590  nop     dword ptr [rax+rax+00h]
0x14000b595  mov     rbp, [rsp+48h+arg_10]
0x14000b59a  mov     rax, rbx
0x14000b59d  mov     rbx, [rsp+48h+arg_8]
0x14000b5a2  add     rsp, 30h
0x14000b5a6  pop     r14
0x14000b5a8  pop     rdi
0x14000b5a9  pop     rsi
0x14000b5aa  retn
```
