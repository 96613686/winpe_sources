# NetSetupService::ReplayPendedNotifyObjectEvents(void)

- ea: `0x18000c5e0`
- end: `0x18000ca6a`
- name: `?ReplayPendedNotifyObjectEvents@NetSetupService@@AEAAXXZ`
- size: `1162`
- prototype: `void __fastcall(NetSetupService *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x180006e34`
- `0x1800078f8`
- `0x180007bfc`
- `0x180007d80`
- `0x180007f00`
- `0x180008084`
- `0x1800082c0`
- `0x180008380`
- `0x180008d94`
- `0x180008e3c`
- `0x18000c5e0`
- `0x18000d8ec`
- `0x18000fd7c`
- `0x1800275e4`
- `0x1800283fc`
- `0x1800285cc`
- `0x18002ba28`
- `0x18002d5b8`
- `0x180031010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000c703`
- `RPCRT4!UuidCreate` at `0x18000c703`

## string_xrefs

- `0x18000c619`: `Services\netsetupsvc`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall NetSetupService::ReplayPendedNotifyObjectEvents(NetSetupService *this)
{
  unsigned int ValueDword; // eax
  int v3; // r8d
  _QWORD *v4; // rdi
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  _QWORD *v13; // rcx
  _QWORD *v14; // rbx
  _QWORD *v15; // rdi
  std::_Ref_count_base *v16; // rbx
  __int64 *v17; // [rsp+40h] [rbp-128h] BYREF
  __int64 v18; // [rsp+48h] [rbp-120h] BYREF
  int v19; // [rsp+50h] [rbp-118h]
  __int128 v20; // [rsp+54h] [rbp-114h]
  char v21[8]; // [rsp+68h] [rbp-100h] BYREF
  __int64 v22; // [rsp+70h] [rbp-F8h] BYREF
  _QWORD *v23; // [rsp+78h] [rbp-F0h] BYREF
  _QWORD *v24; // [rsp+80h] [rbp-E8h]
  _BYTE v25[12]; // [rsp+88h] [rbp-E0h]
  int v26; // [rsp+94h] [rbp-D4h]
  __int64 v27; // [rsp+98h] [rbp-D0h] BYREF
  _QWORD v28[3]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 *v29; // [rsp+B8h] [rbp-B0h] BYREF
  std::_Ref_count_base *v30; // [rsp+C0h] [rbp-A8h]
  _OWORD v31[2]; // [rsp+C8h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+E8h] [rbp-80h]
  __int64 v33; // [rsp+F0h] [rbp-78h]
  _OWORD v34[4]; // [rsp+100h] [rbp-68h] BYREF
  UUID Uuid; // [rsp+140h] [rbp-28h] BYREF

  RegistryKey::TryOpenSubKey((char *)this + 280, &v27, L"Services\\netsetupsvc", 3, 0);
  if ( v27 && (unsigned int)RegistryKey::GetValueDword(&v27, L"Start", 0, 0) == 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      ValueDword = RegistryKey::GetValueDword(&v27, L"Start", 0, 0);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, ValueDword);
    }
    try
    {
      v34[0] = *((_OWORD *)this + 19);
      v34[1] = *((_OWORD *)this + 20);
      v34[2] = *((_OWORD *)this + 21);
      v34[3] = *((_OWORD *)this + 22);
      Uuid = (UUID)*((_OWORD *)this + 23);
      UuidCreate(&Uuid);
      v28[0] = 12;
      v28[2] = 0;
      v28[1] = v34;
      NetSetupSvcTransactionCoordinator::CreateNewTransaction(
        (NetSetupService *)((char *)this + 32),
        &v29,
        &Uuid,
        (__int64)v28);
      v22 = *v29;
      v17 = &v22;
      v18 = 0;
      v19 = 1;
      v20 = NETSETUP_GLOBAL_ID;
      *(_DWORD *)v25 = 146;
      *(_QWORD *)&v25[4] = 0;
      v26 = 0;
      v31[0] = NETSETUPPKEY_Global_BindingsLastSeenByNotifyObjects;
      v31[1] = 0x92u;
      v32 = 0;
      v33 = 0;
      NetSetup2::ActiveObject::SetRawProperty((NetSetup2::ActiveObject *)&v17, (const struct _NETSETUPPROPERTY *)v31);
      std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(&v18);
      NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(
        (unsigned int)&v22,
        (unsigned int)&v23,
        v3,
        0,
        0,
        0,
        0);
      v6 = v23;
      v5 = v23;
      v4 = v24;
      while ( v5 != v4 )
      {
        v21[0] = 1;
        NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(*v5++, NETSETUPPKEY_Bind_ControllerResultDirty, v21);
        v6 = v23;
      }
      if ( v6 )
      {
        std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>();
        std::_Deallocate<16>(v23, (*(_QWORD *)v25 - (_QWORD)v23) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ProtocolDriver>(&v22, &v23);
      v7 = v23;
      v8 = v23;
      v9 = v24;
      while ( v8 != v9 )
      {
        v21[0] = 1;
        NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(*v8++, NETSETUPPKEY_Bind_ControllerResultDirty, v21);
        v7 = v23;
      }
      if ( v7 )
      {
        std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>();
        std::_Deallocate<16>(v23, (*(_QWORD *)v25 - (_QWORD)v23) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ServiceDriver>(&v22, &v23);
      v10 = v23;
      v11 = v23;
      v12 = v24;
      while ( v11 != v12 )
      {
        v21[0] = 1;
        NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(*v11++, NETSETUPPKEY_Bind_ControllerResultDirty, v21);
        v10 = v23;
      }
      if ( v10 )
      {
        std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>();
        std::_Deallocate<16>(v23, (*(_QWORD *)v25 - (_QWORD)v23) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ClientDriver>(&v22, &v23);
      v13 = v23;
      v14 = v23;
      v15 = v24;
      while ( v14 != v15 )
      {
        v21[0] = 1;
        NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(*v14++, NETSETUPPKEY_Bind_ControllerResultDirty, v21);
        v13 = v23;
      }
      if ( v13 )
      {
        std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>();
        std::_Deallocate<16>(v23, (*(_QWORD *)v25 - (_QWORD)v23) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      NetSetup2::details::TransactionBase::Commit((NetSetup2::details::TransactionBase *)&v22);
      v22 = 0;
      v16 = v30;
      if ( v30 && _InterlockedExchangeAdd((volatile signed __int32 *)v30 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(std::_Ref_count_base *))v16)(v16);
        std::_Ref_count_base::_Decwref(v16);
      }
    }
    catch ( ... )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids);
    }
    RegistryKey::SetValue(&v27, L"Start", 3, 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
}

```

## disassembly

```asm
0x18000c5e0  mov     [rsp+arg_8], rbx
0x18000c5e5  mov     [rsp+arg_10], rsi
0x18000c5ea  push    rdi
0x18000c5eb  sub     rsp, 160h
0x18000c5f2  mov     rax, cs:__security_cookie
0x18000c5f9  xor     rax, rsp
0x18000c5fc  mov     [rsp+168h+var_18], rax
0x18000c604  mov     rbx, rcx
0x18000c607  xor     esi, esi
0x18000c609  add     rcx, 118h
0x18000c610  mov     [rsp+168h+var_148], rsi
0x18000c615  lea     r9d, [rsi+3]
0x18000c619  lea     r8, aServicesNetset; "Services\\netsetupsvc"
0x18000c620  lea     rdx, [rsp+168h+var_D0]
0x18000c628  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18000c62d  nop
0x18000c62e  cmp     [rsp+168h+var_D0], rsi
0x18000c636  jz      loc_18000CA38
0x18000c63c  xor     r9d, r9d
0x18000c63f  xor     r8d, r8d
0x18000c642  lea     rdx, aStart; "Start"
0x18000c649  lea     rcx, [rsp+168h+var_D0]
0x18000c651  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18000c656  cmp     eax, 2
0x18000c659  jnz     loc_18000CA38
0x18000c65f  lea     rcx, WPP_GLOBAL_Control
0x18000c666  mov     rax, cs:WPP_GLOBAL_Control
0x18000c66d  cmp     rax, rcx
0x18000c670  jz      short loc_18000C6B0
0x18000c672  cmp     byte ptr [rax+19h], 4
0x18000c676  jb      short loc_18000C6B0
0x18000c678  xor     r9d, r9d
0x18000c67b  xor     r8d, r8d
0x18000c67e  lea     rdx, aStart; "Start"
0x18000c685  lea     rcx, [rsp+168h+var_D0]
0x18000c68d  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18000c692  lea     edx, [rsi+1Dh]
0x18000c695  mov     r9d, eax
0x18000c698  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000c69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6a6  mov     rcx, [rcx+10h]
0x18000c6aa  call    WPP_SF_d
0x18000c6af  nop
0x18000c6b0  movups  xmm0, xmmword ptr [rbx+130h]
0x18000c6b7  movaps  [rsp+168h+var_68], xmm0
0x18000c6bf  movups  xmm1, xmmword ptr [rbx+140h]
0x18000c6c6  movaps  [rsp+168h+var_58], xmm1
0x18000c6ce  movups  xmm0, xmmword ptr [rbx+150h]
0x18000c6d5  movaps  [rsp+168h+var_48], xmm0
0x18000c6dd  movups  xmm1, xmmword ptr [rbx+160h]
0x18000c6e4  movaps  [rsp+168h+var_38], xmm1
0x18000c6ec  movups  xmm0, xmmword ptr [rbx+170h]
0x18000c6f3  movaps  xmmword ptr [rsp+168h+Uuid.Data1], xmm0
0x18000c6fb  lea     rcx, [rsp+168h+Uuid]; Uuid
0x18000c703  call    cs:__imp_UuidCreate
0x18000c709  mov     [rsp+168h+var_C8], 0Ch
0x18000c715  mov     [rsp+168h+var_B8], rsi
0x18000c71d  lea     rax, [rsp+168h+var_68]
0x18000c725  mov     [rsp+168h+var_C0], rax
0x18000c72d  lea     rcx, [rbx+20h]; struct StackLock *
0x18000c731  lea     r9, [rsp+168h+var_C8]
0x18000c739  lea     r8, [rsp+168h+Uuid]
0x18000c741  lea     rdx, [rsp+168h+var_B0]
0x18000c749  call    ?CreateNewTransaction@NetSetupSvcTransactionCoordinator@@QEAA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@std@@AEBU_GUID@@PEAU_NETSETUP_ENVIRONMENT@@@Z; NetSetupSvcTransactionCoordinator::CreateNewTransaction(_GUID const &,_NETSETUP_ENVIRONMENT *)
0x18000c74e  nop
0x18000c74f  mov     rax, [rsp+168h+var_B0]
0x18000c757  mov     rcx, [rax]
0x18000c75a  mov     [rsp+168h+var_F8], rcx
0x18000c75f  lea     rax, [rsp+168h+var_F8]
0x18000c764  mov     [rsp+168h+var_128], rax
0x18000c769  mov     [rsp+168h+var_120], rsi
0x18000c76e  mov     [rsp+168h+var_118], 1
0x18000c776  movups  xmm0, cs:NETSETUP_GLOBAL_ID
0x18000c77d  movdqu  [rsp+168h+var_114], xmm0
0x18000c783  movups  xmm0, cs:NETSETUPPKEY_Global_BindingsLastSeenByNotifyObjects
0x18000c78a  mov     eax, cs:dword_1800377F0
0x18000c790  mov     dword ptr [rsp+168h+var_E0], eax
0x18000c797  xor     eax, eax
0x18000c799  mov     qword ptr [rsp+168h+var_E0+4], rax
0x18000c7a1  mov     dword ptr [rsp+168h+var_E0+0Ch], eax
0x18000c7a8  movups  [rsp+168h+var_A0], xmm0
0x18000c7b0  movups  xmm0, [rsp+168h+var_E0]
0x18000c7b8  movups  [rsp+168h+var_90], xmm0
0x18000c7c0  mov     [rsp+168h+var_80], rsi
0x18000c7c8  mov     [rsp+168h+var_78], rsi
0x18000c7d0  lea     rdx, [rsp+168h+var_A0]; struct _NETSETUPPROPERTY *
0x18000c7d8  lea     rcx, [rsp+168h+var_128]; this
0x18000c7dd  call    ?SetRawProperty@ActiveObject@NetSetup2@@QEAAXAEBU_NETSETUPPROPERTY@@@Z; NetSetup2::ActiveObject::SetRawProperty(_NETSETUPPROPERTY const &)
0x18000c7e2  nop
0x18000c7e3  lea     rcx, [rsp+168h+var_120]
0x18000c7e8  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18000c7ed  mov     [rsp+168h+var_138], esi
0x18000c7f1  mov     [rsp+168h+var_140], rsi
0x18000c7f6  mov     dword ptr [rsp+168h+var_148], esi
0x18000c7fa  xor     r9d, r9d
0x18000c7fd  lea     rdx, [rsp+168h+var_F0]
0x18000c802  lea     rcx, [rsp+168h+var_F8]
0x18000c807  call    ??$GetAllObjectsInner@VNetworkInterface@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z; NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)
0x18000c80c  nop
0x18000c80d  mov     rcx, [rsp+168h+var_F0]
0x18000c812  mov     rbx, rcx
0x18000c815  mov     rdx, [rsp+168h+var_E8]
0x18000c81d  mov     rdi, rdx
0x18000c820  cmp     rbx, rdi
0x18000c823  jz      short loc_18000C851
0x18000c825  mov     [rsp+168h+var_100], 1
0x18000c82a  lea     r8, [rsp+168h+var_100]
0x18000c82f  lea     rdx, NETSETUPPKEY_Bind_ControllerResultDirty
0x18000c836  mov     rcx, [rbx]
0x18000c839  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18000c83e  add     rbx, 8
0x18000c842  mov     rdx, [rsp+168h+var_E8]
0x18000c84a  mov     rcx, [rsp+168h+var_F0]
0x18000c84f  jmp     short loc_18000C820
0x18000c851  test    rcx, rcx
0x18000c854  jz      short loc_18000C874
0x18000c856  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(std::unique_ptr<NetSetup2::ClientDriver> *,std::unique_ptr<NetSetup2::ClientDriver> * const,std::allocator<std::unique_ptr<NetSetup2::ClientDriver>> &)
0x18000c85b  mov     rcx, [rsp+168h+var_F0]
0x18000c860  mov     rdx, qword ptr [rsp+168h+var_E0]
0x18000c868  sub     rdx, rcx
0x18000c86b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000c86f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c874  lea     rdx, [rsp+168h+var_F0]
0x18000c879  lea     rcx, [rsp+168h+var_F8]
0x18000c87e  call    ??$GetAllObjectsInner@VProtocolDriver@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VProtocolDriver@NetSetup2@@U?$default_delete@VProtocolDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VProtocolDriver@NetSetup2@@U?$default_delete@VProtocolDriver@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z; NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ProtocolDriver>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)
0x18000c883  nop
0x18000c884  mov     rcx, [rsp+168h+var_F0]
0x18000c889  mov     rbx, rcx
0x18000c88c  mov     rdx, [rsp+168h+var_E8]
0x18000c894  mov     rdi, rdx
0x18000c897  cmp     rbx, rdi
0x18000c89a  jz      short loc_18000C8C8
0x18000c89c  mov     [rsp+168h+var_100], 1
0x18000c8a1  lea     r8, [rsp+168h+var_100]
0x18000c8a6  lea     rdx, NETSETUPPKEY_Bind_ControllerResultDirty
0x18000c8ad  mov     rcx, [rbx]
0x18000c8b0  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18000c8b5  add     rbx, 8
0x18000c8b9  mov     rdx, [rsp+168h+var_E8]
0x18000c8c1  mov     rcx, [rsp+168h+var_F0]
0x18000c8c6  jmp     short loc_18000C897
0x18000c8c8  test    rcx, rcx
0x18000c8cb  jz      short loc_18000C8EB
0x18000c8cd  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(std::unique_ptr<NetSetup2::ClientDriver> *,std::unique_ptr<NetSetup2::ClientDriver> * const,std::allocator<std::unique_ptr<NetSetup2::ClientDriver>> &)
0x18000c8d2  mov     rcx, [rsp+168h+var_F0]
0x18000c8d7  mov     rdx, qword ptr [rsp+168h+var_E0]
0x18000c8df  sub     rdx, rcx
0x18000c8e2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000c8e6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c8eb  lea     rdx, [rsp+168h+var_F0]
0x18000c8f0  lea     rcx, [rsp+168h+var_F8]
0x18000c8f5  call    ??$GetAllObjectsInner@VServiceDriver@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VServiceDriver@NetSetup2@@U?$default_delete@VServiceDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VServiceDriver@NetSetup2@@U?$default_delete@VServiceDriver@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z; NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ServiceDriver>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)
0x18000c8fa  nop
0x18000c8fb  mov     rcx, [rsp+168h+var_F0]
0x18000c900  mov     rbx, rcx
0x18000c903  mov     rdx, [rsp+168h+var_E8]
0x18000c90b  mov     rdi, rdx
0x18000c90e  cmp     rbx, rdi
0x18000c911  jz      short loc_18000C93F
0x18000c913  mov     [rsp+168h+var_100], 1
0x18000c918  lea     r8, [rsp+168h+var_100]
0x18000c91d  lea     rdx, NETSETUPPKEY_Bind_ControllerResultDirty
0x18000c924  mov     rcx, [rbx]
0x18000c927  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18000c92c  add     rbx, 8
0x18000c930  mov     rdx, [rsp+168h+var_E8]
0x18000c938  mov     rcx, [rsp+168h+var_F0]
0x18000c93d  jmp     short loc_18000C90E
0x18000c93f  test    rcx, rcx
0x18000c942  jz      short loc_18000C962
0x18000c944  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(std::unique_ptr<NetSetup2::ClientDriver> *,std::unique_ptr<NetSetup2::ClientDriver> * const,std::allocator<std::unique_ptr<NetSetup2::ClientDriver>> &)
0x18000c949  mov     rcx, [rsp+168h+var_F0]
0x18000c94e  mov     rdx, qword ptr [rsp+168h+var_E0]
0x18000c956  sub     rdx, rcx
0x18000c959  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000c95d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c962  lea     rdx, [rsp+168h+var_F0]
0x18000c967  lea     rcx, [rsp+168h+var_F8]
0x18000c96c  call    ??$GetAllObjectsInner@VClientDriver@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z; NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::ClientDriver>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)
0x18000c971  nop
0x18000c972  mov     rcx, [rsp+168h+var_F0]
0x18000c977  mov     rbx, rcx
0x18000c97a  mov     rdx, [rsp+168h+var_E8]
0x18000c982  mov     rdi, rdx
0x18000c985  cmp     rbx, rdi
0x18000c988  jz      short loc_18000C9B6
0x18000c98a  mov     [rsp+168h+var_100], 1
0x18000c98f  lea     r8, [rsp+168h+var_100]
0x18000c994  lea     rdx, NETSETUPPKEY_Bind_ControllerResultDirty
0x18000c99b  mov     rcx, [rbx]
0x18000c99e  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18000c9a3  add     rbx, 8
0x18000c9a7  mov     rdx, [rsp+168h+var_E8]
0x18000c9af  mov     rcx, [rsp+168h+var_F0]
0x18000c9b4  jmp     short loc_18000C985
0x18000c9b6  test    rcx, rcx
0x18000c9b9  jz      short loc_18000C9D9
0x18000c9bb  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(std::unique_ptr<NetSetup2::ClientDriver> *,std::unique_ptr<NetSetup2::ClientDriver> * const,std::allocator<std::unique_ptr<NetSetup2::ClientDriver>> &)
0x18000c9c0  mov     rcx, [rsp+168h+var_F0]
0x18000c9c5  mov     rdx, qword ptr [rsp+168h+var_E0]
0x18000c9cd  sub     rdx, rcx
0x18000c9d0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000c9d4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c9d9  lea     rcx, [rsp+168h+var_F8]; this
0x18000c9de  call    ?Commit@TransactionBase@details@NetSetup2@@QEAAXXZ; NetSetup2::details::TransactionBase::Commit(void)
0x18000c9e3  nop
0x18000c9e4  mov     [rsp+168h+var_F8], rsi
0x18000c9e9  mov     rbx, [rsp+168h+var_A8]
0x18000c9f1  test    rbx, rbx
0x18000c9f4  jz      short loc_18000CA1A
0x18000c9f6  or      eax, 0FFFFFFFFh
0x18000c9f9  lock xadd [rbx+8], eax
0x18000c9fe  cmp     eax, 1
0x18000ca01  jnz     short loc_18000CA1A
0x18000ca03  mov     rax, [rbx]
0x18000ca06  mov     rcx, rbx
0x18000ca09  mov     rax, [rax]
0x18000ca0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca11  mov     rcx, rbx; this
0x18000ca14  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000ca19  nop
0x18000ca1a  jmp     short $+2
0x18000ca1c  xor     r9d, r9d
0x18000ca1f  lea     r8d, [r9+3]
0x18000ca23  lea     rdx, aStart; "Start"
0x18000ca2a  lea     rcx, [rsp+168h+var_D0]
0x18000ca32  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18000ca37  nop
0x18000ca38  lea     rcx, [rsp+168h+var_D0]
0x18000ca40  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000ca45  mov     rcx, [rsp+168h+var_18]
0x18000ca4d  xor     rcx, rsp; StackCookie
0x18000ca50  call    __security_check_cookie
0x18000ca55  lea     r11, [rsp+168h+var_8]
0x18000ca5d  mov     rbx, [r11+18h]
0x18000ca61  mov     rsi, [r11+20h]
0x18000ca65  mov     rsp, r11
0x18000ca68  pop     rdi
0x18000ca69  retn
```
