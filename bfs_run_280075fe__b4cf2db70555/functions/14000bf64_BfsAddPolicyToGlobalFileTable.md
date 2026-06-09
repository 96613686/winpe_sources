# BfsAddPolicyToGlobalFileTable

- ea: `0x14000bf64`
- end: `0x14000c1ad`
- name: `BfsAddPolicyToGlobalFileTable`
- size: `585`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140009b9c`
- `0x14000cd20`
- `0x14000dadc`

## callees

- `0x140001008`
- `0x140001320`
- `0x1400013e0`
- `0x140001bc0`
- `0x14000bf64`
- `0x14000c434`
- `0x14000d848`
- `0x140012b68`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bfca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c03e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bfca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c03e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c13b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c172`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c13b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c172`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000bfe7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000bfe7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c015`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c154`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c015`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c154`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bfb8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bfd6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c02d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bfb8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000bfd6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c02d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c021`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c160`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c17e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c021`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c160`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c17e`

## pseudocode

```c
__int64 __fastcall BfsAddPolicyToGlobalFileTable(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        UNICODE_STRING *a4,
        int a5)
{
  __int64 v8; // r12
  int v9; // r14d
  struct _UNICODE_STRING *GlobalFileEntry; // rsi
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int inserted; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v20; // [rsp+20h] [rbp-51h]
  struct _UNICODE_STRING *v21; // [rsp+30h] [rbp-41h] BYREF
  unsigned __int8 *v22; // [rsp+38h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+40h] [rbp-31h] BYREF
  struct _UNICODE_STRING **v24; // [rsp+60h] [rbp-11h]
  __int64 v25; // [rsp+68h] [rbp-9h]

  v22 = a3;
  v21 = 0;
  BfsUpdateUnicodeStringHash(&a4->Length, &v21);
  v8 = BfsFinalHash(&v21);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 8, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  v9 = 1;
  GlobalFileEntry = (struct _UNICODE_STRING *)BfsGetGlobalFileEntry(a1, a4);
  if ( !GlobalFileEntry )
  {
    ExReleasePushLockSharedEx(a1, 0);
    KeLeaveCriticalRegion();
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1, 0);
    v9 = 2;
    v21 = (struct _UNICODE_STRING *)BfsGetGlobalFileEntry(a1, a4);
    GlobalFileEntry = v21;
    if ( !v21 )
    {
      v11 = BfsCreateGlobalFileEntry(a4, a5, &v21);
      inserted = v11;
      if ( v11 < 0 )
      {
        v15 = (unsigned int)dword_140019000;
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v21) = v11;
LABEL_6:
          v25 = 4;
          v24 = &v21;
          tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v12, v13, v20, &v23);
        }
LABEL_14:
        ExReleasePushLockExclusiveEx(a1, 0);
        goto LABEL_17;
      }
      GlobalFileEntry = v21;
      inserted = BfsInsertEntryHashTable(*(_QWORD *)(a1 + 40), v8, v21);
      if ( inserted < 0 )
      {
        if ( (unsigned int)dword_140019000 <= 3 )
          goto LABEL_14;
        LODWORD(v21) = inserted;
        goto LABEL_6;
      }
    }
  }
  inserted = BfsUpdateGlobalFilePolicy(a1, (__int64)GlobalFileEntry, a2, v22);
  if ( inserted >= 0 )
  {
    if ( v9 != 2 )
    {
      if ( v9 != 1 )
      {
LABEL_18:
        ExReleasePushLockExclusiveEx(a1 + 8, 0);
        KeLeaveCriticalRegion();
        return (unsigned int)inserted;
      }
      ExReleasePushLockSharedEx(a1, 0);
LABEL_17:
      KeLeaveCriticalRegion();
      goto LABEL_18;
    }
    goto LABEL_14;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v21) = inserted;
    v24 = &v21;
    v25 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v16, (unsigned __int8 *)&byte_140016D91, v17, v18, v20, &v23);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14000bf64  push    rbp
0x14000bf66  push    rbx
0x14000bf67  push    rsi
0x14000bf68  push    rdi
0x14000bf69  push    r12
0x14000bf6b  push    r13
0x14000bf6d  push    r14
0x14000bf6f  push    r15
0x14000bf71  lea     rbp, [rsp-17h]
0x14000bf76  sub     rsp, 88h
0x14000bf7d  mov     rax, cs:__security_cookie
0x14000bf84  xor     rax, rsp
0x14000bf87  mov     [rbp+4Fh+var_50], rax
0x14000bf8b  mov     r13, rdx
0x14000bf8e  mov     [rbp+4Fh+var_88], r8
0x14000bf92  mov     rdi, rcx
0x14000bf95  mov     [rbp+4Fh+var_90], 0
0x14000bf9d  lea     rdx, [rbp+4Fh+var_90]
0x14000bfa1  mov     rcx, r9
0x14000bfa4  mov     rbx, r9
0x14000bfa7  call    BfsUpdateUnicodeStringHash
0x14000bfac  lea     rcx, [rbp+4Fh+var_90]
0x14000bfb0  call    BfsFinalHash
0x14000bfb5  mov     r12, rax
0x14000bfb8  call    cs:__imp_KeEnterCriticalRegion
0x14000bfbf  nop     dword ptr [rax+rax+00h]
0x14000bfc4  xor     edx, edx
0x14000bfc6  lea     rcx, [rdi+8]
0x14000bfca  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000bfd1  nop     dword ptr [rax+rax+00h]
0x14000bfd6  call    cs:__imp_KeEnterCriticalRegion
0x14000bfdd  nop     dword ptr [rax+rax+00h]
0x14000bfe2  xor     edx, edx
0x14000bfe4  mov     rcx, rdi
0x14000bfe7  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000bfee  nop     dword ptr [rax+rax+00h]
0x14000bff3  mov     rdx, rbx
0x14000bff6  mov     rcx, rdi
0x14000bff9  mov     r14d, 1
0x14000bfff  call    BfsGetGlobalFileEntry
0x14000c004  mov     rsi, rax
0x14000c007  test    rax, rax
0x14000c00a  jnz     loc_14000C0DF
0x14000c010  xor     edx, edx
0x14000c012  mov     rcx, rdi
0x14000c015  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c01c  nop     dword ptr [rax+rax+00h]
0x14000c021  call    cs:__imp_KeLeaveCriticalRegion
0x14000c028  nop     dword ptr [rax+rax+00h]
0x14000c02d  call    cs:__imp_KeEnterCriticalRegion
0x14000c034  nop     dword ptr [rax+rax+00h]
0x14000c039  xor     edx, edx
0x14000c03b  mov     rcx, rdi
0x14000c03e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c045  nop     dword ptr [rax+rax+00h]
0x14000c04a  mov     rdx, rbx
0x14000c04d  lea     r14d, [rsi+2]
0x14000c051  mov     rcx, rdi
0x14000c054  call    BfsGetGlobalFileEntry
0x14000c059  mov     [rbp+4Fh+var_90], rax
0x14000c05d  mov     rsi, rax
0x14000c060  test    rax, rax
0x14000c063  jnz     short loc_14000C0DF
0x14000c065  mov     edx, [rbp+4Fh+arg_20]
0x14000c068  lea     r8, [rbp+4Fh+var_90]
0x14000c06c  mov     rcx, rbx; SourceString
0x14000c06f  call    BfsCreateGlobalFileEntry
0x14000c074  mov     ebx, eax
0x14000c076  test    eax, eax
0x14000c078  jns     short loc_14000C0B6
0x14000c07a  mov     ecx, cs:dword_140019000; int
0x14000c080  cmp     ecx, 3
0x14000c083  jbe     loc_14000C136
0x14000c089  mov     dword ptr [rbp+4Fh+var_90], eax
0x14000c08c  lea     rax, [rbp+4Fh+var_90]
0x14000c090  mov     [rbp+4Fh+var_58], 4
0x14000c098  mov     [rbp+4Fh+var_60], rax
0x14000c09c  lea     rdx, byte_140016D91; int
0x14000c0a3  lea     rax, [rbp+4Fh+var_80]
0x14000c0a7  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000c0ac  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c0b1  jmp     loc_14000C136
0x14000c0b6  mov     rsi, [rbp+4Fh+var_90]
0x14000c0ba  mov     rdx, r12
0x14000c0bd  mov     rcx, [rdi+28h]
0x14000c0c1  mov     r8, rsi
0x14000c0c4  call    BfsInsertEntryHashTable
0x14000c0c9  mov     ebx, eax
0x14000c0cb  test    eax, eax
0x14000c0cd  jns     short loc_14000C0DF
0x14000c0cf  mov     eax, cs:dword_140019000
0x14000c0d5  cmp     eax, 3
0x14000c0d8  jbe     short loc_14000C136
0x14000c0da  mov     dword ptr [rbp+4Fh+var_90], ebx
0x14000c0dd  jmp     short loc_14000C08C
0x14000c0df  mov     r9, [rbp+4Fh+var_88]
0x14000c0e3  mov     r8, r13
0x14000c0e6  mov     rdx, rsi
0x14000c0e9  mov     rcx, rdi
0x14000c0ec  call    BfsUpdateGlobalFilePolicy
0x14000c0f1  mov     ebx, eax
0x14000c0f3  test    eax, eax
0x14000c0f5  jns     short loc_14000C130
0x14000c0f7  mov     eax, cs:dword_140019000
0x14000c0fd  cmp     eax, 3
0x14000c100  jbe     loc_14000C18A
0x14000c106  lea     rax, [rbp+4Fh+var_90]
0x14000c10a  mov     dword ptr [rbp+4Fh+var_90], ebx
0x14000c10d  mov     [rbp+4Fh+var_60], rax
0x14000c111  lea     rdx, byte_140016D91; int
0x14000c118  lea     rax, [rbp+4Fh+var_80]
0x14000c11c  mov     [rbp+4Fh+var_58], 4
0x14000c124  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000c129  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c12e  jmp     short loc_14000C18A
0x14000c130  cmp     r14d, 2
0x14000c134  jnz     short loc_14000C149
0x14000c136  xor     edx, edx
0x14000c138  mov     rcx, rdi
0x14000c13b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c142  nop     dword ptr [rax+rax+00h]
0x14000c147  jmp     short loc_14000C160
0x14000c149  cmp     r14d, 1
0x14000c14d  jnz     short loc_14000C16C
0x14000c14f  xor     edx, edx
0x14000c151  mov     rcx, rdi
0x14000c154  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c15b  nop     dword ptr [rax+rax+00h]
0x14000c160  call    cs:__imp_KeLeaveCriticalRegion
0x14000c167  nop     dword ptr [rax+rax+00h]
0x14000c16c  xor     edx, edx
0x14000c16e  lea     rcx, [rdi+8]
0x14000c172  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c179  nop     dword ptr [rax+rax+00h]
0x14000c17e  call    cs:__imp_KeLeaveCriticalRegion
0x14000c185  nop     dword ptr [rax+rax+00h]
0x14000c18a  mov     eax, ebx
0x14000c18c  mov     rcx, [rbp+4Fh+var_50]
0x14000c190  xor     rcx, rsp; StackCookie
0x14000c193  call    __security_check_cookie
0x14000c198  add     rsp, 88h
0x14000c19f  pop     r15
0x14000c1a1  pop     r14
0x14000c1a3  pop     r13
0x14000c1a5  pop     r12
0x14000c1a7  pop     rdi
0x14000c1a8  pop     rsi
0x14000c1a9  pop     rbx
0x14000c1aa  pop     rbp
0x14000c1ab  retn
```
