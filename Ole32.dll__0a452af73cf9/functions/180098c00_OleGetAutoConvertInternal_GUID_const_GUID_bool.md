# OleGetAutoConvertInternal(_GUID const &,_GUID *,bool)

- ea: `0x180098c00`
- end: `0x180098dfe`
- name: `?OleGetAutoConvertInternal@@YAJAEBU_GUID@@PEAU1@_N@Z`
- size: `510`
- prototype: `HRESULT __fastcall(const _GUID *clsidOld, _GUID *pClsidNew, bool clsidOld)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003bf9c`
- `0x18004b870`
- `0x18004d258`
- `0x18006110c`
- `0x18007dcf0`
- `0x18007e45c`
- `0x1800990a0`

## callees

- `0x1800185ec`
- `0x18001a3c8`
- `0x18001aafc`
- `0x18001b0e4`
- `0x18001c1d0`
- `0x180098c00`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098dcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098dcf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180098dbe`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180098dbe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180098c75`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180098c75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098de0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098de0`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x180098d66`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x180098d66`

## string_xrefs

- `0x180098d27`: `com\ole32\ole232\stdimpl\olereg.cpp`
- `0x180098d76`: `com\ole32\ole232\stdimpl\olereg.cpp`

## pseudocode

```c
__int64 __fastcall OleGetAutoConvertInternal(const _GUID *clsidOld, _GUID *pClsidNew, bool a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // edx
  HRESULT v9; // eax
  int String; // eax
  IPackagedComClassCatalogInternal *m_ptr; // rdi
  HKEY__ *hkeyClsid; // [rsp+30h] [rbp-20h] BYREF
  wil::com_ptr_t<IComCatalogSCM,wil::err_returncode_policy> comCatalogScm; // [rsp+38h] [rbp-18h] BYREF
  wil::com_ptr_t<IPackagedComClassCatalogInternal,wil::err_returncode_policy> packagedComCatalog; // [rsp+40h] [rbp-10h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  RegistrationSource source; // [rsp+80h] [rbp+30h] BYREF
  wil::com_ptr_t<IRegistration,wil::err_returncode_policy> registrationInfo; // [rsp+88h] [rbp+38h] BYREF

  LOBYTE(source) = a3;
  hkeyClsid = 0;
  packagedComCatalog.m_ptr = 0;
  if ( !IsValidPtrOut(pClsidNew, 0x10u) )
    return 2147942487LL;
  comCatalogScm.m_ptr = 0;
  *pClsidNew = GUID_NULL;
  if ( CoCreateInstance(
         &GUID_00000346_0000_0000_c000_000000000046,
         0,
         1u,
         &GUID_000001fd_0000_0000_c000_000000000046,
         (LPVOID *)&comCatalogScm.m_ptr) < 0 )
    goto LABEL_15;
  registrationInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         clsidOld,
         comCatalogScm.m_ptr,
         &GUID_430be197_0244_2f7b_80fd_c7c473983ad0,
         (void **)&registrationInfo.m_ptr) < 0
    || (source = RegistrationSourceSystemRegistry,
        ((int (__fastcall *)(IRegistration *, RegistrationSource *))registrationInfo.m_ptr->lpVtbl[1].QueryInterface)(
          registrationInfo.m_ptr,
          &source) < 0)
    || source != RegistrationSourcePackagedCom )
  {
    wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&registrationInfo);
