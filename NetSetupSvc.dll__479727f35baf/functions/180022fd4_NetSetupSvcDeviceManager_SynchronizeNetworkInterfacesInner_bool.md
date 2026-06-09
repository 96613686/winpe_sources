# NetSetupSvcDeviceManager::SynchronizeNetworkInterfacesInner(bool &)

- ea: `0x180022fd4`
- end: `0x180023556`
- name: `?SynchronizeNetworkInterfacesInner@NetSetupSvcDeviceManager@@AEAAXAEA_N@Z`
- size: `1410`
- prototype: `void __fastcall(NetSetupSvcDeviceManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `30`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001ae20`

## callees

- `0x1800027c0`
- `0x180008d94`
- `0x18000d8ec`
- `0x18000d954`
- `0x18000df60`
- `0x18000fd7c`
- `0x180010284`
- `0x18001d080`
- `0x18001d0ac`
- `0x18001d3b4`
- `0x18001d3e4`
- `0x18001d414`
- `0x18001d444`
- `0x18001d8d8`
- `0x18001d92c`
- `0x18001eb14`
- `0x18001f258`
- `0x180020318`
- `0x18002266c`
- `0x180022fd4`
- `0x180023650`
- `0x180023718`
- `0x180023c2c`
- `0x180023c60`
- `0x1800244a4`
- `0x180024930`
- `0x180024bc0`
- `0x180024c44`
- `0x18002ba28`
- `0x180031010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800230c9`
- `RPCRT4!UuidCreate` at `0x1800230c9`

## pseudocode

