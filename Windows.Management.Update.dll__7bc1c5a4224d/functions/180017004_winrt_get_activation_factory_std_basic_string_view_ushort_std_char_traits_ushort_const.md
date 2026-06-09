# winrt_get_activation_factory(std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x180017004`
- end: `0x1800175c5`
- name: `?winrt_get_activation_factory@@YAPEAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `1473`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x1800175cc`

## callees

- `0x180002cfc`
- `0x180010464`
- `0x1800104cc`
- `0x180010534`
- `0x18001059c`
- `0x180010604`
- `0x18001066c`
- `0x1800106d4`
- `0x180010730`
- `0x1800107a4`
- `0x18001080c`
- `0x1800108f8`
- `0x18001177c`
- `0x180011bd4`
- `0x180014ecc`
- `0x180017004`

## string_xrefs

- `0x1800171e3`: `Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult`
- `0x1800173d2`: `Windows.Management.Update.WindowsSoftwareUpdateProviderStatus`
- `0x180017400`: `Windows.Management.Update.WindowsSoftwareUpdateResult`
- `0x18001742e`: `Windows.Management.Update.WindowsSoftwareUpdateScanResult`
- `0x18001745c`: `Windows.Management.Update.WindowsSoftwareUpdateVersion`
- `0x18001748a`: `Windows.Management.Update.WindowsUpdateAdministrator`
- `0x1800174b8`: `Windows.Management.Update.WindowsUpdateApprovalData`
- `0x1800174e6`: `Windows.Management.Update.WindowsUpdateManager`
- `0x180017514`: `Windows.Management.Update.WindowsUpdateManagerScanOptions`
- `0x180017542`: `Windows.Management.Update.WindowsUpdateRestartRequestOptions`

## pseudocode

