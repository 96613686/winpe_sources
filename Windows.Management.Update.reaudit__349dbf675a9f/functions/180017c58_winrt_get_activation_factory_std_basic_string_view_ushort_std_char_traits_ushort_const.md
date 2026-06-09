# winrt_get_activation_factory(std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x180017c58`
- end: `0x180018271`
- name: `?winrt_get_activation_factory@@YAPEAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `1561`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180018278`

## callees

- `0x180002cac`
- `0x180010ff4`
- `0x18001105c`
- `0x1800110c4`
- `0x18001112c`
- `0x180011194`
- `0x1800111fc`
- `0x180011254`
- `0x1800112cc`
- `0x180011334`
- `0x180011440`
- `0x180012324`
- `0x1800127c0`
- `0x180015ad8`
- `0x180017c58`

## string_xrefs

- `0x180017e5d`: `Windows.Management.Update.WindowsSoftwareUpdateOptionalActionInfo`
- `0x180017ebd`: `Windows.Management.Update.WindowsSoftwareUpdateOptionalInfo`
- `0x180017f1d`: `Windows.Management.Update.WindowsSoftwareUpdateProvider`
- `0x180017f7d`: `Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult`
- `0x180018008`: `Windows.Management.Update.WindowsSoftwareUpdateProviderStatus`
- `0x180018036`: `Windows.Management.Update.WindowsSoftwareUpdateResult`
- `0x180018061`: `Windows.Management.Update.WindowsSoftwareUpdateScanResult`
- `0x18001808c`: `Windows.Management.Update.WindowsSoftwareUpdateVersion`
- `0x1800180ba`: `Windows.Management.Update.WindowsUpdateAdministrator`
- `0x1800180e8`: `Windows.Management.Update.WindowsUpdateApprovalData`
- `0x180018116`: `Windows.Management.Update.WindowsUpdateManager`
- `0x180018144`: `Windows.Management.Update.WindowsUpdateManagerScanOptions`
- `0x180018172`: `Windows.Management.Update.WindowsUpdateRestartRequestOptions`

## pseudocode

