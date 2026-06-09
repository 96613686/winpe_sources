# CodeIntegrity::Management::GetTenantID(_GUID &)

- ea: `0x180012f90`
- end: `0x18001365a`
- name: `?GetTenantID@Management@CodeIntegrity@@YA?AU_GUID@@AEAU3@@Z`
- size: `1738`
- prototype: `struct _GUID *__fastcall(struct _GUID *this, struct _GUID *__return_ptr retstr, struct _GUID *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009370`

## callees

- `0x180002a90`
- `0x180003888`
- `0x180005d4c`
- `0x18000828c`
- `0x180008474`
- `0x180009f94`
- `0x18000d450`
- `0x18000d470`
- `0x18000e8e8`
- `0x18000fc6c`
- `0x1800108cc`
- `0x18001097c`
- `0x1800109b4`
- `0x1800109d8`
- `0x180010a1c`
- `0x180011250`
- `0x180011350`
- `0x180011498`
- `0x1800114b8`
- `0x180011648`
- `0x180011b30`
- `0x180012f90`
- `0x180015448`
- `0x1800154a4`
- `0x1800154c0`
- `0x1800156b0`
- `0x1800157c4`
- `0x1800158a8`
- `0x180016368`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013319`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013319`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800132ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800132ed`
- `ntdll!RtlGetPersistedStateLocation` at `0x180013030`
- `ntdll!RtlGetPersistedStateLocation` at `0x180013030`
- `RPCRT4!UuidFromStringW` at `0x18001326d`
- `RPCRT4!UuidFromStringW` at `0x18001328f`
- `RPCRT4!UuidFromStringW` at `0x180013472`
- `RPCRT4!UuidFromStringW` at `0x180013489`
- `RPCRT4!UuidFromStringW` at `0x18001326d`
- `RPCRT4!UuidFromStringW` at `0x18001328f`
- `RPCRT4!UuidFromStringW` at `0x180013472`
- `RPCRT4!UuidFromStringW` at `0x180013489`
- `RPCRT4!UuidToStringW` at `0x180013090`
- `RPCRT4!UuidToStringW` at `0x180013090`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800134f5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800134f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013214`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013214`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800135a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800135a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131ba`

## string_xrefs

- `0x180013045`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x1800132ae`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x1800133cb`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x18001341c`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x1800134a8`: `onecore\base\ci\management\dll\manageci.cpp`
- `0x1800132e6`: `dmenrollengine.dll`

## pseudocode

