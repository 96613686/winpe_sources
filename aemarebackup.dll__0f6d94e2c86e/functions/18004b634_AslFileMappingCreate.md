# AslFileMappingCreate

- ea: `0x18004b634`
- end: `0x18004b92d`
- name: `AslFileMappingCreate`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800e223c`

## callees

- `0x180004ea0`
- `0x18000589c`
- `0x18004b634`
- `0x18004b934`
- `0x18004c020`
- `0x18004ccd4`

## import_xrefs

- `ntdll!ZwQueryInformationFile` at `0x18004b89b`
- `ntdll!ZwQueryInformationFile` at `0x18004b89b`
- `ntdll!RtlAllocateHeap` at `0x18004b6bb`
- `ntdll!RtlAllocateHeap` at `0x18004b6bb`
- `ntdll!RtlFreeUnicodeString` at `0x18004b8fb`
- `ntdll!RtlFreeUnicodeString` at `0x18004b8fb`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18004b71c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18004b71c`
- `ntdll!ZwCreateFile` at `0x18004b7c0`
- `ntdll!ZwCreateFile` at `0x18004b7c0`
- `ntdll!ZwClose` at `0x18004b7ed`
- `ntdll!ZwClose` at `0x18004b7ed`
- `ntdll!RtlInitUnicodeString` at `0x18004b69e`
- `ntdll!RtlInitUnicodeString` at `0x18004b69e`

## string_xrefs

