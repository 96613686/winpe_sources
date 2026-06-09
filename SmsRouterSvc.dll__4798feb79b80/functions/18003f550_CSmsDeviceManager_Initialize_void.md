# CSmsDeviceManager::Initialize(void)

- ea: `0x18003f550`
- end: `0x18003f9ab`
- name: `?Initialize@CSmsDeviceManager@@UEAAJXZ`
- size: `1115`
- prototype: `__int64 __fastcall(CSmsDeviceManager *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003a60`
- `0x18001446c`
- `0x1800183c8`
- `0x180027e1c`
- `0x180028090`
- `0x18003f550`
- `0x18003f9b4`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f77c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f862`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f8bf`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f94b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f77c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f862`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f8bf`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003f94b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f61d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f6b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f61d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f62c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f70c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f62c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f70c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18003f7c1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18003f7c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f7f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f7f9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18003f66a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18003f702`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18003f66a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18003f702`

## string_xrefs

- `0x18003f60f`: `SmsRouter\TextMessageReadyEvent`
- `0x18003f6a7`: `SmsRouter\WapMessageReadyEvent`
- `0x18003f63b`: `Failed to create m_hTextMessageReady`
- `0x18003f683`: `Failed to create m_hTextMessageReadyWait`
- `0x18003f71b`: `Failed to create m_hWapMessageReadyWait`
- `0x18003f6d3`: `Failed to create m_hWapMessageReady`
- `0x18003f805`: `CoCreateInstance.CellularAPI, Ignoring the error`
- `0x18003f7cb`: `Failed to load CLSIDFromProgID("CellularAPI"), Ignoring the error`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSmsDeviceManager::Initialize(CSmsDeviceManager *this)
{
  char *v2; // r15
  char *v3; // rsi
  const char *v4; // r14
  HANDLE EventW; // rax
  signed int v6; // eax
  signed int LastError; // eax
  HANDLE v8; // rax
  signed int v9; // eax
  signed int v10; // eax
  int v11; // eax
  unsigned int v12; // edi
  _BYTE *v13; // rdx
  HRESULT v15; // eax
  HRESULT v16; // eax
  _BYTE *v17; // rdx
  _BYTE *v18; // rdx
  _BYTE *v19; // rdx
  __int64 v20[8]; // [rsp+40h] [rbp-79h] BYREF
  void **v21; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v22[56]; // [rsp+88h] [rbp-31h] BYREF
  _BYTE *v23; // [rsp+C0h] [rbp+7h]
  GUID clsid; // [rsp+D0h] [rbp+17h] BYREF

  clsid = 0;
  v2 = (char *)this - 24;
  v20[0] = (__int64)off_1800705C8;
  v20[1] = (__int64)this - 24;
  v20[7] = (__int64)v20;
  Windows::Sms::Common::undo_action::undo_action(&v21, v20);
  v3 = (char *)this + 72;
  (**((void (__fastcall ***)(char *))this + 9))((char *)this + 72);
  if ( *((_DWORD *)this + 3) || *((_DWORD *)this + 5) )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 72);
    v21 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v23 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v23 )
    {
      v19 = v22;
      LOBYTE(v19) = v23 != v22;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v23 + 32LL))(v23, v19);
    }
    return 2147549183LL;
  }
  else
  {
    CExecutionManager::Initialize((char *)this + 312);
    v4 = "CSmsDeviceManager::Initialize";
    if ( !g_fTextDone )
    {
      EventW = CreateEventW(0, 0, 0, L"SmsRouter\\TextMessageReadyEvent");
      *((_QWORD *)this + 4) = EventW;
      if ( EventW )
      {
        if ( !RegisterWaitForSingleObject(
                (PHANDLE)this + 6,
                EventW,
                CSmsDeviceManager::TextMessageReadyCallbackStatic,
                v2,
                0xFFFFFFFF,
                8u) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          LogSmsRouterError(
            "CSmsDeviceManager::Initialize",
            0x629u,
            LastError,
            "Failed to create m_hTextMessageReadyWait");
        }
      }
      else
      {
        v6 = GetLastError();
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        LogSmsRouterError("CSmsDeviceManager::Initialize", 0x622u, v6, "Failed to create m_hTextMessageReady");
      }
    }
    if ( !g_fWapDone )
    {
      v8 = CreateEventW(0, 0, 0, L"SmsRouter\\WapMessageReadyEvent");
      *((_QWORD *)this + 5) = v8;
      if ( v8 )
      {
        if ( !RegisterWaitForSingleObject(
                (PHANDLE)this + 7,
                v8,
                CSmsDeviceManager::WapMessageReadyCallbackStatic,
                v2,
                0xFFFFFFFF,
                8u) )
        {
          v10 = GetLastError();
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
          LogSmsRouterError("CSmsDeviceManager::Initialize", 0x63Au, v10, "Failed to create m_hWapMessageReadyWait");
        }
      }
      else
      {
        v9 = GetLastError();
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        LogSmsRouterError("CSmsDeviceManager::Initialize", 0x633u, v9, "Failed to create m_hWapMessageReady");
      }
    }
    v11 = CSmsDeviceManager::InitializeDeviceWatcher((CSmsDeviceManager *)v2);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v15 = CLSIDFromProgID(L"CellularAPI", &clsid);
      if ( v15 >= 0 )
      {
        v4 = (char *)this + 120;
        v16 = CoCreateInstance(&clsid, 0, 1u, &GUID_bc5d649c_7dd5_4fee_bbc2_b80d73abed98, (LPVOID *)this + 15);
        v12 = v16;
        if ( v16 >= 0 )
          goto LABEL_33;
        LogSmsRouterError(
          "CSmsDeviceManager::Initialize",
          0x64Fu,
          v16,
          "CoCreateInstance.CellularAPI, Ignoring the error");
      }
      else
      {
        LogSmsRouterError(
          "CSmsDeviceManager::Initialize",
          0x647u,
          v15,
          "Failed to load CLSIDFromProgID(\"CellularAPI\"), Ignoring the error");
      }
      while ( 1 )
      {
        *((_DWORD *)this + 3) = 1;
        Windows::Sms::Common::undo_action::release((Windows::Sms::Common::undo_action *)&v21);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 72);
        CExecutionManager::Start((CSmsDeviceManager *)((char *)this + 312));
        v21 = &Windows::Sms::Common::undo_action::`vftable';
        if ( v23 )
          break;
        std::_Xbad_function_call();
LABEL_33:
        if ( (*(int (__fastcall **)(_QWORD, char *))(**(_QWORD **)v4 + 24LL))(*(_QWORD *)v4, v2) < 0 )
        {
          LogSmsRouterError(
            "CSmsDeviceManager::Initialize",
            0x654u,
            v12,
            "m_Cellular->RegisterForModemExistenceChanges");
          (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 72);
          v21 = &Windows::Sms::Common::undo_action::`vftable';
          if ( !v23 )
          {
            std::_Xbad_function_call();
            __debugbreak();
          }
          (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v23 )
          {
            v17 = v22;
            LOBYTE(v17) = v23 != v22;
            (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v23 + 32LL))(v23, v17);
          }
          return v12;
        }
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v23 )
      {
        v18 = v22;
        LOBYTE(v18) = v23 != v22;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v23 + 32LL))(v23, v18);
      }
      return 0;
    }
    else
    {
      LogSmsRouterError("CSmsDeviceManager::Initialize", 0x641u, v11, "IntializeDeviceWatcher");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 72);
      v21 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v23 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v23 )
      {
        v13 = v22;
        LOBYTE(v13) = v23 != v22;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v23 + 32LL))(v23, v13);
      }
      return v12;
    }
  }
}

