# _lambda_b13bb2d520eda7eb632fbc60e1aba087_::operator()_wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits_

- ea: `0x18007e778`
- end: `0x18007edb9`
- name: `_lambda_b13bb2d520eda7eb632fbc60e1aba087_::operator()_wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits_`
- size: `1601`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800862d0`

## callees

- `0x1800060a0`
- `0x180007c80`
- `0x180008250`
- `0x180008d50`
- `0x1800093a0`
- `0x180009a80`
- `0x18000bba8`
- `0x18001484c`
- `0x18001ccf0`
- `0x180020720`
- `0x180025c10`
- `0x180025cb0`
- `0x180027f20`
- `0x18002edc0`
- `0x1800348f4`
- `0x180035340`
- `0x1800356c8`
- `0x1800717b8`
- `0x180071aec`
- `0x180073718`
- `0x18007d284`
- `0x18007e778`
- `0x180080bb4`
- `0x180081890`
- `0x180081a34`
- `0x180086980`
- `0x1800875c4`
- `0x18008ff80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007eb46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ec4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007eb46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ec4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ec77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ec77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ecaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ecaa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007ea77`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007ea77`

## string_xrefs

- `0x18007eda6`: `shellcommon\shell\wpccore\sync\sync\api.cpp`
- `0x18007e83d`: `SyncAppTimeLimitsWithMonitoringFlags: response:{0}, cv:{1}, attempt:{2}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall lambda_b13bb2d520eda7eb632fbc60e1aba087_::operator()_wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits_(
        __int64 *a1,
        __int64 a2)
{
  __int64 *v2; // r12
  __int64 *v3; // rdi
  _DWORD *v4; // rbp
  Private::Format *v5; // rbx
  _QWORD *v6; // rdx
  const unsigned __int16 *v7; // rdx
  _DWORD *v8; // rdx
  _DWORD v9[21]; // [rsp+0h] [rbp-168h] BYREF
  int v10; // [rsp+54h] [rbp-114h]
  __int64 *v11; // [rsp+60h] [rbp-108h]
  __int64 *v12; // [rsp+68h] [rbp-100h]
  __int64 v13; // [rsp+70h] [rbp-F8h]
  int v14; // [rsp+A8h] [rbp-C0h] BYREF

  v2 = a1;
  v12 = a1;
  v3 = a1;
  v11 = a1;
  v13 = a2;
  v9[20] = 0;
  v10 = 1;
  while ( 2 )
  {
    try
    {
      Sync::DownloadAppTimeLimitsPolicy((__int64)&v14, *v2, v3[1], v3[2], v3[3], (_QWORD *)v3[4], (_OWORD *)v3[5]);
    }
    catch ( ... )
    {
      v8 = v9;
      v4 = v8;
      if ( (int)v8[21] < 2 )
      {
        *(_OWORD *)(v4 + 34) = 0;
        *((_QWORD *)v4 + 19) = 0;
        *((_QWORD *)v4 + 20) = 0;
        std::wstring::_Construct<1,unsigned short const *>(
          (char **)v4 + 17,
          L"SyncAppTimeLimitsWithMonitoringFlags: retrying after exception, cv:{0}",
          0x46u);
        v5 = (Private::Format *)StringAlgo::FormatString(v4 + 52, v4 + 34);
        v6 = *(_QWORD **)(*((_QWORD *)v4 + 12) + 32LL);
        if ( v6[3] > 0xFu )
          v6 = (_QWORD *)*v6;
        StringAlgo::ToUnicode(v4 + 34, v6);
        v4[20] |= 4u;
        v7 = (const unsigned __int16 *)(v4 + 34);
        if ( *((_QWORD *)v4 + 20) > 7u )
          v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 17);
        Private::Format::Replace(v5, v7);
        std::wstring::~wstring((char **)v4 + 17);
        v4[18] = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(v4 + 18, v5);
        std::wstring::~wstring((char **)v4 + 26);
        Sleep(0x12Cu);
        v2 = v12;
        v3 = v12;
        ++v10;
        continue;
      }
      throw;
    }
    break;
  }
}

```

## disassembly

