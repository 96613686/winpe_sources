# CEndpointCharacteristicsCache::PopulateEndpointCharacteristicsCache(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180008910`
- end: `0x180008d5c`
- name: `?PopulateEndpointCharacteristicsCache@CEndpointCharacteristicsCache@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1100`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008910`
- `0x1800097c0`
- `0x18000accc`
- `0x18000af70`
- `0x180018198`
- `0x18013da34`
- `0x180147a20`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008d1a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008d1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ca5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000892c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000892c`
- `ext-ms-win-audiocore-pal-l1-2-0!PerformEndpointDiscoveryForUnpluggedEndpoints` at `0x180008bc1`
- `ext-ms-win-audiocore-pal-l1-2-0!PerformEndpointDiscoveryForUnpluggedEndpoints` at `0x180008bc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall CEndpointCharacteristicsCache::PopulateEndpointCharacteristicsCache(
        PTP_CALLBACK_INSTANCE Instance,
        _BYTE *Context,
        PTP_WORK Work)
{
  int v4; // eax
  unsigned int i; // edi
  _QWORD *v6; // rbx
  _QWORD *v7; // rdi
  __int64 v8; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v9; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *v11; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v12; // [rsp+50h] [rbp-10h]
  __int64 v13; // [rsp+58h] [rbp-8h]
  LPVOID v14; // [rsp+88h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+38h] BYREF

  if ( CoInitializeEx(0, 0) >= 0 )
  {
    std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(&v11);
    if ( !Context[104] )
    {
      v8 = 0;
      if ( ((int (__fastcall *)(struct IMMDeviceEnumerator *, _QWORD, _QWORD, __int64 *))g_DeviceEnumerator->lpVtbl->GetDefaultAudioEndpoint)(
             g_DeviceEnumerator,
             0,
             0,
             &v8) >= 0 )
      {
        pv = 0;
        if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 40LL))(v8, &pv) >= 0 )
        {
          v14 = 0;
          (*(void (__fastcall **)(_BYTE *, LPVOID, _QWORD, __int64, LPVOID *))(*(_QWORD *)Context + 24LL))(
            Context,
            pv,
            0,
            1,
            &v14);
          if ( v14 )
            std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(
              &v11,
              &v14);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v14);
        }
        CoTaskMemFree(pv);
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v8);
      if ( !Context[104] )
      {
        pv = 0;
        if ( ((int (__fastcall *)(struct IMMDeviceEnumerator *, __int64, _QWORD, LPVOID *))g_DeviceEnumerator->lpVtbl->GetDefaultAudioEndpoint)(
               g_DeviceEnumerator,
               1,
               0,
               &pv) >= 0 )
        {
          v14 = 0;
          if ( (*(int (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)pv + 40LL))(pv, &v14) >= 0 )
          {
            v10 = 0;
            (*(void (__fastcall **)(_BYTE *, LPVOID, _QWORD, __int64, __int64 *))(*(_QWORD *)Context + 24LL))(
              Context,
              v14,
              0,
              1,
              &v10);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v10);
          }
          CoTaskMemFree(v14);
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pv);
      }
    }
    if ( !Context[104] )
    {
      v8 = 0;
      if ( ((int (__fastcall *)(struct IMMDeviceEnumerator *, _QWORD, __int64, __int64 *))g_DeviceEnumerator->lpVtbl->GetDefaultAudioEndpoint)(
             g_DeviceEnumerator,
             0,
             2,
             &v8) >= 0 )
      {
        pv = 0;
        if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 40LL))(v8, &pv) >= 0 )
        {
          v14 = 0;
          (*(void (__fastcall **)(_BYTE *, LPVOID, _QWORD, __int64, LPVOID *))(*(_QWORD *)Context + 24LL))(
            Context,
            pv,
            0,
            1,
            &v14);
          if ( v14 )
            std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(
              &v11,
              &v14);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v14);
        }
        CoTaskMemFree(pv);
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v8);
      if ( !Context[104] )
      {
        pv = 0;
        if ( ((int (__fastcall *)(struct IMMDeviceEnumerator *, __int64, __int64, LPVOID *))g_DeviceEnumerator->lpVtbl->GetDefaultAudioEndpoint)(
               g_DeviceEnumerator,
               1,
               2,
               &pv) >= 0 )
        {
          v14 = 0;
          if ( (*(int (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)pv + 40LL))(pv, &v14) >= 0 )
          {
            v10 = 0;
            (*(void (__fastcall **)(_BYTE *, LPVOID, _QWORD, __int64, __int64 *))(*(_QWORD *)Context + 24LL))(
              Context,
              v14,
              0,
              1,
              &v10);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v10);
          }
          CoTaskMemFree(v14);
        }
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pv);
        if ( !Context[104] )
        {
          v8 = 0;
          v4 = PerformEndpointDiscoveryForUnpluggedEndpoints();
          LODWORD(v14) = 0;
          if ( ((int (__fastcall *)(struct IMMDeviceEnumerator *, __int64, _QWORD, __int64 *))g_DeviceEnumerator->lpVtbl->EnumAudioEndpoints)(
                 g_DeviceEnumerator,
                 2,
                 v4 != 0 ? 9 : 1,
                 &v8) >= 0
            && (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 24LL))(v8, &v14) >= 0 )
          {
            for ( i = 0; !Context[104] && i < (unsigned int)v14; ++i )
            {
              v10 = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 32LL))(v8, i, &v10) >= 0 )
              {
                v9 = 0;
                if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 40LL))(v10, &v9) >= 0 )
                {
                  pv = 0;
                  (*(void (__fastcall **)(_BYTE *, LPVOID, _QWORD, __int64, LPVOID *))(*(_QWORD *)Context + 24LL))(
                    Context,
                    v9,
                    0,
                    1,
                    &pv);
                  if ( pv )
                    std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(
                      &v11,
                      &pv);
                  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&pv);
                }
                CoTaskMemFree(v9);
              }
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            }
          }
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
    }
    v6 = v11;
    v7 = v12;
    while ( v6 != v7 )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 56LL))(*v6) )
        CSpatialProperties::EnsureSpatialSettingsAreInitialized((LPCRITICAL_SECTION)(*v6 + 448LL));
      ++v6;
    }
    CoUninitialize();
    if ( v11 )
    {
      std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(v11, v12);
      std::_Deallocate<16>(v11, (v13 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFF8uLL);
    }
  }
}

```

