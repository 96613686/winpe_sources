# CSmsDeviceManager::ProcessDeviceInterfaceId(ushort const *)

- ea: `0x180040274`
- end: `0x180040912`
- name: `?ProcessDeviceInterfaceId@CSmsDeviceManager@@AEAAJPEBG@Z`
- size: `1694`
- prototype: `__int64 __fastcall(void (__fastcall ***this)(char *), const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800442e0`

## callees

- `0x180003a60`
- `0x18000498c`
- `0x180004998`
- `0x18000659c`
- `0x18001446c`
- `0x18003e790`
- `0x180040274`
- `0x180040918`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004043d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800404ec`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800405c5`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004060e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800406b7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180040700`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800407f8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180040841`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800408b2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004043d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800404ec`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800405c5`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004060e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800406b7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180040700`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800407f8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180040841`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800408b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040576`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040576`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004066c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004066c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800403f7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800404a6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800403f7`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800404a6`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180040491`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180040491`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800403e2`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x1800403e2`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180040333`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180040333`

## string_xrefs

- `0x1800404c0`: `CM_Open_DevNode_Key failed for device Id: %S`
- `0x180040688`: `CLSIDFromString failed for NetCfgInstanceId: %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsDeviceManager::ProcessDeviceInterfaceId(
        void (__fastcall ***this)(char *),
        const unsigned __int16 *a2)
{
  int ObjectProperties; // eax
  unsigned int v5; // edi
  wchar_t *v6; // rsi
  CONFIGRET v7; // eax
  signed int v8; // eax
  _BYTE *v9; // rdx
  CONFIGRET v10; // eax
  signed int v11; // eax
  _BYTE *v12; // rdx
  LSTATUS v13; // eax
  _BYTE *v14; // rdx
  _BYTE *v15; // rdx
  _BYTE *v16; // rdx
  _BYTE *v17; // rdx
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  char *v20; // r15
  __int64 v21; // rbx
  _BYTE *v22; // rdx
  _BYTE *v23; // rdx
  _BYTE *v25; // rdx
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  DEVNODE pdnDevInst; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v31[8]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v32[8]; // [rsp+B0h] [rbp-50h] BYREF
  DEVPROPKEY v33; // [rsp+F0h] [rbp-10h] BYREF
  int v34; // [rsp+104h] [rbp+4h]
  __int64 v35; // [rsp+108h] [rbp+8h]
  void **v36; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v37[56]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE *v38; // [rsp+150h] [rbp+50h]
  GUID pclsid; // [rsp+160h] [rbp+60h] BYREF
  void **v40; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v41[56]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE *v42; // [rsp+1B0h] [rbp+B0h]
  OLECHAR Data[40]; // [rsp+1C0h] [rbp+C0h] BYREF

  v26 = 0;
  v29 = 0;
  v33 = DEVPKEY_Device_InstanceId;
  v34 = 0;
  v35 = 0;
  pdnDevInst = 0;
  hKey[0] = 0;
  memset_0(Data, 0, sizeof(Data));
  cbData = 80;
  pclsid = GUID_NULL;
  ObjectProperties = DevGetObjectProperties(1, a2, 0, 1, &v33, &v26, &v29);
  v5 = ObjectProperties;
  if ( ObjectProperties < 0 )
  {
    LogSmsRouterError(
      "CSmsDeviceManager::ProcessDeviceInterfaceId",
      0x1F1u,
      ObjectProperties,
      "Failed to get actual device Id for interface: %S",
      a2);
    return v5;
  }
  v31[0] = off_1800704C8;
  v31[1] = &v26;
  v31[2] = &v29;
  v31[7] = v31;
  Windows::Sms::Common::undo_action::undo_action(&v36, v31);
  if ( v26 != 1 || *(_DWORD *)(v29 + 32) != 18 )
  {
    v5 = -2147418113;
    LogSmsRouterError(
      "CSmsDeviceManager::ProcessDeviceInterfaceId",
      0x1FCu,
      -2147418113,
      "Failed to get actual device Id for interface: %S",
      a2);
    v36 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v38 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v38 )
    {
      v25 = v37;
      LOBYTE(v25) = v38 != v37;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v38 + 32LL))(v38, v25);
    }
    return v5;
  }
  v6 = *(wchar_t **)(v29 + 40);
  LogSmsRouterInfo("CSmsDeviceManager::ProcessDeviceInterfaceId", 0x201u, "Received net device id: %S", v6);
  v7 = CM_Locate_DevNodeW(&pdnDevInst, v6, 0);
  if ( v7 )
  {
    v8 = CM_MapCrToWin32Err(v7, 0x490u);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    LogSmsRouterError(
      "CSmsDeviceManager::ProcessDeviceInterfaceId",
      0x207u,
      v5,
      "CM_Locate_DevInst failed for device Id: %S",
      v6);
    v36 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v38 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v38 )
    {
      v9 = v37;
      LOBYTE(v9) = v38 != v37;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v38 + 32LL))(v38, v9);
    }
    return v5;
  }
  v10 = CM_Open_DevNode_Key(pdnDevInst, 1u, 0, 1u, hKey, 1u);
  if ( v10 )
  {
    v11 = CM_MapCrToWin32Err(v10, 0x490u);
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    LogSmsRouterError(
      "CSmsDeviceManager::ProcessDeviceInterfaceId",
      0x20Fu,
      v5,
      "CM_Open_DevNode_Key failed for device Id: %S",
      v6);
    v36 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v38 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v38 )
    {
      v12 = v37;
      LOBYTE(v12) = v38 != v37;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v38 + 32LL))(v38, v12);
    }
    return v5;
  }
  v32[0] = off_180070430;
  v32[1] = hKey;
  v32[7] = v32;
  Windows::Sms::Common::undo_action::undo_action(&v40, v32);
  v13 = RegQueryValueExW(hKey[0], L"NetCfgInstanceId", 0, 0, (LPBYTE)Data, &cbData);
  v5 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    LogSmsRouterError(
      "CSmsDeviceManager::ProcessDeviceInterfaceId",
      0x21Cu,
      v5,
      "Query NetCfgInstanceId failed for device Id: %S",
      v6);
    v40 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v42 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v42 )
    {
      v14 = v41;
      LOBYTE(v14) = v42 != v41;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v14);
      v42 = 0;
    }
    v36 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v38 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v38 )
    {
      v15 = v37;
      LOBYTE(v15) = v38 != v37;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v38 + 32LL))(v38, v15);
    }
    return v5;
  }
  LogSmsRouterInfo("CSmsDeviceManager::ProcessDeviceInterfaceId", 0x220u, "Received NetCfgInstanceId: %S", Data);
  v5 = CLSIDFromString(Data, &pclsid);
  if ( (v5 & 0x80000000) != 0 )
  {
    LogSmsRouterError(
      "CSmsDeviceManager::ProcessDeviceInterfaceId",
      0x224u,
      v5,
      "CLSIDFromString failed for NetCfgInstanceId: %S",
      Data);
    v40 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v42 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v42 )
    {
      v16 = v41;
      LOBYTE(v16) = v42 != v41;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v16);
      v42 = 0;
    }
    v36 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v38 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v38 )
    {
      v17 = v37;
      LOBYTE(v17) = v38 != v37;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v38 + 32LL))(v38, v17);
    }
    return v5;
  }
  hKey[1] = (HKEY)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  hKey[2] = (HKEY)(this + 12);
  (*this[12])((char *)this + 96);
  if ( *((_DWORD *)this + 9) )
  {
    v18 = std::map<_GUID,std::wstring,CGuidLessCompare,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](
            this + 32,
            &pclsid);
    v19 = -1;
    do
      ++v19;
    while ( v6[v19] );
    if ( v19 > *(_QWORD *)(v18 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v18);
    }
    else
    {
      if ( *(_QWORD *)(v18 + 24) <= 7u )
        v20 = (char *)v18;
      else
        v20 = *(char **)v18;
      *(_QWORD *)(v18 + 16) = v19;
      v21 = 2 * v19;
      memmove_0(v20, v6, 2 * v19);
      *(_WORD *)&v20[v21] = 0;
    }
  }
  this[12][1]((char *)this + 96);
  if ( *((_DWORD *)this + 10) )
    CSmsDeviceManager::ProcessInterfaceGUID((CSmsDeviceManager *)this, &pclsid);
  v40 = &Windows::Sms::Common::undo_action::`vftable';
  if ( !v42 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v42 )
  {
    v22 = v41;
    LOBYTE(v22) = v42 != v41;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v22);
    v42 = 0;
  }
  v36 = &Windows::Sms::Common::undo_action::`vftable';
  if ( !v38 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v38 )
  {
    v23 = v37;
    LOBYTE(v23) = v38 != v37;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v38 + 32LL))(v38, v23);
  }
  return 0;
}

```

