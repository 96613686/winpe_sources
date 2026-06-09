# CServiceModule::_TryLoadBacklightServer(void)

- ea: `0x1800194b0`
- end: `0x18001975b`
- name: `?_TryLoadBacklightServer@CServiceModule@@AEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025bbc`

## callees

- `0x180019270`
- `0x1800194b0`
- `0x180019764`
- `0x180019784`
- `0x1800197b4`
- `0x18001d3c8`
- `0x18001ec9c`
- `0x18001f170`
- `0x18001f1b0`
- `0x180025a34`
- `0x180028578`
- `0x180028cbc`
- `0x180028d90`
- `0x18002a1b4`
- `0x18002ab14`
- `0x180031010`

## string_xrefs

- `0x180019579`: `drivers\tablet\platform\pen\penservice\penservice.cpp`
- `0x1800195c2`: `drivers\tablet\platform\pen\penservice\penservice.cpp`
- `0x180019663`: `drivers\tablet\platform\pen\penservice\penservice.cpp`

## pseudocode

```c
__int64 __fastcall CServiceModule::_TryLoadBacklightServer(CServiceModule *this)
{
  int v1; // edi
  volatile signed __int32 *v2; // rbx
  const char *v3; // r9
  volatile signed __int32 *v4; // rbx
  __int64 (__fastcall *v5)(volatile signed __int32 *, __int64 *); // rdi
  int v6; // eax
  unsigned int v7; // edi
  volatile signed __int32 *v8; // rbx
  int v10; // eax
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // rbx
  int v13[2]; // [rsp+20h] [rbp-58h] BYREF
  char v14; // [rsp+28h] [rbp-50h]
  int v15[14]; // [rsp+30h] [rbp-48h] BYREF
  volatile signed __int32 *v16; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  volatile signed __int32 *v18; // [rsp+80h] [rbp+8h] BYREF
  char v19; // [rsp+88h] [rbp+10h] BYREF

  v18 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::start(
    &v18,
    v13);
  tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(
    (__int64)v15,
    (__int64 *)&v18);
  wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>((void **)&v18);
  v1 = dword_1800414A0;
  v2 = v16;
  v18 = v16;
  if ( v16 )
    _InterlockedAdd(v16 + 74, 1u);
  tip2::details::shared_data<1,0,0>::begin_update(v2 + 2);
  *((_DWORD *)v2 + 68) = v1;
  tip2::test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>((void **)&v18);
  *(_QWORD *)v13 = v15;
  v14 = 1;
  if ( dword_1800414A0 == 3 )
  {
    wil::GetActivationFactory<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics>(&v18);
    v4 = v18;
    if ( !v18 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD67,
        (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
        v3);
    v5 = *(__int64 (__fastcall **)(volatile signed __int32 *, __int64 *))(*(_QWORD *)v18 + 48LL);
    wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHost,wil::err_returncode_policy>::reset(&qword_1800414A8);
    v6 = v5(v4, &qword_1800414A8);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD69,
        (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
        (const char *)(unsigned int)v6,
        v13[0]);
      wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>((__int64 *)&v18);
      v14 = 0;
      v8 = v16;
      wil::EnterCriticalSection(&v19, v16 + 50);
      *((_DWORD *)v8 + 18) |= 0x300u;
      if ( *((_QWORD *)v8 + 31) )
        tip2::details::shared_data<1,0,0>::complete_helper(v8 + 2, 2);
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v19);
      tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>((__int64)v15);
      return v7;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1800414A8 + 48LL))(qword_1800414A8);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6B,
        (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
        (const char *)(unsigned int)v10,
        v13[0]);
      wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>((__int64 *)&v18);
      v14 = 0;
      v11 = v16;
      wil::EnterCriticalSection(&v19, v16 + 50);
      *((_DWORD *)v11 + 18) |= 0x300u;
      if ( *((_QWORD *)v11 + 31) )
        tip2::details::shared_data<1,0,0>::complete_helper(v11 + 2, 2);
      goto LABEL_9;
    }
    wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>((__int64 *)&v18);
  }
  v12 = v16;
  wil::EnterCriticalSection(&v18, v16 + 50);
  *((_DWORD *)v12 + 18) |= 0x300u;
  if ( *((_QWORD *)v12 + 31) )
    tip2::details::shared_data<1,0,0>::complete_helper(v12 + 2, 2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
  tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>((__int64)v15);
  return 0;
}

```