```asm
0x18007e778  mov     [rsp+arg_10], rbx
0x18007e77d  push    rdi
0x18007e77e  push    r12
0x18007e780  push    r13
0x18007e782  push    r14
0x18007e784  push    r15
0x18007e786  sub     rsp, 140h
0x18007e78d  mov     rax, cs:__security_cookie
0x18007e794  xor     rax, rsp
0x18007e797  mov     [rsp+168h+var_30], rax
0x18007e79f  mov     r13, rdx
0x18007e7a2  mov     r12, rcx
0x18007e7a5  mov     [rsp+168h+var_100], rcx
0x18007e7aa  mov     rdi, rcx
0x18007e7ad  mov     [rsp+168h+var_108], rcx
0x18007e7b2  mov     [rsp+168h+var_F8], rdx
0x18007e7b7  xor     r14d, r14d
0x18007e7ba  mov     [rsp+168h+var_118], r14d
0x18007e7bf  mov     [rsp+168h+var_114], 1
0x18007e7c7  lea     ebx, [r14+1]
0x18007e7cb  cmp     ebx, 2
0x18007e7ce  jg      loc_18007ED06
0x18007e7d4  mov     rax, [rdi+28h]
0x18007e7d8  mov     [rsp+168h+var_138], rax
0x18007e7dd  mov     rax, [rdi+20h]
0x18007e7e1  mov     [rsp+168h+var_140], rax
0x18007e7e6  mov     rax, [rdi+18h]
0x18007e7ea  mov     [rsp+168h+var_148], rax
0x18007e7ef  mov     r9, [rdi+10h]
0x18007e7f3  mov     r8, [rdi+8]
0x18007e7f7  mov     rdx, [r12]
0x18007e7fb  lea     rcx, [rsp+168h+var_C0]
0x18007e803  call    ?DownloadAppTimeLimitsPolicy@Sync@@YA?AU?$pair@KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVSid@@AEBVTicketContainer@1@AEBV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@AEAVSyncErrorContainer@1@@Z; Sync::DownloadAppTimeLimitsPolicy(Sid const &,Sync::TicketContainer const &,Optional<std::wstring> const &,std::wstring const &,std::string const &,Sync::SyncErrorContainer &)
0x18007e809  mov     eax, [rsp+168h+var_C0]
0x18007e810  mov     dword ptr [rsp+168h+pv], eax
0x18007e814  xorps   xmm0, xmm0
0x18007e817  movups  xmmword ptr [rsp+168h+var_E0], xmm0
0x18007e81f  mov     [rsp+168h+var_D0], 0
0x18007e82b  mov     [rsp+168h+var_C8], 0
0x18007e837  mov     r8d, 47h ; 'G'
0x18007e83d  lea     rdx, aSyncapptimelim_1; "SyncAppTimeLimitsWithMonitoringFlags: r"...
0x18007e844  lea     rcx, [rsp+168h+var_E0]
0x18007e84c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e851  lea     rdx, [rsp+168h+var_E0]
0x18007e859  lea     rcx, [rsp+168h+var_98]
0x18007e861  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18007e866  nop
0x18007e867  lea     rdx, [rsp+168h+pv]
0x18007e86c  mov     rcx, rax; this
0x18007e86f  call    ??$?LK@Format@Private@@QEAAAEAV01@AEBK@Z; Private::Format::operator%<ulong>(ulong const &)
0x18007e874  mov     rbx, rax
0x18007e877  mov     rdx, [rdi+20h]
0x18007e87b  cmp     qword ptr [rdx+18h], 0Fh
0x18007e880  jbe     short loc_18007E885
0x18007e882  mov     rdx, [rdx]
0x18007e885  lea     rcx, [rsp+168h+var_E0]
0x18007e88d  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; StringAlgo::ToUnicode(char const *)
0x18007e892  or      r14d, 1
0x18007e896  mov     [rsp+168h+var_118], r14d
0x18007e89b  lea     rdx, [rsp+168h+var_E0]
0x18007e8a3  cmp     [rsp+168h+var_C8], 7
0x18007e8ac  cmova   rdx, [rsp+168h+var_E0]; unsigned __int16 *
0x18007e8b5  mov     rcx, rbx; this
0x18007e8b8  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x18007e8bd  nop
0x18007e8be  lea     rcx, [rsp+168h+var_E0]
0x18007e8c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e8cb  lea     rdx, [rsp+168h+var_114]
0x18007e8d0  lea     rcx, [rsp+168h+var_E0]
0x18007e8d8  call    ??$ToString@H@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBH@Z; StringAlgo::ToString<int>(int const &)
0x18007e8dd  nop
0x18007e8de  cmp     qword ptr [rax+18h], 7
0x18007e8e3  jbe     short loc_18007E8E8
0x18007e8e5  mov     rax, [rax]
0x18007e8e8  mov     rdx, rax; unsigned __int16 *
0x18007e8eb  mov     rcx, rbx; this
0x18007e8ee  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x18007e8f3  nop
0x18007e8f4  lea     rcx, [rsp+168h+var_E0]
0x18007e8fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e901  mov     dword ptr [rsp+168h+var_120], 2
0x18007e909  mov     rdx, rbx
0x18007e90c  lea     rcx, [rsp+168h+var_120]
0x18007e911  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18007e916  nop
0x18007e917  lea     rcx, [rsp+168h+var_98]
0x18007e91f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007e924  mov     dword ptr [rsp+168h+var_120], 3
0x18007e92c  lea     rdx, [rsp+168h+var_B8]
0x18007e934  lea     rcx, [rsp+168h+var_120]
0x18007e939  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18007e93e  lea     rdx, [rsp+168h+pv]
0x18007e943  mov     rcx, r13
0x18007e946  call    ??$ResponseCode@AEBK@SyncAppTimeLimits@SyncLogger@Internal@Sync@wpc@@QEAAXAEBK@Z; wpc::Sync::Internal::SyncLogger::SyncAppTimeLimits::ResponseCode<ulong const &>(ulong const &)
0x18007e94b  mov     r15d, dword ptr [rsp+168h+pv]
0x18007e950  mov     eax, r15d
0x18007e953  sub     eax, 0C8h
0x18007e958  jz      loc_18007EA91
0x18007e95e  sub     eax, 1
0x18007e961  jz      loc_18007EA91
0x18007e967  sub     eax, 1
0x18007e96a  jz      loc_18007EA91
0x18007e970  sub     eax, 1
0x18007e973  jz      loc_18007EA91
0x18007e979  cmp     eax, 1
0x18007e97c  jz      short loc_18007E98B
0x18007e97e  cmp     r15d, 130h
0x18007e985  jz      loc_18007EA91
0x18007e98b  mov     ebx, [rsp+168h+var_114]
0x18007e98f  cmp     ebx, 2
0x18007e992  jge     loc_18007ED2F
0x18007e998  xorps   xmm0, xmm0
0x18007e99b  movups  xmmword ptr [rsp+168h+var_E0], xmm0
0x18007e9a3  mov     [rsp+168h+var_D0], 0
0x18007e9af  mov     [rsp+168h+var_C8], 0
0x18007e9bb  mov     r8d, 51h ; 'Q'
0x18007e9c1  lea     rdx, aSyncapptimelim; "SyncAppTimeLimitsWithMonitoringFlags: r"...
0x18007e9c8  lea     rcx, [rsp+168h+var_E0]
0x18007e9d0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007e9d5  lea     rdx, [rsp+168h+var_E0]
0x18007e9dd  lea     rcx, [rsp+168h+var_98]
0x18007e9e5  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18007e9ea  nop
0x18007e9eb  lea     rdx, [rsp+168h+pv]
0x18007e9f0  mov     rcx, rax; this
0x18007e9f3  call    ??$?LK@Format@Private@@QEAAAEAV01@AEBK@Z; Private::Format::operator%<ulong>(ulong const &)
0x18007e9f8  mov     r15, rax
0x18007e9fb  mov     rdx, [rdi+20h]
0x18007e9ff  cmp     qword ptr [rdx+18h], 0Fh
0x18007ea04  jbe     short loc_18007EA09
0x18007ea06  mov     rdx, [rdx]
0x18007ea09  lea     rcx, [rsp+168h+var_E0]
0x18007ea11  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; StringAlgo::ToUnicode(char const *)
0x18007ea16  or      r14d, 2
0x18007ea1a  mov     [rsp+168h+var_118], r14d
0x18007ea1f  lea     rdx, [rsp+168h+var_E0]
0x18007ea27  cmp     [rsp+168h+var_C8], 7
0x18007ea30  cmova   rdx, [rsp+168h+var_E0]; unsigned __int16 *
0x18007ea39  mov     rcx, r15; this
0x18007ea3c  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x18007ea41  nop
0x18007ea42  lea     rcx, [rsp+168h+var_E0]
0x18007ea4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ea4f  mov     dword ptr [rsp+168h+var_120], 2
0x18007ea57  mov     rdx, r15
0x18007ea5a  lea     rcx, [rsp+168h+var_120]
0x18007ea5f  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18007ea64  nop
0x18007ea65  lea     rcx, [rsp+168h+var_98]
0x18007ea6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ea72  mov     ecx, 12Ch; dwMilliseconds
0x18007ea77  call    cs:__imp_Sleep
0x18007ea7d  nop
0x18007ea7e  lea     rcx, [rsp+168h+var_B8]
0x18007ea86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ea8b  nop
0x18007ea8c  jmp     loc_18007ECFB
0x18007ea91  lea     rdx, [rsp+168h+var_B8]
0x18007ea99  lea     rcx, [rsp+168h+var_68]
0x18007eaa1  call    ?ParseAppTimeLimitsPolicyWithMonitoringFlags@Sync@@YA?AV?$tuple@UAppTimeLimitsSettings@Policy@wpc@@UMonitoringFlags@Sync@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEAVSyncErrorContainer@1@@Z; Sync::ParseAppTimeLimitsPolicyWithMonitoringFlags(std::wstring const &,Sync::SyncErrorContainer &)
0x18007eaa6  nop
0x18007eaa7  lea     rdx, [rsp+168h+var_60]
0x18007eaaf  lea     rcx, [rsp+168h+var_98]
0x18007eab7  call    ??0AppTimeLimitsSettings@Policy@wpc@@QEAA@$$QEAU012@@Z; wpc::Policy::AppTimeLimitsSettings::AppTimeLimitsSettings(wpc::Policy::AppTimeLimitsSettings &&)
0x18007eabc  mov     rdx, rax
0x18007eabf  mov     rcx, [rdi+30h]
0x18007eac3  call    ??$?4UAppTimeLimitsSettings@Policy@wpc@@@?$Optional@UAppTimeLimitsSettings@Policy@wpc@@@@QEAAAEAV0@UAppTimeLimitsSettings@Policy@wpc@@@Z; Optional<wpc::Policy::AppTimeLimitsSettings>::operator=<wpc::Policy::AppTimeLimitsSettings>(wpc::Policy::AppTimeLimitsSettings)
0x18007eac8  mov     rcx, [rdi+38h]
0x18007eacc  movzx   eax, [rsp+168h+var_68]
0x18007ead4  mov     [rcx], ax
0x18007ead7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60845038@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60845038@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60845038> `wil::Feature<__WilFeatureTraits_Feature_60845038>::GetImpl(void)'::`2'::impl
0x18007eade  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60845038@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60845038>::__private_IsEnabled(void)
0x18007eae3  test    al, al
0x18007eae5  jz      loc_18007ECB1
0x18007eaeb  mov     rax, [rdi+38h]
0x18007eaef  mov     cl, [rax]
0x18007eaf1  mov     [rsp+168h+var_127], cl
0x18007eaf5  mov     al, [rax+1]
0x18007eaf8  mov     [rsp+168h+var_128], al
0x18007eafc  mov     [rsp+168h+pv], 0
0x18007eb05  lea     rcx, [rsp+168h+pv]
0x18007eb0a  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>::ensure_data(void)
0x18007eb0f  mov     rcx, [rax]
0x18007eb12  add     rcx, 8
0x18007eb16  lea     rdx, [rsp+168h+var_F0]
0x18007eb1b  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18007eb20  lea     rcx, [rsp+168h+pv]
0x18007eb25  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>::ensure_data(void)
0x18007eb2a  mov     r14, [rax]
0x18007eb2d  mov     [rsp+168h+var_120], r14
0x18007eb32  test    r14, r14
0x18007eb35  jz      short loc_18007EB3F
0x18007eb37  lock inc dword ptr [r14+120h]
0x18007eb3f  lea     rcx, [r14+0C8h]; lpCriticalSection
0x18007eb46  call    cs:__imp_EnterCriticalSection
0x18007eb4c  inc     dword ptr [r14+0F0h]
0x18007eb53  mov     [r14+118h], r15d
0x18007eb5a  cmp     [rsp+168h+var_A8], 0
0x18007eb63  setnz   al
0x18007eb66  mov     [r14+110h], al
0x18007eb6d  lea     r12, [rsp+168h+var_B8]
0x18007eb75  cmp     [rsp+168h+var_A0], 7
0x18007eb7e  cmova   r12, [rsp+168h+var_B8]
0x18007eb87  mov     r13, [rsp+168h+var_A8]
0x18007eb8f  lea     r15, ds:0[r13*2]
0x18007eb97  cmp     r13, 0Eh
0x18007eb9b  jb      short loc_18007EBCA
0x18007eb9d  lea     rbx, [r15+r12]
0x18007eba1  mov     r9d, 0Eh
0x18007eba7  mov     r8, cs:off_1800B3C78; "\"runWpcmonExe\""
0x18007ebae  mov     rdx, rbx
0x18007ebb1  mov     rcx, r12
0x18007ebb4  call    __std_search_2
0x18007ebb9  cmp     rax, rbx
0x18007ebbc  jz      short loc_18007EBCA
0x18007ebbe  sub     rax, r12
0x18007ebc1  sar     rax, 1
0x18007ebc4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007ebc8  jmp     short loc_18007EBD1
0x18007ebca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007ebce  mov     rax, rdi
0x18007ebd1  cmp     rax, rdi
0x18007ebd4  setnz   al
0x18007ebd7  mov     [r14+111h], al
0x18007ebde  cmp     r13, 0Eh
0x18007ebe2  jb      short loc_18007EC0D
0x18007ebe4  lea     rbx, [r12+r15]
0x18007ebe8  mov     r9d, 0Eh
0x18007ebee  mov     r8, cs:off_1800B3C68; "\"runWpcmonSvc\""
0x18007ebf5  mov     rdx, rbx
0x18007ebf8  mov     rcx, r12
0x18007ebfb  call    __std_search_2
0x18007ec00  cmp     rax, rbx
0x18007ec03  jz      short loc_18007EC0D
0x18007ec05  sub     rax, r12
0x18007ec08  sar     rax, 1
0x18007ec0b  jmp     short loc_18007EC10
0x18007ec0d  mov     rax, rdi
0x18007ec10  cmp     rax, rdi
0x18007ec13  setnz   al
0x18007ec16  mov     [r14+112h], al
0x18007ec1d  mov     al, [rsp+168h+var_128]
0x18007ec21  mov     [r14+113h], al
0x18007ec28  mov     al, [rsp+168h+var_127]
0x18007ec2c  mov     [r14+114h], al
0x18007ec33  mov     rax, [rsp+168h+pv]
0x18007ec38  test    rax, rax
0x18007ec3b  jz      short loc_18007EC7D
0x18007ec3d  lea     rbx, [rax+8]
0x18007ec41  lea     r14, [rbx+0C0h]
0x18007ec48  mov     rcx, r14; lpCriticalSection
0x18007ec4b  call    cs:__imp_EnterCriticalSection
0x18007ec51  or      dword ptr [rbx+40h], 300h
0x18007ec58  cmp     qword ptr [rbx+0F0h], 0
0x18007ec60  jz      short loc_18007EC6F
0x18007ec62  mov     edx, 2
0x18007ec67  mov     rcx, rbx
0x18007ec6a  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18007ec6f  test    r14, r14
0x18007ec72  jz      short loc_18007EC7D
0x18007ec74  mov     rcx, r14; lpCriticalSection
0x18007ec77  call    cs:__imp_LeaveCriticalSection
0x18007ec7d  lea     rcx, [rsp+168h+var_120]
0x18007ec82  call    ??1?$test_data_control@V?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>::~test_data_control<tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>>(void)
0x18007ec87  mov     rbx, [rsp+168h+pv]
0x18007ec8c  test    rbx, rbx
0x18007ec8f  jz      short loc_18007ECB1
0x18007ec91  mov     eax, edi
0x18007ec93  lock xadd [rbx+120h], eax
0x18007ec9b  add     eax, edi
0x18007ec9d  jnz     short loc_18007ECB1
0x18007ec9f  mov     rcx, rbx
0x18007eca2  call    ??1?$merged_data@U_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest@TipTests@Sync@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>::~merged_data<Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest,Sync::TipTests::_tip_SyncAppTimeLimitsWithMonitoringFlagsTipTest>(void)
0x18007eca7  mov     rcx, rbx; pv
0x18007ecaa  call    cs:__imp_CoTaskMemFree
0x18007ecb0  nop
0x18007ecb1  lea     rcx, [rsp+168h+var_40]
0x18007ecb9  call    ??1?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UTimeLimitsRule@Policy@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UTimeLimitsRule@Policy@wpc@@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>(void)
0x18007ecbe  cmp     [rsp+168h+var_48], 0
0x18007ecc7  jz      short loc_18007ECD5
0x18007ecc9  mov     [rsp+168h+var_48], 0
0x18007ecd5  lea     rcx, [rsp+168h+var_B8]
0x18007ecdd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ece2  nop
0x18007ece3  jmp     short loc_18007ED06
0x18007ece5  mov     ebx, [rsp+168h+var_114]
0x18007ece9  mov     r14d, [rsp+168h+var_118]
0x18007ecee  mov     r12, [rsp+168h+var_100]
0x18007ecf3  mov     rdi, r12
0x18007ecf6  mov     r13, [rsp+168h+var_F8]
0x18007ecfb  inc     ebx
0x18007ecfd  mov     [rsp+168h+var_114], ebx
0x18007ed01  jmp     loc_18007E7CB
0x18007ed06  mov     rcx, [rsp+168h+var_30]
0x18007ed0e  xor     rcx, rsp; StackCookie
0x18007ed11  call    __security_check_cookie
0x18007ed16  mov     rbx, [rsp+168h+arg_10]
0x18007ed1e  add     rsp, 140h
0x18007ed25  pop     r15
0x18007ed27  pop     r14
  ... truncated ...
```
