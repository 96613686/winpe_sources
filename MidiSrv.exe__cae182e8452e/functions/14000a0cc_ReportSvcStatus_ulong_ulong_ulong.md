# ReportSvcStatus(ulong,ulong,ulong)

- ea: `0x14000a0cc`
- end: `0x14000a258`
- name: `?ReportSvcStatus@@YAXKKK@Z`
- size: `396`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x14000b1f0`
- `0x14000b2b8`
- `0x14000b970`

## callees

- `0x140001094`
- `0x14000179c`
- `0x1400054c0`
- `0x14000984c`
- `0x140009984`
- `0x14000a0cc`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a1d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a1d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a111`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000a111`

## string_xrefs

- `0x14000a1e2`: `Failed to set the service status.`
- `0x14000a1e9`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000a208`: `Failed to set the service status.`

## pseudocode

```c
void __fastcall ReportSvcStatus(DWORD a1, DWORD a2, DWORD a3)
{
  _DWORD *v6; // r14
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // [rsp+20h] [rbp-49h]
  const char *v11; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v12[11]; // [rsp+38h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    LODWORD(v12[0]) = a1;
    LODWORD(v11) = GetCurrentProcessId();
    v12[10] = 4;
    v12[9] = &v11;
    v12[8] = 4;
    v12[7] = v12;
    v12[5] = "ReportSvcStatus";
    LODWORD(v10) = 5;
    v12[6] = 16;
    tlgWriteTransfer_EventWriteTransfer(v6, byte_140086CDD, 0, 0);
  }
  g_SvcStatus.dwCurrentState = a1;
  g_SvcStatus.dwWin32ExitCode = a2;
  g_SvcStatus.dwWaitHint = a3;
  if ( a1 == 2 )
  {
    g_SvcStatus.dwControlsAccepted = 0;
LABEL_7:
    g_SvcStatus.dwCheckPoint = dword_140096618++;
    goto LABEL_9;
  }
  g_SvcStatus.dwControlsAccepted = 1;
  if ( a1 != 4 && a1 != 1 )
    goto LABEL_7;
  g_SvcStatus.dwCheckPoint = 0;
LABEL_9:
  if ( !SetServiceStatus(g_SvcStatusHandle, &g_SvcStatus) )
  {
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)0x57,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
      "Failed to set the service status.",
      v10);
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v7 > 2u )
    {
      v11 = "ReportSvcStatus";
      v12[0] = L"Failed to set the service status.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (__int64)v7,
        (__int64)byte_1400871B9,
        v8,
        v9,
        &v11,
        v12);
    }
  }
}

```

## disassembly

```asm
0x14000a0cc  mov     [rsp-8+arg_18], rbx
0x14000a0d1  push    rbp
0x14000a0d2  push    rsi
0x14000a0d3  push    rdi
0x14000a0d4  push    r13
0x14000a0d6  push    r14
0x14000a0d8  lea     rbp, [rsp-37h]
0x14000a0dd  sub     rsp, 0A0h
0x14000a0e4  mov     rax, cs:__security_cookie
0x14000a0eb  xor     rax, rsp
0x14000a0ee  mov     [rbp+57h+var_30], rax
0x14000a0f2  mov     esi, r8d
0x14000a0f5  mov     edi, edx
0x14000a0f7  mov     ebx, ecx
0x14000a0f9  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000a0fe  lea     r13, aReportsvcstatu; "ReportSvcStatus"
0x14000a105  mov     r14, [rax+8]
0x14000a109  mov     eax, [r14]
0x14000a10c  cmp     eax, 4
0x14000a10f  jbe     short loc_14000A16F
0x14000a111  call    cs:__imp_GetCurrentProcessId
0x14000a117  xor     r9d, r9d
0x14000a11a  mov     dword ptr [rbp+57h+var_88], ebx
0x14000a11d  mov     dword ptr [rbp+57h+var_90], eax
0x14000a120  lea     rdx, byte_140086CDD
0x14000a127  lea     rax, [rbp+57h+var_90]
0x14000a12b  mov     [rbp+57h+var_38], 4
0x14000a133  mov     [rbp+57h+var_40], rax
0x14000a137  xor     r8d, r8d
0x14000a13a  lea     rax, [rbp+57h+var_88]
0x14000a13e  mov     [rbp+57h+var_48], 4
0x14000a146  mov     [rbp+57h+var_50], rax
0x14000a14a  mov     rcx, r14
0x14000a14d  lea     rax, [rbp+57h+var_80]
0x14000a151  mov     [rbp+57h+var_60], r13
0x14000a155  mov     [rsp+0C0h+var_98], rax
0x14000a15a  mov     dword ptr [rsp+0C0h+var_A0], 5; char *
0x14000a162  mov     [rbp+57h+var_58], 10h
0x14000a16a  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a16f  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS g_SvcStatus ...
0x14000a175  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, edi; _SERVICE_STATUS g_SvcStatus ...
0x14000a17b  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, esi; _SERVICE_STATUS g_SvcStatus ...
0x14000a181  cmp     ebx, 2
0x14000a184  jnz     short loc_14000A192
0x14000a186  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 0; _SERVICE_STATUS g_SvcStatus ...
0x14000a190  jmp     short loc_14000A1A6
0x14000a192  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1; _SERVICE_STATUS g_SvcStatus ...
0x14000a19c  cmp     ebx, 4
0x14000a19f  jz      short loc_14000A1BC
0x14000a1a1  cmp     ebx, 1
0x14000a1a4  jz      short loc_14000A1BC
0x14000a1a6  mov     eax, cs:dword_140096618
0x14000a1ac  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, eax; _SERVICE_STATUS g_SvcStatus ...
0x14000a1b2  inc     eax
0x14000a1b4  mov     cs:dword_140096618, eax
0x14000a1ba  jmp     short loc_14000A1C6
0x14000a1bc  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_SvcStatus ...
0x14000a1c6  mov     rcx, cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000a1cd  lea     rdx, ?g_SvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000a1d4  call    cs:__imp_SetServiceStatus
0x14000a1da  test    eax, eax
0x14000a1dc  jnz     short loc_14000A235
0x14000a1de  mov     rcx, [rbp+5Fh]; this
0x14000a1e2  lea     r9, aFailedToSetThe_0; "Failed to set the service status."
0x14000a1e9  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000a1f0  lea     edx, [rax+57h]; void *
0x14000a1f3  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000a1f8  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000a1fd  mov     rcx, [rax+8]
0x14000a201  mov     eax, [rcx]
0x14000a203  cmp     eax, 2
0x14000a206  jbe     short loc_14000A235
0x14000a208  lea     rax, aFailedToSetThe; "Failed to set the service status."
0x14000a20f  mov     [rbp+57h+var_90], r13
0x14000a213  mov     [rbp+57h+var_88], rax
0x14000a217  lea     rdx, byte_1400871B9
0x14000a21e  lea     rax, [rbp+57h+var_88]
0x14000a222  mov     [rsp+0C0h+var_98], rax
0x14000a227  lea     rax, [rbp+57h+var_90]
0x14000a22b  mov     [rsp+0C0h+var_A0], rax
0x14000a230  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000a235  mov     rcx, [rbp+57h+var_30]
0x14000a239  xor     rcx, rsp; StackCookie
0x14000a23c  call    __security_check_cookie
0x14000a241  mov     rbx, [rsp+0C0h+arg_18]
0x14000a249  add     rsp, 0A0h
0x14000a250  pop     r14
0x14000a252  pop     r13
0x14000a254  pop     rdi
0x14000a255  pop     rsi
0x14000a256  pop     rbp
0x14000a257  retn
```
