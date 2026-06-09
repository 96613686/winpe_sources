# DmRaiseToastNotificationAndWait(ushort const *,uint,uint,ushort const *,ushort const *,ushort const *,_GUID const &,ulong,int *)

- ea: `0x1800704a0`
- end: `0x1800716a9`
- name: `?DmRaiseToastNotificationAndWait@@YAJPEBGII000AEBU_GUID@@KPEAH@Z`
- size: `4617`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLibFileName@<rcx>, UINT uID@<edx>, UINT@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void *, int *)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007270`
- `0x180051d48`
- `0x180053f9c`
- `0x180057c4c`
- `0x180057c6c`
- `0x18005bcd8`
- `0x18005fc38`
- `0x180064a44`
- `0x18006ed58`
- `0x18006ede8`
- `0x18006ee38`
- `0x18006eee8`
- `0x18006efac`
- `0x18006f070`
- `0x18006f2d0`
- `0x18006f2e8`
- `0x18006f824`
- `0x18006f8a8`
- `0x18006f9b4`
- `0x18006fc00`
- `0x18006fc44`
- `0x1800704a0`
- `0x1800719cc`
- `0x180071b24`
- `0x180071fd8`
- `0x1800724f0`
- `0x180072818`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800709ba`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800709ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180070876`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180070876`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800708dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007095b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800708dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007095b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007113d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007113d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007067f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800706c5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180070768`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180070a88`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180071358`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180071657`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007067f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800706c5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180070768`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180070a88`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180071358`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180071657`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007063d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180071022`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007063d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180071022`

## string_xrefs

