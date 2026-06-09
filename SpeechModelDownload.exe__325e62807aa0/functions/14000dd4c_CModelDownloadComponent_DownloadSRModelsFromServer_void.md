# CModelDownloadComponent::DownloadSRModelsFromServer(void)

- ea: `0x14000dd4c`
- end: `0x14000df3f`
- name: `?DownloadSRModelsFromServer@CModelDownloadComponent@@AEAAJXZ`
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
- `0x14000dd4c`
- `0x14000e340`
- `0x14000e8d8`
- `0x14000fafc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dd98`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000dd8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000dd8e`

## string_xrefs

- `0x14000de38`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(573)`
- `0x14000de5e`: `CModelDownloadComponent::InitializeSRModelParameters`
- `0x14000de57`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(576)`
- `0x14000de87`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1241)`
- `0x14000dea6`: `CModelDownloadComponent::DownloadSRModelFromServer`
- `0x14000de9f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1242)`
- `0x14000ddb5`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1320)`
- `0x14000ddbc`: `CModelDownloadComponent::DownloadSRModelsFromServer`
- `0x14000dedb`: `CModelDownloadComponent::DownloadSRModelsFromServer`
- `0x14000de03`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1323)`
- `0x14000decf`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1327)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::DownloadSRModelsFromServer(CModelDownloadComponent *this)
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
    SPTelemetry::ModelUpdate::Begin(v2, "SR");
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
        L"CModelDownloadComponent::DownloadSRModelsFromServer",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1320)",
        v4);
      goto LABEL_21;
    }
  }
  v5 = CModelDownloadComponent::EnumerateAllLocaleSubFolders(this, Buffer, L"Speech_OneCore\\Engines\\SR");
  v4 = v5;
  if ( v5 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadSRModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1323)",
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
      v9 = CModelDownloadComponent::InitializeModelParameters(this, L"SR", v6, v8);
      if ( v9 < 0 )
      {
        v10 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(576)";
        goto LABEL_16;
      }
      v9 = CModelDownloadComponent::DownloadModelFromServer(this);
      if ( v9 < 0 )
      {
        v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1242)";
        goto LABEL_19;
      }
LABEL_20:
      if ( ++v7 >= *((_DWORD *)this + 6145) )
        goto LABEL_21;
    }
    v9 = -2147024882;
    v10 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(573)";
LABEL_16:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::InitializeSRModelParameters",
      v10,
      v9);
    v11 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1241)";
