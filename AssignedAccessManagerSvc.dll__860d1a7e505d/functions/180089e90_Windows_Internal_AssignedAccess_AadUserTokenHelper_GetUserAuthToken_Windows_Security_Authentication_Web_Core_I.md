# Windows::Internal::AssignedAccess::AadUserTokenHelper::GetUserAuthToken(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180089e90`
- end: `0x18008a2b6`
- name: `?GetUserAuthToken@AadUserTokenHelper@AssignedAccess@Internal@Windows@@AEAAJPEAUIWebTokenRequest@Core@Web@Authentication@Security@4@PEAUIWebAuthenticationCoreManagerStatics@67894@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1062`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180089cbc`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180013fac`
- `0x18001f2b0`
- `0x18002074c`
- `0x1800221e0`
- `0x1800271e4`
- `0x18002901c`
- `0x1800890c8`
- `0x180089518`
- `0x180089700`
- `0x180089e90`
- `0x18008a5e0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a0c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a22f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a0c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a22f`

## string_xrefs

- `0x180089ec0`: `AadUserTokenHelper_GetUserAuthToken`
- `0x180089f39`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x180089f8b`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x18008a00f`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x18008a098`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x18008a120`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x18008a1ac`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`
- `0x18008a20a`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\aadusertokenhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::AssignedAccess::AadUserTokenHelper::GetUserAuthToken(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rbx
  int v33; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v35; // rax
  __int64 v36; // rcx
  int v38; // [rsp+20h] [rbp-E0h] BYREF
  __int64 *v39; // [rsp+28h] [rbp-D8h] BYREF
  __int64 *v40; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+48h] [rbp-B8h] BYREF
  int v44; // [rsp+4Ch] [rbp-B4h] BYREF
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v48; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR v49[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v50[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v50,
    "AadUserTokenHelper_GetUserAuthToken");
  v50[0] = &AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken::`vftable';
  AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken::StartActivity((AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken *)v50);
  v7 = *a3;
  v48 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v7 + 48))(a3, a2, &v48);
  v11 = v8;
  if ( v8 >= 0 )
  {
    LOBYTE(v38) = 0;
    v8 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
           v48,
           v9,
           v10,
           &v38);
    v11 = v8;
    if ( v8 < 0 )
    {
      v12 = 129;
      goto LABEL_5;
    }
    if ( (_BYTE)v38 )
    {
      v11 = -2147023436;
      v13 = 2147943860LL;
      v12 = 130;
      goto LABEL_6;
    }
    v39 = 0;
    v14 = *v48;
    v39 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v14 + 64))(v48, &v39);
    v11 = v15;
    if ( v15 < 0 )
    {
      v16 = 132;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
        (const char *)(unsigned int)v15,
        v38);
LABEL_12:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
      goto LABEL_41;
    }
    v43 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v39 + 56))(v39, &v43);
    v11 = v15;
    if ( v15 < 0 )
    {
      v16 = 134;
      goto LABEL_11;
    }
    if ( v43 )
    {
      v41 = 0;
      v17 = *v39;
      v41 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v17 + 64))(v39, &v41);
      v11 = v18;
      if ( v18 >= 0 )
      {
        v44 = 0;
        v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 48LL))(v41, &v44);
        v11 = v18;
        if ( v18 >= 0 )
        {
          string = 0;
          v20 = v41;
          v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 56LL);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
            &string,
            0);
          v22 = v21(v20, &string);
          v11 = v22;
          if ( v22 >= 0 )
          {
            v49[0] = WindowsGetStringRawBuffer(string, 0);
            AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthTokenFailed<unsigned long &,unsigned short const *>(
              &v44,
              (__int64 *)v49);
            v11 = -2147467259;
            v23 = 2147500037LL;
            v24 = 144;
          }
          else
          {
            v23 = (unsigned int)v22;
            v24 = 142;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
            (const char *)v23,
            v38);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
          goto LABEL_19;
        }
        v19 = 140;
      }
      else
      {
        v19 = 138;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
        (const char *)(unsigned int)v18,
        v38);
LABEL_19:
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v41);
      goto LABEL_12;
    }
    v40 = 0;
    v25 = *v39;
    v40 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v25 + 48))(v39, &v40);
    v11 = v26;
    if ( v26 >= 0 )
    {
      v45 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v40 + 56))(v40, &v45);
      v11 = v26;
      if ( v26 >= 0 )
      {
        if ( v45 == 1 )
        {
          v42 = 0;
          v29 = *v40;
          v42 = 0;
          v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v29 + 48))(v40, 0, &v42);
          v11 = v30;
          if ( v30 >= 0 )
          {
            v47 = 0;
            v31 = v42;
            v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 48LL);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
              &v47,
              0);
            v33 = v32(v31, &v47);
            v11 = v33;
            if ( v33 >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(v47, 0);
              v35 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
              std::wstring::_Assign<unsigned short>(a4, v36, v35);
              wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v50);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v47);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v42);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v40);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v39);
              v11 = 0;
              goto LABEL_41;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9B,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
              (const char *)(unsigned int)v33,
              v38);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v47);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
              (const char *)(unsigned int)v30,
              v38);
          }
          wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v42);
          goto LABEL_30;
        }
        v11 = -2147418113;
        v28 = 2147549183LL;
        v27 = 151;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
          (const char *)v28,
          v38);
LABEL_30:
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v40);
        goto LABEL_12;
      }
      v27 = 150;
    }
    else
    {
      v27 = 148;
    }
    v28 = (unsigned int)v26;
    goto LABEL_29;
  }
  v12 = 127;
LABEL_5:
  v13 = (unsigned int)v8;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\aadusertokenhelper.cpp",
    (const char *)v13,
    v38);
LABEL_41:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v48);
  AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken::~AadUserTokenHelper_GetUserAuthToken((AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken *)v50);
  return v11;
}

```

## disassembly

```asm
0x180089e90  push    rbp
0x180089e92  push    rbx
0x180089e93  push    rsi
0x180089e94  push    rdi
0x180089e95  push    r14
0x180089e97  lea     rbp, [rsp-0E0h]
0x180089e9f  sub     rsp, 1E0h
0x180089ea6  mov     rax, cs:__security_cookie
0x180089ead  xor     rax, rsp
0x180089eb0  mov     [rbp+100h+var_30], rax
0x180089eb7  mov     rsi, r9
0x180089eba  mov     rdi, r8
0x180089ebd  mov     rbx, rdx
0x180089ec0  lea     rdx, aAadusertokenhe; "AadUserTokenHelper_GetUserAuthToken"
0x180089ec7  lea     rcx, [rbp+100h+var_180]
0x180089ecb  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180089ed0  lea     rax, ??_7AadUserTokenHelper_GetUserAuthToken@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken::`vftable'
0x180089ed7  mov     [rbp+100h+var_180], rax
0x180089edb  lea     rcx, [rbp+100h+var_180]; this
0x180089edf  call    ?StartActivity@AadUserTokenHelper_GetUserAuthToken@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken::StartActivity(void)
0x180089ee4  nop
0x180089ee5  mov     rax, [rdi]
0x180089ee8  xor     r14d, r14d
0x180089eeb  mov     [rsp+200h+var_198], r14
0x180089ef0  lea     r8, [rsp+200h+var_198]
0x180089ef5  mov     rdx, rbx
0x180089ef8  mov     rcx, rdi
0x180089efb  mov     rax, [rax+30h]
0x180089eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089f04  mov     ebx, eax
0x180089f06  test    eax, eax
0x180089f08  jns     short loc_180089F10
0x180089f0a  lea     edx, [r14+7Fh]
0x180089f0e  jmp     short loc_180089F2F
0x180089f10  mov     byte ptr [rsp+200h+var_1E0], r14b; int
0x180089f15  lea     r9, [rsp+200h+var_1E0]
0x180089f1a  mov     rcx, [rsp+200h+var_198]
0x180089f1f  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180089f24  mov     ebx, eax
0x180089f26  test    eax, eax
0x180089f28  jns     short loc_180089F4A
0x180089f2a  mov     edx, 81h; void *
0x180089f2f  mov     r9d, eax; char *
0x180089f32  mov     rcx, [rbp+108h]; this
0x180089f39  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180089f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089f45  jmp     loc_18008A283
0x180089f4a  cmp     byte ptr [rsp+200h+var_1E0], r14b
0x180089f4f  jz      short loc_180089F60
0x180089f51  mov     ebx, 800705B4h
0x180089f56  mov     r9d, ebx
0x180089f59  mov     edx, 82h
0x180089f5e  jmp     short loc_180089F32
0x180089f60  mov     [rsp+200h+var_1D8], r14
0x180089f65  mov     rcx, [rsp+200h+var_198]
0x180089f6a  mov     rax, [rcx]
0x180089f6d  mov     [rsp+200h+var_1D8], r14
0x180089f72  lea     rdx, [rsp+200h+var_1D8]
0x180089f77  mov     rax, [rax+40h]
0x180089f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089f80  mov     ebx, eax
0x180089f82  test    eax, eax
0x180089f84  jns     short loc_180089FB1
0x180089f86  mov     edx, 84h; void *
0x180089f8b  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180089f92  mov     r9d, eax; char *
0x180089f95  mov     rcx, [rbp+108h]; this
0x180089f9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089fa1  nop
0x180089fa2  lea     rcx, [rsp+200h+var_1D8]
0x180089fa7  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180089fac  jmp     loc_18008A283
0x180089fb1  mov     [rsp+200h+var_1B8], r14d
0x180089fb6  mov     rcx, [rsp+200h+var_1D8]
0x180089fbb  mov     rax, [rcx]
0x180089fbe  lea     rdx, [rsp+200h+var_1B8]
0x180089fc3  mov     rax, [rax+38h]
0x180089fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089fcc  mov     ebx, eax
0x180089fce  test    eax, eax
0x180089fd0  jns     short loc_180089FD9
0x180089fd2  mov     edx, 86h
0x180089fd7  jmp     short loc_180089F8B
0x180089fd9  cmp     [rsp+200h+var_1B8], r14d
0x180089fde  jz      loc_18008A0EB
0x180089fe4  mov     [rsp+200h+var_1C8], r14
0x180089fe9  mov     rcx, [rsp+200h+var_1D8]
0x180089fee  mov     rax, [rcx]
0x180089ff1  mov     [rsp+200h+var_1C8], r14
0x180089ff6  lea     rdx, [rsp+200h+var_1C8]
0x180089ffb  mov     rax, [rax+40h]
0x180089fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a004  mov     ebx, eax
0x18008a006  test    eax, eax
0x18008a008  jns     short loc_18008A035
0x18008a00a  mov     edx, 8Ah; void *
0x18008a00f  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18008a016  mov     r9d, eax; char *
0x18008a019  mov     rcx, [rbp+108h]; this
0x18008a020  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a025  nop
0x18008a026  lea     rcx, [rsp+200h+var_1C8]
0x18008a02b  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18008a030  jmp     loc_180089FA2
0x18008a035  mov     [rsp+200h+var_1B4], r14d
0x18008a03a  mov     rcx, [rsp+200h+var_1C8]
0x18008a03f  mov     rax, [rcx]
0x18008a042  lea     rdx, [rsp+200h+var_1B4]
0x18008a047  mov     rax, [rax+30h]
0x18008a04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a050  mov     ebx, eax
0x18008a052  test    eax, eax
0x18008a054  jns     short loc_18008A05D
0x18008a056  mov     edx, 8Ch
0x18008a05b  jmp     short loc_18008A00F
0x18008a05d  mov     [rsp+200h+string], r14
0x18008a062  mov     rdi, [rsp+200h+var_1C8]
0x18008a067  mov     rax, [rdi]
0x18008a06a  mov     rbx, [rax+38h]
0x18008a06e  xor     edx, edx
0x18008a070  lea     rcx, [rsp+200h+string]
0x18008a075  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18008a07a  lea     rdx, [rsp+200h+string]
0x18008a07f  mov     rcx, rdi
0x18008a082  mov     rax, rbx
0x18008a085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a08a  mov     ebx, eax
0x18008a08c  test    eax, eax
0x18008a08e  jns     short loc_18008A0BB
0x18008a090  mov     r9d, eax; char *
0x18008a093  mov     edx, 8Eh; void *
0x18008a098  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18008a09f  mov     rcx, [rbp+108h]; this
0x18008a0a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a0ab  nop
0x18008a0ac  lea     rcx, [rsp+200h+string]
0x18008a0b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18008a0b6  jmp     loc_18008A026
0x18008a0bb  xor     edx, edx; length
0x18008a0bd  mov     rcx, [rsp+200h+string]; string
0x18008a0c2  call    cs:__imp_WindowsGetStringRawBuffer
0x18008a0c8  mov     [rsp+200h+var_190], rax
0x18008a0cd  lea     rdx, [rsp+200h+var_190]
0x18008a0d2  lea     rcx, [rsp+200h+var_1B4]
0x18008a0d7  call    ??$AadUserTokenHelper_GetUserAuthTokenFailed@AEAKPEBG@AssignedAccessTelemetry@@SAXAEAK$$QEAPEBG@Z; AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthTokenFailed<ulong &,ushort const *>(ulong &,ushort const * &&)
0x18008a0dc  mov     ebx, 80004005h
0x18008a0e1  mov     r9d, ebx
0x18008a0e4  mov     edx, 90h
0x18008a0e9  jmp     short loc_18008A098
0x18008a0eb  mov     [rsp+200h+var_1D0], r14
0x18008a0f0  mov     rcx, [rsp+200h+var_1D8]
0x18008a0f5  mov     rax, [rcx]
0x18008a0f8  mov     [rsp+200h+var_1D0], r14
0x18008a0fd  lea     rdx, [rsp+200h+var_1D0]
0x18008a102  mov     rax, [rax+30h]
0x18008a106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a10b  mov     ebx, eax
0x18008a10d  test    eax, eax
0x18008a10f  jns     short loc_18008A13C
0x18008a111  mov     edx, 94h; void *
0x18008a116  mov     r9d, eax; char *
0x18008a119  mov     rcx, [rbp+108h]; this
0x18008a120  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18008a127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a12c  nop
0x18008a12d  lea     rcx, [rsp+200h+var_1D0]
0x18008a132  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18008a137  jmp     loc_180089FA2
0x18008a13c  mov     [rsp+200h+var_1B0], r14d
0x18008a141  mov     rcx, [rsp+200h+var_1D0]
0x18008a146  mov     rax, [rcx]
0x18008a149  lea     rdx, [rsp+200h+var_1B0]
0x18008a14e  mov     rax, [rax+38h]
0x18008a152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a157  mov     ebx, eax
0x18008a159  test    eax, eax
0x18008a15b  jns     short loc_18008A164
0x18008a15d  mov     edx, 96h
0x18008a162  jmp     short loc_18008A116
0x18008a164  cmp     [rsp+200h+var_1B0], 1
0x18008a169  jz      short loc_18008A17A
0x18008a16b  mov     ebx, 8000FFFFh
0x18008a170  mov     r9d, ebx
0x18008a173  mov     edx, 97h
0x18008a178  jmp     short loc_18008A119
0x18008a17a  mov     [rsp+200h+var_1C0], r14
0x18008a17f  mov     rcx, [rsp+200h+var_1D0]
0x18008a184  mov     rax, [rcx]
0x18008a187  mov     [rsp+200h+var_1C0], r14
0x18008a18c  lea     r8, [rsp+200h+var_1C0]
0x18008a191  xor     edx, edx
0x18008a193  mov     rax, [rax+30h]
0x18008a197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a19c  mov     ebx, eax
0x18008a19e  test    eax, eax
0x18008a1a0  jns     short loc_18008A1CD
0x18008a1a2  mov     rcx, [rbp+108h]; this
0x18008a1a9  mov     r9d, eax; char *
0x18008a1ac  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18008a1b3  mov     edx, 99h; void *
0x18008a1b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a1bd  nop
0x18008a1be  lea     rcx, [rsp+200h+var_1C0]
0x18008a1c3  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18008a1c8  jmp     loc_18008A12D
0x18008a1cd  mov     [rsp+200h+var_1A0], r14
0x18008a1d2  mov     rdi, [rsp+200h+var_1C0]
0x18008a1d7  mov     rax, [rdi]
0x18008a1da  mov     rbx, [rax+30h]
0x18008a1de  xor     edx, edx
0x18008a1e0  lea     rcx, [rsp+200h+var_1A0]
0x18008a1e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18008a1ea  lea     rdx, [rsp+200h+var_1A0]
0x18008a1ef  mov     rcx, rdi
0x18008a1f2  mov     rax, rbx
0x18008a1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1fa  mov     ebx, eax
0x18008a1fc  test    eax, eax
0x18008a1fe  jns     short loc_18008A228
0x18008a200  mov     rcx, [rbp+108h]; this
0x18008a207  mov     r9d, eax; char *
0x18008a20a  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18008a211  mov     edx, 9Bh; void *
0x18008a216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a21b  nop
0x18008a21c  lea     rcx, [rsp+200h+var_1A0]
0x18008a221  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18008a226  jmp     short loc_18008A1BE
0x18008a228  xor     edx, edx; length
0x18008a22a  mov     rcx, [rsp+200h+var_1A0]; string
0x18008a22f  call    cs:__imp_WindowsGetStringRawBuffer
0x18008a235  mov     rcx, rax
0x18008a238  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18008a23d  mov     r8, rax
0x18008a240  mov     rdx, rcx
0x18008a243  mov     rcx, rsi
0x18008a246  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18008a24b  lea     rcx, [rbp+100h+var_180]
0x18008a24f  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18008a254  nop
0x18008a255  lea     rcx, [rsp+200h+var_1A0]
0x18008a25a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18008a25f  nop
0x18008a260  lea     rcx, [rsp+200h+var_1C0]
0x18008a265  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18008a26a  nop
0x18008a26b  lea     rcx, [rsp+200h+var_1D0]
0x18008a270  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18008a275  nop
0x18008a276  lea     rcx, [rsp+200h+var_1D8]
0x18008a27b  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18008a280  mov     ebx, r14d
0x18008a283  lea     rcx, [rsp+200h+var_198]
0x18008a288  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18008a28d  nop
0x18008a28e  lea     rcx, [rbp+100h+var_180]; this
0x18008a292  call    ??1AadUserTokenHelper_GetUserAuthToken@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AadUserTokenHelper_GetUserAuthToken::~AadUserTokenHelper_GetUserAuthToken(void)
0x18008a297  mov     eax, ebx
0x18008a299  mov     rcx, [rbp+100h+var_30]
0x18008a2a0  xor     rcx, rsp; StackCookie
0x18008a2a3  call    __security_check_cookie
0x18008a2a8  add     rsp, 1E0h
0x18008a2af  pop     r14
0x18008a2b1  pop     rdi
0x18008a2b2  pop     rsi
0x18008a2b3  pop     rbx
0x18008a2b4  pop     rbp
0x18008a2b5  retn
```
