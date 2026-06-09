# InstallQueue::InstallProductsForUser(CallerContext const &,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IFulfillmentDataInfo *> *,WindowsUpdate::Internal::InstallType,ulong,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,bool,bool,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IInstallItem *> * *)

- ea: `0x1800555f0`
- end: `0x180056afa`
- name: `?InstallProductsForUser@InstallQueue@@QEAAJAEBVCallerContext@@PEAU?$IVectorView@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@W4InstallType@Internal@WindowsUpdate@@KPEAUHSTRING__@@333_N4PEAPEAU?$IVectorView@PEAUIInstallItem@Internal@WindowsUpdate@@@456@@Z`
- size: `5386`
- prototype: `__int64 __usercall@<rax>(InstallQueue *this@<rcx>, int, __int64, HSTRING, __int64, HSTRING string, char, int, __int64)`
- caller_count: `3`
- callee_count: `47`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800287e0`
- `0x180028990`
- `0x180028af0`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x1800127c8`
- `0x18001af10`
- `0x18001bf24`
- `0x18001c414`
- `0x18001ddb0`
- `0x18001e03c`
- `0x180020960`
- `0x180028cd4`
- `0x18002c310`
- `0x18002cec8`
- `0x18002ec2c`
- `0x18002f214`
- `0x180033188`
- `0x1800331d4`
- `0x18003f884`
- `0x18004c9fc`
- `0x18004cd44`
- `0x18004cf74`
- `0x18004e364`
- `0x18004e44c`
- `0x18004e938`
- `0x18004ea48`
- `0x18004eb3c`
- `0x18004f73c`
- `0x18004fa08`
- `0x18004febc`
- `0x1800509c8`
- `0x1800514a8`
- `0x180051508`
- `0x180052268`
- `0x1800555f0`
- `0x1800578cc`
- `0x18005bccc`
- `0x18005bdd8`
- `0x18005c03c`
- `0x18005cf90`
- `0x18005d568`
- `0x18005da40`
- `0x18005e110`
- `0x180061fb0`
- `0x180063178`
- `0x180064ffc`
- `0x1801db6f0`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180055828`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180055828`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18005579f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18005579f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005596b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055ae5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055bd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055cc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055cf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055ee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005609e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800560b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005596b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055ae5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055bd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055cc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055cf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055ee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005609e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800560b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800556bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005589b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800558a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055dbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800556bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005589b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800558a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055dbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056128`

## string_xrefs

- `0x180055b1c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800556e4`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180055726`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800557da`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800557f5`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180055880`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800558e4`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180056604`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005688a`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x1800556d2`: `Only admins are allowed to install for all users. cv = %ws`
- `0x1800558d7`: `InstallQueue::InstallProductsForUser`
- `0x180055dff`: `InstallQueue::InstallProductsForUser`
- `0x180056151`: `InstallQueue::InstallProductsForUser`
- `0x1800563ce`: `InstallQueue::InstallProductsForUser`
- `0x180055deb`: `Install request: productId = %s. Item already found queued up. Updating with VolumePath = %s, Flags = %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=39 #try_helpers=1
__int64 __fastcall InstallQueue::InstallProductsForUser(
        InstallQueue *this,
        struct WindowsUpdate::Internal::InstallItem *a2,
        HSTRING a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        HSTRING a7,
        __int64 a8,
        HSTRING string,
        char a10,
        char a11,
        _QWORD *a12)
{
  InstallQueue *v12; // r13
  HSTRING v13; // r14
  HSTRING v14; // rdi
  unsigned int v15; // esi
  TokenHelpers *v16; // rcx
  const char *StringRawBuffer; // rax
  __int64 v18; // rcx
  int v19; // eax
  PCWSTR v20; // rax
  int v21; // eax
  unsigned __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // ebx
  __int64 v27; // rcx
  int v28; // eax
  WindowsUpdate::Internal::InstallItem *v29; // rbx
  __int64 (__fastcall *v30)(WindowsUpdate::Internal::InstallItem *, GUID *, HSTRING *); // rdi
  int v31; // eax
  int v32; // eax
  int i; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD, HSTRING *); // rbx
  int v36; // eax
  int v37; // eax
  int j; // eax
  HSTRING v39; // rbx
  void (__fastcall *v40)(HSTRING, HSTRING *); // rdi
  __int64 (__fastcall *v41)(HSTRING, HSTRING *); // rdi
  int v42; // eax
  __int64 v43; // rcx
  char v44; // al
  __int64 v45; // rcx
  const unsigned __int16 *v46; // rax
  int updated; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  int v52; // eax
  __int64 v53; // rdx
  HSTRING v54; // rcx
  int v55; // eax
  HSTRING v56; // rbx
  _QWORD *v57; // rsi
  HSTRING v58; // rsi
  HSTRING v59; // r13
  __int64 v60; // r14
  __int64 (__fastcall *v61)(__int64, HSTRING *); // rdi
  int v62; // eax
  char v63; // r14
  int v64; // eax
  HSTRING v65; // rdi
  InstallQueue *v66; // rdi
  int inserted; // eax
  int v68; // eax
  const char *v69; // r9
  __int64 v70; // rsi
  __int64 (__fastcall *v71)(__int64, HSTRING *); // rdi
  int v72; // eax
  __int64 v73; // rcx
  unsigned __int128 v74; // kr20_16
  __int64 v75; // rsi
  int v76; // eax
  int v77; // eax
  __int64 v78; // rcx
  HSTRING m; // rax
  HSTRING k; // rcx
  HSTRING v81; // r14
  HSTRING n; // rdi
  HSTRING v83; // rbx
  __int64 v84; // r13
  struct WindowsUpdate::Internal::InstallItem *v85; // rbx
  int v86; // eax
  int v87; // eax
  __int64 v88; // rcx
  unsigned __int128 v89; // kr40_16
  const char *v90; // r9
  int v91; // eax
  struct WindowsUpdate::Internal::InstallItem *v92; // rbx
  int ii; // eax
  const char *v94; // r9
  __int64 v95; // rdi
  __int64 jj; // rbx
  int v97; // [rsp+20h] [rbp-398h]
  int v98; // [rsp+58h] [rbp-360h]
  HSTRING v99; // [rsp+70h] [rbp-348h] BYREF
  HSTRING v100; // [rsp+78h] [rbp-340h] BYREF
  HSTRING v101; // [rsp+80h] [rbp-338h] BYREF
  WindowsUpdate::Internal::InstallItem *v102; // [rsp+88h] [rbp-330h] BYREF
  HSTRING v103; // [rsp+90h] [rbp-328h] BYREF
  HSTRING v104; // [rsp+98h] [rbp-320h] BYREF
  unsigned __int128 v105; // [rsp+A0h] [rbp-318h] BYREF
  HSTRING v106; // [rsp+B0h] [rbp-308h] BYREF
  unsigned int v107; // [rsp+B8h] [rbp-300h] BYREF
  HSTRING newString; // [rsp+C0h] [rbp-2F8h] BYREF
  HSTRING v109; // [rsp+C8h] [rbp-2F0h] BYREF
  __int64 v110; // [rsp+D0h] [rbp-2E8h] BYREF
  HSTRING v111; // [rsp+D8h] [rbp-2E0h] BYREF
  InstallQueue *v112; // [rsp+E0h] [rbp-2D8h]
  HSTRING v113; // [rsp+E8h] [rbp-2D0h] BYREF
  int v114; // [rsp+F0h] [rbp-2C8h]
  __int64 v115; // [rsp+F8h] [rbp-2C0h] BYREF
  struct WindowsUpdate::Internal::InstallItem *v116; // [rsp+100h] [rbp-2B8h]
  _QWORD *v117; // [rsp+108h] [rbp-2B0h]
  struct WindowsUpdate::Internal::InstallItem *v118; // [rsp+110h] [rbp-2A8h] BYREF
  _QWORD v119[2]; // [rsp+118h] [rbp-2A0h] BYREF
  HSTRING v120; // [rsp+128h] [rbp-290h] BYREF
  __int64 v121; // [rsp+130h] [rbp-288h] BYREF
  __int128 v122; // [rsp+138h] [rbp-280h] BYREF
  __int64 v123; // [rsp+148h] [rbp-270h]
  __int64 v124; // [rsp+150h] [rbp-268h] BYREF
  __int128 v125; // [rsp+158h] [rbp-260h] BYREF
  HSTRING v126; // [rsp+168h] [rbp-250h] BYREF
  __int64 v127; // [rsp+170h] [rbp-248h] BYREF
  HSTRING v128; // [rsp+178h] [rbp-240h] BYREF
  InstallQueue *v129; // [rsp+180h] [rbp-238h]
  _QWORD v130[2]; // [rsp+188h] [rbp-230h] BYREF
  __int64 v131; // [rsp+198h] [rbp-220h] BYREF
  __int64 v132; // [rsp+1A0h] [rbp-218h]
  HSTRING v133; // [rsp+1A8h] [rbp-210h]
  char v134[8]; // [rsp+1B0h] [rbp-208h] BYREF
  int v135; // [rsp+1B8h] [rbp-200h]
  char v136[8]; // [rsp+1C0h] [rbp-1F8h] BYREF
  HSTRING v137; // [rsp+1C8h] [rbp-1F0h] BYREF
  char v138[144]; // [rsp+1D0h] [rbp-1E8h] BYREF
  unsigned __int16 v139[136]; // [rsp+260h] [rbp-158h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]
  int v141; // [rsp+3D8h] [rbp+20h] BYREF

  v141 = a4;
  v116 = a2;
  v12 = this;
  v112 = this;
  v129 = this;
  v118 = a2;
  v126 = a3;
  v124 = a6;
  v13 = a7;
  v111 = a7;
  v120 = a7;
  v127 = a8;
  v14 = string;
  v109 = string;
  v117 = a12;
  *a12 = 0;
  v15 = a5;
  if ( (a5 & 0x2000) != 0 )
  {
    v16 = (TokenHelpers *)*((_QWORD *)a2 + 2);
    if ( !v16 || !TokenHelpers::IsAdmin(v16, a2) )
    {
      StringRawBuffer = (const char *)WindowsGetStringRawBuffer(v14, 0);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)0x80070005LL,
        (int)"Only admins are allowed to install for all users. cv = %ws",
        StringRawBuffer);
    }
  }
  v110 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
  v19 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IInstallItem,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IInstallItem *>,0>>(
          v18,
          &v110);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      (const char *)(unsigned int)v19,
      v97);
  v121 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v121);
  LODWORD(v99) = 300000;
  v101 = (HSTRING)v12;
  Microsoft::WRL::Details::MakeAndInitialize<InstallQueue::SuspendScope,IInspectable,unsigned int &,InstallQueue *>(
    &v121,
    &v99,
    &v101);
  newString = 0;
  if ( !v14 )
    goto LABEL_12;
  v20 = WindowsGetStringRawBuffer(v14, 0);
  _o_wcstombs(v138, v20, 129);
  if ( TraceLoggingCorrelationVector::Validate(v138) )
  {
    v21 = Microsoft::WRL::Wrappers::HString::Set(&newString, &v109);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v21,
        v97);
  }
  if ( !newString )
  {
LABEL_12:
    TraceLoggingCorrelationVector::Increment((InstallQueue *)((char *)v12 + 48), v138);
    _o_mbstowcs(v139, v138, 129);
    LODWORD(v99) = 0;
    v22 = -1;
    do
      ++v22;
    while ( v139[v22] );
    v23 = ULongLongToUInt(v22, (unsigned int *)&v99);
    if ( v23 >= 0 )
      v23 = Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)&newString,
              v139,
              (unsigned int)v99);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v23,
        v97);
    WindowsGetStringRawBuffer(newString, 0);
    WindowsGetStringRawBuffer(v14, 0);
    LogMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      0xFFu,
      "InstallQueue::InstallProductsForUser",
      -1,
      L"Empty or Invalid Correlation Vector cvIn = %s. Using CV from queue cv = %s",
      0,
      0);
  }
  v125 = 0;
  std::_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>::_Alloc_sentinel_and_proxy(&v125);
  v107 = 0;
  v24 = (*(__int64 (__fastcall **)(HSTRING, unsigned int *))(*(_QWORD *)v126 + 56LL))(v126, &v107);
  v25 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      (const char *)(unsigned int)v24,
      v97);
    std::_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>::~_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>(&v125);
    WindowsDeleteString(newString);
    newString = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v121);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
    return v25;
  }
  if ( v107 > 1 )
  {
    v102 = 0;
    v100 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
    v28 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
            v27,
            &v102);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v28,
        v97);
    v29 = v102;
    v30 = **(__int64 (__fastcall ***)(WindowsUpdate::Internal::InstallItem *, GUID *, HSTRING *))v102;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v100);
    v31 = v30(v29, &GUID_98b9acc1_4b56_532e_ac73_03d5291cca90, &v100);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v31,
        v97);
    v119[0] = &v126;
    v119[1] = &v100;
    v32 = ForeachInstallWorkFactory__lambda_839672c131b18dc4a7abad89d951fa4c_(v119);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v32,
        v97);
    v101 = v100;
    *(_QWORD *)&v105 = v100;
    DWORD2(v105) = 0;
    v106 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
      &v101,
      &v131);
    for ( i = DWORD2(v105); i != (_DWORD)v132; i = ++DWORD2(v105) )
    {
      v34 = v105;
      v35 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v105 + 48LL);
      WindowsDeleteString(v106);
      v106 = 0;
      v36 = v35(v34, DWORD2(v105), &v106);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v36,
          v97);
      v103 = 0;
      v101 = v106;
      v37 = Microsoft::WRL::Wrappers::HString::Set(&v103, &v101);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v37,
          v97);
      std::_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString>(
        &v125,
        v119,
        &v103);
      WindowsDeleteString(v103);
    }
    WindowsDeleteString(v133);
    v133 = 0;
    WindowsDeleteString(v106);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v100);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
    v12 = v112;
    v15 = a5;
    v13 = v111;
  }
  std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(v130);
  std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(&v122);
  std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(&v131);
  v101 = v126;
  *(_QWORD *)&v105 = v126;
  DWORD2(v105) = 0;
  v106 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
    &v101,
    v134);
  for ( j = DWORD2(v105); j != v135; j = ++DWORD2(v105) )
  {
    v39 = *(HSTRING *)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v105);
    v103 = v39;
    if ( v39 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v39 + 8LL))(v39);
    v104 = 0;
    v40 = *(void (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v39 + 168LL);
    WindowsDeleteString(0);
    v104 = 0;
    v40(v39, &v104);
    v99 = 0;
    v41 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v39 + 48LL);
    WindowsDeleteString(0);
    v99 = 0;
    v42 = v41(v39, &v99);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v42,
        v97);
    std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(
      &v125,
      &v113,
      &v99);
    v44 = std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,bool,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,bool>>,0>>::_Lower_bound_duplicate<Microsoft::WRL::Wrappers::HString>(
            v43,
            v115,
            &v99);
    v45 = v125;
    if ( v44 )
      v45 = v115;
    if ( v45 != (_QWORD)v125 )
      goto LABEL_54;
    v102 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
    v46 = WindowsGetStringRawBuffer(v99, 0);
    if ( (int)InstallQueue::_FindInstallItem(v12, v46, &v102) >= 0 )
    {
      WindowsGetStringRawBuffer(v13, 0);
      WindowsGetStringRawBuffer(v99, 0);
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        0x137u,
        "InstallQueue::InstallProductsForUser",
        -1,
        L"Install request: productId = %s. Item already found queued up. Updating with VolumePath = %s, Flags = %x",
        0,
        0);
      updated = WindowsUpdate::Internal::InstallItem::UpdateProperties(v102, v13, v15, 0);
      if ( updated < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)updated,
          v97);
      if ( (v15 & 0x20) != 0 )
      {
        v48 = WindowsUpdate::Internal::InstallItem::Pause(v102, v15 & 1, newString);
        if ( v48 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x13D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v48,
            v97);
      }
      v49 = (*(__int64 (__fastcall **)(__int64, WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)v110 + 104LL))(
              v110,
              v102);
      if ( v49 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x13F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v49,
          v97);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
