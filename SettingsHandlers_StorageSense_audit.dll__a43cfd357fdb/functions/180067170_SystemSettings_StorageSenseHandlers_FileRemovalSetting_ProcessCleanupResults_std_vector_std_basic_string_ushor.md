# SystemSettings::StorageSenseHandlers::FileRemovalSetting::ProcessCleanupResults(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,tagSAFEARRAY *)

- ea: `0x180067170`
- end: `0x180067667`
- name: `?ProcessCleanupResults@FileRemovalSetting@StorageSenseHandlers@SystemSettings@@IEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUtagSAFEARRAY@@@Z`
- size: `1271`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *this, std::_Ref_count_base **, std::_Ref_count_base *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006697c`

## callees

- `0x180006e50`
- `0x1800077ec`
- `0x180012374`
- `0x18001fc0c`
- `0x180023928`
- `0x1800286c0`
- `0x18005c450`
- `0x18005dcec`
- `0x18005e944`
- `0x18005eba8`
- `0x18005edb0`
- `0x18005eebc`
- `0x18005fa88`
- `0x18005fe44`
- `0x180061884`
- `0x180067170`
- `0x180068c30`
- `0x180069934`
- `0x180074b70`
- `0x18007523c`
- `0x180075660`
- `0x180079544`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180067251`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180067251`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180067219`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180067219`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800671bd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800671bd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067415`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067415`

## string_xrefs

- `0x1800671f1`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180067445`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x1800671c9`: `CleanupRecommendations`
- `0x180067225`: `CleanupRecommendations`
- `0x18006725d`: `CleanupRecommendations`
- `0x18006742a`: `CleanupRecommendations`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::FileRemovalSetting::ProcessCleanupResults(
        SystemSettings::DataModel::CSettingBase *this,
        std::_Ref_count_base **a2,
        std::_Ref_count_base *a3)
{
  std::_Ref_count_base *v3; // r15
  SystemSettings::DataModel::CSettingBase *v4; // rdi
  HRESULT LBound; // esi
  __int64 v7; // r8
  __int64 *v8; // rsi
  __int64 *v9; // r14
  LONG v10; // r13d
  __int64 v11; // rcx
  int v12; // eax
  int v13; // ecx
  __int64 v14; // rdx
  __int64 v15; // rdx
  char *v16; // r8
  HRESULT v17; // eax
  unsigned int v18; // r15d
  struct SystemSettings::StorageSenseHandlers::RecommendationSingleton *Instance; // rax
  __int64 Recommender; // r15
  char *v21; // r15
  struct SystemSettings::StorageSenseHandlers::RecommendationSingleton *v22; // rax
  __int64 SectionSingleton; // rax
  bool v24; // cl
  const HSTRING__ *v25; // rdx
  std::_Ref_count_base **v26; // [rsp+30h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B0h]
  LONG plLbound; // [rsp+50h] [rbp-A8h] BYREF
  LONG plUbound; // [rsp+54h] [rbp-A4h] BYREF
  int v31; // [rsp+58h] [rbp-A0h]
  std::_Ref_count_base **v32; // [rsp+60h] [rbp-98h] BYREF
  std::_Ref_count_base *v33[2]; // [rsp+68h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-80h]
  _DWORD *v35; // [rsp+80h] [rbp-78h] BYREF
  __int64 *v36; // [rsp+88h] [rbp-70h]
  SystemSettings::DataModel::CSettingBase *v37; // [rsp+90h] [rbp-68h]
  char *v38; // [rsp+98h] [rbp-60h]
  __int16 v39; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v40; // [rsp+A2h] [rbp-56h]
  int v41; // [rsp+AAh] [rbp-4Eh]
  __int16 v42; // [rsp+AEh] [rbp-4Ah]
  __int64 v43; // [rsp+B0h] [rbp-48h]
  __int64 v44; // [rsp+B8h] [rbp-40h]
  int v45; // [rsp+C0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v3 = a3;
  v32 = a2;
  v4 = this;
  v37 = this;
  v33[0] = a3;
  v35 = 0;
  LBound = SafeArrayAccessData((SAFEARRAY *)a3, (void **)&v35);
  if ( LBound < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x322,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)LBound,
      (int)"%hs",
      "CleanupRecommendations");
    return (unsigned int)LBound;
  }
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound((SAFEARRAY *)v3, 1u, &plLbound);
  if ( LBound < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)LBound,
      (int)"%hs",
      "CleanupRecommendations");
    return (unsigned int)LBound;
  }
  LBound = SafeArrayGetUBound((SAFEARRAY *)v3, 1u, &plUbound);
  if ( LBound < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x326,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)LBound,
      (int)"%hs",
      "CleanupRecommendations");
    return (unsigned int)LBound;
  }
  v27 = 0;
  v28 = 0;
  v8 = (__int64 *)((char *)v4 + 328);
  v26 = (std::_Ref_count_base **)((char *)v4 + 328);
  v9 = (__int64 *)((char *)v4 + 336);
  v36 = (__int64 *)((char *)v4 + 336);
  if ( *((_QWORD *)v4 + 41) != *((_QWORD *)v4 + 42) )
  {
    std::_Destroy_range<std::allocator<std::pair<std::wstring,unsigned long>>>(*v8);
    *v9 = *v8;
  }
  v10 = plLbound;
  v11 = *((_QWORD *)&v27 + 1);
  while ( v10 <= plUbound )
  {
    try
    {
      v12 = v35[v10];
      v31 = v12;
      if ( !v12 || v12 == 3 )
      {
        v15 = 32LL * v10;
        v16 = (char *)*v32 + v15;
        if ( v11 == v28 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v27, v11, v16);
          goto LABEL_22;
        }
        std::wstring::wstring(v11, (char *)*v32 + v15, v16);
        v11 = *((_QWORD *)&v27 + 1) + 32LL;
        *((_QWORD *)&v27 + 1) += 32LL;
      }
      else
      {
        std::wstring::wstring(&v39, (char *)*v32 + 32 * v10, v7);
        v13 = v31;
        v45 = v31;
        v14 = *v9;
        if ( *v9 == *((_QWORD *)v4 + 43) )
        {
          std::vector<std::pair<std::wstring,unsigned long>>::_Emplace_reallocate<std::pair<std::wstring,unsigned long>>(
            (char *)v4 + 328,
            v14,
            &v39);
        }
        else
        {
          *(_WORD *)v14 = v39;
          *(_QWORD *)(v14 + 2) = v40;
          *(_DWORD *)(v14 + 10) = v41;
          *(_WORD *)(v14 + 14) = v42;
          *(_QWORD *)(v14 + 16) = v43;
          *(_QWORD *)(v14 + 24) = v44;
          v43 = 0;
          v44 = 7;
          v39 = 0;
          *(_DWORD *)(v14 + 32) = v13;
          *v9 += 40;
        }
        std::wstring::_Tidy_deallocate(&v39);
LABEL_22:
        v11 = *((_QWORD *)&v27 + 1);
      }
      ++v10;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x33A,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
        "%hs",
        "CleanupRecommendations");
      v9 = v36;
      v4 = v37;
      v3 = v33[0];
      v8 = (__int64 *)v26;
      break;
    }
  }
  v17 = SafeArrayUnaccessData((SAFEARRAY *)v3);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x33B,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)v17,
      (int)"%hs",
      "CleanupRecommendations");
    goto LABEL_40;
  }
  if ( (_QWORD)v27 != *((_QWORD *)&v27 + 1) )
  {
    Instance = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance();
    Recommender = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetRecommender(
                    Instance,
                    *((unsigned int *)v4 + 76));
    *(_OWORD *)v33 = 0;
    v34 = 0;
    if ( (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 5 )
    {
      std::vector<std::wstring>::_Buy_nonzero(v33);
      v32 = v33;
      v33[1] = (std::_Ref_count_base *)std::_Uninitialized_copy<std::wstring *,std::wstring *,std::allocator<std::wstring>>(
                                         v27,
                                         *((_QWORD *)&v27 + 1),
                                         v33[0],
                                         v33);
      v32 = 0;
      std::_Tidy_guard<std::vector<std::wstring>>::~_Tidy_guard<std::vector<std::wstring>>(&v32);
    }
    SystemSettings::StorageSenseHandlers::FileRemovalRecommender::UpdateRecommendationList(Recommender, v33);
    v21 = (char *)operator new(0x30u);
    v26 = (std::_Ref_count_base **)v21;
    *(_OWORD *)v21 = 0;
    *((_DWORD *)v21 + 2) = 1;
    *((_DWORD *)v21 + 3) = 1;
    *(_QWORD *)v21 = &std::_Ref_count_obj2<SystemSettings::StorageSenseHandlers::UserFilesDeletedNotification>::`vftable';
    *((_QWORD *)v21 + 2) = &SystemSettings::StorageSenseHandlers::UserFilesDeletedNotification::`vftable';
    *((_QWORD *)v21 + 3) = 0;
    *((_QWORD *)v21 + 4) = 0;
    *((_QWORD *)v21 + 5) = 0;
    v37 = (SystemSettings::DataModel::CSettingBase *)(v21 + 16);
    v38 = v21;
    if ( v21 + 24 != (char *)&v27 )
      std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(
        v21 + 24,
        v27,
        (__int64)(*((_QWORD *)&v27 + 1) - v27) >> 5);
    v22 = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance();
    SectionSingleton = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetSectionSingleton(
                         v22,
                         *((unsigned int *)v4 + 76));
    *(_OWORD *)v33 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v21 + 2);
    v33[0] = (std::_Ref_count_base *)(v21 + 16);
    v33[1] = (std::_Ref_count_base *)v21;
    v26 = v33;
    SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
      SectionSingleton,
      &v26);
    if ( v33[1] )
      std::_Ref_count_base::_Decref(v33[1]);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v21);
  }
  v24 = *v8 != *v9;
  *((_BYTE *)v4 + 282) = v24;
  *((_BYTE *)v4 + 283) = !v24;
  if ( !v24 )
  {
    v25 = &stru_18010F018;
    goto LABEL_38;
  }
  if ( v24 )
  {
    v25 = &stru_18010EFA0;
LABEL_38:
    SystemSettings::DataModel::CSettingBase::OnValueChanged(v4, (const unsigned __int16 *)v25);
  }
  v26 = (std::_Ref_count_base **)(0xCCCCCCCCCCCCCCCDuLL * ((*v9 - *v8) >> 3));
  CleanupRecommendationsLogger::FileCleanupExecutionFinished<enum SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &,unsigned __int64>(
    (char *)v4 + 304,
    &v26);
  v18 = 0;
LABEL_40:
  std::vector<std::wstring>::_Tidy(&v27);
  return v18;
}

```

