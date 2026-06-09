# BfsProcessSetPolicyRequest

- ea: `0x140009b9c`
- end: `0x14000a35b`
- name: `BfsProcessSetPolicyRequest`
- size: `1983`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140003640`

## callees

- `0x140001008`
- `0x140003210`
- `0x1400034e4`
- `0x140004fc0`
- `0x140006040`
- `0x140006af4`
- `0x140006b90`
- `0x140006e14`
- `0x140007044`
- `0x140007614`
- `0x140009b9c`
- `0x14000b2e0`
- `0x14000bf64`
- `0x14001033c`
- `0x140010ffc`
- `0x140013730`
- `0x140013840`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009d31`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009f0a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009d31`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009f0a`
- `ntoskrnl!SeTokenObjectType` at `0x140009d20`
- `ntoskrnl!IoCreateFile` at `0x140009ec7`
- `ntoskrnl!IoCreateFile` at `0x140009ec7`
- `ntoskrnl!IoFileObjectType` at `0x140009ef5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a09c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a09c`
- `ntoskrnl!ZwOpenFile` at `0x140009e54`
- `ntoskrnl!ZwOpenFile` at `0x140009e54`
- `ntoskrnl!ZwClose` at `0x14000a296`
- `ntoskrnl!ZwClose` at `0x14000a296`
- `ntoskrnl!ProbeForRead` at `0x140009c9d`
- `ntoskrnl!ProbeForRead` at `0x140009c9d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a2af`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a2c8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a2af`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a2c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a24c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a27d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a31f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a24c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a27d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a31f`
- `ntoskrnl!SeQueryInformationToken` at `0x140009da2`
- `ntoskrnl!SeQueryInformationToken` at `0x140009dc9`
- `ntoskrnl!SeQueryInformationToken` at `0x140009da2`
- `ntoskrnl!SeQueryInformationToken` at `0x140009dc9`
- `ntoskrnl!ExAllocatePool2` at `0x140009cc6`
- `ntoskrnl!ExAllocatePool2` at `0x140009cc6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a262`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a262`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140009f35`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140009f35`

## pseudocode

```c
__int64 __fastcall BfsProcessSetPolicyRequest(__int64 a1, unsigned int a2)
{
  PWSTR Buffer; // r13
  void *v4; // r15
  unsigned int v5; // r12d
  SIZE_T v6; // rbx
  volatile void *v7; // r14
  int v8; // edi
  void *Pool2; // rax
  NTSTATUS v10; // eax
  int v11; // r8d
  int v12; // r9d
  NTSTATUS FileNameInformationUnsafe; // ebx
  int v14; // ecx
  NTSTATUS *v15; // rax
  char v16; // si
  ULONG v17; // eax
  int v18; // edi
  __int64 v19; // rcx
  char *v20; // r9
  PVOID *Object; // [rsp+20h] [rbp-1A8h]
  NTSTATUS v22; // [rsp+70h] [rbp-158h] BYREF
  NTSTATUS v23; // [rsp+74h] [rbp-154h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp-150h] BYREF
  char v25; // [rsp+80h] [rbp-148h] BYREF
  PVOID v26; // [rsp+88h] [rbp-140h]
  PVOID Token; // [rsp+90h] [rbp-138h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-130h] BYREF
  PVOID TokenInformation; // [rsp+A0h] [rbp-128h] BYREF
  PVOID v30; // [rsp+A8h] [rbp-120h] BYREF
  PVOID v31; // [rsp+B0h] [rbp-118h] BYREF
  UNICODE_STRING String1; // [rsp+B8h] [rbp-110h] BYREF
  PVOID P[2]; // [rsp+C8h] [rbp-100h] BYREF
  __int128 v34; // [rsp+E0h] [rbp-E8h] BYREF
  UNICODE_STRING String2; // [rsp+F0h] [rbp-D8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp-C8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+130h] [rbp-98h] BYREF
  UNICODE_STRING v38; // [rsp+140h] [rbp-88h] BYREF
  __int128 v39; // [rsp+150h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+160h] [rbp-68h] BYREF
  NTSTATUS *v41; // [rsp+180h] [rbp-48h]
  __int64 v42; // [rsp+188h] [rbp-40h]

  v30 = 0;
  FileHandle = 0;
  String1 = 0;
  v38 = 0;
  FileNameInformation = 0;
  v31 = 0;
  IoStatusBlock = 0;
  v39 = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  v26 = 0;
  String2 = 0;
  Token = 0;
  TokenInformation = 0;
  if ( a2 < 0x30 )
    return 3221225507LL;
  Buffer = 0;
  v4 = *(void **)a1;
  v5 = *(_DWORD *)(a1 + 8);
  v23 = *(_DWORD *)(a1 + 12);
  v22 = *(_DWORD *)(a1 + 16);
  v6 = *(unsigned __int16 *)(a1 + 24);
  v7 = *(volatile void **)(a1 + 32);
  v8 = *(_DWORD *)(a1 + 40);
  if ( (unsigned int)Feature_AppSiloBfsProcessSetPolicyRequestBufferCheck__private_IsEnabledDeviceUsageNoInline()
    && (v6 & 1) != 0 )
  {
    return 3221225485LL;
  }
  ProbeForRead(v7, v6, 2u);
  if ( !(_WORD)v6 )
    return 3221225990LL;
  Pool2 = (void *)ExAllocatePool2(256, v6, 1349740098);
  P[1] = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  LOWORD(P[0]) = v6;
  WORD1(P[0]) = v6;
  memmove(Pool2, (const void *)v7, v6);
  v10 = ObReferenceObjectByHandle(v4, 8u, (POBJECT_TYPE)SeTokenObjectType, 1, &Token, 0);
  FileNameInformationUnsafe = v10;
  if ( v10 < 0 )
  {
    v14 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v22 = v10;
LABEL_13:
      v15 = &v22;
LABEL_49:
      v41 = v15;
      v42 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140016D91, v11, v12, (int)Object, &v40);
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  if ( !BfsIsApplicableToken(Token, 1) )
  {
    FileNameInformationUnsafe = -1073700352;
    goto LABEL_16;
  }
  FileNameInformationUnsafe = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( FileNameInformationUnsafe >= 0 )
  {
    FileNameInformationUnsafe = SeQueryInformationToken(Token, TokenAppContainerSid, &v30);
    if ( FileNameInformationUnsafe >= 0 )
    {
      v16 = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 1536;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v17 = 33;
      if ( v5 != 2 )
        v17 = 96;
      FileNameInformationUnsafe = ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, v17);
      if ( FileNameInformationUnsafe == -1073741772 )
      {
        FileNameInformationUnsafe = IoCreateFile(
                                      &FileHandle,
                                      0x80100000,
                                      &ObjectAttributes,
                                      &IoStatusBlock,
                                      0,
                                      0x80u,
                                      7u,
                                      1u,
                                      0x20u,
                                      0,
                                      0,
                                      CreateFileTypeNone,
                                      0,
                                      0x104u);
        v16 = 1;
      }
      if ( FileNameInformationUnsafe >= 0 )
      {
        FileNameInformationUnsafe = ObReferenceObjectByHandle(
                                      FileHandle,
                                      0x80000000,
                                      (POBJECT_TYPE)IoFileObjectType,
                                      0,
                                      &v31,
                                      0);
        if ( FileNameInformationUnsafe >= 0 )
        {
          FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                        (PFILE_OBJECT)v31,
                                        0,
                                        0x101u,
                                        &FileNameInformation);
          if ( FileNameInformationUnsafe >= 0 )
          {
            String1 = *(UNICODE_STRING *)BfsGetFileName(&v34, FileNameInformation);
            String2 = *(UNICODE_STRING *)BfsGetShareName(&v34, FileNameInformation);
            if ( !v16 )
              goto LABEL_32;
            v38 = *(UNICODE_STRING *)BfsGetFinalPathComponent(&v34, P);
            if ( !(unsigned __int16)_mm_cvtsi128_si32((__m128i)v38) )
            {
              FileNameInformationUnsafe = -1073741766;
              goto LABEL_16;
            }
            FileNameInformationUnsafe = BfsAllocateAndConcatenatePath(&String1, &v38);
            if ( FileNameInformationUnsafe >= 0 )
            {
              Buffer = String1.Buffer;
LABEL_32:
              Object = *(PVOID **)v30;
              FileNameInformationUnsafe = BfsGetPolicyEntry(
                                            gBfsFilterHandle,
                                            0,
                                            &gBfsPolicyTable,
                                            *(_QWORD *)TokenInformation);
              if ( FileNameInformationUnsafe >= 0 )
              {
                if ( v8 && (v18 = v8 - 1) != 0 )
                {
                  if ( v18 != 1 )
                    goto LABEL_50;
                  FileNameInformationUnsafe = BfsDeleteEntry(
                                                *((_QWORD *)v26 + 6),
                                                v5,
                                                &FileNameInformation->Volume,
                                                &String1);
                  if ( FileNameInformationUnsafe >= 0 )
                    goto LABEL_50;
                }
                else if ( !String2.Buffer
                       || !RtlCompareUnicodeString(&String1, &String2, 1u)
                       || (!(unsigned int)Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline(v19)
                         ? (v20 = 0)
                         : (v20 = &v25),
                           (unsigned int)BfsGetPolicy(*((_QWORD *)v26 + 6), &FileNameInformation->Volume, &String2, v20)
                         - 1 <= 1
                        || (FileNameInformationUnsafe = BfsAddOrModifyEntry(
                                                          *((_QWORD *)v26 + 6),
                                                          2,
                                                          2,
                                                          0,
                                                          (__int64)&FileNameInformation->Volume,
                                                          (__int64)&String2),
                            FileNameInformationUnsafe >= 0)) )
                {
                  FileNameInformationUnsafe = BfsAddOrModifyEntry(
                                                *((_QWORD *)v26 + 6),
                                                v5,
                                                v23,
                                                v22,
                                                (__int64)&FileNameInformation->Volume,
                                                (__int64)&String1);
                  if ( FileNameInformationUnsafe >= 0 )
                  {
                    v34 = 0;
                    *((_QWORD *)&v34 + 1) = FileNameInformation->Name.Buffer;
                    LOWORD(v34) = FileNameInformation->Name.Length - FileNameInformation->Stream.Length;
                    WORD1(v34) = v34;
                    v39 = v34;
                    LODWORD(Object) = v5;
                    FileNameInformationUnsafe = BfsAddPolicyToGlobalFileTable(
                                                  &gBfsGlobalFileTable,
                                                  *(_QWORD *)TokenInformation,
                                                  *(_QWORD *)v30,
                                                  &v39);
                    if ( FileNameInformationUnsafe >= 0 )
                      goto LABEL_50;
                  }
                  if ( (unsigned int)dword_140019000 <= 3 )
                    goto LABEL_50;
                  v15 = &v23;
                  v23 = FileNameInformationUnsafe;
                  goto LABEL_49;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_16:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v22 = FileNameInformationUnsafe;
    goto LABEL_13;
  }
LABEL_50:
  if ( v26 )
    BfsDereferencePolicyEntryEx(v26);
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v31 )
    ObfDereferenceObject(v31);
  if ( Token )
    ObfDereferenceObject(Token);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v30 )
    ExFreePoolWithTag(v30, 0);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x140009b9c  mov     r11, rsp
0x140009b9f  mov     [r11+10h], rbx
0x140009ba3  mov     [r11+18h], rsi
0x140009ba7  push    rdi
0x140009ba8  push    r12
0x140009baa  push    r13
0x140009bac  push    r14
0x140009bae  push    r15
0x140009bb0  sub     rsp, 1A0h
0x140009bb7  mov     rax, cs:__security_cookie
0x140009bbe  xor     rax, rsp
0x140009bc1  mov     [rsp+1C8h+var_38], rax
0x140009bc9  xor     esi, esi
0x140009bcb  mov     [r11-120h], rsi
0x140009bd2  mov     [r11-130h], rsi
0x140009bd9  xorps   xmm0, xmm0
0x140009bdc  movups  xmmword ptr [rsp+1C8h+String1.Length], xmm0
0x140009be4  xorps   xmm1, xmm1
0x140009be7  movups  xmmword ptr [rsp+1C8h+var_88.Length], xmm1
0x140009bef  mov     [rsp+1C8h+FileNameInformation], rsi
0x140009bf4  mov     [r11-118h], rsi
0x140009bfb  movups  xmmword ptr [rsp+1C8h+IoStatusBlock], xmm0
0x140009c03  movups  xmmword ptr [r11-78h], xmm1
0x140009c08  xor     eax, eax
0x140009c0a  movups  xmmword ptr [rsp+1C8h+ObjectAttributes.Length], xmm0
0x140009c12  movups  xmmword ptr [rsp+1C8h+ObjectAttributes.ObjectName], xmm0
0x140009c1a  movups  xmmword ptr [rsp+1C8h+ObjectAttributes+1Ch], xmm0
0x140009c22  movups  xmmword ptr [rsp+1C8h+P], xmm0
0x140009c2a  mov     [r11-140h], rsi
0x140009c31  movups  xmmword ptr [rsp+1C8h+String2.Length], xmm1
0x140009c39  mov     [r11-138h], rsi
0x140009c40  mov     [r11-128h], rsi
0x140009c47  cmp     edx, 30h ; '0'
0x140009c4a  jnb     short loc_140009C56
0x140009c4c  mov     eax, 0C0000023h
0x140009c51  jmp     loc_14000A32D
0x140009c56  mov     r13, rsi
0x140009c59  mov     r15, [rcx]
0x140009c5c  mov     r12d, [rcx+8]
0x140009c60  mov     eax, [rcx+0Ch]
0x140009c63  mov     [rsp+1C8h+var_154], eax
0x140009c67  mov     eax, [rcx+10h]
0x140009c6a  mov     [rsp+1C8h+var_158], eax
0x140009c6e  movzx   ebx, word ptr [rcx+18h]
0x140009c72  mov     r14, [rcx+20h]
0x140009c76  mov     edi, [rcx+28h]
0x140009c79  call    Feature_AppSiloBfsProcessSetPolicyRequestBufferCheck__private_IsEnabledDeviceUsageNoInline
0x140009c7e  test    eax, eax
0x140009c80  jz      short loc_140009C91
0x140009c82  test    bl, 1
0x140009c85  jz      short loc_140009C91
0x140009c87  mov     eax, 0C000000Dh
0x140009c8c  jmp     loc_14000A32D
0x140009c91  mov     r8d, 2; Alignment
0x140009c97  mov     rdx, rbx; Length
0x140009c9a  mov     rcx, r14; Address
0x140009c9d  call    cs:__imp_ProbeForRead
0x140009ca4  nop     dword ptr [rax+rax+00h]
0x140009ca9  test    bx, bx
0x140009cac  jnz     short loc_140009CB8
0x140009cae  mov     eax, 0C0000206h
0x140009cb3  jmp     loc_14000A32D
0x140009cb8  mov     r8d, 50736642h
0x140009cbe  mov     rdx, rbx
0x140009cc1  mov     ecx, 100h
0x140009cc6  call    cs:__imp_ExAllocatePool2
0x140009ccd  nop     dword ptr [rax+rax+00h]
0x140009cd2  mov     [rsp+1C8h+P+8], rax
0x140009cda  test    rax, rax
0x140009cdd  jnz     short loc_140009CE9
0x140009cdf  mov     eax, 0C0000017h
0x140009ce4  jmp     loc_14000A32D
0x140009ce9  mov     word ptr [rsp+1C8h+P], bx
0x140009cf1  mov     word ptr [rsp+1C8h+P+2], bx
0x140009cf9  mov     r8, rbx; Size
0x140009cfc  mov     rdx, r14; Src
0x140009cff  mov     rcx, rax; void *
0x140009d02  call    memmove
0x140009d07  nop
0x140009d08  xor     r14d, r14d
0x140009d0b  mov     [rsp+1C8h+HandleInformation], r14; HandleInformation
0x140009d10  lea     rax, [rsp+1C8h+Token]
0x140009d18  mov     [rsp+1C8h+Object], rax; Object
0x140009d1d  mov     r9b, 1; AccessMode
0x140009d20  mov     r8, cs:__imp_SeTokenObjectType
0x140009d27  mov     r8, [r8]; ObjectType
0x140009d2a  lea     edx, [r14+8]; DesiredAccess
0x140009d2e  mov     rcx, r15; Handle
0x140009d31  call    cs:__imp_ObReferenceObjectByHandle
0x140009d38  nop     dword ptr [rax+rax+00h]
0x140009d3d  mov     ebx, eax
0x140009d3f  test    eax, eax
0x140009d41  jns     short loc_140009D60
0x140009d43  mov     ecx, cs:dword_140019000
0x140009d49  cmp     ecx, 3
0x140009d4c  jbe     loc_14000A22E
0x140009d52  mov     [rsp+1C8h+var_158], eax
0x140009d56  lea     rax, [rsp+1C8h+var_158]
0x140009d5b  jmp     loc_14000A201
0x140009d60  mov     dl, 1
0x140009d62  mov     rcx, [rsp+1C8h+Token]; Object
0x140009d6a  call    BfsIsApplicableToken
0x140009d6f  test    al, al
0x140009d71  jnz     short loc_140009D8D
0x140009d73  mov     ebx, 0C000A200h
0x140009d78  mov     eax, cs:dword_140019000
0x140009d7e  cmp     eax, 3
0x140009d81  jbe     loc_14000A22E
0x140009d87  mov     [rsp+1C8h+var_158], ebx
0x140009d8b  jmp     short loc_140009D56
0x140009d8d  lea     r8, [rsp+1C8h+TokenInformation]; TokenInformation
0x140009d95  mov     edx, 1; TokenInformationClass
0x140009d9a  mov     rcx, [rsp+1C8h+Token]; Token
0x140009da2  call    cs:__imp_SeQueryInformationToken
0x140009da9  nop     dword ptr [rax+rax+00h]
0x140009dae  mov     ebx, eax
0x140009db0  test    eax, eax
0x140009db2  js      short loc_140009D78
0x140009db4  lea     r8, [rsp+1C8h+var_120]; TokenInformation
0x140009dbc  mov     edx, 1Fh; TokenInformationClass
0x140009dc1  mov     rcx, [rsp+1C8h+Token]; Token
0x140009dc9  call    cs:__imp_SeQueryInformationToken
0x140009dd0  nop     dword ptr [rax+rax+00h]
0x140009dd5  mov     ebx, eax
0x140009dd7  test    eax, eax
0x140009dd9  js      short loc_140009D78
0x140009ddb  mov     sil, r14b
0x140009dde  mov     [rsp+1C8h+ObjectAttributes.Length], 30h ; '0'
0x140009de9  mov     [rsp+1C8h+ObjectAttributes.RootDirectory], r14
0x140009df1  mov     [rsp+1C8h+ObjectAttributes.Attributes], 600h
0x140009dfc  lea     rax, [rsp+1C8h+P]
0x140009e04  mov     [rsp+1C8h+ObjectAttributes.ObjectName], rax
0x140009e0c  xorps   xmm0, xmm0
0x140009e0f  movdqu  xmmword ptr [rsp+1C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140009e18  mov     eax, 21h ; '!'
0x140009e1d  lea     ecx, [rax+3Fh]
0x140009e20  cmp     r12d, 2
0x140009e24  cmovnz  eax, ecx
0x140009e27  mov     dword ptr [rsp+1C8h+HandleInformation], eax; OpenOptions
0x140009e2b  mov     dword ptr [rsp+1C8h+Object], 3; ShareAccess
0x140009e33  lea     r9, [rsp+1C8h+IoStatusBlock]; IoStatusBlock
0x140009e3b  lea     r8, [rsp+1C8h+ObjectAttributes]; ObjectAttributes
0x140009e43  mov     r15d, 80000000h
0x140009e49  mov     edx, r15d; DesiredAccess
0x140009e4c  lea     rcx, [rsp+1C8h+FileHandle]; FileHandle
0x140009e54  call    cs:__imp_ZwOpenFile
0x140009e5b  nop     dword ptr [rax+rax+00h]
0x140009e60  mov     ebx, eax
0x140009e62  cmp     eax, 0C0000034h
0x140009e67  jnz     short loc_140009ED8
0x140009e69  mov     [rsp+1C8h+Options], 104h; Options
0x140009e71  mov     [rsp+1C8h+InternalParameters], r14; InternalParameters
0x140009e76  mov     [rsp+1C8h+CreateFileType], r14d; CreateFileType
0x140009e7b  mov     [rsp+1C8h+EaLength], r14d; EaLength
0x140009e80  mov     [rsp+1C8h+EaBuffer], r14; EaBuffer
0x140009e85  mov     [rsp+1C8h+CreateOptions], 20h ; ' '; CreateOptions
0x140009e8d  mov     [rsp+1C8h+Disposition], 1; Disposition
0x140009e95  mov     [rsp+1C8h+ShareAccess], 7; ShareAccess
0x140009e9d  mov     dword ptr [rsp+1C8h+HandleInformation], 80h; FileAttributes
0x140009ea5  mov     [rsp+1C8h+Object], r14; AllocationSize
0x140009eaa  lea     r9, [rsp+1C8h+IoStatusBlock]; IoStatusBlock
0x140009eb2  lea     r8, [rsp+1C8h+ObjectAttributes]; ObjectAttributes
0x140009eba  mov     edx, 80100000h; DesiredAccess
0x140009ebf  lea     rcx, [rsp+1C8h+FileHandle]; FileHandle
0x140009ec7  call    cs:__imp_IoCreateFile
0x140009ece  nop     dword ptr [rax+rax+00h]
0x140009ed3  mov     ebx, eax
0x140009ed5  mov     sil, 1
0x140009ed8  test    ebx, ebx
0x140009eda  js      loc_140009D78
0x140009ee0  mov     [rsp+1C8h+HandleInformation], r14; HandleInformation
0x140009ee5  lea     rax, [rsp+1C8h+var_118]
0x140009eed  mov     [rsp+1C8h+Object], rax; Object
0x140009ef2  xor     r9d, r9d; AccessMode
0x140009ef5  mov     r8, cs:__imp_IoFileObjectType
0x140009efc  mov     r8, [r8]; ObjectType
0x140009eff  mov     edx, r15d; DesiredAccess
0x140009f02  mov     rcx, [rsp+1C8h+FileHandle]; Handle
0x140009f0a  call    cs:__imp_ObReferenceObjectByHandle
0x140009f11  nop     dword ptr [rax+rax+00h]
0x140009f16  mov     ebx, eax
0x140009f18  test    eax, eax
0x140009f1a  js      loc_140009D78
0x140009f20  lea     r9, [rsp+1C8h+FileNameInformation]; FileNameInformation
0x140009f25  xor     edx, edx; Instance
0x140009f27  mov     r8d, 101h; NameOptions
0x140009f2d  mov     rcx, [rsp+1C8h+var_118]; FileObject
0x140009f35  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140009f3c  nop     dword ptr [rax+rax+00h]
0x140009f41  mov     ebx, eax
0x140009f43  test    eax, eax
0x140009f45  js      loc_140009D78
0x140009f4b  mov     rdx, [rsp+1C8h+FileNameInformation]
0x140009f50  lea     rcx, [rsp+1C8h+var_E8]
0x140009f58  call    BfsGetFileName
0x140009f5d  movups  xmm1, xmmword ptr [rax]
0x140009f60  movdqu  xmmword ptr [rsp+1C8h+String1.Length], xmm1
0x140009f69  mov     rdx, [rsp+1C8h+FileNameInformation]
0x140009f6e  lea     rcx, [rsp+1C8h+var_E8]
0x140009f76  call    BfsGetShareName
0x140009f7b  movups  xmm1, xmmword ptr [rax]
0x140009f7e  movdqu  xmmword ptr [rsp+1C8h+String2.Length], xmm1
0x140009f87  test    sil, sil
0x140009f8a  jz      short loc_140009FEE
0x140009f8c  lea     rdx, [rsp+1C8h+P]
0x140009f94  lea     rcx, [rsp+1C8h+var_E8]
0x140009f9c  call    BfsGetFinalPathComponent
0x140009fa1  movups  xmm1, xmmword ptr [rax]
0x140009fa4  movups  xmmword ptr [rsp+1C8h+var_88.Length], xmm1
0x140009fac  movd    eax, xmm1
0x140009fb0  test    ax, ax
0x140009fb3  jnz     short loc_140009FBF
0x140009fb5  mov     ebx, 0C000003Ah
0x140009fba  jmp     loc_140009D78
0x140009fbf  lea     r8, [rsp+1C8h+String1]
0x140009fc7  lea     rdx, [rsp+1C8h+var_88]; PCUNICODE_STRING
0x140009fcf  lea     rcx, [rsp+1C8h+String1]; Source
0x140009fd7  call    BfsAllocateAndConcatenatePath
0x140009fdc  mov     ebx, eax
0x140009fde  test    eax, eax
0x140009fe0  js      loc_140009D78
0x140009fe6  mov     r13, [rsp+1C8h+String1.Buffer]
0x140009fee  lea     rax, [rsp+1C8h+var_140]
0x140009ff6  mov     [rsp+1C8h+HandleInformation], rax
0x140009ffb  mov     rax, [rsp+1C8h+var_120]
0x14000a003  mov     rcx, [rax]
0x14000a006  mov     [rsp+1C8h+Object], rcx
0x14000a00b  mov     r9, [rsp+1C8h+TokenInformation]
0x14000a013  mov     r9, [r9]
0x14000a016  lea     r8, gBfsPolicyTable
0x14000a01d  xor     edx, edx
0x14000a01f  mov     rcx, cs:gBfsFilterHandle
0x14000a026  call    BfsGetPolicyEntry
0x14000a02b  mov     ebx, eax
0x14000a02d  test    eax, eax
0x14000a02f  js      loc_140009D78
0x14000a035  test    edi, edi
0x14000a037  jz      short loc_14000A07B
0x14000a039  sub     edi, 1
0x14000a03c  jz      short loc_14000A07B
0x14000a03e  cmp     edi, 1
0x14000a041  jnz     loc_14000A22E
0x14000a047  mov     r8, [rsp+1C8h+FileNameInformation]
0x14000a04c  add     r8, 18h
0x14000a050  lea     r9, [rsp+1C8h+String1]
0x14000a058  mov     edx, r12d
0x14000a05b  mov     rcx, [rsp+1C8h+var_140]
0x14000a063  mov     rcx, [rcx+30h]
0x14000a067  call    BfsDeleteEntry
0x14000a06c  mov     ebx, eax
0x14000a06e  test    eax, eax
0x14000a070  jns     loc_14000A22E
0x14000a076  jmp     loc_140009D78
0x14000a07b  cmp     [rsp+1C8h+String2.Buffer], r14
0x14000a083  jz      loc_14000A131
0x14000a089  mov     r8b, 1; CaseInSensitive
0x14000a08c  lea     rdx, [rsp+1C8h+String2]; String2
0x14000a094  lea     rcx, [rsp+1C8h+String1]; String1
0x14000a09c  call    cs:__imp_RtlCompareUnicodeString
0x14000a0a3  nop     dword ptr [rax+rax+00h]
0x14000a0a8  test    eax, eax
0x14000a0aa  jz      loc_14000A131
0x14000a0b0  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14000a0b5  mov     rdx, [rsp+1C8h+FileNameInformation]
0x14000a0ba  lea     r8, [rsp+1C8h+String2]
0x14000a0c2  mov     rcx, [rsp+1C8h+var_140]
0x14000a0ca  add     rdx, 18h
0x14000a0ce  mov     rcx, [rcx+30h]
0x14000a0d2  test    eax, eax
0x14000a0d4  jz      short loc_14000A0E0
0x14000a0d6  lea     r9, [rsp+1C8h+var_148]
0x14000a0de  jmp     short loc_14000A0E3
0x14000a0e0  xor     r9d, r9d
0x14000a0e3  call    BfsGetPolicy
0x14000a0e8  dec     eax
0x14000a0ea  cmp     eax, 1
0x14000a0ed  jbe     short loc_14000A131
0x14000a0ef  mov     rax, [rsp+1C8h+FileNameInformation]
0x14000a0f4  add     rax, 18h
0x14000a0f8  lea     rcx, [rsp+1C8h+String2]
0x14000a100  mov     [rsp+1C8h+HandleInformation], rcx
0x14000a105  mov     [rsp+1C8h+Object], rax
0x14000a10a  xor     r9d, r9d
0x14000a10d  lea     eax, [r9+2]
0x14000a111  mov     r8d, eax
0x14000a114  mov     edx, eax
0x14000a116  mov     rcx, [rsp+1C8h+var_140]
0x14000a11e  mov     rcx, [rcx+30h]
0x14000a122  call    BfsAddOrModifyEntry
0x14000a127  mov     ebx, eax
0x14000a129  test    eax, eax
0x14000a12b  js      loc_140009D78
0x14000a131  mov     rax, [rsp+1C8h+FileNameInformation]
0x14000a136  add     rax, 18h
0x14000a13a  lea     rcx, [rsp+1C8h+String1]
0x14000a142  mov     [rsp+1C8h+HandleInformation], rcx
0x14000a147  mov     [rsp+1C8h+Object], rax
0x14000a14c  mov     r9d, [rsp+1C8h+var_158]
0x14000a151  mov     r8d, [rsp+1C8h+var_154]
0x14000a156  mov     edx, r12d
  ... truncated ...
```
