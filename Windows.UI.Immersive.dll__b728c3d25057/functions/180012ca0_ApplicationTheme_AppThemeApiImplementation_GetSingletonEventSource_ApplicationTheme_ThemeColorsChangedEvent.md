# ApplicationTheme::AppThemeApiImplementation::GetSingletonEventSource(ApplicationTheme::ThemeColorsChangedEvent * *)

- ea: `0x180012ca0`
- end: `0x18001323b`
- name: `?GetSingletonEventSource@AppThemeApiImplementation@ApplicationTheme@@EEAAJPEAPEAVThemeColorsChangedEvent@2@@Z`
- size: `1435`
- prototype: `__int64 __fastcall(ApplicationTheme::AppThemeApiImplementation *__hidden this, struct ApplicationTheme::ThemeColorsChangedEvent **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012ca0`
- `0x180013244`
- `0x180013270`
- `0x180034db4`
- `0x180050ba0`
- `0x18005659c`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012f95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001301b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001307b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012f95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001301b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001307b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ee0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ee0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013167`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013198`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013167`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012ce4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012ce4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012dae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012d25`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012d25`

## pseudocode

```c
__int64 __fastcall ApplicationTheme::AppThemeApiImplementation::GetSingletonEventSource(
        ApplicationTheme::AppThemeApiImplementation *this,
        struct ApplicationTheme::ThemeColorsChangedEvent **a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int v9; // eax
  int v10; // ebx
  HRESULT v11; // eax
  struct ApplicationTheme::ThemeColorsChangedEvent *v12; // rax
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v15; // rcx
  ApplicationTheme::ThemeColorsChangedEvent *v17; // rax
  __int64 v18; // rbx
  int v19; // edi
  __int64 v20; // rbx
  struct ApplicationTheme::ThemeColorsChangedEvent *v21; // rcx
  __int64 (__fastcall *v22)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent **); // rdi
  struct ApplicationTheme::ThemeColorsChangedEvent *v23; // rcx
  struct ApplicationTheme::ThemeColorsChangedEvent *v24; // r8
  int v25; // eax
  unsigned int v26; // ebx
  struct ApplicationTheme::ThemeColorsChangedEvent *v27; // rcx
  __int64 v28; // rcx
  struct ApplicationTheme::ThemeColorsChangedEvent *v29; // rcx
  struct ApplicationTheme::ThemeColorsChangedEvent *v30; // rcx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v33; // rcx
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v35; // rcx
  int v36; // [rsp+20h] [rbp-49h]
  char v37[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v38; // [rsp+38h] [rbp-31h] BYREF
  struct ApplicationTheme::ThemeColorsChangedEvent *v39; // [rsp+40h] [rbp-29h] BYREF
  __int64 v40; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  struct ApplicationTheme::ThemeColorsChangedEvent *v42; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER v43; // [rsp+60h] [rbp-9h] BYREF
  HSTRING v44; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+17h] BYREF
  HSTRING string; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  v38 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_17b0e613_942a_422d_904c_f90dc71a7dae, &v38);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v36);
    v28 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      return v5;
    }
    return v5;
  }
  v41 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v38 + 56LL))(
         v38,
         &v41);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v6,
      v36);
    v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v34)[2])(v34);
    }
    v35 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    return v5;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
  v40 = 0;
  v8 = **v41;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v40);
  v9 = v8(v7, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v40);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v9,
      v36);
    goto LABEL_54;
  }
  v44 = 0;
  v11 = WindowsCreateStringReference(L"ApplicationTheme.ThemeColorsChangedEvent", 0x28u, &v43, &v44);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v39 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent **))(*(_QWORD *)v40 + 48LL))(
          v40,
          v44,
          &v39);
  if ( v10 != -2147483637 )
  {
LABEL_7:
    if ( v10 >= 0 )
    {
      v12 = v39;
      v13 = v40;
      v39 = 0;
      *a2 = v12;
      v44 = 0;
      if ( v13 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
      if ( v41 )
      {
        v41 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
      }
      v15 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v10,
      v36);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    v44 = 0;
LABEL_54:
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v38);
    return (unsigned int)v10;
  }
  v42 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
  v42 = 0;
  v17 = (ApplicationTheme::ThemeColorsChangedEvent *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v17 )
  {
    v19 = -2147024882;
    goto LABEL_52;
  }
  v18 = ApplicationTheme::ThemeColorsChangedEvent::ThemeColorsChangedEvent(v17);
  v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ApplicationTheme::ThemeColorsChangedEvent **))v18)(
          v18,
          &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
          &v42);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v19 < 0 )
  {
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v19,
      v36);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
    v44 = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v38);
    return (unsigned int)v19;
  }
  AcquireSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
  v20 = v40;
  v21 = v39;
  v22 = *(__int64 (__fastcall **)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent **))(*(_QWORD *)v40 + 48LL);
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v10 = v22(v20, v44, &v39);
  if ( v10 != -2147483637 )
  {
LABEL_27:
    ReleaseSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
    v27 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_7;
  }
  v23 = v39;
  v37[0] = 0;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v42;
  if ( v42 )
  {
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v42 + 8LL))(v42);
    v24 = v42;
  }
  v39 = v24;
  v25 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent *, char *))(*(_QWORD *)v40 + 80LL))(
          v40,
          v44,
          v24,
          v37);
  v26 = v25;
  if ( v25 >= 0 )
  {
    if ( v37[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
        (const char *)0x8000FFFFLL,
        v36);
      ReleaseSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v39);
      v44 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v41);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v38);
      return 2147549183LL;
    }
    v10 = 0;
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18A,
    (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
    (const char *)(unsigned int)v25,
    v36);
  ReleaseSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
  v29 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v40;
  v44 = 0;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
  if ( v41 )
  {
    v41 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v32)[2])(v32);
  }
  v33 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return v26;
}

