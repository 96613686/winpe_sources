# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUpdateItems(void)

- ea: `0x180022404`
- end: `0x180022a05`
- name: `?GetUpdateItems@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@QEAA?AU?$IVectorView@USystemUpdateItem@Update@System@Windows@winrt@@@Collections@Foundation@56@XZ`
- size: `1537`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800223b0`

## callees

- `0x180002dc0`
- `0x180004b90`
- `0x180005954`
- `0x180005a1c`
- `0x180008cec`
- `0x18000ab28`
- `0x18001cffc`
- `0x18001d06c`
- `0x18001d0c8`
- `0x18001dee4`
- `0x18001e45c`
- `0x18001f378`
- `0x180022404`
- `0x180022a0c`
- `0x180022ba4`
- `0x1800253c4`
- `0x1800257a8`
- `0x180027068`
- `0x1800271ac`
- `0x18002b010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800224e8`
- `OLEAUT32!__imp_VariantInit` at `0x1800224e8`
- `OLEAUT32!__imp_VariantClear` at `0x180022930`
- `OLEAUT32!__imp_VariantClear` at `0x180022930`

## string_xrefs

- `0x180022477`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x1800224b5`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x18002251f`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x18002255d`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x1800225f2`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x18002262b`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x180022664`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`
- `0x18002269d`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUpdateItems(
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *a1,
        __int64 a2)
{
  int v3; // eax
  int v4; // eax
  unsigned int i; // edi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  double v12; // xmm0_8
  double v13; // xmm0_8
  _QWORD *v14; // rax
  __int64 result; // rax
  int v16; // [rsp+20h] [rbp-148h]
  __int64 v17; // [rsp+50h] [rbp-118h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-110h] BYREF
  __int64 v19; // [rsp+60h] [rbp-108h] BYREF
  __int128 v20; // [rsp+68h] [rbp-100h] BYREF
  double v21; // [rsp+78h] [rbp-F0h] BYREF
  int v22; // [rsp+80h] [rbp-E8h] BYREF
  int v23; // [rsp+84h] [rbp-E4h] BYREF
  int updated; // [rsp+88h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+90h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+98h] [rbp-D0h] BYREF
  _lambda_12ef4a55c56a96ec7ad58335194b061f_ *v27; // [rsp+A0h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-C0h]
  unsigned __int16 *v29; // [rsp+B8h] [rbp-B0h] BYREF
  winrt::impl *v30; // [rsp+C0h] [rbp-A8h] BYREF
  unsigned __int16 *v31; // [rsp+C8h] [rbp-A0h] BYREF
  winrt::impl *v32; // [rsp+D0h] [rbp-98h] BYREF
  _BYTE v33[8]; // [rsp+D8h] [rbp-90h] BYREF
  _BYTE v34[8]; // [rsp+E0h] [rbp-88h] BYREF
  _BYTE v35[16]; // [rsp+E8h] [rbp-80h] BYREF
  double v36; // [rsp+F8h] [rbp-70h] BYREF
  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *v37; // [rsp+100h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+108h] [rbp-60h] BYREF
  const wil::ResultException *v39; // [rsp+120h] [rbp-48h] BYREF
  __int128 v40; // [rsp+128h] [rbp-40h] BYREF
  int v41; // [rsp+138h] [rbp-30h]
  __int128 v42; // [rsp+140h] [rbp-28h] BYREF
  __int64 v43; // [rsp+150h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v37 = a1;
  v21 = *(double *)&a2;
  try
  {
    winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(a1, &v26);
    v19 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v26 + 56LL))(v26, 1, &v19);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2B4,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v3,
        v16);
    v18 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 40LL))(v19, &v18);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2B7,
        (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
        (const char *)(unsigned int)v4,
        v16);
    std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(&v27);
    for ( i = 0; i < v18; ++i )
    {
      VariantInit(&pvarg);
      v17 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 24LL))(v19, i, &v17);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2BF,
          (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
          (const char *)(unsigned int)v6,
          v16);
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v17 + 168LL))(v17, 0, &pvarg);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2C0,
          (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
          (const char *)(unsigned int)v7,
          v16);
      if ( pvarg.vt == 19 && pvarg.lVal )
      {
        v29 = 0;
        v31 = 0;
        v42 = 0;
        v43 = 0;
        v40 = 0;
        v41 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 24LL))(v17, &v42);
        if ( v8 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2CA,
            (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
            (const char *)(unsigned int)v8,
            v16);
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v17 + 48LL))(v17, &v29);
        if ( v9 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2CB,
            (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
            (const char *)(unsigned int)v9,
            v16);
        v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v17 + 56LL))(v17, &v31);
        if ( v10 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2CC,
            (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
            (const char *)(unsigned int)v10,
            v16);
        v11 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 72LL))(v17, &v40);
        if ( v11 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2CD,
            (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
            (const char *)(unsigned int)v11,
            v16);
        updated = winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UpdateStatusToUpdateItemState((unsigned int)v42);
        winrt::hstring::hstring((winrt::hstring *)&v30, v29);
        winrt::hstring::hstring((winrt::hstring *)v35, &v30);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v30);
        winrt::hstring::hstring((winrt::hstring *)&v32, v31);
        winrt::hstring::hstring((winrt::hstring *)v34, &v32);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
        v20 = v40;
        winrt::to_hstring(v33, &v20);
        v23 = v41;
        if ( (_DWORD)v43 == 4 )
        {
          v12 = (double)SHIDWORD(v43) / 100.0;
        }
        else if ( (_DWORD)v43 == 10 )
        {
          v12 = DOUBLE_1_0;
        }
        else
        {
          v12 = 0.0;
        }
        v21 = v12;
        v13 = 0.0;
        if ( (_DWORD)v43 == 10 )
          v13 = (double)SHIDWORD(v43) / 100.0;
        v36 = v13;
        v22 = DWORD1(v42);
        winrt::make<winrt::Windows::System::Update::implementation::SystemUpdateItem,enum winrt::Windows::System::Update::SystemUpdateItemState &,winrt::hstring &,winrt::hstring &,winrt::hstring &,unsigned int &,double &,double &,long &>(
          &v25,
          &updated,
          (const struct winrt::hstring *)v35,
          (const struct winrt::hstring *)v34,
          (const struct winrt::hstring *)v33,
          &v23,
          (__int64 *)&v21,
          (__int64 *)&v36,
          &v22);
        if ( (_QWORD)v28 == *((_QWORD *)&v28 + 1) )
          std::vector<winrt::Windows::System::Update::SystemUpdateItem>::_Emplace_reallocate<winrt::Windows::System::Update::SystemUpdateItem const &>(
            &v27,
            (_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v28,
            &v25);
        else
          std::vector<winrt::Windows::System::Update::SystemUpdateItem>::_Emplace_back_with_unused_capacity<winrt::Windows::System::Update::SystemUpdateItem const &>((__int64)&v27);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v25);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v33);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v34);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v35);
      }
      if ( v17 )
        winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v17);
      VariantClear(&pvarg);
    }
    v14 = winrt::single_threaded_vector<winrt::Windows::System::Update::SystemUpdateItem,std::allocator<winrt::Windows::System::Update::SystemUpdateItem>>(
            &v21,
            (__int64)&v27);
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
      v14,
      a2);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v21);
    if ( v27 )
    {
      std::_Destroy_range<std::allocator<winrt::Windows::System::Update::SystemUpdateItem>>(
        v27,
        (_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v28);
      std::_Deallocate<16>(v27, (*((_QWORD *)&v28 + 1) - (_QWORD)v27) & 0xFFFFFFFFFFFFFFF8uLL);
      v27 = 0;
      v28 = 0;
    }
    if ( v19 )
      winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v19);
    if ( v26 )
      winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(&v26);
    result = a2;
  }
  catch ( const wil::ResultException *v39 )
  {
    *((_DWORD *)v37 + 14) = *((_DWORD *)v39 + 8);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180022404  mov     [rsp+arg_10], rbx
0x180022409  push    rdi
0x18002240a  sub     rsp, 160h
0x180022411  mov     rax, cs:__security_cookie
0x180022418  xor     rax, rsp
0x18002241b  mov     [rsp+168h+var_10], rax
0x180022423  mov     rbx, rdx
0x180022426  mov     [rsp+168h+var_68], rcx
0x18002242e  mov     [rsp+168h+var_F0], rdx
0x180022433  lea     rdx, [rsp+168h+var_D0]
0x18002243b  call    ?GetUsoSession@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AU?$com_ptr@UIUsoSessionCommon@@@6@XZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetUsoSession(void)
0x180022440  nop
0x180022441  mov     [rsp+168h+var_108], 0
0x18002244a  mov     rcx, [rsp+168h+var_D0]
0x180022452  mov     rax, [rcx]
0x180022455  lea     r8, [rsp+168h+var_108]
0x18002245a  mov     edx, 1
0x18002245f  mov     rax, [rax+38h]
0x180022463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022468  mov     rcx, [rsp+168h]; this
0x180022470  test    eax, eax
0x180022472  jns     short loc_180022488
0x180022474  mov     r9d, eax; char *
0x180022477  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18002247e  mov     edx, 2B4h; void *
0x180022483  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022488  mov     [rsp+168h+var_110], 0
0x180022490  mov     rcx, [rsp+168h+var_108]
0x180022495  mov     rax, [rcx]
0x180022498  lea     rdx, [rsp+168h+var_110]
0x18002249d  mov     rax, [rax+28h]
0x1800224a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224a6  mov     rcx, [rsp+168h]; this
0x1800224ae  test    eax, eax
0x1800224b0  jns     short loc_1800224C6
0x1800224b2  mov     r9d, eax; char *
0x1800224b5  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x1800224bc  mov     edx, 2B7h; void *
0x1800224c1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800224c6  lea     rcx, [rsp+168h+var_C8]
0x1800224ce  call    ??0?$vector@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@V?$allocator@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(void)
0x1800224d3  nop
0x1800224d4  xor     edi, edi
0x1800224d6  cmp     edi, [rsp+168h+var_110]
0x1800224da  jnb     loc_18002293D
0x1800224e0  lea     rcx, [rsp+168h+pvarg]; pvarg
0x1800224e8  call    cs:__imp_VariantInit
0x1800224ee  nop
0x1800224ef  mov     [rsp+168h+var_118], 0
0x1800224f8  mov     rcx, [rsp+168h+var_108]
0x1800224fd  mov     rax, [rcx]
0x180022500  lea     r8, [rsp+168h+var_118]
0x180022505  mov     edx, edi
0x180022507  mov     rax, [rax+18h]
0x18002250b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022510  mov     rcx, [rsp+168h]; this
0x180022518  test    eax, eax
0x18002251a  jns     short loc_180022530
0x18002251c  mov     r9d, eax; char *
0x18002251f  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180022526  mov     edx, 2BFh; void *
0x18002252b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022530  mov     rcx, [rsp+168h+var_118]
0x180022535  mov     rax, [rcx]
0x180022538  lea     r8, [rsp+168h+pvarg]
0x180022540  xor     edx, edx
0x180022542  mov     rax, [rax+0A8h]
0x180022549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002254e  mov     rcx, [rsp+168h]; this
0x180022556  test    eax, eax
0x180022558  jns     short loc_18002256E
0x18002255a  mov     r9d, eax; char *
0x18002255d  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180022564  mov     edx, 2C0h; void *
0x180022569  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002256e  cmp     word ptr [rsp+168h+pvarg], 13h
0x180022577  jnz     loc_180022915
0x18002257d  cmp     dword ptr [rsp+168h+pvarg+8], 0
0x180022585  jz      loc_180022915
0x18002258b  mov     [rsp+168h+var_B0], 0
0x180022597  mov     [rsp+168h+var_A0], 0
0x1800225a3  xorps   xmm0, xmm0
0x1800225a6  xor     eax, eax
0x1800225a8  movups  [rsp+168h+var_28], xmm0
0x1800225b0  mov     [rsp+168h+var_18], rax
0x1800225b8  xorps   xmm1, xmm1
0x1800225bb  movups  [rsp+168h+var_40], xmm1
0x1800225c3  mov     [rsp+168h+var_30], eax
0x1800225ca  mov     rcx, [rsp+168h+var_118]
0x1800225cf  mov     rax, [rcx]
0x1800225d2  lea     rdx, [rsp+168h+var_28]
0x1800225da  mov     rax, [rax+18h]
0x1800225de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225e3  mov     rcx, [rsp+168h]; this
0x1800225eb  test    eax, eax
0x1800225ed  jns     short loc_180022603
0x1800225ef  mov     r9d, eax; char *
0x1800225f2  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x1800225f9  mov     edx, 2CAh; void *
0x1800225fe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022603  mov     rcx, [rsp+168h+var_118]
0x180022608  mov     rax, [rcx]
0x18002260b  lea     rdx, [rsp+168h+var_B0]
0x180022613  mov     rax, [rax+30h]
0x180022617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002261c  mov     rcx, [rsp+168h]; this
0x180022624  test    eax, eax
0x180022626  jns     short loc_18002263C
0x180022628  mov     r9d, eax; char *
0x18002262b  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x180022632  mov     edx, 2CBh; void *
0x180022637  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002263c  mov     rcx, [rsp+168h+var_118]
0x180022641  mov     rax, [rcx]
0x180022644  lea     rdx, [rsp+168h+var_A0]
0x18002264c  mov     rax, [rax+38h]
0x180022650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022655  mov     rcx, [rsp+168h]; this
0x18002265d  test    eax, eax
0x18002265f  jns     short loc_180022675
0x180022661  mov     r9d, eax; char *
0x180022664  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18002266b  mov     edx, 2CCh; void *
0x180022670  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022675  mov     rcx, [rsp+168h+var_118]
0x18002267a  mov     rax, [rcx]
0x18002267d  lea     rdx, [rsp+168h+var_40]
0x180022685  mov     rax, [rax+48h]
0x180022689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002268e  mov     rcx, [rsp+168h]; this
0x180022696  test    eax, eax
0x180022698  jns     short loc_1800226AE
0x18002269a  mov     r9d, eax; char *
0x18002269d  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x1800226a4  mov     edx, 2CDh; void *
0x1800226a9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800226ae  mov     ecx, dword ptr [rsp+168h+var_28]
0x1800226b5  call    ?UpdateStatusToUpdateItemState@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@CA?AW4SystemUpdateItemState@3456@W4tagUpdateStatus@@@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UpdateStatusToUpdateItemState(tagUpdateStatus)
0x1800226ba  mov     [rsp+168h+var_E0], eax
0x1800226c1  mov     rdx, [rsp+168h+var_B0]; unsigned __int16 *
0x1800226c9  lea     rcx, [rsp+168h+var_A8]; this
0x1800226d1  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800226d6  nop
0x1800226d7  lea     rdx, [rsp+168h+var_A8]; struct winrt::hstring *
0x1800226df  lea     rcx, [rsp+168h+var_80]; this
0x1800226e7  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800226ec  nop
0x1800226ed  lea     rcx, [rsp+168h+var_A8]
0x1800226f5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800226fa  mov     rdx, [rsp+168h+var_A0]; unsigned __int16 *
0x180022702  lea     rcx, [rsp+168h+var_98]; this
0x18002270a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18002270f  nop
0x180022710  lea     rdx, [rsp+168h+var_98]; struct winrt::hstring *
0x180022718  lea     rcx, [rsp+168h+var_88]; this
0x180022720  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180022725  nop
0x180022726  lea     rcx, [rsp+168h+var_98]
0x18002272e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022733  mov     eax, dword ptr [rsp+168h+var_40]
0x18002273a  mov     dword ptr [rsp+168h+var_100], eax
0x18002273e  movzx   eax, word ptr [rsp+168h+var_40+4]
0x180022746  mov     word ptr [rsp+168h+var_100+4], ax
0x18002274b  movzx   eax, word ptr [rsp+168h+var_40+6]
0x180022753  mov     word ptr [rsp+168h+var_100+6], ax
0x180022758  mov     al, byte ptr [rsp+168h+var_40+8]
0x18002275f  mov     byte ptr [rsp+168h+var_100+8], al
0x180022763  mov     al, byte ptr [rsp+168h+var_40+9]
0x18002276a  mov     byte ptr [rsp+168h+var_100+9], al
0x18002276e  mov     al, byte ptr [rsp+168h+var_40+0Ah]
0x180022775  mov     byte ptr [rsp+168h+var_100+0Ah], al
0x180022779  mov     al, byte ptr [rsp+168h+var_40+0Bh]
0x180022780  mov     byte ptr [rsp+168h+var_100+0Bh], al
0x180022784  mov     al, byte ptr [rsp+168h+var_40+0Ch]
0x18002278b  mov     byte ptr [rsp+168h+var_100+0Ch], al
0x18002278f  mov     al, byte ptr [rsp+168h+var_40+0Dh]
0x180022796  mov     byte ptr [rsp+168h+var_100+0Dh], al
0x18002279a  mov     al, byte ptr [rsp+168h+var_40+0Eh]
0x1800227a1  mov     byte ptr [rsp+168h+var_100+0Eh], al
0x1800227a5  mov     al, byte ptr [rsp+168h+var_40+0Fh]
0x1800227ac  mov     byte ptr [rsp+168h+var_100+0Fh], al
0x1800227b0  lea     rdx, [rsp+168h+var_100]
0x1800227b5  lea     rcx, [rsp+168h+var_90]
0x1800227bd  call    ?to_hstring@winrt@@YA?AUhstring@1@AEBUguid@1@@Z; winrt::to_hstring(winrt::guid const &)
0x1800227c2  nop
0x1800227c3  mov     eax, [rsp+168h+var_30]
0x1800227ca  mov     [rsp+168h+var_E4], eax
0x1800227d1  mov     rcx, [rsp+168h+var_18]
0x1800227d9  cmp     ecx, 4
0x1800227dc  jnz     short loc_1800227F7
0x1800227de  mov     eax, dword ptr [rsp+168h+var_18+4]
0x1800227e5  xorps   xmm0, xmm0
0x1800227e8  cvtsi2sd xmm0, rax
0x1800227ed  divsd   xmm0, cs:__real@4059000000000000
0x1800227f5  jmp     short loc_180022809
0x1800227f7  cmp     ecx, 0Ah
0x1800227fa  jnz     short loc_180022806
0x1800227fc  movsd   xmm0, cs:__real@3ff0000000000000
0x180022804  jmp     short loc_180022809
0x180022806  xorps   xmm0, xmm0
0x180022809  movsd   [rsp+168h+var_F0], xmm0
0x18002280f  xorps   xmm0, xmm0
0x180022812  cmp     ecx, 0Ah
0x180022815  jnz     short loc_18002282B
0x180022817  mov     eax, dword ptr [rsp+168h+var_18+4]
0x18002281e  cvtsi2sd xmm0, rax
0x180022823  divsd   xmm0, cs:__real@4059000000000000
0x18002282b  movsd   [rsp+168h+var_70], xmm0
0x180022834  mov     eax, dword ptr [rsp+168h+var_28+4]
0x18002283b  mov     [rsp+168h+var_E8], eax
0x180022842  lea     rax, [rsp+168h+var_E8]
0x18002284a  mov     [rsp+168h+var_128], rax
0x18002284f  lea     rax, [rsp+168h+var_70]
0x180022857  mov     [rsp+168h+var_130], rax
0x18002285c  lea     rax, [rsp+168h+var_F0]
0x180022861  mov     [rsp+168h+var_138], rax
0x180022866  lea     rax, [rsp+168h+var_E4]
0x18002286e  mov     [rsp+168h+var_140], rax
0x180022873  lea     rax, [rsp+168h+var_90]
0x18002287b  mov     [rsp+168h+var_148], rax
0x180022880  lea     r9, [rsp+168h+var_88]
0x180022888  lea     r8, [rsp+168h+var_80]
0x180022890  lea     rdx, [rsp+168h+var_E0]
0x180022898  lea     rcx, [rsp+168h+var_D8]
0x1800228a0  call    ??$make@USystemUpdateItem@implementation@Update@System@Windows@winrt@@AEAW4SystemUpdateItemState@3456@AEAUhstring@6@AEAU86@AEAU86@AEAIAEANAEANAEAJ@winrt@@YA?A_PAEAW4SystemUpdateItemState@Update@System@Windows@0@AEAUhstring@0@11AEAIAEAN3AEAJ@Z
0x1800228a5  nop
0x1800228a6  mov     rdx, qword ptr [rsp+168h+var_C0]
0x1800228ae  lea     rcx, [rsp+168h+var_C8]
0x1800228b6  cmp     rdx, qword ptr [rsp+168h+var_C0+8]
0x1800228be  jz      short loc_1800228CF
0x1800228c0  lea     rdx, [rsp+168h+var_D8]
0x1800228c8  call    ??$_Emplace_back_with_unused_capacity@AEBUSystemUpdateItem@Update@System@Windows@winrt@@@?$vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@AEAAAEAUSystemUpdateItem@Update@System@Windows@winrt@@AEBU23456@@Z; std::vector<winrt::Windows::System::Update::SystemUpdateItem>::_Emplace_back_with_unused_capacity<winrt::Windows::System::Update::SystemUpdateItem const &>(winrt::Windows::System::Update::SystemUpdateItem const &)
0x1800228cd  jmp     short loc_1800228DD
0x1800228cf  lea     r8, [rsp+168h+var_D8]
0x1800228d7  call    ??$_Emplace_reallocate@AEBUSystemUpdateItem@Update@System@Windows@winrt@@@?$vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@AEAAPEAUSystemUpdateItem@Update@System@Windows@winrt@@QEAU23456@AEBU23456@@Z; std::vector<winrt::Windows::System::Update::SystemUpdateItem>::_Emplace_reallocate<winrt::Windows::System::Update::SystemUpdateItem const &>(winrt::Windows::System::Update::SystemUpdateItem * const,winrt::Windows::System::Update::SystemUpdateItem const &)
0x1800228dc  nop
0x1800228dd  lea     rcx, [rsp+168h+var_D8]; this
0x1800228e5  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800228ea  nop
0x1800228eb  lea     rcx, [rsp+168h+var_90]
0x1800228f3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800228f8  nop
0x1800228f9  lea     rcx, [rsp+168h+var_88]
0x180022901  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022906  nop
0x180022907  lea     rcx, [rsp+168h+var_80]
0x18002290f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022914  nop
0x180022915  cmp     [rsp+168h+var_118], 0
0x18002291b  jz      short loc_180022928
0x18002291d  lea     rcx, [rsp+168h+var_118]
0x180022922  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x180022927  nop
0x180022928  lea     rcx, [rsp+168h+pvarg]; pvarg
0x180022930  call    cs:__imp_VariantClear
0x180022936  inc     edi
0x180022938  jmp     loc_1800224D6
0x18002293d  lea     rdx, [rsp+168h+var_C8]
0x180022945  lea     rcx, [rsp+168h+var_F0]
0x18002294a  call    ??$single_threaded_vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@USystemUpdateItem@Update@System@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@USystemUpdateItem@Update@System@Windows@winrt@@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::System::Update::SystemUpdateItem,std::allocator<winrt::Windows::System::Update::SystemUpdateItem>>(std::vector<winrt::Windows::System::Update::SystemUpdateItem> &&)
0x18002294f  nop
0x180022950  mov     rdx, rbx
0x180022953  mov     rcx, rax
0x180022956  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(void)
0x18002295b  nop
0x18002295c  lea     rcx, [rsp+168h+var_F0]; this
0x180022961  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180022966  nop
0x180022967  mov     rcx, [rsp+168h+var_C8]; this
0x18002296f  test    rcx, rcx
0x180022972  jz      short loc_1800229B5
0x180022974  mov     rdx, qword ptr [rsp+168h+var_C0]
0x18002297c  call    ??$_Destroy_range@V?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@std@@@std@@YAXPEAUSystemUpdateItem@Update@System@Windows@winrt@@QEAU12345@AEAV?$allocator@USystemUpdateItem@Update@System@Windows@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::Windows::System::Update::SystemUpdateItem>>(winrt::Windows::System::Update::SystemUpdateItem *,winrt::Windows::System::Update::SystemUpdateItem * const,std::allocator<winrt::Windows::System::Update::SystemUpdateItem> &)
0x180022981  mov     rcx, [rsp+168h+var_C8]
0x180022989  mov     rdx, qword ptr [rsp+168h+var_C0+8]
0x180022991  sub     rdx, rcx
0x180022994  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180022998  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002299d  mov     [rsp+168h+var_C8], 0
0x1800229a9  xorps   xmm0, xmm0
0x1800229ac  movdqu  [rsp+168h+var_C0], xmm0
0x1800229b5  cmp     [rsp+168h+var_108], 0
0x1800229bb  jz      short loc_1800229C8
0x1800229bd  lea     rcx, [rsp+168h+var_108]
0x1800229c2  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x1800229c7  nop
0x1800229c8  cmp     [rsp+168h+var_D0], 0
0x1800229d1  jz      short loc_1800229E0
0x1800229d3  lea     rcx, [rsp+168h+var_D0]
0x1800229db  call    ?unconditional_release_ref@?$com_ptr@UIUsoSessionCommon@@@winrt@@AEAAXXZ; winrt::com_ptr<IUsoSessionCommon>::unconditional_release_ref(void)
0x1800229e0  mov     rax, rbx
0x1800229e3  mov     rcx, [rsp+168h+var_10]
0x1800229eb  xor     rcx, rsp; StackCookie
0x1800229ee  call    __security_check_cookie
0x1800229f3  mov     rbx, [rsp+168h+arg_10]
0x1800229fb  add     rsp, 160h
0x180022a02  pop     rdi
0x180022a03  retn
```
