# BfsPolicyEntryExists

- ea: `0x140008e84`
- end: `0x14000910b`
- name: `BfsPolicyEntryExists`
- size: `647`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400055d8`
- `0x140005d4c`
- `0x140009530`
- `0x14000995c`

## callees

- `0x140001bc0`
- `0x140007890`
- `0x140008ca8`
- `0x140008d3c`
- `0x140008e84`
- `0x140012bc8`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008fa0`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008fc2`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008fa0`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008fc2`
- `ntoskrnl!RtlLengthSid` at `0x140008ed0`
- `ntoskrnl!RtlLengthSid` at `0x140008eee`
- `ntoskrnl!RtlLengthSid` at `0x140008ed0`
- `ntoskrnl!RtlLengthSid` at `0x140008eee`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140008f2a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140008f2a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140008f5c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140008f79`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140008f5c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140008f79`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000906a`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000906a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400090d0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400090e0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400090d0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400090e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000907d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000907d`
- `ntoskrnl!ExAllocatePool2` at `0x140009019`
- `ntoskrnl!ExAllocatePool2` at `0x140009019`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008f19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008f19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008f68`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008f85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008f68`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008f85`
- `FLTMGR!FltClose` at `0x140009098`
- `FLTMGR!FltClose` at `0x140009098`

## pseudocode

```c
bool __fastcall BfsPolicyEntryExists(int a1, int a2, __int64 a3, void *a4, PSID Sid)
{
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // rax
  bool v12; // bl
  int v14; // r9d
  ULONG Length; // r12d
  void *FileInformation; // r14
  char v17; // r15
  NTSTATUS v18; // ebx
  HANDLE FileHandle; // [rsp+68h] [rbp-11h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+70h] [rbp-9h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp+17h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+6Fh] BYREF
  void *v24; // [rsp+F0h] [rbp+77h]

  v24 = a4;
  FileHandle = 0;
  v23 = 0;
  FileName = 0;
  UnicodeString = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v23);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v23);
  v23 = BfsFinalHash(&v23);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a3, 0);
  v11 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  if ( v11 )
  {
    v12 = (*(_DWORD *)(v11 + 56) & 0x10000000) != 0;
    ExReleasePushLockSharedEx(a3, 0);
    KeLeaveCriticalRegion();
  }
  else
  {
    ExReleasePushLockSharedEx(a3, 0);
    KeLeaveCriticalRegion();
    if ( RtlConvertSidToUnicodeString(&UnicodeString, a4, 1u) < 0 )
      return 0;
    v12 = 0;
    if ( RtlConvertSidToUnicodeString(&FileName, Sid, 1u) >= 0 )
    {
      LOBYTE(v14) = 1;
      if ( (int)BfsOpenPolicyDirectory(a1, a2, (unsigned int)&UnicodeString, v14, (__int64)&FileHandle) < 0 )
        goto LABEL_12;
      Length = FileName.Length + 16;
      IoStatusBlock = 0;
      FileInformation = (void *)ExAllocatePool2(256, Length, 1316185666);
      if ( FileInformation )
      {
        v17 = 1;
        v18 = ZwQueryDirectoryFile(
                FileHandle,
                0,
                0,
                0,
                &IoStatusBlock,
                FileInformation,
                Length,
                FileNamesInformation,
                1u,
                &FileName,
                1u);
        ExFreePoolWithTag(FileInformation, 0);
        v12 = v18 >= 0;
      }
      else
      {
        v17 = 0;
      }
      FltClose(FileHandle);
      if ( !v12 )
      {
        if ( v17 )
        {
LABEL_12:
          if ( (unsigned int)BfsInsertNotPresentPolicyEntry(a3, v23, v24, Sid) == 0x40000000 )
            v12 = 1;
        }
      }
      RtlFreeUnicodeString(&FileName);
    }
    RtlFreeUnicodeString(&UnicodeString);
  }
  return v12;
}

```

## disassembly

