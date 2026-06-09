# DdcWnsListener::RegisterWnsChannel(FILETIMEEX *,ushort *,ulong *)

- ea: `0x180024fb8`
- end: `0x180025366`
- name: `?RegisterWnsChannel@DdcWnsListener@@CAJPEATFILETIMEEX@@PEAGPEAK@Z`
- size: `942`
- prototype: `__int64 __fastcall(union FILETIMEEX *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024d0c`

## callees

- `0x1800024c0`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x18002450c`
- `0x180024fb8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002526e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002526e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025103`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180025103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002525d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002525d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800251d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800252ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800251d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800252ee`

## string_xrefs

- `0x1800252dd`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcwnslistener.cpp`
- `0x18002504a`: `CPR(pwszChannelUri)`
- `0x18002507e`: `CPR(pcchChannelUri)`
- `0x1800250b6`: `CBR(*pcchChannelUri == 2048)`
- `0x180025177`: `CHR(spChannelManagerStatics->CreatePushNotificationChannelForApplicationAsyncWithId( HStringReference(wszAppId).Get(), spChannelOperation.GetAddressOf()))`
- `0x1800252c6`: `CHR(BlockOnCompletionAndGetResults<IAsyncOperationCompletedHandler<PushNotificationChannel*>>( spChannelOperation.Get(), spChannel.GetAddressOf()))`
- `0x1800251fe`: `CHR(spChannel->get_Uri(hstrUri.GetAddressOf()))`
- `0x180025286`: `CBR(wcscpy_s(pwszChannelUri, 2048, WindowsGetStringRawBuffer(hstrUri.Get(), nullptr)) == 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DdcWnsListener::RegisterWnsChannel(union FILETIMEEX *a1, unsigned __int16 *a2, unsigned int *a3)
{
  int ActivationFactory; // ebx
  HRESULT v7; // edx
  int v8; // ecx
  char v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v12; // rax
  __int64 v13; // r8
  int (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  int (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v21; // rcx
  char v23; // [rsp+20h] [rbp-60h]
  const char *v24; // [rsp+28h] [rbp-58h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h] BYREF
  int (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  __int64 v28; // [rsp+48h] [rbp-38h] BYREF
  __int64 v29; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v31; // [rsp+70h] [rbp-10h]

  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  string = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( *a3 == 2048 )
        {
          *a2 = 0;
          *a3 = 0;
          v31 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.Networking.PushNotifications.PushNotificationChannelManager",
            0x44u,
            0x43u);
          ActivationFactory = RoGetActivationFactory(v31, &GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0, &v28);
          if ( ActivationFactory >= 0 )
          {
            v10 = v28;
            v11 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v28 + 56LL);
            v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                    &hstringHeader,
                    (const WCHAR **)off_18002B7C8,
                    v9);
            ActivationFactory = v11(v10, v12[1].Reserved.Reserved1, &v27);
            if ( ActivationFactory >= 0 )
            {
              v14 = v27;
              ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(
                                    v27,
                                    v7,
                                    v13);
              if ( ActivationFactory < 0
                || (ActivationFactory = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v14)[8])(
                                          v14,
                                          &v26),
                    ActivationFactory < 0) )
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_36;
                v24 = "CHR(BlockOnCompletionAndGetResults<IAsyncOperationCompletedHandler<PushNotificationChannel*>>( spC"
                      "hannelOperation.Get(), spChannel.GetAddressOf()))";
                v23 = -52;
              }
              else
              {
                v15 = v26;
                v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 48LL);
                WindowsDeleteString(string);
                string = 0;
                ActivationFactory = v16(v15, &string);
                if ( ActivationFactory >= 0 )
                {
                  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 56LL))(v26, &v29);
                  if ( ActivationFactory >= 0 )
                  {
                    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                    if ( !(unsigned int)_o_wcscpy_s(a2, 2048, StringRawBuffer) )
                    {
                      v18 = -1;
                      do
                        ++v18;
                      while ( a2[v18] );
                      *a3 = v18;
                      a2[(unsigned int)v18] = 0;
                      *(_QWORD *)a1 = v29;
                      goto LABEL_36;
                    }
                    ActivationFactory = -2147418113;
                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_36;
                    v24 = "CBR(wcscpy_s(pwszChannelUri, 2048, WindowsGetStringRawBuffer(hstrUri.Get(), nullptr)) == 0)";
                    v23 = -47;
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                      goto LABEL_36;
                    v24 = "CHR(spChannel->get_ExpirationTime(&expiryDateTime))";
                    v23 = -49;
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_36;
                  v24 = "CHR(spChannel->get_Uri(hstrUri.GetAddressOf()))";
                  v23 = -50;
                }
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_36;
              v24 = "CHR(spChannelManagerStatics->CreatePushNotificationChannelForApplicationAsyncWithId( HStringReferenc"
                    "e(wszAppId).Get(), spChannelOperation.GetAddressOf()))";
              v23 = -56;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_36;
            v24 = "CHR(GetActivationFactory( HStringReference(RuntimeClass_Windows_Networking_PushNotifications_PushNotif"
                  "icationChannelManager).Get(), spChannelManagerStatics.GetAddressOf()))";
            v23 = -60;
          }
          McTemplateU0dsqs_EventWriteTransfer(
            v8,
            v7,
            ActivationFactory,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
            v23,
            v24);
          goto LABEL_36;
        }
        ActivationFactory = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)a1,
            (_DWORD)a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
            189,
            "CBR(*pcchChannelUri == 2048)");
      }
      else
      {
        ActivationFactory = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)a1,
            (_DWORD)a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
            188,
            "CPR(pcchChannelUri)");
      }
    }
    else
    {
      ActivationFactory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          0,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
          187,
          "CPR(pwszChannelUri)");
    }
  }
  else
  {
    ActivationFactory = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
        186,
        "CPR(pftExpiration)");
  }
