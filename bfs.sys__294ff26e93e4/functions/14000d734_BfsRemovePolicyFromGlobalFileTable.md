# BfsRemovePolicyFromGlobalFileTable

- ea: `0x14000d734`
- end: `0x14000d8f9`
- name: `BfsRemovePolicyFromGlobalFileTable`
- size: `453`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x14000d58c`

## callees

- `0x140001008`
- `0x140001320`
- `0x1400013e0`
- `0x14000c4ac`
- `0x14000ca5c`
- `0x14000d734`
- `0x140012cd4`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d786`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d85a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d786`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000d85a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d8a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d8c3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d8a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d8c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d810`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d822`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d833`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d892`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d810`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d822`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d833`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d892`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d774`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d849`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d774`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d849`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8cf`

## pseudocode

```c
__int64 __fastcall BfsRemovePolicyFromGlobalFileTable(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 GlobalFileEntry; // rax
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rsi
  unsigned int v12; // ebx
  __int64 GlobalFilePolicy; // rax
  PVOID *v14; // rbx
  __int64 v15; // rax
  void *v16; // rbx
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
    && (GlobalFilePolicy = BfsGetGlobalFilePolicy(GlobalFileEntry, a2, a3), (v14 = (PVOID *)GlobalFilePolicy) != 0) )
  {
    BfsRemoveEntryHashTable(*(_QWORD *)(v11 + 88), GlobalFilePolicy);
    ExFreePoolWithTag(v14[3], 0);
    ExFreePoolWithTag(v14[4], 0);
    ExFreePoolWithTag(v14, 0);
    if ( !*(_DWORD *)(*(_QWORD *)(v11 + 88) + 20LL) )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(a1, 0);
      v15 = BfsGetGlobalFileEntry(a1, a4);
      v16 = (void *)v15;
      if ( v15 )
      {
        BfsRemoveEntryHashTable(*(_QWORD *)(a1 + 40), v15);
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
      tlgWriteTransfer_EtwWriteTransfer(-1073741275, (int)&byte_140016D91, v9, v10, v18, &v20);
    }
  }
  ExReleasePushLockExclusiveEx(a1 + 8, 0);
  KeLeaveCriticalRegion();
  return v12;
}

```

## disassembly

