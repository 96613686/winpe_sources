# BfsPolicyEntryExistsLocked

- ea: `0x140009114`
- end: `0x140009389`
- name: `BfsPolicyEntryExistsLocked`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ebf4`

## callees

- `0x140001bc0`
- `0x140007b60`
- `0x140008ca8`
- `0x140008d3c`
- `0x140009114`
- `0x140012bc8`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400091e8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009207`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400091e8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009207`
- `ntoskrnl!RtlLengthSid` at `0x14000915d`
- `ntoskrnl!RtlLengthSid` at `0x14000917b`
- `ntoskrnl!RtlLengthSid` at `0x14000915d`
- `ntoskrnl!RtlLengthSid` at `0x14000917b`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400092c3`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400092c3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000921d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009345`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009355`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000921d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009345`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140009355`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092d6`
- `ntoskrnl!ExAllocatePool2` at `0x140009272`
- `ntoskrnl!ExAllocatePool2` at `0x140009272`
- `FLTMGR!FltClose` at `0x1400092fd`
- `FLTMGR!FltClose` at `0x1400092fd`

## pseudocode

```c
NTSTATUS __fastcall BfsPolicyEntryExistsLocked(int a1, __int64 a2, __int64 a3, void *a4, PSID Sid, int a6)
{
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rax
  NTSTATUS result; // eax
  NTSTATUS v16; // ebx
  int v17; // r9d
  bool v18; // bl
  ULONG Length; // r14d
  void *FileInformation; // rsi
  char v21; // di
  NTSTATUS v22; // ebx
  struct _UNICODE_STRING FileName; // [rsp+68h] [rbp-9h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+17h] BYREF
  __int64 v26; // [rsp+D0h] [rbp+5Fh] BYREF
  HANDLE FileHandle; // [rsp+D8h] [rbp+67h] BYREF

  FileHandle = 0;
  v26 = 0;
  FileName = 0;
  UnicodeString = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v26);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v26);
  v11 = BfsFinalHash(&v26);
  v12 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a3 + 8);
  v13 = v11;
  v26 = v11;
  v14 = BfsLookupPolicyEntryHashTable(v12);
  if ( !v14 )
  {
    result = RtlConvertSidToUnicodeString(&UnicodeString, a4, 1u);
    if ( result < 0 )
      return result;
    v16 = RtlConvertSidToUnicodeString(&FileName, Sid, 1u);
    if ( v16 < 0 )
    {
      RtlFreeUnicodeString(&UnicodeString);
      return v16;
    }
    LOBYTE(v17) = 1;
    v18 = 0;
    if ( (int)BfsOpenPolicyDirectory(a1, 0, (unsigned int)&UnicodeString, v17, (__int64)&FileHandle) >= 0 )
    {
      Length = FileName.Length + 16;
      IoStatusBlock = 0;
      FileInformation = (void *)ExAllocatePool2(256, Length, 1316185666);
      if ( FileInformation )
      {
        v21 = 1;
        v22 = ZwQueryDirectoryFile(
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
        v18 = v22 >= 0;
      }
      else
      {
        v21 = 0;
      }
      FltClose(FileHandle);
      if ( v18 || !v21 )
      {
LABEL_19:
        RtlFreeUnicodeString(&FileName);
        RtlFreeUnicodeString(&UnicodeString);
        return !v18 ? 0xC0000225 : 0;
      }
      v13 = v26;
    }
    if ( a6 == 1 )
      return -1073741267;
    if ( (unsigned int)BfsInsertNotPresentPolicyEntryLocked(a3, v13, a4, Sid) == 0x40000000 )
      v18 = 1;
    goto LABEL_19;
  }
  if ( (*(_DWORD *)(v14 + 56) & 0x10000000) != 0 )
    return 0;
  else
    return -1073741275;
}