```

## disassembly

```asm
0x180012ca0  push    rbp
0x180012ca2  push    rsi
0x180012ca3  push    r14
0x180012ca5  lea     rbp, [rsp-47h]
0x180012caa  sub     rsp, 0B0h
0x180012cb1  mov     rax, cs:__security_cookie
0x180012cb8  xor     rax, rsp
0x180012cbb  mov     [rbp+57h+var_20], rax
0x180012cbf  xor     r14d, r14d
0x180012cc2  lea     r9, [rbp+57h+string]; string
0x180012cc6  mov     [rdx], r14
0x180012cc9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180012ccd  mov     rsi, rdx
0x180012cd0  mov     [rbp+57h+var_88], r14
0x180012cd4  mov     edx, 2Dh ; '-'; length
0x180012cd9  mov     [rbp+57h+string], r14
0x180012cdd  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180012ce4  call    cs:__imp_WindowsCreateStringReference
0x180012cea  test    eax, eax
0x180012cec  js      loc_18001315A
0x180012cf2  mov     rcx, [rbp+57h+var_88]
0x180012cf6  mov     [rsp+0C0h+arg_0], rbx
0x180012cfe  mov     rbx, [rbp+57h+string]
0x180012d02  test    rcx, rcx
0x180012d05  jz      short loc_180012D17
0x180012d07  mov     [rbp+57h+var_88], r14
0x180012d0b  mov     rax, [rcx]
0x180012d0e  mov     rax, [rax+10h]
0x180012d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d17  lea     r8, [rbp+57h+var_88]
0x180012d1b  mov     rcx, rbx
0x180012d1e  lea     rdx, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180012d25  call    cs:__imp_RoGetActivationFactory
0x180012d2b  mov     ebx, eax
0x180012d2d  test    eax, eax
0x180012d2f  js      loc_180012FBD
0x180012d35  mov     rcx, [rbp+57h+var_88]
0x180012d39  lea     rdx, [rbp+57h+var_70]
0x180012d3d  mov     [rbp+57h+var_70], r14
0x180012d41  mov     rax, [rcx]
0x180012d44  mov     rax, [rax+38h]
0x180012d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d4d  mov     ebx, eax
0x180012d4f  test    eax, eax
0x180012d51  js      loc_180013109
0x180012d57  mov     rbx, [rbp+57h+var_70]
0x180012d5b  lea     rcx, [rbp+57h+var_78]
0x180012d5f  mov     [rbp+57h+var_78], r14
0x180012d63  mov     [rsp+0C0h+arg_10], rdi
0x180012d6b  mov     rax, [rbx]
0x180012d6e  mov     rdi, [rax]
0x180012d71  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180012d76  lea     r8, [rbp+57h+var_78]
0x180012d7a  mov     rcx, rbx
0x180012d7d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180012d84  mov     rax, rdi
0x180012d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d8c  mov     ebx, eax
0x180012d8e  test    eax, eax
0x180012d90  js      loc_18001316E
0x180012d96  lea     r9, [rbp+57h+var_48]; string
0x180012d9a  mov     [rbp+57h+var_48], r14
0x180012d9e  lea     r8, [rbp+57h+var_60]; hstringHeader
0x180012da2  mov     edx, 28h ; '('; length
0x180012da7  lea     rcx, aApplicationthe; "ApplicationTheme.ThemeColorsChangedEven"...
0x180012dae  call    cs:__imp_WindowsCreateStringReference
0x180012db4  test    eax, eax
0x180012db6  js      loc_18001318B
0x180012dbc  mov     rcx, [rbp+57h+var_78]
0x180012dc0  lea     r8, [rbp+57h+var_80]
0x180012dc4  mov     rdx, [rbp+57h+var_48]
0x180012dc8  mov     [rbp+57h+var_80], r14
0x180012dcc  mov     rax, [rcx]
0x180012dcf  mov     rax, [rax+30h]
0x180012dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dd8  mov     ebx, eax
0x180012dda  cmp     eax, 8000000Bh
0x180012ddf  jz      loc_180012E71
0x180012de5  test    ebx, ebx
0x180012de7  js      loc_1800131F4
0x180012ded  mov     rax, [rbp+57h+var_80]
0x180012df1  mov     rcx, [rbp+57h+var_78]
0x180012df5  mov     [rbp+57h+var_80], r14
0x180012df9  mov     [rsi], rax
0x180012dfc  mov     [rbp+57h+var_48], r14
0x180012e00  test    rcx, rcx
0x180012e03  jz      short loc_180012E15
0x180012e05  mov     [rbp+57h+var_78], r14
0x180012e09  mov     rax, [rcx]
0x180012e0c  mov     rax, [rax+10h]
0x180012e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e15  mov     rcx, [rbp+57h+var_70]
0x180012e19  test    rcx, rcx
0x180012e1c  jz      short loc_180012E2E
0x180012e1e  mov     [rbp+57h+var_70], r14
0x180012e22  mov     rax, [rcx]
0x180012e25  mov     rax, [rax+10h]
0x180012e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e2e  mov     rcx, [rbp+57h+var_88]
0x180012e32  test    rcx, rcx
0x180012e35  jz      short loc_180012E47
0x180012e37  mov     [rbp+57h+var_88], r14
0x180012e3b  mov     rax, [rcx]
0x180012e3e  mov     rax, [rax+10h]
0x180012e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e47  xor     eax, eax
0x180012e49  mov     rdi, [rsp+0C0h+arg_10]
0x180012e51  mov     rbx, [rsp+0C0h+arg_0]
0x180012e59  mov     rcx, [rbp+57h+var_20]
0x180012e5d  xor     rcx, rsp; StackCookie
0x180012e60  call    __security_check_cookie
0x180012e65  add     rsp, 0B0h
0x180012e6c  pop     r14
0x180012e6e  pop     rsi
0x180012e6f  pop     rbp
0x180012e70  retn
0x180012e71  lea     rcx, [rbp+57h+var_68]
0x180012e75  mov     [rbp+57h+var_68], r14
0x180012e79  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180012e7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012e85  mov     [rbp+57h+var_68], r14
0x180012e89  mov     ecx, 78h ; 'x'; unsigned __int64
0x180012e8e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012e93  test    rax, rax
0x180012e96  jz      loc_18001319F
0x180012e9c  mov     rcx, rax; this
0x180012e9f  call    ??0ThemeColorsChangedEvent@ApplicationTheme@@QEAA@XZ; ApplicationTheme::ThemeColorsChangedEvent::ThemeColorsChangedEvent(void)
0x180012ea4  mov     rbx, rax
0x180012ea7  lea     r8, [rbp+57h+var_68]
0x180012eab  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180012eb2  mov     rcx, [rax]
0x180012eb5  mov     rax, [rcx]
0x180012eb8  mov     rcx, rbx
0x180012ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec0  mov     rcx, [rbx]
0x180012ec3  mov     edi, eax
0x180012ec5  mov     rax, [rcx+10h]
0x180012ec9  mov     rcx, rbx
0x180012ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ed1  test    edi, edi
0x180012ed3  js      loc_1800131A4
0x180012ed9  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180012ee0  call    cs:__imp_AcquireSRWLockExclusive
0x180012ee6  mov     rbx, [rbp+57h+var_78]
0x180012eea  mov     rcx, [rbp+57h+var_80]
0x180012eee  mov     rax, [rbx]
0x180012ef1  mov     rdi, [rax+30h]
0x180012ef5  test    rcx, rcx
0x180012ef8  jz      short loc_180012F0A
0x180012efa  mov     [rbp+57h+var_80], r14
0x180012efe  mov     rdx, [rcx]
0x180012f01  mov     rax, [rdx+10h]
0x180012f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f0a  mov     rdx, [rbp+57h+var_48]
0x180012f0e  lea     r8, [rbp+57h+var_80]
0x180012f12  mov     rcx, rbx
0x180012f15  mov     rax, rdi
0x180012f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f1d  mov     ebx, eax
0x180012f1f  cmp     eax, 8000000Bh
0x180012f24  jnz     short loc_180012F8E
0x180012f26  mov     rcx, [rbp+57h+var_80]
0x180012f2a  mov     [rbp+57h+var_90], r14b
0x180012f2e  test    rcx, rcx
0x180012f31  jz      short loc_180012F43
0x180012f33  mov     [rbp+57h+var_80], r14
0x180012f37  mov     rax, [rcx]
0x180012f3a  mov     rax, [rax+10h]
0x180012f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f43  mov     r8, [rbp+57h+var_68]
0x180012f47  test    r8, r8
0x180012f4a  jz      short loc_180012F5F
0x180012f4c  mov     rax, [r8]
0x180012f4f  mov     rcx, r8
0x180012f52  mov     rax, [rax+8]
0x180012f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f5b  mov     r8, [rbp+57h+var_68]
0x180012f5f  mov     rcx, [rbp+57h+var_78]
0x180012f63  lea     r9, [rbp+57h+var_90]
0x180012f67  mov     rdx, [rbp+57h+var_48]
0x180012f6b  mov     [rbp+57h+var_80], r8
0x180012f6f  mov     rax, [rcx]
0x180012f72  mov     rax, [rax+50h]
0x180012f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7b  mov     ebx, eax
0x180012f7d  test    eax, eax
0x180012f7f  js      loc_18001305C
0x180012f85  cmp     [rbp+57h+var_90], r14b
0x180012f89  jnz     short loc_180012FF9
0x180012f8b  mov     ebx, r14d
0x180012f8e  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180012f95  call    cs:__imp_ReleaseSRWLockExclusive
0x180012f9b  mov     rcx, [rbp+57h+var_68]
0x180012f9f  test    rcx, rcx
0x180012fa2  jz      loc_180012DE5
0x180012fa8  mov     [rbp+57h+var_68], r14
0x180012fac  mov     rax, [rcx]
0x180012faf  mov     rax, [rax+10h]
0x180012fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fb8  jmp     loc_180012DE5
0x180012fbd  mov     rcx, [rbp+5Fh]; this
0x180012fc1  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180012fc8  mov     r9d, ebx; char *
0x180012fcb  mov     edx, 16Bh; void *
0x180012fd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012fd5  mov     rcx, [rbp+57h+var_88]
0x180012fd9  test    rcx, rcx
0x180012fdc  jz      loc_180013153
0x180012fe2  mov     [rbp+57h+var_88], r14
0x180012fe6  mov     rax, [rcx]
0x180012fe9  mov     rax, [rax+10h]
0x180012fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ff2  mov     eax, ebx
0x180012ff4  jmp     loc_180012E51
0x180012ff9  mov     rcx, [rbp+5Fh]; this
0x180012ffd  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180013004  mov     r9d, 8000FFFFh; char *
0x18001300a  mov     edx, 18Bh; void *
0x18001300f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013014  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18001301b  call    cs:__imp_ReleaseSRWLockExclusive
0x180013021  lea     rcx, [rbp+57h+var_68]
0x180013025  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18001302a  lea     rcx, [rbp+57h+var_80]
0x18001302e  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013033  lea     rcx, [rbp+57h+var_78]
0x180013037  mov     [rbp+57h+var_48], r14
0x18001303b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013040  lea     rcx, [rbp+57h+var_70]
0x180013044  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013049  lea     rcx, [rbp+57h+var_88]
0x18001304d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013052  mov     eax, 8000FFFFh
0x180013057  jmp     loc_180012E49
0x18001305c  mov     rcx, [rbp+5Fh]; this
0x180013060  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180013067  mov     r9d, ebx; char *
0x18001306a  mov     edx, 18Ah; void *
0x18001306f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013074  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18001307b  call    cs:__imp_ReleaseSRWLockExclusive
0x180013081  mov     rcx, [rbp+57h+var_68]
0x180013085  test    rcx, rcx
0x180013088  jz      short loc_18001309A
0x18001308a  mov     [rbp+57h+var_68], r14
0x18001308e  mov     rax, [rcx]
0x180013091  mov     rax, [rax+10h]
0x180013095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001309a  mov     rcx, [rbp+57h+var_80]
0x18001309e  test    rcx, rcx
0x1800130a1  jz      short loc_1800130B3
0x1800130a3  mov     [rbp+57h+var_80], r14
0x1800130a7  mov     rax, [rcx]
0x1800130aa  mov     rax, [rax+10h]
0x1800130ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130b3  mov     rcx, [rbp+57h+var_78]
0x1800130b7  mov     [rbp+57h+var_48], r14
0x1800130bb  test    rcx, rcx
0x1800130be  jz      short loc_1800130D0
0x1800130c0  mov     [rbp+57h+var_78], r14
0x1800130c4  mov     rax, [rcx]
0x1800130c7  mov     rax, [rax+10h]
0x1800130cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130d0  mov     rcx, [rbp+57h+var_70]
0x1800130d4  test    rcx, rcx
0x1800130d7  jz      short loc_1800130E9
0x1800130d9  mov     [rbp+57h+var_70], r14
0x1800130dd  mov     rax, [rcx]
0x1800130e0  mov     rax, [rax+10h]
0x1800130e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130e9  mov     rcx, [rbp+57h+var_88]
0x1800130ed  test    rcx, rcx
0x1800130f0  jz      short loc_180013102
0x1800130f2  mov     [rbp+57h+var_88], r14
0x1800130f6  mov     rax, [rcx]
0x1800130f9  mov     rax, [rax+10h]
0x1800130fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013102  mov     eax, ebx
0x180013104  jmp     loc_180012E49
0x180013109  mov     rcx, [rbp+5Fh]; this
0x18001310d  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180013114  mov     r9d, ebx; char *
0x180013117  mov     edx, 16Eh; void *
0x18001311c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013121  mov     rcx, [rbp+57h+var_70]
0x180013125  test    rcx, rcx
0x180013128  jz      short loc_18001313A
0x18001312a  mov     [rbp+57h+var_70], r14
0x18001312e  mov     rax, [rcx]
0x180013131  mov     rax, [rax+10h]
0x180013135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001313a  mov     rcx, [rbp+57h+var_88]
0x18001313e  test    rcx, rcx
0x180013141  jz      short loc_180013153
0x180013143  mov     [rbp+57h+var_88], r14
0x180013147  mov     rax, [rcx]
0x18001314a  mov     rax, [rax+10h]
0x18001314e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013153  mov     eax, ebx
0x180013155  jmp     loc_180012E51
  ... truncated ...
```