## disassembly

```asm
0x1800194b0  mov     rax, rsp
0x1800194b3  mov     [rax+18h], rbx
0x1800194b7  mov     [rax+20h], rdi
0x1800194bb  mov     [rax+8], rcx
0x1800194bf  push    r14
0x1800194c1  sub     rsp, 70h
0x1800194c5  mov     qword ptr [rax+8], 0
0x1800194cd  lea     rdx, [rax-58h]
0x1800194d1  lea     rcx, [rax+8]
0x1800194d5  call    ?start@?$tip_test@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::start(void)
0x1800194da  lea     rdx, [rsp+78h+arg_0]
0x1800194e2  lea     rcx, [rsp+78h+var_48]
0x1800194e7  call    ??0?$test_watcher@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@IEAA@AEAV?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy> &)
0x1800194ec  lea     rcx, [rsp+78h+arg_0]
0x1800194f4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>,wil::err_returncode_policy>(void)
0x1800194f9  nop
0x1800194fa  mov     edi, cs:dword_1800414A0
0x180019500  mov     rbx, [rsp+78h+var_10]
0x180019505  mov     [rsp+78h+arg_0], rbx
0x18001950d  mov     r14d, 1
0x180019513  test    rbx, rbx
0x180019516  jz      short loc_180019520
0x180019518  lock add [rbx+128h], r14d
0x180019520  lea     rcx, [rbx+8]
0x180019524  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180019529  mov     [rbx+110h], edi
0x18001952f  lea     rcx, [rsp+78h+arg_0]
0x180019537  call    ??1?$test_data_control@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_data_control<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(void)
0x18001953c  lea     rax, [rsp+78h+var_48]
0x180019541  mov     qword ptr [rsp+78h+var_58], rax; int
0x180019546  mov     [rsp+78h+var_50], r14b
0x18001954b  cmp     cs:dword_1800414A0, 3
0x180019552  jz      short loc_180019559
0x180019554  jmp     loc_1800196F6
0x180019559  lea     rcx, [rsp+78h+arg_0]
0x180019561  call    ??$GetActivationFactory@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics>(ushort const *)
0x180019566  nop
0x180019567  mov     rcx, [rsp+78h]; this
0x18001956c  mov     rbx, [rsp+78h+arg_0]
0x180019574  test    rbx, rbx
0x180019577  jnz     short loc_18001958B
0x180019579  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x180019580  mov     edx, 0D67h; void *
0x180019585  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001958b  mov     rax, [rbx]
0x18001958e  mov     rdi, [rax+30h]
0x180019592  lea     rcx, qword_1800414A8
0x180019599  call    ?reset@?$com_ptr_t@UIBacklightServerHost@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHost,wil::err_returncode_policy>::reset(void)
0x18001959e  lea     rdx, qword_1800414A8
0x1800195a5  mov     rcx, rbx
0x1800195a8  mov     rax, rdi
0x1800195ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195b0  mov     edi, eax
0x1800195b2  test    eax, eax
0x1800195b4  jns     loc_18001963E
0x1800195ba  mov     rcx, [rsp+78h]; this
0x1800195bf  mov     r9d, eax; char *
0x1800195c2  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x1800195c9  mov     edx, 0D69h; void *
0x1800195ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800195d3  nop
0x1800195d4  lea     rcx, [rsp+78h+arg_0]
0x1800195dc  call    ??1?$com_ptr_t@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>(void)
0x1800195e1  nop
0x1800195e2  mov     [rsp+78h+var_50], 0
0x1800195e7  mov     rbx, [rsp+78h+var_10]
0x1800195ec  lea     rdx, [rbx+0C8h]
0x1800195f3  lea     rcx, [rsp+78h+arg_8]
0x1800195fb  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180019600  or      dword ptr [rbx+48h], 300h
0x180019607  cmp     qword ptr [rbx+0F8h], 0
0x18001960f  jz      short loc_18001961F
0x180019611  mov     edx, 2
0x180019616  lea     rcx, [rbx+8]
0x18001961a  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18001961f  lea     rcx, [rsp+78h+arg_8]
0x180019627  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001962c  nop
0x18001962d  lea     rcx, [rsp+78h+var_48]
0x180019632  call    ??1?$test_watcher@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(void)
0x180019637  mov     eax, edi
0x180019639  jmp     loc_180019748
0x18001963e  mov     rcx, cs:qword_1800414A8
0x180019645  mov     rax, [rcx]
0x180019648  mov     rax, [rax+30h]
0x18001964c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019651  mov     edi, eax
0x180019653  test    eax, eax
0x180019655  jns     loc_1800196DC
0x18001965b  mov     rcx, [rsp+78h]; this
0x180019660  mov     r9d, eax; char *
0x180019663  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x18001966a  mov     edx, 0D6Bh; void *
0x18001966f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019674  nop
0x180019675  lea     rcx, [rsp+78h+arg_0]
0x18001967d  call    ??1?$com_ptr_t@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>(void)
0x180019682  nop
0x180019683  mov     [rsp+78h+var_50], 0
0x180019688  mov     rbx, [rsp+78h+var_10]
0x18001968d  lea     rdx, [rbx+0C8h]
0x180019694  lea     rcx, [rsp+78h+arg_8]
0x18001969c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800196a1  or      dword ptr [rbx+48h], 300h
0x1800196a8  cmp     qword ptr [rbx+0F8h], 0
0x1800196b0  jz      short loc_1800196C0
0x1800196b2  mov     edx, 2
0x1800196b7  lea     rcx, [rbx+8]
0x1800196bb  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x1800196c0  lea     rcx, [rsp+78h+arg_8]
0x1800196c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800196cd  nop
0x1800196ce  lea     rcx, [rsp+78h+var_48]
0x1800196d3  call    ??1?$test_watcher@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(void)
0x1800196d8  mov     eax, edi
0x1800196da  jmp     short loc_180019748
0x1800196dc  lea     rcx, [rsp+78h+arg_0]
0x1800196e4  call    ??1?$com_ptr_t@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics,wil::err_exception_policy>(void)
0x1800196e9  nop
0x1800196ea  jmp     short loc_1800196F1
0x1800196ec  mov     r14b, [rsp+78h+var_50]
0x1800196f1  test    r14b, r14b
0x1800196f4  jz      short loc_18001973C
0x1800196f6  mov     rbx, [rsp+78h+var_10]
0x1800196fb  lea     rdx, [rbx+0C8h]
0x180019702  lea     rcx, [rsp+78h+arg_0]
0x18001970a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001970f  or      dword ptr [rbx+48h], 300h
0x180019716  cmp     qword ptr [rbx+0F8h], 0
0x18001971e  jz      short loc_18001972E
0x180019720  mov     edx, 2
0x180019725  lea     rcx, [rbx+8]
0x180019729  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x18001972e  lea     rcx, [rsp+78h+arg_0]
0x180019736  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001973b  nop
0x18001973c  lea     rcx, [rsp+78h+var_48]
0x180019741  call    ??1?$test_watcher@V?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>::~test_watcher<tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>>(void)
0x180019746  xor     eax, eax
0x180019748  lea     r11, [rsp+78h+var_8]
0x18001974d  mov     rbx, [r11+20h]
0x180019751  mov     rdi, [r11+28h]
0x180019755  mov     rsp, r11
0x180019758  pop     r14
0x18001975a  retn
```
