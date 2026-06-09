# CSmsInterceptor::RegisterForMessages(ushort const *,ushort const *,ushort const *,ushort const *,_WNF_STATE_NAME *,int,int)

- ea: `0x180010a28`
- end: `0x1800112df`
- name: `?RegisterForMessages@CSmsInterceptor@@QEAAJPEBG000PEAU_WNF_STATE_NAME@@HH@Z`
- size: `2231`
- prototype: `__int64 __fastcall(CSmsInterceptor *this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _WNF_STATE_NAME *, int, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fd94`
- `0x180016c90`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x1800069f0`
- `0x18000d84c`
- `0x18000db54`
- `0x18000dc24`
- `0x18000e05c`
- `0x18000e534`
- `0x18000eaa4`
- `0x18000ece0`
- `0x18000ee74`
- `0x18000f580`
- `0x18000f8b4`
- `0x180010a28`
- `0x1800112e8`
- `0x1800332b4`
- `0x180033d7c`
- `0x180034f0c`
- `0x1800352b8`
- `0x18003547c`
- `0x18003620c`
- `0x180036650`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010ba6`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010dc1`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010e97`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010f6c`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001102d`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180011278`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010ba6`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010dc1`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010e97`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180010f6c`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001102d`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180011278`

## string_xrefs

- `0x1800111fd`: `RegisterForMessages succeeded RegId: %S, RegName: %S, AppName: %S, UserSid: %S, FilterXML: %S`
- `0x180011209`: `CSmsInterceptor::RegisterForMessages`

## pseudocode

```c
__int64 __fastcall CSmsInterceptor::RegisterForMessages(
        CSmsInterceptor *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct _WNF_STATE_NAME *a6,
        int a7,
        int a8)
{
  _QWORD *v12; // rax
  int v13; // r12d
  int RegistrationId; // eax
  unsigned __int16 **v15; // rdx
  int v16; // edi
  void *v17; // rcx
  _QWORD *v18; // rbx
  void *v19; // rcx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v22; // rdi
  CRegistration *v23; // rsi
  volatile signed __int32 *v24; // rbx
  __int64 *v25; // rdx
  void *v26; // rcx
  _QWORD *v27; // rbx
  void *v28; // rcx
  volatile signed __int32 *v29; // rbx
  void *v30; // rcx
  _QWORD *v31; // rbx
  void *v32; // rcx
  volatile signed __int32 *v33; // rbx
  int v34; // r15d
  void *v35; // rcx
  _QWORD *v36; // rbx
  void *v37; // rcx
  int v38; // esi
  void *v39; // rcx
  _QWORD *v40; // rbx
  void *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rcx
  __int64 v45; // rax
  _QWORD *v46; // rbx
  const unsigned __int16 *v47; // r8
  __int64 **v48; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  const wchar_t *v51; // r9
  void *v52; // rcx
  _QWORD *v53; // rbx
  void *v54; // rcx
  void *Block[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v56; // [rsp+50h] [rbp-B0h]
  __int128 v57; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v58; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v59; // [rsp+70h] [rbp-90h]
  void **v60; // [rsp+78h] [rbp-88h]
  char *v61; // [rsp+80h] [rbp-80h]
  const wchar_t *v62; // [rsp+88h] [rbp-78h]
  _BYTE v63[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v64[152]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v65[104]; // [rsp+138h] [rbp+38h] BYREF
  unsigned __int16 *v66[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v67; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v68; // [rsp+1B8h] [rbp+B8h]
  __int64 v69[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v70; // [rsp+1D0h] [rbp+D0h]
  CSmsInterceptor *v71; // [rsp+1D8h] [rbp+D8h]
  __int64 *v72; // [rsp+1F8h] [rbp+F8h]
  _BYTE v73[32]; // [rsp+200h] [rbp+100h] BYREF

  v62 = a4;
  v59 = a2;
  v58 = a5;
  v57 = 0;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v64);
  Block[1] = 0;
  v12 = operator new(0x28u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  v13 = 1;
  *((_WORD *)v12 + 12) = 257;
  Block[0] = v12;
  *(_OWORD *)v66 = 0;
  v67 = 0;
  v68 = 7;
  LOWORD(v66[0]) = 0;
  RegistrationId = CRegistration::GetRegistrationId(a2, a3, a4, v66);
  if ( RegistrationId >= 0 )
  {
    v15 = v66;
    if ( v68 > 7 )
      v15 = (unsigned __int16 **)v66[0];
    RegistrationId = CSmsInterceptor::GetRegistration(this, v15, &v57);
  }
  if ( RegistrationId == -2147023728 )
  {
    v16 = CRegistration::CreateRegistrationId(a2, a3, a4, v66);
    if ( v16 < 0 )
    {
      std::wstring::~wstring(v66);
      v17 = Block[0];
      v18 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      if ( !*((_BYTE *)v18 + 25) )
      {
        do
        {
          std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(
            Block,
            Block,
            v18[2]);
          v19 = v18;
          v18 = (_QWORD *)*v18;
          operator delete(v19);
        }
        while ( !*((_BYTE *)v18 + 25) );
        v17 = Block[0];
      }
      operator delete(v17);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v65);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v65);
      v20 = (volatile signed __int32 *)*((_QWORD *)&v57 + 1);
      if ( *((_QWORD *)&v57 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v57 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
      return (unsigned int)v16;
    }
    v69[0] = (__int64)&std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CSmsInterceptor::*)(std::shared_ptr<std::vector<unsigned char>> &),CSmsInterceptor *,std::_Ph<1> const &>,void,std::shared_ptr<std::vector<unsigned char>> &>::`vftable';
    v69[1] = (__int64)CSmsInterceptor::AcknowledgeMessageCallback;
    v70 = v56;
    v71 = this;
    v72 = v69;
    v22 = (volatile signed __int32 *)operator new(0x1C8u);
    v60 = (void **)v22;
    *(_OWORD *)v22 = 0;
    *((_DWORD *)v22 + 2) = 1;
    *((_DWORD *)v22 + 3) = 1;
    *(_QWORD *)v22 = &std::_Ref_count_obj2<CRegistration>::`vftable';
    v23 = (CRegistration *)(v22 + 4);
    CRegistration::CRegistration((void *)(v22 + 4), (__int64)v69);
    *(_QWORD *)&v57 = v22 + 4;
    v24 = (volatile signed __int32 *)*((_QWORD *)&v57 + 1);
    *((_QWORD *)&v57 + 1) = v22;
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    CRegistration::Initialize(v23, v59, a3, a4, a6, a7 == 0, a8);
    if ( v72 )
    {
      v25 = v69;
      LOBYTE(v25) = v72 != v69;
      (*(void (__fastcall **)(__int64 *, __int64 *))(*v72 + 32))(v72, v25);
    }
    goto LABEL_41;
  }
  v23 = (CRegistration *)v57;
  if ( (unsigned int)CRegistration::HasAccess(v57, a3, a4, (char *)this + 72) )
  {
    v13 = 0;
    if ( !a6 || *a6 == *((_QWORD *)v23 + 26) )
    {
      v22 = (volatile signed __int32 *)*((_QWORD *)&v57 + 1);
LABEL_41:
      v34 = CRegistration::SetFilterRules(v23, v58, Block);
      if ( v34 >= 0 )
      {
        v38 = CRegistration::Save((LPCWSTR)v23);
        if ( v38 >= 0 )
        {
          if ( v13 )
          {
            v60 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
            v61 = (char *)this + 16;
            (**((void (__fastcall ***)(char *))this + 2))((char *)this + 16);
            v42 = stdext::hash_map<std::wstring,std::shared_ptr<CRegistration>,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CRegistration>>>>::operator[](
                    (char *)this + 488,
                    v66);
            std::shared_ptr<SmsStoreMessage>::operator=(v42, &v57);
            std::_Tree<std::_Tset_traits<std::shared_ptr<CRegistration>,CRegistrationPrioirtyCompare,std::allocator<std::shared_ptr<CRegistration>>,0>>::insert<0,0>(
              (char *)this + 552,
              v63,
              &v57);
            v43 = v57;
            CSmsInterceptor::GetGroupId(v44, v73);
            v45 = std::map<std::wstring,std::set<std::wstring>>::operator[]((char *)this + 568, v73);
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
              v45,
              v63,
              v43);
            std::wstring::~wstring(v73);
            (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16);
            v22 = (volatile signed __int32 *)*((_QWORD *)&v57 + 1);
          }
          v46 = *(_QWORD **)Block[0];
          while ( v46 != Block[0] )
          {
            v47 = (const unsigned __int16 *)v66;
            if ( v68 > 7 )
              v47 = v66[0];
            CSmsInterceptor::ScheduleNextRegistration(this, v46[4], v47, 0);
            v48 = (__int64 **)v46[2];
            if ( *((_BYTE *)v48 + 25) )
            {
              for ( i = v46[1]; !*(_BYTE *)(i + 25) && v46 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
                v46 = (_QWORD *)i;
              v46 = (_QWORD *)i;
            }
            else
            {
              v46 = (_QWORD *)v46[2];
              for ( j = *v48; !*((_BYTE *)j + 25); j = (__int64 *)*j )
                v46 = j;
            }
          }
          v51 = (const wchar_t *)v66;
          if ( v68 > 7 )
            v51 = v66[0];
          LogSmsRouterInfo(
            "CSmsInterceptor::RegisterForMessages",
            0x166u,
            "RegisterForMessages succeeded RegId: %S, RegName: %S, AppName: %S, UserSid: %S, FilterXML: %S",
            v51,
            v59,
            a3,
            v62,
            v58);
          std::wstring::~wstring(v66);
          v52 = Block[0];
          v53 = (_QWORD *)*((_QWORD *)Block[0] + 1);
          if ( !*((_BYTE *)v53 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(
                Block,
                Block,
                v53[2]);
              v54 = v53;
              v53 = (_QWORD *)*v53;
              operator delete(v54);
            }
            while ( !*((_BYTE *)v53 + 25) );
            v52 = Block[0];
          }
          operator delete(v52);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v65);
          std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v65);
          if ( v22 )
          {
            if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          return 0;
        }
        else
        {
          std::wstring::~wstring(v66);
          v39 = Block[0];
          v40 = (_QWORD *)*((_QWORD *)Block[0] + 1);
          if ( !*((_BYTE *)v40 + 25) )
          {
            do
            {
              std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(
                Block,
                Block,
                v40[2]);
              v41 = v40;
              v40 = (_QWORD *)*v40;
              operator delete(v41);
            }
            while ( !*((_BYTE *)v40 + 25) );
            v39 = Block[0];
          }
          operator delete(v39);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v65);
          std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v65);
          if ( v22 )
          {
            if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          return (unsigned int)v38;
        }
      }
      else
      {
        std::wstring::~wstring(v66);
        v35 = Block[0];
        v36 = (_QWORD *)*((_QWORD *)Block[0] + 1);
        if ( !*((_BYTE *)v36 + 25) )
        {
          do
          {
            std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(
              Block,
              Block,
              v36[2]);
            v37 = v36;
            v36 = (_QWORD *)*v36;
            operator delete(v37);
          }
          while ( !*((_BYTE *)v36 + 25) );
          v35 = Block[0];
        }
        operator delete(v35);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v65);
        std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v65);
        if ( v22 )
        {
          if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
            if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          }
        }
        return (unsigned int)v34;
      }
    }
    std::wstring::~wstring(v66);
    v30 = Block[0];
    v31 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    if ( !*((_BYTE *)v31 + 25) )
    {
      do
      {
        std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(
          Block,
          Block,
          v31[2]);
        v32 = v31;
        v31 = (_QWORD *)*v31;
        operator delete(v32);
      }
      while ( !*((_BYTE *)v31 + 25) );
      v30 = Block[0];
    }
    operator delete(v30);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v65);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v65);
    v33 = (volatile signed __int32 *)*((_QWORD *)&v57 + 1);
    if ( *((_QWORD *)&v57 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v57 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    return 2147942450LL;
  }
  else
  {
    std::wstring::~wstring(v66);
    v26 = Block[0];
    v27 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    if ( !*((_BYTE *)v27 + 25) )
    {
      do
      {
        std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(
          Block,
          Block,
          v27[2]);
        v28 = v27;
        v27 = (_QWORD *)*v27;
        operator delete(v28);
      }
      while ( !*((_BYTE *)v27 + 25) );
      v26 = Block[0];
    }
    operator delete(v26);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v65);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v65);
    v29 = (volatile signed __int32 *)*((_QWORD *)&v57 + 1);
    if ( *((_QWORD *)&v57 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v57 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x180010a28  push    rbp
0x180010a2a  push    rbx
0x180010a2b  push    rsi
0x180010a2c  push    rdi
0x180010a2d  push    r12
0x180010a2f  push    r13
0x180010a31  push    r14
0x180010a33  push    r15
0x180010a35  lea     rbp, [rsp-138h]
0x180010a3d  sub     rsp, 238h
0x180010a44  mov     rax, cs:__security_cookie
0x180010a4b  xor     rax, rsp
0x180010a4e  mov     [rbp+170h+var_50], rax
0x180010a55  mov     r15, r9
0x180010a58  mov     [rbp+170h+var_1E8], r9
0x180010a5c  mov     r13, r8
0x180010a5f  mov     rbx, rdx
0x180010a62  mov     [rsp+270h+var_200], rdx
0x180010a67  mov     r14, rcx
0x180010a6a  mov     rax, [rbp+170h+arg_20]
0x180010a71  mov     [rsp+270h+var_208], rax
0x180010a76  xor     edi, edi
0x180010a78  xorps   xmm0, xmm0
0x180010a7b  movdqu  [rsp+270h+var_218], xmm0
0x180010a81  lea     rcx, [rbp+170h+var_1D0]
0x180010a85  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180010a8a  nop
0x180010a8b  mov     [rsp+270h+Block], rdi
0x180010a90  mov     [rsp+270h+var_228], rdi
0x180010a95  lea     ecx, [rdi+28h]; Size
0x180010a98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010a9d  mov     [rax], rax
0x180010aa0  mov     [rax+8], rax
0x180010aa4  mov     [rax+10h], rax
0x180010aa8  lea     r12d, [rdi+1]
0x180010aac  mov     word ptr [rax+18h], 101h
0x180010ab2  mov     [rsp+270h+Block], rax
0x180010ab7  xorps   xmm0, xmm0
0x180010aba  movups  xmmword ptr [rbp+170h+var_D0], xmm0
0x180010ac1  mov     [rbp+170h+var_C0], rdi
0x180010ac8  mov     [rbp+170h+var_B8], 7
0x180010ad3  mov     word ptr [rbp+170h+var_D0], di
0x180010ada  lea     r9, [rbp+170h+var_D0]
0x180010ae1  mov     r8, r15
0x180010ae4  mov     rdx, r13
0x180010ae7  mov     rcx, rbx
0x180010aea  call    ?GetRegistrationId@CRegistration@@SAJPEBG00AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRegistration::GetRegistrationId(ushort const *,ushort const *,ushort const *,std::wstring &)
0x180010aef  test    eax, eax
0x180010af1  js      short loc_180010B17
0x180010af3  lea     rdx, [rbp+170h+var_D0]
0x180010afa  cmp     [rbp+170h+var_B8], 7
0x180010b02  cmova   rdx, [rbp+170h+var_D0]
0x180010b0a  lea     r8, [rsp+270h+var_218]
0x180010b0f  mov     rcx, r14
0x180010b12  call    ?GetRegistration@CSmsInterceptor@@AEAAJPEBGAEAV?$shared_ptr@VCRegistration@@@std@@@Z; CSmsInterceptor::GetRegistration(ushort const *,std::shared_ptr<CRegistration> &)
0x180010b17  or      esi, 0FFFFFFFFh
0x180010b1a  mov     r8, r15
0x180010b1d  mov     rdx, r13
0x180010b20  cmp     eax, 80070490h
0x180010b25  jnz     loc_180010D46
0x180010b2b  lea     r9, [rbp+170h+var_D0]
0x180010b32  mov     rcx, rbx
0x180010b35  call    ?CreateRegistrationId@CRegistration@@SAJPEBG00AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRegistration::CreateRegistrationId(ushort const *,ushort const *,ushort const *,std::wstring &)
0x180010b3a  mov     edi, eax
0x180010b3c  test    eax, eax
0x180010b3e  jns     loc_180010BF1
0x180010b44  lea     rcx, [rbp+170h+var_D0]; void *
0x180010b4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010b50  nop
0x180010b51  mov     rcx, [rsp+270h+Block]
0x180010b56  mov     rbx, [rcx+8]
0x180010b5a  cmp     byte ptr [rbx+19h], 0
0x180010b5e  jnz     short loc_180010B8E
0x180010b60  mov     r8, [rbx+10h]
0x180010b64  lea     rdx, [rsp+270h+Block]
0x180010b69  lea     rcx, [rsp+270h+Block]
0x180010b6e  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAUSmsServiceCallContext@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@1@PEAU?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>> &,std::_Tree_node<SmsServiceCallContext *,void *> *)
0x180010b73  mov     rcx, rbx; Block
0x180010b76  mov     rbx, [rbx]
0x180010b79  mov     edx, 28h ; '('
0x180010b7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010b83  cmp     byte ptr [rbx+19h], 0
0x180010b87  jz      short loc_180010B60
0x180010b89  mov     rcx, [rsp+270h+Block]; Block
0x180010b8e  mov     edx, 28h ; '('
0x180010b93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010b98  nop
0x180010b99  lea     rcx, [rbp+170h+var_138]
0x180010b9d  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180010ba2  lea     rcx, [rbp+170h+var_138]
0x180010ba6  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180010bac  nop
0x180010bad  mov     rbx, qword ptr [rsp+270h+var_218+8]
0x180010bb2  test    rbx, rbx
0x180010bb5  jz      short loc_180010BEA
0x180010bb7  mov     eax, esi
0x180010bb9  lock xadd [rbx+8], eax
0x180010bbe  add     eax, esi
0x180010bc0  jnz     short loc_180010BEA
0x180010bc2  mov     rax, [rbx]
0x180010bc5  mov     rcx, rbx
0x180010bc8  mov     rax, [rax]
0x180010bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bd0  mov     eax, esi
0x180010bd2  lock xadd [rbx+0Ch], eax
0x180010bd7  add     eax, esi
0x180010bd9  jnz     short loc_180010BEA
0x180010bdb  mov     rax, [rbx]
0x180010bde  mov     rcx, rbx
0x180010be1  mov     rax, [rax+8]
0x180010be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bea  mov     eax, edi
0x180010bec  jmp     loc_1800112BC
0x180010bf1  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8CSmsInterceptor@@EAAXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@2@@ZPEAV3@AEBU?$_Ph@$00@2@@std@@XAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (CSmsInterceptor::*)(std::shared_ptr<std::vector<uchar>> &),CSmsInterceptor *,std::_Ph<1> const &>,void,std::shared_ptr<std::vector<uchar>> &>::`vftable'
0x180010bf8  mov     [rbp+170h+var_B0], rax
0x180010bff  lea     rax, ?AcknowledgeMessageCallback@CSmsInterceptor@@QEAAXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Z; CSmsInterceptor::AcknowledgeMessageCallback(std::shared_ptr<std::vector<uchar>> &)
0x180010c06  mov     [rbp+170h+var_A8], rax
0x180010c0d  mov     al, [rsp+270h+var_220]
0x180010c11  mov     [rbp+170h+var_A0], al
0x180010c17  mov     [rbp+170h+var_98], r14
0x180010c1e  lea     rax, [rbp+170h+var_B0]
0x180010c25  mov     [rbp+170h+var_78], rax
0x180010c2c  lea     rbx, [rbp+170h+var_D0]
0x180010c33  cmp     [rbp+170h+var_B8], 7
0x180010c3b  cmova   rbx, [rbp+170h+var_D0]
0x180010c43  mov     ecx, 1C8h; Size
0x180010c48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010c4d  mov     rdi, rax
0x180010c50  mov     [rsp+270h+var_1F8], rax
0x180010c55  lea     r9, [r14+248h]
0x180010c5c  lea     r8, [r14+68h]
0x180010c60  xorps   xmm0, xmm0
0x180010c63  movups  xmmword ptr [rax], xmm0
0x180010c66  mov     [rax+8], r12d
0x180010c6a  mov     [rax+0Ch], r12d
0x180010c6e  lea     rax, ??_7?$_Ref_count_obj2@VCRegistration@@@std@@6B@; const std::_Ref_count_obj2<CRegistration>::`vftable'
0x180010c75  mov     [rdi], rax
0x180010c78  lea     rsi, [rdi+10h]
0x180010c7c  lea     rax, [rbp+170h+var_B0]
0x180010c83  mov     [rsp+270h+var_250], rax; __int64
0x180010c88  mov     rdx, rbx
0x180010c8b  mov     rcx, rsi; void *
0x180010c8e  call    ??0CRegistration@@QEAA@PEBGAEAVCSmsMessageStore@@AEAVCExecutionManager@@AEBV?$function@$$A6AXAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Z@std@@@Z; CRegistration::CRegistration(ushort const *,CSmsMessageStore &,CExecutionManager &,std::function<void (std::shared_ptr<std::vector<uchar>> &)> const &)
0x180010c93  nop
0x180010c94  mov     qword ptr [rsp+270h+var_218], rsi
0x180010c99  mov     rbx, qword ptr [rsp+270h+var_218+8]
0x180010c9e  mov     qword ptr [rsp+270h+var_218+8], rdi
0x180010ca3  test    rbx, rbx
0x180010ca6  jz      short loc_180010CDF
0x180010ca8  or      eax, 0FFFFFFFFh
0x180010cab  lock xadd [rbx+8], eax
0x180010cb0  cmp     eax, 1
0x180010cb3  jnz     short loc_180010CDF
0x180010cb5  mov     rax, [rbx]
0x180010cb8  mov     rcx, rbx
0x180010cbb  mov     rax, [rax]
0x180010cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc3  or      eax, 0FFFFFFFFh
0x180010cc6  lock xadd [rbx+0Ch], eax
0x180010ccb  cmp     eax, 1
0x180010cce  jnz     short loc_180010CDF
0x180010cd0  mov     rax, [rbx]
0x180010cd3  mov     rcx, rbx
0x180010cd6  mov     rax, [rax+8]
0x180010cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cdf  xor     ecx, ecx
0x180010ce1  cmp     [rbp+170h+arg_30], ecx
0x180010ce7  setz    cl
0x180010cea  mov     eax, [rbp+170h+arg_38]
0x180010cf0  mov     [rsp+270h+var_240], eax; int
0x180010cf4  mov     [rsp+270h+var_248], ecx; int
0x180010cf8  mov     rax, [rbp+170h+arg_28]
0x180010cff  mov     [rsp+270h+var_250], rax; struct _WNF_STATE_NAME *
0x180010d04  mov     r9, r15; unsigned __int16 *
0x180010d07  mov     r8, r13; unsigned __int16 *
0x180010d0a  mov     rdx, [rsp+270h+var_200]; unsigned __int16 *
0x180010d0f  mov     rcx, rsi; this
0x180010d12  call    ?Initialize@CRegistration@@QEAAJPEBG00PEAU_WNF_STATE_NAME@@HH@Z; CRegistration::Initialize(ushort const *,ushort const *,ushort const *,_WNF_STATE_NAME *,int,int)
0x180010d17  nop
0x180010d18  mov     rcx, [rbp+170h+var_78]
0x180010d1f  test    rcx, rcx
0x180010d22  jz      loc_180010EED
0x180010d28  mov     rax, [rcx]
0x180010d2b  lea     rdx, [rbp+170h+var_B0]
0x180010d32  cmp     rcx, rdx
0x180010d35  setnz   dl
0x180010d38  mov     rax, [rax+20h]
0x180010d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d41  jmp     loc_180010EED
0x180010d46  lea     r9, [r14+48h]
0x180010d4a  mov     rsi, qword ptr [rsp+270h+var_218]
0x180010d4f  mov     rcx, rsi
0x180010d52  call    ?HasAccess@CRegistration@@QEAAHPEBG0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRegistration::HasAccess(ushort const *,ushort const *,std::wstring const &)
0x180010d57  test    eax, eax
0x180010d59  jnz     loc_180010E12
0x180010d5f  lea     rcx, [rbp+170h+var_D0]; void *
0x180010d66  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010d6b  nop
0x180010d6c  mov     rcx, [rsp+270h+Block]
0x180010d71  mov     rbx, [rcx+8]
0x180010d75  cmp     [rbx+19h], dil
0x180010d79  jnz     short loc_180010DA9
0x180010d7b  mov     r8, [rbx+10h]
0x180010d7f  lea     rdx, [rsp+270h+Block]
0x180010d84  lea     rcx, [rsp+270h+Block]
0x180010d89  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAUSmsServiceCallContext@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@1@PEAU?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>> &,std::_Tree_node<SmsServiceCallContext *,void *> *)
0x180010d8e  mov     rcx, rbx; Block
0x180010d91  mov     rbx, [rbx]
0x180010d94  mov     edx, 28h ; '('
0x180010d99  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010d9e  cmp     [rbx+19h], dil
0x180010da2  jz      short loc_180010D7B
0x180010da4  mov     rcx, [rsp+270h+Block]; Block
0x180010da9  mov     edx, 28h ; '('
0x180010dae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010db3  nop
0x180010db4  lea     rcx, [rbp+170h+var_138]
0x180010db8  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180010dbd  lea     rcx, [rbp+170h+var_138]
0x180010dc1  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180010dc7  nop
0x180010dc8  mov     rbx, qword ptr [rsp+270h+var_218+8]
0x180010dcd  test    rbx, rbx
0x180010dd0  jz      short loc_180010E08
0x180010dd2  or      edi, 0FFFFFFFFh
0x180010dd5  mov     eax, edi
0x180010dd7  lock xadd [rbx+8], eax
0x180010ddc  add     eax, edi
0x180010dde  jnz     short loc_180010E08
0x180010de0  mov     rax, [rbx]
0x180010de3  mov     rcx, rbx
0x180010de6  mov     rax, [rax]
0x180010de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dee  mov     eax, edi
0x180010df0  lock xadd [rbx+0Ch], eax
0x180010df5  add     eax, edi
0x180010df7  jnz     short loc_180010E08
0x180010df9  mov     rax, [rbx]
0x180010dfc  mov     rcx, rbx
0x180010dff  mov     rax, [rax+8]
0x180010e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e08  mov     eax, 80070005h
0x180010e0d  jmp     loc_1800112BC
0x180010e12  mov     r12d, edi
0x180010e15  mov     rax, [rbp+170h+arg_28]
0x180010e1c  test    rax, rax
0x180010e1f  jz      loc_180010EE8
0x180010e25  mov     rax, [rax]
0x180010e28  cmp     rax, [rsi+0D0h]
0x180010e2f  jz      loc_180010EE8
0x180010e35  lea     rcx, [rbp+170h+var_D0]; void *
0x180010e3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010e41  nop
0x180010e42  mov     rcx, [rsp+270h+Block]
0x180010e47  mov     rbx, [rcx+8]
0x180010e4b  cmp     [rbx+19h], dil
0x180010e4f  jnz     short loc_180010E7F
0x180010e51  mov     r8, [rbx+10h]
0x180010e55  lea     rdx, [rsp+270h+Block]
0x180010e5a  lea     rcx, [rsp+270h+Block]
0x180010e5f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAUSmsServiceCallContext@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@std@@@1@PEAU?$_Tree_node@PEAUSmsServiceCallContext@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<SmsServiceCallContext *>>::_Erase_tree<std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>>>(std::allocator<std::_Tree_node<SmsServiceCallContext *,void *>> &,std::_Tree_node<SmsServiceCallContext *,void *> *)
0x180010e64  mov     rcx, rbx; Block
0x180010e67  mov     rbx, [rbx]
0x180010e6a  mov     edx, 28h ; '('
0x180010e6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010e74  cmp     [rbx+19h], dil
0x180010e78  jz      short loc_180010E51
0x180010e7a  mov     rcx, [rsp+270h+Block]; Block
0x180010e7f  mov     edx, 28h ; '('
0x180010e84  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010e89  nop
0x180010e8a  lea     rcx, [rbp+170h+var_138]
0x180010e8e  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180010e93  lea     rcx, [rbp+170h+var_138]
0x180010e97  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180010e9d  nop
0x180010e9e  mov     rbx, qword ptr [rsp+270h+var_218+8]
0x180010ea3  test    rbx, rbx
0x180010ea6  jz      short loc_180010EDE
0x180010ea8  or      edi, 0FFFFFFFFh
0x180010eab  mov     eax, edi
0x180010ead  lock xadd [rbx+8], eax
0x180010eb2  add     eax, edi
0x180010eb4  jnz     short loc_180010EDE
0x180010eb6  mov     rax, [rbx]
0x180010eb9  mov     rcx, rbx
0x180010ebc  mov     rax, [rax]
0x180010ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ec4  mov     eax, edi
0x180010ec6  lock xadd [rbx+0Ch], eax
0x180010ecb  add     eax, edi
0x180010ecd  jnz     short loc_180010EDE
0x180010ecf  mov     rax, [rbx]
0x180010ed2  mov     rcx, rbx
0x180010ed5  mov     rax, [rax+8]
0x180010ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ede  mov     eax, 80070032h
0x180010ee3  jmp     loc_1800112BC
0x180010ee8  mov     rdi, qword ptr [rsp+270h+var_218+8]
0x180010eed  lea     r8, [rsp+270h+Block]
  ... truncated ...
```