- `0x180070efc`: `Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int64 __fastcall DmRaiseToastNotificationAndWait(
        LPCWSTR lpLibFileName,
        UINT uID,
        UINT a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *pszPath,
        const unsigned __int16 *a6,
        const struct _GUID *a7,
        void *a8,
        int *a9)
{
  int ShortcutPath; // eax
  unsigned int LastError; // ebx
  int FileNameNoExtension; // eax
  wchar_t *v15; // rbx
  int Shortcut; // eax
  int v17; // edi
  __int64 v18; // rdi
  int ActivationFactory; // eax
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rdi
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64, __int64 *); // rbx
  int v29; // eax
  HMODULE Library; // rax
  const char *v31; // r9
  HINSTANCE v32; // rbx
  __int64 v33; // rdx
  int StringW; // eax
  wchar_t *v35; // rdi
  __int64 v36; // rdx
  int v37; // eax
  wchar_t *v38; // rbx
  wchar_t *v39; // rax
  __int64 v40; // r14
  __int64 (__fastcall *v41)(__int64, _QWORD, __int64 *); // rsi
  int v42; // eax
  unsigned int v43; // esi
  __int64 v44; // r14
  __int64 (__fastcall *v45)(__int64, _QWORD, __int64 *); // rsi
  __int64 v46; // rax
  int v47; // eax
  int v48; // eax
  __int64 v49; // rsi
  __int64 (__fastcall *v50)(__int64, __int64, __int64 *); // rdi
  int v51; // eax
  __int64 v52; // rsi
  __int64 (__fastcall *v53)(__int64, __int64, __int64 *); // rdi
  int v54; // eax
  __int64 v55; // rsi
  __int64 (__fastcall *v56)(__int64, _QWORD, __int64 *); // rdi
  __int64 v57; // rax
  int v58; // eax
  int v59; // eax
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, __int64, __int64 *); // rbx
  int v62; // eax
  __int64 v63; // rdi
  __int64 (__fastcall *v64)(__int64, __int64, const unsigned __int16 **); // rbx
  int v65; // eax
  const unsigned __int16 *v66; // rdi
  __int64 (__fastcall *v67)(const unsigned __int16 *, _QWORD, _QWORD); // rbx
  int v68; // eax
  __int64 (__fastcall ***v69)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v70)(_QWORD, GUID *, __int64 *); // rdi
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rsi
  __int64 (__fastcall *v74)(__int64, __int64, __int64); // rdi
  __int64 v75; // rbx
  __int64 v76; // rsi
  __int64 (__fastcall *v77)(__int64, __int64, __int64); // rdi
  __int64 v78; // rbx
  __int64 v79; // rbx
  int v80; // eax
  __int64 v81; // rdi
  __int64 (__fastcall *v82)(__int64, __int64, const unsigned __int16 **); // rbx
  int v83; // eax
  int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // rdi
  __int64 (__fastcall *v87)(__int64, _QWORD); // rbx
  __int64 v88; // rax
  wchar_t *EventW; // rax
  __m128i si128; // xmm6
  char *v91; // rdi
  _QWORD *v92; // rsi
  char *v93; // r15
  volatile signed __int32 *v94; // rbx
  __int64 *v95; // rax
  __int64 v96; // r14
  int v97; // r12d
  __int64 v98; // rdx
  volatile signed __int32 *v99; // r15
  __int64 *v100; // rax
  __int64 v101; // r14
  const unsigned __int16 *v102; // r14
  __int64 (__fastcall *v103)(const unsigned __int16 *, __int64, __int64 *); // r15
  __int64 *v104; // rax
  __int64 v105; // rbx
  int v106; // eax
  unsigned int v107; // r8d
  int v108; // r9d
  unsigned __int64 v109; // r9
  __int64 v110; // rdx
  wil *v111; // rcx
  int v113[2]; // [rsp+28h] [rbp-E0h] BYREF
  wchar_t *v114; // [rsp+30h] [rbp-D8h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v116; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v117; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v118; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *v120; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v121; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v122; // [rsp+70h] [rbp-98h] BYREF
  __int64 v123; // [rsp+78h] [rbp-90h] BYREF
  __int64 v124; // [rsp+80h] [rbp-88h] BYREF
  __int64 v125; // [rsp+88h] [rbp-80h] BYREF
  __int64 v126; // [rsp+90h] [rbp-78h] BYREF
  __int64 v127; // [rsp+98h] [rbp-70h] BYREF
  __int64 v128; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v129; // [rsp+A8h] [rbp-60h] BYREF
  wchar_t *v130; // [rsp+B0h] [rbp-58h] BYREF
  const unsigned __int16 *v131; // [rsp+B8h] [rbp-50h] BYREF
  __int64 (__fastcall ***v132)(_QWORD, _QWORD, _QWORD); // [rsp+C0h] [rbp-48h] BYREF
  __int64 v133; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v134; // [rsp+D0h] [rbp-38h] BYREF
  const unsigned __int16 *v135; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v136; // [rsp+E0h] [rbp-28h] BYREF
  int v137; // [rsp+E8h] [rbp-20h] BYREF
  const unsigned __int16 *v138; // [rsp+F0h] [rbp-18h] BYREF
  int v139; // [rsp+F8h] [rbp-10h] BYREF
  const unsigned __int16 *v140; // [rsp+100h] [rbp-8h] BYREF
  WCHAR Buffer[4]; // [rsp+108h] [rbp+0h] BYREF
  WCHAR v142[4]; // [rsp+110h] [rbp+8h] BYREF
  __int64 v143; // [rsp+118h] [rbp+10h]
  __int64 v144; // [rsp+120h] [rbp+18h] BYREF
  __int64 v145; // [rsp+128h] [rbp+20h] BYREF
  __int64 v146; // [rsp+130h] [rbp+28h] BYREF
  int *v147; // [rsp+138h] [rbp+30h]
  LPCWSTR *p_lpFileName; // [rsp+140h] [rbp+38h]
  char v149; // [rsp+148h] [rbp+40h]
  HSTRING_HEADER hstringHeader; // [rsp+158h] [rbp+50h] BYREF
  __int64 v151; // [rsp+170h] [rbp+68h]
  HSTRING_HEADER v152; // [rsp+178h] [rbp+70h] BYREF
  __int64 v153; // [rsp+190h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+200h] [rbp+F8h]

  v135 = a4;
  v140 = a4;
  v138 = a6;
  v147 = a9;
  lpFileName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpFileName,
    0);
  ShortcutPath = GetShortcutPath(&lpFileName);
  LastError = ShortcutPath;
  if ( ShortcutPath >= 0 )
  {
    v114 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v114,
      0);
    FileNameNoExtension = GetFileNameNoExtension(pszPath);
    LastError = FileNameNoExtension;
    if ( FileNameNoExtension < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)FileNameNoExtension,
        v113[0]);
LABEL_5:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v114);
      goto LABEL_131;
    }
    v15 = v114;
    Shortcut = CreateShortcut(pszPath, lpFileName, v114, a7);
    v17 = Shortcut;
    if ( Shortcut < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)Shortcut,
        v113[0]);
LABEL_8:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v114);
      LastError = v17;
      goto LABEL_131;
    }
    p_lpFileName = &lpFileName;
    v149 = 1;
    *(_QWORD *)v113 = 0;
    v151 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.UI.Notifications.ToastNotificationManager",
      0x32u,
      0x31u);
    v18 = v151;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v113);
    ActivationFactory = RoGetActivationFactory(v18, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, v113);
    v17 = ActivationFactory;
    v151 = 0;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v113[0]);
LABEL_11:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v113);
      DeleteFileW(lpFileName);
      goto LABEL_8;
    }
    LOBYTE(v123) = 0;
    if ( (int)IsDup(v113, v15, a6, &v123) >= 0 && (_BYTE)v123 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v113);
      DeleteFileW(lpFileName);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v114);
      LastError = 1;
      goto LABEL_131;
    }
    v117 = 0;
    v20 = *(_QWORD *)v113;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v113 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
    v130 = v15;
    v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v130);
    v23 = v21(v20, *(_QWORD *)(v22 + 24), &v117);
    LastError = v23;
    v151 = 0;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v23,
        v113[0]);
LABEL_17:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v113);
      DeleteFileW(lpFileName);
      goto LABEL_5;
    }
    v116 = 0;
    v24 = *(_QWORD *)v113;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v113 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
    v26 = v25(v24, 5, &v116);
    LastError = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v26,
        v113[0]);
LABEL_20:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      goto LABEL_17;
    }
    v118 = 0;
    v27 = v116;
    v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v116 + 128LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
    v151 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"text", 5u, 4u);
    v29 = v28(v27, v151, &v118);
    LastError = v29;
    v151 = 0;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v29,
        v113[0]);
LABEL_23:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
      goto LABEL_20;
    }
    v120 = 0;
    Str = 0;
    Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
    v32 = Library;
    v132 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))Library;
    if ( !Library )
    {
      v33 = 323;
LABEL_26:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v33,
                    (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                    v31);
LABEL_27:
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v132);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v120);
      goto LABEL_23;
    }
    *(_QWORD *)Buffer = 0;
    StringW = LoadStringW(Library, uID, Buffer, 0);
    if ( !StringW )
    {
      v33 = 327;
      goto LABEL_26;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v133,
      *(_QWORD *)Buffer,
      StringW);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v120,
      &v133);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v133);
    v35 = v120;
    if ( !v120 )
    {
      v36 = 330;
LABEL_33:
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)0x8007000ELL,
        v113[0]);
      goto LABEL_27;
    }
    *(_QWORD *)v142 = 0;
    v37 = LoadStringW(v32, a3, v142, 0);
    if ( !v37 )
    {
      v33 = 334;
      goto LABEL_26;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v133,
      *(_QWORD *)v142,
      v37);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &Str,
      &v133);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v133);
    v38 = Str;
    if ( !Str )
    {
      v36 = 337;
      goto LABEL_33;
    }
    v39 = wcsstr(Str, &word_1800D1BD0);
    if ( v39 )
    {
      *(_DWORD *)v39 = 2621183;
      v39[2] = -257;
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v132);
    v121 = 0;
    v40 = v118;
    v41 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v118 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
    v42 = v41(v40, 0, &v121);
    v43 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v42,
        v113[0]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v120);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v113);
      DeleteFileW(lpFileName);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v114);
      LastError = v43;
      goto LABEL_131;
    }
    v122 = 0;
    v44 = v116;
    v45 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v116 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
    v130 = v35;
    v46 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v130);
    v47 = v45(v44, *(_QWORD *)(v46 + 24), &v122);
    v17 = v47;
    v151 = 0;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v47,
        v113[0]);
LABEL_44:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v120);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
      goto LABEL_11;
    }
    v124 = 0;
    v48 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlText>::As<Windows::Data::Xml::Dom::IXmlNode>(&v122, &v124);
    v17 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v48,
        v113[0]);
LABEL_47:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
      goto LABEL_44;
    }
    v126 = 0;
    v49 = v121;
    v50 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v121 + 176LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
    v51 = v50(v49, v124, &v126);
    v17 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v51,
        v113[0]);
LABEL_50:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
      goto LABEL_47;
    }
    v125 = 0;
    v52 = v118;
    v53 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v118 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
    v54 = v53(v52, 1, &v125);
    v17 = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16C,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v54,
        v113[0]);
LABEL_53:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
      goto LABEL_50;
    }
    v127 = 0;
    v55 = v116;
    v56 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v116 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
    v130 = v38;
    v57 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v130);
    v58 = v56(v55, *(_QWORD *)(v57 + 24), &v127);
    LastError = v58;
    v151 = 0;
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v58,
        v113[0]);
LABEL_56:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
      goto LABEL_28;
    }
    v128 = 0;
    v59 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlText>::As<Windows::Data::Xml::Dom::IXmlNode>(&v127, &v128);
    LastError = v59;
    if ( v59 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v59,
        v113[0]);
LABEL_59:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
      goto LABEL_56;
    }
    v129 = 0;
    v60 = v125;
    v61 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v125 + 176LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
    v62 = v61(v60, v128, &v129);
    LastError = v62;
    if ( v62 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v62,
        v113[0]);
LABEL_62:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
      goto LABEL_59;
    }
    if ( v135 )
    {
      v135 = 0;
      v63 = v116;
      v64 = *(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 **))(*(_QWORD *)v116 + 128LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
      v151 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"toast", 6u, 5u);
      v65 = v64(v63, v151, &v135);
      LastError = v65;
      v151 = 0;
      if ( v65 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17B,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
          (const char *)(unsigned int)v65,
          v113[0]);
LABEL_66:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
        goto LABEL_62;
      }
      v132 = 0;
      v66 = v135;
      v67 = *(__int64 (__fastcall **)(const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v135 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
      v68 = v67(v66, 0, &v132);
      LastError = v68;
      if ( v68 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17D,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
          (const char *)(unsigned int)v68,
          v113[0]);
LABEL_69:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
        goto LABEL_66;
      }
      v133 = 0;
      v69 = v132;
      v70 = (__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))**v132;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
      v71 = v70(v69, &GUID_2dfb8a1f_6b10_4ef8_9f83_efcce8faec37, &v133);
      LastError = v71;
      if ( v71 < 0 )
      {
        v72 = 383;
LABEL_72:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v72,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
          (const char *)(unsigned int)v71,
          v113[0]);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
        goto LABEL_69;
      }
      v73 = v133;
      v74 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v133 + 64LL);
      v153 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v152, L"Protocol", 9u, 8u);
      v75 = v153;
      v151 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"activationType", 0xFu, 0xEu);
      v71 = v74(v73, v151, v75);
      LastError = v71;
      v151 = 0;
      v153 = 0;
      if ( v71 < 0 )
      {
        v72 = 384;
        goto LABEL_72;
      }
      v76 = v133;
      v77 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v133 + 64LL);
      v78 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v152, &v140) + 24);
      v151 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"launch", 7u, 6u);
      v71 = v77(v76, v151, v78);
      LastError = v71;
      v151 = 0;
      v153 = 0;
      if ( v71 < 0 )
      {
        v72 = 385;
        goto LABEL_72;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
    }
    v134 = 0;
    v151 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.UI.Notifications.ToastNotification",
      0x2Bu,
      0x2Au);
    v79 = v151;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
    v80 = RoGetActivationFactory(v79, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v134);
    LastError = v80;
    v151 = 0;
    if ( v80 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v80,
        v113[0]);
LABEL_80:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
      goto LABEL_62;
    }
    v131 = 0;
    v81 = v134;
    v82 = *(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 **))(*(_QWORD *)v134 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
    v83 = v82(v81, v116, &v131);
    LastError = v83;
    if ( v83 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18A,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
        (const char *)(unsigned int)v83,
        v113[0]);
LABEL_83:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
      goto LABEL_80;
    }
    v136 = 0;
    v84 = Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotification>::As<Windows::UI::Notifications::IToastNotification2>(
            &v131,
            &v136);
    LastError = v84;
    if ( v84 >= 0 )
    {
      v86 = v136;
      v87 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v136 + 48LL);
      v88 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v138);
      v84 = v87(v86, *(_QWORD *)(v88 + 24));
      LastError = v84;
      v151 = 0;
      if ( v84 >= 0 )
      {
        EventW = (wchar_t *)CreateEventW(0, 1, 0, 0);
        si128 = 0;
        *(_OWORD *)&v152.Reserved.Reserved1 = 0;
        if ( EventW )
        {
          v130 = EventW;
          v91 = (char *)operator new(0x18u);
          v138 = (const unsigned __int16 *)v91;
          *(_OWORD *)v91 = 0;
          *((_DWORD *)v91 + 2) = 1;
          *((_DWORD *)v91 + 3) = 1;
          *(_QWORD *)v91 = ___7___Ref_count_obj2_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__6B_;
          v92 = v91 + 16;
          ____Construct_in_place_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__V12__std__YAXAEAV__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil____QEAV12__Z(
            v91 + 16,
            &v130);
          v152.Reserved.Reserved1 = v91 + 16;
          *(_QWORD *)&v152.Reserved.Reserved2[8] = v91;
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v130);
          si128 = _mm_load_si128((const __m128i *)&v152);
        }
        else
        {
          v91 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          v92 = 0;
        }
        v144 = 0;
        v139 = 0;
        v138 = v131;
        v140 = *(const unsigned __int16 **)(*(_QWORD *)v131 + 88LL);
        v93 = v91;
        v94 = (volatile signed __int32 *)v91;
        if ( v91 )
          _InterlockedAdd((volatile signed __int32 *)v91 + 2, 1u);
        hstringHeader.Reserved.Reserved1 = v92;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v91;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v139;
        v95 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Notifications::ToastNotification___Windows::UI::Notifications::IToastNotification____IInspectable___::___Windows::UI::Notifications::IToastNotification___IInspectable____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::UI::Notifications::ToastNotification___IInspectable_______lambda_d72aaddd843b7a859df3dff814dbcb8a___1_Windows::UI::Notifications::IToastNotification___IInspectable_____lambda_d72aaddd843b7a859df3dff814dbcb8a___(
                           &v130,
                           &hstringHeader);
        v96 = *v95;
        v143 = *v95;
        *v95 = 0;
        if ( v130 )
        {
          v130 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>>>::Release();
        }
        else
        {
          v94 = (volatile signed __int32 *)v91;
          v93 = v91;
        }
        v97 = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64, __int64 *))v140)(v138, v96, &v144);
        if ( v96 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        else
          v94 = (volatile signed __int32 *)v93;
        std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(&hstringHeader);
        if ( v97 >= 0 )
        {
          v145 = 0;
          v138 = v131;
          v140 = *(const unsigned __int16 **)(*(_QWORD *)v131 + 72LL);
          v99 = v94;
          if ( v94 )
            _InterlockedIncrement(v94 + 2);
          *(__m128i *)&hstringHeader.Reserved.Reserved1 = si128;
          v100 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Notifications::ToastNotification___Windows::UI::Notifications::IToastNotification____Windows::Foundation::Internal::AggregateType_Windows::UI::Notifications::ToastDismissedEventArgs___Windows::UI::Notifications::IToastDismissedEventArgs_____::___Windows::UI::Notifications::IToastNotification___Windows::UI::Notifications::IToastDismissedEventArgs____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::UI::Notifications::ToastNotification___Windows::UI::Notifications::ToastDismissedEventArgs_______lambda_68edc55b1f95f5f0805039d2492bd11a___1_Windows::UI::Notifications::IToastNotification___Windows::UI::Notifications::IToastDismissedEventArgs_____lambda_68edc55b1f95f5f0805039d2492bd11a___(
                              &v130,
                              &hstringHeader);
          v101 = *v100;
          v143 = *v100;
          *v100 = 0;
          if ( v130 )
          {
            v130 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>>>::Release();
          }
          else
          {
            v99 = v94;
          }
          v97 = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64, __int64 *))v140)(v138, v101, &v145);
          if ( v101 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
          else
            v94 = v99;
          std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(&hstringHeader);
          if ( v97 >= 0 )
          {
            v146 = 0;
            v137 = 0;
            v102 = v131;
            v103 = *(__int64 (__fastcall **)(const unsigned __int16 *, __int64, __int64 *))(*(_QWORD *)v131 + 104LL);
            if ( v94 )
              _InterlockedIncrement(v94 + 2);
            hstringHeader.Reserved.Reserved1 = v92;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v91;
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v137;
            v104 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Notifications::ToastNotification___Windows::UI::Notifications::IToastNotification____Windows::Foundation::Internal::AggregateType_Windows::UI::Notifications::ToastFailedEventArgs___Windows::UI::Notifications::IToastFailedEventArgs_____::___Windows::UI::Notifications::IToastNotification___Windows::UI::Notifications::IToastFailedEventArgs____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::UI::Notifications::ToastNotification___Windows::UI::Notifications::ToastFailedEventArgs_______lambda_10b9a37bb7008d4afcf0a92e884b18a0___1_Windows::UI::Notifications::IToastNotification___Windows::UI::Notifications::IToastFailedEventArgs_____lambda_10b9a37bb7008d4afcf0a92e884b18a0___(
                                &v130,
                                &hstringHeader);
            v105 = *v104;
            v143 = *v104;
            *v104 = 0;
            if ( v130 )
            {
              v130 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastDismissedEventArgs *>>>::Release();
            }
            v17 = v103(v102, v105, &v146);
            if ( v105 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
            std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(&hstringHeader);
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1BA,
                (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
                (const char *)(unsigned int)v17,
                v113[0]);
              std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(&v152);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
              goto LABEL_53;
            }
            v106 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v117 + 48LL))(v117, v131);
            LastError = v106;
            if ( v106 >= 0 )
            {
              if ( v92 )
                v111 = (wil *)*v92;
              else
                v111 = 0;
              wil::handle_wait(v111, (void *)(unsigned int)a8, v107, v108);
              *v147 = v139;
              LastError = v137;
              if ( v137 >= 0 )
              {
                std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(&v152);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v120);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v113);
                DeleteFileW(lpFileName);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v114);
                LastError = 0;
                goto LABEL_131;
              }
              v109 = (unsigned int)v137;
              v110 = 449;
            }
            else
            {
              v109 = (unsigned int)v106;
              v110 = 445;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v110,
              (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
              (const char *)v109,
              v113[0]);
            std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(&v152);
            goto LABEL_87;
          }
          v98 = 423;
        }
        else
        {
          v98 = 413;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v98,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
          (const char *)(unsigned int)v97,
          v113[0]);
        std::_Ptr_base<pplx::details::_Task_impl<int>>::_Decref(&v152);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v131);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v129);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v128);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v127);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v126);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v124);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v120);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v118);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v116);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v113);
        DeleteFileW(lpFileName);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v114);
        LastError = v97;
        goto LABEL_131;
      }
      v85 = 398;
    }
    else
    {
      v85 = 397;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v85,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
      (const char *)(unsigned int)v84,
      v113[0]);
LABEL_87:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v136);
    goto LABEL_83;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11C,
    (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
    (const char *)(unsigned int)ShortcutPath,
    v113[0]);
LABEL_131:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x1800704a0  mov     rax, rsp
0x1800704a3  push    rbp
0x1800704a4  push    rbx
0x1800704a5  push    rsi
0x1800704a6  push    rdi
0x1800704a7  push    r12
0x1800704a9  push    r13
0x1800704ab  push    r14
0x1800704ad  push    r15
0x1800704af  lea     rbp, [rax-0F8h]
0x1800704b6  sub     rsp, 1B8h
0x1800704bd  movaps  xmmword ptr [rax-58h], xmm6
0x1800704c1  mov     rax, cs:__security_cookie
0x1800704c8  xor     rax, rsp
0x1800704cb  mov     [rbp+0F0h+var_60], rax
0x1800704d2  mov     rax, r9
0x1800704d5  mov     [rbp+0F0h+var_120], rax
0x1800704d9  mov     r13d, r8d
0x1800704dc  mov     r12d, edx
0x1800704df  mov     r15, rcx
0x1800704e2  mov     [rbp+0F0h+var_F8], rax
0x1800704e6  mov     rdi, [rbp+0F0h+pszPath]
0x1800704ed  mov     rsi, [rbp+0F0h+arg_28]
0x1800704f4  mov     [rbp+0F0h+var_108], rsi
0x1800704f8  mov     r14, [rbp+0F0h+arg_30]
0x1800704ff  mov     rax, [rbp+0F0h+arg_40]
0x180070506  mov     [rbp+0F0h+var_C0], rax
0x18007050a  mov     [rsp+1F0h+lpFileName], 0
0x180070513  xor     edx, edx
0x180070515  lea     rcx, [rsp+1F0h+lpFileName]
0x18007051a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18007051f  lea     rcx, [rsp+1F0h+lpFileName]
0x180070524  call    GetShortcutPath
0x180070529  mov     ebx, eax
0x18007052b  test    eax, eax
0x18007052d  jns     short loc_18007054F
0x18007052f  mov     rcx, [rbp+0F8h]; this
0x180070536  mov     r9d, eax; char *
0x180070539  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180070540  mov     edx, 11Ch; void *
0x180070545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007054a  jmp     loc_180071671
0x18007054f  mov     [rsp+1F0h+var_1C8], 0
0x180070558  xor     edx, edx
0x18007055a  lea     rcx, [rsp+1F0h+var_1C8]
0x18007055f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180070564  lea     rdx, [rsp+1F0h+var_1C8]
0x180070569  mov     rcx, rdi; pszPath
0x18007056c  call    GetFileNameNoExtension
0x180070571  mov     ebx, eax
0x180070573  test    eax, eax
0x180070575  jns     short loc_1800705A2
0x180070577  mov     rcx, [rbp+0F8h]; this
0x18007057e  mov     r9d, eax; char *
0x180070581  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180070588  mov     edx, 11Fh; void *
0x18007058d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070592  nop
0x180070593  lea     rcx, [rsp+1F0h+var_1C8]
0x180070598  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007059d  jmp     loc_180071671
0x1800705a2  mov     r9, r14
0x1800705a5  mov     rbx, [rsp+1F0h+var_1C8]
0x1800705aa  mov     r8, rbx
0x1800705ad  mov     rdx, [rsp+1F0h+lpFileName]
0x1800705b2  mov     rcx, rdi
0x1800705b5  call    CreateShortcut
0x1800705ba  mov     edi, eax
0x1800705bc  xor     r14d, r14d
0x1800705bf  test    eax, eax
0x1800705c1  jns     short loc_1800705F0
0x1800705c3  mov     rcx, [rbp+0F8h]; this
0x1800705ca  mov     r9d, eax; char *
0x1800705cd  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x1800705d4  mov     edx, 122h; void *
0x1800705d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800705de  nop
0x1800705df  lea     rcx, [rsp+1F0h+var_1C8]
0x1800705e4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800705e9  mov     ebx, edi
0x1800705eb  jmp     loc_180071671
0x1800705f0  lea     rax, [rsp+1F0h+lpFileName]
0x1800705f5  mov     [rbp+0F0h+var_B8], rax
0x1800705f9  mov     [rbp+0F0h+var_B0], 1
0x1800705fd  mov     qword ptr [rsp+1F0h+var_1D0], r14; int
0x180070602  mov     [rbp+0F0h+var_88], r14
0x180070606  mov     r9d, 31h ; '1'; unsigned int
0x18007060c  lea     r8d, [r9+1]; unsigned int
0x180070610  lea     rdx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x180070617  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x18007061b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180070620  mov     rdi, [rbp+0F0h+var_88]
0x180070624  lea     rcx, [rsp+1F0h+var_1D0]
0x180070629  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007062e  lea     r8, [rsp+1F0h+var_1D0]
0x180070633  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x18007063a  mov     rcx, rdi
0x18007063d  call    cs:__imp_RoGetActivationFactory
0x180070644  nop     dword ptr [rax+rax+00h]
0x180070649  mov     edi, eax
0x18007064b  mov     [rbp+0F0h+var_88], r14
0x18007064f  test    eax, eax
0x180070651  jns     short loc_180070690
0x180070653  mov     rcx, [rbp+0F8h]; this
0x18007065a  mov     r9d, eax; char *
0x18007065d  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180070664  mov     edx, 12Ch; void *
0x180070669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007066e  nop
0x18007066f  lea     rcx, [rsp+1F0h+var_1D0]
0x180070674  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070679  nop
0x18007067a  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x18007067f  call    cs:__imp_DeleteFileW
0x180070686  nop     dword ptr [rax+rax+00h]
0x18007068b  jmp     loc_1800705DF
0x180070690  mov     byte ptr [rsp+1F0h+var_180], r14b
0x180070695  lea     r9, [rsp+1F0h+var_180]
0x18007069a  mov     r8, rsi
0x18007069d  mov     rdx, rbx
0x1800706a0  lea     rcx, [rsp+1F0h+var_1D0]
0x1800706a5  call    IsDup
0x1800706aa  test    eax, eax
0x1800706ac  js      short loc_1800706E6
0x1800706ae  cmp     byte ptr [rsp+1F0h+var_180], r14b
0x1800706b3  jz      short loc_1800706E6
0x1800706b5  lea     rcx, [rsp+1F0h+var_1D0]
0x1800706ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800706bf  nop
0x1800706c0  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x1800706c5  call    cs:__imp_DeleteFileW
0x1800706cc  nop     dword ptr [rax+rax+00h]
0x1800706d1  nop
0x1800706d2  lea     rcx, [rsp+1F0h+var_1C8]
0x1800706d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800706dc  mov     ebx, 1
0x1800706e1  jmp     loc_180071671
0x1800706e6  mov     [rsp+1F0h+var_1B0], r14
0x1800706eb  mov     rsi, qword ptr [rsp+1F0h+var_1D0]
0x1800706f0  mov     rax, [rsi]
0x1800706f3  mov     rdi, [rax+38h]
0x1800706f7  lea     rcx, [rsp+1F0h+var_1B0]
0x1800706fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070701  mov     [rbp+0F0h+var_148], rbx
0x180070705  lea     rdx, [rbp+0F0h+var_148]
0x180070709  lea     rcx, [rbp+0F0h+hstringHeader]
0x18007070d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180070712  nop
0x180070713  lea     r8, [rsp+1F0h+var_1B0]
0x180070718  mov     rdx, [rax+18h]
0x18007071c  mov     rcx, rsi
0x18007071f  mov     rax, rdi
0x180070722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070727  mov     ebx, eax
0x180070729  mov     [rbp+0F0h+var_88], r14
0x18007072d  test    eax, eax
0x18007072f  jns     short loc_180070779
0x180070731  mov     rcx, [rbp+0F8h]; this
0x180070738  mov     r9d, eax; char *
0x18007073b  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180070742  mov     edx, 136h; void *
0x180070747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007074c  nop
0x18007074d  lea     rcx, [rsp+1F0h+var_1B0]
0x180070752  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070757  nop
0x180070758  lea     rcx, [rsp+1F0h+var_1D0]
0x18007075d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070762  nop
0x180070763  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x180070768  call    cs:__imp_DeleteFileW
0x18007076f  nop     dword ptr [rax+rax+00h]
0x180070774  jmp     loc_180070593
0x180070779  mov     [rsp+1F0h+var_1B8], r14
0x18007077e  mov     rdi, qword ptr [rsp+1F0h+var_1D0]
0x180070783  mov     rax, [rdi]
0x180070786  mov     rbx, [rax+40h]
0x18007078a  lea     rcx, [rsp+1F0h+var_1B8]
0x18007078f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070794  lea     r8, [rsp+1F0h+var_1B8]
0x180070799  mov     esi, 5
0x18007079e  mov     edx, esi
0x1800707a0  mov     rcx, rdi
0x1800707a3  mov     rax, rbx
0x1800707a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800707ab  mov     ebx, eax
0x1800707ad  test    eax, eax
0x1800707af  jns     short loc_1800707DC
0x1800707b1  mov     rcx, [rbp+0F8h]; this
0x1800707b8  mov     r9d, eax; char *
0x1800707bb  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x1800707c2  mov     edx, 139h; void *
0x1800707c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800707cc  nop
0x1800707cd  lea     rcx, [rsp+1F0h+var_1B8]
0x1800707d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800707d7  jmp     loc_18007074D
0x1800707dc  mov     [rsp+1F0h+var_1A8], r14
0x1800707e1  mov     rdi, [rsp+1F0h+var_1B8]
0x1800707e6  mov     rax, [rdi]
0x1800707e9  mov     rbx, [rax+80h]
0x1800707f0  lea     rcx, [rsp+1F0h+var_1A8]
0x1800707f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800707fa  mov     [rbp+0F0h+var_88], r14
0x1800707fe  mov     r9d, 4; unsigned int
0x180070804  mov     r8d, esi; unsigned int
0x180070807  lea     rdx, aText; "text"
0x18007080e  lea     rcx, [rbp+0F0h+hstringHeader]; hstringHeader
0x180070812  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180070817  nop
0x180070818  lea     r8, [rsp+1F0h+var_1A8]
0x18007081d  mov     rdx, [rbp+0F0h+var_88]
0x180070821  mov     rcx, rdi
0x180070824  mov     rax, rbx
0x180070827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007082c  mov     ebx, eax
0x18007082e  mov     [rbp+0F0h+var_88], r14
0x180070832  test    eax, eax
0x180070834  jns     short loc_180070861
0x180070836  mov     rcx, [rbp+0F8h]; this
0x18007083d  mov     r9d, eax; char *
0x180070840  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180070847  mov     edx, 13Ch; void *
0x18007084c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070851  nop
0x180070852  lea     rcx, [rsp+1F0h+var_1A8]
0x180070857  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007085c  jmp     loc_1800707CD
0x180070861  mov     [rsp+1F0h+var_198], r14
0x180070866  mov     [rsp+1F0h+Str], r14
0x18007086b  xor     edx, edx; hFile
0x18007086d  mov     r8d, 800h; dwFlags
0x180070873  mov     rcx, r15; lpLibFileName
0x180070876  call    cs:__imp_LoadLibraryExW
0x18007087d  nop     dword ptr [rax+rax+00h]
0x180070882  mov     rbx, rax
0x180070885  mov     [rbp+0F0h+var_138], rax
0x180070889  xor     r15d, r15d
0x18007088c  test    rax, rax
0x18007088f  jnz     short loc_1800708CC
0x180070891  mov     edx, 143h; void *
0x180070896  mov     rcx, [rbp+0F8h]; this
0x18007089d  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x1800708a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800708a9  mov     ebx, eax
0x1800708ab  lea     rcx, [rbp+0F0h+var_138]
0x1800708af  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800708b4  nop
0x1800708b5  lea     rcx, [rsp+1F0h+Str]
0x1800708ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800708bf  nop
0x1800708c0  lea     rcx, [rsp+1F0h+var_198]
0x1800708c5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800708ca  jmp     short loc_180070852
0x1800708cc  mov     qword ptr [rbp+0F0h+Buffer], r15
0x1800708d0  xor     r9d, r9d; cchBufferMax
0x1800708d3  lea     r8, [rbp+0F0h+Buffer]; lpBuffer
0x1800708d7  mov     edx, r12d; uID
0x1800708da  mov     rcx, rbx; hInstance
0x1800708dd  call    cs:__imp_LoadStringW
0x1800708e4  nop     dword ptr [rax+rax+00h]
0x1800708e9  test    eax, eax
0x1800708eb  jnz     short loc_1800708F4
0x1800708ed  mov     edx, 147h
0x1800708f2  jmp     short loc_180070896
0x1800708f4  movsxd  r8, eax
0x1800708f7  mov     rdx, qword ptr [rbp+0F0h+Buffer]
0x1800708fb  lea     rcx, [rbp+0F0h+var_130]
0x1800708ff  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180070904  lea     rdx, [rbp+0F0h+var_130]
0x180070908  lea     rcx, [rsp+1F0h+var_198]
0x18007090d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180070912  lea     rcx, [rbp+0F0h+var_130]
0x180070916  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007091b  mov     rdi, [rsp+1F0h+var_198]
0x180070920  test    rdi, rdi
0x180070923  jnz     short loc_18007094A
0x180070925  mov     edx, 14Ah; void *
0x18007092a  mov     ebx, 8007000Eh
0x18007092f  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180070936  mov     r9d, ebx; char *
0x180070939  mov     rcx, [rbp+0F8h]; this
0x180070940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070945  jmp     loc_1800708AB
0x18007094a  mov     qword ptr [rbp+0F0h+var_E8], r15
0x18007094e  xor     r9d, r9d; cchBufferMax
0x180070951  lea     r8, [rbp+0F0h+var_E8]; lpBuffer
0x180070955  mov     edx, r13d; uID
0x180070958  mov     rcx, rbx; hInstance
0x18007095b  call    cs:__imp_LoadStringW
0x180070962  nop     dword ptr [rax+rax+00h]
0x180070967  test    eax, eax
0x180070969  jnz     short loc_180070975
0x18007096b  mov     edx, 14Eh
0x180070970  jmp     loc_180070896
0x180070975  movsxd  r8, eax
0x180070978  mov     rdx, qword ptr [rbp+0F0h+var_E8]
0x18007097c  lea     rcx, [rbp+0F0h+var_130]
0x180070980  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180070985  lea     rdx, [rbp+0F0h+var_130]
  ... truncated ...
```
