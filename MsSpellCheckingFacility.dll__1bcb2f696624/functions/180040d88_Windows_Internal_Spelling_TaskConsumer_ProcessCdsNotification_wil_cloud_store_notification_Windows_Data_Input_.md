# Windows::Internal::Spelling::TaskConsumer::ProcessCdsNotification(wil::cloud_store_notification<Windows::Data::Input::Text::RoamingDictionary> &)

- ea: `0x180040d88`
- end: `0x1800411ae`
- name: `?ProcessCdsNotification@TaskConsumer@Spelling@Internal@Windows@@AEAAXAEAV?$cloud_store_notification@URoamingDictionary@Text@Input@Data@Windows@@@wil@@@Z`
- size: `1062`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180046920`

## callees

- `0x180022cf0`
- `0x1800338a0`
- `0x18003fdc0`
- `0x1800405d4`
- `0x180040d88`
- `0x1800411b4`
- `0x180041284`
- `0x1800412ac`
- `0x1800412d8`
- `0x1800414cc`
- `0x1800414fc`
- `0x180041524`
- `0x180041570`
- `0x18004159c`
- `0x180041708`
- `0x180046ef8`
- `0x180047770`
- `0x180047b18`
- `0x180061320`
- `0x18006a0e4`
- `0x18007ded0`
- `0x18007df64`
- `0x18007e014`
- `0x18007f0b0`
- `0x18007ff94`
- `0x180080210`
- `0x180080350`
- `0x18008347c`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040f45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004103a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040f45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004103a`

## string_xrefs