LABEL_15:
    v9 = InternalRegOpenClassKey(clsidOld, 131097, &hkeyClsid);
    v7 = v9;
    if ( v9 >= 0 )
    {
      String = OleRegGetString(hkeyClsid, Com::Catalog::Constants::AutoConvertTo, (wchar_t **)&packagedComCatalog);
      m_ptr = packagedComCatalog.m_ptr;
      v7 = String;
      if ( String >= 0 )
      {
        if ( LOWORD(packagedComCatalog.m_ptr->lpVtbl) )
          v7 = CLSIDFromString((LPCOLESTR)packagedComCatalog.m_ptr, pClsidNew);
        else
          v7 = -2147221166;
      }
      if ( hkeyClsid )
      {
        RegCloseKey(hkeyClsid);
        hkeyClsid = 0;
      }
      CoTaskMemFree(m_ptr);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x2F5u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v9);
    }
    goto LABEL_24;
  }
  packagedComCatalog.m_ptr = 0;
  v6 = ((__int64 (__fastcall *)(IComCatalogSCM *, GUID *, wil::com_ptr_t<IPackagedComClassCatalogInternal,wil::err_returncode_policy> *))comCatalogScm.m_ptr->lpVtbl->QueryInterface)(
         comCatalogScm.m_ptr,
         &GUID_84066cce_9a85_496d_9444_12646c933b4a,
         &packagedComCatalog);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(IPackagedComClassCatalogInternal *, const _GUID *, _GUID *))packagedComCatalog.m_ptr->lpVtbl[1].Release)(
           packagedComCatalog.m_ptr,
           clsidOld,
           pClsidNew);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      goto LABEL_13;
    }
    v8 = 751;
  }
  else
  {
    v8 = 749;
  }
  wil::details::in1diag3::Return_Hr(retaddr, v8, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v6);
LABEL_13:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&packagedComCatalog);
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&registrationInfo);
LABEL_24:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&comCatalogScm);
  return v7;
}