```c
struct _GUID *__fastcall CodeIntegrity::Management::GetTenantID(
        struct _GUID *this,
        struct _GUID *__return_ptr retstr,
        struct _GUID *a3)
{
  int PersistedStateLocation; // eax
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  const WCHAR *v14; // rax
  LSTATUS v15; // eax
  signed int v16; // ebx
  unsigned int v17; // r8d
  unsigned int ValueW; // eax
  unsigned int v19; // r8d
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rax
  signed int v22; // eax
  HMODULE Library; // rax
  unsigned int v24; // r8d
  const char *v25; // r9
  FARPROC ProcAddress; // rax
  unsigned int v27; // r8d
  const char *v28; // r9
  int v29; // ebx
  const wchar_t *v30; // rcx
  int AadTenantID; // eax
  HRESULT v32; // eax
  __int64 v33; // rax
  __int64 v34; // rax
  signed int v35; // eax
  const WCHAR *v36; // rax
  unsigned int v37; // eax
  unsigned int v38; // r8d
  __int64 v39; // rdx
  const BYTE *v40; // rax
  DWORD v41; // edx
  unsigned int v42; // eax
  unsigned int v43; // r8d
  void *v44; // rdx
  unsigned int v45; // r8d
  const char *v46; // r9
  wil::details *v47; // rcx
  struct _GUID *result; // rax
  unsigned int v49; // r8d
  const char *v50; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-438h]
  unsigned int phkResulta; // [rsp+20h] [rbp-438h]
  unsigned int phkResultb; // [rsp+20h] [rbp-438h]
  STRSAFE_PCNZWCH psz; // [rsp+40h] [rbp-418h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-410h] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-408h] BYREF
  DWORD pcbData[2]; // [rsp+58h] [rbp-400h] BYREF
  HMODULE v58[2]; // [rsp+60h] [rbp-3F8h] BYREF
  _BYTE v59[8]; // [rsp+70h] [rbp-3E8h] BYREF
  _BYTE v60[232]; // [rsp+78h] [rbp-3E0h] BYREF
  void *p_psz; // [rsp+160h] [rbp-2F8h] BYREF
  HKEY v62; // [rsp+168h] [rbp-2F0h] BYREF
  char v63; // [rsp+170h] [rbp-2E8h]
  _BYTE v64[16]; // [rsp+180h] [rbp-2D8h] BYREF
  HKEY v65[2]; // [rsp+1A0h] [rbp-2B8h] BYREF
  char v66; // [rsp+1B0h] [rbp-2A8h]
  UUID Uuid; // [rsp+1C0h] [rbp-298h] BYREF
  _BYTE v68[16]; // [rsp+1D0h] [rbp-288h] BYREF
  __int64 v69; // [rsp+1E0h] [rbp-278h]
  _BYTE v70[32]; // [rsp+1F0h] [rbp-268h] BYREF
  unsigned int pvData[132]; // [rsp+210h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+0h]

  LODWORD(v65[0]) = 0;
  memset_0(pvData, 0, 0x20Au);
  *(_QWORD *)pcbData = 261;
  psz = 0;
  Uuid = 0;
  std::wstring::wstring(v68, 261);
  StringUuid = 0;
  hkey = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CIEnrollments",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Control\\CI\\Enrollments",
                             0);
  try
  {
    if ( PersistedStateLocation < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)PersistedStateLocation,
        (int)pvData);
    v6 = std::wstring::wstring(v64, pvData);
    std::wstring::operator=(v68, v6);
    std::wstring::_Tidy_deallocate(v64);
    v7 = UuidToStringW(retstr, &StringUuid);
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x1FB, v8, (const char *)v7, (unsigned int)pvData);
    v9 = std::wstring::wstring(v70, StringUuid);
    std::wstring::wstring(v65, L"\\");
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
    v12 = std::wstring::_Insert<unsigned short>(v11, v11, v10, v69);
    std::wstring::wstring(&p_psz, v12);
    std::wstring::wstring(v64, v13, &p_psz, v9);
    std::wstring::operator=(v68, v64);
    std::wstring::_Tidy_deallocate(v64);
    std::wstring::_Tidy_deallocate(&p_psz);
    std::wstring::_Tidy_deallocate(v65);
    std::wstring::_Tidy_deallocate(v70);
    v65[0] = (HKEY)&hkey;
    v65[1] = 0;
    v66 = 1;
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
    v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v14, 0, 0x20019u, &v65[1]);
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(v65);
    if ( v16 < 0 )
    {
      if ( v16 != -2147024894 )
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x245, v17, (const char *)(unsigned int)v16, phkResult);
      Library = LoadLibraryExW(L"dmenrollengine.dll", 0, 0x800u);
      v58[0] = Library;
      if ( !Library )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x21A, v24, v25);
      ProcAddress = GetProcAddress(Library, "GetEnrollmentTenantID");
      if ( !ProcAddress )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x221, v27, v28);
      p_psz = &psz;
      v62 = 0;
      v63 = 1;
      *(struct _GUID *)v65 = *retstr;
      v29 = ((__int64 (__fastcall *)(HKEY *, HKEY *))ProcAddress)(v65, &v62);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>(&p_psz);
      if ( v29 < 0 || (v30 = psz, !*psz) )
      {
        p_psz = &psz;
        v62 = 0;
        v63 = 1;
        AadTenantID = NetGetAadTenantID(v30, &v62);
        if ( AadTenantID < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x228,
            (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
            (const char *)(unsigned int)AadTenantID,
            phkResult);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>(&p_psz);
        v30 = psz;
      }
      if ( v30 )
        v32 = StringLengthWorkerW(v30, 0x7FFFFFFFu, (size_t *)v65);
      else
        v32 = -2147024809;
      if ( v32 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x22B,
          (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
          (const char *)(unsigned int)v32,
          phkResult);
      std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v59);
      v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v59, L"{");
      v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, psz);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L"}");
      if ( UuidFromStringW((RPC_WSTR)psz, &Uuid) )
        v35 = UuidFromStringW((RPC_WSTR)psz, &Uuid) | 0x80010000;
      else
        v35 = 0;
      if ( v35 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x232,
          (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
          (const char *)(unsigned int)v35,
          phkResult);
      p_psz = &hkey;
      v62 = 0;
      v63 = 1;
      v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
      v37 = RegCreateKeyW(HKEY_LOCAL_MACHINE, v36, &v62);
      if ( v37 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x237, v38, (const char *)v37, phkResult);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_psz);
      std::wstring::wstring(v64, v39);
      LODWORD(v65[0]) = 11;
      std::basic_stringbuf<unsigned short>::_Get_buffer_view(v60, &p_psz);
      if ( p_psz )
        std::wstring::assign(v64, p_psz, v62);
      v40 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v64);
      v42 = RegSetValueExW(hkey, L"TenantID", 0, 1u, v40, v41);
      if ( v42 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x241, v43, (const char *)v42, phkResultb);
      std::wstring::_Tidy_deallocate(v64);
      std::basic_ostringstream<unsigned short>::`vbase destructor'(v59);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v58);
    }
    else
    {
      ValueW = RegGetValueW(hkey, 0, L"TenantID", 2u, 0, pvData, pcbData);
      if ( ValueW )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x20E, v19, (const char *)ValueW, phkResulta);
      std::wstring::wstring(v64, (char *)pvData + 2, (*(_QWORD *)pcbData >> 1) - 3LL);
      v20 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v64);
      if ( UuidFromStringW(v20, &Uuid) )
      {
        v21 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v64);
        v22 = UuidFromStringW(v21, &Uuid) | 0x80010000;
      }
      else
      {
        v22 = 0;
      }
      if ( v22 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x213,
          (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
          (const char *)(unsigned int)v22,
          phkResulta);
      std::wstring::_Tidy_deallocate(v64);
    }
    *this = Uuid;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    std::wstring::_Tidy_deallocate(v68);
    v47 = (wil::details *)psz;
    psz = 0;
    if ( v47 )
      wil::details::FreeProcessHeap(v47, v44);
    result = this;
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x24C, v45, v46);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x24D, v49, v50);
  }
  if ( PersistedStateLocation < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
      (const char *)(unsigned int)PersistedStateLocation,
      (int)pvData);
}

