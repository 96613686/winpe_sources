# CAvEndpointBuilder::CollectDeviceInformation(IPnpInterface *,ENDPOINT_DESCRIPTOR const *,AUDIO_DEVICE_INFORMATION *)

- ea: `0x180005660`
- end: `0x180005cfe`
- name: `?CollectDeviceInformation@CAvEndpointBuilder@@AEAAJPEAUIPnpInterface@@PEBUENDPOINT_DESCRIPTOR@@PEAUAUDIO_DEVICE_INFORMATION@@@Z`
- size: `1694`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IPnpInterface *, const struct ENDPOINT_DESCRIPTOR *, struct AUDIO_DEVICE_INFORMATION *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800071dc`

## callees

- `0x180005660`
- `0x180005d04`
- `0x180006b0c`
- `0x180010e60`
- `0x180029024`
- `0x1800339a8`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000575b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000577c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000579a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057f3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000575b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000577c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000579a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800059d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800059d5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800056f6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800056f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005a0e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005ab1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005af1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b40`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b70`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005bb0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c89`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005a0e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005ab1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005af1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b40`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005b70`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005bb0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005c89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000574a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000574a`

## pseudocode

```c
__int64 __fastcall CAvEndpointBuilder::CollectDeviceInformation(
        CAvEndpointBuilder *this,
        struct IPnpInterface *a2,
        const struct ENDPOINT_DESCRIPTOR *a3,
        struct AUDIO_DEVICE_INFORMATION *a4)
{
  struct AUDIO_DEVICE_INFORMATION *v4; // r15
  const struct ENDPOINT_DESCRIPTOR *v5; // rsi
  struct IPnpInterface *v6; // r12
  struct AUDIO_DEVICE_INFORMATION *v7; // r14
  int EndpointDescriptorRoot; // eax
  HRESULT v9; // edi
  __int64 v10; // rax
  const wchar_t *v11; // r8
  unsigned __int64 v12; // rdx
  WCHAR *v13; // rcx
  wchar_t v14; // r9
  WCHAR *v15; // rax
  ATL::CAtlException *v17; // rbx
  ATL::CAtlException *v18; // rbx
  ATL::CAtlException *v19; // rbx
  ATL::CAtlException *v20; // rbx
  int v21[4]; // [rsp+40h] [rbp-4D8h] BYREF
  DWORD pcbData[4]; // [rsp+50h] [rbp-4C8h] BYREF
  LPOLESTR lpsz[2]; // [rsp+60h] [rbp-4B8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+70h] [rbp-4A8h] BYREF
  _QWORD *v25; // [rsp+80h] [rbp-498h]
  struct AUDIO_DEVICE_INFORMATION *v26; // [rsp+88h] [rbp-490h]
  struct IPnpInterface *v27; // [rsp+90h] [rbp-488h]
  ATL::CAtlException *v28; // [rsp+A0h] [rbp-478h] BYREF
  ATL::CAtlException *v29; // [rsp+A8h] [rbp-470h] BYREF
  ATL::CAtlException *v30; // [rsp+B0h] [rbp-468h] BYREF
  ATL::CAtlException *v31; // [rsp+B8h] [rbp-460h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-458h] BYREF
  _BYTE pvData[528]; // [rsp+2D0h] [rbp-248h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v27 = a2;
  *(_QWORD *)pcbData = a3;
  v7 = a4;
  v26 = a4;
  *(_OWORD *)lpsz = *(_OWORD *)((char *)a3 + 20);
  EndpointDescriptorRoot = GetEndpointDescriptorRoot(
                             (struct _GUID *)lpsz,
                             (enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011)*((_DWORD *)a3 + 4));
  if ( EndpointDescriptorRoot != -1 )
  {
    *((_DWORD *)v4 + 1) = qword_18006A170[6 * EndpointDescriptorRoot];
    lpsz[0] = 0;
    v9 = StringFromCLSID((const IID *const)((char *)v5 + 20), lpsz);
    if ( v9 < 0 )
    {
LABEL_4:
      CoTaskMemFree(lpsz[0]);
      goto LABEL_70;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v4 + 40, lpsz[0]);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v28) )
      {
        v17 = v28;
        if ( *(_DWORD *)v28 == -1073741571 )
          _o__resetstkoflw();
        v21[0] = *(_DWORD *)v17;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180005723);
        v9 = v21[0];
        if ( v21[0] < 0 )
          goto LABEL_4;
        v5 = *(const struct ENDPOINT_DESCRIPTOR **)pcbData;
        v6 = v27;
        v7 = v26;
        v4 = v26;
      }
    }
    CoTaskMemFree(lpsz[0]);
    if ( (unsigned int)_o__wcsicmp(*((_QWORD *)v5 + 15), L"HDAUDIO") )
    {
      if ( (unsigned int)_o__wcsicmp(*((_QWORD *)v5 + 15), L"USB") )
      {
        if ( (unsigned int)_o__wcsicmp(*((_QWORD *)v5 + 15), L"PCI") )
        {
          if ( (unsigned int)_o__wcsicmp(*((_QWORD *)v5 + 15), L"BTHENUM")
            && (unsigned int)_o__wcsicmp(*((_QWORD *)v5 + 15), L"BTHHFENUM")
            && (unsigned int)_o__wcsicmp(*((_QWORD *)v5 + 15), L"BTHLE") )
          {
            *(_DWORD *)v4 = ((unsigned int)_o__wcsicmp(*((_QWORD *)v5 + 15), L"V1394") != 0) + 4;
          }
          else
          {
            *(_DWORD *)v4 = 3;
          }
        }
        else
        {
          *(_DWORD *)v4 = 0;
        }
      }
      else
      {
        *(_DWORD *)v4 = 2;
      }
    }
    else
    {
      *(_DWORD *)v4 = 1;
    }
    lpsz[0] = 0;
    *(_QWORD *)pcbData = 0;
    v9 = (*(__int64 (__fastcall **)(struct IPnpInterface *, DWORD *))(*(_QWORD *)v6 + 24LL))(v6, pcbData);
    if ( v9 < 0 )
    {
      if ( *(_QWORD *)pcbData )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
      if ( lpsz[0] )
        (*(void (__fastcall **)(LPOLESTR))(*(_QWORD *)lpsz[0] + 16LL))(lpsz[0]);
      goto LABEL_70;
    }
    *(_QWORD *)v21 = 0;
    v9 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, int *))pcbData)(
           *(_QWORD *)pcbData,
           &GUID_d666063f_1587_4e43_81f1_b948e807363f,
           v21);
    if ( v9 < 0
      || (v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPOLESTR *))(**(_QWORD **)v21 + 32LL))(
                 *(_QWORD *)v21,
                 0,
                 lpsz),
          v9 < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(pcbData);