LABEL_54:
      WindowsDeleteString(v99);
      v99 = 0;
      WindowsDeleteString(v104);
      v104 = 0;
      goto LABEL_55;
    }
    if ( v104 )
    {
      std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::find(
        v130,
        &v101,
        &v104);
      if ( v101 == (HSTRING)v130[0] )
      {
        v100 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v100);
        v51 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(
                v50,
                &v100);
        if ( v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x149,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v51,
            v97);
        v52 = (*(__int64 (__fastcall **)(HSTRING, HSTRING))(*(_QWORD *)v100 + 104LL))(v100, v39);
        if ( v52 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v52,
            v97);
        v53 = *(_QWORD *)std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,>(
                           v130,
                           v119,
                           &v104);
        v54 = v100;
        v100 = 0;
        v109 = *(HSTRING *)(v53 + 40);
        *(_QWORD *)(v53 + 40) = v54;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v109);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v100);
      }
      else
      {
        v55 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)v101 + 5) + 104LL))(*((_QWORD *)v101 + 5), v39);
        if ( v55 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x14F,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v55,
            v97);
      }
    }
    else if ( *((_QWORD *)&v122 + 1) == v123 )
    {
      std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::IFulfillmentDataInfo>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::IFulfillmentDataInfo> const &>(
        &v122,
        *((_QWORD *)&v122 + 1),
        &v103);
    }
    else
    {
      **((_QWORD **)&v122 + 1) = v39;
      if ( v39 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v39 + 8LL))(v39);
      *((_QWORD *)&v122 + 1) += 8LL;
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
    WindowsDeleteString(v99);
    v99 = 0;
    WindowsDeleteString(v104);
