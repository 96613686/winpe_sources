# AslFileMappingCreate

- ea: `0x180020570`
- end: `0x180020869`
- name: `AslFileMappingCreate`
- size: `761`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18011aa44`
- `0x1801b2224`
- `0x1801b2fa8`
- `0x1801b43b0`
- `0x1801b63b0`
- `0x1801b6e90`
- `0x1801b73d0`
- `0x1801be108`
- `0x1801fcdf0`
- `0x180215fd0`

## callees

- `0x180008570`
- `0x1800091d4`
- `0x18001a2f4`
- `0x18001b860`
- `0x180020570`
- `0x180020870`

## import_xrefs

- `ntdll!ZwQueryInformationFile` at `0x1800207d7`
- `ntdll!ZwQueryInformationFile` at `0x1800207d7`
- `ntdll!ZwCreateFile` at `0x1800206fc`
- `ntdll!ZwCreateFile` at `0x1800206fc`
- `ntdll!RtlFreeUnicodeString` at `0x180020837`
- `ntdll!RtlFreeUnicodeString` at `0x180020837`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180020658`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180020658`
- `ntdll!ZwClose` at `0x180020729`
- `ntdll!ZwClose` at `0x180020729`
- `ntdll!RtlAllocateHeap` at `0x1800205f7`
- `ntdll!RtlAllocateHeap` at `0x1800205f7`
- `ntdll!RtlInitUnicodeString` at `0x1800205da`
- `ntdll!RtlInitUnicodeString` at `0x1800205da`

## string_xrefs

- `0x180020668`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18002067a`: `AslFileMappingCreate`
- `0x1800207f0`: `AslFileMappingCreate`
- `0x18002077e`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180020794`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(_QWORD *a1, const WCHAR *a2)
{
  PVOID Heap; // rax
  PVOID v5; // rsi
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  void *v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-A1h]
  __int64 FileAttributes; // [rsp+28h] [rbp-99h]
  void *FileHandle; // [rsp+60h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK v21; // [rsp+78h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-9h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp+7h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+17h]

  v25 = 0;
  FileInformation = 0;
  DestinationString = 0;
  v21 = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v5 = Heap;
  if ( Heap )
  {
    v7 = AslStringDuplicate(Heap, a2);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = "AslStringDuplicate failed [%x]";
      v9 = 123;
LABEL_29:
      LODWORD(AllocationSize) = v7;
      AslLogCallPrintf(1, "AslFileMappingCreate", v9, v8, AllocationSize);
      goto LABEL_30;
    }
    if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu)
      && (v10 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v6 = v10, v10 < 0) )
    {
      LODWORD(FileAttributes) = v10;
      v11 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v12 = 148;
    }
    else
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      IoStatusBlock = 0;
      FileHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 5u, 1u, 0x60u, 0, 0);
      if ( v6 < 0 )
      {
        v13 = FileHandle;
      }
      else
      {
        v13 = 0;
        *((_QWORD *)v5 + 1) = FileHandle;
        v6 = 0;
        FileHandle = 0;
        *((_BYTE *)v5 + 48) = 1;
      }
      if ( v13 )
        ZwClose(v13);
      if ( v6 >= 0 )
      {
        v25 = 0;
        v21 = 0;
        FileInformation = 0;
        v7 = ZwQueryInformationFile(*((HANDLE *)v5 + 1), &v21, &FileInformation, 0x18u, FileStandardInformation);
        v6 = v7;
        if ( v7 >= 0 )
        {
          v6 = 0;
          *((_QWORD *)v5 + 3) = *((_QWORD *)&FileInformation + 1);
          *((_DWORD *)v5 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
          *a1 = v5;
          goto LABEL_32;
        }
        v8 = "NtQueryInformationFile failed [%x]";
        v9 = 183;
        goto LABEL_29;
      }
      if ( v6 == -1073741766 || v6 == -1073741772 || v6 == -1073741620 )
        goto LABEL_30;
      v14 = (unsigned int)(v6 + 1073741805);
      if ( (unsigned int)v14 <= 0x30 && (v15 = 0x1000000008001LL, _bittest64(&v15, v14)) || v6 == -1073741638 )
      {
        LODWORD(FileAttributes) = v6;
        AslLogCallPrintf(
          3,
          "AslFileMappingCreate",
          163,
          "RtlFileMapInitializeByFilePath failed %S [%x]",
          a2,
          FileAttributes);
LABEL_30:
        AslFileMappingDelete(v5);
        goto LABEL_32;
      }
      LODWORD(FileAttributes) = v6;
      v11 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v12 = 161;
    }
    AslLogCallPrintf(1, "AslFileMappingCreate", v12, v11, a2, FileAttributes);
    goto LABEL_30;
  }
  v6 = -1073741801;
LABEL_32:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020570  mov     [rsp-8+arg_10], rbx
0x180020575  push    rbp
0x180020576  push    rsi
0x180020577  push    rdi
0x180020578  push    r12
0x18002057a  push    r15
0x18002057c  lea     rbp, [rsp-2Fh]
0x180020581  sub     rsp, 0F0h
0x180020588  mov     rax, cs:__security_cookie
0x18002058f  xor     rax, rsp
0x180020592  mov     [rbp+4Fh+var_30], rax
0x180020596  xor     eax, eax
0x180020598  xorps   xmm0, xmm0
0x18002059b  xor     r12d, r12d
0x18002059e  mov     [rbp+4Fh+var_38], rax
0x1800205a2  xorps   xmm1, xmm1
0x1800205a5  mov     rdi, rdx
0x1800205a8  mov     r15, rcx
0x1800205ab  movups  [rbp+4Fh+FileInformation], xmm0
0x1800205af  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800205b3  movups  xmmword ptr [rbp+4Fh+var_98], xmm1
0x1800205b7  test    rdx, rdx
0x1800205ba  jz      loc_180020841
0x1800205c0  cmp     [rdx], r12w
0x1800205c4  jz      loc_180020841
0x1800205ca  test    rcx, rcx
0x1800205cd  jz      loc_180020841
0x1800205d3  mov     [rcx], r12
0x1800205d6  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800205da  call    cs:__imp_RtlInitUnicodeString
0x1800205e0  mov     rcx, gs:60h
0x1800205e9  lea     edx, [r12+8]; Flags
0x1800205ee  lea     r8d, [r12+50h]; Size
0x1800205f3  mov     rcx, [rcx+30h]; HeapHandle
0x1800205f7  call    cs:__imp_RtlAllocateHeap
0x1800205fd  mov     rsi, rax
0x180020600  test    rax, rax
0x180020603  jnz     short loc_18002060F
0x180020605  mov     ebx, 0C0000017h
0x18002060a  jmp     loc_18002082D
0x18002060f  mov     rdx, rdi
0x180020612  mov     rcx, rsi
0x180020615  call    AslStringDuplicate
0x18002061a  mov     ebx, eax
0x18002061c  test    eax, eax
0x18002061e  jns     short loc_180020632
0x180020620  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x180020627  mov     r8d, 7Bh ; '{'
0x18002062d  jmp     loc_1800207F0
0x180020632  mov     r8d, 0Ch; MaxCount
0x180020638  lea     rdx, aSystemroot_4; "\\SystemRoot\\"
0x18002063f  mov     rcx, rdi; String1
0x180020642  call    _wcsnicmp
0x180020647  test    eax, eax
0x180020649  jz      short loc_180020690
0x18002064b  xor     r9d, r9d
0x18002064e  lea     rdx, [rbp+4Fh+DestinationString]
0x180020652  xor     r8d, r8d
0x180020655  mov     rcx, rdi
0x180020658  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18002065e  mov     ebx, eax
0x180020660  test    eax, eax
0x180020662  jns     short loc_180020690
0x180020664  mov     dword ptr [rsp+110h+FileAttributes], eax
0x180020668  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18002066f  mov     r8d, 94h
0x180020675  mov     ecx, 1
0x18002067a  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x180020681  mov     [rsp+110h+AllocationSize], rdi
0x180020686  call    AslLogCallPrintf
0x18002068b  jmp     loc_180020805
0x180020690  mov     [rsp+110h+EaLength], r12d; EaLength
0x180020695  lea     rax, [rbp+4Fh+DestinationString]
0x180020699  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x18002069e  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800206a2  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x1800206aa  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800206ae  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x1800206b6  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800206ba  xorps   xmm0, xmm0
0x1800206bd  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x1800206c5  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x1800206cd  mov     edx, 80100080h; DesiredAccess
0x1800206d2  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x1800206d7  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800206df  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800206e7  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1800206eb  mov     [rbp+4Fh+FileHandle], r12
0x1800206ef  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x1800206f3  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800206f7  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800206fc  call    cs:__imp_ZwCreateFile
0x180020702  mov     ebx, eax
0x180020704  test    eax, eax
0x180020706  js      short loc_180020720
0x180020708  mov     rax, [rbp+4Fh+FileHandle]
0x18002070c  mov     rcx, r12
0x18002070f  mov     [rsi+8], rax
0x180020713  mov     ebx, r12d
0x180020716  mov     [rbp+4Fh+FileHandle], rcx
0x18002071a  mov     byte ptr [rsi+30h], 1
0x18002071e  jmp     short loc_180020724
0x180020720  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180020724  test    rcx, rcx
0x180020727  jz      short loc_18002072F
0x180020729  call    cs:__imp_ZwClose
0x18002072f  test    ebx, ebx
0x180020731  jns     short loc_1800207AB
0x180020733  cmp     ebx, 0C000003Ah
0x180020739  jz      loc_180020805
0x18002073f  cmp     ebx, 0C0000034h
0x180020745  jz      loc_180020805
0x18002074b  cmp     ebx, 0C00000CCh
0x180020751  jz      loc_180020805
0x180020757  lea     eax, [rbx+3FFFFFEDh]
0x18002075d  cmp     eax, 30h ; '0'
0x180020760  ja      short loc_180020772
0x180020762  mov     rcx, 1000000008001h
0x18002076c  bt      rcx, rax
0x180020770  jb      short loc_180020790
0x180020772  cmp     ebx, 0C00000BAh
0x180020778  jz      short loc_180020790
0x18002077a  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x18002077e  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180020785  mov     r8d, 0A1h
0x18002078b  jmp     loc_180020675
0x180020790  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x180020794  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18002079b  mov     r8d, 0A3h
0x1800207a1  mov     ecx, 3
0x1800207a6  jmp     loc_18002067A
0x1800207ab  xor     eax, eax
0x1800207ad  mov     dword ptr [rsp+110h+AllocationSize], 5; FileInformationClass
0x1800207b5  xorps   xmm0, xmm0
0x1800207b8  mov     [rbp+4Fh+var_38], rax
0x1800207bc  xorps   xmm1, xmm1
0x1800207bf  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x1800207c3  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x1800207c7  lea     r9d, [rax+18h]; Length
0x1800207cb  movups  [rbp+4Fh+FileInformation], xmm1
0x1800207cf  mov     rcx, [rsi+8]; FileHandle
0x1800207d3  lea     rdx, [rbp+4Fh+var_98]; IoStatusBlock
0x1800207d7  call    cs:__imp_ZwQueryInformationFile
0x1800207dd  mov     ebx, eax
0x1800207df  test    eax, eax
0x1800207e1  jns     short loc_18002080F
0x1800207e3  lea     r9, aNtqueryinforma_2; "NtQueryInformationFile failed [%x]"
0x1800207ea  mov     r8d, 0B7h
0x1800207f0  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x1800207f7  mov     dword ptr [rsp+110h+AllocationSize], eax
0x1800207fb  mov     ecx, 1
0x180020800  call    AslLogCallPrintf
0x180020805  mov     rcx, rsi; P
0x180020808  call    AslFileMappingDelete
0x18002080d  jmp     short loc_18002082D
0x18002080f  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x180020813  mov     ebx, r12d
0x180020816  mov     [rsi+18h], rax
0x18002081a  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x18002081e  neg     rax
0x180020821  sbb     ecx, ecx
0x180020823  neg     ecx
0x180020825  inc     ecx
0x180020827  mov     [rsi+38h], ecx
0x18002082a  mov     [r15], rsi
0x18002082d  cmp     [rbp+4Fh+DestinationString.Buffer], rdi
0x180020831  jz      short loc_18002083D
0x180020833  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x180020837  call    cs:__imp_RtlFreeUnicodeString
0x18002083d  mov     eax, ebx
0x18002083f  jmp     short loc_180020846
0x180020841  mov     eax, 0C000000Dh
0x180020846  mov     rcx, [rbp+4Fh+var_30]
0x18002084a  xor     rcx, rsp; StackCookie
0x18002084d  call    __security_check_cookie
0x180020852  mov     rbx, [rsp+110h+arg_10]
0x18002085a  add     rsp, 0F0h
0x180020861  pop     r15
0x180020863  pop     r12
0x180020865  pop     rdi
0x180020866  pop     rsi
0x180020867  pop     rbp
0x180020868  retn
```
