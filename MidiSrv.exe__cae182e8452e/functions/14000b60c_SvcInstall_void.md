# SvcInstall(void)

- ea: `0x14000b60c`
- end: `0x14000b962`
- name: `?SvcInstall@@YAXXZ`
- size: `854`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000ce08`

## callees

- `0x140001008`
- `0x140001094`
- `0x1400054c0`
- `0x1400060f8`
- `0x14000984c`
- `0x140009984`
- `0x1400099c0`
- `0x14000af90`
- `0x14000b60c`
- `0x14000ba28`
- `0x14000bf9c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000b69c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000b69c`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x14000b859`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x14000b859`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000b92e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000b938`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000b92e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000b938`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14000b776`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14000b776`

## string_xrefs

- `0x14000b6b4`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000b737`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000b796`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000b877`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000b642`: `SvcInstall`
- `0x14000b6ad`: `Cannot install service. Failed to retrieve module file name.`
- `0x14000b6d7`: `Cannot install service. Failed to retrieve module file name.`
- `0x14000b728`: `Cannot install service. Failed to compose quoted path.`
- `0x14000b75c`: `Cannot install service. Failed to compose quoted path.`
- `0x14000b78f`: `Cannot install service. OpenSCManager failed. This must be run as Administrator.`
- `0x14000b7b7`: `Cannot install service. OpenSCManager failed. This must be run as Administrator.`
- `0x14000b848`: `Windows MIDI Service (Preview)`
- `0x14000b870`: `Cannot install service. CreateService failed.`
- `0x14000b898`: `Cannot install service. CreateService failed.`
- `0x14000b8f4`: `Service install complete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void SvcInstall(void)
{
  _DWORD *v0; // rcx
  __int64 v1; // r8
  __int64 v2; // r9
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // eax
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const wchar_t *v10; // rax
  __int16 *v11; // rdx
  SC_HANDLE v12; // rbx
  _DWORD *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  _DWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  const char *dwServiceType; // [rsp+20h] [rbp-E0h]
  const char *dwServiceTypea; // [rsp+20h] [rbp-E0h]
  const char *dwStartType; // [rsp+28h] [rbp-D8h]
  SC_HANDLE hSCObject; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v23; // [rsp+78h] [rbp-88h] BYREF
  const char *v24; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR BinaryPathName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v0 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v0 > 4u )
  {
    hSCObject = (SC_HANDLE)"SvcInstall";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)v0,
      (__int64)word_140087132,
      v1,
      v2,
      &hSCObject);
  }
  memset_0(Filename, 0, 0x208u);
  memset_0(BinaryPathName, 0, 0x208u);
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
  {
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)0xCC,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
      "Cannot install service. Failed to retrieve module file name.",
      dwServiceType);
    v3 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v3 > 2u )
    {
      hSCObject = (SC_HANDLE)L"Cannot install service. Failed to retrieve module file name.";
      v23 = (const wchar_t *)"SvcInstall";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (__int64)v3,
        (__int64)qword_140086F88,
        v4,
        v5,
        &v23,
        &hSCObject);
    }
    return;
  }
  v6 = StringCbPrintfW(BinaryPathName, 0x104u, L"\"%s\"", Filename);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
      (const char *)(unsigned int)v6,
      (int)"Cannot install service. Failed to compose quoted path.",
      dwStartType);
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v7 <= 2u )
      return;
    v10 = L"Cannot install service. Failed to compose quoted path.";
    v11 = word_140086FE2;
