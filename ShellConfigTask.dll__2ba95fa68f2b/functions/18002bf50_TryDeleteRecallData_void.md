# TryDeleteRecallData(void)

- ea: `0x18002bf50`
- end: `0x18002c44d`
- name: `?TryDeleteRecallData@@YAJXZ`
- size: `1277`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d050`

## callees

- `0x180002590`
- `0x180002998`
- `0x18000f29c`
- `0x180013890`
- `0x18002189c`
- `0x1800248a0`
- `0x180027d98`
- `0x180028010`
- `0x1800282d8`
- `0x18002869c`
- `0x180029644`
- `0x1800299f4`
- `0x18002a1f8`
- `0x18002bf50`
- `0x18002e27c`
- `0x18002e79c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bfe3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c034`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c2c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c336`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c387`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c3bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bfe3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c034`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c2c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c336`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c387`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c3bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c41d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c41d`

## pseudocode

```c
__int64 TryDeleteRecallData(void)
{
  int v0; // r14d
  _QWORD *v1; // rax
  int UserWorkingDirectories; // esi
  __int64 v3; // rdi
  __int64 v4; // rdi
  _QWORD *i; // rsi
  _QWORD *v6; // r15
  __int64 v7; // r8
  _QWORD *v8; // rdx
  _DWORD *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r8
  _QWORD *v12; // rdx
  _DWORD *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rdi
  __int64 v16; // rdi
  char *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  void *v19; // rbx
  LPVOID pv; // [rsp+20h] [rbp-148h] BYREF
  _QWORD v22[2]; // [rsp+28h] [rbp-140h] BYREF
  _DWORD *v23; // [rsp+38h] [rbp-130h]
  _DWORD *v24; // [rsp+40h] [rbp-128h] BYREF
  __int128 v25; // [rsp+48h] [rbp-120h] BYREF
  __int64 v26; // [rsp+58h] [rbp-110h]
  __int128 v27; // [rsp+60h] [rbp-108h] BYREF
  __int64 v28; // [rsp+70h] [rbp-F8h]
  __int64 v29; // [rsp+78h] [rbp-F0h]
  __int128 v30; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v31; // [rsp+90h] [rbp-D8h]
  __int64 v32; // [rsp+98h] [rbp-D0h]
  __int128 v33; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-B8h]
  __int64 v35; // [rsp+B8h] [rbp-B0h]
  __int128 v36; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-98h]
  __int64 v38; // [rsp+D8h] [rbp-90h]
  _BYTE v39[32]; // [rsp+E0h] [rbp-88h] BYREF
  _BYTE Src[32]; // [rsp+100h] [rbp-68h] BYREF

  v0 = 0;
  LODWORD(v23) = 0;
  pv = 0;
  v1 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v1 + 8LL, v22);
  v25 = 0;
  v26 = 0;
  UserWorkingDirectories = GetUserWorkingDirectories(&v25);
  v3 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(&pv);
  v24 = (_DWORD *)v3;
  if ( v3 )
    _InterlockedAdd((volatile signed __int32 *)(v3 + 288), 1u);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 200));
  ++*(_DWORD *)(v3 + 240);
  *(_DWORD *)(v3 + 272) = UserWorkingDirectories;
  tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(&v24);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl'::`2'::impl) )
  {
    v4 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(&pv);
    v24 = (_DWORD *)v4;
    if ( v4 )
      _InterlockedAdd((volatile signed __int32 *)(v4 + 288), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 200));
    ++*(_DWORD *)(v4 + 240);
    *(_DWORD *)(v4 + 276) = UserWorkingDirectories;
    tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(&v24);
  }
  if ( UserWorkingDirectories < 0 )
  {
    v15 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(&pv);
    v22[0] = v15;
    if ( v15 )
      _InterlockedAdd((volatile signed __int32 *)(v15 + 288), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 200));
    ++*(_DWORD *)(v15 + 240);
    *(_DWORD *)(v15 + 280) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(v22);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl'::`2'::impl) )
    {
      v16 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(&pv);
      v22[0] = v16;
      if ( v16 )
        _InterlockedAdd((volatile signed __int32 *)(v16 + 288), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 200));
      ++*(_DWORD *)(v16 + 240);
      *(_DWORD *)(v16 + 284) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(v22);
    }
  }
  else
  {
    v6 = (_QWORD *)*((_QWORD *)&v25 + 1);
    for ( i = (_QWORD *)v25; i != v6; i += 4 )
    {
      v7 = -1;
      do
        ++v7;
      while ( aAppdataLocalCo[v7] );
      v30 = 0;
      v31 = 0;
      v32 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v30, L"AppData\\Local\\CoreAIPlatform.00\\UKP", v7);
      if ( i[3] <= 7u )
        v8 = i;
      else
        v8 = (_QWORD *)*i;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v27, v8, i[2]);
      std::filesystem::operator/(Src, (struct std::filesystem::path *)&v27, (std::filesystem *)&v30);
      std::wstring::~wstring(&v27);
      std::wstring::~wstring(&v30);
      v9 = operator new(0x18u);
      v9[2] = 1;
      *((_QWORD *)v9 + 2) = &pv;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)v9 = &winrt::impl::variadic_delegate<_lambda_1a0270f7638d532f133ef47fc8d485f4_,void,std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> &>::`vftable';
      v23 = v9;
      if ( (int)ForEachUniqueDirectoryHandle((struct std::filesystem::path *)Src) < 0 )
      {
        v10 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(&pv);
        v22[0] = v10;
        if ( v10 )
          _InterlockedAdd((volatile signed __int32 *)(v10 + 288), 1u);
        EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 200));
        ++*(_DWORD *)(v10 + 240);
        *(_DWORD *)(v10 + 280) = 2;
        tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(v22);
      }
      v0 |= 0x1Fu;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl'::`2'::impl) )
      {
        v11 = -1;
        do
          ++v11;
        while ( aAppdataLocalPa[v11] );
        v36 = 0;
        v37 = 0;
        v38 = 0;
        std::wstring::_Construct<1,unsigned short const *>(
          &v36,
          L"AppData\\Local\\packages\\MicrosoftWindows.Client.AIX_cw5n1h2txyewy\\settings",
          v11);
        if ( i[3] <= 7u )
          v12 = i;
        else
          v12 = (_QWORD *)*i;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v33, v12, i[2]);
        std::filesystem::operator/(v39, (struct std::filesystem::path *)&v33, (std::filesystem *)&v36);
        std::wstring::~wstring(&v33);
        std::wstring::~wstring(&v36);
        v13 = operator new(0x18u);
        v13[2] = 1;
        *((_QWORD *)v13 + 2) = &pv;
        _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
        *(_QWORD *)v13 = &winrt::impl::variadic_delegate<_lambda_ec0f780715fc02ca6d1d3142df673352_,void,std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> &>::`vftable';
        v24 = v13;
        if ( (int)ForEachSettingDirectoryHandle((struct std::filesystem::path *)v39) < 0 )
        {
          v14 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(&pv);
          v22[0] = v14;
          if ( v14 )
            _InterlockedAdd((volatile signed __int32 *)(v14 + 288), 1u);
          EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 200));
          ++*(_DWORD *)(v14 + 240);
          *(_DWORD *)(v14 + 284) = 3;
          tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(v22);
        }
        v0 |= 0x3E0u;
        std::wstring::~wstring(v39);
      }
      std::wstring::~wstring(Src);
    }
  }
  if ( pv )
  {
    v17 = (char *)pv + 8;
    v18 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    *((_DWORD *)v17 + 16) |= 0x300u;
    if ( *((_QWORD *)v17 + 30) )
      tip2::details::shared_data<0,0,0>::complete_helper(v17, 2);
    if ( v18 )
      LeaveCriticalSection(v18);
  }
  std::vector<std::wstring>::~vector<std::wstring>(&v25);
  v19 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(v19);
    CoTaskMemFree(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18002bf50  push    rbx
0x18002bf52  push    rsi
0x18002bf53  push    rdi
0x18002bf54  push    r12
0x18002bf56  push    r14
0x18002bf58  push    r15
0x18002bf5a  sub     rsp, 138h
0x18002bf61  mov     rax, cs:__security_cookie
0x18002bf68  xor     rax, rsp
0x18002bf6b  mov     [rsp+168h+var_48], rax
0x18002bf73  xor     r12d, r12d
0x18002bf76  mov     r14d, r12d
0x18002bf79  mov     dword ptr [rsp+168h+var_130], r12d
0x18002bf7e  mov     [rsp+168h+pv], r12
0x18002bf83  lea     rcx, [rsp+168h+pv]
0x18002bf88  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)
0x18002bf8d  mov     rcx, [rax]
0x18002bf90  add     rcx, 8
0x18002bf94  lea     rdx, [rsp+168h+var_140]
0x18002bf99  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18002bf9e  nop
0x18002bf9f  xorps   xmm0, xmm0
0x18002bfa2  movdqu  [rsp+168h+var_120], xmm0
0x18002bfa8  mov     [rsp+168h+var_110], r12
0x18002bfad  lea     rcx, [rsp+168h+var_120]
0x18002bfb2  call    ?GetUserWorkingDirectories@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetUserWorkingDirectories(std::vector<std::wstring> &)
0x18002bfb7  mov     esi, eax
0x18002bfb9  lea     rcx, [rsp+168h+pv]
0x18002bfbe  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)
0x18002bfc3  mov     rdi, [rax]
0x18002bfc6  mov     [rsp+168h+var_128], rdi
0x18002bfcb  lea     ebx, [r12+1]
0x18002bfd0  test    rdi, rdi
0x18002bfd3  jz      short loc_18002BFDC
0x18002bfd5  lock add [rdi+120h], ebx
0x18002bfdc  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18002bfe3  call    cs:__imp_EnterCriticalSection
0x18002bfe9  add     [rdi+0F0h], ebx
0x18002bfef  mov     [rdi+110h], esi
0x18002bff5  lea     rcx, [rsp+168h+var_128]
0x18002bffa  call    ??1?$test_data_control@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)
0x18002bfff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59302972@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972> `wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl(void)'::`2'::impl
0x18002c006  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(void)
0x18002c00b  test    al, al
0x18002c00d  jz      short loc_18002C050
0x18002c00f  lea     rcx, [rsp+168h+pv]
0x18002c014  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)
0x18002c019  mov     rdi, [rax]
0x18002c01c  mov     [rsp+168h+var_128], rdi
0x18002c021  test    rdi, rdi
0x18002c024  jz      short loc_18002C02D
0x18002c026  lock add [rdi+120h], ebx
0x18002c02d  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18002c034  call    cs:__imp_EnterCriticalSection
0x18002c03a  add     [rdi+0F0h], ebx
0x18002c040  mov     [rdi+114h], esi
0x18002c046  lea     rcx, [rsp+168h+var_128]
0x18002c04b  call    ??1?$test_data_control@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)
0x18002c050  test    esi, esi
0x18002c052  js      loc_18002C311
0x18002c058  mov     rsi, qword ptr [rsp+168h+var_120]
0x18002c05d  mov     r15, qword ptr [rsp+168h+var_120+8]
0x18002c062  cmp     rsi, r15
0x18002c065  jz      loc_18002C3A3
0x18002c06b  mov     rdx, cs:off_180034620; "AppData\\Local\\CoreAIPlatform.00\\UKP"
0x18002c072  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c076  inc     r8
0x18002c079  cmp     [rdx+r8*2], r12w
0x18002c07e  jnz     short loc_18002C076
0x18002c080  xorps   xmm0, xmm0
0x18002c083  movups  [rsp+168h+var_E8], xmm0
0x18002c08b  mov     [rsp+168h+var_D8], r12
0x18002c093  mov     [rsp+168h+var_D0], r12
0x18002c09b  lea     rcx, [rsp+168h+var_E8]
0x18002c0a3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c0a8  nop
0x18002c0a9  cmp     qword ptr [rsi+18h], 7
0x18002c0ae  jbe     short loc_18002C0B5
0x18002c0b0  mov     rdx, [rsi]
0x18002c0b3  jmp     short loc_18002C0B8
0x18002c0b5  mov     rdx, rsi
0x18002c0b8  xorps   xmm0, xmm0
0x18002c0bb  movups  [rsp+168h+var_108], xmm0
0x18002c0c0  mov     [rsp+168h+var_F8], r12
0x18002c0c5  mov     [rsp+168h+var_F0], r12
0x18002c0ca  mov     r8, [rsi+10h]
0x18002c0ce  lea     rcx, [rsp+168h+var_108]
0x18002c0d3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c0d8  nop
0x18002c0d9  lea     r8, [rsp+168h+var_E8]; this
0x18002c0e1  lea     rdx, [rsp+168h+var_108]; struct std::filesystem::path *
0x18002c0e6  lea     rcx, [rsp+168h+Src]; Src
0x18002c0ee  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18002c0f3  nop
0x18002c0f4  lea     rcx, [rsp+168h+var_108]
0x18002c0f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c0fe  nop
0x18002c0ff  lea     rcx, [rsp+168h+var_E8]
0x18002c107  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c10c  mov     ecx, 18h; Size
0x18002c111  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c116  mov     [rax+8], ebx
0x18002c119  lea     rcx, [rsp+168h+pv]
0x18002c11e  mov     [rax+10h], rcx
0x18002c122  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002c129  lea     rcx, ??_7?$variadic_delegate@V_lambda_1a0270f7638d532f133ef47fc8d485f4_@@XAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@impl@winrt@@6B@; const winrt::impl::variadic_delegate<_lambda_1a0270f7638d532f133ef47fc8d485f4_,void,std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &>::`vftable'
0x18002c130  mov     [rax], rcx
0x18002c133  mov     [rsp+168h+var_130], rax
0x18002c138  lea     rdx, [rsp+168h+var_130]
0x18002c13d  lea     rcx, [rsp+168h+Src]; struct std::filesystem::path *
0x18002c145  call    ?ForEachUniqueDirectoryHandle@@YAJAEBVpath@filesystem@std@@U?$delegate@$$A6AXAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z@winrt@@@Z; ForEachUniqueDirectoryHandle(std::filesystem::path const &,winrt::delegate<void (std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)>)
0x18002c14a  test    eax, eax
0x18002c14c  jns     short loc_18002C193
0x18002c14e  lea     rcx, [rsp+168h+pv]
0x18002c153  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)
0x18002c158  mov     rdi, [rax]
0x18002c15b  mov     [rsp+168h+var_140], rdi
0x18002c160  test    rdi, rdi
0x18002c163  jz      short loc_18002C16C
0x18002c165  lock add [rdi+120h], ebx
0x18002c16c  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18002c173  call    cs:__imp_EnterCriticalSection
0x18002c179  add     [rdi+0F0h], ebx
0x18002c17f  mov     dword ptr [rdi+118h], 2
0x18002c189  lea     rcx, [rsp+168h+var_140]
0x18002c18e  call    ??1?$test_data_control@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)
0x18002c193  or      r14d, 1Fh
0x18002c197  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59302972@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972> `wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl(void)'::`2'::impl
0x18002c19e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(void)
0x18002c1a3  test    al, al
0x18002c1a5  jz      loc_18002C2FB
0x18002c1ab  mov     rdx, cs:off_180034628; "AppData\\Local\\packages\\MicrosoftWind"...
0x18002c1b2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c1b6  inc     r8
0x18002c1b9  cmp     [rdx+r8*2], r12w
0x18002c1be  jnz     short loc_18002C1B6
0x18002c1c0  xorps   xmm0, xmm0
0x18002c1c3  movups  [rsp+168h+var_A8], xmm0
0x18002c1cb  mov     [rsp+168h+var_98], r12
0x18002c1d3  mov     [rsp+168h+var_90], r12
0x18002c1db  lea     rcx, [rsp+168h+var_A8]
0x18002c1e3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c1e8  nop
0x18002c1e9  cmp     qword ptr [rsi+18h], 7
0x18002c1ee  jbe     short loc_18002C1F5
0x18002c1f0  mov     rdx, [rsi]
0x18002c1f3  jmp     short loc_18002C1F8
0x18002c1f5  mov     rdx, rsi
0x18002c1f8  xorps   xmm0, xmm0
0x18002c1fb  movups  [rsp+168h+var_C8], xmm0
0x18002c203  mov     [rsp+168h+var_B8], r12
0x18002c20b  mov     [rsp+168h+var_B0], r12
0x18002c213  mov     r8, [rsi+10h]
0x18002c217  lea     rcx, [rsp+168h+var_C8]
0x18002c21f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002c224  nop
0x18002c225  lea     r8, [rsp+168h+var_A8]; this
0x18002c22d  lea     rdx, [rsp+168h+var_C8]; struct std::filesystem::path *
0x18002c235  lea     rcx, [rsp+168h+var_88]; Src
0x18002c23d  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18002c242  nop
0x18002c243  lea     rcx, [rsp+168h+var_C8]
0x18002c24b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c250  nop
0x18002c251  lea     rcx, [rsp+168h+var_A8]
0x18002c259  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c25e  mov     ecx, 18h; Size
0x18002c263  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c268  mov     [rax+8], ebx
0x18002c26b  lea     rcx, [rsp+168h+pv]
0x18002c270  mov     [rax+10h], rcx
0x18002c274  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002c27b  lea     rcx, ??_7?$variadic_delegate@V_lambda_ec0f780715fc02ca6d1d3142df673352_@@XAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@impl@winrt@@6B@; const winrt::impl::variadic_delegate<_lambda_ec0f780715fc02ca6d1d3142df673352_,void,std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &>::`vftable'
0x18002c282  mov     [rax], rcx
0x18002c285  mov     [rsp+168h+var_128], rax
0x18002c28a  lea     rdx, [rsp+168h+var_128]
0x18002c28f  lea     rcx, [rsp+168h+var_88]; struct std::filesystem::path *
0x18002c297  call    ?ForEachSettingDirectoryHandle@@YAJAEBVpath@filesystem@std@@U?$delegate@$$A6AXAEBVpath@filesystem@std@@AEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z@winrt@@@Z; ForEachSettingDirectoryHandle(std::filesystem::path const &,winrt::delegate<void (std::filesystem::path const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)>)
0x18002c29c  test    eax, eax
0x18002c29e  jns     short loc_18002C2E6
0x18002c2a0  lea     rcx, [rsp+168h+pv]
0x18002c2a5  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)
0x18002c2aa  mov     rdi, [rax]
0x18002c2ad  mov     [rsp+168h+var_140], rdi
0x18002c2b2  test    rdi, rdi
0x18002c2b5  jz      short loc_18002C2BE
0x18002c2b7  lock add [rdi+120h], ebx
0x18002c2be  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18002c2c5  call    cs:__imp_EnterCriticalSection
0x18002c2cb  add     [rdi+0F0h], ebx
0x18002c2d1  mov     dword ptr [rdi+11Ch], 3
0x18002c2db  lea     rcx, [rsp+168h+var_140]
0x18002c2e0  call    ??1?$test_data_control@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)
0x18002c2e5  nop
0x18002c2e6  or      r14d, 3E0h
0x18002c2ed  lea     rcx, [rsp+168h+var_88]
0x18002c2f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c2fa  nop
0x18002c2fb  lea     rcx, [rsp+168h+Src]
0x18002c303  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c308  add     rsi, 20h ; ' '
0x18002c30c  jmp     loc_18002C062
0x18002c311  lea     rcx, [rsp+168h+pv]
0x18002c316  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)
0x18002c31b  mov     rdi, [rax]
0x18002c31e  mov     [rsp+168h+var_140], rdi
0x18002c323  test    rdi, rdi
0x18002c326  jz      short loc_18002C32F
0x18002c328  lock add [rdi+120h], ebx
0x18002c32f  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18002c336  call    cs:__imp_EnterCriticalSection
0x18002c33c  add     [rdi+0F0h], ebx
0x18002c342  mov     [rdi+118h], ebx
0x18002c348  lea     rcx, [rsp+168h+var_140]
0x18002c34d  call    ??1?$test_data_control@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)
0x18002c352  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59302972@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972> `wil::Feature<__WilFeatureTraits_Feature_59302972>::GetImpl(void)'::`2'::impl
0x18002c359  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59302972@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59302972>::__private_IsEnabled(void)
0x18002c35e  test    al, al
0x18002c360  jz      short loc_18002C3A3
0x18002c362  lea     rcx, [rsp+168h+pv]
0x18002c367  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::ensure_data(void)
0x18002c36c  mov     rdi, [rax]
0x18002c36f  mov     [rsp+168h+var_140], rdi
0x18002c374  test    rdi, rdi
0x18002c377  jz      short loc_18002C380
0x18002c379  lock add [rdi+120h], ebx
0x18002c380  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18002c387  call    cs:__imp_EnterCriticalSection
0x18002c38d  add     [rdi+0F0h], ebx
0x18002c393  mov     [rdi+11Ch], ebx
0x18002c399  lea     rcx, [rsp+168h+var_140]
0x18002c39e  call    ??1?$test_data_control@V?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>::~test_data_control<tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>>(void)
0x18002c3a3  mov     rax, [rsp+168h+pv]
0x18002c3a8  test    rax, rax
0x18002c3ab  jz      short loc_18002C3ED
0x18002c3ad  lea     rbx, [rax+8]
0x18002c3b1  lea     rdi, [rbx+0C0h]
0x18002c3b8  mov     rcx, rdi; lpCriticalSection
0x18002c3bb  call    cs:__imp_EnterCriticalSection
0x18002c3c1  or      dword ptr [rbx+40h], 300h
0x18002c3c8  cmp     [rbx+0F0h], r12
0x18002c3cf  jz      short loc_18002C3DE
0x18002c3d1  mov     edx, 2
0x18002c3d6  mov     rcx, rbx
0x18002c3d9  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18002c3de  test    rdi, rdi
0x18002c3e1  jz      short loc_18002C3ED
0x18002c3e3  mov     rcx, rdi; lpCriticalSection
0x18002c3e6  call    cs:__imp_LeaveCriticalSection
0x18002c3ec  nop
0x18002c3ed  lea     rcx, [rsp+168h+var_120]
0x18002c3f2  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18002c3f7  nop
0x18002c3f8  mov     rbx, [rsp+168h+pv]
0x18002c3fd  test    rbx, rbx
0x18002c400  jz      short loc_18002C423
0x18002c402  or      eax, 0FFFFFFFFh
0x18002c405  lock xadd [rbx+120h], eax
0x18002c40d  cmp     eax, 1
0x18002c410  jnz     short loc_18002C423
0x18002c412  mov     rcx, rbx
0x18002c415  call    ??1?$merged_data@U_tip_RecallDataDeletedTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>::~merged_data<_tip_RecallDataDeletedTest,_tip_RecallDataDeletedTest>(void)
0x18002c41a  mov     rcx, rbx; pv
0x18002c41d  call    cs:__imp_CoTaskMemFree
0x18002c423  xor     eax, eax
0x18002c425  jmp     short loc_18002C42B
0x18002c427  mov     eax, dword ptr [rsp+168h+var_130]
0x18002c42b  mov     rcx, [rsp+168h+var_48]
0x18002c433  xor     rcx, rsp; StackCookie
0x18002c436  call    __security_check_cookie
0x18002c43b  add     rsp, 138h
0x18002c442  pop     r15
0x18002c444  pop     r14
0x18002c446  pop     r12
0x18002c448  pop     rdi
0x18002c449  pop     rsi
0x18002c44a  pop     rbx
0x18002c44b  retn
```
