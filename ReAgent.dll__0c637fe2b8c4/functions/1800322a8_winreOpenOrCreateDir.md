# winreOpenOrCreateDir

- ea: `0x1800322a8`
- end: `0x180032482`
- name: `winreOpenOrCreateDir`
- size: `474`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002a570`
- `0x18002b358`
- `0x18002b6f0`
- `0x18002bfac`
- `0x180038120`
- `0x180039dd4`
- `0x18003a248`
- `0x18003aac0`

## callees

- `0x1800059fc`
- `0x1800322a8`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800323a4`
- `KERNEL32!GetLastError` at `0x1800323ee`
- `KERNEL32!GetLastError` at `0x180032417`
- `KERNEL32!GetLastError` at `0x1800323a4`
- `KERNEL32!GetLastError` at `0x1800323ee`
- `KERNEL32!GetLastError` at `0x180032417`
- `KERNEL32!CreateFileW` at `0x1800322fe`
- `KERNEL32!CreateFileW` at `0x1800322fe`
- `KERNEL32!CloseHandle` at `0x18003234f`
- `KERNEL32!CloseHandle` at `0x18003234f`
- `KERNEL32!SetFileAttributesW` at `0x18003240d`
- `KERNEL32!SetFileAttributesW` at `0x18003240d`
- `KERNEL32!GetFileInformationByHandle` at `0x180032328`
- `KERNEL32!GetFileInformationByHandle` at `0x180032328`
- `KERNEL32!CreateDirectoryW` at `0x1800323e4`
- `KERNEL32!CreateDirectoryW` at `0x1800323e4`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003239a`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003239a`
- `ole32!CoTaskMemFree` at `0x180032439`
- `ole32!CoTaskMemFree` at `0x180032439`

## string_xrefs

- `0x1800323f4`: `failed to create directory`
- `0x1800323c2`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x1800323aa`: `failed to convert string security descriptor`
- `0x1800323bb`: `winreOpenOrCreateDir %s (0x%x) in file %S line %d`
- `0x18003244e`: `winreOpenOrCreateDir failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreOpenOrCreateDir(LPCWSTR lpFileName)
{
  HANDLE FileW; // rdi
  int v3; // ecx
  DWORD v4; // ebx
  DWORD LastError; // eax
  const wchar_t *v6; // r8
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-41h]
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+40h] [rbp-29h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+58h] [rbp-11h] BYREF
  WCHAR StringSecurityDescriptor[20]; // [rsp+90h] [rbp+27h] BYREF

  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  FileW = CreateFileW(lpFileName, 0x40000000u, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    SecurityDescriptor.nLength = 24;
    wcscpy(StringSecurityDescriptor, L"D:(A;OICI;GA;;BA)");
    SecurityDescriptor.bInheritHandle = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           StringSecurityDescriptor,
           1u,
           &SecurityDescriptor.lpSecurityDescriptor,
           0) )
    {
      if ( CreateDirectoryW(lpFileName, &SecurityDescriptor) )
      {
        if ( SetFileAttributesW(lpFileName, 0x2006u) )
        {
          v4 = 0;
          goto LABEL_16;
        }
        LastError = GetLastError();
        v6 = L"failed to set file attributes";
        LODWORD(dwFlagsAndAttributes) = 1177;
      }
      else
      {
        LastError = GetLastError();
        v6 = L"failed to create directory";
        LODWORD(dwFlagsAndAttributes) = 1169;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = L"failed to convert string security descriptor";
      LODWORD(dwFlagsAndAttributes) = 1167;
    }
    v4 = LastError;
    UnattendLogW(
      2,
      L"winreOpenOrCreateDir %s (0x%x) in file %S line %d",
      v6,
      LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      dwFlagsAndAttributes);
    goto LABEL_16;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle(FileW, &FileInformation) && (FileInformation.dwFileAttributes & 0x10) != 0 )
    v3 = 0;
  else
    v3 = 2;
  v4 = v3;
  if ( FileW )
    CloseHandle(FileW);
LABEL_16:
  if ( SecurityDescriptor.lpSecurityDescriptor )
  {
    CoTaskMemFree(SecurityDescriptor.lpSecurityDescriptor);
    SecurityDescriptor.lpSecurityDescriptor = 0;
  }
  if ( v4 )
    UnattendLogW(1, L"winreOpenOrCreateDir failed: 0x%x", v4);
  return v4;
}

