# CInterceptorFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800076b0`
- end: `0x180007d3e`
- name: `?CreateInstance@CInterceptorFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `1678`
- prototype: `__int64 __fastcall(CInterceptorFactory *this, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800070b8`
- `0x1800076b0`
- `0x180008094`
- `0x1800080e8`
- `0x180008198`
- `0x1800081f4`
- `0x180008250`
- `0x1800082b0`
- `0x180008310`
- `0x180008370`
- `0x1800083d0`
- `0x180008430`
- `0x18000848c`
- `0x1800084e8`
- `0x180008540`
- `0x18000859c`
- `0x18000866c`
- `0x18000881c`
- `0x180008958`
- `0x1800089b0`
- `0x180008af0`
- `0x180009f74`
- `0x18000a010`
- `0x18002515c`
- `0x1800266e0`
- `0x18002b3c0`
- `0x18002b400`
- `0x18002bdb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007957`
- `KERNEL32!GetLastError` at `0x1800079cf`
- `KERNEL32!GetLastError` at `0x180007957`
- `KERNEL32!GetLastError` at `0x1800079cf`
- `KERNEL32!GetProcAddress` at `0x1800079c4`
- `KERNEL32!GetProcAddress` at `0x1800079c4`
- `KERNEL32!EnterCriticalSection` at `0x180007bbd`
- `KERNEL32!EnterCriticalSection` at `0x180007bbd`
- `KERNEL32!LeaveCriticalSection` at `0x180007bd7`
- `KERNEL32!LeaveCriticalSection` at `0x180007be7`
- `KERNEL32!LeaveCriticalSection` at `0x180007bd7`
- `KERNEL32!LeaveCriticalSection` at `0x180007be7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800078e6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800078e6`
- `ADVAPI32!RegCloseKey` at `0x18000783f`
- `ADVAPI32!RegCloseKey` at `0x180007891`
- `ADVAPI32!RegCloseKey` at `0x180007937`
- `ADVAPI32!RegCloseKey` at `0x1800079ae`
- `ADVAPI32!RegCloseKey` at `0x180007a22`
- `ADVAPI32!RegCloseKey` at `0x180007aad`
- `ADVAPI32!RegCloseKey` at `0x180007b53`
- `ADVAPI32!RegCloseKey` at `0x180007ca7`
- `ADVAPI32!RegCloseKey` at `0x180007cfb`
- `ADVAPI32!RegCloseKey` at `0x18000783f`
- `ADVAPI32!RegCloseKey` at `0x180007891`
- `ADVAPI32!RegCloseKey` at `0x180007937`
- `ADVAPI32!RegCloseKey` at `0x1800079ae`
- `ADVAPI32!RegCloseKey` at `0x180007a22`
- `ADVAPI32!RegCloseKey` at `0x180007aad`
- `ADVAPI32!RegCloseKey` at `0x180007b53`
- `ADVAPI32!RegCloseKey` at `0x180007ca7`
- `ADVAPI32!RegCloseKey` at `0x180007cfb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800077f5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800077f5`
- `ole32!StringFromGUID2` at `0x180007714`
- `ole32!StringFromGUID2` at `0x180007714`
- `ole32!CoTaskMemFree` at `0x1800077bf`
- `ole32!CoTaskMemFree` at `0x1800077bf`
- `ole32!CoLoadLibrary` at `0x18000794c`
- `ole32!CoLoadLibrary` at `0x18000794c`
- `ole32!StringFromCLSID` at `0x180007775`
- `ole32!StringFromCLSID` at `0x180007775`
- `SHLWAPI!PathFindFileNameW` at `0x1800078b3`
- `SHLWAPI!PathFindFileNameW` at `0x1800078b3`

## string_xrefs

- `0x180007735`: `(hr=0x%08x) CInterceptorFactory::CreateInstance() failed due to invalid arg`
- `0x18000779c`: `SOFTWARE\Classes\CLSID\%s\InProcServer32`
- `0x1800078df`: `Interceptor.dll`
- `0x1800079ba`: `DllGetClassObject`
- `0x180007a59`: `(hr=0x%08x) CInterceptorFactory::CreateInstance() failed DllGetClassObject()`

## pseudocode

```c
__int64 __fastcall CInterceptorFactory::CreateInstance(
        CInterceptorFactory *this,
        struct IUnknown *a2,
        struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  LSTATUS v12; // eax
  HKEY v13; // rbx
  __int64 v14; // rcx
  const wchar_t *v15; // rdx
  unsigned int v16; // eax
  int StringValue; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  LPCWSTR v20; // rdi
  LPWSTR FileNameW; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  LPCWSTR v27; // rdx
  HINSTANCE Library; // rax
  signed int LastError; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  LPCWSTR v32; // rdx
  FARPROC ProcAddress; // rax
  signed int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  LPCWSTR v37; // rdx
  __int64 v38; // rcx
  LPCWSTR v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rcx
  LPCWSTR v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rcx
  int v45; // edi
  __int64 v46; // rax
  __int64 v47; // r15
  __int64 *v48; // r14
  __int64 v49; // r12
  struct _RTL_CRITICAL_SECTION *v50; // rsi
  __int64 v51; // rcx
  LPCWSTR v52; // rdx
  LPCWSTR v53; // rdx
  _BYTE v55[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v58; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v59; // [rsp+50h] [rbp-B0h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  void *v61; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v62; // [rsp+68h] [rbp-98h] BYREF
  int v63; // [rsp+70h] [rbp-90h]
  __int64 v64; // [rsp+78h] [rbp-88h]
  OLECHAR sz[64]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR szLibName[264]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t Buffer[264]; // [rsp+310h] [rbp+210h] BYREF

  if ( olog == 100 )
  {
    memset(sz, 0, sizeof(sz));
    StringFromGUID2(a3, sz, 64);
    LogLineFormat<40,wchar_t [64]>(v9, v8, sz);
  }
  if ( !a4 )
  {
    LODWORD(hKey) = -2147467261;
    LogLineFormat<76,long>(10, L"(hr=0x%08x) CInterceptorFactory::CreateInstance() failed due to invalid arg", &hKey);
    return (unsigned int)hKey;
  }
  *a4 = 0;
  JITVirtualize::JITVirtualize((JITVirtualize *)v55);
  memset(szLibName, 0, 520);
  LODWORD(hKey) = StringFromCLSID((const IID *const)((char *)this + 8), &lpsz);
  if ( (int)hKey >= 0 )
  {
    snwprintf_s(Buffer, 0x104u, 0xFFFFFFFFFFFFFFFFuLL, L"SOFTWARE\\Classes\\CLSID\\%s\\InProcServer32", lpsz);
    CoTaskMemFree(lpsz);
    v63 = 0;
    v64 = 0;
    hKey = 0;
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey);
    v13 = 0;
    if ( !v12 )
      v13 = hKey;
    v62 = v13;
    v14 = (unsigned int)-v12;
    v15 = (const wchar_t *)(v12 & (unsigned int)-(v12 != 0));
    if ( (v12 != 0 ? v12 : 0) != 0 )
    {
      v16 = (unsigned __int16)(v12 != 0 ? v12 : 0) | 0x80070000;
      if ( (int)v15 <= 0 )
        v16 = (unsigned int)v15;
      LODWORD(hKey) = v16;
      LogLineFormat<72,long,wchar_t [260]>(v14, v15, &hKey, Buffer);
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    LODWORD(hKey) = 260;
    StringValue = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&v62, v15, szLibName, (unsigned int *)&hKey);
    if ( StringValue )
    {
      v19 = (unsigned __int16)StringValue | 0x80070000;
      if ( StringValue <= 0 )
        v19 = (unsigned int)StringValue;
      LODWORD(hKey) = v19;
      LogLineFormat<83,long,wchar_t [260]>(v19, v18, &hKey, Buffer);
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    ATL::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>(
      &pszPath,
      szLibName);
    v20 = pszPath;
    FileNameW = PathFindFileNameW(pszPath);
    if ( !*FileNameW || (v24 = FileNameW - v20, (_DWORD)v24 == -1) )
    {
      LODWORD(hKey) = -2147024894;
      LogLineFormat<73,long,wchar_t [260]>(v23, v22, &hKey, szLibName);
      v53 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 8LL))(*(_QWORD *)v53);
      }
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    if ( !_wcsicmp(&szLibName[(int)v24], L"Interceptor.dll") )
    {
      LODWORD(hKey) = -2147467259;
      LogLineFormat<82,long,wchar_t [260]>(v26, v25, &hKey, szLibName);
      v27 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
      }
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    Library = CoLoadLibrary(szLibName, 1);
    if ( !Library )
    {
      LastError = GetLastError();
      v31 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v31 = (unsigned int)LastError;
      LODWORD(hKey) = v31;
      LogLineFormat<75,long,wchar_t [260]>(v31, v30, &hKey, szLibName);
      v32 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v32 + 8LL))(*(_QWORD *)v32);
      }
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    if ( !ProcAddress )
    {
      v34 = GetLastError();
      v36 = (unsigned __int16)v34 | 0x80070000;
      if ( v34 <= 0 )
        v36 = (unsigned int)v34;
      LODWORD(hKey) = v36;
      LogLineFormat<91,long>(v36, v35, &hKey);
      v37 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 8LL))(*(_QWORD *)v37);
      }
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    _mm_lfence();
    v59 = 0;
    LODWORD(hKey) = ((__int64 (__fastcall *)(char *, GUID *, __int64 *))ProcAddress)(
                      (char *)this + 8,
                      &IID_IClassFactory,
                      &v59);
    if ( (int)hKey < 0 )
    {
      LogLineFormat<77,long>(
        v38,
        L"(hr=0x%08x) CInterceptorFactory::CreateInstance() failed DllGetClassObject()",
        &hKey);
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v39 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 8LL))(*(_QWORD *)v39);
      }
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    v58 = 0;
    LODWORD(hKey) = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, GUID *, __int64 *))(*(_QWORD *)v59 + 24LL))(
                      v59,
                      a2,
                      &IID_IUnknown,
                      &v58);
    if ( (int)hKey < 0 )
    {
      LogLineFormat<89,long>(v41, v40, &hKey);
      if ( v58 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v42 = pszPath - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)pszPath - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v42 + 8LL))(*(_QWORD *)v42);
      }
      if ( v13 )
        RegCloseKey(v13);
      goto LABEL_88;
    }
    if ( memcmp(a3, &IID_IUnknown, 0x10u) )
    {
      v61 = 0;
      v45 = (**(__int64 (__fastcall ***)(__int64, struct _GUID *, void **))v58)(v58, a3, &v61);
      LODWORD(hKey) = v45;
      if ( v45 >= 0 )
      {
        _mm_lfence();
        InterceptInterface(a3, v61, a4);
      }
      goto LABEL_72;
    }
    v45 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v58)(v58, &IID_IUnknown, a4);
    LODWORD(hKey) = v45;
    if ( v45 >= 0 )
    {
      _mm_lfence();
      v46 = Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance();
      v47 = v46;
      if ( *a4 )
      {
        v48 = *(__int64 **)*a4;
        v49 = *v48;
        v50 = (struct _RTL_CRITICAL_SECTION *)(v46 + 64);
        EnterCriticalSection((LPCRITICAL_SECTION)(v46 + 64));
        if ( (unsigned __int8)SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>::VtblMethodSwap(
                                v51,
                                v48) )
        {
          LeaveCriticalSection(v50);
          TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::insert(v47, v48, v49);
          goto LABEL_72;
        }
        LogLineFormat<48>();
        LeaveCriticalSection(v50);
      }
      LogLineFormat<72>();
    }
