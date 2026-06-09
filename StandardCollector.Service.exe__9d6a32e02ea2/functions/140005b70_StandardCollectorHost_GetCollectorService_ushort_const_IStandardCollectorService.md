# StandardCollectorHost::GetCollectorService(ushort const *,IStandardCollectorService * *)

- ea: `0x140005b70`
- end: `0x140006364`
- name: `?GetCollectorService@StandardCollectorHost@@UEAAJPEBGPEAPEAUIStandardCollectorService@@@Z`
- size: `2036`
- prototype: `__int64 __fastcall(StandardCollectorHost *this, const unsigned __int16 *, struct IStandardCollectorService **)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x140002e74`
- `0x1400043a0`
- `0x140005b70`
- `0x14000697c`
- `0x140006d10`
- `0x140006dc0`
- `0x14000792c`
- `0x14000a278`
- `0x14000ec38`
- `0x14000f098`
- `0x1400108a8`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x140005d15`
- `VCRUNTIME140!wcsrchr` at `0x140005d15`
- `KERNEL32!CreateThreadpoolTimer` at `0x140005c7e`
- `KERNEL32!CreateThreadpoolTimer` at `0x140005c7e`
- `KERNEL32!GetProcAddress` at `0x140006005`
- `KERNEL32!GetProcAddress` at `0x140006005`
- `KERNEL32!LeaveCriticalSection` at `0x140006262`
- `KERNEL32!LeaveCriticalSection` at `0x140006312`
- `KERNEL32!LeaveCriticalSection` at `0x140006262`
- `KERNEL32!LeaveCriticalSection` at `0x140006312`
- `KERNEL32!EnterCriticalSection` at `0x140005bdb`
- `KERNEL32!EnterCriticalSection` at `0x140005bdb`
- `KERNEL32!LoadLibraryExW` at `0x140005fa4`
- `KERNEL32!LoadLibraryExW` at `0x140005fa4`
- `KERNEL32!GetLastError` at `0x140005c90`
- `KERNEL32!GetLastError` at `0x140005faf`
- `KERNEL32!GetLastError` at `0x140005c90`
- `KERNEL32!GetLastError` at `0x140005faf`
- `OLEAUT32!__imp_SysAllocString` at `0x140005bb8`
- `OLEAUT32!__imp_SysAllocString` at `0x140005d8f`
- `OLEAUT32!__imp_SysAllocString` at `0x140005bb8`
- `OLEAUT32!__imp_SysAllocString` at `0x140005d8f`
- `OLEAUT32!__imp_SysFreeString` at `0x140005d69`
- `OLEAUT32!__imp_SysFreeString` at `0x140005d72`
- `OLEAUT32!__imp_SysFreeString` at `0x140005d86`
- `OLEAUT32!__imp_SysFreeString` at `0x140005dfa`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e04`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e27`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e33`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e6c`
- `OLEAUT32!__imp_SysFreeString` at `0x140005ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x140005eed`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fe3`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fed`
- `OLEAUT32!__imp_SysFreeString` at `0x14000624e`
- `OLEAUT32!__imp_SysFreeString` at `0x140006258`
- `OLEAUT32!__imp_SysFreeString` at `0x14000626e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400062ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1400062fa`
- `OLEAUT32!__imp_SysFreeString` at `0x14000631c`
- `OLEAUT32!__imp_SysFreeString` at `0x140005d69`
- `OLEAUT32!__imp_SysFreeString` at `0x140005d72`
- `OLEAUT32!__imp_SysFreeString` at `0x140005d86`
- `OLEAUT32!__imp_SysFreeString` at `0x140005dfa`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e04`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e27`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e33`
- `OLEAUT32!__imp_SysFreeString` at `0x140005e6c`
- `OLEAUT32!__imp_SysFreeString` at `0x140005ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x140005eed`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fe3`
- `OLEAUT32!__imp_SysFreeString` at `0x140005fed`
- `OLEAUT32!__imp_SysFreeString` at `0x14000624e`
- `OLEAUT32!__imp_SysFreeString` at `0x140006258`
- `OLEAUT32!__imp_SysFreeString` at `0x14000626e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400062ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1400062fa`
- `OLEAUT32!__imp_SysFreeString` at `0x14000631c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140005dc8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140005e7e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140005dc8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140005e7e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140005dd3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140005e89`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140005dd3`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140005e89`

## string_xrefs

- `0x140005c3b`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Service\StandardCollectorHost.cpp`
- `0x140005f84`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Service\StandardCollectorHost.cpp`
- `0x140005f0f`: `\DiagnosticsHub.StandardCollector.Runtime.dll`
- `0x140005ffb`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall StandardCollectorHost::GetCollectorService(
        StandardCollectorHost *this,
        const unsigned __int16 *a2,
        struct IStandardCollectorService **a3)
{
  BSTR v5; // r14
  struct _RTL_CRITICAL_SECTION *v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  unsigned __int16 **v10; // r8
  signed int v11; // ebx
  signed int LastError; // eax
  CHAR *v13; // rbx
  int ModulePath; // edi
  wchar_t *v15; // rax
  const OLECHAR *v16; // rsi
  OLECHAR *v17; // rcx
  OLECHAR *v18; // rdi
  UINT v19; // eax
  UINT v20; // eax
  int v21; // esi
  OLECHAR *v22; // rcx
  __int64 v23; // rdi
  DiagHubCommon::LogStream *v24; // r13
  __int64 v25; // rax
  WCHAR *v26; // rsi
  HMODULE Library; // rax
  signed int v28; // eax
  signed int v29; // r13d
  FARPROC ProcAddress; // rax
  int v31; // eax
  _QWORD *v32; // rcx
  int v33; // eax
  int v34; // eax
  __int64 (*v35)(void); // rax
  unsigned int v36; // r14d
  BSTR v38; // [rsp+30h] [rbp-D8h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-D0h] BYREF
  BSTR v40; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v41[4]; // [rsp+48h] [rbp-C0h] BYREF
  struct _RTL_CRITICAL_SECTION *v42; // [rsp+68h] [rbp-A0h]
  __int64 (***v43)(void); // [rsp+80h] [rbp-88h] BYREF
  _QWORD *v44; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v45; // [rsp+90h] [rbp-78h] BYREF
  wchar_t *Str[2]; // [rsp+98h] [rbp-70h] BYREF
  OLECHAR *psz[2]; // [rsp+A8h] [rbp-60h]
  wchar_t *v48; // [rsp+B8h] [rbp-50h]

  v41[3] = a3;
  if ( !a2 || !a3 )
    return 2147500035LL;
  v5 = SysAllocString(a2);
  v40 = v5;
  if ( !v5 )
    ATL::AtlThrowImpl(-2147024882);
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  v42 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v41[2] = (char *)this + 88;
  v8 = std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(
         v7,
         &v40);
  v9 = *(_QWORD *)(std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(
                     (char *)this + 88,
                     v41,
                     &v40,
                     v8)
                 + 8);
  if ( !v9 )
    v9 = *((_QWORD *)this + 12);
  if ( v9 != *((_QWORD *)this + 12) )
  {
    if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Service\\StandardCollectorHost.cpp",
        L"Returning runtime version '%s'",
        v5);
    v11 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IStandardCollectorService **))(v9 + 24))(
            *(_QWORD *)(v9 + 24),
            &GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44,
            a3);
    goto LABEL_103;
  }
  if ( !qword_140024848 )
  {
    qword_140024848 = (__int64)CreateThreadpoolTimer(
                                 anonymous_namespace_::ServiceLifetimeManager::HostShutdownMain,
                                 0,
                                 0);
    if ( !qword_140024848 )
    {
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v11 = LastError;
      if ( v11 < 0 )
      {
        _mm_lfence();
LABEL_103:
        LeaveCriticalSection(v6);
        SysFreeString(v5);
        return (unsigned int)v11;
      }
    }
  }
  v13 = 0;
  bstrString = 0;
  v38 = 0;
  if ( *v5 != 35 || v5[1] )
  {
    v11 = DiagHubCommon::DetermineVsInstanceRoot((DiagHubCommon *)v5, (const unsigned __int16 *)&bstrString, v10);
    if ( v11 < 0 )
    {
      _mm_lfence();
      SysFreeString(0);
      SysFreeString(bstrString);
      goto LABEL_103;
    }
    v13 = (CHAR *)bstrString;
    if ( bstrString )
    {
      v20 = SysStringByteLen(bstrString);
      v38 = SysAllocStringByteLen(v13, v20);
      if ( !v38 )
      {
        _mm_lfence();
        goto LABEL_32;
      }
    }
    else
    {
      v38 = 0;
    }
    ModulePath = ATL::CComBSTR::Append((ATL::CComBSTR *)&v38, L"\\Team Tools\\DiagnosticsHub\\Collector");
    if ( ModulePath < 0 )
    {
      _mm_lfence();
      SysFreeString(v38);
      v17 = (OLECHAR *)v13;
      goto LABEL_24;
    }
    v18 = v38;
    goto LABEL_42;
  }
  *(_OWORD *)Str = 0;
  *(_OWORD *)psz = 0;
  v48 = 0;
  ModulePath = DiagHubCommon::ModulePath::GetModulePath(0);
  if ( ModulePath < 0
    || ((v15 = wcsrchr(Str[0], 0x5Cu)) != 0
      ? (const OLECHAR *)(*v15 = 0, v16 = Str[0], psz[1] = Str[0], v48 = v15 + 1, ModulePath = 0)
      : (ModulePath = -2147024735, v16 = psz[1]),
        ModulePath < 0) )
  {
    _mm_lfence();
    std::vector<unsigned short>::~vector<unsigned short>(Str);
    SysFreeString(0);
    v17 = 0;
LABEL_24:
    SysFreeString(v17);
    v11 = ModulePath;
    goto LABEL_103;
  }
  if ( v16 )
  {
    SysFreeString(0);
    v13 = (CHAR *)SysAllocString(v16);
    bstrString = (BSTR)v13;
    if ( !v13 )
      ATL::AtlThrowImpl(-2147024882);
  }
  if ( v13 )
  {
    v19 = SysStringByteLen((BSTR)v13);
    v18 = SysAllocStringByteLen(v13, v19);
    v38 = v18;
    if ( v18 )
      goto LABEL_29;
    _mm_lfence();
    std::vector<unsigned short>::~vector<unsigned short>(Str);
LABEL_32:
    SysFreeString(0);
    SysFreeString((BSTR)v13);
LABEL_102:
    v11 = -2147024882;
    goto LABEL_103;
  }
  v18 = 0;
  v38 = 0;
LABEL_29:
  std::vector<unsigned short>::~vector<unsigned short>(Str);
LABEL_42:
  v41[0] = 0;
  v21 = DiagHubCommon::RegisterStandardCollectorProxyStubs(v13, v41);
  if ( v21 < 0 )
  {
    _mm_lfence();
    if ( v41[0] )
      (**(void (__fastcall ***)(_QWORD, __int64))v41[0])(v41[0], 1);
    v22 = v18;
LABEL_46:
    SysFreeString(v22);
    SysFreeString((BSTR)v13);
    v11 = v21;
    goto LABEL_103;
  }
  v23 = v41[0];
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v41[0] + 8LL))(v41[0]);
  v21 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v38, L"\\DiagnosticsHub.StandardCollector.Runtime.dll");
  if ( v21 < 0 )
  {
    _mm_lfence();
    if ( v23 )
      (**(void (__fastcall ***)(__int64, __int64))v23)(v23, 1);
    v22 = v38;
    goto LABEL_46;
  }
  v24 = _logger;
  if ( *((_QWORD *)_logger + 7) == *((_QWORD *)_logger + 8) )
  {
    v26 = v38;
  }
  else
  {
    v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v26 = v38;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)v24 + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Service\\StandardCollectorHost.cpp",
      L"Loading runtime version for '%s' from '%s'. Proxy stubs registered from '%s'",
      v5,
      v38,
      v25);
  }
  Library = LoadLibraryExW(v26, 0, 8u);
  if ( !Library || (ProcAddress = GetProcAddress(Library, "DllGetClassObject")) == 0 )
  {
    v28 = GetLastError();
    v29 = (unsigned __int16)v28 | 0x80070000;
    if ( v28 <= 0 )
      v29 = v28;
    goto LABEL_57;
  }
  v44 = 0;
  v29 = ((__int64 (__fastcall *)(GUID *, GUID *, _QWORD **))ProcAddress)(
          &CLSID_StandardCollectorService,
          &GUID_00000001_0000_0000_c000_000000000046,
          &v44);
  if ( v29 < 0 )
  {
    _mm_lfence();
    if ( v44 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v44 + 16LL))(v44, *v44);
LABEL_57:
    if ( v23 )
      (**(void (__fastcall ***)(__int64, __int64))v23)(v23, 1);
    SysFreeString(v26);
    SysFreeString((BSTR)v13);
    v11 = v29;
    goto LABEL_103;
  }
  v43 = 0;
  v31 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, GUID *, __int64 (****)(void)))(*v44 + 24LL))(
          v44,
          0,
          &IID_IStandardCollectorService,
          &v43);
  v29 = v31;
  if ( v31 < 0 )
  {
    _mm_lfence();
    if ( v43 )
      ((void (__fastcall *)(__int64 (***)(void), __int64 (**)(void)))(*v43)[2])(v43, *v43);
    if ( v44 )
      (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
    goto LABEL_57;
  }
  v32 = 0;
  v45 = 0;
  if ( v43 )
  {
    v33 = ((__int64 (__fastcall *)(__int64 (***)(void), GUID *, _QWORD **))**v43)(
            v43,
            &GUID_bc93e0a1_8adb_482a_a4b8_44759daa4fd3,
            &v45);
    if ( v33 >= 0 )
    {
      v32 = v45;
    }
    else
    {
      v32 = 0;
      v45 = 0;
    }
  }
  if ( v32 )
  {
    v34 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64 *))(*v32 + 24LL))(
            v32,
            &qword_140024830,
            &qword_140023220);
    v29 = v34;
    if ( v34 < 0 )
    {
      _mm_lfence();
      if ( v45 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v45 + 16LL))(v45, *v45);
      if ( v43 )
        ((void (__fastcall *)(__int64 (***)(void)))(*v43)[2])(v43);
      if ( v44 )
        (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
      goto LABEL_57;
    }
  }
  try
  {
    std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::emplace<ATL::CComBSTR &,ATL::CComPtr<IStandardCollectorService> &>();
    v35 = **v43;
  }
  catch ( std::bad_alloc )
  {
    if ( v45 )
      (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    if ( v43 )
      ((void (__fastcall *)(__int64 (***)(void)))(*v43)[2])(v43);
    if ( v44 )
      (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
    if ( v41[0] )
      (**(void (__fastcall ***)(_QWORD, __int64))v41[0])(v41[0], 1);
    SysFreeString(v38);
    SysFreeString(bstrString);
    v5 = v40;
    v6 = v42;
    goto LABEL_102;
  }
  std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::emplace<ATL::CComBSTR &,ATL::CComPtr<IStandardCollectorService> &>();
  v35 = **v43;
  if ( v45 )
    (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
  if ( v43 )
    ((void (__fastcall *)(__int64 (***)(void)))(*v43)[2])(v43);
  if ( v44 )
    (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
  if ( v41[0] )
    (**(void (__fastcall ***)(_QWORD, __int64))v41[0])(v41[0], 1);
  SysFreeString(v38);
  SysFreeString(bstrString);
  v5 = v40;
  v6 = v42;
}

```

