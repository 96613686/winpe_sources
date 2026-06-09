# WriteOutServicesBindings

- ea: `0x180038b30`
- end: `0x180038fb6`
- name: `WriteOutServicesBindings`
- size: `1158`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005660`
- `0x180006eb0`
- `0x18000a430`
- `0x18000cf70`
- `0x18000d474`
- `0x18000e4c8`
- `0x18000e970`
- `0x18000ead8`
- `0x18000ec20`
- `0x18000ecc8`
- `0x180010200`
- `0x1800109f0`
- `0x180012108`
- `0x18001368c`
- `0x180013994`
- `0x18001439c`
- `0x180014a98`
- `0x180015f50`
- `0x180017320`
- `0x1800190d0`
- `0x180027ac0`
- `0x180027b38`
- `0x1800285fc`
- `0x180029d20`
- `0x18002a84c`
- `0x180038b30`
- `0x180038fbc`
- `0x1800390c4`
- `0x18003ad28`
- `0x180055d20`
- `0x18005823c`
- `0x180064704`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038bc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038d02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038ef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038f15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038f82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038bc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038d02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038ef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038f15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038f82`

## string_xrefs

- `0x180038ba4`: `Services`
- `0x180038bdf`: `CompatibilityWriteOutServiceBindings`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
LSTATUS __fastcall WriteOutServicesBindings(__int64 a1, void *a2, __int64 *a3)
{
  HKEY CurrentControlSetRegistryHandle; // rax
  HKEY *v6; // rax
  __int64 v7; // rbx
  const WCHAR *v8; // rdi
  const WCHAR *v9; // r14
  const WCHAR *v10; // r8
  __int64 *v11; // rax
  _QWORD *v12; // rsi
  __int64 v13; // rbx
  __int64 BindingPath; // rax
  __int64 i; // rax
  __int64 *v16; // rsi
  __int64 *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 j; // rax
  HKEY v22; // rcx
  __int64 *v23; // rsi
  __int64 *k; // rbx
  const WCHAR *p_Block; // r8
  __int64 v26; // rdx
  wchar_t *m; // rbx
  const wchar_t *v28; // rdx
  LSTATUS result; // eax
  HKEY v30; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v31; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  char v34[24]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v35[4]; // [rsp+80h] [rbp-80h] BYREF
  char v36[16]; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v37; // [rsp+B0h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v39; // [rsp+C0h] [rbp-40h] BYREF
  void *Block; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v41; // [rsp+D0h] [rbp-30h] BYREF
  int v42; // [rsp+D8h] [rbp-28h]
  __int128 v43; // [rsp+DCh] [rbp-24h]
  __int64 *v44[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v45[48]; // [rsp+100h] [rbp+0h] BYREF
  void **v46; // [rsp+130h] [rbp+30h] BYREF
  char v47[272]; // [rsp+138h] [rbp+38h] BYREF
  char v48[8]; // [rsp+248h] [rbp+148h] BYREF
  char v49[48]; // [rsp+250h] [rbp+150h] BYREF

  v35[3] = -2;
  Block = a2;
  v41 = 0;
  v42 = 9;
  v43 = 0;
  CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&Block);
  v6 = (HKEY *)RegistryKey::DuplicateFrom(&hKey, CurrentControlSetRegistryHandle);
  RegistryKey::TryOpenSubKey(v6, (HKEY)&v39, L"Services", 8u, 0);
  if ( hKey )
    RegCloseKey(hKey);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v41);
  if ( !v39 )
    return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
  v7 = *a3;
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v46,
    "CompatibilityWriteOutServiceBindings");
  v46 = &NetSetupTraceLogging::CompatibilityWriteOutServiceBindings::`vftable';
  NetSetupTraceLogging::CompatibilityWriteOutServiceBindings::StartActivity(
    (NetSetupTraceLogging::CompatibilityWriteOutServiceBindings *)&v46,
    (const struct _GUID *)(v7 + 632));
  Block = a2;
  v41 = 0;
  v42 = 9;
  v43 = 0;
  NetSetup2::ActiveObject::GetProperty((void ***)&Block, (GUID *)v32, (__int128 *)&NETSETUPPKEY_NetCfg_DirtyServices, 0);
  NetSetup2::Property::GetStringArray(v32, v35);
  std::vector<_NETSETUPPROPKEY>::_Tidy(v34);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v41);
  v8 = (const WCHAR *)v35[0];
  v9 = (const WCHAR *)v35[1];
  while ( v8 != v9 )
  {
    if ( *((_QWORD *)v8 + 3) < 8u )
      v10 = v8;
    else
      v10 = *(const WCHAR **)v8;
    RegistryKey::TryOpenSubKey(&v39, (HKEY)&v37, v10, 0x2001Du, 0);
    if ( v37 )
    {
      v11 = std::unordered_map<std::wstring,std::set<BindPathDescriptor>>::operator[](
              (__int64 **)(*a3 + 728),
              (__int64)v8);
      v12 = (_QWORD *)*v11;
      v13 = *(_QWORD *)*v11;
      while ( (_QWORD *)v13 != v12 )
      {
        BindingPath = GetBindingPath(&Block, v13 + 28);
        if ( *(_QWORD *)(BindingPath + 24) >= 8u )
          BindingPath = *(_QWORD *)BindingPath;
        RegistryKey::CreateSubKey(&v37, (HKEY)&v31, (const WCHAR *)BindingPath, 2u, 0, 0);
        if ( v31 )
          RegCloseKey(v31);
        if ( *(_QWORD *)((char *)&v43 + 4) >= 8u )
          operator delete(Block);
        if ( !*(_BYTE *)(v13 + 25) )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 25LL) )
          {
            for ( i = *(_QWORD *)(v13 + 8); !*(_BYTE *)(i + 25) && v13 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
              v13 = i;
          }
          else
          {
            i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Min();
          }
          v13 = i;
        }
      }
      v16 = std::unordered_map<std::wstring,std::set<BindPathDescriptor>>::operator[](
              (__int64 **)(*a3 + 792),
              (__int64)v8);
      std::unordered_set<_GUID>::unordered_set<_GUID>(v44);
      v17 = (__int64 *)*v16;
      v18 = *v17;
      while ( (__int64 *)v18 != v17 )
      {
        std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::_Insert<_GUID const &,std::_Nil>(
          v44,
          (__int64)v36,
          v18 + 32);
        v19 = GetBindingPath(&Block, v18 + 28);
        if ( *(_QWORD *)(v19 + 24) >= 8u )
          v19 = *(_QWORD *)v19;
        RegistryKey::DeleteSubKey((RegistryKey *)&v37, (const wchar_t *)v19);
        LOBYTE(v20) = 1;
        std::wstring::_Tidy(&Block, v20, 0);
        if ( !*(_BYTE *)(v18 + 25) )
        {
          if ( *(_BYTE *)(*(_QWORD *)(v18 + 16) + 25LL) )
          {
            for ( j = *(_QWORD *)(v18 + 8); !*(_BYTE *)(j + 25) && v18 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
              v18 = j;
          }
          else
          {
            j = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Min();
          }
          v18 = j;
        }
      }
      RegistryKey::TryOpenSubKey(&v37, (HKEY)&v30, L"Parameters\\Adapters", 0x20019u, 0);
      v22 = v30;
      if ( v30 )
      {
        *(_OWORD *)v32 = 0;
        v33 = 0;
        v23 = v44[0];
        for ( k = (__int64 *)*v44[0]; k != v23; k = (__int64 *)*k )
        {
          StringFromGuid(&Block, k + 2);
          p_Block = (const WCHAR *)&Block;
          if ( *(_QWORD *)((char *)&v43 + 4) >= 8u )
            p_Block = (const WCHAR *)Block;
          RegistryKey::TryOpenSubKey(&v30, (HKEY)&hKey, p_Block, 0x20019u, 0);
          if ( hKey && !RegistryKey::GetNumSubKeys((RegistryKey *)&hKey) )
            std::vector<std::wstring>::push_back(v32, &Block);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          LOBYTE(v26) = 1;
          std::wstring::_Tidy(&Block, v26, 0);
        }
        for ( m = v32[0]; m != v32[1]; m += 16 )
        {
          if ( *((_QWORD *)m + 3) < 8u )
            v28 = m;
          else
            v28 = *(const wchar_t **)m;
          RegistryKey::DeleteEmptySubKey(&v30, v28);
        }
        std::vector<std::wstring>::_Tidy(v32);
        v22 = v30;
      }
      if ( v22 )
        RegCloseKey(v22);
      std::vector<NetSetupLoadedPlugin const *>::~vector<NetSetupLoadedPlugin const *>((__int64)v45);
      std::list<_GUID>::~list<_GUID>(v44);
      if ( v37 )
        RegCloseKey(v37);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v37);
    }
    v8 += 16;
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v46);
  std::vector<std::wstring>::_Tidy(v35);
  v46 = &NetSetupTraceLogging::CompatibilityWriteOutServiceBindings::`vftable';
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v46);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v49);
  wil::details::shared_object<wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v48);
  result = wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v47);
  if ( v39 )
    return RegCloseKey(v39);
  return result;
}

