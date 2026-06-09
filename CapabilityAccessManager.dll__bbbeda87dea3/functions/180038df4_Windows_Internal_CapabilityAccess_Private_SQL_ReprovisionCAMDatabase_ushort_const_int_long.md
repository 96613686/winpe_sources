# Windows::Internal::CapabilityAccess::Private::SQL::ReprovisionCAMDatabase(ushort const *,int,long)

- ea: `0x180038df4`
- end: `0x18003952e`
- name: `?ReprovisionCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YAJPEBGHJ@Z`
- size: `1850`
- prototype: `__int64 __fastcall(Windows::Internal::CapabilityAccess::Private::SQL *this, const unsigned __int16 *, __int64)`
- caller_count: `4`
- callee_count: `44`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800204f8`
- `0x18002bc40`
- `0x18004d850`
- `0x18004ea1c`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x180017bc4`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001dd1c`
- `0x18001dfc0`
- `0x18001e118`
- `0x18001e32c`
- `0x18001e42c`
- `0x180020fcc`
- `0x1800211d4`
- `0x18002392c`
- `0x1800293e8`
- `0x180029408`
- `0x18002a32c`
- `0x18002a920`
- `0x18002d638`
- `0x18002e704`
- `0x18002e79c`
- `0x18002f560`
- `0x18002fd78`
- `0x1800311c4`
- `0x18003121c`
- `0x1800314fc`
- `0x180031d34`
- `0x180033360`
- `0x180033404`
- `0x180033574`
- `0x180037460`
- `0x180038df4`
- `0x180039e9c`
- `0x18003b1a0`
- `0x18003e21c`
- `0x18003e25c`
- `0x18003e2e8`
- `0x18005b1dc`
- `0x18005b41c`
- `0x18005c2c8`
- `0x1800a25e8`
- `0x1800a37b8`
- `0x1800a3ef4`
- `0x1800a5134`
- `0x1800a6080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800393fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800393fa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180039170`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800391b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800391f0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180039170`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800391b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800391f0`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180038ebc`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180038ebc`

## string_xrefs

- `0x180039476`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180039490`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800394aa`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800394c3`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800394dc`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800394f1`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180039506`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003951b`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::SQL::ReprovisionCAMDatabase(
        Windows::Internal::CapabilityAccess::Private::SQL *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  DWORD CurrentThreadId; // eax
  int v5; // edx
  int v6; // r8d
  _QWORD *v7; // rax
  __int64 v8; // r14
  __int64 v9; // rax
  __int64 v10; // r8
  StateRepository::Database *v11; // r15
  __int64 v12; // rax
  const char *v13; // rdx
  int (*v14)(void *); // r8
  void *v15; // r9
  int v16; // eax
  __int64 i; // rsi
  Windows::Internal::CapabilityAccess::Private::SQL *v18; // rcx
  Windows::Internal::CapabilityAccess::Private::SQL *v19; // rcx
  __int64 CAMDatabasePath; // rax
  __int64 v21; // rax
  int v22; // eax
  int RuntimeTargetSchemaVersion; // eax
  int v24; // eax
  DWORD v25; // eax
  const char *v26; // r9
  __int64 result; // rax
  int v28; // [rsp+20h] [rbp-298h]
  char v29; // [rsp+31h] [rbp-287h] BYREF
  struct _GUID UnbiasedTime; // [rsp+40h] [rbp-278h] BYREF
  __int64 v31; // [rsp+50h] [rbp-268h] BYREF
  __int64 v32; // [rsp+58h] [rbp-260h]
  __int64 v33; // [rsp+60h] [rbp-258h]
  __int64 v34; // [rsp+68h] [rbp-250h] BYREF
  __int64 v35; // [rsp+70h] [rbp-248h] BYREF
  Windows::Internal::CapabilityAccess::Private::SQL *v36; // [rsp+78h] [rbp-240h] BYREF
  __int64 v37; // [rsp+80h] [rbp-238h] BYREF
  StateRepository::Database *v38; // [rsp+88h] [rbp-230h] BYREF
  std::_Ref_count_base *v39; // [rsp+90h] [rbp-228h]
  _QWORD v40[5]; // [rsp+98h] [rbp-220h] BYREF
  char v41; // [rsp+C0h] [rbp-1F8h]
  _BYTE v42[16]; // [rsp+C8h] [rbp-1F0h] BYREF
  _BYTE v43[56]; // [rsp+D8h] [rbp-1E0h] BYREF
  _BYTE v44[128]; // [rsp+110h] [rbp-1A8h] BYREF
  _BYTE v45[224]; // [rsp+190h] [rbp-128h] BYREF
  int v46[2]; // [rsp+270h] [rbp-48h] BYREF
  unsigned __int64 v47; // [rsp+288h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]
  int v49; // [rsp+2C8h] [rbp+10h] BYREF

  v49 = (int)a2;
  v36 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, CurrentThreadId, (__int64)this);
  }
  try
  {
    if ( !Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
        (const char *)0x8000FFFFLL,
        v28);
    _acquire___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &Windows::Internal::CapabilityAccess::Private::Globals::SemaphoreManager::m_databaseRecoverySemaphore,
      &v34,
      a3,
      0);
    if ( v34 )
    {
      v29 = 0;
      wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v45);
      *(_QWORD *)&UnbiasedTime.Data1 = 0;
      QueryUnbiasedInterruptTime((PULONGLONG)&UnbiasedTime.Data1);
      v35 = *(_QWORD *)&UnbiasedTime.Data1;
      v40[0] = v45;
      v40[1] = &v35;
      v40[2] = &v29;
      v40[3] = &v49;
      v40[4] = &v36;
      v41 = 1;
      Windows::Internal::CapabilityAccess::Private::Globals::ServiceStateTracker::SetDatabaseReadyState(0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids);
      }
      try
      {
        Windows::Internal::CapabilityAccess::Private::SQL::GetAllTableNames(&v31);
        v37 = 0;
        std::make_shared<StateRepository::Database,>(&v38);
        *(_QWORD *)&UnbiasedTime.Data1 = 0x43FA75E47D2743EELL;
        *(_DWORD *)UnbiasedTime.Data4 = -2124808784;
        *(_DWORD *)&UnbiasedTime.Data4[4] = 1096871268;
        v7 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                         v42,
                         &v38);
        Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(
          (Windows::Internal::CapabilityAccess::Private::SQL *)v43,
          v7,
          &UnbiasedTime,
          7);
        v8 = v32;
        for ( i = v31; i != v8; i += 32 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v9 = std::_String_val<std::_Simple_types<char>>::_Myptr(i);
            WPP_SF_s(*(_QWORD *)(v10 + 16), 13, v10, v9);
          }
          v11 = v38;
          *(_QWORD *)&UnbiasedTime.Data1 = std::_String_val<std::_Simple_types<char>>::_Myptr(i);
          v12 = Windows::Internal::CapabilityAccess::Private::SQL::FormatUTF8Statement<char const *>(
                  v46,
                  "DROP TABLE IF EXISTS %s",
                  (const char *)&UnbiasedTime);
          v13 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v12);
          v16 = StateRepository::Database::Execute(v11, v13, v14, v15);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xA39,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
              (const char *)(unsigned int)v16,
              v28);
          if ( v47 > 0xF )
            std::_Deallocate<16>(*(_QWORD *)v46, v47 + 1);
        }
        Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v43);
        Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v43);
        if ( v39 )
          std::_Ref_count_base::_Decref(v39);
        StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
        if ( v31 )
        {
          std::_Destroy_range<std::allocator<std::string>>(v31, v32);
          std::_Deallocate<16>(v31, (v33 - v31) & 0xFFFFFFFFFFFFFFE0uLL);
        }
      }
      catch ( ... )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids);
        }
      }
      v18 = (Windows::Internal::CapabilityAccess::Private::SQL *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids);
      }
      Windows::Internal::CapabilityAccess::Private::SQL::CreateStringTables(v18);
      Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(v19);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl'::`2'::impl) )
      {
        StateRepository::Database::Database((StateRepository::Database *)v44);
        CAMDatabasePath = Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath((int)v46);
        v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(CAMDatabasePath);
        v22 = StateRepository::Database::Open(v44, v21, 2);
        if ( v22 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA95,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v22,
            v28);
        std::wstring::_Tidy_deallocate(v46);
        RuntimeTargetSchemaVersion = Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::GetRuntimeTargetSchemaVersion();
        v24 = StateRepository::Database::SetPragma(
                (StateRepository::Database *)v44,
                "user_version",
                RuntimeTargetSchemaVersion);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA99,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
            (const char *)(unsigned int)v24,
            v28);
        StateRepository::Database::~Database((StateRepository::Database *)v44);
      }
      v29 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids);
      }
      v41 = 0;
      lambda_bf7297053d080727a3d0a631756caaba_::operator()(v40);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v45);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v25 = GetCurrentThreadId();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids, v25);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v34);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAA7,
                           (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x180038df4  mov     [rsp+arg_10], rbx
0x180038df9  mov     [rsp+arg_18], rsi
0x180038dfe  mov     [rsp+arg_8], edx
0x180038e02  push    rdi
0x180038e03  push    r14
0x180038e05  push    r15
0x180038e07  sub     rsp, 2A0h
0x180038e0e  mov     rax, cs:__security_cookie
0x180038e15  xor     rax, rsp
0x180038e18  mov     [rsp+2B8h+var_28], rax
0x180038e20  mov     rdi, rcx
0x180038e23  mov     [rsp+2B8h+var_240], rcx
0x180038e28  lea     rbx, WPP_GLOBAL_Control
0x180038e2f  mov     rax, cs:WPP_GLOBAL_Control
0x180038e36  cmp     rax, rbx
0x180038e39  jz      short loc_180038E65
0x180038e3b  test    byte ptr [rax+1Ch], 1
0x180038e3f  jz      short loc_180038E65
0x180038e41  cmp     byte ptr [rax+19h], 2
0x180038e45  jb      short loc_180038E65
0x180038e47  call    cs:__imp_GetCurrentThreadId
0x180038e4d  mov     qword ptr [rsp+2B8h+var_298], rdi; int
0x180038e52  mov     r9d, eax
0x180038e55  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e5c  mov     rcx, [rcx+10h]
0x180038e60  call    WPP_SF_dS
0x180038e65  mov     eax, cs:?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x180038e6b  nop
0x180038e6c  mov     rcx, [rsp+2B8h]; this
0x180038e74  cmp     eax, 1
0x180038e77  jb      loc_18003945B
0x180038e7d  xor     r9d, r9d
0x180038e80  lea     rdx, [rsp+2B8h+var_250]
0x180038e85  lea     rcx, ?m_databaseRecoverySemaphore@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x180038e8c  call    ?acquire@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180038e91  nop
0x180038e92  xor     edi, edi
0x180038e94  cmp     [rsp+2B8h+var_250], rdi
0x180038e99  jz      loc_1800393E2
0x180038e9f  mov     [rsp+2B8h+var_287], dil
0x180038ea4  lea     rcx, [rsp+2B8h+var_128]; this
0x180038eac  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x180038eb1  nop
0x180038eb2  mov     [rsp+2B8h+UnbiasedTime], rdi
0x180038eb7  lea     rcx, [rsp+2B8h+UnbiasedTime]; UnbiasedTime
0x180038ebc  call    cs:__imp_QueryUnbiasedInterruptTime
0x180038ec2  mov     rax, [rsp+2B8h+UnbiasedTime]
0x180038ec7  mov     [rsp+2B8h+var_248], rax
0x180038ecc  lea     rax, [rsp+2B8h+var_128]
0x180038ed4  mov     [rsp+2B8h+var_220], rax
0x180038edc  lea     rax, [rsp+2B8h+var_248]
0x180038ee1  mov     [rsp+2B8h+var_218], rax
0x180038ee9  lea     rax, [rsp+2B8h+var_287]
0x180038eee  mov     [rsp+2B8h+var_210], rax
0x180038ef6  lea     rax, [rsp+2B8h+arg_8]
0x180038efe  mov     [rsp+2B8h+var_208], rax
0x180038f06  lea     rax, [rsp+2B8h+var_240]
0x180038f0b  mov     [rsp+2B8h+var_200], rax
0x180038f13  mov     [rsp+2B8h+var_1F8], 1
0x180038f1b  xor     ecx, ecx; bool
0x180038f1d  call    ?SetDatabaseReadyState@ServiceStateTracker@Globals@Private@CapabilityAccess@Internal@Windows@@SAX_N@Z; Windows::Internal::CapabilityAccess::Private::Globals::ServiceStateTracker::SetDatabaseReadyState(bool)
0x180038f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f29  cmp     rcx, rbx
0x180038f2c  jz      short loc_180038F4D
0x180038f2e  test    byte ptr [rcx+1Ch], 1
0x180038f32  jz      short loc_180038F4D
0x180038f34  cmp     byte ptr [rcx+19h], 4
0x180038f38  jb      short loc_180038F4D
0x180038f3a  lea     edx, [rdi+0Ch]
0x180038f3d  lea     r8, WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids
0x180038f44  mov     rcx, [rcx+10h]
0x180038f48  call    WPP_SF_
0x180038f4d  mov     [rsp+2B8h+var_288], dil
0x180038f52  lea     rcx, [rsp+2B8h+var_268]
0x180038f57  call    ?GetAllTableNames@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetAllTableNames(uint)
0x180038f5c  nop
0x180038f5d  mov     [rsp+2B8h+var_238], rdi
0x180038f65  lea     rcx, [rsp+2B8h+var_230]
0x180038f6d  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x180038f72  nop
0x180038f73  mov     dword ptr [rsp+2B8h+UnbiasedTime], 7D2743EEh
0x180038f7b  mov     dword ptr [rsp+2B8h+UnbiasedTime+4], 43FA75E4h
0x180038f83  mov     [rsp+2B8h+var_270], 8159FDB0h
0x180038f8b  mov     [rsp+2B8h+var_26C], 4160ED64h
0x180038f93  lea     rdx, [rsp+2B8h+var_230]
0x180038f9b  lea     rcx, [rsp+2B8h+var_1F0]
0x180038fa3  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180038fa8  mov     r9d, 7
0x180038fae  lea     r8, [rsp+2B8h+UnbiasedTime]
0x180038fb3  mov     rdx, rax
0x180038fb6  lea     rcx, [rsp+2B8h+var_1E0]
0x180038fbe  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x180038fc3  nop
0x180038fc4  mov     rsi, qword ptr [rsp+2B8h+var_268]
0x180038fc9  mov     r14, qword ptr [rsp+2B8h+var_268+8]
0x180038fce  cmp     rsi, r14
0x180038fd1  jz      loc_180039083
0x180038fd7  mov     r8, cs:WPP_GLOBAL_Control
0x180038fde  cmp     r8, rbx
0x180038fe1  jz      short loc_18003900A
0x180038fe3  test    byte ptr [r8+1Ch], 1
0x180038fe8  jz      short loc_18003900A
0x180038fea  cmp     byte ptr [r8+19h], 4
0x180038fef  jb      short loc_18003900A
0x180038ff1  mov     rcx, rsi
0x180038ff4  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180038ff9  mov     edx, 0Dh
0x180038ffe  mov     r9, rax
0x180039001  mov     rcx, [r8+10h]
0x180039005  call    WPP_SF_s
0x18003900a  mov     r15, [rsp+2B8h+var_230]
0x180039012  mov     rcx, rsi
0x180039015  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18003901a  mov     [rsp+2B8h+UnbiasedTime], rax
0x18003901f  lea     r8, [rsp+2B8h+UnbiasedTime]
0x180039024  lea     rdx, aDropTableIfExi_1; "DROP TABLE IF EXISTS %s"
0x18003902b  lea     rcx, [rsp+2B8h+var_48]
0x180039033  call    ??$FormatUTF8Statement@PEBD@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBD$$QEAPEBD@Z; Windows::Internal::CapabilityAccess::Private::SQL::FormatUTF8Statement<char const *>(char const * const,char const * &&)
0x180039038  nop
0x180039039  mov     rcx, rax
0x18003903c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180039041  mov     rdx, rax; char *
0x180039044  mov     rcx, r15; this
0x180039047  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18003904c  mov     rcx, [rsp+2B8h]; this
0x180039054  test    eax, eax
0x180039056  js      loc_180039473
0x18003905c  mov     rdx, [rsp+2B8h+var_30]
0x180039064  cmp     rdx, 0Fh
0x180039068  jbe     short loc_18003907A
0x18003906a  inc     rdx
0x18003906d  mov     rcx, qword ptr [rsp+2B8h+var_48]
0x180039075  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003907a  add     rsi, 20h ; ' '
0x18003907e  jmp     loc_180038FCE
0x180039083  lea     rcx, [rsp+2B8h+var_1E0]; this
0x18003908b  call    ?CommitTransaction@DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction(void)
0x180039090  mov     [rsp+2B8h+var_288], 1
0x180039095  lea     rcx, [rsp+2B8h+var_1E0]; this
0x18003909d  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x1800390a2  nop
0x1800390a3  mov     rcx, [rsp+2B8h+var_228]; this
0x1800390ab  test    rcx, rcx
0x1800390ae  jz      short loc_1800390B6
0x1800390b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800390b5  nop
0x1800390b6  lea     rcx, [rsp+2B8h+var_238]; this
0x1800390be  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800390c3  nop
0x1800390c4  mov     rcx, qword ptr [rsp+2B8h+var_268]
0x1800390c9  test    rcx, rcx
0x1800390cc  jz      short loc_1800390EF
0x1800390ce  mov     rdx, qword ptr [rsp+2B8h+var_268+8]
0x1800390d3  call    ??$_Destroy_range@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@YAXPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::string>>(std::string *,std::string * const,std::allocator<std::string> &)
0x1800390d8  mov     rcx, qword ptr [rsp+2B8h+var_268]
0x1800390dd  mov     rdx, [rsp+2B8h+var_258]
0x1800390e2  sub     rdx, rcx
0x1800390e5  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800390e9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800390ee  nop
0x1800390ef  jmp     loc_1800392AF
0x1800390f4  xor     edi, edi
0x1800390f6  cmp     [rsp+2B8h+var_288], dil
0x1800390fb  jnz     loc_1800392A8
0x180039101  xorps   xmm0, xmm0
0x180039104  movdqu  [rsp+2B8h+var_268], xmm0
0x18003910a  mov     [rsp+2B8h+var_258], rdi
0x18003910f  mov     ebx, edi
0x180039111  cmp     ebx, 0Fh
0x180039114  jnb     short loc_180039158
0x180039116  call    ?GetUsageRecordingSemaphore@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAAEAV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@XZ
0x18003911b  mov     r9d, 2710h
0x180039121  lea     rdx, [rsp+2B8h+UnbiasedTime]
0x180039126  mov     rcx, rax
0x180039129  call    ?acquire@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003912e  nop
0x18003912f  cmp     [rsp+2B8h+UnbiasedTime], rdi
0x180039134  jz      loc_180039488
0x18003913a  lea     rdx, [rsp+2B8h+UnbiasedTime]
0x18003913f  lea     rcx, [rsp+2B8h+var_268]
0x180039144  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z
0x180039149  nop
0x18003914a  lea     rcx, [rsp+2B8h+UnbiasedTime]
0x18003914f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180039154  inc     ebx
0x180039156  jmp     short loc_180039111
0x180039158  lea     rcx, [rsp+2B8h+var_48]; int
0x180039160  call    ?GetCAMDatabasePath@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath(void)
0x180039165  mov     rcx, rax
0x180039168  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003916d  mov     rcx, rax; lpFileName
0x180039170  call    cs:__imp_DeleteFileW
0x180039176  mov     ebx, eax
0x180039178  lea     rcx, [rsp+2B8h+var_48]
0x180039180  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039185  test    ebx, ebx
0x180039187  jnz     short loc_180039198
0x180039189  call    cs:__imp_GetLastError
0x18003918f  cmp     eax, 2
0x180039192  jnz     loc_1800394A2
0x180039198  lea     rcx, [rsp+2B8h+var_48]; int
0x1800391a0  call    ?GetCAMDatabaseShmPath@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseShmPath(void)
0x1800391a5  mov     rcx, rax
0x1800391a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800391ad  mov     rcx, rax; lpFileName
0x1800391b0  call    cs:__imp_DeleteFileW
0x1800391b6  mov     ebx, eax
0x1800391b8  lea     rcx, [rsp+2B8h+var_48]
0x1800391c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800391c5  test    ebx, ebx
0x1800391c7  jnz     short loc_1800391D8
0x1800391c9  call    cs:__imp_GetLastError
0x1800391cf  cmp     eax, 2
0x1800391d2  jnz     loc_1800394BB
0x1800391d8  lea     rcx, [rsp+2B8h+var_48]; int
0x1800391e0  call    ?GetCAMDatabaseWalPath@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabaseWalPath(void)
0x1800391e5  mov     rcx, rax
0x1800391e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800391ed  mov     rcx, rax; lpFileName
0x1800391f0  call    cs:__imp_DeleteFileW
0x1800391f6  mov     ebx, eax
0x1800391f8  lea     rcx, [rsp+2B8h+var_48]
0x180039200  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039205  test    ebx, ebx
0x180039207  jnz     short loc_180039218
0x180039209  call    cs:__imp_GetLastError
0x18003920f  cmp     eax, 2
0x180039212  jnz     loc_1800394D4
0x180039218  lea     rcx, [rsp+2B8h+var_1A8]; this
0x180039220  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x180039225  nop
0x180039226  lea     rcx, [rsp+2B8h+var_48]; int
0x18003922e  call    ?GetCAMDatabasePath@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath(void)
0x180039233  nop
0x180039234  mov     rcx, rax
0x180039237  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003923c  mov     r8d, 2
0x180039242  mov     rdx, rax
0x180039245  lea     rcx, [rsp+2B8h+var_1A8]
0x18003924d  call    ?Open@Database@StateRepository@@QEAAJPEB_WW4OpenFlags@12@PEBI@Z; StateRepository::Database::Open(wchar_t const *,StateRepository::Database::OpenFlags,uint const *)
0x180039252  mov     rcx, [rsp+2B8h]; this
0x18003925a  test    eax, eax
0x18003925c  js      loc_1800394EE
0x180039262  lea     rcx, [rsp+2B8h+var_48]
0x18003926a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003926f  nop
0x180039270  lea     rcx, [rsp+2B8h+var_1A8]; this
0x180039278  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x18003927d  nop
0x18003927e  mov     rcx, qword ptr [rsp+2B8h+var_268]
0x180039283  test    rcx, rcx
0x180039286  jz      short loc_1800392A8
0x180039288  mov     rdx, qword ptr [rsp+2B8h+var_268+8]
0x18003928d  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z
0x180039292  mov     rcx, qword ptr [rsp+2B8h+var_268]
0x180039297  mov     rdx, [rsp+2B8h+var_258]
0x18003929c  sub     rdx, rcx
0x18003929f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800392a3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800392a8  lea     rbx, WPP_GLOBAL_Control
0x1800392af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392b6  cmp     rcx, rbx
0x1800392b9  jz      short loc_1800392DC
0x1800392bb  test    byte ptr [rcx+1Ch], 1
0x1800392bf  jz      short loc_1800392DC
0x1800392c1  cmp     byte ptr [rcx+19h], 4
0x1800392c5  jb      short loc_1800392DC
0x1800392c7  mov     edx, 10h
0x1800392cc  lea     r8, WPP_6bcbc0a63258347bc79449ed03003c7b_Traceguids
0x1800392d3  mov     rcx, [rcx+10h]
0x1800392d7  call    WPP_SF_
0x1800392dc  call    ?CreateStringTables@SQL@Private@CapabilityAccess@Internal@Windows@@YAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::CreateStringTables(void)
0x1800392e1  call    ?CreateRecordTables@SQL@Private@CapabilityAccess@Internal@Windows@@YAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::CreateRecordTables(void)
0x1800392e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload> `wil::Feature<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::GetImpl(void)'::`2'::impl
0x1800392ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_Hardening_Wave2_Frontload>::__private_IsEnabled(void)
0x1800392f2  test    al, al
0x1800392f4  jz      loc_18003938A
0x1800392fa  lea     rcx, [rsp+2B8h+var_1A8]; this
0x180039302  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x180039307  nop
0x180039308  lea     rcx, [rsp+2B8h+var_48]; int
0x180039310  call    ?GetCAMDatabasePath@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SQL::GetCAMDatabasePath(void)
0x180039315  nop
0x180039316  mov     rcx, rax
0x180039319  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003931e  mov     r8d, 2
0x180039324  mov     rdx, rax
0x180039327  lea     rcx, [rsp+2B8h+var_1A8]
0x18003932f  call    ?Open@Database@StateRepository@@QEAAJPEB_WW4OpenFlags@12@PEBI@Z; StateRepository::Database::Open(wchar_t const *,StateRepository::Database::OpenFlags,uint const *)
0x180039334  mov     rcx, [rsp+2B8h]; this
0x18003933c  test    eax, eax
0x18003933e  js      loc_180039503
0x180039344  lea     rcx, [rsp+2B8h+var_48]
0x18003934c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039351  call    ?GetRuntimeTargetSchemaVersion@UsageDatabaseManager@Globals@Private@CapabilityAccess@Internal@Windows@@SAHXZ; Windows::Internal::CapabilityAccess::Private::Globals::UsageDatabaseManager::GetRuntimeTargetSchemaVersion(void)
0x180039356  movsxd  r8, eax; __int64
0x180039359  lea     rdx, aUserVersion; "user_version"
0x180039360  lea     rcx, [rsp+2B8h+var_1A8]; this
0x180039368  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x18003936d  mov     rcx, [rsp+2B8h]; this
  ... truncated ...
```
