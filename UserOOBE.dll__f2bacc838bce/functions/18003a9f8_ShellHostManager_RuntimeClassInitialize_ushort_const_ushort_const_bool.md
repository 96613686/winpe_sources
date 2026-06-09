# ShellHostManager::RuntimeClassInitialize(ushort const *,ushort const *,bool)

- ea: `0x18003a9f8`
- end: `0x18003adb3`
- name: `?RuntimeClassInitialize@ShellHostManager@@QEAAJPEBG0_N@Z`
- size: `955`
- prototype: `int(ShellHostManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003381c`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x18000e270`
- `0x180032ef4`
- `0x180032f7c`
- `0x18003349c`
- `0x1800335cc`
- `0x180033bc0`
- `0x180036028`
- `0x1800368d8`
- `0x180036e3c`
- `0x180037090`
- `0x1800370c8`
- `0x1800376b0`
- `0x18003a9f8`
- `0x18003aea8`
- `0x18003c024`
- `0x18003c060`
- `0x18003c480`
- `0x18003e1a8`
- `0x18003eed4`
- `0x18003f184`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003abb8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003abb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ShellHostManager::RuntimeClassInitialize(
        ShellHostManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  ShellHostManager *v8; // rax
  int v9; // edi
  __int64 v10; // rbx
  ShellHostManager *v11; // rax
  char v12; // di
  __int64 v13; // rbx
  int v14; // eax
  HRESULT v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  LPVOID v18; // rsi
  __int64 (__fastcall *v19)(LPVOID, __int64 *, GUID *, char *); // rdi
  const char *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  const char *v24; // rax
  int ppv; // [rsp+20h] [rbp-60h]
  __int64 v27; // [rsp+30h] [rbp-50h] BYREF
  __int64 v28; // [rsp+38h] [rbp-48h]
  _BYTE v29[56]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v30; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  LPVOID v32; // [rsp+C0h] [rbp+40h] BYREF
  ShellHostManager *v33; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v34; // [rsp+D0h] [rbp+50h] BYREF
  int v35; // [rsp+D8h] [rbp+58h]

  v35 = 0;
  CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[50],unsigned short const (&)[13]>();
  v32 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::start_and_watch_errors(
    &v32,
    v29);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>(&v32);
  *((_OWORD *)this + 11) = *(_OWORD *)(v30 + 152);
  *((_BYTE *)this + 32) = a4;
  if ( a2 )
  {
    v8 = (ShellHostManager *)winrt::hstring::hstring((winrt::hstring *)&v33, a2);
    v9 = 1;
  }
  else
  {
    v8 = (ShellHostManager *)winrt::hstring::hstring((winrt::hstring *)&v32, &qword_180054928);
    v9 = 2;
  }
  v35 = v9;
  if ( (ShellHostManager *)((char *)this + 40) != v8 )
  {
    v10 = *(_QWORD *)v8;
    *(_QWORD *)v8 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::close((char *)this + 40);
    winrt::handle_type<winrt::impl::hstring_traits>::close((char *)this + 40);
    *((_QWORD *)this + 5) = v10;
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    v35 = v9;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    v35 = v9;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v33);
  }
  if ( a3 )
  {
    v11 = (ShellHostManager *)winrt::hstring::hstring((winrt::hstring *)&v33, a3);
    v12 = v9 | 4;
  }
  else
  {
    v11 = (ShellHostManager *)winrt::hstring::hstring((winrt::hstring *)&v32, &qword_180054928);
    v12 = v9 | 8;
  }
  if ( (ShellHostManager *)((char *)this + 48) != v11 )
  {
    v13 = *(_QWORD *)v11;
    *(_QWORD *)v11 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::close((char *)this + 48);
    winrt::handle_type<winrt::impl::hstring_traits>::close((char *)this + 48);
    *((_QWORD *)this + 6) = v13;
  }
  if ( (v12 & 8) != 0 )
  {
    v12 &= ~8u;
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v32);
  }
  if ( (v12 & 4) != 0 )
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v33);
  v14 = SetFullscreenCXHRunning(1u);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36C,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)(unsigned int)v14,
      ppv);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging>::GetImpl'::`2'::impl) )
    goto LABEL_28;
  v32 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v15 = CoCreateInstance(
          &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
          0,
          0x404u,
          &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
          &v32);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v18 = v32;
    v19 = *(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, char *))(*(_QWORD *)v32 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 168);
    v15 = v19(v18, qword_18005C558, &GUID_1b69f343_1af8_43fb_bfe3_b27c09b74d0b, (char *)this + 168);
    v16 = v15;
    if ( v15 < 0 )
    {
      v17 = 882;
      goto LABEL_26;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
LABEL_28:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost>::GetImpl'::`2'::impl)
      && !*((_BYTE *)this + 32) )
    {
      v33 = this;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 200);
      Microsoft::WRL::Details::Make_LambdaHelpers::CLambda__lambda_c2d825d8203ae353d8ec6158cba6feb7_____lambda_c2d825d8203ae353d8ec6158cba6feb7__const___(
        &v34,
        &v33);
      v21 = v34;
      *((_QWORD *)this + 25) = v34;
      v16 = v21 == 0 ? 0x8007000E : 0;
      if ( !v21 )
      {
        v22 = 903;
LABEL_32:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
          (const char *)v16,
          ppv);
        goto LABEL_36;
      }
      v33 = this;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 208);
      Microsoft::WRL::Details::Make_LambdaHelpers::CLambda__lambda_84e44cf042b64a660f101ce25cfaf3ae_____lambda_84e44cf042b64a660f101ce25cfaf3ae__const___(
        &v34,
        &v33);
      v23 = v34;
      *((_QWORD *)this + 26) = v34;
      v16 = v23 == 0 ? 0x8007000E : 0;
      if ( !v23 )
      {
        v22 = 909;
        goto LABEL_32;
      }
    }
    v24 = tip2::details::reason_string((tip2::details *)"ShellHostAppManagerTest::reason::class_initialized", v20);
    tip2::details::shared_data<1,0,0>::set_flag_without_lock(v30 + 8, 1, v24);
    tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(
      &v33,
      &v30);
    winrt::hstring::operator std::basic_string_view<unsigned short>((char *)this + 40, &v27);
    std::wstring::_Assign<unsigned short>((char *)v33 + 272, v27, v28);
    tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(&v33);
    tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(
      &v33,
      &v30);
    winrt::hstring::operator std::basic_string_view<unsigned short>((char *)this + 48, &v27);
    std::wstring::_Assign<unsigned short>((char *)v33 + 336, v27, v28);
    tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(&v33);
    CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[50],unsigned short const (&)[11]>("AppManager-ShellHostManagerRuntimeClassInitialize");
    v16 = 0;
    goto LABEL_36;
  }
  v17 = 881;
