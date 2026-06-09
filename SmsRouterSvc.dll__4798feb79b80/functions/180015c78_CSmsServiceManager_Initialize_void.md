# CSmsServiceManager::Initialize(void)

- ea: `0x180015c78`
- end: `0x1800160e1`
- name: `?Initialize@CSmsServiceManager@@QEAAJXZ`
- size: `1129`
- prototype: `__int64 __fastcall(CSmsServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017648`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x18000fd94`
- `0x18001446c`
- `0x180015c78`
- `0x1800183c8`
- `0x180026640`
- `0x180039ab4`
- `0x18003d938`
- `0x180051420`
- `0x180063f98`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015d48`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015dd4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015e5b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015ee1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015fb2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180016036`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180016091`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015d48`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015dd4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015e5b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015ee1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180015fb2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180016036`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180016091`

## string_xrefs

- `0x180015d08`: `Create SmsRouter private namespace failed.`
- `0x180015d17`: `CSmsServiceManager::Initialize`
- `0x180015da3`: `CSmsServiceManager::Initialize`
- `0x180015e2a`: `CSmsServiceManager::Initialize`
- `0x180015eb0`: `CSmsServiceManager::Initialize`
- `0x180015f81`: `CSmsServiceManager::Initialize`
- `0x180015d94`: `CBroadcastConfigManager::GetInstance().Initialize()`
- `0x180015ea1`: `m_broker.Initialize`
- `0x180015f72`: `m_broker.Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsServiceManager::Initialize(CSmsServiceManager *this)
{
  char *v2; // rbx
  int SmsRouterNamespace; // eax
  unsigned int v4; // esi
  _BYTE *v5; // rdx
  int v7; // eax
  _BYTE *v8; // rdx
  int v9; // eax
  CSmsRouterBroker *v10; // rcx
  _BYTE *v11; // rdx
  int v12; // eax
  _BYTE *v13; // rdx
  CSmsDeviceManager *v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  _BYTE *v18; // rdx
  _BYTE *v19; // rdx
  _BYTE *v20; // rdx
  CSmsDeviceManager *v21; // [rsp+20h] [rbp-89h]
  __int64 v22[9]; // [rsp+38h] [rbp-71h] BYREF
  void **v23; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v24[56]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE *v25; // [rsp+C0h] [rbp+17h]

  v22[0] = (__int64)off_180070238;
  v22[1] = (__int64)this;
  v22[7] = (__int64)v22;
  Windows::Sms::Common::undo_action::undo_action(&v23, v22);
  v2 = (char *)this + 40;
  (**((void (__fastcall ***)(char *))this + 5))((char *)this + 40);
  if ( *(_QWORD *)((char *)this + 28) )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
    v23 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v25 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v25 )
    {
      v20 = v24;
      LOBYTE(v20) = v25 != v24;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v20);
    }
    return 2147549183LL;
  }
  else
  {
    SmsRouterNamespace = CSmsRpcUtils::CreateSmsRouterNamespace((void **)this + 106);
    v4 = SmsRouterNamespace;
    if ( SmsRouterNamespace < 0 )
    {
      LogSmsRouterError(
        "CSmsServiceManager::Initialize",
        0x71u,
        SmsRouterNamespace,
        "Create SmsRouter private namespace failed.");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
      v23 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v25 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v25 )
      {
        v5 = v24;
        LOBYTE(v5) = v25 != v24;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v5);
      }
      return v4;
    }
    v7 = CBroadcastConfigManager::Initialize(&CBroadcastConfigManager::s_Instance);
    v4 = v7;
    if ( v7 < 0 )
    {
      LogSmsRouterError(
        "CSmsServiceManager::Initialize",
        0x77u,
        v7,
        "CBroadcastConfigManager::GetInstance().Initialize()");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
      v23 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v25 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v25 )
      {
        v8 = v24;
        LOBYTE(v8) = v25 != v24;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v8);
      }
      return v4;
    }
    v9 = CSmsInterceptor::Initialize((CSmsServiceManager *)((char *)this + 96));
    v4 = v9;
    if ( v9 < 0 )
    {
      LogSmsRouterError("CSmsServiceManager::Initialize", 0x7Du, v9, "m_Interceptor.Initialize");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
      v23 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v25 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v25 )
      {
        v11 = v24;
        LOBYTE(v11) = v25 != v24;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v11);
      }
      return v4;
    }
    v12 = CSmsRouterBroker::Initialize(v10, this);
    v4 = v12;
    if ( v12 < 0 )
    {
      LogSmsRouterError("CSmsServiceManager::Initialize", 0x83u, v12, "m_broker.Initialize");
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
      v23 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v25 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v25 )
      {
        v13 = v24;
        LOBYTE(v13) = v25 != v24;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v13);
      }
      return v4;
    }
    v21 = (CSmsDeviceManager *)operator new(0x1E8u);
    v14 = CSmsDeviceManager::CSmsDeviceManager(v21);
    v15 = ((unsigned __int64)v14 + 24) & -(__int64)(v14 != 0);
    v16 = *((_QWORD *)this + 105);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)this + 105) = v15;
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
    v4 = v17;
    if ( v17 < 0 )
    {
      LogSmsRouterError("CSmsServiceManager::Initialize", 0x8Au, v17, "m_broker.Initialize", v21);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
      v23 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v25 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v25 )
      {
        v18 = v24;
        LOBYTE(v18) = v25 != v24;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v18);
      }
      return v4;
    }
    (*(void (__fastcall **)(_QWORD, CSmsServiceManager *))(**((_QWORD **)this + 105) + 40LL))(
      *((_QWORD *)this + 105),
      this);
    *(_QWORD *)((char *)this + 28) = 1;
    Windows::Sms::Common::undo_action::release((Windows::Sms::Common::undo_action *)&v23);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
    v23 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v25 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v25 )
    {
      v19 = v24;
      LOBYTE(v19) = v25 != v24;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, v19);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180015c78  push    rbp