LABEL_69:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(lpsz);
      goto LABEL_70;
    }
    if ( *(_QWORD *)v21 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 16LL))(*(_QWORD *)v21);
    if ( *(_QWORD *)pcbData )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
    *(_OWORD *)pvar = 0;
    v25 = 0;
    v9 = (*(__int64 (__fastcall **)(LPOLESTR, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)lpsz[0] + 40LL))(
           lpsz[0],
           &DEVPKEY_Device_Driver,
           pvar);
    if ( v9 < 0 )
      goto LABEL_68;
    if ( LOWORD(pvar[0]) != 31 )
    {
      v9 = -2147024809;
      goto LABEL_68;
    }
    pcbData[0] = 520;
    v10 = 2147483646;
    v11 = L"SYSTEM\\CurrentControlSet\\Control\\Class\\";
    v12 = 260;
    v13 = SubKey;
    do
    {
      if ( !v10 )
        break;
      v14 = *v11;
      if ( !*v11 )
        break;
      ++v11;
      *v13++ = v14;
      --v10;
      --v12;
    }
    while ( v12 );
    v15 = v13 - 1;
    if ( v12 )
      v15 = v13;
    *v15 = 0;
    StringCbCatW(SubKey, v12, (const unsigned __int16 *)pvar[1]);
    if ( !RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Driver", 2u, 0, pvData, pcbData) )
    {
      if ( __eh34_try(-1, 2) )
      {
        __eh34_scope_strut(2);
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v7 + 8, pvData);
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v29) )
        {
          v18 = v29;
          if ( *(_DWORD *)v29 == -1073741571 )
            _o__resetstkoflw();
          v21[0] = *(_DWORD *)v18;
          __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800059F3);
          v9 = v21[0];
          if ( v21[0] >= 0 )
          {
            v7 = v26;
            goto LABEL_42;
          }
