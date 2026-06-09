# __AppSrvComponent::Initialize(ushort const *)

- ea: `0x18001716c`
- end: `0x1800172dd`
- name: `?Initialize@__AppSrvComponent@@QEAAJPEBG@Z`
- size: `369`
- prototype: `__int64 __fastcall(__AppSrvComponent *__hidden this, LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034980`

## callees

- `0x180003f30`
- `0x18001716c`
- `0x1800172e4`
- `0x18001a280`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800171c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800171c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800171dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017217`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001723f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017269`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800171dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017217`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001723f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001724e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001724e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017299`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800171a1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800171a1`

## string_xrefs

- `0x1800171d3`: `StartComponent`
- `0x1800171f2`: `APPCMP_STARTCOMPONENTFN failed 0x%x`
- `0x180017210`: `StopComponent`
- `0x18001722c`: `APPCMP_STOPCOMPONENTFN failed 0x%x`

## pseudocode

```c
__int64 __fastcall __AppSrvComponent::Initialize(__AppSrvComponent *this, LPCWSTR lpSrc)
{
  DWORD v3; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD v6; // eax
  const char *v7; // rdx
  DWORD LastError; // ebx
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  DWORD v12; // eax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x105u);
  if ( !v3 )
    goto LABEL_14;
  if ( v3 > 0x105 )
  {
    LastError = 1359;
LABEL_16:
    __AppSrvComponent::Cleanup(this);
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  Library = LoadLibraryExW(Dst, 0, 0);
  *(_QWORD *)this = Library;
  if ( !Library )
  {
LABEL_14:
    LastError = GetLastError();
LABEL_15:
    if ( !LastError )
      return LastError;
    goto LABEL_16;
  }
  ProcAddress = GetProcAddress(Library, "StartComponent");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
  {
    v6 = GetLastError();
    v7 = "APPCMP_STARTCOMPONENTFN failed 0x%x";
LABEL_6:
    LastError = v6;
    _DbgPrintMessage(4, v7, v6);
    goto LABEL_15;
  }
  v9 = GetProcAddress(*(HMODULE *)this, "StopComponent");
  *((_QWORD *)this + 2) = v9;
  if ( !v9 )
  {
    v6 = GetLastError();
    v7 = "APPCMP_STOPCOMPONENTFN failed 0x%x";
    goto LABEL_6;
  }
  v10 = GetProcAddress(*(HMODULE *)this, "OnSessionChange");
  *((_QWORD *)this + 4) = v10;
  if ( !v10 )
  {
    v6 = GetLastError();
    v7 = "APPSRVCMP_ONSESSIONCHANGE failed 0x%x";
    goto LABEL_6;
  }
  LastError = 0;
  v11 = GetProcAddress(*(HMODULE *)this, "Refresh");
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
  {
    v12 = GetLastError();
    _DbgPrintMessage(4, "PFN_APPCMPREFRESH failed 0x%x", v12);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001716c  mov     [rsp+arg_10], rbx
0x180017171  push    rdi
0x180017172  sub     rsp, 240h
0x180017179  mov     rax, cs:__security_cookie
0x180017180  xor     rax, rsp
0x180017183  mov     [rsp+248h+var_18], rax
0x18001718b  mov     rax, rdx
0x18001718e  mov     rdi, rcx
0x180017191  mov     ebx, 105h
0x180017196  lea     rdx, [rsp+248h+Dst]; lpDst
0x18001719b  mov     r8d, ebx; nSize
0x18001719e  mov     rcx, rax; lpSrc
0x1800171a1  call    cs:__imp_ExpandEnvironmentStringsW
0x1800171a7  test    eax, eax
0x1800171a9  jz      loc_180017299
0x1800171af  cmp     eax, ebx
0x1800171b1  ja      loc_180017292
0x1800171b7  xor     r8d, r8d; dwFlags
0x1800171ba  lea     rcx, [rsp+248h+Dst]; lpLibFileName
0x1800171bf  xor     edx, edx; hFile
0x1800171c1  call    cs:__imp_LoadLibraryExW
0x1800171c7  mov     [rdi], rax
0x1800171ca  test    rax, rax
0x1800171cd  jz      loc_180017299
0x1800171d3  lea     rdx, aStartcomponent; "StartComponent"
0x1800171da  mov     rcx, rax; hModule
0x1800171dd  call    cs:__imp_GetProcAddress
0x1800171e3  mov     [rdi+8], rax
0x1800171e7  test    rax, rax
0x1800171ea  jnz     short loc_18001720D
0x1800171ec  call    cs:__imp_GetLastError
0x1800171f2  lea     rdx, aAppcmpStartcom; "APPCMP_STARTCOMPONENTFN failed 0x%x"
0x1800171f9  mov     r8d, eax
0x1800171fc  mov     ecx, 4; int
0x180017201  mov     ebx, eax
0x180017203  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017208  jmp     loc_1800172A1
0x18001720d  mov     rcx, [rdi]; hModule
0x180017210  lea     rdx, aStopcomponent; "StopComponent"
0x180017217  call    cs:__imp_GetProcAddress
0x18001721d  mov     [rdi+10h], rax
0x180017221  test    rax, rax
0x180017224  jnz     short loc_180017235
0x180017226  call    cs:__imp_GetLastError
0x18001722c  lea     rdx, aAppcmpStopcomp; "APPCMP_STOPCOMPONENTFN failed 0x%x"
0x180017233  jmp     short loc_1800171F9
0x180017235  mov     rcx, [rdi]; hModule
0x180017238  lea     rdx, aOnsessionchang; "OnSessionChange"
0x18001723f  call    cs:__imp_GetProcAddress
0x180017245  mov     [rdi+20h], rax
0x180017249  test    rax, rax
0x18001724c  jnz     short loc_18001725D
0x18001724e  call    cs:__imp_GetLastError
0x180017254  lea     rdx, aAppsrvcmpOnses; "APPSRVCMP_ONSESSIONCHANGE failed 0x%x"
0x18001725b  jmp     short loc_1800171F9
0x18001725d  mov     rcx, [rdi]; hModule
0x180017260  lea     rdx, aRefresh; "Refresh"
0x180017267  xor     ebx, ebx
0x180017269  call    cs:__imp_GetProcAddress
0x18001726f  mov     [rdi+18h], rax
0x180017273  test    rax, rax
0x180017276  jnz     short loc_1800172BA
0x180017278  call    cs:__imp_GetLastError
0x18001727e  mov     r8d, eax
0x180017281  lea     rdx, aPfnAppcmprefre; "PFN_APPCMPREFRESH failed 0x%x"
0x180017288  lea     ecx, [rbx+4]; int
0x18001728b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017290  jmp     short loc_1800172BA
0x180017292  mov     ebx, 54Fh
0x180017297  jmp     short loc_1800172A5
0x180017299  call    cs:__imp_GetLastError
0x18001729f  mov     ebx, eax
0x1800172a1  test    ebx, ebx
0x1800172a3  jz      short loc_1800172BA
0x1800172a5  mov     rcx, rdi; this
0x1800172a8  call    ?Cleanup@__AppSrvComponent@@QEAAXXZ; __AppSrvComponent::Cleanup(void)
0x1800172ad  test    ebx, ebx
0x1800172af  jle     short loc_1800172BA
0x1800172b1  movzx   ebx, bx
0x1800172b4  or      ebx, 80070000h
0x1800172ba  mov     eax, ebx
0x1800172bc  mov     rcx, [rsp+248h+var_18]
0x1800172c4  xor     rcx, rsp; StackCookie
0x1800172c7  call    __security_check_cookie
0x1800172cc  mov     rbx, [rsp+248h+arg_10]
0x1800172d4  add     rsp, 240h
0x1800172db  pop     rdi
0x1800172dc  retn
```