## disassembly

```asm
0x180040274  mov     [rsp-8+arg_10], rbx
0x180040279  mov     [rsp-8+arg_18], rsi
0x18004027e  push    rbp
0x18004027f  push    rdi
0x180040280  push    r12
0x180040282  push    r14
0x180040284  push    r15
0x180040286  lea     rbp, [rsp-120h]
0x18004028e  sub     rsp, 220h
0x180040295  mov     rax, cs:__security_cookie
0x18004029c  xor     rax, rsp
0x18004029f  mov     [rbp+140h+var_30], rax
0x1800402a6  mov     rbx, rdx
0x1800402a9  mov     r14, rcx
0x1800402ac  xor     r12d, r12d
0x1800402af  mov     [rsp+240h+var_200], r12d
0x1800402b4  mov     [rsp+240h+var_1F0], r12
0x1800402b9  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x1800402c0  movups  [rbp+140h+var_150], xmm0
0x1800402c4  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x1800402ca  mov     [rbp+140h+var_140], eax
0x1800402cd  mov     [rbp+140h+var_13C], r12d
0x1800402d1  mov     [rbp+140h+var_138], r12
0x1800402d5  mov     [rsp+240h+pdnDevInst], r12d
0x1800402da  mov     [rsp+240h+hKey], r12
0x1800402df  lea     edi, [r12+50h]
0x1800402e4  mov     r8d, edi; Size
0x1800402e7  xor     edx, edx; Val
0x1800402e9  lea     rcx, [rbp+140h+Data]; void *
0x1800402f0  call    memset_0
0x1800402f5  mov     [rsp+240h+cbData], edi
0x1800402f9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180040300  movdqu  xmmword ptr [rbp+140h+pclsid.Data1], xmm0
0x180040305  lea     rax, [rsp+240h+var_1F0]
0x18004030a  mov     [rsp+240h+var_210], rax
0x18004030f  lea     rax, [rsp+240h+var_200]
0x180040314  mov     qword ptr [rsp+240h+ulFlags], rax
0x180040319  lea     rax, [rbp+140h+var_150]
0x18004031d  mov     [rsp+240h+phkDevice], rax
0x180040322  lea     r15d, [r12+1]
0x180040327  mov     r9d, r15d
0x18004032a  xor     r8d, r8d
0x18004032d  mov     rdx, rbx
0x180040330  mov     ecx, r15d
0x180040333  call    cs:__imp_DevGetObjectProperties
0x180040339  mov     edi, eax
0x18004033b  test    eax, eax
0x18004033d  jns     short loc_180040364
0x18004033f  mov     [rsp+240h+phkDevice], rbx
0x180040344  lea     r9, aFailedToGetAct; "Failed to get actual device Id for inte"...
0x18004034b  mov     r8d, eax; int
0x18004034e  mov     edx, 1F1h; unsigned int
0x180040353  lea     rcx, aCsmsdevicemana_8; "CSmsDeviceManager::ProcessDeviceInterfa"...
0x18004035a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004035f  jmp     loc_1800408E5
0x180040364  lea     rax, off_1800704C8
0x18004036b  mov     [rsp+240h+var_1D0], rax
0x180040370  lea     rax, [rsp+240h+var_200]
0x180040375  mov     [rsp+240h+var_1C8], rax
0x18004037a  lea     rax, [rsp+240h+var_1F0]
0x18004037f  mov     [rbp+140h+var_1C0], rax
0x180040383  lea     rax, [rsp+240h+var_1D0]
0x180040388  mov     [rbp+140h+var_198], rax
0x18004038c  lea     rdx, [rsp+240h+var_1D0]
0x180040391  lea     rcx, [rbp+140h+var_130]
0x180040395  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x18004039a  nop
0x18004039b  cmp     [rsp+240h+var_200], r15d
0x1800403a0  jnz     loc_180040878
0x1800403a6  mov     rsi, [rsp+240h+var_1F0]
0x1800403ab  cmp     dword ptr [rsi+20h], 12h
0x1800403af  jnz     loc_180040878
0x1800403b5  mov     rsi, [rsi+28h]
0x1800403b9  mov     r9, rsi
0x1800403bc  lea     r8, aReceivedNetDev; "Received net device id: %S"
0x1800403c3  mov     edx, 201h; unsigned int
0x1800403c8  lea     rbx, aCsmsdevicemana_8; "CSmsDeviceManager::ProcessDeviceInterfa"...
0x1800403cf  mov     rcx, rbx; char *
0x1800403d2  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x1800403d7  xor     r8d, r8d; ulFlags
0x1800403da  mov     rdx, rsi; pDeviceID
0x1800403dd  lea     rcx, [rsp+240h+pdnDevInst]; pdnDevInst
0x1800403e2  call    cs:__imp_CM_Locate_DevNodeW
0x1800403e8  test    eax, eax
0x1800403ea  jz      loc_180040475
0x1800403f0  mov     edx, 490h; DefaultErr
0x1800403f5  mov     ecx, eax; CmReturnCode
0x1800403f7  call    cs:__imp_CM_MapCrToWin32Err
0x1800403fd  mov     edi, eax
0x1800403ff  test    eax, eax
0x180040401  jle     short loc_18004040C
0x180040403  movzx   edi, ax
0x180040406  or      edi, 80070000h
0x18004040c  mov     [rsp+240h+phkDevice], rsi
0x180040411  lea     r9, aCmLocateDevins; "CM_Locate_DevInst failed for device Id:"...
0x180040418  mov     r8d, edi; int
0x18004041b  mov     edx, 207h; unsigned int
0x180040420  mov     rcx, rbx; char *
0x180040423  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180040428  nop
0x180040429  lea     rbx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180040430  mov     [rbp+140h+var_130], rbx
0x180040434  mov     rcx, [rbp+140h+var_F0]
0x180040438  test    rcx, rcx
0x18004043b  jnz     short loc_180040444
0x18004043d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180040443  int     3; Trap to Debugger
0x180040444  mov     rax, [rcx]
0x180040447  mov     rax, [rax+10h]
0x18004044b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040450  mov     rcx, [rbp+140h+var_F0]
0x180040454  test    rcx, rcx
0x180040457  jz      short loc_180040470
0x180040459  mov     rax, [rcx]
0x18004045c  lea     rdx, [rbp+140h+var_128]
0x180040460  cmp     rcx, rdx
0x180040463  setnz   dl
0x180040466  mov     rax, [rax+20h]
0x18004046a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004046f  nop
0x180040470  jmp     loc_1800408E5
0x180040475  mov     [rsp+240h+ulFlags], r15d; ulFlags
0x18004047a  lea     rax, [rsp+240h+hKey]
0x18004047f  mov     [rsp+240h+phkDevice], rax; phkDevice
0x180040484  mov     r9d, r15d; Disposition
0x180040487  xor     r8d, r8d; ulHardwareProfile
0x18004048a  mov     edx, r15d; samDesired
0x18004048d  mov     ecx, [rsp+240h+pdnDevInst]; dnDevNode
0x180040491  call    cs:__imp_CM_Open_DevNode_Key
0x180040497  test    eax, eax
0x180040499  jz      loc_180040524
0x18004049f  mov     edx, 490h; DefaultErr
0x1800404a4  mov     ecx, eax; CmReturnCode
0x1800404a6  call    cs:__imp_CM_MapCrToWin32Err
0x1800404ac  mov     edi, eax
0x1800404ae  test    eax, eax
0x1800404b0  jle     short loc_1800404BB
0x1800404b2  movzx   edi, ax
0x1800404b5  or      edi, 80070000h
0x1800404bb  mov     [rsp+240h+phkDevice], rsi
0x1800404c0  lea     r9, aCmOpenDevnodeK_0; "CM_Open_DevNode_Key failed for device I"...
0x1800404c7  mov     r8d, edi; int
0x1800404ca  mov     edx, 20Fh; unsigned int
0x1800404cf  mov     rcx, rbx; char *
0x1800404d2  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800404d7  nop
0x1800404d8  lea     rbx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x1800404df  mov     [rbp+140h+var_130], rbx
0x1800404e3  mov     rcx, [rbp+140h+var_F0]
0x1800404e7  test    rcx, rcx
0x1800404ea  jnz     short loc_1800404F3
0x1800404ec  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800404f2  int     3; Trap to Debugger
0x1800404f3  mov     rax, [rcx]
0x1800404f6  mov     rax, [rax+10h]
0x1800404fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404ff  mov     rcx, [rbp+140h+var_F0]
0x180040503  test    rcx, rcx
0x180040506  jz      short loc_18004051F
0x180040508  mov     rax, [rcx]
0x18004050b  lea     rdx, [rbp+140h+var_128]
0x18004050f  cmp     rcx, rdx
0x180040512  setnz   dl
0x180040515  mov     rax, [rax+20h]
0x180040519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004051e  nop
0x18004051f  jmp     loc_1800408E5
0x180040524  lea     rax, off_180070430
0x18004052b  mov     [rbp+140h+var_190], rax
0x18004052f  lea     rax, [rsp+240h+hKey]
0x180040534  mov     [rbp+140h+var_188], rax
0x180040538  lea     rax, [rbp+140h+var_190]
0x18004053c  mov     [rbp+140h+var_158], rax
0x180040540  lea     rdx, [rbp+140h+var_190]
0x180040544  lea     rcx, [rbp+140h+var_D0]
0x180040548  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x18004054d  nop
0x18004054e  lea     rax, [rsp+240h+cbData]
0x180040553  mov     qword ptr [rsp+240h+ulFlags], rax; lpcbData
0x180040558  lea     rax, [rbp+140h+Data]
0x18004055f  mov     [rsp+240h+phkDevice], rax; lpData
0x180040564  xor     r9d, r9d; lpType
0x180040567  xor     r8d, r8d; lpReserved
0x18004056a  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x180040571  mov     rcx, [rsp+240h+hKey]; hKey
0x180040576  call    cs:__imp_RegQueryValueExW
0x18004057c  mov     edi, eax
0x18004057e  test    eax, eax
0x180040580  jz      loc_180040646
0x180040586  jle     short loc_180040591
0x180040588  movzx   edi, ax
0x18004058b  or      edi, 80070000h
0x180040591  mov     [rsp+240h+phkDevice], rsi
0x180040596  lea     r9, aQueryNetcfgins; "Query NetCfgInstanceId failed for devic"...
0x18004059d  mov     r8d, edi; int
0x1800405a0  mov     edx, 21Ch; unsigned int
0x1800405a5  mov     rcx, rbx; char *
0x1800405a8  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800405ad  nop
0x1800405ae  lea     rbx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x1800405b5  mov     [rbp+140h+var_D0], rbx
0x1800405b9  mov     rcx, [rbp+140h+var_90]
0x1800405c0  test    rcx, rcx
0x1800405c3  jnz     short loc_1800405CC
0x1800405c5  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800405cb  int     3; Trap to Debugger
0x1800405cc  mov     rax, [rcx]
0x1800405cf  mov     rax, [rax+10h]
0x1800405d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405d8  mov     rcx, [rbp+140h+var_90]
0x1800405df  test    rcx, rcx
0x1800405e2  jz      short loc_180040601
0x1800405e4  mov     rax, [rcx]
0x1800405e7  lea     rdx, [rbp+140h+var_C8]
0x1800405eb  cmp     rcx, rdx
0x1800405ee  setnz   dl
0x1800405f1  mov     rax, [rax+20h]
0x1800405f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405fa  mov     [rbp+140h+var_90], r12
0x180040601  mov     [rbp+140h+var_130], rbx
0x180040605  mov     rcx, [rbp+140h+var_F0]
0x180040609  test    rcx, rcx
0x18004060c  jnz     short loc_180040615
0x18004060e  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180040614  int     3; Trap to Debugger
0x180040615  mov     rax, [rcx]
0x180040618  mov     rax, [rax+10h]
0x18004061c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040621  mov     rcx, [rbp+140h+var_F0]
0x180040625  test    rcx, rcx
0x180040628  jz      short loc_180040641
0x18004062a  mov     rax, [rcx]
0x18004062d  lea     rdx, [rbp+140h+var_128]
0x180040631  cmp     rcx, rdx
0x180040634  setnz   dl
0x180040637  mov     rax, [rax+20h]
0x18004063b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040640  nop
0x180040641  jmp     loc_1800408E5
0x180040646  lea     r9, [rbp+140h+Data]
0x18004064d  lea     r8, aReceivedNetcfg; "Received NetCfgInstanceId: %S"
0x180040654  mov     edx, 220h; unsigned int
0x180040659  mov     rcx, rbx; char *
0x18004065c  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180040661  lea     rdx, [rbp+140h+pclsid]; pclsid
0x180040665  lea     rcx, [rbp+140h+Data]; lpsz
0x18004066c  call    cs:__imp_CLSIDFromString
0x180040672  mov     edi, eax
0x180040674  test    eax, eax
0x180040676  jns     loc_180040738
0x18004067c  lea     rax, [rbp+140h+Data]
0x180040683  mov     [rsp+240h+phkDevice], rax
0x180040688  lea     r9, aClsidfromstrin; "CLSIDFromString failed for NetCfgInstan"...
0x18004068f  mov     r8d, edi; int
0x180040692  mov     edx, 224h; unsigned int
0x180040697  mov     rcx, rbx; char *
0x18004069a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004069f  nop
0x1800406a0  lea     rbx, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x1800406a7  mov     [rbp+140h+var_D0], rbx
0x1800406ab  mov     rcx, [rbp+140h+var_90]
0x1800406b2  test    rcx, rcx
0x1800406b5  jnz     short loc_1800406BE
0x1800406b7  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800406bd  int     3; Trap to Debugger
0x1800406be  mov     rax, [rcx]
0x1800406c1  mov     rax, [rax+10h]
0x1800406c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406ca  mov     rcx, [rbp+140h+var_90]
0x1800406d1  test    rcx, rcx
0x1800406d4  jz      short loc_1800406F3
0x1800406d6  mov     rax, [rcx]
0x1800406d9  lea     rdx, [rbp+140h+var_C8]
0x1800406dd  cmp     rcx, rdx
0x1800406e0  setnz   dl
0x1800406e3  mov     rax, [rax+20h]
0x1800406e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406ec  mov     [rbp+140h+var_90], r12
0x1800406f3  mov     [rbp+140h+var_130], rbx
0x1800406f7  mov     rcx, [rbp+140h+var_F0]
0x1800406fb  test    rcx, rcx
0x1800406fe  jnz     short loc_180040707
0x180040700  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180040706  int     3; Trap to Debugger
0x180040707  mov     rax, [rcx]
0x18004070a  mov     rax, [rax+10h]
0x18004070e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040713  mov     rcx, [rbp+140h+var_F0]
0x180040717  test    rcx, rcx
0x18004071a  jz      short loc_180040733
0x18004071c  mov     rax, [rcx]
0x18004071f  lea     rdx, [rbp+140h+var_128]
0x180040723  cmp     rcx, rdx
0x180040726  setnz   dl
0x180040729  mov     rax, [rax+20h]
0x18004072d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040732  nop
0x180040733  jmp     loc_1800408E5
0x180040738  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004073f  mov     [rsp+240h+var_1E0], rax
  ... truncated ...
```
