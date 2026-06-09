# SetProtectedProcessEnvironmentVariables

- ea: `0x1400070a0`
- end: `0x140007284`
- name: `SetProtectedProcessEnvironmentVariables`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007634`

## callees

- `0x1400023d0`
- `0x140005128`
- `0x1400070a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007239`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000712a`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000716d`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1400071e9`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000722f`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000712a`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000716d`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1400071e9`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14000722f`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1400070db`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1400071c0`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1400070db`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFolderPathW` at `0x1400071c0`

## string_xrefs

- `0x1400070e7`: `SHGetFolderPath failed`
- `0x1400071cc`: `GetBasicProfileFolderPath failed`
- `0x1400071e2`: `ProgramData`

## pseudocode

```c
__int64 SetProtectedProcessEnvironmentVariables()
{
  int v0; // ebx
  const char *v1; // rax
  __int64 v2; // rdx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  wil::details *pszPath; // [rsp+20h] [rbp-238h]
  WCHAR Value[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+258h] [rbp+0h]

  Value[0] = 0;
  v0 = SHGetFolderPathW(0, 28, 0, 1u, Value);
  if ( v0 < 0 )
  {
    v1 = "SHGetFolderPath failed";
    v2 = 121;
LABEL_3:
    LODWORD(pszPath) = v0;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\werfaultsecuremain.cpp",
      "SetProtectedProcessEnvironmentVariables",
      pszPath,
      (int)v1,
      *(const char **)Value);
    return (unsigned int)v0;
  }
  if ( !SetEnvironmentVariableW(L"TEMP", Value) )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError > 0 )
      v0 = (unsigned __int16)LastError | 0x80070000;
    v2 = 128;
    if ( v0 >= 0 )
      v0 = -2147467259;
    v1 = "SetEnvironmentVariableW failed";
    goto LABEL_3;
  }
  if ( !SetEnvironmentVariableW(L"TMP", Value) )
  {
    v5 = GetLastError();
    v0 = v5;
    if ( v5 > 0 )
      v0 = (unsigned __int16)v5 | 0x80070000;
    v2 = 136;
    if ( v0 >= 0 )
      v0 = -2147467259;
    v1 = "SetEnvironmentVariableW failed";
    goto LABEL_3;
  }
  v0 = SHGetFolderPathW(0, 35, 0, 1u, Value);
  if ( v0 < 0 )
  {
    v1 = "GetBasicProfileFolderPath failed";
    v2 = 152;
    goto LABEL_3;
  }
  if ( !SetEnvironmentVariableW(L"ProgramData", Value) )
  {
    v6 = GetLastError();
    v0 = v6;
    if ( v6 > 0 )
      v0 = (unsigned __int16)v6 | 0x80070000;
    v2 = 159;
    if ( v0 >= 0 )
      v0 = -2147467259;
    v1 = "SetEnvironmentVariableW failed";
    goto LABEL_3;
  }
  if ( !SetEnvironmentVariableW(L"ALLUSERSPROFILE", Value) )
  {
    v7 = GetLastError();
    v0 = v7;
    if ( v7 > 0 )
      v0 = (unsigned __int16)v7 | 0x80070000;
    v2 = 167;
    if ( v0 >= 0 )
      v0 = -2147467259;
    v1 = "SetEnvironmentVariableW failed";
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1400070a0  push    rbx
0x1400070a2  sub     rsp, 250h
0x1400070a9  mov     rax, cs:__security_cookie
0x1400070b0  xor     rax, rsp
0x1400070b3  mov     [rsp+258h+var_18], rax
0x1400070bb  xor     eax, eax
0x1400070bd  mov     r9d, 1; dwFlags
0x1400070c3  mov     [rsp+258h+Value], ax; char *
0x1400070c8  xor     r8d, r8d; hToken
0x1400070cb  lea     rax, [rsp+258h+Value]
0x1400070d0  xor     ecx, ecx; hwnd
0x1400070d2  mov     [rsp+258h+pszPath], rax; pszPath
0x1400070d7  lea     edx, [r9+1Bh]; csidl
0x1400070db  call    cs:__imp_SHGetFolderPathW
0x1400070e1  mov     ebx, eax
0x1400070e3  test    eax, eax
0x1400070e5  jns     short loc_14000711E
0x1400070e7  lea     rax, aShgetfolderpat_0; "SHGetFolderPath failed"
0x1400070ee  mov     edx, 79h ; 'y'; void *
0x1400070f3  mov     rcx, [rsp+258h]; this
0x1400070fb  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\werfa"...
0x140007102  mov     qword ptr [rsp+258h+var_230], rax; int
0x140007107  lea     r9, aSetprotectedpr; "SetProtectedProcessEnvironmentVariables"
0x14000710e  mov     dword ptr [rsp+258h+pszPath], ebx; wil::details *
0x140007112  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140007117  mov     eax, ebx
0x140007119  jmp     loc_14000726B
0x14000711e  lea     rdx, [rsp+258h+Value]; lpValue
0x140007123  lea     rcx, Name; "TEMP"
0x14000712a  call    cs:__imp_SetEnvironmentVariableW
0x140007130  test    eax, eax
0x140007132  jnz     short loc_140007161
0x140007134  call    cs:__imp_GetLastError
0x14000713a  mov     ebx, eax
0x14000713c  test    eax, eax
0x14000713e  jle     short loc_140007149
0x140007140  movzx   ebx, ax
0x140007143  or      ebx, 80070000h
0x140007149  mov     eax, 80004005h
0x14000714e  test    ebx, ebx
0x140007150  mov     edx, 80h
0x140007155  cmovns  ebx, eax
0x140007158  lea     rax, aSetenvironment; "SetEnvironmentVariableW failed"
0x14000715f  jmp     short loc_1400070F3
0x140007161  lea     rdx, [rsp+258h+Value]; lpValue
0x140007166  lea     rcx, aTmp; "TMP"
0x14000716d  call    cs:__imp_SetEnvironmentVariableW
0x140007173  test    eax, eax
0x140007175  jnz     short loc_1400071A7
0x140007177  call    cs:__imp_GetLastError
0x14000717d  mov     ebx, eax
0x14000717f  test    eax, eax
0x140007181  jle     short loc_14000718C
0x140007183  movzx   ebx, ax
0x140007186  or      ebx, 80070000h
0x14000718c  mov     eax, 80004005h
0x140007191  test    ebx, ebx
0x140007193  mov     edx, 88h
0x140007198  cmovns  ebx, eax
0x14000719b  lea     rax, aSetenvironment; "SetEnvironmentVariableW failed"
0x1400071a2  jmp     loc_1400070F3
0x1400071a7  mov     r9d, 1; dwFlags
0x1400071ad  lea     rax, [rsp+258h+Value]
0x1400071b2  xor     r8d, r8d; hToken
0x1400071b5  mov     [rsp+258h+pszPath], rax; pszPath
0x1400071ba  xor     ecx, ecx; hwnd
0x1400071bc  lea     edx, [r9+22h]; csidl
0x1400071c0  call    cs:__imp_SHGetFolderPathW
0x1400071c6  mov     ebx, eax
0x1400071c8  test    eax, eax
0x1400071ca  jns     short loc_1400071DD
0x1400071cc  lea     rax, aGetbasicprofil; "GetBasicProfileFolderPath failed"
0x1400071d3  mov     edx, 98h
0x1400071d8  jmp     loc_1400070F3
0x1400071dd  lea     rdx, [rsp+258h+Value]; lpValue
0x1400071e2  lea     rcx, aProgramdata; "ProgramData"
0x1400071e9  call    cs:__imp_SetEnvironmentVariableW
0x1400071ef  test    eax, eax
0x1400071f1  jnz     short loc_140007223
0x1400071f3  call    cs:__imp_GetLastError
0x1400071f9  mov     ebx, eax
0x1400071fb  test    eax, eax
0x1400071fd  jle     short loc_140007208
0x1400071ff  movzx   ebx, ax
0x140007202  or      ebx, 80070000h
0x140007208  mov     eax, 80004005h
0x14000720d  test    ebx, ebx
0x14000720f  mov     edx, 9Fh
0x140007214  cmovns  ebx, eax
0x140007217  lea     rax, aSetenvironment; "SetEnvironmentVariableW failed"
0x14000721e  jmp     loc_1400070F3
0x140007223  lea     rdx, [rsp+258h+Value]; lpValue
0x140007228  lea     rcx, aAllusersprofil; "ALLUSERSPROFILE"
0x14000722f  call    cs:__imp_SetEnvironmentVariableW
0x140007235  test    eax, eax
0x140007237  jnz     short loc_140007269
0x140007239  call    cs:__imp_GetLastError
0x14000723f  mov     ebx, eax
0x140007241  test    eax, eax
0x140007243  jle     short loc_14000724E
0x140007245  movzx   ebx, ax
0x140007248  or      ebx, 80070000h
0x14000724e  mov     eax, 80004005h
0x140007253  test    ebx, ebx
0x140007255  mov     edx, 0A7h
0x14000725a  cmovns  ebx, eax
0x14000725d  lea     rax, aSetenvironment; "SetEnvironmentVariableW failed"
0x140007264  jmp     loc_1400070F3
0x140007269  xor     eax, eax
0x14000726b  mov     rcx, [rsp+258h+var_18]
0x140007273  xor     rcx, rsp; StackCookie
0x140007276  call    __security_check_cookie
0x14000727b  add     rsp, 250h
0x140007282  pop     rbx
0x140007283  retn
```
