# AppActivation::PrepareExtensionForActivate(ActivateByExtensionArgs *,_ActivateComponentInfo const *)

- ea: `0x18000cd40`
- end: `0x18000d69d`
- name: `?PrepareExtensionForActivate@AppActivation@@AEAAJPEAUActivateByExtensionArgs@@PEBU_ActivateComponentInfo@@@Z`
- size: `2397`
- prototype: `__int64 __fastcall(AppActivation *__hidden this, struct ActivateByExtensionArgs *, const struct _ActivateComponentInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b5f0`

## callees

- `0x18000b5c0`
- `0x18000cd40`
- `0x18000d6b0`
- `0x180011328`
- `0x180032820`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d5c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d653`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d5c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d40b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ce86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cec2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d278`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d40b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000ce9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000ce9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ce61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ce61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000cdd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000cdd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cf84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d06b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cf84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d06b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000cddb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000cddb`
- `api-ms-win-core-winrt-registration-l1-1-0!RoGetActivatableClassRegistration` at `0x18000d299`
- `api-ms-win-core-winrt-registration-l1-1-0!RoGetActivatableClassRegistration` at `0x18000d299`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall AppActivation::PrepareExtensionForActivate(
        AppActivation *this,
        HSTRING *a2,
        const struct _ActivateComponentInfo *a3)
{
  HSTRING *v4; // rsi
  int v6; // r13d
  HSTRING v7; // rbx
  __int64 v8; // rcx
  HSTRING *v9; // r12
  const WCHAR *StringRawBuffer; // rax
  LPWSTR FileNameW; // rax
  const WCHAR *v12; // rdi
  unsigned __int64 v13; // rbx
  HRESULT v14; // ebx
  __int64 v15; // rcx
  UINT32 v17; // edx
  const WCHAR *v18; // rcx
  HSTRING v19; // rdi
  HRESULT v20; // eax
  unsigned int v21; // ebx
  __int64 (__fastcall *v22)(HSTRING *, char *); // rdi
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, __int64 *); // rdi
  __int64 v27; // rdx
  int ActivatableClassRegistration; // ebx
  int v29; // eax
  _QWORD *v30; // rbx
  HSTRING **v31; // rdi
  HRESULT v32; // eax
  unsigned int v33; // eax
  __int64 v34; // rdx
  HSTRING *v35; // r12
  HSTRING *v36; // rcx
  int v37; // eax
  __int64 v38; // rsi
  int v39; // edi
  int v40; // ebx
  HSTRING *v41; // rsi
  HSTRING **v42; // rbx
  __int64 v43; // rdi
  HRESULT v44; // eax
  HSTRING *v45; // rcx
  int v46; // eax
  _QWORD *v47; // rcx
  __int64 v48; // rcx
  int v49; // eax
  int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rbx
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  __int64 v55; // rcx
  _QWORD *v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rsi
  int v59; // edi
  _QWORD *v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // [rsp+20h] [rbp-59h] BYREF
  unsigned int v67; // [rsp+28h] [rbp-51h]
  _QWORD *v68; // [rsp+30h] [rbp-49h] BYREF
  __int64 v69; // [rsp+38h] [rbp-41h] BYREF
  int v70; // [rsp+40h] [rbp-39h]
  HSTRING *v71; // [rsp+48h] [rbp-31h] BYREF
  __int64 v72; // [rsp+50h] [rbp-29h] BYREF
  int v73; // [rsp+58h] [rbp-21h]
  HSTRING **v74; // [rsp+60h] [rbp-19h]
  HSTRING *v75; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = a2;
  v6 = 0;
  v66 = 0;
  if ( a3 )
  {
    v51 = *((_QWORD *)a3 + 2);
    if ( v51 )
    {
      ActivatableClassRegistration = RoGetActivatableClassRegistration(v51, &v66);
      if ( ActivatableClassRegistration >= 0 )
      {
        v52 = v66;
        if ( *((_QWORD *)this + 24) != v66 )
        {
          if ( v66 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 8LL))(v66);
          v53 = *((_QWORD *)this + 24);
          *((_QWORD *)this + 24) = v52;
          if ( v53 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        }
        goto LABEL_24;
      }
      v64 = 441;
LABEL_106:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v64,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)ActivatableClassRegistration,
        v66);
LABEL_111:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
      return (unsigned int)ActivatableClassRegistration;
    }
  }
  v7 = a2[2];
  if ( *((HSTRING *)this + 21) != v7 )
  {
    if ( v7 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v7 + 8LL))(a2[2]);
    v8 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = v7;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = (HSTRING *)((char *)this + 128);
  StringRawBuffer = WindowsGetStringRawBuffer(v4[3], 0);
  FileNameW = PathFindFileNameW(StringRawBuffer);
  v12 = FileNameW;
  if ( FileNameW )
  {
    v13 = -1;
    do
      ++v13;
    while ( FileNameW[v13] );
    if ( v13 > 0xFFFFFFFF )
    {
      v14 = -2147024362;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v14,
        v66);
      v15 = v66;
      if ( v66 )
      {
        v66 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return (unsigned int)v14;
    }
    WindowsDeleteString(*v9);
    v17 = v13;
    v18 = v12;
  }
  else
  {
    WindowsDeleteString(*v9);
    v17 = 0;
    v18 = &Src;
  }
  *v9 = 0;
  v14 = WindowsCreateString(v18, v17, (HSTRING *)this + 16);
  if ( v14 < 0 )
    goto LABEL_12;
  v19 = v4[3];
  if ( !v19 || v19 != *((HSTRING *)this + 17) )
  {
    WindowsDeleteString(*((HSTRING *)this + 17));
    *((_QWORD *)this + 17) = 0;
    v20 = WindowsDuplicateString(v19, (HSTRING *)this + 17);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
        (const char *)(unsigned int)v20,
        v66);
      v62 = v66;
      if ( v66 )
      {
        v66 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      }
      return v21;
    }
  }
  v4 = (HSTRING *)*((_QWORD *)this + 21);
  v22 = (__int64 (__fastcall *)(HSTRING *, char *))*((_QWORD *)*v4 + 6);
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  v23 = v22(v4, (char *)this + 152);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v23,
      v66);
    v63 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    return v24;
  }
  v25 = *((_QWORD *)this + 21);
  v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 80LL);
  v27 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  ActivatableClassRegistration = v26(v25, &v66);
  if ( ActivatableClassRegistration < 0 )
  {
    v64 = 451;
    goto LABEL_106;
  }
LABEL_24:
  v68 = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v66 + 80LL))(v66, &v68);
  ActivatableClassRegistration = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v29,
      v66);
    v56 = v68;
    if ( v68 )
    {
      v68 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
    }
    v57 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    return (unsigned int)ActivatableClassRegistration;
  }
  v69 = 0;
  v70 = 0;
  v30 = v68;
  v31 = (HSTRING **)*v68;
  v74 = (HSTRING **)&v69;
  v75 = 0;
  string = 0;
  v32 = WindowsCreateStringReference(L"AppObject.EntryPoint", 0x14u, &hstringHeader, &string);
  if ( v32 < 0 )
  {
    RaiseException(v32, 1u, 0, 0);
    goto LABEL_113;
  }
  v33 = ((__int64 (__fastcall *)(_QWORD *, HSTRING, HSTRING **))v31[6])(v30, string, &v75);
  v34 = v33;
  v67 = v33;
  string = 0;
  v31 = v74;
  v4 = v75;
  v6 = 7;
  if ( v75 )
  {
    v71 = 0;
    v49 = (*(__int64 (__fastcall **)(HSTRING *, GUID *, HSTRING **))*v75)(
            v75,
            &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
            &v71);
    LODWORD(v30) = v49;
    if ( v49 >= 0 )
    {
      v35 = v71;
      (*((void (__fastcall **)(HSTRING *))*v4 + 2))(v4);
      LODWORD(v30) = 7;
LABEL_49:
      v34 = v67;
      goto LABEL_28;
    }
LABEL_113:
    if ( v49 == -2147467262 )
    {
      v35 = v4;
      LODWORD(v30) = 3;
    }
    else
    {
      (*((void (__fastcall **)(HSTRING *))*v4 + 2))(v4);
      v35 = 0;
    }
    goto LABEL_49;
  }
  v35 = 0;
  LODWORD(v30) = 0;
LABEL_28:
  v36 = *v31;
  *v31 = v35;
  v37 = *((_DWORD *)v31 + 2);
  *((_DWORD *)v31 + 2) = (_DWORD)v30;
  if ( v36 && ((v37 - 3) & 0xFFFFFFFB) == 0 )
  {
    (*((void (__fastcall **)(HSTRING *, __int64))*v36 + 2))(v36, v34);
    LODWORD(v34) = v67;
  }
  if ( (int)v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v34,
      v66);
    RoVariant::~RoVariant((RoVariant *)&v69);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v66);
    return v67;
  }
  v38 = v69;
  v39 = v70;
  WindowsDeleteString(*((HSTRING *)this + 18));
  *((_QWORD *)this + 18) = 0;
  if ( this == (AppActivation *)-144LL )
  {
    v40 = -2147467261;
    goto LABEL_90;
  }
  if ( v39 != 7 )
  {
    v40 = -2147316576;
    if ( v39 < 0 )
      v40 = v39;
    goto LABEL_90;
  }
  v40 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v38 + 152LL))(v38, (char *)this + 144);
  if ( v40 < 0 )
  {
LABEL_90:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v40,
      v66);
    if ( v69 && ((v70 - 3) & 0xFFFFFFFB) == 0 )
      (*(void (**)(void))(*(_QWORD *)v69 + 16LL))();
    v60 = v68;
    if ( v68 )
    {
      v68 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    }
    v61 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    return (unsigned int)v40;
  }
  v41 = 0;
  v72 = 0;
  v73 = 0;
  v42 = (HSTRING **)v68;
  v43 = *v68;
  v74 = (HSTRING **)&v72;
  v75 = 0;
  string = 0;
  v44 = WindowsCreateStringReference(L"AppObject.RuntimeType", 0x15u, &hstringHeader, &string);
  if ( v44 < 0 )
  {
    RaiseException(v44, 1u, 0, 0);
    goto LABEL_121;
  }
  LODWORD(v43) = (*(__int64 (__fastcall **)(HSTRING **, HSTRING, HSTRING **))(v43 + 48))(v42, string, &v75);
  string = 0;
  v42 = v74;
  v35 = v75;
  if ( !v75 )
  {
    v6 = 0;
    goto LABEL_36;
  }
  v71 = 0;
  v50 = (*(__int64 (__fastcall **)(HSTRING *, GUID *, HSTRING **))*v75)(
          v75,
          &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
          &v71);
  v67 = v50;
  if ( v50 < 0 )
  {
LABEL_121:
    if ( v50 == -2147467262 )
    {
      v41 = v35;
      v6 = 3;
    }
    else
    {
      (*((void (__fastcall **)(HSTRING *))*v35 + 2))(v35);
      v6 = v67;
    }
    goto LABEL_36;
  }
  v41 = v71;
  (*((void (__fastcall **)(HSTRING *))*v35 + 2))(v35);
LABEL_36:
  v45 = *v42;
  *v42 = v41;
  v46 = *((_DWORD *)v42 + 2);
  *((_DWORD *)v42 + 2) = v6;
  if ( v45 && ((v46 - 3) & 0xFFFFFFFB) == 0 )
    (*((void (__fastcall **)(HSTRING *))*v45 + 2))(v45);
  if ( (int)v43 >= 0 )
  {
    v58 = v72;
    v59 = v73;
    WindowsDeleteString(*((HSTRING *)this + 20));
    *((_QWORD *)this + 20) = 0;
    if ( this == (AppActivation *)-160LL )
    {
      ActivatableClassRegistration = -2147467261;
    }
    else if ( v59 == 7 )
    {
      ActivatableClassRegistration = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v58 + 152LL))(
                                       v58,
                                       (char *)this + 160);
      if ( ActivatableClassRegistration >= 0 )
        goto LABEL_39;
    }
    else
    {
      ActivatableClassRegistration = -2147316576;
      if ( v59 < 0 )
        ActivatableClassRegistration = v59;
    }
    v65 = 465;
LABEL_110:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v65,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)ActivatableClassRegistration,
      v66);
    RoVariant::~RoVariant((RoVariant *)&v72);
    RoVariant::~RoVariant((RoVariant *)&v69);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
    goto LABEL_111;
  }
  if ( (_DWORD)v43 == -2147483637 )
  {
LABEL_39:
    ActivatableClassRegistration = AppActivation::SetExtensionContext(this, *((_QWORD *)this + 9), a3);
    if ( ActivatableClassRegistration >= 0 )
    {
      if ( v72 && ((v73 - 3) & 0xFFFFFFFB) == 0 )
        (*(void (**)(void))(*(_QWORD *)v72 + 16LL))();
      if ( v69 && ((v70 - 3) & 0xFFFFFFFB) == 0 )
        (*(void (**)(void))(*(_QWORD *)v69 + 16LL))();
      v47 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
      }
      v48 = v66;
      if ( v66 )
      {
        v66 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      return 0;
    }
    v65 = 473;
    goto LABEL_110;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D6,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
    (const char *)(unsigned int)v43,
    v66);
  if ( v72 && ((v73 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (**)(void))(*(_QWORD *)v72 + 16LL))();
  if ( v69 && ((v70 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (**)(void))(*(_QWORD *)v69 + 16LL))();
  v54 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
  }
  v55 = v66;
  if ( v66 )
  {
    v66 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  }
  return (unsigned int)v43;
}

```