```asm
0x140008e84  mov     rax, rsp
0x140008e87  mov     [rax+8], rbx
0x140008e8b  mov     [rax+10h], rsi
0x140008e8f  mov     [rax+20h], r9
0x140008e93  push    rbp
0x140008e94  push    rdi
0x140008e95  push    r12
0x140008e97  push    r14
0x140008e99  push    r15
0x140008e9b  lea     rbp, [rax-57h]
0x140008e9f  sub     rsp, 0A0h
0x140008ea6  xorps   xmm0, xmm0
0x140008ea9  mov     [rbp+4Fh+FileHandle], 0
0x140008eb1  mov     r15, rcx
0x140008eb4  mov     [rbp+4Fh+arg_10], 0
0x140008ebc  mov     rcx, r9; Sid
0x140008ebf  mov     rbx, r9
0x140008ec2  movups  xmmword ptr [rbp+4Fh+var_58.Length], xmm0
0x140008ec6  mov     rsi, r8
0x140008ec9  mov     r14, rdx
0x140008ecc  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x140008ed0  call    cs:__imp_RtlLengthSid
0x140008ed7  nop     dword ptr [rax+rax+00h]
0x140008edc  lea     r8, [rbp+4Fh+arg_10]
0x140008ee0  mov     rcx, rbx
0x140008ee3  mov     edx, eax
0x140008ee5  call    BfsUpdateHash
0x140008eea  mov     rcx, [rbp+4Fh+Sid]; Sid
0x140008eee  call    cs:__imp_RtlLengthSid
0x140008ef5  nop     dword ptr [rax+rax+00h]
0x140008efa  mov     rcx, [rbp+4Fh+Sid]
0x140008efe  lea     r8, [rbp+4Fh+arg_10]
0x140008f02  mov     edx, eax
0x140008f04  call    BfsUpdateHash
0x140008f09  lea     rcx, [rbp+4Fh+arg_10]
0x140008f0d  call    BfsFinalHash
0x140008f12  mov     rdi, rax
0x140008f15  mov     [rbp+4Fh+arg_10], rax
0x140008f19  call    cs:__imp_KeEnterCriticalRegion
0x140008f20  nop     dword ptr [rax+rax+00h]
0x140008f25  xor     edx, edx
0x140008f27  mov     rcx, rsi
0x140008f2a  call    cs:__imp_ExAcquirePushLockSharedEx
0x140008f31  nop     dword ptr [rax+rax+00h]
0x140008f36  mov     r9, [rbp+4Fh+Sid]
0x140008f3a  mov     r8, rbx
0x140008f3d  mov     rcx, [rsi+8]; HashTable
0x140008f41  mov     rdx, rdi
0x140008f44  call    BfsLookupPolicyEntryHashTable
0x140008f49  xor     edx, edx
0x140008f4b  mov     rcx, rsi
0x140008f4e  test    rax, rax
0x140008f51  jz      short loc_140008F79
0x140008f53  mov     ebx, [rax+38h]
0x140008f56  shr     ebx, 1Ch
0x140008f59  and     bl, 1
0x140008f5c  call    cs:__imp_ExReleasePushLockSharedEx
0x140008f63  nop     dword ptr [rax+rax+00h]
0x140008f68  call    cs:__imp_KeLeaveCriticalRegion
0x140008f6f  nop     dword ptr [rax+rax+00h]
0x140008f74  jmp     loc_1400090EC
0x140008f79  call    cs:__imp_ExReleasePushLockSharedEx
0x140008f80  nop     dword ptr [rax+rax+00h]
0x140008f85  call    cs:__imp_KeLeaveCriticalRegion
0x140008f8c  nop     dword ptr [rax+rax+00h]
0x140008f91  mov     edi, 1
0x140008f96  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x140008f9a  mov     r8b, dil; AllocateDestinationString
0x140008f9d  mov     rdx, rbx; Sid
0x140008fa0  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008fa7  nop     dword ptr [rax+rax+00h]
0x140008fac  test    eax, eax
0x140008fae  jns     short loc_140008FB7
0x140008fb0  xor     al, al
0x140008fb2  jmp     loc_1400090EE
0x140008fb7  mov     rdx, [rbp+4Fh+Sid]; Sid
0x140008fbb  lea     rcx, [rbp+4Fh+var_58]; UnicodeString
0x140008fbf  mov     r8b, dil; AllocateDestinationString
0x140008fc2  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008fc9  nop     dword ptr [rax+rax+00h]
0x140008fce  xor     bl, bl
0x140008fd0  test    eax, eax
0x140008fd2  js      loc_1400090DC
0x140008fd8  lea     rax, [rbp+4Fh+FileHandle]
0x140008fdc  mov     r9b, dil
0x140008fdf  lea     r8, [rbp+4Fh+UnicodeString]
0x140008fe3  mov     [rsp+0C0h+IoStatusBlock], rax
0x140008fe8  mov     rdx, r14
0x140008feb  mov     rcx, r15
0x140008fee  call    BfsOpenPolicyDirectory
0x140008ff3  test    eax, eax
0x140008ff5  js      loc_1400090AD
0x140008ffb  movzx   r12d, [rbp+4Fh+var_58.Length]
0x140009000  xorps   xmm0, xmm0
0x140009003  add     r12d, 10h
0x140009007  mov     ecx, 100h
0x14000900c  mov     edx, r12d
0x14000900f  mov     r8d, 4E736642h
0x140009015  movups  xmmword ptr [rbp+4Fh+var_38], xmm0
0x140009019  call    cs:__imp_ExAllocatePool2
0x140009020  nop     dword ptr [rax+rax+00h]
0x140009025  mov     r14, rax
0x140009028  test    rax, rax
0x14000902b  jz      short loc_140009091
0x14000902d  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140009031  lea     rax, [rbp+4Fh+var_58]
0x140009035  mov     [rsp+0C0h+RestartScan], dil; RestartScan
0x14000903a  xor     r9d, r9d; ApcContext
0x14000903d  mov     [rsp+0C0h+FileName], rax; FileName
0x140009042  xor     r8d, r8d; ApcRoutine
0x140009045  mov     [rsp+0C0h+ReturnSingleEntry], dil; ReturnSingleEntry
0x14000904a  lea     rax, [rbp+4Fh+var_38]
0x14000904e  mov     [rsp+0C0h+FileInformationClass], 0Ch; FileInformationClass
0x140009056  xor     edx, edx; Event
0x140009058  mov     [rsp+0C0h+Length], r12d; Length
0x14000905d  mov     r15b, dil
0x140009060  mov     [rsp+0C0h+FileInformation], r14; FileInformation
0x140009065  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14000906a  call    cs:__imp_ZwQueryDirectoryFile
0x140009071  nop     dword ptr [rax+rax+00h]
0x140009076  xor     edx, edx; Tag
0x140009078  mov     rcx, r14; P
0x14000907b  mov     ebx, eax
0x14000907d  call    cs:__imp_ExFreePoolWithTag
0x140009084  nop     dword ptr [rax+rax+00h]
0x140009089  shr     ebx, 1Fh
0x14000908c  xor     bl, dil
0x14000908f  jmp     short loc_140009094
0x140009091  xor     r15b, r15b
0x140009094  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140009098  call    cs:__imp_FltClose
0x14000909f  nop     dword ptr [rax+rax+00h]
0x1400090a4  test    bl, bl
0x1400090a6  jnz     short loc_1400090CC
0x1400090a8  test    r15b, r15b
0x1400090ab  jz      short loc_1400090CC
0x1400090ad  mov     r9, [rbp+4Fh+Sid]
0x1400090b1  mov     rcx, rsi
0x1400090b4  mov     r8, [rbp+4Fh+arg_18]
0x1400090b8  mov     rdx, [rbp+4Fh+arg_10]
0x1400090bc  call    BfsInsertNotPresentPolicyEntry
0x1400090c1  cmp     eax, 40000000h
0x1400090c6  movzx   ebx, bl
0x1400090c9  cmovz   ebx, edi
0x1400090cc  lea     rcx, [rbp+4Fh+var_58]; UnicodeString
0x1400090d0  call    cs:__imp_RtlFreeUnicodeString
0x1400090d7  nop     dword ptr [rax+rax+00h]
0x1400090dc  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x1400090e0  call    cs:__imp_RtlFreeUnicodeString
0x1400090e7  nop     dword ptr [rax+rax+00h]
0x1400090ec  mov     al, bl
0x1400090ee  lea     r11, [rsp+0C0h+var_20]
0x1400090f6  mov     rbx, [r11+30h]
0x1400090fa  mov     rsi, [r11+38h]
0x1400090fe  mov     rsp, r11
0x140009101  pop     r15
0x140009103  pop     r14
0x140009105  pop     r12
0x140009107  pop     rdi
0x140009108  pop     rbp
0x140009109  retn
```