0x180015c7a  push    rbx
0x180015c7b  push    rsi
0x180015c7c  push    rdi
0x180015c7d  lea     rbp, [rsp-3Fh]
0x180015c82  sub     rsp, 0E8h
0x180015c89  mov     rax, cs:__security_cookie
0x180015c90  xor     rax, rsp
0x180015c93  mov     [rbp+57h+var_30], rax
0x180015c97  mov     rdi, rcx
0x180015c9a  lea     rax, off_180070238
0x180015ca1  mov     [rbp+57h+var_C8], rax
0x180015ca5  mov     [rbp+57h+var_C0], rcx
0x180015ca9  lea     rax, [rbp+57h+var_C8]
0x180015cad  mov     [rbp+57h+var_90], rax
0x180015cb1  lea     rdx, [rbp+57h+var_C8]
0x180015cb5  lea     rcx, [rbp+57h+var_80]
0x180015cb9  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x180015cbe  nop
0x180015cbf  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180015cc6  mov     [rsp+100h+var_D8], rax
0x180015ccb  lea     rbx, [rdi+28h]
0x180015ccf  mov     [rbp+57h+var_D0], rbx
0x180015cd3  mov     rax, [rbx]
0x180015cd6  mov     rcx, rbx
0x180015cd9  mov     rax, [rax]
0x180015cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce1  nop
0x180015ce2  cmp     dword ptr [rdi+1Ch], 0
0x180015ce6  jnz     loc_18001606D
0x180015cec  cmp     dword ptr [rdi+20h], 0
0x180015cf0  jnz     loc_18001606D
0x180015cf6  lea     rcx, [rdi+350h]; void **
0x180015cfd  call    ?CreateSmsRouterNamespace@CSmsRpcUtils@@SAJPEAPEAX@Z; CSmsRpcUtils::CreateSmsRouterNamespace(void * *)
0x180015d02  mov     esi, eax
0x180015d04  test    eax, eax
0x180015d06  jns     short loc_180015D82
0x180015d08  lea     r9, aCreateSmsroute; "Create SmsRouter private namespace fail"...
0x180015d0f  mov     r8d, eax; int
0x180015d12  mov     edx, 71h ; 'q'; unsigned int
0x180015d17  lea     rcx, aCsmsserviceman_3; "CSmsServiceManager::Initialize"
0x180015d1e  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180015d23  nop
0x180015d24  mov     rdx, [rbx]
0x180015d27  mov     rcx, rbx
0x180015d2a  mov     rax, [rdx+8]
0x180015d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d33  nop
0x180015d34  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180015d3b  mov     [rbp+57h+var_80], rax
0x180015d3f  mov     rcx, [rbp+57h+var_40]
0x180015d43  test    rcx, rcx
0x180015d46  jnz     short loc_180015D4F
0x180015d48  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180015d4e  int     3; Trap to Debugger
0x180015d4f  mov     rax, [rcx]
0x180015d52  mov     rax, [rax+10h]
0x180015d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d5b  mov     rcx, [rbp+57h+var_40]
0x180015d5f  test    rcx, rcx
0x180015d62  jz      short loc_180015D7B
0x180015d64  mov     rax, [rcx]
0x180015d67  lea     rdx, [rbp+57h+var_78]
0x180015d6b  cmp     rcx, rdx
0x180015d6e  setnz   dl
0x180015d71  mov     rax, [rax+20h]
0x180015d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d7a  nop
0x180015d7b  mov     eax, esi
0x180015d7d  jmp     loc_1800160C9
0x180015d82  lea     rcx, ?s_Instance@CBroadcastConfigManager@@0V1@A; Context
0x180015d89  call    ?Initialize@CBroadcastConfigManager@@QEAAJXZ; CBroadcastConfigManager::Initialize(void)
0x180015d8e  mov     esi, eax
0x180015d90  test    eax, eax
0x180015d92  jns     short loc_180015E0C
0x180015d94  lea     r9, aCbroadcastconf; "CBroadcastConfigManager::GetInstance()."...
0x180015d9b  mov     r8d, eax; int
0x180015d9e  mov     edx, 77h ; 'w'; unsigned int
0x180015da3  lea     rcx, aCsmsserviceman_3; "CSmsServiceManager::Initialize"
0x180015daa  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180015daf  nop
0x180015db0  mov     rcx, [rbx]
0x180015db3  mov     rax, [rcx+8]
0x180015db7  mov     rcx, rbx
0x180015dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dbf  nop
0x180015dc0  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180015dc7  mov     [rbp+57h+var_80], rax
0x180015dcb  mov     rcx, [rbp+57h+var_40]
0x180015dcf  test    rcx, rcx
0x180015dd2  jnz     short loc_180015DDB
0x180015dd4  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180015dda  int     3; Trap to Debugger
0x180015ddb  mov     rax, [rcx]
0x180015dde  mov     rax, [rax+10h]
0x180015de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015de7  mov     rcx, [rbp+57h+var_40]
0x180015deb  test    rcx, rcx
0x180015dee  jz      short loc_180015E07
0x180015df0  mov     rax, [rcx]
0x180015df3  lea     rdx, [rbp+57h+var_78]
0x180015df7  cmp     rcx, rdx
0x180015dfa  setnz   dl
0x180015dfd  mov     rax, [rax+20h]
0x180015e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e06  nop
0x180015e07  jmp     loc_180015D7B
0x180015e0c  lea     rcx, [rdi+60h]; this
0x180015e10  call    ?Initialize@CSmsInterceptor@@QEAAJXZ; CSmsInterceptor::Initialize(void)
0x180015e15  mov     esi, eax
0x180015e17  test    eax, eax
0x180015e19  jns     short loc_180015E93
0x180015e1b  lea     r9, aMInterceptorIn; "m_Interceptor.Initialize"
0x180015e22  mov     r8d, eax; int
0x180015e25  mov     edx, 7Dh ; '}'; unsigned int
0x180015e2a  lea     rcx, aCsmsserviceman_3; "CSmsServiceManager::Initialize"
0x180015e31  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180015e36  nop
0x180015e37  mov     rcx, [rbx]
0x180015e3a  mov     rax, [rcx+8]
0x180015e3e  mov     rcx, rbx
0x180015e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e46  nop
0x180015e47  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180015e4e  mov     [rbp+57h+var_80], rax
0x180015e52  mov     rcx, [rbp+57h+var_40]
0x180015e56  test    rcx, rcx
0x180015e59  jnz     short loc_180015E62
0x180015e5b  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180015e61  int     3; Trap to Debugger
0x180015e62  mov     rax, [rcx]
0x180015e65  mov     rax, [rax+10h]
0x180015e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e6e  mov     rcx, [rbp+57h+var_40]
0x180015e72  test    rcx, rcx
0x180015e75  jz      short loc_180015E8E
0x180015e77  mov     rax, [rcx]
0x180015e7a  lea     rdx, [rbp+57h+var_78]
0x180015e7e  cmp     rcx, rdx
0x180015e81  setnz   dl
0x180015e84  mov     rax, [rax+20h]
0x180015e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e8d  nop
0x180015e8e  jmp     loc_180015D7B
0x180015e93  mov     rdx, rdi; struct CSmsServiceManager *
0x180015e96  call    ?Initialize@CSmsRouterBroker@@QEAAJPEAVCSmsServiceManager@@@Z; CSmsRouterBroker::Initialize(CSmsServiceManager *)
0x180015e9b  mov     esi, eax
0x180015e9d  test    eax, eax
0x180015e9f  jns     short loc_180015F19
0x180015ea1  lea     r9, aMBrokerInitial; "m_broker.Initialize"
0x180015ea8  mov     r8d, eax; int
0x180015eab  mov     edx, 83h; unsigned int
0x180015eb0  lea     rcx, aCsmsserviceman_3; "CSmsServiceManager::Initialize"
0x180015eb7  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180015ebc  nop
0x180015ebd  mov     rcx, [rbx]
0x180015ec0  mov     rax, [rcx+8]
0x180015ec4  mov     rcx, rbx
0x180015ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ecc  nop
0x180015ecd  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180015ed4  mov     [rbp+57h+var_80], rax
0x180015ed8  mov     rcx, [rbp+57h+var_40]
0x180015edc  test    rcx, rcx
0x180015edf  jnz     short loc_180015EE8
0x180015ee1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180015ee7  int     3; Trap to Debugger
0x180015ee8  mov     rax, [rcx]
0x180015eeb  mov     rax, [rax+10h]
0x180015eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef4  mov     rcx, [rbp+57h+var_40]
0x180015ef8  test    rcx, rcx
0x180015efb  jz      short loc_180015F14
0x180015efd  mov     rax, [rcx]
0x180015f00  lea     rdx, [rbp+57h+var_78]
0x180015f04  cmp     rcx, rdx
0x180015f07  setnz   dl
0x180015f0a  mov     rax, [rax+20h]
0x180015f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f13  nop
0x180015f14  jmp     loc_180015D7B
0x180015f19  mov     ecx, 1E8h; Size
0x180015f1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015f23  mov     [rsp+100h+var_E0], rax
0x180015f28  mov     rcx, rax; this
0x180015f2b  call    ??0CSmsDeviceManager@@QEAA@XZ; CSmsDeviceManager::CSmsDeviceManager(void)
0x180015f30  nop
0x180015f31  lea     rcx, [rax+18h]
0x180015f35  neg     rax
0x180015f38  sbb     rsi, rsi
0x180015f3b  and     rsi, rcx
0x180015f3e  mov     rcx, [rdi+348h]
0x180015f45  test    rcx, rcx
0x180015f48  jz      short loc_180015F56
0x180015f4a  mov     rax, [rcx]
0x180015f4d  mov     rax, [rax+10h]
0x180015f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f56  mov     [rdi+348h], rsi
0x180015f5d  mov     rax, [rsi]
0x180015f60  mov     rcx, rsi
0x180015f63  mov     rax, [rax+18h]
0x180015f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f6c  mov     esi, eax
0x180015f6e  test    eax, eax
0x180015f70  jns     short loc_180015FEA
0x180015f72  lea     r9, aMBrokerInitial; "m_broker.Initialize"
0x180015f79  mov     r8d, eax; int
0x180015f7c  mov     edx, 8Ah; unsigned int
0x180015f81  lea     rcx, aCsmsserviceman_3; "CSmsServiceManager::Initialize"
0x180015f88  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180015f8d  nop
0x180015f8e  mov     rcx, [rbx]
0x180015f91  mov     rax, [rcx+8]
0x180015f95  mov     rcx, rbx
0x180015f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f9d  nop
0x180015f9e  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180015fa5  mov     [rbp+57h+var_80], rax
0x180015fa9  mov     rcx, [rbp+57h+var_40]
0x180015fad  test    rcx, rcx
0x180015fb0  jnz     short loc_180015FB9
0x180015fb2  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180015fb8  int     3; Trap to Debugger
0x180015fb9  mov     rax, [rcx]
0x180015fbc  mov     rax, [rax+10h]
0x180015fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fc5  mov     rcx, [rbp+57h+var_40]
0x180015fc9  test    rcx, rcx
0x180015fcc  jz      short loc_180015FE5
0x180015fce  mov     rax, [rcx]
0x180015fd1  lea     rdx, [rbp+57h+var_78]
0x180015fd5  cmp     rcx, rdx
0x180015fd8  setnz   dl
0x180015fdb  mov     rax, [rax+20h]
0x180015fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe4  nop
0x180015fe5  jmp     loc_180015D7B
0x180015fea  mov     rcx, [rdi+348h]
0x180015ff1  mov     rax, [rcx]
0x180015ff4  mov     rdx, rdi
0x180015ff7  mov     rax, [rax+28h]
0x180015ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016000  mov     qword ptr [rdi+1Ch], 1
0x180016008  lea     rcx, [rbp+57h+var_80]; this
0x18001600c  call    ?release@undo_action@Common@Sms@Windows@@QEAAXXZ; Windows::Sms::Common::undo_action::release(void)
0x180016011  nop
0x180016012  mov     rax, [rbx]
0x180016015  mov     rcx, rbx
0x180016018  mov     rax, [rax+8]
0x18001601c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016021  nop
0x180016022  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180016029  mov     [rbp+57h+var_80], rax
0x18001602d  mov     rcx, [rbp+57h+var_40]
0x180016031  test    rcx, rcx
0x180016034  jnz     short loc_18001603D
0x180016036  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001603c  int     3; Trap to Debugger
0x18001603d  mov     rax, [rcx]
0x180016040  mov     rax, [rax+10h]
0x180016044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016049  mov     rcx, [rbp+57h+var_40]
0x18001604d  test    rcx, rcx
0x180016050  jz      short loc_180016069
0x180016052  mov     rax, [rcx]
0x180016055  lea     rdx, [rbp+57h+var_78]
0x180016059  cmp     rcx, rdx
0x18001605c  setnz   dl
0x18001605f  mov     rax, [rax+20h]
0x180016063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016068  nop
0x180016069  xor     eax, eax
0x18001606b  jmp     short loc_1800160C9
0x18001606d  mov     rax, [rbx]
0x180016070  mov     rcx, rbx
0x180016073  mov     rax, [rax+8]
0x180016077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001607c  nop
0x18001607d  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180016084  mov     [rbp+57h+var_80], rax
0x180016088  mov     rcx, [rbp+57h+var_40]
0x18001608c  test    rcx, rcx
0x18001608f  jnz     short loc_180016098
0x180016091  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180016097  int     3; Trap to Debugger
0x180016098  mov     rax, [rcx]
0x18001609b  mov     rax, [rax+10h]
0x18001609f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160a4  mov     rcx, [rbp+57h+var_40]
0x1800160a8  test    rcx, rcx
0x1800160ab  jz      short loc_1800160C4
0x1800160ad  mov     rax, [rcx]
0x1800160b0  lea     rdx, [rbp+57h+var_78]
0x1800160b4  cmp     rcx, rdx
0x1800160b7  setnz   dl
0x1800160ba  mov     rax, [rax+20h]
0x1800160be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160c3  nop
0x1800160c4  mov     eax, 8000FFFFh
0x1800160c9  mov     rcx, [rbp+57h+var_30]
  ... truncated ...
```