```c
_QWORD *__fastcall winrt_get_activation_factory(_QWORD *a1)
{
  _WORD *v1; // rdx
  __int64 v2; // r10
  _WORD *v3; // rax
  __int64 v4; // r10
  _WORD *v5; // rcx
  wchar_t *v6; // r8
  void ***v7; // rcx
  _QWORD *result; // rax
  void **v9; // rdx
  _WORD *v10; // rcx
  wchar_t *v11; // r8
  _WORD *v12; // rcx
  wchar_t *v13; // r8
  _WORD *v14; // rcx
  wchar_t *v15; // r8
  _WORD *v16; // rcx
  wchar_t *v17; // r8
  _WORD *v18; // rcx
  wchar_t *v19; // r8
  _WORD *v20; // rcx
  wchar_t *v21; // r8
  _WORD *v22; // rcx
  wchar_t *v23; // r8
  wchar_t *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r11
  __int64 updated; // rax
  _QWORD *v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // r11
  __int64 v33; // rcx
  __int64 v34; // r11
  __int64 v35; // rcx
  __int64 v36; // r11
  __int64 v37; // rcx
  __int64 v38; // r11
  __int64 v39; // rcx
  __int64 v40; // r11
  __int64 v41; // rcx
  __int64 v42; // r11
  __int64 v43; // rcx
  __int64 v44; // r11
  __int64 v45; // rcx
  __int64 v46; // r11
  __int64 v47; // rcx
  __int64 v48; // r11
  _BYTE v49[16]; // [rsp+20h] [rbp-10h] BYREF
  _QWORD *v50; // [rsp+40h] [rbp+10h] BYREF

  v1 = (_WORD *)*a1;
  v2 = 2LL * a1[1];
  v3 = (_WORD *)(v2 + *a1);
  v4 = v2 >> 1;
  if ( v4 == 47 )
  {
    v10 = v3;
    v11 = L"";
    while ( v10 != v1 )
    {
      if ( *--v10 != *--v11 )
        goto LABEL_11;
    }
    v7 = (void ***)operator new(0x20u);
    *v7 = 0;
    v7[1] = 0;
    result = v7 + 2;
    v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
    v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdate,winrt::Windows::Management::Update::IWindowsSoftwareUpdateFactory>::`vftable';
    v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdate>::`vftable';
  }
  else if ( v4 == 57 )
  {
    v5 = v3;
    v6 = L"";
    while ( v5 != v1 )
    {
      if ( *--v5 != *--v6 )
        goto LABEL_11;
    }
    v7 = (void ***)operator new(0x20u);
    *v7 = 0;
    v7[1] = 0;
    result = v7 + 2;
    v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
    v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfoFactory>::`vftable';
    v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo>::`vftable';
  }
  else
  {
LABEL_11:
    if ( v4 == 61 )
    {
      v12 = v3;
      v13 = L"";
      while ( v12 != v1 )
      {
        if ( *--v12 != *--v13 )
          goto LABEL_15;
      }
      v7 = (void ***)operator new(0x20u);
      *v7 = 0;
      v7[1] = 0;
      result = v7 + 2;
      v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateAppPackageInfoFactory>::`vftable';
      v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo>::`vftable';
    }
    else
    {
LABEL_15:
      if ( v4 == 59 )
      {
        v14 = v3;
        v15 = L"";
        while ( v14 != v1 )
        {
          if ( *--v14 != *--v15 )
            goto LABEL_19;
        }
        v7 = (void ***)operator new(0x20u);
        *v7 = 0;
        v7[1] = 0;
        result = v7 + 2;
        v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
        v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::`vftable';
        v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo>::`vftable';
      }
      else
      {
LABEL_19:
        if ( v4 == 60 )
        {
          v16 = v3;
          v17 = L"";
          while ( v16 != v1 )
          {
            if ( *--v16 != *--v17 )
              goto LABEL_23;
          }
          v7 = (void ***)operator new(0x20u);
          *v7 = 0;
          v7[1] = 0;
          result = v7 + 2;
          v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
          v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfoFactory>::`vftable';
          v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable';
        }
        else
        {
LABEL_23:
          if ( v4 == 63 )
          {
            v18 = v3;
            v19 = L"";
            while ( v18 != v1 )
            {
              if ( *--v18 != *--v19 )
                goto LABEL_27;
            }
            v7 = (void ***)operator new(0x20u);
            *v7 = 0;
            v7[1] = 0;
            result = v7 + 2;
            v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
            v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfoFactory>::`vftable';
            v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable';
          }
          else
          {
LABEL_27:
            if ( v4 == 65 )
            {
              v20 = v3;
              v21 = L"";
              while ( v20 != v1 )
              {
                if ( *--v20 != *--v21 )
                  goto LABEL_31;
              }
              v7 = (void ***)operator new(0x20u);
              *v7 = 0;
              v7[1] = 0;
              result = v7 + 2;
              v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
              v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalActionInfoFactory>::`vftable';
              v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo>::`vftable';
            }
            else
            {
LABEL_31:
              if ( v4 != 59 )
              {
LABEL_35:
                if ( v4 == 55 )
                {
                  v24 = L"";
                  while ( v3 != v1 )
                  {
                    if ( *--v3 != *--v24 )
                      goto LABEL_39;
                  }
                  v29 = operator new(0x20u);
                  *v29 = 0;
                  v29[1] = 0;
                  v29[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
                  v29[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::`vftable';
                  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
                  v50 = v29 + 2;
                  *v29 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider>::`vftable';
                  v28 = &v50;
                  v29[1] = 1;
                }
                else
                {
LABEL_39:
                  std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                    v49,
                    L"Windows.Management.Update.WindowsSoftwareUpdateProviderActionResult");
                  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v25, v26, v49) )
                  {
                    updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderActionResult,>(&v50);
                  }
                  else
                  {
                    std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                      v49,
                      L"Windows.Management.Update.WindowsSoftwareUpdateProviderStatus");
                    if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v31, v32, v49) )
                    {
                      updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProviderStatus,>(&v50);
                    }
                    else
                    {
                      std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                        v49,
                        L"Windows.Management.Update.WindowsSoftwareUpdateResult");
                      if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v33, v34, v49) )
                      {
                        updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateResult,>(&v50);
                      }
                      else
                      {
                        std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                          v49,
                          L"Windows.Management.Update.WindowsSoftwareUpdateScanResult");
                        if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v35, v36, v49) )
                        {
                          updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateScanResult,>(&v50);
                        }
                        else
                        {
                          std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                            v49,
                            L"Windows.Management.Update.WindowsSoftwareUpdateVersion");
                          if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v37, v38, v49) )
                          {
                            updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateVersion,>(&v50);
                          }
                          else
                          {
                            std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                              v49,
                              L"Windows.Management.Update.WindowsUpdateAdministrator");
                            if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v39, v40, v49) )
                            {
                              updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateAdministrator,>(&v50);
                            }
                            else
                            {
                              std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                v49,
                                L"Windows.Management.Update.WindowsUpdateApprovalData");
                              if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v41, v42, v49) )
                              {
                                updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateApprovalData,>(&v50);
                              }
                              else
                              {
                                std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                  v49,
                                  L"Windows.Management.Update.WindowsUpdateManager");
                                if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(
                                                        v43,
                                                        v44,
                                                        v49) )
                                {
                                  updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManager,>(&v50);
                                }
                                else
                                {
                                  std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                    v49,
                                    L"Windows.Management.Update.WindowsUpdateManagerScanOptions");
                                  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(
                                                          v45,
                                                          v46,
                                                          v49) )
                                  {
                                    updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateManagerScanOptions,>(&v50);
                                  }
                                  else
                                  {
                                    std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
                                      v49,
                                      L"Windows.Management.Update.WindowsUpdateRestartRequestOptions");
                                    if ( !(unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(
                                                             v47,
                                                             v48,
                                                             v49) )
                                      return 0;
                                    updated = winrt::make<winrt::Windows::Management::Update::factory_implementation::WindowsUpdateRestartRequestOptions,>(&v50);
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                  v28 = (_QWORD *)updated;
                }
                v30 = winrt::detach_abi(v28);
                winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider((winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider *)&v50);
                return (_QWORD *)v30;
              }
              v22 = v3;
              v23 = L"";
              while ( v22 != v1 )
              {
                if ( *--v22 != *--v23 )
                  goto LABEL_35;
              }
              v7 = (void ***)operator new(0x20u);
              *v7 = 0;
              v7[1] = 0;
              result = v7 + 2;
              v7[2] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable';
              v7[3] = &winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::`vftable';
              v9 = &winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo>::`vftable';
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
0x180017004  mov     [rsp-8+arg_8], rbx
0x180017009  push    rbp
0x18001700a  mov     rbp, rsp
0x18001700d  sub     rsp, 30h
0x180017011  mov     rax, [rcx+8]
0x180017015  xor     ebx, ebx
0x180017017  mov     rdx, [rcx]
0x18001701a  mov     r11, rcx
0x18001701d  lea     r10, [rax+rax]
0x180017021  lea     rax, [r10+rdx]
0x180017025  sar     r10, 1
0x180017028  cmp     r10, 2Fh ; '/'
0x18001702c  jz      short loc_180017094
0x18001702e  cmp     r10, 39h ; '9'
0x180017032  jnz     loc_1800170B9
0x180017038  mov     rcx, rax
0x18001703b  lea     r8, aWindowsManagem_12+72h; ""
0x180017042  cmp     rcx, rdx
0x180017045  jz      short loc_18001705B
0x180017047  add     r8, 0FFFFFFFFFFFFFFFEh
0x18001704b  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18001704f  movzx   r9d, word ptr [r8]
0x180017053  cmp     [rcx], r9w
0x180017057  jz      short loc_180017042
0x180017059  jmp     short loc_1800170B9
0x18001705b  mov     ecx, 20h ; ' '; Size
0x180017060  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017065  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x18001706c  mov     rcx, rax
0x18001706f  mov     [rax], rbx
0x180017072  mov     [rax+8], rbx
0x180017076  add     rax, 10h
0x18001707a  mov     [rax], rdx
0x18001707d  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateActionInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateActionInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateActionInfoFactory>::`vftable'
0x180017084  mov     [rax+8], rdx
0x180017088  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateActionInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateActionInfo>::`vftable'
0x18001708f  jmp     loc_1800175A8
0x180017094  mov     rcx, rax
0x180017097  lea     r8, aWindowsManagem_15+5Eh; ""
0x18001709e  cmp     rcx, rdx
0x1800170a1  jz      loc_180017574
0x1800170a7  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800170ab  add     rcx, 0FFFFFFFFFFFFFFFEh
0x1800170af  movzx   r9d, word ptr [r8]
0x1800170b3  cmp     [rcx], r9w
0x1800170b7  jz      short loc_18001709E
0x1800170b9  cmp     r10, 3Dh ; '='
0x1800170bd  jnz     short loc_1800170E4
0x1800170bf  mov     rcx, rax
0x1800170c2  lea     r8, aWindowsManagem_3+7Ah; ""
0x1800170c9  cmp     rcx, rdx
0x1800170cc  jz      loc_180017218
0x1800170d2  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800170d6  add     rcx, 0FFFFFFFFFFFFFFFEh
0x1800170da  movzx   r9d, word ptr [r8]
0x1800170de  cmp     [rcx], r9w
0x1800170e2  jz      short loc_1800170C9
0x1800170e4  cmp     r10, 3Bh ; ';'
0x1800170e8  jnz     short loc_18001710F
0x1800170ea  mov     rcx, rax
0x1800170ed  lea     r8, aWindowsManagem_16+76h; ""
0x1800170f4  cmp     rcx, rdx
0x1800170f7  jz      loc_180017251
0x1800170fd  add     r8, 0FFFFFFFFFFFFFFFEh
0x180017101  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180017105  movzx   r9d, word ptr [r8]
0x180017109  cmp     [rcx], r9w
0x18001710d  jz      short loc_1800170F4
0x18001710f  cmp     r10, 3Ch ; '<'
0x180017113  jnz     short loc_18001713A
0x180017115  mov     rcx, rax
0x180017118  lea     r8, aWindowsManagem_4+78h; ""
0x18001711f  cmp     rcx, rdx
0x180017122  jz      loc_18001728A
0x180017128  add     r8, 0FFFFFFFFFFFFFFFEh
0x18001712c  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180017130  movzx   r9d, word ptr [r8]
0x180017134  cmp     [rcx], r9w
0x180017138  jz      short loc_18001711F
0x18001713a  cmp     r10, 3Fh ; '?'
0x18001713e  jnz     short loc_180017165
0x180017140  mov     rcx, rax
0x180017143  lea     r8, aWindowsManagem_5+7Eh; ""
0x18001714a  cmp     rcx, rdx
0x18001714d  jz      loc_1800172C3
0x180017153  add     r8, 0FFFFFFFFFFFFFFFEh
0x180017157  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18001715b  movzx   r9d, word ptr [r8]
0x18001715f  cmp     [rcx], r9w
0x180017163  jz      short loc_18001714A
0x180017165  cmp     r10, 41h ; 'A'
0x180017169  jnz     short loc_180017190
0x18001716b  mov     rcx, rax
0x18001716e  lea     r8, aWindowsManagem_10+82h; ""
0x180017175  cmp     rcx, rdx
0x180017178  jz      loc_1800172FC
0x18001717e  add     r8, 0FFFFFFFFFFFFFFFEh
0x180017182  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180017186  movzx   r9d, word ptr [r8]
0x18001718a  cmp     [rcx], r9w
0x18001718e  jz      short loc_180017175
0x180017190  cmp     r10, 3Bh ; ';'
0x180017194  jnz     short loc_1800171BB
0x180017196  mov     rcx, rax
0x180017199  lea     r8, aWindowsManagem_8+76h; ""
0x1800171a0  cmp     rcx, rdx
0x1800171a3  jz      loc_180017335
0x1800171a9  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800171ad  add     rcx, 0FFFFFFFFFFFFFFFEh
0x1800171b1  movzx   r9d, word ptr [r8]
0x1800171b5  cmp     [rcx], r9w
0x1800171b9  jz      short loc_1800171A0
0x1800171bb  cmp     r10, 37h ; '7'
0x1800171bf  jnz     short loc_1800171E3
0x1800171c1  lea     rcx, aWindowsManagem_13+6Eh; ""
0x1800171c8  cmp     rax, rdx
0x1800171cb  jz      loc_18001736E
0x1800171d1  add     rcx, 0FFFFFFFFFFFFFFFEh
0x1800171d5  add     rax, 0FFFFFFFFFFFFFFFEh
0x1800171d9  movzx   r8d, word ptr [rcx]
0x1800171dd  cmp     [rax], r8w
0x1800171e1  jz      short loc_1800171C8
0x1800171e3  lea     rdx, aWindowsManagem_6; "Windows.Management.Update.WindowsSoftwa"...
0x1800171ea  lea     rcx, [rbp+var_10]
0x1800171ee  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x1800171f3  lea     r8, [rbp+var_10]
0x1800171f7  mov     rdx, r11
0x1800171fa  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800171ff  test    al, al
0x180017201  jz      loc_1800173D2
0x180017207  lea     rcx, [rbp+arg_0]
0x18001720b  call    ??$make@UWindowsSoftwareUpdateProviderActionResult@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180017210  mov     rcx, rax
0x180017213  jmp     loc_1800173B9
0x180017218  mov     ecx, 20h ; ' '; Size
0x18001721d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017222  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017229  mov     rcx, rax
0x18001722c  mov     [rax], rbx
0x18001722f  mov     [rax+8], rbx
0x180017233  add     rax, 10h
0x180017237  mov     [rax], rdx
0x18001723a  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateAppPackageInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateAppPackageInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateAppPackageInfoFactory>::`vftable'
0x180017241  mov     [rax+8], rdx
0x180017245  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateAppPackageInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateAppPackageInfo>::`vftable'
0x18001724c  jmp     loc_1800175A8
0x180017251  mov     ecx, 20h ; ' '; Size
0x180017256  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001725b  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017262  mov     rcx, rax
0x180017265  mov     [rax], rbx
0x180017268  mov     [rax+8], rbx
0x18001726c  add     rax, 10h
0x180017270  mov     [rax], rdx
0x180017273  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateApprovalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateApprovalInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateApprovalInfoFactory>::`vftable'
0x18001727a  mov     [rax+8], rdx
0x18001727e  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateApprovalInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateApprovalInfo>::`vftable'
0x180017285  jmp     loc_1800175A8
0x18001728a  mov     ecx, 20h ; ' '; Size
0x18001728f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017294  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x18001729b  mov     rcx, rax
0x18001729e  mov     [rax], rbx
0x1800172a1  mov     [rax+8], rbx
0x1800172a5  add     rax, 10h
0x1800172a9  mov     [rax], rdx
0x1800172ac  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateExecutionInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateExecutionInfoFactory>::`vftable'
0x1800172b3  mov     [rax+8], rdx
0x1800172b7  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo>::`vftable'
0x1800172be  jmp     loc_1800175A8
0x1800172c3  mov     ecx, 20h ; ' '; Size
0x1800172c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800172cd  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x1800172d4  mov     rcx, rax
0x1800172d7  mov     [rax], rbx
0x1800172da  mov     [rax+8], rbx
0x1800172de  add     rax, 10h
0x1800172e2  mov     [rax], rdx
0x1800172e5  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateLocalizationInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateLocalizationInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateLocalizationInfoFactory>::`vftable'
0x1800172ec  mov     [rax+8], rdx
0x1800172f0  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateLocalizationInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateLocalizationInfo>::`vftable'
0x1800172f7  jmp     loc_1800175A8
0x1800172fc  mov     ecx, 20h ; ' '; Size
0x180017301  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017306  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x18001730d  mov     rcx, rax
0x180017310  mov     [rax], rbx
0x180017313  mov     [rax+8], rbx
0x180017317  add     rax, 10h
0x18001731b  mov     [rax], rdx
0x18001731e  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateOptionalActionInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalActionInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalActionInfoFactory>::`vftable'
0x180017325  mov     [rax+8], rdx
0x180017329  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateOptionalActionInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalActionInfo>::`vftable'
0x180017330  jmp     loc_1800175A8
0x180017335  mov     ecx, 20h ; ' '; Size
0x18001733a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001733f  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180017346  mov     rcx, rax
0x180017349  mov     [rax], rbx
0x18001734c  mov     [rax+8], rbx
0x180017350  add     rax, 10h
0x180017354  mov     [rax], rdx
0x180017357  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateOptionalInfo@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateOptionalInfoFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo,winrt::Windows::Management::Update::IWindowsSoftwareUpdateOptionalInfoFactory>::`vftable'
0x18001735e  mov     [rax+8], rdx
0x180017362  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateOptionalInfo@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateOptionalInfo>::`vftable'
0x180017369  jmp     loc_1800175A8
0x18001736e  mov     ecx, 20h ; ' '; Size
0x180017373  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017378  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateExecutionInfo@factory_implementation@Update@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateExecutionInfo,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x18001737f  mov     [rax], rbx
0x180017382  lea     rcx, [rax+10h]
0x180017386  mov     [rax+8], rbx
0x18001738a  mov     [rcx], rdx
0x18001738d  lea     rdx, ??_7?$produce@UWindowsSoftwareUpdateProvider@factory_implementation@Update@Management@Windows@winrt@@UIWindowsSoftwareUpdateProviderFactory@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider,winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderFactory>::`vftable'
0x180017394  mov     [rcx+8], rdx
0x180017398  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001739f  lea     rdx, ??_7?$heap_implements@UWindowsSoftwareUpdateProvider@factory_implementation@Update@Management@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Management::Update::factory_implementation::WindowsSoftwareUpdateProvider>::`vftable'
0x1800173a6  mov     [rbp+arg_0], rcx
0x1800173aa  mov     [rax], rdx
0x1800173ad  lea     rcx, [rbp+arg_0]
0x1800173b1  mov     qword ptr [rax+8], 1
0x1800173b9  call    ?detach_abi@winrt@@YAPEAX$$QEAUIUnknown@Foundation@Windows@1@@Z; winrt::detach_abi(winrt::Windows::Foundation::IUnknown &&)
0x1800173be  lea     rcx, [rbp+arg_0]; this
0x1800173c2  mov     rbx, rax
0x1800173c5  call    ??1IWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider(void)
0x1800173ca  mov     rax, rbx
0x1800173cd  jmp     loc_1800175BA
0x1800173d2  lea     rdx, aWindowsManagem_7; "Windows.Management.Update.WindowsSoftwa"...
0x1800173d9  lea     rcx, [rbp+var_10]
0x1800173dd  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x1800173e2  lea     r8, [rbp+var_10]
0x1800173e6  mov     rdx, r11
0x1800173e9  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800173ee  test    al, al
0x1800173f0  jz      short loc_180017400
0x1800173f2  lea     rcx, [rbp+arg_0]
0x1800173f6  call    ??$make@UWindowsSoftwareUpdateProviderStatus@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x1800173fb  jmp     loc_180017210
0x180017400  lea     rdx, aWindowsManagem_18; "Windows.Management.Update.WindowsSoftwa"...
0x180017407  lea     rcx, [rbp+var_10]
0x18001740b  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x180017410  lea     r8, [rbp+var_10]
0x180017414  mov     rdx, r11
0x180017417  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x18001741c  test    al, al
0x18001741e  jz      short loc_18001742E
0x180017420  lea     rcx, [rbp+arg_0]
0x180017424  call    ??$make@UWindowsSoftwareUpdateResult@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180017429  jmp     loc_180017210
0x18001742e  lea     rdx, aWindowsManagem_11; "Windows.Management.Update.WindowsSoftwa"...
0x180017435  lea     rcx, [rbp+var_10]
0x180017439  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x18001743e  lea     r8, [rbp+var_10]
0x180017442  mov     rdx, r11
0x180017445  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x18001744a  test    al, al
0x18001744c  jz      short loc_18001745C
0x18001744e  lea     rcx, [rbp+arg_0]
0x180017452  call    ??$make@UWindowsSoftwareUpdateScanResult@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180017457  jmp     loc_180017210
0x18001745c  lea     rdx, aWindowsManagem_19; "Windows.Management.Update.WindowsSoftwa"...
0x180017463  lea     rcx, [rbp+var_10]
0x180017467  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x18001746c  lea     r8, [rbp+var_10]
0x180017470  mov     rdx, r11
0x180017473  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180017478  test    al, al
0x18001747a  jz      short loc_18001748A
0x18001747c  lea     rcx, [rbp+arg_0]
0x180017480  call    ??$make@UWindowsSoftwareUpdateVersion@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x180017485  jmp     loc_180017210
0x18001748a  lea     rdx, aWindowsManagem_17; "Windows.Management.Update.WindowsUpdate"...
0x180017491  lea     rcx, [rbp+var_10]
0x180017495  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x18001749a  lea     r8, [rbp+var_10]
0x18001749e  mov     rdx, r11
0x1800174a1  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800174a6  test    al, al
0x1800174a8  jz      short loc_1800174B8
0x1800174aa  lea     rcx, [rbp+arg_0]
0x1800174ae  call    ??$make@UWindowsUpdateAdministrator@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x1800174b3  jmp     loc_180017210
0x1800174b8  lea     rdx, aWindowsManagem_1; "Windows.Management.Update.WindowsUpdate"...
0x1800174bf  lea     rcx, [rbp+var_10]
0x1800174c3  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x1800174c8  lea     r8, [rbp+var_10]
0x1800174cc  mov     rdx, r11
0x1800174cf  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800174d4  test    al, al
0x1800174d6  jz      short loc_1800174E6
0x1800174d8  lea     rcx, [rbp+arg_0]
0x1800174dc  call    ??$make@UWindowsUpdateApprovalData@factory_implementation@Update@Management@Windows@winrt@@$$V@winrt@@YA?A_PXZ
0x1800174e1  jmp     loc_180017210
0x1800174e6  lea     rdx, aWindowsManagem_2; "Windows.Management.Update.WindowsUpdate"...
0x1800174ed  lea     rcx, [rbp+var_10]
0x1800174f1  call    ??0?$basic_string_view@GU?$char_traits@G@std@@@std@@QEAA@QEBG@Z; std::basic_string_view<ushort>::basic_string_view<ushort,std::char_traits<ushort>>(ushort const * const)
0x1800174f6  lea     r8, [rbp+var_10]
0x1800174fa  mov     rdx, r11
0x1800174fd  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180017502  test    al, al
  ... truncated ...
```
