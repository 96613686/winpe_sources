# DdcRegistrationController::RegisterUserDevice(IDdcStoppable *,int,MdmRegistrationTrigger,void *)

- ea: `0x18000ca4c`
- end: `0x18000cd9e`
- name: `?RegisterUserDevice@DdcRegistrationController@@SAJPEAVIDdcStoppable@@HW4MdmRegistrationTrigger@@PEAX@Z`
- size: `850`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800042c0`

## callees

- `0x1800024c0`
- `0x180003c2c`
- `0x180004060`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x180005190`
- `0x1800058c4`
- `0x180009164`
- `0x18000921c`
- `0x18000a7b8`
- `0x18000ca4c`
- `0x18000df90`
- `0x18000ed24`
- `0x18000f534`
- `0x18001505c`
- `0x18001691c`
- `0x180026a08`
- `0x180027dc8`
- `0x18002a010`

## import_xrefs

- `MdmCommon!MdmRegisterUserDevice` at `0x18000cccd`
- `MdmCommon!MdmRegisterUserDevice` at `0x18000cccd`

## string_xrefs

- `0x18000cb03`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcRegistrationController::RegisterUserDevice(
        unsigned int (__fastcall ***a1)(_QWORD),
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  int v6; // r12d
  unsigned int v7; // esi
  int v8; // edx
  int v9; // ecx
  int UserInfo; // ebx
  int v11; // r15d
  int v12; // edx
  int v13; // edx
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  int v19; // edx
  int v20; // ecx
  int v21; // edx
  int v22; // ecx
  __int64 v23; // rax
  int v24; // edx
  int v25; // ecx
  __int64 v26; // rcx
  int v28; // [rsp+50h] [rbp-39h] BYREF
  int v29; // [rsp+54h] [rbp-35h] BYREF
  int v30; // [rsp+58h] [rbp-31h] BYREF
  int v31; // [rsp+5Ch] [rbp-2Dh] BYREF
  int v32; // [rsp+60h] [rbp-29h] BYREF
  struct Windows::Data::Json::IJsonValue *v33; // [rsp+68h] [rbp-21h] BYREF
  struct Windows::Data::Json::IJsonValue *v34; // [rsp+70h] [rbp-19h] BYREF
  __int64 v35; // [rsp+78h] [rbp-11h] BYREF
  __int64 v36; // [rsp+80h] [rbp-9h]
  _OWORD v37[2]; // [rsp+88h] [rbp-1h] BYREF

  v31 = 0;
  v37[0] = 0;
  v37[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v37[0]) = 0;
  v34 = 0;
  v33 = 0;
  v29 = 0;
  v6 = 0;
  v32 = 0;
  v28 = 0;
  v7 = 0;
  v30 = 0;
  v35 = a4;
  v36 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0qq_EventWriteTransfer(a1, a2, (unsigned int)a2, a3);
  UserInfo = DdcDeviceInfoHelper::FmdDisabledByPolicy(&v30, a2);
  v11 = v30;
  if ( UserInfo < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        UserInfo,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        68,
        "CHR(DdcDeviceInfoHelper::FmdDisabledByPolicy(&fIsFmdDisabledByPolicy))");
    goto LABEL_37;
  }
  if ( v30 )
  {
    DdcStateController::ProcessStateChange();
    goto LABEL_37;
  }
  CheckIfConnectedAccountsChanged();
  if ( a3 == 2 )
  {
    UserInfo = IsTooSoonForUserRegistration((unsigned int *)&v29, v12);
    if ( UserInfo < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v14,
          v13,
          UserInfo,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          85,
          "CHR(IsTooSoonForUserRegistration(&fTooSoonForRegistration))");
      goto LABEL_37;
    }
    if ( v29 )
      goto LABEL_37;
  }
  UserInfo = DdcUserInfoHelper::GetUserInfo(&v34);
  if ( UserInfo < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v16,
        v15,
        UserInfo,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        93,
        "CHR(DdcUserInfoHelper::GetUserInfo(pUserInfo.GetAddressOf()))");
    goto LABEL_37;
  }
  if ( (**a1)(a1) )
  {
LABEL_18:
    v7 = 1;
    goto LABEL_37;
  }
  UserInfo = DdcDeviceInfoHelper::GetDeviceInfo(&v33, 1);
  if ( UserInfo >= 0 )
  {
    if ( (**a1)(a1) )
      goto LABEL_18;
    UserInfo = DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v35, L"RegisterUserDevice");
    if ( UserInfo >= 0 )
    {
      UserInfo = DdcMsaHelper::GetUserTicket((__int64)v37, &v32, &v28);
      if ( v28 )
      {
        UserInfo = 0;
      }
      else if ( UserInfo >= 0 )
      {
        v6 = 1;
        if ( (**a1)(a1) )
        {
          v7 = 1;
        }
        else
        {
          v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          UserInfo = MdmRegisterUserDevice(&v31, v23, a3, v33, v34);
          if ( UserInfo >= 0 )
          {
            UpdateUserRegistrationTimestamp();
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v25,
              v24,
              UserInfo,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
              127,
              "CHR(MdmRegisterUserDevice( &dwHttpStatus, wstrTicket.c_str(), eTrigger, deviceInfo.Get(), pUserInfo.Get() ))");
          }
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v22,
          v21,
          UserInfo,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          114,
          "CHR(hr)");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v20,
        v19,
        UserInfo,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        102,
        "CHR(pdcActivationWrapper.ActivateClient(L\"RegisterUserDevice\"))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v18,
      v17,
      UserInfo,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
      98,
      "CHR(DdcDeviceInfoHelper::GetDeviceInfo(deviceInfo.GetAddressOf(), true))");
  }
