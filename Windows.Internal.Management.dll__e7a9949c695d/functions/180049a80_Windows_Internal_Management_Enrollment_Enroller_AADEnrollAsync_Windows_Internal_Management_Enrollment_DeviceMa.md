# Windows::Internal::Management::Enrollment::Enroller::AADEnrollAsync(Windows::Internal::Management::Enrollment::DeviceManagementDeviceEnrollmentInformation,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> * *)

- ea: `0x180049a80`
- end: `0x18004a165`
- name: `?AADEnrollAsync@Enroller@Enrollment@Management@Internal@Windows@@UEAAJUDeviceManagementDeviceEnrollmentInformation@2345@PEAPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@5@@Z`
- size: `1765`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004d50`
- `0x18000992c`
- `0x18000a2a4`
- `0x18000d724`
- `0x180015e4c`
- `0x1800168d0`
- `0x180018ff0`
- `0x18003b544`
- `0x18003b838`
- `0x18003bb2c`
- `0x18003bbd4`
- `0x18003d6dc`
- `0x18003ea60`
- `0x180040b68`
- `0x180041e1c`
- `0x180046318`
- `0x180049a80`
- `0x18004aa4c`
- `0x18005a894`
- `0x18005b67c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180049c92`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180049c92`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x180049b15`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x180049b15`

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
  __int64 v27[2]; // [rsp+78h] [rbp-88h] BYREF
  int v28; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING *v37; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v38; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v39; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v41; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v42; // [rsp+F0h] [rbp-10h] BYREF
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
  v4 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Enrollment::EnrollmentResult,Windows::Internal::Management::Enrollment::EnrollmentResult,>((__int64)&v36);
  IsLockedToMmpc = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B6,
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
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v27[0] + 8), (HSTRING *)a2);
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v12 = v27[0];
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v27[0] + 8), (HSTRING *)(a2 + 8));
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v13 = v27[0];
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v27[0] + 8), (HSTRING *)(a2 + 16));
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v14 = v27[0];
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v27[0] + 8), (HSTRING *)(a2 + 24));
  CreateRefCountedObj<Windows::Internal::String,>(&v34);
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v34 + 8), (HSTRING *)(a2 + 40));
  CreateRefCountedObj<Windows::Internal::String,>(&v33);
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v33 + 8), (HSTRING *)(a2 + 48));
  CreateRefCountedObj<Windows::Internal::String,>(&v32);
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v32 + 8), (HSTRING *)(a2 + 56));
  CreateRefCountedObj<Windows::Internal::String,>(&v31);
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v31 + 8), (HSTRING *)(a2 + 64));
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  v15 = (HSTRING *)(a2 + 72);
  v16 = v27[0];
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v27[0] + 8), v15);
  CreateRefCountedObj<Windows::Internal::String,>(v27);
  std::wstring::wstring(v47);
  TargetedSID = GetTargetedSID((__int64)v47);
  LODWORD(v30) = TargetedSID;
  v26 = TargetedSID;
  if ( (byte_1800FB141 & 1) != 0 )
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
            v27,
            &v35,
            &v44,
            &v43,
            &v42,
            &v41,
            &v40,
            &v39,
            &v38,
            (__int64 *)&v37,
            v10,
            (__int64)&v30,
            v46);
    std::wstring::~wstring(v47);
    if ( v20 )
      (*((void (__fastcall **)(HSTRING *))*v20 + 2))(v20);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
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
0x180049a80  mov     [rsp-8+arg_0], rbx
0x180049a85  push    rbp
0x180049a86  push    rsi
0x180049a87  push    rdi
0x180049a88  push    r12
0x180049a8a  push    r13
0x180049a8c  push    r14
0x180049a8e  push    r15
0x180049a90  lea     rbp, [rsp-50h]
0x180049a95  sub     rsp, 150h
0x180049a9c  mov     rax, cs:__security_cookie
0x180049aa3  xor     rax, rsp
0x180049aa6  mov     [rbp+80h+var_38], rax
0x180049aaa  mov     [rbp+80h+var_60], r8
0x180049aae  mov     r12, rdx
0x180049ab1  mov     [rbp+80h+var_C8], rdx
0x180049ab5  xor     esi, esi
0x180049ab7  mov     [rsp+180h+var_10C], esi
0x180049abb  mov     [rbp+80h+var_C0], rsi
0x180049abf  lea     rcx, [rbp+80h+var_C0]
0x180049ac3  call    ??$MakeAndInitialize@VEnrollmentResult@Enrollment@Management@Internal@Windows@@V12345@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VEnrollmentResult@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Enrollment::EnrollmentResult,Windows::Internal::Management::Enrollment::EnrollmentResult,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::EnrollmentResult>>)
0x180049ac8  mov     ebx, eax
0x180049aca  test    eax, eax
0x180049acc  jns     short loc_180049AEE
0x180049ace  mov     rcx, [rbp+88h]; this
0x180049ad5  mov     r9d, eax; char *
0x180049ad8  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180049adf  mov     edx, 9B6h; void *
0x180049ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049ae9  jmp     loc_18004A133
0x180049aee  mov     [rsp+180h+var_110], esi
0x180049af2  mov     r8, r12
0x180049af5  lea     rdx, [rsp+180h+var_10C]
0x180049afa  lea     rcx, [rsp+180h+var_108]
0x180049aff  call    ??0_lambda_06f40ebce54247e3f11ddce21d34cd52_@@QEAA@PEAV?$SimpleVectorView@PEAUIPackage@Provisioning@Management@Windows@@V?$Vector@PEAUIPackage@Provisioning@Management@Windows@@U?$DefaultEqualityPredicate@PEAUIPackage@Provisioning@Management@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@U?$VectorOptions@PEAUIPackage@Provisioning@Management@Windows@@$00$00$0A@@6784@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAPEAI@Z; _lambda_06f40ebce54247e3f11ddce21d34cd52_::_lambda_06f40ebce54247e3f11ddce21d34cd52_(Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::Vector<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Management::Provisioning::IPackage *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,XWinRT::IntVersionTag,1> *,uint * &)
0x180049b04  mov     rdx, rax
0x180049b07  lea     rcx, [rbp+80h+var_78]
0x180049b0b  call    wil__ScopeExit__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049b10  lea     rcx, [rsp+180h+var_110]
0x180049b15  call    cs:__imp_Mmpc_Lockdown_IsLockedToMmpc
0x180049b1b  mov     ebx, eax
0x180049b1d  mov     [rsp+180h+var_10C], eax
0x180049b21  test    eax, eax
0x180049b23  jns     short loc_180049B33
0x180049b25  lea     rcx, [rbp+80h+var_78]
0x180049b29  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049b2e  jmp     loc_18004A133
0x180049b33  mov     [rbp+80h+var_F8], esi
0x180049b36  lea     rcx, [rbp+80h+var_F8]; int *
0x180049b3a  call    ?Mmpc_IsOnPremiseSupportingDevice@@YAJPEAH@Z; Mmpc_IsOnPremiseSupportingDevice(int *)
0x180049b3f  mov     [rsp+180h+var_10C], eax
0x180049b43  test    eax, eax
0x180049b45  js      short loc_180049B5F
0x180049b47  cmp     [rbp+80h+var_F8], esi
0x180049b4a  jz      short loc_180049B5F
0x180049b4c  lea     rcx, [rbp+80h+var_78]
0x180049b50  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049b55  mov     ebx, 80180026h
0x180049b5a  jmp     loc_18004A133
0x180049b5f  mov     ecx, esi
0x180049b61  mov     r8d, [r12+20h]
0x180049b66  cmp     r8d, 7
0x180049b6a  jg      short loc_180049BDE
0x180049b6c  jz      short loc_180049BC2
0x180049b6e  mov     edx, r8d
0x180049b71  test    r8d, r8d
0x180049b74  jz      loc_180049C06
0x180049b7a  sub     edx, 1
0x180049b7d  jz      short loc_180049BFA
0x180049b7f  sub     edx, 1
0x180049b82  jz      short loc_180049BA1
0x180049b84  sub     edx, 1
0x180049b87  jz      short loc_180049B9C
0x180049b89  sub     edx, 1
0x180049b8c  jz      short loc_180049B95
0x180049b8e  cmp     edx, 2
0x180049b91  jz      short loc_180049C06
0x180049b93  jmp     short loc_180049BFA
0x180049b95  mov     ecx, 200h
0x180049b9a  jmp     short loc_180049C06
0x180049b9c  mov     ecx, 80h
0x180049ba1  or      ecx, 1
0x180049ba4  cmp     [rsp+180h+var_110], esi
0x180049ba8  jz      short loc_180049BB8
0x180049baa  mov     ebx, 18h
0x180049baf  bts     ecx, 12h
0x180049bb3  jmp     loc_180049C7D
0x180049bb8  mov     ebx, 5
0x180049bbd  jmp     loc_180049C7D
0x180049bc2  cmp     [rsp+180h+var_110], esi
0x180049bc6  jz      short loc_180049BD7
0x180049bc8  mov     ebx, 18h
0x180049bcd  mov     ecx, 41000h
0x180049bd2  jmp     loc_180049C7D
0x180049bd7  mov     ecx, 1000h
0x180049bdc  jmp     short loc_180049BFA
0x180049bde  mov     edx, r8d
0x180049be1  sub     edx, 8
0x180049be4  jz      short loc_180049C5A
0x180049be6  sub     edx, 1
0x180049be9  jz      short loc_180049C47
0x180049beb  sub     edx, 1
0x180049bee  jz      short loc_180049C3A
0x180049bf0  sub     edx, 1
0x180049bf3  jz      short loc_180049C2D
0x180049bf5  cmp     edx, 1
0x180049bf8  jz      short loc_180049C01
0x180049bfa  mov     ebx, 0Dh
0x180049bff  jmp     short loc_180049C7D
0x180049c01  mov     ecx, 100000h
0x180049c06  mov     eax, ecx
0x180049c08  bts     eax, 0Ch
0x180049c0c  mov     ebx, 6
0x180049c11  cmp     r8d, ebx
0x180049c14  cmovnz  eax, ecx
0x180049c17  mov     ecx, eax
0x180049c19  cmp     [rsp+180h+var_110], esi
0x180049c1d  jz      short loc_180049C28
0x180049c1f  mov     ebx, 1Ah
0x180049c24  bts     ecx, 12h
0x180049c28  or      ecx, 4
0x180049c2b  jmp     short loc_180049C7D
0x180049c2d  cmp     [rsp+180h+var_110], esi
0x180049c31  jnz     short loc_180049C60
0x180049c33  mov     ecx, 10004h
0x180049c38  jmp     short loc_180049C78
0x180049c3a  cmp     [rsp+180h+var_110], esi
0x180049c3e  jnz     short loc_180049C60
0x180049c40  mov     ecx, 8004h
0x180049c45  jmp     short loc_180049C78
0x180049c47  lea     rcx, [rbp+80h+var_78]
0x180049c4b  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049c50  mov     ebx, 80004001h
0x180049c55  jmp     loc_18004A133
0x180049c5a  cmp     [rsp+180h+var_110], esi
0x180049c5e  jz      short loc_180049C73
0x180049c60  lea     rcx, [rbp+80h+var_78]
0x180049c64  call    wil__details__ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f______ScopeExitFn__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x180049c69  mov     ebx, 80180014h
0x180049c6e  jmp     loc_18004A133
0x180049c73  mov     ecx, 2004h
0x180049c78  mov     ebx, 6
0x180049c7d  mov     edi, ecx
0x180049c7f  bts     edi, 11h
0x180049c83  cmp     [r12+50h], esi
0x180049c88  cmovz   edi, ecx
0x180049c8b  mov     [rbp+80h+var_F4], esi
0x180049c8e  lea     rcx, [rbp+80h+var_F4]
0x180049c92  call    cs:__imp_OOBEComplete
0x180049c98  test    eax, eax
0x180049c9a  jz      short loc_180049CA5
0x180049c9c  cmp     [rbp+80h+var_F4], esi
0x180049c9f  jz      short loc_180049CA5
0x180049ca1  bts     edi, 16h
0x180049ca5  mov     ecx, ebx
0x180049ca7  call    ?AccessCheck@Enroller@Enrollment@Management@Internal@Windows@@SAJW4EnrollmentEnrollType@@@Z; Windows::Internal::Management::Enrollment::Enroller::AccessCheck(EnrollmentEnrollType)
0x180049cac  mov     ebx, eax
0x180049cae  mov     [rsp+180h+var_10C], eax
0x180049cb2  test    eax, eax
0x180049cb4  js      loc_180049B25
0x180049cba  lea     rcx, [rsp+180h+var_108]
0x180049cbf  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049cc4  mov     rsi, [rsp+180h+var_108]
0x180049cc9  lea     rcx, [rsi+8]; this
0x180049ccd  mov     rdx, r12; HSTRING *
0x180049cd0  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049cd5  lea     rcx, [rsp+180h+var_108]
0x180049cda  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049cdf  lea     rdx, [r12+8]; HSTRING *
0x180049ce4  mov     r14, [rsp+180h+var_108]
0x180049ce9  lea     rcx, [r14+8]; this
0x180049ced  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049cf2  lea     rcx, [rsp+180h+var_108]
0x180049cf7  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049cfc  lea     rdx, [r12+10h]; HSTRING *
0x180049d01  mov     r15, [rsp+180h+var_108]
0x180049d06  lea     rcx, [r15+8]; this
0x180049d0a  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049d0f  lea     rcx, [rsp+180h+var_108]
0x180049d14  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049d19  lea     rdx, [r12+18h]; HSTRING *
0x180049d1e  mov     r13, [rsp+180h+var_108]
0x180049d23  lea     rcx, [r13+8]; this
0x180049d27  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049d2c  lea     rcx, [rbp+80h+var_D0]
0x180049d30  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049d35  lea     rdx, [r12+28h]; HSTRING *
0x180049d3a  mov     rcx, [rbp+80h+var_D0]
0x180049d3e  add     rcx, 8; this
0x180049d42  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049d47  lea     rcx, [rbp+80h+var_D8]
0x180049d4b  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049d50  lea     rdx, [r12+30h]; HSTRING *
0x180049d55  mov     rcx, [rbp+80h+var_D8]
0x180049d59  add     rcx, 8; this
0x180049d5d  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049d62  lea     rcx, [rbp+80h+var_E0]
0x180049d66  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049d6b  lea     rdx, [r12+38h]; HSTRING *
0x180049d70  mov     rcx, [rbp+80h+var_E0]
0x180049d74  add     rcx, 8; this
0x180049d78  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049d7d  lea     rcx, [rbp+80h+var_E8]
0x180049d81  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049d86  lea     rdx, [r12+40h]; HSTRING *
0x180049d8b  mov     rcx, [rbp+80h+var_E8]
0x180049d8f  add     rcx, 8; this
0x180049d93  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049d98  lea     rcx, [rsp+180h+var_108]
0x180049d9d  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049da2  lea     rdx, [r12+48h]; HSTRING *
0x180049da7  mov     r12, [rsp+180h+var_108]
0x180049dac  lea     rcx, [r12+8]; this
0x180049db1  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180049db6  lea     rcx, [rsp+180h+var_108]
0x180049dbb  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180049dc0  lea     rcx, [rbp+80h+var_58]
0x180049dc4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180049dc9  lea     rcx, [rbp+80h+var_58]
0x180049dcd  call    GetTargetedSID
0x180049dd2  mov     edx, eax
0x180049dd4  mov     dword ptr [rbp+80h+var_F0], eax
0x180049dd7  mov     [rsp+180h+var_10C], eax
0x180049ddb  test    cs:byte_1800FB141, 1
0x180049de2  jz      short loc_180049E0D
0x180049de4  lea     rcx, [rbp+80h+var_58]
0x180049de8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049ded  mov     r8, rax
0x180049df0  mov     r9d, edx
0x180049df3  lea     rdx, EnterpriseDiagnosticsEnrollAPISID
0x180049dfa  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180049e01  call    McTemplateU0zd_EventWriteTransfer
0x180049e06  mov     edx, [rsp+180h+var_10C]
0x180049e0a  mov     dword ptr [rbp+80h+var_F0], edx
0x180049e0d  mov     rbx, [rsp+180h+var_108]
0x180049e12  test    edx, edx
0x180049e14  js      short loc_180049E32
0x180049e16  lea     rcx, [rbp+80h+var_58]
0x180049e1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049e1f  test    rax, rax
0x180049e22  jz      short loc_180049E4A
0x180049e24  lea     rcx, [rbx+8]; this
0x180049e28  mov     rdx, rax; unsigned __int16 *
0x180049e2b  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180049e30  jmp     short loc_180049E4A
0x180049e32  mov     rax, [rbp+80h+var_C8]
0x180049e36  cmp     dword ptr [rax+20h], 7
0x180049e3a  jz      loc_18004A045
0x180049e40  cmp     dword ptr [rax+20h], 1
0x180049e44  jz      loc_18004A045
0x180049e4a  mov     rax, [rbp+80h+var_C0]
0x180049e4e  mov     [rbp+80h+var_F0], rax
0x180049e52  lea     rcx, [rbp+80h+var_F0]
0x180049e56  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049e5b  mov     [rbp+80h+var_B8], rbx
0x180049e5f  lea     rcx, [rbp+80h+var_B8]
0x180049e63  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049e68  mov     [rbp+80h+var_B0], r12
0x180049e6c  lea     rcx, [rbp+80h+var_B0]
0x180049e70  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049e75  mov     rax, [rbp+80h+var_E8]
0x180049e79  mov     [rbp+80h+var_A8], rax
0x180049e7d  lea     rcx, [rbp+80h+var_A8]
0x180049e81  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049e86  mov     rax, [rbp+80h+var_E0]
0x180049e8a  mov     [rbp+80h+var_A0], rax
0x180049e8e  lea     rcx, [rbp+80h+var_A0]
0x180049e92  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049e97  mov     rax, [rbp+80h+var_D8]
0x180049e9b  mov     [rbp+80h+var_98], rax
0x180049e9f  lea     rcx, [rbp+80h+var_98]
0x180049ea3  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049ea8  mov     rax, [rbp+80h+var_D0]
0x180049eac  mov     [rbp+80h+var_90], rax
0x180049eb0  lea     rcx, [rbp+80h+var_90]
0x180049eb4  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049eb9  mov     [rbp+80h+var_88], r13
0x180049ebd  lea     rcx, [rbp+80h+var_88]
0x180049ec1  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049ec6  mov     [rbp+80h+var_80], r15
0x180049eca  lea     rcx, [rbp+80h+var_80]
0x180049ece  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049ed3  mov     [rbp+80h+var_C8], r14
0x180049ed7  lea     rcx, [rbp+80h+var_C8]
0x180049edb  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049ee0  mov     [rsp+180h+var_108], rsi
0x180049ee5  lea     rcx, [rsp+180h+var_108]
0x180049eea  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x180049eef  mov     rax, [rbp+80h+var_60]
0x180049ef3  mov     [rsp+180h+var_120], rax
0x180049ef8  lea     rax, [rbp+80h+var_F0]
0x180049efc  mov     [rsp+180h+var_128], rax
0x180049f01  mov     [rsp+180h+var_130], edi
0x180049f05  lea     rax, [rbp+80h+var_B8]
0x180049f09  mov     [rsp+180h+var_138], rax
0x180049f0e  lea     rax, [rbp+80h+var_B0]
0x180049f12  mov     [rsp+180h+var_140], rax
0x180049f17  lea     rax, [rbp+80h+var_A8]
0x180049f1b  mov     [rsp+180h+var_148], rax
0x180049f20  lea     rax, [rbp+80h+var_A0]
  ... truncated ...
```
