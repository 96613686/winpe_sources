# SvcUninstall(void)

- ea: `0x14000bbbc`
- end: `0x14000bf93`
- name: `?SvcUninstall@@YAXXZ`
- size: `983`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14000ce08`

## callees

- `0x140001008`
- `0x140001094`
- `0x1400054c0`
- `0x14000984c`
- `0x140009984`
- `0x14000bbbc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000bd56`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000bd56`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x14000bc78`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x14000bd90`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x14000bc78`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x14000bd90`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14000bc4e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x14000bc4e`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x14000be0c`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x14000be0c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000beb2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000bf16`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000beb2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000bf16`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14000bc2c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x14000bc2c`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14000bcfb`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x14000bcfb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000bd48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000bd5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000bd48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000bd5c`

## string_xrefs

- `0x14000bc8d`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000bd10`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000bdbb`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000be25`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000be61`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000bec5`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000bf29`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000bbe4`: `SvcUninstall`
- `0x14000bf22`: `Cannot uninstall service. OpenSCManager failed`
- `0x14000bf4a`: `Cannot uninstall service. OpenSCManager failed.`
- `0x14000bebe`: `Cannot uninstall service. OpenService failed`
- `0x14000bee6`: `Cannot uninstall service. OpenService failed.`
- `0x14000bc86`: `Cannot uninstall service. QueryServiceStatusEx failed`
- `0x14000bcb2`: `Cannot uninstall service. QueryServiceStatusEx failed.`
- `0x14000bd09`: `Cannot uninstall service. Service is not stopped and SERVICE_CONTROL_STOP failed`
- `0x14000bd35`: `Cannot uninstall service. Service is not stopped and SERVICE_CONTROL_STOP failed.`
- `0x14000be5a`: `Cannot uninstall service. QueryServiceStatusEx after SERVICE_CONTROL_STOP failed.`
- `0x14000be82`: `Cannot uninstall service. QueryServiceStatusEx after SERVICE_CONTROL_STOP failed.`
- `0x14000bdb4`: `Service did not stop during uninstall. Calling DeleteService anyway, but deletion will pend.`
- `0x14000bddc`: `Service did not stop during uninstall. Calling DeleteService anyway, but deletion will pend.`
- `0x14000be1e`: `Cannot uninstall service. DeleteService failed.`
- `0x14000be46`: `Cannot uninstall service. DeleteService failed.`

## pseudocode