## disassembly

```asm
0x180008910  mov     [rsp-18h+arg_0], rbx
0x180008915  mov     [rsp-18h+arg_10], rsi
0x18000891a  push    rbp
0x18000891b  push    rdi
0x18000891c  push    r14
0x18000891e  mov     rbp, rsp
0x180008921  sub     rsp, 60h
0x180008925  mov     rbx, rdx
0x180008928  xor     edx, edx; dwCoInit
0x18000892a  xor     ecx, ecx; pvReserved
0x18000892c  call    cs:__imp_CoInitializeEx
0x180008932  xor     esi, esi
0x180008934  test    eax, eax
0x180008936  js      loc_180008D47
0x18000893c  lea     rcx, [rbp+var_18]; void *
0x180008940  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x180008945  nop
0x180008946  lea     r14d, [rsi+1]
0x18000894a  cmp     [rbx+68h], sil
0x18000894e  jnz     loc_180008A7C
0x180008954  mov     [rbp+var_30], rsi
0x180008958  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18000895f  mov     rax, [rcx]
0x180008962  lea     r9, [rbp+var_30]
0x180008966  xor     r8d, r8d
0x180008969  xor     edx, edx
0x18000896b  mov     rax, [rax+20h]
0x18000896f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008974  test    eax, eax
0x180008976  js      short loc_1800089E3
0x180008978  mov     [rbp+pv], rsi
0x18000897c  mov     rcx, [rbp+var_30]
0x180008980  mov     rax, [rcx]
0x180008983  lea     rdx, [rbp+pv]
0x180008987  mov     rax, [rax+28h]
0x18000898b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008990  test    eax, eax
0x180008992  js      short loc_1800089D8
0x180008994  mov     [rbp+arg_8], rsi
0x180008998  mov     rax, [rbx]
0x18000899b  lea     rcx, [rbp+arg_8]
0x18000899f  mov     [rsp+60h+var_40], rcx
0x1800089a4  mov     r9d, r14d
0x1800089a7  xor     r8d, r8d
0x1800089aa  mov     rdx, [rbp+pv]
0x1800089ae  mov     rcx, rbx
0x1800089b1  mov     rax, [rax+18h]
0x1800089b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ba  cmp     [rbp+arg_8], rsi
0x1800089be  jz      short loc_1800089CE
0x1800089c0  lea     rdx, [rbp+arg_8]
0x1800089c4  lea     rcx, [rbp+var_18]
0x1800089c8  call    ??$emplace_back@AEAPEAVCEndpointCharacteristics@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAAEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@AEAPEAVCEndpointCharacteristics@@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(CEndpointCharacteristics * &)
0x1800089cd  nop
0x1800089ce  lea     rcx, [rbp+arg_8]
0x1800089d2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800089d7  nop
0x1800089d8  mov     rcx, [rbp+pv]; pv
0x1800089dc  call    cs:__imp_CoTaskMemFree
0x1800089e2  nop
0x1800089e3  lea     rcx, [rbp+var_30]
0x1800089e7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800089ec  cmp     [rbx+68h], sil
0x1800089f0  jnz     loc_180008A7C
0x1800089f6  mov     [rbp+pv], rsi
0x1800089fa  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008a01  mov     rax, [rcx]
0x180008a04  lea     r9, [rbp+pv]
0x180008a08  xor     r8d, r8d
0x180008a0b  mov     edx, r14d
0x180008a0e  mov     rax, [rax+20h]
0x180008a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a17  test    eax, eax
0x180008a19  js      short loc_180008A73
0x180008a1b  mov     [rbp+arg_8], rsi
0x180008a1f  mov     rcx, [rbp+pv]
0x180008a23  mov     rax, [rcx]
0x180008a26  lea     rdx, [rbp+arg_8]
0x180008a2a  mov     rax, [rax+28h]
0x180008a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a33  test    eax, eax
0x180008a35  js      short loc_180008A68
0x180008a37  mov     [rbp+var_20], rsi
0x180008a3b  mov     rax, [rbx]
0x180008a3e  lea     rcx, [rbp+var_20]
0x180008a42  mov     [rsp+60h+var_40], rcx
0x180008a47  mov     r9d, r14d
0x180008a4a  xor     r8d, r8d
0x180008a4d  mov     rdx, [rbp+arg_8]
0x180008a51  mov     rcx, rbx
0x180008a54  mov     rax, [rax+18h]
0x180008a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a5d  nop
0x180008a5e  lea     rcx, [rbp+var_20]
0x180008a62  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008a67  nop
0x180008a68  mov     rcx, [rbp+arg_8]; pv
0x180008a6c  call    cs:__imp_CoTaskMemFree
0x180008a72  nop
0x180008a73  lea     rcx, [rbp+pv]
0x180008a77  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008a7c  mov     edi, 2
0x180008a81  cmp     [rbx+68h], sil
0x180008a85  jnz     loc_180008CE5
0x180008a8b  mov     [rbp+var_30], rsi
0x180008a8f  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008a96  mov     rax, [rcx]
0x180008a99  lea     r9, [rbp+var_30]
0x180008a9d  mov     r8d, edi
0x180008aa0  xor     edx, edx
0x180008aa2  mov     rax, [rax+20h]
0x180008aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aab  test    eax, eax
0x180008aad  js      short loc_180008B1A
0x180008aaf  mov     [rbp+pv], rsi
0x180008ab3  mov     rcx, [rbp+var_30]
0x180008ab7  mov     rax, [rcx]
0x180008aba  lea     rdx, [rbp+pv]
0x180008abe  mov     rax, [rax+28h]
0x180008ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac7  test    eax, eax
0x180008ac9  js      short loc_180008B0F
0x180008acb  mov     [rbp+arg_8], rsi
0x180008acf  mov     rax, [rbx]
0x180008ad2  lea     rcx, [rbp+arg_8]
0x180008ad6  mov     [rsp+60h+var_40], rcx
0x180008adb  mov     r9d, r14d
0x180008ade  xor     r8d, r8d
0x180008ae1  mov     rdx, [rbp+pv]
0x180008ae5  mov     rcx, rbx
0x180008ae8  mov     rax, [rax+18h]
0x180008aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af1  cmp     [rbp+arg_8], rsi
0x180008af5  jz      short loc_180008B05
0x180008af7  lea     rdx, [rbp+arg_8]
0x180008afb  lea     rcx, [rbp+var_18]
0x180008aff  call    ??$emplace_back@AEAPEAVCEndpointCharacteristics@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAAEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@AEAPEAVCEndpointCharacteristics@@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(CEndpointCharacteristics * &)
0x180008b04  nop
0x180008b05  lea     rcx, [rbp+arg_8]
0x180008b09  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008b0e  nop
0x180008b0f  mov     rcx, [rbp+pv]; pv
0x180008b13  call    cs:__imp_CoTaskMemFree
0x180008b19  nop
0x180008b1a  lea     rcx, [rbp+var_30]
0x180008b1e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008b23  cmp     [rbx+68h], sil
0x180008b27  jnz     loc_180008CE5
0x180008b2d  mov     [rbp+pv], rsi
0x180008b31  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008b38  mov     rax, [rcx]
0x180008b3b  lea     r9, [rbp+pv]
0x180008b3f  mov     r8d, edi
0x180008b42  mov     edx, r14d
0x180008b45  mov     rax, [rax+20h]
0x180008b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4e  test    eax, eax
0x180008b50  js      short loc_180008BAA
0x180008b52  mov     [rbp+arg_8], rsi
0x180008b56  mov     rcx, [rbp+pv]
0x180008b5a  mov     rax, [rcx]
0x180008b5d  lea     rdx, [rbp+arg_8]
0x180008b61  mov     rax, [rax+28h]
0x180008b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6a  test    eax, eax
0x180008b6c  js      short loc_180008B9F
0x180008b6e  mov     [rbp+var_20], rsi
0x180008b72  mov     rax, [rbx]
0x180008b75  lea     rcx, [rbp+var_20]
0x180008b79  mov     [rsp+60h+var_40], rcx
0x180008b7e  mov     r9d, r14d
0x180008b81  xor     r8d, r8d
0x180008b84  mov     rdx, [rbp+arg_8]
0x180008b88  mov     rcx, rbx
0x180008b8b  mov     rax, [rax+18h]
0x180008b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b94  nop
0x180008b95  lea     rcx, [rbp+var_20]
0x180008b99  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008b9e  nop
0x180008b9f  mov     rcx, [rbp+arg_8]; pv
0x180008ba3  call    cs:__imp_CoTaskMemFree
0x180008ba9  nop
0x180008baa  lea     rcx, [rbp+pv]
0x180008bae  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008bb3  cmp     [rbx+68h], sil
0x180008bb7  jnz     loc_180008CE5
0x180008bbd  mov     [rbp+var_30], rsi
0x180008bc1  call    cs:__imp_PerformEndpointDiscoveryForUnpluggedEndpoints
0x180008bc7  neg     eax
0x180008bc9  sbb     r8d, r8d
0x180008bcc  and     r8d, 8
0x180008bd0  add     r8d, r14d
0x180008bd3  mov     dword ptr [rbp+arg_8], esi
0x180008bd6  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008bdd  mov     rax, [rcx]
0x180008be0  lea     r9, [rbp+var_30]
0x180008be4  mov     edx, edi
0x180008be6  mov     rax, [rax+18h]
0x180008bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bef  test    eax, eax
0x180008bf1  js      loc_180008CCF
0x180008bf7  mov     rcx, [rbp+var_30]
0x180008bfb  mov     rax, [rcx]
0x180008bfe  lea     rdx, [rbp+arg_8]
0x180008c02  mov     rax, [rax+18h]
0x180008c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c0b  test    eax, eax
0x180008c0d  js      loc_180008CCF
0x180008c13  mov     edi, esi
0x180008c15  jmp     loc_180008CC5
0x180008c1a  cmp     edi, dword ptr [rbp+arg_8]
0x180008c1d  jnb     loc_180008CCF
0x180008c23  mov     [rbp+var_20], rsi
0x180008c27  mov     rcx, [rbp+var_30]
0x180008c2b  mov     rax, [rcx]
0x180008c2e  lea     r8, [rbp+var_20]
0x180008c32  mov     edx, edi
0x180008c34  mov     rax, [rax+20h]
0x180008c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3d  test    eax, eax
0x180008c3f  js      short loc_180008CAC
0x180008c41  mov     [rbp+var_28], rsi
0x180008c45  mov     rcx, [rbp+var_20]
0x180008c49  mov     rax, [rcx]
0x180008c4c  lea     rdx, [rbp+var_28]
0x180008c50  mov     rax, [rax+28h]
0x180008c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c59  test    eax, eax
0x180008c5b  js      short loc_180008CA1
0x180008c5d  mov     [rbp+pv], rsi
0x180008c61  mov     rax, [rbx]
0x180008c64  lea     rcx, [rbp+pv]
0x180008c68  mov     [rsp+60h+var_40], rcx
0x180008c6d  mov     r9d, r14d
0x180008c70  xor     r8d, r8d
0x180008c73  mov     rdx, [rbp+var_28]
0x180008c77  mov     rcx, rbx
0x180008c7a  mov     rax, [rax+18h]
0x180008c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c83  cmp     [rbp+pv], rsi
0x180008c87  jz      short loc_180008C97
0x180008c89  lea     rdx, [rbp+pv]
0x180008c8d  lea     rcx, [rbp+var_18]
0x180008c91  call    ??$emplace_back@AEAPEAVCEndpointCharacteristics@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAAEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@AEAPEAVCEndpointCharacteristics@@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(CEndpointCharacteristics * &)
0x180008c96  nop
0x180008c97  lea     rcx, [rbp+pv]
0x180008c9b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008ca0  nop
0x180008ca1  mov     rcx, [rbp+var_28]; pv
0x180008ca5  call    cs:__imp_CoTaskMemFree
0x180008cab  nop
0x180008cac  mov     rcx, [rbp+var_20]
0x180008cb0  test    rcx, rcx
0x180008cb3  jz      short loc_180008CC2
0x180008cb5  mov     rax, [rcx]
0x180008cb8  mov     rax, [rax+10h]
0x180008cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc1  nop
0x180008cc2  add     edi, r14d
0x180008cc5  cmp     [rbx+68h], sil
0x180008cc9  jz      loc_180008C1A
0x180008ccf  mov     rcx, [rbp+var_30]
0x180008cd3  test    rcx, rcx
0x180008cd6  jz      short loc_180008CE5
0x180008cd8  mov     rax, [rcx]
0x180008cdb  mov     rax, [rax+10h]
0x180008cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce4  nop
0x180008ce5  mov     rbx, [rbp+var_18]
0x180008ce9  mov     rdi, [rbp+var_10]
0x180008ced  jmp     short loc_180008D15
0x180008cef  mov     rcx, [rbx]
0x180008cf2  mov     rax, [rcx]
0x180008cf5  mov     rax, [rax+38h]
0x180008cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfe  test    eax, eax
0x180008d00  jnz     short loc_180008D11
0x180008d02  mov     rcx, [rbx]
0x180008d05  add     rcx, 1C0h; lpCriticalSection
0x180008d0c  call    ?EnsureSpatialSettingsAreInitialized@CSpatialProperties@@QEAAXXZ; CSpatialProperties::EnsureSpatialSettingsAreInitialized(void)
0x180008d11  add     rbx, 8
0x180008d15  cmp     rbx, rdi
0x180008d18  jnz     short loc_180008CEF
0x180008d1a  call    cs:__imp_CoUninitialize
0x180008d20  nop
0x180008d21  mov     rcx, [rbp+var_18]
0x180008d25  test    rcx, rcx
0x180008d28  jz      short loc_180008D47
0x180008d2a  mov     rdx, [rbp+var_10]
0x180008d2e  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>> &)
0x180008d33  mov     rcx, [rbp+var_18]
0x180008d37  mov     rdx, [rbp+var_8]
0x180008d3b  sub     rdx, rcx
0x180008d3e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180008d42  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008d47  lea     r11, [rsp+60h+var_s0]
0x180008d4c  mov     rbx, [r11+20h]
0x180008d50  mov     rsi, [r11+30h]
0x180008d54  mov     rsp, r11
  ... truncated ...
```
