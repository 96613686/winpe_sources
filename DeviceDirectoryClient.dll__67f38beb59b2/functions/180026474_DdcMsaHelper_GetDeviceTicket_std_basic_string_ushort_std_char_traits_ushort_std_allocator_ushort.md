# DdcMsaHelper::GetDeviceTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180026474`
- end: `0x180026a00`
- name: `?GetDeviceTicket@DdcMsaHelper@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1420`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c034`
- `0x180011bf0`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180002f9c`
- `0x180004060`
- `0x180004e10`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x180025920`
- `0x180026474`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002664b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002664b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180026579`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180026579`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800268c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800268c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026928`
- `MdmCommon!MdmGetServiceTarget` at `0x180026503`
- `MdmCommon!MdmGetServiceTarget` at `0x180026503`

## string_xrefs

- `0x1800264e5`: `CPR(pwstrToken)`
- `0x180026904`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmsahelper.cpp`
- `0x18002651c`: `CHR(MdmGetServiceTarget(&pwszServiceTarget))`
- `0x1800265f8`: `CHR(ActivateInstance( HStringReference(RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager).Get(), pManager.GetAddressOf()))`
- `0x180026664`: `CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest).Get(), pRequestFactory.GetAddressOf()))`
- `0x1800266df`: `CHR(pRequestFactory->CreateOnlineIdServiceTicketRequest( HStringReference(pwszServiceTarget).Get(), HStringReference(LIVE_ID_SERVICE_POLICY).Get(), pRequest.GetAddressOf()))`
- `0x1800268f0`: `CHR(BlockOnCompletionAndGetResults(pOperation.Get(), pIdentity.GetAddressOf()))`
- `0x180026547`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x180026623`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
__int64 __fastcall DdcMsaHelper::GetDeviceTicket(__int64 a1, int a2)
{
  int ServiceTarget; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // edx
  int v7; // ecx
  int v8; // edx
  int v9; // ecx
  char v10; // r8
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, PVOID, PVOID, __int64 *); // rdi
  PVOID Reserved1; // rbx
  char v14; // r8
  HSTRING_HEADER *v15; // rax
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  HRESULT v20; // edx
  int v21; // ecx
  __int64 v22; // r8
  int (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rdi
  int v24; // edx
  int v25; // ecx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // edx
  int v29; // ecx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64 *); // rbx
  int v32; // edx
  int v33; // ecx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, HSTRING *); // rbx
  int v36; // edx
  int v37; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v39; // r8
  int v40; // ecx
  __int64 v41; // rcx
  int (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  PVOID v45; // rcx
  __int64 v47; // [rsp+0h] [rbp-E8h] BYREF
  PVOID v48; // [rsp+30h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+50h] [rbp-98h] BYREF
  int (__fastcall ***v53)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-90h] BYREF
  __int64 v54; // [rsp+60h] [rbp-88h] BYREF
  __int64 v55; // [rsp+68h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+70h] [rbp-78h] BYREF
  PVOID v57[4]; // [rsp+80h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-30h]

  v48 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  v52 = 0;
  v51 = 0;
  v50 = 0;
  string = 0;
  Block[0] = 0;
  if ( a1 )
  {
    ServiceTarget = MdmGetServiceTarget((unsigned __int16 **)Block);
    if ( ServiceTarget >= 0 )
    {
      v59 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
        0x42u,
        0x41u);
      v48 = 0;
      v57[0] = 0;
      ServiceTarget = RoActivateInstance(v59, v57);
      if ( ServiceTarget >= 0 )
      {
        if ( !memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
        {
          v48 = v57[0];
        }
        else
        {
          ServiceTarget = (**(__int64 (__fastcall ***)(PVOID, GUID *, PVOID *))v57[0])(
                            v57[0],
                            &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
                            &v48);
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v57[0] + 16LL))(v57[0]);
        }
      }
      if ( ServiceTarget >= 0 )
      {
        v59 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
          0x46u,
          0x45u);
        ServiceTarget = RoGetActivationFactory(v59, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v54);
        if ( ServiceTarget >= 0 )
        {
          v11 = v54;
          v12 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, __int64 *))(*(_QWORD *)v54 + 48LL);
          Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                        &hstringHeader,
                        (const WCHAR **)off_18002B7E0,
                        v10)[1].Reserved.Reserved1;
          v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  (HSTRING_HEADER *)v57,
                  (const WCHAR **)Block,
                  v14);
          ServiceTarget = v12(v11, v15[1].Reserved.Reserved1, Reserved1, &v55);
          if ( ServiceTarget >= 0 )
          {
            *(IID *)v57 = rclsid;
            ServiceTarget = (*(__int64 (__fastcall **)(PVOID, PVOID *))(*(_QWORD *)v48 + 72LL))(v48, v57);
            if ( ServiceTarget >= 0 )
            {
              ServiceTarget = (*(__int64 (__fastcall **)(PVOID, __int64, _QWORD))(*(_QWORD *)v48 + 56LL))(
                                v48,
                                v55,
                                &v53);
              if ( ServiceTarget >= 0 )
              {
                v23 = v53;
                ServiceTarget = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
                                  v53,
                                  v20,
                                  v22);
                if ( ServiceTarget < 0
                  || (ServiceTarget = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v23)[8])(
                                        v23,
                                        &v52),
                      ServiceTarget < 0) )
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    McTemplateU0dsqs_EventWriteTransfer(
                      v25,
                      v24,
                      ServiceTarget,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                      65,
                      "CHR(BlockOnCompletionAndGetResults(pOperation.Get(), pIdentity.GetAddressOf()))");
                }
                else
                {
                  v26 = v52;
                  v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 48LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
                  ServiceTarget = v27(v26, &v51);
                  if ( ServiceTarget >= 0 )
                  {
                    v30 = v51;
                    v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 48LL);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
                    ServiceTarget = v31(v30, 0, &v50);
                    if ( ServiceTarget >= 0 )
                    {
                      v34 = v50;
                      v35 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 48LL);
                      WindowsDeleteString(string);
                      string = 0;
                      ServiceTarget = v35(v34, &string);
                      if ( ServiceTarget >= 0 )
                      {
                        if ( __eh34_try(-1, 0) )
                        {
                          __eh34_scope_strut(0);
                          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                          std::wstring::assign(a1, (__int64)StringRawBuffer, v39);
                        }
                        if ( __eh34_catch(0) )
                        {
                          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
                          {
                            LODWORD(v57[0]) = -2147024882;
                            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                              McTemplateU0dsqs_EventWriteTransfer(
                                v40,
                                (unsigned int)&v47,
                                -2147024882,
                                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                                77,
                                "CHR(((HRESULT)0x8007000EL))");
                            ServiceTarget = (int)v57[0];
                            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800268DB);
                          }
                        }
                      }
                      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                      {
                        McTemplateU0dsqs_EventWriteTransfer(
                          v37,
                          v36,
                          ServiceTarget,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                          69,
                          "CHR(pTicket->get_Value(hstrTicket.GetAddressOf()))");
                      }
                    }
                    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                    {
                      McTemplateU0dsqs_EventWriteTransfer(
                        v33,
                        v32,
                        ServiceTarget,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                        68,
                        "CHR(pTickets->GetAt(0, &pTicket))");
                    }
                  }
                  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
                  {
                    McTemplateU0dsqs_EventWriteTransfer(
                      v29,
                      v28,
                      ServiceTarget,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                      67,
                      "CHR(pIdentity->get_Tickets(&pTickets))");
                  }
                }
              }
              else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              {
                McTemplateU0dsqs_EventWriteTransfer(
                  v21,
                  v20,
                  ServiceTarget,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                  64,
                  "CHR(pManager->AuthenticateUserHostAsync(pRequest.Get(), pOperation.GetAddressOf()))");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                v19,
                v18,
                ServiceTarget,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
                63,
                "CHR(pManager->put_ApplicationId(g_ApplicationId))");
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v17,
              v16,
              ServiceTarget,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
              61,
              "CHR(pRequestFactory->CreateOnlineIdServiceTicketRequest( HStringReference(pwszServiceTarget).Get(), HStrin"
              "gReference(LIVE_ID_SERVICE_POLICY).Get(), pRequest.GetAddressOf()))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v9,
            v8,
            ServiceTarget,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
            56,
            "CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdSer"
            "viceTicketRequest).Get(), pRequestFactory.GetAddressOf()))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          ServiceTarget,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
          52,
          "CHR(ActivateInstance( HStringReference(RuntimeClass_Windows_Internal_Security_WebAuthentication_Authentication"
          "Manager).Get(), pManager.GetAddressOf()))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        ServiceTarget,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
        48,
        "CHR(MdmGetServiceTarget(&pwszServiceTarget))");
    }
  }
  else
  {
    ServiceTarget = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_41;
    McTemplateU0dsqs_EventWriteTransfer(
      0,
      a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
      46,
      "CPR(pwstrToken)");
  }
  if ( Block[0] )
    operator delete(Block[0]);
