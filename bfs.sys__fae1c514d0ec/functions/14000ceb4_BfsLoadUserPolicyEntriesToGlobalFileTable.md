# BfsLoadUserPolicyEntriesToGlobalFileTable

- ea: `0x14000ceb4`
- end: `0x14000d2cc`
- name: `BfsLoadUserPolicyEntriesToGlobalFileTable`
- size: `1048`
- prototype: `__int64 __fastcall(struct _FLT_FILTER *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000cb34`

## callees

- `0x140001008`
- `0x140006330`
- `0x140008ecc`
- `0x14000c0f4`
- `0x14000ceb4`
- `0x1400107ec`
- `0x140010cc8`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000d199`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000d199`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000cf60`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000d067`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000cf60`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000d067`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cf4c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d053`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cf4c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d053`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d111`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000d111`
- `ntoskrnl!ZwClose` at `0x14000d1dd`
- `ntoskrnl!ZwClose` at `0x14000d1dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d122`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d147`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d202`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d219`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d122`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d147`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d202`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d219`
- `ntoskrnl!ExAllocatePool2` at `0x14000cfe2`
- `ntoskrnl!ExAllocatePool2` at `0x14000cfe2`

## pseudocode

```c
__int64 __fastcall BfsLoadUserPolicyEntriesToGlobalFileTable(
        struct _FLT_FILTER *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r9
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  int v11; // ebx
  int v12; // ecx
  __int64 FileInformation; // rsi
  NTSTATUS i; // eax
  unsigned int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  struct _UNICODE_STRING *v19; // rdi
  __int64 v20; // rax
  PVOID v21; // rcx
  __int64 v22; // rax
  int IoStatusBlock; // [rsp+20h] [rbp-E0h]
  int IoStatusBlocka; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-98h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID v29; // [rsp+80h] [rbp-80h] BYREF
  PVOID v30; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v31; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK v33; // [rsp+B0h] [rbp-50h] BYREF
  PVOID v34[20]; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+160h] [rbp+60h] BYREF
  int *v36; // [rsp+180h] [rbp+80h]
  __int64 v37; // [rsp+188h] [rbp+88h]

  v29 = 0;
  v33 = 0;
  DestinationString = 0;
  v31 = 0;
  memset(v34, 0, 0x98u);
  v26 = 0;
  P[1] = P;
  FileHandle = 0;
  P[0] = P;
  v30 = 0;
  RtlInitUnicodeString(&DestinationString, L"S-1-*");
  SeConvertStringSidToSid(*(_QWORD *)(a4 + 8), &v30);
  LOBYTE(v7) = 1;
  v8 = BfsOpenPolicyDirectory((__int64)a1, 0, a4, v7, &FileHandle);
  v11 = v8;
  if ( v8 < 0 )
  {
    v12 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_23;
    v26 = v8;
    goto LABEL_4;
  }
  FileInformation = ExAllocatePool2(256, 390, 1316185666);
  if ( !FileInformation )
  {
    v11 = -1073741801;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_23;
    v26 = -1073741801;
LABEL_4:
    v37 = 4;
    v36 = &v26;
    tlgWriteTransfer_EtwWriteTransfer(v12, (int)&byte_140016D91, v9, v10, IoStatusBlock, &v35);
    goto LABEL_23;
  }
  for ( i = ZwQueryDirectoryFile(
              FileHandle,
              0,
              0,
              0,
              &v33,
              (PVOID)FileInformation,
              0x186u,
              FileNamesInformation,
              1u,
              &DestinationString,
              1u);
        ;
        i = ZwQueryDirectoryFile(
              FileHandle,
              0,
              0,
              0,
              &v33,
              (PVOID)FileInformation,
              0x186u,
              FileNamesInformation,
              1u,
              &DestinationString,
              0) )
  {
    v11 = i;
    if ( i < 0 )
    {
      if ( i == -2147483642 || i == -1073741809 )
        v11 = 0;
      goto LABEL_22;
    }
    v15 = *(_DWORD *)(FileInformation + 8);
    if ( v15 )
      break;
LABEL_17:
    ;
  }
  *(_WORD *)(FileInformation + 2 * ((unsigned __int64)v15 >> 1) + 12) = 0;
  RtlInitUnicodeString(&v31, (PCWSTR)(FileInformation + 12));
  SeConvertStringSidToSid(v31.Buffer, &v29);
  v11 = BfsCreateStorage(a1, 0, FileHandle, &v31, (unsigned __int64 **)&v34[6]);
  if ( v11 >= 0 )
  {
    v11 = BfsEnumeratePolicy((__int64)v34, (__int64)P, 0, &v26);
    if ( v11 >= 0 )
    {
      while ( 1 )
      {
        v19 = (struct _UNICODE_STRING *)P[0];
        if ( P[0] == P )
          break;
        if ( *((PVOID **)P[0] + 1) != P || (v20 = *(_QWORD *)P[0], *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0]) )
LABEL_37:
          __fastfail(3u);
        P[0] = *(PVOID *)P[0];
        *(_QWORD *)(v20 + 8) = P;
        BfsAddPolicyToGlobalFileTable(a3, (__int64)v30, (__int64)v29, v19 + 2);
        RtlFreeUnicodeString(v19 + 2);
        ExFreePoolWithTag(v19, 0);
      }
      BfsCloseStorage((_QWORD *)v34[6]);
      v34[6] = 0;
      ExFreePoolWithTag(v29, 0);
      v29 = 0;
      goto LABEL_17;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v26 = v11;
    v36 = &v26;
    v37 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v16, (int)&byte_140016D91, v17, v18, IoStatusBlocka, &v35);
  }
