# CSmsInterceptor::Initialize(void)

- ea: `0x18000fd94`
- end: `0x180010946`
- name: `?Initialize@CSmsInterceptor@@QEAAJXZ`
- size: `2994`
- prototype: `__int64 __fastcall(CSmsInterceptor *__hidden this)`
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015c78`

## callees

- `0x180003a60`
- `0x180003a84`
- `0x180003a90`
- `0x180003ad4`
- `0x180003f50`
- `0x180003f8c`
- `0x180003fbc`
- `0x1800069f0`
- `0x180006a5c`
- `0x180006c84`
- `0x18000ae8c`
- `0x18000b7d0`
- `0x18000b868`
- `0x18000d8a8`
- `0x18000db54`
- `0x18000dc24`
- `0x18000dd64`
- `0x18000df8c`
- `0x18000eaa4`
- `0x18000ece0`
- `0x18000ee74`
- `0x18000f018`
- `0x18000f580`
- `0x18000fd94`
- `0x180010a28`
- `0x1800112e8`
- `0x180011778`
- `0x180011cc0`
- `0x18001c944`
- `0x18001d008`
- `0x18001d80c`
- `0x180026f00`
- `0x1800272e4`
- `0x1800275fc`
- `0x180027e1c`
- `0x180028090`
- `0x1800332b4`
- `0x180034780`
- `0x180034b80`
- `0x180035048`
- `0x180035660`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## string_xrefs

- `0x18000fe17`: `SmsInterceptStore.db`
- `0x18000ff86`: `CSmsInterceptor::Initialize`
- `0x18001005e`: `CSmsInterceptor::Initialize`
- `0x180010052`: `Loaded registration RegId: %S, RegName: %S, AppName: %S, UserSid: %S, IsTransient: %d, FilterXML: %S`
- `0x1800100e8`: `Cleaning up stale registration RegId: %S, RegName: %S for application: %S since the application is uninstalled.`
- `0x1800101c8`: `Cleaning up stale registration RegId: %S, RegName: %S for application: %S since it has not accessed messages for %d notifications`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CSmsInterceptor::Initialize(CSmsInterceptor *this)
{
  unsigned int v2; // esi
  _QWORD *v3; // rax
  int v4; // r12d
  char *i; // rdi
  char *v6; // rbx
  char *v7; // rsi
  char *v8; // r14
  int v9; // r12d
  const wchar_t *v10; // r14
  const wchar_t *v11; // rax
  const wchar_t *v12; // rax
  int v13; // r10d
  const WCHAR *v14; // r15
  const wchar_t *v15; // r8
  const wchar_t *v16; // rbx
  const wchar_t *v17; // rdx
  const wchar_t *v18; // rsi
  const wchar_t *v19; // rcx
  const wchar_t *v20; // r9
  void **p_Block; // rdx
  const WCHAR *v22; // rcx
  const wchar_t *v23; // rax
  const unsigned __int16 *v24; // rcx
  const wchar_t *v25; // rax
  unsigned int MaxNotifyCount; // eax
  unsigned int v27; // ecx
  const wchar_t *v28; // rax
  __int64 v29; // rax
  void *v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // rax
  volatile signed __int32 *v33; // rbx
  char *v34; // rdi
  CSmsMessageStore *v35; // r13
  char *v36; // r14
  char *v37; // r12
  unsigned __int64 v38; // rbx
  __int64 v39; // rax
  bool v40; // cf
  unsigned __int64 v41; // rax
  unsigned __int64 *v42; // rax
  char *v43; // r15
  __int64 *j; // rbx
  unsigned int v45; // ebx
  __int64 v46; // rcx
  unsigned int v47; // edi
  CSmsInterceptor *v48; // r13
  char *v49; // rsi
  unsigned int v50; // r13d
  char *v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // r14
  _QWORD *v55; // rax
  CRegistration **v56; // rax
  _QWORD *v57; // rbx
  const unsigned __int16 *v58; // r9
  const unsigned __int16 *v59; // rdx
  __int64 **v60; // rcx
  __int64 k; // rax
  __int64 *m; // rcx
  _QWORD *v63; // rdi
  __int64 v64; // rcx
  char *v65; // r14
  _QWORD *v66; // rbx
  __int64 n; // rsi
  char *v68; // rbx
  __int64 v69; // rax
  __int64 v70; // rcx
  __int64 v71; // r15
  __int64 v72; // rcx
  _QWORD *v73; // rsi
  char *v74; // rdi
  __int64 ii; // r14
  char *v76; // rbx
  __int64 v77; // rax
  __int64 v78; // rcx
  __int64 v79; // r15
  __int64 *v80; // rdx
  const unsigned __int16 *v81; // rax
  unsigned int v83; // [rsp+50h] [rbp-B0h] BYREF
  char v84; // [rsp+54h] [rbp-ACh]
  int v85; // [rsp+58h] [rbp-A8h]
  _QWORD v86[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v87; // [rsp+70h] [rbp-90h]
  void *v88[2]; // [rsp+78h] [rbp-88h] BYREF
  void *v89[2]; // [rsp+88h] [rbp-78h] BYREF
  void *v90; // [rsp+98h] [rbp-68h] BYREF
  volatile signed __int32 *v91; // [rsp+A0h] [rbp-60h]
  void *v92; // [rsp+A8h] [rbp-58h] BYREF
  CSmsMessageStore *v93; // [rsp+B8h] [rbp-48h]
  CSmsInterceptor *v94; // [rsp+C0h] [rbp-40h]
  char *v95; // [rsp+C8h] [rbp-38h]
  void *v96[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v97; // [rsp+E0h] [rbp-20h]
  void *v98; // [rsp+E8h] [rbp-18h] BYREF
  void *v99; // [rsp+F8h] [rbp-8h] BYREF
  void *Block; // [rsp+108h] [rbp+8h] BYREF
  void *v101[4]; // [rsp+118h] [rbp+18h] BYREF
  char v102[16]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v103[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v104; // [rsp+158h] [rbp+58h]
  unsigned __int64 v105; // [rsp+160h] [rbp+60h]
  _BYTE v106[40]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v107[2]; // [rsp+190h] [rbp+90h] BYREF
  char v108; // [rsp+1A0h] [rbp+A0h]
  CSmsInterceptor *v109; // [rsp+1A8h] [rbp+A8h]
  __int64 *v110; // [rsp+1C8h] [rbp+C8h]

  v94 = this;
  v2 = 0;
  v86[1] = 0;
  v3 = operator new(0x40u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v86[0] = v3;
  if ( *((_DWORD *)this + 16) )
  {
    v4 = -2147418113;
    goto LABEL_149;
  }
  CExecutionManager::Initialize((char *)this + 584);
  v93 = (CSmsInterceptor *)((char *)this + 104);
  v4 = CSmsMessageStore::Open((CSmsInterceptor *)((char *)this + 104), "SmsInterceptStore.db");
  v85 = v4;
  if ( v4 < 0 )
    goto LABEL_149;
  CSmsRpcUtils::GetUserSid((char *)this + 72);
  v101[2] = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v101[3] = (char *)this + 16;
  (**((void (__fastcall ***)(char *))this + 2))((char *)this + 16);
  *(_OWORD *)v96 = 0;
  v97 = 0;
  CRegistration::GetRegistrationIdList(v96);
  v107[0] = (__int64)&std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CSmsInterceptor::*)(std::shared_ptr<std::vector<unsigned char>> &),CSmsInterceptor *,std::_Ph<1> const &>,void,std::shared_ptr<std::vector<unsigned char>> &>::`vftable';
  v107[1] = (__int64)CSmsInterceptor::AcknowledgeMessageCallback;
  v108 = v84;
  v109 = this;
  v110 = v107;
  for ( i = (char *)v96[0]; ; i += 32 )
  {
    v6 = (char *)v96[1];
    if ( i == v96[1] )
      break;
    std::wstring::wstring(v103, i);
    v7 = (char *)operator new(0x1C8u);
    v95 = v7;
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<CRegistration>::`vftable';
    v8 = v7 + 16;
    CRegistration::CRegistration(v7 + 16, (__int64)v107);
    v90 = v7 + 16;
    v91 = (volatile signed __int32 *)v7;
    v9 = CRegistration::Load((CRegistration *)(v7 + 16));
    v85 = v9;
    if ( v9 < 0 )
    {
      v10 = (const wchar_t *)(v7 + 64);
      if ( *((_QWORD *)v7 + 11) > 7u )
        v10 = *(const wchar_t **)v10;
      v11 = (const wchar_t *)v103;
      if ( v105 > 7 )
        v11 = (const wchar_t *)v103[0];
      LogSmsRouterError(
        "CSmsInterceptor::Initialize",
        0x56u,
        v9,
        "Failed to load registration RegId: %S, RegName: %S",
        v11,
        v10);
      v85 = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v7)(v7);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
      }
      v2 = 0;
      goto LABEL_70;
    }
    v12 = (const wchar_t *)(v7 + 160);
    if ( *((_QWORD *)v7 + 23) > 7u )
      v12 = *(const wchar_t **)v12;
    v13 = *((_DWORD *)v7 + 12);
    v14 = (const WCHAR *)(v7 + 128);
    if ( *((_QWORD *)v7 + 19) <= 7u )
      v15 = (const wchar_t *)(v7 + 128);
    else
      v15 = *(const wchar_t **)v14;
    v16 = (const wchar_t *)(v7 + 96);
    if ( *((_QWORD *)v7 + 15) <= 7u )
      v17 = (const wchar_t *)(v7 + 96);
    else
      v17 = *(const wchar_t **)v16;
    v18 = (const wchar_t *)(v7 + 64);
    if ( *((_QWORD *)v8 + 9) <= 7u )
      v19 = (const wchar_t *)(v8 + 48);
    else
      v19 = *(const wchar_t **)v18;
    v20 = (const wchar_t *)v103;
    if ( v105 > 7 )
      v20 = (const wchar_t *)v103[0];
    LogSmsRouterInfo(
      "CSmsInterceptor::Initialize",
      0x62u,
      "Loaded registration RegId: %S, RegName: %S, AppName: %S, UserSid: %S, IsTransient: %d, FilterXML: %S",
      v20,
      v19,
      v17,
      v15,
      v13,
      v12);
    if ( *((_DWORD *)v8 + 8) )
    {
      p_Block = v101;
LABEL_65:
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        v86,
        p_Block,
        v8);
      goto LABEL_66;
    }
    if ( *((_DWORD *)v8 + 9) )
    {
      if ( *((_QWORD *)v8 + 17) > 7u )
        v14 = *(const WCHAR **)v14;
      if ( *((_QWORD *)v8 + 13) <= 7u )
        v22 = (const WCHAR *)(v8 + 80);
      else
        v22 = *(const WCHAR **)v16;
      if ( (unsigned int)CSmsRpcUtils::IsAppInstalled(v22, v14, 1) )
        goto LABEL_66;
      if ( *((_QWORD *)v8 + 13) > 7u )
        v16 = *(const wchar_t **)v16;
      if ( *((_QWORD *)v8 + 9) > 7u )
        v18 = *(const wchar_t **)v18;
      v23 = (const wchar_t *)v103;
      if ( v105 > 7 )
        v23 = (const wchar_t *)v103[0];
      LogSmsRouterError(
        "CSmsInterceptor::Initialize",
        0x77u,
        -2147023728,
        "Cleaning up stale registration RegId: %S, RegName: %S for application: %S since the application is uninstalled.",
        v23,
        v18,
        v16);
      p_Block = &Block;
      goto LABEL_65;
    }
    if ( *((_QWORD *)v8 + 17) <= 7u )
      v24 = (const unsigned __int16 *)(v8 + 112);
    else
      v24 = *(const unsigned __int16 **)v14;
    if ( !(unsigned int)CSmsRpcUtils::IsValidUserSid(v24) )
    {
      if ( *((_QWORD *)v8 + 17) > 7u )
        v14 = *(const WCHAR **)v14;
      if ( *((_QWORD *)v8 + 13) > 7u )
        v16 = *(const wchar_t **)v16;
      if ( *((_QWORD *)v8 + 9) > 7u )
        v18 = *(const wchar_t **)v18;
      v25 = (const wchar_t *)v103;
      if ( v105 > 7 )
        v25 = (const wchar_t *)v103[0];
      LogSmsRouterError(
        "CSmsInterceptor::Initialize",
        0x84u,
        -2147023559,
        "Cleaning up stale registration RegId: %S, RegName: %S for application: %S since the user: %S is now invalid.",
        v25,
        v18,
        v16,
        v14);
      p_Block = &v99;
      goto LABEL_65;
    }
    MaxNotifyCount = CRegistration::GetMaxNotifyCount();
    v27 = *((_DWORD *)v8 + 68);
    if ( v27 > MaxNotifyCount )
    {
      if ( *((_QWORD *)v8 + 13) > 7u )
        v16 = *(const wchar_t **)v16;
      if ( *((_QWORD *)v8 + 9) > 7u )
        v18 = *(const wchar_t **)v18;
      v28 = (const wchar_t *)v103;
      if ( v105 > 7 )
        v28 = (const wchar_t *)v103[0];
      LogSmsRouterError(
        "CSmsInterceptor::Initialize",
        0x91u,
        -2147019873,
        "Cleaning up stale registration RegId: %S, RegName: %S for application: %S since it has not accessed messages for"
        " %d notifications",
        v28,
        v18,
        v16,
        v27);
      p_Block = &v98;
      goto LABEL_65;
    }
LABEL_66:
    v29 = stdext::hash_map<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>>::operator[](
            (char *)this + 488,
            v8);
    std::shared_ptr<SmsStoreMessage>::operator=(v29, &v90);
    std::_Tree<std::_Tset_traits<std::shared_ptr<CRegistration>,CRegistrationPrioirtyCompare,std::allocator<std::shared_ptr<CRegistration>>,0>>::insert<0,0>(
      (char *)this + 552,
      &v92,
      &v90);
    v30 = v90;
    CSmsInterceptor::GetGroupId(v31, v106);
    v32 = std::map<std::wstring,std::set<std::wstring>>::operator[]((char *)this + 568, v106);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v32,
      v88,
      v30);
    std::wstring::~wstring(v106);
    v33 = v91;
    v2 = 0;
    if ( v91 )
    {
      if ( _InterlockedExchangeAdd(v91 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
LABEL_70:
    std::wstring::~wstring(v103);
  }
  v34 = (char *)v96[0];
  if ( v96[0] != v96[1] )
  {
    do
    {
      std::wstring::~wstring(v34);
      v34 += 32;
    }
    while ( v34 != v6 );
    v96[1] = v96[0];
  }
  *((_DWORD *)this + 16) = 1;
  v98 = 0;
  v99 = 0;
  v90 = 0;
  v89[0] = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v35 = v93;
  v36 = (char *)v93 + 8;
  v89[1] = (char *)v93 + 8;
  (**((void (__fastcall ***)(char *))v93 + 1))((char *)v93 + 8);
  Block = 0;
  v88[0] = 0;
  v92 = 0;
  v37 = (char *)operator new[](saturated_mul(*((_QWORD *)v35 + 40), 8u));
  Block = v37;
  v38 = *((_QWORD *)v35 + 40);
  v39 = 32 * v38;
  if ( !is_mul_ok(v38, 0x20u) )
    v39 = -1;
  v40 = __CFADD__(v39, 8);
  v41 = v39 + 8;
  if ( v40 )
    v41 = -1;
  v42 = (unsigned __int64 *)operator new[](v41);
  v101[0] = v42;
  *v42 = v38;
  v43 = (char *)(v42 + 1);
  v95 = (char *)(v42 + 1);
  `eh vector constructor iterator'(v42 + 1, 0x20u, v38, std::wstring::wstring, std::wstring::~wstring);
  v88[0] = v43;
  v92 = operator new[](saturated_mul(*((_QWORD *)v35 + 40), 4u));
  for ( j = (__int64 *)*((_QWORD *)v35 + 39); ; *((_DWORD *)v92 + v2++) = *((_DWORD *)j + 14) )
  {
    j = (__int64 *)*j;
    if ( j == *((__int64 **)v35 + 39) )
      break;
    *(_QWORD *)&v37[8 * v2] = j[2];
    std::wstring::operator=(&v43[32 * v2], j + 3);
  }
  v45 = *((_DWORD *)v35 + 80);
  v87 = v45;
  v83 = v45;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v36 + 8LL))(v36);
  v98 = v37;
  v99 = v43;
  v90 = v92;
  v89[0] = 0;
  v88[0] = 0;
  v47 = 0;
  v48 = v94;
  if ( v45 )
  {
    v49 = (char *)v94 + 488;
    v50 = v45;
    do
    {
      v51 = (char *)v101[0] + 32 * v47 + 8;
      v52 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v46, v51);
      v53 = *(_QWORD *)(std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
                          v49,
                          v102,
                          v51,
                          v52)
                      + 8);
      if ( !v53 || v53 == *((_QWORD *)v49 + 1) )
      {
        if ( *((_QWORD *)v51 + 3) > 7u )
          v51 = *(char **)v51;
        CSmsMessageStore::DeleteMessageDeliveryStatus(v93, *(_QWORD *)&v37[8 * v47], (const unsigned __int16 *)v51);
      }
      else
      {
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
          v86,
          v103,
          v51);
        v54 = v104;
        if ( *(_BYTE *)(v104 + 25) || (unsigned __int8)std::operator<<unsigned short>(v51, v104 + 32) || v54 == v86[0] )
        {
          v56 = (CRegistration **)stdext::hash_map<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>>::operator[](
                                    v49,
                                    v51);
          CRegistration::DeliveryMessage(*v56, *(_QWORD *)&v37[8 * v47], 0);
        }
        else
        {
          v55 = (_QWORD *)stdext::hash_map<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>>::operator[](
                            v49,
                            v51);
          std::_Tree<std::_Tset_traits<SmsServiceCallContext *,std::less<SmsServiceCallContext *>,std::allocator<SmsServiceCallContext *>,0>>::insert<0,0>(
            *v55 + 248LL,
            v106,
            &v37[8 * v47]);
        }
      }
      ++v47;
    }
    while ( v47 < v50 );
    v48 = v94;
    v43 = v95;
  }
  v57 = *(_QWORD **)v86[0];
  while ( v57 != (_QWORD *)v86[0] )
  {
    if ( *((_QWORD *)v48 + 12) <= 7u )
      v58 = (const unsigned __int16 *)((char *)v48 + 72);
    else
      v58 = (const unsigned __int16 *)*((_QWORD *)v48 + 9);
    v59 = (const unsigned __int16 *)(v57 + 4);
    if ( v57[7] > 7u )
      v59 = *(const unsigned __int16 **)v59;
    CSmsInterceptor::UnregisterForMessagesLocal(v48, v59, 0, v58);
    v60 = (__int64 **)v57[2];
    if ( *((_BYTE *)v60 + 25) )
    {
      for ( k = v57[1]; !*(_BYTE *)(k + 25) && v57 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
        v57 = (_QWORD *)k;
      v57 = (_QWORD *)k;
    }
    else
    {
      v57 = (_QWORD *)v57[2];
      for ( m = *v60; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v57 = m;
    }
  }
  CSmsMessageStore::GetMessageList((_DWORD)v48 + 104, 1, (unsigned int)v89, (unsigned int)v88, (__int64)&v83);
  v63 = v89[0];
  v98 = v89[0];
  operator delete(Block);
  v65 = (char *)v88[0];
  v99 = v88[0];
  if ( v43 )
  {
    v66 = v101[0];
    `eh vector destructor iterator'(v43, 0x20u, *(_QWORD *)v101[0], std::wstring::~wstring);
    operator delete[](v66, 32LL * *v66 + 8);
  }
  v89[0] = 0;
  v88[0] = 0;
  for ( n = 0; (unsigned int)n < v83; n = (unsigned int)(n + 1) )
  {
    v68 = &v65[32 * (unsigned int)n];
    if ( *((_QWORD *)v68 + 2)
      && (v69 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v64, &v65[32 * (unsigned int)n]),
          (v70 = *(_QWORD *)(std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
                               (char *)v48 + 488,
                               v106,
                               &v65[32 * (unsigned int)n],
                               v69)
                           + 8)) != 0)
      && v70 != *((_QWORD *)v48 + 62)
      && ((std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
             v86,
             v103,
             &v65[32 * (unsigned int)n]),
           v71 = v104,
           *(_BYTE *)(v104 + 25))
       || (unsigned __int8)std::operator<<unsigned short>(&v65[32 * (unsigned int)n], v104 + 32)
       || v71 == v86[0]) )
    {
      if ( *((_QWORD *)v68 + 3) > 7u )
        v68 = *(char **)v68;
      CSmsInterceptor::ScheduleProcessMessage(v48, v63[n], (const unsigned __int16 *)v68);
    }
    else
    {
      CSmsInterceptor::ScheduleNextRegistration(v48, v63[n], 0, 1);
    }
  }
  CSmsMessageStore::GetMessageList((_DWORD)v48 + 104, 2, (unsigned int)v89, (unsigned int)v88, (__int64)&v83);
  v73 = v89[0];
  v98 = v89[0];
  if ( v63 )
    operator delete(v63);
  v74 = (char *)v88[0];
  v99 = v88[0];
  if ( v65 )
  {
    `eh vector destructor iterator'(v65, 0x20u, *((_QWORD *)v65 - 1), std::wstring::~wstring);
    operator delete[](v65 - 8, 32LL * *((_QWORD *)v65 - 1) + 8);
  }
  for ( ii = 0; (unsigned int)ii < v83; ii = (unsigned int)(ii + 1) )
  {
    v76 = &v74[32 * (unsigned int)ii];
    if ( *((_QWORD *)v76 + 2)
      && (v77 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v72, &v74[32 * (unsigned int)ii]),
          (v78 = *(_QWORD *)(std::_Hash<stdext::_Hmap_traits<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>,0>>::_Find_last<std::wstring>(
                               (char *)v48 + 488,
                               v106,
                               &v74[32 * (unsigned int)ii],
                               v77)
                           + 8)) != 0)
      && v78 != *((_QWORD *)v48 + 62)
      && ((std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
             v86,
             v103,
             &v74[32 * (unsigned int)ii]),
           v79 = v104,
           *(_BYTE *)(v104 + 25))
       || (unsigned __int8)std::operator<<unsigned short>(&v74[32 * (unsigned int)ii], v104 + 32)
       || v79 == v86[0]) )
    {
      if ( *((_QWORD *)v76 + 3) > 7u )
        v76 = *(char **)v76;
    }
    else
    {
      v76 = 0;
    }
    CSmsInterceptor::ScheduleNextRegistration(v48, v73[ii], (const unsigned __int16 *)v76, 1);
  }
  operator delete(v92);
  if ( v74 )
  {
    `eh vector destructor iterator'(v74, 0x20u, *((_QWORD *)v74 - 1), std::wstring::~wstring);
    operator delete[](v74 - 8, 32LL * *((_QWORD *)v74 - 1) + 8);
  }
  if ( v73 )
    operator delete(v73);
  if ( v110 )
  {
    v80 = v107;
    LOBYTE(v80) = v110 != v107;
    (*(void (__fastcall **)(__int64 *, __int64 *))(*v110 + 32))(v110, v80);
    v110 = 0;
  }
  std::vector<std::wstring>::~vector<std::wstring>(v96);
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v48 + 2) + 8LL))((__int64)v48 + 16);
  v81 = (const unsigned __int16 *)((char *)v48 + 72);
  if ( *((_QWORD *)v48 + 12) > 7u )
    v81 = *(const unsigned __int16 **)v81;
  CSmsInterceptor::RegisterForMessages(
    v48,
    L"SmsDropAcceptImmediate",
    L"SmsRouter",
    v81,
    L"<SmsMessageFilter Action=\"Drop\" Flags=\"1\"><FilterRule></FilterRule></SmsMessageFilter>",
    0,
    0,
    0);
  CExecutionManager::Start((CSmsInterceptor *)((char *)v48 + 584));
  v4 = v85;
LABEL_149:
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v86);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000fd94  push    rbp
0x18000fd96  push    rbx
0x18000fd97  push    rsi
0x18000fd98  push    rdi
0x18000fd99  push    r12
0x18000fd9b  push    r13
0x18000fd9d  push    r14
0x18000fd9f  push    r15
0x18000fda1  lea     rbp, [rsp-0E8h]
0x18000fda9  sub     rsp, 1E8h
0x18000fdb0  mov     rax, cs:__security_cookie
0x18000fdb7  xor     rax, rsp
0x18000fdba  mov     [rbp+120h+var_50], rax
0x18000fdc1  mov     r13, rcx
0x18000fdc4  mov     [rbp+120h+var_160], rcx
0x18000fdc8  xor     esi, esi
0x18000fdca  mov     [rsp+220h+var_1C0], rsi
0x18000fdcf  mov     [rsp+220h+var_1B8], rsi
0x18000fdd4  lea     ecx, [rsi+40h]; Size
0x18000fdd7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fddc  mov     [rax], rax
0x18000fddf  mov     [rax+8], rax
0x18000fde3  mov     [rax+10h], rax
0x18000fde7  mov     word ptr [rax+18h], 101h
0x18000fded  mov     [rsp+220h+var_1C0], rax
0x18000fdf2  cmp     [r13+40h], esi
0x18000fdf6  jz      short loc_18000FE03
0x18000fdf8  mov     r12d, 8000FFFFh
0x18000fdfe  jmp     loc_180010916
0x18000fe03  lea     rcx, [r13+248h]; Context
0x18000fe0a  call    ?Initialize@CExecutionManager@@QEAAJXZ; CExecutionManager::Initialize(void)
0x18000fe0f  lea     r15, [r13+68h]
0x18000fe13  mov     [rbp+120h+var_168], r15
0x18000fe17  lea     rdx, aSmsinterceptst; "SmsInterceptStore.db"
0x18000fe1e  mov     rcx, r15; this
0x18000fe21  call    ?Open@CSmsMessageStore@@QEAAJPEAD@Z; CSmsMessageStore::Open(char *)
0x18000fe26  mov     r12d, eax
0x18000fe29  mov     [rsp+220h+var_1C8], eax
0x18000fe2d  test    eax, eax
0x18000fe2f  js      loc_180010916
0x18000fe35  lea     rcx, [r13+48h]
0x18000fe39  call    ?GetUserSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSmsRpcUtils::GetUserSid(std::wstring &)
0x18000fe3e  lea     r14, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18000fe45  mov     [rbp+120h+var_F8], r14
0x18000fe49  lea     rcx, [r13+10h]
0x18000fe4d  mov     [rbp+120h+var_F0], rcx
0x18000fe51  mov     rax, [rcx]
0x18000fe54  mov     rax, [rax]
0x18000fe57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe5c  nop
0x18000fe5d  xorps   xmm0, xmm0
0x18000fe60  movdqu  xmmword ptr [rbp+120h+var_150], xmm0
0x18000fe65  mov     [rbp+120h+var_140], rsi
0x18000fe69  lea     rcx, [rbp+120h+var_150]
0x18000fe6d  call    ?GetRegistrationIdList@CRegistration@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CRegistration::GetRegistrationIdList(std::vector<std::wstring> &)
0x18000fe72  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8CSmsInterceptor@@EAAXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@2@@ZPEAV3@AEBU?$_Ph@$00@2@@std@@XAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CSmsInterceptor::*)(std::shared_ptr<std::vector<uchar>> &),CSmsInterceptor *,std::_Ph<1> const &>,void,std::shared_ptr<std::vector<uchar>> &>::`vftable'
0x18000fe79  mov     [rbp+120h+var_90], rax
0x18000fe80  lea     rax, ?AcknowledgeMessageCallback@CSmsInterceptor@@QEAAXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Z; CSmsInterceptor::AcknowledgeMessageCallback(std::shared_ptr<std::vector<uchar>> &)
0x18000fe87  mov     [rbp+120h+var_88], rax
0x18000fe8e  mov     al, [rsp+220h+var_1CC]
0x18000fe92  mov     [rbp+120h+var_80], al
0x18000fe98  mov     [rbp+120h+var_78], r13
0x18000fe9f  lea     rax, [rbp+120h+var_90]
0x18000fea6  mov     [rbp+120h+var_58], rax
0x18000fead  mov     rdi, [rbp+120h+var_150]
0x18000feb1  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000feb5  mov     rbx, [rbp+120h+var_150+8]
0x18000feb9  cmp     rdi, rbx
0x18000febc  jz      loc_1800102D4
0x18000fec2  mov     rdx, rdi
0x18000fec5  lea     rcx, [rbp+120h+var_D8]
0x18000fec9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000fece  nop
0x18000fecf  lea     rbx, [rbp+120h+var_D8]
0x18000fed3  cmp     [rbp+120h+var_C0], 7
0x18000fed8  cmova   rbx, [rbp+120h+var_D8]
0x18000fedd  mov     ecx, 1C8h; Size
0x18000fee2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fee7  mov     rsi, rax
0x18000feea  mov     [rbp+120h+var_158], rax
0x18000feee  xorps   xmm0, xmm0
0x18000fef1  movups  xmmword ptr [rax], xmm0
0x18000fef4  mov     dword ptr [rax+8], 1
0x18000fefb  mov     dword ptr [rax+0Ch], 1
0x18000ff02  lea     rax, ??_7?$_Ref_count_obj2@VCRegistration@@@std@@6B@; const std::_Ref_count_obj2<CRegistration>::`vftable'
0x18000ff09  mov     [rsi], rax
0x18000ff0c  lea     r14, [rsi+10h]
0x18000ff10  lea     rax, [rbp+120h+var_90]
0x18000ff17  mov     [rsp+220h+var_200], rax; __int64
0x18000ff1c  lea     r9, [r13+248h]
0x18000ff23  mov     r8, r15
0x18000ff26  mov     rdx, rbx
0x18000ff29  mov     rcx, r14; void *
0x18000ff2c  call    ??0CRegistration@@QEAA@PEBGAEAVCSmsMessageStore@@AEAVCExecutionManager@@AEBV?$function@$$A6AXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Z@std@@@Z; CRegistration::CRegistration(ushort const *,CSmsMessageStore &,CExecutionManager &,std::function<void (std::shared_ptr<std::vector<uchar>> &)> const &)
0x18000ff31  nop
0x18000ff32  mov     [rbp+120h+var_188], r14
0x18000ff36  mov     [rbp+120h+var_180], rsi
0x18000ff3a  mov     rcx, r14; this
0x18000ff3d  call    ?Load@CRegistration@@QEAAJXZ; CRegistration::Load(void)
0x18000ff42  mov     r12d, eax
0x18000ff45  mov     [rsp+220h+var_1C8], eax
0x18000ff49  test    eax, eax
0x18000ff4b  jns     loc_18000FFDD
0x18000ff51  add     r14, 30h ; '0'
0x18000ff55  cmp     qword ptr [r14+18h], 7
0x18000ff5a  jbe     short loc_18000FF5F
0x18000ff5c  mov     r14, [r14]
0x18000ff5f  lea     rax, [rbp+120h+var_D8]
0x18000ff63  cmp     [rbp+120h+var_C0], 7
0x18000ff68  cmova   rax, [rbp+120h+var_D8]
0x18000ff6d  mov     [rsp+220h+var_1F8], r14
0x18000ff72  mov     [rsp+220h+var_200], rax
0x18000ff77  lea     r9, aFailedToLoadRe; "Failed to load registration RegId: %S, "...
0x18000ff7e  mov     r8d, r12d; int
0x18000ff81  mov     edx, 56h ; 'V'; unsigned int
0x18000ff86  lea     rcx, aCsmsintercepto; "CSmsInterceptor::Initialize"
0x18000ff8d  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000ff92  mov     [rsp+220h+var_1C8], 0
0x18000ff9a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ff9e  mov     eax, r12d
0x18000ffa1  lock xadd [rsi+8], eax
0x18000ffa6  add     eax, r12d
0x18000ffa9  jnz     short loc_18000FFD6
0x18000ffab  mov     rax, [rsi]
0x18000ffae  mov     rcx, rsi
0x18000ffb1  mov     rax, [rax]
0x18000ffb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb9  mov     eax, r12d
0x18000ffbc  lock xadd [rsi+0Ch], eax
0x18000ffc1  add     eax, r12d
0x18000ffc4  jnz     short loc_18000FFD6
0x18000ffc6  mov     rax, [rsi]
0x18000ffc9  mov     rcx, rsi
0x18000ffcc  mov     rax, [rax+8]
0x18000ffd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd5  nop
0x18000ffd6  xor     esi, esi
0x18000ffd8  jmp     loc_1800102C2
0x18000ffdd  lea     rax, [r14+90h]
0x18000ffe4  cmp     qword ptr [rax+18h], 7
0x18000ffe9  jbe     short loc_18000FFEE
0x18000ffeb  mov     rax, [rax]
0x18000ffee  mov     r10d, [r14+20h]
0x18000fff2  lea     r15, [r14+70h]
0x18000fff6  cmp     qword ptr [r15+18h], 7
0x18000fffb  jbe     short loc_180010002
0x18000fffd  mov     r8, [r15]
0x180010000  jmp     short loc_180010005
0x180010002  mov     r8, r15
0x180010005  lea     rbx, [r14+50h]
0x180010009  cmp     qword ptr [rbx+18h], 7
0x18001000e  jbe     short loc_180010015
0x180010010  mov     rdx, [rbx]
0x180010013  jmp     short loc_180010018
0x180010015  mov     rdx, rbx
0x180010018  lea     rsi, [r14+30h]
0x18001001c  cmp     qword ptr [rsi+18h], 7
0x180010021  jbe     short loc_180010028
0x180010023  mov     rcx, [rsi]
0x180010026  jmp     short loc_18001002B
0x180010028  mov     rcx, rsi
0x18001002b  lea     r9, [rbp+120h+var_D8]
0x18001002f  cmp     [rbp+120h+var_C0], 7
0x180010034  cmova   r9, [rbp+120h+var_D8]
0x180010039  mov     [rsp+220h+var_1E0], rax
0x18001003e  mov     [rsp+220h+var_1E8], r10d
0x180010043  mov     qword ptr [rsp+220h+var_1F0], r8
0x180010048  mov     [rsp+220h+var_1F8], rdx
0x18001004d  mov     [rsp+220h+var_200], rcx
0x180010052  lea     r8, aLoadedRegistra; "Loaded registration RegId: %S, RegName:"...
0x180010059  mov     edx, 62h ; 'b'; unsigned int
0x18001005e  lea     r12, aCsmsintercepto; "CSmsInterceptor::Initialize"
0x180010065  mov     rcx, r12; char *
0x180010068  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001006d  cmp     dword ptr [r14+20h], 0
0x180010072  jz      short loc_18001007D
0x180010074  lea     rdx, [rbp+120h+var_108]
0x180010078  jmp     loc_1800101E6
0x18001007d  cmp     dword ptr [r14+24h], 0
0x180010082  jz      loc_18001010B
0x180010088  cmp     qword ptr [r15+18h], 7
0x18001008d  jbe     short loc_180010092
0x18001008f  mov     r15, [r15]
0x180010092  cmp     qword ptr [rbx+18h], 7
0x180010097  jbe     short loc_18001009E
0x180010099  mov     rcx, [rbx]
0x18001009c  jmp     short loc_1800100A1
0x18001009e  mov     rcx, rbx; packageFullName
0x1800100a1  mov     r8d, 1; int
0x1800100a7  mov     rdx, r15; StringSid
0x1800100aa  call    ?IsAppInstalled@CSmsRpcUtils@@SAHPEBG0H@Z; CSmsRpcUtils::IsAppInstalled(ushort const *,ushort const *,int)
0x1800100af  test    eax, eax
0x1800100b1  jnz     loc_1800101F3
0x1800100b7  cmp     qword ptr [rbx+18h], 7
0x1800100bc  jbe     short loc_1800100C1
0x1800100be  mov     rbx, [rbx]
0x1800100c1  cmp     qword ptr [rsi+18h], 7
0x1800100c6  jbe     short loc_1800100CB
0x1800100c8  mov     rsi, [rsi]
0x1800100cb  lea     rax, [rbp+120h+var_D8]
0x1800100cf  cmp     [rbp+120h+var_C0], 7
0x1800100d4  cmova   rax, [rbp+120h+var_D8]
0x1800100d9  mov     qword ptr [rsp+220h+var_1F0], rbx
0x1800100de  mov     [rsp+220h+var_1F8], rsi
0x1800100e3  mov     [rsp+220h+var_200], rax
0x1800100e8  lea     r9, aCleaningUpStal_1; "Cleaning up stale registration RegId: %"...
0x1800100ef  mov     edx, 77h ; 'w'; unsigned int
0x1800100f4  mov     r8d, 80070490h; int
0x1800100fa  mov     rcx, r12; char *
0x1800100fd  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180010102  lea     rdx, [rbp+120h+Block]
0x180010106  jmp     loc_1800101E6
0x18001010b  cmp     qword ptr [r15+18h], 7
0x180010110  jbe     short loc_180010117
0x180010112  mov     rcx, [r15]
0x180010115  jmp     short loc_18001011A
0x180010117  mov     rcx, r15; unsigned __int16 *
0x18001011a  call    ?IsValidUserSid@CSmsRpcUtils@@SAHPEBG@Z; CSmsRpcUtils::IsValidUserSid(ushort const *)
0x18001011f  test    eax, eax
0x180010121  jnz     short loc_180010183
0x180010123  cmp     qword ptr [r15+18h], 7
0x180010128  jbe     short loc_18001012D
0x18001012a  mov     r15, [r15]
0x18001012d  cmp     qword ptr [rbx+18h], 7
0x180010132  jbe     short loc_180010137
0x180010134  mov     rbx, [rbx]
0x180010137  cmp     qword ptr [rsi+18h], 7
0x18001013c  jbe     short loc_180010141
0x18001013e  mov     rsi, [rsi]
0x180010141  lea     rax, [rbp+120h+var_D8]
0x180010145  cmp     [rbp+120h+var_C0], 7
0x18001014a  cmova   rax, [rbp+120h+var_D8]
0x18001014f  mov     qword ptr [rsp+220h+var_1E8], r15
0x180010154  mov     qword ptr [rsp+220h+var_1F0], rbx
0x180010159  mov     [rsp+220h+var_1F8], rsi
0x18001015e  mov     [rsp+220h+var_200], rax
0x180010163  lea     r9, aCleaningUpStal_0; "Cleaning up stale registration RegId: %"...
0x18001016a  mov     edx, 84h; unsigned int
0x18001016f  mov     r8d, 80070539h; int
0x180010175  mov     rcx, r12; char *
0x180010178  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001017d  lea     rdx, [rbp+120h+var_128]
0x180010181  jmp     short loc_1800101E6
0x180010183  call    ?GetMaxNotifyCount@CRegistration@@SAKXZ; CRegistration::GetMaxNotifyCount(void)
0x180010188  mov     ecx, [r14+110h]
0x18001018f  cmp     ecx, eax
0x180010191  jbe     short loc_1800101F3
0x180010193  cmp     qword ptr [rbx+18h], 7
0x180010198  jbe     short loc_18001019D
0x18001019a  mov     rbx, [rbx]
0x18001019d  cmp     qword ptr [rsi+18h], 7
0x1800101a2  jbe     short loc_1800101A7
0x1800101a4  mov     rsi, [rsi]
0x1800101a7  lea     rax, [rbp+120h+var_D8]
0x1800101ab  cmp     [rbp+120h+var_C0], 7
0x1800101b0  cmova   rax, [rbp+120h+var_D8]
0x1800101b5  mov     [rsp+220h+var_1E8], ecx
0x1800101b9  mov     qword ptr [rsp+220h+var_1F0], rbx
0x1800101be  mov     [rsp+220h+var_1F8], rsi
0x1800101c3  mov     [rsp+220h+var_200], rax
0x1800101c8  lea     r9, aCleaningUpStal; "Cleaning up stale registration RegId: %"...
0x1800101cf  mov     edx, 91h; unsigned int
0x1800101d4  mov     r8d, 8007139Fh; int
0x1800101da  mov     rcx, r12; char *
0x1800101dd  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800101e2  lea     rdx, [rbp+120h+var_138]
0x1800101e6  mov     r8, r14
0x1800101e9  lea     rcx, [rsp+220h+var_1C0]
0x1800101ee  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x1800101f3  lea     rcx, [r13+1E8h]
0x1800101fa  mov     rdx, r14
0x1800101fd  call    ??A?$hash_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCRegistration@@@2@@std@@@2@@stdext@@QEAAAEAV?$shared_ptr@VCRegistration@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; stdext::hash_map<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>>::operator[](std::wstring const &)
0x180010202  mov     rcx, rax
0x180010205  lea     rdx, [rbp+120h+var_188]
0x180010209  call    ??4?$shared_ptr@USmsStoreMessage@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<SmsStoreMessage>::operator=(std::shared_ptr<SmsStoreMessage> const &)
0x18001020e  lea     rcx, [r13+228h]
0x180010215  lea     r8, [rbp+120h+var_188]
0x180010219  lea     rdx, [rbp+120h+var_178]
0x18001021d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$shared_ptr@VCRegistration@@@std@@VCRegistrationPrioirtyCompare@@V?$allocator@V?$shared_ptr@VCRegistration@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$shared_ptr@VCRegistration@@@std@@@std@@@std@@@std@@_N@1@AEBV?$shared_ptr@VCRegistration@@@1@@Z; std::_Tree<std::_Tset_traits<std::shared_ptr<CRegistration>,CRegistrationPrioirtyCompare,std::allocator<std::shared_ptr<CRegistration>>,0>>::insert<0,0>(std::shared_ptr<CRegistration> const &)
0x180010222  mov     rbx, [rbp+120h+var_188]
0x180010226  lea     r9, [rbx+70h]
0x18001022a  cmp     qword ptr [r9+18h], 7
0x18001022f  jbe     short loc_180010234
0x180010231  mov     r9, [r9]
0x180010234  lea     r8, [rbx+50h]
0x180010238  cmp     qword ptr [r8+18h], 7
0x18001023d  jbe     short loc_180010242
0x18001023f  mov     r8, [r8]
0x180010242  lea     rdx, [rbp+120h+var_B8]
0x180010246  call    ?GetGroupId@CSmsInterceptor@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CSmsInterceptor::GetGroupId(ushort const *,ushort const *)
0x18001024b  nop
0x18001024c  lea     rcx, [r13+238h]
0x180010253  lea     rdx, [rbp+120h+var_B8]
0x180010257  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::set<std::wstring>>::operator[](std::wstring const &)
0x18001025c  mov     r8, rbx
0x18001025f  lea     rdx, [rsp+220h+var_1A8]
0x180010264  mov     rcx, rax
0x180010267  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x18001026c  nop
0x18001026d  lea     rcx, [rbp+120h+var_B8]; void *
  ... truncated ...
```