LABEL_55:
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v103);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v136);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v106);
  v56 = *(HSTRING *)v130[0];
  v57 = v117;
LABEL_72:
  v109 = v56;
  while ( !*((_BYTE *)v56 + 25) )
  {
    InstallQueue::_FindWorkByCategoryId(v12, &v104, *((_QWORD *)v56 + 4));
    try
    {
      v58 = v104;
      if ( v104 )
      {
        WindowsGetStringRawBuffer(*((HSTRING *)v56 + 4), 0);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          0x15Eu,
          "InstallQueue::InstallProductsForUser",
          -1,
          L"Found Existing work for categoryId = %s. Adding to existing work",
          0,
          0);
        v100 = 0;
        v59 = v56 + 10;
        v60 = *((_QWORD *)v56 + 5);
        v61 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v60 + 64LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v100);
        v62 = v61(v60, &v100);
        if ( v62 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x160,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v62,
            v97);
        v63 = 1;
        v101 = v100;
        v113 = v100;
        v114 = 0;
        v115 = 0;
        wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
          &v101,
          v134);
        v64 = v114;
        while ( v64 != v135 )
        {
          v65 = *(HSTRING *)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v113);
          v101 = v65;
          if ( v65 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v65 + 8LL))(v65);
          LODWORD(v99) = 0;
          if ( (*(int (__fastcall **)(HSTRING, HSTRING, HSTRING *))(*(_QWORD *)v58 + 120LL))(v58, v65, &v99) < 0 )
          {
            LogSimpleMessage(
              2u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
              0x17Au,
              "InstallQueue::InstallProductsForUser",
              -1,
              L"Cannot Add fulfillment data to existing work. Creating a separate work item",
              0,
              0);
            v63 = 0;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
            break;
          }
          v111 = 0;
          v137 = v58;
          v128 = v65;
          v66 = v112;
          v119[0] = v112;
          wil::MakeOrThrow<WindowsUpdate::Internal::InstallItem,InstallQueue *,CallerContext,enum WindowsUpdate::Internal::InstallType &,unsigned long &,WindowsUpdate::Internal::IFulfillmentDataInfo *,WindowsUpdate::Internal::IInstallWork *,unsigned int &,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,WindowsUpdate::Internal::InstallWorkStatus *,bool>(
            (unsigned int)&v102,
            (unsigned int)v119,
            (_DWORD)v116,
            (unsigned int)&v141,
            (__int64)&a5,
            (__int64)&v128,
            (__int64)&v137,
            (__int64)&v99,
            (__int64)&v124,
            (__int64)&v120,
            (__int64)&v127,
            v98,
            (__int64)&v111);
          inserted = InstallQueue::_InsertInstallItem(v66, v102);
          if ( inserted < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x175,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
              (const char *)(unsigned int)inserted,
              v97);
          v68 = (*(__int64 (__fastcall **)(__int64, WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)v110 + 104LL))(
                  v110,
                  v102);
          if ( v68 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x176,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
              (const char *)(unsigned int)v68,
              v97);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
          v64 = ++v114;
          v111 = v120;
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v136);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v100);
        if ( v63 )
        {
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v104);
          v12 = v112;
