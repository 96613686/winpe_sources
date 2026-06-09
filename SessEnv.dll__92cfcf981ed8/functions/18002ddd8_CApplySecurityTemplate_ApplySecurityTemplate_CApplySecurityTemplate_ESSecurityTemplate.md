# CApplySecurityTemplate::ApplySecurityTemplate(CApplySecurityTemplate::ESSecurityTemplate)

- ea: `0x18002ddd8`
- end: `0x18002e3fb`
- name: `?ApplySecurityTemplate@CApplySecurityTemplate@@AEAAJW4ESSecurityTemplate@1@@Z`
- size: `1571`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e410`

## callees

- `0x180001008`
- `0x180001090`
- `0x1800013a4`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x18002d830`
- `0x18002ddd8`
- `0x18004325c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e221`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e221`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e3c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e3c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3cb`
- `SHELL32!SHGetKnownFolderPath` at `0x18002de48`
- `SHELL32!SHGetKnownFolderPath` at `0x18002de48`
- `SCECLI!SceSetupSystemByInfName` at `0x18002df9e`
- `SCECLI!SceSetupSystemByInfName` at `0x18002e120`
- `SCECLI!SceSetupSystemByInfName` at `0x18002df9e`
- `SCECLI!SceSetupSystemByInfName` at `0x18002e120`

## string_xrefs

- `0x18002de73`: `ApplySecurityTemplate`
- `0x18002df2c`: `ApplySecurityTemplate`
- `0x18002dfd7`: `ApplySecurityTemplate`
- `0x18002e0ab`: `ApplySecurityTemplate`
- `0x18002e155`: `ApplySecurityTemplate`
- `0x18002e256`: `ApplySecurityTemplate`
- `0x18002e309`: `ApplySecurityTemplate`
- `0x18002e2ba`: `SecurityTemplate`
- `0x18002de86`: `SHGetKnownFolderPath`
- `0x18002e035`: `applied security template`
- `0x18002e1b3`: `applied RDSH-Update security template on top`
- `0x18002e269`: `RegCreateKeyEx REG_CONTROL_TSERVER failed`
- `0x18002e31c`: `RegSetValueEx REG_VALUE_SECURITY_TEMPLATE in REG_CONTROL_TSERVER failed`
- `0x18002e37d`: `marked the reg key REG_VALUE_SECURITY_TEMPLATE in REG_CONTROL_TSERVER`

## pseudocode

