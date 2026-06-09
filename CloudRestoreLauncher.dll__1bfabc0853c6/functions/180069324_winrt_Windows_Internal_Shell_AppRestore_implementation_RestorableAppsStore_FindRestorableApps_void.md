# winrt::Windows::Internal::Shell::AppRestore::implementation::RestorableAppsStore::FindRestorableApps(void)

- ea: `0x180069324`
- end: `0x180069914`
- name: `?FindRestorableApps@RestorableAppsStore@implementation@AppRestore@Shell@Internal@Windows@winrt@@QEAA?AU?$IVectorView@URestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@Collections@Foundation@67@XZ`
- size: `1520`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800692d0`

## callees

- `0x18000cbbc`
- `0x18000d688`
- `0x180012ab4`
- `0x180012b84`
- `0x180015140`
- `0x1800156f4`
- `0x1800162a4`
- `0x18001666c`
- `0x180016d30`
- `0x18001cfa4`
- `0x18001d1f4`
- `0x18001d234`
- `0x180022308`
- `0x1800356e4`
- `0x180035d88`
- `0x18003628c`
- `0x180036c44`
- `0x180043f40`
- `0x180044840`
- `0x18004623c`
- `0x1800596bc`
- `0x18005b944`
- `0x18005bf50`
- `0x18005c068`
- `0x180068890`
- `0x180068980`
- `0x1800689f4`
- `0x180068d30`
- `0x180068eb4`
- `0x180069324`
- `0x18006aa54`
- `0x18006aa8c`
- `0x18006ac7c`
- `0x18012d010`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800697a2`
- `OLE32!CoTaskMemAlloc` at `0x1800697a2`

## string_xrefs