## disassembly

```asm
0x140005b70  push    rbx
0x140005b72  push    rsi
0x140005b73  push    rdi
0x140005b74  push    r12
0x140005b76  push    r13
0x140005b78  push    r14
0x140005b7a  push    r15
0x140005b7c  sub     rsp, 0D0h
0x140005b83  mov     rax, cs:__security_cookie
0x140005b8a  xor     rax, rsp
0x140005b8d  mov     [rsp+108h+var_48], rax
0x140005b95  mov     r13, r8
0x140005b98  mov     [rsp+108h+var_A8], r8
0x140005b9d  mov     rdi, rcx
0x140005ba0  xor     r12d, r12d
0x140005ba3  test    rdx, rdx
0x140005ba6  jz      loc_140006326
0x140005bac  test    r8, r8
0x140005baf  jz      loc_140006326
0x140005bb5  mov     rcx, rdx; psz
0x140005bb8  call    cs:__imp_SysAllocString
0x140005bbe  mov     r14, rax
0x140005bc1  mov     [rsp+108h+var_C8], rax
0x140005bc6  test    rax, rax
0x140005bc9  jz      loc_14000634E
0x140005bcf  lea     r15, [rdi+30h]
0x140005bd3  mov     [rsp+108h+var_A0], r15
0x140005bd8  mov     rcx, r15; lpCriticalSection
0x140005bdb  call    cs:__imp_EnterCriticalSection
0x140005be1  nop
0x140005be2  lea     rsi, [rdi+58h]
0x140005be6  mov     [rsp+108h+var_B0], rsi
0x140005beb  lea     rdx, [rsp+108h+var_C8]
0x140005bf0  call    ??$?RVCComBSTR@ATL@@@?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@QEBA_KAEBVCComBSTR@ATL@@@Z; std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>::operator()<ATL::CComBSTR>(ATL::CComBSTR const &)
0x140005bf5  mov     r9, rax
0x140005bf8  lea     r8, [rsp+108h+var_C8]
0x140005bfd  lea     rdx, [rsp+108h+var_C0]
0x140005c02  mov     rcx, rsi
0x140005c05  call    ??$_Find_last@VCComBSTR@ATL@@@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@PEAX@std@@@1@AEBVCComBSTR@ATL@@_K@Z; std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Find_last<ATL::CComBSTR>(ATL::CComBSTR const &,unsigned __int64)
0x140005c0a  mov     rbx, [rax+8]
0x140005c0e  test    rbx, rbx
0x140005c11  jnz     short loc_140005C17
0x140005c13  mov     rbx, [rsi+8]
0x140005c17  cmp     rbx, [rdi+60h]
0x140005c1b  jz      short loc_140005C69
0x140005c1d  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x140005c24  add     rcx, 38h ; '8'; this
0x140005c28  mov     rax, [rcx+8]
0x140005c2c  cmp     [rcx], rax
0x140005c2f  jz      short loc_140005C48
0x140005c31  mov     r9, r14
0x140005c34  lea     r8, aReturningRunti; "Returning runtime version '%s'"
0x140005c3b  lea     rdx, aDAWork1SSource_0; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x140005c42  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140005c47  nop
0x140005c48  mov     rcx, [rbx+18h]
0x140005c4c  mov     rax, [rcx]
0x140005c4f  mov     r8, r13
0x140005c52  lea     rdx, _GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44
0x140005c59  mov     rax, [rax]
0x140005c5c  call    cs:__guard_dispatch_icall_fptr
0x140005c62  mov     ebx, eax
0x140005c64  jmp     loc_14000630F
0x140005c69  cmp     cs:qword_140024848, r12
0x140005c70  jnz     short loc_140005CB0
0x140005c72  xor     r8d, r8d; pcbe
0x140005c75  xor     edx, edx; pv
0x140005c77  lea     rcx, _anonymous_namespace___ServiceLifetimeManager__HostShutdownMain; pfnti
0x140005c7e  call    cs:__imp_CreateThreadpoolTimer
0x140005c84  mov     cs:qword_140024848, rax
0x140005c8b  test    rax, rax
0x140005c8e  jnz     short loc_140005CB0
0x140005c90  call    cs:__imp_GetLastError
0x140005c96  movzx   ebx, ax
0x140005c99  or      ebx, 80070000h
0x140005c9f  test    eax, eax
0x140005ca1  cmovle  ebx, eax
0x140005ca4  test    ebx, ebx
0x140005ca6  jns     short loc_140005CB0
0x140005ca8  lfence
0x140005cab  jmp     loc_14000630F
0x140005cb0  mov     rbx, r12
0x140005cb3  mov     [rsp+108h+bstrString], rbx
0x140005cb8  mov     [rsp+108h+var_D8], r12
0x140005cbd  cmp     word ptr [r14], 23h ; '#'
0x140005cc2  jnz     loc_140005E0F
0x140005cc8  cmp     [r14+2], r12w
0x140005ccd  jnz     loc_140005E0F
0x140005cd3  xorps   xmm0, xmm0
0x140005cd6  movdqu  xmmword ptr [rsp+108h+Str], xmm0
0x140005cdf  xorps   xmm1, xmm1
0x140005ce2  movdqu  xmmword ptr [rsp+108h+psz], xmm1
0x140005ceb  mov     [rsp+108h+var_50], r12
0x140005cf3  lea     rdx, [rsp+108h+Str]
0x140005cfb  xor     ecx, ecx; hModule
0x140005cfd  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x140005d02  mov     edi, eax
0x140005d04  test    eax, eax
0x140005d06  js      short loc_140005D56
0x140005d08  mov     edx, 5Ch ; '\'; Ch
0x140005d0d  mov     rcx, [rsp+108h+Str]; Str
0x140005d15  call    cs:__imp_wcsrchr
0x140005d1b  test    rax, rax
0x140005d1e  jnz     short loc_140005D2F
0x140005d20  mov     edi, 800700A1h
0x140005d25  mov     rsi, [rsp+108h+psz+8]
0x140005d2d  jmp     short loc_140005D52
0x140005d2f  mov     [rax], r12w
0x140005d33  mov     rsi, [rsp+108h+Str]
0x140005d3b  mov     [rsp+108h+psz+8], rsi
0x140005d43  add     rax, 2
0x140005d47  mov     [rsp+108h+var_50], rax
0x140005d4f  mov     edi, r12d
0x140005d52  test    edi, edi
0x140005d54  jns     short loc_140005D7F
0x140005d56  lfence
0x140005d59  lea     rcx, [rsp+108h+Str]
0x140005d61  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x140005d66  nop
0x140005d67  xor     ecx, ecx; bstrString
0x140005d69  call    cs:__imp_SysFreeString
0x140005d6f  nop
0x140005d70  xor     ecx, ecx; bstrString
0x140005d72  call    cs:__imp_SysFreeString
0x140005d78  mov     ebx, edi
0x140005d7a  jmp     loc_14000630F
0x140005d7f  test    rsi, rsi
0x140005d82  jz      short loc_140005DA6
0x140005d84  xor     ecx, ecx; bstrString
0x140005d86  call    cs:__imp_SysFreeString
0x140005d8c  mov     rcx, rsi; psz
0x140005d8f  call    cs:__imp_SysAllocString
0x140005d95  mov     rbx, rax
0x140005d98  mov     [rsp+108h+bstrString], rax
0x140005d9d  test    rax, rax
0x140005da0  jz      loc_140006359
0x140005da6  test    rbx, rbx
0x140005da9  jnz     short loc_140005DC5
0x140005dab  mov     rdi, r12
0x140005dae  mov     [rsp+108h+var_D8], r12
0x140005db3  lea     rcx, [rsp+108h+Str]
0x140005dbb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x140005dc0  jmp     loc_140005EA9
0x140005dc5  mov     rcx, rbx; bstr
0x140005dc8  call    cs:__imp_SysStringByteLen
0x140005dce  mov     edx, eax; len
0x140005dd0  mov     rcx, rbx; psz
0x140005dd3  call    cs:__imp_SysAllocStringByteLen
0x140005dd9  mov     rdi, rax
0x140005ddc  mov     [rsp+108h+var_D8], rax
0x140005de1  test    rax, rax
0x140005de4  jnz     short loc_140005DB3
0x140005de6  lfence
0x140005de9  lea     rcx, [rsp+108h+Str]
0x140005df1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x140005df6  nop
0x140005df7  mov     rcx, rdi; bstrString
0x140005dfa  call    cs:__imp_SysFreeString
0x140005e00  nop
0x140005e01  mov     rcx, rbx; bstrString
0x140005e04  call    cs:__imp_SysFreeString
0x140005e0a  jmp     loc_14000630A
0x140005e0f  lea     rdx, [rsp+108h+bstrString]; unsigned __int16 *
0x140005e14  mov     rcx, r14; this
0x140005e17  call    ?DetermineVsInstanceRoot@DiagHubCommon@@YAJPEBGPEAPEAG@Z; DiagHubCommon::DetermineVsInstanceRoot(ushort const *,ushort * *)
0x140005e1c  mov     ebx, eax
0x140005e1e  test    eax, eax
0x140005e20  jns     short loc_140005E3E
0x140005e22  lfence
0x140005e25  xor     ecx, ecx; bstrString
0x140005e27  call    cs:__imp_SysFreeString
0x140005e2d  nop
0x140005e2e  mov     rcx, [rsp+108h+bstrString]; bstrString
0x140005e33  call    cs:__imp_SysFreeString
0x140005e39  jmp     loc_14000630F
0x140005e3e  mov     rbx, [rsp+108h+bstrString]
0x140005e43  test    rbx, rbx
0x140005e46  jnz     short loc_140005E7B
0x140005e48  mov     [rsp+108h+var_D8], r12
0x140005e4d  lea     rdx, aTeamToolsDiagn; "\\Team Tools\\DiagnosticsHub\\Collector"
0x140005e54  lea     rcx, [rsp+108h+var_D8]; this
0x140005e59  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140005e5e  mov     edi, eax
0x140005e60  test    eax, eax
0x140005e62  jns     short loc_140005EA4
0x140005e64  lfence
0x140005e67  mov     rcx, [rsp+108h+var_D8]; bstrString
0x140005e6c  call    cs:__imp_SysFreeString
0x140005e72  nop
0x140005e73  mov     rcx, rbx
0x140005e76  jmp     loc_140005D72
0x140005e7b  mov     rcx, rbx; bstr
0x140005e7e  call    cs:__imp_SysStringByteLen
0x140005e84  mov     edx, eax; len
0x140005e86  mov     rcx, rbx; psz
0x140005e89  call    cs:__imp_SysAllocStringByteLen
0x140005e8f  mov     [rsp+108h+var_D8], rax
0x140005e94  test    rax, rax
0x140005e97  jnz     short loc_140005E4D
0x140005e99  lfence
0x140005e9c  mov     rcx, rax
0x140005e9f  jmp     loc_140005DFA
0x140005ea4  mov     rdi, [rsp+108h+var_D8]
0x140005ea9  mov     [rsp+108h+var_C0], r12
0x140005eae  lea     rdx, [rsp+108h+var_C0]
0x140005eb3  mov     rcx, rbx
0x140005eb6  call    ?RegisterStandardCollectorProxyStubs@DiagHubCommon@@YAJPEBGAEAV?$unique_ptr@VComProxyRegistration@DiagHubCommon@@U?$default_delete@VComProxyRegistration@DiagHubCommon@@@std@@@std@@@Z; DiagHubCommon::RegisterStandardCollectorProxyStubs(ushort const *,std::unique_ptr<DiagHubCommon::ComProxyRegistration> &)
0x140005ebb  mov     esi, eax
0x140005ebd  test    eax, eax
0x140005ebf  jns     short loc_140005EFA
0x140005ec1  lfence
0x140005ec4  mov     rcx, [rsp+108h+var_C0]
0x140005ec9  test    rcx, rcx
0x140005ecc  jz      short loc_140005EE0
0x140005ece  mov     rdx, [rcx]
0x140005ed1  mov     rax, [rdx]
0x140005ed4  mov     edx, 1
0x140005ed9  call    cs:__guard_dispatch_icall_fptr
0x140005edf  nop
0x140005ee0  mov     rcx, rdi; bstrString
0x140005ee3  call    cs:__imp_SysFreeString
0x140005ee9  nop
0x140005eea  mov     rcx, rbx; bstrString
0x140005eed  call    cs:__imp_SysFreeString
0x140005ef3  mov     ebx, esi
0x140005ef5  jmp     loc_14000630F
0x140005efa  mov     rdi, [rsp+108h+var_C0]
0x140005eff  mov     rax, [rdi]
0x140005f02  mov     rcx, rdi
0x140005f05  mov     rax, [rax+8]
0x140005f09  call    cs:__guard_dispatch_icall_fptr
0x140005f0f  lea     rdx, aDiagnosticshub_0; "\\DiagnosticsHub.StandardCollector.Runt"...
0x140005f16  lea     rcx, [rsp+108h+var_D8]; this
0x140005f1b  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140005f20  mov     esi, eax
0x140005f22  test    eax, eax
0x140005f24  jns     short loc_140005F4A
0x140005f26  lfence
0x140005f29  test    rdi, rdi
0x140005f2c  jz      short loc_140005F43
0x140005f2e  mov     rcx, [rdi]
0x140005f31  mov     rax, [rcx]
0x140005f34  mov     edx, 1
0x140005f39  mov     rcx, rdi
0x140005f3c  call    cs:__guard_dispatch_icall_fptr
0x140005f42  nop
0x140005f43  mov     rcx, [rsp+108h+var_D8]
0x140005f48  jmp     short loc_140005EE3
0x140005f4a  mov     r13, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x140005f51  mov     rax, [r13+40h]
0x140005f55  cmp     [r13+38h], rax
0x140005f59  jz      short loc_140005F96
0x140005f5b  mov     rax, [rdi]
0x140005f5e  mov     rcx, rdi
0x140005f61  mov     rax, [rax+10h]
0x140005f65  call    cs:__guard_dispatch_icall_fptr
0x140005f6b  mov     [rsp+108h+var_E0], rax
0x140005f70  mov     rsi, [rsp+108h+var_D8]
0x140005f75  mov     [rsp+108h+var_E8], rsi
0x140005f7a  mov     r9, r14
0x140005f7d  lea     r8, aLoadingRuntime; "Loading runtime version for '%s' from '"...
0x140005f84  lea     rdx, aDAWork1SSource_0; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x140005f8b  lea     rcx, [r13+38h]; this
0x140005f8f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140005f94  jmp     short loc_140005F9B
0x140005f96  mov     rsi, [rsp+108h+var_D8]
0x140005f9b  xor     edx, edx; hFile
0x140005f9d  lea     r8d, [rdx+8]; dwFlags
0x140005fa1  mov     rcx, rsi; lpLibFileName
0x140005fa4  call    cs:__imp_LoadLibraryExW
0x140005faa  test    rax, rax
0x140005fad  jnz     short loc_140005FFB
0x140005faf  call    cs:__imp_GetLastError
0x140005fb5  movzx   r13d, ax
0x140005fb9  or      r13d, 80070000h
0x140005fc0  test    eax, eax
0x140005fc2  cmovle  r13d, eax
0x140005fc6  test    rdi, rdi
0x140005fc9  jz      short loc_140005FE0
0x140005fcb  mov     rax, [rdi]
0x140005fce  mov     edx, 1
0x140005fd3  mov     rcx, rdi
0x140005fd6  mov     rax, [rax]
0x140005fd9  call    cs:__guard_dispatch_icall_fptr
0x140005fdf  nop
0x140005fe0  mov     rcx, rsi; bstrString
0x140005fe3  call    cs:__imp_SysFreeString
0x140005fe9  nop
0x140005fea  mov     rcx, rbx; bstrString
0x140005fed  call    cs:__imp_SysFreeString
0x140005ff3  mov     ebx, r13d
0x140005ff6  jmp     loc_14000630F
0x140005ffb  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x140006002  mov     rcx, rax; hModule
0x140006005  call    cs:__imp_GetProcAddress
0x14000600b  test    rax, rax
0x14000600e  jz      short loc_140005FAF
0x140006010  mov     [rsp+108h+var_80], r12
0x140006018  lea     r8, [rsp+108h+var_80]
0x140006020  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
  ... truncated ...
```