## disassembly

```asm
0x180067170  mov     r11, rsp
0x180067173  mov     [r11+20h], rbx
0x180067177  push    rsi
0x180067178  push    rdi
0x180067179  push    r13
0x18006717b  push    r14
0x18006717d  push    r15
0x18006717f  sub     rsp, 0D0h
0x180067186  mov     rax, cs:__security_cookie
0x18006718d  xor     rax, rsp
0x180067190  mov     [rsp+0F8h+var_30], rax
0x180067198  mov     r15, r8
0x18006719b  mov     [rsp+0F8h+var_98], rdx
0x1800671a0  mov     rdi, rcx
0x1800671a3  mov     [rsp+0F8h+var_68], rcx
0x1800671ab  mov     [rsp+0F8h+var_90], r8
0x1800671b0  xor     ebx, ebx
0x1800671b2  mov     [r11-78h], rbx
0x1800671b6  lea     rdx, [r11-78h]; ppvData
0x1800671ba  mov     rcx, r8; psa
0x1800671bd  call    cs:__imp_SafeArrayAccessData
0x1800671c3  mov     esi, eax
0x1800671c5  test    eax, eax
0x1800671c7  jns     short loc_180067204
0x1800671c9  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x1800671d0  mov     [rsp+0F8h+var_D0], rdx; char *
0x1800671d5  lea     rdx, aHs; "%hs"
0x1800671dc  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x1800671e1  mov     edx, 322h; void *
0x1800671e6  mov     rcx, [rsp+0F8h]; this
0x1800671ee  mov     r9d, esi; char *
0x1800671f1  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x1800671f8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800671fd  mov     eax, esi
0x1800671ff  jmp     loc_18006763F
0x180067204  mov     [rsp+0F8h+plLbound], ebx
0x180067208  mov     [rsp+0F8h+plUbound], ebx
0x18006720c  lea     r8, [rsp+0F8h+plLbound]; plLbound
0x180067211  mov     edx, 1; nDim
0x180067216  mov     rcx, r15; psa
0x180067219  call    cs:__imp_SafeArrayGetLBound
0x18006721f  mov     esi, eax
0x180067221  test    eax, eax
0x180067223  jns     short loc_180067244
0x180067225  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x18006722c  mov     [rsp+0F8h+var_D0], rdx
0x180067231  lea     rdx, aHs; "%hs"
0x180067238  mov     qword ptr [rsp+0F8h+var_D8], rdx
0x18006723d  mov     edx, 325h
0x180067242  jmp     short loc_1800671E6
0x180067244  lea     r8, [rsp+0F8h+plUbound]; plUbound
0x180067249  mov     edx, 1; nDim
0x18006724e  mov     rcx, r15; psa
0x180067251  call    cs:__imp_SafeArrayGetUBound
0x180067257  mov     esi, eax
0x180067259  test    eax, eax
0x18006725b  jns     short loc_18006727F
0x18006725d  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x180067264  mov     [rsp+0F8h+var_D0], rdx
0x180067269  lea     rdx, aHs; "%hs"
0x180067270  mov     qword ptr [rsp+0F8h+var_D8], rdx
0x180067275  mov     edx, 326h
0x18006727a  jmp     loc_1800671E6
0x18006727f  xorps   xmm0, xmm0
0x180067282  movdqu  [rsp+0F8h+var_C0], xmm0
0x180067288  mov     [rsp+0F8h+var_B0], rbx
0x18006728d  lea     rsi, [rdi+148h]
0x180067294  mov     [rsp+0F8h+var_C8], rsi
0x180067299  lea     r14, [rsi+8]
0x18006729d  mov     [rsp+0F8h+var_70], r14
0x1800672a5  mov     rdx, [r14]
0x1800672a8  cmp     [rsi], rdx
0x1800672ab  jz      short loc_1800672BB
0x1800672ad  mov     rcx, [rsi]
0x1800672b0  call    ??$_Destroy_range@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@YAXPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@0@QEAU10@AEAV?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<std::wstring,ulong>>>(std::pair<std::wstring,ulong> *,std::pair<std::wstring,ulong> * const,std::allocator<std::pair<std::wstring,ulong>> &)
0x1800672b5  mov     rax, [rsi]
0x1800672b8  mov     [r14], rax
0x1800672bb  mov     r13d, [rsp+0F8h+plLbound]
0x1800672c0  mov     rcx, qword ptr [rsp+0F8h+var_C0+8]
0x1800672c5  cmp     r13d, [rsp+0F8h+plUbound]
0x1800672ca  jg      loc_1800673F4
0x1800672d0  movsxd  rdx, r13d
0x1800672d3  mov     rax, [rsp+0F8h+var_78]
0x1800672db  mov     eax, [rax+rdx*4]
0x1800672de  mov     [rsp+0F8h+var_A0], eax
0x1800672e2  test    eax, eax
0x1800672e4  jz      loc_1800673AC
0x1800672ea  cmp     eax, 3
0x1800672ed  jz      loc_1800673AC
0x1800672f3  shl     rdx, 5
0x1800672f7  mov     rax, [rsp+0F8h+var_98]
0x1800672fc  add     rdx, [rax]
0x1800672ff  lea     rcx, [rsp+0F8h+var_58]
0x180067307  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006730c  mov     ecx, [rsp+0F8h+var_A0]
0x180067310  mov     [rsp+0F8h+var_38], ecx
0x180067317  mov     rdx, [r14]
0x18006731a  cmp     rdx, [rsi+10h]
0x18006731e  jz      short loc_18006738C
0x180067320  movzx   eax, [rsp+0F8h+var_58]
0x180067328  mov     [rdx], ax
0x18006732b  movsd   xmm0, [rsp+0F8h+var_56]
0x180067334  movsd   qword ptr [rdx+2], xmm0
0x180067339  mov     eax, [rsp+0F8h+var_4E]
0x180067340  mov     [rdx+0Ah], eax
0x180067343  movzx   eax, [rsp+0F8h+var_4A]
0x18006734b  mov     [rdx+0Eh], ax
0x18006734f  mov     rax, [rsp+0F8h+var_48]
0x180067357  mov     [rdx+10h], rax
0x18006735b  mov     rax, [rsp+0F8h+var_40]
0x180067363  mov     [rdx+18h], rax
0x180067367  mov     [rsp+0F8h+var_48], rbx
0x18006736f  mov     [rsp+0F8h+var_40], 7
0x18006737b  mov     [rsp+0F8h+var_58], bx
0x180067383  mov     [rdx+20h], ecx
0x180067386  add     qword ptr [r14], 28h ; '('
0x18006738a  jmp     short loc_18006739D
0x18006738c  lea     r8, [rsp+0F8h+var_58]
0x180067394  mov     rcx, rsi
0x180067397  call    ??$_Emplace_reallocate@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<std::wstring,ulong>>::_Emplace_reallocate<std::pair<std::wstring,ulong>>(std::pair<std::wstring,ulong> * const,std::pair<std::wstring,ulong> &&)
0x18006739c  nop
0x18006739d  lea     rcx, [rsp+0F8h+var_58]
0x1800673a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800673aa  jmp     short loc_1800673E7
0x1800673ac  shl     rdx, 5
0x1800673b0  mov     rax, [rsp+0F8h+var_98]
0x1800673b5  mov     r8, [rax]
0x1800673b8  add     r8, rdx
0x1800673bb  cmp     rcx, [rsp+0F8h+var_B0]
0x1800673c0  jz      short loc_1800673DA
0x1800673c2  mov     rdx, r8
0x1800673c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800673ca  mov     rcx, qword ptr [rsp+0F8h+var_C0+8]
0x1800673cf  add     rcx, 20h ; ' '
0x1800673d3  mov     qword ptr [rsp+0F8h+var_C0+8], rcx
0x1800673d8  jmp     short loc_1800673EC
0x1800673da  mov     rdx, rcx
0x1800673dd  lea     rcx, [rsp+0F8h+var_C0]
0x1800673e2  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800673e7  mov     rcx, qword ptr [rsp+0F8h+var_C0+8]
0x1800673ec  inc     r13d
0x1800673ef  jmp     loc_1800672C5
0x1800673f4  jmp     short loc_180067412
0x1800673f6  xor     ebx, ebx
0x1800673f8  mov     r14, [rsp+0F8h+var_70]
0x180067400  mov     rdi, [rsp+0F8h+var_68]
0x180067408  mov     r15, [rsp+0F8h+var_90]
0x18006740d  mov     rsi, [rsp+0F8h+var_C8]
0x180067412  mov     rcx, r15; psa
0x180067415  call    cs:__imp_SafeArrayUnaccessData
0x18006741b  mov     r15d, eax
0x18006741e  test    eax, eax
0x180067420  jns     short loc_18006745B
0x180067422  mov     rcx, [rsp+0F8h]; this
0x18006742a  lea     rdx, aCleanuprecomme; "CleanupRecommendations"
0x180067431  mov     [rsp+0F8h+var_D0], rdx; char *
0x180067436  lea     rdx, aHs; "%hs"
0x18006743d  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180067442  mov     r9d, eax; char *
0x180067445  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x18006744c  mov     edx, 33Bh; void *
0x180067451  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180067456  jmp     loc_180067632
0x18006745b  mov     rax, qword ptr [rsp+0F8h+var_C0+8]
0x180067460  cmp     qword ptr [rsp+0F8h+var_C0], rax
0x180067465  jz      loc_1800675CA
0x18006746b  call    ?GetInstance@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance(void)
0x180067470  mov     edx, [rdi+130h]
0x180067476  mov     rcx, rax
0x180067479  call    ?GetRecommender@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@QEAAPEAVCleanupRecommender@23@W4RecommenderKind@RecommenderEngineUtils@23@@Z; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetRecommender(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind)
0x18006747e  mov     r15, rax
0x180067481  xorps   xmm0, xmm0
0x180067484  movdqu  xmmword ptr [rsp+0F8h+var_90], xmm0
0x18006748a  mov     [rsp+0F8h+var_80], rbx
0x18006748f  mov     rdx, qword ptr [rsp+0F8h+var_C0+8]
0x180067494  sub     rdx, qword ptr [rsp+0F8h+var_C0]
0x180067499  sar     rdx, 5
0x18006749d  test    rdx, rdx
0x1800674a0  jz      short loc_1800674E3
0x1800674a2  lea     rcx, [rsp+0F8h+var_90]
0x1800674a7  call    ?_Buy_nonzero@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::wstring>::_Buy_nonzero(unsigned __int64)
0x1800674ac  lea     rax, [rsp+0F8h+var_90]
0x1800674b1  mov     [rsp+0F8h+var_98], rax
0x1800674b6  lea     r9, [rsp+0F8h+var_90]
0x1800674bb  mov     r8, [rsp+0F8h+var_90]
0x1800674c0  mov     rdx, qword ptr [rsp+0F8h+var_C0+8]
0x1800674c5  mov     rcx, qword ptr [rsp+0F8h+var_C0]
0x1800674ca  call    ??$_Uninitialized_copy@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Uninitialized_copy<std::wstring *,std::wstring *,std::allocator<std::wstring>>(std::wstring *,std::wstring *,std::wstring *,std::allocator<std::wstring> &)
0x1800674cf  mov     [rsp+0F8h+var_90+8], rax
0x1800674d4  mov     [rsp+0F8h+var_98], rbx
0x1800674d9  lea     rcx, [rsp+0F8h+var_98]
0x1800674de  call    ??1?$_Tidy_guard@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<std::wstring>>::~_Tidy_guard<std::vector<std::wstring>>(void)
0x1800674e3  lea     rdx, [rsp+0F8h+var_90]
0x1800674e8  mov     rcx, r15
0x1800674eb  call    ?UpdateRecommendationList@FileRemovalRecommender@StorageSenseHandlers@SystemSettings@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; SystemSettings::StorageSenseHandlers::FileRemovalRecommender::UpdateRecommendationList(std::vector<std::wstring>)
0x1800674f0  mov     ecx, 30h ; '0'; Size
0x1800674f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800674fa  mov     r15, rax
0x1800674fd  mov     [rsp+0F8h+var_C8], rax
0x180067502  xorps   xmm0, xmm0
0x180067505  movups  xmmword ptr [rax], xmm0
0x180067508  mov     dword ptr [rax+8], 1
0x18006750f  mov     dword ptr [rax+0Ch], 1
0x180067516  lea     rax, ??_7?$_Ref_count_obj2@UUserFilesDeletedNotification@StorageSenseHandlers@SystemSettings@@@std@@6B@; const std::_Ref_count_obj2<SystemSettings::StorageSenseHandlers::UserFilesDeletedNotification>::`vftable'
0x18006751d  mov     [r15], rax
0x180067520  lea     r13, [r15+10h]
0x180067524  lea     rax, ??_7UserFilesDeletedNotification@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::UserFilesDeletedNotification::`vftable'
0x18006752b  mov     [r13+0], rax
0x18006752f  mov     [r13+8], rbx
0x180067533  mov     [r13+10h], rbx
0x180067537  mov     [r13+18h], rbx
0x18006753b  mov     [rsp+0F8h+var_68], r13
0x180067543  mov     [rsp+0F8h+var_60], r15
0x18006754b  lea     rcx, [r13+8]
0x18006754f  lea     rax, [rsp+0F8h+var_C0]
0x180067554  cmp     rcx, rax
0x180067557  jz      short loc_18006756F
0x180067559  mov     r8, qword ptr [rsp+0F8h+var_C0+8]
0x18006755e  mov     rdx, qword ptr [rsp+0F8h+var_C0]
0x180067563  sub     r8, rdx
0x180067566  sar     r8, 5
0x18006756a  call    ??$_Assign_counted_range@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::vector<std::wstring>::_Assign_counted_range<std::wstring *>(std::wstring *,unsigned __int64)
0x18006756f  call    ?GetInstance@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance(void)
0x180067574  mov     edx, [rdi+130h]
0x18006757a  mov     rcx, rax
0x18006757d  call    ?GetSectionSingleton@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@QEAAPEAVSectionSingleton@23@W4RecommenderKind@RecommenderEngineUtils@23@@Z; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetSectionSingleton(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind)
0x180067582  xorps   xmm0, xmm0
0x180067585  movdqu  xmmword ptr [rsp+0F8h+var_90], xmm0
0x18006758b  lock inc dword ptr [r15+8]
0x180067590  mov     [rsp+0F8h+var_90], r13
0x180067595  mov     [rsp+0F8h+var_90+8], r15
0x18006759a  lea     rcx, [rsp+0F8h+var_90]
0x18006759f  mov     [rsp+0F8h+var_C8], rcx
0x1800675a4  lea     rdx, [rsp+0F8h+var_C8]
0x1800675a9  mov     rcx, rax
0x1800675ac  call    ??$_Notify@V_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_ const &)
0x1800675b1  nop
0x1800675b2  mov     rcx, [rsp+0F8h+var_90+8]; this
0x1800675b7  test    rcx, rcx
0x1800675ba  jz      short loc_1800675C2
0x1800675bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800675c1  nop
0x1800675c2  mov     rcx, r15; this
0x1800675c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800675ca  mov     rax, [r14]
0x1800675cd  cmp     [rsi], rax
0x1800675d0  setnz   cl
0x1800675d3  mov     [rdi+11Ah], cl
0x1800675d9  mov     al, cl
0x1800675db  xor     al, 1
0x1800675dd  mov     [rdi+11Bh], al
0x1800675e3  jz      short loc_1800675EE
0x1800675e5  lea     rdx, stru_18010F018
0x1800675ec  jmp     short loc_1800675F9
0x1800675ee  test    cl, cl
0x1800675f0  jz      short loc_180067601
0x1800675f2  lea     rdx, stru_18010EFA0; unsigned __int16 *
0x1800675f9  mov     rcx, rdi; this
0x1800675fc  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180067601  mov     rax, [r14]
0x180067604  sub     rax, [rsi]
0x180067607  sar     rax, 3
0x18006760b  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180067615  imul    rax, rcx
0x180067619  mov     [rsp+0F8h+var_C8], rax
0x18006761e  lea     rcx, [rdi+130h]
0x180067625  lea     rdx, [rsp+0F8h+var_C8]
0x18006762a  call    ??$FileCleanupExecutionFinished@AEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@_K@CleanupRecommendationsLogger@@SAXAEAW4RecommenderKind@RecommenderEngineUtils@StorageSenseHandlers@SystemSettings@@$$QEA_K@Z; CleanupRecommendationsLogger::FileCleanupExecutionFinished<SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &,unsigned __int64>(SystemSettings::StorageSenseHandlers::RecommenderEngineUtils::RecommenderKind &,unsigned __int64 &&)
0x18006762f  mov     r15d, ebx
0x180067632  lea     rcx, [rsp+0F8h+var_C0]
0x180067637  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006763c  mov     eax, r15d
0x18006763f  mov     rcx, [rsp+0F8h+var_30]
0x180067647  xor     rcx, rsp; StackCookie
0x18006764a  call    __security_check_cookie
0x18006764f  mov     rbx, [rsp+0F8h+arg_18]
0x180067657  add     rsp, 0D0h
0x18006765e  pop     r15
0x180067660  pop     r14
0x180067662  pop     r13
0x180067664  pop     rdi
0x180067665  pop     rsi
0x180067666  retn
```
