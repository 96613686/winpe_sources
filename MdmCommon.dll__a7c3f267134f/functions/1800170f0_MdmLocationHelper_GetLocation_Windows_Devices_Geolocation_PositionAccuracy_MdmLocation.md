# MdmLocationHelper::GetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)

- ea: `0x1800170f0`
- end: `0x180017828`
- name: `?GetLocation@MdmLocationHelper@@SAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z`
- size: `1848`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800035e0`

## callees

- `0x180001520`
- `0x180001594`
- `0x1800065c0`
- `0x1800170f0`
- `0x18001dbe4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001717c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001717c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001719e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001719e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173fc`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180017260`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180017260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001772f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001772f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800173ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800173ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180017362`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180017362`

## string_xrefs

- `0x180017704`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmlocationhelper.cpp`
- `0x1800176ed`: `CHR(ActivateInstance(geolocatorClassId.Get(), pGeolocator.GetAddressOf()))`
- `0x18001738d`: `CBR(hComplete.m_h != 0)`
- `0x1800173cc`: `CHR(pGetOperation->put_Completed(CompletionCallback.Get()))`
- `0x180017424`: `CBR(WaitForSingleObject(hComplete, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 ))`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
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
0x1800170f0  mov     [rsp-8+arg_10], rbx
0x1800170f5  mov     [rsp-8+arg_18], rsi
0x1800170fa  push    rbp
0x1800170fb  push    rdi
0x1800170fc  push    r12
0x1800170fe  push    r14
0x180017100  push    r15
0x180017102  lea     rbp, [rsp-37h]
0x180017107  sub     rsp, 100h
0x18001710e  mov     rax, cs:__security_cookie
0x180017115  xor     rax, rsp
0x180017118  mov     [rbp+57h+var_28], rax
0x18001711c  mov     r14, rdx
0x18001711f  mov     esi, ecx
0x180017121  xor     r15d, r15d
0x180017124  mov     [rbp+57h+var_C8], r15d
0x180017128  mov     [rsp+120h+var_F0], r15
0x18001712d  mov     [rbp+57h+var_A8], r15
0x180017131  mov     [rbp+57h+var_B8], r15
0x180017135  mov     [rbp+57h+var_D0], r15
0x180017139  mov     [rsp+120h+var_D8], r15
0x18001713e  mov     [rsp+120h+var_E0], r15
0x180017143  mov     [rsp+120h+var_E8], r15
0x180017148  xorps   xmm0, xmm0
0x18001714b  movsd   [rbp+57h+var_A0], xmm0
0x180017150  movsd   [rbp+57h+var_98], xmm0
0x180017155  xorps   xmm1, xmm1
0x180017158  xor     eax, eax
0x18001715a  movups  [rbp+57h+var_60], xmm1
0x18001715e  mov     [rbp+57h+var_50], rax
0x180017162  mov     [rbp+57h+hHandle], r15
0x180017166  mov     [rbp+57h+var_70], r15
0x18001716a  lea     r9, [rbp+57h+string]; string
0x18001716e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180017172  lea     edx, [rax+26h]; length
0x180017175  lea     rcx, ?RuntimeClass_Windows_Devices_Geolocation_Geolocator@@3QBGB; "Windows.Devices.Geolocation.Geolocator"
0x18001717c  call    cs:__imp_WindowsCreateStringReference
0x180017183  nop     dword ptr [rax+rax+00h]
0x180017188  lea     r12d, [r15+1]
0x18001718c  test    eax, eax
0x18001718e  jns     short loc_1800171AA
0x180017190  xor     r9d, r9d; lpArguments
0x180017193  xor     r8d, r8d; nNumberOfArguments
0x180017196  mov     edx, r12d; dwExceptionFlags
0x180017199  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001719e  call    cs:__imp_RaiseException
0x1800171a5  nop     dword ptr [rax+rax+00h]
0x1800171aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800171b1  mov     ecx, 28h ; '('; unsigned __int64
0x1800171b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800171bb  mov     rbx, rax
0x1800171be  test    rax, rax
0x1800171c1  jz      short loc_180017218
0x1800171c3  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>::`vftable'
0x1800171ca  mov     [rbx], rax
0x1800171cd  mov     [rbx+0Ch], r12d
0x1800171d1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`vftable'
0x1800171d8  mov     [rbx], rax
0x1800171db  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800171e2  test    rcx, rcx
0x1800171e5  jz      short loc_1800171F4
0x1800171e7  mov     rax, [rcx]
0x1800171ea  mov     rax, [rax+8]
0x1800171ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171f3  nop
0x1800171f4  lea     rax, [rbp+57h+hHandle]
0x1800171f8  mov     [rbx+10h], rax
0x1800171fc  lea     rax, [rbp+57h+var_B8]
0x180017200  mov     [rbx+18h], rax
0x180017204  lea     rax, [rbp+57h+var_C8]
0x180017208  mov     [rbx+20h], rax
0x18001720c  lea     rax, off_1800200E0
0x180017213  mov     [rbx], rax
0x180017216  jmp     short loc_18001721B
0x180017218  mov     rbx, r15
0x18001721b  mov     [rbp+57h+var_68], rbx
0x18001721f  test    r14, r14
0x180017222  jnz     short loc_18001724F
0x180017224  mov     edi, 80070057h
0x180017229  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180017230  jz      loc_180017711
0x180017236  lea     rax, aCbrPresult0; "CBR(pResult != 0)"
0x18001723d  mov     [rsp+120h+var_F8], rax
0x180017242  mov     dword ptr [rsp+120h+var_100], 48h ; 'H'
0x18001724a  jmp     loc_180017701
0x18001724f  mov     [rsp+120h+var_F0], r15
0x180017254  mov     [rbp+57h+var_B0], r15
0x180017258  lea     rdx, [rbp+57h+var_B0]
0x18001725c  mov     rcx, [rbp+57h+string]
0x180017260  call    cs:__imp_RoActivateInstance
0x180017267  nop     dword ptr [rax+rax+00h]
0x18001726c  mov     edi, eax
0x18001726e  test    eax, eax
0x180017270  js      loc_1800176E4
0x180017276  mov     r8d, 10h; Size
0x18001727c  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180017283  lea     rcx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f; Buf1
0x18001728a  call    memcmp_0
0x18001728f  mov     rcx, [rbp+57h+var_B0]
0x180017293  test    eax, eax
0x180017295  jnz     short loc_18001729E
0x180017297  mov     [rsp+120h+var_F0], rcx
0x18001729c  jmp     short loc_1800172D4
0x18001729e  mov     rax, [rcx]
0x1800172a1  lea     r8, [rsp+120h+var_F0]
0x1800172a6  lea     rdx, _GUID_a9c3bf62_4524_4989_8aa9_de019d2e551f
0x1800172ad  mov     rax, [rax]
0x1800172b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172b5  mov     edi, eax
0x1800172b7  mov     rcx, [rbp+57h+var_B0]
0x1800172bb  mov     rax, [rcx]
0x1800172be  mov     rax, [rax+10h]
0x1800172c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c7  test    edi, edi
0x1800172c9  js      loc_1800176E4
0x1800172cf  mov     rcx, [rsp+120h+var_F0]
0x1800172d4  mov     rax, [rcx]
0x1800172d7  mov     edx, esi
0x1800172d9  mov     rax, [rax+38h]
0x1800172dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172e2  mov     edi, eax
0x1800172e4  test    eax, eax
0x1800172e6  jns     short loc_18001730E
0x1800172e8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x1800172ef  jz      loc_180017711
0x1800172f5  lea     rax, aChrPgeolocator; "CHR(pGeolocator->put_DesiredAccuracy(de"...
0x1800172fc  mov     [rsp+120h+var_F8], rax
0x180017301  mov     dword ptr [rsp+120h+var_100], 4Ch ; 'L'
0x180017309  jmp     loc_180017701
0x18001730e  mov     rcx, [rsp+120h+var_F0]
0x180017313  mov     rdx, r15
0x180017316  mov     rax, [rcx]
0x180017319  lea     r9, [rbp+57h+var_A8]
0x18001731d  mov     r8d, 47868C00h
0x180017323  mov     rax, [rax+70h]
0x180017327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001732c  mov     edi, eax
0x18001732e  test    eax, eax
0x180017330  jns     short loc_180017358
0x180017332  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180017339  jz      loc_180017711
0x18001733f  lea     rax, aChrPgeolocator_0; "CHR(pGeolocator->GetGeopositionAsyncWit"...
0x180017346  mov     [rsp+120h+var_F8], rax
0x18001734b  mov     dword ptr [rsp+120h+var_100], 4Dh ; 'M'
0x180017353  jmp     loc_180017701
0x180017358  xor     r9d, r9d; lpName
0x18001735b  xor     r8d, r8d; bInitialState
0x18001735e  xor     edx, edx; bManualReset
0x180017360  xor     ecx, ecx; lpEventAttributes
0x180017362  call    cs:__imp_CreateEventA
0x180017369  nop     dword ptr [rax+rax+00h]
0x18001736e  mov     [rbp+57h+hHandle], rax
0x180017372  test    rax, rax
0x180017375  jnz     short loc_1800173A6
0x180017377  mov     r8d, 80004005h
0x18001737d  mov     edi, r8d
0x180017380  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180017387  jz      loc_180017711
0x18001738d  lea     rax, aCbrHcompleteMH; "CBR(hComplete.m_h != 0)"
0x180017394  mov     [rsp+120h+var_F8], rax
0x180017399  mov     dword ptr [rsp+120h+var_100], 51h ; 'Q'
0x1800173a1  jmp     loc_180017704
0x1800173a6  mov     rcx, [rbp+57h+var_A8]
0x1800173aa  mov     rax, [rcx]
0x1800173ad  mov     rdx, rbx
0x1800173b0  mov     rax, [rax+30h]
0x1800173b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173b9  mov     edi, eax
0x1800173bb  test    eax, eax
0x1800173bd  jns     short loc_1800173E5
0x1800173bf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x1800173c6  jz      loc_180017711
0x1800173cc  lea     rax, aChrPgetoperati; "CHR(pGetOperation->put_Completed(Comple"...
0x1800173d3  mov     [rsp+120h+var_F8], rax
0x1800173d8  mov     dword ptr [rsp+120h+var_100], 52h ; 'R'
0x1800173e0  jmp     loc_180017701
0x1800173e5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800173e8  mov     rcx, [rbp+57h+hHandle]; hHandle
0x1800173ec  call    cs:__imp_WaitForSingleObject
0x1800173f3  nop     dword ptr [rax+rax+00h]
0x1800173f8  test    eax, eax
0x1800173fa  jz      short loc_18001743D
0x1800173fc  call    cs:__imp_GetLastError
0x180017403  nop     dword ptr [rax+rax+00h]
0x180017408  mov     edi, eax
0x18001740a  test    eax, eax
0x18001740c  jle     short loc_180017417
0x18001740e  movzx   edi, ax
0x180017411  or      edi, 80070000h
0x180017417  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x18001741e  jz      loc_180017711
0x180017424  lea     rax, aCbrWaitforsing; "CBR(WaitForSingleObject(hComplete, 0xFF"...
0x18001742b  mov     [rsp+120h+var_F8], rax
0x180017430  mov     dword ptr [rsp+120h+var_100], 55h ; 'U'
0x180017438  jmp     loc_180017701
0x18001743d  mov     edi, [rbp+57h+var_C8]
0x180017440  test    edi, edi
0x180017442  jns     short loc_18001746A
0x180017444  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x18001744b  jz      loc_180017711
0x180017451  lea     rax, aChrHrcallback; "CHR(hrCallback)"
0x180017458  mov     [rsp+120h+var_F8], rax
0x18001745d  mov     dword ptr [rsp+120h+var_100], 56h ; 'V'
0x180017465  jmp     loc_180017701
0x18001746a  cmp     [rbp+57h+var_B8], r15
0x18001746e  jnz     short loc_18001749F
0x180017470  mov     r8d, 80004005h
0x180017476  mov     edi, r8d
0x180017479  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180017480  jz      loc_180017711
0x180017486  lea     rax, aCbrPgeopositio; "CBR(pGeoposition != 0)"
0x18001748d  mov     [rsp+120h+var_F8], rax
0x180017492  mov     dword ptr [rsp+120h+var_100], 57h ; 'W'
0x18001749a  jmp     loc_180017704
0x18001749f  mov     rcx, [rbp+57h+var_B8]
0x1800174a3  mov     rax, [rcx]
0x1800174a6  lea     rdx, [rsp+120h+var_D8]
0x1800174ab  mov     rax, [rax+30h]
0x1800174af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174b4  mov     edi, eax
0x1800174b6  test    eax, eax
0x1800174b8  jns     short loc_1800174E0
0x1800174ba  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x1800174c1  jz      loc_180017711
0x1800174c7  lea     rax, aChrPgeopositio; "CHR(pGeoposition->get_Coordinate(pGeoco"...
0x1800174ce  mov     [rsp+120h+var_F8], rax
0x1800174d3  mov     dword ptr [rsp+120h+var_100], 5Ah ; 'Z'
0x1800174db  jmp     loc_180017701
0x1800174e0  mov     rcx, [rsp+120h+var_D8]
0x1800174e5  mov     rax, [rcx]
0x1800174e8  lea     rdx, [rbp+57h+var_A0]
0x1800174ec  mov     rax, [rax+48h]
0x1800174f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174f5  mov     edi, eax
0x1800174f7  test    eax, eax
0x1800174f9  jns     short loc_180017521
0x1800174fb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180017502  jz      loc_180017711
0x180017508  lea     rax, aChrPgeocoordin; "CHR(pGeocoordinate->get_Accuracy(&dPosi"...
0x18001750f  mov     [rsp+120h+var_F8], rax
0x180017514  mov     dword ptr [rsp+120h+var_100], 5Bh ; '['
0x18001751c  jmp     loc_180017701
0x180017521  mov     rdi, [rsp+120h+var_D8]
0x180017526  mov     rax, [rdi]
0x180017529  mov     rsi, [rax+50h]
0x18001752d  mov     rcx, [rsp+120h+var_E8]
0x180017532  test    rcx, rcx
0x180017535  jz      short loc_180017549
0x180017537  mov     [rsp+120h+var_E8], r15
0x18001753c  mov     rdx, [rcx]
0x18001753f  mov     rax, [rdx+10h]
0x180017543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017548  nop
0x180017549  lea     rdx, [rsp+120h+var_E8]
0x18001754e  mov     rcx, rdi
0x180017551  mov     rax, rsi
0x180017554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017559  mov     edi, eax
0x18001755b  test    eax, eax
0x18001755d  jns     short loc_180017585
0x18001755f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180017566  jz      loc_180017711
0x18001756c  lea     rax, aChrPgeocoordin_1; "CHR(pGeocoordinate->get_AltitudeAccurac"...
0x180017573  mov     [rsp+120h+var_F8], rax
0x180017578  mov     dword ptr [rsp+120h+var_100], 5Ch ; '\'
0x180017580  jmp     loc_180017701
0x180017585  cvttsd2si rax, [rbp+57h+var_A0]
0x18001758b  mov     dword ptr [rbp+57h+var_80+8], eax
0x18001758e  mov     rcx, [rsp+120h+var_E8]
0x180017593  test    rcx, rcx
0x180017596  jz      short loc_1800175B7
0x180017598  mov     dword ptr [rbp+57h+var_80+0Ch], r12d
0x18001759c  mov     rax, [rcx]
0x18001759f  lea     rdx, [rbp+57h+var_98]
0x1800175a3  mov     rax, [rax+30h]
0x1800175a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175ac  cvttsd2si rax, [rbp+57h+var_98]
0x1800175b2  mov     dword ptr [rbp+57h+var_70], eax
0x1800175b5  jmp     short loc_1800175BB
0x1800175b7  mov     dword ptr [rbp+57h+var_80+0Ch], r15d
0x1800175bb  mov     rdi, [rsp+120h+var_D8]
0x1800175c0  mov     rax, [rdi]
0x1800175c3  mov     rsi, [rax]
0x1800175c6  mov     rcx, [rsp+120h+var_E0]
0x1800175cb  test    rcx, rcx
0x1800175ce  jz      short loc_1800175E2
0x1800175d0  mov     [rsp+120h+var_E0], r15
0x1800175d5  mov     rdx, [rcx]
0x1800175d8  mov     rax, [rdx+10h]
0x1800175dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175e1  nop
0x1800175e2  lea     r8, [rsp+120h+var_E0]
0x1800175e7  lea     rdx, _GUID_feea0525_d22c_4d46_b527_0b96066fc7db
0x1800175ee  mov     rcx, rdi
0x1800175f1  mov     rax, rsi
0x1800175f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175f9  mov     edi, eax
0x1800175fb  test    eax, eax
0x1800175fd  jns     short loc_180017625
0x1800175ff  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
  ... truncated ...
```