```c
_QWORD *__fastcall winrt_get_activation_factory(_QWORD *n)
{
  _WORD *v1; // rdx
  _QWORD *v2; // r10
  __int64 v3; // r9
  __int64 v4; // rax
  __int64 v5; // r9
  _WORD *j; // r8
  void ***v7; // rcx
  _QWORD *result; // rax
  void **v9; // rdx
  _WORD *i; // r8
  _WORD *m; // r8
  _WORD *k; // r8
  __int64 v13; // rcx
  __int64 v14; // r10
  __int64 v15; // rcx
  __int64 v16; // r10
  __int64 v17; // rcx
  __int64 v18; // r10
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r10
  __int64 updated; // rax
  __int64 v25; // rcx
  __int64 v26; // r10
  __int64 v27; // rcx
  __int64 v28; // r10
  __int64 v29; // rcx
  __int64 v30; // r10
  __int64 v31; // rcx
  __int64 v32; // r10
  __int64 v33; // rcx
  __int64 v34; // r10
  __int64 v35; // rcx
  __int64 v36; // r10
  __int64 v37; // rcx
  __int64 v38; // r10
  __int64 v39; // rcx
  __int64 v40; // r10
  _QWORD v41[2]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v42[2]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v43[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v44[2]; // [rsp+50h] [rbp-10h] BYREF
  _QWORD *v45; // [rsp+70h] [rbp+10h] BYREF

  v1 = (_WORD *)*n;
  v2 = n;
  v3 = 2LL * n[1];
  v4 = v3 + *n;
  v5 = v3 >> 1;
  if ( v5 == 47 )
  {
    for ( i = (_WORD *)(v4 - 2); i + 1 != v1; --i )
    {
      n = (_QWORD *)*(unsigned __int16 *)((char *)L"" + (_QWORD)i - v4);
      if ( *i != (_WORD)n )
        goto LABEL_12;
    }
    v7 = (void ***)operator new(0x20u);
    *v7 = 0;
    v7[1] = 0;
    v7[3] = 0;
    result = v7 + 2;
    v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
    v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdateFactory>::`vftable';
    v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdate>::`vftable';
  }
  else if ( v5 == 57 )
  {
    for ( j = (_WORD *)(v4 - 2); j + 1 != v1; --j )
    {
      n = (_QWORD *)*(unsigned __int16 *)((char *)L"" + (_QWORD)j - v4);
      if ( *j != (_WORD)n )
        goto LABEL_13;
    }
    v7 = (void ***)operator new(0x20u);
    *v7 = 0;
    v7[1] = 0;
    v7[3] = 0;
    result = v7 + 2;
    v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
    v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfoFactory>::`vftable';
    v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo>::`vftable';
  }
  else
  {
LABEL_12:
    if ( v5 == 61 )
    {
      for ( k = (_WORD *)(v4 - 2); k + 1 != v1; --k )
      {
        n = (_QWORD *)*(unsigned __int16 *)((char *)L"" + (_QWORD)k - v4);
        if ( *k != (_WORD)n )
          goto LABEL_23;
      }
      v7 = (void ***)operator new(0x20u);
      *v7 = 0;
      v7[1] = 0;
      v7[3] = 0;
      result = v7 + 2;
      v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateAppPackageInfoFactory>::`vftable';
      v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo>::`vftable';
    }
    else
    {
LABEL_13:
      if ( v5 == 59 )
      {
        for ( m = (_WORD *)(v4 - 2); m + 1 != v1; --m )
        {
          n = (_QWORD *)*(unsigned __int16 *)((char *)L"" + (_QWORD)m - v4);
          if ( *m != (_WORD)n )
            goto LABEL_24;
        }
        v7 = (void ***)operator new(0x20u);
        *v7 = 0;
        v7[1] = 0;
        v7[3] = 0;
        result = v7 + 2;
        v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
        v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::`vftable';
        v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo>::`vftable';
      }
      else
      {
LABEL_23:
        if ( v5 == 60 )
        {
          for ( n = (_QWORD *)(v4 - 2); (_WORD *)((char *)n + 2) != v1; n = (_QWORD *)((char *)n - 2) )
          {
            if ( *(_WORD *)n != *(const unsigned __int16 *)((char *)L"" + (_QWORD)n - v4) )
              goto LABEL_34;
          }
          v7 = (void ***)operator new(0x20u);
          *v7 = 0;
          v7[1] = 0;
          v7[3] = 0;
          result = v7 + 2;
          v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
          v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfoFactory>::`vftable';
          v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
        }
        else
        {
LABEL_24:
          if ( v5 == 63 )
          {
            for ( n = (_QWORD *)(v4 - 2); (_WORD *)((char *)n + 2) != v1; n = (_QWORD *)((char *)n - 2) )
            {
              if ( *(_WORD *)n != *(const unsigned __int16 *)((char *)L"" + (_QWORD)n - v4) )
                goto LABEL_34;
            }
            v7 = (void ***)operator new(0x20u);
            *v7 = 0;
            v7[1] = 0;
            v7[3] = 0;
            result = v7 + 2;
            v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
            v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfoFactory>::`vftable';
            v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable';
          }
          else
          {
LABEL_34:
            v41[1] = 65;
            v41[0] = L"Windows.Management.Update.WindowsSoftwareUpdateOptionalActionInfo";
            if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(n, v2, v41) )
            {
              v7 = (void ***)operator new(0x20u);
              *v7 = 0;
              v7[1] = 0;
              v7[3] = 0;
              result = v7 + 2;
              v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
              v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalActionInfoFactory>::`vftable';
              v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo>::`vftable';
            }
            else
            {
              v42[1] = 59;
              v42[0] = L"Windows.Management.Update.WindowsSoftwareUpdateOptionalInfo";
              if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v13, v14, v42) )
              {
                v7 = (void ***)operator new(0x20u);
                *v7 = 0;
                v7[1] = 0;
                v7[3] = 0;
                result = v7 + 2;
                v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
                v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::`vftable';
                v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo>::`vftable';
              }
              else
              {
                v43[1] = 55;
                v43[0] = L"Windows.Management.Update.WindowsSoftwareUpdateProvider";
                if ( !(unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v15, v16, v43) )
                {
                  v44[1] = 67;
                  v44[0] = L"Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult";
                  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v17, v18, v44) )
                  {
                    v19 = operator new(0x20u);
                    *v19 = 0;
                    v19[1] = 0;
                    v19[3] = 0;
                    v19[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
                    v19[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResultFactory>::`vftable';
                    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
                    v45 = v19 + 2;
                    *v19 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable';
                    v20 = &v45;
                    v19[1] = 1;
                  }
                  else
                  {
                    std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                      v44,
                      L"Windows.Management.Update.WindowsSoftwareUpdateProviderStatus");
                    if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v22, v23, v44) )
                    {
                      updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatus,>(&v45);
                    }
                    else
                    {
                      std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                        v44,
                        L"Windows.Management.Update.WindowsSoftwareUpdateResult");
                      if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v25, v26, v44) )
                      {
                        updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,>(&v45);
                      }
                      else
                      {
                        std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                          v44,
                          L"Windows.Management.Update.WindowsSoftwareUpdateScanResult");
                        if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v27, v28, v44) )
                        {
                          updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResult,>(&v45);
                        }
                        else
                        {
                          std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                            v44,
                            L"Windows.Management.Update.WindowsSoftwareUpdateVersion");
                          if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v29, v30, v44) )
                          {
                            updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,>(&v45);
                          }
                          else
                          {
                            std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                              v44,
                              L"Windows.Management.Update.WindowsUpdateAdministrator");
                            if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v31, v32, v44) )
                            {
                              updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,>(&v45);
                            }
                            else
                            {
                              std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                v44,
                                L"Windows.Management.Update.WindowsUpdateApprovalData");
                              if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v33, v34, v44) )
                              {
                                updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateApprovalData,>(&v45);
                              }
                              else
                              {
                                std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                  v44,
                                  L"Windows.Management.Update.WindowsUpdateManager");
                                if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(
                                                        v35,
                                                        v36,
                                                        v44) )
                                {
                                  updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,>(&v45);
                                }
                                else
                                {
                                  std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                    v44,
                                    L"Windows.Management.Update.WindowsUpdateManagerScanOptions");
                                  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(
                                                          v37,
                                                          v38,
                                                          v44) )
                                  {
                                    updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,>(&v45);
                                  }
                                  else
                                  {
                                    std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                      v44,
                                      L"Windows.Management.Update.WindowsUpdateRestartRequestOptions");
                                    if ( !(unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(
                                                             v39,
                                                             v40,
                                                             v44) )
                                      return 0;
                                    updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateRestartRequestOptions,>(&v45);
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                    v20 = (_QWORD *)updated;
                  }
                  v21 = winrt::detach_abi(v20);
                  winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider((winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider *)&v45);
                  return (_QWORD *)v21;
                }
                v7 = (void ***)operator new(0x20u);
                *v7 = 0;
                v7[1] = 0;
                v7[3] = 0;
                result = v7 + 2;
                v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
                v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::`vftable';
                v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider>::`vftable';
              }
            }
          }
        }
      }
    }
  }
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *v7 = v9;
  v7[1] = (void **)1;
  return result;
}

