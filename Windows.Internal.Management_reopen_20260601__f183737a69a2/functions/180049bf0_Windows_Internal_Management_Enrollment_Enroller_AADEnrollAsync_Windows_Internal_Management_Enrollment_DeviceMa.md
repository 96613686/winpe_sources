# Windows::Internal::Management::Enrollment::Enroller::AADEnrollAsync(Windows::Internal::Management::Enrollment::DeviceManagementDeviceEnrollmentInformation,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> * *)

- ea: `0x180049bf0`
- end: `0x18004a2e2`
- name: `?AADEnrollAsync@Enroller@Enrollment@Management@Internal@Windows@@UEAAJUDeviceManagementDeviceEnrollmentInformation@2345@PEAPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@5@@Z`
- size: `1778`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004eb0`
- `0x180009be4`
- `0x18000a5c4`
- `0x18000dc18`
- `0x18001656c`
- `0x180017024`
- `0x18001823c`
- `0x18003a904`
- `0x18003afc8`
- `0x18003b2cc`
- `0x18003b374`
- `0x18003d034`
- `0x18003e440`
- `0x1800405a4`
- `0x180041874`
- `0x180045fa4`
- `0x180049bf0`
- `0x18004ac2c`
- `0x18005b2f8`
- `0x18005c134`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180049e08`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180049e08`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x180049c85`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x180049c85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Management::Enrollment::Enroller::AADEnrollAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // eax
  int IsLockedToMmpc; // ebx
  __int64 v6; // rax
  char v7; // cl
  int v8; // r8d
  unsigned int v9; // ebx
  char v10; // di
  __int64 v11; // rsi
  __int64 v12; // r14
  __int64 v13; // r15
  __int64 v14; // r13
  HSTRING *v15; // rdx
  __int64 v16; // r12
  int TargetedSID; // edx
  __int64 v18; // rax
  unsigned int v19; // edx
  HSTRING *v20; // rbx
  const unsigned __int16 *v21; // rax
  int v22; // edi
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+74h] [rbp-8Ch] BYREF
  _QWORD v27[2]; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h] BYREF
  HSTRING *v31; // [rsp+98h] [rbp-68h] BYREF
  HSTRING *v32; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING *v33; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING *v34; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING *v37; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v38; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING *v39; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING *v40; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING *v41; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING *v42; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v43; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v44; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v45[24]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v46; // [rsp+120h] [rbp+20h]
  _BYTE v47[32]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v46 = a3;
  v35 = a2;
  v26 = 0;
  v36 = 0;
  v4 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Enrollment::EnrollmentResult,Windows::Internal::Management::Enrollment::EnrollmentResult,>(&v36);
  IsLockedToMmpc = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\enroller.cpp",
      (const char *)(unsigned int)v4,
      v24);
    goto LABEL_95;
  }
  v25 = 0;
  v6 = _lambda_06f40ebce54247e3f11ddce21d34cd52_::_lambda_06f40ebce54247e3f11ddce21d34cd52_(v27, &v26, a2);
  wil::ScopeExit__lambda_69febd7a99d3cb245321704ad0be5e6f___(v45, v6);
  IsLockedToMmpc = Mmpc_Lockdown_IsLockedToMmpc(&v25);
  v26 = IsLockedToMmpc;
  if ( IsLockedToMmpc < 0 )
  {
LABEL_4:
    wil::details::ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___::_ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___(v45);
    goto LABEL_95;
  }
  v28 = 0;
  v26 = Mmpc_IsOnPremiseSupportingDevice(&v28);
  if ( v26 >= 0 && v28 )
  {
    wil::details::ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___::_ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___(v45);
    IsLockedToMmpc = -2145910746;
    goto LABEL_95;
  }
  v7 = 0;
  v8 = *(_DWORD *)(a2 + 32);
  if ( v8 > 7 )
  {
    switch ( v8 )
    {
      case 8:
        if ( !v25 )
        {
          v7 = 4;
          goto LABEL_42;
        }
        break;
      case 9:
        wil::details::ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___::_ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___(v45);
        IsLockedToMmpc = -2147467263;
        goto LABEL_95;
      case 10:
        if ( !v25 )
        {
          v7 = 4;
          goto LABEL_42;
        }
        break;
      case 11:
        if ( !v25 )
        {
          v7 = 4;
LABEL_42:
          v9 = 6;
          goto LABEL_43;
        }
        break;
      case 12:
        goto LABEL_31;
      default:
        goto LABEL_30;
    }
    wil::details::ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___::_ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___(v45);
    IsLockedToMmpc = -2145910764;
    goto LABEL_95;
  }
  if ( v8 == 7 )
  {
    if ( v25 )
    {
      v9 = 24;
      v7 = 0;
      goto LABEL_43;
    }
    v7 = 0;
    goto LABEL_30;
  }
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      if ( v8 != 2 )
      {
        if ( v8 != 3 )
        {
          if ( v8 != 4 && v8 != 6 )
            goto LABEL_30;
          goto LABEL_31;
        }
        v7 = 0x80;
      }
      v7 |= 1u;
      if ( v25 )
        v9 = 24;
      else
        v9 = 5;
      goto LABEL_43;
    }
