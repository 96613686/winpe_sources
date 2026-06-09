# VmMigrationTcpTransport::ReceiveSequenceAsynchronous(void *)

- ea: `0x140097680`
- end: `0x140097bfd`
- name: `?ReceiveSequenceAsynchronous@VmMigrationTcpTransport@@UEAAJPEAX@Z`
- size: `1405`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, void *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14006af38`
- `0x14006fd2c`
- `0x140078c98`
- `0x140095d6c`
- `0x140095de4`
- `0x140095e54`
- `0x140096ab4`
- `0x140097680`
- `0x140097c04`
- `0x1400988d0`
- `0x14009f9ec`
- `0x1400a009c`
- `0x1400a0154`
- `0x1400a05e8`
- `0x1400c21e4`
- `0x1400d7940`
- `0x14011d700`
- `0x14011d7f4`
- `0x14011d820`
- `0x14012bea0`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x14013fa98`
- `0x14014c9c8`
- `0x14015e968`
- `0x1401ddd6c`
- `0x1401de81c`
- `0x1401e1864`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400979df`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400979df`

## string_xrefs

- `0x1400976c6`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400976f1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097719`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097741`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097769`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097791`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400977b9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097a3d`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097aa3`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097ac1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097af2`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x140097b81`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VmMigrationTcpTransport::ReceiveSequenceAsynchronous(VmMigrationTcpTransport *this, void *a2)
{
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v4; // rbx
  __int64 future; // rbx
  __int64 v6; // rax
  DWORD v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  const char *v11; // r9
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  signed int v15; // ebx
  int LastError; // eax
  int v17; // eax
  signed int v18; // esi
  void *v19; // rdx
  wil::details *v20; // rcx
  int v21; // eax
  signed int v22; // edi
  int v24; // [rsp+20h] [rbp-F8h]
  struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *v25; // [rsp+30h] [rbp-E8h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-E0h] BYREF
  _QWORD v27[2]; // [rsp+48h] [rbp-D0h] BYREF
  char v28; // [rsp+58h] [rbp-C0h]
  __int64 (__fastcall *v29)(VmMigrationTcpTransport *); // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v30[16]; // [rsp+68h] [rbp-B0h] BYREF
  _BYTE v31[16]; // [rsp+78h] [rbp-A0h] BYREF
  void *v32; // [rsp+88h] [rbp-90h]
  VmMigrationTcpTransport *v33; // [rsp+90h] [rbp-88h]
  __int128 v34; // [rsp+98h] [rbp-80h] BYREF
  __int128 v35; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-60h] BYREF
  __int128 v37; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v38; // [rsp+D8h] [rbp-40h]
  HANDLE Handles[3]; // [rsp+E0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( *((_QWORD *)this + 65) == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4EE,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_DWORD *)this + 138) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4EF,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 72) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F0,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 71) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F1,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 81) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FD,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 91) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FE,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  if ( !*((_QWORD *)this + 73) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4FF,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)0x8007139FLL,
      v24);
  v34 = 0u;
  v35 = 0;
  v36 = 0;
  v27[0] = &v34;
  v27[1] = &v36;
  v28 = 1;
  if ( a2 )
  {
    _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v35,
      1);
    _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v36,
      1);
    v37 = 0;
    v38 = 0;
    v29 = VmMigrationTcpTransport::SendDuplexRepliesDuringAsyncSequence;
    std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(v30, &v36);
    std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(v31, &v35);
    v32 = a2;
    v33 = this;
    v4 = (struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *)operator new(0x110u);
    v25 = v4;
    memset_0(v4, 0, 0x110u);
    std::_Associated_state<long>::_Associated_state<long>(v4);
    *(_QWORD *)v4 = &std::_Packaged_state<long (void)>::`vftable';
    v26[0] = (char *)v4 + 208;
    *((_QWORD *)v4 + 33) = 0;
    *((_QWORD *)v4 + 33) = ____Global_new_V___Func_impl_no_alloc_V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__std__J__V_std__V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__2__std__YAPEAV___Func_impl_no_alloc_V___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__std__J__V_0___QEAV___Binder_U_Unforced_std__P8VmMigrationTcpTransport__EAAJPEAXV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__1__EPEAV3_AEAPEAXAEAV45_AEAV45__0__Z(&v29);
    *(_QWORD *)&v37 = v4;
    BYTE8(v37) = 0;
    LOBYTE(v38) = 0;
    __1__tuple_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__V12__std__QEAA_XZ(v30);
    future = std::packaged_task<long (void)>::get_future(&v37, v26);
    if ( &v34 != (__int128 *)future )
    {
      if ( (_QWORD)v34 )
        std::_Associated_state<int>::_Release();
      v6 = *(_QWORD *)future;
      *(_QWORD *)future = 0;
      *(_QWORD *)&v34 = v6;
      BYTE8(v34) = *(_BYTE *)(future + 8);
    }
    std::_State_manager<int>::~_State_manager<int>(v26);
    std::thread::_Start<std::packaged_task<long (void)>,>(v26, &v37);
    std::thread::detach((std::thread *)v26);
    std::thread::~thread((std::thread *)v26);
    std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(&v37);
  }
  Handles[0] = *((HANDLE *)this + 91);
  Handles[1] = *((HANDLE *)this + 73);
  Handles[2] = *((HANDLE *)this + 81);
  while ( 1 )
  {
    v7 = WaitForMultipleObjects(3u, Handles, 0, 0x7530u);
    if ( !v7 )
    {
      v13 = 2147500036LL;
      v14 = 1329;
      goto LABEL_37;
    }
    if ( v7 == 1 )
    {
      v15 = *((_DWORD *)this + 148);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x538,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)(unsigned int)v15,
          v24);
      goto LABEL_38;
    }
    if ( v7 != 2 )
      break;
    v25 = 0;
    if ( !(unsigned int)VmMigrationTcpTransport::LookupNextUnusedBuffer(this, &v25) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x543,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        v11);
    v12 = VmMigrationTcpTransport::PostReceiveBuffer(this, v25);
    if ( v12 < 0 )
    {
      v13 = (unsigned int)v12;
      v14 = 1358;
LABEL_37:
      v15 = wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)v14,
              (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
              (const char *)v13,
              v24);
      goto LABEL_38;
    }
  }
  if ( v7 == 258 )
  {
    v13 = 2147943860LL;
    v14 = 1363;
    goto LABEL_37;
  }
  v15 = -2147418113;
  if ( v7 == -1 )
  {
    LastError = wil::details::in1diag3::Log_GetLastError(retaddr, v8, v9, v10);
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_38:
  v17 = VmMigrationTcpTransport::FlushPendingReceives(this, 0x7530u);
  v18 = v17;
  if ( v17 >= 0 )
  {
    if ( (unsigned __int8)_is_valid___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEBA_NXZ(&v35) )
    {
      if ( (_QWORD)v35 )
        v20 = *(wil::details **)v35;
      else
        v20 = 0;
      wil::details::SetEvent(v20, v19);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 71) + 16LL))(*((_QWORD *)this + 71));
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x569,
      (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
      (const char *)(unsigned int)v17,
      v24);
    if ( v15 >= 0 )
      v15 = v18;
  }
  if ( a2 )
  {
    if ( v15 >= 0 )
      v28 = 0;
    else
      wil::details::lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e___::reset(v27);
    v21 = std::future<long>::get(&v34);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58B,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)(unsigned int)v21,
        v24);
      if ( v15 >= 0 )
        v15 = v22;
    }
  }
  wil::details::lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e___::reset(v27);
  std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(&v36);
  std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(&v35);
  std::_State_manager<int>::~_State_manager<int>(&v34);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140097680  mov     [rsp+arg_8], rbx
0x140097685  mov     [rsp+arg_10], rsi
0x14009768a  push    rdi
0x14009768b  push    r14
0x14009768d  push    r15
0x14009768f  sub     rsp, 100h
0x140097696  mov     rax, cs:__security_cookie
0x14009769d  xor     rax, rsp
0x1400976a0  mov     [rsp+118h+var_20], rax
0x1400976a8  mov     r14, rdx
0x1400976ab  mov     rdi, rcx
0x1400976ae  mov     rcx, [rsp+118h]; this
0x1400976b6  cmp     qword ptr [rdi+208h], 0FFFFFFFFFFFFFFFFh
0x1400976be  jnz     short loc_1400976D7
0x1400976c0  mov     r9d, 8007139Fh; char *
0x1400976c6  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400976cd  mov     edx, 4EEh; void *
0x1400976d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400976d7  mov     rcx, [rsp+118h]; this
0x1400976df  xor     r15d, r15d
0x1400976e2  cmp     [rdi+228h], r15d
0x1400976e9  jnz     short loc_140097702
0x1400976eb  mov     r9d, 8007139Fh; char *
0x1400976f1  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400976f8  mov     edx, 4EFh; void *
0x1400976fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140097702  mov     rcx, [rsp+118h]; this
0x14009770a  cmp     [rdi+240h], r15
0x140097711  jnz     short loc_14009772A
0x140097713  mov     r9d, 8007139Fh; char *
0x140097719  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097720  mov     edx, 4F0h; void *
0x140097725  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009772a  mov     rcx, [rsp+118h]; this
0x140097732  cmp     [rdi+238h], r15
0x140097739  jnz     short loc_140097752
0x14009773b  mov     r9d, 8007139Fh; char *
0x140097741  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097748  mov     edx, 4F1h; void *
0x14009774d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140097752  mov     rcx, [rsp+118h]; this
0x14009775a  cmp     [rdi+288h], r15
0x140097761  jnz     short loc_14009777A
0x140097763  mov     r9d, 8007139Fh; char *
0x140097769  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097770  mov     edx, 4FDh; void *
0x140097775  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009777a  mov     rcx, [rsp+118h]; this
0x140097782  cmp     [rdi+2D8h], r15
0x140097789  jnz     short loc_1400977A2
0x14009778b  mov     r9d, 8007139Fh; char *
0x140097791  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097798  mov     edx, 4FEh; void *
0x14009779d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400977a2  mov     rcx, [rsp+118h]; this
0x1400977aa  cmp     [rdi+248h], r15
0x1400977b1  jnz     short loc_1400977CA
0x1400977b3  mov     r9d, 8007139Fh; char *
0x1400977b9  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1400977c0  mov     edx, 4FFh; void *
0x1400977c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400977ca  xorps   xmm0, xmm0
0x1400977cd  movups  [rsp+118h+var_80], xmm0
0x1400977d5  mov     qword ptr [rsp+118h+var_80], r15
0x1400977dd  mov     byte ptr [rsp+118h+var_80+8], r15b
0x1400977e5  xorps   xmm1, xmm1
0x1400977e8  movdqu  [rsp+118h+var_70], xmm1
0x1400977f1  movdqu  [rsp+118h+var_60], xmm1
0x1400977fa  lea     rax, [rsp+118h+var_80]
0x140097802  mov     [rsp+118h+var_D0], rax
0x140097807  lea     rax, [rsp+118h+var_60]
0x14009780f  mov     [rsp+118h+var_C8], rax
0x140097814  mov     [rsp+118h+var_C0], 1
0x140097819  test    r14, r14
0x14009781c  jz      loc_14009799B
0x140097822  mov     edx, 1
0x140097827  lea     rcx, [rsp+118h+var_70]
0x14009782f  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140097834  mov     edx, 1
0x140097839  lea     rcx, [rsp+118h+var_60]
0x140097841  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140097846  xorps   xmm0, xmm0
0x140097849  xor     eax, eax
0x14009784b  movups  [rsp+118h+var_50], xmm0
0x140097853  mov     [rsp+118h+var_40], rax
0x14009785b  lea     rax, ?SendDuplexRepliesDuringAsyncSequence@VmMigrationTcpTransport@@IEAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@Z
0x140097862  mov     [rsp+118h+var_B8], rax
0x140097867  lea     rdx, [rsp+118h+var_60]
0x14009786f  lea     rcx, [rsp+118h+var_B0]
0x140097874  call    ??0?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(std::shared_ptr<MuxMigrationReply::IReplyProcessor> const &)
0x140097879  lea     rdx, [rsp+118h+var_70]
0x140097881  lea     rcx, [rsp+118h+var_A0]
0x140097886  call    ??0?$shared_ptr@VIReplyProcessor@MuxMigrationReply@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<MuxMigrationReply::IReplyProcessor>::shared_ptr<MuxMigrationReply::IReplyProcessor>(std::shared_ptr<MuxMigrationReply::IReplyProcessor> const &)
0x14009788b  mov     [rsp+118h+var_90], r14
0x140097893  mov     [rsp+118h+var_88], rdi
0x14009789b  mov     esi, 110h
0x1400978a0  mov     ecx, esi; Size
0x1400978a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400978a7  mov     rbx, rax
0x1400978aa  mov     [rsp+118h+var_E8], rax
0x1400978af  mov     r8d, esi; Size
0x1400978b2  xor     edx, edx; Val
0x1400978b4  mov     rcx, rax; void *
0x1400978b7  call    memset_0
0x1400978bc  mov     rcx, rbx
0x1400978bf  call    ??0?$_Associated_state@J@std@@QEAA@PEAU?$_Deleter_base@J@1@@Z; std::_Associated_state<long>::_Associated_state<long>(std::_Deleter_base<long> *)
0x1400978c4  nop
0x1400978c5  lea     rax, ??_7?$_Packaged_state@$$A6AJXZ@std@@6B@; const std::_Packaged_state<long (void)>::`vftable'
0x1400978cc  mov     [rbx], rax
0x1400978cf  lea     rsi, [rbx+0D0h]
0x1400978d6  mov     [rsp+118h+var_E0], rsi
0x1400978db  mov     [rsi+38h], r15
0x1400978df  lea     rcx, [rsp+118h+var_B8]
0x1400978e4  call    ??$_Global_new@V?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@std@@J$$V@std@@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@2@@std@@YAPEAV?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@std@@J$$V@0@$$QEAV?$_Binder@U_Unforced@std@@P8VmMigrationTcpTransport@@EAAJPEAXV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@1@_EPEAV3@AEAPEAXAEAV45@AEAV45@@0@@Z
0x1400978e9  mov     [rsi+38h], rax
0x1400978ed  mov     qword ptr [rsp+118h+var_50], rbx
0x1400978f5  mov     byte ptr [rsp+118h+var_50+8], r15b
0x1400978fd  mov     byte ptr [rsp+118h+var_40], r15b
0x140097905  lea     rcx, [rsp+118h+var_B0]; void *
0x14009790a  call    ??1?$tuple@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@V12@@std@@QEAA@XZ
0x14009790f  lea     rdx, [rsp+118h+var_E0]
0x140097914  lea     rcx, [rsp+118h+var_50]
0x14009791c  call    ?get_future@?$packaged_task@$$A6AJXZ@std@@QEAA?AV?$future@J@2@XZ; std::packaged_task<long (void)>::get_future(void)
0x140097921  mov     rbx, rax
0x140097924  lea     rax, [rsp+118h+var_80]
0x14009792c  cmp     rax, rbx
0x14009792f  jz      short loc_14009795B
0x140097931  mov     rcx, qword ptr [rsp+118h+var_80]
0x140097939  test    rcx, rcx
0x14009793c  jz      short loc_140097943
0x14009793e  call    ?_Release@?$_Associated_state@H@std@@QEAAXXZ; std::_Associated_state<int>::_Release(void)
0x140097943  mov     rax, [rbx]
0x140097946  mov     [rbx], r15
0x140097949  mov     qword ptr [rsp+118h+var_80], rax
0x140097951  mov     al, [rbx+8]
0x140097954  mov     byte ptr [rsp+118h+var_80+8], al
0x14009795b  lea     rcx, [rsp+118h+var_E0]
0x140097960  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x140097965  lea     rdx, [rsp+118h+var_50]
0x14009796d  lea     rcx, [rsp+118h+var_E0]
0x140097972  call    ??$_Start@V?$packaged_task@$$A6AJXZ@std@@$$V@thread@std@@AEAAX$$QEAV?$packaged_task@$$A6AJXZ@1@@Z; std::thread::_Start<std::packaged_task<long (void)>,>(std::packaged_task<long (void)> &&)
0x140097977  nop
0x140097978  lea     rcx, [rsp+118h+var_E0]; this
0x14009797d  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x140097982  nop
0x140097983  lea     rcx, [rsp+118h+var_E0]; this
0x140097988  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x14009798d  nop
0x14009798e  lea     rcx, [rsp+118h+var_50]
0x140097996  call    ??1?$packaged_task@$$A6AJV?$future@J@std@@0@Z@std@@QEAA@XZ; std::packaged_task<long (std::future<long>,std::future<long>)>::~packaged_task<long (std::future<long>,std::future<long>)>(void)
0x14009799b  mov     rax, [rdi+2D8h]
0x1400979a2  mov     [rsp+118h+Handles], rax
0x1400979aa  mov     rax, [rdi+248h]
0x1400979b1  mov     [rsp+118h+var_30], rax
0x1400979b9  mov     rax, [rdi+288h]
0x1400979c0  mov     [rsp+118h+var_28], rax
0x1400979c8  mov     esi, 7530h
0x1400979cd  mov     r9d, esi; dwMilliseconds
0x1400979d0  xor     r8d, r8d; bWaitAll
0x1400979d3  lea     rdx, [rsp+118h+Handles]; lpHandles
0x1400979db  lea     ecx, [r8+3]; nCount
0x1400979df  call    cs:__imp_WaitForMultipleObjects
0x1400979e6  nop     dword ptr [rax+rax+00h]
0x1400979eb  test    eax, eax
0x1400979ed  jz      loc_140097AB6
0x1400979f3  cmp     eax, 1
0x1400979f6  jz      loc_140097A8E
0x1400979fc  cmp     eax, 2
0x1400979ff  jnz     short loc_140097A52
0x140097a01  mov     [rsp+118h+var_E8], r15
0x140097a06  mov     rbx, [rsp+118h]
0x140097a0e  lea     rdx, [rsp+118h+var_E8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **
0x140097a13  mov     rcx, rdi; this
0x140097a16  call    ?LookupNextUnusedBuffer@VmMigrationTcpTransport@@IEAAHPEAPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::LookupNextUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *)
0x140097a1b  test    eax, eax
0x140097a1d  jz      short loc_140097A3D
0x140097a1f  mov     rdx, [rsp+118h+var_E8]; struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *
0x140097a24  mov     rcx, rdi; this
0x140097a27  call    ?PostReceiveBuffer@VmMigrationTcpTransport@@IEAAJPEAU_TRANSPORT_BUFFER@1@@Z; VmMigrationTcpTransport::PostReceiveBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER *)
0x140097a2c  test    eax, eax
0x140097a2e  jns     short loc_1400979CD
0x140097a30  mov     r9d, eax
0x140097a33  mov     edx, 54Eh
0x140097a38  jmp     loc_140097AC1
0x140097a3d  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097a44  mov     edx, 543h; void *
0x140097a49  mov     rcx, rbx; this
0x140097a4c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140097a52  cmp     eax, 102h
0x140097a57  jz      short loc_140097A81
0x140097a59  mov     ebx, 8000FFFFh
0x140097a5e  cmp     eax, 0FFFFFFFFh
0x140097a61  jnz     short loc_140097AD7
0x140097a63  mov     rcx, [rsp+118h]; this
0x140097a6b  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x140097a70  mov     ebx, eax
0x140097a72  test    eax, eax
0x140097a74  jle     short loc_140097AD7
0x140097a76  movzx   ebx, ax
0x140097a79  or      ebx, 80070000h
0x140097a7f  jmp     short loc_140097AD7
0x140097a81  mov     r9d, 800705B4h
0x140097a87  mov     edx, 553h
0x140097a8c  jmp     short loc_140097AC1
0x140097a8e  mov     ebx, [rdi+250h]
0x140097a94  mov     rcx, [rsp+118h]; this
0x140097a9c  test    ebx, ebx
0x140097a9e  jns     short loc_140097AD7
0x140097aa0  mov     r9d, ebx; char *
0x140097aa3  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097aaa  mov     edx, 538h; void *
0x140097aaf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140097ab4  jmp     short loc_140097AD7
0x140097ab6  mov     r9d, 80004004h; char *
0x140097abc  mov     edx, 531h; void *
0x140097ac1  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097ac8  mov     rcx, [rsp+118h]; this
0x140097ad0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140097ad5  mov     ebx, eax
0x140097ad7  mov     edx, esi; unsigned int
0x140097ad9  mov     rcx, rdi; this
0x140097adc  call    ?FlushPendingReceives@VmMigrationTcpTransport@@IEAAJK@Z; VmMigrationTcpTransport::FlushPendingReceives(ulong)
0x140097ae1  mov     esi, eax
0x140097ae3  mov     rcx, [rsp+118h]; this
0x140097aeb  test    eax, eax
0x140097aed  jns     short loc_140097B0B
0x140097aef  mov     r9d, eax; char *
0x140097af2  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097af9  mov     edx, 569h; void *
0x140097afe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140097b03  test    ebx, ebx
0x140097b05  js      short loc_140097B49
0x140097b07  mov     ebx, esi
0x140097b09  jmp     short loc_140097B49
0x140097b0b  lea     rcx, [rsp+118h+var_70]
0x140097b13  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEBA_NXZ
0x140097b18  test    al, al
0x140097b1a  jz      short loc_140097B36
0x140097b1c  mov     rax, qword ptr [rsp+118h+var_70]
0x140097b24  test    rax, rax
0x140097b27  jz      short loc_140097B2E
0x140097b29  mov     rcx, [rax]
0x140097b2c  jmp     short loc_140097B31
0x140097b2e  mov     rcx, r15; this
0x140097b31  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x140097b36  mov     rcx, [rdi+238h]
0x140097b3d  mov     rax, [rcx]
0x140097b40  mov     rax, [rax+10h]
0x140097b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140097b49  test    r14, r14
0x140097b4c  jz      short loc_140097B97
0x140097b4e  test    ebx, ebx
0x140097b50  jns     short loc_140097B5E
0x140097b52  lea     rcx, [rsp+118h+var_D0]
0x140097b57  call    wil__details__lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e_____reset
0x140097b5c  jmp     short loc_140097B63
0x140097b5e  mov     [rsp+118h+var_C0], r15b
0x140097b63  lea     rcx, [rsp+118h+var_80]
0x140097b6b  call    ?get@?$future@J@std@@QEAAJXZ; std::future<long>::get(void)
0x140097b70  mov     edi, eax
0x140097b72  mov     rcx, [rsp+118h]; this
0x140097b7a  test    eax, eax
0x140097b7c  jns     short loc_140097B97
0x140097b7e  mov     r9d, eax; char *
0x140097b81  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x140097b88  mov     edx, 58Bh; void *
0x140097b8d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140097b92  test    ebx, ebx
0x140097b94  cmovns  ebx, edi
0x140097b97  lea     rcx, [rsp+118h+var_D0]
0x140097b9c  call    wil__details__lambda_call__lambda_ac9bedc8f8020e36458987a4993f965e_____reset
0x140097ba1  nop
0x140097ba2  lea     rcx, [rsp+118h+var_60]; void *
0x140097baa  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x140097baf  nop
0x140097bb0  lea     rcx, [rsp+118h+var_70]; void *
0x140097bb8  call    ??1?$shared_ptr@VIMigrationTransferTransportAdapterSource@@@std@@QEAA@XZ; std::shared_ptr<IMigrationTransferTransportAdapterSource>::~shared_ptr<IMigrationTransferTransportAdapterSource>(void)
0x140097bbd  nop
0x140097bbe  lea     rcx, [rsp+118h+var_80]
0x140097bc6  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x140097bcb  mov     eax, ebx
0x140097bcd  jmp     short loc_140097BD3
0x140097bcf  mov     eax, dword ptr [rsp+118h+var_E8]
0x140097bd3  mov     rcx, [rsp+118h+var_20]
0x140097bdb  xor     rcx, rsp; StackCookie
0x140097bde  call    __security_check_cookie
0x140097be3  lea     r11, [rsp+118h+var_18]
0x140097beb  mov     rbx, [r11+28h]
0x140097bef  mov     rsi, [r11+30h]
0x140097bf3  mov     rsp, r11
0x140097bf6  pop     r15
0x140097bf8  pop     r14
0x140097bfa  pop     rdi
0x140097bfb  retn
```