```c
void __fastcall NetSetupSvcDeviceManager::SynchronizeNetworkInterfacesInner(NetSetupSvcDeviceManager *this, bool *a2)
{
  void *KtmHandle; // rsi
  __int64 v5; // r8
  _DWORD *v6; // rdx
  _QWORD *v7; // r10
  __int64 v8; // r9
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r10
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // r10
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // r10
  __int64 v24; // r8
  __int64 v25; // rcx
  std::_Ref_count_base *v26; // rdi
  __int64 v27; // rdx
  HResultException *v28; // rbx
  int v29; // eax
  _DWORD v30[10]; // [rsp+0h] [rbp-178h] BYREF
  __int64 v31; // [rsp+28h] [rbp-150h]
  __int64 v32; // [rsp+40h] [rbp-138h] BYREF
  HResultException *v33; // [rsp+48h] [rbp-130h] BYREF
  bool *v34; // [rsp+50h] [rbp-128h]
  __int64 *v35; // [rsp+58h] [rbp-120h] BYREF
  __int64 v36; // [rsp+60h] [rbp-118h] BYREF
  int v37; // [rsp+68h] [rbp-110h]
  __int128 v38; // [rsp+6Ch] [rbp-10Ch]
  __int64 v39; // [rsp+80h] [rbp-F8h] BYREF
  __int64 *v40; // [rsp+88h] [rbp-F0h] BYREF
  __int64 v41; // [rsp+90h] [rbp-E8h]
  __int64 *v42; // [rsp+98h] [rbp-E0h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-D8h]
  __int64 *v44; // [rsp+A8h] [rbp-D0h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-C8h]
  __int64 *v46; // [rsp+B8h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-B8h]
  __int64 *v48; // [rsp+C8h] [rbp-B0h] BYREF
  _DWORD *v49; // [rsp+D0h] [rbp-A8h]
  _QWORD v50[3]; // [rsp+D8h] [rbp-A0h] BYREF
  __int64 *v51; // [rsp+F0h] [rbp-88h] BYREF
  std::_Ref_count_base *v52; // [rsp+F8h] [rbp-80h]
  _OWORD v53[4]; // [rsp+100h] [rbp-78h] BYREF
  UUID Uuid; // [rsp+140h] [rbp-38h] BYREF

  v34 = a2;
  std::set<std::wstring>::set<std::wstring>(&v48);
  v42 = 0;
  v43 = 0;
  std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Alloc_sentinel_and_proxy(&v42);
  std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(&v46);
  v40 = 0;
  v41 = 0;
  std::_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>::_Alloc_sentinel_and_proxy(&v40);
  std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(&v44);
  v53[0] = *((_OWORD *)g_NetSetupService + 19);
  v53[1] = *((_OWORD *)g_NetSetupService + 20);
  v53[2] = *((_OWORD *)g_NetSetupService + 21);
  v53[3] = *((_OWORD *)g_NetSetupService + 22);
  Uuid = (UUID)*((_OWORD *)g_NetSetupService + 23);
  UuidCreate(&Uuid);
  v50[0] = 4;
  v50[2] = 0;
  v50[1] = v53;
  NetSetupSvcTransactionCoordinator::CreateNewTransaction(
    (NetSetupService *)((char *)g_NetSetupService + 32),
    &v51,
    &Uuid,
    (__int64)v50);
  v39 = *v51;
  v35 = &v39;
  v36 = 0;
  v37 = 9;
  v38 = 0;
  KtmHandle = NetSetup2::TransactionObject::get_KtmHandle((NetSetup2::TransactionObject *)&v35);
  std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(&v36);
  GetDevicesNeedingWork((int)&v39, (int)KtmHandle, (int)&v48, (int)&v42, (__int64)&v46, (__int64)&v40, (__int64)&v44);
  v6 = v49;
  if ( v43 || v49 || v47 || v41 || v45 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_P(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
        (char *)v49 + v47 + v41 + v45 + v43);
      v7 = WPP_GLOBAL_Control;
    }
    v8 = *v42;
    v32 = *v42;
    while ( !*(_BYTE *)(v8 + 25) )
    {
      if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 4u )
        ((void (__fastcall *)(_QWORD, __int64, __int64 *, __int64, _DWORD, __int64))WPP_SF__guid_)(
          v7[2],
          21,
          WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
          v8 + 28,
          v30[8],
          v31);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<_GUID>>,std::_Iterator_base0>::operator++(
        &v32,
        v6);
      v8 = v32;
    }
    v9 = *v46;
    v32 = *v46;
    while ( !*(_BYTE *)(v9 + 25) )
    {
      if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 4u )
      {
        v10 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(
                v9 + 48,
                v6,
                v9 + 32);
        WPP_SF_S_guid_(*(_QWORD *)(v11 + 16), 22, v12, v10, v12);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(
        &v32,
        v6);
      v9 = v32;
    }
    v13 = *v48;
    v32 = *v48;
    while ( !*(_BYTE *)(v13 + 25) )
    {
      if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 4u )
      {
        v14 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(
                v13 + 32,
                v6,
                v5);
        WPP_SF_S(*(_QWORD *)(v15 + 16), 23, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v14);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(
        &v32,
        v6);
      v13 = v32;
    }
    v16 = *v40;
    v32 = *v40;
    while ( !*(_BYTE *)(v16 + 25) )
    {
      if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 4u )
      {
        v17 = ((__int64 (__fastcall *)(__int64, __int64, __int64))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(
                v16 + 32,
                v16 + 80,
                v16 + 64);
        WPP_SF_S_guid__guid_(*(_QWORD *)(v18 + 16), v19, v20, v17, v20, v19);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(
        &v32,
        v6);
      v16 = v32;
    }
    v21 = *v44;
    v32 = *v44;
    while ( !*(_BYTE *)(v21 + 25) )
    {
      if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 4u )
      {
        v22 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(
                v21 + 48,
                v6,
                v21 + 32);
        WPP_SF_S_guid_(*(_QWORD *)(v23 + 16), 25, v24, v22, v24);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(
        &v32,
        v6);
      v21 = v32;
    }
    NetSetupSvcDeviceManager::UninstallDevices(v13, &v39, &v42, a2);
    NetSetupSvcDeviceManager::ReinstallDevices(
      (HKEY)(_DWORD)this,
      (unsigned int)&v39,
      (__int64 **)(unsigned int)&v46,
      (_QWORD *)(_DWORD)KtmHandle,
      a2);
    NetSetupSvcDeviceManager::InstallDevices((__int64)this, (__int64)&v39, &v48, (__int64)KtmHandle, a2);
    NetSetupSvcDeviceManager::MergeDevices(v25, &v39, &v40, KtmHandle, a2);
    NetSetupSvcDeviceManager::UpgradeDevices((int)this, (int)&v39, (int)&v44, (int)KtmHandle, (__int64)a2);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      NetSetup2::details::TransactionBase::Commit((NetSetup2::details::TransactionBase *)&v39);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &HResultException `RTTI Type Descriptor', &v33) )
      {
        v6 = v30;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          v28 = v33;
        }
        else
        {
          v28 = v33;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
            *((unsigned int *)v33 + 8));
        }
        v29 = *((_DWORD *)v28 + 8);
        if ( v29 != -2147018096 && v29 != -2147018195 && v29 != -2147018170 && v29 != -803667947 )
          throw;
        *v34 = 0;
        __eh34_try_continuation(0, &HResultException `RTTI Type Descriptor', &loc_1800234AD);
      }
    }
  }
  v39 = 0;
  v26 = v52;
  if ( v52 && _InterlockedExchangeAdd((volatile signed __int32 *)v52 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *, _DWORD *))v26)(v26, v6);
    std::_Ref_count_base::_Decwref(v26);
  }
  std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>(
    &v44,
    v6);
  std::_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>::~_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>(&v40);
  std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>(
    &v46,
    v27);
  std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>(&v42);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v48);
}

```

## disassembly

```asm
0x180022fd4  mov     [rsp+arg_10], rbx
0x180022fd9  mov     [rsp+arg_18], rsi
0x180022fde  push    rdi
0x180022fdf  push    r14
0x180022fe1  push    r15
0x180022fe3  sub     rsp, 160h
0x180022fea  mov     rax, cs:__security_cookie
0x180022ff1  xor     rax, rsp
0x180022ff4  mov     [rsp+178h+var_28], rax
0x180022ffc  mov     rdi, rdx
0x180022fff  mov     r14, rcx
0x180023002  mov     [rsp+178h+var_128], rdx
0x180023007  lea     rcx, [rsp+178h+var_B0]
0x18002300f  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180023014  nop
0x180023015  xor     ebx, ebx
0x180023017  mov     [rsp+178h+var_E0], rbx
0x18002301f  mov     [rsp+178h+var_D8], rbx
0x180023027  lea     rcx, [rsp+178h+var_E0]
0x18002302f  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Alloc_sentinel_and_proxy(void)
0x180023034  nop
0x180023035  lea     rcx, [rsp+178h+var_C0]
0x18002303d  call    ??0?$map@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@@std@@QEAA@XZ; std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(void)
0x180023042  nop
0x180023043  mov     [rsp+178h+var_F0], rbx
0x18002304b  mov     [rsp+178h+var_E8], rbx
0x180023053  lea     rcx, [rsp+178h+var_F0]
0x18002305b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@UInterfacesToMerge@@U?$less@UInterfacesToMerge@@@std@@V?$allocator@UInterfacesToMerge@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>::_Alloc_sentinel_and_proxy(void)
0x180023060  nop
0x180023061  lea     rcx, [rsp+178h+var_D0]
0x180023069  call    ??0?$map@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@3@@std@@QEAA@XZ; std::map<_GUID,std::wstring>::map<_GUID,std::wstring>(void)
0x18002306e  nop
0x18002306f  mov     rax, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x180023076  movups  xmm0, xmmword ptr [rax+130h]
0x18002307d  movaps  [rsp+178h+var_78], xmm0
0x180023085  movups  xmm1, xmmword ptr [rax+140h]
0x18002308c  movaps  [rsp+178h+var_68], xmm1
0x180023094  movups  xmm0, xmmword ptr [rax+150h]
0x18002309b  movaps  [rsp+178h+var_58], xmm0
0x1800230a3  movups  xmm1, xmmword ptr [rax+160h]
0x1800230aa  movaps  [rsp+178h+var_48], xmm1
0x1800230b2  movups  xmm0, xmmword ptr [rax+170h]
0x1800230b9  movaps  xmmword ptr [rsp+178h+Uuid.Data1], xmm0
0x1800230c1  lea     rcx, [rsp+178h+Uuid]; Uuid
0x1800230c9  call    cs:__imp_UuidCreate
0x1800230cf  mov     [rsp+178h+var_A0], 4
0x1800230db  mov     [rsp+178h+var_90], rbx
0x1800230e3  lea     rax, [rsp+178h+var_78]
0x1800230eb  mov     [rsp+178h+var_98], rax
0x1800230f3  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x1800230fa  add     rcx, 20h ; ' '; struct StackLock *
0x1800230fe  lea     r9, [rsp+178h+var_A0]
0x180023106  lea     r8, [rsp+178h+Uuid]
0x18002310e  lea     rdx, [rsp+178h+var_88]
0x180023116  call    ?CreateNewTransaction@NetSetupSvcTransactionCoordinator@@QEAA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@std@@AEBU_GUID@@PEAU_NETSETUP_ENVIRONMENT@@@Z; NetSetupSvcTransactionCoordinator::CreateNewTransaction(_GUID const &,_NETSETUP_ENVIRONMENT *)
0x18002311b  nop
0x18002311c  mov     rax, [rsp+178h+var_88]
0x180023124  mov     rcx, [rax]
0x180023127  mov     [rsp+178h+var_F8], rcx
0x18002312f  xorps   xmm0, xmm0
0x180023132  lea     rax, [rsp+178h+var_F8]
0x18002313a  mov     [rsp+178h+var_120], rax
0x18002313f  mov     [rsp+178h+var_118], rbx
0x180023144  mov     [rsp+178h+var_110], 9
0x18002314c  movdqu  [rsp+178h+var_10C], xmm0
0x180023152  lea     rcx, [rsp+178h+var_120]; this
0x180023157  call    ?get_KtmHandle@TransactionObject@NetSetup2@@QEBAPEAXXZ; NetSetup2::TransactionObject::get_KtmHandle(void)
0x18002315c  mov     rsi, rax
0x18002315f  lea     rcx, [rsp+178h+var_118]
0x180023164  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x180023169  lea     rax, [rsp+178h+var_D0]
0x180023171  mov     [rsp+178h+var_148], rax
0x180023176  lea     rax, [rsp+178h+var_F0]
0x18002317e  mov     [rsp+178h+var_150], rax
0x180023183  lea     rax, [rsp+178h+var_C0]
0x18002318b  mov     [rsp+178h+var_158], rax
0x180023190  lea     r9, [rsp+178h+var_E0]
0x180023198  lea     r8, [rsp+178h+var_B0]
0x1800231a0  mov     rdx, rsi
0x1800231a3  lea     rcx, [rsp+178h+var_F8]
0x1800231ab  call    GetDevicesNeedingWork
0x1800231b0  mov     rdx, [rsp+178h+var_A8]
0x1800231b8  cmp     [rsp+178h+var_D8], rbx
0x1800231c0  jnz     short loc_1800231E9
0x1800231c2  test    rdx, rdx
0x1800231c5  jnz     short loc_1800231E9
0x1800231c7  cmp     [rsp+178h+var_B8], rbx
0x1800231cf  jnz     short loc_1800231E9
0x1800231d1  cmp     [rsp+178h+var_E8], rbx
0x1800231d9  jnz     short loc_1800231E9
0x1800231db  cmp     [rsp+178h+var_C8], rbx
0x1800231e3  jz      loc_1800234AF
0x1800231e9  lea     r15, WPP_GLOBAL_Control
0x1800231f0  mov     r10, cs:WPP_GLOBAL_Control
0x1800231f7  cmp     r10, r15
0x1800231fa  jz      short loc_180023242
0x1800231fc  cmp     byte ptr [r10+19h], 4
0x180023201  jb      short loc_180023242
0x180023203  mov     r9, [rsp+178h+var_C8]
0x18002320b  add     r9, [rsp+178h+var_E8]
0x180023213  add     r9, [rsp+178h+var_B8]
0x18002321b  add     r9, rdx
0x18002321e  add     r9, [rsp+178h+var_D8]
0x180023226  mov     edx, 14h
0x18002322b  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180023232  mov     rcx, [r10+10h]
0x180023236  call    WPP_SF_P
0x18002323b  mov     r10, cs:WPP_GLOBAL_Control
0x180023242  mov     r9, [rsp+178h+var_E0]
0x18002324a  mov     r9, [r9]
0x18002324d  mov     [rsp+178h+var_138], r9
0x180023252  cmp     [r9+19h], bl
0x180023256  jnz     short loc_180023295
0x180023258  cmp     r10, r15
0x18002325b  jz      short loc_180023284
0x18002325d  cmp     byte ptr [r10+19h], 4
0x180023262  jb      short loc_180023284
0x180023264  add     r9, 1Ch
0x180023268  mov     edx, 15h
0x18002326d  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180023274  mov     rcx, [r10+10h]
0x180023278  call    WPP_SF__guid_
0x18002327d  mov     r10, cs:WPP_GLOBAL_Control
0x180023284  lea     rcx, [rsp+178h+var_138]
0x180023289  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<_GUID>>,std::_Iterator_base0>::operator++(void)
0x18002328e  mov     r9, [rsp+178h+var_138]
0x180023293  jmp     short loc_180023252
0x180023295  mov     rax, [rsp+178h+var_C0]
0x18002329d  mov     rax, [rax]
0x1800232a0  mov     [rsp+178h+var_138], rax
0x1800232a5  cmp     [rax+19h], bl
0x1800232a8  jnz     short loc_1800232F1
0x1800232aa  cmp     r10, r15
0x1800232ad  jz      short loc_1800232E0
0x1800232af  cmp     byte ptr [r10+19h], 4
0x1800232b4  jb      short loc_1800232E0
0x1800232b6  lea     r8, [rax+20h]
0x1800232ba  lea     rcx, [r8+10h]
0x1800232be  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800232c3  mov     r9, rax
0x1800232c6  mov     edx, 16h
0x1800232cb  mov     [rsp+178h+var_158], r8
0x1800232d0  mov     rcx, [r10+10h]
0x1800232d4  call    WPP_SF_S_guid_
0x1800232d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800232e0  lea     rcx, [rsp+178h+var_138]
0x1800232e5  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800232ea  mov     rax, [rsp+178h+var_138]
0x1800232ef  jmp     short loc_1800232A5
0x1800232f1  mov     rcx, [rsp+178h+var_B0]
0x1800232f9  mov     rcx, [rcx]
0x1800232fc  mov     [rsp+178h+var_138], rcx
0x180023301  cmp     [rcx+19h], bl
0x180023304  jnz     short loc_18002334B
0x180023306  cmp     r10, r15
0x180023309  jz      short loc_18002333A
0x18002330b  cmp     byte ptr [r10+19h], 4
0x180023310  jb      short loc_18002333A
0x180023312  add     rcx, 20h ; ' '
0x180023316  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002331b  mov     r9, rax
0x18002331e  mov     edx, 17h
0x180023323  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18002332a  mov     rcx, [r10+10h]
0x18002332e  call    WPP_SF_S
0x180023333  mov     r10, cs:WPP_GLOBAL_Control
0x18002333a  lea     rcx, [rsp+178h+var_138]
0x18002333f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180023344  mov     rcx, [rsp+178h+var_138]
0x180023349  jmp     short loc_180023301
0x18002334b  mov     rax, [rsp+178h+var_F0]
0x180023353  mov     rax, [rax]
0x180023356  mov     [rsp+178h+var_138], rax
0x18002335b  cmp     [rax+19h], bl
0x18002335e  jnz     short loc_1800233AB
0x180023360  cmp     r10, r15
0x180023363  jz      short loc_18002339A
0x180023365  cmp     byte ptr [r10+19h], 4
0x18002336a  jb      short loc_18002339A
0x18002336c  lea     rcx, [rax+20h]
0x180023370  lea     rdx, [rcx+30h]
0x180023374  lea     r8, [rcx+20h]
0x180023378  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002337d  mov     r9, rax
0x180023380  mov     [rsp+178h+var_150], rdx
0x180023385  mov     [rsp+178h+var_158], r8
0x18002338a  mov     rcx, [r10+10h]
0x18002338e  call    WPP_SF_S_guid__guid_
0x180023393  mov     r10, cs:WPP_GLOBAL_Control
0x18002339a  lea     rcx, [rsp+178h+var_138]
0x18002339f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800233a4  mov     rax, [rsp+178h+var_138]
0x1800233a9  jmp     short loc_18002335B
0x1800233ab  mov     rax, [rsp+178h+var_D0]
0x1800233b3  mov     rax, [rax]
0x1800233b6  mov     [rsp+178h+var_138], rax
0x1800233bb  cmp     [rax+19h], bl
0x1800233be  jnz     short loc_180023407
0x1800233c0  cmp     r10, r15
0x1800233c3  jz      short loc_1800233F6
0x1800233c5  cmp     byte ptr [r10+19h], 4
0x1800233ca  jb      short loc_1800233F6
0x1800233cc  lea     r8, [rax+20h]
0x1800233d0  lea     rcx, [r8+10h]
0x1800233d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800233d9  mov     r9, rax
0x1800233dc  mov     edx, 19h
0x1800233e1  mov     [rsp+178h+var_158], r8
0x1800233e6  mov     rcx, [r10+10h]
0x1800233ea  call    WPP_SF_S_guid_
0x1800233ef  mov     r10, cs:WPP_GLOBAL_Control
0x1800233f6  lea     rcx, [rsp+178h+var_138]
0x1800233fb  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180023400  mov     rax, [rsp+178h+var_138]
0x180023405  jmp     short loc_1800233BB
0x180023407  mov     r9, rdi
0x18002340a  lea     r8, [rsp+178h+var_E0]
0x180023412  lea     rdx, [rsp+178h+var_F8]
0x18002341a  call    ?UninstallDevices@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@AEA_N@Z; NetSetupSvcDeviceManager::UninstallDevices(NetSetup2::NonOwningTransaction &,std::set<_GUID> const &,bool &)
0x18002341f  mov     [rsp+178h+var_158], rdi
0x180023424  mov     r9, rsi
0x180023427  lea     r8, [rsp+178h+var_C0]
0x18002342f  lea     rdx, [rsp+178h+var_F8]
0x180023437  mov     rcx, r14
0x18002343a  call    ?ReinstallDevices@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$set@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@U?$less@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@V?$allocator@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@PEAXAEA_N@Z; NetSetupSvcDeviceManager::ReinstallDevices(NetSetup2::NonOwningTransaction &,std::set<std::pair<_GUID,std::wstring>> const &,void *,bool &)
0x18002343f  mov     [rsp+178h+var_158], rdi
0x180023444  mov     r9, rsi
0x180023447  lea     r8, [rsp+178h+var_B0]
0x18002344f  lea     rdx, [rsp+178h+var_F8]
0x180023457  mov     rcx, r14
0x18002345a  call    ?InstallDevices@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEAXAEA_N@Z; NetSetupSvcDeviceManager::InstallDevices(NetSetup2::NonOwningTransaction &,std::set<std::wstring> const &,void *,bool &)
0x18002345f  mov     [rsp+178h+var_158], rdi
0x180023464  mov     r9, rsi
0x180023467  lea     r8, [rsp+178h+var_F0]
0x18002346f  lea     rdx, [rsp+178h+var_F8]
0x180023477  call    ?MergeDevices@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$set@UInterfacesToMerge@@U?$less@UInterfacesToMerge@@@std@@V?$allocator@UInterfacesToMerge@@@3@@std@@PEAXAEA_N@Z; NetSetupSvcDeviceManager::MergeDevices(NetSetup2::NonOwningTransaction &,std::set<InterfacesToMerge> const &,void *,bool &)
0x18002347c  mov     [rsp+178h+var_158], rdi
0x180023481  mov     r9, rsi
0x180023484  lea     r8, [rsp+178h+var_D0]
0x18002348c  lea     rdx, [rsp+178h+var_F8]
0x180023494  mov     rcx, r14
0x180023497  call    ?UpgradeDevices@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$set@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@U?$less@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@V?$allocator@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@PEAXAEA_N@Z; NetSetupSvcDeviceManager::UpgradeDevices(NetSetup2::NonOwningTransaction &,std::set<std::pair<_GUID,std::wstring>> const &,void *,bool &)
0x18002349c  nop
0x18002349d  lea     rcx, [rsp+178h+var_F8]; this
0x1800234a5  call    ?Commit@TransactionBase@details@NetSetup2@@QEAAXXZ; NetSetup2::details::TransactionBase::Commit(void)
0x1800234aa  nop
0x1800234ab  jmp     short loc_1800234AF
0x1800234ad  xor     ebx, ebx
0x1800234af  mov     [rsp+178h+var_F8], rbx
0x1800234b7  mov     rdi, [rsp+178h+var_80]
0x1800234bf  test    rdi, rdi
0x1800234c2  jz      short loc_1800234E8
0x1800234c4  or      eax, 0FFFFFFFFh
0x1800234c7  lock xadd [rdi+8], eax
0x1800234cc  cmp     eax, 1
0x1800234cf  jnz     short loc_1800234E8
0x1800234d1  mov     rax, [rdi]
0x1800234d4  mov     rcx, rdi
0x1800234d7  mov     rax, [rax]
0x1800234da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234df  mov     rcx, rdi; this
0x1800234e2  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800234e7  nop
0x1800234e8  lea     rcx, [rsp+178h+var_D0]
0x1800234f0  call    ??1?$_Tree@V?$_Tset_traits@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@U?$less@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@V?$allocator@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>(void)
0x1800234f5  nop
0x1800234f6  lea     rcx, [rsp+178h+var_F0]
0x1800234fe  call    ??1?$_Tree@V?$_Tset_traits@UInterfacesToMerge@@U?$less@UInterfacesToMerge@@@std@@V?$allocator@UInterfacesToMerge@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>::~_Tree<std::_Tset_traits<InterfacesToMerge,std::less<InterfacesToMerge>,std::allocator<InterfacesToMerge>,0>>(void)
0x180023503  nop
0x180023504  lea     rcx, [rsp+178h+var_C0]
0x18002350c  call    ??1?$_Tree@V?$_Tset_traits@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@U?$less@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@V?$allocator@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>::~_Tree<std::_Tset_traits<std::pair<_GUID,std::wstring>,std::less<std::pair<_GUID,std::wstring>>,std::allocator<std::pair<_GUID,std::wstring>>,0>>(void)
0x180023511  nop
0x180023512  lea     rcx, [rsp+178h+var_E0]
0x18002351a  call    ??1?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>(void)
0x18002351f  nop
0x180023520  lea     rcx, [rsp+178h+var_B0]
0x180023528  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18002352d  mov     rcx, [rsp+178h+var_28]
0x180023535  xor     rcx, rsp; StackCookie
0x180023538  call    __security_check_cookie
0x18002353d  lea     r11, [rsp+178h+var_18]
0x180023545  mov     rbx, [r11+30h]
0x180023549  mov     rsi, [r11+38h]
0x18002354d  mov     rsp, r11
0x180023550  pop     r15
0x180023552  pop     r14
0x180023554  pop     rdi
0x180023555  retn
```