```asm
0x14000d734  push    rbp
0x14000d736  push    rbx
0x14000d737  push    rsi
0x14000d738  push    rdi
0x14000d739  push    r12
0x14000d73b  push    r14
0x14000d73d  push    r15
0x14000d73f  mov     rbp, rsp
0x14000d742  sub     rsp, 70h
0x14000d746  mov     rax, cs:__security_cookie
0x14000d74d  xor     rax, rsp
0x14000d750  mov     [rbp+var_8], rax
0x14000d754  mov     rbx, rdx
0x14000d757  mov     [rbp+var_40], 0
0x14000d75f  mov     rdi, rcx
0x14000d762  lea     rdx, [rbp+var_40]
0x14000d766  mov     rcx, r9
0x14000d769  mov     r14, r9
0x14000d76c  mov     r12, r8
0x14000d76f  call    BfsUpdateUnicodeStringHash
0x14000d774  call    cs:__imp_KeEnterCriticalRegion
0x14000d77b  nop     dword ptr [rax+rax+00h]
0x14000d780  xor     edx, edx
0x14000d782  lea     rcx, [rdi+8]
0x14000d786  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d78d  nop     dword ptr [rax+rax+00h]
0x14000d792  mov     rdx, r14
0x14000d795  mov     rcx, rdi
0x14000d798  call    BfsGetGlobalFileEntry
0x14000d79d  mov     rsi, rax
0x14000d7a0  test    rax, rax
0x14000d7a3  jnz     short loc_14000D7E8
0x14000d7a5  mov     eax, cs:dword_140019000
0x14000d7ab  mov     ecx, 0C0000225h; int
0x14000d7b0  mov     ebx, ecx
0x14000d7b2  cmp     eax, 3
0x14000d7b5  jbe     loc_14000D8BD
0x14000d7bb  lea     rax, [rbp+var_40]
0x14000d7bf  mov     dword ptr [rbp+var_40], ecx
0x14000d7c2  mov     [rbp+var_18], rax
0x14000d7c6  lea     rdx, byte_140016D91; int
0x14000d7cd  lea     rax, [rbp+var_38]
0x14000d7d1  mov     [rbp+var_10], 4
0x14000d7d9  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x14000d7de  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d7e3  jmp     loc_14000D8BD
0x14000d7e8  mov     r8, r12
0x14000d7eb  mov     rdx, rbx
0x14000d7ee  mov     rcx, rsi
0x14000d7f1  call    BfsGetGlobalFilePolicy
0x14000d7f6  mov     rbx, rax
0x14000d7f9  test    rax, rax
0x14000d7fc  jz      short loc_14000D7A5
0x14000d7fe  mov     rcx, [rsi+58h]
0x14000d802  mov     rdx, rax
0x14000d805  call    BfsRemoveEntryHashTable
0x14000d80a  mov     rcx, [rbx+18h]; P
0x14000d80e  xor     edx, edx; Tag
0x14000d810  call    cs:__imp_ExFreePoolWithTag
0x14000d817  nop     dword ptr [rax+rax+00h]
0x14000d81c  mov     rcx, [rbx+20h]; P
0x14000d820  xor     edx, edx; Tag
0x14000d822  call    cs:__imp_ExFreePoolWithTag
0x14000d829  nop     dword ptr [rax+rax+00h]
0x14000d82e  xor     edx, edx; Tag
0x14000d830  mov     rcx, rbx; P
0x14000d833  call    cs:__imp_ExFreePoolWithTag
0x14000d83a  nop     dword ptr [rax+rax+00h]
0x14000d83f  mov     rax, [rsi+58h]
0x14000d843  cmp     dword ptr [rax+14h], 0
0x14000d847  jnz     short loc_14000D8BB
0x14000d849  call    cs:__imp_KeEnterCriticalRegion
0x14000d850  nop     dword ptr [rax+rax+00h]
0x14000d855  xor     edx, edx
0x14000d857  mov     rcx, rdi
0x14000d85a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000d861  nop     dword ptr [rax+rax+00h]
0x14000d866  mov     rdx, r14
0x14000d869  mov     rcx, rdi
0x14000d86c  call    BfsGetGlobalFileEntry
0x14000d871  mov     rbx, rax
0x14000d874  test    rax, rax
0x14000d877  jz      short loc_14000D89E
0x14000d879  mov     rcx, [rdi+28h]
0x14000d87d  mov     rdx, rax
0x14000d880  call    BfsRemoveEntryHashTable
0x14000d885  mov     rcx, rbx
0x14000d888  call    BfsClearGlobalFileEntry
0x14000d88d  xor     edx, edx; Tag
0x14000d88f  mov     rcx, rbx; P
0x14000d892  call    cs:__imp_ExFreePoolWithTag
0x14000d899  nop     dword ptr [rax+rax+00h]
0x14000d89e  xor     edx, edx
0x14000d8a0  mov     rcx, rdi
0x14000d8a3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d8aa  nop     dword ptr [rax+rax+00h]
0x14000d8af  call    cs:__imp_KeLeaveCriticalRegion
0x14000d8b6  nop     dword ptr [rax+rax+00h]
0x14000d8bb  xor     ebx, ebx
0x14000d8bd  xor     edx, edx
0x14000d8bf  lea     rcx, [rdi+8]
0x14000d8c3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d8ca  nop     dword ptr [rax+rax+00h]
0x14000d8cf  call    cs:__imp_KeLeaveCriticalRegion
0x14000d8d6  nop     dword ptr [rax+rax+00h]
0x14000d8db  mov     eax, ebx
0x14000d8dd  mov     rcx, [rbp+var_8]
0x14000d8e1  xor     rcx, rsp; StackCookie
0x14000d8e4  call    __security_check_cookie
0x14000d8e9  add     rsp, 70h
0x14000d8ed  pop     r15
0x14000d8ef  pop     r14
0x14000d8f1  pop     r12
0x14000d8f3  pop     rdi
0x14000d8f4  pop     rsi
0x14000d8f5  pop     rbx
0x14000d8f6  pop     rbp
0x14000d8f7  retn
```