```

## disassembly

```asm
0x180012f90  push    rbx
0x180012f92  push    rsi
0x180012f93  push    rdi
0x180012f94  push    r14
0x180012f96  sub     rsp, 438h
0x180012f9d  mov     rax, cs:__security_cookie
0x180012fa4  xor     rax, rsp
0x180012fa7  mov     [rsp+458h+var_38], rax
0x180012faf  mov     rdi, rdx
0x180012fb2  mov     rsi, rcx
0x180012fb5  xor     r14d, r14d
0x180012fb8  mov     dword ptr [rsp+458h+var_2B8], r14d
0x180012fc0  xor     edx, edx; Val
0x180012fc2  mov     r8d, 20Ah; Size
0x180012fc8  lea     rcx, [rsp+458h+var_248]; void *
0x180012fd0  call    memset_0
0x180012fd5  mov     edx, 105h
0x180012fda  mov     qword ptr [rsp+458h+var_400], rdx
0x180012fdf  mov     [rsp+458h+psz], r14
0x180012fe4  xorps   xmm0, xmm0
0x180012fe7  movups  xmmword ptr [rsp+458h+Uuid.Data1], xmm0
0x180012fef  lea     rcx, [rsp+458h+var_288]
0x180012ff7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180012ffc  nop
0x180012ffd  mov     [rsp+458h+StringUuid], r14
0x180013002  mov     [rsp+458h+hkey], r14
0x180013007  mov     [rsp+458h+pcbData], r14
0x18001300c  mov     dword ptr [rsp+458h+pvData], edx
0x180013010  lea     rax, [rsp+458h+var_248]
0x180013018  mov     [rsp+458h+phkResult], rax; unsigned int
0x18001301d  xor     r9d, r9d
0x180013020  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\CI"...
0x180013027  xor     edx, edx
0x180013029  lea     rcx, aCienrollments; "CIEnrollments"
0x180013030  call    cs:__imp_RtlGetPersistedStateLocation
0x180013036  mov     rcx, [rsp+458h]; this
0x18001303e  test    eax, eax
0x180013040  jns     short loc_180013056
0x180013042  mov     r9d, eax; char *
0x180013045  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x18001304c  mov     edx, 1F8h; void *
0x180013051  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180013056  lea     rdx, [rsp+458h+var_248]
0x18001305e  lea     rcx, [rsp+458h+var_2D8]
0x180013066  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001306b  mov     rdx, rax
0x18001306e  lea     rcx, [rsp+458h+var_288]
0x180013076  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001307b  lea     rcx, [rsp+458h+var_2D8]
0x180013083  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013088  lea     rdx, [rsp+458h+StringUuid]; StringUuid
0x18001308d  mov     rcx, rdi; Uuid
0x180013090  call    cs:__imp_UuidToStringW
0x180013096  mov     rcx, [rsp+458h]; this
0x18001309e  test    eax, eax
0x1800130a0  jz      short loc_1800130AF
0x1800130a2  mov     r9d, eax; char *
0x1800130a5  mov     edx, 1FBh; void *
0x1800130aa  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800130af  mov     rdx, [rsp+458h+StringUuid]
0x1800130b4  lea     rcx, [rsp+458h+var_268]
0x1800130bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800130c1  mov     rbx, rax
0x1800130c4  lea     rdx, asc_18002ED88; "\\"
0x1800130cb  lea     rcx, [rsp+458h+var_2B8]
0x1800130d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800130d8  mov     rdx, rax
0x1800130db  lea     rcx, [rsp+458h+var_288]
0x1800130e3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800130e8  mov     r8, rax
0x1800130eb  mov     r9, [rsp+458h+var_278]
0x1800130f3  mov     rcx, rdx
0x1800130f6  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x1800130fb  mov     rdx, rax
0x1800130fe  lea     rcx, [rsp+458h+var_2F8]
0x180013106  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001310b  nop
0x18001310c  mov     r9, rbx
0x18001310f  lea     r8, [rsp+458h+var_2F8]
0x180013117  lea     rcx, [rsp+458h+var_2D8]
0x18001311f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x180013124  lea     rdx, [rsp+458h+var_2D8]
0x18001312c  lea     rcx, [rsp+458h+var_288]
0x180013134  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180013139  lea     rcx, [rsp+458h+var_2D8]
0x180013141  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013146  nop
0x180013147  lea     rcx, [rsp+458h+var_2F8]
0x18001314f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013154  nop
0x180013155  lea     rcx, [rsp+458h+var_2B8]
0x18001315d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013162  nop
0x180013163  lea     rcx, [rsp+458h+var_268]
0x18001316b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013170  lea     rax, [rsp+458h+hkey]
0x180013175  mov     [rsp+458h+var_2B8], rax
0x18001317d  mov     [rsp+458h+var_2B8+8], r14
0x180013185  mov     [rsp+458h+var_2A8], 1
0x18001318d  lea     rcx, [rsp+458h+var_288]
0x180013195  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001319a  mov     rdx, rax; lpSubKey
0x18001319d  lea     rax, [rsp+458h+var_2B8+8]
0x1800131a5  mov     [rsp+458h+phkResult], rax; int
0x1800131aa  mov     r9d, 20019h; samDesired
0x1800131b0  xor     r8d, r8d; ulOptions
0x1800131b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800131ba  call    cs:__imp_RegOpenKeyExW
0x1800131c0  mov     ebx, eax
0x1800131c2  test    eax, eax
0x1800131c4  jle     short loc_1800131CF
0x1800131c6  movzx   ebx, ax
0x1800131c9  or      ebx, 80070000h
0x1800131cf  lea     rcx, [rsp+458h+var_2B8]
0x1800131d7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800131dc  test    ebx, ebx
0x1800131de  js      loc_1800132D2
0x1800131e4  lea     rax, [rsp+458h+var_400]
0x1800131e9  mov     [rsp+458h+pcbData], rax; pcbData
0x1800131ee  lea     rax, [rsp+458h+var_248]
0x1800131f6  mov     [rsp+458h+pvData], rax; pvData
0x1800131fb  mov     [rsp+458h+phkResult], r14; int
0x180013200  mov     r9d, 2; dwFlags
0x180013206  lea     r8, Value; "TenantID"
0x18001320d  xor     edx, edx; lpSubKey
0x18001320f  mov     rcx, [rsp+458h+hkey]; hkey
0x180013214  call    cs:__imp_RegGetValueW
0x18001321a  mov     rcx, [rsp+458h]; this
0x180013222  test    eax, eax
0x180013224  jz      short loc_180013233
0x180013226  mov     r9d, eax; char *
0x180013229  mov     edx, 20Eh; void *
0x18001322e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180013233  mov     r8, qword ptr [rsp+458h+var_400]
0x180013238  shr     r8, 1
0x18001323b  sub     r8, 3
0x18001323f  lea     rdx, [rsp+458h+var_248+2]
0x180013247  lea     rcx, [rsp+458h+var_2D8]
0x18001324f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180013254  nop
0x180013255  lea     rcx, [rsp+458h+var_2D8]
0x18001325d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013262  mov     rcx, rax; StringUuid
0x180013265  lea     rdx, [rsp+458h+Uuid]; Uuid
0x18001326d  call    cs:__imp_UuidFromStringW
0x180013273  test    eax, eax
0x180013275  jz      short loc_18001329C
0x180013277  lea     rcx, [rsp+458h+var_2D8]
0x18001327f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013284  mov     rcx, rax; StringUuid
0x180013287  lea     rdx, [rsp+458h+Uuid]; Uuid
0x18001328f  call    cs:__imp_UuidFromStringW
0x180013295  or      eax, 80010000h
0x18001329a  jmp     short loc_18001329F
0x18001329c  mov     eax, r14d
0x18001329f  mov     rcx, [rsp+458h]; this
0x1800132a7  test    eax, eax
0x1800132a9  jns     short loc_1800132C0
0x1800132ab  mov     r9d, eax; char *
0x1800132ae  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x1800132b5  mov     edx, 213h; void *
0x1800132ba  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800132c0  lea     rcx, [rsp+458h+var_2D8]
0x1800132c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800132cd  jmp     loc_1800135E8
0x1800132d2  cmp     ebx, 80070002h
0x1800132d8  jnz     loc_180013626
0x1800132de  xor     edx, edx; hFile
0x1800132e0  mov     r8d, 800h; dwFlags
0x1800132e6  lea     rcx, LibFileName; "dmenrollengine.dll"
0x1800132ed  call    cs:__imp_LoadLibraryExW
0x1800132f3  mov     [rsp+458h+var_3F8], rax
0x1800132f8  test    rax, rax
0x1800132fb  jnz     short loc_18001330F
0x1800132fd  mov     rcx, [rsp+458h]; this
0x180013305  mov     edx, 21Ah; void *
0x18001330a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001330f  lea     rdx, aGetenrollmentt; "GetEnrollmentTenantID"
0x180013316  mov     rcx, rax; hModule
0x180013319  call    cs:__imp_GetProcAddress
0x18001331f  test    rax, rax
0x180013322  jnz     short loc_180013336
0x180013324  mov     rcx, [rsp+458h]; this
0x18001332c  mov     edx, 221h; void *
0x180013331  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180013336  lea     rcx, [rsp+458h+psz]
0x18001333b  mov     [rsp+458h+var_2F8], rcx
0x180013343  mov     [rsp+458h+var_2F0], r14
0x18001334b  mov     [rsp+458h+var_2E8], 1
0x180013353  movups  xmm0, xmmword ptr [rdi]
0x180013356  movdqu  xmmword ptr [rsp+458h+var_2B8], xmm0
0x18001335f  lea     rdx, [rsp+458h+var_2F0]
0x180013367  lea     rcx, [rsp+458h+var_2B8]
0x18001336f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013374  mov     ebx, eax
0x180013376  lea     rcx, [rsp+458h+var_2F8]
0x18001337e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>(void)
0x180013383  test    ebx, ebx
0x180013385  js      short loc_180013392
0x180013387  mov     rcx, [rsp+458h+psz]
0x18001338c  cmp     [rcx], r14w
0x180013390  jnz     short loc_1800133EF
0x180013392  lea     rax, [rsp+458h+psz]
0x180013397  mov     [rsp+458h+var_2F8], rax
0x18001339f  mov     [rsp+458h+var_2F0], r14
0x1800133a7  mov     [rsp+458h+var_2E8], 1
0x1800133af  lea     rdx, [rsp+458h+var_2F0]
0x1800133b7  call    NetGetAadTenantID
0x1800133bc  mov     rcx, [rsp+458h]; this
0x1800133c4  test    eax, eax
0x1800133c6  jns     short loc_1800133DD
0x1800133c8  mov     r9d, eax; char *
0x1800133cb  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x1800133d2  mov     edx, 228h; void *
0x1800133d7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800133dd  lea     rcx, [rsp+458h+var_2F8]
0x1800133e5  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>(void)
0x1800133ea  mov     rcx, [rsp+458h+psz]; psz
0x1800133ef  test    rcx, rcx
0x1800133f2  jz      short loc_180013408
0x1800133f4  lea     r8, [rsp+458h+var_2B8]; pcchLength
0x1800133fc  mov     edx, 7FFFFFFFh; cchMax
0x180013401  call    StringLengthWorkerW
0x180013406  jmp     short loc_18001340D
0x180013408  mov     eax, 80070057h
0x18001340d  mov     rcx, [rsp+458h]; this
0x180013415  test    eax, eax
0x180013417  jns     short loc_18001342D
0x180013419  mov     r9d, eax; char *
0x18001341c  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180013423  mov     edx, 22Bh; void *
0x180013428  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001342d  lea     rcx, [rsp+458h+var_3E8]
0x180013432  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180013437  nop
0x180013438  lea     rdx, asc_18002F8DC; "{"
0x18001343f  lea     rcx, [rsp+458h+var_3E8]
0x180013444  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180013449  mov     rdx, [rsp+458h+psz]
0x18001344e  mov     rcx, rax
0x180013451  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180013456  lea     rdx, asc_18002F8D8; "}"
0x18001345d  mov     rcx, rax
0x180013460  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180013465  lea     rdx, [rsp+458h+Uuid]; Uuid
0x18001346d  mov     rcx, [rsp+458h+psz]; StringUuid
0x180013472  call    cs:__imp_UuidFromStringW
0x180013478  test    eax, eax
0x18001347a  jz      short loc_180013496
0x18001347c  lea     rdx, [rsp+458h+Uuid]; Uuid
0x180013484  mov     rcx, [rsp+458h+psz]; StringUuid
0x180013489  call    cs:__imp_UuidFromStringW
0x18001348f  or      eax, 80010000h
0x180013494  jmp     short loc_180013499
0x180013496  mov     eax, r14d
0x180013499  mov     rcx, [rsp+458h]; this
0x1800134a1  test    eax, eax
0x1800134a3  jns     short loc_1800134B9
0x1800134a5  mov     r9d, eax; char *
0x1800134a8  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x1800134af  mov     edx, 232h; void *
0x1800134b4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800134b9  lea     rax, [rsp+458h+hkey]
0x1800134be  mov     [rsp+458h+var_2F8], rax
0x1800134c6  mov     [rsp+458h+var_2F0], r14
0x1800134ce  mov     [rsp+458h+var_2E8], 1
0x1800134d6  lea     rcx, [rsp+458h+var_288]
0x1800134de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800134e3  mov     rdx, rax; lpSubKey
0x1800134e6  lea     r8, [rsp+458h+var_2F0]; phkResult
0x1800134ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800134f5  call    cs:__imp_RegCreateKeyW
0x1800134fb  mov     rcx, [rsp+458h]; this
0x180013503  test    eax, eax
0x180013505  jz      short loc_180013515
0x180013507  mov     r9d, eax; char *
0x18001350a  mov     edx, 237h; void *
0x18001350f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180013515  lea     rcx, [rsp+458h+var_2F8]
0x18001351d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180013522  nop
0x180013523  lea     rcx, [rsp+458h+var_2D8]
0x18001352b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013530  mov     dword ptr [rsp+458h+var_2B8], 0Bh
0x18001353b  lea     rdx, [rsp+458h+var_2F8]
0x180013543  lea     rcx, [rsp+458h+var_3E0]
0x180013548  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x18001354d  mov     rdx, [rsp+458h+var_2F8]
0x180013555  test    rdx, rdx
0x180013558  jz      short loc_180013570
0x18001355a  mov     r8, [rsp+458h+var_2F0]
0x180013562  lea     rcx, [rsp+458h+var_2D8]
0x18001356a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18001356f  nop
0x180013570  mov     eax, [rsp+458h+var_2C8]
0x180013577  lea     edx, [rax+rax]
0x18001357a  lea     rcx, [rsp+458h+var_2D8]
0x180013582  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013587  mov     dword ptr [rsp+458h+pvData], edx; cbData
0x18001358b  mov     [rsp+458h+phkResult], rax; unsigned int
  ... truncated ...
```
