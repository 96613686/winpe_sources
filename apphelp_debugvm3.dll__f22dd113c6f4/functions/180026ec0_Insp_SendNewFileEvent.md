# Insp_SendNewFileEvent

- ea: `0x180026ec0`
- end: `0x1800270ba`
- name: `Insp_SendNewFileEvent`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x180026e50`
- `0x1800270c0`

## callees

- `0x18000f114`
- `0x180026ec0`
- `0x1800272ec`
- `0x180039a66`
- `0x180059199`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x180026f6e`
- `ntdll!RtlGetNtSystemRoot` at `0x180026f6e`
- `ntdll!EtwEventWriteNoRegistration` at `0x180027059`
- `ntdll!EtwEventWriteNoRegistration` at `0x180027059`
- `ntdll!wcscat_s` at `0x180026f9c`
- `ntdll!wcscat_s` at `0x180026f9c`
- `ntdll!wcscpy_s` at `0x180026f83`
- `ntdll!wcscpy_s` at `0x180026f83`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180026efc`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180026efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027076`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180026fe0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180026fe0`

## string_xrefs

- `0x180026f89`: `\Temp\`
- `0x180027067`: `Unable to retrieve temp path [%d]`

## pseudocode

```c
DWORD __fastcall Insp_SendNewFileEvent(void *a1)
{
  DWORD result; // eax
  size_t v2; // rdi
  unsigned __int64 v3; // rbx
  const wchar_t *NtSystemRoot; // rax
  size_t TempPath2W; // r8
  DWORD LastError; // eax
  const char *v7; // r9
  __int64 v8; // r8
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+54h] [rbp-ACh]
  WCHAR szFilePath; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[260]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Destination[264]; // [rsp+270h] [rbp+170h] BYREF

  v9 = 0;
  result = GetFinalPathNameByHandleW(a1, &szFilePath, 0x103u, 0);
  if ( result - 1 > 0x102 )
  {
    LastError = GetLastError();
    v7 = "Unable to retrieve filename [%d]";
    v8 = 207;
    return AslLogCallPrintf(1, "Insp_SendNewFileEvent", v8, v7, LastError);
  }
  if ( result < 7 )
    return result;
  if ( String1[1] != 58 )
    return result;
  result = wcsncmp_0(&szFilePath, L"\\\\?\\", 4u);
  if ( result )
    return result;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( String1[v3] );
  result = Insp_ExtensionMatch(String1, v3);
  if ( !result )
    return result;
  NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot();
  wcscpy_s(Destination, 0x104u, NtSystemRoot);
  wcscat_s(Destination, 0x104u, L"\\Temp\\");
  do
    ++v2;
  while ( Destination[v2] );
  if ( v3 > v2 )
  {
    result = wcsnicmp_0(String1, Destination, v2);
    if ( !result )
      return result;
  }
  TempPath2W = (unsigned int)GetTempPath2W(259, Destination);
  if ( TempPath2W - 1 > 0x102 )
  {
    LastError = GetLastError();
    v7 = "Unable to retrieve temp path [%d]";
    v8 = 253;
    return AslLogCallPrintf(1, "Insp_SendNewFileEvent", v8, v7, LastError);
  }
  if ( v3 <= TempPath2W || (result = wcsnicmp_0(String1, Destination, TempPath2W)) != 0 )
  {
    v10[1] = 4;
    v9 = 2 * v3;
    v10[0] = &v9;
    v11 = 2 * v3;
    v10[2] = String1;
    v12 = 0;
    return EtwEventWriteNoRegistration(AE_LOG, AE_INSTALL_FILE, 2, v10);
  }
  return result;
}