```

## disassembly

```asm
0x18003f550  mov     [rsp-8+arg_8], rbx
0x18003f555  mov     [rsp-8+arg_10], rsi
0x18003f55a  push    rbp
0x18003f55b  push    rdi
0x18003f55c  push    r12
0x18003f55e  push    r14
0x18003f560  push    r15
0x18003f562  lea     rbp, [rsp-37h]
0x18003f567  sub     rsp, 0F0h
0x18003f56e  mov     rax, cs:__security_cookie
0x18003f575  xor     rax, rsp
0x18003f578  mov     [rbp+57h+var_30], rax
0x18003f57c  mov     rbx, rcx
0x18003f57f  xorps   xmm0, xmm0
0x18003f582  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x18003f586  lea     r15, [rcx-18h]
0x18003f58a  lea     rax, off_1800705C8
0x18003f591  mov     [rbp+57h+var_D0], rax
0x18003f595  mov     [rbp+57h+var_C8], r15
0x18003f599  lea     rax, [rbp+57h+var_D0]
0x18003f59d  mov     [rbp+57h+var_98], rax
0x18003f5a1  lea     rdx, [rbp+57h+var_D0]
0x18003f5a5  lea     rcx, [rbp+57h+var_90]
0x18003f5a9  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x18003f5ae  nop
0x18003f5af  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18003f5b6  mov     [rsp+110h+var_E0], rax
0x18003f5bb  lea     rsi, [rbx+48h]
0x18003f5bf  mov     [rsp+110h+var_D8], rsi
0x18003f5c4  mov     rax, [rsi]
0x18003f5c7  mov     rcx, rsi
0x18003f5ca  mov     rax, [rax]
0x18003f5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5d2  nop
0x18003f5d3  cmp     dword ptr [rbx+0Ch], 0
0x18003f5d7  jnz     loc_18003F927
0x18003f5dd  cmp     dword ptr [rbx+14h], 0
0x18003f5e1  jnz     loc_18003F927
0x18003f5e7  lea     r12, [rbx+138h]
0x18003f5ee  mov     rcx, r12; Context
0x18003f5f1  call    ?Initialize@CExecutionManager@@QEAAJXZ; CExecutionManager::Initialize(void)
0x18003f5f6  mov     edi, 80070000h
0x18003f5fb  lea     r14, aCsmsdevicemana_12; "CSmsDeviceManager::Initialize"
0x18003f602  cmp     cs:?g_fTextDone@@3HA, 0; int g_fTextDone
0x18003f609  jnz     loc_18003F69A
0x18003f60f  lea     r9, aSmsrouterTextm; "SmsRouter\\TextMessageReadyEvent"
0x18003f616  xor     r8d, r8d; bInitialState
0x18003f619  xor     edx, edx; bManualReset
0x18003f61b  xor     ecx, ecx; lpEventAttributes
0x18003f61d  call    cs:__imp_CreateEventW
0x18003f623  mov     [rbx+20h], rax
0x18003f627  test    rax, rax
0x18003f62a  jnz     short loc_18003F649
0x18003f62c  call    cs:__imp_GetLastError
0x18003f632  test    eax, eax
0x18003f634  jle     short loc_18003F63B
0x18003f636  movzx   eax, ax
0x18003f639  or      eax, edi
0x18003f63b  lea     r9, aFailedToCreate_7; "Failed to create m_hTextMessageReady"
0x18003f642  mov     edx, 622h
0x18003f647  jmp     short loc_18003F68F
0x18003f649  lea     rcx, [rbx+30h]; phNewWaitObject
0x18003f64d  mov     [rsp+110h+dwFlags], 8; dwFlags
0x18003f655  mov     [rsp+110h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18003f65d  mov     r9, r15; Context
0x18003f660  lea     r8, ?TextMessageReadyCallbackStatic@CSmsDeviceManager@@CAXPEAXE@Z; Callback
0x18003f667  mov     rdx, rax; hObject
0x18003f66a  call    cs:__imp_RegisterWaitForSingleObject
0x18003f670  test    eax, eax
0x18003f672  jnz     short loc_18003F69A
0x18003f674  call    cs:__imp_GetLastError
0x18003f67a  test    eax, eax
0x18003f67c  jle     short loc_18003F683
0x18003f67e  movzx   eax, ax
0x18003f681  or      eax, edi
0x18003f683  lea     r9, aFailedToCreate_12; "Failed to create m_hTextMessageReadyWai"...
0x18003f68a  mov     edx, 629h; unsigned int
0x18003f68f  mov     r8d, eax; int
0x18003f692  mov     rcx, r14; char *
0x18003f695  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003f69a  cmp     cs:?g_fWapDone@@3HA, 0; int g_fWapDone
0x18003f6a1  jnz     loc_18003F732
0x18003f6a7  lea     r9, aSmsrouterWapme; "SmsRouter\\WapMessageReadyEvent"
0x18003f6ae  xor     r8d, r8d; bInitialState
0x18003f6b1  xor     edx, edx; bManualReset
0x18003f6b3  xor     ecx, ecx; lpEventAttributes
0x18003f6b5  call    cs:__imp_CreateEventW
0x18003f6bb  mov     [rbx+28h], rax
0x18003f6bf  test    rax, rax
0x18003f6c2  jnz     short loc_18003F6E1
0x18003f6c4  call    cs:__imp_GetLastError
0x18003f6ca  test    eax, eax
0x18003f6cc  jle     short loc_18003F6D3
0x18003f6ce  movzx   eax, ax
0x18003f6d1  or      eax, edi
0x18003f6d3  lea     r9, aFailedToCreate_8; "Failed to create m_hWapMessageReady"
0x18003f6da  mov     edx, 633h
0x18003f6df  jmp     short loc_18003F727
0x18003f6e1  lea     rcx, [rbx+38h]; phNewWaitObject
0x18003f6e5  mov     [rsp+110h+dwFlags], 8; dwFlags
0x18003f6ed  mov     [rsp+110h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18003f6f5  mov     r9, r15; Context
0x18003f6f8  lea     r8, ?WapMessageReadyCallbackStatic@CSmsDeviceManager@@CAXPEAXE@Z; Callback
0x18003f6ff  mov     rdx, rax; hObject
0x18003f702  call    cs:__imp_RegisterWaitForSingleObject
0x18003f708  test    eax, eax
0x18003f70a  jnz     short loc_18003F732
0x18003f70c  call    cs:__imp_GetLastError
0x18003f712  test    eax, eax
0x18003f714  jle     short loc_18003F71B
0x18003f716  movzx   eax, ax
0x18003f719  or      eax, edi
0x18003f71b  lea     r9, aFailedToCreate_0; "Failed to create m_hWapMessageReadyWait"
0x18003f722  mov     edx, 63Ah; unsigned int
0x18003f727  mov     r8d, eax; int
0x18003f72a  mov     rcx, r14; char *
0x18003f72d  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003f732  mov     rcx, r15; this
0x18003f735  call    ?InitializeDeviceWatcher@CSmsDeviceManager@@AEAAJXZ; CSmsDeviceManager::InitializeDeviceWatcher(void)
0x18003f73a  mov     edi, eax
0x18003f73c  test    eax, eax
0x18003f73e  jns     short loc_18003F7B6
0x18003f740  lea     r9, aIntializedevic; "IntializeDeviceWatcher"
0x18003f747  mov     r8d, eax; int
0x18003f74a  mov     edx, 641h; unsigned int
0x18003f74f  mov     rcx, r14; char *
0x18003f752  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003f757  nop
0x18003f758  mov     rdx, [rsi]
0x18003f75b  mov     rcx, rsi
0x18003f75e  mov     rax, [rdx+8]
0x18003f762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f767  nop
0x18003f768  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18003f76f  mov     [rbp+57h+var_90], rax
0x18003f773  mov     rcx, [rbp+57h+var_50]
0x18003f777  test    rcx, rcx
0x18003f77a  jnz     short loc_18003F783
0x18003f77c  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003f782  int     3; Trap to Debugger
0x18003f783  mov     rax, [rcx]
0x18003f786  mov     rax, [rax+10h]
0x18003f78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f78f  mov     rcx, [rbp+57h+var_50]
0x18003f793  test    rcx, rcx
0x18003f796  jz      short loc_18003F7AF
0x18003f798  mov     rax, [rcx]
0x18003f79b  lea     rdx, [rbp+57h+var_88]
0x18003f79f  cmp     rcx, rdx
0x18003f7a2  setnz   dl
0x18003f7a5  mov     rax, [rax+20h]
0x18003f7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7ae  nop
0x18003f7af  mov     eax, edi
0x18003f7b1  jmp     loc_18003F983
0x18003f7b6  lea     rdx, [rbp+57h+clsid]; lpclsid
0x18003f7ba  lea     rcx, szProgID; "CellularAPI"
0x18003f7c1  call    cs:__imp_CLSIDFromProgID
0x18003f7c7  test    eax, eax
0x18003f7c9  jns     short loc_18003F7DF
0x18003f7cb  lea     r9, aFailedToLoadCl; "Failed to load CLSIDFromProgID(\"Cellul"...
0x18003f7d2  mov     r8d, eax
0x18003f7d5  mov     edx, 647h
0x18003f7da  mov     rcx, r14
0x18003f7dd  jmp     short loc_18003F81B
0x18003f7df  lea     r14, [rbx+78h]
0x18003f7e3  mov     qword ptr [rsp+110h+dwMilliseconds], r14; ppv
0x18003f7e8  lea     r9, _GUID_bc5d649c_7dd5_4fee_bbc2_b80d73abed98; riid
0x18003f7ef  xor     edx, edx; pUnkOuter
0x18003f7f1  lea     r8d, [rdx+1]; dwClsContext
0x18003f7f5  lea     rcx, [rbp+57h+clsid]; rclsid
0x18003f7f9  call    cs:__imp_CoCreateInstance
0x18003f7ff  mov     edi, eax
0x18003f801  test    eax, eax
0x18003f803  jns     short loc_18003F869
0x18003f805  lea     r9, aCocreateinstan; "CoCreateInstance.CellularAPI, Ignoring "...
0x18003f80c  mov     r8d, eax; int
0x18003f80f  mov     edx, 64Fh; unsigned int
0x18003f814  lea     rcx, aCsmsdevicemana_12; "CSmsDeviceManager::Initialize"
0x18003f81b  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003f820  mov     dword ptr [rbx+0Ch], 1
0x18003f827  lea     rcx, [rbp+57h+var_90]; this
0x18003f82b  call    ?release@undo_action@Common@Sms@Windows@@QEAAXXZ; Windows::Sms::Common::undo_action::release(void)
0x18003f830  nop
0x18003f831  mov     rax, [rsi]
0x18003f834  mov     rcx, rsi
0x18003f837  mov     rax, [rax+8]
0x18003f83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f840  nop
0x18003f841  mov     rcx, r12; this
0x18003f844  call    ?Start@CExecutionManager@@QEAAJXZ; CExecutionManager::Start(void)
0x18003f849  nop
0x18003f84a  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18003f851  mov     [rbp+57h+var_90], rax
0x18003f855  mov     rcx, [rbp+57h+var_50]
0x18003f859  test    rcx, rcx
0x18003f85c  jnz     loc_18003F8F7
0x18003f862  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003f868  nop
0x18003f869  mov     rcx, [r14]
0x18003f86c  mov     rax, [rcx]
0x18003f86f  mov     rdx, r15
0x18003f872  mov     rax, [rax+18h]
0x18003f876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f87b  test    eax, eax
0x18003f87d  jns     short loc_18003F820
0x18003f87f  lea     r9, aMCellularRegis; "m_Cellular->RegisterForModemExistenceCh"...
0x18003f886  mov     r8d, edi; int
0x18003f889  mov     edx, 654h; unsigned int
0x18003f88e  lea     rcx, aCsmsdevicemana_12; "CSmsDeviceManager::Initialize"
0x18003f895  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18003f89a  nop
0x18003f89b  mov     rax, [rsi]
0x18003f89e  mov     rcx, rsi
0x18003f8a1  mov     rax, [rax+8]
0x18003f8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8aa  nop
0x18003f8ab  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18003f8b2  mov     [rbp+57h+var_90], rax
0x18003f8b6  mov     rcx, [rbp+57h+var_50]
0x18003f8ba  test    rcx, rcx
0x18003f8bd  jnz     short loc_18003F8C6
0x18003f8bf  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003f8c5  int     3; Trap to Debugger
0x18003f8c6  mov     rax, [rcx]
0x18003f8c9  mov     rax, [rax+10h]
0x18003f8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8d2  mov     rcx, [rbp+57h+var_50]
0x18003f8d6  test    rcx, rcx
0x18003f8d9  jz      short loc_18003F8F2
0x18003f8db  mov     rax, [rcx]
0x18003f8de  lea     rdx, [rbp+57h+var_88]
0x18003f8e2  cmp     rcx, rdx
0x18003f8e5  setnz   dl
0x18003f8e8  mov     rax, [rax+20h]
0x18003f8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8f1  nop
0x18003f8f2  jmp     loc_18003F7AF
0x18003f8f7  mov     rax, [rcx]
0x18003f8fa  mov     rax, [rax+10h]
0x18003f8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f903  mov     rcx, [rbp+57h+var_50]
0x18003f907  test    rcx, rcx
0x18003f90a  jz      short loc_18003F923
0x18003f90c  mov     rax, [rcx]
0x18003f90f  lea     rdx, [rbp+57h+var_88]
0x18003f913  cmp     rcx, rdx
0x18003f916  setnz   dl
0x18003f919  mov     rax, [rax+20h]
0x18003f91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f922  nop
0x18003f923  xor     eax, eax
0x18003f925  jmp     short loc_18003F983
0x18003f927  mov     rax, [rsi]
0x18003f92a  mov     rcx, rsi
0x18003f92d  mov     rax, [rax+8]
0x18003f931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f936  nop
0x18003f937  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18003f93e  mov     [rbp+57h+var_90], rax
0x18003f942  mov     rcx, [rbp+57h+var_50]
0x18003f946  test    rcx, rcx
0x18003f949  jnz     short loc_18003F952
0x18003f94b  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003f951  int     3; Trap to Debugger
0x18003f952  mov     rax, [rcx]
0x18003f955  mov     rax, [rax+10h]
0x18003f959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f95e  mov     rcx, [rbp+57h+var_50]
0x18003f962  test    rcx, rcx
0x18003f965  jz      short loc_18003F97E
0x18003f967  mov     rax, [rcx]
0x18003f96a  lea     rdx, [rbp+57h+var_88]
0x18003f96e  cmp     rcx, rdx
0x18003f971  setnz   dl
0x18003f974  mov     rax, [rax+20h]
0x18003f978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f97d  nop
0x18003f97e  mov     eax, 8000FFFFh
0x18003f983  mov     rcx, [rbp+57h+var_30]
0x18003f987  xor     rcx, rsp; StackCookie
0x18003f98a  call    __security_check_cookie
0x18003f98f  lea     r11, [rsp+110h+var_20]
0x18003f997  mov     rbx, [r11+38h]
0x18003f99b  mov     rsi, [r11+40h]
0x18003f99f  mov     rsp, r11
0x18003f9a2  pop     r15
0x18003f9a4  pop     r14
0x18003f9a6  pop     r12
0x18003f9a8  pop     rdi
0x18003f9a9  pop     rbp
0x18003f9aa  retn
```