```

## disassembly

```asm
0x140009114  mov     rax, rsp
0x140009117  mov     [rax+8], rbx
0x14000911b  mov     [rax+20h], rsi
0x14000911f  mov     [rax+10h], rdx
0x140009123  push    rbp
0x140009124  push    rdi
0x140009125  push    r13
0x140009127  push    r14
0x140009129  push    r15
0x14000912b  lea     rbp, [rax-4Fh]
0x14000912f  sub     rsp, 90h
0x140009136  xorps   xmm0, xmm0
0x140009139  mov     [rbp+47h+FileHandle], 0
0x140009141  mov     rdi, rcx
0x140009144  mov     [rbp+47h+arg_8], 0
0x14000914c  mov     rcx, r9; Sid
0x14000914f  mov     r15, r9
0x140009152  movups  xmmword ptr [rbp+47h+var_50.Length], xmm0
0x140009156  mov     r13, r8
0x140009159  movups  xmmword ptr [rbp+47h+UnicodeString.Length], xmm0
0x14000915d  call    cs:__imp_RtlLengthSid
0x140009164  nop     dword ptr [rax+rax+00h]
0x140009169  lea     r8, [rbp+47h+arg_8]
0x14000916d  mov     rcx, r15
0x140009170  mov     edx, eax
0x140009172  call    BfsUpdateHash
0x140009177  mov     rcx, [rbp+47h+Sid]; Sid
0x14000917b  call    cs:__imp_RtlLengthSid
0x140009182  nop     dword ptr [rax+rax+00h]
0x140009187  mov     rcx, [rbp+47h+Sid]
0x14000918b  lea     r8, [rbp+47h+arg_8]
0x14000918f  mov     edx, eax
0x140009191  call    BfsUpdateHash
0x140009196  lea     rcx, [rbp+47h+arg_8]
0x14000919a  call    BfsFinalHash
0x14000919f  mov     r9, [rbp+47h+Sid]
0x1400091a3  mov     rdx, rax
0x1400091a6  mov     rcx, [r13+8]; HashTable
0x1400091aa  mov     r8, r15
0x1400091ad  mov     rsi, rax
0x1400091b0  mov     [rbp+47h+arg_8], rax
0x1400091b4  call    BfsLookupPolicyEntryHashTable
0x1400091b9  test    rax, rax
0x1400091bc  jz      short loc_1400091D8
0x1400091be  test    dword ptr [rax+38h], 10000000h
0x1400091c5  jnz     short loc_1400091D1
0x1400091c7  mov     eax, 0C0000225h
0x1400091cc  jmp     loc_14000936C
0x1400091d1  xor     eax, eax
0x1400091d3  jmp     loc_14000936C
0x1400091d8  mov     r14d, 1
0x1400091de  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x1400091e2  mov     r8b, r14b; AllocateDestinationString
0x1400091e5  mov     rdx, r15; Sid
0x1400091e8  call    cs:__imp_RtlConvertSidToUnicodeString
0x1400091ef  nop     dword ptr [rax+rax+00h]
0x1400091f4  test    eax, eax
0x1400091f6  js      loc_14000936C
0x1400091fc  mov     rdx, [rbp+47h+Sid]; Sid
0x140009200  lea     rcx, [rbp+47h+var_50]; UnicodeString
0x140009204  mov     r8b, r14b; AllocateDestinationString
0x140009207  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000920e  nop     dword ptr [rax+rax+00h]
0x140009213  mov     ebx, eax
0x140009215  test    eax, eax
0x140009217  jns     short loc_140009230
0x140009219  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x14000921d  call    cs:__imp_RtlFreeUnicodeString
0x140009224  nop     dword ptr [rax+rax+00h]
0x140009229  mov     eax, ebx
0x14000922b  jmp     loc_14000936C
0x140009230  lea     rax, [rbp+47h+FileHandle]
0x140009234  mov     r9b, r14b
0x140009237  lea     r8, [rbp+47h+UnicodeString]
0x14000923b  mov     [rsp+0B0h+IoStatusBlock], rax
0x140009240  xor     edx, edx
0x140009242  mov     rcx, rdi
0x140009245  xor     bl, bl
0x140009247  call    BfsOpenPolicyDirectory
0x14000924c  test    eax, eax
0x14000924e  js      loc_140009316
0x140009254  movzx   r14d, [rbp+47h+var_50.Length]
0x140009259  xorps   xmm0, xmm0
0x14000925c  add     r14d, 10h
0x140009260  mov     ecx, 100h
0x140009265  mov     edx, r14d
0x140009268  mov     r8d, 4E736642h
0x14000926e  movups  xmmword ptr [rbp+47h+var_30], xmm0
0x140009272  call    cs:__imp_ExAllocatePool2
0x140009279  nop     dword ptr [rax+rax+00h]
0x14000927e  mov     rsi, rax
0x140009281  test    rax, rax
0x140009284  jz      short loc_1400092F0
0x140009286  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x14000928a  lea     rax, [rbp+47h+var_50]
0x14000928e  mov     dil, 1
0x140009291  xor     r9d, r9d; ApcContext
0x140009294  mov     [rsp+0B0h+RestartScan], dil; RestartScan
0x140009299  xor     r8d, r8d; ApcRoutine
0x14000929c  mov     [rsp+0B0h+FileName], rax; FileName
0x1400092a1  xor     edx, edx; Event
0x1400092a3  mov     [rsp+0B0h+ReturnSingleEntry], dil; ReturnSingleEntry
0x1400092a8  lea     rax, [rbp+47h+var_30]
0x1400092ac  mov     [rsp+0B0h+FileInformationClass], 0Ch; FileInformationClass
0x1400092b4  mov     [rsp+0B0h+Length], r14d; Length
0x1400092b9  mov     [rsp+0B0h+FileInformation], rsi; FileInformation
0x1400092be  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x1400092c3  call    cs:__imp_ZwQueryDirectoryFile
0x1400092ca  nop     dword ptr [rax+rax+00h]
0x1400092cf  xor     edx, edx; Tag
0x1400092d1  mov     rcx, rsi; P
0x1400092d4  mov     ebx, eax
0x1400092d6  call    cs:__imp_ExFreePoolWithTag
0x1400092dd  nop     dword ptr [rax+rax+00h]
0x1400092e2  shr     ebx, 1Fh
0x1400092e5  mov     r14d, 1
0x1400092eb  xor     bl, r14b
0x1400092ee  jmp     short loc_1400092F9
0x1400092f0  xor     dil, dil
0x1400092f3  mov     r14d, 1
0x1400092f9  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x1400092fd  call    cs:__imp_FltClose
0x140009304  nop     dword ptr [rax+rax+00h]
0x140009309  test    bl, bl
0x14000930b  jnz     short loc_140009341
0x14000930d  test    dil, dil
0x140009310  jz      short loc_140009341
0x140009312  mov     rsi, [rbp+47h+arg_8]
0x140009316  cmp     [rbp+47h+arg_28], r14d
0x14000931a  jnz     short loc_140009323
0x14000931c  mov     eax, 0C000022Dh
0x140009321  jmp     short loc_14000936C
0x140009323  mov     r9, [rbp+47h+Sid]
0x140009327  mov     r8, r15
0x14000932a  mov     rdx, rsi
0x14000932d  mov     rcx, r13
0x140009330  call    BfsInsertNotPresentPolicyEntryLocked
0x140009335  cmp     eax, 40000000h
0x14000933a  movzx   ebx, bl
0x14000933d  cmovz   ebx, r14d
0x140009341  lea     rcx, [rbp+47h+var_50]; UnicodeString
0x140009345  call    cs:__imp_RtlFreeUnicodeString
0x14000934c  nop     dword ptr [rax+rax+00h]
0x140009351  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x140009355  call    cs:__imp_RtlFreeUnicodeString
0x14000935c  nop     dword ptr [rax+rax+00h]
0x140009361  neg     bl
0x140009363  sbb     eax, eax
0x140009365  not     eax
0x140009367  and     eax, 0C0000225h
0x14000936c  lea     r11, [rsp+0B0h+var_20]
0x140009374  mov     rbx, [r11+30h]
0x140009378  mov     rsi, [r11+48h]
0x14000937c  mov     rsp, r11
0x14000937f  pop     r15
0x140009381  pop     r14
0x140009383  pop     r13
0x140009385  pop     rdi
0x140009386  pop     rbp
0x140009387  retn
```