LABEL_41:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  v41 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v53;
  if ( v53 )
  {
    v53 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v42)[2])(v42);
  }
  v43 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v45 + 16LL))(v45);
  }
  return (unsigned int)ServiceTarget;
}

```

## disassembly

```asm
0x180026474  mov     r11, rsp
0x180026477  mov     [r11+10h], rbx
0x18002647b  mov     [r11+18h], rsi
0x18002647f  push    rdi
0x180026480  push    r14
0x180026482  push    r15
0x180026484  sub     rsp, 0D0h
0x18002648b  mov     rax, cs:__security_cookie
0x180026492  xor     rax, rsp
0x180026495  mov     [rsp+0E8h+var_28], rax
0x18002649d  mov     r15, rcx
0x1800264a0  xor     r14d, r14d
0x1800264a3  mov     [rsp+0E8h+var_B8], r14
0x1800264a8  mov     [r11-80h], r14
0x1800264ac  mov     [rsp+0E8h+var_88], r14
0x1800264b1  mov     [rsp+0E8h+var_90], r14
0x1800264b6  mov     [rsp+0E8h+var_98], r14
0x1800264bb  mov     [rsp+0E8h+var_A0], r14
0x1800264c0  mov     [rsp+0E8h+var_A8], r14
0x1800264c5  mov     [rsp+0E8h+string], r14
0x1800264ca  mov     [r11-78h], r14
0x1800264ce  test    rcx, rcx
0x1800264d1  jnz     short loc_1800264FE
0x1800264d3  mov     ebx, 80070057h
0x1800264d8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800264df  jz      loc_180026923
0x1800264e5  lea     rax, aCprPwstrtoken; "CPR(pwstrToken)"
0x1800264ec  mov     [rsp+0E8h+var_C0], rax
0x1800264f1  mov     [rsp+0E8h+var_C8], 2Eh ; '.'
0x1800264f9  jmp     loc_180026904
0x1800264fe  lea     rcx, [rsp+0E8h+Block]
0x180026503  call    cs:__imp_?MdmGetServiceTarget@@YAJPEAPEAG@Z; MdmGetServiceTarget(ushort * *)
0x180026509  mov     ebx, eax
0x18002650b  test    eax, eax
0x18002650d  jns     short loc_180026535
0x18002650f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026516  jz      loc_180026913
0x18002651c  lea     rax, aChrMdmgetservi; "CHR(MdmGetServiceTarget(&pwszServiceTar"...
0x180026523  mov     [rsp+0E8h+var_C0], rax
0x180026528  mov     [rsp+0E8h+var_C8], 30h ; '0'
0x180026530  jmp     loc_180026904
0x180026535  mov     [rsp+0E8h+var_30], r14
0x18002653d  mov     r9d, 41h ; 'A'; unsigned int
0x180026543  lea     r8d, [r9+1]; unsigned int
0x180026547  lea     rdx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x18002654e  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x180026556  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002655b  nop
0x18002655c  mov     [rsp+0E8h+var_B8], r14
0x180026561  mov     [rsp+0E8h+var_68], r14
0x180026569  lea     rdx, [rsp+0E8h+var_68]
0x180026571  mov     rcx, [rsp+0E8h+var_30]
0x180026579  call    cs:__imp_RoActivateInstance
0x18002657f  mov     ebx, eax
0x180026581  test    eax, eax
0x180026583  js      short loc_1800265E7
0x180026585  mov     r8d, 10h; Size
0x18002658b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180026592  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x180026599  call    memcmp_0
0x18002659e  test    eax, eax
0x1800265a0  jnz     short loc_1800265B1
0x1800265a2  mov     rax, [rsp+0E8h+var_68]
0x1800265aa  mov     [rsp+0E8h+var_B8], rax
0x1800265af  jmp     short loc_1800265E7
0x1800265b1  mov     rcx, [rsp+0E8h+var_68]
0x1800265b9  mov     rax, [rcx]
0x1800265bc  lea     r8, [rsp+0E8h+var_B8]
0x1800265c1  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x1800265c8  mov     rax, [rax]
0x1800265cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265d0  mov     ebx, eax
0x1800265d2  mov     rcx, [rsp+0E8h+var_68]
0x1800265da  mov     rax, [rcx]
0x1800265dd  mov     rax, [rax+10h]
0x1800265e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265e6  nop
0x1800265e7  test    ebx, ebx
0x1800265e9  jns     short loc_180026611
0x1800265eb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800265f2  jz      loc_180026913
0x1800265f8  lea     rax, aChrActivateins_8; "CHR(ActivateInstance( HStringReference("...
0x1800265ff  mov     [rsp+0E8h+var_C0], rax
0x180026604  mov     [rsp+0E8h+var_C8], 34h ; '4'
0x18002660c  jmp     loc_180026904
0x180026611  mov     [rsp+0E8h+var_30], r14
0x180026619  mov     r9d, 45h ; 'E'; unsigned int
0x18002661f  lea     r8d, [r9+1]; unsigned int
0x180026623  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18002662a  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x180026632  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026637  lea     r8, [rsp+0E8h+var_88]
0x18002663c  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180026643  mov     rcx, [rsp+0E8h+var_30]
0x18002664b  call    cs:__imp_RoGetActivationFactory
0x180026651  mov     ebx, eax
0x180026653  test    eax, eax
0x180026655  jns     short loc_18002667D
0x180026657  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002665e  jz      loc_180026913
0x180026664  lea     rax, aChrGetactivati_2; "CHR(GetActivationFactory( HStringRefere"...
0x18002666b  mov     [rsp+0E8h+var_C0], rax
0x180026670  mov     [rsp+0E8h+var_C8], 38h ; '8'
0x180026678  jmp     loc_180026904
0x18002667d  mov     rsi, [rsp+0E8h+var_88]
0x180026682  mov     rax, [rsi]
0x180026685  mov     rdi, [rax+30h]
0x180026689  lea     rdx, off_18002B7E0; "MBI_SSL"
0x180026690  lea     rcx, [rsp+0E8h+hstringHeader]
0x180026698  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002669d  nop
0x18002669e  mov     rbx, [rax+18h]
0x1800266a2  lea     rdx, [rsp+0E8h+Block]
0x1800266a7  lea     rcx, [rsp+0E8h+var_68]
0x1800266af  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800266b4  nop
0x1800266b5  lea     r9, [rsp+0E8h+var_80]
0x1800266ba  mov     r8, rbx
0x1800266bd  mov     rdx, [rax+18h]
0x1800266c1  mov     rcx, rsi
0x1800266c4  mov     rax, rdi
0x1800266c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266cc  mov     ebx, eax
0x1800266ce  test    eax, eax
0x1800266d0  jns     short loc_1800266F8
0x1800266d2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800266d9  jz      loc_180026913
0x1800266df  lea     rax, aChrPrequestfac; "CHR(pRequestFactory->CreateOnlineIdServ"...
0x1800266e6  mov     [rsp+0E8h+var_C0], rax
0x1800266eb  mov     [rsp+0E8h+var_C8], 3Dh ; '='
0x1800266f3  jmp     loc_180026904
0x1800266f8  mov     rcx, [rsp+0E8h+var_B8]
0x1800266fd  movups  xmm0, xmmword ptr cs:rclsid.Data1
0x180026704  movdqu  xmmword ptr [rsp+0E8h+var_68], xmm0
0x18002670d  mov     rax, [rcx]
0x180026710  lea     rdx, [rsp+0E8h+var_68]
0x180026718  mov     rax, [rax+48h]
0x18002671c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026721  mov     ebx, eax
0x180026723  test    eax, eax
0x180026725  jns     short loc_18002674D
0x180026727  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002672e  jz      loc_180026913
0x180026734  lea     rax, aChrPmanagerPut; "CHR(pManager->put_ApplicationId(g_Appli"...
0x18002673b  mov     [rsp+0E8h+var_C0], rax
0x180026740  mov     [rsp+0E8h+var_C8], 3Fh ; '?'
0x180026748  jmp     loc_180026904
0x18002674d  mov     rcx, [rsp+0E8h+var_B8]
0x180026752  mov     rax, [rcx]
0x180026755  lea     r8, [rsp+0E8h+var_90]
0x18002675a  mov     rdx, [rsp+0E8h+var_80]
0x18002675f  mov     rax, [rax+38h]
0x180026763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026768  mov     ebx, eax
0x18002676a  test    eax, eax
0x18002676c  jns     short loc_180026794
0x18002676e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026775  jz      loc_180026913
0x18002677b  lea     rax, aChrPmanagerAut; "CHR(pManager->AuthenticateUserHostAsync"...
0x180026782  mov     [rsp+0E8h+var_C0], rax
0x180026787  mov     [rsp+0E8h+var_C8], 40h ; '@'
0x18002678f  jmp     loc_180026904
0x180026794  mov     rdi, [rsp+0E8h+var_90]
0x180026799  mov     rcx, rdi
0x18002679c  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)
0x1800267a1  mov     ebx, eax
0x1800267a3  test    eax, eax
0x1800267a5  js      loc_1800268E7
0x1800267ab  mov     rax, [rdi]
0x1800267ae  lea     rdx, [rsp+0E8h+var_98]
0x1800267b3  mov     rcx, rdi
0x1800267b6  mov     rax, [rax+40h]
0x1800267ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267bf  mov     ebx, eax
0x1800267c1  test    eax, eax
0x1800267c3  js      loc_1800268E7
0x1800267c9  mov     rdi, [rsp+0E8h+var_98]
0x1800267ce  mov     rax, [rdi]
0x1800267d1  mov     rbx, [rax+30h]
0x1800267d5  lea     rcx, [rsp+0E8h+var_A0]
0x1800267da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800267df  lea     rdx, [rsp+0E8h+var_A0]
0x1800267e4  mov     rcx, rdi
0x1800267e7  mov     rax, rbx
0x1800267ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267ef  mov     ebx, eax
0x1800267f1  test    eax, eax
0x1800267f3  jns     short loc_18002681B
0x1800267f5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800267fc  jz      loc_180026913
0x180026802  lea     rax, aChrPidentityGe; "CHR(pIdentity->get_Tickets(&pTickets))"
0x180026809  mov     [rsp+0E8h+var_C0], rax
0x18002680e  mov     [rsp+0E8h+var_C8], 43h ; 'C'
0x180026816  jmp     loc_180026904
0x18002681b  mov     rdi, [rsp+0E8h+var_A0]
0x180026820  mov     rax, [rdi]
0x180026823  mov     rbx, [rax+30h]
0x180026827  lea     rcx, [rsp+0E8h+var_A8]
0x18002682c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026831  lea     r8, [rsp+0E8h+var_A8]
0x180026836  xor     edx, edx
0x180026838  mov     rcx, rdi
0x18002683b  mov     rax, rbx
0x18002683e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026843  mov     ebx, eax
0x180026845  test    eax, eax
0x180026847  jns     short loc_18002686F
0x180026849  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180026850  jz      loc_180026913
0x180026856  lea     rax, aChrPticketsGet; "CHR(pTickets->GetAt(0, &pTicket))"
0x18002685d  mov     [rsp+0E8h+var_C0], rax
0x180026862  mov     [rsp+0E8h+var_C8], 44h ; 'D'
0x18002686a  jmp     loc_180026904
0x18002686f  mov     rdi, [rsp+0E8h+var_A8]
0x180026874  mov     rax, [rdi]
0x180026877  mov     rbx, [rax+30h]
0x18002687b  mov     rcx, [rsp+0E8h+string]; string
0x180026880  call    cs:__imp_WindowsDeleteString
0x180026886  mov     [rsp+0E8h+string], r14
0x18002688b  lea     rdx, [rsp+0E8h+string]
0x180026890  mov     rcx, rdi
0x180026893  mov     rax, rbx
0x180026896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002689b  mov     ebx, eax
0x18002689d  test    eax, eax
0x18002689f  jns     short loc_1800268C0
0x1800268a1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800268a8  jz      short loc_180026913
0x1800268aa  lea     rax, aChrPticketGetV; "CHR(pTicket->get_Value(hstrTicket.GetAd"...
0x1800268b1  mov     [rsp+0E8h+var_C0], rax
0x1800268b6  mov     [rsp+0E8h+var_C8], 45h ; 'E'
0x1800268be  jmp     short loc_180026904
0x1800268c0  xor     edx, edx; length
0x1800268c2  mov     rcx, [rsp+0E8h+string]; string
0x1800268c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800268cd  mov     rdx, rax
0x1800268d0  mov     rcx, r15
0x1800268d3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800268d8  nop
0x1800268d9  jmp     short loc_180026913
0x1800268db  xor     r14d, r14d
0x1800268de  mov     ebx, dword ptr [rsp+0E8h+var_68]
0x1800268e5  jmp     short loc_180026913
0x1800268e7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800268ee  jz      short loc_180026913
0x1800268f0  lea     rax, aChrBlockoncomp; "CHR(BlockOnCompletionAndGetResults(pOpe"...
0x1800268f7  mov     [rsp+0E8h+var_C0], rax
0x1800268fc  mov     [rsp+0E8h+var_C8], 41h ; 'A'
0x180026904  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18002690b  mov     r8d, ebx
0x18002690e  call    McTemplateU0dsqs_EventWriteTransfer
0x180026913  mov     rcx, [rsp+0E8h+Block]; Block
0x180026918  test    rcx, rcx
0x18002691b  jz      short loc_180026923
0x18002691d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026922  nop
0x180026923  mov     rcx, [rsp+0E8h+string]; string
0x180026928  call    cs:__imp_WindowsDeleteString
0x18002692e  mov     [rsp+0E8h+string], r14
0x180026933  lea     rcx, [rsp+0E8h+var_A8]
0x180026938  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002693d  nop
0x18002693e  lea     rcx, [rsp+0E8h+var_A0]
0x180026943  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026948  nop
0x180026949  mov     rcx, [rsp+0E8h+var_98]
0x18002694e  test    rcx, rcx
0x180026951  jz      short loc_180026965
0x180026953  mov     [rsp+0E8h+var_98], r14
0x180026958  mov     rax, [rcx]
0x18002695b  mov     rax, [rax+10h]
0x18002695f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026964  nop
0x180026965  mov     rcx, [rsp+0E8h+var_90]
0x18002696a  test    rcx, rcx
0x18002696d  jz      short loc_180026981
0x18002696f  mov     [rsp+0E8h+var_90], r14
0x180026974  mov     rax, [rcx]
0x180026977  mov     rax, [rax+10h]
0x18002697b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026980  nop
0x180026981  mov     rcx, [rsp+0E8h+var_88]
0x180026986  test    rcx, rcx
0x180026989  jz      short loc_18002699D
0x18002698b  mov     [rsp+0E8h+var_88], r14
0x180026990  mov     rax, [rcx]
0x180026993  mov     rax, [rax+10h]
0x180026997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002699c  nop
0x18002699d  mov     rcx, [rsp+0E8h+var_80]
0x1800269a2  test    rcx, rcx
0x1800269a5  jz      short loc_1800269B9
0x1800269a7  mov     [rsp+0E8h+var_80], r14
0x1800269ac  mov     rax, [rcx]
0x1800269af  mov     rax, [rax+10h]
0x1800269b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269b8  nop
0x1800269b9  mov     rcx, [rsp+0E8h+var_B8]
0x1800269be  test    rcx, rcx
0x1800269c1  jz      short loc_1800269D5
  ... truncated ...
```
