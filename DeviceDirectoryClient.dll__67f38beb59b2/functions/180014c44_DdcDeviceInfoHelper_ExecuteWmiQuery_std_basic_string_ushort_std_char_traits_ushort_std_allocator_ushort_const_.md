# DdcDeviceInfoHelper::ExecuteWmiQuery(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IEnumWbemClassObject * *)

- ea: `0x180014c44`
- end: `0x180015054`
- name: `?ExecuteWmiQuery@DdcDeviceInfoHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAPEAUIEnumWbemClassObject@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(int, int, IUnknown **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015a4c`

## callees

- `0x1800028d4`
- `0x180004060`
- `0x180004d5c`
- `0x1800050b8`
- `0x180014624`
- `0x180014c44`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180014dcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f20`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180014dcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f20`
- `OLEAUT32!__imp_SysFreeString` at `0x180014f6f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014e4a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014fe4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014e4a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014fe4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014d0a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014d0a`

## string_xrefs

- `0x180014ca2`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180014d23`: `CHR(CoCreateInstance( CLSID_WbemLocator, nullptr, CLSCTX_INPROC_SERVER, __uuidof(IWbemLocator), (LPVOID*)pWbemLocator.ReleaseAndGetAddressOf()))`
- `0x180014e08`: `CHR(pWbemLocator->ConnectServer( _bstr_t(wstrServer.c_str()), nullptr, nullptr, 0, 0, nullptr, nullptr, pWbemServices.ReleaseAndGetAddressOf()))`
- `0x180014e63`: `CHR(CoSetProxyBlanket( pWbemServices.Get(), 0xFFFFFFFFL, 0xffffffff, ( ( OLECHAR * )( INT_PTR )-1 ), 0, 3, ( ( void * )( INT_PTR )-1 ), EOAC_DEFAULT))`
- `0x180014fa4`: `CHR(pWbemServices->ExecQuery( _bstr_t(L"WQL"), _bstr_t(wstrQuery.c_str()), WBEM_FLAG_RETURN_IMMEDIATELY | WBEM_FLAG_FORWARD_ONLY, nullptr, pEnumerator.ReleaseAndGetAddressOf()))`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::ExecuteWmiQuery(int a1, int a2, IUnknown **a3)
{
  int v4; // r8d
  HRESULT v5; // ebx
  LPVOID v6; // rbx
  __int64 (__fastcall *v7)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **); // r14
  const unsigned __int16 *v8; // rax
  _bstr_t *v9; // rax
  __int64 v10; // rdx
  BSTR *v11; // rdi
  BSTR v12; // rcx
  IUnknown *v13; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // r14
  const unsigned __int16 *v15; // rax
  _bstr_t *v16; // rax
  __int64 v17; // rbx
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  BSTR *v20; // rdi
  BSTR v21; // rcx
  BSTR *v22; // rdi
  BSTR v23; // rcx
  IUnknown *v24; // rax
  char ppv; // [rsp+20h] [rbp-50h]
  const char *dwImpLevel; // [rsp+28h] [rbp-48h]
  IUnknown *pProxy; // [rsp+50h] [rbp-20h] BYREF
  LPVOID v29; // [rsp+58h] [rbp-18h] BYREF
  void *Block; // [rsp+60h] [rbp-10h] BYREF
  void *v31; // [rsp+68h] [rbp-8h] BYREF
  IUnknown *v32; // [rsp+C8h] [rbp+58h] BYREF

  v29 = 0;
  pProxy = 0;
  v32 = 0;
  if ( !a3 )
  {
    v4 = -2147024809;
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      dwImpLevel = "CPR(ppEnumerator)";
      ppv = -76;
LABEL_4:
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        v4,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        ppv,
        dwImpLevel);
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  if ( *a3 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        181,
        "CBR(*ppEnumerator == nullptr)");
    goto LABEL_60;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v5 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &v29);
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_60;
    dwImpLevel = "CHR(CoCreateInstance( CLSID_WbemLocator, nullptr, CLSCTX_INPROC_SERVER, __uuidof(IWbemLocator), (LPVOID"
                 "*)pWbemLocator.ReleaseAndGetAddressOf()))";
    ppv = -67;
LABEL_12:
    v4 = v5;
    goto LABEL_4;
  }
  v6 = v29;
  v7 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)v29 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v9 = _bstr_t::_bstr_t((_bstr_t *)&Block, v8);
  if ( *(_QWORD *)v9 )
    v10 = **(_QWORD **)v9;
  else
    v10 = 0;
  v5 = v7(v6, v10, 0, 0, 0, 0, 0, 0, &pProxy);
  v11 = (BSTR *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v11 )
  {
    if ( *v11 )
    {
      SysFreeString(*v11);
      *v11 = 0;
    }
    v12 = v11[1];
    if ( v12 )
    {
      operator delete(v12);
      v11[1] = 0;
    }
    operator delete(v11);
  }
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_60;
    dwImpLevel = "CHR(pWbemLocator->ConnectServer( _bstr_t(wstrServer.c_str()), nullptr, nullptr, 0, 0, nullptr, nullptr,"
                 " pWbemServices.ReleaseAndGetAddressOf()))";
    ppv = -57;
    goto LABEL_12;
  }
  v5 = CoSetProxyBlanket(
         pProxy,
         0xFFFFFFFF,
         0xFFFFFFFF,
         (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
         0,
         3u,
         (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
         0x800u);
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_60;
    dwImpLevel = "CHR(CoSetProxyBlanket( pWbemServices.Get(), 0xFFFFFFFFL, 0xffffffff, ( ( OLECHAR * )( INT_PTR )-1 ), 0,"
                 " 3, ( ( void * )( INT_PTR )-1 ), EOAC_DEFAULT))";
    ppv = -46;
    goto LABEL_12;
  }
  v13 = pProxy;
  Release = pProxy->lpVtbl[6].Release;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v16 = _bstr_t::_bstr_t((_bstr_t *)&v31, v15);
  if ( *(_QWORD *)v16 )
    v17 = **(_QWORD **)v16;
  else
    v17 = 0;
  v18 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"WQL");
  if ( *(_QWORD *)v18 )
    v19 = **(_QWORD **)v18;
  else
    v19 = 0;
  v5 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64, _QWORD, IUnknown **))Release)(
         v13,
         v19,
         v17,
         48,
         0,
         &v32);
  v20 = (BSTR *)Block;
  if ( Block )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v20 )
    {
      if ( *v20 )
      {
        SysFreeString(*v20);
        *v20 = 0;
      }
      v21 = v20[1];
      if ( v21 )
      {
        operator delete(v21);
        v20[1] = 0;
      }
      operator delete(v20);
    }
    Block = 0;
  }
  v22 = (BSTR *)v31;
  if ( v31 && _InterlockedExchangeAdd((volatile signed __int32 *)v31 + 4, 0xFFFFFFFF) == 1 && v22 )
  {
    if ( *v22 )
    {
      SysFreeString(*v22);
      *v22 = 0;
    }
    v23 = v22[1];
    if ( v23 )
    {
      operator delete(v23);
      v22[1] = 0;
    }
    operator delete(v22);
  }
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_60;
    dwImpLevel = "CHR(pWbemServices->ExecQuery( _bstr_t(L\"WQL\"), _bstr_t(wstrQuery.c_str()), WBEM_FLAG_RETURN_IMMEDIATE"
                 "LY | WBEM_FLAG_FORWARD_ONLY, nullptr, pEnumerator.ReleaseAndGetAddressOf()))";
    ppv = -39;
    goto LABEL_12;
  }
  v5 = CoSetProxyBlanket(
         v32,
         0xFFFFFFFF,
         0xFFFFFFFF,
         (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
         0,
         3u,
         (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
         0x800u);
  if ( v5 >= 0 )
  {
    v24 = v32;
    v32 = 0;
    *a3 = v24;
    goto LABEL_60;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    dwImpLevel = "CHR(CoSetProxyBlanket( pEnumerator.Get(), 0xFFFFFFFFL, 0xffffffff, ( ( OLECHAR * )( INT_PTR )-1 ), 0, 3"
                 ", ( ( void * )( INT_PTR )-1 ), EOAC_DEFAULT))";
    ppv = -29;
    goto LABEL_12;
  }
LABEL_60:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014c44  mov     [rsp-38h+arg_0], rbx
0x180014c49  push    rbp
0x180014c4a  push    rsi
0x180014c4b  push    rdi
0x180014c4c  push    r12
0x180014c4e  push    r13
0x180014c50  push    r14
0x180014c52  push    r15
0x180014c54  mov     rbp, rsp
0x180014c57  sub     rsp, 70h
0x180014c5b  mov     rsi, r8
0x180014c5e  mov     rdi, rdx
0x180014c61  mov     r15, rcx
0x180014c64  xor     r12d, r12d
0x180014c67  mov     [rbp+var_18], r12
0x180014c6b  mov     [rbp+pProxy], r12
0x180014c6f  mov     [rbp+arg_18], r12
0x180014c73  test    r8, r8
0x180014c76  jnz     short loc_180014CB3
0x180014c78  mov     r8d, 80070057h
0x180014c7e  mov     ebx, r8d
0x180014c81  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014c88  jz      loc_18001501D
0x180014c8e  lea     rax, aCprPpenumerato; "CPR(ppEnumerator)"
0x180014c95  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180014c9a  mov     dword ptr [rsp+70h+ppv], 4B4h
0x180014ca2  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180014ca9  call    McTemplateU0dsqs_EventWriteTransfer
0x180014cae  jmp     loc_18001501D
0x180014cb3  cmp     [r8], r12
0x180014cb6  jz      short loc_180014CE4
0x180014cb8  mov     r8d, 80070057h
0x180014cbe  mov     ebx, r8d
0x180014cc1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014cc8  jz      loc_18001501D
0x180014cce  lea     rax, aCbrPpenumerato; "CBR(*ppEnumerator == nullptr)"
0x180014cd5  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180014cda  mov     dword ptr [rsp+70h+ppv], 4B5h
0x180014ce2  jmp     short loc_180014CA2
0x180014ce4  lea     rcx, [rbp+var_18]
0x180014ce8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014ced  lea     rax, [rbp+var_18]
0x180014cf1  mov     [rsp+70h+ppv], rax; ppv
0x180014cf6  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x180014cfd  xor     edx, edx; pUnkOuter
0x180014cff  lea     r8d, [rdx+1]; dwClsContext
0x180014d03  lea     rcx, CLSID_WbemLocator; rclsid
0x180014d0a  call    cs:__imp_CoCreateInstance
0x180014d10  mov     ebx, eax
0x180014d12  test    eax, eax
0x180014d14  jns     short loc_180014D3F
0x180014d16  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014d1d  jz      loc_18001501D
0x180014d23  lea     rax, aChrCocreateins_6; "CHR(CoCreateInstance( CLSID_WbemLocator"...
0x180014d2a  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180014d2f  mov     dword ptr [rsp+70h+ppv], 4BDh
0x180014d37  mov     r8d, ebx
0x180014d3a  jmp     loc_180014CA2
0x180014d3f  mov     rbx, [rbp+var_18]
0x180014d43  mov     rax, [rbx]
0x180014d46  mov     r14, [rax+18h]
0x180014d4a  lea     rcx, [rbp+pProxy]
0x180014d4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014d53  mov     rcx, rdi
0x180014d56  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014d5b  mov     rdx, rax; unsigned __int16 *
0x180014d5e  lea     rcx, [rbp+Block]; this
0x180014d62  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180014d67  nop
0x180014d68  mov     rdx, [rax]
0x180014d6b  test    rdx, rdx
0x180014d6e  jz      short loc_180014D75
0x180014d70  mov     rdx, [rdx]
0x180014d73  jmp     short loc_180014D78
0x180014d75  mov     rdx, r12
0x180014d78  lea     rax, [rbp+pProxy]
0x180014d7c  mov     [rsp+70h+var_30], rax
0x180014d81  mov     qword ptr [rsp+70h+dwCapabilities], r12
0x180014d86  mov     [rsp+70h+pAuthInfo], r12
0x180014d8b  mov     [rsp+70h+dwImpLevel], r12d
0x180014d90  mov     [rsp+70h+ppv], r12
0x180014d95  xor     r9d, r9d
0x180014d98  xor     r8d, r8d
0x180014d9b  mov     rcx, rbx
0x180014d9e  mov     rax, r14
0x180014da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014da6  mov     ebx, eax
0x180014da8  or      r13, 0FFFFFFFFFFFFFFFFh
0x180014dac  mov     rdi, [rbp+Block]
0x180014db0  test    rdi, rdi
0x180014db3  jz      short loc_180014DF7
0x180014db5  mov     eax, r13d
0x180014db8  lock xadd [rdi+10h], eax
0x180014dbd  add     eax, r13d
0x180014dc0  jnz     short loc_180014DF7
0x180014dc2  test    rdi, rdi
0x180014dc5  jz      short loc_180014DF7
0x180014dc7  mov     rcx, [rdi]; bstrString
0x180014dca  test    rcx, rcx
0x180014dcd  jz      short loc_180014DD8
0x180014dcf  call    cs:__imp_SysFreeString
0x180014dd5  mov     [rdi], r12
0x180014dd8  mov     rcx, [rdi+8]; Block
0x180014ddc  test    rcx, rcx
0x180014ddf  jz      short loc_180014DEA
0x180014de1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014de6  mov     [rdi+8], r12
0x180014dea  mov     edx, 18h
0x180014def  mov     rcx, rdi; Block
0x180014df2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014df7  test    ebx, ebx
0x180014df9  jns     short loc_180014E21
0x180014dfb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014e02  jz      loc_18001501D
0x180014e08  lea     rax, aChrPwbemlocato; "CHR(pWbemLocator->ConnectServer( _bstr_"...
0x180014e0f  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180014e14  mov     dword ptr [rsp+70h+ppv], 4C7h
0x180014e1c  jmp     loc_180014D37
0x180014e21  mov     [rsp+70h+dwCapabilities], 800h; dwCapabilities
0x180014e29  mov     [rsp+70h+pAuthInfo], r13; pAuthInfo
0x180014e2e  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x180014e36  mov     dword ptr [rsp+70h+ppv], r12d; dwAuthnLevel
0x180014e3b  mov     r9, r13; pServerPrincName
0x180014e3e  or      eax, 0FFFFFFFFh
0x180014e41  mov     r8d, eax; dwAuthzSvc
0x180014e44  mov     edx, eax; dwAuthnSvc
0x180014e46  mov     rcx, [rbp+pProxy]; pProxy
0x180014e4a  call    cs:__imp_CoSetProxyBlanket
0x180014e50  mov     ebx, eax
0x180014e52  test    eax, eax
0x180014e54  jns     short loc_180014E7C
0x180014e56  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014e5d  jz      loc_18001501D
0x180014e63  lea     rax, aChrCosetproxyb_1; "CHR(CoSetProxyBlanket( pWbemServices.Ge"...
0x180014e6a  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180014e6f  mov     dword ptr [rsp+70h+ppv], 4D2h
0x180014e77  jmp     loc_180014D37
0x180014e7c  mov     rdi, [rbp+pProxy]
0x180014e80  mov     rax, [rdi]
0x180014e83  mov     r14, [rax+0A0h]
0x180014e8a  lea     rcx, [rbp+arg_18]
0x180014e8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014e93  mov     rcx, r15
0x180014e96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014e9b  mov     rdx, rax; unsigned __int16 *
0x180014e9e  lea     rcx, [rbp+var_8]; this
0x180014ea2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180014ea7  nop
0x180014ea8  mov     rbx, [rax]
0x180014eab  test    rbx, rbx
0x180014eae  jz      short loc_180014EB5
0x180014eb0  mov     rbx, [rbx]
0x180014eb3  jmp     short loc_180014EB8
0x180014eb5  mov     rbx, r12
0x180014eb8  lea     rdx, aWql; "WQL"
0x180014ebf  lea     rcx, [rbp+Block]; this
0x180014ec3  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180014ec8  nop
0x180014ec9  mov     rcx, [rax]
0x180014ecc  test    rcx, rcx
0x180014ecf  jz      short loc_180014ED6
0x180014ed1  mov     rdx, [rcx]
0x180014ed4  jmp     short loc_180014ED9
0x180014ed6  mov     rdx, r12
0x180014ed9  lea     rax, [rbp+arg_18]
0x180014edd  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180014ee2  mov     [rsp+70h+ppv], r12
0x180014ee7  mov     r9d, 30h ; '0'
0x180014eed  mov     r8, rbx
0x180014ef0  mov     rcx, rdi
0x180014ef3  mov     rax, r14
0x180014ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014efb  mov     ebx, eax
0x180014efd  mov     rdi, [rbp+Block]
0x180014f01  test    rdi, rdi
0x180014f04  jz      short loc_180014F4C
0x180014f06  mov     eax, r13d
0x180014f09  lock xadd [rdi+10h], eax
0x180014f0e  add     eax, r13d
0x180014f11  jnz     short loc_180014F48
0x180014f13  test    rdi, rdi
0x180014f16  jz      short loc_180014F48
0x180014f18  mov     rcx, [rdi]; bstrString
0x180014f1b  test    rcx, rcx
0x180014f1e  jz      short loc_180014F29
0x180014f20  call    cs:__imp_SysFreeString
0x180014f26  mov     [rdi], r12
0x180014f29  mov     rcx, [rdi+8]; Block
0x180014f2d  test    rcx, rcx
0x180014f30  jz      short loc_180014F3B
0x180014f32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014f37  mov     [rdi+8], r12
0x180014f3b  mov     edx, 18h
0x180014f40  mov     rcx, rdi; Block
0x180014f43  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014f48  mov     [rbp+Block], r12
0x180014f4c  mov     rdi, [rbp+var_8]
0x180014f50  test    rdi, rdi
0x180014f53  jz      short loc_180014F97
0x180014f55  mov     eax, r13d
0x180014f58  lock xadd [rdi+10h], eax
0x180014f5d  add     eax, r13d
0x180014f60  jnz     short loc_180014F97
0x180014f62  test    rdi, rdi
0x180014f65  jz      short loc_180014F97
0x180014f67  mov     rcx, [rdi]; bstrString
0x180014f6a  test    rcx, rcx
0x180014f6d  jz      short loc_180014F78
0x180014f6f  call    cs:__imp_SysFreeString
0x180014f75  mov     [rdi], r12
0x180014f78  mov     rcx, [rdi+8]; Block
0x180014f7c  test    rcx, rcx
0x180014f7f  jz      short loc_180014F8A
0x180014f81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014f86  mov     [rdi+8], r12
0x180014f8a  mov     edx, 18h
0x180014f8f  mov     rcx, rdi; Block
0x180014f92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014f97  test    ebx, ebx
0x180014f99  jns     short loc_180014FBD
0x180014f9b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014fa2  jz      short loc_18001501D
0x180014fa4  lea     rax, aChrPwbemservic; "CHR(pWbemServices->ExecQuery( _bstr_t(L"...
0x180014fab  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180014fb0  mov     dword ptr [rsp+70h+ppv], 4D9h
0x180014fb8  jmp     loc_180014D37
0x180014fbd  mov     [rsp+70h+dwCapabilities], 800h; dwCapabilities
0x180014fc5  mov     [rsp+70h+pAuthInfo], r13; pAuthInfo
0x180014fca  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x180014fd2  mov     dword ptr [rsp+70h+ppv], r12d; dwAuthnLevel
0x180014fd7  mov     r9, r13; pServerPrincName
0x180014fda  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180014fdd  mov     r8d, edx; dwAuthzSvc
0x180014fe0  mov     rcx, [rbp+arg_18]; pProxy
0x180014fe4  call    cs:__imp_CoSetProxyBlanket
0x180014fea  mov     ebx, eax
0x180014fec  test    eax, eax
0x180014fee  jns     short loc_180015012
0x180014ff0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180014ff7  jz      short loc_18001501D
0x180014ff9  lea     rax, aChrCosetproxyb_0; "CHR(CoSetProxyBlanket( pEnumerator.Get("...
0x180015000  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x180015005  mov     dword ptr [rsp+70h+ppv], 4E3h
0x18001500d  jmp     loc_180014D37
0x180015012  mov     rax, [rbp+arg_18]
0x180015016  mov     [rbp+arg_18], r12
0x18001501a  mov     [rsi], rax
0x18001501d  lea     rcx, [rbp+arg_18]
0x180015021  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015026  nop
0x180015027  lea     rcx, [rbp+pProxy]
0x18001502b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015030  nop
0x180015031  lea     rcx, [rbp+var_18]
0x180015035  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001503a  mov     eax, ebx
0x18001503c  mov     rbx, [rsp+70h+arg_0]
0x180015044  add     rsp, 70h
0x180015048  pop     r15
0x18001504a  pop     r14
0x18001504c  pop     r13
0x18001504e  pop     r12
0x180015050  pop     rdi
0x180015051  pop     rsi
0x180015052  pop     rbp
0x180015053  retn
```
