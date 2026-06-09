# Windows::Compat::Inventory::Service::InventoryScheduler::DoWork(void)

- ea: `0x180022e5c`
- end: `0x18002372b`
- name: `?DoWork@InventoryScheduler@Service@Inventory@Compat@Windows@@AEAAXXZ`
- size: `2255`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::InventoryScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001f6e0`

## callees

- `0x1800019bc`
- `0x180002bf0`
- `0x180003100`
- `0x180003af4`
- `0x180006e54`
- `0x18000fc88`
- `0x1800108d4`
- `0x1800152d0`
- `0x180022e5c`
- `0x180028308`
- `0x18002ce04`
- `0x18002d068`
- `0x1800be9e8`
- `0x1800bedd8`
- `0x1800bf294`
- `0x1800bfe9c`
- `0x1800c0418`
- `0x1800c07ec`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002362a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002362a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022e93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023016`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023066`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023097`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022e93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023016`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023066`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002359c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002359c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180023008`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180023008`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002328d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002328d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800230fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800233ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800230fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800233ec`

## string_xrefs

- `0x180023719`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800236bf`: `onecore\base\appcompat\inventory\service\scheduler\inventoryscheduler.cpp`
- `0x180023702`: `onecore\base\appcompat\inventory\service\scheduler\inventoryscheduler.cpp`
- `0x180022fa5`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x18002302d`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x1800230d7`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x18002339b`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x1800233d0`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x180023546`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x1800235b3`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x1800235d3`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x180023649`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x18002369e`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x1800236e1`: `Windows::Compat::Inventory::Service::InventoryScheduler::DoWork`
- `0x180023020`: `Service is shutting down.`
- `0x1800235c6`: `Service is shutting down.`
- `0x1800233c3`: `TelemetryProvider %ls paused. Waiting for window to reopen`
- `0x18002363c`: `InventoryScheduler thread is done.`
- `0x180023539`: `TelemetryProvider completed:%ls Runtime:%I64u TimeOverdue:%u`
- `0x1800232a3`: `RegSetValueExW failed: %ls [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall Windows::Compat::Inventory::Service::InventoryScheduler::DoWork(
        Windows::Compat::Inventory::Service::InventoryScheduler *this)
{
  int NextTelemetryProvider; // eax
  unsigned int v3; // ebx
  TelemetryProvider *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  TelemetryProvider *v7; // rdi
  unsigned int OverdueTime; // esi
  unsigned int v9; // eax
  TelemetryProvider *v10; // rax
  TelemetryProvider *v11; // rsi
  TelemetryProvider *v12; // rsi
  DWORD v13; // esi
  unsigned int v14; // esi
  const wchar_t **v15; // rsi
  unsigned int v16; // esi
  __int64 v17; // r8
  __int64 v18; // r10
  signed __int64 v19; // r8
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  void *v23; // r12
  void *v24; // r15
  __int64 v25; // r8
  int v26; // r15d
  LSTATUS v27; // eax
  unsigned int v28; // eax
  int v29; // eax
  ULONGLONG v30; // r12
  void **v31; // rdx
  UtcThrottle *v32; // rcx
  int v33; // r15d
  int v34; // r8d
  int v35; // r9d
  const char *v36; // r9
  unsigned int v37; // eax
  unsigned int v38; // eax
  DWORD lpData; // [rsp+20h] [rbp-1A8h]
  int lpDataa; // [rsp+20h] [rbp-1A8h]
  int lpDatab; // [rsp+20h] [rbp-1A8h]
  BYTE Data[8]; // [rsp+70h] [rbp-158h] BYREF
  unsigned int v43; // [rsp+78h] [rbp-150h]
  int v44; // [rsp+7Ch] [rbp-14Ch] BYREF
  int v45; // [rsp+80h] [rbp-148h] BYREF
  int v46; // [rsp+84h] [rbp-144h] BYREF
  unsigned int v47; // [rsp+88h] [rbp-140h] BYREF
  Windows::Compat::Inventory::Service::InventoryScheduler *v48; // [rsp+90h] [rbp-138h]
  char *TickCount64; // [rsp+98h] [rbp-130h] BYREF
  const wchar_t *v50; // [rsp+A0h] [rbp-128h] BYREF
  TelemetryProvider *v51; // [rsp+A8h] [rbp-120h]
  TelemetryProvider *v52; // [rsp+B0h] [rbp-118h]
  ULONGLONG v53; // [rsp+B8h] [rbp-110h] BYREF
  __int64 v54[3]; // [rsp+C0h] [rbp-108h] BYREF
  HANDLE Handles[3]; // [rsp+D8h] [rbp-F0h] BYREF
  char v56[144]; // [rsp+F0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v48 = this;
  if ( WaitForSingleObject(*((HANDLE *)this + 5), 0x3E8u) )
    return;
  while ( 1 )
  {
    *(_QWORD *)Data = 0;
    NextTelemetryProvider = TelemetryController::GetNextTelemetryProvider(
                              (struct TelemetryProvider **)Data,
                              1,
                              *((HKEY *)this + 1),
                              *((HKEY *)this + 2));
    v3 = NextTelemetryProvider;
    if ( NextTelemetryProvider < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
        124,
        "failed [%#x]",
        NextTelemetryProvider);
      v37 = wil::verify_hresult<long>(v3);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\scheduler\\inventoryscheduler.cpp",
        (const char *)v37,
        lpDataa);
    }
    v4 = *(TelemetryProvider **)Data;
    v51 = *(TelemetryProvider **)Data;
    v5 = TelemetryController::GetNextTelemetryProvider(
           (struct TelemetryProvider **)Data,
           0,
           *((HKEY *)this + 1),
           *((HKEY *)this + 2));
    v6 = v5;
    if ( v5 < 0 )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork", 128, "failed [%#x]", v5);
      v38 = wil::verify_hresult<long>(v6);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\scheduler\\inventoryscheduler.cpp",
        (const char *)v38,
        lpDatab);
    }
    v7 = *(TelemetryProvider **)Data;
    v52 = *(TelemetryProvider **)Data;
    if ( v4 )
    {
      if ( *((_BYTE *)v4 + 50) )
        goto LABEL_13;
      OverdueTime = TelemetryProvider::GetOverdueTime(v4);
      if ( v7 )
        v9 = TelemetryProvider::GetOverdueTime(v7);
      else
        v9 = 0;
      if ( OverdueTime < v9 )
      {
        v12 = v4;
        v4 = 0;
        v51 = 0;
        TelemetryProvider::~TelemetryProvider(v12);
        operator delete(v12, (const struct std::nothrow_t *)0x40);
LABEL_13:
        if ( v4 )
          goto LABEL_16;
        goto LABEL_14;
      }
      v10 = v4;
      v4 = 0;
      v51 = 0;
      v11 = v7;
      v7 = v10;
      v52 = v10;
      if ( v11 )
      {
        TelemetryProvider::~TelemetryProvider(v11);
        operator delete(v11, (const struct std::nothrow_t *)0x40);
      }
    }
LABEL_14:
    if ( !v7 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
        153,
        "No more TelemetryProviders due.");
      goto LABEL_80;
    }
LABEL_16:
    (*(void (__fastcall **)(Windows::Compat::Inventory::Service::InventoryScheduler *, TelemetryProvider *, TelemetryProvider *))(*(_QWORD *)this + 40LL))(
      this,
      v4,
      v7);
    Handles[0] = *((HANDLE *)this + 6);
    Handles[1] = *((HANDLE *)this + 7);
    Handles[2] = *((HANDLE *)this + 4);
    v13 = WaitForMultipleObjects(3u, Handles, 0, 0x36EE80u);
    if ( !WaitForSingleObject(*((HANDLE *)this + 4), 0) )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
        171,
        "Service is shutting down.");
      if ( v7 )
      {
        TelemetryProvider::~TelemetryProvider(v7);
        operator delete(v7, (const struct std::nothrow_t *)0x40);
      }
LABEL_78:
      if ( v4 )
      {
        TelemetryProvider::~TelemetryProvider(v4);
        operator delete(v4, (const struct std::nothrow_t *)0x40);
      }
      goto LABEL_80;
    }
    if ( !v13 )
    {
      if ( WaitForSingleObject(*((HANDLE *)this + 7), 0x64u) )
        goto LABEL_23;
      v14 = TelemetryProvider::GetOverdueTime(v7);
      if ( v14 <= TelemetryProvider::GetOverdueTime(v4) )
        goto LABEL_23;
LABEL_27:
      v15 = (const wchar_t **)v7;
      goto LABEL_30;
    }
    if ( v13 == 1 )
    {
      if ( !WaitForSingleObject(*((HANDLE *)this + 6), 0x64u) )
      {
        v16 = TelemetryProvider::GetOverdueTime(v4);
        if ( v16 >= TelemetryProvider::GetOverdueTime(v7) )
        {
LABEL_23:
          v15 = (const wchar_t **)v4;
          goto LABEL_30;
        }
      }
      goto LABEL_27;
    }
    if ( v13 != 258 )
      break;
    v15 = 0;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
      213,
      "Wait timed out. Adjusting priority and waiting more");
LABEL_30:
    if ( v15 )
    {
      v43 = TelemetryProvider::GetOverdueTime((TelemetryProvider *)v15);
      TickCount64 = (char *)GetTickCount64();
      LOBYTE(v17) = *((_BYTE *)v15 + 50);
      (*(void (__fastcall **)(Windows::Compat::Inventory::Service::InventoryScheduler *, const wchar_t *, __int64))(*(_QWORD *)this + 24LL))(
        this,
        v15[2],
        v17);
      v18 = *((_QWORD *)this + 3);
      while ( 1 )
      {
        v19 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v18 + 136), 0);
        if ( (unsigned int)v19 == 0x7FFFFFFF || v19 < 0 )
          break;
        v20 = HIDWORD(v19);
        LODWORD(v20) = HIDWORD(v19) & 0x7FFFFFFF;
        if ( (unsigned int)v19 == 9
          || (unsigned int)v19 == 99
          || (unsigned int)v19 == 999
          || (unsigned int)v19 == 9999
          || (unsigned int)v19 == 99999
          || (unsigned int)v19 == 999999
          || (unsigned int)v19 == 9999999
          || (unsigned int)v19 == 99999999
          || (unsigned int)v19 == 999999999 )
        {
          ++v20;
        }
        v21 = v20 << 32;
        if ( v20 < *(unsigned __int8 *)(v18 + 130) )
          v22 = (((unsigned int)v19 + 1LL) | v21) & 0x7FFFFFFFFFFFFFFFLL;
        else
          v22 = (unsigned int)v19 | v21 | 0x8000000000000000uLL;
        if ( v19 == _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 136), v22, v19) )
          goto LABEL_50;
      }
      v22 = v19;
LABEL_50:
      TraceLoggingCorrelationVector::ToStringImpl((TraceLoggingCorrelationVector *)v18, v22, v56);
      v23 = (void *)(*(__int64 (__fastcall **)(Windows::Compat::Inventory::Service::InventoryScheduler *, const wchar_t **))(*(_QWORD *)this + 56LL))(
                      this,
                      v15);
      v24 = (void *)*((_QWORD *)this + 4);
      if ( TelemetryProvider::IsRunNeeded((TelemetryProvider *)v15) )
      {
        *(_DWORD *)Data = 1;
        v27 = RegSetValueExW((HKEY)v15[5], L"Pending", 0, 4u, Data, 4u);
        if ( v27 )
          AslLogCallPrintf(1, "TelemetryProvider::MarkPending", 787, "RegSetValueExW failed: %ls [%#x]", *v15, v27);
        *((_BYTE *)v15 + 52) = 1;
        v28 = TelemetryProvider::GetOverdueTime((TelemetryProvider *)v15);
        AslLogCallPrintf(
          3,
          "TelemetryProvider::SendTelemetry",
          403,
          "Running \"%ls!%ls\" %u sec overdue",
          v15[1],
          *v15,
          v28);
        v29 = TelemetryProvider::RunCommand((TelemetryProvider *)v15, v56, v24, v23);
        v26 = v29;
        if ( v29 < 0 )
          AslLogCallPrintf(
            1,
            "TelemetryProvider::SendTelemetry",
            407,
            "TelemetryProvider failed: %ls!%ls [%#x]",
            v15[1],
            *v15,
            v29);
        if ( v26 != 459998 )
          TelemetryProvider::WriteStatus((TelemetryProvider *)v15, v26);
      }
      else
      {
        AslLogCallPrintf(1, "TelemetryProvider::SendTelemetry", 396, "%ls!%ls", v15[1], *v15);
        v26 = 1;
      }
      LOBYTE(v25) = *((_BYTE *)v15 + 50);
      (*(void (__fastcall **)(Windows::Compat::Inventory::Service::InventoryScheduler *, const wchar_t *, __int64))(*(_QWORD *)this + 32LL))(
        this,
        v15[2],
        v25);
      if ( v26 >= 0 )
      {
        if ( v26 == 459998 )
        {
          AslLogCallPrintf(
            3,
            "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
            253,
            "TelemetryProvider %ls paused. Waiting for window to reopen",
            v15[2]);
        }
        else if ( !v26 )
        {
          v30 = GetTickCount64() - (_QWORD)TickCount64;
          UtcThrottle::Throttle(v32, v31);
          v33 = DWORD2(xmmword_1800FF000);
          if ( **((_DWORD **)&xmmword_1800FF000 + 1) > 5u
            && (*(_QWORD *)(*((_QWORD *)&xmmword_1800FF000 + 1) + 16LL) & 0x400000000000LL) != 0
            && (*(_QWORD *)(*((_QWORD *)&xmmword_1800FF000 + 1) + 24LL) & 0x400000000000LL) == *(_QWORD *)(*((_QWORD *)&xmmword_1800FF000 + 1) + 24LL) )
          {
            TickCount64 = &Str;
            *(_QWORD *)Data = InventoryCoreGetVersion();
            v44 = *((unsigned __int8 *)v15 + 50);
            v45 = (unsigned __int8)IsCrmRegisterPresent();
            v46 = 0;
            v50 = v15[2];
            v53 = v30;
            v47 = v43;
            v54[0] = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
              v33,
              (unsigned int)byte_1800F055B,
              v34,
              v35,
              (__int64)v54,
              (__int64)&v47,
              (__int64)&v53,
              (__int64)&v50,
              (__int64)&v46,
              (__int64)&v45,
              (__int64)&v44,
              (__int64)Data,
              (__int64)&TickCount64);
          }
          AslLogCallPrintf(
            3,
            "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
            270,
            "TelemetryProvider completed:%ls Runtime:%I64u TimeOverdue:%u",
            v15[2],
            v30,
            v43);
        }
      }
      else
      {
        AslLogCallPrintf(
          3,
          "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
          248,
          "TelemetryProvider %ls failed [%#x]",
          v15[2],
          v26);
      }
    }
    if ( v7 )
    {
      TelemetryProvider::~TelemetryProvider(v7);
      operator delete(v7, (const struct std::nothrow_t *)0x40);
    }
    if ( v4 )
    {
      TelemetryProvider::~TelemetryProvider(v4);
      operator delete(v4, (const struct std::nothrow_t *)0x40);
    }
  }
  if ( v13 == -1 )
  {
    lpData = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
      220,
      "WaitForMultipleObjects failed [%#x]",
      lpData);
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
      224,
      "Service is shutting down.");
  }
  if ( v7 )
  {
    TelemetryProvider::~TelemetryProvider(v7);
    operator delete(v7, (const struct std::nothrow_t *)0x40);
  }
  if ( v4 )
    goto LABEL_78;
LABEL_80:
  if ( !SetEvent(*((HANDLE *)this + 4)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v36);
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::Service::InventoryScheduler::DoWork",
    290,
    "InventoryScheduler thread is done.");
  (*(void (__fastcall **)(Windows::Compat::Inventory::Service::InventoryScheduler *))(*(_QWORD *)this + 48LL))(this);
}

```

