# BfsRemovePolicyFromGlobalFileTable

- ea: `0x14000d5a0`
- end: `0x14000d765`
- name: `BfsRemovePolicyFromGlobalFileTable`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d3f8`

## callees

- `0x140001008`
- `0x140001320`
- `0x1400013e0`
- `0x14000c31c`
- `0x14000c8cc`
- `0x14000d5a0`
- `0x140012b9c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d5f2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d6c6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d5f2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d6c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d70f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d72f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d70f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d72f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d67c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d69f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d67c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d68e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d69f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6fe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d5e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d6b5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d5e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d6b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d71b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d73b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d71b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d73b`

## pseudocode

```c
__int64 __fastcall BfsRemovePolicyFromGlobalFileTable(__int64 a1, unsigned __int8 *a2, unsigned __int8 *a3, __int64 a4)
{
  __int64 GlobalFileEntry; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rsi
  unsigned int v12; // ebx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *GlobalFilePolicy; // rax
  PVOID *p_Flink; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v15; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v16; // rbx
  int v18; // [rsp+20h] [rbp-50h]
  __int64 v19; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v21; // [rsp+58h] [rbp-18h]
  __int64 v22; // [rsp+60h] [rbp-10h]

  v19 = 0;
  BfsUpdateUnicodeStringHash(a4, &v19);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 8, 0);
  GlobalFileEntry = BfsGetGlobalFileEntry(a1, a4);
  v11 = GlobalFileEntry;
  if ( GlobalFileEntry
    && (GlobalFilePolicy = BfsGetGlobalFilePolicy(GlobalFileEntry, a2, a3),
        (p_Flink = (PVOID *)&GlobalFilePolicy->Linkage.Flink) != 0) )
  {
    BfsRemoveEntryHashTable(*(struct _RTL_DYNAMIC_HASH_TABLE **)(v11 + 88), GlobalFilePolicy);
    ExFreePoolWithTag(p_Flink[3], 0);
    ExFreePoolWithTag(p_Flink[4], 0);
    ExFreePoolWithTag(p_Flink, 0);
    if ( !*(_DWORD *)(*(_QWORD *)(v11 + 88) + 20LL) )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1, 0);
      v15 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)BfsGetGlobalFileEntry(a1, a4);
      v16 = v15;
      if ( v15 )
      {
        BfsRemoveEntryHashTable(*(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 40), v15);
        BfsClearGlobalFileEntry((__int64)v16);
        ExFreePoolWithTag(v16, 0);
      }
      ExReleasePushLockExclusiveEx(a1, 0);
      KeLeaveCriticalRegion();
    }
    v12 = 0;
  }
  else
  {
    v12 = -1073741275;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v19) = -1073741275;
      v21 = &v19;
      v22 = 4;
      tlgWriteTransfer_EtwWriteTransfer(3221226021LL, (unsigned __int8 *)&byte_140016D91, v9, v10, v18, &v20);
    }
  }
  ExReleasePushLockExclusiveEx(a1 + 8, 0);
  KeLeaveCriticalRegion();
  return v12;
}