```c
void SvcUninstall(void)
{
  _DWORD *v0; // rcx
  __int64 v1; // r8
  __int64 v2; // r9
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // rbx
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const wchar_t *v12; // rax
  char *v13; // rdx
  ULONGLONG TickCount64; // r14
  ULONGLONG v15; // rsi
  _DWORD *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  _DWORD *v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  _DWORD *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  const char *pcbBytesNeeded; // [rsp+20h] [rbp-59h]
  const char *pcbBytesNeededa; // [rsp+20h] [rbp-59h]
  char v27[8]; // [rsp+30h] [rbp-49h] BYREF
  const wchar_t *v28; // [rsp+38h] [rbp-41h] BYREF
  DWORD v29; // [rsp+40h] [rbp-39h] BYREF
  BYTE Buffer[16]; // [rsp+48h] [rbp-31h] BYREF
  __int128 v31; // [rsp+58h] [rbp-21h]
  int v32; // [rsp+68h] [rbp-11h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v0 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v0 > 4u )
  {
    *(_QWORD *)v27 = "SvcUninstall";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)v0,
      (__int64)byte_140086E6B,
      v1,
      v2,
      v27);
  }
  v32 = 0;
  v29 = 0;
  *(_OWORD *)Buffer = 0;
  v31 = 0;
  v3 = OpenSCManagerW(0, 0, 0xF003Fu);
  v4 = v3;
  if ( v3 )
  {
    v5 = OpenServiceW(v3, L"MidiSrv", 0x10024u);
    if ( !v5 )
    {
      wil::details::in1diag3::Log_GetLastErrorMsg(
        retaddr,
        (void *)0x159,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
        "Cannot uninstall service. OpenService failed",
        pcbBytesNeeded);
      v19 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v19 > 2u )
      {
        *(_QWORD *)v27 = "SvcUninstall";
        v28 = L"Cannot uninstall service. OpenService failed.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (__int64)v19,
          (__int64)&word_140086B4E,
          v20,
          v21,
          v27,
          &v28);
      }
      goto LABEL_27;
    }
    if ( !QueryServiceStatusEx(v5, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v29) )
    {
      wil::details::in1diag3::Log_GetLastErrorMsg(
        retaddr,
        (void *)0x168,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
        "Cannot uninstall service. QueryServiceStatusEx failed",
        pcbBytesNeededa);
      v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v6 > 2u )
      {
        v28 = (const wchar_t *)"SvcUninstall";
        *(_QWORD *)v27 = L"Cannot uninstall service. QueryServiceStatusEx failed.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (__int64)v6,
          (__int64)&word_140086E8E,
          v7,
          v8,
          &v28,
          v27);
      }
      goto LABEL_24;
    }
    if ( *(_DWORD *)&Buffer[4] == 1 )
    {
LABEL_18:
      if ( DeleteService(v5) )
        goto LABEL_24;
      wil::details::in1diag3::Log_GetLastErrorMsg(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
        "Cannot uninstall service. DeleteService failed.",
        pcbBytesNeededa);
      v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v9 <= 2u )
        goto LABEL_24;
      v12 = L"Cannot uninstall service. DeleteService failed.";
      v13 = byte_140086FB5;
    }
    else
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( ControlService(v5, 1u, &ServiceStatus) )
      {
        TickCount64 = GetTickCount64();
        while ( 1 )
        {
          Sleep(0x1F4u);
          v15 = GetTickCount64();
          v32 = 0;
          v29 = 0;
          *(_OWORD *)Buffer = 0;
          v31 = 0;
          if ( !QueryServiceStatusEx(v5, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v29) )
            break;
          if ( *(_DWORD *)&Buffer[4] == 1 )
            goto LABEL_18;
          if ( v15 - TickCount64 >= 0x7530 )
          {
            wil::details::in1diag3::Log_GetLastErrorMsg(
              retaddr,
              (void *)0x1A6,
              (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
              "Service did not stop during uninstall. Calling DeleteService anyway, but deletion will pend.",
              pcbBytesNeededa);
            v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
            if ( *v16 > 2u )
            {
              *(_QWORD *)v27 = "SvcUninstall";
              v28 = L"Service did not stop during uninstall. Calling DeleteService anyway, but deletion will pend.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                (__int64)v16,
                (__int64)&dword_14008703C,
                v17,
                v18,
                v27,
                &v28);
            }
            goto LABEL_18;
          }
        }
        wil::details::in1diag3::Log_GetLastErrorMsg(
          retaddr,
          (void *)0x195,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
          "Cannot uninstall service. QueryServiceStatusEx after SERVICE_CONTROL_STOP failed.",
          pcbBytesNeededa);
        v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v9 <= 2u )
          goto LABEL_24;
        v12 = L"Cannot uninstall service. QueryServiceStatusEx after SERVICE_CONTROL_STOP failed.";
        v13 = byte_140086F5B;
      }
      else
      {
        wil::details::in1diag3::Log_GetLastErrorMsg(
          retaddr,
          (void *)0x17C,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
          "Cannot uninstall service. Service is not stopped and SERVICE_CONTROL_STOP failed",
          pcbBytesNeededa);
        v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v9 <= 2u )
        {
LABEL_24:
          CloseServiceHandle(v5);
LABEL_27:
          CloseServiceHandle(v4);
          return;
        }
        v12 = L"Cannot uninstall service. Service is not stopped and SERVICE_CONTROL_STOP failed.";
        v13 = byte_140086B21;
      }
    }
    v28 = v12;
    *(_QWORD *)v27 = "SvcUninstall";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (__int64)v13,
      v10,
      v11,
      v27,
      &v28);
    goto LABEL_24;
  }
  wil::details::in1diag3::Log_GetLastErrorMsg(
    retaddr,
    (void *)0x149,
    (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
    "Cannot uninstall service. OpenSCManager failed",
    pcbBytesNeeded);
  v22 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v22 > 2u )
  {
    *(_QWORD *)v27 = "SvcUninstall";
    v28 = L"Cannot uninstall service. OpenSCManager failed.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (__int64)v22,
      (__int64)byte_140086F01,
      v23,
      v24,
      v27,
      &v28);
  }
}

```

## disassembly