LABEL_105:
          v13 = v111;
          goto LABEL_149;
        }
        v13 = v111;
      }
      else
      {
        v59 = v56 + 10;
      }
      v103 = 0;
      v70 = *(_QWORD *)v59;
      v71 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v59 + 64LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v103);
      v72 = v71(v70, &v103);
      if ( v72 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v72,
          v97);
      v12 = v112;
      WindowsUpdate::Internal::InstallItem::Create(
        (unsigned int)&v105,
        (_DWORD)v112,
        (_DWORD)v116,
        (_DWORD)v103,
        v141,
        a5,
        v124,
        (__int64)v13,
        v127,
        (__int64)newString,
        0,
        v98,
        a10);
      v73 = v105;
      v74 = v105;
      v75 = *((_QWORD *)&v105 + 1);
      while ( (_QWORD)v74 != v75 )
      {
        v76 = InstallQueue::_InsertInstallItem(v12, *(struct WindowsUpdate::Internal::InstallItem **)v74);
        if ( v76 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x189,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v76,
            v97);
        v77 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v110 + 104LL))(v110, *(_QWORD *)v74);
        if ( v77 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x18A,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v77,
            v97);
        v73 = v105;
        v74 = __PAIR128__(*((unsigned __int64 *)&v105 + 1), (__int64)v74 + 8);
      }
      if ( v73 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::IFulfillmentDataInfo>>>(
          v73,
          *((_QWORD *)&v74 + 1));
        std::_Deallocate<16>(v105, ((unsigned __int64)v106 - v105) & 0xFFFFFFFFFFFFFFF8uLL);
        v105 = 0;
        v106 = 0;
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v103);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v104);
      goto LABEL_105;
    }
    catch ( ... )
    {
      if ( a11 )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x191,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          v69);
        v56 = v109;
        v12 = v129;
        v112 = v129;
        v116 = v118;
        v13 = v120;
        v111 = v120;
        goto LABEL_149;
      }
      throw;
    }