LABEL_26:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
    (const char *)(unsigned int)v15,
    ppv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
LABEL_36:
  tip2::test_watcher<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::~test_watcher<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(v29);
  return v16;
}

```

## disassembly

```asm
0x18003a9f8  push    rbp
0x18003a9fa  push    rbx
0x18003a9fb  push    rsi
0x18003a9fc  push    rdi
0x18003a9fd  push    r12
0x18003a9ff  push    r14
0x18003aa01  push    r15
0x18003aa03  mov     rbp, rsp
0x18003aa06  sub     rsp, 80h
0x18003aa0d  mov     bl, r9b
0x18003aa10  mov     rsi, r8
0x18003aa13  mov     rdi, rdx
0x18003aa16  mov     r14, rcx
0x18003aa19  mov     [rbp+arg_18], 0
0x18003aa20  call    ??$CoreEvent1@AEAY0DC@$$CBDAEAY0N@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0DC@$$CBDAEAY0N@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[50],ushort const (&)[13]>(char const (&)[50],ushort const (&)[13])
0x18003aa25  mov     [rbp+arg_0], 0
0x18003aa2d  lea     rdx, [rbp+var_40]
0x18003aa31  lea     rcx, [rbp+arg_0]
0x18003aa35  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::start_and_watch_errors(void)
0x18003aa3a  lea     rcx, [rbp+arg_0]
0x18003aa3e  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy>(void)
0x18003aa43  nop
0x18003aa44  mov     rax, [rbp+var_8]
0x18003aa48  movups  xmm0, xmmword ptr [rax+98h]
0x18003aa4f  movdqu  xmmword ptr [r14+0B0h], xmm0
0x18003aa58  mov     [r14+20h], bl
0x18003aa5c  test    rdi, rdi
0x18003aa5f  jz      short loc_18003AA75
0x18003aa61  mov     rdx, rdi; unsigned __int16 *
0x18003aa64  lea     rcx, [rbp+arg_8]; this
0x18003aa68  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003aa6d  nop
0x18003aa6e  mov     edi, 1
0x18003aa73  jmp     short loc_18003AA8A
0x18003aa75  lea     rdx, qword_180054928; unsigned __int16 *
0x18003aa7c  lea     rcx, [rbp+arg_0]; this
0x18003aa80  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003aa85  mov     edi, 2
0x18003aa8a  mov     [rbp+arg_18], edi
0x18003aa8d  lea     r12, [r14+28h]
0x18003aa91  cmp     r12, rax
0x18003aa94  jz      short loc_18003AAB4
0x18003aa96  mov     rbx, [rax]
0x18003aa99  mov     qword ptr [rax], 0
0x18003aaa0  mov     rcx, r12
0x18003aaa3  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003aaa8  mov     rcx, r12
0x18003aaab  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003aab0  mov     [r12], rbx
0x18003aab4  test    dil, 2
0x18003aab8  jz      short loc_18003AACA
0x18003aaba  and     edi, 0FFFFFFFDh
0x18003aabd  mov     [rbp+arg_18], edi
0x18003aac0  lea     rcx, [rbp+arg_0]
0x18003aac4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003aac9  nop
0x18003aaca  test    dil, 1
0x18003aace  jz      short loc_18003AADF
0x18003aad0  and     edi, 0FFFFFFFEh
0x18003aad3  mov     [rbp+arg_18], edi
0x18003aad6  lea     rcx, [rbp+arg_8]
0x18003aada  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003aadf  test    rsi, rsi
0x18003aae2  jz      short loc_18003AAF6
0x18003aae4  mov     rdx, rsi; unsigned __int16 *
0x18003aae7  lea     rcx, [rbp+arg_8]; this
0x18003aaeb  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003aaf0  nop
0x18003aaf1  or      edi, 4
0x18003aaf4  jmp     short loc_18003AB09
0x18003aaf6  lea     rdx, qword_180054928; unsigned __int16 *
0x18003aafd  lea     rcx, [rbp+arg_0]; this
0x18003ab01  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003ab06  or      edi, 8
0x18003ab09  lea     r15, [r14+30h]
0x18003ab0d  cmp     r15, rax
0x18003ab10  jz      short loc_18003AB2F
0x18003ab12  mov     rbx, [rax]
0x18003ab15  mov     qword ptr [rax], 0
0x18003ab1c  mov     rcx, r15
0x18003ab1f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003ab24  mov     rcx, r15
0x18003ab27  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003ab2c  mov     [r15], rbx
0x18003ab2f  test    dil, 8
0x18003ab33  jz      short loc_18003AB42
0x18003ab35  and     edi, 0FFFFFFF7h
0x18003ab38  lea     rcx, [rbp+arg_0]
0x18003ab3c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003ab41  nop
0x18003ab42  test    dil, 4
0x18003ab46  jz      short loc_18003AB51
0x18003ab48  lea     rcx, [rbp+arg_8]
0x18003ab4c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003ab51  mov     cl, 1; bool
0x18003ab53  call    ?SetFullscreenCXHRunning@@YAJ_N@Z; SetFullscreenCXHRunning(bool)
0x18003ab58  mov     rcx, [rbp+38h]; this
0x18003ab5c  test    eax, eax
0x18003ab5e  jns     short loc_18003AB74
0x18003ab60  mov     r9d, eax; char *
0x18003ab63  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x18003ab6a  mov     edx, 36Ch; void *
0x18003ab6f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ab74  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging> `wil::Feature<__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging>::GetImpl(void)'::`2'::impl
0x18003ab7b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHostDebugging>::__private_IsEnabled(void)
0x18003ab80  test    al, al
0x18003ab82  jz      loc_18003AC37
0x18003ab88  mov     [rbp+arg_0], 0
0x18003ab90  lea     rcx, [rbp+arg_0]
0x18003ab94  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ab99  lea     rax, [rbp+arg_0]
0x18003ab9d  mov     qword ptr [rsp+80h+ppv], rax; int
0x18003aba2  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18003aba9  xor     edx, edx; pUnkOuter
0x18003abab  mov     r8d, 404h; dwClsContext
0x18003abb1  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x18003abb8  call    cs:__imp_CoCreateInstance
0x18003abbe  mov     ebx, eax
0x18003abc0  test    eax, eax
0x18003abc2  jns     short loc_18003ABCB
0x18003abc4  mov     edx, 371h
0x18003abc9  jmp     short loc_18003AC0C
0x18003abcb  mov     rsi, [rbp+arg_0]
0x18003abcf  mov     rax, [rsi]
0x18003abd2  mov     rdi, [rax+18h]
0x18003abd6  lea     rbx, [r14+0A8h]
0x18003abdd  mov     rcx, rbx
0x18003abe0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003abe5  mov     r9, rbx
0x18003abe8  lea     r8, _GUID_1b69f343_1af8_43fb_bfe3_b27c09b74d0b
0x18003abef  lea     rdx, qword_18005C558
0x18003abf6  mov     rcx, rsi
0x18003abf9  mov     rax, rdi
0x18003abfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac01  mov     ebx, eax
0x18003ac03  test    eax, eax
0x18003ac05  jns     short loc_18003AC2E
0x18003ac07  mov     edx, 372h; void *
0x18003ac0c  mov     r9d, eax; char *
0x18003ac0f  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x18003ac16  mov     rcx, [rbp+38h]; this
0x18003ac1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac1f  nop
0x18003ac20  lea     rcx, [rbp+arg_0]
0x18003ac24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ac29  jmp     loc_18003AD96
0x18003ac2e  lea     rcx, [rbp+arg_0]
0x18003ac32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ac37  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost> `wil::Feature<__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost>::GetImpl(void)'::`2'::impl
0x18003ac3e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRetryHandler_ShellHost>::__private_IsEnabled(void)
0x18003ac43  test    al, al
0x18003ac45  jz      loc_18003ACEF
0x18003ac4b  cmp     byte ptr [r14+20h], 0
0x18003ac50  jnz     loc_18003ACEF
0x18003ac56  mov     [rbp+arg_8], r14
0x18003ac5a  lea     rbx, [r14+0C8h]
0x18003ac61  mov     rcx, rbx
0x18003ac64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003ac69  lea     rdx, [rbp+arg_8]
0x18003ac6d  lea     rcx, [rbp+arg_10]
0x18003ac71  call    Microsoft__WRL__Details__Make_LambdaHelpers__CLambda__lambda_c2d825d8203ae353d8ec6158cba6feb7_____lambda_c2d825d8203ae353d8ec6158cba6feb7__const___
0x18003ac76  mov     rcx, [rbp+arg_10]
0x18003ac7a  mov     [rbx], rcx
0x18003ac7d  mov     rax, rcx
0x18003ac80  neg     rax
0x18003ac83  sbb     ebx, ebx
0x18003ac85  not     ebx
0x18003ac87  mov     edi, 8007000Eh
0x18003ac8c  and     ebx, edi
0x18003ac8e  test    rcx, rcx
0x18003ac91  jnz     short loc_18003ACB0
0x18003ac93  mov     edx, 387h; void *
0x18003ac98  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x18003ac9f  mov     r9d, ebx; char *
0x18003aca2  mov     rcx, [rbp+38h]; this
0x18003aca6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003acab  jmp     loc_18003AD96
0x18003acb0  mov     [rbp+arg_8], r14
0x18003acb4  lea     rbx, [r14+0D0h]
0x18003acbb  mov     rcx, rbx
0x18003acbe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003acc3  lea     rdx, [rbp+arg_8]
0x18003acc7  lea     rcx, [rbp+arg_10]
0x18003accb  call    Microsoft__WRL__Details__Make_LambdaHelpers__CLambda__lambda_84e44cf042b64a660f101ce25cfaf3ae_____lambda_84e44cf042b64a660f101ce25cfaf3ae__const___
0x18003acd0  mov     rcx, [rbp+arg_10]
0x18003acd4  mov     [rbx], rcx
0x18003acd7  mov     rax, rcx
0x18003acda  neg     rax
0x18003acdd  sbb     ebx, ebx
0x18003acdf  not     ebx
0x18003ace1  and     ebx, edi
0x18003ace3  test    rcx, rcx
0x18003ace6  jnz     short loc_18003ACEF
0x18003ace8  mov     edx, 38Dh
0x18003aced  jmp     short loc_18003AC98
0x18003acef  lea     rcx, aShellhostappma_7; "ShellHostAppManagerTest::reason::class_"...
0x18003acf6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18003acfb  mov     r8, rax
0x18003acfe  mov     edx, 1
0x18003ad03  mov     rcx, [rbp+var_8]
0x18003ad07  add     rcx, 8
0x18003ad0b  call    ?set_flag_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXGPEBD@Z; tip2::details::shared_data<1,0,0>::set_flag_without_lock(ushort,char const *)
0x18003ad10  lea     rdx, [rbp+var_8]
0x18003ad14  lea     rcx, [rbp+arg_8]
0x18003ad18  call    ??0?$test_data_control@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy> const &)
0x18003ad1d  nop
0x18003ad1e  lea     rdx, [rbp+var_50]
0x18003ad22  mov     rcx, r12
0x18003ad25  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18003ad2a  mov     rcx, [rbp+arg_8]
0x18003ad2e  add     rcx, 110h
0x18003ad35  mov     r8, [rbp+var_48]
0x18003ad39  mov     rdx, [rbp+var_50]
0x18003ad3d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003ad42  nop
0x18003ad43  lea     rcx, [rbp+arg_8]
0x18003ad47  call    ??1?$test_data_control@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(void)
0x18003ad4c  lea     rdx, [rbp+var_8]
0x18003ad50  lea     rcx, [rbp+arg_8]
0x18003ad54  call    ??0?$test_data_control@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>,wil::err_returncode_policy> const &)
0x18003ad59  nop
0x18003ad5a  lea     rdx, [rbp+var_50]
0x18003ad5e  mov     rcx, r15
0x18003ad61  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18003ad66  mov     rcx, [rbp+arg_8]
0x18003ad6a  add     rcx, 150h
0x18003ad71  mov     r8, [rbp+var_48]
0x18003ad75  mov     rdx, [rbp+var_50]
0x18003ad79  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003ad7e  nop
0x18003ad7f  lea     rcx, [rbp+arg_8]
0x18003ad83  call    ??1?$test_data_control@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(void)
0x18003ad88  lea     rcx, aAppmanagerShel_3; "AppManager-ShellHostManagerRuntimeClass"...
0x18003ad8f  call    ??$CoreEvent1@AEAY0DC@$$CBDAEAY0L@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0DC@$$CBDAEAY0L@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[50],ushort const (&)[11]>(char const (&)[50],ushort const (&)[11])
0x18003ad94  xor     ebx, ebx
0x18003ad96  lea     rcx, [rbp+var_40]
0x18003ad9a  call    ??1?$test_watcher@V?$merged_data@U_tip_ShellHostAppManagerTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>::~test_watcher<tip2::details::merged_data<_tip_ShellHostAppManagerTest,_tip_ShellHostAppManagerTest>>(void)
0x18003ad9f  mov     eax, ebx
0x18003ada1  add     rsp, 80h
0x18003ada8  pop     r15
0x18003adaa  pop     r14
0x18003adac  pop     r12
0x18003adae  pop     rdi
0x18003adaf  pop     rsi
0x18003adb0  pop     rbx
0x18003adb1  pop     rbp
0x18003adb2  retn
```
