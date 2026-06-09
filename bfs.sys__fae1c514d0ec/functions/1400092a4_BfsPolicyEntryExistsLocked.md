# BfsPolicyEntryExistsLocked

- ea: `0x1400092a4`
- end: `0x140009519`
- name: `BfsPolicyEntryExistsLocked`
- size: `629`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64, void *, PSID Sid, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ed84`

## callees

- `0x1400017b0`
- `0x140007cf0`
- `0x140008e38`
- `0x140008ecc`
- `0x1400092a4`
- `0x140012d00`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009378`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009397`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009378`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140009397`
- `ntoskrnl!RtlLengthSid` at `0x1400092ed`
- `ntoskrnl!RtlLengthSid` at `0x14000930b`
- `ntoskrnl!RtlLengthSid` at `0x1400092ed`
- `ntoskrnl!RtlLengthSid` at `0x14000930b`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140009453`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140009453`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400093ad`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400094d5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400094e5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400093ad`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400094d5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400094e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009466`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009466`
- `ntoskrnl!ExAllocatePool2` at `0x140009402`
- `ntoskrnl!ExAllocatePool2` at `0x140009402`
- `FLTMGR!FltClose` at `0x14000948d`
- `FLTMGR!FltClose` at `0x14000948d`

## pseudocode

```c
NTSTATUS __fastcall BfsPolicyEntryExistsLocked(__int64 a1, __int64 a2, __int64 a3, void *a4, PSID Sid, int a6)
{
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rax
  NTSTATUS result; // eax
  NTSTATUS v16; // ebx
  __int64 v17; // r9
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
    if ( (int)BfsOpenPolicyDirectory(a1, 0, (__int64)&UnicodeString, v17, &FileHandle) >= 0 )
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
0x1400092a4  mov     rax, rsp
0x1400092a7  mov     [rax+8], rbx
0x1400092ab  mov     [rax+20h], rsi
0x1400092af  mov     [rax+10h], rdx
0x1400092b3  push    rbp
0x1400092b4  push    rdi
0x1400092b5  push    r13
0x1400092b7  push    r14
0x1400092b9  push    r15
0x1400092bb  lea     rbp, [rax-4Fh]
0x1400092bf  sub     rsp, 90h
0x1400092c6  xorps   xmm0, xmm0
0x1400092c9  mov     [rbp+47h+FileHandle], 0
0x1400092d1  mov     rdi, rcx
0x1400092d4  mov     [rbp+47h+arg_8], 0
0x1400092dc  mov     rcx, r9; Sid
0x1400092df  mov     r15, r9
0x1400092e2  movups  xmmword ptr [rbp+47h+var_50.Length], xmm0
0x1400092e6  mov     r13, r8
0x1400092e9  movups  xmmword ptr [rbp+47h+UnicodeString.Length], xmm0
0x1400092ed  call    cs:__imp_RtlLengthSid
0x1400092f4  nop     dword ptr [rax+rax+00h]
0x1400092f9  lea     r8, [rbp+47h+arg_8]
0x1400092fd  mov     rcx, r15
0x140009300  mov     edx, eax
0x140009302  call    BfsUpdateHash
0x140009307  mov     rcx, [rbp+47h+Sid]; Sid
0x14000930b  call    cs:__imp_RtlLengthSid
0x140009312  nop     dword ptr [rax+rax+00h]
0x140009317  mov     rcx, [rbp+47h+Sid]
0x14000931b  lea     r8, [rbp+47h+arg_8]
0x14000931f  mov     edx, eax
0x140009321  call    BfsUpdateHash
0x140009326  lea     rcx, [rbp+47h+arg_8]
0x14000932a  call    BfsFinalHash
0x14000932f  mov     r9, [rbp+47h+Sid]
0x140009333  mov     rdx, rax
0x140009336  mov     rcx, [r13+8]; HashTable
0x14000933a  mov     r8, r15
0x14000933d  mov     rsi, rax
0x140009340  mov     [rbp+47h+arg_8], rax
0x140009344  call    BfsLookupPolicyEntryHashTable
0x140009349  test    rax, rax
0x14000934c  jz      short loc_140009368
0x14000934e  test    dword ptr [rax+38h], 10000000h
0x140009355  jnz     short loc_140009361
0x140009357  mov     eax, 0C0000225h
0x14000935c  jmp     loc_1400094FC
0x140009361  xor     eax, eax
0x140009363  jmp     loc_1400094FC
0x140009368  mov     r14d, 1
0x14000936e  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x140009372  mov     r8b, r14b; AllocateDestinationString
0x140009375  mov     rdx, r15; Sid
0x140009378  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000937f  nop     dword ptr [rax+rax+00h]
0x140009384  test    eax, eax
0x140009386  js      loc_1400094FC
0x14000938c  mov     rdx, [rbp+47h+Sid]; Sid
0x140009390  lea     rcx, [rbp+47h+var_50]; UnicodeString
0x140009394  mov     r8b, r14b; AllocateDestinationString
0x140009397  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000939e  nop     dword ptr [rax+rax+00h]
0x1400093a3  mov     ebx, eax
0x1400093a5  test    eax, eax
0x1400093a7  jns     short loc_1400093C0
0x1400093a9  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x1400093ad  call    cs:__imp_RtlFreeUnicodeString
0x1400093b4  nop     dword ptr [rax+rax+00h]
0x1400093b9  mov     eax, ebx
0x1400093bb  jmp     loc_1400094FC
0x1400093c0  lea     rax, [rbp+47h+FileHandle]
0x1400093c4  mov     r9b, r14b
0x1400093c7  lea     r8, [rbp+47h+UnicodeString]
0x1400093cb  mov     [rsp+0B0h+IoStatusBlock], rax
0x1400093d0  xor     edx, edx
0x1400093d2  mov     rcx, rdi
0x1400093d5  xor     bl, bl
0x1400093d7  call    BfsOpenPolicyDirectory
0x1400093dc  test    eax, eax
0x1400093de  js      loc_1400094A6
0x1400093e4  movzx   r14d, [rbp+47h+var_50.Length]
0x1400093e9  xorps   xmm0, xmm0
0x1400093ec  add     r14d, 10h
0x1400093f0  mov     ecx, 100h
0x1400093f5  mov     edx, r14d
0x1400093f8  mov     r8d, 4E736642h
0x1400093fe  movups  xmmword ptr [rbp+47h+var_30], xmm0
0x140009402  call    cs:__imp_ExAllocatePool2
0x140009409  nop     dword ptr [rax+rax+00h]
0x14000940e  mov     rsi, rax
0x140009411  test    rax, rax
0x140009414  jz      short loc_140009480
0x140009416  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x14000941a  lea     rax, [rbp+47h+var_50]
0x14000941e  mov     dil, 1
0x140009421  xor     r9d, r9d; ApcContext
0x140009424  mov     [rsp+0B0h+RestartScan], dil; RestartScan
0x140009429  xor     r8d, r8d; ApcRoutine
0x14000942c  mov     [rsp+0B0h+FileName], rax; FileName
0x140009431  xor     edx, edx; Event
0x140009433  mov     [rsp+0B0h+ReturnSingleEntry], dil; ReturnSingleEntry
0x140009438  lea     rax, [rbp+47h+var_30]
0x14000943c  mov     [rsp+0B0h+FileInformationClass], 0Ch; FileInformationClass
0x140009444  mov     [rsp+0B0h+Length], r14d; Length
0x140009449  mov     [rsp+0B0h+FileInformation], rsi; FileInformation
0x14000944e  mov     [rsp+0B0h+IoStatusBlock], rax; IoStatusBlock
0x140009453  call    cs:__imp_ZwQueryDirectoryFile
0x14000945a  nop     dword ptr [rax+rax+00h]
0x14000945f  xor     edx, edx; Tag
0x140009461  mov     rcx, rsi; P
0x140009464  mov     ebx, eax
0x140009466  call    cs:__imp_ExFreePoolWithTag
0x14000946d  nop     dword ptr [rax+rax+00h]
0x140009472  shr     ebx, 1Fh
0x140009475  mov     r14d, 1
0x14000947b  xor     bl, r14b
0x14000947e  jmp     short loc_140009489
0x140009480  xor     dil, dil
0x140009483  mov     r14d, 1
0x140009489  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x14000948d  call    cs:__imp_FltClose
0x140009494  nop     dword ptr [rax+rax+00h]
0x140009499  test    bl, bl
0x14000949b  jnz     short loc_1400094D1
0x14000949d  test    dil, dil
0x1400094a0  jz      short loc_1400094D1
0x1400094a2  mov     rsi, [rbp+47h+arg_8]
0x1400094a6  cmp     [rbp+47h+arg_28], r14d
0x1400094aa  jnz     short loc_1400094B3
0x1400094ac  mov     eax, 0C000022Dh
0x1400094b1  jmp     short loc_1400094FC
0x1400094b3  mov     r9, [rbp+47h+Sid]
0x1400094b7  mov     r8, r15
0x1400094ba  mov     rdx, rsi
0x1400094bd  mov     rcx, r13
0x1400094c0  call    BfsInsertNotPresentPolicyEntryLocked
0x1400094c5  cmp     eax, 40000000h
0x1400094ca  movzx   ebx, bl
0x1400094cd  cmovz   ebx, r14d
0x1400094d1  lea     rcx, [rbp+47h+var_50]; UnicodeString
0x1400094d5  call    cs:__imp_RtlFreeUnicodeString
0x1400094dc  nop     dword ptr [rax+rax+00h]
0x1400094e1  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x1400094e5  call    cs:__imp_RtlFreeUnicodeString
0x1400094ec  nop     dword ptr [rax+rax+00h]
0x1400094f1  neg     bl
0x1400094f3  sbb     eax, eax
0x1400094f5  not     eax
0x1400094f7  and     eax, 0C0000225h
0x1400094fc  lea     r11, [rsp+0B0h+var_20]
0x140009504  mov     rbx, [r11+30h]
0x140009508  mov     rsi, [r11+48h]
0x14000950c  mov     rsp, r11
0x14000950f  pop     r15
0x140009511  pop     r14
0x140009513  pop     r13
0x140009515  pop     rdi
0x140009516  pop     rbp
0x140009517  retn
```