LABEL_19:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadSRModelFromServer",
      v11,
      v9);
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::DownloadSRModelsFromServer",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1327)",
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
0x14000dd4c  push    rbx
0x14000dd4e  push    rdi
0x14000dd4f  push    r14
0x14000dd51  push    r15
0x14000dd53  sub     rsp, 258h
0x14000dd5a  mov     rax, cs:__security_cookie
0x14000dd61  xor     rax, rsp
0x14000dd64  mov     [rsp+278h+var_38], rax
0x14000dd6c  mov     rdi, rcx
0x14000dd6f  mov     rcx, [rcx+18h]; this
0x14000dd73  test    rcx, rcx
0x14000dd76  jz      short loc_14000DD84
0x14000dd78  lea     rdx, aSr; "SR"
0x14000dd7f  call    ?Begin@ModelUpdate@SPTelemetry@@QEAAXPEBD@Z; SPTelemetry::ModelUpdate::Begin(char const *)
0x14000dd84  mov     edx, 104h; uSize
0x14000dd89  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x14000dd8e  call    cs:__imp_GetWindowsDirectoryW
0x14000dd94  test    eax, eax
0x14000dd96  jnz     short loc_14000DDE5
0x14000dd98  call    cs:__imp_GetLastError
0x14000dd9e  mov     ebx, eax
0x14000dda0  test    eax, eax
0x14000dda2  jle     short loc_14000DDAD
0x14000dda4  movzx   ebx, ax
0x14000dda7  or      ebx, 80070000h
0x14000ddad  test    ebx, ebx
0x14000ddaf  jns     short loc_14000DDE5
0x14000ddb1  mov     [rsp+278h+var_250], ebx
0x14000ddb5  lea     rax, aOnecoreuapEndu_116; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ddbc  lea     r9, aCmodeldownload_17; "CModelDownloadComponent::DownloadSRMode"...
0x14000ddc3  mov     [rsp+278h+var_258], rax
0x14000ddc8  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000ddcf  mov     ecx, 2; int
0x14000ddd4  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000dddb  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000dde0  jmp     loc_14000DF0F
0x14000dde5  lea     r8, aSpeechOnecoreE_0; "Speech_OneCore\\Engines\\SR"
0x14000ddec  mov     rcx, rdi; this
0x14000ddef  lea     rdx, [rsp+278h+Buffer]; unsigned __int16 *
0x14000ddf4  call    ?EnumerateAllLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG0@Z; CModelDownloadComponent::EnumerateAllLocaleSubFolders(ushort const *,ushort const *)
0x14000ddf9  mov     ebx, eax
0x14000ddfb  test    eax, eax
0x14000ddfd  jns     short loc_14000DE0C
0x14000ddff  mov     [rsp+278h+var_250], eax
0x14000de03  lea     rax, aOnecoreuapEndu_62; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000de0a  jmp     short loc_14000DDBC
0x14000de0c  xor     r15d, r15d
0x14000de0f  cmp     [rdi+6004h], r15d
0x14000de16  jle     loc_14000DF0F
0x14000de1c  movsxd  rax, r15d
0x14000de1f  imul    r9, rax, 20Ah
0x14000de26  add     r9, 1EC2h
0x14000de2d  add     r9, rdi; unsigned __int16 *
0x14000de30  jnz     short loc_14000DE41
0x14000de32  mov     r14d, 8007000Eh
0x14000de38  lea     rax, aOnecoreuapEndu_80; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000de3f  jmp     short loc_14000DE5E
0x14000de41  lea     rdx, aSr_0; "SR"
0x14000de48  mov     rcx, rdi; this
0x14000de4b  call    ?InitializeModelParameters@CModelDownloadComponent@@AEAAJPEBG00@Z; CModelDownloadComponent::InitializeModelParameters(ushort const *,ushort const *,ushort const *)
0x14000de50  mov     r14d, eax
0x14000de53  test    eax, eax
0x14000de55  jns     short loc_14000DE90
0x14000de57  lea     rax, aOnecoreuapEndu_119; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000de5e  lea     r9, aCmodeldownload_24; "CModelDownloadComponent::InitializeSRMo"...
0x14000de65  mov     ecx, 2; int
0x14000de6a  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000de71  mov     [rsp+278h+var_250], r14d
0x14000de76  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000de7d  mov     [rsp+278h+var_258], rax
0x14000de82  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000de87  lea     rax, aOnecoreuapEndu_131; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000de8e  jmp     short loc_14000DEA6
0x14000de90  mov     rcx, rdi; this
0x14000de93  call    ?DownloadModelFromServer@CModelDownloadComponent@@AEAAJXZ; CModelDownloadComponent::DownloadModelFromServer(void)
0x14000de98  mov     r14d, eax
0x14000de9b  test    eax, eax
0x14000de9d  jns     short loc_14000DEFF
0x14000de9f  lea     rax, aOnecoreuapEndu_134; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000dea6  lea     r9, aCmodeldownload_14; "CModelDownloadComponent::DownloadSRMode"...
0x14000dead  mov     ecx, 2; int
0x14000deb2  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000deb9  mov     [rsp+278h+var_250], r14d
0x14000debe  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000dec5  mov     [rsp+278h+var_258], rax
0x14000deca  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000decf  lea     rax, aOnecoreuapEndu_73; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ded6  mov     [rsp+278h+var_250], r14d
0x14000dedb  lea     r9, aCmodeldownload_17; "CModelDownloadComponent::DownloadSRMode"...
0x14000dee2  mov     [rsp+278h+var_258], rax
0x14000dee7  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000deee  mov     ecx, 2; int
0x14000def3  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000defa  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000deff  inc     r15d
0x14000df02  cmp     r15d, [rdi+6004h]
0x14000df09  jl      loc_14000DE1C
0x14000df0f  mov     rcx, [rdi+18h]; this
0x14000df13  test    rcx, rcx
0x14000df16  jz      short loc_14000DF1F
0x14000df18  mov     edx, ebx; int
0x14000df1a  call    ?End@ModelUpdate@SPTelemetry@@QEAAXJ@Z; SPTelemetry::ModelUpdate::End(long)
0x14000df1f  mov     eax, ebx
0x14000df21  mov     rcx, [rsp+278h+var_38]
0x14000df29  xor     rcx, rsp; StackCookie
0x14000df2c  call    __security_check_cookie
0x14000df31  add     rsp, 258h
0x14000df38  pop     r15
0x14000df3a  pop     r14
0x14000df3c  pop     rdi
0x14000df3d  pop     rbx
0x14000df3e  retn
```