- `0x18004b72c`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18004b73e`: `AslFileMappingCreate`
- `0x18004b8b4`: `AslFileMappingCreate`
- `0x18004b842`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x18004b858`: `RtlFileMapInitializeByFilePath failed %S [%x]`

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
0x18004b634  mov     [rsp-8+arg_10], rbx
0x18004b639  push    rbp
0x18004b63a  push    rsi
0x18004b63b  push    rdi
0x18004b63c  push    r12
0x18004b63e  push    r15
0x18004b640  lea     rbp, [rsp-2Fh]
0x18004b645  sub     rsp, 0F0h
0x18004b64c  mov     rax, cs:__security_cookie
0x18004b653  xor     rax, rsp
0x18004b656  mov     [rbp+4Fh+var_30], rax
0x18004b65a  xor     eax, eax
0x18004b65c  xorps   xmm0, xmm0
0x18004b65f  xor     r12d, r12d
0x18004b662  mov     [rbp+4Fh+var_38], rax
0x18004b666  xorps   xmm1, xmm1
0x18004b669  mov     rdi, rdx
0x18004b66c  mov     r15, rcx
0x18004b66f  movups  [rbp+4Fh+FileInformation], xmm0
0x18004b673  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18004b677  movups  xmmword ptr [rbp+4Fh+var_98], xmm1
0x18004b67b  test    rdx, rdx
0x18004b67e  jz      loc_18004B905
0x18004b684  cmp     [rdx], r12w
0x18004b688  jz      loc_18004B905
0x18004b68e  test    rcx, rcx
0x18004b691  jz      loc_18004B905
0x18004b697  mov     [rcx], r12
0x18004b69a  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18004b69e  call    cs:__imp_RtlInitUnicodeString
0x18004b6a4  mov     rcx, gs:60h
0x18004b6ad  lea     edx, [r12+8]; Flags
0x18004b6b2  lea     r8d, [r12+50h]; Size
0x18004b6b7  mov     rcx, [rcx+30h]; HeapHandle
0x18004b6bb  call    cs:__imp_RtlAllocateHeap
0x18004b6c1  mov     rsi, rax
0x18004b6c4  test    rax, rax
0x18004b6c7  jnz     short loc_18004B6D3
0x18004b6c9  mov     ebx, 0C0000017h
0x18004b6ce  jmp     loc_18004B8F1
0x18004b6d3  mov     rdx, rdi
0x18004b6d6  mov     rcx, rsi
0x18004b6d9  call    AslStringDuplicate
0x18004b6de  mov     ebx, eax
0x18004b6e0  test    eax, eax
0x18004b6e2  jns     short loc_18004B6F6
0x18004b6e4  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x18004b6eb  mov     r8d, 7Bh ; '{'
0x18004b6f1  jmp     loc_18004B8B4
0x18004b6f6  mov     r8d, 0Ch; MaxCount
0x18004b6fc  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18004b703  mov     rcx, rdi; String1
0x18004b706  call    _wcsnicmp
0x18004b70b  test    eax, eax
0x18004b70d  jz      short loc_18004B754
0x18004b70f  xor     r9d, r9d
0x18004b712  lea     rdx, [rbp+4Fh+DestinationString]
0x18004b716  xor     r8d, r8d
0x18004b719  mov     rcx, rdi
0x18004b71c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18004b722  mov     ebx, eax
0x18004b724  test    eax, eax
0x18004b726  jns     short loc_18004B754
0x18004b728  mov     dword ptr [rsp+110h+FileAttributes], eax
0x18004b72c  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18004b733  mov     r8d, 94h
0x18004b739  mov     ecx, 1
0x18004b73e  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x18004b745  mov     [rsp+110h+AllocationSize], rdi
0x18004b74a  call    AslLogCallPrintf
0x18004b74f  jmp     loc_18004B8C9
0x18004b754  mov     [rsp+110h+EaLength], r12d; EaLength
0x18004b759  lea     rax, [rbp+4Fh+DestinationString]
0x18004b75d  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x18004b762  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18004b766  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x18004b76e  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18004b772  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18004b77a  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18004b77e  xorps   xmm0, xmm0
0x18004b781  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x18004b789  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x18004b791  mov     edx, 80100080h; DesiredAccess
0x18004b796  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x18004b79b  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18004b7a3  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18004b7ab  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18004b7af  mov     [rbp+4Fh+FileHandle], r12
0x18004b7b3  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18004b7b7  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18004b7bb  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18004b7c0  call    cs:__imp_ZwCreateFile
0x18004b7c6  mov     ebx, eax
0x18004b7c8  test    eax, eax
0x18004b7ca  js      short loc_18004B7E4
0x18004b7cc  mov     rax, [rbp+4Fh+FileHandle]
0x18004b7d0  mov     rcx, r12
0x18004b7d3  mov     [rsi+8], rax
0x18004b7d7  mov     ebx, r12d
0x18004b7da  mov     [rbp+4Fh+FileHandle], rcx
0x18004b7de  mov     byte ptr [rsi+30h], 1
0x18004b7e2  jmp     short loc_18004B7E8
0x18004b7e4  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x18004b7e8  test    rcx, rcx
0x18004b7eb  jz      short loc_18004B7F3
0x18004b7ed  call    cs:__imp_ZwClose
0x18004b7f3  test    ebx, ebx
0x18004b7f5  jns     short loc_18004B86F
0x18004b7f7  cmp     ebx, 0C000003Ah
0x18004b7fd  jz      loc_18004B8C9
0x18004b803  cmp     ebx, 0C0000034h
0x18004b809  jz      loc_18004B8C9
0x18004b80f  cmp     ebx, 0C00000CCh
0x18004b815  jz      loc_18004B8C9
0x18004b81b  lea     eax, [rbx+3FFFFFEDh]
0x18004b821  cmp     eax, 30h ; '0'
0x18004b824  ja      short loc_18004B836
0x18004b826  mov     rcx, 1000000008001h
0x18004b830  bt      rcx, rax
0x18004b834  jb      short loc_18004B854
0x18004b836  cmp     ebx, 0C00000BAh
0x18004b83c  jz      short loc_18004B854
0x18004b83e  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x18004b842  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18004b849  mov     r8d, 0A1h
0x18004b84f  jmp     loc_18004B739
0x18004b854  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x18004b858  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18004b85f  mov     r8d, 0A3h
0x18004b865  mov     ecx, 3
0x18004b86a  jmp     loc_18004B73E
0x18004b86f  xor     eax, eax
0x18004b871  mov     dword ptr [rsp+110h+AllocationSize], 5; FileInformationClass
0x18004b879  xorps   xmm0, xmm0
0x18004b87c  mov     [rbp+4Fh+var_38], rax
0x18004b880  xorps   xmm1, xmm1
0x18004b883  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x18004b887  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x18004b88b  lea     r9d, [rax+18h]; Length
0x18004b88f  movups  [rbp+4Fh+FileInformation], xmm1
0x18004b893  mov     rcx, [rsi+8]; FileHandle
0x18004b897  lea     rdx, [rbp+4Fh+var_98]; IoStatusBlock
0x18004b89b  call    cs:__imp_ZwQueryInformationFile
0x18004b8a1  mov     ebx, eax
0x18004b8a3  test    eax, eax
0x18004b8a5  jns     short loc_18004B8D3
0x18004b8a7  lea     r9, aNtqueryinforma; "NtQueryInformationFile failed [%x]"
0x18004b8ae  mov     r8d, 0B7h
0x18004b8b4  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x18004b8bb  mov     dword ptr [rsp+110h+AllocationSize], eax
0x18004b8bf  mov     ecx, 1
0x18004b8c4  call    AslLogCallPrintf
0x18004b8c9  mov     rcx, rsi; P
0x18004b8cc  call    AslFileMappingDelete
0x18004b8d1  jmp     short loc_18004B8F1
0x18004b8d3  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x18004b8d7  mov     ebx, r12d
0x18004b8da  mov     [rsi+18h], rax
0x18004b8de  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x18004b8e2  neg     rax
0x18004b8e5  sbb     ecx, ecx
0x18004b8e7  neg     ecx
0x18004b8e9  inc     ecx
0x18004b8eb  mov     [rsi+38h], ecx
0x18004b8ee  mov     [r15], rsi
0x18004b8f1  cmp     [rbp+4Fh+DestinationString.Buffer], rdi
0x18004b8f5  jz      short loc_18004B901
0x18004b8f7  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x18004b8fb  call    cs:__imp_RtlFreeUnicodeString
0x18004b901  mov     eax, ebx
0x18004b903  jmp     short loc_18004B90A
0x18004b905  mov     eax, 0C000000Dh
0x18004b90a  mov     rcx, [rbp+4Fh+var_30]
0x18004b90e  xor     rcx, rsp; StackCookie
0x18004b911  call    __security_check_cookie
0x18004b916  mov     rbx, [rsp+110h+arg_10]
0x18004b91e  add     rsp, 0F0h
0x18004b925  pop     r15
0x18004b927  pop     r12
0x18004b929  pop     rdi
0x18004b92a  pop     rsi
0x18004b92b  pop     rbp
0x18004b92c  retn
```
