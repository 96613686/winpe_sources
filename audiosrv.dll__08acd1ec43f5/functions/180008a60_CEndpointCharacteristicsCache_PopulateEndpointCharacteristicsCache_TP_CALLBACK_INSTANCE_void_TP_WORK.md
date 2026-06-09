# CEndpointCharacteristicsCache::PopulateEndpointCharacteristicsCache(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180008a60`
- end: `0x180008eac`
- name: `?PopulateEndpointCharacteristicsCache@CEndpointCharacteristicsCache@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1100`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008a60`
- `0x180009910`
- `0x18000ae1c`
- `0x18000b0c0`
- `0x1800182e8`
- `0x18013dd24`
- `0x180148730`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008a7c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008df5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008df5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008e6a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008e6a`
- `ext-ms-win-audiocore-pal-l1-2-0!PerformEndpointDiscoveryForUnpluggedEndpoints` at `0x180008d11`
- `ext-ms-win-audiocore-pal-l1-2-0!PerformEndpointDiscoveryForUnpluggedEndpoints` at `0x180008d11`

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
0x180008a60  mov     [rsp-18h+arg_0], rbx
0x180008a65  mov     [rsp-18h+arg_10], rsi
0x180008a6a  push    rbp
0x180008a6b  push    rdi
0x180008a6c  push    r14
0x180008a6e  mov     rbp, rsp
0x180008a71  sub     rsp, 60h
0x180008a75  mov     rbx, rdx
0x180008a78  xor     edx, edx; dwCoInit
0x180008a7a  xor     ecx, ecx; pvReserved
0x180008a7c  call    cs:__imp_CoInitializeEx
0x180008a82  xor     esi, esi
0x180008a84  test    eax, eax
0x180008a86  js      loc_180008E97
0x180008a8c  lea     rcx, [rbp+var_18]; void *
0x180008a90  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x180008a95  nop
0x180008a96  lea     r14d, [rsi+1]
0x180008a9a  cmp     [rbx+68h], sil
0x180008a9e  jnz     loc_180008BCC
0x180008aa4  mov     [rbp+var_30], rsi
0x180008aa8  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008aaf  mov     rax, [rcx]
0x180008ab2  lea     r9, [rbp+var_30]
0x180008ab6  xor     r8d, r8d
0x180008ab9  xor     edx, edx
0x180008abb  mov     rax, [rax+20h]
0x180008abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac4  test    eax, eax
0x180008ac6  js      short loc_180008B33
0x180008ac8  mov     [rbp+pv], rsi
0x180008acc  mov     rcx, [rbp+var_30]
0x180008ad0  mov     rax, [rcx]
0x180008ad3  lea     rdx, [rbp+pv]
0x180008ad7  mov     rax, [rax+28h]
0x180008adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ae0  test    eax, eax
0x180008ae2  js      short loc_180008B28
0x180008ae4  mov     [rbp+arg_8], rsi
0x180008ae8  mov     rax, [rbx]
0x180008aeb  lea     rcx, [rbp+arg_8]
0x180008aef  mov     [rsp+60h+var_40], rcx
0x180008af4  mov     r9d, r14d
0x180008af7  xor     r8d, r8d
0x180008afa  mov     rdx, [rbp+pv]
0x180008afe  mov     rcx, rbx
0x180008b01  mov     rax, [rax+18h]
0x180008b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0a  cmp     [rbp+arg_8], rsi
0x180008b0e  jz      short loc_180008B1E
0x180008b10  lea     rdx, [rbp+arg_8]
0x180008b14  lea     rcx, [rbp+var_18]
0x180008b18  call    ??$emplace_back@AEAPEAVCEndpointCharacteristics@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAAEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@AEAPEAVCEndpointCharacteristics@@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(CEndpointCharacteristics * &)
0x180008b1d  nop
0x180008b1e  lea     rcx, [rbp+arg_8]
0x180008b22  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008b27  nop
0x180008b28  mov     rcx, [rbp+pv]; pv
0x180008b2c  call    cs:__imp_CoTaskMemFree
0x180008b32  nop
0x180008b33  lea     rcx, [rbp+var_30]
0x180008b37  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008b3c  cmp     [rbx+68h], sil
0x180008b40  jnz     loc_180008BCC
0x180008b46  mov     [rbp+pv], rsi
0x180008b4a  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008b51  mov     rax, [rcx]
0x180008b54  lea     r9, [rbp+pv]
0x180008b58  xor     r8d, r8d
0x180008b5b  mov     edx, r14d
0x180008b5e  mov     rax, [rax+20h]
0x180008b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b67  test    eax, eax
0x180008b69  js      short loc_180008BC3
0x180008b6b  mov     [rbp+arg_8], rsi
0x180008b6f  mov     rcx, [rbp+pv]
0x180008b73  mov     rax, [rcx]
0x180008b76  lea     rdx, [rbp+arg_8]
0x180008b7a  mov     rax, [rax+28h]
0x180008b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b83  test    eax, eax
0x180008b85  js      short loc_180008BB8
0x180008b87  mov     [rbp+var_20], rsi
0x180008b8b  mov     rax, [rbx]
0x180008b8e  lea     rcx, [rbp+var_20]
0x180008b92  mov     [rsp+60h+var_40], rcx
0x180008b97  mov     r9d, r14d
0x180008b9a  xor     r8d, r8d
0x180008b9d  mov     rdx, [rbp+arg_8]
0x180008ba1  mov     rcx, rbx
0x180008ba4  mov     rax, [rax+18h]
0x180008ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bad  nop
0x180008bae  lea     rcx, [rbp+var_20]
0x180008bb2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008bb7  nop
0x180008bb8  mov     rcx, [rbp+arg_8]; pv
0x180008bbc  call    cs:__imp_CoTaskMemFree
0x180008bc2  nop
0x180008bc3  lea     rcx, [rbp+pv]
0x180008bc7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008bcc  mov     edi, 2
0x180008bd1  cmp     [rbx+68h], sil
0x180008bd5  jnz     loc_180008E35
0x180008bdb  mov     [rbp+var_30], rsi
0x180008bdf  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008be6  mov     rax, [rcx]
0x180008be9  lea     r9, [rbp+var_30]
0x180008bed  mov     r8d, edi
0x180008bf0  xor     edx, edx
0x180008bf2  mov     rax, [rax+20h]
0x180008bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bfb  test    eax, eax
0x180008bfd  js      short loc_180008C6A
0x180008bff  mov     [rbp+pv], rsi
0x180008c03  mov     rcx, [rbp+var_30]
0x180008c07  mov     rax, [rcx]
0x180008c0a  lea     rdx, [rbp+pv]
0x180008c0e  mov     rax, [rax+28h]
0x180008c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c17  test    eax, eax
0x180008c19  js      short loc_180008C5F
0x180008c1b  mov     [rbp+arg_8], rsi
0x180008c1f  mov     rax, [rbx]
0x180008c22  lea     rcx, [rbp+arg_8]
0x180008c26  mov     [rsp+60h+var_40], rcx
0x180008c2b  mov     r9d, r14d
0x180008c2e  xor     r8d, r8d
0x180008c31  mov     rdx, [rbp+pv]
0x180008c35  mov     rcx, rbx
0x180008c38  mov     rax, [rax+18h]
0x180008c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c41  cmp     [rbp+arg_8], rsi
0x180008c45  jz      short loc_180008C55
0x180008c47  lea     rdx, [rbp+arg_8]
0x180008c4b  lea     rcx, [rbp+var_18]
0x180008c4f  call    ??$emplace_back@AEAPEAVCEndpointCharacteristics@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAAEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@AEAPEAVCEndpointCharacteristics@@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(CEndpointCharacteristics * &)
0x180008c54  nop
0x180008c55  lea     rcx, [rbp+arg_8]
0x180008c59  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008c5e  nop
0x180008c5f  mov     rcx, [rbp+pv]; pv
0x180008c63  call    cs:__imp_CoTaskMemFree
0x180008c69  nop
0x180008c6a  lea     rcx, [rbp+var_30]
0x180008c6e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008c73  cmp     [rbx+68h], sil
0x180008c77  jnz     loc_180008E35
0x180008c7d  mov     [rbp+pv], rsi
0x180008c81  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008c88  mov     rax, [rcx]
0x180008c8b  lea     r9, [rbp+pv]
0x180008c8f  mov     r8d, edi
0x180008c92  mov     edx, r14d
0x180008c95  mov     rax, [rax+20h]
0x180008c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9e  test    eax, eax
0x180008ca0  js      short loc_180008CFA
0x180008ca2  mov     [rbp+arg_8], rsi
0x180008ca6  mov     rcx, [rbp+pv]
0x180008caa  mov     rax, [rcx]
0x180008cad  lea     rdx, [rbp+arg_8]
0x180008cb1  mov     rax, [rax+28h]
0x180008cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cba  test    eax, eax
0x180008cbc  js      short loc_180008CEF
0x180008cbe  mov     [rbp+var_20], rsi
0x180008cc2  mov     rax, [rbx]
0x180008cc5  lea     rcx, [rbp+var_20]
0x180008cc9  mov     [rsp+60h+var_40], rcx
0x180008cce  mov     r9d, r14d
0x180008cd1  xor     r8d, r8d
0x180008cd4  mov     rdx, [rbp+arg_8]
0x180008cd8  mov     rcx, rbx
0x180008cdb  mov     rax, [rax+18h]
0x180008cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce4  nop
0x180008ce5  lea     rcx, [rbp+var_20]
0x180008ce9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008cee  nop
0x180008cef  mov     rcx, [rbp+arg_8]; pv
0x180008cf3  call    cs:__imp_CoTaskMemFree
0x180008cf9  nop
0x180008cfa  lea     rcx, [rbp+pv]
0x180008cfe  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008d03  cmp     [rbx+68h], sil
0x180008d07  jnz     loc_180008E35
0x180008d0d  mov     [rbp+var_30], rsi
0x180008d11  call    cs:__imp_PerformEndpointDiscoveryForUnpluggedEndpoints
0x180008d17  neg     eax
0x180008d19  sbb     r8d, r8d
0x180008d1c  and     r8d, 8
0x180008d20  add     r8d, r14d
0x180008d23  mov     dword ptr [rbp+arg_8], esi
0x180008d26  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180008d2d  mov     rax, [rcx]
0x180008d30  lea     r9, [rbp+var_30]
0x180008d34  mov     edx, edi
0x180008d36  mov     rax, [rax+18h]
0x180008d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d3f  test    eax, eax
0x180008d41  js      loc_180008E1F
0x180008d47  mov     rcx, [rbp+var_30]
0x180008d4b  mov     rax, [rcx]
0x180008d4e  lea     rdx, [rbp+arg_8]
0x180008d52  mov     rax, [rax+18h]
0x180008d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d5b  test    eax, eax
0x180008d5d  js      loc_180008E1F
0x180008d63  mov     edi, esi
0x180008d65  jmp     loc_180008E15
0x180008d6a  cmp     edi, dword ptr [rbp+arg_8]
0x180008d6d  jnb     loc_180008E1F
0x180008d73  mov     [rbp+var_20], rsi
0x180008d77  mov     rcx, [rbp+var_30]
0x180008d7b  mov     rax, [rcx]
0x180008d7e  lea     r8, [rbp+var_20]
0x180008d82  mov     edx, edi
0x180008d84  mov     rax, [rax+20h]
0x180008d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d8d  test    eax, eax
0x180008d8f  js      short loc_180008DFC
0x180008d91  mov     [rbp+var_28], rsi
0x180008d95  mov     rcx, [rbp+var_20]
0x180008d99  mov     rax, [rcx]
0x180008d9c  lea     rdx, [rbp+var_28]
0x180008da0  mov     rax, [rax+28h]
0x180008da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da9  test    eax, eax
0x180008dab  js      short loc_180008DF1
0x180008dad  mov     [rbp+pv], rsi
0x180008db1  mov     rax, [rbx]
0x180008db4  lea     rcx, [rbp+pv]
0x180008db8  mov     [rsp+60h+var_40], rcx
0x180008dbd  mov     r9d, r14d
0x180008dc0  xor     r8d, r8d
0x180008dc3  mov     rdx, [rbp+var_28]
0x180008dc7  mov     rcx, rbx
0x180008dca  mov     rax, [rax+18h]
0x180008dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dd3  cmp     [rbp+pv], rsi
0x180008dd7  jz      short loc_180008DE7
0x180008dd9  lea     rdx, [rbp+pv]
0x180008ddd  lea     rcx, [rbp+var_18]
0x180008de1  call    ??$emplace_back@AEAPEAVCEndpointCharacteristics@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAAEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@AEAPEAVCEndpointCharacteristics@@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::emplace_back<CEndpointCharacteristics * &>(CEndpointCharacteristics * &)
0x180008de6  nop
0x180008de7  lea     rcx, [rbp+pv]
0x180008deb  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180008df0  nop
0x180008df1  mov     rcx, [rbp+var_28]; pv
0x180008df5  call    cs:__imp_CoTaskMemFree
0x180008dfb  nop
0x180008dfc  mov     rcx, [rbp+var_20]
0x180008e00  test    rcx, rcx
0x180008e03  jz      short loc_180008E12
0x180008e05  mov     rax, [rcx]
0x180008e08  mov     rax, [rax+10h]
0x180008e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e11  nop
0x180008e12  add     edi, r14d
0x180008e15  cmp     [rbx+68h], sil
0x180008e19  jz      loc_180008D6A
0x180008e1f  mov     rcx, [rbp+var_30]
0x180008e23  test    rcx, rcx
0x180008e26  jz      short loc_180008E35
0x180008e28  mov     rax, [rcx]
0x180008e2b  mov     rax, [rax+10h]
0x180008e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e34  nop
0x180008e35  mov     rbx, [rbp+var_18]
0x180008e39  mov     rdi, [rbp+var_10]
0x180008e3d  jmp     short loc_180008E65
0x180008e3f  mov     rcx, [rbx]
0x180008e42  mov     rax, [rcx]
0x180008e45  mov     rax, [rax+38h]
0x180008e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e4e  test    eax, eax
0x180008e50  jnz     short loc_180008E61
0x180008e52  mov     rcx, [rbx]
0x180008e55  add     rcx, 1C0h; lpCriticalSection
0x180008e5c  call    ?EnsureSpatialSettingsAreInitialized@CSpatialProperties@@QEAAXXZ; CSpatialProperties::EnsureSpatialSettingsAreInitialized(void)
0x180008e61  add     rbx, 8
0x180008e65  cmp     rbx, rdi
0x180008e68  jnz     short loc_180008E3F
0x180008e6a  call    cs:__imp_CoUninitialize
0x180008e70  nop
0x180008e71  mov     rcx, [rbp+var_18]
0x180008e75  test    rcx, rcx
0x180008e78  jz      short loc_180008E97
0x180008e7a  mov     rdx, [rbp+var_10]
0x180008e7e  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>>(wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> *,wil::com_ptr_t<IWeakReference,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>> &)
0x180008e83  mov     rcx, [rbp+var_18]
0x180008e87  mov     rdx, [rbp+var_8]
0x180008e8b  sub     rdx, rcx
0x180008e8e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180008e92  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008e97  lea     r11, [rsp+60h+var_s0]
0x180008e9c  mov     rbx, [r11+20h]
0x180008ea0  mov     rsi, [r11+30h]
0x180008ea4  mov     rsp, r11
  ... truncated ...
```
