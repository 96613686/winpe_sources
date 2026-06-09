# SvcInit(void)

- ea: `0x14000b2b8`
- end: `0x14000b604`
- name: `?SvcInit@@YAXXZ`
- size: `844`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x14000b970`

## callees

- `0x140001008`
- `0x140001094`
- `0x14000179c`
- `0x1400054c0`
- `0x1400054e4`
- `0x140005868`
- `0x140006218`
- `0x140007d54`
- `0x14000984c`
- `0x140009984`
- `0x14000a0cc`
- `0x14000b2b8`
- `0x14000c598`
- `0x14000c5c8`
- `0x14000ca00`
- `0x140010068`
- `0x1400113b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b330`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b330`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b587`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b35d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b355`

## string_xrefs

- `0x14000b381`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000b4e4`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000b5a3`: `avcore\midi2\service\exe\midiservice.cpp`
- `0x14000b37a`: `Cannot init service. stop event creation failed.`
- `0x14000b3b9`: `Cannot init service. stop event creation failed.`
- `0x14000b4a6`: `g_MidiService is nullptr.`
- `0x14000b52b`: `MidiService initialization failed.`

## pseudocode

```c
void SvcInit(void)
{
  HRESULT v0; // eax
  _DWORD *v1; // rcx
  int v2; // r8d
  int v3; // r9d
  HANDLE EventW; // rax
  HANDLE v5; // rsi
  void *v6; // rdi
  DWORD LastError; // ebx
  DWORD v8; // eax
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  CMidiSrv *v12; // rax
  void *v13; // rdx
  unsigned int v14; // r8d
  const char *v15; // r9
  CMidiSrv *v16; // rbx
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  unsigned int v21; // ebx
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // ebx
  char *v25; // [rsp+20h] [rbp-79h]
  char v26[8]; // [rsp+30h] [rbp-69h] BYREF
  const char *v27; // [rsp+38h] [rbp-61h] BYREF
  int v28; // [rsp+40h] [rbp-59h] BYREF
  const char *v29; // [rsp+48h] [rbp-51h]
  __int64 v30; // [rsp+50h] [rbp-49h]
  const char *v31; // [rsp+80h] [rbp-19h]
  __int64 v32; // [rsp+88h] [rbp-11h]
  const wchar_t *v33; // [rsp+90h] [rbp-9h]
  __int64 v34; // [rsp+98h] [rbp-1h]
  char *v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v0 = CoInitializeEx_0(0, 0);
  if ( v0 < 0 )
  {
    v28 = 6532;
    v29 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\base.h";
    v30 = 0;
    winrt::throw_hresult((unsigned int)v0, &v28);
  }
  v1 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v1 > 4u )
  {
    *(_QWORD *)v26 = "SvcInit";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v1,
      (unsigned int)byte_140086EBB,
      v2,
      v3,
      (__int64)v26);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = g_SvcStopEvent;
  v6 = EventW;
  if ( (char *)g_SvcStopEvent - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  g_SvcStopEvent = v6;
  if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v12 = (CMidiSrv *)operator new(0x90u);
    v27 = (const char *)v12;
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 7) = 0;
    *((_QWORD *)v12 + 8) = 0;
    *((_QWORD *)v12 + 9) = 0;
    *((_QWORD *)v12 + 10) = 0;
    *((_QWORD *)v12 + 11) = 0;
    *((_QWORD *)v12 + 12) = 0;
    *((_QWORD *)v12 + 13) = 0;
    *((_QWORD *)v12 + 14) = 0;
    *((_QWORD *)v12 + 15) = 0;
    *((_WORD *)v12 + 64) = 0;
    *((_QWORD *)v12 + 17) = 0;
    v16 = g_MidiService;
    g_MidiService = v12;
    if ( v16 )
    {
      CMidiSrv::~CMidiSrv(v16);
      operator delete(v16);
      v12 = g_MidiService;
    }
    if ( v12 )
    {
      v20 = CMidiSrv::Initialize(v12);
      v21 = v20;
      if ( v20 >= 0 )
      {
        ReportSvcStatus(4u, 0, 0);
        WaitForSingleObject(g_SvcStopEvent, 0xFFFFFFFF);
        v23 = CMidiSrv::Shutdown(g_MidiService);
        v24 = v23;
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x218,
            (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
            (const char *)(unsigned int)v23,
            (int)v25);
        ReportSvcStatus(1u, v24, 0);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x202,
          (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
          (const char *)(unsigned int)v20,
          (int)v25);
        ReportSvcStatus(1u, v21, 0);
        v22 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v22 > 2u )
        {
          *(_DWORD *)v26 = v21;
          v35 = v26;
          v36 = 4;
          v33 = L"MidiService initialization failed.";
          v34 = 70;
          v31 = "SvcInit";
          v32 = 8;
          tlgWriteTransfer_EventWriteTransfer(v22, byte_140087155, 0, 0);
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_NullAlloc(retaddr, v13, v14, v15);
      ReportSvcStatus(1u, 8u, 0);
      v17 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v17 > 2u )
      {
        *(_QWORD *)v26 = "SvcInit";
        v27 = (const char *)L"g_MidiService is nullptr.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v17,
          (unsigned int)&dword_14008718C,
          v18,
          v19,
          (__int64)v26,
          (__int64)&v27);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Log_GetLastErrorMsg(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiservice.cpp",
      "Cannot init service. stop event creation failed.",
      v25);
    v8 = GetLastError();
    ReportSvcStatus(1u, v8, 0);
    v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v9 > 2u )
    {
      v27 = "SvcInit";
      *(_QWORD *)v26 = L"Cannot init service. stop event creation failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (unsigned int)byte_140087069,
        v10,
        v11,
        (__int64)&v27,
        (__int64)v26);
    }
  }
}

```