LABEL_72:
    if ( v45 < 0 )
      LogLineFormat<57,long>(v44, v43, &hKey);
    else
      LogLineFormat<60,long>(v44, v43, &hKey);
    if ( v58 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    if ( v59 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    v52 = pszPath - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)pszPath - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v52 + 8LL))(*(_QWORD *)v52);
    }
    if ( v13 )
      RegCloseKey(v13);
    goto LABEL_88;
  }
  LogLineFormat<78,long>(v11, v10, &hKey);
LABEL_88:
  if ( v55[0] )
    DisableVirtualization();
  return (unsigned int)hKey;
}

```

## disassembly

```asm
0x1800076b0  push    rbp
0x1800076b2  push    rbx
0x1800076b3  push    rsi
0x1800076b4  push    rdi
0x1800076b5  push    r12
0x1800076b7  push    r13
0x1800076b9  push    r14
0x1800076bb  push    r15
0x1800076bd  lea     rbp, [rsp-438h]
0x1800076c5  sub     rsp, 538h
0x1800076cc  mov     rax, cs:__security_cookie
0x1800076d3  xor     rax, rsp
0x1800076d6  mov     [rbp+470h+var_50], rax
0x1800076dd  mov     rsi, r9
0x1800076e0  mov     r14, r8
0x1800076e3  mov     r12, rdx
0x1800076e6  mov     r15, rcx
0x1800076e9  xor     r13d, r13d
0x1800076ec  cmp     cs:?olog@@3VOLog@@A, 64h ; 'd'; OLog olog
0x1800076f3  jnz     short loc_180007723
0x1800076f5  mov     [rbp+470h+sz], r13w
0x1800076fa  xor     edx, edx; Val
0x1800076fc  lea     r8d, [r13+7Eh]; Size
0x180007700  lea     rcx, [rbp+470h+var_4EE]; void *
0x180007704  call    memset
0x180007709  lea     r8d, [r13+40h]; cchMax
0x18000770d  lea     rdx, [rbp+470h+sz]; lpsz
0x180007711  mov     rcx, r14; rguid
0x180007714  call    cs:__imp_StringFromGUID2
0x18000771a  lea     r8, [rbp+470h+sz]
0x18000771e  call    ??$LogLineFormat@$0CI@$$BY0EA@_W@@YAXW4Severity@Logging@Mso@@AEAY0CI@$$CB_WAEAY0EA@$$CB_W@Z; LogLineFormat<40,wchar_t [64]>(Mso::Logging::Severity,wchar_t const (&)[40],wchar_t const (&)[64])
0x180007723  test    rsi, rsi
0x180007726  jnz     short loc_180007749
0x180007728  mov     dword ptr [rsp+570h+hKey], 80004003h
0x180007730  lea     r8, [rsp+570h+hKey]
0x180007735  lea     rdx, aHr0x08xCinterc_6; "(hr=0x%08x) CInterceptorFactory::Create"...
0x18000773c  lea     ecx, [rsi+0Ah]
0x18000773f  call    ??$LogLineFormat@$0EM@J@@YAXW4Severity@Logging@Mso@@AEAY0EM@$$CB_WAEBJ@Z; LogLineFormat<76,long>(Mso::Logging::Severity,wchar_t const (&)[76],long const &)
0x180007744  jmp     loc_180007D17
0x180007749  mov     [rsi], r13
0x18000774c  lea     rcx, [rsp+570h+var_540]; this
0x180007751  call    ??0JITVirtualize@@QEAA@XZ; JITVirtualize::JITVirtualize(void)
0x180007756  mov     [rbp+470h+szLibName], r13w
0x18000775b  xor     edx, edx; Val
0x18000775d  mov     r8d, 206h; Size
0x180007763  lea     rcx, [rbp+470h+var_46E]; void *
0x180007767  call    memset
0x18000776c  lea     rdx, [rsp+570h+lpsz]; lplpsz
0x180007771  lea     rcx, [r15+8]; rclsid
0x180007775  call    cs:__imp_StringFromCLSID
0x18000777b  mov     dword ptr [rsp+570h+hKey], eax
0x18000777f  test    eax, eax
0x180007781  jns     short loc_180007792
0x180007783  lea     r8, [rsp+570h+hKey]
0x180007788  call    ??$LogLineFormat@$0EO@J@@YAXW4Severity@Logging@Mso@@AEAY0EO@$$CB_WAEBJ@Z; LogLineFormat<78,long>(Mso::Logging::Severity,wchar_t const (&)[78],long const &)
0x18000778d  jmp     loc_180007D02
0x180007792  mov     rax, [rsp+570h+lpsz]
0x180007797  mov     [rsp+570h+phkResult], rax
0x18000779c  lea     r9, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID\\%s\\InProcSer"...
0x1800077a3  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800077a7  mov     edi, 104h
0x1800077ac  mov     edx, edi; BufferCount
0x1800077ae  lea     rcx, [rbp+470h+Buffer]; Buffer
0x1800077b5  call    _snwprintf_s
0x1800077ba  mov     rcx, [rsp+570h+lpsz]; pv
0x1800077bf  call    cs:__imp_CoTaskMemFree
0x1800077c5  mov     [rsp+570h+var_500], r13d
0x1800077ca  mov     [rsp+570h+var_4F8], r13
0x1800077cf  mov     [rsp+570h+hKey], r13
0x1800077d4  lea     rax, [rsp+570h+hKey]
0x1800077d9  mov     [rsp+570h+phkResult], rax; phkResult
0x1800077de  mov     r9d, 20019h; samDesired
0x1800077e4  xor     r8d, r8d; ulOptions
0x1800077e7  lea     rdx, [rbp+470h+Buffer]; lpSubKey
0x1800077ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800077f5  call    cs:__imp_RegOpenKeyExW
0x1800077fb  mov     rbx, r13
0x1800077fe  test    eax, eax
0x180007800  cmovz   rbx, [rsp+570h+hKey]
0x180007806  mov     [rsp+570h+var_508], rbx
0x18000780b  mov     ecx, eax
0x18000780d  neg     ecx
0x18000780f  sbb     edx, edx
0x180007811  and     edx, eax; wchar_t *
0x180007813  jz      short loc_18000784B
0x180007815  movzx   eax, dx
0x180007818  or      eax, 80070000h
0x18000781d  test    edx, edx
0x18000781f  cmovle  eax, edx
0x180007822  mov     dword ptr [rsp+570h+hKey], eax
0x180007826  lea     r9, [rbp+470h+Buffer]
0x18000782d  lea     r8, [rsp+570h+hKey]
0x180007832  call    ??$LogLineFormat@$0EI@J$$BY0BAE@_W@@YAXW4Severity@Logging@Mso@@AEAY0EI@$$CB_WAEBJAEAY0BAE@$$CB_W@Z; LogLineFormat<72,long,wchar_t [260]>(Mso::Logging::Severity,wchar_t const (&)[72],long const &,wchar_t const (&)[260])
0x180007837  test    rbx, rbx
0x18000783a  jz      short loc_180007846
0x18000783c  mov     rcx, rbx; hKey
0x18000783f  call    cs:__imp_RegCloseKey
0x180007845  nop
0x180007846  jmp     loc_180007D02
0x18000784b  mov     dword ptr [rsp+570h+hKey], edi
0x18000784f  lea     r9, [rsp+570h+hKey]; unsigned int *
0x180007854  lea     r8, [rbp+470h+szLibName]; wchar_t *
0x180007858  lea     rcx, [rsp+570h+var_508]; this
0x18000785d  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEB_WPEA_WPEAK@Z; ATL::CRegKey::QueryStringValue(wchar_t const *,wchar_t *,ulong *)
0x180007862  test    eax, eax
0x180007864  jz      short loc_18000789D
0x180007866  movzx   ecx, ax
0x180007869  or      ecx, 80070000h
0x18000786f  test    eax, eax
0x180007871  cmovle  ecx, eax
0x180007874  mov     dword ptr [rsp+570h+hKey], ecx
0x180007878  lea     r9, [rbp+470h+Buffer]
0x18000787f  lea     r8, [rsp+570h+hKey]
0x180007884  call    ??$LogLineFormat@$0FD@J$$BY0BAE@_W@@YAXW4Severity@Logging@Mso@@AEAY0FD@$$CB_WAEBJAEAY0BAE@$$CB_W@Z; LogLineFormat<83,long,wchar_t [260]>(Mso::Logging::Severity,wchar_t const (&)[83],long const &,wchar_t const (&)[260])
0x180007889  test    rbx, rbx
0x18000788c  jz      short loc_180007898
0x18000788e  mov     rcx, rbx; hKey
0x180007891  call    cs:__imp_RegCloseKey
0x180007897  nop
0x180007898  jmp     loc_180007D02
0x18000789d  lea     rdx, [rbp+470h+szLibName]
0x1800078a1  lea     rcx, [rsp+570h+pszPath]
0x1800078a6  call    ??0?$CPathT@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>::CPathT<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>(wchar_t const *)
0x1800078ab  mov     rdi, [rsp+570h+pszPath]
0x1800078b0  mov     rcx, rdi; pszPath
0x1800078b3  call    cs:__imp_PathFindFileNameW
0x1800078b9  cmp     [rax], r13w
0x1800078bd  jz      loc_180007CB0
0x1800078c3  sub     rax, rdi
0x1800078c6  sar     rax, 1
0x1800078c9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800078cd  cmp     eax, edi
0x1800078cf  jz      loc_180007CB4
0x1800078d5  cdqe
0x1800078d7  lea     rcx, [rbp+470h+szLibName]
0x1800078db  lea     rcx, [rcx+rax*2]; String1
0x1800078df  lea     rdx, aInterceptorDll_0; "Interceptor.dll"
0x1800078e6  call    cs:__imp__wcsicmp
0x1800078ec  test    eax, eax
0x1800078ee  jnz     short loc_180007943
0x1800078f0  mov     dword ptr [rsp+570h+hKey], 80004005h
0x1800078f8  lea     r9, [rbp+470h+szLibName]
0x1800078fc  lea     r8, [rsp+570h+hKey]
0x180007901  call    ??$LogLineFormat@$0FC@J$$BY0BAE@_W@@YAXW4Severity@Logging@Mso@@AEAY0FC@$$CB_WAEBJAEAY0BAE@$$CB_W@Z; LogLineFormat<82,long,wchar_t [260]>(Mso::Logging::Severity,wchar_t const (&)[82],long const &,wchar_t const (&)[260])
0x180007906  mov     rdx, [rsp+570h+pszPath]
0x18000790b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000790f  mov     eax, edi
0x180007911  lock xadd [rdx+10h], eax
0x180007916  add     eax, edi
0x180007918  test    eax, eax
0x18000791a  jg      short loc_18000792F
0x18000791c  lfence
0x18000791f  mov     rcx, [rdx]
0x180007922  mov     rax, [rcx]
0x180007925  mov     rax, [rax+8]
0x180007929  call    cs:__guard_dispatch_icall_fptr
0x18000792f  test    rbx, rbx
0x180007932  jz      short loc_18000793E
0x180007934  mov     rcx, rbx; hKey
0x180007937  call    cs:__imp_RegCloseKey
0x18000793d  nop
0x18000793e  jmp     loc_180007D02
0x180007943  mov     edx, 1; bAutoFree
0x180007948  lea     rcx, [rbp+470h+szLibName]; lpszLibName
0x18000794c  call    cs:__imp_CoLoadLibrary
0x180007952  test    rax, rax
0x180007955  jnz     short loc_1800079BA
0x180007957  call    cs:__imp_GetLastError
0x18000795d  movzx   ecx, ax
0x180007960  or      ecx, 80070000h
0x180007966  test    eax, eax
0x180007968  cmovle  ecx, eax
0x18000796b  mov     dword ptr [rsp+570h+hKey], ecx
0x18000796f  lea     r9, [rbp+470h+szLibName]
0x180007973  lea     r8, [rsp+570h+hKey]
0x180007978  call    ??$LogLineFormat@$0EL@J$$BY0BAE@_W@@YAXW4Severity@Logging@Mso@@AEAY0EL@$$CB_WAEBJAEAY0BAE@$$CB_W@Z; LogLineFormat<75,long,wchar_t [260]>(Mso::Logging::Severity,wchar_t const (&)[75],long const &,wchar_t const (&)[260])
0x18000797d  mov     rdx, [rsp+570h+pszPath]
0x180007982  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180007986  mov     eax, edi
0x180007988  lock xadd [rdx+10h], eax
0x18000798d  add     eax, edi
0x18000798f  test    eax, eax
0x180007991  jg      short loc_1800079A6
0x180007993  lfence
0x180007996  mov     rcx, [rdx]
0x180007999  mov     rax, [rcx]
0x18000799c  mov     rax, [rax+8]
0x1800079a0  call    cs:__guard_dispatch_icall_fptr
0x1800079a6  test    rbx, rbx
0x1800079a9  jz      short loc_1800079B5
0x1800079ab  mov     rcx, rbx; hKey
0x1800079ae  call    cs:__imp_RegCloseKey
0x1800079b4  nop
0x1800079b5  jmp     loc_180007D02
0x1800079ba  lea     rdx, ProcName; "DllGetClassObject"
0x1800079c1  mov     rcx, rax; hModule
0x1800079c4  call    cs:__imp_GetProcAddress
0x1800079ca  test    rax, rax
0x1800079cd  jnz     short loc_180007A2E
0x1800079cf  call    cs:__imp_GetLastError
0x1800079d5  movzx   ecx, ax
0x1800079d8  or      ecx, 80070000h
0x1800079de  test    eax, eax
0x1800079e0  cmovle  ecx, eax
0x1800079e3  mov     dword ptr [rsp+570h+hKey], ecx
0x1800079e7  lea     r8, [rsp+570h+hKey]
0x1800079ec  call    ??$LogLineFormat@$0FL@J@@YAXW4Severity@Logging@Mso@@AEAY0FL@$$CB_WAEBJ@Z; LogLineFormat<91,long>(Mso::Logging::Severity,wchar_t const (&)[91],long const &)
0x1800079f1  mov     rdx, [rsp+570h+pszPath]
0x1800079f6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800079fa  mov     eax, edi
0x1800079fc  lock xadd [rdx+10h], eax
0x180007a01  add     eax, edi
0x180007a03  test    eax, eax
0x180007a05  jg      short loc_180007A1A
0x180007a07  lfence
0x180007a0a  mov     rcx, [rdx]
0x180007a0d  mov     rax, [rcx]
0x180007a10  mov     rax, [rax+8]
0x180007a14  call    cs:__guard_dispatch_icall_fptr
0x180007a1a  test    rbx, rbx
0x180007a1d  jz      short loc_180007A29
0x180007a1f  mov     rcx, rbx; hKey
0x180007a22  call    cs:__imp_RegCloseKey
0x180007a28  nop
0x180007a29  jmp     loc_180007D02
0x180007a2e  lfence
0x180007a31  mov     [rsp+570h+var_520], r13
0x180007a36  lea     r8, [rsp+570h+var_520]
0x180007a3b  lea     rdx, IID_IClassFactory
0x180007a42  lea     rcx, [r15+8]
0x180007a46  call    cs:__guard_dispatch_icall_fptr
0x180007a4c  mov     dword ptr [rsp+570h+hKey], eax
0x180007a50  test    eax, eax
0x180007a52  jns     short loc_180007AB9
0x180007a54  lea     r8, [rsp+570h+hKey]
0x180007a59  lea     rdx, aHr0x08xCinterc_8; "(hr=0x%08x) CInterceptorFactory::Create"...
0x180007a60  call    ??$LogLineFormat@$0EN@J@@YAXW4Severity@Logging@Mso@@AEAY0EN@$$CB_WAEBJ@Z; LogLineFormat<77,long>(Mso::Logging::Severity,wchar_t const (&)[77],long const &)
0x180007a65  mov     rcx, [rsp+570h+var_520]
0x180007a6a  test    rcx, rcx
0x180007a6d  jz      short loc_180007A7C
0x180007a6f  mov     rax, [rcx]
0x180007a72  mov     rax, [rax+10h]
0x180007a76  call    cs:__guard_dispatch_icall_fptr
0x180007a7c  mov     rdx, [rsp+570h+pszPath]
0x180007a81  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180007a85  mov     eax, edi
0x180007a87  lock xadd [rdx+10h], eax
0x180007a8c  add     eax, edi
0x180007a8e  test    eax, eax
0x180007a90  jg      short loc_180007AA5
0x180007a92  lfence
0x180007a95  mov     rcx, [rdx]
0x180007a98  mov     rax, [rcx]
0x180007a9b  mov     rax, [rax+8]
0x180007a9f  call    cs:__guard_dispatch_icall_fptr
0x180007aa5  test    rbx, rbx
0x180007aa8  jz      short loc_180007AB4
0x180007aaa  mov     rcx, rbx; hKey
0x180007aad  call    cs:__imp_RegCloseKey
0x180007ab3  nop
0x180007ab4  jmp     loc_180007D02
0x180007ab9  mov     [rsp+570h+var_528], r13
0x180007abe  mov     rcx, [rsp+570h+var_520]
0x180007ac3  mov     rax, [rcx]
0x180007ac6  lea     r9, [rsp+570h+var_528]
0x180007acb  lea     r15, IID_IUnknown
0x180007ad2  mov     r8, r15
0x180007ad5  mov     rdx, r12
0x180007ad8  mov     rax, [rax+18h]
0x180007adc  call    cs:__guard_dispatch_icall_fptr
0x180007ae2  mov     dword ptr [rsp+570h+hKey], eax
0x180007ae6  test    eax, eax
0x180007ae8  jns     short loc_180007B5F
0x180007aea  lea     r8, [rsp+570h+hKey]
0x180007aef  call    ??$LogLineFormat@$0FJ@J@@YAXW4Severity@Logging@Mso@@AEAY0FJ@$$CB_WAEBJ@Z; LogLineFormat<89,long>(Mso::Logging::Severity,wchar_t const (&)[89],long const &)
0x180007af4  mov     rcx, [rsp+570h+var_528]
0x180007af9  test    rcx, rcx
0x180007afc  jz      short loc_180007B0B
0x180007afe  mov     rax, [rcx]
0x180007b01  mov     rax, [rax+10h]
0x180007b05  call    cs:__guard_dispatch_icall_fptr
0x180007b0b  mov     rcx, [rsp+570h+var_520]
0x180007b10  test    rcx, rcx
0x180007b13  jz      short loc_180007B22
0x180007b15  mov     rax, [rcx]
0x180007b18  mov     rax, [rax+10h]
0x180007b1c  call    cs:__guard_dispatch_icall_fptr
0x180007b22  mov     rdx, [rsp+570h+pszPath]
0x180007b27  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180007b2b  mov     eax, edi
0x180007b2d  lock xadd [rdx+10h], eax
0x180007b32  add     eax, edi
0x180007b34  test    eax, eax
0x180007b36  jg      short loc_180007B4B
0x180007b38  lfence
0x180007b3b  mov     rcx, [rdx]
0x180007b3e  mov     rax, [rcx]
0x180007b41  mov     rax, [rax+8]
0x180007b45  call    cs:__guard_dispatch_icall_fptr
0x180007b4b  test    rbx, rbx
  ... truncated ...
```