LABEL_68:
          PropVariantClear(pvar);
          goto LABEL_69;
        }
      }
    }
LABEL_42:
    PropVariantClear(pvar);
    *(_OWORD *)pvar = 0;
    v25 = 0;
    v9 = (*(__int64 (__fastcall **)(LPOLESTR, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)lpsz[0] + 40LL))(
           lpsz[0],
           &DEVPKEY_Device_DriverDate,
           pvar);
    if ( v9 >= 0 )
    {
      if ( LOWORD(pvar[0]) == 64 )
      {
        *(_QWORD *)v21 = 0x2B6109100LL;
        *(_QWORD *)pcbData = (__int64)pvar[1] / 10000000 - 0x2B6109100LL;
        *((_DWORD *)v7 + 6) = (__int64)pvar[1] / 10000000 + 1240428288;
        PropVariantClear(pvar);
        *(_OWORD *)pvar = 0;
        v25 = 0;
        v9 = (*(__int64 (__fastcall **)(LPOLESTR, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)lpsz[0] + 40LL))(
               lpsz[0],
               &DEVPKEY_Device_DriverVersion,
               pvar);
        if ( v9 < 0 )
        {
          PropVariantClear(pvar);
          if ( !lpsz[0] )
            goto LABEL_70;
LABEL_65:
          (*(void (__fastcall **)(LPOLESTR))(*(_QWORD *)lpsz[0] + 16LL))(lpsz[0]);
          goto LABEL_70;
        }
        if ( LOWORD(pvar[0]) != 31 )
        {
          v9 = -2147024809;
          PropVariantClear(pvar);
          if ( !lpsz[0] )
            goto LABEL_70;
          goto LABEL_65;
        }
        if ( __eh34_try(-1, 4) )
        {
          __eh34_scope_strut(4);
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v7 + 16, pvar[1]);
        }
        if ( __eh34_catch(4) )
        {
          if ( __eh34_catch_type(4, &ATL::CAtlException `RTTI Type Descriptor', &v30) )
          {
            v19 = v30;
            if ( *(_DWORD *)v30 == -1073741571 )
              _o__resetstkoflw();
            v21[0] = *(_DWORD *)v19;
            __eh34_try_continuation(4, &ATL::CAtlException `RTTI Type Descriptor', &loc_180005B31);
            v9 = v21[0];
            if ( v21[0] < 0 )
            {
              PropVariantClear(pvar);
              if ( !lpsz[0] )
                goto LABEL_70;
              goto LABEL_65;
            }
            v7 = v26;
          }
        }
        PropVariantClear(pvar);
        *(_OWORD *)pvar = 0;
        v25 = 0;
        v9 = (*(__int64 (__fastcall **)(LPOLESTR, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)lpsz[0] + 40LL))(
               lpsz[0],
               &DEVPKEY_Device_HardwareIds,
               pvar);
        if ( v9 < 0 )
        {
          PropVariantClear(pvar);
          if ( !lpsz[0] )
            goto LABEL_70;
          goto LABEL_65;
        }
        if ( LOWORD(pvar[0]) == 4127 && LODWORD(pvar[1]) )
        {
          if ( __eh34_try(-1, 6) )
          {
            __eh34_scope_strut(6);
            v9 = 0;
            ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v7 + 32, *v25);
          }
          if ( __eh34_catch(6) )
          {
            if ( __eh34_catch_type(6, &ATL::CAtlException `RTTI Type Descriptor', &v31) )
            {
              v20 = v31;
              if ( *(_DWORD *)v31 == -1073741571 )
                _o__resetstkoflw();
              v21[0] = *(_DWORD *)v20;
              __eh34_try_continuation(6, &ATL::CAtlException `RTTI Type Descriptor', &loc_180005C17);
              v9 = v21[0];
              if ( v21[0] < 0 )
              {
                PropVariantClear(pvar);
                if ( !lpsz[0] )
                  goto LABEL_70;
                goto LABEL_65;
              }
            }
          }
          PropVariantClear(pvar);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(lpsz);
          return (unsigned int)v9;
        }
        v9 = -2147024809;
      }
      else
      {
        v9 = -2147024809;
      }
    }
    goto LABEL_68;
  }
  v9 = -2147418113;