- `0x180069902`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 *__fastcall winrt::Windows::Internal::Shell::AppRestore::implementation::RestorableAppsStore::FindRestorableApps(
        __int64 a1,
        __int64 *a2)
{
  __int64 **v3; // r12
  _QWORD *v4; // rdi
  _QWORD *v5; // rsi
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  __int64 *v11; // rsi
  void (__fastcall *v12)(__int64 *, _BYTE *, __int64); // rdi
  __int64 v13; // rax
  const struct winrt::hstring *v14; // rdx
  __int64 *v15; // rdi
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rax
  AppCompatInfo *v19; // rcx
  int v20; // edi
  __int64 *v21; // rsi
  __int64 (__fastcall *v22)(__int64 *, int *, _QWORD, __int64); // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  const unsigned __int16 *v25; // rax
  AppCompatInfo *v26; // rdi
  __int64 *v27; // rsi
  __int64 (__fastcall *v28)(__int64 *, int *, __int64, __int64); // rdi
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rax
  __int64 v34; // rdx
  int v35; // r14d
  int v36; // eax
  int v37; // eax
  int v38; // r10d
  __int64 v39; // rax
  unsigned int v40; // eax
  LPVOID v41; // rax
  wil::details::in1diag3 *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rbx
  unsigned int v45; // eax
  __int64 *v46; // rbx
  int v48; // [rsp+20h] [rbp-E0h]
  char *v49; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v50; // [rsp+40h] [rbp-C0h] BYREF
  char v51; // [rsp+48h] [rbp-B8h]
  int v52; // [rsp+4Ch] [rbp-B4h]
  __int64 v53; // [rsp+50h] [rbp-B0h] BYREF
  int v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+68h] [rbp-98h]
  char v57[8]; // [rsp+70h] [rbp-90h] BYREF
  char v58[8]; // [rsp+78h] [rbp-88h] BYREF
  char v59[8]; // [rsp+80h] [rbp-80h] BYREF
  char v60[8]; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v61; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v62; // [rsp+98h] [rbp-68h]
  __int64 v63; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v64; // [rsp+A8h] [rbp-58h]
  _QWORD *v65; // [rsp+B0h] [rbp-50h] BYREF
  int v66; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v67; // [rsp+C0h] [rbp-40h]
  void *v68; // [rsp+E8h] [rbp-18h]
  char v69[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v70[32]; // [rsp+100h] [rbp+0h] BYREF
  char v71[8]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v72; // [rsp+128h] [rbp+28h]
  _BYTE v73[112]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]
  __int64 v75; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 *v76; // [rsp+1E8h] [rbp+E8h]
  char *v77; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v78; // [rsp+1F8h] [rbp+F8h] BYREF

  v76 = a2;
  v3 = (__int64 **)(a1 + 40);
  (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 40) + 8LL))(*(_QWORD *)(a1 + 40), v71);
  v4 = operator new(0x48u);
  memset_0(v4, 0, 0x48u);
  v5 = v4 + 2;
  v62 = v4 + 2;
  v4[2] = &winrt::impl::produce<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::CompatibleFileInfo>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Shell::AppRestore::CompatibleFileInfo>>::`vftable';
  v4[3] = &winrt::impl::produce<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>>::`vftable';
  v4[4] = &winrt::impl::produce<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>(v4 + 1);
  v4[1] = 1;
  *((_DWORD *)v4 + 10) = 0;
  v4[6] = 0;
  v4[7] = 0;
  v4[8] = 0;
  *v4 = &winrt::impl::heap_implements<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>>::`vftable';
  v65 = v4 + 2;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v77,
    &word_1801382A0,
    -1);
  if ( !v77 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v6, v7);
  v8 = 24;
  v9 = v72;
  v64 = v72;
  v10 = (_QWORD *)*v72;
  while ( v10 != v9 )
  {
    v78 = (__int64)(v10 + 3);
    v11 = *v3;
    v12 = *(void (__fastcall **)(__int64 *, _BYTE *, __int64))(**v3 + 40);
    v13 = winrt::hstring::hstring((winrt::hstring *)v57, (const struct winrt::hstring *)(v10 + 2));
    v12(v11, v70, v13);
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v14 = (const struct winrt::hstring *)(v10 + 2);
    if ( *(_BYTE *)(a1 + 36) )
    {
      v15 = *v3;
      v16 = **v3;
      v49 = v58;
      v17 = winrt::hstring::hstring((winrt::hstring *)v58, v14);
      if ( !*(_BYTE *)(a1 + 36) )
        std::_Throw_bad_optional_access();
      v18 = (*(__int64 (__fastcall **)(__int64 *, int *, _QWORD, __int64))(v16 + 24))(
              v15,
              &v66,
              *(unsigned int *)(a1 + 32),
              v17);
      AppCompatInfo::operator=(&v50, v18);
      v19 = (AppCompatInfo *)&v66;
LABEL_7:
      AppCompatInfo::~AppCompatInfo(v19);
      goto LABEL_8;
    }
    v21 = *v3;
    v22 = *(__int64 (__fastcall **)(__int64 *, int *, _QWORD, __int64))(**v3 + 24);
    v23 = winrt::hstring::hstring((winrt::hstring *)v59, v14);
    v24 = v22(v21, &v66, 0, v23);
    AppCompatInfo::operator=(&v50, v24);
    AppCompatInfo::~AppCompatInfo((AppCompatInfo *)&v66);
    v20 = (_DWORD)v10 + 24;
    v25 = winrt::hstring::c_str((winrt::hstring *)(v10 + 5));
    if ( !(unsigned int)std::basic_string_view<unsigned short>::compare(&c_externalMsiCatalogSource, v25) )
    {
      if ( v51 )
      {
        v26 = AppCompatInfo::AppCompatInfo((AppCompatInfo *)v73, (const struct AppCompatInfo *)&v50);
        v8 |= 1u;
      }
      else
      {
        v27 = *v3;
        v28 = *(__int64 (__fastcall **)(__int64 *, int *, __int64, __int64))(**v3 + 24);
        v29 = winrt::hstring::hstring((winrt::hstring *)v60, (const struct winrt::hstring *)(v10 + 2));
        v26 = (AppCompatInfo *)v28(v27, &v66, 1, v29);
        v8 |= 2u;
      }
      if ( &v50 != (__int64 *)v26 )
      {
        v30 = *(_QWORD *)v26;
        *(_QWORD *)v26 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach(&v50, v30);
      }
      v51 = *((_BYTE *)v26 + 8);
      v52 = *((_DWORD *)v26 + 3);
      v31 = (__int64 *)((char *)v26 + 16);
      if ( &v53 != (__int64 *)((char *)v26 + 16) )
      {
        v32 = *v31;
        *v31 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach(&v53, v32);
      }
      v54 = *((_DWORD *)v26 + 6);
      v33 = (__int64 *)((char *)v26 + 32);
      if ( &v55 != (__int64 *)((char *)v26 + 32) )
      {
        v34 = *v33;
        *v33 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach(&v55, v34);
      }
      v56 = *((_QWORD *)v26 + 5);
      if ( (v8 & 2) != 0 )
      {
        v8 &= ~2u;
        AppCompatInfo::~AppCompatInfo((AppCompatInfo *)&v66);
      }
      if ( (v8 & 1) != 0 )
      {
        v8 &= ~1u;
        v19 = (AppCompatInfo *)v73;
        goto LABEL_7;
      }
LABEL_8:
      v20 = v78;
    }
    if ( v51 )
    {
      v52 |= 0x40000u;
      v61 = winrt::hstring::c_str((winrt::hstring *)&v50);
      v49 = v77;
      v78 = 0;
      v35 = v8 | 0x40;
      v36 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short *,unsigned short [3],unsigned short const *>(
              &v78,
              &v49,
              L", ",
              &v61);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7B3,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          (const char *)(unsigned int)v36,
          v48);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v77,
        &v78);
      v8 = v35 & 0xFFFFFFBF;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v78);
    }
    v68 = operator new(0xF0u);
    v37 = std::shared_ptr<IRestorableAppDataStore>::shared_ptr<IRestorableAppDataStore>(v69, v3);
    v39 = winrt::impl::heap_implements<winrt::Windows::Internal::Shell::AppRestore::implementation::RestorableApp>::heap_implements<winrt::Windows::Internal::Shell::AppRestore::implementation::RestorableApp>(
            v38,
            v37,
            v20,
            (unsigned int)&v50,
            (__int64)v70);
    v63 = (v39 + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)v39 >> 64);
    v8 |= 0x80u;
    v66 = 0;
    v67 = 0;
    v5 = v62;
    v40 = (*(__int64 (__fastcall **)(_QWORD *))(*v62 + 104LL))(v62);
    winrt::check_hresult(&v75, v40, &v66);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v63);
    AppCompatInfo::~AppCompatInfo((AppCompatInfo *)&v50);
    AppMatchingInfo::~AppMatchingInfo((AppMatchingInfo *)v70);
    v10 = (_QWORD *)*v10;
    v9 = v64;
  }
  if ( !*(_BYTE *)(a1 + 56) )
  {
    v75 = 0;
    v41 = CoTaskMemAlloc(0x120u);
    if ( !v41 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v42);
    v78 = tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>(
            v41,
            0);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::operator=(
      &v75,
      &v78);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>(&v78);
    v43 = v75;
    if ( v75 && tip2::details::shared_data<1,0,0>::is_running(v75 + 8) )
    {
      v44 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>>::ensure_data(&v75);
      v78 = v44;
      if ( v44 )
        _InterlockedIncrement((volatile signed __int32 *)(v44 + 280));
      tip2::details::shared_data<1,0,0>::begin_update(v44 + 8);
      *(_BYTE *)(v44 + 272) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>>(&v78);
    }
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(v43, PreventedTaskbarPinsForAllApp, v77);
    *(_BYTE *)(a1 + 56) = 1;
    wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>(&v75);
  }
  v78 = 0;
  v66 = 0;
  v67 = 0;
  v45 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v5 + 64LL))(v5, &v78);
  winrt::check_hresult(&v75, v45, &v66);
  v46 = v76;
  *v76 = v78;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v77);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v65);
  std::_Hash<std::_Umap_traits<winrt::hstring,AppMetaData const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,AppMetaData const>>,0>>::~_Hash<std::_Umap_traits<winrt::hstring,AppMetaData const,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,AppMetaData const>>,0>>(v71);
  return v46;
}

```