LABEL_37:
  DdcTraceHelper::TraceRegisterUserDeviceResult(v7, v36 != 0, a3, (unsigned int)v29, v32, v6, v28, v11, UserInfo, v31);
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v26, DEVICE_DIRECTORY_CLIENT_REGISTER_USER_DEVICE_RESULT, (unsigned int)UserInfo);
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v34);
  std::wstring::_Tidy_deallocate((__int64)v37);
  return (unsigned int)UserInfo;
}

```

## disassembly

```asm
0x18000ca4c  push    rbp
0x18000ca4e  push    rbx
0x18000ca4f  push    rsi
0x18000ca50  push    rdi
0x18000ca51  push    r12
0x18000ca53  push    r14
0x18000ca55  push    r15
0x18000ca57  lea     rbp, [rsp-27h]
0x18000ca5c  sub     rsp, 0B0h
0x18000ca63  mov     rax, cs:__security_cookie
0x18000ca6a  xor     rax, rsp
0x18000ca6d  mov     [rbp+57h+var_38], rax
0x18000ca71  mov     r14d, r8d
0x18000ca74  mov     rdi, rcx
0x18000ca77  mov     [rbp+57h+var_84], 0
0x18000ca7e  xorps   xmm0, xmm0
0x18000ca81  movups  [rbp+57h+var_58], xmm0
0x18000ca85  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000ca8d  movdqu  [rbp+57h+var_48], xmm1
0x18000ca92  xor     eax, eax
0x18000ca94  mov     word ptr [rbp+57h+var_58], ax
0x18000ca98  mov     [rbp+57h+var_70], rax
0x18000ca9c  mov     [rbp+57h+var_78], rax
0x18000caa0  mov     [rbp+57h+var_8C], eax
0x18000caa3  xor     r12d, r12d
0x18000caa6  mov     [rbp+57h+var_80], r12d
0x18000caaa  mov     [rbp+57h+var_90], r12d
0x18000caae  xor     esi, esi
0x18000cab0  mov     [rbp+57h+var_88], esi
0x18000cab3  mov     [rbp+57h+var_68], r9
0x18000cab7  mov     [rbp+57h+var_60], rsi
0x18000cabb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000cac2  jz      short loc_18000CACF
0x18000cac4  mov     r9d, r8d
0x18000cac7  mov     r8d, edx
0x18000caca  call    McTemplateU0qq_EventWriteTransfer
0x18000cacf  lea     rcx, [rbp+57h+var_88]; int *
0x18000cad3  call    ?FmdDisabledByPolicy@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::FmdDisabledByPolicy(int *)
0x18000cad8  mov     ebx, eax
0x18000cada  mov     r15d, [rbp+57h+var_88]
0x18000cade  test    eax, eax
0x18000cae0  jns     short loc_18000CB17
0x18000cae2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000cae9  jz      loc_18000CD00
0x18000caef  lea     rax, aChrDdcdevicein; "CHR(DdcDeviceInfoHelper::FmdDisabledByP"...
0x18000caf6  mov     [rsp+0E0h+var_B8], rax
0x18000cafb  mov     dword ptr [rsp+0E0h+var_C0], 244h
0x18000cb03  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000cb0a  mov     r8d, ebx
0x18000cb0d  call    McTemplateU0dsqs_EventWriteTransfer
0x18000cb12  jmp     loc_18000CD00
0x18000cb17  test    r15d, r15d
0x18000cb1a  jz      short loc_18000CB26
0x18000cb1c  call    ?ProcessStateChange@DdcStateController@@SAJXZ; DdcStateController::ProcessStateChange(void)
0x18000cb21  jmp     loc_18000CD00
0x18000cb26  call    ?CheckIfConnectedAccountsChanged@@YAJXZ; CheckIfConnectedAccountsChanged(void)
0x18000cb2b  cmp     r14d, 2
0x18000cb2f  jnz     short loc_18000CB6D
0x18000cb31  lea     rcx, [rbp+57h+var_8C]; int *
0x18000cb35  call    ?IsTooSoonForUserRegistration@@YAJPEAH@Z; IsTooSoonForUserRegistration(int *)
0x18000cb3a  mov     ebx, eax
0x18000cb3c  test    eax, eax
0x18000cb3e  jns     short loc_18000CB63
0x18000cb40  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000cb47  jz      loc_18000CD00
0x18000cb4d  lea     rax, aChrIstoosoonfo; "CHR(IsTooSoonForUserRegistration(&fTooS"...
0x18000cb54  mov     [rsp+0E0h+var_B8], rax
0x18000cb59  mov     dword ptr [rsp+0E0h+var_C0], 255h
0x18000cb61  jmp     short loc_18000CB03
0x18000cb63  cmp     [rbp+57h+var_8C], 0
0x18000cb67  jnz     loc_18000CD00
0x18000cb6d  lea     rcx, [rbp+57h+var_70]; struct Windows::Data::Json::IJsonValue **
0x18000cb71  call    ?GetUserInfo@DdcUserInfoHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcUserInfoHelper::GetUserInfo(Windows::Data::Json::IJsonValue * *)
0x18000cb76  mov     ebx, eax
0x18000cb78  test    eax, eax
0x18000cb7a  jns     short loc_18000CBA2
0x18000cb7c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000cb83  jz      loc_18000CD00
0x18000cb89  lea     rax, aChrDdcuserinfo; "CHR(DdcUserInfoHelper::GetUserInfo(pUse"...
0x18000cb90  mov     [rsp+0E0h+var_B8], rax
0x18000cb95  mov     dword ptr [rsp+0E0h+var_C0], 25Dh
0x18000cb9d  jmp     loc_18000CB03
0x18000cba2  mov     rax, [rdi]
0x18000cba5  mov     rcx, rdi
0x18000cba8  mov     rax, [rax]
0x18000cbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb0  test    eax, eax
0x18000cbb2  jz      short loc_18000CBBE
0x18000cbb4  mov     esi, 1
0x18000cbb9  jmp     loc_18000CD00
0x18000cbbe  mov     edx, 1; int
0x18000cbc3  lea     rcx, [rbp+57h+var_78]; struct Windows::Data::Json::IJsonValue **
0x18000cbc7  call    ?GetDeviceInfo@DdcDeviceInfoHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@H@Z; DdcDeviceInfoHelper::GetDeviceInfo(Windows::Data::Json::IJsonValue * *,int)
0x18000cbcc  mov     ebx, eax
0x18000cbce  test    eax, eax
0x18000cbd0  jns     short loc_18000CBF8
0x18000cbd2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000cbd9  jz      loc_18000CD00
0x18000cbdf  lea     rax, aChrDdcdevicein_3; "CHR(DdcDeviceInfoHelper::GetDeviceInfo("...
0x18000cbe6  mov     [rsp+0E0h+var_B8], rax
0x18000cbeb  mov     dword ptr [rsp+0E0h+var_C0], 262h
0x18000cbf3  jmp     loc_18000CB03
0x18000cbf8  mov     rax, [rdi]
0x18000cbfb  mov     rcx, rdi
0x18000cbfe  mov     rax, [rax]
0x18000cc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc06  test    eax, eax
0x18000cc08  jnz     short loc_18000CBB4
0x18000cc0a  lea     rdx, aRegisteruserde; "RegisterUserDevice"
0x18000cc11  lea     rcx, [rbp+57h+var_68]; this
0x18000cc15  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x18000cc1a  mov     ebx, eax
0x18000cc1c  test    eax, eax
0x18000cc1e  jns     short loc_18000CC46
0x18000cc20  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000cc27  jz      loc_18000CD00
0x18000cc2d  lea     rax, aChrPdcactivati; "CHR(pdcActivationWrapper.ActivateClient"...
0x18000cc34  mov     [rsp+0E0h+var_B8], rax
0x18000cc39  mov     dword ptr [rsp+0E0h+var_C0], 266h
0x18000cc41  jmp     loc_18000CB03
0x18000cc46  lea     r8, [rbp+57h+var_90]
0x18000cc4a  lea     rdx, [rbp+57h+var_80]
0x18000cc4e  lea     rcx, [rbp+57h+var_58]
0x18000cc52  call    ?GetUserTicket@DdcMsaHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAKAEAH@Z; DdcMsaHelper::GetUserTicket(std::wstring &,ulong &,int &)
0x18000cc57  mov     ebx, eax
0x18000cc59  cmp     [rbp+57h+var_90], 0
0x18000cc5d  jz      short loc_18000CC66
0x18000cc5f  xor     ebx, ebx
0x18000cc61  jmp     loc_18000CD00
0x18000cc66  test    ebx, ebx
0x18000cc68  jns     short loc_18000CC90
0x18000cc6a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000cc71  jz      loc_18000CD00
0x18000cc77  lea     rax, aChrHr; "CHR(hr)"
0x18000cc7e  mov     [rsp+0E0h+var_B8], rax
0x18000cc83  mov     dword ptr [rsp+0E0h+var_C0], 272h
0x18000cc8b  jmp     loc_18000CB03
0x18000cc90  mov     r12d, 1
0x18000cc96  mov     rax, [rdi]
0x18000cc99  mov     rcx, rdi
0x18000cc9c  mov     rax, [rax]
0x18000cc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca4  test    eax, eax
0x18000cca6  jz      short loc_18000CCAD
0x18000cca8  mov     esi, r12d
0x18000ccab  jmp     short loc_18000CD00
0x18000ccad  lea     rcx, [rbp+57h+var_58]
0x18000ccb1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ccb6  mov     rdx, rax
0x18000ccb9  mov     rax, [rbp+57h+var_70]
0x18000ccbd  mov     [rsp+0E0h+var_C0], rax
0x18000ccc2  mov     r9, [rbp+57h+var_78]
0x18000ccc6  mov     r8d, r14d
0x18000ccc9  lea     rcx, [rbp+57h+var_84]
0x18000cccd  call    cs:__imp_?MdmRegisterUserDevice@@YAJPEAKPEBGW4MdmRegistrationTrigger@@PEAUIJsonValue@Json@Data@Windows@@3@Z; MdmRegisterUserDevice(ulong *,ushort const *,MdmRegistrationTrigger,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *)
0x18000ccd3  mov     ebx, eax
0x18000ccd5  test    eax, eax
0x18000ccd7  jns     short loc_18000CCFB
0x18000ccd9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x18000cce0  jz      short loc_18000CD00
0x18000cce2  lea     rax, aChrMdmregister_0; "CHR(MdmRegisterUserDevice( &dwHttpStatu"...
0x18000cce9  mov     [rsp+0E0h+var_B8], rax
0x18000ccee  mov     dword ptr [rsp+0E0h+var_C0], 27Fh
0x18000ccf6  jmp     loc_18000CB03
0x18000ccfb  call    ?UpdateUserRegistrationTimestamp@@YAJXZ; UpdateUserRegistrationTimestamp(void)
0x18000cd00  mov     eax, [rbp+57h+var_84]
0x18000cd03  mov     r10d, [rbp+57h+var_90]
0x18000cd07  mov     r11d, [rbp+57h+var_80]
0x18000cd0b  xor     edx, edx
0x18000cd0d  cmp     [rbp+57h+var_60], rdx
0x18000cd11  setnz   dl
0x18000cd14  mov     [rsp+0E0h+var_98], eax
0x18000cd18  mov     [rsp+0E0h+var_A0], ebx
0x18000cd1c  mov     [rsp+0E0h+var_A8], r15d
0x18000cd21  mov     [rsp+0E0h+var_B0], r10d
0x18000cd26  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x18000cd2b  mov     dword ptr [rsp+0E0h+var_C0], r11d
0x18000cd30  mov     r9d, [rbp+57h+var_8C]
0x18000cd34  mov     r8d, r14d
0x18000cd37  mov     ecx, esi
0x18000cd39  call    ?TraceRegisterUserDeviceResult@DdcTraceHelper@@SAXHHW4MdmRegistrationTrigger@@HKHHHJK@Z; DdcTraceHelper::TraceRegisterUserDeviceResult(int,int,MdmRegistrationTrigger,int,ulong,int,int,int,long,ulong)
0x18000cd3e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000cd45  jz      short loc_18000CD57
0x18000cd47  mov     r8d, ebx
0x18000cd4a  lea     rdx, DEVICE_DIRECTORY_CLIENT_REGISTER_USER_DEVICE_RESULT
0x18000cd51  call    McTemplateU0q_EventWriteTransfer
0x18000cd56  nop
0x18000cd57  lea     rcx, [rbp+57h+var_68]; this
0x18000cd5b  call    ?DeactivateClient@DdcPdcActivationWrapper@@QEAAXXZ; DdcPdcActivationWrapper::DeactivateClient(void)
0x18000cd60  nop
0x18000cd61  lea     rcx, [rbp+57h+var_78]
0x18000cd65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cd6a  nop
0x18000cd6b  lea     rcx, [rbp+57h+var_70]
0x18000cd6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cd74  nop
0x18000cd75  lea     rcx, [rbp+57h+var_58]
0x18000cd79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cd7e  mov     eax, ebx
0x18000cd80  mov     rcx, [rbp+57h+var_38]
0x18000cd84  xor     rcx, rsp; StackCookie
0x18000cd87  call    __security_check_cookie
0x18000cd8c  add     rsp, 0B0h
0x18000cd93  pop     r15
0x18000cd95  pop     r14
0x18000cd97  pop     r12
0x18000cd99  pop     rdi
0x18000cd9a  pop     rsi
0x18000cd9b  pop     rbx
0x18000cd9c  pop     rbp
0x18000cd9d  retn
```