LABEL_12:
    v23 = v10;
    hSCObject = (SC_HANDLE)"SvcInstall";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)v11,
      v8,
      v9,
      &hSCObject,
      &v23);
    return;
  }
  v12 = OpenSCManagerW(0, 0, 0xF003Fu);
  v24 = (const char *)v12;
  if ( !v12 )
  {
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)0xEE,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
      "Cannot install service. OpenSCManager failed. This must be run as Administrator.",
      dwServiceType);
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v7 <= 2u )
      return;
    v10 = L"Cannot install service. OpenSCManager failed. This must be run as Administrator.";
    v11 = word_1400870E2;
    goto LABEL_12;
  }
  hSCObject = CreateServiceW(
                v12,
                L"MidiSrv",
                L"Windows MIDI Service (Preview)",
                0xF01FFu,
                0x10u,
                3u,
                1u,
                BinaryPathName,
                0,
                0,
                0,
                L"LocalSystem",
                0);
  if ( hSCObject )
  {
    SvcUpdateDescription(&hSCObject);
    if ( (unsigned int)SvcSetStartTriggerRpc(&hSCObject) )
    {
      v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v16 > 4u )
      {
        v23 = L"Service install complete.";
        v24 = "SvcInstall";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (__int64)v16,
          (__int64)byte_140086B7B,
          v17,
          v18,
          &v24,
          &v23);
      }
    }
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
  }
  else
  {
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)0x10D,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
      "Cannot install service. CreateService failed.",
      dwServiceTypea);
    v13 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v13 > 2u )
    {
      v23 = L"Cannot install service. CreateService failed.";
      hSCObject = (SC_HANDLE)"SvcInstall";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (__int64)v13,
        (__int64)&word_140086E3E,
        v14,
        v15,
        &hSCObject,
        &v23);
    }
  }
  CloseServiceHandle(v12);
}

