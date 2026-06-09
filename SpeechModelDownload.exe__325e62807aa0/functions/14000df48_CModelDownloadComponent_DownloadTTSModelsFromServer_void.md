# CModelDownloadComponent::DownloadTTSModelsFromServer(void)

- ea: `0x14000df48`
- end: `0x14000e13b`
- name: `?DownloadTTSModelsFromServer@CModelDownloadComponent@@AEAAJXZ`
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
- `0x14000df48`
- `0x14000e340`
- `0x14000e8d8`
- `0x14000fafc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df94`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000df8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000df8a`

## string_xrefs

- `0x14000e034`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(601)`
- `0x14000e05a`: `CModelDownloadComponent::InitializeTTSModelParameters`
- `0x14000e053`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(604)`
- `0x14000e083`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1265)`
- `0x14000e0a2`: `CModelDownloadComponent::DownloadTTSModelFromServer`
- `0x14000e09b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1266)`
- `0x14000dfb1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1363)`
- `0x14000dfb8`: `CModelDownloadComponent::DownloadTTSModelsFromServer`
- `0x14000e0d7`: `CModelDownloadComponent::DownloadTTSModelsFromServer`
- `0x14000dfff`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1366)`
- `0x14000e0cb`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1370)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::DownloadTTSModelsFromServer(CModelDownloadComponent *this)
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
    SPTelemetry::ModelUpdate::Begin(v2, "TTS");
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
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
        L"CModelDownloadComponent::DownloadTTSModelsFromServer",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1363)",
        v4);
      goto LABEL_21;
    }
  }
  v5 = CModelDownloadComponent::EnumerateAllLocaleSubFolders(this, Buffer, L"Speech_OneCore\\Engines\\TTS");
  v4 = v5;
  if ( v5 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadTTSModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1366)",
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
      v9 = CModelDownloadComponent::InitializeModelParameters(this, L"TTS", v6, v8);
      if ( v9 < 0 )
      {
        v10 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(604)";
        goto LABEL_16;
      }
      v9 = CModelDownloadComponent::DownloadModelFromServer(this);
      if ( v9 < 0 )
      {
        v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1266)";
        goto LABEL_19;
      }
LABEL_20:
      if ( ++v7 >= *((_DWORD *)this + 6145) )
        goto LABEL_21;
    }
    v9 = -2147024882;
    v10 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(601)";
LABEL_16:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::InitializeTTSModelParameters",
      v10,
      v9);
    v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1265)";
LABEL_19:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadTTSModelFromServer",
      v11,
      v9);
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadTTSModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1370)",
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
0x14000df48  push    rbx
0x14000df4a  push    rdi
0x14000df4b  push    r14
0x14000df4d  push    r15
0x14000df4f  sub     rsp, 258h
0x14000df56  mov     rax, cs:__security_cookie
0x14000df5d  xor     rax, rsp
0x14000df60  mov     [rsp+278h+var_38], rax
0x14000df68  mov     rdi, rcx
0x14000df6b  mov     rcx, [rcx+18h]; this
0x14000df6f  test    rcx, rcx
0x14000df72  jz      short loc_14000DF80
0x14000df74  lea     rdx, aTts_0; "TTS"
0x14000df7b  call    ?Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z; SPTelemetry::ModelUpdate::Begin(char const *)
0x14000df80  mov     edx, 104h; uSize
0x14000df85  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x14000df8a  call    cs:__imp_GetWindowsDirectoryW
0x14000df90  test    eax, eax
0x14000df92  jnz     short loc_14000DFE1
0x14000df94  call    cs:__imp_GetLastError
0x14000df9a  mov     ebx, eax
0x14000df9c  test    eax, eax
0x14000df9e  jle     short loc_14000DFA9
0x14000dfa0  movzx   ebx, ax
0x14000dfa3  or      ebx, 80070000h
0x14000dfa9  test    ebx, ebx
0x14000dfab  jns     short loc_14000DFE1
0x14000dfad  mov     [rsp+278h+var_250], ebx
0x14000dfb1  lea     rax, aOnecoreuapEndu_76; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dfb8  lea     r9, aCmodeldownload_1; "CModelDownloadComponent::DownloadTTSMod"...
0x14000dfbf  mov     [rsp+278h+var_258], rax
0x14000dfc4  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000dfcb  mov     ecx, 2; int
0x14000dfd0  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000dfd7  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dfdc  jmp     loc_14000E10B
0x14000dfe1  lea     r8, aSpeechOnecoreE; "Speech_OneCore\\Engines\\TTS"
0x14000dfe8  mov     rcx, rdi; this
0x14000dfeb  lea     rdx, [rsp+278h+Buffer]; unsigned __int16 *
0x14000dff0  call    ?EnumerateAllLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG0@Z; CModelDownloadComponent::EnumerateAllLocaleSubFolders(ushort const *,ushort const *)
0x14000dff5  mov     ebx, eax
0x14000dff7  test    eax, eax
0x14000dff9  jns     short loc_14000E008
0x14000dffb  mov     [rsp+278h+var_250], eax
0x14000dfff  lea     rax, aOnecoreuapEndu_176; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e006  jmp     short loc_14000DFB8
0x14000e008  xor     r15d, r15d
0x14000e00b  cmp     [rdi+6004h], r15d
0x14000e012  jle     loc_14000E10B
0x14000e018  movsxd  rax, r15d
0x14000e01b  imul    r9, rax, 20Ah
0x14000e022  add     r9, 1EC2h
0x14000e029  add     r9, rdi; unsigned __int16 *
0x14000e02c  jnz     short loc_14000E03D
0x14000e02e  mov     r14d, 8007000Eh
0x14000e034  lea     rax, aOnecoreuapEndu_160; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e03b  jmp     short loc_14000E05A
0x14000e03d  lea     rdx, aTts; "TTS"
0x14000e044  mov     rcx, rdi; this
0x14000e047  call    ?InitializeModelParameters@CModelDownloadComponent@@AEAAJPEBG00@Z; CModelDownloadComponent::InitializeModelParameters(ushort const *,ushort const *,ushort const *)
0x14000e04c  mov     r14d, eax
0x14000e04f  test    eax, eax
0x14000e051  jns     short loc_14000E08C
0x14000e053  lea     rax, aOnecoreuapEndu_77; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e05a  lea     r9, aCmodeldownload_13; "CModelDownloadComponent::InitializeTTSM"...
0x14000e061  mov     ecx, 2; int
0x14000e066  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e06d  mov     [rsp+278h+var_250], r14d
0x14000e072  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000e079  mov     [rsp+278h+var_258], rax
0x14000e07e  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e083  lea     rax, aOnecoreuapEndu_138; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e08a  jmp     short loc_14000E0A2
0x14000e08c  mov     rcx, rdi; this
0x14000e08f  call    ?DownloadModelFromServer@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::DownloadModelFromServer(void)
0x14000e094  mov     r14d, eax
0x14000e097  test    eax, eax
0x14000e099  jns     short loc_14000E0FB
0x14000e09b  lea     rax, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e0a2  lea     r9, aCmodeldownload_19; "CModelDownloadComponent::DownloadTTSMod"...
0x14000e0a9  mov     ecx, 2; int
0x14000e0ae  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e0b5  mov     [rsp+278h+var_250], r14d
0x14000e0ba  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000e0c1  mov     [rsp+278h+var_258], rax
0x14000e0c6  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e0cb  lea     rax, aOnecoreuapEndu_47; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e0d2  mov     [rsp+278h+var_250], r14d
0x14000e0d7  lea     r9, aCmodeldownload_1; "CModelDownloadComponent::DownloadTTSMod"...
0x14000e0de  mov     [rsp+278h+var_258], rax
0x14000e0e3  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e0ea  mov     ecx, 2; int
0x14000e0ef  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000e0f6  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e0fb  inc     r15d
0x14000e0fe  cmp     r15d, [rdi+6004h]
0x14000e105  jl      loc_14000E018
0x14000e10b  mov     rcx, [rdi+18h]; this
0x14000e10f  test    rcx, rcx
0x14000e112  jz      short loc_14000E11B
0x14000e114  mov     edx, ebx; int
0x14000e116  call    ?End@ModelUpdate@SPTelemetry@@QEAAXJ@Z; SPTelemetry::ModelUpdate::End(long)
0x14000e11b  mov     eax, ebx
0x14000e11d  mov     rcx, [rsp+278h+var_38]
0x14000e125  xor     rcx, rsp; StackCookie
0x14000e128  call    __security_check_cookie
0x14000e12d  add     rsp, 258h
0x14000e134  pop     r15
0x14000e136  pop     r14
0x14000e138  pop     rdi
0x14000e139  pop     rbx
0x14000e13a  retn
```