LABEL_36:
  WindowsDeleteString(string);
  string = 0;
  v19 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v20)[2])(v20);
  }
  v21 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180024fb8  push    rbp
0x180024fba  push    rbx
0x180024fbb  push    rsi
0x180024fbc  push    rdi
0x180024fbd  push    r12
0x180024fbf  push    r14
0x180024fc1  push    r15
0x180024fc3  mov     rbp, rsp
0x180024fc6  sub     rsp, 80h
0x180024fcd  mov     rax, cs:__security_cookie
0x180024fd4  xor     rax, rsp
0x180024fd7  mov     [rbp+var_8], rax
0x180024fdb  mov     r14, r8
0x180024fde  mov     rsi, rdx
0x180024fe1  mov     r15, rcx
0x180024fe4  xor     r12d, r12d
0x180024fe7  mov     [rbp+var_30], r12
0x180024feb  mov     [rbp+var_38], r12
0x180024fef  mov     [rbp+var_40], r12
0x180024ff3  mov     [rbp+var_48], r12
0x180024ff7  mov     [rbp+string], r12
0x180024ffb  test    rcx, rcx
0x180024ffe  jnz     short loc_18002502F
0x180025000  mov     r8d, 80070057h
0x180025006  mov     ebx, r8d
0x180025009  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025010  jz      loc_1800252EA
0x180025016  lea     rax, aCprPftexpirati; "CPR(pftExpiration)"
0x18002501d  mov     [rsp+80h+var_58], rax
0x180025022  mov     dword ptr [rsp+80h+var_60], 0BAh
0x18002502a  jmp     loc_1800252DD
0x18002502f  test    rsi, rsi
0x180025032  jnz     short loc_180025063
0x180025034  mov     r8d, 80070057h
0x18002503a  mov     ebx, r8d
0x18002503d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025044  jz      loc_1800252EA
0x18002504a  lea     rax, aCprPwszchannel; "CPR(pwszChannelUri)"
0x180025051  mov     [rsp+80h+var_58], rax
0x180025056  mov     dword ptr [rsp+80h+var_60], 0BBh
0x18002505e  jmp     loc_1800252DD
0x180025063  test    r14, r14
0x180025066  jnz     short loc_180025097
0x180025068  mov     r8d, 80070057h
0x18002506e  mov     ebx, r8d
0x180025071  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025078  jz      loc_1800252EA
0x18002507e  lea     rax, aCprPcchchannel; "CPR(pcchChannelUri)"
0x180025085  mov     [rsp+80h+var_58], rax
0x18002508a  mov     dword ptr [rsp+80h+var_60], 0BCh
0x180025092  jmp     loc_1800252DD
0x180025097  cmp     dword ptr [r8], 800h
0x18002509e  jz      short loc_1800250CF
0x1800250a0  mov     r8d, 80070057h
0x1800250a6  mov     ebx, r8d
0x1800250a9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800250b0  jz      loc_1800252EA
0x1800250b6  lea     rax, aCbrPcchchannel; "CBR(*pcchChannelUri == 2048)"
0x1800250bd  mov     [rsp+80h+var_58], rax
0x1800250c2  mov     dword ptr [rsp+80h+var_60], 0BDh
0x1800250ca  jmp     loc_1800252DD
0x1800250cf  mov     [rdx], r12w
0x1800250d3  mov     [r8], r12d
0x1800250d6  mov     [rbp+var_10], r12
0x1800250da  mov     r9d, 43h ; 'C'; unsigned int
0x1800250e0  lea     r8d, [r9+1]; unsigned int
0x1800250e4  lea     rdx, ?RuntimeClass_Windows_Networking_PushNotifications_PushNotificationChannelManager@@3QBGB; "Windows.Networking.PushNotifications.Pu"...
0x1800250eb  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800250ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800250f4  lea     r8, [rbp+var_38]
0x1800250f8  lea     rdx, _GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0
0x1800250ff  mov     rcx, [rbp+var_10]
0x180025103  call    cs:__imp_RoGetActivationFactory
0x180025109  mov     ebx, eax
0x18002510b  test    eax, eax
0x18002510d  jns     short loc_180025135
0x18002510f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025116  jz      loc_1800252EA
0x18002511c  lea     rax, aChrGetactivati_4; "CHR(GetActivationFactory( HStringRefere"...
0x180025123  mov     [rsp+80h+var_58], rax
0x180025128  mov     dword ptr [rsp+80h+var_60], 0C4h
0x180025130  jmp     loc_1800252DA
0x180025135  mov     rdi, [rbp+var_38]
0x180025139  mov     rax, [rdi]
0x18002513c  mov     rbx, [rax+38h]
0x180025140  lea     rdx, off_18002B7C8; "7bf7f519-2c1b-439d-b296-0878bd5c4991"
0x180025147  lea     rcx, [rbp+hstringHeader]
0x18002514b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180025150  nop
0x180025151  lea     r8, [rbp+var_40]
0x180025155  mov     rdx, [rax+18h]
0x180025159  mov     rcx, rdi
0x18002515c  mov     rax, rbx
0x18002515f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025164  mov     ebx, eax
0x180025166  test    eax, eax
0x180025168  jns     short loc_180025190
0x18002516a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025171  jz      loc_1800252EA
0x180025177  lea     rax, aChrSpchannelma; "CHR(spChannelManagerStatics->CreatePush"...
0x18002517e  mov     [rsp+80h+var_58], rax
0x180025183  mov     dword ptr [rsp+80h+var_60], 0C8h
0x18002518b  jmp     loc_1800252DA
0x180025190  mov     rdi, [rbp+var_40]
0x180025194  mov     rcx, rdi
0x180025197  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)
0x18002519c  mov     ebx, eax
0x18002519e  test    eax, eax
0x1800251a0  js      loc_1800252BD
0x1800251a6  mov     rax, [rdi]
0x1800251a9  lea     rdx, [rbp+var_48]
0x1800251ad  mov     rcx, rdi
0x1800251b0  mov     rax, [rax+40h]
0x1800251b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251b9  mov     ebx, eax
0x1800251bb  test    eax, eax
0x1800251bd  js      loc_1800252BD
0x1800251c3  mov     rdi, [rbp+var_48]
0x1800251c7  mov     rax, [rdi]
0x1800251ca  mov     rbx, [rax+30h]
0x1800251ce  mov     rcx, [rbp+string]; string
0x1800251d2  call    cs:__imp_WindowsDeleteString
0x1800251d8  mov     [rbp+string], r12
0x1800251dc  lea     rdx, [rbp+string]
0x1800251e0  mov     rcx, rdi
0x1800251e3  mov     rax, rbx
0x1800251e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251eb  mov     ebx, eax
0x1800251ed  test    eax, eax
0x1800251ef  jns     short loc_180025217
0x1800251f1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800251f8  jz      loc_1800252EA
0x1800251fe  lea     rax, aChrSpchannelGe_0; "CHR(spChannel->get_Uri(hstrUri.GetAddre"...
0x180025205  mov     [rsp+80h+var_58], rax
0x18002520a  mov     dword ptr [rsp+80h+var_60], 0CEh
0x180025212  jmp     loc_1800252DA
0x180025217  mov     rcx, [rbp+var_48]
0x18002521b  mov     rax, [rcx]
0x18002521e  lea     rdx, [rbp+var_30]
0x180025222  mov     rax, [rax+38h]
0x180025226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002522b  mov     ebx, eax
0x18002522d  test    eax, eax
0x18002522f  jns     short loc_180025257
0x180025231  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025238  jz      loc_1800252EA
0x18002523e  lea     rax, aChrSpchannelGe; "CHR(spChannel->get_ExpirationTime(&expi"...
0x180025245  mov     [rsp+80h+var_58], rax
0x18002524a  mov     dword ptr [rsp+80h+var_60], 0CFh
0x180025252  jmp     loc_1800252DA
0x180025257  xor     edx, edx; length
0x180025259  mov     rcx, [rbp+string]; string
0x18002525d  call    cs:__imp_WindowsGetStringRawBuffer
0x180025263  mov     r8, rax
0x180025266  mov     edx, 800h
0x18002526b  mov     rcx, rsi
0x18002526e  call    cs:__imp__o_wcscpy_s
0x180025274  test    eax, eax
0x180025276  jz      short loc_18002529C
0x180025278  mov     ebx, 8000FFFFh
0x18002527d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180025284  jz      short loc_1800252EA
0x180025286  lea     rax, aCbrWcscpySPwsz_0; "CBR(wcscpy_s(pwszChannelUri, 2048, Wind"...
0x18002528d  mov     [rsp+80h+var_58], rax
0x180025292  mov     dword ptr [rsp+80h+var_60], 0D1h
0x18002529a  jmp     short loc_1800252DA
0x18002529c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800252a0  inc     rax
0x1800252a3  cmp     [rsi+rax*2], r12w
0x1800252a8  jnz     short loc_1800252A0
0x1800252aa  mov     ecx, eax
0x1800252ac  mov     [r14], ecx
0x1800252af  mov     [rsi+rcx*2], r12w
0x1800252b4  mov     rax, [rbp+var_30]
0x1800252b8  mov     [r15], rax
0x1800252bb  jmp     short loc_1800252EA
0x1800252bd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800252c4  jz      short loc_1800252EA
0x1800252c6  lea     rax, aChrBlockoncomp_2; "CHR(BlockOnCompletionAndGetResults<IAsy"...
0x1800252cd  mov     [rsp+80h+var_58], rax
0x1800252d2  mov     dword ptr [rsp+80h+var_60], 0CCh
0x1800252da  mov     r8d, ebx
0x1800252dd  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800252e4  call    McTemplateU0dsqs_EventWriteTransfer
0x1800252e9  nop
0x1800252ea  mov     rcx, [rbp+string]; string
0x1800252ee  call    cs:__imp_WindowsDeleteString
0x1800252f4  mov     [rbp+string], r12
0x1800252f8  mov     rcx, [rbp+var_48]
0x1800252fc  test    rcx, rcx
0x1800252ff  jz      short loc_180025312
0x180025301  mov     [rbp+var_48], r12
0x180025305  mov     rax, [rcx]
0x180025308  mov     rax, [rax+10h]
0x18002530c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025311  nop
0x180025312  mov     rcx, [rbp+var_40]
0x180025316  test    rcx, rcx
0x180025319  jz      short loc_18002532C
0x18002531b  mov     [rbp+var_40], r12
0x18002531f  mov     rax, [rcx]
0x180025322  mov     rax, [rax+10h]
0x180025326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002532b  nop
0x18002532c  mov     rcx, [rbp+var_38]
0x180025330  test    rcx, rcx
0x180025333  jz      short loc_180025346
0x180025335  mov     [rbp+var_38], r12
0x180025339  mov     rax, [rcx]
0x18002533c  mov     rax, [rax+10h]
0x180025340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025345  nop
0x180025346  mov     eax, ebx
0x180025348  mov     rcx, [rbp+var_8]
0x18002534c  xor     rcx, rsp; StackCookie
0x18002534f  call    __security_check_cookie
0x180025354  add     rsp, 80h
0x18002535b  pop     r15
0x18002535d  pop     r14
0x18002535f  pop     r12
0x180025361  pop     rdi
0x180025362  pop     rsi
0x180025363  pop     rbx
0x180025364  pop     rbp
0x180025365  retn
```