## disassembly

```asm
0x14000b2b8  push    rbp
0x14000b2ba  push    rbx
0x14000b2bb  push    rsi
0x14000b2bc  push    rdi
0x14000b2bd  push    r12
0x14000b2bf  push    r14
0x14000b2c1  push    r15
0x14000b2c3  lea     rbp, [rsp-27h]
0x14000b2c8  sub     rsp, 0C0h
0x14000b2cf  mov     rax, cs:__security_cookie
0x14000b2d6  xor     rax, rsp
0x14000b2d9  mov     [rbp+57h+var_40], rax
0x14000b2dd  xor     edx, edx; dwCoInit
0x14000b2df  xor     ecx, ecx; pvReserved
0x14000b2e1  xor     r14d, r14d
0x14000b2e4  call    CoInitializeEx_0
0x14000b2e9  test    eax, eax
0x14000b2eb  js      loc_14000B5E2
0x14000b2f1  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b2f6  lea     r15, aSvcinit; "SvcInit"
0x14000b2fd  mov     rcx, [rax+8]
0x14000b301  mov     eax, [rcx]
0x14000b303  cmp     eax, 4
0x14000b306  jbe     short loc_14000B321
0x14000b308  lea     rax, [rbp+57h+var_C0]
0x14000b30c  mov     qword ptr [rbp+57h+var_C0], r15
0x14000b310  lea     rdx, byte_140086EBB
0x14000b317  mov     [rsp+0F0h+var_D0], rax; int
0x14000b31c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14000b321  xor     r9d, r9d; lpName
0x14000b324  xor     r8d, r8d; bInitialState
0x14000b327  xor     ecx, ecx; lpEventAttributes
0x14000b329  lea     r12d, [r9+1]
0x14000b32d  mov     edx, r12d; bManualReset
0x14000b330  call    cs:__imp_CreateEventW
0x14000b336  mov     rsi, cs:?g_SvcStopEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_SvcStopEvent
0x14000b33d  mov     rdi, rax
0x14000b340  lea     rdx, [rsi-1]
0x14000b344  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000b348  ja      short loc_14000B363
0x14000b34a  call    cs:__imp_GetLastError
0x14000b350  mov     rcx, rsi; hObject
0x14000b353  mov     ebx, eax
0x14000b355  call    cs:__imp_CloseHandle
0x14000b35b  mov     ecx, ebx; dwErrCode
0x14000b35d  call    cs:__imp_SetLastError
0x14000b363  lea     rax, [rdi+1]
0x14000b367  mov     cs:?g_SvcStopEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, rdi; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_SvcStopEvent
0x14000b36e  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000b374  jnz     short loc_14000B3EB
0x14000b376  mov     rcx, [rbp+5Fh]; this
0x14000b37a  lea     r9, aCannotInitServ; "Cannot init service. stop event creatio"...
0x14000b381  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000b388  mov     edx, 1DFh; void *
0x14000b38d  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14000b392  call    cs:__imp_GetLastError
0x14000b398  xor     r8d, r8d; unsigned int
0x14000b39b  mov     ecx, r12d; unsigned int
0x14000b39e  mov     edx, eax; unsigned int
0x14000b3a0  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x14000b3a5  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b3aa  mov     rcx, [rax+8]
0x14000b3ae  mov     eax, [rcx]
0x14000b3b0  cmp     eax, 2
0x14000b3b3  jbe     loc_14000B5C4
0x14000b3b9  lea     rax, aCannotInitServ_0; "Cannot init service. stop event creatio"...
0x14000b3c0  mov     [rbp+57h+var_B8], r15
0x14000b3c4  mov     qword ptr [rbp+57h+var_C0], rax
0x14000b3c8  lea     rdx, byte_140087069
0x14000b3cf  lea     rax, [rbp+57h+var_C0]
0x14000b3d3  mov     [rsp+0F0h+var_C8], rax
0x14000b3d8  lea     rax, [rbp+57h+var_B8]
0x14000b3dc  mov     [rsp+0F0h+var_D0], rax
0x14000b3e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000b3e6  jmp     loc_14000B5C4
0x14000b3eb  mov     edi, 90h
0x14000b3f0  mov     ecx, edi; Size
0x14000b3f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b3f7  mov     [rbp+57h+var_B8], rax
0x14000b3fb  mov     [rax], r14
0x14000b3fe  mov     [rax+8], r14
0x14000b402  mov     [rax+10h], r14
0x14000b406  mov     [rax+18h], r14
0x14000b40a  mov     [rax+20h], r14
0x14000b40e  mov     [rax+28h], r14
0x14000b412  mov     [rax+30h], r14
0x14000b416  mov     [rax+38h], r14
0x14000b41a  mov     [rax+40h], r14
0x14000b41e  mov     [rax+48h], r14
0x14000b422  mov     [rax+50h], r14
0x14000b426  mov     [rax+58h], r14
0x14000b42a  mov     [rax+60h], r14
0x14000b42e  mov     [rax+68h], r14
0x14000b432  mov     [rax+70h], r14
0x14000b436  mov     [rax+78h], r14
0x14000b43a  mov     [rax+80h], r14w
0x14000b442  mov     [rax+88h], r14
0x14000b449  mov     rbx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14000b450  mov     cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A, rax; std::unique_ptr<CMidiSrv> g_MidiService
0x14000b457  test    rbx, rbx
0x14000b45a  jz      short loc_14000B475
0x14000b45c  mov     rcx, rbx; this
0x14000b45f  call    ??1CMidiSrv@@QEAA@XZ; CMidiSrv::~CMidiSrv(void)
0x14000b464  mov     edx, edi
0x14000b466  mov     rcx, rbx; Block
0x14000b469  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b46e  mov     rax, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14000b475  test    rax, rax
0x14000b478  jnz     short loc_14000B4CE
0x14000b47a  mov     rcx, [rbp+5Fh]; this
0x14000b47e  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x14000b483  xor     r8d, r8d; unsigned int
0x14000b486  mov     ecx, r12d; unsigned int
0x14000b489  lea     edx, [r8+8]; unsigned int
0x14000b48d  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x14000b492  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b497  mov     rcx, [rax+8]
0x14000b49b  mov     eax, [rcx]
0x14000b49d  cmp     eax, 2
0x14000b4a0  jbe     loc_14000B5C4
0x14000b4a6  lea     rax, aGMidiserviceIs; "g_MidiService is nullptr."
0x14000b4ad  mov     qword ptr [rbp+57h+var_C0], r15
0x14000b4b1  mov     [rbp+57h+var_B8], rax
0x14000b4b5  lea     rdx, dword_14008718C
0x14000b4bc  lea     rax, [rbp+57h+var_B8]
0x14000b4c0  mov     [rsp+0F0h+var_C8], rax
0x14000b4c5  lea     rax, [rbp+57h+var_C0]
0x14000b4c9  jmp     loc_14000B3DC
0x14000b4ce  mov     rcx, rax; this
0x14000b4d1  call    ?Initialize@CMidiSrv@@QEAAJXZ; CMidiSrv::Initialize(void)
0x14000b4d6  mov     ebx, eax
0x14000b4d8  test    eax, eax
0x14000b4da  jns     loc_14000B570
0x14000b4e0  mov     rcx, [rbp+5Fh]; this
0x14000b4e4  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000b4eb  mov     r9d, eax; char *
0x14000b4ee  mov     edx, 202h; void *
0x14000b4f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000b4f8  xor     r8d, r8d; unsigned int
0x14000b4fb  mov     edx, ebx; unsigned int
0x14000b4fd  mov     ecx, r12d; unsigned int
0x14000b500  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x14000b505  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14000b50a  mov     rcx, [rax+8]
0x14000b50e  mov     eax, [rcx]
0x14000b510  cmp     eax, 2
0x14000b513  jbe     loc_14000B5C4
0x14000b519  lea     rax, [rbp+57h+var_C0]
0x14000b51d  mov     dword ptr [rbp+57h+var_C0], ebx
0x14000b520  mov     [rbp+57h+var_50], rax
0x14000b524  lea     rdx, byte_140087155
0x14000b52b  lea     rax, aMidiserviceIni; "MidiService initialization failed."
0x14000b532  mov     [rbp+57h+var_48], 4
0x14000b53a  mov     [rbp+57h+var_60], rax
0x14000b53e  xor     r9d, r9d
0x14000b541  lea     rax, [rbp+57h+var_90]
0x14000b545  mov     [rbp+57h+var_58], 46h ; 'F'
0x14000b54d  mov     [rsp+0F0h+var_C8], rax
0x14000b552  xor     r8d, r8d
0x14000b555  mov     dword ptr [rsp+0F0h+var_D0], 5
0x14000b55d  mov     [rbp+57h+var_70], r15
0x14000b561  mov     [rbp+57h+var_68], 8
0x14000b569  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b56e  jmp     short loc_14000B5C4
0x14000b570  xor     edx, edx; unsigned int
0x14000b572  xor     r8d, r8d; unsigned int
0x14000b575  lea     ecx, [rdx+4]; unsigned int
0x14000b578  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x14000b57d  mov     rcx, cs:?g_SvcStopEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hHandle
0x14000b584  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000b587  call    cs:__imp_WaitForSingleObject
0x14000b58d  mov     rcx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; this
0x14000b594  call    ?Shutdown@CMidiSrv@@QEAAJXZ; CMidiSrv::Shutdown(void)
0x14000b599  mov     ebx, eax
0x14000b59b  test    eax, eax
0x14000b59d  jns     short loc_14000B5B7
0x14000b59f  mov     rcx, [rbp+5Fh]; this
0x14000b5a3  lea     r8, aAvcoreMidi2Ser_0; "avcore\\midi2\\service\\exe\\midiservic"...
0x14000b5aa  mov     r9d, eax; char *
0x14000b5ad  mov     edx, 218h; void *
0x14000b5b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000b5b7  xor     r8d, r8d; unsigned int
0x14000b5ba  mov     edx, ebx; unsigned int
0x14000b5bc  mov     ecx, r12d; unsigned int
0x14000b5bf  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x14000b5c4  mov     rcx, [rbp+57h+var_40]
0x14000b5c8  xor     rcx, rsp; StackCookie
0x14000b5cb  call    __security_check_cookie
0x14000b5d0  add     rsp, 0C0h
0x14000b5d7  pop     r15
0x14000b5d9  pop     r14
0x14000b5db  pop     r12
0x14000b5dd  pop     rdi
0x14000b5de  pop     rsi
0x14000b5df  pop     rbx
0x14000b5e0  pop     rbp
0x14000b5e1  retn
0x14000b5e2  lea     rcx, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14000b5e9  mov     [rbp+57h+var_B0], 1984h
0x14000b5f0  mov     [rbp+57h+var_A8], rcx
0x14000b5f4  lea     rdx, [rbp+57h+var_B0]
0x14000b5f8  mov     ecx, eax
0x14000b5fa  mov     [rbp+57h+var_A0], r14
0x14000b5fe  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