```

## disassembly

```asm
0x180017c58  mov     [rsp-8+arg_8], rbx
0x180017c5d  push    rbp
0x180017c5e  mov     rbp, rsp
0x180017c61  sub     rsp, 60h
0x180017c65  mov     rax, [rcx+8]
0x180017c69  xor     ebx, ebx
0x180017c6b  mov     rdx, [rcx]
0x180017c6e  mov     r10, rcx
0x180017c71  lea     r9, [rax+rax]
0x180017c75  lea     rax, [r9+rdx]
0x180017c79  sar     r9, 1
0x180017c7c  cmp     r9, 2Fh ; '/'
0x180017c80  jz      short loc_180017CF1
0x180017c82  cmp     r9, 39h ; '9'
0x180017c86  jnz     loc_180017D1D
0x180017c8c  lea     r11, aWindowsManagem_12+72h; ""
0x180017c93  sub     r11, rax
0x180017c96  lea     r8, [rax-2]
0x180017c9a  lea     rcx, [r8+2]
0x180017c9e  cmp     rcx, rdx
0x180017ca1  jz      short loc_180017CB4
0x180017ca3  movzx   ecx, word ptr [r8+r11]
0x180017ca8  cmp     [r8], cx
0x180017cac  jnz     short loc_180017D23
0x180017cae  sub     r8, 2
0x180017cb2  jmp     short loc_180017C9A
0x180017cb4  mov     ecx, 20h ; ' '; Size
0x180017cb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017cbe  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017cc5  mov     rcx, rax
0x180017cc8  mov     [rax], rbx
0x180017ccb  mov     [rax+8], rbx
0x180017ccf  mov     [rax+18h], rbx
0x180017cd3  add     rax, 10h
0x180017cd7  mov     [rax], rdx
0x180017cda  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateActionInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateActionInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfoFactory>::`vftable'
0x180017ce1  mov     [rax+8], rdx
0x180017ce5  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateActionInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo>::`vftable'
0x180017cec  jmp     loc_180018253
0x180017cf1  lea     r11, aWindowsManagem_15+5Eh; ""
0x180017cf8  sub     r11, rax
0x180017cfb  lea     r8, [rax-2]
0x180017cff  lea     rcx, [r8+2]
0x180017d03  cmp     rcx, rdx
0x180017d06  jz      loc_18001821B
0x180017d0c  movzx   ecx, word ptr [r8+r11]
0x180017d11  cmp     [r8], cx
0x180017d15  jnz     short loc_180017D1D
0x180017d17  sub     r8, 2
0x180017d1b  jmp     short loc_180017CFF
0x180017d1d  cmp     r9, 3Dh ; '='
0x180017d21  jz      short loc_180017D92
0x180017d23  cmp     r9, 3Bh ; ';'
0x180017d27  jnz     loc_180017DBE
0x180017d2d  lea     r11, aWindowsManagem_16+76h; ""
0x180017d34  sub     r11, rax
0x180017d37  lea     r8, [rax-2]
0x180017d3b  lea     rcx, [r8+2]
0x180017d3f  cmp     rcx, rdx
0x180017d42  jz      short loc_180017D55
0x180017d44  movzx   ecx, word ptr [r8+r11]
0x180017d49  cmp     [r8], cx
0x180017d4d  jnz     short loc_180017DC4
0x180017d4f  sub     r8, 2
0x180017d53  jmp     short loc_180017D3B
0x180017d55  mov     ecx, 20h ; ' '; Size
0x180017d5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017d5f  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017d66  mov     rcx, rax
0x180017d69  mov     [rax], rbx
0x180017d6c  mov     [rax+8], rbx
0x180017d70  mov     [rax+18h], rbx
0x180017d74  add     rax, 10h
0x180017d78  mov     [rax], rdx
0x180017d7b  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateApprovalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateApprovalInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::`vftable'
0x180017d82  mov     [rax+8], rdx
0x180017d86  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateApprovalInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo>::`vftable'
0x180017d8d  jmp     loc_180018253
0x180017d92  lea     r11, aWindowsManagem_3+7Ah; ""
0x180017d99  sub     r11, rax
0x180017d9c  lea     r8, [rax-2]
0x180017da0  lea     rcx, [r8+2]
0x180017da4  cmp     rcx, rdx
0x180017da7  jz      loc_1800181E1
0x180017dad  movzx   ecx, word ptr [r8+r11]
0x180017db2  cmp     [r8], cx
0x180017db6  jnz     short loc_180017DBE
0x180017db8  sub     r8, 2
0x180017dbc  jmp     short loc_180017DA0
0x180017dbe  cmp     r9, 3Ch ; '<'
0x180017dc2  jz      short loc_180017E32
0x180017dc4  cmp     r9, 3Fh ; '?'
0x180017dc8  jnz     loc_180017E5D
0x180017dce  lea     r8, aWindowsManagem_5+7Eh; ""
0x180017dd5  sub     r8, rax
0x180017dd8  lea     rcx, [rax-2]
0x180017ddc  lea     rax, [rcx+2]
0x180017de0  cmp     rax, rdx
0x180017de3  jz      short loc_180017DF5
0x180017de5  movzx   eax, word ptr [rcx+r8]
0x180017dea  cmp     [rcx], ax
0x180017ded  jnz     short loc_180017E5D
0x180017def  sub     rcx, 2
0x180017df3  jmp     short loc_180017DDC
0x180017df5  mov     ecx, 20h ; ' '; Size
0x180017dfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017dff  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017e06  mov     rcx, rax
0x180017e09  mov     [rax], rbx
0x180017e0c  mov     [rax+8], rbx
0x180017e10  mov     [rax+18h], rbx
0x180017e14  add     rax, 10h
0x180017e18  mov     [rax], rdx
0x180017e1b  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateLocalizationInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfoFactory>::`vftable'
0x180017e22  mov     [rax+8], rdx
0x180017e26  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x180017e2d  jmp     loc_180018253
0x180017e32  lea     r8, aWindowsManagem_4+78h; ""
0x180017e39  sub     r8, rax
0x180017e3c  lea     rcx, [rax-2]
0x180017e40  lea     rax, [rcx+2]
0x180017e44  cmp     rax, rdx
0x180017e47  jz      loc_1800181A7
0x180017e4d  movzx   eax, word ptr [rcx+r8]
0x180017e52  cmp     [rcx], ax
0x180017e55  jnz     short loc_180017E5D
0x180017e57  sub     rcx, 2
0x180017e5b  jmp     short loc_180017E40
0x180017e5d  lea     rax, aWindowsManagem_10; "Windows.Management.Update.WindowsSoftwa"...
0x180017e64  mov     [rbp+var_38], 41h ; 'A'
0x180017e6c  lea     r8, [rbp+var_40]
0x180017e70  mov     [rbp+var_40], rax
0x180017e74  mov     rdx, r10
0x180017e77  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180017e7c  test    al, al
0x180017e7e  jz      short loc_180017EBD
0x180017e80  mov     ecx, 20h ; ' '; Size
0x180017e85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017e8a  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017e91  mov     rcx, rax
0x180017e94  mov     [rax], rbx
0x180017e97  mov     [rax+8], rbx
0x180017e9b  mov     [rax+18h], rbx
0x180017e9f  add     rax, 10h
0x180017ea3  mov     [rax], rdx
0x180017ea6  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateOptionalActionInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalActionInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalActionInfoFactory>::`vftable'
0x180017ead  mov     [rax+8], rdx
0x180017eb1  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateOptionalActionInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo>::`vftable'
0x180017eb8  jmp     loc_180018253
0x180017ebd  lea     rax, aWindowsManagem_8; "Windows.Management.Update.WindowsSoftwa"...
0x180017ec4  mov     [rbp+var_28], 3Bh ; ';'
0x180017ecc  lea     r8, [rbp+var_30]
0x180017ed0  mov     [rbp+var_30], rax
0x180017ed4  mov     rdx, r10
0x180017ed7  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180017edc  test    al, al
0x180017ede  jz      short loc_180017F1D
0x180017ee0  mov     ecx, 20h ; ' '; Size
0x180017ee5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017eea  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017ef1  mov     rcx, rax
0x180017ef4  mov     [rax], rbx
0x180017ef7  mov     [rax+8], rbx
0x180017efb  mov     [rax+18h], rbx
0x180017eff  add     rax, 10h
0x180017f03  mov     [rax], rdx
0x180017f06  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateOptionalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::`vftable'
0x180017f0d  mov     [rax+8], rdx
0x180017f11  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateOptionalInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo>::`vftable'
0x180017f18  jmp     loc_180018253
0x180017f1d  lea     rax, aWindowsManagem_13; "Windows.Management.Update.WindowsSoftwa"...
0x180017f24  mov     [rbp+var_18], 37h ; '7'
0x180017f2c  lea     r8, [rbp+var_20]
0x180017f30  mov     [rbp+var_20], rax
0x180017f34  mov     rdx, r10
0x180017f37  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180017f3c  test    al, al
0x180017f3e  jz      short loc_180017F7D
0x180017f40  mov     ecx, 20h ; ' '; Size
0x180017f45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f4a  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017f51  mov     rcx, rax
0x180017f54  mov     [rax], rbx
0x180017f57  mov     [rax+8], rbx
0x180017f5b  mov     [rax+18h], rbx
0x180017f5f  add     rax, 10h
0x180017f63  mov     [rax], rdx
0x180017f66  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateProvider@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::`vftable'
0x180017f6d  mov     [rax+8], rdx
0x180017f71  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateProvider@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider>::`vftable'
0x180017f78  jmp     loc_180018253
0x180017f7d  lea     rax, aWindowsManagem_6; "Windows.Management.Update.WindowsSoftwa"...
0x180017f84  mov     [rbp+var_8], 43h ; 'C'
0x180017f8c  lea     r8, [rbp+var_10]
0x180017f90  mov     [rbp+var_10], rax
0x180017f94  mov     rdx, r10
0x180017f97  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180017f9c  test    al, al
0x180017f9e  jz      short loc_180018008
0x180017fa0  mov     ecx, 20h ; ' '; Size
0x180017fa5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017faa  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017fb1  mov     [rax], rbx
0x180017fb4  lea     rcx, [rax+10h]
0x180017fb8  mov     [rax+8], rbx
0x180017fbc  mov     [rax+18h], rbx
0x180017fc0  mov     [rcx], rdx
0x180017fc3  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateProviderActionResult@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderActionResultFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderActionResultFactory>::`vftable'
0x180017fca  mov     [rcx+8], rdx
0x180017fce  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180017fd5  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateProviderActionResult@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult>::`vftable'
0x180017fdc  mov     [rbp+arg_0], rcx
0x180017fe0  mov     [rax], rdx
0x180017fe3  lea     rcx, [rbp+arg_0]
0x180017fe7  mov     qword ptr [rax+8], 1
0x180017fef  call    ?detach_abi@winrt@@YAPEAX$$QEAUIUnknown@Foundation@Windows@1@@Z; winrt::detach_abi(winrt::Windows::Foundation::IUnknown &&)
0x180017ff4  lea     rcx, [rbp+arg_0]; this
0x180017ff8  mov     rbx, rax
0x180017ffb  call    ??1IWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider(void)
0x180018000  mov     rax, rbx
0x180018003  jmp     loc_180018265
0x180018008  lea     rdx, aWindowsManagem_7; "Windows.Management.Update.WindowsSoftwa"...
0x18001800f  lea     rcx, [rbp+var_10]
0x180018013  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x180018018  lea     r8, [rbp+var_10]
0x18001801c  mov     rdx, r10
0x18001801f  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180018024  test    al, al
0x180018026  jz      short loc_180018036
0x180018028  lea     rcx, [rbp+arg_0]
0x18001802c  call    ??$make@UWindowsSoftwareUpdateProviderStatus@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180018031  mov     rcx, rax
0x180018034  jmp     short loc_180017FEF
0x180018036  lea     rdx, aWindowsManagem_18; "Windows.Management.Update.WindowsSoftwa"...
0x18001803d  lea     rcx, [rbp+var_10]
0x180018041  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x180018046  lea     r8, [rbp+var_10]
0x18001804a  mov     rdx, r10
0x18001804d  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180018052  test    al, al
0x180018054  jz      short loc_180018061
0x180018056  lea     rcx, [rbp+arg_0]
0x18001805a  call    ??$make@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x18001805f  jmp     short loc_180018031
0x180018061  lea     rdx, aWindowsManagem_11; "Windows.Management.Update.WindowsSoftwa"...
0x180018068  lea     rcx, [rbp+var_10]
0x18001806c  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x180018071  lea     r8, [rbp+var_10]
0x180018075  mov     rdx, r10
0x180018078  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x18001807d  test    al, al
0x18001807f  jz      short loc_18001808C
0x180018081  lea     rcx, [rbp+arg_0]
0x180018085  call    ??$make@UWindowsSoftwareUpdateScanResult@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x18001808a  jmp     short loc_180018031
0x18001808c  lea     rdx, aWindowsManagem_19; "Windows.Management.Update.WindowsSoftwa"...
0x180018093  lea     rcx, [rbp+var_10]
0x180018097  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x18001809c  lea     r8, [rbp+var_10]
0x1800180a0  mov     rdx, r10
0x1800180a3  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800180a8  test    al, al
0x1800180aa  jz      short loc_1800180BA
0x1800180ac  lea     rcx, [rbp+arg_0]
0x1800180b0  call    ??$make@UWindowsSoftwareUpdateVersion@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x1800180b5  jmp     loc_180018031
0x1800180ba  lea     rdx, aWindowsManagem_17; "Windows.Management.Update.WindowsUpdate"...
0x1800180c1  lea     rcx, [rbp+var_10]
0x1800180c5  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x1800180ca  lea     r8, [rbp+var_10]
0x1800180ce  mov     rdx, r10
0x1800180d1  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800180d6  test    al, al
0x1800180d8  jz      short loc_1800180E8
0x1800180da  lea     rcx, [rbp+arg_0]
0x1800180de  call    ??$make@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x1800180e3  jmp     loc_180018031
0x1800180e8  lea     rdx, aWindowsManagem_1; "Windows.Management.Update.WindowsUpdate"...
0x1800180ef  lea     rcx, [rbp+var_10]
0x1800180f3  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x1800180f8  lea     r8, [rbp+var_10]
0x1800180fc  mov     rdx, r10
0x1800180ff  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180018104  test    al, al
0x180018106  jz      short loc_180018116
0x180018108  lea     rcx, [rbp+arg_0]
0x18001810c  call    ??$make@UWindowsUpdateApprovalData@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180018111  jmp     loc_180018031
0x180018116  lea     rdx, aWindowsManagem_2; "Windows.Management.Update.WindowsUpdate"...
0x18001811d  lea     rcx, [rbp+var_10]
0x180018121  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x180018126  lea     r8, [rbp+var_10]
0x18001812a  mov     rdx, r10
0x18001812d  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180018132  test    al, al
0x180018134  jz      short loc_180018144
0x180018136  lea     rcx, [rbp+arg_0]
0x18001813a  call    ??$make@UWindowsUpdateManager@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x18001813f  jmp     loc_180018031
0x180018144  lea     rdx, aWindowsManagem_14; "Windows.Management.Update.WindowsUpdate"...
  ... truncated ...
```
