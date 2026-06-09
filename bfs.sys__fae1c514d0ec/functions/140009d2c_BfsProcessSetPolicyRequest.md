# BfsProcessSetPolicyRequest

- ea: `0x140009d2c`
- end: `0x14000a4eb`
- name: `BfsProcessSetPolicyRequest`
- size: `1983`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140003770`

## callees

- `0x140001008`
- `0x140003340`
- `0x140003614`
- `0x140005150`
- `0x1400061d0`
- `0x140006c84`
- `0x140006d20`
- `0x140006fa4`
- `0x1400071d4`
- `0x1400077a4`
- `0x140009d2c`
- `0x14000b470`
- `0x14000c0f4`
- `0x1400104ec`
- `0x140011194`
- `0x140013860`
- `0x140013980`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009ec1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a09a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009ec1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000a09a`
- `ntoskrnl!SeTokenObjectType` at `0x140009eb0`
- `ntoskrnl!IoCreateFile` at `0x14000a057`
- `ntoskrnl!IoCreateFile` at `0x14000a057`
- `ntoskrnl!IoFileObjectType` at `0x14000a085`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a22c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a22c`
- `ntoskrnl!ZwOpenFile` at `0x140009fe4`
- `ntoskrnl!ZwOpenFile` at `0x140009fe4`
- `ntoskrnl!ZwClose` at `0x14000a426`
- `ntoskrnl!ZwClose` at `0x14000a426`
- `ntoskrnl!ProbeForRead` at `0x140009e2d`
- `ntoskrnl!ProbeForRead` at `0x140009e2d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a43f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a458`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a43f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a458`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a40d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a473`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a48e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a4af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a40d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a473`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a48e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a4af`
- `ntoskrnl!SeQueryInformationToken` at `0x140009f32`
- `ntoskrnl!SeQueryInformationToken` at `0x140009f59`
- `ntoskrnl!SeQueryInformationToken` at `0x140009f32`
- `ntoskrnl!SeQueryInformationToken` at `0x140009f59`
- `ntoskrnl!ExAllocatePool2` at `0x140009e56`
- `ntoskrnl!ExAllocatePool2` at `0x140009e56`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a3f2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000a3f2`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000a0c5`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14000a0c5`

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
  int FileNameInformationUnsafe; // ebx
  int v14; // ecx
  NTSTATUS *v15; // rax
  char v16; // si
  ULONG v17; // eax
  int v18; // edi
  __int64 v19; // rcx
  char *v20; // r9
  int Object; // [rsp+20h] [rbp-1A8h]
  NTSTATUS v22; // [rsp+70h] [rbp-158h] BYREF
  int v23; // [rsp+74h] [rbp-154h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp-150h] BYREF
  char v25; // [rsp+80h] [rbp-148h] BYREF
  PVOID v26; // [rsp+88h] [rbp-140h] BYREF
  PVOID Token; // [rsp+90h] [rbp-138h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-130h] BYREF
  PVOID TokenInformation; // [rsp+A0h] [rbp-128h] BYREF
  PVOID v30; // [rsp+A8h] [rbp-120h] BYREF
  PVOID v31; // [rsp+B0h] [rbp-118h] BYREF
  UNICODE_STRING String1; // [rsp+B8h] [rbp-110h] BYREF
  PVOID P[2]; // [rsp+C8h] [rbp-100h] BYREF
  UNICODE_STRING v34; // [rsp+E0h] [rbp-E8h] BYREF
  UNICODE_STRING String2; // [rsp+F0h] [rbp-D8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp-C8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+130h] [rbp-98h] BYREF
  UNICODE_STRING v38; // [rsp+140h] [rbp-88h] BYREF
  UNICODE_STRING v39; // [rsp+150h] [rbp-78h] BYREF
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
      tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140016D91, v11, v12, Object, &v40);
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  if ( !(unsigned __int8)BfsIsApplicableToken(Token) )
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
              FileNameInformationUnsafe = BfsGetPolicyEntry(
                                            (int)gBfsFilterHandle,
                                            0,
                                            (__int64)&gBfsPolicyTable,
                                            *(void **)TokenInformation,
                                            *(PSID *)v30,
                                            (__int64 *)&v26);
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
                    v34.Buffer = FileNameInformation->Name.Buffer;
                    v34.Length = FileNameInformation->Name.Length - FileNameInformation->Stream.Length;
                    v34.MaximumLength = v34.Length;
                    v39 = v34;
                    Object = v5;
                    FileNameInformationUnsafe = BfsAddPolicyToGlobalFileTable(
                                                  (__int64)&gBfsGlobalFileTable,
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
    BfsDereferencePolicyEntryEx((char *)v26, 0);
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
0x140009d2c  mov     r11, rsp
0x140009d2f  mov     [r11+10h], rbx
0x140009d33  mov     [r11+18h], rsi
0x140009d37  push    rdi
0x140009d38  push    r12
0x140009d3a  push    r13
0x140009d3c  push    r14
0x140009d3e  push    r15
0x140009d40  sub     rsp, 1A0h
0x140009d47  mov     rax, cs:__security_cookie
0x140009d4e  xor     rax, rsp
0x140009d51  mov     [rsp+1C8h+var_38], rax
0x140009d59  xor     esi, esi
0x140009d5b  mov     [r11-120h], rsi
0x140009d62  mov     [r11-130h], rsi
0x140009d69  xorps   xmm0, xmm0
0x140009d6c  movups  xmmword ptr [rsp+1C8h+String1.Length], xmm0
0x140009d74  xorps   xmm1, xmm1
0x140009d77  movups  xmmword ptr [rsp+1C8h+var_88.Length], xmm1
0x140009d7f  mov     [rsp+1C8h+FileNameInformation], rsi
0x140009d84  mov     [r11-118h], rsi
0x140009d8b  movups  xmmword ptr [rsp+1C8h+IoStatusBlock], xmm0
0x140009d93  movups  xmmword ptr [r11-78h], xmm1
0x140009d98  xor     eax, eax
0x140009d9a  movups  xmmword ptr [rsp+1C8h+ObjectAttributes.Length], xmm0
0x140009da2  movups  xmmword ptr [rsp+1C8h+ObjectAttributes.ObjectName], xmm0
0x140009daa  movups  xmmword ptr [rsp+1C8h+ObjectAttributes+1Ch], xmm0
0x140009db2  movups  xmmword ptr [rsp+1C8h+P], xmm0
0x140009dba  mov     [r11-140h], rsi
0x140009dc1  movups  xmmword ptr [rsp+1C8h+String2.Length], xmm1
0x140009dc9  mov     [r11-138h], rsi
0x140009dd0  mov     [r11-128h], rsi
0x140009dd7  cmp     edx, 30h ; '0'
0x140009dda  jnb     short loc_140009DE6
0x140009ddc  mov     eax, 0C0000023h
0x140009de1  jmp     loc_14000A4BD
0x140009de6  mov     r13, rsi
0x140009de9  mov     r15, [rcx]
0x140009dec  mov     r12d, [rcx+8]
0x140009df0  mov     eax, [rcx+0Ch]
0x140009df3  mov     [rsp+1C8h+var_154], eax
0x140009df7  mov     eax, [rcx+10h]
0x140009dfa  mov     [rsp+1C8h+var_158], eax
0x140009dfe  movzx   ebx, word ptr [rcx+18h]
0x140009e02  mov     r14, [rcx+20h]
0x140009e06  mov     edi, [rcx+28h]
0x140009e09  call    Feature_AppSiloBfsProcessSetPolicyRequestBufferCheck__private_IsEnabledDeviceUsageNoInline
0x140009e0e  test    eax, eax
0x140009e10  jz      short loc_140009E21
0x140009e12  test    bl, 1
0x140009e15  jz      short loc_140009E21
0x140009e17  mov     eax, 0C000000Dh
0x140009e1c  jmp     loc_14000A4BD
0x140009e21  mov     r8d, 2; Alignment
0x140009e27  mov     rdx, rbx; Length
0x140009e2a  mov     rcx, r14; Address
0x140009e2d  call    cs:__imp_ProbeForRead
0x140009e34  nop     dword ptr [rax+rax+00h]
0x140009e39  test    bx, bx
0x140009e3c  jnz     short loc_140009E48
0x140009e3e  mov     eax, 0C0000206h
0x140009e43  jmp     loc_14000A4BD
0x140009e48  mov     r8d, 50736642h
0x140009e4e  mov     rdx, rbx
0x140009e51  mov     ecx, 100h
0x140009e56  call    cs:__imp_ExAllocatePool2
0x140009e5d  nop     dword ptr [rax+rax+00h]
0x140009e62  mov     [rsp+1C8h+P+8], rax
0x140009e6a  test    rax, rax
0x140009e6d  jnz     short loc_140009E79
0x140009e6f  mov     eax, 0C0000017h
0x140009e74  jmp     loc_14000A4BD
0x140009e79  mov     word ptr [rsp+1C8h+P], bx
0x140009e81  mov     word ptr [rsp+1C8h+P+2], bx
0x140009e89  mov     r8, rbx; Size
0x140009e8c  mov     rdx, r14; Src
0x140009e8f  mov     rcx, rax; void *
0x140009e92  call    memmove
0x140009e97  nop
0x140009e98  xor     r14d, r14d
0x140009e9b  mov     [rsp+1C8h+HandleInformation], r14; HandleInformation
0x140009ea0  lea     rax, [rsp+1C8h+Token]
0x140009ea8  mov     [rsp+1C8h+Object], rax; Object
0x140009ead  mov     r9b, 1; AccessMode
0x140009eb0  mov     r8, cs:__imp_SeTokenObjectType
0x140009eb7  mov     r8, [r8]; ObjectType
0x140009eba  lea     edx, [r14+8]; DesiredAccess
0x140009ebe  mov     rcx, r15; Handle
0x140009ec1  call    cs:__imp_ObReferenceObjectByHandle
0x140009ec8  nop     dword ptr [rax+rax+00h]
0x140009ecd  mov     ebx, eax
0x140009ecf  test    eax, eax
0x140009ed1  jns     short loc_140009EF0
0x140009ed3  mov     ecx, cs:dword_140019000
0x140009ed9  cmp     ecx, 3
0x140009edc  jbe     loc_14000A3BE
0x140009ee2  mov     [rsp+1C8h+var_158], eax
0x140009ee6  lea     rax, [rsp+1C8h+var_158]
0x140009eeb  jmp     loc_14000A391
0x140009ef0  mov     dl, 1
0x140009ef2  mov     rcx, [rsp+1C8h+Token]; Object
0x140009efa  call    BfsIsApplicableToken
0x140009eff  test    al, al
0x140009f01  jnz     short loc_140009F1D
0x140009f03  mov     ebx, 0C000A200h
0x140009f08  mov     eax, cs:dword_140019000
0x140009f0e  cmp     eax, 3
0x140009f11  jbe     loc_14000A3BE
0x140009f17  mov     [rsp+1C8h+var_158], ebx
0x140009f1b  jmp     short loc_140009EE6
0x140009f1d  lea     r8, [rsp+1C8h+TokenInformation]; TokenInformation
0x140009f25  mov     edx, 1; TokenInformationClass
0x140009f2a  mov     rcx, [rsp+1C8h+Token]; Token
0x140009f32  call    cs:__imp_SeQueryInformationToken
0x140009f39  nop     dword ptr [rax+rax+00h]
0x140009f3e  mov     ebx, eax
0x140009f40  test    eax, eax
0x140009f42  js      short loc_140009F08
0x140009f44  lea     r8, [rsp+1C8h+var_120]; TokenInformation
0x140009f4c  mov     edx, 1Fh; TokenInformationClass
0x140009f51  mov     rcx, [rsp+1C8h+Token]; Token
0x140009f59  call    cs:__imp_SeQueryInformationToken
0x140009f60  nop     dword ptr [rax+rax+00h]
0x140009f65  mov     ebx, eax
0x140009f67  test    eax, eax
0x140009f69  js      short loc_140009F08
0x140009f6b  mov     sil, r14b
0x140009f6e  mov     [rsp+1C8h+ObjectAttributes.Length], 30h ; '0'
0x140009f79  mov     [rsp+1C8h+ObjectAttributes.RootDirectory], r14
0x140009f81  mov     [rsp+1C8h+ObjectAttributes.Attributes], 600h
0x140009f8c  lea     rax, [rsp+1C8h+P]
0x140009f94  mov     [rsp+1C8h+ObjectAttributes.ObjectName], rax
0x140009f9c  xorps   xmm0, xmm0
0x140009f9f  movdqu  xmmword ptr [rsp+1C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140009fa8  mov     eax, 21h ; '!'
0x140009fad  lea     ecx, [rax+3Fh]
0x140009fb0  cmp     r12d, 2
0x140009fb4  cmovnz  eax, ecx
0x140009fb7  mov     dword ptr [rsp+1C8h+HandleInformation], eax; OpenOptions
0x140009fbb  mov     dword ptr [rsp+1C8h+Object], 3; ShareAccess
0x140009fc3  lea     r9, [rsp+1C8h+IoStatusBlock]; IoStatusBlock
0x140009fcb  lea     r8, [rsp+1C8h+ObjectAttributes]; ObjectAttributes
0x140009fd3  mov     r15d, 80000000h
0x140009fd9  mov     edx, r15d; DesiredAccess
0x140009fdc  lea     rcx, [rsp+1C8h+FileHandle]; FileHandle
0x140009fe4  call    cs:__imp_ZwOpenFile
0x140009feb  nop     dword ptr [rax+rax+00h]
0x140009ff0  mov     ebx, eax
0x140009ff2  cmp     eax, 0C0000034h
0x140009ff7  jnz     short loc_14000A068
0x140009ff9  mov     [rsp+1C8h+Options], 104h; Options
0x14000a001  mov     [rsp+1C8h+InternalParameters], r14; InternalParameters
0x14000a006  mov     [rsp+1C8h+CreateFileType], r14d; CreateFileType
0x14000a00b  mov     [rsp+1C8h+EaLength], r14d; EaLength
0x14000a010  mov     [rsp+1C8h+EaBuffer], r14; EaBuffer
0x14000a015  mov     [rsp+1C8h+CreateOptions], 20h ; ' '; CreateOptions
0x14000a01d  mov     [rsp+1C8h+Disposition], 1; Disposition
0x14000a025  mov     [rsp+1C8h+ShareAccess], 7; ShareAccess
0x14000a02d  mov     dword ptr [rsp+1C8h+HandleInformation], 80h; FileAttributes
0x14000a035  mov     [rsp+1C8h+Object], r14; AllocationSize
0x14000a03a  lea     r9, [rsp+1C8h+IoStatusBlock]; IoStatusBlock
0x14000a042  lea     r8, [rsp+1C8h+ObjectAttributes]; ObjectAttributes
0x14000a04a  mov     edx, 80100000h; DesiredAccess
0x14000a04f  lea     rcx, [rsp+1C8h+FileHandle]; FileHandle
0x14000a057  call    cs:__imp_IoCreateFile
0x14000a05e  nop     dword ptr [rax+rax+00h]
0x14000a063  mov     ebx, eax
0x14000a065  mov     sil, 1
0x14000a068  test    ebx, ebx
0x14000a06a  js      loc_140009F08
0x14000a070  mov     [rsp+1C8h+HandleInformation], r14; HandleInformation
0x14000a075  lea     rax, [rsp+1C8h+var_118]
0x14000a07d  mov     [rsp+1C8h+Object], rax; Object
0x14000a082  xor     r9d, r9d; AccessMode
0x14000a085  mov     r8, cs:__imp_IoFileObjectType
0x14000a08c  mov     r8, [r8]; ObjectType
0x14000a08f  mov     edx, r15d; DesiredAccess
0x14000a092  mov     rcx, [rsp+1C8h+FileHandle]; Handle
0x14000a09a  call    cs:__imp_ObReferenceObjectByHandle
0x14000a0a1  nop     dword ptr [rax+rax+00h]
0x14000a0a6  mov     ebx, eax
0x14000a0a8  test    eax, eax
0x14000a0aa  js      loc_140009F08
0x14000a0b0  lea     r9, [rsp+1C8h+FileNameInformation]; FileNameInformation
0x14000a0b5  xor     edx, edx; Instance
0x14000a0b7  mov     r8d, 101h; NameOptions
0x14000a0bd  mov     rcx, [rsp+1C8h+var_118]; FileObject
0x14000a0c5  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14000a0cc  nop     dword ptr [rax+rax+00h]
0x14000a0d1  mov     ebx, eax
0x14000a0d3  test    eax, eax
0x14000a0d5  js      loc_140009F08
0x14000a0db  mov     rdx, [rsp+1C8h+FileNameInformation]
0x14000a0e0  lea     rcx, [rsp+1C8h+var_E8]
0x14000a0e8  call    BfsGetFileName
0x14000a0ed  movups  xmm1, xmmword ptr [rax]
0x14000a0f0  movdqu  xmmword ptr [rsp+1C8h+String1.Length], xmm1
0x14000a0f9  mov     rdx, [rsp+1C8h+FileNameInformation]
0x14000a0fe  lea     rcx, [rsp+1C8h+var_E8]
0x14000a106  call    BfsGetShareName
0x14000a10b  movups  xmm1, xmmword ptr [rax]
0x14000a10e  movdqu  xmmword ptr [rsp+1C8h+String2.Length], xmm1
0x14000a117  test    sil, sil
0x14000a11a  jz      short loc_14000A17E
0x14000a11c  lea     rdx, [rsp+1C8h+P]
0x14000a124  lea     rcx, [rsp+1C8h+var_E8]
0x14000a12c  call    BfsGetFinalPathComponent
0x14000a131  movups  xmm1, xmmword ptr [rax]
0x14000a134  movups  xmmword ptr [rsp+1C8h+var_88.Length], xmm1
0x14000a13c  movd    eax, xmm1
0x14000a140  test    ax, ax
0x14000a143  jnz     short loc_14000A14F
0x14000a145  mov     ebx, 0C000003Ah
0x14000a14a  jmp     loc_140009F08
0x14000a14f  lea     r8, [rsp+1C8h+String1]
0x14000a157  lea     rdx, [rsp+1C8h+var_88]; PCUNICODE_STRING
0x14000a15f  lea     rcx, [rsp+1C8h+String1]; Source
0x14000a167  call    BfsAllocateAndConcatenatePath
0x14000a16c  mov     ebx, eax
0x14000a16e  test    eax, eax
0x14000a170  js      loc_140009F08
0x14000a176  mov     r13, [rsp+1C8h+String1.Buffer]
0x14000a17e  lea     rax, [rsp+1C8h+var_140]
0x14000a186  mov     [rsp+1C8h+HandleInformation], rax
0x14000a18b  mov     rax, [rsp+1C8h+var_120]
0x14000a193  mov     rcx, [rax]
0x14000a196  mov     [rsp+1C8h+Object], rcx
0x14000a19b  mov     r9, [rsp+1C8h+TokenInformation]
0x14000a1a3  mov     r9, [r9]
0x14000a1a6  lea     r8, gBfsPolicyTable
0x14000a1ad  xor     edx, edx
0x14000a1af  mov     rcx, cs:gBfsFilterHandle
0x14000a1b6  call    BfsGetPolicyEntry
0x14000a1bb  mov     ebx, eax
0x14000a1bd  test    eax, eax
0x14000a1bf  js      loc_140009F08
0x14000a1c5  test    edi, edi
0x14000a1c7  jz      short loc_14000A20B
0x14000a1c9  sub     edi, 1
0x14000a1cc  jz      short loc_14000A20B
0x14000a1ce  cmp     edi, 1
0x14000a1d1  jnz     loc_14000A3BE
0x14000a1d7  mov     r8, [rsp+1C8h+FileNameInformation]
0x14000a1dc  add     r8, 18h
0x14000a1e0  lea     r9, [rsp+1C8h+String1]
0x14000a1e8  mov     edx, r12d
0x14000a1eb  mov     rcx, [rsp+1C8h+var_140]
0x14000a1f3  mov     rcx, [rcx+30h]
0x14000a1f7  call    BfsDeleteEntry
0x14000a1fc  mov     ebx, eax
0x14000a1fe  test    eax, eax
0x14000a200  jns     loc_14000A3BE
0x14000a206  jmp     loc_140009F08
0x14000a20b  cmp     [rsp+1C8h+String2.Buffer], r14
0x14000a213  jz      loc_14000A2C1
0x14000a219  mov     r8b, 1; CaseInSensitive
0x14000a21c  lea     rdx, [rsp+1C8h+String2]; String2
0x14000a224  lea     rcx, [rsp+1C8h+String1]; String1
0x14000a22c  call    cs:__imp_RtlCompareUnicodeString
0x14000a233  nop     dword ptr [rax+rax+00h]
0x14000a238  test    eax, eax
0x14000a23a  jz      loc_14000A2C1
0x14000a240  call    Feature_AgenticAppContainerBfsSupport__private_IsEnabledDeviceUsageNoInline
0x14000a245  mov     rdx, [rsp+1C8h+FileNameInformation]
0x14000a24a  lea     r8, [rsp+1C8h+String2]
0x14000a252  mov     rcx, [rsp+1C8h+var_140]
0x14000a25a  add     rdx, 18h
0x14000a25e  mov     rcx, [rcx+30h]
0x14000a262  test    eax, eax
0x14000a264  jz      short loc_14000A270
0x14000a266  lea     r9, [rsp+1C8h+var_148]
0x14000a26e  jmp     short loc_14000A273
0x14000a270  xor     r9d, r9d
0x14000a273  call    BfsGetPolicy
0x14000a278  dec     eax
0x14000a27a  cmp     eax, 1
0x14000a27d  jbe     short loc_14000A2C1
0x14000a27f  mov     rax, [rsp+1C8h+FileNameInformation]
0x14000a284  add     rax, 18h
0x14000a288  lea     rcx, [rsp+1C8h+String2]
0x14000a290  mov     [rsp+1C8h+HandleInformation], rcx
0x14000a295  mov     [rsp+1C8h+Object], rax
0x14000a29a  xor     r9d, r9d
0x14000a29d  lea     eax, [r9+2]
0x14000a2a1  mov     r8d, eax
0x14000a2a4  mov     edx, eax
0x14000a2a6  mov     rcx, [rsp+1C8h+var_140]
0x14000a2ae  mov     rcx, [rcx+30h]
0x14000a2b2  call    BfsAddOrModifyEntry
0x14000a2b7  mov     ebx, eax
0x14000a2b9  test    eax, eax
0x14000a2bb  js      loc_140009F08
0x14000a2c1  mov     rax, [rsp+1C8h+FileNameInformation]
0x14000a2c6  add     rax, 18h
0x14000a2ca  lea     rcx, [rsp+1C8h+String1]
0x14000a2d2  mov     [rsp+1C8h+HandleInformation], rcx
0x14000a2d7  mov     [rsp+1C8h+Object], rax
0x14000a2dc  mov     r9d, [rsp+1C8h+var_158]
0x14000a2e1  mov     r8d, [rsp+1C8h+var_154]
0x14000a2e6  mov     edx, r12d
  ... truncated ...
```