```c
__int64 __fastcall CApplySecurityTemplate::ApplySecurityTemplate(__int64 a1, int a2)
{
  __int64 v2; // r14
  HRESULT v4; // eax
  unsigned int v5; // ebx
  char *v6; // rdx
  const char **v7; // rax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  const char **phkResult; // [rsp+38h] [rbp-C8h]
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  const char *v17; // [rsp+58h] [rbp-A8h] BYREF
  const char *v18; // [rsp+60h] [rbp-A0h] BYREF
  const char *v19; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  PWSTR ppszPath; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v23[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = a2;
  hKey = 0;
  *(_DWORD *)Data = 0;
  ppszPath = 0;
  memset_0(v23, 0, 0x20Au);
  v4 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = StringCchPrintfW(v23, 0x105u, L"%s\\inf\\%s", ppszPath, off_18005F178[v2]);
    v5 = v8;
    if ( v8 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v8, 0);
      if ( (unsigned int)dword_180084170 <= 3 )
        goto LABEL_42;
      v17 = "ApplySecurityTemplate";
      v6 = byte_1800797B3;
      v19 = "StringCchPrintfW";
      v18 = "Warning HResult failed";
      phkResult = &v17;
      v7 = &v18;
      goto LABEL_4;
    }
    v9 = SceSetupSystemByInfName(v23, 0, 96);
    v5 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(0, v5, 0);
        if ( (unsigned int)dword_180084170 <= 3 )
          goto LABEL_42;
        v17 = "ApplySecurityTemplate";
        v6 = byte_180079773;
        v19 = "SceSetupSystemByInfName";
        v18 = "Warning HResult failed";
        phkResult = &v17;
        v7 = &v18;
        goto LABEL_4;
      }
    }
    if ( (unsigned int)dword_180084170 > 4 )
    {
      v17 = "applied security template";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)&dword_180084170,
        (__int64)byte_18007974D,
        0,
        0,
        (const unsigned __int16 **)&v17);
    }
    v10 = StringCchPrintfW(v23, 0x105u, L"%s\\inf\\%s", ppszPath, L"rdshup.inf");
    v5 = v10;
    if ( v10 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v10, 0);
      if ( (unsigned int)dword_180084170 <= 3 )
        goto LABEL_42;
      v17 = "ApplySecurityTemplate";
      v6 = byte_18007970D;
      v19 = "StringCchPrintfW";
      v18 = "Warning HResult failed";
      phkResult = &v17;
      v7 = &v18;
      goto LABEL_4;
    }
    v11 = SceSetupSystemByInfName(v23, 0, 0xFFFF);
    if ( v11 )
    {
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      else
        v5 = v11;
      MicrosoftTelemetryAssertTriggeredArgs(0, v5, 0);
      if ( (unsigned int)dword_180084170 > 3 )
      {
        v17 = "ApplySecurityTemplate";
        v6 = byte_1800796CD;
        v19 = "SceSetupSystemByInfName";
        v18 = "Warning HResult failed";
        phkResult = &v17;
        v7 = &v18;
        goto LABEL_4;
      }
    }
    else
    {
      if ( (unsigned int)dword_180084170 > 4 )
      {
        v17 = "applied RDSH-Update security template on top";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (__int64)&dword_180084170,
          (__int64)&byte_1800796A7,
          0,
          0,
          (const unsigned __int16 **)&v17);
      }
      v12 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Control\\Terminal Server",
              0,
              0,
              0,
              0x20006u,
              0,
              &hKey,
              0);
      if ( v12 )
      {
        if ( v12 > 0 )
          v5 = (unsigned __int16)v12 | 0x80070000;
        else
          v5 = v12;
        MicrosoftTelemetryAssertTriggeredArgs(0, v5, 0);
        if ( (unsigned int)dword_180084170 > 3 )
        {
          v17 = "ApplySecurityTemplate";
          v6 = &byte_180079667;
          v19 = "RegCreateKeyEx REG_CONTROL_TSERVER failed";
          v18 = "Warning HResult failed";
          phkResult = &v17;
          v7 = &v18;
          goto LABEL_4;
        }
      }
      else
      {
        *(_DWORD *)Data = v2;
        v13 = RegSetValueExW(hKey, L"SecurityTemplate", 0, 4u, Data, 4u);
        if ( v13 )
        {
          if ( v13 > 0 )
            v5 = (unsigned __int16)v13 | 0x80070000;
          else
            v5 = v13;
          MicrosoftTelemetryAssertTriggeredArgs(0, v5, 0);
          if ( (unsigned int)dword_180084170 > 3 )
          {
            v17 = "ApplySecurityTemplate";
            v6 = &byte_180079627;
            v19 = "RegSetValueEx REG_VALUE_SECURITY_TEMPLATE in REG_CONTROL_TSERVER failed";
            v18 = "Warning HResult failed";
            phkResult = &v17;
            v7 = &v18;
            goto LABEL_4;
          }
        }
        else
        {
          if ( (unsigned int)dword_180084170 > 5 )
          {
            v16 = *(_DWORD *)Data;
            v17 = "marked the reg key REG_VALUE_SECURITY_TEMPLATE in REG_CONTROL_TSERVER";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (__int64)&dword_180084170,
              (__int64)&unk_1800795F8,
              0,
              0,
              (const unsigned __int16 **)&v17,
              (__int64)&v16);
          }
          *(_DWORD *)(a1 + 1592) = 1;
        }
      }
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v4, 0);
    if ( (unsigned int)dword_180084170 > 3 )
    {
      v18 = "ApplySecurityTemplate";
      v6 = byte_1800797F3;
      v19 = "SHGetKnownFolderPath";
      v17 = "Warning HResult failed";
      phkResult = &v18;
      v7 = &v17;
LABEL_4:
      v16 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&dword_180084170,
        (__int64)v6,
        0,
        0,
        (const unsigned __int16 **)v7,
        (const unsigned __int16 **)&v19,
        (__int64)&v16,
        (const unsigned __int16 **)phkResult);
    }
  }
LABEL_42:
  TraceLoggingWriteConfigSecurityEvent(v5, v2);
  RegCloseKey(hKey);
  CoTaskMemFree(ppszPath);
  return v5;
}

```

