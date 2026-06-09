# CloudExperienceHostLauncherToastActivationHandler::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180011820`
- end: `0x180011eee`
- name: `?Activate@CloudExperienceHostLauncherToastActivationHandler@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `1742`
- prototype: `__int64 __fastcall(CloudExperienceHostLauncherToastActivationHandler *this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e10`
- `0x1800032b0`
- `0x18000532c`
- `0x180009f90`
- `0x18000e2bc`
- `0x18000ee5c`
- `0x1800111b4`
- `0x18001136c`
- `0x1800113cc`
- `0x180011820`
- `0x180012328`
- `0x180012370`
- `0x180013700`
- `0x180014604`
- `0x180014cc4`
- `0x1800154b4`
- `0x180015510`
- `0x18001565c`
- `0x1800156b8`
- `0x180015744`
- `0x1800157fc`
- `0x1800158f4`
- `0x1800164c8`
- `0x180016a1c`
- `0x180016da0`
- `0x180016eb8`
- `0x180016f3c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001186b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001186b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011923`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011923`

## string_xrefs

- `0x180011900`: `Windows.Data.Json.JsonObject`
- `0x180011db5`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011dca`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011de2`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011df7`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011e0c`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011e21`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011e36`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011e4b`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011e60`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011e75`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011ea8`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011edb`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180011e9c`: `Arguments must be of the form 'activateToast?params=<JSON object>'`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostLauncherToastActivationHandler::Activate(
        CloudExperienceHostLauncherToastActivationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4,
        unsigned int a5)
{
  __int64 v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  unsigned __int64 v10; // rdx
  __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  __int64 v13; // rax
  int ActivationFactory; // eax
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 *), _BYTE *); // rbx
  __int64 v18; // rax
  int v19; // eax
  __int64 (__fastcall **v20)(__int64, GUID *, __int64 *); // rax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, unsigned __int64, char *); // rbx
  int v24; // eax
  unsigned __int64 v25; // rdx
  const unsigned __int16 *v26; // rcx
  __int64 (__fastcall ***v27)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v28)(__int64, GUID *, __int64 *); // rbx
  int v29; // eax
  signed int v30; // esi
  const unsigned __int16 *v31; // rdx
  ScoobeToastTriggers *v32; // rcx
  int v33; // eax
  unsigned __int64 v34; // rdx
  __int64 v35; // rcx
  UserOOBETelemetry *v36; // rcx
  __int64 v37; // rcx
  UserOOBETelemetry *v38; // rcx
  __int64 (__fastcall ***v39)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v40)(__int64, GUID *, __int64 *); // rbx
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  const unsigned __int16 *v43; // rcx
  const unsigned __int16 *v44; // rcx
  ScoobeToastTriggers *v45; // rcx
  unsigned int v46; // r8d
  int v47; // eax
  unsigned __int64 v48; // rdx
  int v49; // ebx
  __int64 v50; // rcx
  UserOOBETelemetry *v51; // rcx
  __int64 v52; // rcx
  UserOOBETelemetry *v53; // rcx
  __int64 v54; // rcx
  UserOOBETelemetry *v55; // rcx
  __int64 (__fastcall ***v56)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v57)(__int64, GUID *, __int64 *); // rbx
  int v58; // eax
  const char *v59; // r9
  __int64 result; // rax
  unsigned int v61; // eax
  unsigned int v62; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-D8h]
  const char *v64; // [rsp+28h] [rbp-D0h]
  char v65; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v66[7]; // [rsp+31h] [rbp-C7h] BYREF
  HSTRING v67; // [rsp+38h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v68)(__int64, GUID *, __int64 *); // [rsp+40h] [rbp-B8h] BYREF
  __int64 v69; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+50h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A0h] BYREF
  unsigned __int64 v72; // [rsp+70h] [rbp-88h]
  _QWORD v73[3]; // [rsp+78h] [rbp-80h] BYREF
  unsigned __int64 v74; // [rsp+90h] [rbp-68h]
  _QWORD v75[3]; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 v76; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v7 = -1;
  v8 = CompareStringOrdinal(a2, -1, L"Windows.SystemToast.CloudExperienceHostLauncherCustom", -1, 1);
  try
  {
    if ( v8 != 2 )
    {
      v62 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x19F,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)v62,
        (int)"Cannot use this activation handler with the provided AUMID",
        v64);
    }
    std::wstring::wstring(v73, a3);
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73, v73[2]);
    v11 = v9;
    if ( v10 >= 0x15 )
    {
      v12 = v9 + 2 * v10;
      v13 = _std_search_2(v9, v12, L"activateToast?params=", 21);
      if ( v13 == v12 )
        goto LABEL_52;
      v7 = (v13 - v11) >> 1;
    }
    if ( !v7 )
    {
      std::wstring::substr(v73, v75);
      v70 = 0;
      v72 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      ActivationFactory = RoGetActivationFactory(v72, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v70);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)(unsigned int)ActivationFactory,
          bIgnoreCase);
      v68 = 0;
      v66[0] = 0;
      v16 = v70;
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 *), _BYTE *))(*(_QWORD *)v70 + 56LL);
      v68 = 0;
      *(double *)&v67 = COERCE_DOUBLE(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75, v15));
      v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v67);
      v19 = v17(v16, *(_QWORD *)(v18 + 24), &v68, v66);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x151,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)(unsigned int)v19,
          bIgnoreCase);
      if ( !v66[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x152,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)0x80070057LL,
          bIgnoreCase);
      v69 = 0;
      v20 = *v68;
      v69 = 0;
      v21 = (*v20)((__int64)v68, &GUID_c9d9a725_786b_5113_b4b7_9b61764c220b, &v69);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)(unsigned int)v21,
          bIgnoreCase);
      v65 = 0;
      v22 = v69;
      v23 = *(__int64 (__fastcall **)(__int64, unsigned __int64, char *))(*(_QWORD *)v69 + 64LL);
      v72 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"NumMinutesToPostpone", 0x15u, 0x14u);
      v24 = v23(v22, v72, &v65);
      LOBYTE(v26) = (_BYTE)retaddr;
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x158,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)(unsigned int)v24,
          bIgnoreCase);
      if ( v65 )
      {
        *(double *)&v67 = 0.0;
        v27 = v68;
        v28 = (*v68)[11];
        v72 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"NumMinutesToPostpone",
          0x15u,
          0x14u);
        v29 = v28((__int64)v27, (GUID *)v72, (__int64 *)&v67);
        v26 = (const unsigned __int16 *)retaddr;
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x15D,
            (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
            (const char *)(unsigned int)v29,
            bIgnoreCase);
        v30 = (int)*(double *)&v67;
      }
      else
      {
        if ( !a5 )
          goto LABEL_33;
        std::wstring::wstring(&hstringHeader, *((_QWORD *)a4 + 1));
        v30 = std::stol(&hstringHeader);
        v25 = v72;
        if ( v72 > 7 )
          std::_Deallocate<16>(hstringHeader.Reserved.Reserved1, 2 * v72 + 2);
      }
      if ( v30 )
      {
        if ( v30 >= 0 )
        {
          *(double *)&v67 = 0.0;
          v39 = v68;
          v40 = (*v68)[11];
          v72 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"PreviousNumberOfConsecutivePostpones",
            0x25u,
            0x24u);
          v41 = v40((__int64)v39, (GUID *)v72, (__int64 *)&v67);
          if ( v41 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x187,
              (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
              (const char *)(unsigned int)v41,
              bIgnoreCase);
          SetScoobeUserIntentState(L"IntroPostponed");
          SetScoobeIntentPropertyValue(v42, L"IsPostponed", 1u);
          SetScoobeIntentPropertyValue(v43, L"TimeToPostponeInMinutes", v30);
          SetScoobeIntentPropertyValue(v44, L"NumberOfConsecutivePostpones", (int)*(double *)&v67 + 1);
          v47 = ScoobeToastTriggers::RegisterTimeTriggeredTask(v45, (const unsigned __int16 *)(unsigned int)v30, v46);
          if ( v47 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x18D,
              (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
              (const char *)(unsigned int)v47,
              bIgnoreCase);
          v49 = (int)*(double *)&v67;
          if ( v65 )
          {
            if ( UserOOBETelemetry::IsEnabled((unsigned __int8)retaddr, v48) )
            {
              wil::details::static_lazy<UserOOBETelemetry>::get(
                v50,
                _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_);
              UserOOBETelemetry::ScoobePostponedFromActionCenterToastButton_(v51, v30, v49 + 1);
            }
          }
          else if ( UserOOBETelemetry::IsEnabled((unsigned __int8)retaddr, v48) )
          {
            wil::details::static_lazy<UserOOBETelemetry>::get(
              v52,
              _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_);
            UserOOBETelemetry::ScoobePostponedFromActionCenterToastDropdown_(v53, v30, v49 + 1);
          }
        }
        else
        {
          SetScoobeIntentPropertyValue(v26, L"NumberOfConsecutivePostpones", 0);
          SetScoobeUserIntentState(L"IntroSkipped");
          v33 = ScoobeToastTriggers::DeleteRegisteredTaskIfPresent(v32, v31);
          if ( v33 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x179,
              (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
              (const char *)(unsigned int)v33,
              bIgnoreCase);
          if ( v65 )
          {
            if ( UserOOBETelemetry::IsEnabled((unsigned __int8)retaddr, v34) )
            {
              wil::details::static_lazy<UserOOBETelemetry>::get(
                v35,
                _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_);
              UserOOBETelemetry::ScoobeActionCenterPostponeToastDismissedFromButton_(v36);
            }
          }
          else if ( UserOOBETelemetry::IsEnabled((unsigned __int8)retaddr, v34) )
          {
            wil::details::static_lazy<UserOOBETelemetry>::get(
              v37,
              _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_);
            UserOOBETelemetry::ScoobeActionCenterPostponeToastDismissedFromDropdown_(v38);
          }
        }
LABEL_37:
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v69);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v68);
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v70);
        if ( v76 > 7 )
          std::_Deallocate<16>(v75[0], 2 * v76 + 2);
        if ( v74 > 7 )
          std::_Deallocate<16>(v73[0], 2 * v74 + 2);
        return 0;
      }
