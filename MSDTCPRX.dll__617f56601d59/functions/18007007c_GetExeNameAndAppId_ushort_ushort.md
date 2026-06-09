# GetExeNameAndAppId(ushort * *,ushort * *)

- ea: `0x18007007c`
- end: `0x18007028a`
- name: `?GetExeNameAndAppId@@YAJPEAPEAG0@Z`
- size: `526`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180070290`

## callees

- `0x180006324`
- `0x18000e6f4`
- `0x18006ffd0`
- `0x18007007c`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007022e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007022e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070103`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800700f9`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800700f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800700e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800700e2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180070136`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180070136`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18007015a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18007015a`
- `msvcrt!_stricmp` at `0x1800701e1`
- `msvcrt!_stricmp` at `0x1800701e1`
- `msvcrt!strchr` at `0x180070168`
- `msvcrt!strchr` at `0x180070168`
- `msvcrt!_wcsicmp` at `0x18007014c`
- `msvcrt!_wcsicmp` at `0x18007014c`

## string_xrefs

- `0x180070145`: `dllhost.exe`
- `0x18007018d`: `/ProcessID`

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
0x18007007c  mov     [rsp-8+arg_10], rbx
0x180070081  mov     [rsp-8+arg_18], rsi
0x180070086  push    rbp
0x180070087  push    rdi
0x180070088  push    r14
0x18007008a  lea     rbp, [rsp-500h]
0x180070092  sub     rsp, 600h
0x180070099  mov     rax, cs:__security_cookie
0x1800700a0  xor     rax, rsp
0x1800700a3  mov     [rbp+510h+var_20], rax
0x1800700aa  mov     [rsp+610h+FilePart], 0
0x1800700b3  mov     ebx, 105h
0x1800700b8  mov     [rsp+610h+dwSize], ebx
0x1800700bc  mov     rsi, rdx
0x1800700bf  mov     r14, rcx
0x1800700c2  test    rcx, rcx
0x1800700c5  jz      loc_18007025E
0x1800700cb  test    rdx, rdx
0x1800700ce  jz      loc_18007025E
0x1800700d4  mov     qword ptr [rcx], 0
0x1800700db  mov     qword ptr [rdx], 0
0x1800700e2  call    cs:__imp_GetCurrentProcess
0x1800700e8  lea     r9, [rsp+610h+dwSize]; lpdwSize
0x1800700ed  xor     edx, edx; dwFlags
0x1800700ef  mov     rcx, rax; hProcess
0x1800700f2  lea     r8, [rbp+510h+ExeName]; lpExeName
0x1800700f9  call    cs:__imp_QueryFullProcessImageNameW
0x1800700ff  test    eax, eax
0x180070101  jnz     short loc_180070121
0x180070103  call    cs:__imp_GetLastError
0x180070109  mov     ebx, eax
0x18007010b  test    eax, eax
0x18007010d  jle     loc_18007025A
0x180070113  movzx   ebx, ax
0x180070116  or      ebx, 80070000h
0x18007011c  jmp     loc_18007025A
0x180070121  lea     r9, [rsp+610h+FilePart]; lpFilePart
0x180070126  mov     edx, ebx; nBufferLength
0x180070128  lea     r8, [rbp+510h+Buffer]; lpBuffer
0x18007012f  lea     rcx, [rbp+510h+ExeName]; lpFileName
0x180070136  call    cs:__imp_GetFullPathNameW
0x18007013c  test    eax, eax
0x18007013e  jz      short loc_180070103
0x180070140  mov     rdx, [rsp+610h+FilePart]; String2
0x180070145  lea     rcx, aDllhostExe; "dllhost.exe"
0x18007014c  call    cs:__imp__wcsicmp
0x180070152  test    eax, eax
0x180070154  jnz     loc_18007024B
0x18007015a  call    cs:__imp_GetCommandLineA
0x180070160  mov     rcx, rax; Str
0x180070163  mov     edx, 20h ; ' '; Val
0x180070168  call    cs:__imp_strchr
0x18007016e  test    rax, rax
0x180070171  lea     rcx, [rax+1]
0x180070175  cmovz   rcx, rax; char *
0x180070179  test    rcx, rcx
0x18007017c  jz      loc_18007024B
0x180070182  mov     eax, dword ptr cs:aProcessid+7; "sID"
0x180070188  lea     rdx, [rsp+610h+String1]; char **
0x18007018d  movsd   xmm0, qword ptr cs:aProcessid; "/ProcessID"
0x180070195  movsd   qword ptr [rsp+610h+String2], xmm0
0x18007019b  mov     dword ptr [rsp+610h+String2+7], eax
0x18007019f  lea     rax, [rbp+510h+var_550]
0x1800701a3  mov     [rsp+610h+String1], rax
0x1800701a8  call    ?GetCommandLineArgumentsForTraceFileName@@YAHPEADQEAPEADHH@Z; GetCommandLineArgumentsForTraceFileName(char *,char * * const,int,int)
0x1800701ad  cmp     eax, 1
0x1800701b0  jl      loc_18007024B
0x1800701b6  mov     rbx, [rsp+610h+String1]
0x1800701bb  mov     rax, rbx
0x1800701be  cmp     byte ptr [rax], 0
0x1800701c1  jz      short loc_1800701EB
0x1800701c3  cmp     byte ptr [rax], 3Ah ; ':'
0x1800701c6  lea     rdi, [rax+1]
0x1800701ca  jz      short loc_1800701D1
0x1800701cc  mov     rax, rdi
0x1800701cf  jmp     short loc_1800701BE
0x1800701d1  mov     byte ptr [rax], 0
0x1800701d4  cmp     byte ptr [rdi], 0
0x1800701d7  jz      short loc_1800701EB
0x1800701d9  lea     rdx, [rsp+610h+String2]; String2
0x1800701de  mov     rcx, rbx; String1
0x1800701e1  call    cs:__imp__stricmp
0x1800701e7  test    eax, eax
0x1800701e9  jz      short loc_1800701EE
0x1800701eb  mov     rdi, rbx
0x1800701ee  lea     r8, [rsp+610h+String1]; unsigned __int64 *
0x1800701f3  mov     [rsp+610h+String1], 0
0x1800701fc  mov     edx, 28h ; '('; unsigned __int64
0x180070201  mov     rcx, rdi; char *
0x180070204  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180070209  test    eax, eax
0x18007020b  js      short loc_18007024B
0x18007020d  mov     r9d, dword ptr [rsp+610h+String1]
0x180070212  lea     rax, [rsp+610h+WideCharStr]
0x180070217  inc     r9d; cbMultiByte
0x18007021a  mov     [rsp+610h+cchWideChar], 29h ; ')'; cchWideChar
0x180070222  mov     r8, rdi; lpMultiByteStr
0x180070225  mov     [rsp+610h+lpWideCharStr], rax; lpWideCharStr
0x18007022a  xor     edx, edx; dwFlags
0x18007022c  xor     ecx, ecx; CodePage
0x18007022e  call    cs:__imp_MultiByteToWideChar
0x180070234  test    eax, eax
0x180070236  jz      short loc_18007024B
0x180070238  mov     rdx, rsi; unsigned __int16 **
0x18007023b  lea     rcx, [rsp+610h+WideCharStr]; unsigned __int16 *
0x180070240  xor     ebx, ebx
0x180070242  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180070247  test    eax, eax
0x180070249  js      short loc_18007025A
0x18007024b  mov     rcx, [rsp+610h+FilePart]; unsigned __int16 *
0x180070250  mov     rdx, r14; unsigned __int16 **
0x180070253  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180070258  mov     ebx, eax
0x18007025a  mov     eax, ebx
0x18007025c  jmp     short loc_180070263
0x18007025e  mov     eax, 80070057h
0x180070263  mov     rcx, [rbp+510h+var_20]
0x18007026a  xor     rcx, rsp; StackCookie
0x18007026d  call    __security_check_cookie
0x180070272  lea     r11, [rsp+610h+var_10]
0x18007027a  mov     rbx, [r11+30h]
0x18007027e  mov     rsi, [r11+38h]
0x180070282  mov     rsp, r11
0x180070285  pop     r14
0x180070287  pop     rdi
0x180070288  pop     rbp
0x180070289  retn
```
