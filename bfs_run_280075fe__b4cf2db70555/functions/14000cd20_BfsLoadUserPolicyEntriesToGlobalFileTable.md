# BfsLoadUserPolicyEntriesToGlobalFileTable

- ea: `0x14000cd20`
- end: `0x14000d138`
- name: `BfsLoadUserPolicyEntriesToGlobalFileTable`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000c9a4`

## callees

- `0x140001008`
- `0x1400061a0`
- `0x140008d3c`
- `0x14000bf64`
- `0x14000cd20`
- `0x14001064c`
- `0x140010b30`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000d005`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000d005`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000cdcc`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000ced3`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000cdcc`
- `ntoskrnl!SeConvertStringSidToSid` at `0x14000ced3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cdb8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cebf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cdb8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cebf`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000cf7d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000cf7d`
- `ntoskrnl!ZwClose` at `0x14000d049`
- `ntoskrnl!ZwClose` at `0x14000d049`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cfb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d030`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d06e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d085`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cf8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cfb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d030`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d06e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d085`
- `ntoskrnl!ExAllocatePool2` at `0x14000ce4e`
- `ntoskrnl!ExAllocatePool2` at `0x14000ce4e`

## pseudocode

```c
__int64 __fastcall BfsLoadUserPolicyEntriesToGlobalFileTable(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v7; // r9d
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  int Storage; // ebx
  int v12; // ecx
  __int64 Pool2; // rsi
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
  PIO_STATUS_BLOCK IoStatusBlocka; // [rsp+20h] [rbp-E0h]
  PVOID FileInformation; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-98h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID v30; // [rsp+80h] [rbp-80h] BYREF
  PVOID v31; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v32; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK v34; // [rsp+B0h] [rbp-50h] BYREF
  PVOID v35[20]; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+160h] [rbp+60h] BYREF
  int *v37; // [rsp+180h] [rbp+80h]
  __int64 v38; // [rsp+188h] [rbp+88h]

  v30 = 0;
  v34 = 0;
  DestinationString = 0;
  v32 = 0;
  memset(v35, 0, 0x98u);
  v27 = 0;
  P[1] = P;
  FileHandle = 0;
  P[0] = P;
  v31 = 0;
  RtlInitUnicodeString(&DestinationString, L"S-1-*");
  SeConvertStringSidToSid(*(_QWORD *)(a4 + 8), &v31);
  LOBYTE(v7) = 1;
  v8 = BfsOpenPolicyDirectory(a1, 0, a4, v7, (__int64)&FileHandle);
  Storage = v8;
  if ( v8 < 0 )
  {
    v12 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_23;
    v27 = v8;
    goto LABEL_4;
  }
  Pool2 = ExAllocatePool2(256, 390, 1316185666);
  if ( !Pool2 )
  {
    Storage = -1073741801;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_23;
    v27 = -1073741801;
LABEL_4:
    v38 = 4;
    v37 = &v27;
    tlgWriteTransfer_EtwWriteTransfer(v12, (int)&byte_140016D91, v9, v10, IoStatusBlock, &v36);
    goto LABEL_23;
  }
  for ( i = ZwQueryDirectoryFile(
              FileHandle,
              0,
              0,
              0,
              &v34,
              (PVOID)Pool2,
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
              &v34,
              (PVOID)Pool2,
              0x186u,
              FileNamesInformation,
              1u,
              &DestinationString,
              0) )
  {
    Storage = i;
    if ( i < 0 )
    {
      if ( i == -2147483642 || i == -1073741809 )
        Storage = 0;
      goto LABEL_22;
    }
    v15 = *(_DWORD *)(Pool2 + 8);
    if ( v15 )
      break;
LABEL_17:
    ;
  }
  *(_WORD *)(Pool2 + 2 * ((unsigned __int64)v15 >> 1) + 12) = 0;
  RtlInitUnicodeString(&v32, (PCWSTR)(Pool2 + 12));
  SeConvertStringSidToSid(v32.Buffer, &v30);
  Storage = BfsCreateStorage(a1, 0, (_DWORD)FileHandle, (unsigned int)&v32, (__int64)&v35[6]);
  if ( Storage >= 0 )
  {
    Storage = BfsEnumeratePolicy(v35, P, 0, &v27, IoStatusBlocka, FileInformation);
    if ( Storage >= 0 )
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
        BfsAddPolicyToGlobalFileTable(a3, v31, v30, &v19[2]);
        RtlFreeUnicodeString(v19 + 2);
        ExFreePoolWithTag(v19, 0);
      }
      BfsCloseStorage(v35[6]);
      v35[6] = 0;
      ExFreePoolWithTag(v30, 0);
      v30 = 0;
      goto LABEL_17;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v27 = Storage;
    v37 = &v27;
    v38 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v16, (int)&byte_140016D91, v17, v18, (int)IoStatusBlocka, &v36);
  }