## disassembly

```asm
0x18002ddd8  mov     [rsp-8+arg_10], rbx
0x18002dddd  mov     [rsp-8+arg_18], rsi
0x18002dde2  push    rbp
0x18002dde3  push    r13
0x18002dde5  push    r14
0x18002dde7  lea     rbp, [rsp-1B0h]
0x18002ddef  sub     rsp, 2B0h
0x18002ddf6  mov     rax, cs:__security_cookie
0x18002ddfd  xor     rax, rsp
0x18002de00  mov     [rbp+1C0h+var_20], rax
0x18002de07  movsxd  r14, edx
0x18002de0a  mov     rsi, rcx
0x18002de0d  xor     edx, edx; Val
0x18002de0f  mov     [rbp+1C0h+hKey], 0
0x18002de17  lea     rcx, [rbp+1C0h+var_230]; void *
0x18002de1b  mov     dword ptr [rsp+2C0h+Data], 0
0x18002de23  mov     r8d, 20Ah; Size
0x18002de29  mov     [rsp+2C0h+ppszPath], 0
0x18002de32  call    memset_0
0x18002de37  lea     r9, [rsp+2C0h+ppszPath]; ppszPath
0x18002de3c  xor     r8d, r8d; hToken
0x18002de3f  xor     edx, edx; dwFlags
0x18002de41  lea     rcx, FOLDERID_Windows; rfid
0x18002de48  call    cs:__imp_SHGetKnownFolderPath
0x18002de4e  mov     ebx, eax
0x18002de50  test    eax, eax
0x18002de52  jns     loc_18002DEE1
0x18002de58  xor     r8d, r8d
0x18002de5b  mov     edx, eax
0x18002de5d  xor     ecx, ecx
0x18002de5f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002de64  mov     ecx, cs:dword_180084170
0x18002de6a  cmp     ecx, 3
0x18002de6d  jbe     loc_18002E3B2
0x18002de73  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002de7a  mov     [rsp+2C0h+var_260], rax
0x18002de7f  lea     rdx, byte_1800797F3
0x18002de86  lea     rax, aShgetknownfold_0; "SHGetKnownFolderPath"
0x18002de8d  mov     [rsp+2C0h+var_258], rax
0x18002de92  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002de99  mov     [rsp+2C0h+var_268], rax
0x18002de9e  lea     rax, [rsp+2C0h+var_260]
0x18002dea3  mov     [rsp+2C0h+phkResult], rax
0x18002dea8  lea     rax, [rsp+2C0h+var_270]
0x18002dead  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18002deb2  lea     rax, [rsp+2C0h+var_258]
0x18002deb7  mov     qword ptr [rsp+2C0h+samDesired], rax
0x18002debc  lea     rax, [rsp+2C0h+var_268]
0x18002dec1  xor     r9d, r9d
0x18002dec4  mov     [rsp+2C0h+var_270], ebx
0x18002dec8  xor     r8d, r8d
0x18002decb  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18002ded0  lea     rcx, dword_180084170
0x18002ded7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002dedc  jmp     loc_18002E3B2
0x18002dee1  mov     r9, [rsp+2C0h+ppszPath]
0x18002dee6  lea     rcx, off_18005F178; "defltbase.inf"
0x18002deed  mov     rax, [rcx+r14*8]
0x18002def1  lea     r8, aSInfS; "%s\\inf\\%s"
0x18002def8  lea     rcx, [rbp+1C0h+var_230]; unsigned __int16 *
0x18002defc  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18002df01  mov     edx, 105h; unsigned __int64
0x18002df06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002df0b  mov     ebx, eax
0x18002df0d  test    eax, eax
0x18002df0f  jns     short loc_18002DF7F
0x18002df11  xor     r8d, r8d
0x18002df14  mov     edx, eax
0x18002df16  xor     ecx, ecx
0x18002df18  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002df1d  mov     eax, cs:dword_180084170
0x18002df23  cmp     eax, 3
0x18002df26  jbe     loc_18002E3B2
0x18002df2c  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002df33  mov     [rsp+2C0h+var_268], rax
0x18002df38  lea     rdx, byte_1800797B3
0x18002df3f  lea     rax, aStringcchprint_0; "StringCchPrintfW"
0x18002df46  mov     [rsp+2C0h+var_258], rax
0x18002df4b  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002df52  mov     [rsp+2C0h+var_260], rax
0x18002df57  lea     rax, [rsp+2C0h+var_268]
0x18002df5c  mov     [rsp+2C0h+phkResult], rax
0x18002df61  lea     rax, [rsp+2C0h+var_270]
0x18002df66  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18002df6b  lea     rax, [rsp+2C0h+var_258]
0x18002df70  mov     qword ptr [rsp+2C0h+samDesired], rax
0x18002df75  lea     rax, [rsp+2C0h+var_260]
0x18002df7a  jmp     loc_18002DEC1
0x18002df7f  xor     r9d, r9d
0x18002df82  mov     qword ptr [rsp+2C0h+samDesired], 0
0x18002df8b  xor     edx, edx
0x18002df8d  mov     qword ptr [rsp+2C0h+dwOptions], 0
0x18002df96  lea     rcx, [rbp+1C0h+var_230]
0x18002df9a  lea     r8d, [r9+60h]
0x18002df9e  call    cs:__imp_SceSetupSystemByInfName
0x18002dfa4  mov     ebx, eax
0x18002dfa6  mov     r13d, 80070000h
0x18002dfac  test    eax, eax
0x18002dfae  jz      short loc_18002E02A
0x18002dfb0  jle     short loc_18002DFB8
0x18002dfb2  movzx   ebx, ax
0x18002dfb5  or      ebx, r13d
0x18002dfb8  test    ebx, ebx
0x18002dfba  jns     short loc_18002E02A
0x18002dfbc  xor     r8d, r8d
0x18002dfbf  mov     edx, ebx
0x18002dfc1  xor     ecx, ecx
0x18002dfc3  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002dfc8  mov     eax, cs:dword_180084170
0x18002dfce  cmp     eax, 3
0x18002dfd1  jbe     loc_18002E3B2
0x18002dfd7  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002dfde  mov     [rsp+2C0h+var_268], rax
0x18002dfe3  lea     rdx, byte_180079773
0x18002dfea  lea     rax, aScesetupsystem_0; "SceSetupSystemByInfName"
0x18002dff1  mov     [rsp+2C0h+var_258], rax
0x18002dff6  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002dffd  mov     [rsp+2C0h+var_260], rax
0x18002e002  lea     rax, [rsp+2C0h+var_268]
0x18002e007  mov     [rsp+2C0h+phkResult], rax
0x18002e00c  lea     rax, [rsp+2C0h+var_270]
0x18002e011  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18002e016  lea     rax, [rsp+2C0h+var_258]
0x18002e01b  mov     qword ptr [rsp+2C0h+samDesired], rax
0x18002e020  lea     rax, [rsp+2C0h+var_260]
0x18002e025  jmp     loc_18002DEC1
0x18002e02a  mov     eax, cs:dword_180084170
0x18002e030  cmp     eax, 4
0x18002e033  jbe     short loc_18002E064
0x18002e035  lea     rax, aAppliedSecurit; "applied security template"
0x18002e03c  xor     r9d, r9d
0x18002e03f  mov     [rsp+2C0h+var_268], rax
0x18002e044  lea     rdx, byte_18007974D
0x18002e04b  lea     rax, [rsp+2C0h+var_268]
0x18002e050  xor     r8d, r8d
0x18002e053  lea     rcx, dword_180084170
0x18002e05a  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18002e05f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002e064  mov     rax, cs:off_18005F188; "rdshup.inf"
0x18002e06b  lea     r8, aSInfS; "%s\\inf\\%s"
0x18002e072  mov     r9, [rsp+2C0h+ppszPath]
0x18002e077  lea     rcx, [rbp+1C0h+var_230]; unsigned __int16 *
0x18002e07b  mov     edx, 105h; unsigned __int64
0x18002e080  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18002e085  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e08a  mov     ebx, eax
0x18002e08c  test    eax, eax
0x18002e08e  jns     short loc_18002E0FE
0x18002e090  xor     r8d, r8d
0x18002e093  mov     edx, eax
0x18002e095  xor     ecx, ecx
0x18002e097  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e09c  mov     eax, cs:dword_180084170
0x18002e0a2  cmp     eax, 3
0x18002e0a5  jbe     loc_18002E3B2
0x18002e0ab  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002e0b2  mov     [rsp+2C0h+var_268], rax
0x18002e0b7  lea     rdx, byte_18007970D
0x18002e0be  lea     rax, aStringcchprint_0; "StringCchPrintfW"
0x18002e0c5  mov     [rsp+2C0h+var_258], rax
0x18002e0ca  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e0d1  mov     [rsp+2C0h+var_260], rax
0x18002e0d6  lea     rax, [rsp+2C0h+var_268]
0x18002e0db  mov     [rsp+2C0h+phkResult], rax
0x18002e0e0  lea     rax, [rsp+2C0h+var_270]
0x18002e0e5  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18002e0ea  lea     rax, [rsp+2C0h+var_258]
0x18002e0ef  mov     qword ptr [rsp+2C0h+samDesired], rax
0x18002e0f4  lea     rax, [rsp+2C0h+var_260]
0x18002e0f9  jmp     loc_18002DEC1
0x18002e0fe  xor     edx, edx
0x18002e100  mov     qword ptr [rsp+2C0h+samDesired], 0
0x18002e109  mov     r8d, 0FFFFh
0x18002e10f  mov     qword ptr [rsp+2C0h+dwOptions], 0
0x18002e118  lea     rcx, [rbp+1C0h+var_230]
0x18002e11c  lea     r9d, [rdx+10h]
0x18002e120  call    cs:__imp_SceSetupSystemByInfName
0x18002e126  test    eax, eax
0x18002e128  jz      short loc_18002E1A8
0x18002e12a  jg      short loc_18002E130
0x18002e12c  mov     ebx, eax
0x18002e12e  jmp     short loc_18002E136
0x18002e130  movzx   ebx, ax
0x18002e133  or      ebx, r13d
0x18002e136  test    ebx, ebx
0x18002e138  jns     short loc_18002E1A8
0x18002e13a  xor     r8d, r8d
0x18002e13d  mov     edx, ebx
0x18002e13f  xor     ecx, ecx
0x18002e141  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e146  mov     eax, cs:dword_180084170
0x18002e14c  cmp     eax, 3
0x18002e14f  jbe     loc_18002E3B2
0x18002e155  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002e15c  mov     [rsp+2C0h+var_268], rax
0x18002e161  lea     rdx, byte_1800796CD
0x18002e168  lea     rax, aScesetupsystem_0; "SceSetupSystemByInfName"
0x18002e16f  mov     [rsp+2C0h+var_258], rax
0x18002e174  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e17b  mov     [rsp+2C0h+var_260], rax
0x18002e180  lea     rax, [rsp+2C0h+var_268]
0x18002e185  mov     [rsp+2C0h+phkResult], rax
0x18002e18a  lea     rax, [rsp+2C0h+var_270]
0x18002e18f  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18002e194  lea     rax, [rsp+2C0h+var_258]
0x18002e199  mov     qword ptr [rsp+2C0h+samDesired], rax
0x18002e19e  lea     rax, [rsp+2C0h+var_260]
0x18002e1a3  jmp     loc_18002DEC1
0x18002e1a8  mov     eax, cs:dword_180084170
0x18002e1ae  cmp     eax, 4
0x18002e1b1  jbe     short loc_18002E1E2
0x18002e1b3  lea     rax, aAppliedRdshUpd; "applied RDSH-Update security template o"...
0x18002e1ba  xor     r9d, r9d
0x18002e1bd  mov     [rsp+2C0h+var_268], rax
0x18002e1c2  lea     rdx, byte_1800796A7
0x18002e1c9  lea     rax, [rsp+2C0h+var_268]
0x18002e1ce  xor     r8d, r8d
0x18002e1d1  lea     rcx, dword_180084170
0x18002e1d8  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18002e1dd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002e1e2  mov     [rsp+2C0h+lpdwDisposition], 0; lpdwDisposition
0x18002e1eb  lea     rax, [rbp+1C0h+hKey]
0x18002e1ef  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18002e1f4  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18002e1fb  mov     [rsp+2C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002e204  xor     r9d, r9d; lpClass
0x18002e207  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x18002e20f  xor     r8d, r8d; Reserved
0x18002e212  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e219  mov     [rsp+2C0h+dwOptions], 0; dwOptions
0x18002e221  call    cs:__imp_RegCreateKeyExW
0x18002e227  test    eax, eax
0x18002e229  jz      short loc_18002E2A9
0x18002e22b  jg      short loc_18002E231
0x18002e22d  mov     ebx, eax
0x18002e22f  jmp     short loc_18002E237
0x18002e231  movzx   ebx, ax
0x18002e234  or      ebx, r13d
0x18002e237  test    ebx, ebx
0x18002e239  jns     short loc_18002E2A9
0x18002e23b  xor     r8d, r8d
0x18002e23e  mov     edx, ebx
0x18002e240  xor     ecx, ecx
0x18002e242  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e247  mov     eax, cs:dword_180084170
0x18002e24d  cmp     eax, 3
0x18002e250  jbe     loc_18002E3B2
0x18002e256  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002e25d  mov     [rsp+2C0h+var_268], rax
0x18002e262  lea     rdx, byte_180079667
0x18002e269  lea     rax, aRegcreatekeyex; "RegCreateKeyEx REG_CONTROL_TSERVER fail"...
0x18002e270  mov     [rsp+2C0h+var_258], rax
0x18002e275  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e27c  mov     [rsp+2C0h+var_260], rax
0x18002e281  lea     rax, [rsp+2C0h+var_268]
0x18002e286  mov     [rsp+2C0h+phkResult], rax
0x18002e28b  lea     rax, [rsp+2C0h+var_270]
0x18002e290  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18002e295  lea     rax, [rsp+2C0h+var_258]
0x18002e29a  mov     qword ptr [rsp+2C0h+samDesired], rax
0x18002e29f  lea     rax, [rsp+2C0h+var_260]
0x18002e2a4  jmp     loc_18002DEC1
0x18002e2a9  mov     rcx, [rbp+1C0h+hKey]; hKey
0x18002e2ad  lea     rax, [rsp+2C0h+Data]
0x18002e2b2  mov     [rsp+2C0h+samDesired], 4; cbData
0x18002e2ba  lea     rdx, aSecuritytempla; "SecurityTemplate"
0x18002e2c1  mov     r9d, 4; dwType
0x18002e2c7  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18002e2cc  xor     r8d, r8d; Reserved
0x18002e2cf  mov     dword ptr [rsp+2C0h+Data], r14d
0x18002e2d4  call    cs:__imp_RegSetValueExW
0x18002e2da  test    eax, eax
0x18002e2dc  jz      short loc_18002E35C
0x18002e2de  jg      short loc_18002E2E4
0x18002e2e0  mov     ebx, eax
0x18002e2e2  jmp     short loc_18002E2EA
0x18002e2e4  movzx   ebx, ax
0x18002e2e7  or      ebx, r13d
0x18002e2ea  test    ebx, ebx
0x18002e2ec  jns     short loc_18002E35C
0x18002e2ee  xor     r8d, r8d
0x18002e2f1  mov     edx, ebx
0x18002e2f3  xor     ecx, ecx
0x18002e2f5  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e2fa  mov     eax, cs:dword_180084170
0x18002e300  cmp     eax, 3
0x18002e303  jbe     loc_18002E3B2
0x18002e309  lea     rax, aApplysecurityt_0; "ApplySecurityTemplate"
0x18002e310  mov     [rsp+2C0h+var_268], rax
0x18002e315  lea     rdx, byte_180079627
0x18002e31c  lea     rax, aRegsetvalueexR; "RegSetValueEx REG_VALUE_SECURITY_TEMPLA"...
0x18002e323  mov     [rsp+2C0h+var_258], rax
0x18002e328  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002e32f  mov     [rsp+2C0h+var_260], rax
0x18002e334  lea     rax, [rsp+2C0h+var_268]
0x18002e339  mov     [rsp+2C0h+phkResult], rax
0x18002e33e  lea     rax, [rsp+2C0h+var_270]
0x18002e343  mov     [rsp+2C0h+lpSecurityAttributes], rax
0x18002e348  lea     rax, [rsp+2C0h+var_258]
0x18002e34d  mov     qword ptr [rsp+2C0h+samDesired], rax
  ... truncated ...
```
