# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::GetFileIdByFileName(ushort const * const,_LARGE_INTEGER *)

- ea: `0x1800281cc`
- end: `0x18002835f`
- name: `?GetFileIdByFileName@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJQEBGPEAT_LARGE_INTEGER@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(const WCHAR *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b848`

## callees

- `0x180026d68`
- `0x180027008`
- `0x1800281cc`
- `0x1800293a4`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002833a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002833a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800282fc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800282fc`
- `ntdll!RtlFreeUnicodeString` at `0x18002831f`
- `ntdll!RtlFreeUnicodeString` at `0x18002831f`
- `ntdll!NtCreateFile` at `0x1800282a7`
- `ntdll!NtCreateFile` at `0x1800282a7`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180028233`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180028233`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::GetFileIdByFileName(
        const WCHAR *a1,
        DWORD *a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  unsigned int v7; // [rsp+60h] [rbp-49h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-41h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp+7h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+C0h] [rbp+17h] BYREF

  FileHandle = (void *)-1LL;
  *(_QWORD *)&NtPathName.Length = 0;
  NtPathName.Buffer = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0);
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0, 1u, 1u, 0x4000u, 0, 0);
  if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v3, &v7) )
  {
    v4 = v7;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_11;
  }
  if ( (((unsigned __int64)FileHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    || !GetFileInformationByHandle(FileHandle, &FileInformation) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    goto LABEL_3;
  }
  a2[1] = FileInformation.nFileIndexHigh;
  *a2 = FileInformation.nFileIndexLow;
  v4 = v7;
LABEL_11:
  if ( NtPathName.Buffer )
    RtlFreeUnicodeString(&NtPathName);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(FileHandle);
  return v4;
}

```

## disassembly

```asm
0x1800281cc  mov     [rsp-8+arg_10], rbx
0x1800281d1  push    rbp
0x1800281d2  lea     rbp, [rsp-57h]
0x1800281d7  sub     rsp, 100h
0x1800281de  mov     rax, cs:__security_cookie
0x1800281e5  xor     rax, rsp
0x1800281e8  mov     [rbp+57h+var_8], rax
0x1800281ec  xor     eax, eax
0x1800281ee  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800281f6  xorps   xmm0, xmm0
0x1800281f9  mov     qword ptr [rbp+57h+NtPathName.Length], rax
0x1800281fd  xorps   xmm1, xmm1
0x180028200  mov     [rbp+57h+NtPathName.Buffer], rax
0x180028204  mov     rbx, rdx
0x180028207  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18002820a  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18002820e  mov     [rbp+57h+var_A0], eax
0x180028211  xor     r9d, r9d; DirectoryInfo
0x180028214  xor     r8d, r8d; NtFileNamePart
0x180028217  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002821b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002821f  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028223  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180028227  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm1
0x18002822b  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm1
0x18002822f  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm1
0x180028233  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180028239  mov     [rsp+100h+EaLength], 0; EaLength
0x180028241  lea     rax, [rbp+57h+NtPathName]
0x180028245  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x18002824e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180028252  mov     [rsp+100h+CreateOptions], 4000h; CreateOptions
0x18002825a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002825e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180028262  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180028266  mov     eax, 1
0x18002826b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180028272  mov     [rsp+100h+CreateDisposition], eax; CreateDisposition
0x180028276  xorps   xmm0, xmm0
0x180028279  mov     [rsp+100h+ShareAccess], eax; ShareAccess
0x18002827d  mov     edx, 120089h; DesiredAccess
0x180028282  mov     [rsp+100h+FileAttributes], 0; FileAttributes
0x18002828a  mov     [rsp+100h+AllocationSize], 0; AllocationSize
0x180028293  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002829b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800282a2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800282a7  call    cs:__imp_NtCreateFile
0x1800282ad  mov     ecx, eax
0x1800282af  lea     rdx, [rbp+57h+var_A0]
0x1800282b3  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x1800282b8  test    eax, eax
0x1800282ba  jnz     short loc_1800282C8
0x1800282bc  mov     ebx, [rbp+57h+var_A0]
0x1800282bf  mov     ecx, ebx
0x1800282c1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800282c6  jmp     short loc_180028314
0x1800282c8  mov     rcx, [rbp+57h+FileHandle]; hFile
0x1800282cc  lea     rax, [rcx+1]
0x1800282d0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800282d6  jnz     short loc_1800282F8
0x1800282d8  call    cs:__imp_GetLastError
0x1800282de  mov     ebx, eax
0x1800282e0  test    eax, eax
0x1800282e2  jnz     short loc_1800282EB
0x1800282e4  mov     ebx, 80004005h
0x1800282e9  jmp     short loc_1800282BF
0x1800282eb  jle     short loc_1800282BF
0x1800282ed  movzx   ebx, ax
0x1800282f0  or      ebx, 80070000h
0x1800282f6  jmp     short loc_1800282BF
0x1800282f8  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800282fc  call    cs:__imp_GetFileInformationByHandle
0x180028302  test    eax, eax
0x180028304  jz      short loc_1800282D8
0x180028306  mov     eax, [rbp+57h+FileInformation.nFileIndexHigh]
0x180028309  mov     [rbx+4], eax
0x18002830c  mov     eax, [rbp+57h+FileInformation.nFileIndexLow]
0x18002830f  mov     [rbx], eax
0x180028311  mov     ebx, [rbp+57h+var_A0]
0x180028314  cmp     [rbp+57h+NtPathName.Buffer], 0
0x180028319  jz      short loc_180028325
0x18002831b  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18002831f  call    cs:__imp_RtlFreeUnicodeString
0x180028325  mov     ecx, ebx
0x180028327  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002832c  mov     rcx, [rbp+57h+FileHandle]; hObject
0x180028330  lea     rdx, [rcx-1]
0x180028334  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028338  ja      short loc_180028340
0x18002833a  call    cs:__imp_CloseHandle
0x180028340  mov     eax, ebx
0x180028342  mov     rcx, [rbp+57h+var_8]
0x180028346  xor     rcx, rsp; StackCookie
0x180028349  call    __security_check_cookie
0x18002834e  mov     rbx, [rsp+100h+arg_10]
0x180028356  add     rsp, 100h
0x18002835d  pop     rbp
0x18002835e  retn
```