- `0x180040e80`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180041029`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::Spelling::TaskConsumer::ProcessCdsNotification(WCHAR *this, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 **v5; // rsi
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rax
  int TickCount64; // r14d
  int FileSizeFromName; // ebx
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // eax
  const char *v14; // r9
  struct _TP_TIMER *v16; // rdx
  __int64 v17; // r8
  int v18; // [rsp+20h] [rbp-3A8h] BYREF
  int v19; // [rsp+24h] [rbp-3A4h] BYREF
  int v20; // [rsp+28h] [rbp-3A0h] BYREF
  int v21; // [rsp+2Ch] [rbp-39Ch] BYREF
  int v22; // [rsp+30h] [rbp-398h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-390h] BYREF
  __int64 v24; // [rsp+40h] [rbp-388h]
  _BYTE v25[8]; // [rsp+48h] [rbp-380h] BYREF
  __int64 v26; // [rsp+50h] [rbp-378h]
  _BYTE v27[16]; // [rsp+58h] [rbp-370h] BYREF
  WCHAR *v28; // [rsp+68h] [rbp-360h]
  _BYTE v29[16]; // [rsp+70h] [rbp-358h] BYREF
  _BYTE v30[8]; // [rsp+80h] [rbp-348h] BYREF
  int v31; // [rsp+88h] [rbp-340h]
  __int64 *v32; // [rsp+90h] [rbp-338h] BYREF
  int v33; // [rsp+98h] [rbp-330h]
  _BYTE v34[8]; // [rsp+A0h] [rbp-328h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-320h]
  _BYTE v36[8]; // [rsp+B0h] [rbp-318h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-310h]
  _BYTE v38[8]; // [rsp+C0h] [rbp-308h] BYREF
  char v39; // [rsp+C8h] [rbp-300h] BYREF
  __int64 v40; // [rsp+D8h] [rbp-2F0h]
  char v41; // [rsp+E8h] [rbp-2E0h]
  _QWORD v42[42]; // [rsp+100h] [rbp-2C8h] BYREF
  _QWORD v43[42]; // [rsp+250h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  v28 = this;
  wil::cloud_store_notification<Windows::Data::Input::Text::RoamingDictionary>::release_data_item(a2, v38);
  v4 = *((_QWORD *)this + 10);
  if ( !v4 || v4 != v40 )
  {
    wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v42,
      "ActivityProcessCdsNotification");
    v42[0] = &SpellingTelemetry::ActivityProcessCdsNotification::`vftable';
    SpellingTelemetry::ActivityProcessCdsNotification::StartActivity((SpellingTelemetry::ActivityProcessCdsNotification *)v42);
    if ( *((_QWORD *)this + 10) )
      SpellingTelemetry::CdsUpdateNotification();
    std::set<std::wstring>::set<std::wstring>(v27);
    v5 = (__int64 **)&v39;
    if ( !v38[0] )
      v5 = (__int64 **)v27;
    LOBYTE(v18) = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 6) + 24LL))(
           *((_QWORD *)this + 6),
           L"UserDictionaryUploaded",
           &v18);
    if ( v6 >= 0 )
    {
      if ( !(_BYTE)v18 )
      {
        if ( v41 )
        {
          SpellerTip::CDSNotificationHandledHelper::Completed();
          wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v42);
          SpellingTelemetry::IgnoreCdsNotificationByDefaultData();
        }
        else
        {
          TickCount64 = GetTickCount64();
          wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
            v43,
            "ActivityMergeCloudDictionary");
          v43[0] = &SpellingTelemetry::ActivityMergeCloudDictionary::`vftable';
          SpellingTelemetry::ActivityMergeCloudDictionary::StartActivity((SpellingTelemetry::ActivityMergeCloudDictionary *)v43);
          Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile((__int64)v25, this + 8, 0);
          Windows::Internal::Spelling::TaskConsumer::MergeList(v30, v25, v5);
          Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(this + 8, &v32);
          FileSizeFromName = Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(this + 8);
          v11 = std::set<std::wstring>::set<std::wstring>(v29);
          Windows::Internal::Spelling::TaskConsumer::UpdateMtf((__int64)this, 0, (__int64)v30, v11);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v29);
          try
          {
            if ( v26 )
              Windows::Internal::Spelling::TaskConsumer::SaveToCds((Windows::Internal::Spelling::TaskConsumer *)this);
            LOBYTE(v12) = 1;
            v13 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 6) + 32LL))(
                    *((_QWORD *)this + 6),
                    L"UserDictionaryUploaded",
                    v12);
            if ( v13 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2D0,
                (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roa"
                              "mingdictionarymanager.cpp",
                (const char *)(unsigned int)v13,
                v18);
            v20 = GetTickCount64() - TickCount64;
            v21 = FileSizeFromName;
            v22 = v31;
            v19 = v33;
            SpellingTelemetry::MergeCloudDictionary<unsigned int,unsigned int,unsigned int,unsigned int>(
              &v19,
              &v22,
              &v21,
              &v20);
            *((_DWORD *)this + 34) = 0;
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x2D9,
              (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roami"
                            "ngdictionarymanager.cpp",
              v14);
            Windows::Internal::Spelling::TaskConsumer::RetrySaveToCdsLater(
              (Windows::Internal::Spelling::TaskConsumer *)v28,
              v16,
              v17);
          }
          SpellerTip::CDSNotificationHandledHelper::Completed();
          wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v43);
          wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v42);
          std::tuple<std::set<std::wstring>,std::set<std::wstring>>::~tuple<std::set<std::wstring>,std::set<std::wstring>>(v30);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v25,
            v25);
          SpellingTelemetry::ActivityMergeCloudDictionary::~ActivityMergeCloudDictionary((SpellingTelemetry::ActivityMergeCloudDictionary *)v43);
        }
        goto LABEL_29;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AC,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdict"
                      "ionarymanager.cpp",
        (const char *)(unsigned int)v6,
        v18);
    }
    Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile((__int64)v23, this + 8, 0);
    if ( v5[1] )
    {
      Windows::Internal::Spelling::TaskConsumer::MakeDiff(v34, v23, v5);
      if ( v37 || v35 )
      {
        Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(this + 8, v5);
        Windows::Internal::Spelling::TaskConsumer::UpdateMtf((__int64)this, 0, (__int64)v36, (__int64)v34);
      }
      *((_QWORD *)this + 10) = v40;
      SpellerTip::CDSNotificationHandledHelper::Completed();
      wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v42);
      std::tuple<std::set<std::wstring>,std::set<std::wstring>>::~tuple<std::set<std::wstring>,std::set<std::wstring>>(v34);
    }
    else
    {
      if ( v24 )
      {
        Windows::Globalization::Spelling::UserDictionaries::ClearFile(this + 8);
        v7 = std::set<std::wstring>::set<std::wstring>(v25);
        v8 = std::set<std::wstring>::set<std::wstring>(v29);
        Windows::Internal::Spelling::TaskConsumer::UpdateMtf((__int64)this, 1, v8, v7);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v29);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v25);
      }
      SpellerTip::CDSNotificationHandledHelper::Completed();
      wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v42);
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v23,
      v23);
LABEL_29:
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v27);
    SpellingTelemetry::ActivityProcessCdsNotification::~ActivityProcessCdsNotification((SpellingTelemetry::ActivityProcessCdsNotification *)v42);
    return wil::cloud_store_data<Windows::Data::Input::Text::RoamingDictionary>::~cloud_store_data<Windows::Data::Input::Text::RoamingDictionary>(v38);
  }
  LOBYTE(v3) = 100;
  SpellerTip::CDSNotificationHandledHelper::Cancelled(v3);
  return wil::cloud_store_data<Windows::Data::Input::Text::RoamingDictionary>::~cloud_store_data<Windows::Data::Input::Text::RoamingDictionary>(v38);
}

```

## disassembly

```asm
0x180040d88  mov     [rsp+arg_10], rbx
0x180040d8d  mov     [rsp+arg_18], rsi
0x180040d92  push    rdi
0x180040d93  push    r14
0x180040d95  push    r15
0x180040d97  sub     rsp, 3B0h
0x180040d9e  mov     rax, cs:__security_cookie
0x180040da5  xor     rax, rsp
0x180040da8  mov     [rsp+3C8h+var_28], rax
0x180040db0  mov     rax, rdx
0x180040db3  mov     rdi, rcx
0x180040db6  mov     [rsp+3C8h+var_360], rcx
0x180040dbb  xor     r15d, r15d
0x180040dbe  lea     rdx, [rsp+3C8h+var_308]
0x180040dc6  mov     rcx, rax
0x180040dc9  call    ?release_data_item@?$cloud_store_notification@URoamingDictionary@Text@Input@Data@Windows@@@wil@@QEAA?AV?$cloud_store_data@URoamingDictionary@Text@Input@Data@Windows@@@2@XZ; wil::cloud_store_notification<Windows::Data::Input::Text::RoamingDictionary>::release_data_item(void)
0x180040dce  nop
0x180040dcf  mov     rax, [rdi+50h]
0x180040dd3  test    rax, rax
0x180040dd6  jz      short loc_180040DEE
0x180040dd8  cmp     rax, [rsp+3C8h+var_2F0]
0x180040de0  jnz     short loc_180040DEE
0x180040de2  mov     cl, 64h ; 'd'
0x180040de4  call    ?Cancelled@CDSNotificationHandledHelper@SpellerTip@@SAXW4FinalState@2@@Z; SpellerTip::CDSNotificationHandledHelper::Cancelled(SpellerTip::FinalState)
0x180040de9  jmp     loc_180041178
0x180040dee  lea     rdx, aActivityproces; "ActivityProcessCdsNotification"
0x180040df5  lea     rcx, [rsp+3C8h+var_2C8]
0x180040dfd  call    ??0?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040e02  lea     rax, ??_7ActivityProcessCdsNotification@SpellingTelemetry@@6B@; const SpellingTelemetry::ActivityProcessCdsNotification::`vftable'
0x180040e09  mov     [rsp+3C8h+var_2C8], rax
0x180040e11  lea     rcx, [rsp+3C8h+var_2C8]; this
0x180040e19  call    ?StartActivity@ActivityProcessCdsNotification@SpellingTelemetry@@QEAAXXZ; SpellingTelemetry::ActivityProcessCdsNotification::StartActivity(void)
0x180040e1e  nop
0x180040e1f  cmp     [rdi+50h], r15
0x180040e23  jz      short loc_180040E2A
0x180040e25  call    ?CdsUpdateNotification@SpellingTelemetry@@SAXXZ; SpellingTelemetry::CdsUpdateNotification(void)
0x180040e2a  lea     rcx, [rsp+3C8h+var_370]
0x180040e2f  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180040e34  nop
0x180040e35  cmp     [rsp+3C8h+var_308], r15b
0x180040e3d  lea     rsi, [rsp+3C8h+var_300]
0x180040e45  jnz     short loc_180040E4C
0x180040e47  lea     rsi, [rsp+3C8h+var_370]
0x180040e4c  mov     byte ptr [rsp+3C8h+var_3A8], r15b; int
0x180040e51  mov     rcx, [rdi+30h]
0x180040e55  mov     rax, [rcx]
0x180040e58  lea     r8, [rsp+3C8h+var_3A8]
0x180040e5d  lea     rdx, aUserdictionary; "UserDictionaryUploaded"
0x180040e64  mov     rax, [rax+18h]
0x180040e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e6d  mov     rcx, [rsp+3C8h]; this
0x180040e75  test    eax, eax
0x180040e77  jns     loc_180040F14
0x180040e7d  mov     r9d, eax; char *
0x180040e80  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180040e87  mov     edx, 2ACh; void *
0x180040e8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040e91  lea     rbx, [rdi+10h]
0x180040e95  xor     r8d, r8d
0x180040e98  mov     rdx, rbx
0x180040e9b  lea     rcx, [rsp+3C8h+var_390]
0x180040ea0  call    ?ReadWordsFromFile@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@_N@Z; Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile(std::wstring const &,bool)
0x180040ea5  nop
0x180040ea6  cmp     [rsi+8], r15
0x180040eaa  jnz     loc_1800410D3
0x180040eb0  cmp     [rsp+3C8h+var_388], r15
0x180040eb5  jz      short loc_180040EFD
0x180040eb7  mov     rcx, rbx
0x180040eba  call    ?ClearFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Globalization::Spelling::UserDictionaries::ClearFile(std::wstring const &)
0x180040ebf  lea     rcx, [rsp+3C8h+var_380]
0x180040ec4  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180040ec9  mov     rbx, rax
0x180040ecc  lea     rcx, [rsp+3C8h+var_358]
0x180040ed1  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180040ed6  nop
0x180040ed7  mov     r9, rbx
0x180040eda  mov     r8, rax
0x180040edd  mov     dl, 1
0x180040edf  mov     rcx, rdi
0x180040ee2  call    ?UpdateMtf@TaskConsumer@Spelling@Internal@Windows@@AEAAX_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Windows::Internal::Spelling::TaskConsumer::UpdateMtf(bool,std::set<std::wstring> const &,std::set<std::wstring> const &)
0x180040ee7  nop
0x180040ee8  lea     rcx, [rsp+3C8h+var_358]
0x180040eed  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180040ef2  nop
0x180040ef3  lea     rcx, [rsp+3C8h+var_380]
0x180040ef8  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180040efd  call    ?Completed@CDSNotificationHandledHelper@SpellerTip@@SAXXZ; SpellerTip::CDSNotificationHandledHelper::Completed(void)
0x180040f02  lea     rcx, [rsp+3C8h+var_2C8]
0x180040f0a  call    ?Stop@?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180040f0f  jmp     loc_18004114F
0x180040f14  cmp     byte ptr [rsp+3C8h+var_3A8], r15b
0x180040f19  jnz     loc_180040E91
0x180040f1f  cmp     [rsp+3C8h+var_2E0], r15b
0x180040f27  jz      short loc_180040F45
0x180040f29  call    ?Completed@CDSNotificationHandledHelper@SpellerTip@@SAXXZ; SpellerTip::CDSNotificationHandledHelper::Completed(void)
0x180040f2e  lea     rcx, [rsp+3C8h+var_2C8]
0x180040f36  call    ?Stop@?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180040f3b  call    ?IgnoreCdsNotificationByDefaultData@SpellingTelemetry@@SAXXZ; SpellingTelemetry::IgnoreCdsNotificationByDefaultData(void)
0x180040f40  jmp     loc_18004115F
0x180040f45  call    cs:__imp_GetTickCount64
0x180040f4b  mov     r14, rax
0x180040f4e  lea     rdx, aActivitymergec; "ActivityMergeCloudDictionary"
0x180040f55  lea     rcx, [rsp+3C8h+var_178]
0x180040f5d  call    ??0?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040f62  lea     rax, ??_7ActivityMergeCloudDictionary@SpellingTelemetry@@6B@; const SpellingTelemetry::ActivityMergeCloudDictionary::`vftable'
0x180040f69  mov     [rsp+3C8h+var_178], rax
0x180040f71  lea     rcx, [rsp+3C8h+var_178]; this
0x180040f79  call    ?StartActivity@ActivityMergeCloudDictionary@SpellingTelemetry@@QEAAXXZ; SpellingTelemetry::ActivityMergeCloudDictionary::StartActivity(void)
0x180040f7e  nop
0x180040f7f  lea     rbx, [rdi+10h]
0x180040f83  xor     r8d, r8d
0x180040f86  mov     rdx, rbx
0x180040f89  lea     rcx, [rsp+3C8h+var_380]
0x180040f8e  call    ?ReadWordsFromFile@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@_N@Z; Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile(std::wstring const &,bool)
0x180040f93  nop
0x180040f94  mov     r8, rsi
0x180040f97  lea     rdx, [rsp+3C8h+var_380]
0x180040f9c  lea     rcx, [rsp+3C8h+var_348]
0x180040fa4  call    ?MergeList@TaskConsumer@Spelling@Internal@Windows@@SA?AV?$tuple@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V12@@std@@AEBV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@AEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; Windows::Internal::Spelling::TaskConsumer::MergeList(std::map<std::wstring const,std::wstring> const &,std::set<std::wstring> const &)
0x180040fa9  nop
0x180040faa  lea     rdx, [rsp+3C8h+var_338]
0x180040fb2  mov     rcx, rbx; lpFileName
0x180040fb5  call    ?OverwriteWordsToFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(std::wstring const &,std::set<std::wstring> const &)
0x180040fba  mov     rcx, rbx
0x180040fbd  call    ?GetFileSizeFromName@UserDictionaries@Spelling@Globalization@Windows@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(std::wstring const &)
0x180040fc2  mov     rbx, rax
0x180040fc5  lea     rcx, [rsp+3C8h+var_358]
0x180040fca  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180040fcf  nop
0x180040fd0  mov     r9, rax
0x180040fd3  lea     r8, [rsp+3C8h+var_348]
0x180040fdb  xor     edx, edx
0x180040fdd  mov     rcx, rdi
0x180040fe0  call    ?UpdateMtf@TaskConsumer@Spelling@Internal@Windows@@AEAAX_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Windows::Internal::Spelling::TaskConsumer::UpdateMtf(bool,std::set<std::wstring> const &,std::set<std::wstring> const &)
0x180040fe5  nop
0x180040fe6  lea     rcx, [rsp+3C8h+var_358]
0x180040feb  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180040ff0  nop
0x180040ff1  cmp     [rsp+3C8h+var_378], r15
0x180040ff6  jz      short loc_180041000
0x180040ff8  mov     rcx, rdi; this
0x180040ffb  call    ?SaveToCds@TaskConsumer@Spelling@Internal@Windows@@AEAA_NXZ; Windows::Internal::Spelling::TaskConsumer::SaveToCds(void)
0x180041000  mov     rcx, [rdi+30h]
0x180041004  mov     rax, [rcx]
0x180041007  mov     r8b, 1
0x18004100a  lea     rdx, aUserdictionary; "UserDictionaryUploaded"
0x180041011  mov     rax, [rax+20h]
0x180041015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004101a  mov     rcx, [rsp+3C8h]; this
0x180041022  test    eax, eax
0x180041024  jns     short loc_18004103A
0x180041026  mov     r9d, eax; char *
0x180041029  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180041030  mov     edx, 2D0h; void *
0x180041035  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004103a  call    cs:__imp_GetTickCount64
0x180041040  sub     eax, r14d
0x180041043  mov     [rsp+3C8h+var_3A0], eax
0x180041047  mov     [rsp+3C8h+var_39C], ebx
0x18004104b  mov     eax, [rsp+3C8h+var_340]
0x180041052  mov     [rsp+3C8h+var_398], eax
0x180041056  mov     eax, [rsp+3C8h+var_330]
0x18004105d  mov     [rsp+3C8h+var_3A4], eax
0x180041061  lea     r9, [rsp+3C8h+var_3A0]
0x180041066  lea     r8, [rsp+3C8h+var_39C]
0x18004106b  lea     rdx, [rsp+3C8h+var_398]
0x180041070  lea     rcx, [rsp+3C8h+var_3A4]
0x180041075  call    ??$MergeCloudDictionary@IIII@SpellingTelemetry@@SAX$$QEAI000@Z; SpellingTelemetry::MergeCloudDictionary<uint,uint,uint,uint>(uint &&,uint &&,uint &&,uint &&)
0x18004107a  mov     [rdi+88h], r15d
0x180041081  jmp     short $+2
0x180041083  call    ?Completed@CDSNotificationHandledHelper@SpellerTip@@SAXXZ; SpellerTip::CDSNotificationHandledHelper::Completed(void)
0x180041088  lea     rcx, [rsp+3C8h+var_178]
0x180041090  call    ?Stop@?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180041095  lea     rcx, [rsp+3C8h+var_2C8]
0x18004109d  call    ?Stop@?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800410a2  nop
0x1800410a3  lea     rcx, [rsp+3C8h+var_348]
0x1800410ab  call    ??1?$tuple@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V12@@std@@QEAA@XZ; std::tuple<std::set<std::wstring>,std::set<std::wstring>>::~tuple<std::set<std::wstring>,std::set<std::wstring>>(void)
0x1800410b0  nop
0x1800410b1  lea     rdx, [rsp+3C8h+var_380]
0x1800410b6  lea     rcx, [rsp+3C8h+var_380]
0x1800410bb  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1800410c0  nop
0x1800410c1  lea     rcx, [rsp+3C8h+var_178]; this
0x1800410c9  call    ??1ActivityMergeCloudDictionary@SpellingTelemetry@@QEAA@XZ; SpellingTelemetry::ActivityMergeCloudDictionary::~ActivityMergeCloudDictionary(void)
0x1800410ce  jmp     loc_18004115F
0x1800410d3  mov     r8, rsi
0x1800410d6  lea     rdx, [rsp+3C8h+var_390]
0x1800410db  lea     rcx, [rsp+3C8h+var_328]
0x1800410e3  call    ?MakeDiff@TaskConsumer@Spelling@Internal@Windows@@SA?AV?$tuple@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V12@@std@@AEBV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@AEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; Windows::Internal::Spelling::TaskConsumer::MakeDiff(std::map<std::wstring const,std::wstring> const &,std::set<std::wstring> const &)
0x1800410e8  nop
0x1800410e9  cmp     [rsp+3C8h+var_310], r15
0x1800410f1  jnz     short loc_1800410FD
0x1800410f3  cmp     [rsp+3C8h+var_320], r15
0x1800410fb  jz      short loc_180041122
0x1800410fd  mov     rdx, rsi
0x180041100  mov     rcx, rbx; lpFileName
0x180041103  call    ?OverwriteWordsToFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(std::wstring const &,std::set<std::wstring> const &)
0x180041108  lea     r9, [rsp+3C8h+var_328]
0x180041110  lea     r8, [rsp+3C8h+var_318]
0x180041118  xor     edx, edx
0x18004111a  mov     rcx, rdi
0x18004111d  call    ?UpdateMtf@TaskConsumer@Spelling@Internal@Windows@@AEAAX_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Windows::Internal::Spelling::TaskConsumer::UpdateMtf(bool,std::set<std::wstring> const &,std::set<std::wstring> const &)
0x180041122  mov     rax, [rsp+3C8h+var_2F0]
0x18004112a  mov     [rdi+50h], rax
0x18004112e  call    ?Completed@CDSNotificationHandledHelper@SpellerTip@@SAXXZ; SpellerTip::CDSNotificationHandledHelper::Completed(void)
0x180041133  lea     rcx, [rsp+3C8h+var_2C8]
0x18004113b  call    ?Stop@?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180041140  nop
0x180041141  lea     rcx, [rsp+3C8h+var_328]
0x180041149  call    ??1?$tuple@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V12@@std@@QEAA@XZ; std::tuple<std::set<std::wstring>,std::set<std::wstring>>::~tuple<std::set<std::wstring>,std::set<std::wstring>>(void)
0x18004114e  nop
0x18004114f  lea     rdx, [rsp+3C8h+var_390]
0x180041154  lea     rcx, [rsp+3C8h+var_390]
0x180041159  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x18004115e  nop
0x18004115f  lea     rcx, [rsp+3C8h+var_370]
0x180041164  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180041169  nop
0x18004116a  lea     rcx, [rsp+3C8h+var_2C8]; this
0x180041172  call    ??1ActivityProcessCdsNotification@SpellingTelemetry@@QEAA@XZ; SpellingTelemetry::ActivityProcessCdsNotification::~ActivityProcessCdsNotification(void)
0x180041177  nop
0x180041178  lea     rcx, [rsp+3C8h+var_308]
0x180041180  call    ??1?$cloud_store_data@URoamingDictionary@Text@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::Text::RoamingDictionary>::~cloud_store_data<Windows::Data::Input::Text::RoamingDictionary>(void)
0x180041185  mov     rcx, [rsp+3C8h+var_28]
0x18004118d  xor     rcx, rsp; StackCookie
0x180041190  call    __security_check_cookie
0x180041195  lea     r11, [rsp+3C8h+var_18]
0x18004119d  mov     rbx, [r11+30h]
0x1800411a1  mov     rsi, [r11+38h]
0x1800411a5  mov     rsp, r11
0x1800411a8  pop     r15
0x1800411aa  pop     r14
0x1800411ac  pop     rdi
0x1800411ad  retn
```