```

## disassembly

```asm
0x1800322a8  mov     [rsp-8+arg_8], rbx
0x1800322ad  mov     [rsp-8+arg_10], rdi
0x1800322b2  push    rbp
0x1800322b3  lea     rbp, [rsp-57h]
0x1800322b8  sub     rsp, 0C0h
0x1800322bf  mov     rax, cs:__security_cookie
0x1800322c6  xor     rax, rsp
0x1800322c9  mov     [rbp+57h+var_8], rax
0x1800322cd  xor     eax, eax
0x1800322cf  xorps   xmm0, xmm0
0x1800322d2  mov     [rsp+0C0h+hTemplateFile], rax; hTemplateFile
0x1800322d7  xor     r9d, r9d; lpSecurityAttributes
0x1800322da  mov     dword ptr [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800322e2  mov     edx, 40000000h; dwDesiredAccess
0x1800322e7  mov     rbx, rcx
0x1800322ea  mov     [rbp+57h+var_70], rax
0x1800322ee  lea     r8d, [rax+7]; dwShareMode
0x1800322f2  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800322fa  movups  xmmword ptr [rbp+57h+SecurityDescriptor], xmm0
0x1800322fe  call    cs:__imp_CreateFileW
0x180032304  mov     rdi, rax
0x180032307  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003230b  jz      short loc_18003235A
0x18003230d  xorps   xmm0, xmm0
0x180032310  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180032314  xor     eax, eax
0x180032316  mov     rcx, rdi; hFile
0x180032319  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x18003231d  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180032320  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180032324  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180032328  call    cs:__imp_GetFileInformationByHandle
0x18003232e  test    eax, eax
0x180032330  jz      short loc_18003233C
0x180032332  test    byte ptr [rbp+57h+FileInformation.dwFileAttributes], 10h
0x180032336  jz      short loc_18003233C
0x180032338  xor     ecx, ecx
0x18003233a  jmp     short loc_180032341
0x18003233c  mov     ecx, 2
0x180032341  mov     ebx, ecx
0x180032343  test    rdi, rdi
0x180032346  jz      loc_180032430
0x18003234c  mov     rcx, rdi; hObject
0x18003234f  call    cs:__imp_CloseHandle
0x180032355  jmp     loc_180032430
0x18003235a  movups  xmm0, xmmword ptr cs:aDAOiciGaBa; "D:(A;OICI;GA;;;BA)"
0x180032361  xor     r9d, r9d; SecurityDescriptorSize
0x180032364  lea     r8, [rbp+57h+SecurityDescriptor+8]; SecurityDescriptor
0x180032368  movups  xmm1, xmmword ptr cs:aDAOiciGaBa+10h; "I;GA;;;BA)"
0x18003236f  lea     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180032373  mov     dword ptr [rbp+57h+SecurityDescriptor], 18h
0x18003237a  movups  xmmword ptr [rbp+57h+StringSecurityDescriptor], xmm0
0x18003237e  lea     edx, [r9+1]; StringSDRevision
0x180032382  mov     dword ptr [rbp+57h+var_70], 0
0x180032389  movsd   xmm0, qword ptr cs:aDAOiciGaBa+1Eh; "BA)"
0x180032391  movups  [rbp+57h+var_20], xmm1
0x180032395  movsd   qword ptr [rbp+57h+var_20+0Eh], xmm0
0x18003239a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800323a0  test    eax, eax
0x1800323a2  jnz     short loc_1800323DD
0x1800323a4  call    cs:__imp_GetLastError
0x1800323aa  lea     r8, aFailedToConver; "failed to convert string security descr"...
0x1800323b1  mov     dword ptr [rsp+0C0h+dwFlagsAndAttributes], 48Fh
0x1800323b9  mov     ebx, eax
0x1800323bb  lea     rdx, aWinreopenorcre_0; "winreOpenOrCreateDir %s (0x%x) in file "...
0x1800323c2  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800323c9  mov     r9d, ebx
0x1800323cc  mov     ecx, 2
0x1800323d1  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800323d6  call    UnattendLogW
0x1800323db  jmp     short loc_180032430
0x1800323dd  lea     rdx, [rbp+57h+SecurityDescriptor]; lpSecurityAttributes
0x1800323e1  mov     rcx, rbx; lpPathName
0x1800323e4  call    cs:__imp_CreateDirectoryW
0x1800323ea  test    eax, eax
0x1800323ec  jnz     short loc_180032405
0x1800323ee  call    cs:__imp_GetLastError
0x1800323f4  lea     r8, aFailedToCreate_8; "failed to create directory"
0x1800323fb  mov     dword ptr [rsp+0C0h+dwFlagsAndAttributes], 491h
0x180032403  jmp     short loc_1800323B9
0x180032405  mov     edx, 2006h; dwFileAttributes
0x18003240a  mov     rcx, rbx; lpFileName
0x18003240d  call    cs:__imp_SetFileAttributesW
0x180032413  test    eax, eax
0x180032415  jnz     short loc_18003242E
0x180032417  call    cs:__imp_GetLastError
0x18003241d  lea     r8, aFailedToSetFil; "failed to set file attributes"
0x180032424  mov     dword ptr [rsp+0C0h+dwFlagsAndAttributes], 499h
0x18003242c  jmp     short loc_1800323B9
0x18003242e  xor     ebx, ebx
0x180032430  mov     rcx, [rbp+57h+SecurityDescriptor+8]; pv
0x180032434  test    rcx, rcx
0x180032437  jz      short loc_180032447
0x180032439  call    cs:__imp_CoTaskMemFree
0x18003243f  mov     [rbp+57h+SecurityDescriptor+8], 0
0x180032447  test    ebx, ebx
0x180032449  jz      short loc_18003245F
0x18003244b  mov     r8d, ebx
0x18003244e  lea     rdx, aWinreopenorcre; "winreOpenOrCreateDir failed: 0x%x"
0x180032455  mov     ecx, 1
0x18003245a  call    UnattendLogW
0x18003245f  mov     eax, ebx
0x180032461  mov     rcx, [rbp+57h+var_8]
0x180032465  xor     rcx, rsp; StackCookie
0x180032468  call    __security_check_cookie
0x18003246d  lea     r11, [rsp+0C0h+var_s0]
0x180032475  mov     rbx, [r11+18h]
0x180032479  mov     rdi, [r11+20h]
0x18003247d  mov     rsp, r11
0x180032480  pop     rbp
0x180032481  retn
```
