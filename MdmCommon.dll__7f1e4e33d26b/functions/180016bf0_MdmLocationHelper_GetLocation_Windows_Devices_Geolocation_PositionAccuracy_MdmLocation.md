# MdmLocationHelper::GetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)

- ea: `0x180016bf0`
- end: `0x1800172fd`
- name: `?GetLocation@MdmLocationHelper@@SAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z`
- size: `1805`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800035d0`

## callees

- `0x180001520`
- `0x180001594`
- `0x180006548`
- `0x180016bf0`
- `0x18001d504`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c7c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c98`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ede`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180016d54`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180016d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001720b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001720b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016ed4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016ed4`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180016e50`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180016e50`

## string_xrefs

- `0x1800171e0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmlocationhelper.cpp`
- `0x1800171c9`: `CHR(ActivateInstance(geolocatorClassId.Get(), pGeolocator.GetAddressOf()))`
- `0x180016e75`: `CBR(hComplete.m_h != 0)`
- `0x180016eb4`: `CHR(pGetOperation->put_Completed(CompletionCallback.Get()))`
- `0x180016f00`: `CBR(WaitForSingleObject(hComplete, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 ))`

## pseudocode

```c
__int64 __fastcall MdmLocationHelper::GetLocation(unsigned int a1, __int64 a2)
{
  _QWORD *v4; // rax
  int v5; // edx
  int v6; // ecx
  _QWORD *v7; // rbx
  signed int v8; // edi
  int v9; // eax
  __int64 v10; // rcx
  int v11; // edx
  int v12; // ecx
  signed int LastError; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rsi
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  char v31; // [rsp+20h] [rbp-A9h]
  const char *v32; // [rsp+28h] [rbp-A1h]
  __int64 v33; // [rsp+30h] [rbp-99h] BYREF
  __int64 v34; // [rsp+38h] [rbp-91h] BYREF
  __int64 v35; // [rsp+40h] [rbp-89h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-81h] BYREF
  __int64 v37; // [rsp+50h] [rbp-79h] BYREF
  int v38; // [rsp+58h] [rbp-71h] BYREF
  HANDLE hHandle; // [rsp+60h] [rbp-69h] BYREF
  __int64 v40; // [rsp+68h] [rbp-61h] BYREF
  __int64 v41; // [rsp+70h] [rbp-59h] BYREF
  __int64 v42; // [rsp+78h] [rbp-51h] BYREF
  double v43; // [rsp+80h] [rbp-49h] BYREF
  double v44[3]; // [rsp+88h] [rbp-41h] BYREF
  __int128 v45; // [rsp+A0h] [rbp-29h]
  __int64 v46; // [rsp+B0h] [rbp-19h]
  _QWORD *v47; // [rsp+B8h] [rbp-11h]
  __int128 v48; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v49; // [rsp+D0h] [rbp+7h]
  HSTRING string; // [rsp+D8h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp+17h] BYREF

  v38 = 0;
  v33 = 0;
  v42 = 0;
  v40 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v43 = 0.0;
  v44[0] = 0.0;
  v48 = 0;
  v49 = 0;
  hHandle = 0;
  v46 = 0;
  if ( WindowsCreateStringReference(L"Windows.Devices.Geolocation.Geolocator", 0x26u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v4;
  if ( v4 )
  {
    *v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>::`vftable';
    *((_DWORD *)v4 + 3) = 1;
    *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`vftable';
    v6 = (int)Microsoft::WRL::Details::ModuleBase::module_;
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v7[2] = &hHandle;
    v7[3] = &v40;
    v7[4] = &v38;
    *v7 = off_1800200E0;
  }
  else
  {
    v7 = 0;
  }
  v47 = v7;
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_70;
    v32 = "CBR(pResult != 0)";
    v31 = 72;
    goto LABEL_69;
  }
  v33 = 0;
  v41 = 0;
  v8 = RoActivateInstance(string, &v41);
  if ( v8 < 0 )
    goto LABEL_67;
  v9 = memcmp_0(&GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
  v10 = v41;
  if ( !v9 )
  {
    v33 = v41;
    goto LABEL_16;
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v41)(
         v41,
         &GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f,
         &v33);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v8 < 0 )
  {
LABEL_67:
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_70;
    v32 = "CHR(ActivateInstance(geolocatorClassId.Get(), pGeolocator.GetAddressOf()))";
    v31 = 75;
    goto LABEL_69;
  }
  v10 = v33;
LABEL_16:
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 56LL))(v10, a1);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_70;
    v32 = "CHR(pGeolocator->put_DesiredAccuracy(desiredAccuracy))";
    v31 = 76;
    goto LABEL_69;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v33 + 112LL))(
         v33,
         0,
         1200000000,
         &v42);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_70;
    v32 = "CHR(pGeolocator->GetGeopositionAsyncWithAgeAndTimeout(ageTimeSpan, timeoutTimeSpan, pGetOperation.GetAddressOf()))";
    v31 = 77;
    goto LABEL_69;
  }
  hHandle = CreateEventA(0, 0, 0, 0);
  if ( hHandle )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v42 + 48LL))(v42, v7);
    if ( v8 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_70;
      v32 = "CHR(pGetOperation->put_Completed(CompletionCallback.Get()))";
      v31 = 82;
      goto LABEL_69;
    }
    if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v32 = "CBR(WaitForSingleObject(hComplete, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 ))";
        v31 = 85;
