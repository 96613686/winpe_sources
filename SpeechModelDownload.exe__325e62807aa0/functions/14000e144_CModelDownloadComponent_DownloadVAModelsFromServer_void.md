# CModelDownloadComponent::DownloadVAModelsFromServer(void)

- ea: `0x14000e144`
- end: `0x14000e337`
- name: `?DownloadVAModelsFromServer@CModelDownloadComponent@@AEAAJXZ`
- size: `499`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d890`

## callees

- `0x140002600`
- `0x14000985c`
- `0x14000c3d8`
- `0x14000d5a4`
- `0x14000e144`
- `0x14000e340`
- `0x14000e8d8`
- `0x14000fafc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e190`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000e186`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000e186`

## string_xrefs

- `0x14000e230`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(629)`
- `0x14000e256`: `CModelDownloadComponent::InitializeVAModelParameters`
- `0x14000e24f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(632)`
- `0x14000e27f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1289)`
- `0x14000e29e`: `CModelDownloadComponent::DownloadVAModelFromServer`
- `0x14000e297`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1290)`
- `0x14000e1ad`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1406)`
- `0x14000e1b4`: `CModelDownloadComponent::DownloadVAModelsFromServer`
- `0x14000e2d3`: `CModelDownloadComponent::DownloadVAModelsFromServer`
- `0x14000e1fb`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1409)`
- `0x14000e2c7`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1413)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::DownloadVAModelsFromServer(CModelDownloadComponent *this)
{
  SPTelemetry::ModelUpdate *v2; // rcx
  signed int LastError; // eax
  signed int v4; // ebx
  int v5; // eax
  const unsigned __int16 *v6; // r8
  int v7; // r15d
  const unsigned __int16 *v8; // r9
  int v9; // r14d
  const wchar_t *v10; // rax
  const wchar_t *v11; // rax
  SPTelemetry::ModelUpdate *v12; // rcx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  v2 = (SPTelemetry::ModelUpdate *)*((_QWORD *)this + 3);
  if ( v2 )
    SPTelemetry::ModelUpdate::Begin(v2, "VA");
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::DownloadVAModelsFromServer",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1406)",
        v4);
      goto LABEL_21;
    }
  }
  v5 = CModelDownloadComponent::EnumerateAllLocaleSubFolders(this, Buffer, L"Speech_OneCore\\VoiceActivation");
  v4 = v5;
  if ( v5 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadVAModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1409)",
      v5);
    goto LABEL_21;
  }
  v7 = 0;
  if ( *((int *)this + 6145) > 0 )
  {
    while ( 1 )
    {
      v8 = (const unsigned __int16 *)((char *)this + 522 * v7 + 7874);
      if ( !v8 )
        break;
      v9 = CModelDownloadComponent::InitializeModelParameters(this, L"VA", v6, v8);
      if ( v9 < 0 )
      {
        v10 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(632)";
        goto LABEL_16;
      }
      v9 = CModelDownloadComponent::DownloadModelFromServer(this);
      if ( v9 < 0 )
      {
        v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1290)";
        goto LABEL_19;
      }
LABEL_20:
      if ( ++v7 >= *((_DWORD *)this + 6145) )
        goto LABEL_21;
    }
    v9 = -2147024882;
    v10 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(629)";
LABEL_16:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::InitializeVAModelParameters",
      v10,
      v9);
    v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1289)";
LABEL_19:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadVAModelFromServer",
      v11,
      v9);
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadVAModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1413)",
      v9);
    goto LABEL_20;
  }
LABEL_21:
  v12 = (SPTelemetry::ModelUpdate *)*((_QWORD *)this + 3);
  if ( v12 )
    SPTelemetry::ModelUpdate::End(v12, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000e144  push    rbx
0x14000e146  push    rdi
0x14000e147  push    r14
0x14000e149  push    r15
0x14000e14b  sub     rsp, 258h
0x14000e152  mov     rax, cs:__security_cookie
0x14000e159  xor     rax, rsp
0x14000e15c  mov     [rsp+278h+var_38], rax
0x14000e164  mov     rdi, rcx
0x14000e167  mov     rcx, [rcx+18h]; this
0x14000e16b  test    rcx, rcx
0x14000e16e  jz      short loc_14000E17C
0x14000e170  lea     rdx, aVa_0; "VA"
0x14000e177  call    ?Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z; SPTelemetry::ModelUpdate::Begin(char const *)
0x14000e17c  mov     edx, 104h; uSize
0x14000e181  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x14000e186  call    cs:__imp_GetSystemDirectoryW
0x14000e18c  test    eax, eax
0x14000e18e  jnz     short loc_14000E1DD
0x14000e190  call    cs:__imp_GetLastError
0x14000e196  mov     ebx, eax
0x14000e198  test    eax, eax
0x14000e19a  jle     short loc_14000E1A5
0x14000e19c  movzx   ebx, ax
0x14000e19f  or      ebx, 80070000h
0x14000e1a5  test    ebx, ebx
0x14000e1a7  jns     short loc_14000E1DD
0x14000e1a9  mov     [rsp+278h+var_250], ebx
0x14000e1ad  lea     rax, aOnecoreuapEndu_83; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e1b4  lea     r9, aCmodeldownload_10; "CModelDownloadComponent::DownloadVAMode"...
0x14000e1bb  mov     [rsp+278h+var_258], rax
0x14000e1c0  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e1c7  mov     ecx, 2; int
0x14000e1cc  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000e1d3  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e1d8  jmp     loc_14000E307
0x14000e1dd  lea     r8, aSpeechOnecoreV; "Speech_OneCore\\VoiceActivation"
0x14000e1e4  mov     rcx, rdi; this
0x14000e1e7  lea     rdx, [rsp+278h+Buffer]; unsigned __int16 *
0x14000e1ec  call    ?EnumerateAllLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG0@Z; CModelDownloadComponent::EnumerateAllLocaleSubFolders(ushort const *,ushort const *)
0x14000e1f1  mov     ebx, eax
0x14000e1f3  test    eax, eax
0x14000e1f5  jns     short loc_14000E204
0x14000e1f7  mov     [rsp+278h+var_250], eax
0x14000e1fb  lea     rax, aOnecoreuapEndu_25; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e202  jmp     short loc_14000E1B4
0x14000e204  xor     r15d, r15d
0x14000e207  cmp     [rdi+6004h], r15d
0x14000e20e  jle     loc_14000E307
0x14000e214  movsxd  rax, r15d
0x14000e217  imul    r9, rax, 20Ah
0x14000e21e  add     r9, 1EC2h
0x14000e225  add     r9, rdi; unsigned __int16 *
0x14000e228  jnz     short loc_14000E239
0x14000e22a  mov     r14d, 8007000Eh
0x14000e230  lea     rax, aOnecoreuapEndu_141; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e237  jmp     short loc_14000E256
0x14000e239  lea     rdx, aVa; "VA"
0x14000e240  mov     rcx, rdi; this
0x14000e243  call    ?InitializeModelParameters@CModelDownloadComponent@@AEAAJPEBG00@Z; CModelDownloadComponent::InitializeModelParameters(ushort const *,ushort const *,ushort const *)
0x14000e248  mov     r14d, eax
0x14000e24b  test    eax, eax
0x14000e24d  jns     short loc_14000E288
0x14000e24f  lea     rax, aOnecoreuapEndu_175; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e256  lea     r9, aCmodeldownload_31; "CModelDownloadComponent::InitializeVAMo"...
0x14000e25d  mov     ecx, 2; int
0x14000e262  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e269  mov     [rsp+278h+var_250], r14d
0x14000e26e  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000e275  mov     [rsp+278h+var_258], rax
0x14000e27a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e27f  lea     rax, aOnecoreuapEndu_120; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e286  jmp     short loc_14000E29E
0x14000e288  mov     rcx, rdi; this
0x14000e28b  call    ?DownloadModelFromServer@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::DownloadModelFromServer(void)
0x14000e290  mov     r14d, eax
0x14000e293  test    eax, eax
0x14000e295  jns     short loc_14000E2F7
0x14000e297  lea     rax, aOnecoreuapEndu_10; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e29e  lea     r9, aCmodeldownload_15; "CModelDownloadComponent::DownloadVAMode"...
0x14000e2a5  mov     ecx, 2; int
0x14000e2aa  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e2b1  mov     [rsp+278h+var_250], r14d
0x14000e2b6  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000e2bd  mov     [rsp+278h+var_258], rax
0x14000e2c2  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e2c7  lea     rax, aOnecoreuapEndu_26; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e2ce  mov     [rsp+278h+var_250], r14d
0x14000e2d3  lea     r9, aCmodeldownload_10; "CModelDownloadComponent::DownloadVAMode"...
0x14000e2da  mov     [rsp+278h+var_258], rax
0x14000e2df  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e2e6  mov     ecx, 2; int
0x14000e2eb  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000e2f2  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e2f7  inc     r15d
0x14000e2fa  cmp     r15d, [rdi+6004h]
0x14000e301  jl      loc_14000E214
0x14000e307  mov     rcx, [rdi+18h]; this
0x14000e30b  test    rcx, rcx
0x14000e30e  jz      short loc_14000E317
0x14000e310  mov     edx, ebx; int
0x14000e312  call    ?End@ModelUpdate@SPTelemetry@@QEAAXJ@Z; SPTelemetry::ModelUpdate::End(long)
0x14000e317  mov     eax, ebx
0x14000e319  mov     rcx, [rsp+278h+var_38]
0x14000e321  xor     rcx, rsp; StackCookie
0x14000e324  call    __security_check_cookie
0x14000e329  add     rsp, 258h
0x14000e330  pop     r15
0x14000e332  pop     r14
0x14000e334  pop     rdi
0x14000e335  pop     rbx
0x14000e336  retn
```