## disassembly

```asm
0x18000cd40  mov     [rsp-8+arg_18], rbx
0x18000cd45  push    rbp
0x18000cd46  push    rsi
0x18000cd47  push    rdi
0x18000cd48  push    r12
0x18000cd4a  push    r13
0x18000cd4c  push    r14
0x18000cd4e  push    r15
0x18000cd50  lea     rbp, [rsp-27h]
0x18000cd55  sub     rsp, 0A0h
0x18000cd5c  mov     rax, cs:__security_cookie
0x18000cd63  xor     rax, rsp
0x18000cd66  mov     [rbp+57h+var_40], rax
0x18000cd6a  mov     r15, r8
0x18000cd6d  mov     rsi, rdx
0x18000cd70  mov     r14, rcx
0x18000cd73  xor     r13d, r13d
0x18000cd76  mov     [rbp+57h+var_B0], r13
0x18000cd7a  test    r8, r8
0x18000cd7d  jnz     loc_18000D288
0x18000cd83  mov     rbx, [rdx+10h]
0x18000cd87  cmp     [r14+0A8h], rbx
0x18000cd8e  jz      short loc_18000CDC5
0x18000cd90  test    rbx, rbx
0x18000cd93  jz      short loc_18000CDA5
0x18000cd95  mov     rax, [rbx]
0x18000cd98  mov     rcx, rbx
0x18000cd9b  mov     rax, [rax+8]
0x18000cd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cda4  nop
0x18000cda5  mov     rcx, [r14+0A8h]
0x18000cdac  mov     [r14+0A8h], rbx
0x18000cdb3  test    rcx, rcx
0x18000cdb6  jz      short loc_18000CDC5
0x18000cdb8  mov     rax, [rcx]
0x18000cdbb  mov     rax, [rax+10h]
0x18000cdbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc4  nop
0x18000cdc5  lea     r12, [r14+80h]
0x18000cdcc  xor     edx, edx; length
0x18000cdce  mov     rcx, [rsi+18h]; string
0x18000cdd2  call    cs:__imp_WindowsGetStringRawBuffer
0x18000cdd8  mov     rcx, rax; pszPath
0x18000cddb  call    cs:__imp_PathFindFileNameW
0x18000cde1  mov     rdi, rax
0x18000cde4  test    rax, rax
0x18000cde7  jz      short loc_18000CE47
0x18000cde9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cdf0  inc     rbx
0x18000cdf3  cmp     word ptr [rax+rbx*2], 0
0x18000cdf8  jnz     short loc_18000CDF0
0x18000cdfa  mov     eax, 0FFFFFFFFh
0x18000cdff  cmp     rbx, rax
0x18000ce02  jbe     loc_18000D274
0x18000ce08  mov     ebx, 80070216h
0x18000ce0d  mov     rcx, [rbp+5Fh]; this
0x18000ce11  mov     r9d, ebx; char *
0x18000ce14  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000ce1b  mov     edx, 1BFh; void *
0x18000ce20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce25  nop
0x18000ce26  mov     rcx, [rbp+57h+var_B0]
0x18000ce2a  test    rcx, rcx
0x18000ce2d  jz      short loc_18000CE40
0x18000ce2f  mov     [rbp+57h+var_B0], r13
0x18000ce33  mov     rax, [rcx]
0x18000ce36  mov     rax, [rax+10h]
0x18000ce3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce3f  nop
0x18000ce40  mov     eax, ebx
0x18000ce42  jmp     loc_18000D13A
0x18000ce47  mov     rcx, [r12]; string
0x18000ce4b  call    cs:__imp_WindowsDeleteString
0x18000ce51  xor     edx, edx; length
0x18000ce53  lea     rcx, Src; sourceString
0x18000ce5a  mov     [r12], r13
0x18000ce5e  mov     r8, r12; string
0x18000ce61  call    cs:__imp_WindowsCreateString
0x18000ce67  mov     ebx, eax
0x18000ce69  test    eax, eax
0x18000ce6b  js      short loc_18000CE0D
0x18000ce6d  mov     rdi, [rsi+18h]
0x18000ce71  test    rdi, rdi
0x18000ce74  jz      short loc_18000CE7F
0x18000ce76  cmp     rdi, [r14+88h]
0x18000ce7d  jz      short loc_18000CEAD
0x18000ce7f  mov     rcx, [r14+88h]; string
0x18000ce86  call    cs:__imp_WindowsDeleteString
0x18000ce8c  mov     [r14+88h], r13
0x18000ce93  lea     rdx, [r14+88h]; newString
0x18000ce9a  mov     rcx, rdi; string
0x18000ce9d  call    cs:__imp_WindowsDuplicateString
0x18000cea3  mov     ebx, eax
0x18000cea5  test    eax, eax
0x18000cea7  js      loc_18000D4B4
0x18000cead  mov     rsi, [r14+0A8h]
0x18000ceb4  mov     rax, [rsi]
0x18000ceb7  mov     rdi, [rax+30h]
0x18000cebb  mov     rcx, [r14+98h]; string
0x18000cec2  call    cs:__imp_WindowsDeleteString
0x18000cec8  mov     [r14+98h], r13
0x18000cecf  lea     rdx, [r14+98h]
0x18000ced6  mov     rcx, rsi
0x18000ced9  mov     rax, rdi
0x18000cedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee1  mov     ebx, eax
0x18000cee3  test    eax, eax
0x18000cee5  js      loc_18000D510
0x18000ceeb  mov     rbx, [r14+0A8h]
0x18000cef2  mov     rax, [rbx]
0x18000cef5  mov     rdi, [rax+50h]
0x18000cef9  mov     rdx, [rbp+57h+var_B0]
0x18000cefd  test    rdx, rdx
0x18000cf00  jz      short loc_18000CF16
0x18000cf02  mov     [rbp+57h+var_B0], r13
0x18000cf06  mov     rcx, [rdx]
0x18000cf09  mov     rax, [rcx+10h]
0x18000cf0d  mov     rcx, rdx
0x18000cf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf15  nop
0x18000cf16  lea     rdx, [rbp+57h+var_B0]
0x18000cf1a  mov     rcx, rbx
0x18000cf1d  mov     rax, rdi
0x18000cf20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf25  mov     ebx, eax
0x18000cf27  test    eax, eax
0x18000cf29  js      loc_18000D551
0x18000cf2f  mov     [rbp+57h+var_A0], r13
0x18000cf33  mov     rcx, [rbp+57h+var_B0]
0x18000cf37  mov     rax, [rcx]
0x18000cf3a  lea     rdx, [rbp+57h+var_A0]
0x18000cf3e  mov     rax, [rax+50h]
0x18000cf42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf47  mov     ebx, eax
0x18000cf49  test    eax, eax
0x18000cf4b  js      loc_18000D362
0x18000cf51  mov     [rbp+57h+var_98], r13
0x18000cf55  mov     [rbp+57h+var_90], r13d
0x18000cf59  mov     rbx, [rbp+57h+var_A0]
0x18000cf5d  mov     rdi, [rbx]
0x18000cf60  lea     rax, [rbp+57h+var_98]
0x18000cf64  mov     [rbp+57h+var_70], rax
0x18000cf68  mov     [rbp+57h+var_68], r13
0x18000cf6c  mov     [rbp+57h+string], r13
0x18000cf70  lea     r9, [rbp+57h+string]; string
0x18000cf74  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000cf78  mov     edx, 14h; length
0x18000cf7d  lea     rcx, aAppobjectEntry; "AppObject.EntryPoint"
0x18000cf84  call    cs:__imp_WindowsCreateStringReference
0x18000cf8a  test    eax, eax
0x18000cf8c  js      loc_18000D5BA
0x18000cf92  lea     r8, [rbp+57h+var_68]
0x18000cf96  mov     rdx, [rbp+57h+string]
0x18000cf9a  mov     rcx, rbx
0x18000cf9d  mov     rax, [rdi+30h]
0x18000cfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfa6  mov     edx, eax
0x18000cfa8  mov     [rbp+57h+var_A8], eax
0x18000cfab  mov     [rbp+57h+string], r13
0x18000cfaf  mov     rdi, [rbp+57h+var_70]
0x18000cfb3  mov     rsi, [rbp+57h+var_68]
0x18000cfb7  mov     r13d, 7
0x18000cfbd  test    rsi, rsi
0x18000cfc0  jnz     loc_18000D161
0x18000cfc6  xor     r12d, r12d
0x18000cfc9  xor     ebx, ebx
0x18000cfcb  mov     rcx, [rdi]
0x18000cfce  mov     [rdi], r12
0x18000cfd1  mov     eax, [rdi+8]
0x18000cfd4  mov     [rdi+8], ebx
0x18000cfd7  test    rcx, rcx
0x18000cfda  jnz     loc_18000D1EF
0x18000cfe0  test    edx, edx
0x18000cfe2  js      loc_18000D5F9
0x18000cfe8  mov     rsi, [rbp+57h+var_98]
0x18000cfec  mov     edi, [rbp+57h+var_90]
0x18000cfef  lea     rbx, [r14+90h]
0x18000cff6  mov     rcx, [rbx]; string
0x18000cff9  call    cs:__imp_WindowsDeleteString
0x18000cfff  mov     qword ptr [rbx], 0
0x18000d006  test    rbx, rbx
0x18000d009  jz      loc_18000D44A
0x18000d00f  cmp     edi, 7
0x18000d012  jnz     loc_18000D637
0x18000d018  mov     rax, [rsi]
0x18000d01b  mov     rdx, rbx
0x18000d01e  mov     rcx, rsi
0x18000d021  mov     rax, [rax+98h]
0x18000d028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d02d  mov     ebx, eax
0x18000d02f  test    eax, eax
0x18000d031  js      loc_18000D44F
0x18000d037  xor     esi, esi
0x18000d039  mov     [rbp+57h+var_80], rsi
0x18000d03d  mov     [rbp+57h+var_78], esi
0x18000d040  mov     rbx, [rbp+57h+var_A0]
0x18000d044  mov     rdi, [rbx]
0x18000d047  lea     rax, [rbp+57h+var_80]
0x18000d04b  mov     [rbp+57h+var_70], rax
0x18000d04f  mov     [rbp+57h+var_68], rsi
0x18000d053  mov     [rbp+57h+string], rsi
0x18000d057  lea     r9, [rbp+57h+string]; string
0x18000d05b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000d05f  mov     edx, 15h; length
0x18000d064  lea     rcx, aAppobjectRunti; "AppObject.RuntimeType"
0x18000d06b  call    cs:__imp_WindowsCreateStringReference
0x18000d071  test    eax, eax
0x18000d073  js      loc_18000D646
0x18000d079  lea     r8, [rbp+57h+var_68]
0x18000d07d  mov     rdx, [rbp+57h+string]
0x18000d081  mov     rcx, rbx
0x18000d084  mov     rax, [rdi+30h]
0x18000d088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d08d  mov     edi, eax
0x18000d08f  mov     [rbp+57h+string], rsi
0x18000d093  mov     rbx, [rbp+57h+var_70]
0x18000d097  mov     r12, [rbp+57h+var_68]
0x18000d09b  test    r12, r12
0x18000d09e  jnz     loc_18000D1AA
0x18000d0a4  mov     r13d, r12d
0x18000d0a7  mov     rcx, [rbx]
0x18000d0aa  mov     [rbx], rsi
0x18000d0ad  mov     eax, [rbx+8]
0x18000d0b0  mov     [rbx+8], r13d
0x18000d0b4  test    rcx, rcx
0x18000d0b7  jnz     loc_18000D211
0x18000d0bd  test    edi, edi
0x18000d0bf  jns     loc_18000D3FA
0x18000d0c5  cmp     edi, 8000000Bh
0x18000d0cb  jnz     loc_18000D2F4
0x18000d0d1  mov     r8, r15; struct _ActivateComponentInfo *
0x18000d0d4  mov     rdx, [r14+48h]; unsigned __int64
0x18000d0d8  mov     rcx, r14; this
0x18000d0db  call    ?SetExtensionContext@AppActivation@@AEAAJ_KPEBU_ActivateComponentInfo@@@Z; AppActivation::SetExtensionContext(unsigned __int64,_ActivateComponentInfo const *)
0x18000d0e0  mov     ebx, eax
0x18000d0e2  test    eax, eax
0x18000d0e4  js      loc_18000D692
0x18000d0ea  mov     rcx, [rbp+57h+var_80]
0x18000d0ee  test    rcx, rcx
0x18000d0f1  jnz     loc_18000D230
0x18000d0f7  mov     rcx, [rbp+57h+var_98]
0x18000d0fb  test    rcx, rcx
0x18000d0fe  jnz     loc_18000D252
0x18000d104  mov     rcx, [rbp+57h+var_A0]
0x18000d108  test    rcx, rcx
0x18000d10b  jz      short loc_18000D11E
0x18000d10d  mov     [rbp+57h+var_A0], r12
0x18000d111  mov     rax, [rcx]
0x18000d114  mov     rax, [rax+10h]
0x18000d118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d11d  nop
0x18000d11e  mov     rcx, [rbp+57h+var_B0]
0x18000d122  test    rcx, rcx
0x18000d125  jz      short loc_18000D138
0x18000d127  mov     [rbp+57h+var_B0], r12
0x18000d12b  mov     rax, [rcx]
0x18000d12e  mov     rax, [rax+10h]
0x18000d132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d137  nop
0x18000d138  xor     eax, eax
0x18000d13a  mov     rcx, [rbp+57h+var_40]
0x18000d13e  xor     rcx, rsp; StackCookie
0x18000d141  call    __security_check_cookie
0x18000d146  mov     rbx, [rsp+0D0h+arg_18]
0x18000d14e  add     rsp, 0A0h
0x18000d155  pop     r15
0x18000d157  pop     r14
0x18000d159  pop     r13
0x18000d15b  pop     r12
0x18000d15d  pop     rdi
0x18000d15e  pop     rsi
0x18000d15f  pop     rbp
0x18000d160  retn
0x18000d161  mov     [rbp+57h+var_88], 0
0x18000d169  mov     rax, [rsi]
0x18000d16c  lea     r8, [rbp+57h+var_88]
0x18000d170  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18000d177  mov     rcx, rsi
0x18000d17a  mov     rax, [rax]
0x18000d17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d182  mov     ebx, eax
0x18000d184  test    eax, eax
0x18000d186  js      loc_18000D5CE
0x18000d18c  mov     r12, [rbp+57h+var_88]
0x18000d190  mov     rax, [rsi]
0x18000d193  mov     rcx, rsi
0x18000d196  mov     rax, [rax+10h]
0x18000d19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19f  mov     ebx, r13d
0x18000d1a2  mov     edx, [rbp+57h+var_A8]
0x18000d1a5  jmp     loc_18000CFCB
0x18000d1aa  mov     [rbp+57h+var_88], rsi
0x18000d1ae  mov     rax, [r12]
0x18000d1b2  lea     r8, [rbp+57h+var_88]
0x18000d1b6  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18000d1bd  mov     rcx, r12
0x18000d1c0  mov     rax, [rax]
0x18000d1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1c8  mov     [rbp+57h+var_A8], eax
0x18000d1cb  test    eax, eax
  ... truncated ...
```
