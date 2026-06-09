# BfsPolicyEntryExists

- ea: `0x140009014`
- end: `0x14000929b`
- name: `BfsPolicyEntryExists`
- size: `647`
- prototype: `bool __fastcall(__int64, __int64, __int64, void *, PSID Sid)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140005768`
- `0x140005edc`
- `0x1400096c0`
- `0x140009aec`

## callees

- `0x1400017b0`
- `0x140007a20`
- `0x140008e38`
- `0x140008ecc`
- `0x140009014`
- `0x140012d00`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009130`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009152`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009130`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009152`
- `ntoskrnl!RtlLengthSid` at `0x140009060`
- `ntoskrnl!RtlLengthSid` at `0x14000907e`
- `ntoskrnl!RtlLengthSid` at `0x140009060`
- `ntoskrnl!RtlLengthSid` at `0x14000907e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400090ba`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400090ba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400090ec`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140009109`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400090ec`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140009109`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400091fa`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400091fa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009260`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009270`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009260`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009270`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000920d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000920d`
- `ntoskrnl!ExAllocatePool2` at `0x1400091a9`
- `ntoskrnl!ExAllocatePool2` at `0x1400091a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400090a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400090a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400090f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009115`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400090f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009115`
- `FLTMGR!FltClose` at `0x140009228`
- `FLTMGR!FltClose` at `0x140009228`

## pseudocode

```c
bool __fastcall BfsPolicyEntryExists(__int64 a1, __int64 a2, __int64 a3, void *a4, PSID Sid)
{
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // rax
  bool v12; // bl
  __int64 v14; // r9
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
      if ( (int)BfsOpenPolicyDirectory(a1, a2, (__int64)&UnicodeString, v14, &FileHandle) < 0 )
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
0x140009014  mov     rax, rsp
0x140009017  mov     [rax+8], rbx
0x14000901b  mov     [rax+10h], rsi
0x14000901f  mov     [rax+20h], r9
0x140009023  push    rbp
0x140009024  push    rdi
0x140009025  push    r12
0x140009027  push    r14
0x140009029  push    r15
0x14000902b  lea     rbp, [rax-57h]
0x14000902f  sub     rsp, 0A0h
0x140009036  xorps   xmm0, xmm0
0x140009039  mov     [rbp+4Fh+FileHandle], 0
0x140009041  mov     r15, rcx
0x140009044  mov     [rbp+4Fh+arg_10], 0
0x14000904c  mov     rcx, r9; Sid
0x14000904f  mov     rbx, r9
0x140009052  movups  xmmword ptr [rbp+4Fh+var_58.Length], xmm0
0x140009056  mov     rsi, r8
0x140009059  mov     r14, rdx
0x14000905c  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x140009060  call    cs:__imp_RtlLengthSid
0x140009067  nop     dword ptr [rax+rax+00h]
0x14000906c  lea     r8, [rbp+4Fh+arg_10]
0x140009070  mov     rcx, rbx
0x140009073  mov     edx, eax
0x140009075  call    BfsUpdateHash
0x14000907a  mov     rcx, [rbp+4Fh+Sid]; Sid
0x14000907e  call    cs:__imp_RtlLengthSid
0x140009085  nop     dword ptr [rax+rax+00h]
0x14000908a  mov     rcx, [rbp+4Fh+Sid]
0x14000908e  lea     r8, [rbp+4Fh+arg_10]
0x140009092  mov     edx, eax
0x140009094  call    BfsUpdateHash
0x140009099  lea     rcx, [rbp+4Fh+arg_10]
0x14000909d  call    BfsFinalHash
0x1400090a2  mov     rdi, rax
0x1400090a5  mov     [rbp+4Fh+arg_10], rax
0x1400090a9  call    cs:__imp_KeEnterCriticalRegion
0x1400090b0  nop     dword ptr [rax+rax+00h]
0x1400090b5  xor     edx, edx
0x1400090b7  mov     rcx, rsi
0x1400090ba  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400090c1  nop     dword ptr [rax+rax+00h]
0x1400090c6  mov     r9, [rbp+4Fh+Sid]
0x1400090ca  mov     r8, rbx
0x1400090cd  mov     rcx, [rsi+8]; HashTable
0x1400090d1  mov     rdx, rdi
0x1400090d4  call    BfsLookupPolicyEntryHashTable
0x1400090d9  xor     edx, edx
0x1400090db  mov     rcx, rsi
0x1400090de  test    rax, rax
0x1400090e1  jz      short loc_140009109
0x1400090e3  mov     ebx, [rax+38h]
0x1400090e6  shr     ebx, 1Ch
0x1400090e9  and     bl, 1
0x1400090ec  call    cs:__imp_ExReleasePushLockSharedEx
0x1400090f3  nop     dword ptr [rax+rax+00h]
0x1400090f8  call    cs:__imp_KeLeaveCriticalRegion
0x1400090ff  nop     dword ptr [rax+rax+00h]
0x140009104  jmp     loc_14000927C
0x140009109  call    cs:__imp_ExReleasePushLockSharedEx
0x140009110  nop     dword ptr [rax+rax+00h]
0x140009115  call    cs:__imp_KeLeaveCriticalRegion
0x14000911c  nop     dword ptr [rax+rax+00h]
0x140009121  mov     edi, 1
0x140009126  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x14000912a  mov     r8b, dil; AllocateDestinationString
0x14000912d  mov     rdx, rbx; Sid
0x140009130  call    cs:__imp_RtlConvertSidToUnicodeString
0x140009137  nop     dword ptr [rax+rax+00h]
0x14000913c  test    eax, eax
0x14000913e  jns     short loc_140009147
0x140009140  xor     al, al
0x140009142  jmp     loc_14000927E
0x140009147  mov     rdx, [rbp+4Fh+Sid]; Sid
0x14000914b  lea     rcx, [rbp+4Fh+var_58]; UnicodeString
0x14000914f  mov     r8b, dil; AllocateDestinationString
0x140009152  call    cs:__imp_RtlConvertSidToUnicodeString
0x140009159  nop     dword ptr [rax+rax+00h]
0x14000915e  xor     bl, bl
0x140009160  test    eax, eax
0x140009162  js      loc_14000926C
0x140009168  lea     rax, [rbp+4Fh+FileHandle]
0x14000916c  mov     r9b, dil
0x14000916f  lea     r8, [rbp+4Fh+UnicodeString]
0x140009173  mov     [rsp+0C0h+IoStatusBlock], rax
0x140009178  mov     rdx, r14
0x14000917b  mov     rcx, r15
0x14000917e  call    BfsOpenPolicyDirectory
0x140009183  test    eax, eax
0x140009185  js      loc_14000923D
0x14000918b  movzx   r12d, [rbp+4Fh+var_58.Length]
0x140009190  xorps   xmm0, xmm0
0x140009193  add     r12d, 10h
0x140009197  mov     ecx, 100h
0x14000919c  mov     edx, r12d
0x14000919f  mov     r8d, 4E736642h
0x1400091a5  movups  xmmword ptr [rbp+4Fh+var_38], xmm0
0x1400091a9  call    cs:__imp_ExAllocatePool2
0x1400091b0  nop     dword ptr [rax+rax+00h]
0x1400091b5  mov     r14, rax
0x1400091b8  test    rax, rax
0x1400091bb  jz      short loc_140009221
0x1400091bd  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400091c1  lea     rax, [rbp+4Fh+var_58]
0x1400091c5  mov     [rsp+0C0h+RestartScan], dil; RestartScan
0x1400091ca  xor     r9d, r9d; ApcContext
0x1400091cd  mov     [rsp+0C0h+FileName], rax; FileName
0x1400091d2  xor     r8d, r8d; ApcRoutine
0x1400091d5  mov     [rsp+0C0h+ReturnSingleEntry], dil; ReturnSingleEntry
0x1400091da  lea     rax, [rbp+4Fh+var_38]
0x1400091de  mov     [rsp+0C0h+FileInformationClass], 0Ch; FileInformationClass
0x1400091e6  xor     edx, edx; Event
0x1400091e8  mov     [rsp+0C0h+Length], r12d; Length
0x1400091ed  mov     r15b, dil
0x1400091f0  mov     [rsp+0C0h+FileInformation], r14; FileInformation
0x1400091f5  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x1400091fa  call    cs:__imp_ZwQueryDirectoryFile
0x140009201  nop     dword ptr [rax+rax+00h]
0x140009206  xor     edx, edx; Tag
0x140009208  mov     rcx, r14; P
0x14000920b  mov     ebx, eax
0x14000920d  call    cs:__imp_ExFreePoolWithTag
0x140009214  nop     dword ptr [rax+rax+00h]
0x140009219  shr     ebx, 1Fh
0x14000921c  xor     bl, dil
0x14000921f  jmp     short loc_140009224
0x140009221  xor     r15b, r15b
0x140009224  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140009228  call    cs:__imp_FltClose
0x14000922f  nop     dword ptr [rax+rax+00h]
0x140009234  test    bl, bl
0x140009236  jnz     short loc_14000925C
0x140009238  test    r15b, r15b
0x14000923b  jz      short loc_14000925C
0x14000923d  mov     r9, [rbp+4Fh+Sid]
0x140009241  mov     rcx, rsi
0x140009244  mov     r8, [rbp+4Fh+arg_18]
0x140009248  mov     rdx, [rbp+4Fh+arg_10]
0x14000924c  call    BfsInsertNotPresentPolicyEntry
0x140009251  cmp     eax, 40000000h
0x140009256  movzx   ebx, bl
0x140009259  cmovz   ebx, edi
0x14000925c  lea     rcx, [rbp+4Fh+var_58]; UnicodeString
0x140009260  call    cs:__imp_RtlFreeUnicodeString
0x140009267  nop     dword ptr [rax+rax+00h]
0x14000926c  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x140009270  call    cs:__imp_RtlFreeUnicodeString
0x140009277  nop     dword ptr [rax+rax+00h]
0x14000927c  mov     al, bl
0x14000927e  lea     r11, [rsp+0C0h+var_20]
0x140009286  mov     rbx, [r11+30h]
0x14000928a  mov     rsi, [r11+38h]
0x14000928e  mov     rsp, r11
0x140009291  pop     r15
0x140009293  pop     r14
0x140009295  pop     r12
0x140009297  pop     rdi
0x140009298  pop     rbp
0x140009299  retn
```