```

## disassembly

```asm
0x180098c00  mov     [rsp-18h+arg_0], rbx
0x180098c05  mov     byte ptr [rsp-18h+source], r8b
0x180098c0a  push    rbp
0x180098c0b  push    rsi
0x180098c0c  push    rdi
0x180098c0d  mov     rbp, rsp
0x180098c10  sub     rsp, 50h
0x180098c14  mov     rsi, pClsidNew
0x180098c17  mov     [rbp+hkeyClsid], 0
0x180098c1f  mov     rdi, clsidOld
0x180098c22  mov     [rbp+packagedComCatalog.m_ptr], 0
0x180098c2a  mov     clsidOld, rsi; pv
0x180098c2d  mov     edx, 10h; cb
0x180098c32  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x180098c37  test    eax, eax
0x180098c39  jnz     short loc_180098C45
0x180098c3b  mov     eax, 80070057h
0x180098c40  jmp     loc_180098DF1
0x180098c45  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180098c4c  xor     edx, edx; pUnkOuter
0x180098c4e  mov     [rbp+comCatalogScm.m_ptr], 0
0x180098c56  lea     rax, [rbp+comCatalogScm]
0x180098c5a  lea     r9, _GUID_000001fd_0000_0000_c000_000000000046; riid
0x180098c61  mov     [rsp+50h+ppv], rax; ppv
0x180098c66  lea     clsidOld, _GUID_00000346_0000_0000_c000_000000000046; rclsid
0x180098c6d  lea     r8d, [pClsidNew+1]; dwClsContext
0x180098c71  movdqu  xmmword ptr [rsi], xmm0
0x180098c75  call    cs:__imp_CoCreateInstance
0x180098c7b  test    eax, eax
0x180098c7d  js      loc_180098D5A
0x180098c83  mov     pClsidNew, [rbp+comCatalogScm.m_ptr]; pComCatalog
0x180098c87  lea     r9, [rbp+registrationInfo]; ppv
0x180098c8b  lea     r8, _GUID_430be197_0244_2f7b_80fd_c7c473983ad0; riid
0x180098c92  mov     [rbp+registrationInfo.m_ptr], 0
0x180098c9a  mov     clsidOld, rdi; clsid
0x180098c9d  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x180098ca2  test    eax, eax
0x180098ca4  js      loc_180098D51
0x180098caa  mov     clsidOld, [rbp+registrationInfo.m_ptr]
0x180098cae  lea     pClsidNew, [rbp+source]
0x180098cb2  mov     [rbp+source], 0
0x180098cb9  mov     rax, [clsidOld]
0x180098cbc  mov     rax, [rax+18h]
0x180098cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cc5  test    eax, eax
0x180098cc7  js      loc_180098D51
0x180098ccd  cmp     [rbp+source], 2
0x180098cd1  jnz     short loc_180098D51
0x180098cd3  mov     clsidOld, [rbp+comCatalogScm.m_ptr]
0x180098cd7  lea     r8, [rbp+packagedComCatalog]
0x180098cdb  mov     [rbp+packagedComCatalog.m_ptr], 0
0x180098ce3  lea     pClsidNew, _GUID_84066cce_9a85_496d_9444_12646c933b4a
0x180098cea  mov     rax, [clsidOld]
0x180098ced  mov     rax, [rax]
0x180098cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cf5  mov     ebx, eax
0x180098cf7  test    eax, eax
0x180098cf9  jns     short loc_180098D02
0x180098cfb  mov     edx, 2EDh
0x180098d00  jmp     short loc_180098D23
0x180098d02  mov     clsidOld, [rbp+packagedComCatalog.m_ptr]
0x180098d06  mov     r8, rsi
0x180098d09  mov     pClsidNew, rdi
0x180098d0c  mov     rax, [clsidOld]
0x180098d0f  mov     rax, [rax+28h]
0x180098d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d18  mov     ebx, eax
0x180098d1a  test    eax, eax
0x180098d1c  jns     short loc_180098D38
0x180098d1e  mov     edx, 2EFh; lineNumber
0x180098d23  mov     clsidOld, [rbp+18h]; callerReturnAddress
0x180098d27  lea     r8, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x180098d2e  mov     r9d, eax; hr
0x180098d31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098d36  jmp     short loc_180098D3A
0x180098d38  xor     ebx, ebx
0x180098d3a  lea     clsidOld, [rbp+packagedComCatalog]; this
0x180098d3e  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180098d43  lea     clsidOld, [rbp+registrationInfo]; this
0x180098d47  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180098d4c  jmp     loc_180098DE6
0x180098d51  lea     clsidOld, [rbp+registrationInfo]; this
0x180098d55  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180098d5a  lea     r8, [rbp+hkeyClsid]
0x180098d5e  mov     edx, 20019h
0x180098d63  mov     clsidOld, rdi
0x180098d66  call    cs:__imp_InternalRegOpenClassKey
0x180098d6c  mov     ebx, eax
0x180098d6e  test    eax, eax
0x180098d70  jns     short loc_180098D8C
0x180098d72  mov     clsidOld, [rbp+18h]; callerReturnAddress
0x180098d76  lea     r8, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x180098d7d  mov     r9d, eax; hr
0x180098d80  mov     edx, 2F5h; lineNumber
0x180098d85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098d8a  jmp     short loc_180098DE6
0x180098d8c  mov     clsidOld, [rbp+hkeyClsid]; hkey
0x180098d90  lea     r8, [rbp+packagedComCatalog]; ppszValue
0x180098d94  lea     pClsidNew, ?AutoConvertTo@Constants@Catalog@Com@@3QBGB; szKey
0x180098d9b  call    OleRegGetString
0x180098da0  mov     rdi, [rbp+packagedComCatalog.m_ptr]
0x180098da4  mov     ebx, eax
0x180098da6  test    eax, eax
0x180098da8  js      short loc_180098DC6
0x180098daa  xor     eax, eax
0x180098dac  cmp     ax, [rdi]
0x180098daf  jnz     short loc_180098DB8
0x180098db1  mov     ebx, 80040152h
0x180098db6  jmp     short loc_180098DC6
0x180098db8  mov     pClsidNew, rsi; pclsid
0x180098dbb  mov     clsidOld, rdi; lpsz
0x180098dbe  call    cs:__imp_CLSIDFromString
0x180098dc4  mov     ebx, eax
0x180098dc6  mov     clsidOld, [rbp+hkeyClsid]; hKey
0x180098dca  test    clsidOld, clsidOld
0x180098dcd  jz      short loc_180098DDD
0x180098dcf  call    cs:__imp_RegCloseKey
0x180098dd5  mov     [rbp+hkeyClsid], 0
0x180098ddd  mov     clsidOld, rdi; pv
0x180098de0  call    cs:__imp_CoTaskMemFree
0x180098de6  lea     clsidOld, [rbp+comCatalogScm]; this
0x180098dea  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x180098def  mov     eax, ebx
0x180098df1  mov     rbx, [rsp+50h+arg_0]
0x180098df6  add     rsp, 50h
0x180098dfa  pop     rdi
0x180098dfb  pop     rsi
0x180098dfc  pop     rbp
0x180098dfd  retn
```
