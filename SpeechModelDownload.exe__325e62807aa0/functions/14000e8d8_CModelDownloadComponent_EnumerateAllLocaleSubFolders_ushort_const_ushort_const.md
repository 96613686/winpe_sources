# CModelDownloadComponent::EnumerateAllLocaleSubFolders(ushort const *,ushort const *)

- ea: `0x14000e8d8`
- end: `0x14000ea00`
- name: `?EnumerateAllLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG0@Z`
- size: `296`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`

## callees

- `0x140002600`
- `0x14000985c`
- `0x14000af50`
- `0x14000e8d8`
- `0x14000ea08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e965`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000e95b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14000e95b`

## string_xrefs

- `0x14000e933`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2416)`
- `0x14000e9c6`: `CModelDownloadComponent::EnumerateAllLocaleSubFolders`
- `0x14000e97e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2419)`
- `0x14000e9bf`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2421)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::EnumerateAllLocaleSubFolders(
        CModelDownloadComponent *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // rax
  signed int LastError; // eax
  int v9; // eax
  unsigned int v11; // [rsp+28h] [rbp-450h]
  int v12; // [rsp+28h] [rbp-450h]
  unsigned __int16 v13[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Dst[264]; // [rsp+240h] [rbp-238h] BYREF

  *((_DWORD *)this + 6145) = 0;
  swprintf_s<261>(v13, L"%s\\%s", a2, a3);
  v5 = CModelDownloadComponent::EnumerateLocaleSubFolders(this, v13);
  v6 = v5;
  if ( v5 < 0 )
  {
    v11 = v5;
    v7 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2416)";
LABEL_3:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::EnumerateAllLocaleSubFolders",
      v7,
      v11);
    return v6;
  }
  if ( !ExpandEnvironmentStringsW(L"%SystemDrive%\\Data\\SharedData", Dst, 0x104u) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v11 = v6;
    v7 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2419)";
    goto LABEL_3;
  }
  swprintf_s<261>(v13, L"%s\\%s", Dst, a3);
  v9 = CModelDownloadComponent::EnumerateLocaleSubFolders(this, v13);
  if ( v9 < 0 )
  {
    v12 = v9;
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::EnumerateAllLocaleSubFolders",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2421)",
      v12);
  }
  return v6;
}

```

## disassembly

```asm
0x14000e8d8  push    rbx
0x14000e8da  push    rsi
0x14000e8db  push    rdi
0x14000e8dc  sub     rsp, 460h
0x14000e8e3  mov     rax, cs:__security_cookie
0x14000e8ea  xor     rax, rsp
0x14000e8ed  mov     [rsp+478h+var_28], rax
0x14000e8f5  mov     rsi, r8
0x14000e8f8  mov     dword ptr [rcx+6004h], 0
0x14000e902  mov     r9, r8
0x14000e905  mov     rdi, rcx
0x14000e908  mov     r8, rdx
0x14000e90b  lea     rcx, [rsp+478h+var_448]
0x14000e910  lea     rdx, aSS; "%s\\%s"
0x14000e917  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000e91c  lea     rdx, [rsp+478h+var_448]; unsigned __int16 *
0x14000e921  mov     rcx, rdi; this
0x14000e924  call    ?EnumerateLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::EnumerateLocaleSubFolders(ushort const *)
0x14000e929  mov     ebx, eax
0x14000e92b  test    eax, eax
0x14000e92d  jns     short loc_14000E946
0x14000e92f  mov     [rsp+478h+var_450], eax
0x14000e933  lea     rax, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e93a  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000e941  jmp     loc_14000E9C6
0x14000e946  mov     r8d, 104h; nSize
0x14000e94c  lea     rdx, [rsp+478h+Dst]; lpDst
0x14000e954  lea     rcx, Src; "%SystemDrive%\\Data\\SharedData"
0x14000e95b  call    cs:__imp_ExpandEnvironmentStringsW
0x14000e961  test    eax, eax
0x14000e963  jnz     short loc_14000E987
0x14000e965  call    cs:__imp_GetLastError
0x14000e96b  mov     ebx, eax
0x14000e96d  test    eax, eax
0x14000e96f  jle     short loc_14000E97A
0x14000e971  movzx   ebx, ax
0x14000e974  or      ebx, 80070000h
0x14000e97a  mov     [rsp+478h+var_450], ebx
0x14000e97e  lea     rax, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e985  jmp     short loc_14000E93A
0x14000e987  mov     r9, rsi
0x14000e98a  lea     r8, [rsp+478h+Dst]
0x14000e992  lea     rdx, aSS; "%s\\%s"
0x14000e999  lea     rcx, [rsp+478h+var_448]
0x14000e99e  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000e9a3  lea     rdx, [rsp+478h+var_448]; unsigned __int16 *
0x14000e9a8  mov     rcx, rdi; this
0x14000e9ab  call    ?EnumerateLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::EnumerateLocaleSubFolders(ushort const *)
0x14000e9b0  test    eax, eax
0x14000e9b2  jns     short loc_14000E9E3
0x14000e9b4  mov     [rsp+478h+var_450], eax
0x14000e9b8  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000e9bf  lea     rax, aOnecoreuapEndu_13; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e9c6  lea     r9, aCmodeldownload_30; "CModelDownloadComponent::EnumerateAllLo"...
0x14000e9cd  mov     [rsp+478h+var_458], rax
0x14000e9d2  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e9d9  mov     ecx, 2; int
0x14000e9de  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e9e3  mov     eax, ebx
0x14000e9e5  mov     rcx, [rsp+478h+var_28]
0x14000e9ed  xor     rcx, rsp; StackCookie
0x14000e9f0  call    __security_check_cookie
0x14000e9f5  add     rsp, 460h
0x14000e9fc  pop     rdi
0x14000e9fd  pop     rsi
0x14000e9fe  pop     rbx
0x14000e9ff  retn
```