LABEL_22:
  ExFreePoolWithTag((PVOID)Pool2, 0);
LABEL_23:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v35[6] )
    BfsCloseStorage(v35[6]);
  if ( v31 )
    ExFreePoolWithTag(v31, 0);
  v21 = v30;
  if ( !v30 )
    goto LABEL_31;
  while ( 1 )
  {
    ExFreePoolWithTag(v21, 0);
LABEL_31:
    v21 = P[0];
    if ( P[0] == P )
      return (unsigned int)Storage;
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
0x14000cd20  mov     [rsp-8+arg_8], rbx
0x14000cd25  push    rbp
0x14000cd26  push    rsi
0x14000cd27  push    rdi
0x14000cd28  push    r12
0x14000cd2a  push    r15
0x14000cd2c  lea     rbp, [rsp-0A0h]
0x14000cd34  sub     rsp, 1A0h
0x14000cd3b  mov     rax, cs:__security_cookie
0x14000cd42  xor     rax, rsp
0x14000cd45  mov     [rbp+0C0h+var_30], rax
0x14000cd4c  xorps   xmm0, xmm0
0x14000cd4f  mov     [rbp+0C0h+var_140], 0
0x14000cd57  mov     r12, r8
0x14000cd5a  mov     r15, rcx
0x14000cd5d  xorps   xmm1, xmm1
0x14000cd60  lea     rcx, [rbp+0C0h+var_100]; void *
0x14000cd64  mov     r8d, 98h; Size
0x14000cd6a  xor     edx, edx; Val
0x14000cd6c  movups  xmmword ptr [rbp+0C0h+var_110], xmm0
0x14000cd70  mov     rbx, r9
0x14000cd73  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm1
0x14000cd77  movups  xmmword ptr [rbp+0C0h+var_130.Length], xmm0
0x14000cd7b  call    memset
0x14000cd80  lea     rax, [rsp+1C0h+P]
0x14000cd85  mov     [rsp+1C0h+var_160], 0
0x14000cd8d  mov     [rsp+1C0h+var_150], rax
0x14000cd92  lea     rdx, aS1; "S-1-*"
0x14000cd99  lea     rax, [rsp+1C0h+P]
0x14000cd9e  mov     [rsp+1C0h+FileHandle], 0
0x14000cda7  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x14000cdab  mov     [rsp+1C0h+P], rax
0x14000cdb0  mov     [rbp+0C0h+var_138], 0
0x14000cdb8  call    cs:__imp_RtlInitUnicodeString
0x14000cdbf  nop     dword ptr [rax+rax+00h]
0x14000cdc4  mov     rcx, [rbx+8]
0x14000cdc8  lea     rdx, [rbp+0C0h+var_138]
0x14000cdcc  call    cs:__imp_SeConvertStringSidToSid
0x14000cdd3  nop     dword ptr [rax+rax+00h]
0x14000cdd8  lea     rax, [rsp+1C0h+FileHandle]
0x14000cddd  mov     r9b, 1
0x14000cde0  mov     r8, rbx
0x14000cde3  mov     [rsp+1C0h+IoStatusBlock], rax; int
0x14000cde8  xor     edx, edx
0x14000cdea  mov     rcx, r15
0x14000cded  call    BfsOpenPolicyDirectory
0x14000cdf2  mov     ebx, eax
0x14000cdf4  test    eax, eax
0x14000cdf6  jns     short loc_14000CE3C
0x14000cdf8  mov     ecx, cs:dword_140019000; int
0x14000cdfe  cmp     ecx, 3
0x14000ce01  jbe     loc_14000D03C
0x14000ce07  mov     [rsp+1C0h+var_160], eax
0x14000ce0b  lea     rax, [rsp+1C0h+var_160]
0x14000ce10  mov     [rbp+0C0h+var_38], 4
0x14000ce1b  mov     [rbp+0C0h+var_40], rax
0x14000ce22  lea     rdx, byte_140016D91; int
0x14000ce29  lea     rax, [rbp+0C0h+var_60]
0x14000ce2d  mov     [rsp+1C0h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000ce32  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ce37  jmp     loc_14000D03C
0x14000ce3c  mov     ebx, 186h
0x14000ce41  mov     r8d, 4E736642h
0x14000ce47  mov     edx, ebx
0x14000ce49  mov     ecx, 100h
0x14000ce4e  call    cs:__imp_ExAllocatePool2
0x14000ce55  nop     dword ptr [rax+rax+00h]
0x14000ce5a  mov     rsi, rax
0x14000ce5d  test    rax, rax
0x14000ce60  jnz     short loc_14000CE7C
0x14000ce62  mov     eax, cs:dword_140019000
0x14000ce68  mov     ebx, 0C0000017h
0x14000ce6d  cmp     eax, 3
0x14000ce70  jbe     loc_14000D03C
0x14000ce76  mov     [rsp+1C0h+var_160], ebx
0x14000ce7a  jmp     short loc_14000CE0B
0x14000ce7c  mov     [rsp+1C0h+RestartScan], 1
0x14000ce81  lea     rax, [rbp+0C0h+DestinationString]
0x14000ce85  mov     [rsp+1C0h+FileName], rax
0x14000ce8a  mov     [rsp+1C0h+ReturnSingleEntry], 1
0x14000ce8f  mov     [rsp+1C0h+FileInformationClass], 0Ch
0x14000ce97  mov     [rsp+1C0h+Length], ebx
0x14000ce9b  jmp     loc_14000CFEA
0x14000cea0  mov     eax, [rsi+8]
0x14000cea3  test    eax, eax
0x14000cea5  jz      loc_14000CFC7
0x14000ceab  mov     ecx, eax
0x14000cead  lea     rdx, [rsi+0Ch]; SourceString
0x14000ceb1  shr     rcx, 1
0x14000ceb4  xor     eax, eax
0x14000ceb6  mov     [rsi+rcx*2+0Ch], ax
0x14000cebb  lea     rcx, [rbp+0C0h+var_130]; DestinationString
0x14000cebf  call    cs:__imp_RtlInitUnicodeString
0x14000cec6  nop     dword ptr [rax+rax+00h]
0x14000cecb  mov     rcx, [rbp+0C0h+var_130.Buffer]
0x14000cecf  lea     rdx, [rbp+0C0h+var_140]
0x14000ced3  call    cs:__imp_SeConvertStringSidToSid
0x14000ceda  nop     dword ptr [rax+rax+00h]
0x14000cedf  mov     r8, [rsp+1C0h+FileHandle]
0x14000cee4  lea     rax, [rbp+0C0h+var_D0]
0x14000cee8  lea     r9, [rbp+0C0h+var_130]
0x14000ceec  mov     [rsp+1C0h+IoStatusBlock], rax; int
0x14000cef1  xor     edx, edx
0x14000cef3  mov     rcx, r15
0x14000cef6  call    BfsCreateStorage
0x14000cefb  mov     ebx, eax
0x14000cefd  test    eax, eax
0x14000ceff  js      loc_14000D0C4
0x14000cf05  lea     r9, [rsp+1C0h+var_160]
0x14000cf0a  xor     r8d, r8d
0x14000cf0d  lea     rdx, [rsp+1C0h+P]
0x14000cf12  lea     rcx, [rbp+0C0h+var_100]
0x14000cf16  call    BfsEnumeratePolicy
0x14000cf1b  mov     ebx, eax
0x14000cf1d  test    eax, eax
0x14000cf1f  js      loc_14000D0C4
0x14000cf25  mov     rdi, [rsp+1C0h+P]
0x14000cf2a  lea     rax, [rsp+1C0h+P]
0x14000cf2f  cmp     rdi, rax
0x14000cf32  jz      short loc_14000CF9C
0x14000cf34  lea     rax, [rsp+1C0h+P]
0x14000cf39  cmp     [rdi+8], rax
0x14000cf3d  jnz     loc_14000D108
0x14000cf43  mov     rax, [rdi]
0x14000cf46  cmp     [rax+8], rdi
0x14000cf4a  jnz     loc_14000D108
0x14000cf50  mov     [rsp+1C0h+P], rax
0x14000cf55  lea     rcx, [rsp+1C0h+P]
0x14000cf5a  mov     [rax+8], rcx
0x14000cf5e  lea     r9, [rdi+20h]
0x14000cf62  mov     eax, [rdi+10h]
0x14000cf65  mov     rcx, r12
0x14000cf68  mov     r8, [rbp+0C0h+var_140]
0x14000cf6c  mov     rdx, [rbp+0C0h+var_138]
0x14000cf70  mov     dword ptr [rsp+1C0h+IoStatusBlock], eax
0x14000cf74  call    BfsAddPolicyToGlobalFileTable
0x14000cf79  lea     rcx, [rdi+20h]; UnicodeString
0x14000cf7d  call    cs:__imp_RtlFreeUnicodeString
0x14000cf84  nop     dword ptr [rax+rax+00h]
0x14000cf89  xor     edx, edx; Tag
0x14000cf8b  mov     rcx, rdi; P
0x14000cf8e  call    cs:__imp_ExFreePoolWithTag
0x14000cf95  nop     dword ptr [rax+rax+00h]
0x14000cf9a  jmp     short loc_14000CF25
0x14000cf9c  mov     rcx, [rbp+0C0h+var_D0]; P
0x14000cfa0  call    BfsCloseStorage
0x14000cfa5  mov     rcx, [rbp+0C0h+var_140]; P
0x14000cfa9  xor     edx, edx; Tag
0x14000cfab  mov     [rbp+0C0h+var_D0], 0
0x14000cfb3  call    cs:__imp_ExFreePoolWithTag
0x14000cfba  nop     dword ptr [rax+rax+00h]
0x14000cfbf  mov     [rbp+0C0h+var_140], 0
0x14000cfc7  mov     [rsp+1C0h+RestartScan], 0; RestartScan
0x14000cfcc  lea     rax, [rbp+0C0h+DestinationString]
0x14000cfd0  mov     [rsp+1C0h+FileName], rax; FileName
0x14000cfd5  mov     [rsp+1C0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14000cfda  mov     [rsp+1C0h+FileInformationClass], 0Ch; FileInformationClass
0x14000cfe2  mov     [rsp+1C0h+Length], 186h; Length
0x14000cfea  mov     rcx, [rsp+1C0h+FileHandle]; FileHandle
0x14000cfef  lea     rax, [rbp+0C0h+var_110]
0x14000cff3  mov     [rsp+1C0h+FileInformation], rsi; FileInformation
0x14000cff8  xor     r9d, r9d; ApcContext
0x14000cffb  xor     r8d, r8d; ApcRoutine
0x14000cffe  mov     [rsp+1C0h+IoStatusBlock], rax; IoStatusBlock
0x14000d003  xor     edx, edx; Event
0x14000d005  call    cs:__imp_ZwQueryDirectoryFile
0x14000d00c  nop     dword ptr [rax+rax+00h]
0x14000d011  mov     ebx, eax
0x14000d013  test    eax, eax
0x14000d015  jns     loc_14000CEA0
0x14000d01b  cmp     eax, 80000006h
0x14000d020  jz      short loc_14000D029
0x14000d022  cmp     eax, 0C000000Fh
0x14000d027  jnz     short loc_14000D02B
0x14000d029  xor     ebx, ebx
0x14000d02b  xor     edx, edx; Tag
0x14000d02d  mov     rcx, rsi; P
0x14000d030  call    cs:__imp_ExFreePoolWithTag
0x14000d037  nop     dword ptr [rax+rax+00h]
0x14000d03c  cmp     [rsp+1C0h+FileHandle], 0
0x14000d042  jz      short loc_14000D055
0x14000d044  mov     rcx, [rsp+1C0h+FileHandle]; Handle
0x14000d049  call    cs:__imp_ZwClose
0x14000d050  nop     dword ptr [rax+rax+00h]
0x14000d055  mov     rcx, [rbp+0C0h+var_D0]; P
0x14000d059  test    rcx, rcx
0x14000d05c  jz      short loc_14000D063
0x14000d05e  call    BfsCloseStorage
0x14000d063  mov     rcx, [rbp+0C0h+var_138]; P
0x14000d067  test    rcx, rcx
0x14000d06a  jz      short loc_14000D07A
0x14000d06c  xor     edx, edx; Tag
0x14000d06e  call    cs:__imp_ExFreePoolWithTag
0x14000d075  nop     dword ptr [rax+rax+00h]
0x14000d07a  mov     rcx, [rbp+0C0h+var_140]; P
0x14000d07e  test    rcx, rcx
0x14000d081  jz      short loc_14000D091
0x14000d083  xor     edx, edx; Tag
0x14000d085  call    cs:__imp_ExFreePoolWithTag
0x14000d08c  nop     dword ptr [rax+rax+00h]
0x14000d091  mov     rcx, [rsp+1C0h+P]
0x14000d096  lea     rax, [rsp+1C0h+P]
0x14000d09b  cmp     rcx, rax
0x14000d09e  jz      short loc_14000D10F
0x14000d0a0  lea     rax, [rsp+1C0h+P]
0x14000d0a5  cmp     [rcx+8], rax
0x14000d0a9  jnz     short loc_14000D108
0x14000d0ab  mov     rax, [rcx]
0x14000d0ae  cmp     [rax+8], rcx
0x14000d0b2  jnz     short loc_14000D108
0x14000d0b4  lea     rdx, [rsp+1C0h+P]
0x14000d0b9  mov     [rsp+1C0h+P], rax
0x14000d0be  mov     [rax+8], rdx
0x14000d0c2  jmp     short loc_14000D083
0x14000d0c4  mov     eax, cs:dword_140019000
0x14000d0ca  cmp     eax, 3
0x14000d0cd  jbe     loc_14000D02B
0x14000d0d3  lea     rax, [rsp+1C0h+var_160]
0x14000d0d8  mov     [rsp+1C0h+var_160], ebx
0x14000d0dc  mov     [rbp+0C0h+var_40], rax
0x14000d0e3  lea     rdx, byte_140016D91; int
0x14000d0ea  lea     rax, [rbp+0C0h+var_60]
0x14000d0ee  mov     [rbp+0C0h+var_38], 4
0x14000d0f9  mov     [rsp+1C0h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000d0fe  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d103  jmp     loc_14000D02B
0x14000d108  mov     ecx, 3
0x14000d10d  int     29h; Win8: RtlFailFast(ecx)
0x14000d10f  mov     eax, ebx
0x14000d111  mov     rcx, [rbp+0C0h+var_30]
0x14000d118  xor     rcx, rsp; StackCookie
0x14000d11b  call    __security_check_cookie
0x14000d120  mov     rbx, [rsp+1C0h+arg_8]
0x14000d128  add     rsp, 1A0h
0x14000d12f  pop     r15
0x14000d131  pop     r12
0x14000d133  pop     rdi
0x14000d134  pop     rsi
0x14000d135  pop     rbp
0x14000d136  retn
```
