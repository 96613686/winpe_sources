# SystemSettings::StorageSenseHandlers::FileRemovalSetting::InvokeWrapper(std::function<long (tagSAFEARRAY *,tagSAFEARRAY *)>)

- ea: `0x18006697c`
- end: `0x180066c33`
- name: `?InvokeWrapper@FileRemovalSetting@StorageSenseHandlers@SystemSettings@@IEAAJV?$function@$$A6AJPEAUtagSAFEARRAY@@0@Z@std@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *this, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800664b0`
- `0x180066940`

## callees

- `0x180012374`
- `0x18005db18`
- `0x180063b08`
- `0x18006697c`
- `0x180067170`
- `0x1800679fc`
- `0x180069934`
- `0x1800e3010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066b75`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066b8b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066b75`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066b8b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800669ce`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180066a43`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800669ce`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180066a43`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180066add`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180066add`

## string_xrefs

- `0x1800669fe`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180066a73`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180066b25`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180066bb6`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x1800669e0`: `CleanupRecommendations`
- `0x180066a55`: `CleanupRecommendations`
- `0x180066b12`: `CleanupRecommendations`
- `0x180066b9b`: `CleanupRecommendations`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::FileRemovalSetting::InvokeWrapper(
        SystemSettings::DataModel::CSettingBase *this,
        __int64 *a2)
{
  SAFEARRAY *Vector; // r14
  __int64 v5; // rdx
  __int64 *v6; // rcx
  void (__fastcall *v7)(__int64 *, __int64); // rax
  void *v8; // rcx
  SAFEARRAY *v9; // rdi
  __int64 v11; // rcx
  int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 *v15; // rcx
  HRESULT v16; // edi
  __int64 v17; // rdx
  __int64 *v18; // rcx
  __int64 v19; // rdx
  __int64 *v20; // rcx
  std::_Ref_count_base *v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  SAFEARRAY *v24; // [rsp+80h] [rbp+30h] BYREF
  __int64 *v25; // [rsp+88h] [rbp+38h]
  SAFEARRAY *v26; // [rsp+90h] [rbp+40h] BYREF

  v25 = a2;
  CleanupRecommendationsLogger::CleanupExecutionStarted<enum SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &,unsigned __int64 &,unsigned __int64 &>(
    (char *)this + 304,
    (char *)this + 288,
    (char *)this + 296);
  SystemSettings::StorageSenseHandlers::FileRemovalSetting::GetAllSelectedFileNames(this, &v21);
  Vector = SafeArrayCreateVector(8u, 0, (v22 - (__int64)v21) >> 5);
  if ( !Vector )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x367,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)0x8007000ELL,
      (int)"%hs",
      "CleanupRecommendations");
    std::vector<std::wstring>::_Tidy(&v21);
    v6 = (__int64 *)a2[7];
    if ( v6 )
    {
      v7 = *(void (__fastcall **)(__int64 *, __int64))(*v6 + 32);
LABEL_7:
      LOBYTE(v5) = v6 != a2;
      v7(v6, v5);
      a2[7] = 0;
      return 2147942414LL;
    }
    return 2147942414LL;
  }
  v9 = SafeArrayCreateVector(0x13u, 0, (v22 - (__int64)v21) >> 5);
  if ( !v9 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x36B,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)0x8007000ELL,
      (int)"%hs",
      "CleanupRecommendations");
    std::vector<std::wstring>::_Tidy(&v21);
    v6 = (__int64 *)a2[7];
    if ( v6 )
    {
      v5 = *v6;
      v7 = *(void (__fastcall **)(__int64 *, __int64))(*v6 + 32);
      goto LABEL_7;
    }
    return 2147942414LL;
  }
  if ( (int)SystemSettings::StorageSenseHandlers::FileRemovalSetting::SerializeFileList(v8, (__int64 *)&v21, Vector) >= 0 )
  {
    v24 = v9;
    v26 = Vector;
    v11 = a2[7];
    if ( !v11 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(__int64, SAFEARRAY **, SAFEARRAY **))(*(_QWORD *)v11 + 16LL))(v11, &v26, &v24);
  }
  v12 = SystemSettings::StorageSenseHandlers::FileRemovalSetting::ProcessCleanupResults(
          this,
          &v21,
          (std::_Ref_count_base *)v9);
  if ( v12 < 0 )
  {
    v13 = 884;
LABEL_15:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)v12,
      (int)"%hs",
      "CleanupRecommendations");
    std::vector<std::wstring>::_Tidy(&v21);
    v15 = (__int64 *)a2[7];
    if ( v15 )
    {
      LOBYTE(v14) = v15 != a2;
      (*(void (__fastcall **)(__int64 *, __int64))(*v15 + 32))(v15, v14);
      a2[7] = 0;
    }
    return (unsigned int)v12;
  }
  v12 = SafeArrayDestroy(Vector);
  if ( v12 < 0 )
  {
    v13 = 887;
    goto LABEL_15;
  }
  v16 = SafeArrayDestroy(v9);
  if ( v16 >= 0 )
  {
    std::vector<std::wstring>::_Tidy(&v21);
    v20 = (__int64 *)a2[7];
    if ( v20 )
    {
      LOBYTE(v19) = v20 != a2;
      (*(void (__fastcall **)(__int64 *, __int64))(*v20 + 32))(v20, v19);
      a2[7] = 0;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x378,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)v16,
      (int)"%hs",
      "CleanupRecommendations");
    std::vector<std::wstring>::_Tidy(&v21);
    v18 = (__int64 *)a2[7];
    if ( v18 )
    {
      LOBYTE(v17) = v18 != a2;
      (*(void (__fastcall **)(__int64 *, __int64))(*v18 + 32))(v18, v17);
      a2[7] = 0;
    }
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x18006697c  mov     [rsp-28h+arg_8], rdx
0x180066981  push    rbp
0x180066982  push    rbx
0x180066983  push    rsi
0x180066984  push    rdi
0x180066985  push    r14
0x180066987  mov     rbp, rsp
0x18006698a  sub     rsp, 50h
0x18006698e  mov     rbx, rdx
0x180066991  mov     rsi, rcx
0x180066994  lea     r8, [rcx+128h]
0x18006699b  lea     rdx, [rcx+120h]
0x1800669a2  add     rcx, 130h
0x1800669a9  call    ??$CleanupExecutionStarted@AEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@AEA_KAEA_K@CleanupRecommendationsLogger@@SAXAEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@AEA_K1@Z; CleanupRecommendationsLogger::CleanupExecutionStarted<SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &,unsigned __int64 &,unsigned __int64 &>(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &,unsigned __int64 &,unsigned __int64 &)
0x1800669ae  lea     rdx, [rbp+var_20]
0x1800669b2  mov     rcx, rsi; this
0x1800669b5  call    ?GetAllSelectedFileNames@FileRemovalSetting@StorageSenseHandlers@SystemSettings@@IEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; SystemSettings::StorageSenseHandlers::FileRemovalSetting::GetAllSelectedFileNames(void)
0x1800669ba  nop
0x1800669bb  mov     r8, [rbp+var_18]
0x1800669bf  sub     r8, [rbp+var_20]
0x1800669c3  sar     r8, 5; cElements
0x1800669c7  mov     ecx, 8; vt
0x1800669cc  xor     edx, edx; lLbound
0x1800669ce  call    cs:__imp_SafeArrayCreateVector
0x1800669d4  mov     r14, rax
0x1800669d7  test    rax, rax
0x1800669da  jnz     short loc_180066A30
0x1800669dc  mov     rcx, [rbp+28h]; this
0x1800669e0  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x1800669e7  mov     [rsp+50h+var_28], rax; char *
0x1800669ec  lea     rax, aHs; "%hs"
0x1800669f3  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800669f8  mov     r9d, 8007000Eh; char *
0x1800669fe  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180066a05  mov     edx, 367h; void *
0x180066a0a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180066a0f  nop
0x180066a10  lea     rcx, [rbp+var_20]
0x180066a14  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180066a19  nop
0x180066a1a  mov     rcx, [rbx+38h]
0x180066a1e  test    rcx, rcx
0x180066a21  jz      loc_180066AB2
0x180066a27  mov     rax, [rcx]
0x180066a2a  mov     rax, [rax+20h]
0x180066a2e  jmp     short loc_180066A9F
0x180066a30  mov     r8, [rbp+var_18]
0x180066a34  sub     r8, [rbp+var_20]
0x180066a38  sar     r8, 5; cElements
0x180066a3c  mov     ecx, 13h; vt
0x180066a41  xor     edx, edx; lLbound
0x180066a43  call    cs:__imp_SafeArrayCreateVector
0x180066a49  mov     rdi, rax
0x180066a4c  test    rax, rax
0x180066a4f  jnz     short loc_180066ABC
0x180066a51  mov     rcx, [rbp+28h]; this
0x180066a55  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180066a5c  mov     [rsp+50h+var_28], rax; char *
0x180066a61  lea     rax, aHs; "%hs"
0x180066a68  mov     qword ptr [rsp+50h+var_30], rax; int
0x180066a6d  mov     r9d, 8007000Eh; char *
0x180066a73  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180066a7a  mov     edx, 36Bh; void *
0x180066a7f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180066a84  nop
0x180066a85  lea     rcx, [rbp+var_20]
0x180066a89  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180066a8e  nop
0x180066a8f  mov     rcx, [rbx+38h]
0x180066a93  test    rcx, rcx
0x180066a96  jz      short loc_180066AB2
0x180066a98  mov     rdx, [rcx]
0x180066a9b  mov     rax, [rdx+20h]
0x180066a9f  cmp     rcx, rbx
0x180066aa2  setnz   dl
0x180066aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066aaa  mov     qword ptr [rbx+38h], 0
0x180066ab2  mov     eax, 8007000Eh
0x180066ab7  jmp     loc_180066C28
0x180066abc  mov     r8, r14
0x180066abf  lea     rdx, [rbp+var_20]
0x180066ac3  call    ?SerializeFileList@FileRemovalSetting@StorageSenseHandlers@SystemSettings@@IEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUtagSAFEARRAY@@@Z; SystemSettings::StorageSenseHandlers::FileRemovalSetting::SerializeFileList(std::vector<std::wstring> const &,tagSAFEARRAY *)
0x180066ac8  test    eax, eax
0x180066aca  js      short loc_180066AF8
0x180066acc  mov     [rbp+arg_0], rdi
0x180066ad0  mov     [rbp+arg_10], r14
0x180066ad4  mov     rcx, [rbx+38h]
0x180066ad8  test    rcx, rcx
0x180066adb  jnz     short loc_180066AE4
0x180066add  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180066ae3  int     3; Trap to Debugger
0x180066ae4  mov     rax, [rcx]
0x180066ae7  lea     r8, [rbp+arg_0]
0x180066aeb  lea     rdx, [rbp+arg_10]
0x180066aef  mov     rax, [rax+10h]
0x180066af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066af8  mov     r8, rdi
0x180066afb  lea     rdx, [rbp+var_20]
0x180066aff  mov     rcx, rsi; this
0x180066b02  call    ?ProcessCleanupResults@FileRemovalSetting@StorageSenseHandlers@SystemSettings@@IEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUtagSAFEARRAY@@@Z; SystemSettings::StorageSenseHandlers::FileRemovalSetting::ProcessCleanupResults(std::vector<std::wstring> const &,tagSAFEARRAY *)
0x180066b07  mov     esi, eax
0x180066b09  test    eax, eax
0x180066b0b  jns     short loc_180066B72
0x180066b0d  mov     edx, 374h; void *
0x180066b12  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180066b19  mov     [rsp+50h+var_28], rax; char *
0x180066b1e  lea     rax, aHs; "%hs"
0x180066b25  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180066b2c  mov     r9d, esi; char *
0x180066b2f  mov     qword ptr [rsp+50h+var_30], rax; int
0x180066b34  mov     rcx, [rbp+28h]; this
0x180066b38  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180066b3d  nop
0x180066b3e  lea     rcx, [rbp+var_20]
0x180066b42  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180066b47  nop
0x180066b48  mov     rcx, [rbx+38h]
0x180066b4c  test    rcx, rcx
0x180066b4f  jz      short loc_180066B6B
0x180066b51  mov     rax, [rcx]
0x180066b54  cmp     rcx, rbx
0x180066b57  setnz   dl
0x180066b5a  mov     rax, [rax+20h]
0x180066b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b63  mov     qword ptr [rbx+38h], 0
0x180066b6b  mov     eax, esi
0x180066b6d  jmp     loc_180066C28
0x180066b72  mov     rcx, r14; psa
0x180066b75  call    cs:__imp_SafeArrayDestroy
0x180066b7b  mov     esi, eax
0x180066b7d  test    eax, eax
0x180066b7f  jns     short loc_180066B88
0x180066b81  mov     edx, 377h
0x180066b86  jmp     short loc_180066B12
0x180066b88  mov     rcx, rdi; psa
0x180066b8b  call    cs:__imp_SafeArrayDestroy
0x180066b91  mov     edi, eax
0x180066b93  test    eax, eax
0x180066b95  jns     short loc_180066BF9
0x180066b97  mov     rcx, [rbp+28h]; this
0x180066b9b  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180066ba2  mov     [rsp+50h+var_28], rax; char *
0x180066ba7  lea     rax, aHs; "%hs"
0x180066bae  mov     qword ptr [rsp+50h+var_30], rax; int
0x180066bb3  mov     r9d, edi; char *
0x180066bb6  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180066bbd  mov     edx, 378h; void *
0x180066bc2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180066bc7  nop
0x180066bc8  lea     rcx, [rbp+var_20]
0x180066bcc  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180066bd1  nop
0x180066bd2  mov     rcx, [rbx+38h]
0x180066bd6  test    rcx, rcx
0x180066bd9  jz      short loc_180066BF5
0x180066bdb  mov     rax, [rcx]
0x180066bde  cmp     rcx, rbx
0x180066be1  setnz   dl
0x180066be4  mov     rax, [rax+20h]
0x180066be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bed  mov     qword ptr [rbx+38h], 0
0x180066bf5  mov     eax, edi
0x180066bf7  jmp     short loc_180066C28
0x180066bf9  lea     rcx, [rbp+var_20]
0x180066bfd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180066c02  nop
0x180066c03  mov     rcx, [rbx+38h]
0x180066c07  test    rcx, rcx
0x180066c0a  jz      short loc_180066C26
0x180066c0c  mov     rax, [rcx]
0x180066c0f  cmp     rcx, rbx
0x180066c12  setnz   dl
0x180066c15  mov     rax, [rax+20h]
0x180066c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c1e  mov     qword ptr [rbx+38h], 0
0x180066c26  xor     eax, eax
0x180066c28  add     rsp, 50h
0x180066c2c  pop     r14
0x180066c2e  pop     rdi
0x180066c2f  pop     rsi
0x180066c30  pop     rbx
0x180066c31  pop     rbp
0x180066c32  retn
```