```asm
0x14000bbbc  push    rbp
0x14000bbbe  push    rbx
0x14000bbbf  push    rsi
0x14000bbc0  push    rdi
0x14000bbc1  push    r14
0x14000bbc3  push    r15
0x14000bbc5  lea     rbp, [rsp-2Fh]
0x14000bbca  sub     rsp, 0A8h
0x14000bbd1  mov     rax, cs:__security_cookie
0x14000bbd8  xor     rax, rsp
0x14000bbdb  mov     [rbp+57h+var_40], rax
0x14000bbdf  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bbe4  lea     r15, aSvcuninstall; "SvcUninstall"
0x14000bbeb  mov     rcx, [rax+8]
0x14000bbef  mov     eax, [rcx]
0x14000bbf1  cmp     eax, 4
0x14000bbf4  jbe     short loc_14000BC0F
0x14000bbf6  lea     rax, [rbp+57h+var_A0]
0x14000bbfa  mov     qword ptr [rbp+57h+var_A0], r15
0x14000bbfe  lea     rdx, byte_140086E6B
0x14000bc05  mov     [rsp+0D0h+pcbBytesNeeded], rax; char *
0x14000bc0a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000bc0f  xorps   xmm0, xmm0
0x14000bc12  xor     eax, eax
0x14000bc14  xor     edx, edx; lpDatabaseName
0x14000bc16  mov     [rbp+57h+var_68], eax
0x14000bc19  xor     ecx, ecx; lpMachineName
0x14000bc1b  mov     [rbp+57h+var_90], eax
0x14000bc1e  mov     r8d, 0F003Fh; dwDesiredAccess
0x14000bc24  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x14000bc28  movups  [rbp+57h+var_78], xmm0
0x14000bc2c  call    cs:__imp_OpenSCManagerW
0x14000bc32  mov     rdi, rax
0x14000bc35  test    rax, rax
0x14000bc38  jz      loc_14000BF1E
0x14000bc3e  mov     r8d, 10024h; dwDesiredAccess
0x14000bc44  lea     rdx, ServiceName; "MidiSrv"
0x14000bc4b  mov     rcx, rax; hSCManager
0x14000bc4e  call    cs:__imp_OpenServiceW
0x14000bc54  mov     rbx, rax
0x14000bc57  test    rax, rax
0x14000bc5a  jz      loc_14000BEBA
0x14000bc60  lea     rax, [rbp+57h+var_90]
0x14000bc64  mov     r9d, 24h ; '$'; cbBufSize
0x14000bc6a  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14000bc6e  mov     [rsp+0D0h+pcbBytesNeeded], rax; char *
0x14000bc73  xor     edx, edx; InfoLevel
0x14000bc75  mov     rcx, rbx; hService
0x14000bc78  call    cs:__imp_QueryServiceStatusEx
0x14000bc7e  test    eax, eax
0x14000bc80  jnz     short loc_14000BCDA
0x14000bc82  mov     rcx, [rbp+5Fh]; this
0x14000bc86  lea     r9, aCannotUninstal_0; "Cannot uninstall service. QueryServiceS"...
0x14000bc8d  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000bc94  mov     edx, 168h; void *
0x14000bc99  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000bc9e  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bca3  mov     rcx, [rax+8]
0x14000bca7  mov     eax, [rcx]
0x14000bca9  cmp     eax, 2
0x14000bcac  jbe     loc_14000BEAF
0x14000bcb2  lea     rax, aCannotUninstal; "Cannot uninstall service. QueryServiceS"...
0x14000bcb9  mov     [rbp+57h+var_98], r15
0x14000bcbd  mov     qword ptr [rbp+57h+var_A0], rax
0x14000bcc1  lea     rdx, word_140086E8E
0x14000bcc8  lea     rax, [rbp+57h+var_A0]
0x14000bccc  mov     [rsp+0D0h+var_A8], rax
0x14000bcd1  lea     rax, [rbp+57h+var_98]
0x14000bcd5  jmp     loc_14000BEA5
0x14000bcda  cmp     dword ptr [rbp+57h+Buffer+4], 1
0x14000bcde  jz      loc_14000BE09
0x14000bce4  xorps   xmm0, xmm0
0x14000bce7  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x14000bceb  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x14000bcef  mov     edx, 1; dwControl
0x14000bcf4  mov     rcx, rbx; hService
0x14000bcf7  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x14000bcfb  call    cs:__imp_ControlService
0x14000bd01  test    eax, eax
0x14000bd03  jnz     short loc_14000BD48
0x14000bd05  mov     rcx, [rbp+5Fh]; this
0x14000bd09  lea     r9, aCannotUninstal_6; "Cannot uninstall service. Service is no"...
0x14000bd10  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000bd17  mov     edx, 17Ch; void *
0x14000bd1c  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000bd21  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bd26  mov     rcx, [rax+8]
0x14000bd2a  mov     eax, [rcx]
0x14000bd2c  cmp     eax, 2
0x14000bd2f  jbe     loc_14000BEAF
0x14000bd35  lea     rax, aCannotUninstal_2; "Cannot uninstall service. Service is no"...
0x14000bd3c  lea     rdx, byte_140086B21
0x14000bd43  jmp     loc_14000BE90
0x14000bd48  call    cs:__imp_GetTickCount64
0x14000bd4e  mov     r14, rax
0x14000bd51  mov     ecx, 1F4h; dwMilliseconds
0x14000bd56  call    cs:__imp_Sleep
0x14000bd5c  call    cs:__imp_GetTickCount64
0x14000bd62  xorps   xmm0, xmm0
0x14000bd65  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14000bd69  mov     rsi, rax
0x14000bd6c  mov     r9d, 24h ; '$'; cbBufSize
0x14000bd72  xor     eax, eax
0x14000bd74  xor     edx, edx; InfoLevel
0x14000bd76  mov     [rbp+57h+var_68], eax
0x14000bd79  mov     rcx, rbx; hService
0x14000bd7c  mov     [rbp+57h+var_90], eax
0x14000bd7f  lea     rax, [rbp+57h+var_90]
0x14000bd83  mov     [rsp+0D0h+pcbBytesNeeded], rax; char *
0x14000bd88  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x14000bd8c  movups  [rbp+57h+var_78], xmm0
0x14000bd90  call    cs:__imp_QueryServiceStatusEx
0x14000bd96  test    eax, eax
0x14000bd98  jz      loc_14000BE56
0x14000bd9e  cmp     dword ptr [rbp+57h+Buffer+4], 1
0x14000bda2  jz      short loc_14000BE09
0x14000bda4  sub     rsi, r14
0x14000bda7  cmp     rsi, 7530h
0x14000bdae  jb      short loc_14000BD51
0x14000bdb0  mov     rcx, [rbp+5Fh]; this
0x14000bdb4  lea     r9, aServiceDidNotS; "Service did not stop during uninstall. "...
0x14000bdbb  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000bdc2  mov     edx, 1A6h; void *
0x14000bdc7  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000bdcc  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bdd1  mov     rcx, [rax+8]
0x14000bdd5  mov     eax, [rcx]
0x14000bdd7  cmp     eax, 2
0x14000bdda  jbe     short loc_14000BE09
0x14000bddc  lea     rax, aServiceDidNotS_0; "Service did not stop during uninstall. "...
0x14000bde3  mov     qword ptr [rbp+57h+var_A0], r15
0x14000bde7  mov     [rbp+57h+var_98], rax
0x14000bdeb  lea     rdx, dword_14008703C
0x14000bdf2  lea     rax, [rbp+57h+var_98]
0x14000bdf6  mov     [rsp+0D0h+var_A8], rax
0x14000bdfb  lea     rax, [rbp+57h+var_A0]
0x14000bdff  mov     [rsp+0D0h+pcbBytesNeeded], rax; char *
0x14000be04  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000be09  mov     rcx, rbx; hService
0x14000be0c  call    cs:__imp_DeleteService
0x14000be12  test    eax, eax
0x14000be14  jnz     loc_14000BEAF
0x14000be1a  mov     rcx, [rbp+5Fh]; this
0x14000be1e  lea     r9, aCannotUninstal_7; "Cannot uninstall service. DeleteService"...
0x14000be25  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000be2c  mov     edx, 1B6h; void *
0x14000be31  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000be36  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000be3b  mov     rcx, [rax+8]
0x14000be3f  mov     eax, [rcx]
0x14000be41  cmp     eax, 2
0x14000be44  jbe     short loc_14000BEAF
0x14000be46  lea     rax, aCannotUninstal_8; "Cannot uninstall service. DeleteService"...
0x14000be4d  lea     rdx, byte_140086FB5
0x14000be54  jmp     short loc_14000BE90
0x14000be56  mov     rcx, [rbp+5Fh]; this
0x14000be5a  lea     r9, aCannotUninstal_3; "Cannot uninstall service. QueryServiceS"...
0x14000be61  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000be68  mov     edx, 195h; void *
0x14000be6d  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000be72  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000be77  mov     rcx, [rax+8]
0x14000be7b  mov     eax, [rcx]
0x14000be7d  cmp     eax, 2
0x14000be80  jbe     short loc_14000BEAF
0x14000be82  lea     rax, aCannotUninstal_5; "Cannot uninstall service. QueryServiceS"...
0x14000be89  lea     rdx, byte_140086F5B
0x14000be90  mov     [rbp+57h+var_98], rax
0x14000be94  lea     rax, [rbp+57h+var_98]
0x14000be98  mov     [rsp+0D0h+var_A8], rax
0x14000be9d  lea     rax, [rbp+57h+var_A0]
0x14000bea1  mov     qword ptr [rbp+57h+var_A0], r15
0x14000bea5  mov     [rsp+0D0h+pcbBytesNeeded], rax
0x14000beaa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000beaf  mov     rcx, rbx; hSCObject
0x14000beb2  call    cs:__imp_CloseServiceHandle
0x14000beb8  jmp     short loc_14000BF13
0x14000beba  mov     rcx, [rbp+5Fh]; this
0x14000bebe  lea     r9, aCannotUninstal_1; "Cannot uninstall service. OpenService f"...
0x14000bec5  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000becc  mov     edx, 159h; void *
0x14000bed1  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000bed6  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bedb  mov     rcx, [rax+8]
0x14000bedf  mov     eax, [rcx]
0x14000bee1  cmp     eax, 2
0x14000bee4  jbe     short loc_14000BF13
0x14000bee6  lea     rax, aCannotUninstal_10; "Cannot uninstall service. OpenService f"...
0x14000beed  mov     qword ptr [rbp+57h+var_A0], r15
0x14000bef1  mov     [rbp+57h+var_98], rax
0x14000bef5  lea     rdx, word_140086B4E
0x14000befc  lea     rax, [rbp+57h+var_98]
0x14000bf00  mov     [rsp+0D0h+var_A8], rax
0x14000bf05  lea     rax, [rbp+57h+var_A0]
0x14000bf09  mov     [rsp+0D0h+pcbBytesNeeded], rax
0x14000bf0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000bf13  mov     rcx, rdi; hSCObject
0x14000bf16  call    cs:__imp_CloseServiceHandle
0x14000bf1c  jmp     short loc_14000BF77
0x14000bf1e  mov     rcx, [rbp+5Fh]; this
0x14000bf22  lea     r9, aCannotUninstal_4; "Cannot uninstall service. OpenSCManager"...
0x14000bf29  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000bf30  mov     edx, 149h; void *
0x14000bf35  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000bf3a  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000bf3f  mov     rcx, [rax+8]
0x14000bf43  mov     eax, [rcx]
0x14000bf45  cmp     eax, 2
0x14000bf48  jbe     short loc_14000BF77
0x14000bf4a  lea     rax, aCannotUninstal_9; "Cannot uninstall service. OpenSCManager"...
0x14000bf51  mov     qword ptr [rbp+57h+var_A0], r15
0x14000bf55  mov     [rbp+57h+var_98], rax
0x14000bf59  lea     rdx, byte_140086F01
0x14000bf60  lea     rax, [rbp+57h+var_98]
0x14000bf64  mov     [rsp+0D0h+var_A8], rax
0x14000bf69  lea     rax, [rbp+57h+var_A0]
0x14000bf6d  mov     [rsp+0D0h+pcbBytesNeeded], rax
0x14000bf72  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000bf77  mov     rcx, [rbp+57h+var_40]
0x14000bf7b  xor     rcx, rsp; StackCookie
0x14000bf7e  call    __security_check_cookie
0x14000bf83  add     rsp, 0A8h
0x14000bf8a  pop     r15
0x14000bf8c  pop     r14
0x14000bf8e  pop     rdi
0x14000bf8f  pop     rsi
0x14000bf90  pop     rbx
0x14000bf91  pop     rbp
0x14000bf92  retn
```