LABEL_149:
    v57 = v117;
    v78 = *((_QWORD *)v56 + 2);
    if ( !*(_BYTE *)(v78 + 25) )
    {
      v56 = (HSTRING)*((_QWORD *)v56 + 2);
      for ( k = *(HSTRING *)v78; !*((_BYTE *)k + 25); k = *(HSTRING *)k )
        v56 = k;
      goto LABEL_72;
    }
    for ( m = (HSTRING)*((_QWORD *)v56 + 1);
          !*((_BYTE *)m + 25) && v56 == *((HSTRING *)m + 2);
          m = (HSTRING)*((_QWORD *)m + 1) )
    {
      v56 = m;
    }
    v56 = m;
    v109 = m;
  }
  v81 = (HSTRING)*((_QWORD *)&v122 + 1);
  v119[0] = *((_QWORD *)&v122 + 1);
  for ( n = (HSTRING)v122; ; n += 2 )
  {
    v103 = n;
    if ( n == v81 )
      break;
    v83 = *(HSTRING *)n;
    v128 = v83;
    if ( v83 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v83 + 8LL))(v83);
    try
    {
      CollectionHelpers::CreateVectorViewFromSingleObject<WindowsUpdate::Internal::IFulfillmentDataInfo>(&v109, v83);
      WindowsUpdate::Internal::InstallItem::Create(
        (unsigned int)&v105,
        (_DWORD)v12,
        (_DWORD)v116,
        (_DWORD)v109,
        v141,
        a5,
        v124,
        (__int64)v111,
        v127,
        (__int64)newString,
        0,
        v98,
        a10);
      v88 = v105;
      v89 = v105;
      v84 = *((_QWORD *)&v105 + 1);
      while ( (_QWORD)v89 != v84 )
      {
        v101 = *(HSTRING *)v89;
        v85 = (struct WindowsUpdate::Internal::InstallItem *)v101;
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v101);
        v86 = InstallQueue::_InsertInstallItem(v112, v85);
        if ( v86 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A0,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v86,
            v97);
        v87 = (*(__int64 (__fastcall **)(__int64, struct WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)v110 + 104LL))(
                v110,
                v85);
        if ( v87 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A1,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v87,
            v97);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
        v88 = v105;
        v89 = __PAIR128__(*((unsigned __int64 *)&v105 + 1), (__int64)v89 + 8);
      }
      if ( v88 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::IFulfillmentDataInfo>>>(
          v88,
          *((_QWORD *)&v89 + 1));
        std::_Deallocate<16>(v105, ((unsigned __int64)v106 - v105) & 0xFFFFFFFFFFFFFFF8uLL);
        v105 = 0;
        v106 = 0;
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v109);
      v12 = v112;
    }
    catch ( ... )
    {
      if ( a11 )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1A8,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          v90);
        n = v103;
        v81 = (HSTRING)v119[0];
        v12 = v129;
        v112 = v129;
        v116 = v118;
        v111 = v120;
        goto LABEL_128;
      }
      throw;
    }
LABEL_128:
    v57 = v117;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v128);
  }
  v91 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v110 + 64LL))(v110, v57);
  if ( v91 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      (const char *)(unsigned int)v91,
      v97);
  try
  {
    v119[0] = *v57;
    v113 = (HSTRING)v119[0];
    v114 = 0;
    v115 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
      v119,
      v134);
    for ( ii = v114; ii != v135; ii = ++v114 )
    {
      v92 = *(struct WindowsUpdate::Internal::InstallItem **)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v113);
      v118 = v92;
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v118);
      InstallQueue::_ScheduleInstallItem(v12, v92, 0, 0);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v118);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v136);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
    InstallQueue::_ExecuteInstallItems(v12);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      v94);
  }
  v95 = v131;
  if ( v131 )
  {
    for ( jj = v131; jj != v132; jj += 8 )
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(jj);
    std::_Deallocate<16>(v95, ((unsigned __int64)v133 - v95) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  if ( (_QWORD)v122 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::IFulfillmentDataInfo>>>(
      v122,
      *((_QWORD *)&v122 + 1));
    std::_Deallocate<16>(v122, (v123 - v122) & 0xFFFFFFFFFFFFFFF8uLL);
    v122 = 0;
    v123 = 0;
  }
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>(v130);
  std::_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>::~_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>(&v125);
  WindowsDeleteString(newString);
  newString = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v121);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
  return 0;
}