LABEL_69:
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmlocationhelper.cpp",
          v31,
          v32);
      }
    }
    else
    {
      v8 = v38;
      if ( v38 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_70;
        v32 = "CHR(hrCallback)";
        v31 = 86;
        goto LABEL_69;
      }
      if ( v40 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v40 + 48LL))(
               v40,
               &v36);
        if ( v8 >= 0 )
        {
          v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), double *))(*v36)[9])(
                 v36,
                 &v43);
          if ( v8 >= 0 )
          {
            v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
            v15 = (*v36)[10];
            v16 = v34;
            if ( v34 )
            {
              v34 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
            v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v15)(v14, &v34);
            if ( v8 >= 0 )
            {
              DWORD2(v45) = (int)v43;
              if ( v34 )
              {
                HIDWORD(v45) = 1;
                (*(void (__fastcall **)(__int64, double *))(*(_QWORD *)v34 + 48LL))(v34, v44);
                LODWORD(v46) = (int)v44[0];
              }
              else
              {
                HIDWORD(v45) = 0;
              }
              v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
              v18 = **v36;
              v19 = v35;
              if ( v35 )
              {
                v35 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              }
              v8 = v18(v17, &GUID_feea0525_d22c_4d46_b527_0b96066fc7db, &v35);
              if ( v8 >= 0 )
              {
                v20 = v35;
                v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 48LL);
                v22 = v37;
                if ( v37 )
                {
                  v37 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                }
                v8 = v21(v20, &v37);
                if ( v8 >= 0 )
                {
                  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v37 + 48LL))(v37, &v48);
                  if ( v8 >= 0 )
                  {
                    *(_QWORD *)&v45 = v49;
                    *(_OWORD *)a2 = v48;
                    *(_OWORD *)(a2 + 16) = v45;
                    *(_QWORD *)(a2 + 32) = v46;
                    goto LABEL_70;
                  }
                  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                    goto LABEL_70;
                  v32 = "CHR(pGeopoint->get_Position(&basicGeoposition))";
                  v31 = 109;
                }
                else
                {
                  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                    goto LABEL_70;
                  v32 = "CHR(pGeocoordinateWithPoint->get_Point(&pGeopoint))";
                  v31 = 108;
                }
              }
              else
              {
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                  goto LABEL_70;
                v32 = "CHR(pGeocoordinate.As(&pGeocoordinateWithPoint))";
                v31 = 107;
              }
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                goto LABEL_70;
              v32 = "CHR(pGeocoordinate->get_AltitudeAccuracy(&pdAltitudeAccuracy))";
              v31 = 92;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
              goto LABEL_70;
            v32 = "CHR(pGeocoordinate->get_Accuracy(&dPositionAccuracy))";
            v31 = 91;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_70;
          v32 = "CHR(pGeoposition->get_Coordinate(pGeocoordinate.GetAddressOf()))";
          v31 = 90;
        }
        goto LABEL_69;
      }
      v8 = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmlocationhelper.cpp",
          87,
          "CBR(pGeoposition != 0)");
    }
  }
  else
  {
    v8 = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        -2147467259,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmlocationhelper.cpp",
        81,
        "CBR(hComplete.m_h != 0)");
  }
