# LaunchFirstLogonAnimationProcess(LogonAnimationFlags,_PROCESS_INFORMATION *)

- ea: `0x1800673f8`
- end: `0x1800675df`
- name: `?LaunchFirstLogonAnimationProcess@@YAJW4LogonAnimationFlags@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `487`
- prototype: `int __high(enum LogonAnimationFlags, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180069d8c`

## callees

- `0x180008094`
- `0x1800325c0`
- `0x180032640`
- `0x18005d488`
- `0x18005d4e8`
- `0x1800673f8`
- `0x18006c000`
- `0x18006cad0`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x1800675a0`
- `KERNEL32!CreateProcessW` at `0x1800675a0`
- `KERNEL32!GetSystemDirectoryW` at `0x18006743f`
- `KERNEL32!GetSystemDirectoryW` at `0x18006743f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18006747c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18006747c`

## pseudocode

```c
__int64 __fastcall LaunchFirstLogonAnimationProcess(int a1, struct _PROCESS_INFORMATION *a2)
{
  const char *v4; // r9
  __int64 v5; // rdx
  HRESULT v7; // ebx
  __int64 v8; // rdx
  __int64 i; // rbx
  int v10; // eax
  __int64 v11; // rdx
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  struct _STARTUPINFOW StartupInfo; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR CommandLine[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+728h] [rbp+628h]

  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    v5 = 15;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\shell\\lib\\firstlogonanimation\\firstlogonanimation.cpp",
             v4);
  }
  v7 = PathCchCombine(pszPathOut, 0x104u, Buffer, L"oobe\\FirstLogonAnim.exe");
  if ( v7 < 0 )
  {
    v8 = 17;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\shell\\lib\\firstlogonanimation\\firstlogonanimation.cpp",
      (const char *)(unsigned int)v7,
      bInheritHandles);
    return (unsigned int)v7;
  }
  v7 = StringCchCopyW(CommandLine, 0x104u, L"/RunFirstLogonAnim");
  if ( v7 < 0 )
  {
    v8 = 19;
    goto LABEL_6;
  }
  for ( i = 0; i != 5; ++i )
  {
    if ( (a1 & qword_1800A3F50[2 * i]) != LODWORD(qword_1800A3F50[2 * i]) )
      continue;
    v10 = StringCchCatW(CommandLine, 0x104u, L" ");
    if ( v10 >= 0 )
    {
      v10 = StringCchCatW(CommandLine, 0x104u, (const unsigned __int16 *)qword_1800A3F50[2 * i + 1]);
      if ( v10 >= 0 )
        continue;
      v11 = 27;
    }
    else
    {
      v11 = 25;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\shell\\lib\\firstlogonanimation\\firstlogonanimation.cpp",
      (const char *)(unsigned int)v10,
      bInheritHandles);
  }
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  StartupInfo.dwFlags = 32;
  if ( CreateProcessW(pszPathOut, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, a2) )
    return 0;
  v5 = 33;
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\shell\\lib\\firstlogonanimation\\firstlogonanimation.cpp",
           v4);
}

```

## disassembly

```asm
0x1800673f8  mov     [rsp-8+arg_0], rbx
0x1800673fd  mov     [rsp-8+arg_10], rsi
0x180067402  push    rbp
0x180067403  push    rdi
0x180067404  push    r12
0x180067406  push    r13
0x180067408  push    r14
0x18006740a  lea     rbp, [rsp-600h]
0x180067412  sub     rsp, 700h
0x180067419  mov     rax, cs:__security_cookie
0x180067420  xor     rax, rsp
0x180067423  mov     [rbp+620h+var_30], rax
0x18006742a  mov     r14, rdx
0x18006742d  mov     esi, ecx
0x18006742f  mov     r12d, 104h
0x180067435  lea     rcx, [rbp+620h+Buffer]; lpBuffer
0x18006743c  mov     edx, r12d; uSize
0x18006743f  call    cs:__imp_GetSystemDirectoryW
0x180067445  test    eax, eax
0x180067447  jnz     short loc_180067464
0x180067449  lea     edx, [rax+0Fh]; void *
0x18006744c  mov     rcx, [rbp+628h]; this
0x180067453  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\firstlogonanimatio"...
0x18006745a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006745f  jmp     loc_1800675B4
0x180067464  lea     r9, aOobeFirstlogon; "oobe\\FirstLogonAnim.exe"
0x18006746b  mov     rdx, r12; cchPathOut
0x18006746e  lea     r8, [rbp+620h+Buffer]; pszPathIn
0x180067475  lea     rcx, [rbp+620h+pszPathOut]; pszPathOut
0x18006747c  call    cs:__imp_PathCchCombine
0x180067482  mov     ebx, eax
0x180067484  test    eax, eax
0x180067486  jns     short loc_1800674AA
0x180067488  mov     edx, 11h; void *
0x18006748d  mov     rcx, [rbp+628h]; this
0x180067494  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\firstlogonanimatio"...
0x18006749b  mov     r9d, ebx; char *
0x18006749e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800674a3  mov     eax, ebx
0x1800674a5  jmp     loc_1800675B4
0x1800674aa  lea     r8, aRunfirstlogona; "/RunFirstLogonAnim"
0x1800674b1  mov     rdx, r12; unsigned __int64
0x1800674b4  lea     rcx, [rbp+620h+CommandLine]; unsigned __int16 *
0x1800674b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800674bd  mov     ebx, eax
0x1800674bf  test    eax, eax
0x1800674c1  jns     short loc_1800674CA
0x1800674c3  mov     edx, 13h
0x1800674c8  jmp     short loc_18006748D
0x1800674ca  xor     ebx, ebx
0x1800674cc  lea     r13, qword_1800A3F50
0x1800674d3  mov     rdi, rbx
0x1800674d6  add     rdi, rdi
0x1800674d9  mov     eax, [r13+rdi*8+0]
0x1800674de  and     eax, esi
0x1800674e0  cmp     eax, [r13+rdi*8+0]
0x1800674e5  jnz     short loc_180067535
0x1800674e7  lea     r8, asc_1800AC830; " "
0x1800674ee  mov     rdx, r12; unsigned __int64
0x1800674f1  lea     rcx, [rbp+620h+CommandLine]; unsigned __int16 *
0x1800674f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800674fa  test    eax, eax
0x1800674fc  jns     short loc_180067505
0x1800674fe  mov     edx, 19h
0x180067503  jmp     short loc_18006751F
0x180067505  mov     r8, [r13+rdi*8+8]; unsigned __int16 *
0x18006750a  lea     rcx, [rbp+620h+CommandLine]; unsigned __int16 *
0x18006750e  mov     rdx, r12; unsigned __int64
0x180067511  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180067516  test    eax, eax
0x180067518  jns     short loc_180067535
0x18006751a  mov     edx, 1Bh; void *
0x18006751f  mov     rcx, [rbp+628h]; this
0x180067526  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\firstlogonanimatio"...
0x18006752d  mov     r9d, eax; char *
0x180067530  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180067535  inc     rbx
0x180067538  cmp     rbx, 5
0x18006753c  jnz     short loc_1800674D3
0x18006753e  xor     edx, edx; Val
0x180067540  mov     qword ptr [rsp+720h+StartupInfo.cb], 68h ; 'h'
0x180067549  lea     r8d, [rbx+5Bh]; Size
0x18006754d  lea     rcx, [rsp+720h+StartupInfo.lpReserved]; void *
0x180067552  call    memset_0
0x180067557  mov     [rsp+720h+lpProcessInformation], r14; lpProcessInformation
0x18006755c  lea     rax, [rsp+720h+StartupInfo]
0x180067561  mov     [rsp+720h+lpStartupInfo], rax; lpStartupInfo
0x180067566  lea     rdx, [rbp+620h+CommandLine]; lpCommandLine
0x18006756a  mov     [rsp+720h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180067573  lea     rcx, [rbp+620h+pszPathOut]; lpApplicationName
0x18006757a  mov     [rsp+720h+lpEnvironment], 0; lpEnvironment
0x180067583  xor     r9d, r9d; lpThreadAttributes
0x180067586  mov     [rsp+720h+dwCreationFlags], 0; dwCreationFlags
0x18006758e  xor     r8d, r8d; lpProcessAttributes
0x180067591  mov     [rsp+720h+bInheritHandles], 0; bInheritHandles
0x180067599  mov     [rbp+620h+StartupInfo.dwFlags], 20h ; ' '
0x1800675a0  call    cs:__imp_CreateProcessW
0x1800675a6  test    eax, eax
0x1800675a8  jnz     short loc_1800675B2
0x1800675aa  lea     edx, [rbx+1Ch]
0x1800675ad  jmp     loc_18006744C
0x1800675b2  xor     eax, eax
0x1800675b4  mov     rcx, [rbp+620h+var_30]
0x1800675bb  xor     rcx, rsp; StackCookie
0x1800675be  call    __security_check_cookie
0x1800675c3  lea     r11, [rsp+720h+var_20]
0x1800675cb  mov     rbx, [r11+30h]
0x1800675cf  mov     rsi, [r11+40h]
0x1800675d3  mov     rsp, r11
0x1800675d6  pop     r14
0x1800675d8  pop     r13
0x1800675da  pop     r12
0x1800675dc  pop     rdi
0x1800675dd  pop     rbp
0x1800675de  retn
```