```

## disassembly

```asm
0x1800555f0  mov     r11, rsp
0x1800555f3  mov     [r11+20h], r9d
0x1800555f7  push    rbx
0x1800555f8  push    rsi
0x1800555f9  push    rdi
0x1800555fa  push    r12
0x1800555fc  push    r13
0x1800555fe  push    r14
0x180055600  push    r15
0x180055602  sub     rsp, 380h
0x180055609  mov     rax, cs:__security_cookie
0x180055610  xor     rax, rsp
0x180055613  mov     [rsp+3B8h+var_48], rax
0x18005561b  mov     [rsp+3B8h+var_2B8], rdx
0x180055623  mov     r13, rcx
0x180055626  mov     [rsp+3B8h+var_2D8], rcx
0x18005562e  mov     [rsp+3B8h+var_238], rcx
0x180055636  mov     [rsp+3B8h+var_2A8], rdx
0x18005563e  mov     [r11-250h], r8
0x180055645  mov     rax, [rsp+3B8h+arg_28]
0x18005564d  mov     [r11-268h], rax
0x180055654  mov     r14, [rsp+3B8h+arg_30]
0x18005565c  mov     [r11-2E0h], r14
0x180055663  mov     [r11-290h], r14
0x18005566a  mov     rax, [rsp+3B8h+arg_38]
0x180055672  mov     [r11-248h], rax
0x180055679  mov     rdi, [rsp+3B8h+string]
0x180055681  mov     [r11-2F0h], rdi
0x180055688  mov     rax, [rsp+3B8h+arg_58]
0x180055690  mov     [rsp+3B8h+var_2B0], rax
0x180055698  xor     r15d, r15d
0x18005569b  mov     [rax], r15
0x18005569e  mov     esi, [r11+28h]
0x1800556a2  bt      esi, 0Dh
0x1800556a6  jnb     short loc_1800556F5
0x1800556a8  mov     rcx, [rdx+10h]; this
0x1800556ac  test    rcx, rcx
0x1800556af  jz      short loc_1800556BA
0x1800556b1  call    ?IsAdmin@TokenHelpers@@YA_NPEAX@Z; TokenHelpers::IsAdmin(void *)
0x1800556b6  test    al, al
0x1800556b8  jnz     short loc_1800556F5
0x1800556ba  xor     edx, edx; length
0x1800556bc  mov     rcx, rdi; string
0x1800556bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800556c5  mov     rcx, [rsp+3B8h]; this
0x1800556cd  mov     [rsp+3B8h+var_390], rax; char *
0x1800556d2  lea     rax, aOnlyAdminsAreA; "Only admins are allowed to install for "...
0x1800556d9  mov     qword ptr [rsp+3B8h+var_398], rax; int
0x1800556de  mov     r9d, 80070005h; char *
0x1800556e4  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800556eb  mov     edx, 0E3h; void *
0x1800556f0  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800556f5  mov     [rsp+3B8h+var_2E8], r15
0x1800556fd  lea     rcx, [rsp+3B8h+var_2E8]
0x180055705  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005570a  lea     rdx, [rsp+3B8h+var_2E8]
0x180055712  call    ??$CreateExternalObjectVector@UIInstallItem@Internal@WindowsUpdate@@V?$AgileVector@PEAUIInstallItem@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIInstallItem@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInstallItem@Internal@WindowsUpdate@@@2567@$0A@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIInstallItem@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIInstallItem@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInstallItem@Internal@WindowsUpdate@@@2567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IInstallItem,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IInstallItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IInstallItem *>,0> * *)
0x180055717  mov     rcx, [rsp+3B8h]; this
0x18005571f  test    eax, eax
0x180055721  jns     short loc_180055737
0x180055723  mov     r9d, eax; char *
0x180055726  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005572d  mov     edx, 0E7h; void *
0x180055732  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055737  mov     [rsp+3B8h+var_288], r15
0x18005573f  lea     rcx, [rsp+3B8h+var_288]
0x180055747  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005574c  mov     dword ptr [rsp+3B8h+var_348], 493E0h
0x180055754  mov     [rsp+3B8h+var_338], r13
0x18005575c  lea     r8, [rsp+3B8h+var_338]
0x180055764  lea     rdx, [rsp+3B8h+var_348]
0x180055769  lea     rcx, [rsp+3B8h+var_288]
0x180055771  call    ??$MakeAndInitialize@VSuspendScope@InstallQueue@@UIInspectable@@AEAIPEAV2@@Details@WRL@Microsoft@@YAJPEAPEAUIInspectable@@AEAI$$QEAPEAVInstallQueue@@@Z; Microsoft::WRL::Details::MakeAndInitialize<InstallQueue::SuspendScope,IInspectable,uint &,InstallQueue *>(IInspectable * *,uint &,InstallQueue * &&)
0x180055776  mov     [rsp+3B8h+newString], r15
0x18005577e  test    rdi, rdi
0x180055781  jz      short loc_180055801
0x180055783  xor     edx, edx; length
0x180055785  mov     rcx, rdi; string
0x180055788  call    cs:__imp_WindowsGetStringRawBuffer
0x18005578e  mov     rdx, rax
0x180055791  mov     r8d, 81h
0x180055797  lea     rcx, [rsp+3B8h+var_1E8]
0x18005579f  call    cs:__imp__o_wcstombs
0x1800557a5  lea     rcx, [rsp+3B8h+var_1E8]; char *
0x1800557ad  call    ?Validate@TraceLoggingCorrelationVector@@SA_NPEBD@Z; TraceLoggingCorrelationVector::Validate(char const *)
0x1800557b2  test    al, al
0x1800557b4  jz      short loc_1800557EB
0x1800557b6  lea     rdx, [rsp+3B8h+var_2F0]; HSTRING *
0x1800557be  lea     rcx, [rsp+3B8h+newString]; newString
0x1800557c6  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800557cb  mov     rcx, [rsp+3B8h]; this
0x1800557d3  test    eax, eax
0x1800557d5  jns     short loc_1800557EB
0x1800557d7  mov     r9d, eax; char *
0x1800557da  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800557e1  mov     edx, 0F4h; void *
0x1800557e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800557eb  cmp     [rsp+3B8h+newString], r15
0x1800557f3  jz      short loc_180055801
0x1800557f5  lea     r12, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800557fc  jmp     loc_1800558F8
0x180055801  lea     rcx, [r13+30h]; this
0x180055805  lea     rdx, [rsp+3B8h+var_1E8]; char *
0x18005580d  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180055812  mov     r8d, 81h
0x180055818  lea     rdx, [rsp+3B8h+var_1E8]
0x180055820  lea     rcx, [rsp+3B8h+var_158]
0x180055828  call    cs:__imp__o_mbstowcs
0x18005582e  mov     dword ptr [rsp+3B8h+var_348], r15d
0x180055833  lea     rax, [rsp+3B8h+var_158]
0x18005583b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005583f  inc     rcx; unsigned __int64
0x180055842  cmp     [rax+rcx*2], r15w
0x180055847  jnz     short loc_18005583F
0x180055849  lea     rdx, [rsp+3B8h+var_348]; unsigned int *
0x18005584e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180055853  test    eax, eax
0x180055855  js      short loc_180055871
0x180055857  mov     r8d, dword ptr [rsp+3B8h+var_348]; unsigned int
0x18005585c  lea     rdx, [rsp+3B8h+var_158]; unsigned __int16 *
0x180055864  lea     rcx, [rsp+3B8h+newString]; this
0x18005586c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180055871  mov     rcx, [rsp+3B8h]; this
0x180055879  test    eax, eax
0x18005587b  jns     short loc_180055891
0x18005587d  mov     r9d, eax; char *
0x180055880  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x180055887  mov     edx, 0FBh; void *
0x18005588c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055891  xor     edx, edx; length
0x180055893  mov     rcx, [rsp+3B8h+newString]; string
0x18005589b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800558a1  mov     rbx, rax
0x1800558a4  xor     edx, edx; length
0x1800558a6  mov     rcx, rdi; string
0x1800558a9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800558af  mov     [rsp+3B8h+var_370], rbx
0x1800558b4  mov     [rsp+3B8h+var_378], rax
0x1800558b9  mov     [rsp+3B8h+var_380], r15; unsigned __int16 *
0x1800558be  mov     [rsp+3B8h+var_388], r15; char *
0x1800558c3  lea     rax, aEmptyOrInvalid; "Empty or Invalid Correlation Vector cvI"...
0x1800558ca  mov     [rsp+3B8h+var_390], rax; unsigned __int16 *
0x1800558cf  mov     [rsp+3B8h+var_398], 0FFFFFFFFh; int
0x1800558d7  lea     r9, aInstallqueueIn_0; "InstallQueue::InstallProductsForUser"
0x1800558de  mov     r8d, 0FFh; unsigned int
0x1800558e4  lea     r12, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x1800558eb  mov     rdx, r12; char *
0x1800558ee  mov     ecx, 2; unsigned int
0x1800558f3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800558f8  xorps   xmm0, xmm0
0x1800558fb  movdqu  [rsp+3B8h+var_260], xmm0
0x180055904  lea     rcx, [rsp+3B8h+var_260]
0x18005590c  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@VHString@Wrappers@WRL@Microsoft@@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@6@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>::_Alloc_sentinel_and_proxy(void)
0x180055911  nop
0x180055912  mov     [rsp+3B8h+var_300], r15d
0x18005591a  mov     rcx, [rsp+3B8h+var_250]
0x180055922  mov     rax, [rcx]
0x180055925  lea     rdx, [rsp+3B8h+var_300]
0x18005592d  mov     rax, [rax+38h]
0x180055931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055936  mov     ebx, eax
0x180055938  test    eax, eax
0x18005593a  jns     short loc_18005599B
0x18005593c  mov     rcx, [rsp+3B8h]; this
0x180055944  mov     r9d, eax; char *
0x180055947  mov     r8, r12; unsigned int
0x18005594a  mov     edx, 108h; void *
0x18005594f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055954  nop
0x180055955  lea     rcx, [rsp+3B8h+var_260]
0x18005595d  call    ??1?$_Tree@V?$_Tset_traits@VHString@Wrappers@WRL@Microsoft@@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>::~_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>(void)
0x180055962  nop
0x180055963  mov     rcx, [rsp+3B8h+newString]; string
0x18005596b  call    cs:__imp_WindowsDeleteString
0x180055971  mov     [rsp+3B8h+newString], r15
0x180055979  lea     rcx, [rsp+3B8h+var_288]
0x180055981  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180055986  nop
0x180055987  lea     rcx, [rsp+3B8h+var_2E8]
0x18005598f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180055994  mov     eax, ebx
0x180055996  jmp     loc_180056AD6
0x18005599b  cmp     [rsp+3B8h+var_300], 1
0x1800559a3  jbe     loc_180055C0B
0x1800559a9  mov     [rsp+3B8h+var_330], r15
0x1800559b1  mov     [rsp+3B8h+var_340], r15
0x1800559b6  lea     rcx, [rsp+3B8h+var_330]
0x1800559be  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800559c3  lea     rdx, [rsp+3B8h+var_330]
0x1800559cb  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x1800559d0  mov     rcx, [rsp+3B8h]; this
0x1800559d8  test    eax, eax
0x1800559da  jns     short loc_1800559ED
0x1800559dc  mov     r9d, eax; char *
0x1800559df  mov     r8, r12; unsigned int
0x1800559e2  mov     edx, 10Dh; void *
0x1800559e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800559ed  mov     rbx, [rsp+3B8h+var_330]
0x1800559f5  mov     rax, [rbx]
0x1800559f8  mov     rdi, [rax]
0x1800559fb  lea     rcx, [rsp+3B8h+var_340]
0x180055a00  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180055a05  lea     r8, [rsp+3B8h+var_340]
0x180055a0a  lea     rdx, _GUID_98b9acc1_4b56_532e_ac73_03d5291cca90
0x180055a11  mov     rcx, rbx
0x180055a14  mov     rax, rdi
0x180055a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a1c  nop
0x180055a1d  mov     rcx, [rsp+3B8h]; this
0x180055a25  test    eax, eax
0x180055a27  jns     short loc_180055A39
0x180055a29  mov     r9d, eax; char *
0x180055a2c  mov     r8, r12; unsigned int
0x180055a2f  mov     edx, 10Eh; void *
0x180055a34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055a39  lea     rax, [rsp+3B8h+var_250]
0x180055a41  mov     [rsp+3B8h+var_2A0], rax
0x180055a49  lea     rax, [rsp+3B8h+var_340]
0x180055a4e  mov     [rsp+3B8h+var_298], rax
0x180055a56  lea     rcx, [rsp+3B8h+var_2A0]
0x180055a5e  call    ForeachInstallWorkFactory__lambda_839672c131b18dc4a7abad89d951fa4c___; ForeachInstallWorkFactory__lambda_839672c131b18dc4a7abad89d951fa4c_
0x180055a63  mov     rcx, [rsp+3B8h]; this
0x180055a6b  test    eax, eax
0x180055a6d  jns     short loc_180055A7F
0x180055a6f  mov     r9d, eax; char *
0x180055a72  mov     r8, r12; unsigned int
0x180055a75  mov     edx, 114h; void *
0x180055a7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055a7f  mov     rax, [rsp+3B8h+var_340]
0x180055a84  mov     [rsp+3B8h+var_338], rax
0x180055a8c  mov     qword ptr [rsp+3B8h+var_318], rax
0x180055a94  mov     dword ptr [rsp+3B8h+var_318+8], r15d
0x180055a9c  mov     [rsp+3B8h+var_308], r15
0x180055aa4  lea     rdx, [rsp+3B8h+var_220]
0x180055aac  lea     rcx, [rsp+3B8h+var_338]
0x180055ab4  call    ?end@?$vector_range@U?$IVectorView@PEAVToastNotification@Notifications@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(void)
0x180055ab9  nop
0x180055aba  mov     eax, dword ptr [rsp+3B8h+var_318+8]
0x180055ac1  cmp     eax, dword ptr [rsp+3B8h+var_218]
0x180055ac8  jz      loc_180055BB7
0x180055ace  mov     rdi, qword ptr [rsp+3B8h+var_318]
0x180055ad6  mov     rax, [rdi]
0x180055ad9  mov     rbx, [rax+30h]
0x180055add  mov     rcx, [rsp+3B8h+var_308]; string
0x180055ae5  call    cs:__imp_WindowsDeleteString
0x180055aeb  mov     [rsp+3B8h+var_308], r15
0x180055af3  lea     r8, [rsp+3B8h+var_308]
0x180055afb  mov     edx, dword ptr [rsp+3B8h+var_318+8]
0x180055b02  mov     rcx, rdi
0x180055b05  mov     rax, rbx
0x180055b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b0d  mov     rcx, [rsp+3B8h]; this
0x180055b15  test    eax, eax
0x180055b17  jns     short loc_180055B2D
0x180055b19  mov     r9d, eax; char *
0x180055b1c  lea     r8, aOnecoreInterna_11; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180055b23  mov     edx, 1CBEh; void *
0x180055b28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055b2d  mov     [rsp+3B8h+var_328], r15
0x180055b35  mov     rax, [rsp+3B8h+var_308]
0x180055b3d  mov     [rsp+3B8h+var_338], rax
0x180055b45  lea     rdx, [rsp+3B8h+var_338]; HSTRING *
0x180055b4d  lea     rcx, [rsp+3B8h+var_328]; newString
0x180055b55  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180055b5a  mov     rcx, [rsp+3B8h]; this
0x180055b62  test    eax, eax
0x180055b64  jns     short loc_180055B76
0x180055b66  mov     r9d, eax; char *
0x180055b69  mov     r8, r12; unsigned int
0x180055b6c  mov     edx, 119h; void *
0x180055b71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055b76  lea     r8, [rsp+3B8h+var_328]
0x180055b7e  lea     rdx, [rsp+3B8h+var_2A0]
0x180055b86  lea     rcx, [rsp+3B8h+var_260]
0x180055b8e  call    ??$_Emplace@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tset_traits@VHString@Wrappers@WRL@Microsoft@@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@VHString@Wrappers@WRL@Microsoft@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<Microsoft::WRL::Wrappers::HString>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString &&)
0x180055b93  nop
0x180055b94  mov     rcx, [rsp+3B8h+var_328]; string
0x180055b9c  call    cs:__imp_WindowsDeleteString
0x180055ba2  mov     eax, dword ptr [rsp+3B8h+var_318+8]
0x180055ba9  inc     eax
0x180055bab  mov     dword ptr [rsp+3B8h+var_318+8], eax
0x180055bb2  jmp     loc_180055AC1
0x180055bb7  mov     rcx, [rsp+3B8h+var_210]; string
0x180055bbf  call    cs:__imp_WindowsDeleteString
0x180055bc5  mov     [rsp+3B8h+var_210], r15
0x180055bcd  mov     rcx, [rsp+3B8h+var_308]; string
0x180055bd5  call    cs:__imp_WindowsDeleteString
0x180055bdb  nop
0x180055bdc  lea     rcx, [rsp+3B8h+var_340]
0x180055be1  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180055be6  nop
0x180055be7  lea     rcx, [rsp+3B8h+var_330]
0x180055bef  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180055bf4  mov     r13, [rsp+3B8h+var_2D8]
0x180055bfc  mov     esi, [rsp+3B8h+arg_20]
0x180055c03  mov     r14, [rsp+3B8h+var_2E0]
0x180055c0b  lea     rcx, [rsp+3B8h+var_230]
0x180055c13  call    ??0?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@QEAA@XZ; std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(void)
0x180055c18  nop
0x180055c19  lea     rcx, [rsp+3B8h+var_280]; void *
  ... truncated ...
```