```

## disassembly

```asm
0x180038b30  push    rbp
0x180038b32  push    rbx
0x180038b33  push    rsi
0x180038b34  push    rdi
0x180038b35  push    r12
0x180038b37  push    r13
0x180038b39  push    r14
0x180038b3b  push    r15
0x180038b3d  lea     rbp, [rsp-198h]
0x180038b45  sub     rsp, 298h
0x180038b4c  mov     [rbp+1D0h+var_238], 0FFFFFFFFFFFFFFFEh
0x180038b54  mov     rax, cs:__security_cookie
0x180038b5b  xor     rax, rsp
0x180038b5e  mov     [rbp+1D0h+var_50], rax
0x180038b65  mov     r12, r8
0x180038b68  mov     rdi, rdx
0x180038b6b  xor     r13d, r13d
0x180038b6e  xorps   xmm0, xmm0
0x180038b71  mov     [rbp+1D0h+Block], rdx
0x180038b75  mov     [rbp+1D0h+var_200], r13
0x180038b79  lea     esi, [r13+9]
0x180038b7d  mov     [rbp+1D0h+var_1F8], esi
0x180038b80  movdqu  [rbp+1D0h+var_1F4], xmm0
0x180038b85  lea     rcx, [rbp+1D0h+Block]; this
0x180038b89  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x180038b8e  mov     rdx, rax
0x180038b91  lea     rcx, [rbp+1D0h+hKey]
0x180038b95  call    ?DuplicateFrom@RegistryKey@@SA?AV1@PEAUHKEY__@@@Z; RegistryKey::DuplicateFrom(HKEY__ *)
0x180038b9a  nop
0x180038b9b  mov     [rsp+2D0h+var_2B0], r13
0x180038ba0  lea     r9d, [r13+8]
0x180038ba4  lea     r8, aServices; "Services"
0x180038bab  lea     rdx, [rbp+1D0h+var_210]
0x180038baf  mov     rcx, rax
0x180038bb2  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x180038bb7  nop
0x180038bb8  mov     rcx, [rbp+1D0h+hKey]; hKey
0x180038bbc  test    rcx, rcx
0x180038bbf  jz      short loc_180038BC8
0x180038bc1  call    cs:__imp_RegCloseKey
0x180038bc7  nop
0x180038bc8  lea     rcx, [rbp+1D0h+var_200]
0x180038bcc  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180038bd1  cmp     [rbp+1D0h+var_210], r13
0x180038bd5  jz      loc_180038F8A
0x180038bdb  mov     rbx, [r12]
0x180038bdf  lea     rdx, aCompatibilityw; "CompatibilityWriteOutServiceBindings"
0x180038be6  lea     rcx, [rbp+1D0h+var_1A0]
0x180038bea  call    ??0?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180038bef  lea     r15, ??_7CompatibilityWriteOutServiceBindings@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::CompatibilityWriteOutServiceBindings::`vftable'
0x180038bf6  mov     [rbp+1D0h+var_1A0], r15
0x180038bfa  lea     rdx, [rbx+278h]; struct _GUID *
0x180038c01  lea     rcx, [rbp+1D0h+var_1A0]; this
0x180038c05  call    ?StartActivity@CompatibilityWriteOutServiceBindings@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z; NetSetupTraceLogging::CompatibilityWriteOutServiceBindings::StartActivity(_GUID const &)
0x180038c0a  nop
0x180038c0b  xorps   xmm0, xmm0
0x180038c0e  mov     [rbp+1D0h+Block], rdi
0x180038c12  mov     [rbp+1D0h+var_200], r13
0x180038c16  mov     [rbp+1D0h+var_1F8], esi
0x180038c19  movdqu  [rbp+1D0h+var_1F4], xmm0
0x180038c1e  xor     r9d, r9d
0x180038c21  lea     r8, NETSETUPPKEY_NetCfg_DirtyServices; unsigned int
0x180038c28  lea     rdx, [rsp+2D0h+var_280]; struct _NETSETUPPROPKEY *
0x180038c2d  lea     rcx, [rbp+1D0h+Block]; this
0x180038c31  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x180038c36  nop
0x180038c37  lea     rdx, [rbp+1D0h+var_250]
0x180038c3b  lea     rcx, [rsp+2D0h+var_280]
0x180038c40  call    ?GetStringArray@Property@NetSetup2@@QEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; NetSetup2::Property::GetStringArray(void)
0x180038c45  nop
0x180038c46  lea     rcx, [rsp+2D0h+var_268]
0x180038c4b  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180038c50  nop
0x180038c51  lea     rcx, [rbp+1D0h+var_200]
0x180038c55  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180038c5a  mov     rdi, [rbp+1D0h+var_250]
0x180038c5e  mov     r14, [rbp+1D0h+var_248]
0x180038c62  cmp     rdi, r14
0x180038c65  jz      loc_180038F2F
0x180038c6b  cmp     qword ptr [rdi+18h], 8
0x180038c70  jb      short loc_180038C77
0x180038c72  mov     r8, [rdi]
0x180038c75  jmp     short loc_180038C7A
0x180038c77  mov     r8, rdi
0x180038c7a  mov     [rsp+2D0h+var_2B0], r13
0x180038c7f  mov     r9d, 2001Dh
0x180038c85  lea     rdx, [rbp+1D0h+var_220]
0x180038c89  lea     rcx, [rbp+1D0h+var_210]
0x180038c8d  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x180038c92  nop
0x180038c93  cmp     [rbp+1D0h+var_220], r13
0x180038c97  jz      loc_180038F1D
0x180038c9d  mov     rcx, [r12]
0x180038ca1  add     rcx, 2D8h
0x180038ca8  mov     rdx, rdi
0x180038cab  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$set@UBindPathDescriptor@@U?$less@UBindPathDescriptor@@@std@@V?$allocator@UBindPathDescriptor@@@3@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$set@UBindPathDescriptor@@U?$less@UBindPathDescriptor@@@std@@V?$allocator@UBindPathDescriptor@@@3@@2@@std@@@2@@std@@QEAAAEAV?$set@UBindPathDescriptor@@U?$less@UBindPathDescriptor@@@std@@V?$allocator@UBindPathDescriptor@@@3@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::set<BindPathDescriptor>>::operator[](std::wstring const &)
0x180038cb0  mov     rsi, [rax]
0x180038cb3  mov     rbx, [rsi]
0x180038cb6  cmp     rbx, rsi
0x180038cb9  jz      loc_180038D51
0x180038cbf  lea     rdx, [rbx+1Ch]
0x180038cc3  lea     rcx, [rbp+1D0h+Block]
0x180038cc7  call    GetBindingPath
0x180038ccc  nop
0x180038ccd  cmp     qword ptr [rax+18h], 8
0x180038cd2  jb      short loc_180038CD7
0x180038cd4  mov     rax, [rax]
0x180038cd7  mov     [rsp+2D0h+var_2A8], r13
0x180038cdc  mov     [rsp+2D0h+var_2B0], r13
0x180038ce1  mov     r9d, 2
0x180038ce7  mov     r8, rax
0x180038cea  lea     rdx, [rsp+2D0h+var_288]
0x180038cef  lea     rcx, [rbp+1D0h+var_220]
0x180038cf3  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180038cf8  mov     rcx, [rsp+2D0h+var_288]; hKey
0x180038cfd  test    rcx, rcx
0x180038d00  jz      short loc_180038D09
0x180038d02  call    cs:__imp_RegCloseKey
0x180038d08  nop
0x180038d09  cmp     qword ptr [rbp+1D0h+var_1F4+4], 8
0x180038d0e  jb      short loc_180038D19
0x180038d10  mov     rcx, [rbp+1D0h+Block]; Block
0x180038d14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180038d19  cmp     [rbx+19h], r13b
0x180038d1d  jnz     short loc_180038CB6
0x180038d1f  mov     rcx, [rbx+10h]
0x180038d23  cmp     [rcx+19h], r13b
0x180038d27  jnz     short loc_180038D30
0x180038d29  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Min(std::_Tree_node<std::pair<std::wstring const,int>,void *> *)
0x180038d2e  jmp     short loc_180038D49
0x180038d30  mov     rax, [rbx+8]
0x180038d34  jmp     short loc_180038D43
0x180038d36  cmp     rbx, [rax+10h]
0x180038d3a  jnz     short loc_180038D49
0x180038d3c  mov     rbx, rax
0x180038d3f  mov     rax, [rax+8]
0x180038d43  cmp     [rax+19h], r13b
0x180038d47  jz      short loc_180038D36
0x180038d49  mov     rbx, rax
0x180038d4c  jmp     loc_180038CB6
0x180038d51  mov     rcx, [r12]
0x180038d55  add     rcx, 318h
0x180038d5c  mov     rdx, rdi
0x180038d5f  call    ??A?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$set@UBindPathDescriptor@@U?$less@UBindPathDescriptor@@@std@@V?$allocator@UBindPathDescriptor@@@3@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$set@UBindPathDescriptor@@U?$less@UBindPathDescriptor@@@std@@V?$allocator@UBindPathDescriptor@@@3@@2@@std@@@2@@std@@QEAAAEAV?$set@UBindPathDescriptor@@U?$less@UBindPathDescriptor@@@std@@V?$allocator@UBindPathDescriptor@@@3@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::unordered_map<std::wstring,std::set<BindPathDescriptor>>::operator[](std::wstring const &)
0x180038d64  mov     rsi, rax
0x180038d67  lea     rcx, [rbp+1D0h+var_1E0]
0x180038d6b  call    ??0?$unordered_set@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@V?$allocator@U_GUID@@@3@@std@@QEAA@XZ; std::unordered_set<_GUID>::unordered_set<_GUID>(void)
0x180038d70  nop
0x180038d71  mov     rsi, [rsi]
0x180038d74  mov     rbx, [rsi]
0x180038d77  cmp     rbx, rsi
0x180038d7a  jz      short loc_180038DF5
0x180038d7c  lea     r8, [rbx+20h]
0x180038d80  lea     rdx, [rbp+1D0h+var_230]
0x180038d84  lea     rcx, [rbp+1D0h+var_1E0]
0x180038d88  call    ??$_Insert@AEBU_GUID@@U_Nil@std@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@U_Nil@1@@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::_Insert<_GUID const &,std::_Nil>(_GUID const &,std::_Nil)
0x180038d8d  lea     rdx, [rbx+1Ch]
0x180038d91  lea     rcx, [rbp+1D0h+Block]
0x180038d95  call    GetBindingPath
0x180038d9a  nop
0x180038d9b  cmp     qword ptr [rax+18h], 8
0x180038da0  jb      short loc_180038DA5
0x180038da2  mov     rax, [rax]
0x180038da5  mov     rdx, rax; wchar_t *
0x180038da8  lea     rcx, [rbp+1D0h+var_220]; this
0x180038dac  call    ?DeleteSubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteSubKey(wchar_t const *)
0x180038db1  nop
0x180038db2  xor     r8d, r8d
0x180038db5  mov     dl, 1
0x180038db7  lea     rcx, [rbp+1D0h+Block]
0x180038dbb  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180038dc0  cmp     [rbx+19h], r13b
0x180038dc4  jnz     short loc_180038D77
0x180038dc6  mov     rcx, [rbx+10h]
0x180038dca  cmp     [rcx+19h], r13b
0x180038dce  jnz     short loc_180038DD7
0x180038dd0  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Min(std::_Tree_node<std::pair<std::wstring const,int>,void *> *)
0x180038dd5  jmp     short loc_180038DF0
0x180038dd7  mov     rax, [rbx+8]
0x180038ddb  jmp     short loc_180038DEA
0x180038ddd  cmp     rbx, [rax+10h]
0x180038de1  jnz     short loc_180038DF0
0x180038de3  mov     rbx, rax
0x180038de6  mov     rax, [rax+8]
0x180038dea  cmp     [rax+19h], r13b
0x180038dee  jz      short loc_180038DDD
0x180038df0  mov     rbx, rax
0x180038df3  jmp     short loc_180038D77
0x180038df5  mov     [rsp+2D0h+var_2B0], r13
0x180038dfa  mov     r9d, 20019h
0x180038e00  lea     r8, aParametersAdap; "Parameters\\Adapters"
0x180038e07  lea     rdx, [rsp+2D0h+var_290]
0x180038e0c  lea     rcx, [rbp+1D0h+var_220]
0x180038e10  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x180038e15  nop
0x180038e16  mov     rcx, [rsp+2D0h+var_290]
0x180038e1b  test    rcx, rcx
0x180038e1e  jz      loc_180038EED
0x180038e24  xorps   xmm0, xmm0
0x180038e27  movdqu  xmmword ptr [rsp+2D0h+var_280], xmm0
0x180038e2d  mov     [rsp+2D0h+var_270], r13
0x180038e32  mov     rsi, [rbp+1D0h+var_1E0]
0x180038e36  mov     rbx, [rsi]
0x180038e39  cmp     rbx, rsi
0x180038e3c  jz      short loc_180038EB3
0x180038e3e  lea     rdx, [rbx+10h]
0x180038e42  lea     rcx, [rbp+1D0h+Block]
0x180038e46  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x180038e4b  nop
0x180038e4c  lea     r8, [rbp+1D0h+Block]
0x180038e50  cmp     qword ptr [rbp+1D0h+var_1F4+4], 8
0x180038e55  cmovnb  r8, [rbp+1D0h+Block]
0x180038e5a  mov     [rsp+2D0h+var_2B0], r13
0x180038e5f  mov     r9d, 20019h
0x180038e65  lea     rdx, [rbp+1D0h+hKey]
0x180038e69  lea     rcx, [rsp+2D0h+var_290]
0x180038e6e  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x180038e73  nop
0x180038e74  cmp     [rbp+1D0h+hKey], r13
0x180038e78  jz      short loc_180038E96
0x180038e7a  lea     rcx, [rbp+1D0h+hKey]; this
0x180038e7e  call    ?GetNumSubKeys@RegistryKey@@QEBAKXZ; RegistryKey::GetNumSubKeys(void)
0x180038e83  test    eax, eax
0x180038e85  jnz     short loc_180038E96
0x180038e87  lea     rdx, [rbp+1D0h+Block]
0x180038e8b  lea     rcx, [rsp+2D0h+var_280]
0x180038e90  call    ?push_back@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180038e95  nop
0x180038e96  lea     rcx, [rbp+1D0h+hKey]
0x180038e9a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180038e9f  nop
0x180038ea0  xor     r8d, r8d
0x180038ea3  mov     dl, 1
0x180038ea5  lea     rcx, [rbp+1D0h+Block]
0x180038ea9  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180038eae  mov     rbx, [rbx]
0x180038eb1  jmp     short loc_180038E39
0x180038eb3  mov     rbx, [rsp+2D0h+var_280]
0x180038eb8  cmp     rbx, [rsp+2D0h+var_280+8]
0x180038ebd  jz      short loc_180038EDE
0x180038ebf  cmp     qword ptr [rbx+18h], 8
0x180038ec4  jb      short loc_180038ECB
0x180038ec6  mov     rdx, [rbx]
0x180038ec9  jmp     short loc_180038ECE
0x180038ecb  mov     rdx, rbx; wchar_t *
0x180038ece  lea     rcx, [rsp+2D0h+var_290]; this
0x180038ed3  call    ?DeleteEmptySubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteEmptySubKey(wchar_t const *)
0x180038ed8  add     rbx, 20h ; ' '
0x180038edc  jmp     short loc_180038EB8
0x180038ede  lea     rcx, [rsp+2D0h+var_280]
0x180038ee3  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180038ee8  mov     rcx, [rsp+2D0h+var_290]; hKey
0x180038eed  test    rcx, rcx
0x180038ef0  jz      short loc_180038EF9
0x180038ef2  call    cs:__imp_RegCloseKey
0x180038ef8  nop
0x180038ef9  lea     rcx, [rbp+1D0h+var_1D0]
0x180038efd  call    ??1?$vector@PEBVNetSetupLoadedPlugin@@V?$allocator@PEBVNetSetupLoadedPlugin@@@std@@@std@@QEAA@XZ; std::vector<NetSetupLoadedPlugin const *>::~vector<NetSetupLoadedPlugin const *>(void)
0x180038f02  lea     rcx, [rbp+1D0h+var_1E0]
0x180038f06  call    ??1?$list@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::list<_GUID>::~list<_GUID>(void)
0x180038f0b  nop
0x180038f0c  mov     rcx, [rbp+1D0h+var_220]; hKey
0x180038f10  test    rcx, rcx
0x180038f13  jz      short loc_180038F26
0x180038f15  call    cs:__imp_RegCloseKey
0x180038f1b  jmp     short loc_180038F26
0x180038f1d  lea     rcx, [rbp+1D0h+var_220]
0x180038f21  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180038f26  add     rdi, 20h ; ' '
0x180038f2a  jmp     loc_180038C62
0x180038f2f  lea     rcx, [rbp+1D0h+var_1A0]
0x180038f33  call    ?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180038f38  nop
0x180038f39  lea     rcx, [rbp+1D0h+var_250]
0x180038f3d  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180038f42  nop
0x180038f43  lea     rax, ??_7CompatibilityWriteOutServiceBindings@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::CompatibilityWriteOutServiceBindings::`vftable'
0x180038f4a  mov     [rbp+1D0h+var_1A0], rax
0x180038f4e  lea     rcx, [rbp+1D0h+var_1A0]
0x180038f52  call    ?Destroy@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180038f57  lea     rcx, [rbp+1D0h+var_80]; this
0x180038f5e  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180038f63  lea     rcx, [rbp+1D0h+var_88]
0x180038f6a  call    ?reset@?$shared_object@V?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180038f6f  lea     rcx, [rbp+1D0h+var_198]
0x180038f73  call    ??1?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180038f78  nop
0x180038f79  mov     rcx, [rbp+1D0h+var_210]; hKey
0x180038f7d  test    rcx, rcx
0x180038f80  jz      short loc_180038F93
0x180038f82  call    cs:__imp_RegCloseKey
0x180038f88  jmp     short loc_180038F93
0x180038f8a  lea     rcx, [rbp+1D0h+var_210]
0x180038f8e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180038f93  mov     rcx, [rbp+1D0h+var_50]
0x180038f9a  xor     rcx, rsp; StackCookie
0x180038f9d  call    __security_check_cookie
0x180038fa2  add     rsp, 298h
0x180038fa9  pop     r15
0x180038fab  pop     r14
  ... truncated ...
```