## disassembly

```asm
0x180022e5c  push    rbx
0x180022e5e  push    rsi
0x180022e5f  push    rdi
0x180022e60  push    r12
0x180022e62  push    r14
0x180022e64  push    r15
0x180022e66  sub     rsp, 198h
0x180022e6d  mov     rax, cs:__security_cookie
0x180022e74  xor     rax, rsp
0x180022e77  mov     [rsp+1C8h+var_48], rax
0x180022e7f  mov     r14, rcx
0x180022e82  mov     [rsp+1C8h+var_138], rcx
0x180022e8a  mov     edx, 3E8h; dwMilliseconds
0x180022e8f  mov     rcx, [rcx+28h]; hHandle
0x180022e93  call    cs:__imp_WaitForSingleObject
0x180022e99  test    eax, eax
0x180022e9b  jnz     loc_18002366A
0x180022ea1  mov     r15d, 40h ; '@'
0x180022ea7  mov     qword ptr [rsp+1C8h+Data], 0
0x180022eb0  mov     r9, [r14+10h]; HKEY
0x180022eb4  mov     r8, [r14+8]; HKEY
0x180022eb8  mov     dl, 1; bool
0x180022eba  lea     rcx, [rsp+1C8h+Data]; struct TelemetryProvider **
0x180022ebf  call    ?GetNextTelemetryProvider@TelemetryController@@SAJAEAPEAVTelemetryProvider@@_NPEAUHKEY__@@2@Z; TelemetryController::GetNextTelemetryProvider(TelemetryProvider * &,bool,HKEY__ *,HKEY__ *)
0x180022ec4  mov     ebx, eax
0x180022ec6  test    eax, eax
0x180022ec8  js      loc_18002368B
0x180022ece  mov     rbx, qword ptr [rsp+1C8h+Data]
0x180022ed3  mov     [rsp+1C8h+var_120], rbx
0x180022edb  mov     r9, [r14+10h]; HKEY
0x180022edf  mov     r8, [r14+8]; HKEY
0x180022ee3  xor     edx, edx; bool
0x180022ee5  lea     rcx, [rsp+1C8h+Data]; struct TelemetryProvider **
0x180022eea  call    ?GetNextTelemetryProvider@TelemetryController@@SAJAEAPEAVTelemetryProvider@@_NPEAUHKEY__@@2@Z; TelemetryController::GetNextTelemetryProvider(TelemetryProvider * &,bool,HKEY__ *,HKEY__ *)
0x180022eef  mov     edi, eax
0x180022ef1  test    eax, eax
0x180022ef3  js      loc_1800236CE
0x180022ef9  mov     rdi, qword ptr [rsp+1C8h+Data]
0x180022efe  mov     [rsp+1C8h+var_118], rdi
0x180022f06  test    rbx, rbx
0x180022f09  jz      loc_180022F93
0x180022f0f  cmp     byte ptr [rbx+32h], 0
0x180022f13  jnz     short loc_180022F8E
0x180022f15  mov     rcx, rbx; this
0x180022f18  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x180022f1d  mov     esi, eax
0x180022f1f  test    rdi, rdi
0x180022f22  jz      short loc_180022F2E
0x180022f24  mov     rcx, rdi; this
0x180022f27  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x180022f2c  jmp     short loc_180022F30
0x180022f2e  xor     eax, eax
0x180022f30  cmp     esi, eax
0x180022f32  jb      short loc_180022F69
0x180022f34  mov     rax, rbx
0x180022f37  xor     ebx, ebx
0x180022f39  mov     [rsp+1C8h+var_120], rbx
0x180022f41  mov     rsi, rdi
0x180022f44  mov     rdi, rax
0x180022f47  mov     [rsp+1C8h+var_118], rax
0x180022f4f  test    rsi, rsi
0x180022f52  jz      short loc_180022F93
0x180022f54  mov     rcx, rsi; this
0x180022f57  call    ??1TelemetryProvider@@QEAA@XZ; TelemetryProvider::~TelemetryProvider(void)
0x180022f5c  mov     rdx, r15; struct std::nothrow_t *
0x180022f5f  mov     rcx, rsi; void *
0x180022f62  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180022f67  jmp     short loc_180022F93
0x180022f69  mov     rsi, rbx
0x180022f6c  xor     ebx, ebx
0x180022f6e  mov     [rsp+1C8h+var_120], rbx
0x180022f76  test    rsi, rsi
0x180022f79  jz      short loc_180022F93
0x180022f7b  mov     rcx, rsi; this
0x180022f7e  call    ??1TelemetryProvider@@QEAA@XZ; TelemetryProvider::~TelemetryProvider(void)
0x180022f83  mov     rdx, r15; struct std::nothrow_t *
0x180022f86  mov     rcx, rsi; void *
0x180022f89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180022f8e  test    rbx, rbx
0x180022f91  jnz     short loc_180022FBA
0x180022f93  test    rdi, rdi
0x180022f96  jnz     short loc_180022FBA
0x180022f98  lea     r9, aNoMoreTelemetr; "No more TelemetryProviders due."
0x180022f9f  mov     r8d, 99h
0x180022fa5  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::Service::In"...
0x180022fac  lea     ecx, [rdi+3]
0x180022faf  call    AslLogCallPrintf
0x180022fb4  nop
0x180022fb5  jmp     loc_18002361C
0x180022fba  mov     rax, [r14]
0x180022fbd  mov     r8, rdi
0x180022fc0  mov     rdx, rbx
0x180022fc3  mov     rcx, r14
0x180022fc6  mov     rax, [rax+28h]
0x180022fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fcf  mov     rax, [r14+30h]
0x180022fd3  mov     [rsp+1C8h+Handles], rax
0x180022fdb  mov     rax, [r14+38h]
0x180022fdf  mov     [rsp+1C8h+var_E8], rax
0x180022fe7  mov     rax, [r14+20h]
0x180022feb  mov     [rsp+1C8h+var_E0], rax
0x180022ff3  mov     r9d, 36EE80h; dwMilliseconds
0x180022ff9  xor     r8d, r8d; bWaitAll
0x180022ffc  lea     rdx, [rsp+1C8h+Handles]; lpHandles
0x180023004  lea     ecx, [r8+3]; nCount
0x180023008  call    cs:__imp_WaitForMultipleObjects
0x18002300e  mov     esi, eax
0x180023010  xor     edx, edx; dwMilliseconds
0x180023012  mov     rcx, [r14+20h]; hHandle
0x180023016  call    cs:__imp_WaitForSingleObject
0x18002301c  test    eax, eax
0x18002301e  jnz     short loc_18002305B
0x180023020  lea     r9, aServiceIsShutt; "Service is shutting down."
0x180023027  mov     r8d, 0ABh
0x18002302d  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::Service::In"...
0x180023034  lea     ecx, [rax+3]
0x180023037  call    AslLogCallPrintf
0x18002303c  nop
0x18002303d  test    rdi, rdi
0x180023040  jz      short loc_180023056
0x180023042  mov     rcx, rdi; this
0x180023045  call    ??1TelemetryProvider@@QEAA@XZ; TelemetryProvider::~TelemetryProvider(void)
0x18002304a  mov     rdx, r15; struct std::nothrow_t *
0x18002304d  mov     rcx, rdi; void *
0x180023050  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180023055  nop
0x180023056  jmp     loc_180023603
0x18002305b  test    esi, esi
0x18002305d  jnz     short loc_18002308B
0x18002305f  lea     edx, [rsi+64h]; dwMilliseconds
0x180023062  mov     rcx, [r14+38h]; hHandle
0x180023066  call    cs:__imp_WaitForSingleObject
0x18002306c  test    eax, eax
0x18002306e  jnz     short loc_180023086
0x180023070  mov     rcx, rdi; this
0x180023073  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x180023078  mov     esi, eax
0x18002307a  mov     rcx, rbx; this
0x18002307d  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x180023082  cmp     esi, eax
0x180023084  ja      short loc_1800230B7
0x180023086  mov     rsi, rbx
0x180023089  jmp     short loc_1800230E6
0x18002308b  cmp     esi, 1
0x18002308e  jnz     short loc_1800230BC
0x180023090  lea     edx, [rsi+63h]; dwMilliseconds
0x180023093  mov     rcx, [r14+30h]; hHandle
0x180023097  call    cs:__imp_WaitForSingleObject
0x18002309d  test    eax, eax
0x18002309f  jnz     short loc_1800230B7
0x1800230a1  mov     rcx, rbx; this
0x1800230a4  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x1800230a9  mov     esi, eax
0x1800230ab  mov     rcx, rdi; this
0x1800230ae  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x1800230b3  cmp     esi, eax
0x1800230b5  jnb     short loc_180023086
0x1800230b7  mov     rsi, rdi
0x1800230ba  jmp     short loc_1800230E6
0x1800230bc  cmp     esi, 102h
0x1800230c2  jnz     loc_180023597
0x1800230c8  xor     esi, esi
0x1800230ca  lea     r9, aWaitTimedOutAd; "Wait timed out. Adjusting priority and "...
0x1800230d1  mov     r8d, 0D5h
0x1800230d7  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::Service::In"...
0x1800230de  lea     ecx, [rsi+3]
0x1800230e1  call    AslLogCallPrintf
0x1800230e6  test    rsi, rsi
0x1800230e9  jz      loc_18002355D
0x1800230ef  mov     rcx, rsi; this
0x1800230f2  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x1800230f7  mov     [rsp+1C8h+var_150], eax
0x1800230fb  call    cs:__imp_GetTickCount64
0x180023101  mov     [rsp+1C8h+var_130], rax
0x180023109  mov     rcx, [r14]
0x18002310c  mov     rax, [rcx+18h]
0x180023110  mov     r8b, [rsi+32h]
0x180023114  mov     rdx, [rsi+10h]
0x180023118  mov     rcx, r14
0x18002311b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023120  mov     r10, [r14+18h]
0x180023124  xor     r8d, r8d
0x180023127  lock xadd [r10+88h], r8
0x180023130  mov     r11d, r8d
0x180023133  test    r8, r8
0x180023136  sets    al
0x180023139  cmp     r11, 7FFFFFFFh
0x180023140  jz      loc_1800231EF
0x180023146  test    al, al
0x180023148  jnz     loc_1800231EF
0x18002314e  mov     r9, r8
0x180023151  shr     r9, 20h
0x180023155  btr     r9d, 1Fh
0x18002315a  lea     rax, [r11+1]
0x18002315e  cmp     rax, 0Ah
0x180023162  jz      short loc_1800231A2
0x180023164  cmp     rax, 64h ; 'd'
0x180023168  jz      short loc_1800231A2
0x18002316a  cmp     rax, 3E8h
0x180023170  jz      short loc_1800231A2
0x180023172  cmp     rax, 2710h
0x180023178  jz      short loc_1800231A2
0x18002317a  cmp     rax, 186A0h
0x180023180  jz      short loc_1800231A2
0x180023182  cmp     rax, 0F4240h
0x180023188  jz      short loc_1800231A2
0x18002318a  cmp     rax, 989680h
0x180023190  jz      short loc_1800231A2
0x180023192  cmp     rax, 5F5E100h
0x180023198  jz      short loc_1800231A2
0x18002319a  cmp     rax, 3B9ACA00h
0x1800231a0  jnz     short loc_1800231A5
0x1800231a2  inc     r9
0x1800231a5  mov     rdx, r9
0x1800231a8  shl     rdx, 20h
0x1800231ac  movzx   ecx, byte ptr [r10+82h]
0x1800231b4  cmp     r9, rcx
0x1800231b7  jb      short loc_1800231CB
0x1800231b9  or      rdx, r11
0x1800231bc  mov     rax, 8000000000000000h
0x1800231c6  or      rdx, rax
0x1800231c9  jmp     short loc_1800231DB
0x1800231cb  or      rdx, rax
0x1800231ce  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800231d8  and     rdx, rax
0x1800231db  mov     rax, r8
0x1800231de  lock cmpxchg [r10+88h], rdx
0x1800231e7  jnz     loc_180023124
0x1800231ed  jmp     short loc_1800231F2
0x1800231ef  mov     rdx, r8; unsigned __int64
0x1800231f2  lea     r8, [rsp+1C8h+var_D8]; char *
0x1800231fa  mov     rcx, r10; this
0x1800231fd  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180023202  mov     rax, [r14]
0x180023205  mov     rdx, rsi
0x180023208  mov     rcx, r14
0x18002320b  mov     rax, [rax+38h]
0x18002320f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023214  mov     r12, rax
0x180023217  mov     r15, [r14+20h]
0x18002321b  mov     rcx, rsi; this
0x18002321e  call    ?IsRunNeeded@TelemetryProvider@@QEBA_NXZ; TelemetryProvider::IsRunNeeded(void)
0x180023223  test    al, al
0x180023225  jnz     short loc_180023261
0x180023227  mov     rax, [rsi]
0x18002322a  mov     qword ptr [rsp+1C8h+cbData], rax
0x18002322f  mov     rax, [rsi+8]
0x180023233  mov     [rsp+1C8h+lpData], rax
0x180023238  lea     r9, aLsLs; "%ls!%ls"
0x18002323f  mov     r8d, 18Ch
0x180023245  lea     rdx, aTelemetryprovi_1; "TelemetryProvider::SendTelemetry"
0x18002324c  mov     ecx, 1
0x180023251  call    AslLogCallPrintf
0x180023256  mov     r15d, 1
0x18002325c  jmp     loc_180023364
0x180023261  mov     dword ptr [rsp+1C8h+Data], 1
0x180023269  mov     ecx, 4
0x18002326e  mov     [rsp+1C8h+cbData], ecx; cbData
0x180023272  lea     rax, [rsp+1C8h+Data]
0x180023277  mov     [rsp+1C8h+lpData], rax; lpData
0x18002327c  mov     r9d, ecx; dwType
0x18002327f  xor     r8d, r8d; Reserved
0x180023282  lea     rdx, ValueName; "Pending"
0x180023289  mov     rcx, [rsi+28h]; hKey
0x18002328d  call    cs:__imp_RegSetValueExW
0x180023293  test    eax, eax
0x180023295  jz      short loc_1800232C1
0x180023297  mov     [rsp+1C8h+cbData], eax
0x18002329b  mov     rax, [rsi]
0x18002329e  mov     [rsp+1C8h+lpData], rax
0x1800232a3  lea     r9, aRegsetvalueexw; "RegSetValueExW failed: %ls [%#x]"
0x1800232aa  mov     r8d, 313h
0x1800232b0  lea     rdx, aTelemetryprovi_3; "TelemetryProvider::MarkPending"
0x1800232b7  mov     ecx, 1
0x1800232bc  call    AslLogCallPrintf
0x1800232c1  mov     byte ptr [rsi+34h], 1
0x1800232c5  mov     rcx, rsi; this
0x1800232c8  call    ?GetOverdueTime@TelemetryProvider@@QEBAKXZ; TelemetryProvider::GetOverdueTime(void)
0x1800232cd  mov     dword ptr [rsp+1C8h+var_198], eax
0x1800232d1  mov     rax, [rsi]
0x1800232d4  mov     qword ptr [rsp+1C8h+cbData], rax
0x1800232d9  mov     rax, [rsi+8]
0x1800232dd  mov     [rsp+1C8h+lpData], rax
0x1800232e2  lea     r9, aRunningLsLsUSe; "Running \"%ls!%ls\" %u sec overdue"
0x1800232e9  mov     r8d, 193h
0x1800232ef  lea     rdx, aTelemetryprovi_1; "TelemetryProvider::SendTelemetry"
0x1800232f6  mov     ecx, 3
0x1800232fb  call    AslLogCallPrintf
0x180023300  mov     r9, r12; void *
0x180023303  mov     r8, r15; void *
0x180023306  lea     rdx, [rsp+1C8h+var_D8]; char *
0x18002330e  mov     rcx, rsi; this
0x180023311  call    ?RunCommand@TelemetryProvider@@AEAAJPEBDPEAX1@Z; TelemetryProvider::RunCommand(char const *,void *,void *)
0x180023316  mov     r15d, eax
0x180023319  test    eax, eax
0x18002331b  jns     short loc_180023350
0x18002331d  mov     dword ptr [rsp+1C8h+var_198], eax
0x180023321  mov     rcx, [rsi]
0x180023324  mov     qword ptr [rsp+1C8h+cbData], rcx
0x180023329  mov     rcx, [rsi+8]
  ... truncated ...
```