LABEL_70:
  if ( v7 )
    (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
  if ( hHandle )
  {
    CloseHandle(hHandle);
    hHandle = 0;
  }
  v23 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
  if ( v36 )
  {
    v36 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v25)[2])(v25);
  }
  v26 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016bf0  mov     [rsp-8+arg_10], rbx
0x180016bf5  mov     [rsp-8+arg_18], rsi
0x180016bfa  push    rbp
0x180016bfb  push    rdi
0x180016bfc  push    r12
0x180016bfe  push    r14
0x180016c00  push    r15
0x180016c02  lea     rbp, [rsp-37h]
0x180016c07  sub     rsp, 100h
0x180016c0e  mov     rax, cs:__security_cookie
0x180016c15  xor     rax, rsp
0x180016c18  mov     [rbp+57h+var_28], rax
0x180016c1c  mov     r14, rdx
0x180016c1f  mov     esi, ecx
0x180016c21  xor     r15d, r15d
0x180016c24  mov     [rbp+57h+var_C8], r15d
0x180016c28  mov     [rsp+120h+var_F0], r15
0x180016c2d  mov     [rbp+57h+var_A8], r15
0x180016c31  mov     [rbp+57h+var_B8], r15
0x180016c35  mov     [rbp+57h+var_D0], r15
0x180016c39  mov     [rsp+120h+var_D8], r15
0x180016c3e  mov     [rsp+120h+var_E0], r15
0x180016c43  mov     [rsp+120h+var_E8], r15
0x180016c48  xorps   xmm0, xmm0
0x180016c4b  movsd   [rbp+57h+var_A0], xmm0
0x180016c50  movsd   [rbp+57h+var_98], xmm0
0x180016c55  xorps   xmm1, xmm1
0x180016c58  xor     eax, eax
0x180016c5a  movups  [rbp+57h+var_60], xmm1
0x180016c5e  mov     [rbp+57h+var_50], rax
0x180016c62  mov     [rbp+57h+hHandle], r15
0x180016c66  mov     [rbp+57h+var_70], r15
0x180016c6a  lea     r9, [rbp+57h+string]; string
0x180016c6e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180016c72  lea     edx, [rax+26h]; length
0x180016c75  lea     rcx, ?RuntimeClass_Windows_Devices_Geolocation_Geolocator@@3QBGB; "Windows.Devices.Geolocation.Geolocator"
0x180016c7c  call    cs:__imp_WindowsCreateStringReference
0x180016c82  lea     r12d, [r15+1]
0x180016c86  test    eax, eax
0x180016c88  jns     short loc_180016C9E
0x180016c8a  xor     r9d, r9d; lpArguments
0x180016c8d  xor     r8d, r8d; nNumberOfArguments
0x180016c90  mov     edx, r12d; dwExceptionFlags
0x180016c93  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016c98  call    cs:__imp_RaiseException
0x180016c9e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016ca5  mov     ecx, 28h ; '('; unsigned __int64
0x180016caa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016caf  mov     rbx, rax
0x180016cb2  test    rax, rax
0x180016cb5  jz      short loc_180016D0C
0x180016cb7  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>::`vftable'
0x180016cbe  mov     [rbx], rax
0x180016cc1  mov     [rbx+0Ch], r12d
0x180016cc5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`vftable'
0x180016ccc  mov     [rbx], rax
0x180016ccf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180016cd6  test    rcx, rcx
0x180016cd9  jz      short loc_180016CE8
0x180016cdb  mov     rax, [rcx]
0x180016cde  mov     rax, [rax+8]
0x180016ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce7  nop
0x180016ce8  lea     rax, [rbp+57h+hHandle]
0x180016cec  mov     [rbx+10h], rax
0x180016cf0  lea     rax, [rbp+57h+var_B8]
0x180016cf4  mov     [rbx+18h], rax
0x180016cf8  lea     rax, [rbp+57h+var_C8]
0x180016cfc  mov     [rbx+20h], rax
0x180016d00  lea     rax, off_1800200E0
0x180016d07  mov     [rbx], rax
0x180016d0a  jmp     short loc_180016D0F
0x180016d0c  mov     rbx, r15
0x180016d0f  mov     [rbp+57h+var_68], rbx
0x180016d13  test    r14, r14
0x180016d16  jnz     short loc_180016D43
0x180016d18  mov     edi, 80070057h
0x180016d1d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016d24  jz      loc_1800171ED
0x180016d2a  lea     rax, aCbrPresult0; "CBR(pResult != 0)"
0x180016d31  mov     [rsp+120h+var_F8], rax
0x180016d36  mov     dword ptr [rsp+120h+var_100], 48h ; 'H'
0x180016d3e  jmp     loc_1800171DD
0x180016d43  mov     [rsp+120h+var_F0], r15
0x180016d48  mov     [rbp+57h+var_B0], r15
0x180016d4c  lea     rdx, [rbp+57h+var_B0]
0x180016d50  mov     rcx, [rbp+57h+string]
0x180016d54  call    cs:__imp_RoActivateInstance
0x180016d5a  mov     edi, eax
0x180016d5c  test    eax, eax
0x180016d5e  js      loc_1800171C0
0x180016d64  mov     r8d, 10h; Size
0x180016d6a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180016d71  lea     rcx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f; Buf1
0x180016d78  call    memcmp_0
0x180016d7d  mov     rcx, [rbp+57h+var_B0]
0x180016d81  test    eax, eax
0x180016d83  jnz     short loc_180016D8C
0x180016d85  mov     [rsp+120h+var_F0], rcx
0x180016d8a  jmp     short loc_180016DC2
0x180016d8c  mov     rax, [rcx]
0x180016d8f  lea     r8, [rsp+120h+var_F0]
0x180016d94  lea     rdx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f
0x180016d9b  mov     rax, [rax]
0x180016d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016da3  mov     edi, eax
0x180016da5  mov     rcx, [rbp+57h+var_B0]
0x180016da9  mov     rax, [rcx]
0x180016dac  mov     rax, [rax+10h]
0x180016db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016db5  test    edi, edi
0x180016db7  js      loc_1800171C0
0x180016dbd  mov     rcx, [rsp+120h+var_F0]
0x180016dc2  mov     rax, [rcx]
0x180016dc5  mov     edx, esi
0x180016dc7  mov     rax, [rax+38h]
0x180016dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dd0  mov     edi, eax
0x180016dd2  test    eax, eax
0x180016dd4  jns     short loc_180016DFC
0x180016dd6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016ddd  jz      loc_1800171ED
0x180016de3  lea     rax, aChrPgeolocator; "CHR(pGeolocator->put_DesiredAccuracy(de"...
0x180016dea  mov     [rsp+120h+var_F8], rax
0x180016def  mov     dword ptr [rsp+120h+var_100], 4Ch ; 'L'
0x180016df7  jmp     loc_1800171DD
0x180016dfc  mov     rcx, [rsp+120h+var_F0]
0x180016e01  mov     rdx, r15
0x180016e04  mov     rax, [rcx]
0x180016e07  lea     r9, [rbp+57h+var_A8]
0x180016e0b  mov     r8d, 47868C00h
0x180016e11  mov     rax, [rax+70h]
0x180016e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e1a  mov     edi, eax
0x180016e1c  test    eax, eax
0x180016e1e  jns     short loc_180016E46
0x180016e20  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016e27  jz      loc_1800171ED
0x180016e2d  lea     rax, aChrPgeolocator_0; "CHR(pGeolocator->GetGeopositionAsyncWit"...
0x180016e34  mov     [rsp+120h+var_F8], rax
0x180016e39  mov     dword ptr [rsp+120h+var_100], 4Dh ; 'M'
0x180016e41  jmp     loc_1800171DD
0x180016e46  xor     r9d, r9d; lpName
0x180016e49  xor     r8d, r8d; bInitialState
0x180016e4c  xor     edx, edx; bManualReset
0x180016e4e  xor     ecx, ecx; lpEventAttributes
0x180016e50  call    cs:__imp_CreateEventA
0x180016e56  mov     [rbp+57h+hHandle], rax
0x180016e5a  test    rax, rax
0x180016e5d  jnz     short loc_180016E8E
0x180016e5f  mov     r8d, 80004005h
0x180016e65  mov     edi, r8d
0x180016e68  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016e6f  jz      loc_1800171ED
0x180016e75  lea     rax, aCbrHcompleteMH; "CBR(hComplete.m_h != 0)"
0x180016e7c  mov     [rsp+120h+var_F8], rax
0x180016e81  mov     dword ptr [rsp+120h+var_100], 51h ; 'Q'
0x180016e89  jmp     loc_1800171E0
0x180016e8e  mov     rcx, [rbp+57h+var_A8]
0x180016e92  mov     rax, [rcx]
0x180016e95  mov     rdx, rbx
0x180016e98  mov     rax, [rax+30h]
0x180016e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ea1  mov     edi, eax
0x180016ea3  test    eax, eax
0x180016ea5  jns     short loc_180016ECD
0x180016ea7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016eae  jz      loc_1800171ED
0x180016eb4  lea     rax, aChrPgetoperati; "CHR(pGetOperation->put_Completed(Comple"...
0x180016ebb  mov     [rsp+120h+var_F8], rax
0x180016ec0  mov     dword ptr [rsp+120h+var_100], 52h ; 'R'
0x180016ec8  jmp     loc_1800171DD
0x180016ecd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180016ed0  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180016ed4  call    cs:__imp_WaitForSingleObject
0x180016eda  test    eax, eax
0x180016edc  jz      short loc_180016F19
0x180016ede  call    cs:__imp_GetLastError
0x180016ee4  mov     edi, eax
0x180016ee6  test    eax, eax
0x180016ee8  jle     short loc_180016EF3
0x180016eea  movzx   edi, ax
0x180016eed  or      edi, 80070000h
0x180016ef3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016efa  jz      loc_1800171ED
0x180016f00  lea     rax, aCbrWaitforsing; "CBR(WaitForSingleObject(hComplete, 0xFF"...
0x180016f07  mov     [rsp+120h+var_F8], rax
0x180016f0c  mov     dword ptr [rsp+120h+var_100], 55h ; 'U'
0x180016f14  jmp     loc_1800171DD
0x180016f19  mov     edi, [rbp+57h+var_C8]
0x180016f1c  test    edi, edi
0x180016f1e  jns     short loc_180016F46
0x180016f20  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016f27  jz      loc_1800171ED
0x180016f2d  lea     rax, aChrHrcallback; "CHR(hrCallback)"
0x180016f34  mov     [rsp+120h+var_F8], rax
0x180016f39  mov     dword ptr [rsp+120h+var_100], 56h ; 'V'
0x180016f41  jmp     loc_1800171DD
0x180016f46  cmp     [rbp+57h+var_B8], r15
0x180016f4a  jnz     short loc_180016F7B
0x180016f4c  mov     r8d, 80004005h
0x180016f52  mov     edi, r8d
0x180016f55  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016f5c  jz      loc_1800171ED
0x180016f62  lea     rax, aCbrPgeopositio; "CBR(pGeoposition != 0)"
0x180016f69  mov     [rsp+120h+var_F8], rax
0x180016f6e  mov     dword ptr [rsp+120h+var_100], 57h ; 'W'
0x180016f76  jmp     loc_1800171E0
0x180016f7b  mov     rcx, [rbp+57h+var_B8]
0x180016f7f  mov     rax, [rcx]
0x180016f82  lea     rdx, [rsp+120h+var_D8]
0x180016f87  mov     rax, [rax+30h]
0x180016f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f90  mov     edi, eax
0x180016f92  test    eax, eax
0x180016f94  jns     short loc_180016FBC
0x180016f96  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016f9d  jz      loc_1800171ED
0x180016fa3  lea     rax, aChrPgeopositio; "CHR(pGeoposition->get_Coordinate(pGeoco"...
0x180016faa  mov     [rsp+120h+var_F8], rax
0x180016faf  mov     dword ptr [rsp+120h+var_100], 5Ah ; 'Z'
0x180016fb7  jmp     loc_1800171DD
0x180016fbc  mov     rcx, [rsp+120h+var_D8]
0x180016fc1  mov     rax, [rcx]
0x180016fc4  lea     rdx, [rbp+57h+var_A0]
0x180016fc8  mov     rax, [rax+48h]
0x180016fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fd1  mov     edi, eax
0x180016fd3  test    eax, eax
0x180016fd5  jns     short loc_180016FFD
0x180016fd7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180016fde  jz      loc_1800171ED
0x180016fe4  lea     rax, aChrPgeocoordin; "CHR(pGeocoordinate->get_Accuracy(&dPosi"...
0x180016feb  mov     [rsp+120h+var_F8], rax
0x180016ff0  mov     dword ptr [rsp+120h+var_100], 5Bh ; '['
0x180016ff8  jmp     loc_1800171DD
0x180016ffd  mov     rdi, [rsp+120h+var_D8]
0x180017002  mov     rax, [rdi]
0x180017005  mov     rsi, [rax+50h]
0x180017009  mov     rcx, [rsp+120h+var_E8]
0x18001700e  test    rcx, rcx
0x180017011  jz      short loc_180017025
0x180017013  mov     [rsp+120h+var_E8], r15
0x180017018  mov     rdx, [rcx]
0x18001701b  mov     rax, [rdx+10h]
0x18001701f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017024  nop
0x180017025  lea     rdx, [rsp+120h+var_E8]
0x18001702a  mov     rcx, rdi
0x18001702d  mov     rax, rsi
0x180017030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017035  mov     edi, eax
0x180017037  test    eax, eax
0x180017039  jns     short loc_180017061
0x18001703b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180017042  jz      loc_1800171ED
0x180017048  lea     rax, aChrPgeocoordin_1; "CHR(pGeocoordinate->get_AltitudeAccurac"...
0x18001704f  mov     [rsp+120h+var_F8], rax
0x180017054  mov     dword ptr [rsp+120h+var_100], 5Ch ; '\'
0x18001705c  jmp     loc_1800171DD
0x180017061  cvttsd2si rax, [rbp+57h+var_A0]
0x180017067  mov     dword ptr [rbp+57h+var_80+8], eax
0x18001706a  mov     rcx, [rsp+120h+var_E8]
0x18001706f  test    rcx, rcx
0x180017072  jz      short loc_180017093
0x180017074  mov     dword ptr [rbp+57h+var_80+0Ch], r12d
0x180017078  mov     rax, [rcx]
0x18001707b  lea     rdx, [rbp+57h+var_98]
0x18001707f  mov     rax, [rax+30h]
0x180017083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017088  cvttsd2si rax, [rbp+57h+var_98]
0x18001708e  mov     dword ptr [rbp+57h+var_70], eax
0x180017091  jmp     short loc_180017097
0x180017093  mov     dword ptr [rbp+57h+var_80+0Ch], r15d
0x180017097  mov     rdi, [rsp+120h+var_D8]
0x18001709c  mov     rax, [rdi]
0x18001709f  mov     rsi, [rax]
0x1800170a2  mov     rcx, [rsp+120h+var_E0]
0x1800170a7  test    rcx, rcx
0x1800170aa  jz      short loc_1800170BE
0x1800170ac  mov     [rsp+120h+var_E0], r15
0x1800170b1  mov     rdx, [rcx]
0x1800170b4  mov     rax, [rdx+10h]
0x1800170b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170bd  nop
0x1800170be  lea     r8, [rsp+120h+var_E0]
0x1800170c3  lea     rdx, _GUID_feea0525_d22c_4d46_b527_0b96066fc7db
0x1800170ca  mov     rcx, rdi
0x1800170cd  mov     rax, rsi
0x1800170d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170d5  mov     edi, eax
0x1800170d7  test    eax, eax
0x1800170d9  jns     short loc_180017101
0x1800170db  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x1800170e2  jz      loc_1800171ED
0x1800170e8  lea     rax, aChrPgeocoordin_2; "CHR(pGeocoordinate.As(&pGeocoordinateWi"...
0x1800170ef  mov     [rsp+120h+var_F8], rax
0x1800170f4  mov     dword ptr [rsp+120h+var_100], 6Bh ; 'k'
0x1800170fc  jmp     loc_1800171DD
0x180017101  mov     rdi, [rsp+120h+var_E0]
  ... truncated ...
```