## disassembly

```asm
0x180069324  mov     [rsp-8+arg_8], rdx
0x180069329  push    rbp
0x18006932a  push    rbx
0x18006932b  push    rsi
0x18006932c  push    rdi
0x18006932d  push    r12
0x18006932f  push    r13
0x180069331  push    r14
0x180069333  push    r15
0x180069335  lea     rbp, [rsp-98h]
0x18006933d  sub     rsp, 198h
0x180069344  mov     r15, rcx
0x180069347  xor     r13d, r13d
0x18006934a  mov     [rsp+1D0h+var_1A0], r13d
0x18006934f  lea     r12, [rcx+28h]
0x180069353  mov     rcx, [r12]
0x180069357  mov     rax, [rcx]
0x18006935a  lea     rdx, [rbp+0D0h+var_B0]
0x18006935e  mov     rax, [rax+8]
0x180069362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069367  nop
0x180069368  lea     ebx, [r13+48h]
0x18006936c  mov     ecx, ebx; Size
0x18006936e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069373  mov     rdi, rax
0x180069376  mov     r8d, ebx; Size
0x180069379  xor     edx, edx; Val
0x18006937b  mov     rcx, rax; void *
0x18006937e  call    memset_0
0x180069383  lea     rsi, [rdi+10h]
0x180069387  mov     [rbp+0D0h+var_138], rsi
0x18006938b  lea     rax, ??_7?$produce@U?$NonAgileVector@UCompatibleFileInfo@AppRestore@Shell@Internal@Windows@winrt@@@@U?$IVector@UCompatibleFileInfo@AppRestore@Shell@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::CompatibleFileInfo>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Shell::AppRestore::CompatibleFileInfo>>::`vftable'
0x180069392  mov     [rsi], rax
0x180069395  lea     rax, ??_7?$produce@U?$NonAgileVector@URestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@@U?$IVectorView@URestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>>::`vftable'
0x18006939c  mov     [rsi+8], rax
0x1800693a0  lea     rax, ??_7?$produce@U?$NonAgileVector@URestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@@U?$IIterable@URestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>>::`vftable'
0x1800693a7  mov     [rsi+10h], rax
0x1800693ab  lea     rcx, [rdi+8]
0x1800693af  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800693b4  mov     qword ptr [rdi+8], 1
0x1800693bc  xor     eax, eax
0x1800693be  mov     [rdi+28h], eax
0x1800693c1  mov     [rdi+30h], r13
0x1800693c5  mov     [rdi+38h], r13
0x1800693c9  mov     [rdi+40h], r13
0x1800693cd  lea     rax, ??_7?$heap_implements@U?$NonAgileVector@URestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@@@impl@winrt@@6B@; const winrt::impl::heap_implements<NonAgileVector<winrt::Windows::Internal::Shell::AppRestore::RestorableApp>>::`vftable'
0x1800693d4  mov     [rdi], rax
0x1800693d7  mov     [rbp+0D0h+var_120], rsi
0x1800693db  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800693df  lea     rdx, word_1801382A0
0x1800693e6  lea     rcx, [rbp+0D0h+arg_10]
0x1800693ed  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800693f2  mov     [rsp+1D0h+var_1A0], 28h ; '('
0x1800693fa  mov     rcx, [rbp+0D8h]; this
0x180069401  cmp     [rbp+0D0h+arg_10], r13
0x180069408  jz      loc_1800698EE
0x18006940e  lea     r14d, [r13+18h]
0x180069412  mov     [rsp+1D0h+var_1A0], r14d
0x180069417  mov     rax, [rbp+0D0h+var_A8]
0x18006941b  mov     [rbp+0D0h+var_128], rax
0x18006941f  mov     rbx, [rax]
0x180069422  cmp     rbx, rax
0x180069425  jz      loc_18006978C
0x18006942b  lea     r13, [rbx+10h]
0x18006942f  lea     rax, [r13+8]
0x180069433  mov     [rbp+0D0h+arg_18], rax
0x18006943a  mov     rsi, [r12]
0x18006943e  mov     rax, [rsi]
0x180069441  mov     rdi, [rax+28h]
0x180069445  mov     rdx, r13; struct winrt::hstring *
0x180069448  lea     rcx, [rsp+1D0h+var_160]; this
0x18006944d  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180069452  mov     r8, rax
0x180069455  lea     rdx, [rbp+0D0h+var_D0]
0x180069459  mov     rcx, rsi
0x18006945c  mov     rax, rdi
0x18006945f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069464  nop
0x180069465  xor     ecx, ecx
0x180069467  mov     [rsp+1D0h+var_190], rcx
0x18006946c  mov     [rsp+1D0h+var_188], cl
0x180069470  mov     [rsp+1D0h+var_184], ecx
0x180069474  mov     [rsp+1D0h+var_180], rcx
0x180069479  mov     [rsp+1D0h+var_178], ecx
0x18006947d  mov     [rsp+1D0h+var_170], rcx
0x180069482  mov     [rsp+1D0h+var_168], rcx
0x180069487  mov     rdx, r13; struct winrt::hstring *
0x18006948a  cmp     [r15+24h], cl
0x18006948e  jz      short loc_1800694F4
0x180069490  mov     rdi, [r12]
0x180069494  mov     rsi, [rdi]
0x180069497  lea     rax, [rsp+1D0h+var_158]
0x18006949c  mov     [rsp+1D0h+var_198], rax
0x1800694a1  lea     rcx, [rsp+1D0h+var_158]; this
0x1800694a6  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800694ab  nop
0x1800694ac  xor     r13d, r13d
0x1800694af  cmp     [r15+24h], r13b
0x1800694b3  jz      loc_1800698F9
0x1800694b9  mov     r9, rax
0x1800694bc  mov     r8d, [r15+20h]
0x1800694c0  lea     rdx, [rbp+0D0h+var_118]
0x1800694c4  mov     rcx, rdi
0x1800694c7  mov     rax, [rsi+18h]
0x1800694cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800694d0  nop
0x1800694d1  mov     rdx, rax
0x1800694d4  lea     rcx, [rsp+1D0h+var_190]
0x1800694d9  call    ??4AppCompatInfo@@QEAAAEAU0@AEBU0@@Z; AppCompatInfo::operator=(AppCompatInfo const &)
0x1800694de  nop
0x1800694df  lea     rcx, [rbp+0D0h+var_118]; this
0x1800694e3  call    ??1AppCompatInfo@@QEAA@XZ; AppCompatInfo::~AppCompatInfo(void)
0x1800694e8  mov     rdi, [rbp+0D0h+arg_18]
0x1800694ef  jmp     loc_180069656
0x1800694f4  mov     rsi, [r12]
0x1800694f8  mov     rax, [rsi]
0x1800694fb  mov     rdi, [rax+18h]
0x1800694ff  lea     rcx, [rbp+0D0h+var_150]; this
0x180069503  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180069508  mov     r9, rax
0x18006950b  xor     r8d, r8d
0x18006950e  lea     rdx, [rbp+0D0h+var_118]
0x180069512  mov     rcx, rsi
0x180069515  mov     rax, rdi
0x180069518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006951d  nop
0x18006951e  mov     rdx, rax
0x180069521  lea     rcx, [rsp+1D0h+var_190]
0x180069526  call    ??4AppCompatInfo@@QEAAAEAU0@AEBU0@@Z; AppCompatInfo::operator=(AppCompatInfo const &)
0x18006952b  nop
0x18006952c  lea     rcx, [rbp+0D0h+var_118]; this
0x180069530  call    ??1AppCompatInfo@@QEAA@XZ; AppCompatInfo::~AppCompatInfo(void)
0x180069535  lea     rdi, [r13+8]
0x180069539  lea     rcx, [rdi+10h]; this
0x18006953d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180069542  mov     rdx, rax
0x180069545  lea     rcx, ?c_externalMsiCatalogSource@@3V?$basic_string_view@GU?$char_traits@G@std@@@std@@B; std::basic_string_view<ushort> const c_externalMsiCatalogSource
0x18006954c  call    ?compare@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBAHQEBG@Z; std::basic_string_view<ushort>::compare(ushort const * const)
0x180069551  test    eax, eax
0x180069553  jnz     loc_180069653
0x180069559  cmp     [rsp+1D0h+var_188], al
0x18006955d  jz      short loc_180069576
0x18006955f  lea     rdx, [rsp+1D0h+var_190]; struct AppCompatInfo *
0x180069564  lea     rcx, [rbp+0D0h+var_70]; this
0x180069568  call    ??0AppCompatInfo@@QEAA@AEBU0@@Z; AppCompatInfo::AppCompatInfo(AppCompatInfo const &)
0x18006956d  mov     rdi, rax
0x180069570  or      r14d, 1
0x180069574  jmp     short loc_1800695AC
0x180069576  mov     rsi, [r12]
0x18006957a  mov     rax, [rsi]
0x18006957d  mov     rdi, [rax+18h]
0x180069581  mov     rdx, r13; struct winrt::hstring *
0x180069584  lea     rcx, [rbp+0D0h+var_148]; this
0x180069588  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18006958d  mov     r9, rax
0x180069590  mov     r8d, 1
0x180069596  lea     rdx, [rbp+0D0h+var_118]
0x18006959a  mov     rcx, rsi
0x18006959d  mov     rax, rdi
0x1800695a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695a5  mov     rdi, rax
0x1800695a8  or      r14d, 2
0x1800695ac  lea     rax, [rsp+1D0h+var_190]
0x1800695b1  xor     r13d, r13d
0x1800695b4  cmp     rax, rdi
0x1800695b7  jz      short loc_1800695C9
0x1800695b9  mov     rdx, [rdi]
0x1800695bc  mov     [rdi], r13
0x1800695bf  lea     rcx, [rsp+1D0h+var_190]
0x1800695c4  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800695c9  mov     al, [rdi+8]
0x1800695cc  mov     [rsp+1D0h+var_188], al
0x1800695d0  mov     eax, [rdi+0Ch]
0x1800695d3  mov     [rsp+1D0h+var_184], eax
0x1800695d7  lea     rax, [rdi+10h]
0x1800695db  lea     rcx, [rsp+1D0h+var_180]
0x1800695e0  cmp     rcx, rax
0x1800695e3  jz      short loc_1800695F5
0x1800695e5  mov     rdx, [rax]
0x1800695e8  mov     [rax], r13
0x1800695eb  lea     rcx, [rsp+1D0h+var_180]
0x1800695f0  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800695f5  mov     eax, [rdi+18h]
0x1800695f8  mov     [rsp+1D0h+var_178], eax
0x1800695fc  lea     rax, [rdi+20h]
0x180069600  lea     rcx, [rsp+1D0h+var_170]
0x180069605  cmp     rcx, rax
0x180069608  jz      short loc_18006961A
0x18006960a  mov     rdx, [rax]
0x18006960d  mov     [rax], r13
0x180069610  lea     rcx, [rsp+1D0h+var_170]
0x180069615  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18006961a  mov     eax, [rdi+28h]
0x18006961d  mov     dword ptr [rsp+1D0h+var_168], eax
0x180069621  mov     eax, [rdi+2Ch]
0x180069624  mov     dword ptr [rsp+1D0h+var_168+4], eax
0x180069628  test    r14b, 2
0x18006962c  jz      short loc_18006963C
0x18006962e  and     r14d, 0FFFFFFFDh
0x180069632  lea     rcx, [rbp+0D0h+var_118]; this
0x180069636  call    ??1AppCompatInfo@@QEAA@XZ; AppCompatInfo::~AppCompatInfo(void)
0x18006963b  nop
0x18006963c  test    r14b, 1
0x180069640  jz      loc_1800694E8
0x180069646  and     r14d, 0FFFFFFFEh
0x18006964a  lea     rcx, [rbp+0D0h+var_70]
0x18006964e  jmp     loc_1800694E3
0x180069653  xor     r13d, r13d
0x180069656  cmp     [rsp+1D0h+var_188], r13b
0x18006965b  jz      short loc_1800696DB
0x18006965d  bts     [rsp+1D0h+var_184], 12h
0x180069663  lea     rcx, [rsp+1D0h+var_190]; this
0x180069668  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18006966d  mov     [rbp+0D0h+var_140], rax
0x180069671  mov     rax, [rbp+0D0h+arg_10]
0x180069678  mov     [rsp+1D0h+var_198], rax
0x18006967d  mov     [rbp+0D0h+arg_18], r13
0x180069684  or      r14d, 40h
0x180069688  mov     [rsp+1D0h+var_1A0], r14d
0x18006968d  lea     r9, [rbp+0D0h+var_140]
0x180069691  lea     r8, asc_18013EDEC; ", "
0x180069698  lea     rdx, [rsp+1D0h+var_198]
0x18006969d  lea     rcx, [rbp+0D0h+arg_18]
0x1800696a4  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAG$$BY02GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEAGAEAY02$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort *,ushort [3],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort * const &,ushort const (&)[3],ushort const * const &)
0x1800696a9  mov     rcx, [rbp+0D8h]; this
0x1800696b0  test    eax, eax
0x1800696b2  js      loc_1800698FF
0x1800696b8  lea     rdx, [rbp+0D0h+arg_18]
0x1800696bf  lea     rcx, [rbp+0D0h+arg_10]
0x1800696c6  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800696cb  and     r14d, 0FFFFFFBFh
0x1800696cf  lea     rcx, [rbp+0D0h+arg_18]
0x1800696d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800696db  mov     ecx, 0F0h; Size
0x1800696e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800696e5  mov     r10, rax
0x1800696e8  mov     [rbp+0D0h+var_E8], rax
0x1800696ec  mov     rdx, r12
0x1800696ef  lea     rcx, [rbp+0D0h+var_E0]
0x1800696f3  call    ??0?$shared_ptr@UIRestorableAppDataStore@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<IRestorableAppDataStore>::shared_ptr<IRestorableAppDataStore>(std::shared_ptr<IRestorableAppDataStore> const &)
0x1800696f8  lea     rcx, [rbp+0D0h+var_D0]
0x1800696fc  mov     qword ptr [rsp+1D0h+var_1B0], rcx
0x180069701  lea     r9, [rsp+1D0h+var_190]
0x180069706  mov     r8, rdi
0x180069709  mov     rdx, rax
0x18006970c  mov     rcx, r10
0x18006970f  call    ??0?$heap_implements@URestorableApp@implementation@AppRestore@Shell@Internal@Windows@winrt@@@impl@winrt@@QEAA@V?$shared_ptr@UIRestorableAppDataStore@@@std@@AEBUAppMetaData@@AEBUAppCompatInfo@@AEBUAppMatchingInfo@@@Z; winrt::impl::heap_implements<winrt::Windows::Internal::Shell::AppRestore::implementation::RestorableApp>::heap_implements<winrt::Windows::Internal::Shell::AppRestore::implementation::RestorableApp>(std::shared_ptr<IRestorableAppDataStore>,AppMetaData const &,AppCompatInfo const &,AppMatchingInfo const &)
0x180069714  nop
0x180069715  lea     rcx, [rax+10h]
0x180069719  neg     rax
0x18006971c  sbb     rdx, rdx
0x18006971f  and     rdx, rcx
0x180069722  mov     [rbp+0D0h+var_130], rdx
0x180069726  bts     r14d, 7
0x18006972b  mov     [rsp+1D0h+var_1A0], r14d
0x180069730  mov     [rbp+0D0h+var_118], r13d
0x180069734  xorps   xmm0, xmm0
0x180069737  movdqu  [rbp+0D0h+var_110], xmm0
0x18006973c  mov     rsi, [rbp+0D0h+var_138]
0x180069740  mov     rax, [rsi]
0x180069743  mov     rcx, rsi
0x180069746  mov     rax, [rax+68h]
0x18006974a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006974f  lea     r8, [rbp+0D0h+var_118]
0x180069753  mov     edx, eax
0x180069755  lea     rcx, [rbp+0D0h+arg_0]
0x18006975c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180069761  nop
0x180069762  lea     rcx, [rbp+0D0h+var_130]; this
0x180069766  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18006976b  nop
0x18006976c  lea     rcx, [rsp+1D0h+var_190]; this
0x180069771  call    ??1AppCompatInfo@@QEAA@XZ; AppCompatInfo::~AppCompatInfo(void)
0x180069776  nop
0x180069777  lea     rcx, [rbp+0D0h+var_D0]; this
0x18006977b  call    ??1AppMatchingInfo@@QEAA@XZ; AppMatchingInfo::~AppMatchingInfo(void)
0x180069780  mov     rbx, [rbx]
0x180069783  mov     rax, [rbp+0D0h+var_128]
0x180069787  jmp     loc_180069422
0x18006978c  cmp     [r15+38h], r13b
0x180069790  jnz     loc_180069865
0x180069796  mov     [rbp+0D0h+arg_0], r13
0x18006979d  mov     ecx, 120h; cb
0x1800697a2  call    cs:__imp_CoTaskMemAlloc
0x1800697a8  test    rax, rax
0x1800697ab  jz      loc_1800698E8
0x1800697b1  xor     edx, edx
0x1800697b3  mov     rcx, rax
0x1800697b6  call    ??0?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>(_GUID *)
0x1800697bb  mov     [rbp+0D0h+arg_18], rax
0x1800697c2  lea     rdx, [rbp+0D0h+arg_18]
0x1800697c9  lea     rcx, [rbp+0D0h+arg_0]
0x1800697d0  call    ??4?$com_ptr_t@V?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy> &&)
0x1800697d5  lea     rcx, [rbp+0D0h+arg_18]
0x1800697dc  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PreventTaskbarPinsTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PreventTaskbarPinsTipTest,_tip_PreventTaskbarPinsTipTest>,wil::err_returncode_policy>(void)
0x1800697e1  mov     rcx, [rbp+0D0h+arg_0]
0x1800697e8  test    rcx, rcx
0x1800697eb  jz      short loc_180069838
0x1800697ed  add     rcx, 8
0x1800697f1  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
  ... truncated ...
```