```

## disassembly

```asm
0x180026ec0  push    rbp
0x180026ec2  push    rbx
0x180026ec3  push    rdi
0x180026ec4  push    r14
0x180026ec6  lea     rbp, [rsp-398h]
0x180026ece  sub     rsp, 498h
0x180026ed5  mov     rax, cs:__security_cookie
0x180026edc  xor     rax, rsp
0x180026edf  mov     [rbp+3B0h+var_30], rax
0x180026ee6  xor     r14d, r14d
0x180026ee9  lea     rdx, [rsp+4B0h+szFilePath]; lpszFilePath
0x180026eee  xor     r9d, r9d; dwFlags
0x180026ef1  mov     [rsp+4B0h+var_480], r14d
0x180026ef6  mov     r8d, 103h; cchFilePath
0x180026efc  call    cs:__imp_GetFinalPathNameByHandleW
0x180026f02  lea     ecx, [rax-1]
0x180026f05  cmp     ecx, 102h
0x180026f0b  ja      loc_180027076
0x180026f11  cmp     eax, 7
0x180026f14  jb      loc_18002709E
0x180026f1a  cmp     [rsp+4B0h+var_446], 3Ah ; ':'
0x180026f20  jnz     loc_18002709E
0x180026f26  lea     r8d, [r14+4]; MaxCount
0x180026f2a  lea     rdx, asc_180072F08; "\\\\?\\"
0x180026f31  lea     rcx, [rsp+4B0h+szFilePath]; String1
0x180026f36  call    wcsncmp_0
0x180026f3b  test    eax, eax
0x180026f3d  jnz     loc_18002709E
0x180026f43  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026f47  lea     rax, [rsp+4B0h+String1]
0x180026f4c  mov     rbx, rdi
0x180026f4f  inc     rbx
0x180026f52  cmp     [rax+rbx*2], r14w
0x180026f57  jnz     short loc_180026F4F
0x180026f59  mov     rdx, rbx
0x180026f5c  lea     rcx, [rsp+4B0h+String1]
0x180026f61  call    Insp_ExtensionMatch
0x180026f66  test    eax, eax
0x180026f68  jz      loc_18002709E
0x180026f6e  call    cs:__imp_RtlGetNtSystemRoot
0x180026f74  mov     edx, 104h; SizeInWords
0x180026f79  lea     rcx, [rbp+3B0h+Destination]; Destination
0x180026f80  mov     r8, rax; Source
0x180026f83  call    cs:__imp_wcscpy_s
0x180026f89  lea     r8, aTemp_0; "\\Temp\\"
0x180026f90  mov     edx, 104h; SizeInWords
0x180026f95  lea     rcx, [rbp+3B0h+Destination]; Destination
0x180026f9c  call    cs:__imp_wcscat_s
0x180026fa2  lea     rax, [rbp+3B0h+Destination]
0x180026fa9  inc     rdi
0x180026fac  cmp     [rax+rdi*2], r14w
0x180026fb1  jnz     short loc_180026FA9
0x180026fb3  cmp     rbx, rdi
0x180026fb6  jbe     short loc_180026FD4
0x180026fb8  mov     r8, rdi; MaxCount
0x180026fbb  lea     rdx, [rbp+3B0h+Destination]; String2
0x180026fc2  lea     rcx, [rsp+4B0h+String1]; String1
0x180026fc7  call    _wcsnicmp_0
0x180026fcc  test    eax, eax
0x180026fce  jz      loc_18002709E
0x180026fd4  lea     rdx, [rbp+3B0h+Destination]
0x180026fdb  mov     ecx, 103h
0x180026fe0  call    cs:__imp_GetTempPath2W
0x180026fe6  mov     r8d, eax; MaxCount
0x180026fe9  lea     rax, [r8-1]
0x180026fed  cmp     rax, 102h
0x180026ff3  ja      short loc_180027061
0x180026ff5  cmp     rbx, r8
0x180026ff8  jbe     short loc_180027013
0x180026ffa  lea     rdx, [rbp+3B0h+Destination]; String2
0x180027001  lea     rcx, [rsp+4B0h+String1]; String1
0x180027006  call    _wcsnicmp_0
0x18002700b  test    eax, eax
0x18002700d  jz      loc_18002709E
0x180027013  lea     eax, [rbx+rbx]
0x180027016  mov     [rsp+4B0h+var_470], 4
0x18002701f  lea     rcx, [rsp+4B0h+var_480]
0x180027024  mov     [rsp+4B0h+var_480], eax
0x180027028  mov     [rsp+4B0h+var_478], rcx
0x18002702d  lea     r9, [rsp+4B0h+var_478]
0x180027032  lea     rcx, [rsp+4B0h+String1]
0x180027037  mov     [rsp+4B0h+var_460], eax
0x18002703b  mov     [rsp+4B0h+var_468], rcx
0x180027040  lea     rdx, AE_INSTALL_FILE
0x180027047  lea     rcx, AE_LOG
0x18002704e  mov     [rsp+4B0h+var_45C], r14d
0x180027053  mov     r8d, 2
0x180027059  call    cs:__imp_EtwEventWriteNoRegistration
0x18002705f  jmp     short loc_18002709E
0x180027061  call    cs:__imp_GetLastError
0x180027067  lea     r9, aUnableToRetrie; "Unable to retrieve temp path [%d]"
0x18002706e  mov     r8d, 0FDh
0x180027074  jmp     short loc_180027089
0x180027076  call    cs:__imp_GetLastError
0x18002707c  lea     r9, aUnableToRetrie_0; "Unable to retrieve filename [%d]"
0x180027083  mov     r8d, 0CFh
0x180027089  lea     rdx, aInspSendnewfil; "Insp_SendNewFileEvent"
0x180027090  mov     [rsp+4B0h+var_490], eax
0x180027094  mov     ecx, 1
0x180027099  call    AslLogCallPrintf
0x18002709e  mov     rcx, [rbp+3B0h+var_30]
0x1800270a5  xor     rcx, rsp; StackCookie
0x1800270a8  call    __security_check_cookie
0x1800270ad  add     rsp, 498h
0x1800270b4  pop     r14
0x1800270b6  pop     rdi
0x1800270b7  pop     rbx
0x1800270b8  pop     rbp
0x1800270b9  retn
```
