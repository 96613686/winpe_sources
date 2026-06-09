# GetExeNameAndAppId(ushort * *,ushort * *)

- ea: `0x180087a2c`
- end: `0x180087c3a`
- name: `?GetExeNameAndAppId@@YAJPEAPEAG0@Z`
- size: `526`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180087c40`

## callees

- `0x1800676d4`
- `0x1800857c0`
- `0x180087980`
- `0x180087a2c`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180087a92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180087a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ab3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180087b0a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180087b0a`
- `msvcrt!strchr` at `0x180087b18`
- `msvcrt!strchr` at `0x180087b18`
- `msvcrt!_wcsicmp` at `0x180087afc`
- `msvcrt!_wcsicmp` at `0x180087afc`
- `msvcrt!_stricmp` at `0x180087b91`
- `msvcrt!_stricmp` at `0x180087b91`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180087ae6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180087ae6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180087aa9`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180087aa9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087bde`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087bde`

## string_xrefs

- `0x180087b3d`: `/ProcessID`
- `0x180087af5`: `dllhost.exe`

## pseudocode

```c
__int64 __fastcall GetExeNameAndAppId(unsigned __int16 **a1, unsigned __int16 **a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *CommandLineA; // rax
  char *v8; // rax
  int v9; // r8d
  int v10; // r9d
  char *v11; // rcx
  char *v12; // rbx
  char *i; // rax
  const char *v14; // rdi
  char *String1; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwSize; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  char String2[24]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR WideCharStr[48]; // [rsp+60h] [rbp-A0h] BYREF
  char v21; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ExeName[264]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR Buffer[264]; // [rsp+3E0h] [rbp+2E0h] BYREF

  FilePart = 0;
  dwSize = 261;
  if ( !a1 || !a2 )
    return 2147942487LL;
  *a1 = 0;
  *a2 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize)
    && GetFullPathNameW(ExeName, 0x105u, Buffer, &FilePart) )
  {
    if ( _wcsicmp(L"dllhost.exe", FilePart) )
      return (unsigned int)DuplicateString(FilePart, a1);
    CommandLineA = GetCommandLineA();
    v8 = strchr(CommandLineA, 32);
    v11 = v8 + 1;
    if ( !v8 )
      v11 = 0;
    if ( !v11 )
      return (unsigned int)DuplicateString(FilePart, a1);
    strcpy(String2, "/ProcessID");
    String1 = &v21;
    if ( (int)GetCommandLineArgumentsForTraceFileName(v11, &String1, v9, v10) < 1 )
      return (unsigned int)DuplicateString(FilePart, a1);
    v12 = String1;
    for ( i = String1; ; ++i )
    {
      if ( !*i )
        goto LABEL_18;
      v14 = i + 1;
      if ( *i == 58 )
        break;
    }
    *i = 0;
    if ( !*v14 || _stricmp(v12, String2) )
LABEL_18:
      v14 = v12;
    String1 = 0;
    if ( (int)StringCchLengthA(v14, 0x28u, (unsigned __int64 *)&String1) < 0 )
      return (unsigned int)DuplicateString(FilePart, a1);
    if ( !MultiByteToWideChar(0, 0, v14, (_DWORD)String1 + 1, WideCharStr, 41) )
      return (unsigned int)DuplicateString(FilePart, a1);
    v6 = 0;
    if ( (int)DuplicateString(WideCharStr, a2) >= 0 )
      return (unsigned int)DuplicateString(FilePart, a1);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x180087a2c  mov     [rsp-8+arg_10], rbx
0x180087a31  mov     [rsp-8+arg_18], rsi
0x180087a36  push    rbp
0x180087a37  push    rdi
0x180087a38  push    r14
0x180087a3a  lea     rbp, [rsp-500h]
0x180087a42  sub     rsp, 600h
0x180087a49  mov     rax, cs:__security_cookie
0x180087a50  xor     rax, rsp
0x180087a53  mov     [rbp+510h+var_20], rax
0x180087a5a  mov     [rsp+610h+FilePart], 0
0x180087a63  mov     ebx, 105h
0x180087a68  mov     [rsp+610h+dwSize], ebx
0x180087a6c  mov     rsi, rdx
0x180087a6f  mov     r14, rcx
0x180087a72  test    rcx, rcx
0x180087a75  jz      loc_180087C0E
0x180087a7b  test    rdx, rdx
0x180087a7e  jz      loc_180087C0E
0x180087a84  mov     qword ptr [rcx], 0
0x180087a8b  mov     qword ptr [rdx], 0
0x180087a92  call    cs:__imp_GetCurrentProcess
0x180087a98  lea     r9, [rsp+610h+dwSize]; lpdwSize
0x180087a9d  xor     edx, edx; dwFlags
0x180087a9f  mov     rcx, rax; hProcess
0x180087aa2  lea     r8, [rbp+510h+ExeName]; lpExeName
0x180087aa9  call    cs:__imp_QueryFullProcessImageNameW
0x180087aaf  test    eax, eax
0x180087ab1  jnz     short loc_180087AD1
0x180087ab3  call    cs:__imp_GetLastError
0x180087ab9  mov     ebx, eax
0x180087abb  test    eax, eax
0x180087abd  jle     loc_180087C0A
0x180087ac3  movzx   ebx, ax
0x180087ac6  or      ebx, 80070000h
0x180087acc  jmp     loc_180087C0A
0x180087ad1  lea     r9, [rsp+610h+FilePart]; lpFilePart
0x180087ad6  mov     edx, ebx; nBufferLength
0x180087ad8  lea     r8, [rbp+510h+Buffer]; lpBuffer
0x180087adf  lea     rcx, [rbp+510h+ExeName]; lpFileName
0x180087ae6  call    cs:__imp_GetFullPathNameW
0x180087aec  test    eax, eax
0x180087aee  jz      short loc_180087AB3
0x180087af0  mov     rdx, [rsp+610h+FilePart]; String2
0x180087af5  lea     rcx, aDllhostExe; "dllhost.exe"
0x180087afc  call    cs:__imp__wcsicmp
0x180087b02  test    eax, eax
0x180087b04  jnz     loc_180087BFB
0x180087b0a  call    cs:__imp_GetCommandLineA
0x180087b10  mov     rcx, rax; Str
0x180087b13  mov     edx, 20h ; ' '; Val
0x180087b18  call    cs:__imp_strchr
0x180087b1e  test    rax, rax
0x180087b21  lea     rcx, [rax+1]
0x180087b25  cmovz   rcx, rax; char *
0x180087b29  test    rcx, rcx
0x180087b2c  jz      loc_180087BFB
0x180087b32  mov     eax, dword ptr cs:aProcessid+7; "sID"
0x180087b38  lea     rdx, [rsp+610h+String1]; char **
0x180087b3d  movsd   xmm0, qword ptr cs:aProcessid; "/ProcessID"
0x180087b45  movsd   qword ptr [rsp+610h+String2], xmm0
0x180087b4b  mov     dword ptr [rsp+610h+String2+7], eax
0x180087b4f  lea     rax, [rbp+510h+var_550]
0x180087b53  mov     [rsp+610h+String1], rax
0x180087b58  call    ?GetCommandLineArgumentsForTraceFileName@@YAHPEADQEAPEADHH@Z; GetCommandLineArgumentsForTraceFileName(char *,char * * const,int,int)
0x180087b5d  cmp     eax, 1
0x180087b60  jl      loc_180087BFB
0x180087b66  mov     rbx, [rsp+610h+String1]
0x180087b6b  mov     rax, rbx
0x180087b6e  cmp     byte ptr [rax], 0
0x180087b71  jz      short loc_180087B9B
0x180087b73  cmp     byte ptr [rax], 3Ah ; ':'
0x180087b76  lea     rdi, [rax+1]
0x180087b7a  jz      short loc_180087B81
0x180087b7c  mov     rax, rdi
0x180087b7f  jmp     short loc_180087B6E
0x180087b81  mov     byte ptr [rax], 0
0x180087b84  cmp     byte ptr [rdi], 0
0x180087b87  jz      short loc_180087B9B
0x180087b89  lea     rdx, [rsp+610h+String2]; String2
0x180087b8e  mov     rcx, rbx; String1
0x180087b91  call    cs:__imp__stricmp
0x180087b97  test    eax, eax
0x180087b99  jz      short loc_180087B9E
0x180087b9b  mov     rdi, rbx
0x180087b9e  lea     r8, [rsp+610h+String1]; unsigned __int64 *
0x180087ba3  mov     [rsp+610h+String1], 0
0x180087bac  mov     edx, 28h ; '('; unsigned __int64
0x180087bb1  mov     rcx, rdi; char *
0x180087bb4  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180087bb9  test    eax, eax
0x180087bbb  js      short loc_180087BFB
0x180087bbd  mov     r9d, dword ptr [rsp+610h+String1]
0x180087bc2  lea     rax, [rsp+610h+WideCharStr]
0x180087bc7  inc     r9d; cbMultiByte
0x180087bca  mov     [rsp+610h+cchWideChar], 29h ; ')'; cchWideChar
0x180087bd2  mov     r8, rdi; lpMultiByteStr
0x180087bd5  mov     [rsp+610h+lpWideCharStr], rax; lpWideCharStr
0x180087bda  xor     edx, edx; dwFlags
0x180087bdc  xor     ecx, ecx; CodePage
0x180087bde  call    cs:__imp_MultiByteToWideChar
0x180087be4  test    eax, eax
0x180087be6  jz      short loc_180087BFB
0x180087be8  mov     rdx, rsi; unsigned __int16 **
0x180087beb  lea     rcx, [rsp+610h+WideCharStr]; unsigned __int16 *
0x180087bf0  xor     ebx, ebx
0x180087bf2  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180087bf7  test    eax, eax
0x180087bf9  js      short loc_180087C0A
0x180087bfb  mov     rcx, [rsp+610h+FilePart]; unsigned __int16 *
0x180087c00  mov     rdx, r14; unsigned __int16 **
0x180087c03  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180087c08  mov     ebx, eax
0x180087c0a  mov     eax, ebx
0x180087c0c  jmp     short loc_180087C13
0x180087c0e  mov     eax, 80070057h
0x180087c13  mov     rcx, [rbp+510h+var_20]
0x180087c1a  xor     rcx, rsp; StackCookie
0x180087c1d  call    __security_check_cookie
0x180087c22  lea     r11, [rsp+610h+var_10]
0x180087c2a  mov     rbx, [r11+30h]
0x180087c2e  mov     rsi, [r11+38h]
0x180087c32  mov     rsp, r11
0x180087c35  pop     r14
0x180087c37  pop     rdi
0x180087c38  pop     rbp
0x180087c39  retn
```