LABEL_30:
    v9 = 13;
    goto LABEL_43;
  }
LABEL_31:
  v9 = 6;
  if ( v25 )
    v9 = 26;
  v7 = 4;
LABEL_43:
  v10 = v7;
  if ( !*(_DWORD *)(a2 + 80) )
    v10 = v7;
  v29 = 0;
  OOBEComplete(&v29);
  IsLockedToMmpc = Windows::Internal::Management::Enrollment::Enroller::AccessCheck(v9);
  v26 = IsLockedToMmpc;
  if ( IsLockedToMmpc < 0 )
    goto LABEL_4;
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v11 = v27[0];
  Windows::Internal::String::Initialize((HSTRING *)(v27[0] + 8LL), (HSTRING *)a2);
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v12 = v27[0];
  Windows::Internal::String::Initialize((HSTRING *)(v27[0] + 8LL), (HSTRING *)(a2 + 8));
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v13 = v27[0];
  Windows::Internal::String::Initialize((HSTRING *)(v27[0] + 8LL), (HSTRING *)(a2 + 16));
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v14 = v27[0];
  Windows::Internal::String::Initialize((HSTRING *)(v27[0] + 8LL), (HSTRING *)(a2 + 24));
  CreateRefCountedObj<Windows::Internal::String,>(&v34);
  Windows::Internal::String::Initialize(v34 + 1, (HSTRING *)(a2 + 40));
  CreateRefCountedObj<Windows::Internal::String,>(&v33);
  Windows::Internal::String::Initialize(v33 + 1, (HSTRING *)(a2 + 48));
  CreateRefCountedObj<Windows::Internal::String,>(&v32);
  Windows::Internal::String::Initialize(v32 + 1, (HSTRING *)(a2 + 56));
  CreateRefCountedObj<Windows::Internal::String,>(&v31);
  Windows::Internal::String::Initialize(v31 + 1, (HSTRING *)(a2 + 64));
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v15 = (HSTRING *)(a2 + 72);
  v16 = v27[0];
  Windows::Internal::String::Initialize((HSTRING *)(v27[0] + 8LL), v15);
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  std::wstring::wstring(v47);
  TargetedSID = GetTargetedSID((__int64)v47);
  LODWORD(v30) = TargetedSID;
  v26 = TargetedSID;
  if ( (byte_1800FF241 & 1) != 0 )
  {
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
    McTemplateU0zd_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, EnterpriseDiagnosticsEnrollAPISID, v18, v19);
    TargetedSID = v26;
    LODWORD(v30) = v26;
  }
  v20 = (HSTRING *)v27[0];
  if ( TargetedSID >= 0 )
  {
    v21 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
    if ( v21 )
      Windows::Internal::String::_InitializeHelper(v20 + 1, v21);
    goto LABEL_53;
  }
  if ( *(_DWORD *)(v35 + 32) != 7 && *(_DWORD *)(v35 + 32) != 1 )
  {
LABEL_53:
    v30 = v36;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v30);
    v37 = v20;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v37);
    v38 = v16;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v38);
    v39 = v31;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v39);
    v40 = v32;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v40);
    v41 = v33;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v41);
    v42 = v34;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v42);
    v43 = v14;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v43);
    v44 = v13;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v44);
    v35 = v12;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v35);
    v27[0] = v11;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(v27);
    v22 = AADEnrollAsyncImpl<Windows::Internal::Management::Enrollment::IEnrollmentResult,Windows::Internal::Management::Enrollment::EnrollmentResult>(
            (unsigned int)v27,
            (unsigned int)&v35,
            (unsigned int)&v44,
            (unsigned int)&v43,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v38,
            (__int64)&v37,
            v10,
            (__int64)&v30,
            v46);
    std::wstring::~wstring(v47);
    if ( v20 )
      (*((void (__fastcall **)(HSTRING *))*v20 + 2))(v20);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v31 )
      (*((void (__fastcall **)(HSTRING *))*v31 + 2))(v31);
    if ( v32 )
      (*((void (__fastcall **)(HSTRING *))*v32 + 2))(v32);
    if ( v33 )
      (*((void (__fastcall **)(HSTRING *))*v33 + 2))(v33);
    if ( v34 )
      (*((void (__fastcall **)(HSTRING *))*v34 + 2))(v34);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    wil::details::ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___::_ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___(v45);
    IsLockedToMmpc = v22;
    goto LABEL_95;
  }
  std::wstring::~wstring(v47);
  if ( v20 )
    (*((void (__fastcall **)(HSTRING *))*v20 + 2))(v20);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v31 )
    (*((void (__fastcall **)(HSTRING *))*v31 + 2))(v31);
  if ( v32 )
    (*((void (__fastcall **)(HSTRING *))*v32 + 2))(v32);
  if ( v33 )
    (*((void (__fastcall **)(HSTRING *))*v33 + 2))(v33);
  if ( v34 )
    (*((void (__fastcall **)(HSTRING *))*v34 + 2))(v34);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  wil::details::ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___::_ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___(v45);
  IsLockedToMmpc = v30;
