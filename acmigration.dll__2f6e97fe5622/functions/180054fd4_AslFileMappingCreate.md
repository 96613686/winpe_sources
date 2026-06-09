# AslFileMappingCreate

- ea: `0x180054fd4`
- end: `0x1800552cd`
- name: `AslFileMappingCreate`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012b90`
- `0x180015938`
- `0x18005ec7c`

## callees

- `0x180001cf0`
- `0x1800027a8`
- `0x1800543c0`
- `0x180054934`
- `0x180054fd4`
- `0x1800552d4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005503e`
- `ntdll!RtlInitUnicodeString` at `0x18005503e`
- `ntdll!RtlAllocateHeap` at `0x18005505b`
- `ntdll!RtlAllocateHeap` at `0x18005505b`
- `ntdll!ZwClose` at `0x18005518d`
- `ntdll!ZwClose` at `0x18005518d`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800550bc`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800550bc`
- `ntdll!RtlFreeUnicodeString` at `0x18005529b`
- `ntdll!RtlFreeUnicodeString` at `0x18005529b`
- `ntdll!ZwCreateFile` at `0x180055160`
- `ntdll!ZwCreateFile` at `0x180055160`
- `ntdll!ZwQueryInformationFile` at `0x18005523b`
- `ntdll!ZwQueryInformationFile` at `0x18005523b`

## string_xrefs

- `0x1800550cc`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x1800550de`: `AslFileMappingCreate`
- `0x180055254`: `AslFileMappingCreate`
- `0x1800551e2`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x1800551f8`: `RtlFileMapInitializeByFilePath failed %S [%x]`

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
0x180054fd4  mov     [rsp-8+arg_10], rbx
0x180054fd9  push    rbp
0x180054fda  push    rsi
0x180054fdb  push    rdi
0x180054fdc  push    r12
0x180054fde  push    r15
0x180054fe0  lea     rbp, [rsp-2Fh]
0x180054fe5  sub     rsp, 0F0h
0x180054fec  mov     rax, cs:__security_cookie
0x180054ff3  xor     rax, rsp
0x180054ff6  mov     [rbp+4Fh+var_30], rax
0x180054ffa  xor     eax, eax
0x180054ffc  xorps   xmm0, xmm0
0x180054fff  xor     r12d, r12d
0x180055002  mov     [rbp+4Fh+var_38], rax
0x180055006  xorps   xmm1, xmm1
0x180055009  mov     rdi, rdx
0x18005500c  mov     r15, rcx
0x18005500f  movups  [rbp+4Fh+FileInformation], xmm0
0x180055013  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180055017  movups  xmmword ptr [rbp+4Fh+var_98], xmm1
0x18005501b  test    rdx, rdx
0x18005501e  jz      loc_1800552A5
0x180055024  cmp     [rdx], r12w
0x180055028  jz      loc_1800552A5
0x18005502e  test    rcx, rcx
0x180055031  jz      loc_1800552A5
0x180055037  mov     [rcx], r12
0x18005503a  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18005503e  call    cs:__imp_RtlInitUnicodeString
0x180055044  mov     rcx, gs:60h
0x18005504d  lea     edx, [r12+8]; Flags
0x180055052  lea     r8d, [r12+50h]; Size
0x180055057  mov     rcx, [rcx+30h]; HeapHandle
0x18005505b  call    cs:__imp_RtlAllocateHeap
0x180055061  mov     rsi, rax
0x180055064  test    rax, rax
0x180055067  jnz     short loc_180055073
0x180055069  mov     ebx, 0C0000017h
0x18005506e  jmp     loc_180055291
0x180055073  mov     rdx, rdi
0x180055076  mov     rcx, rsi
0x180055079  call    AslStringDuplicate
0x18005507e  mov     ebx, eax
0x180055080  test    eax, eax
0x180055082  jns     short loc_180055096
0x180055084  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x18005508b  mov     r8d, 7Bh ; '{'
0x180055091  jmp     loc_180055254
0x180055096  mov     r8d, 0Ch; MaxCount
0x18005509c  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x1800550a3  mov     rcx, rdi; String1
0x1800550a6  call    _wcsnicmp
0x1800550ab  test    eax, eax
0x1800550ad  jz      short loc_1800550F4
0x1800550af  xor     r9d, r9d
0x1800550b2  lea     rdx, [rbp+4Fh+DestinationString]
0x1800550b6  xor     r8d, r8d
0x1800550b9  mov     rcx, rdi
0x1800550bc  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800550c2  mov     ebx, eax
0x1800550c4  test    eax, eax
0x1800550c6  jns     short loc_1800550F4
0x1800550c8  mov     dword ptr [rsp+110h+FileAttributes], eax
0x1800550cc  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x1800550d3  mov     r8d, 94h
0x1800550d9  mov     ecx, 1
0x1800550de  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x1800550e5  mov     [rsp+110h+AllocationSize], rdi
0x1800550ea  call    AslLogCallPrintf
0x1800550ef  jmp     loc_180055269
0x1800550f4  mov     [rsp+110h+EaLength], r12d; EaLength
0x1800550f9  lea     rax, [rbp+4Fh+DestinationString]
0x1800550fd  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x180055102  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180055106  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x18005510e  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180055112  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18005511a  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18005511e  xorps   xmm0, xmm0
0x180055121  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x180055129  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x180055131  mov     edx, 80100080h; DesiredAccess
0x180055136  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x18005513b  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180055143  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18005514b  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18005514f  mov     [rbp+4Fh+FileHandle], r12
0x180055153  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x180055157  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18005515b  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180055160  call    cs:__imp_ZwCreateFile
0x180055166  mov     ebx, eax
0x180055168  test    eax, eax
0x18005516a  js      short loc_180055184
0x18005516c  mov     rax, [rbp+4Fh+FileHandle]
0x180055170  mov     rcx, r12
0x180055173  mov     [rsi+8], rax
0x180055177  mov     ebx, r12d
0x18005517a  mov     [rbp+4Fh+FileHandle], rcx
0x18005517e  mov     byte ptr [rsi+30h], 1
0x180055182  jmp     short loc_180055188
0x180055184  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180055188  test    rcx, rcx
0x18005518b  jz      short loc_180055193
0x18005518d  call    cs:__imp_ZwClose
0x180055193  test    ebx, ebx
0x180055195  jns     short loc_18005520F
0x180055197  cmp     ebx, 0C000003Ah
0x18005519d  jz      loc_180055269
0x1800551a3  cmp     ebx, 0C0000034h
0x1800551a9  jz      loc_180055269
0x1800551af  cmp     ebx, 0C00000CCh
0x1800551b5  jz      loc_180055269
0x1800551bb  lea     eax, [rbx+3FFFFFEDh]
0x1800551c1  cmp     eax, 30h ; '0'
0x1800551c4  ja      short loc_1800551D6
0x1800551c6  mov     rcx, 1000000008001h
0x1800551d0  bt      rcx, rax
0x1800551d4  jb      short loc_1800551F4
0x1800551d6  cmp     ebx, 0C00000BAh
0x1800551dc  jz      short loc_1800551F4
0x1800551de  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x1800551e2  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x1800551e9  mov     r8d, 0A1h
0x1800551ef  jmp     loc_1800550D9
0x1800551f4  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x1800551f8  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x1800551ff  mov     r8d, 0A3h
0x180055205  mov     ecx, 3
0x18005520a  jmp     loc_1800550DE
0x18005520f  xor     eax, eax
0x180055211  mov     dword ptr [rsp+110h+AllocationSize], 5; FileInformationClass
0x180055219  xorps   xmm0, xmm0
0x18005521c  mov     [rbp+4Fh+var_38], rax
0x180055220  xorps   xmm1, xmm1
0x180055223  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x180055227  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x18005522b  lea     r9d, [rax+18h]; Length
0x18005522f  movups  [rbp+4Fh+FileInformation], xmm1
0x180055233  mov     rcx, [rsi+8]; FileHandle
0x180055237  lea     rdx, [rbp+4Fh+var_98]; IoStatusBlock
0x18005523b  call    cs:__imp_ZwQueryInformationFile
0x180055241  mov     ebx, eax
0x180055243  test    eax, eax
0x180055245  jns     short loc_180055273
0x180055247  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x18005524e  mov     r8d, 0B7h
0x180055254  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x18005525b  mov     dword ptr [rsp+110h+AllocationSize], eax
0x18005525f  mov     ecx, 1
0x180055264  call    AslLogCallPrintf
0x180055269  mov     rcx, rsi; P
0x18005526c  call    AslFileMappingDelete
0x180055271  jmp     short loc_180055291
0x180055273  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x180055277  mov     ebx, r12d
0x18005527a  mov     [rsi+18h], rax
0x18005527e  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x180055282  neg     rax
0x180055285  sbb     ecx, ecx
0x180055287  neg     ecx
0x180055289  inc     ecx
0x18005528b  mov     [rsi+38h], ecx
0x18005528e  mov     [r15], rsi
0x180055291  cmp     [rbp+4Fh+DestinationString.Buffer], rdi
0x180055295  jz      short loc_1800552A1
0x180055297  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x18005529b  call    cs:__imp_RtlFreeUnicodeString
0x1800552a1  mov     eax, ebx
0x1800552a3  jmp     short loc_1800552AA
0x1800552a5  mov     eax, 0C000000Dh
0x1800552aa  mov     rcx, [rbp+4Fh+var_30]
0x1800552ae  xor     rcx, rsp; StackCookie
0x1800552b1  call    __security_check_cookie
0x1800552b6  mov     rbx, [rsp+110h+arg_10]
0x1800552be  add     rsp, 0F0h
0x1800552c5  pop     r15
0x1800552c7  pop     r12
0x1800552c9  pop     rdi
0x1800552ca  pop     rsi
0x1800552cb  pop     rbp
0x1800552cc  retn
```