```

## disassembly

```asm
0x14000d5a0  push    rbp
0x14000d5a2  push    rbx
0x14000d5a3  push    rsi
0x14000d5a4  push    rdi
0x14000d5a5  push    r12
0x14000d5a7  push    r14
0x14000d5a9  push    r15
0x14000d5ab  mov     rbp, rsp
0x14000d5ae  sub     rsp, 70h
0x14000d5b2  mov     rax, cs:__security_cookie
0x14000d5b9  xor     rax, rsp
0x14000d5bc  mov     [rbp+var_8], rax
0x14000d5c0  mov     rbx, rdx
0x14000d5c3  mov     [rbp+var_40], 0
0x14000d5cb  mov     rdi, rcx
0x14000d5ce  lea     rdx, [rbp+var_40]
0x14000d5d2  mov     rcx, r9
0x14000d5d5  mov     r14, r9
0x14000d5d8  mov     r12, r8
0x14000d5db  call    BfsUpdateUnicodeStringHash
0x14000d5e0  call    cs:__imp_KeEnterCriticalRegion
0x14000d5e7  nop     dword ptr [rax+rax+00h]
0x14000d5ec  xor     edx, edx
0x14000d5ee  lea     rcx, [rdi+8]
0x14000d5f2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d5f9  nop     dword ptr [rax+rax+00h]
0x14000d5fe  mov     rdx, r14
0x14000d601  mov     rcx, rdi
0x14000d604  call    BfsGetGlobalFileEntry
0x14000d609  mov     rsi, rax
0x14000d60c  test    rax, rax
0x14000d60f  jnz     short loc_14000D654
0x14000d611  mov     eax, cs:dword_140019000
0x14000d617  mov     ecx, 0C0000225h; int
0x14000d61c  mov     ebx, ecx
0x14000d61e  cmp     eax, 3
0x14000d621  jbe     loc_14000D729
0x14000d627  lea     rax, [rbp+var_40]
0x14000d62b  mov     dword ptr [rbp+var_40], ecx
0x14000d62e  mov     [rbp+var_18], rax
0x14000d632  lea     rdx, byte_140016D91; int
0x14000d639  lea     rax, [rbp+var_38]
0x14000d63d  mov     [rbp+var_10], 4
0x14000d645  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x14000d64a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d64f  jmp     loc_14000D729
0x14000d654  mov     r8, r12
0x14000d657  mov     rdx, rbx
0x14000d65a  mov     rcx, rsi
0x14000d65d  call    BfsGetGlobalFilePolicy
0x14000d662  mov     rbx, rax
0x14000d665  test    rax, rax
0x14000d668  jz      short loc_14000D611
0x14000d66a  mov     rcx, [rsi+58h]
0x14000d66e  mov     rdx, rax
0x14000d671  call    BfsRemoveEntryHashTable
0x14000d676  mov     rcx, [rbx+18h]; P
0x14000d67a  xor     edx, edx; Tag
0x14000d67c  call    cs:__imp_ExFreePoolWithTag
0x14000d683  nop     dword ptr [rax+rax+00h]
0x14000d688  mov     rcx, [rbx+20h]; P
0x14000d68c  xor     edx, edx; Tag
0x14000d68e  call    cs:__imp_ExFreePoolWithTag
0x14000d695  nop     dword ptr [rax+rax+00h]
0x14000d69a  xor     edx, edx; Tag
0x14000d69c  mov     rcx, rbx; P
0x14000d69f  call    cs:__imp_ExFreePoolWithTag
0x14000d6a6  nop     dword ptr [rax+rax+00h]
0x14000d6ab  mov     rax, [rsi+58h]
0x14000d6af  cmp     dword ptr [rax+14h], 0
0x14000d6b3  jnz     short loc_14000D727
0x14000d6b5  call    cs:__imp_KeEnterCriticalRegion
0x14000d6bc  nop     dword ptr [rax+rax+00h]
0x14000d6c1  xor     edx, edx
0x14000d6c3  mov     rcx, rdi
0x14000d6c6  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d6cd  nop     dword ptr [rax+rax+00h]
0x14000d6d2  mov     rdx, r14
0x14000d6d5  mov     rcx, rdi
0x14000d6d8  call    BfsGetGlobalFileEntry
0x14000d6dd  mov     rbx, rax
0x14000d6e0  test    rax, rax
0x14000d6e3  jz      short loc_14000D70A
0x14000d6e5  mov     rcx, [rdi+28h]
0x14000d6e9  mov     rdx, rax
0x14000d6ec  call    BfsRemoveEntryHashTable
0x14000d6f1  mov     rcx, rbx
0x14000d6f4  call    BfsClearGlobalFileEntry
0x14000d6f9  xor     edx, edx; Tag
0x14000d6fb  mov     rcx, rbx; P
0x14000d6fe  call    cs:__imp_ExFreePoolWithTag
0x14000d705  nop     dword ptr [rax+rax+00h]
0x14000d70a  xor     edx, edx
0x14000d70c  mov     rcx, rdi
0x14000d70f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d716  nop     dword ptr [rax+rax+00h]
0x14000d71b  call    cs:__imp_KeLeaveCriticalRegion
0x14000d722  nop     dword ptr [rax+rax+00h]
0x14000d727  xor     ebx, ebx
0x14000d729  xor     edx, edx
0x14000d72b  lea     rcx, [rdi+8]
0x14000d72f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d736  nop     dword ptr [rax+rax+00h]
0x14000d73b  call    cs:__imp_KeLeaveCriticalRegion
0x14000d742  nop     dword ptr [rax+rax+00h]
0x14000d747  mov     eax, ebx
0x14000d749  mov     rcx, [rbp+var_8]
0x14000d74d  xor     rcx, rsp; StackCookie
0x14000d750  call    __security_check_cookie
0x14000d755  add     rsp, 70h
0x14000d759  pop     r15
0x14000d75b  pop     r14
0x14000d75d  pop     r12
0x14000d75f  pop     rdi
0x14000d760  pop     rsi
0x14000d761  pop     rbx
0x14000d762  pop     rbp
0x14000d763  retn
```
