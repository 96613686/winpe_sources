# CModelDownloadComponent::GetModelFilesRootPathExists(ushort *)

- ea: `0x14000f4d4`
- end: `0x14000f557`
- name: `?GetModelFilesRootPathExists@CModelDownloadComponent@@CAJPEAG@Z`
- size: `131`
- prototype: `__int64 __fastcall(LPWSTR lpDst)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c5f0`
- `0x14000d890`
- `0x14000fafc`

## callees

- `0x14000985c`
- `0x14000f4d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f52f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f52f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000f525`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000f525`

## string_xrefs

- `0x14000f4e4`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1075)`
- `0x14000f4ef`: `CModelDownloadComponent::GetModelFilesRootPathExists`
- `0x14000f51e`: `%ProgramData%\Microsoft\Speech_OneCore`
- `0x14000f544`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1078)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::GetModelFilesRootPathExists(LPWSTR lpDst)
{
  unsigned int v1; // ebx
  const wchar_t *v2; // rax
  signed int LastError; // eax

  if ( lpDst )
  {
    if ( ExpandEnvironmentStringsW(L"%ProgramData%\\Microsoft\\Speech_OneCore", lpDst, 0x104u) )
      return 0;
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v2 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1078)";
  }
  else
  {
    v1 = -2147024809;
    v2 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1075)";
  }
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"CModelDownloadComponent::GetModelFilesRootPathExists",
    v2,
    v1);
  return v1;
}

```

## disassembly

```asm
0x14000f4d4  push    rbx
0x14000f4d6  sub     rsp, 30h
0x14000f4da  test    rcx, rcx
0x14000f4dd  jnz     short loc_14000F515
0x14000f4df  mov     ebx, 80070057h
0x14000f4e4  lea     rax, aOnecoreuapEndu_49; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f4eb  mov     [rsp+38h+var_10], ebx
0x14000f4ef  lea     r9, aCmodeldownload_18; "CModelDownloadComponent::GetModelFilesR"...
0x14000f4f6  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000f4fd  mov     [rsp+38h+var_18], rax
0x14000f502  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000f509  mov     ecx, 2; int
0x14000f50e  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000f513  jmp     short loc_14000F54F
0x14000f515  mov     rdx, rcx; lpDst
0x14000f518  mov     r8d, 104h; nSize
0x14000f51e  lea     rcx, aProgramdataMic; "%ProgramData%\\Microsoft\\Speech_OneCor"...
0x14000f525  call    cs:__imp_ExpandEnvironmentStringsW
0x14000f52b  test    eax, eax
0x14000f52d  jnz     short loc_14000F54D
0x14000f52f  call    cs:__imp_GetLastError
0x14000f535  mov     ebx, eax
0x14000f537  test    eax, eax
0x14000f539  jle     short loc_14000F544
0x14000f53b  movzx   ebx, ax
0x14000f53e  or      ebx, 80070000h
0x14000f544  lea     rax, aOnecoreuapEndu_5; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f54b  jmp     short loc_14000F4EB
0x14000f54d  xor     ebx, ebx
0x14000f54f  mov     eax, ebx
0x14000f551  add     rsp, 30h
0x14000f555  pop     rbx
0x14000f556  retn
```