LABEL_33:
      if ( UserOOBETelemetry::IsEnabled((unsigned __int8)v26, v25) )
      {
        wil::details::static_lazy<UserOOBETelemetry>::get(
          v54,
          _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_);
        UserOOBETelemetry::ScoobeActivatedFromActionCenterPostponeToast_(v55);
      }
      *(double *)&v67 = 0.0;
      v56 = v68;
      v57 = (*v68)[10];
      *(double *)&v67 = 0.0;
      v72 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"URI", 4u, 3u);
      v58 = v57((__int64)v56, (GUID *)v72, (__int64 *)&v67);
      if ( v58 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
          (const char *)(unsigned int)v58,
          bIgnoreCase);
      CloudExperienceHostLauncherToastActivationHandler::ProtocolLaunchUriAsync(retaddr, v67);
      Windows::Internal::String::~String((Windows::Internal::String *)&v67);
      goto LABEL_37;
    }
LABEL_52:
    v61 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x19A,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)v61,
      (int)"Arguments must be of the form 'activateToast?params=<JSON object>'",
      v64);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1A2,
                           (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
                           v59);
  }
  return result;
}

```

## disassembly

```asm
0x180011820  mov     rax, rsp
0x180011823  push    rbx
0x180011824  push    rsi
0x180011825  push    rdi
0x180011826  push    r14
0x180011828  push    r15
0x18001182a  sub     rsp, 0D0h
0x180011831  movaps  xmmword ptr [rax-38h], xmm6
0x180011835  mov     rax, cs:__security_cookie
0x18001183c  xor     rax, rsp
0x18001183f  mov     [rsp+0F8h+var_40], rax
0x180011847  mov     r14, r9
0x18001184a  mov     rbx, r8
0x18001184d  mov     rax, rdx
0x180011850  mov     [rsp+0F8h+bIgnoreCase], 1; int
0x180011858  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001185c  mov     r9d, edi; cchCount2
0x18001185f  lea     r8, aWindowsSystemt; "Windows.SystemToast.CloudExperienceHost"...
0x180011866  mov     edx, edi; cchCount1
0x180011868  mov     rcx, rax; lpString1
0x18001186b  call    cs:__imp_CompareStringOrdinal
0x180011871  cmp     eax, 2
0x180011874  jnz     loc_180011EBA
0x18001187a  mov     rdx, rbx
0x18001187d  lea     rcx, [rsp+0F8h+var_80]
0x180011882  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011887  nop
0x180011888  mov     rdx, [rsp+0F8h+var_70]
0x180011890  lea     rcx, [rsp+0F8h+var_80]
0x180011895  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001189a  mov     rsi, rax
0x18001189d  cmp     rdx, 15h
0x1800118a1  jb      short loc_1800118CF
0x1800118a3  lea     rbx, [rax+rdx*2]
0x1800118a7  lea     r9d, [rdi+16h]
0x1800118ab  lea     r8, aActivatetoastP; "activateToast?params="
0x1800118b2  mov     rdx, rbx
0x1800118b5  mov     rcx, rax
0x1800118b8  call    __std_search_2
0x1800118bd  mov     rdi, rax
0x1800118c0  cmp     rax, rbx
0x1800118c3  jz      loc_180011E87
0x1800118c9  sub     rdi, rsi
0x1800118cc  sar     rdi, 1
0x1800118cf  xor     r15d, r15d
0x1800118d2  test    rdi, rdi
0x1800118d5  jnz     loc_180011E87
0x1800118db  lea     rdx, [rsp+0F8h+var_60]
0x1800118e3  lea     rcx, [rsp+0F8h+var_80]
0x1800118e8  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800118ed  nop
0x1800118ee  mov     [rsp+0F8h+var_A8], r15
0x1800118f3  mov     [rsp+0F8h+var_88], r15
0x1800118f8  lea     r9d, [r15+1Ch]; unsigned int
0x1800118fc  lea     r8d, [r15+1Dh]; unsigned int
0x180011900  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180011907  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x18001190c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011911  nop
0x180011912  lea     r8, [rsp+0F8h+var_A8]
0x180011917  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001191e  mov     rcx, [rsp+0F8h+var_88]
0x180011923  call    cs:__imp_RoGetActivationFactory
0x180011929  mov     rcx, [rsp+0F8h]; this
0x180011931  test    eax, eax
0x180011933  js      loc_180011DB2
0x180011939  mov     [rsp+0F8h+var_B8], r15
0x18001193e  mov     [rsp+0F8h+var_C7], r15b
0x180011943  mov     rdi, [rsp+0F8h+var_A8]
0x180011948  mov     rax, [rdi]
0x18001194b  mov     rbx, [rax+38h]
0x18001194f  mov     [rsp+0F8h+var_B8], r15
0x180011954  lea     rcx, [rsp+0F8h+var_60]
0x18001195c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011961  mov     [rsp+0F8h+var_C0], rax
0x180011966  lea     rdx, [rsp+0F8h+var_C0]
0x18001196b  lea     rcx, [rsp+0F8h+hstringHeader]
0x180011970  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180011975  nop
0x180011976  lea     r9, [rsp+0F8h+var_C7]
0x18001197b  lea     r8, [rsp+0F8h+var_B8]
0x180011980  mov     rdx, [rax+18h]
0x180011984  mov     rcx, rdi
0x180011987  mov     rax, rbx
0x18001198a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001198f  mov     rcx, [rsp+0F8h]; this
0x180011997  test    eax, eax
0x180011999  js      loc_180011DC7
0x18001199f  cmp     [rsp+0F8h+var_C7], r15b
0x1800119a4  setz    al
0x1800119a7  mov     rcx, [rsp+0F8h]; this
0x1800119af  test    al, al
0x1800119b1  jnz     loc_180011DDC
0x1800119b7  mov     [rsp+0F8h+var_B0], r15
0x1800119bc  mov     rcx, [rsp+0F8h+var_B8]
0x1800119c1  mov     rax, [rcx]
0x1800119c4  mov     [rsp+0F8h+var_B0], r15
0x1800119c9  lea     r8, [rsp+0F8h+var_B0]
0x1800119ce  lea     rdx, _GUID_c9d9a725_786b_5113_b4b7_9b61764c220b
0x1800119d5  mov     rax, [rax]
0x1800119d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119dd  mov     rcx, [rsp+0F8h]; this
0x1800119e5  test    eax, eax
0x1800119e7  js      loc_180011DF4
0x1800119ed  mov     [rsp+0F8h+var_C8], r15b
0x1800119f2  mov     rdi, [rsp+0F8h+var_B0]
0x1800119f7  mov     rax, [rdi]
0x1800119fa  mov     rbx, [rax+40h]
0x1800119fe  mov     [rsp+0F8h+var_88], r15
0x180011a03  mov     esi, 14h
0x180011a08  mov     r9d, esi; unsigned int
0x180011a0b  lea     r8d, [rsi+1]; unsigned int
0x180011a0f  lea     rdx, sourceString; "NumMinutesToPostpone"
0x180011a16  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180011a1b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011a20  nop
0x180011a21  lea     r8, [rsp+0F8h+var_C8]
0x180011a26  mov     rdx, [rsp+0F8h+var_88]
0x180011a2b  mov     rcx, rdi
0x180011a2e  mov     rax, rbx
0x180011a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a36  mov     rcx, [rsp+0F8h]; this
0x180011a3e  test    eax, eax
0x180011a40  js      loc_180011E09
0x180011a46  cmp     [rsp+0F8h+var_C8], r15b
0x180011a4b  jz      short loc_180011AAF
0x180011a4d  xorps   xmm6, xmm6
0x180011a50  movsd   [rsp+0F8h+var_C0], xmm6
0x180011a56  mov     rdi, [rsp+0F8h+var_B8]
0x180011a5b  mov     rax, [rdi]
0x180011a5e  mov     rbx, [rax+58h]
0x180011a62  mov     [rsp+0F8h+var_88], r15
0x180011a67  mov     r9d, esi; unsigned int
0x180011a6a  mov     r8d, 15h; unsigned int
0x180011a70  lea     rdx, sourceString; "NumMinutesToPostpone"
0x180011a77  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180011a7c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011a81  nop
0x180011a82  lea     r8, [rsp+0F8h+var_C0]
0x180011a87  mov     rdx, [rsp+0F8h+var_88]
0x180011a8c  mov     rcx, rdi
0x180011a8f  mov     rax, rbx
0x180011a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a97  mov     rcx, [rsp+0F8h]; this
0x180011a9f  test    eax, eax
0x180011aa1  js      loc_180011E1E
0x180011aa7  cvttsd2si esi, [rsp+0F8h+var_C0]
0x180011aad  jmp     short loc_180011AF8
0x180011aaf  cmp     [rsp+0F8h+arg_20], r15d
0x180011ab7  jz      loc_180011C91
0x180011abd  mov     rdx, [r14+8]
0x180011ac1  lea     rcx, [rsp+0F8h+hstringHeader]
0x180011ac6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011acb  nop
0x180011acc  lea     rcx, [rsp+0F8h+hstringHeader]
0x180011ad1  call    ?stol@std@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stol(std::wstring const &,unsigned __int64 *,int)
0x180011ad6  mov     esi, eax
0x180011ad8  mov     rdx, [rsp+0F8h+var_88]
0x180011add  cmp     rdx, 7
0x180011ae1  jbe     short loc_180011AF5
0x180011ae3  lea     rdx, ds:2[rdx*2]
0x180011aeb  mov     rcx, qword ptr [rsp+0F8h+hstringHeader.Reserved]
0x180011af0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011af5  xorps   xmm6, xmm6
0x180011af8  test    esi, esi
0x180011afa  jz      loc_180011C91
0x180011b00  jns     short loc_180011B7F
0x180011b02  xor     r8d, r8d; unsigned int
0x180011b05  lea     rdx, aNumberofconsec; "NumberOfConsecutivePostpones"
0x180011b0c  call    ?SetScoobeIntentPropertyValue@@YAXPEBG0K@Z; SetScoobeIntentPropertyValue(ushort const *,ushort const *,ulong)
0x180011b11  lea     rcx, aIntroskipped; "IntroSkipped"
0x180011b18  call    ?SetScoobeUserIntentState@@YAXPEBG@Z; SetScoobeUserIntentState(ushort const *)
0x180011b1d  call    ?DeleteRegisteredTaskIfPresent@ScoobeToastTriggers@@YAJPEBG@Z; ScoobeToastTriggers::DeleteRegisteredTaskIfPresent(ushort const *)
0x180011b22  mov     rcx, [rsp+0F8h]; this
0x180011b2a  test    eax, eax
0x180011b2c  js      loc_180011E33
0x180011b32  cmp     [rsp+0F8h+var_C8], r15b
0x180011b37  jz      short loc_180011B5C
0x180011b39  call    ?IsEnabled@UserOOBETelemetry@@SA_NE_K@Z; UserOOBETelemetry::IsEnabled(uchar,unsigned __int64)
0x180011b3e  test    al, al
0x180011b40  jz      loc_180011D1D
0x180011b46  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_@@CA@XZ; _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_(void)
0x180011b4d  call    ?get@?$static_lazy@VUserOOBETelemetry@@@details@wil@@QEAAPEAVUserOOBETelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserOOBETelemetry>::get(void (*)(void))
0x180011b52  call    ?ScoobeActionCenterPostponeToastDismissedFromButton_@UserOOBETelemetry@@QEAAXXZ; UserOOBETelemetry::ScoobeActionCenterPostponeToastDismissedFromButton_(void)
0x180011b57  jmp     loc_180011D1D
0x180011b5c  call    ?IsEnabled@UserOOBETelemetry@@SA_NE_K@Z; UserOOBETelemetry::IsEnabled(uchar,unsigned __int64)
0x180011b61  test    al, al
0x180011b63  jz      loc_180011D1D
0x180011b69  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_@@CA@XZ; _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_(void)
0x180011b70  call    ?get@?$static_lazy@VUserOOBETelemetry@@@details@wil@@QEAAPEAVUserOOBETelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserOOBETelemetry>::get(void (*)(void))
0x180011b75  call    ?ScoobeActionCenterPostponeToastDismissedFromDropdown_@UserOOBETelemetry@@QEAAXXZ; UserOOBETelemetry::ScoobeActionCenterPostponeToastDismissedFromDropdown_(void)
0x180011b7a  jmp     loc_180011D1D
0x180011b7f  movsd   [rsp+0F8h+var_C0], xmm6
0x180011b85  mov     rdi, [rsp+0F8h+var_B8]
0x180011b8a  mov     rax, [rdi]
0x180011b8d  mov     rbx, [rax+58h]
0x180011b91  mov     [rsp+0F8h+var_88], r15
0x180011b96  mov     r9d, 24h ; '$'; unsigned int
0x180011b9c  lea     r8d, [r9+1]; unsigned int
0x180011ba0  lea     rdx, aPreviousnumber; "PreviousNumberOfConsecutivePostpones"
0x180011ba7  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180011bac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011bb1  nop
0x180011bb2  lea     r8, [rsp+0F8h+var_C0]
0x180011bb7  mov     rdx, [rsp+0F8h+var_88]
0x180011bbc  mov     rcx, rdi
0x180011bbf  mov     rax, rbx
0x180011bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bc7  mov     rcx, [rsp+0F8h]; this
0x180011bcf  test    eax, eax
0x180011bd1  js      loc_180011E48
0x180011bd7  lea     rcx, aIntropostponed; "IntroPostponed"
0x180011bde  call    ?SetScoobeUserIntentState@@YAXPEBG@Z; SetScoobeUserIntentState(ushort const *)
0x180011be3  mov     r8d, 1; unsigned int
0x180011be9  lea     rdx, aIspostponed; "IsPostponed"
0x180011bf0  call    ?SetScoobeIntentPropertyValue@@YAXPEBG0K@Z; SetScoobeIntentPropertyValue(ushort const *,ushort const *,ulong)
0x180011bf5  mov     r8d, esi; unsigned int
0x180011bf8  lea     rdx, aTimetopostpone; "TimeToPostponeInMinutes"
0x180011bff  call    ?SetScoobeIntentPropertyValue@@YAXPEBG0K@Z; SetScoobeIntentPropertyValue(ushort const *,ushort const *,ulong)
0x180011c04  cvttsd2si r8, [rsp+0F8h+var_C0]
0x180011c0b  inc     r8d; unsigned int
0x180011c0e  lea     rdx, aNumberofconsec; "NumberOfConsecutivePostpones"
0x180011c15  call    ?SetScoobeIntentPropertyValue@@YAXPEBG0K@Z; SetScoobeIntentPropertyValue(ushort const *,ushort const *,ulong)
0x180011c1a  mov     edx, esi; unsigned __int16 *
0x180011c1c  call    ?RegisterTimeTriggeredTask@ScoobeToastTriggers@@YAJPEBGK@Z; ScoobeToastTriggers::RegisterTimeTriggeredTask(ushort const *,ulong)
0x180011c21  mov     rcx, [rsp+0F8h]; this
0x180011c29  test    eax, eax
0x180011c2b  js      loc_180011E5D
0x180011c31  cvttsd2si rbx, [rsp+0F8h+var_C0]
0x180011c38  cmp     [rsp+0F8h+var_C8], r15b
0x180011c3d  jz      short loc_180011C68
0x180011c3f  call    ?IsEnabled@UserOOBETelemetry@@SA_NE_K@Z; UserOOBETelemetry::IsEnabled(uchar,unsigned __int64)
0x180011c44  test    al, al
0x180011c46  jz      loc_180011D1D
0x180011c4c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_@@CA@XZ; _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_(void)
0x180011c53  call    ?get@?$static_lazy@VUserOOBETelemetry@@@details@wil@@QEAAPEAVUserOOBETelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserOOBETelemetry>::get(void (*)(void))
0x180011c58  lea     r8d, [rbx+1]; unsigned int
0x180011c5c  mov     edx, esi; unsigned int
0x180011c5e  call    ?ScoobePostponedFromActionCenterToastButton_@UserOOBETelemetry@@QEAAXKK@Z; UserOOBETelemetry::ScoobePostponedFromActionCenterToastButton_(ulong,ulong)
0x180011c63  jmp     loc_180011D1D
0x180011c68  call    ?IsEnabled@UserOOBETelemetry@@SA_NE_K@Z; UserOOBETelemetry::IsEnabled(uchar,unsigned __int64)
0x180011c6d  test    al, al
0x180011c6f  jz      loc_180011D1D
0x180011c75  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_@@CA@XZ; _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_(void)
0x180011c7c  call    ?get@?$static_lazy@VUserOOBETelemetry@@@details@wil@@QEAAPEAVUserOOBETelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserOOBETelemetry>::get(void (*)(void))
0x180011c81  lea     r8d, [rbx+1]; unsigned int
0x180011c85  mov     edx, esi; unsigned int
0x180011c87  call    ?ScoobePostponedFromActionCenterToastDropdown_@UserOOBETelemetry@@QEAAXKK@Z; UserOOBETelemetry::ScoobePostponedFromActionCenterToastDropdown_(ulong,ulong)
0x180011c8c  jmp     loc_180011D1D
0x180011c91  call    ?IsEnabled@UserOOBETelemetry@@SA_NE_K@Z; UserOOBETelemetry::IsEnabled(uchar,unsigned __int64)
0x180011c96  test    al, al
0x180011c98  jz      short loc_180011CAB
0x180011c9a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_@@CA@XZ; _lambda_057586ddce1d50ab1ad7dfbd7c1ab6d7_::_lambda_invoker_cdecl_(void)
0x180011ca1  call    ?get@?$static_lazy@VUserOOBETelemetry@@@details@wil@@QEAAPEAVUserOOBETelemetry@@P6AXXZ@Z; wil::details::static_lazy<UserOOBETelemetry>::get(void (*)(void))
0x180011ca6  call    ?ScoobeActivatedFromActionCenterPostponeToast_@UserOOBETelemetry@@QEAAXXZ; UserOOBETelemetry::ScoobeActivatedFromActionCenterPostponeToast_(void)
0x180011cab  mov     [rsp+0F8h+var_C0], r15
0x180011cb0  mov     rdi, [rsp+0F8h+var_B8]
0x180011cb5  mov     rax, [rdi]
0x180011cb8  mov     rbx, [rax+50h]
0x180011cbc  mov     [rsp+0F8h+var_C0], r15
0x180011cc1  mov     [rsp+0F8h+var_88], r15
0x180011cc6  mov     r9d, 3; unsigned int
0x180011ccc  lea     r8d, [r9+1]; unsigned int
0x180011cd0  lea     rdx, aUri; "URI"
0x180011cd7  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180011cdc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011ce1  nop
0x180011ce2  lea     r8, [rsp+0F8h+var_C0]
0x180011ce7  mov     rdx, [rsp+0F8h+var_88]
0x180011cec  mov     rcx, rdi
0x180011cef  mov     rax, rbx
0x180011cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cf7  mov     rcx, [rsp+0F8h]; this
0x180011cff  test    eax, eax
0x180011d01  js      loc_180011E72
0x180011d07  mov     rdx, [rsp+0F8h+var_C0]; HSTRING
0x180011d0c  call    ?ProtocolLaunchUriAsync@CloudExperienceHostLauncherToastActivationHandler@@AEAAXPEAUHSTRING__@@@Z; CloudExperienceHostLauncherToastActivationHandler::ProtocolLaunchUriAsync(HSTRING__ *)
0x180011d11  nop
0x180011d12  lea     rcx, [rsp+0F8h+var_C0]; this
0x180011d17  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180011d1c  nop
0x180011d1d  lea     rcx, [rsp+0F8h+var_B0]
0x180011d22  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180011d27  nop
0x180011d28  lea     rcx, [rsp+0F8h+var_B8]
0x180011d2d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180011d32  nop
0x180011d33  lea     rcx, [rsp+0F8h+var_A8]
0x180011d38  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180011d3d  nop
0x180011d3e  mov     rdx, [rsp+0F8h+var_48]
0x180011d46  cmp     rdx, 7
0x180011d4a  jbe     short loc_180011D62
0x180011d4c  lea     rdx, ds:2[rdx*2]
0x180011d54  mov     rcx, [rsp+0F8h+var_60]
0x180011d5c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011d61  nop
0x180011d62  mov     rdx, [rsp+0F8h+var_68]
0x180011d6a  cmp     rdx, 7
0x180011d6e  jbe     short loc_180011D83
  ... truncated ...
```