LABEL_22:
  ExFreePoolWithTag((PVOID)FileInformation, 0);
LABEL_23:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v34[6] )
    BfsCloseStorage((_QWORD *)v34[6]);
  if ( v30 )
    ExFreePoolWithTag(v30, 0);
  v21 = v29;
  if ( !v29 )
    goto LABEL_31;
  while ( 1 )
  {
    ExFreePoolWithTag(v21, 0);
LABEL_31:
    v21 = P[0];
    if ( P[0] == P )
      return (unsigned int)v11;
    if ( *((PVOID **)P[0] + 1) != P )
      goto LABEL_37;
    v22 = *(_QWORD *)P[0];
    if ( *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0] )
      goto LABEL_37;
    P[0] = *(PVOID *)P[0];
    *(_QWORD *)(v22 + 8) = P;
  }
}

```

## disassembly

```asm
0x14000ceb4  mov     [rsp-8+arg_8], rbx
0x14000ceb9  push    rbp
0x14000ceba  push    rsi
0x14000cebb  push    rdi
0x14000cebc  push    r12
0x14000cebe  push    r15
0x14000cec0  lea     rbp, [rsp-0A0h]
0x14000cec8  sub     rsp, 1A0h
0x14000cecf  mov     rax, cs:__security_cookie
0x14000ced6  xor     rax, rsp
0x14000ced9  mov     [rbp+0C0h+var_30], rax
0x14000cee0  xorps   xmm0, xmm0
0x14000cee3  mov     [rbp+0C0h+var_140], 0
0x14000ceeb  mov     r12, r8
0x14000ceee  mov     r15, rcx
0x14000cef1  xorps   xmm1, xmm1
0x14000cef4  lea     rcx, [rbp+0C0h+var_100]; void *
0x14000cef8  mov     r8d, 98h; Size
0x14000cefe  xor     edx, edx; Val
0x14000cf00  movups  xmmword ptr [rbp+0C0h+var_110], xmm0
0x14000cf04  mov     rbx, r9
0x14000cf07  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm1
0x14000cf0b  movups  xmmword ptr [rbp+0C0h+var_130.Length], xmm0
0x14000cf0f  call    memset
0x14000cf14  lea     rax, [rsp+1C0h+P]
0x14000cf19  mov     [rsp+1C0h+var_160], 0
0x14000cf21  mov     [rsp+1C0h+var_150], rax
0x14000cf26  lea     rdx, aS1; "S-1-*"
0x14000cf2d  lea     rax, [rsp+1C0h+P]
0x14000cf32  mov     [rsp+1C0h+FileHandle], 0
0x14000cf3b  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x14000cf3f  mov     [rsp+1C0h+P], rax
0x14000cf44  mov     [rbp+0C0h+var_138], 0
0x14000cf4c  call    cs:__imp_RtlInitUnicodeString
0x14000cf53  nop     dword ptr [rax+rax+00h]
0x14000cf58  mov     rcx, [rbx+8]
0x14000cf5c  lea     rdx, [rbp+0C0h+var_138]
0x14000cf60  call    cs:__imp_SeConvertStringSidToSid
0x14000cf67  nop     dword ptr [rax+rax+00h]
0x14000cf6c  lea     rax, [rsp+1C0h+FileHandle]
0x14000cf71  mov     r9b, 1
0x14000cf74  mov     r8, rbx
0x14000cf77  mov     [rsp+1C0h+IoStatusBlock], rax; int
0x14000cf7c  xor     edx, edx
0x14000cf7e  mov     rcx, r15
0x14000cf81  call    BfsOpenPolicyDirectory
0x14000cf86  mov     ebx, eax
0x14000cf88  test    eax, eax
0x14000cf8a  jns     short loc_14000CFD0
0x14000cf8c  mov     ecx, cs:dword_140019000; int
0x14000cf92  cmp     ecx, 3
0x14000cf95  jbe     loc_14000D1D0
0x14000cf9b  mov     [rsp+1C0h+var_160], eax
0x14000cf9f  lea     rax, [rsp+1C0h+var_160]
0x14000cfa4  mov     [rbp+0C0h+var_38], 4
0x14000cfaf  mov     [rbp+0C0h+var_40], rax
0x14000cfb6  lea     rdx, byte_140016D91; int
0x14000cfbd  lea     rax, [rbp+0C0h+var_60]
0x14000cfc1  mov     [rsp+1C0h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000cfc6  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000cfcb  jmp     loc_14000D1D0
0x14000cfd0  mov     ebx, 186h
0x14000cfd5  mov     r8d, 4E736642h
0x14000cfdb  mov     edx, ebx
0x14000cfdd  mov     ecx, 100h
0x14000cfe2  call    cs:__imp_ExAllocatePool2
0x14000cfe9  nop     dword ptr [rax+rax+00h]
0x14000cfee  mov     rsi, rax
0x14000cff1  test    rax, rax
0x14000cff4  jnz     short loc_14000D010
0x14000cff6  mov     eax, cs:dword_140019000
0x14000cffc  mov     ebx, 0C0000017h
0x14000d001  cmp     eax, 3
0x14000d004  jbe     loc_14000D1D0
0x14000d00a  mov     [rsp+1C0h+var_160], ebx
0x14000d00e  jmp     short loc_14000CF9F
0x14000d010  mov     [rsp+1C0h+RestartScan], 1
0x14000d015  lea     rax, [rbp+0C0h+DestinationString]
0x14000d019  mov     [rsp+1C0h+FileName], rax
0x14000d01e  mov     [rsp+1C0h+ReturnSingleEntry], 1
0x14000d023  mov     [rsp+1C0h+FileInformationClass], 0Ch
0x14000d02b  mov     [rsp+1C0h+Length], ebx
0x14000d02f  jmp     loc_14000D17E
0x14000d034  mov     eax, [rsi+8]
0x14000d037  test    eax, eax
0x14000d039  jz      loc_14000D15B
0x14000d03f  mov     ecx, eax
0x14000d041  lea     rdx, [rsi+0Ch]; SourceString
0x14000d045  shr     rcx, 1
0x14000d048  xor     eax, eax
0x14000d04a  mov     [rsi+rcx*2+0Ch], ax
0x14000d04f  lea     rcx, [rbp+0C0h+var_130]; DestinationString
0x14000d053  call    cs:__imp_RtlInitUnicodeString
0x14000d05a  nop     dword ptr [rax+rax+00h]
0x14000d05f  mov     rcx, [rbp+0C0h+var_130.Buffer]
0x14000d063  lea     rdx, [rbp+0C0h+var_140]
0x14000d067  call    cs:__imp_SeConvertStringSidToSid
0x14000d06e  nop     dword ptr [rax+rax+00h]
0x14000d073  mov     r8, [rsp+1C0h+FileHandle]
0x14000d078  lea     rax, [rbp+0C0h+var_D0]
0x14000d07c  lea     r9, [rbp+0C0h+var_130]
0x14000d080  mov     [rsp+1C0h+IoStatusBlock], rax; int
0x14000d085  xor     edx, edx
0x14000d087  mov     rcx, r15
0x14000d08a  call    BfsCreateStorage
0x14000d08f  mov     ebx, eax
0x14000d091  test    eax, eax
0x14000d093  js      loc_14000D258
0x14000d099  lea     r9, [rsp+1C0h+var_160]
0x14000d09e  xor     r8d, r8d
0x14000d0a1  lea     rdx, [rsp+1C0h+P]
0x14000d0a6  lea     rcx, [rbp+0C0h+var_100]
0x14000d0aa  call    BfsEnumeratePolicy
0x14000d0af  mov     ebx, eax
0x14000d0b1  test    eax, eax
0x14000d0b3  js      loc_14000D258
0x14000d0b9  mov     rdi, [rsp+1C0h+P]
0x14000d0be  lea     rax, [rsp+1C0h+P]
0x14000d0c3  cmp     rdi, rax
0x14000d0c6  jz      short loc_14000D130
0x14000d0c8  lea     rax, [rsp+1C0h+P]
0x14000d0cd  cmp     [rdi+8], rax
0x14000d0d1  jnz     loc_14000D29C
0x14000d0d7  mov     rax, [rdi]
0x14000d0da  cmp     [rax+8], rdi
0x14000d0de  jnz     loc_14000D29C
0x14000d0e4  mov     [rsp+1C0h+P], rax
0x14000d0e9  lea     rcx, [rsp+1C0h+P]
0x14000d0ee  mov     [rax+8], rcx
0x14000d0f2  lea     r9, [rdi+20h]
0x14000d0f6  mov     eax, [rdi+10h]
0x14000d0f9  mov     rcx, r12
0x14000d0fc  mov     r8, [rbp+0C0h+var_140]
0x14000d100  mov     rdx, [rbp+0C0h+var_138]
0x14000d104  mov     dword ptr [rsp+1C0h+IoStatusBlock], eax
0x14000d108  call    BfsAddPolicyToGlobalFileTable
0x14000d10d  lea     rcx, [rdi+20h]; UnicodeString
0x14000d111  call    cs:__imp_RtlFreeUnicodeString
0x14000d118  nop     dword ptr [rax+rax+00h]
0x14000d11d  xor     edx, edx; Tag
0x14000d11f  mov     rcx, rdi; P
0x14000d122  call    cs:__imp_ExFreePoolWithTag
0x14000d129  nop     dword ptr [rax+rax+00h]
0x14000d12e  jmp     short loc_14000D0B9
0x14000d130  mov     rcx, [rbp+0C0h+var_D0]; P
0x14000d134  call    BfsCloseStorage
0x14000d139  mov     rcx, [rbp+0C0h+var_140]; P
0x14000d13d  xor     edx, edx; Tag
0x14000d13f  mov     [rbp+0C0h+var_D0], 0
0x14000d147  call    cs:__imp_ExFreePoolWithTag
0x14000d14e  nop     dword ptr [rax+rax+00h]
0x14000d153  mov     [rbp+0C0h+var_140], 0
0x14000d15b  mov     [rsp+1C0h+RestartScan], 0; RestartScan
0x14000d160  lea     rax, [rbp+0C0h+DestinationString]
0x14000d164  mov     [rsp+1C0h+FileName], rax; FileName
0x14000d169  mov     [rsp+1C0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14000d16e  mov     [rsp+1C0h+FileInformationClass], 0Ch; FileInformationClass
0x14000d176  mov     [rsp+1C0h+Length], 186h; Length
0x14000d17e  mov     rcx, [rsp+1C0h+FileHandle]; FileHandle
0x14000d183  lea     rax, [rbp+0C0h+var_110]
0x14000d187  mov     [rsp+1C0h+FileInformation], rsi; FileInformation
0x14000d18c  xor     r9d, r9d; ApcContext
0x14000d18f  xor     r8d, r8d; ApcRoutine
0x14000d192  mov     [rsp+1C0h+IoStatusBlock], rax; IoStatusBlock
0x14000d197  xor     edx, edx; Event
0x14000d199  call    cs:__imp_ZwQueryDirectoryFile
0x14000d1a0  nop     dword ptr [rax+rax+00h]
0x14000d1a5  mov     ebx, eax
0x14000d1a7  test    eax, eax
0x14000d1a9  jns     loc_14000D034
0x14000d1af  cmp     eax, 80000006h
0x14000d1b4  jz      short loc_14000D1BD
0x14000d1b6  cmp     eax, 0C000000Fh
0x14000d1bb  jnz     short loc_14000D1BF
0x14000d1bd  xor     ebx, ebx
0x14000d1bf  xor     edx, edx; Tag
0x14000d1c1  mov     rcx, rsi; P
0x14000d1c4  call    cs:__imp_ExFreePoolWithTag
0x14000d1cb  nop     dword ptr [rax+rax+00h]
0x14000d1d0  cmp     [rsp+1C0h+FileHandle], 0
0x14000d1d6  jz      short loc_14000D1E9
0x14000d1d8  mov     rcx, [rsp+1C0h+FileHandle]; Handle
0x14000d1dd  call    cs:__imp_ZwClose
0x14000d1e4  nop     dword ptr [rax+rax+00h]
0x14000d1e9  mov     rcx, [rbp+0C0h+var_D0]; P
0x14000d1ed  test    rcx, rcx
0x14000d1f0  jz      short loc_14000D1F7
0x14000d1f2  call    BfsCloseStorage
0x14000d1f7  mov     rcx, [rbp+0C0h+var_138]; P
0x14000d1fb  test    rcx, rcx
0x14000d1fe  jz      short loc_14000D20E
0x14000d200  xor     edx, edx; Tag
0x14000d202  call    cs:__imp_ExFreePoolWithTag
0x14000d209  nop     dword ptr [rax+rax+00h]
0x14000d20e  mov     rcx, [rbp+0C0h+var_140]; P
0x14000d212  test    rcx, rcx
0x14000d215  jz      short loc_14000D225
0x14000d217  xor     edx, edx; Tag
0x14000d219  call    cs:__imp_ExFreePoolWithTag
0x14000d220  nop     dword ptr [rax+rax+00h]
0x14000d225  mov     rcx, [rsp+1C0h+P]
0x14000d22a  lea     rax, [rsp+1C0h+P]
0x14000d22f  cmp     rcx, rax
0x14000d232  jz      short loc_14000D2A3
0x14000d234  lea     rax, [rsp+1C0h+P]
0x14000d239  cmp     [rcx+8], rax
0x14000d23d  jnz     short loc_14000D29C
0x14000d23f  mov     rax, [rcx]
0x14000d242  cmp     [rax+8], rcx
0x14000d246  jnz     short loc_14000D29C
0x14000d248  lea     rdx, [rsp+1C0h+P]
0x14000d24d  mov     [rsp+1C0h+P], rax
0x14000d252  mov     [rax+8], rdx
0x14000d256  jmp     short loc_14000D217
0x14000d258  mov     eax, cs:dword_140019000
0x14000d25e  cmp     eax, 3
0x14000d261  jbe     loc_14000D1BF
0x14000d267  lea     rax, [rsp+1C0h+var_160]
0x14000d26c  mov     [rsp+1C0h+var_160], ebx
0x14000d270  mov     [rbp+0C0h+var_40], rax
0x14000d277  lea     rdx, byte_140016D91; int
0x14000d27e  lea     rax, [rbp+0C0h+var_60]
0x14000d282  mov     [rbp+0C0h+var_38], 4
0x14000d28d  mov     [rsp+1C0h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000d292  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d297  jmp     loc_14000D1BF
0x14000d29c  mov     ecx, 3
0x14000d2a1  int     29h; Win8: RtlFailFast(ecx)
0x14000d2a3  mov     eax, ebx
0x14000d2a5  mov     rcx, [rbp+0C0h+var_30]
0x14000d2ac  xor     rcx, rsp; StackCookie
0x14000d2af  call    __security_check_cookie
0x14000d2b4  mov     rbx, [rsp+1C0h+arg_8]
0x14000d2bc  add     rsp, 1A0h
0x14000d2c3  pop     r15
0x14000d2c5  pop     r12
0x14000d2c7  pop     rdi
0x14000d2c8  pop     rsi
0x14000d2c9  pop     rbp
0x14000d2ca  retn
```