LABEL_70:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005660  mov     [rsp+arg_0], rbx
0x180005665  push    rsi
0x180005666  push    rdi
0x180005667  push    r12
0x180005669  push    r14
0x18000566b  push    r15
0x18000566d  sub     rsp, 4F0h
0x180005674  mov     rax, cs:__security_cookie
0x18000567b  xor     rax, rsp
0x18000567e  mov     [rsp+518h+var_38], rax
0x180005686  mov     r15, r9
0x180005689  mov     rsi, r8
0x18000568c  mov     r12, rdx
0x18000568f  mov     [rsp+518h+var_488], rdx
0x180005697  mov     qword ptr [rsp+518h+var_4C8], r8
0x18000569c  mov     r14, r9
0x18000569f  mov     [rsp+518h+var_490], r9
0x1800056a7  movups  xmm0, xmmword ptr [r8+14h]
0x1800056ac  movdqu  xmmword ptr [rsp+518h+lpsz], xmm0
0x1800056b2  mov     edx, [r8+10h]; enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011
0x1800056b6  lea     rcx, [rsp+518h+lpsz]; Buf1
0x1800056bb  call    ?GetEndpointDescriptorRoot@@YAHU_GUID@@W4__MIDL___MIDL_itf_devicetopology_0000_0000_0011@@@Z; GetEndpointDescriptorRoot(_GUID,__MIDL___MIDL_itf_devicetopology_0000_0000_0011)
0x1800056c0  cmp     eax, 0FFFFFFFFh
0x1800056c3  jnz     short loc_1800056CF
0x1800056c5  mov     edi, 8000FFFFh
0x1800056ca  jmp     loc_180005C9A
0x1800056cf  cdqe
0x1800056d1  lea     rax, [rax+rax*2]
0x1800056d5  add     rax, rax
0x1800056d8  lea     rcx, qword_18006A170
0x1800056df  mov     eax, [rcx+rax*8]
0x1800056e2  mov     [r15+4], eax
0x1800056e6  xor     ebx, ebx
0x1800056e8  mov     [rsp+518h+lpsz], rbx
0x1800056ed  lea     rdx, [rsp+518h+lpsz]; lplpsz
0x1800056f2  lea     rcx, [rsi+14h]; rclsid
0x1800056f6  call    cs:__imp_StringFromCLSID
0x1800056fc  mov     edi, eax
0x1800056fe  test    eax, eax
0x180005700  jns     short loc_180005712
0x180005702  mov     rcx, [rsp+518h+lpsz]; pv
0x180005707  call    cs:__imp_CoTaskMemFree
0x18000570d  jmp     loc_180005C9A
0x180005712  lea     rcx, [r15+28h]
0x180005716  mov     rdx, [rsp+518h+lpsz]
0x18000571b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180005720  nop
0x180005721  jmp     short loc_180005745
0x180005723  mov     edi, [rsp+518h+var_4D8]
0x180005727  xor     ebx, ebx
0x180005729  test    edi, edi
0x18000572b  js      short loc_180005702
0x18000572d  mov     rsi, qword ptr [rsp+518h+var_4C8]
0x180005732  mov     r12, [rsp+518h+var_488]
0x18000573a  mov     r14, [rsp+518h+var_490]
0x180005742  mov     r15, r14
0x180005745  mov     rcx, [rsp+518h+lpsz]; pv
0x18000574a  call    cs:__imp_CoTaskMemFree
0x180005750  lea     rdx, aHdaudio; "HDAUDIO"
0x180005757  mov     rcx, [rsi+78h]
0x18000575b  call    cs:__imp__o__wcsicmp
0x180005761  test    eax, eax
0x180005763  jnz     short loc_180005771
0x180005765  mov     dword ptr [r15], 1
0x18000576c  jmp     loc_18000580E
0x180005771  lea     rdx, Enumerator; "USB"
0x180005778  mov     rcx, [rsi+78h]
0x18000577c  call    cs:__imp__o__wcsicmp
0x180005782  test    eax, eax
0x180005784  jnz     short loc_18000578F
0x180005786  mov     dword ptr [r15], 2
0x18000578d  jmp     short loc_18000580E
0x18000578f  lea     rdx, aPci; "PCI"
0x180005796  mov     rcx, [rsi+78h]
0x18000579a  call    cs:__imp__o__wcsicmp
0x1800057a0  test    eax, eax
0x1800057a2  jnz     short loc_1800057A9
0x1800057a4  mov     [r15], ebx
0x1800057a7  jmp     short loc_18000580E
0x1800057a9  lea     rdx, aBthenum; "BTHENUM"
0x1800057b0  mov     rcx, [rsi+78h]
0x1800057b4  call    cs:__imp__o__wcsicmp
0x1800057ba  test    eax, eax
0x1800057bc  jz      short loc_180005807
0x1800057be  lea     rdx, aBthhfenum; "BTHHFENUM"
0x1800057c5  mov     rcx, [rsi+78h]
0x1800057c9  call    cs:__imp__o__wcsicmp
0x1800057cf  test    eax, eax
0x1800057d1  jz      short loc_180005807
0x1800057d3  lea     rdx, aBthle; "BTHLE"
0x1800057da  mov     rcx, [rsi+78h]
0x1800057de  call    cs:__imp__o__wcsicmp
0x1800057e4  test    eax, eax
0x1800057e6  jz      short loc_180005807
0x1800057e8  lea     rdx, aV1394; "V1394"
0x1800057ef  mov     rcx, [rsi+78h]
0x1800057f3  call    cs:__imp__o__wcsicmp
0x1800057f9  neg     eax
0x1800057fb  sbb     ecx, ecx
0x1800057fd  neg     ecx
0x1800057ff  add     ecx, 4
0x180005802  mov     [r15], ecx
0x180005805  jmp     short loc_18000580E
0x180005807  mov     dword ptr [r15], 3
0x18000580e  mov     [rsp+518h+lpsz], rbx
0x180005813  mov     qword ptr [rsp+518h+var_4C8], rbx
0x180005818  mov     rax, [r12]
0x18000581c  lea     rdx, [rsp+518h+var_4C8]
0x180005821  mov     rcx, r12
0x180005824  mov     rax, [rax+18h]
0x180005828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582d  mov     edi, eax
0x18000582f  test    eax, eax
0x180005831  jns     short loc_180005866
0x180005833  mov     rcx, qword ptr [rsp+518h+var_4C8]
0x180005838  test    rcx, rcx
0x18000583b  jz      short loc_18000584A
0x18000583d  mov     rax, [rcx]
0x180005840  mov     rax, [rax+10h]
0x180005844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005849  nop
0x18000584a  mov     rcx, [rsp+518h+lpsz]
0x18000584f  test    rcx, rcx
0x180005852  jz      short loc_180005861
0x180005854  mov     rax, [rcx]
0x180005857  mov     rax, [rax+10h]
0x18000585b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005860  nop
0x180005861  jmp     loc_180005C9A
0x180005866  mov     qword ptr [rsp+518h+var_4D8], rbx
0x18000586b  mov     rcx, qword ptr [rsp+518h+var_4C8]
0x180005870  mov     rax, [rcx]
0x180005873  lea     r8, [rsp+518h+var_4D8]
0x180005878  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x18000587f  mov     rax, [rax]
0x180005882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005887  mov     edi, eax
0x180005889  test    eax, eax
0x18000588b  jns     short loc_1800058A7
0x18000588d  lea     rcx, [rsp+518h+var_4D8]
0x180005892  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005897  nop
0x180005898  lea     rcx, [rsp+518h+var_4C8]
0x18000589d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800058a2  jmp     loc_180005C90
0x1800058a7  mov     rcx, qword ptr [rsp+518h+var_4D8]
0x1800058ac  mov     rax, [rcx]
0x1800058af  lea     r8, [rsp+518h+lpsz]
0x1800058b4  xor     edx, edx
0x1800058b6  mov     rax, [rax+20h]
0x1800058ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058bf  mov     edi, eax
0x1800058c1  test    eax, eax
0x1800058c3  js      short loc_18000588D
0x1800058c5  mov     rcx, qword ptr [rsp+518h+var_4D8]
0x1800058ca  test    rcx, rcx
0x1800058cd  jz      short loc_1800058DC
0x1800058cf  mov     rax, [rcx]
0x1800058d2  mov     rax, [rax+10h]
0x1800058d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058db  nop
0x1800058dc  mov     rcx, qword ptr [rsp+518h+var_4C8]
0x1800058e1  test    rcx, rcx
0x1800058e4  jz      short loc_1800058F3
0x1800058e6  mov     rax, [rcx]
0x1800058e9  mov     rax, [rax+10h]
0x1800058ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f2  nop
0x1800058f3  xorps   xmm0, xmm0
0x1800058f6  xor     eax, eax
0x1800058f8  movups  xmmword ptr [rsp+518h+pvar], xmm0
0x1800058fd  mov     [rsp+518h+var_498], rax
0x180005905  mov     rcx, [rsp+518h+lpsz]
0x18000590a  mov     rax, [rcx]
0x18000590d  lea     r8, [rsp+518h+pvar]
0x180005912  lea     rdx, DEVPKEY_Device_Driver
0x180005919  mov     rax, [rax+28h]
0x18000591d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005922  mov     edi, eax
0x180005924  test    eax, eax
0x180005926  js      loc_180005C84
0x18000592c  cmp     word ptr [rsp+518h+pvar], 1Fh
0x180005932  jnz     loc_180005C7F
0x180005938  mov     [rsp+518h+var_4C8], 208h
0x180005940  mov     eax, 7FFFFFFEh
0x180005945  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cla"...
0x18000594c  mov     edx, 104h
0x180005951  lea     rcx, [rsp+518h+SubKey]
0x180005959  test    rax, rax
0x18000595c  jz      short loc_18000597D
0x18000595e  movzx   r9d, word ptr [r8]
0x180005962  test    r9w, r9w
0x180005966  jz      short loc_18000597D
0x180005968  add     r8, 2
0x18000596c  mov     [rcx], r9w
0x180005970  add     rcx, 2
0x180005974  dec     rax
0x180005977  sub     rdx, 1; unsigned __int64
0x18000597b  jnz     short loc_180005959
0x18000597d  lea     rax, [rcx-2]
0x180005981  test    rdx, rdx
0x180005984  cmovnz  rax, rcx
0x180005988  mov     [rax], bx
0x18000598b  mov     r8, [rsp+518h+pvar+8]; unsigned __int16 *
0x180005990  lea     rcx, [rsp+518h+SubKey]; unsigned __int16 *
0x180005998  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000599d  lea     rax, [rsp+518h+var_4C8]
0x1800059a2  mov     [rsp+518h+pcbData], rax; pcbData
0x1800059a7  lea     rax, [rsp+518h+var_248]
0x1800059af  mov     [rsp+518h+pvData], rax; pvData
0x1800059b4  mov     [rsp+518h+pdwType], rbx; pdwType
0x1800059b9  mov     r9d, 2; dwFlags
0x1800059bf  lea     r8, Value; "Driver"
0x1800059c6  lea     rdx, [rsp+518h+SubKey]; lpSubKey
0x1800059ce  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800059d5  call    cs:__imp_RegGetValueW
0x1800059db  test    eax, eax
0x1800059dd  jnz     short loc_180005A09
0x1800059df  lea     rcx, [r14+8]
0x1800059e3  lea     rdx, [rsp+518h+var_248]
0x1800059eb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800059f0  nop
0x1800059f1  jmp     short loc_180005A09
0x1800059f3  mov     edi, [rsp+518h+var_4D8]
0x1800059f7  xor     ebx, ebx
0x1800059f9  test    edi, edi
0x1800059fb  js      loc_180005C84
0x180005a01  mov     r14, [rsp+518h+var_490]
0x180005a09  lea     rcx, [rsp+518h+pvar]; pvar
0x180005a0e  call    cs:__imp_PropVariantClear
0x180005a14  xorps   xmm0, xmm0
0x180005a17  xor     eax, eax
0x180005a19  movups  xmmword ptr [rsp+518h+pvar], xmm0
0x180005a1e  mov     [rsp+518h+var_498], rax
0x180005a26  mov     rcx, [rsp+518h+lpsz]
0x180005a2b  mov     rax, [rcx]
0x180005a2e  lea     r8, [rsp+518h+pvar]
0x180005a33  lea     rdx, DEVPKEY_Device_DriverDate
0x180005a3a  mov     rax, [rax+28h]
0x180005a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a43  mov     edi, eax
0x180005a45  test    eax, eax
0x180005a47  jns     short loc_180005A4E
0x180005a49  jmp     loc_180005C84
0x180005a4e  cmp     word ptr [rsp+518h+pvar], 40h ; '@'
0x180005a54  jnz     loc_180005C75
0x180005a5a  mov     [rsp+518h+var_4D8], 0B6109100h
0x180005a62  mov     [rsp+518h+var_4D8+4], 2
0x180005a6a  mov     eax, dword ptr [rsp+518h+pvar+0Ch]
0x180005a6e  mov     [rsp+518h+var_4C8+4], eax
0x180005a72  mov     eax, dword ptr [rsp+518h+pvar+8]
0x180005a76  mov     [rsp+518h+var_4C8], eax
0x180005a7a  mov     rax, 0D6BF94D5E57A42BDh
0x180005a84  imul    qword ptr [rsp+518h+var_4C8]
0x180005a89  add     rdx, qword ptr [rsp+518h+var_4C8]
0x180005a8e  sar     rdx, 17h
0x180005a92  mov     rax, rdx
0x180005a95  shr     rax, 3Fh
0x180005a99  add     rdx, rax
0x180005a9c  sub     rdx, qword ptr [rsp+518h+var_4D8]
0x180005aa1  mov     qword ptr [rsp+518h+var_4C8], rdx
0x180005aa6  mov     eax, edx
0x180005aa8  mov     [r14+18h], edx
0x180005aac  lea     rcx, [rsp+518h+pvar]; pvar
0x180005ab1  call    cs:__imp_PropVariantClear
0x180005ab7  xorps   xmm0, xmm0
0x180005aba  xor     eax, eax
0x180005abc  movups  xmmword ptr [rsp+518h+pvar], xmm0
0x180005ac1  mov     [rsp+518h+var_498], rax
0x180005ac9  mov     rcx, [rsp+518h+lpsz]
0x180005ace  mov     rax, [rcx]
0x180005ad1  lea     r8, [rsp+518h+pvar]
0x180005ad6  lea     rdx, DEVPKEY_Device_DriverVersion
0x180005add  mov     rax, [rax+28h]
0x180005ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae6  mov     edi, eax
0x180005ae8  test    eax, eax
0x180005aea  jns     short loc_180005B14
0x180005aec  lea     rcx, [rsp+518h+pvar]; pvar
0x180005af1  call    cs:__imp_PropVariantClear
0x180005af7  nop
0x180005af8  mov     rcx, [rsp+518h+lpsz]
0x180005afd  test    rcx, rcx
0x180005b00  jz      short loc_180005B0F
0x180005b02  mov     rax, [rcx]
0x180005b05  mov     rax, [rax+10h]
0x180005b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0e  nop
0x180005b0f  jmp     loc_180005C9A
0x180005b14  cmp     word ptr [rsp+518h+pvar], 1Fh
0x180005b1a  jnz     loc_180005C4B
0x180005b20  lea     rcx, [r14+10h]
0x180005b24  mov     rdx, [rsp+518h+pvar+8]
0x180005b29  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180005b2e  nop
0x180005b2f  jmp     short loc_180005B6B
0x180005b31  mov     edi, [rsp+518h+var_4D8]
0x180005b35  xor     ebx, ebx
0x180005b37  test    edi, edi
0x180005b39  jns     short loc_180005B63
  ... truncated ...
```
