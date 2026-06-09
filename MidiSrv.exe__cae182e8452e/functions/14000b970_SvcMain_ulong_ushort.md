# SvcMain(ulong,ushort * *)

- ea: `0x14000b970`
- end: `0x14000ba1f`
- name: `?SvcMain@@YAXKPEAPEAG@Z`
- size: `175`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140001008`
- `0x14000984c`
- `0x14000a0cc`
- `0x14000b2b8`
- `0x14000b970`
- `0x14000c578`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000b9bd`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x14000b9bd`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x14000b9df`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x14000b9df`

## pseudocode

```c
void __fastcall SvcMain(__int64 a1, unsigned __int16 **a2)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v9; // [rsp+50h] [rbp+18h] BYREF
  const char *v10; // [rsp+58h] [rbp+20h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v10 = "SvcMain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v2,
      (unsigned int)&word_1400871E6,
      v3,
      v4,
      (__int64)&v10);
  }
  v9 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &v9) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, v5, v6, v7);
  g_SvcStatusHandle = RegisterServiceCtrlHandlerW(L"MidiSrv", SvcCtrlHandler);
  if ( g_SvcStatusHandle )
  {
    g_SvcStatus.dwServiceType = 16;
    g_SvcStatus.dwServiceSpecificExitCode = 0;
    ReportSvcStatus(2u, 0, 0xBB8u);
    SvcInit();
  }
}

```

## disassembly

```asm
0x14000b970  sub     rsp, 38h
0x14000b974  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b979  mov     rcx, [rax+8]
0x14000b97d  mov     eax, [rcx]
0x14000b97f  cmp     eax, 4
0x14000b982  jbe     short loc_14000B9A6
0x14000b984  lea     rax, aSvcmain; "SvcMain"
0x14000b98b  mov     [rsp+38h+arg_18], rax
0x14000b990  lea     rdx, word_1400871E6
0x14000b997  lea     rax, [rsp+38h+arg_18]
0x14000b99c  mov     [rsp+38h+var_18], rax
0x14000b9a1  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000b9a6  mov     r8d, 4
0x14000b9ac  mov     [rsp+38h+arg_10], 1
0x14000b9b4  lea     rdx, [rsp+38h+arg_10]
0x14000b9b9  lea     ecx, [r8+0Ch]
0x14000b9bd  call    cs:__imp_SetProcessMitigationPolicy
0x14000b9c3  test    eax, eax
0x14000b9c5  jnz     short loc_14000B9D1
0x14000b9c7  mov     rcx, [rsp+38h]; this
0x14000b9cc  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14000b9d1  lea     rdx, ?SvcCtrlHandler@@YAXK@Z; lpHandlerProc
0x14000b9d8  lea     rcx, ServiceName; "MidiSrv"
0x14000b9df  call    cs:__imp_RegisterServiceCtrlHandlerW
0x14000b9e5  mov     cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x14000b9ec  test    rax, rax
0x14000b9ef  jz      short loc_14000BA1A
0x14000b9f1  xor     edx, edx; unsigned int
0x14000b9f3  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 10h; _SERVICE_STATUS g_SvcStatus ...
0x14000b9fd  mov     r8d, 0BB8h; unsigned int
0x14000ba03  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, 0; _SERVICE_STATUS g_SvcStatus ...
0x14000ba0d  lea     ecx, [rdx+2]; unsigned int
0x14000ba10  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x14000ba15  call    ?SvcInit@@YAXXZ; SvcInit(void)
0x14000ba1a  add     rsp, 38h
0x14000ba1e  retn
```