```

## disassembly

```asm
0x14000b60c  mov     [rsp-8+arg_0], rbx
0x14000b611  mov     [rsp-8+arg_8], rsi
0x14000b616  push    rbp
0x14000b617  lea     rbp, [rsp-3C0h]
0x14000b61f  sub     rsp, 4C0h
0x14000b626  mov     rax, cs:__security_cookie
0x14000b62d  xor     rax, rsp
0x14000b630  mov     [rbp+3C0h+var_10], rax
0x14000b637  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b63c  mov     rcx, [rax+8]
0x14000b640  mov     eax, [rcx]
0x14000b642  lea     rsi, aSvcinstall; "SvcInstall"
0x14000b649  cmp     eax, 4
0x14000b64c  jbe     short loc_14000B66A
0x14000b64e  mov     [rsp+4C0h+hSCObject], rsi
0x14000b653  lea     rax, [rsp+4C0h+hSCObject]
0x14000b658  mov     qword ptr [rsp+4C0h+dwServiceType], rax; char *
0x14000b65d  lea     rdx, word_140087132
0x14000b664  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000b669  nop
0x14000b66a  mov     ebx, 208h
0x14000b66f  mov     r8d, ebx; Size
0x14000b672  xor     edx, edx; Val
0x14000b674  lea     rcx, [rbp+3C0h+Filename]; void *
0x14000b678  call    memset_0
0x14000b67d  mov     r8d, ebx; Size
0x14000b680  xor     edx, edx; Val
0x14000b682  lea     rcx, [rbp+3C0h+BinaryPathName]; void *
0x14000b689  call    memset_0
0x14000b68e  mov     ebx, 104h
0x14000b693  mov     r8d, ebx; nSize
0x14000b696  lea     rdx, [rbp+3C0h+Filename]; lpFilename
0x14000b69a  xor     ecx, ecx; hModule
0x14000b69c  call    cs:__imp_GetModuleFileNameW
0x14000b6a2  test    eax, eax
0x14000b6a4  jnz     short loc_14000B703
0x14000b6a6  mov     rcx, [rbp+3C8h]; this
0x14000b6ad  lea     r9, aCannotInstallS_1; "Cannot install service. Failed to retri"...
0x14000b6b4  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000b6bb  lea     edx, [rbx-38h]; void *
0x14000b6be  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000b6c3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b6c8  mov     rcx, [rax+8]
0x14000b6cc  mov     eax, [rcx]
0x14000b6ce  cmp     eax, 2
0x14000b6d1  jbe     loc_14000B7E9
0x14000b6d7  lea     rax, aCannotInstallS_3; "Cannot install service. Failed to retri"...
0x14000b6de  mov     [rsp+4C0h+hSCObject], rax
0x14000b6e3  mov     [rsp+4C0h+var_448], rsi
0x14000b6e8  lea     rax, [rsp+4C0h+hSCObject]
0x14000b6ed  mov     qword ptr [rsp+4C0h+dwStartType], rax
0x14000b6f2  lea     rax, [rsp+4C0h+var_448]
0x14000b6f7  lea     rdx, qword_140086F88
0x14000b6fe  jmp     loc_14000B7DE
0x14000b703  lea     r9, [rbp+3C0h+Filename]
0x14000b707  lea     r8, aS; "\"%s\""
0x14000b70e  mov     rdx, rbx; unsigned __int64
0x14000b711  lea     rcx, [rbp+3C0h+BinaryPathName]; unsigned __int16 *
0x14000b718  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b71d  test    eax, eax
0x14000b71f  jns     short loc_14000B76C
0x14000b721  mov     rcx, [rbp+3C8h]; this
0x14000b728  lea     rdx, aCannotInstallS_2; "Cannot install service. Failed to compo"...
0x14000b72f  mov     qword ptr [rsp+4C0h+dwServiceType], rdx; int
0x14000b734  mov     r9d, eax; char *
0x14000b737  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000b73e  mov     edx, 0DDh; void *
0x14000b743  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000b748  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b74d  mov     rcx, [rax+8]
0x14000b751  mov     eax, [rcx]
0x14000b753  cmp     eax, 2
0x14000b756  jbe     loc_14000B7E9
0x14000b75c  lea     rax, aCannotInstallS; "Cannot install service. Failed to compo"...
0x14000b763  lea     rdx, word_140086FE2
0x14000b76a  jmp     short loc_14000B7C5
0x14000b76c  xor     edx, edx; lpDatabaseName
0x14000b76e  xor     ecx, ecx; lpMachineName
0x14000b770  mov     r8d, 0F003Fh; dwDesiredAccess
0x14000b776  call    cs:__imp_OpenSCManagerW
0x14000b77c  mov     rbx, rax
0x14000b77f  mov     [rbp+3C0h+var_440], rax
0x14000b783  test    rax, rax
0x14000b786  jnz     short loc_14000B7EE
0x14000b788  mov     rcx, [rbp+3C8h]; this
0x14000b78f  lea     r9, aCannotInstallS_6; "Cannot install service. OpenSCManager f"...
0x14000b796  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000b79d  mov     edx, 0EEh; void *
0x14000b7a2  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000b7a7  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b7ac  mov     rcx, [rax+8]
0x14000b7b0  mov     eax, [rcx]
0x14000b7b2  cmp     eax, 2
0x14000b7b5  jbe     short loc_14000B7E9
0x14000b7b7  lea     rax, aCannotInstallS_4; "Cannot install service. OpenSCManager f"...
0x14000b7be  lea     rdx, word_1400870E2
0x14000b7c5  mov     [rsp+4C0h+var_448], rax
0x14000b7ca  lea     rax, [rsp+4C0h+var_448]
0x14000b7cf  mov     qword ptr [rsp+4C0h+dwStartType], rax
0x14000b7d4  lea     rax, [rsp+4C0h+hSCObject]
0x14000b7d9  mov     [rsp+4C0h+hSCObject], rsi
0x14000b7de  mov     qword ptr [rsp+4C0h+dwServiceType], rax
0x14000b7e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000b7e8  nop
0x14000b7e9  jmp     loc_14000B93E
0x14000b7ee  mov     [rsp+4C0h+lpPassword], 0; lpPassword
0x14000b7f7  lea     rax, ServiceStartName; "LocalSystem"
0x14000b7fe  mov     [rsp+4C0h+lpServiceStartName], rax; lpServiceStartName
0x14000b803  mov     [rsp+4C0h+lpDependencies], 0; lpDependencies
0x14000b80c  mov     [rsp+4C0h+lpdwTagId], 0; lpdwTagId
0x14000b815  mov     [rsp+4C0h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x14000b81e  lea     rax, [rbp+3C0h+BinaryPathName]
0x14000b825  mov     [rsp+4C0h+lpBinaryPathName], rax; lpBinaryPathName
0x14000b82a  mov     [rsp+4C0h+dwErrorControl], 1; dwErrorControl
0x14000b832  mov     [rsp+4C0h+dwStartType], 3; dwStartType
0x14000b83a  mov     [rsp+4C0h+dwServiceType], 10h; char *
0x14000b842  mov     r9d, 0F01FFh; dwDesiredAccess
0x14000b848  lea     r8, DisplayName; "Windows MIDI Service (Preview)"
0x14000b84f  lea     rdx, ServiceName; "MidiSrv"
0x14000b856  mov     rcx, rbx; hSCManager
0x14000b859  call    cs:__imp_CreateServiceW
0x14000b85f  mov     [rsp+4C0h+hSCObject], rax
0x14000b864  test    rax, rax
0x14000b867  jnz     short loc_14000B8CC
0x14000b869  mov     rcx, [rbp+3C8h]; this
0x14000b870  lea     r9, aCannotInstallS_5; "Cannot install service. CreateService f"...
0x14000b877  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000b87e  mov     edx, 10Dh; void *
0x14000b883  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000b888  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b88d  mov     rcx, [rax+8]
0x14000b891  mov     eax, [rcx]
0x14000b893  cmp     eax, 2
0x14000b896  jbe     short loc_14000B8CA
0x14000b898  lea     rax, aCannotInstallS_0; "Cannot install service. CreateService f"...
0x14000b89f  mov     [rsp+4C0h+var_448], rax
0x14000b8a4  mov     [rsp+4C0h+hSCObject], rsi
0x14000b8a9  lea     rax, [rsp+4C0h+var_448]
0x14000b8ae  mov     qword ptr [rsp+4C0h+dwStartType], rax
0x14000b8b3  lea     rax, [rsp+4C0h+hSCObject]
0x14000b8b8  mov     qword ptr [rsp+4C0h+dwServiceType], rax
0x14000b8bd  lea     rdx, word_140086E3E
0x14000b8c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000b8c9  nop
0x14000b8ca  jmp     short loc_14000B935
0x14000b8cc  lea     rcx, [rsp+4C0h+hSCObject]
0x14000b8d1  call    ?SvcUpdateDescription@@YAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; SvcUpdateDescription(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &)
0x14000b8d6  lea     rcx, [rsp+4C0h+hSCObject]
0x14000b8db  call    ?SvcSetStartTriggerRpc@@YAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; SvcSetStartTriggerRpc(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &)
0x14000b8e0  test    eax, eax
0x14000b8e2  jz      short loc_14000B924
0x14000b8e4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b8e9  mov     rcx, [rax+8]
0x14000b8ed  mov     eax, [rcx]
0x14000b8ef  cmp     eax, 4
0x14000b8f2  jbe     short loc_14000B924
0x14000b8f4  lea     rax, aServiceInstall; "Service install complete."
0x14000b8fb  mov     [rsp+4C0h+var_448], rax
0x14000b900  mov     [rbp+3C0h+var_440], rsi
0x14000b904  lea     rax, [rsp+4C0h+var_448]
0x14000b909  mov     qword ptr [rsp+4C0h+dwStartType], rax
0x14000b90e  lea     rax, [rbp+3C0h+var_440]
0x14000b912  mov     qword ptr [rsp+4C0h+dwServiceType], rax
0x14000b917  lea     rdx, byte_140086B7B
0x14000b91e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000b923  nop
0x14000b924  mov     rcx, [rsp+4C0h+hSCObject]; hSCObject
0x14000b929  test    rcx, rcx
0x14000b92c  jz      short loc_14000B935
0x14000b92e  call    cs:__imp_CloseServiceHandle
0x14000b934  nop
0x14000b935  mov     rcx, rbx; hSCObject
0x14000b938  call    cs:__imp_CloseServiceHandle
0x14000b93e  mov     rcx, [rbp+3C0h+var_10]
0x14000b945  xor     rcx, rsp; StackCookie
0x14000b948  call    __security_check_cookie
0x14000b94d  lea     r11, [rsp+4C0h+var_s0]
0x14000b955  mov     rbx, [r11+10h]
0x14000b959  mov     rsi, [r11+18h]
0x14000b95d  mov     rsp, r11
0x14000b960  pop     rbp
0x14000b961  retn
```