LABEL_95:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  return (unsigned int)IsLockedToMmpc;
}

```

## disassembly

```asm
0x180049bf0  mov     [rsp-8+arg_0], rbx
0x180049bf5  push    rbp
0x180049bf6  push    rsi
0x180049bf7  push    rdi
0x180049bf8  push    r12
0x180049bfa  push    r13
0x180049bfc  push    r14
0x180049bfe  push    r15
0x180049c00  lea     rbp, [rsp-50h]
0x180049c05  sub     rsp, 150h
0x180049c0c  mov     rax, cs:__security_cookie
0x180049c13  xor     rax, rsp
0x180049c16  mov     [rbp+80h+var_38], rax
0x180049c1a  mov     [rbp+80h+var_60], r8
0x180049c1e  mov     r12, rdx
0x180049c21  mov     [rbp+80h+var_C8], rdx
0x180049c25  xor     esi, esi
0x180049c27  mov     [rsp+180h+var_10C], esi
0x180049c2b  mov     [rbp+80h+var_C0], rsi
0x180049c2f  lea     rcx, [rbp+80h+var_C0]
0x180049c33  call    ??$MakeAndInitialize@VEnrollmentResult@Enrollment@Management@Internal@Windows@@V12345@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VEnrollmentResult@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Enrollment::EnrollmentResult,Windows::Internal::Management::Enrollment::EnrollmentResult,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::EnrollmentResult>>)
0x180049c38  mov     ebx, eax
0x180049c3a  test    eax, eax
0x180049c3c  jns     short loc_180049C5E
0x180049c3e  mov     rcx, [rbp+88h]; this
0x180049c45  mov     r9d, eax; char *
0x180049c48  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180049c4f  mov     edx, 9A2h; void *
0x180049c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049c59  jmp     loc_18004A2AF
0x180049c5e  mov     [rsp+180h+var_110], esi
0x180049c62  mov     r8, r12
0x180049c65  lea     rdx, [rsp+180h+var_10C]
0x180049c6a  lea     rcx, [rsp+180h+var_108]
0x180049c6f  call    ??0_lambda_06f40ebce54247e3f11ddce21d34cd52_@@QEAA@PEAV?$SimpleVectorView@PEAUIPackage@Provisioning@Management@Windows@@V?$Vector@PEAUIPackage@Provisioning@Management@Windows@@U?$DefaultEqualityPredicate@PEAUIPackage@Provisioning@Management@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@U?$VectorOptions@PEAUIPackage@Provisioning@Management@Windows@@$00$00$0A@@6784@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAPEAI@Z; _lambda_06f40ebce54247e3f11ddce21d34cd52_::_lambda_06f40ebce54247e3f11ddce21d34cd52_(Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::Vector<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Management::Provisioning::IPackage *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,XWinRT::IntVersionTag,1> *,uint * &)
0x180049c74  mov     rdx, rax
0x180049c77  lea     rcx, [rbp+80h+var_78]
0x180049c7b  call    wil__ScopeExit__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049c80  lea     rcx, [rsp+180h+var_110]
0x180049c85  call    cs:__imp_Mmpc_Lockdown_IsLockedToMmpc
0x180049c8c  nop     dword ptr [rax+rax+00h]
0x180049c91  mov     ebx, eax
0x180049c93  mov     [rsp+180h+var_10C], eax
0x180049c97  test    eax, eax
0x180049c99  jns     short loc_180049CA9
0x180049c9b  lea     rcx, [rbp+80h+var_78]
0x180049c9f  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049ca4  jmp     loc_18004A2AF
0x180049ca9  mov     [rbp+80h+var_F8], esi
0x180049cac  lea     rcx, [rbp+80h+var_F8]; int *
0x180049cb0  call    ?Mmpc_IsOnPremiseSupportingDevice@@YAJPEAH@Z; Mmpc_IsOnPremiseSupportingDevice(int *)
0x180049cb5  mov     [rsp+180h+var_10C], eax
0x180049cb9  test    eax, eax
0x180049cbb  js      short loc_180049CD5
0x180049cbd  cmp     [rbp+80h+var_F8], esi
0x180049cc0  jz      short loc_180049CD5
0x180049cc2  lea     rcx, [rbp+80h+var_78]
0x180049cc6  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049ccb  mov     ebx, 80180026h
0x180049cd0  jmp     loc_18004A2AF
0x180049cd5  mov     ecx, esi
0x180049cd7  mov     r8d, [r12+20h]
0x180049cdc  cmp     r8d, 7
0x180049ce0  jg      short loc_180049D54
0x180049ce2  jz      short loc_180049D38
0x180049ce4  mov     edx, r8d
0x180049ce7  test    r8d, r8d
0x180049cea  jz      loc_180049D7C
0x180049cf0  sub     edx, 1
0x180049cf3  jz      short loc_180049D70
0x180049cf5  sub     edx, 1
0x180049cf8  jz      short loc_180049D17
0x180049cfa  sub     edx, 1
0x180049cfd  jz      short loc_180049D12
0x180049cff  sub     edx, 1
0x180049d02  jz      short loc_180049D0B
0x180049d04  cmp     edx, 2
0x180049d07  jz      short loc_180049D7C
0x180049d09  jmp     short loc_180049D70
0x180049d0b  mov     ecx, 200h
0x180049d10  jmp     short loc_180049D7C
0x180049d12  mov     ecx, 80h
0x180049d17  or      ecx, 1
0x180049d1a  cmp     [rsp+180h+var_110], esi
0x180049d1e  jz      short loc_180049D2E
0x180049d20  mov     ebx, 18h
0x180049d25  bts     ecx, 12h
0x180049d29  jmp     loc_180049DF3
0x180049d2e  mov     ebx, 5
0x180049d33  jmp     loc_180049DF3
0x180049d38  cmp     [rsp+180h+var_110], esi
0x180049d3c  jz      short loc_180049D4D
0x180049d3e  mov     ebx, 18h
0x180049d43  mov     ecx, 41000h
0x180049d48  jmp     loc_180049DF3
0x180049d4d  mov     ecx, 1000h
0x180049d52  jmp     short loc_180049D70
0x180049d54  mov     edx, r8d
0x180049d57  sub     edx, 8
0x180049d5a  jz      short loc_180049DD0
0x180049d5c  sub     edx, 1
0x180049d5f  jz      short loc_180049DBD
0x180049d61  sub     edx, 1
0x180049d64  jz      short loc_180049DB0
0x180049d66  sub     edx, 1
0x180049d69  jz      short loc_180049DA3
0x180049d6b  cmp     edx, 1
0x180049d6e  jz      short loc_180049D77
0x180049d70  mov     ebx, 0Dh
0x180049d75  jmp     short loc_180049DF3
0x180049d77  mov     ecx, 100000h
0x180049d7c  mov     eax, ecx
0x180049d7e  bts     eax, 0Ch
0x180049d82  mov     ebx, 6
0x180049d87  cmp     r8d, ebx
0x180049d8a  cmovnz  eax, ecx
0x180049d8d  mov     ecx, eax
0x180049d8f  cmp     [rsp+180h+var_110], esi
0x180049d93  jz      short loc_180049D9E
0x180049d95  mov     ebx, 1Ah
0x180049d9a  bts     ecx, 12h
0x180049d9e  or      ecx, 4
0x180049da1  jmp     short loc_180049DF3
0x180049da3  cmp     [rsp+180h+var_110], esi
0x180049da7  jnz     short loc_180049DD6
0x180049da9  mov     ecx, 10004h
0x180049dae  jmp     short loc_180049DEE
0x180049db0  cmp     [rsp+180h+var_110], esi
0x180049db4  jnz     short loc_180049DD6
0x180049db6  mov     ecx, 8004h
0x180049dbb  jmp     short loc_180049DEE
0x180049dbd  lea     rcx, [rbp+80h+var_78]
0x180049dc1  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049dc6  mov     ebx, 80004001h
0x180049dcb  jmp     loc_18004A2AF
0x180049dd0  cmp     [rsp+180h+var_110], esi
0x180049dd4  jz      short loc_180049DE9
0x180049dd6  lea     rcx, [rbp+80h+var_78]
0x180049dda  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049ddf  mov     ebx, 80180014h
0x180049de4  jmp     loc_18004A2AF
0x180049de9  mov     ecx, 2004h
0x180049dee  mov     ebx, 6
0x180049df3  mov     edi, ecx
0x180049df5  bts     edi, 11h
0x180049df9  cmp     [r12+50h], esi
0x180049dfe  cmovz   edi, ecx
0x180049e01  mov     [rbp+80h+var_F4], esi
0x180049e04  lea     rcx, [rbp+80h+var_F4]
0x180049e08  call    cs:__imp_OOBEComplete
0x180049e0f  nop     dword ptr [rax+rax+00h]
0x180049e14  test    eax, eax
0x180049e16  jz      short loc_180049E21
0x180049e18  cmp     [rbp+80h+var_F4], esi
0x180049e1b  jz      short loc_180049E21
0x180049e1d  bts     edi, 16h
0x180049e21  mov     ecx, ebx
0x180049e23  call    ?AccessCheck@Enroller@Enrollment@Management@Internal@Windows@@SAJW4EnrollmentEnrollType@@@Z; Windows::Internal::Management::Enrollment::Enroller::AccessCheck(EnrollmentEnrollType)
0x180049e28  mov     ebx, eax
0x180049e2a  mov     [rsp+180h+var_10C], eax
0x180049e2e  test    eax, eax
0x180049e30  js      loc_180049C9B
0x180049e36  lea     rcx, [rsp+180h+var_108]
0x180049e3b  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049e40  mov     rsi, [rsp+180h+var_108]
0x180049e45  lea     rcx, [rsi+8]; this
0x180049e49  mov     rdx, r12; HSTRING *
0x180049e4c  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049e51  lea     rcx, [rsp+180h+var_108]
0x180049e56  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049e5b  lea     rdx, [r12+8]; HSTRING *
0x180049e60  mov     r14, [rsp+180h+var_108]
0x180049e65  lea     rcx, [r14+8]; this
0x180049e69  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049e6e  lea     rcx, [rsp+180h+var_108]
0x180049e73  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049e78  lea     rdx, [r12+10h]; HSTRING *
0x180049e7d  mov     r15, [rsp+180h+var_108]
0x180049e82  lea     rcx, [r15+8]; this
0x180049e86  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049e8b  lea     rcx, [rsp+180h+var_108]
0x180049e90  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049e95  lea     rdx, [r12+18h]; HSTRING *
0x180049e9a  mov     r13, [rsp+180h+var_108]
0x180049e9f  lea     rcx, [r13+8]; this
0x180049ea3  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049ea8  lea     rcx, [rbp+80h+var_D0]
0x180049eac  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049eb1  lea     rdx, [r12+28h]; HSTRING *
0x180049eb6  mov     rcx, [rbp+80h+var_D0]
0x180049eba  add     rcx, 8; this
0x180049ebe  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049ec3  lea     rcx, [rbp+80h+var_D8]
0x180049ec7  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049ecc  lea     rdx, [r12+30h]; HSTRING *
0x180049ed1  mov     rcx, [rbp+80h+var_D8]
0x180049ed5  add     rcx, 8; this
0x180049ed9  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049ede  lea     rcx, [rbp+80h+var_E0]
0x180049ee2  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049ee7  lea     rdx, [r12+38h]; HSTRING *
0x180049eec  mov     rcx, [rbp+80h+var_E0]
0x180049ef0  add     rcx, 8; this
0x180049ef4  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049ef9  lea     rcx, [rbp+80h+var_E8]
0x180049efd  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049f02  lea     rdx, [r12+40h]; HSTRING *
0x180049f07  mov     rcx, [rbp+80h+var_E8]
0x180049f0b  add     rcx, 8; this
0x180049f0f  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049f14  lea     rcx, [rsp+180h+var_108]
0x180049f19  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049f1e  lea     rdx, [r12+48h]; HSTRING *
0x180049f23  mov     r12, [rsp+180h+var_108]
0x180049f28  lea     rcx, [r12+8]; this
0x180049f2d  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049f32  lea     rcx, [rsp+180h+var_108]
0x180049f37  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049f3c  lea     rcx, [rbp+80h+var_58]
0x180049f40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180049f45  lea     rcx, [rbp+80h+var_58]
0x180049f49  call    GetTargetedSID
0x180049f4e  mov     edx, eax
0x180049f50  mov     dword ptr [rbp+80h+var_F0], eax
0x180049f53  mov     [rsp+180h+var_10C], eax
0x180049f57  test    cs:byte_1800FF241, 1
0x180049f5e  jz      short loc_180049F89
0x180049f60  lea     rcx, [rbp+80h+var_58]
0x180049f64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049f69  mov     r8, rax
0x180049f6c  mov     r9d, edx
0x180049f6f  lea     rdx, EnterpriseDiagnosticsEnrollAPISID
0x180049f76  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180049f7d  call    McTemplateU0zd_EventWriteTransfer
0x180049f82  mov     edx, [rsp+180h+var_10C]
0x180049f86  mov     dword ptr [rbp+80h+var_F0], edx
0x180049f89  mov     rbx, [rsp+180h+var_108]
0x180049f8e  test    edx, edx
0x180049f90  js      short loc_180049FAE
0x180049f92  lea     rcx, [rbp+80h+var_58]
0x180049f96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049f9b  test    rax, rax
0x180049f9e  jz      short loc_180049FC6
0x180049fa0  lea     rcx, [rbx+8]; this
0x180049fa4  mov     rdx, rax; unsigned __int16 *
0x180049fa7  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180049fac  jmp     short loc_180049FC6
0x180049fae  mov     rax, [rbp+80h+var_C8]
0x180049fb2  cmp     dword ptr [rax+20h], 7
0x180049fb6  jz      loc_18004A1C1
0x180049fbc  cmp     dword ptr [rax+20h], 1
0x180049fc0  jz      loc_18004A1C1
0x180049fc6  mov     rax, [rbp+80h+var_C0]
0x180049fca  mov     [rbp+80h+var_F0], rax
0x180049fce  lea     rcx, [rbp+80h+var_F0]
0x180049fd2  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049fd7  mov     [rbp+80h+var_B8], rbx
0x180049fdb  lea     rcx, [rbp+80h+var_B8]
0x180049fdf  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049fe4  mov     [rbp+80h+var_B0], r12
0x180049fe8  lea     rcx, [rbp+80h+var_B0]
0x180049fec  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049ff1  mov     rax, [rbp+80h+var_E8]
0x180049ff5  mov     [rbp+80h+var_A8], rax
0x180049ff9  lea     rcx, [rbp+80h+var_A8]
0x180049ffd  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a002  mov     rax, [rbp+80h+var_E0]
0x18004a006  mov     [rbp+80h+var_A0], rax
0x18004a00a  lea     rcx, [rbp+80h+var_A0]
0x18004a00e  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a013  mov     rax, [rbp+80h+var_D8]
0x18004a017  mov     [rbp+80h+var_98], rax
0x18004a01b  lea     rcx, [rbp+80h+var_98]
0x18004a01f  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a024  mov     rax, [rbp+80h+var_D0]
0x18004a028  mov     [rbp+80h+var_90], rax
0x18004a02c  lea     rcx, [rbp+80h+var_90]
0x18004a030  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a035  mov     [rbp+80h+var_88], r13
0x18004a039  lea     rcx, [rbp+80h+var_88]
0x18004a03d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a042  mov     [rbp+80h+var_80], r15
0x18004a046  lea     rcx, [rbp+80h+var_80]
0x18004a04a  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a04f  mov     [rbp+80h+var_C8], r14
0x18004a053  lea     rcx, [rbp+80h+var_C8]
0x18004a057  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a05c  mov     [rsp+180h+var_108], rsi
0x18004a061  lea     rcx, [rsp+180h+var_108]
0x18004a066  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18004a06b  mov     rax, [rbp+80h+var_60]
0x18004a06f  mov     [rsp+180h+var_120], rax
0x18004a074  lea     rax, [rbp+80h+var_F0]
0x18004a078  mov     [rsp+180h+var_128], rax
0x18004a07d  mov     [rsp+180h+var_130], edi
0x18004a081  lea     rax, [rbp+80h+var_B8]
0x18004a085  mov     [rsp+180h+var_138], rax
0x18004a08a  lea     rax, [rbp+80h+var_B0]
0x18004a08e  mov     [rsp+180h+var_140], rax
0x18004a093  lea     rax, [rbp+80h+var_A8]
  ... truncated ...
```
