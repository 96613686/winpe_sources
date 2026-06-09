# Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ProcessEvents(void)

- ea: `0x180010d80`
- end: `0x18001127c`
- name: `?ProcessEvents@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `1276`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd44`

## callees

- `0x180004060`
- `0x180004bd8`
- `0x18000ab4c`
- `0x18000de78`
- `0x18000ed44`
- `0x18000ed7c`
- `0x18000f374`
- `0x18000fa2c`
- `0x180010d80`
- `0x1800120e8`
- `0x1800123b8`
- `0x180012480`
- `0x180012554`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180010fe6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180010fe6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010de1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011006`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001111a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010de1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011006`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001111a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011010`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010dc7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180010dc7`

## string_xrefs

- `0x180010ff1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ProcessEvents(HANDLE *this)
{
  RTL_SRWLOCK *v2; // rdi
  DWORD v3; // eax
  int v4; // edx
  int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rsi
  std::_Ref_count_base *v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // edx
  int v13; // r8d
  RTL_SRWLOCK *v14; // rbx
  __int64 v15; // rcx
  DWORD LastError; // eax
  PVOID *v17; // rdx
  _UNKNOWN **v18; // r8
  __int64 v19; // rcx
  _QWORD **v20; // rsi
  _QWORD *v21; // rdi
  _QWORD *v22; // rbx
  int v23; // esi
  int v24; // edx
  std::_Ref_count_base *v25; // rcx
  int v26; // r8d
  _QWORD *v27; // rdi
  char v28; // r15
  __int16 v29; // r12
  int v30; // [rsp+28h] [rbp-58h]
  __int64 v31[2]; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v33; // [rsp+70h] [rbp-10h] BYREF
  std::_Ref_count_base *v34; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  RTL_SRWLOCK *v36; // [rsp+C0h] [rbp+40h] BYREF
  RTL_SRWLOCK *v37; // [rsp+C8h] [rbp+48h] BYREF

  Handles[0] = this[7];
  Handles[1] = this[8];
  v2 = (RTL_SRWLOCK *)(this + 9);
  while ( 1 )
  {
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !v3 )
      break;
    if ( v3 != 1 )
    {
      AcquireSRWLockExclusive(v2);
      v36 = v2;
      LastError = GetLastError();
      *((_DWORD *)this + 25) = LastError;
      v17 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || (LOBYTE(v17) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        LOBYTE(v17) = 0;
      }
      v18 = &WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_AvrcpTransportChannelq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (int)v17,
          (int)v18,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          2,
          v30,
          26,
          &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
          LastError,
          (char)this);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v36);
      goto LABEL_53;
    }
    while ( 1 )
    {
      AcquireSRWLockExclusive(v2);
      v37 = v2;
      if ( !this[8] )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xAFB,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v6);
      v36 = (RTL_SRWLOCK *)this[8];
      if ( !this[11] )
        break;
      v7 = *(_QWORD *)this[10];
      v8 = *(_QWORD *)(v7 + 16);
      v9 = *(std::_Ref_count_base **)(v7 + 24);
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 24) = 0;
      v10 = *(_QWORD *)this[10];
      v11 = *(_QWORD *)v10;
      this[11] = (char *)this[11] - 1;
      **(_QWORD **)(v10 + 8) = v11;
      *(_QWORD *)(v11 + 8) = *(_QWORD *)(v10 + 8);
      std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>>>(
        v11,
        (_QWORD *)v10);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ResetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v37);
      v14 = 0;
      v36 = 0;
      if ( *(_BYTE *)(v8 + 96) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || (LOBYTE(v12) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
        {
          LOBYTE(v12) = 0;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v13) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
        {
          LOBYTE(v13) = 0;
        }
        if ( (_BYTE)v12 || (_BYTE)v13 )
          WPP_RECORDER_AND_TRACE_SF__guid_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            5,
            1,
            25,
            &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
            v8,
            (char)this);
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || (LOBYTE(v12) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
        {
          LOBYTE(v12) = 0;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v13) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
        {
          LOBYTE(v13) = 0;
        }
        if ( (_BYTE)v12 || (_BYTE)v13 )
          WPP_RECORDER_AND_TRACE_SF__guid_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            5,
            1,
            24,
            &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
            v8,
            (char)this);
        v15 = *(_QWORD *)(v8 + 72);
        if ( !v15 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        HIDWORD(v36) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        LOBYTE(v36) = 1;
        v14 = v36;
      }
      std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(
        v8 + 80,
        &v33);
      if ( v33 )
        (*(void (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v33 + 40LL))(v33, v14);
      if ( v34 )
        std::_Ref_count_base::_Decref(v34);
      if ( v9 )
        std::_Ref_count_base::_Decref(v9);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ResetEvent_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v37);
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (LOBYTE(v4) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
  {
    LOBYTE(v4) = 0;
  }
  if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      v5,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      4,
      1,
      23,
      &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
      (char)this);
  }
LABEL_53:
  std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>>::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>>(v31);
  AcquireSRWLockExclusive(v2);
  v36 = v2;
  v20 = (_QWORD **)(this + 10);
  if ( v31 == (__int64 *)(this + 10) )
  {
    v22 = (_QWORD *)v31[0];
  }
  else
  {
    v21 = (_QWORD *)v31[0];
    std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>>>(
      v19,
      v31[0]);
    *v21 = v21;
    v21[1] = v21;
    v22 = *v20;
    *v20 = v21;
    this[11] = 0;
  }
  v23 = *((_DWORD *)this + 25);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v36);
  v27 = (_QWORD *)*v22;
  v28 = BYTE3(v36);
  v29 = *(_WORD *)((char *)&v36 + 1);
  while ( v27 != v22 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || (LOBYTE(v24) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
    {
      LOBYTE(v24) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v26) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
    {
      LOBYTE(v26) = 0;
    }
    if ( (_BYTE)v24 || (_BYTE)v26 )
      WPP_RECORDER_AND_TRACE_SF__guid_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        v26,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        5,
        1,
        27,
        &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
        v27[2],
        (char)this);
    std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(
      v27[2] + 80LL,
      &v33);
    if ( v33 )
    {
      LOBYTE(v36) = 0;
      *(_WORD *)((char *)&v36 + 1) = v29;
      BYTE3(v36) = v28;
      HIDWORD(v36) = v23;
      (*(void (__fastcall **)(__int64, RTL_SRWLOCK *))(*(_QWORD *)v33 + 40LL))(v33, v36);
    }
    v25 = v34;
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    v27 = (_QWORD *)*v27;
  }
  std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>>>(
    (__int64)v25,
    (__int64)v22);
  std::_Deallocate<16>(v22, (struct std::nothrow_t *)0x20);
}

```

## disassembly

```asm
0x180010d80  mov     [rsp-38h+arg_10], rbx
0x180010d85  push    rbp
0x180010d86  push    rsi
0x180010d87  push    rdi
0x180010d88  push    r12
0x180010d8a  push    r13
0x180010d8c  push    r14
0x180010d8e  push    r15
0x180010d90  mov     rbp, rsp
0x180010d93  sub     rsp, 80h
0x180010d9a  mov     r14, rcx
0x180010d9d  mov     rax, [rcx+38h]
0x180010da1  mov     [rbp+Handles], rax
0x180010da5  mov     rax, [rcx+40h]
0x180010da9  mov     [rbp+var_18], rax
0x180010dad  lea     rdi, [rcx+48h]
0x180010db1  xor     r13d, r13d
0x180010db4  lea     r12d, [r13+1]
0x180010db8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180010dbc  xor     r8d, r8d; bWaitAll
0x180010dbf  lea     rdx, [rbp+Handles]; lpHandles
0x180010dc3  lea     ecx, [r8+2]; nCount
0x180010dc7  call    cs:__imp_WaitForMultipleObjects
0x180010dcd  test    eax, eax
0x180010dcf  jz      loc_18001109F
0x180010dd5  cmp     eax, r12d
0x180010dd8  jnz     loc_180011003
0x180010dde  mov     rcx, rdi; SRWLock
0x180010de1  call    cs:__imp_AcquireSRWLockExclusive
0x180010de7  mov     [rbp+arg_8], rdi
0x180010deb  mov     rax, [r14+40h]
0x180010def  test    rax, rax
0x180010df2  jz      loc_180010FED
0x180010df8  mov     [rbp+arg_0], rax
0x180010dfc  cmp     [r14+58h], r13
0x180010e00  jz      loc_180010FCF
0x180010e06  mov     rax, [r14+50h]
0x180010e0a  mov     rcx, [rax]
0x180010e0d  mov     rsi, [rcx+10h]
0x180010e11  mov     r15, [rcx+18h]
0x180010e15  mov     [rcx+10h], r13
0x180010e19  mov     [rcx+18h], r13
0x180010e1d  mov     rax, [r14+50h]
0x180010e21  mov     rdx, [rax]
0x180010e24  mov     rcx, [rdx]
0x180010e27  dec     qword ptr [r14+58h]
0x180010e2b  mov     rax, [rdx+8]
0x180010e2f  mov     [rax], rcx
0x180010e32  mov     rax, [rdx+8]
0x180010e36  mov     [rcx+8], rax
0x180010e3a  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>::_Freenode<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>> &,std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *> *)
0x180010e3f  lea     rcx, [rbp+arg_0]
0x180010e43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ResetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010e48  lea     rcx, [rbp+arg_8]
0x180010e4c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010e51  mov     rbx, r13
0x180010e54  mov     [rbp+arg_0], rbx
0x180010e58  cmp     [rsi+60h], r13b
0x180010e5c  jnz     loc_180010F07
0x180010e62  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e69  lea     rax, WPP_GLOBAL_Control
0x180010e70  cmp     rcx, rax
0x180010e73  jz      short loc_180010E84
0x180010e75  test    [rcx+1Ch], r12b
0x180010e79  jz      short loc_180010E84
0x180010e7b  cmp     byte ptr [rcx+19h], 5
0x180010e7f  mov     dl, r12b
0x180010e82  jnb     short loc_180010E87
0x180010e84  mov     dl, r13b; int
0x180010e87  lea     rax, WPP_RECORDER_INITIALIZED
0x180010e8e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180010e95  jz      short loc_180010EA1
0x180010e97  cmp     [rcx+30h], r13w
0x180010e9c  mov     r8b, r12b
0x180010e9f  jnz     short loc_180010EA4
0x180010ea1  mov     r8b, r13b; int
0x180010ea4  test    dl, dl
0x180010ea6  jnz     short loc_180010EAD
0x180010ea8  test    r8b, r8b
0x180010eab  jz      short loc_180010EE1
0x180010ead  mov     qword ptr [rsp+80h+var_38], r14; char
0x180010eb2  mov     qword ptr [rsp+80h+var_40], rsi; __int64
0x180010eb7  lea     r9, WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids
0x180010ebe  mov     [rsp+80h+MessageGuid], r9; MessageGuid
0x180010ec3  mov     [rsp+80h+var_50], 18h; __int16
0x180010eca  mov     [rsp+80h+var_58], r12d; int
0x180010ecf  mov     [rsp+80h+var_60], 5; char
0x180010ed4  mov     r9, [rcx+28h]; int
0x180010ed8  mov     rcx, [rcx+10h]; int
0x180010edc  call    WPP_RECORDER_AND_TRACE_SF__guid_q
0x180010ee1  mov     rcx, [rsi+48h]
0x180010ee5  test    rcx, rcx
0x180010ee8  jz      loc_180010FE6
0x180010eee  mov     rax, [rcx]
0x180010ef1  mov     rax, [rax+10h]
0x180010ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efa  mov     dword ptr [rbp+arg_0+4], eax
0x180010efd  mov     byte ptr [rbp+arg_0], r12b
0x180010f01  mov     rbx, [rbp+arg_0]
0x180010f05  jmp     short loc_180010F86
0x180010f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f0e  lea     rax, WPP_GLOBAL_Control
0x180010f15  cmp     rcx, rax
0x180010f18  jz      short loc_180010F29
0x180010f1a  test    [rcx+1Ch], r12b
0x180010f1e  jz      short loc_180010F29
0x180010f20  cmp     byte ptr [rcx+19h], 5
0x180010f24  mov     dl, r12b
0x180010f27  jnb     short loc_180010F2C
0x180010f29  mov     dl, r13b; int
0x180010f2c  lea     rax, WPP_RECORDER_INITIALIZED
0x180010f33  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180010f3a  jz      short loc_180010F46
0x180010f3c  cmp     [rcx+30h], r13w
0x180010f41  mov     r8b, r12b
0x180010f44  jnz     short loc_180010F49
0x180010f46  mov     r8b, r13b; int
0x180010f49  test    dl, dl
0x180010f4b  jnz     short loc_180010F52
0x180010f4d  test    r8b, r8b
0x180010f50  jz      short loc_180010F86
0x180010f52  mov     qword ptr [rsp+80h+var_38], r14; char
0x180010f57  mov     qword ptr [rsp+80h+var_40], rsi; __int64
0x180010f5c  lea     r9, WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids
0x180010f63  mov     [rsp+80h+MessageGuid], r9; MessageGuid
0x180010f68  mov     [rsp+80h+var_50], 19h; __int16
0x180010f6f  mov     [rsp+80h+var_58], r12d; int
0x180010f74  mov     [rsp+80h+var_60], 5; char
0x180010f79  mov     r9, [rcx+28h]; int
0x180010f7d  mov     rcx, [rcx+10h]; int
0x180010f81  call    WPP_RECORDER_AND_TRACE_SF__guid_q
0x180010f86  lea     rcx, [rsi+50h]
0x180010f8a  lea     rdx, [rbp+var_10]
0x180010f8e  call    ?lock@?$weak_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEBA?AV?$shared_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@2@XZ; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(void)
0x180010f93  mov     rcx, [rbp+var_10]
0x180010f97  test    rcx, rcx
0x180010f9a  jz      short loc_180010FAB
0x180010f9c  mov     rax, [rcx]
0x180010f9f  mov     rdx, rbx
0x180010fa2  mov     rax, [rax+28h]
0x180010fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fab  mov     rcx, [rbp+var_8]; this
0x180010faf  test    rcx, rcx
0x180010fb2  jz      short loc_180010FB9
0x180010fb4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010fb9  test    r15, r15
0x180010fbc  jz      loc_180010DDE
0x180010fc2  mov     rcx, r15; this
0x180010fc5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010fca  jmp     loc_180010DDE
0x180010fcf  lea     rcx, [rbp+arg_0]
0x180010fd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ResetEvent@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010fd8  lea     rcx, [rbp+arg_8]
0x180010fdc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010fe1  jmp     loc_180010DB8
0x180010fe6  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180010fec  int     3; Trap to Debugger
0x180010fed  mov     rcx, [rbp+38h]; this
0x180010ff1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010ff8  mov     edx, 0AFBh; void *
0x180010ffd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180011003  mov     rcx, rdi; SRWLock
0x180011006  call    cs:__imp_AcquireSRWLockExclusive
0x18001100c  mov     [rbp+arg_0], rdi
0x180011010  call    cs:__imp_GetLastError
0x180011016  mov     [r14+64h], eax
0x18001101a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011021  lea     rdx, WPP_GLOBAL_Control
0x180011028  cmp     rcx, rdx
0x18001102b  jz      short loc_18001103C
0x18001102d  test    [rcx+1Ch], r12b
0x180011031  jz      short loc_18001103C
0x180011033  cmp     byte ptr [rcx+19h], 2
0x180011037  mov     dl, r12b
0x18001103a  jnb     short loc_18001103F
0x18001103c  mov     dl, r13b; int
0x18001103f  lea     r8, WPP_RECORDER_INITIALIZED
0x180011046  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001104d  setnz   r8b; int
0x180011051  test    dl, dl
0x180011053  jnz     short loc_18001105A
0x180011055  test    r8b, r8b
0x180011058  jz      short loc_180011094
0x18001105a  test    eax, eax
0x18001105c  jle     short loc_180011066
0x18001105e  movzx   eax, ax
0x180011061  or      eax, 80070000h
0x180011066  mov     qword ptr [rsp+80h+var_38], r14; char
0x18001106b  mov     dword ptr [rsp+80h+var_40], eax; char
0x18001106f  lea     rax, WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids
0x180011076  mov     [rsp+80h+MessageGuid], rax; MessageGuid
0x18001107b  mov     [rsp+80h+var_50], 1Ah; __int16
0x180011082  mov     [rsp+80h+var_60], 2; char
0x180011087  mov     r9, [rcx+28h]; int
0x18001108b  mov     rcx, [rcx+10h]; int
0x18001108f  call    WPP_RECORDER_AND_TRACE_SF_AvrcpTransportChannelq
0x180011094  lea     rcx, [rbp+arg_0]
0x180011098  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001109d  jmp     short loc_18001110E
0x18001109f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110a6  lea     rax, WPP_GLOBAL_Control
0x1800110ad  cmp     rcx, rax
0x1800110b0  jz      short loc_1800110C1
0x1800110b2  test    [rcx+1Ch], r12b
0x1800110b6  jz      short loc_1800110C1
0x1800110b8  cmp     byte ptr [rcx+19h], 4
0x1800110bc  mov     dl, r12b
0x1800110bf  jnb     short loc_1800110C4
0x1800110c1  mov     dl, r13b; int
0x1800110c4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800110cb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800110d2  setnz   r8b; int
0x1800110d6  test    dl, dl
0x1800110d8  jnz     short loc_1800110DF
0x1800110da  test    r8b, r8b
0x1800110dd  jz      short loc_18001110E
0x1800110df  mov     qword ptr [rsp+80h+var_40], r14; char
0x1800110e4  lea     r9, WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids
0x1800110eb  mov     [rsp+80h+MessageGuid], r9; MessageGuid
0x1800110f0  mov     [rsp+80h+var_50], 17h; __int16
0x1800110f7  mov     [rsp+80h+var_58], r12d; int
0x1800110fc  mov     [rsp+80h+var_60], 4; char
0x180011101  mov     r9, [rcx+28h]; int
0x180011105  mov     rcx, [rcx+10h]; int
0x180011109  call    WPP_RECORDER_AND_TRACE_SF_q
0x18001110e  lea     rcx, [rbp+var_30]
0x180011112  call    ??0?$list@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@V?$allocator@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>>::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>>(void)
0x180011117  mov     rcx, rdi; SRWLock
0x18001111a  call    cs:__imp_AcquireSRWLockExclusive
0x180011120  mov     [rbp+arg_0], rdi
0x180011124  lea     rsi, [r14+50h]
0x180011128  lea     rax, [rbp+var_30]
0x18001112c  cmp     rax, rsi
0x18001112f  jz      short loc_180011150
0x180011131  mov     rdi, [rbp+var_30]
0x180011135  mov     rdx, rdi
0x180011138  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *>> &,std::_List_node<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>,void *> *)
0x18001113d  mov     [rdi], rdi
0x180011140  mov     [rdi+8], rdi
0x180011144  mov     rbx, [rsi]
0x180011147  mov     [rsi], rdi
0x18001114a  mov     [rsi+8], r13
0x18001114e  jmp     short loc_180011154
0x180011150  mov     rbx, [rbp+var_30]
0x180011154  mov     esi, [r14+64h]
0x180011158  lea     rcx, [rbp+arg_0]
0x18001115c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011161  mov     rdi, [rbx]
0x180011164  mov     r15b, byte ptr [rbp+arg_0+3]
0x180011168  movzx   r12d, word ptr [rbp+arg_0+1]
0x18001116d  cmp     rdi, rbx
0x180011170  jz      loc_18001124B
0x180011176  mov     rcx, cs:WPP_GLOBAL_Control
0x18001117d  lea     rax, WPP_GLOBAL_Control
0x180011184  cmp     rcx, rax
0x180011187  jz      short loc_180011197
0x180011189  test    byte ptr [rcx+1Ch], 1
0x18001118d  jz      short loc_180011197
0x18001118f  cmp     byte ptr [rcx+19h], 5
0x180011193  mov     dl, 1
0x180011195  jnb     short loc_18001119A
0x180011197  mov     dl, r13b; int
0x18001119a  lea     rax, WPP_RECORDER_INITIALIZED
0x1800111a1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800111a8  jz      short loc_1800111B4
0x1800111aa  cmp     [rcx+30h], r13w
0x1800111af  mov     r8b, 1
0x1800111b2  jnz     short loc_1800111B7
0x1800111b4  mov     r8b, r13b; int
0x1800111b7  test    dl, dl
0x1800111b9  jnz     short loc_1800111C0
0x1800111bb  test    r8b, r8b
0x1800111be  jz      short loc_1800111FB
0x1800111c0  mov     qword ptr [rsp+80h+var_38], r14; char
0x1800111c5  mov     rax, [rdi+10h]
0x1800111c9  mov     qword ptr [rsp+80h+var_40], rax; __int64
0x1800111ce  lea     rax, WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids
0x1800111d5  mov     [rsp+80h+MessageGuid], rax; MessageGuid
0x1800111da  mov     [rsp+80h+var_50], 1Bh; __int16
0x1800111e1  mov     [rsp+80h+var_58], 1; int
0x1800111e9  mov     [rsp+80h+var_60], 5; char
0x1800111ee  mov     r9, [rcx+28h]; int
0x1800111f2  mov     rcx, [rcx+10h]; int
0x1800111f6  call    WPP_RECORDER_AND_TRACE_SF__guid_q
0x1800111fb  mov     rcx, [rdi+10h]
0x1800111ff  add     rcx, 50h ; 'P'
0x180011203  lea     rdx, [rbp+var_10]
0x180011207  call    ?lock@?$weak_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@QEBA?AV?$shared_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@2@XZ; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>>::lock(void)
0x18001120c  mov     rcx, [rbp+var_10]
0x180011210  test    rcx, rcx
0x180011213  jz      short loc_180011235
0x180011215  mov     byte ptr [rbp+arg_0], r13b
0x180011219  mov     word ptr [rbp+arg_0+1], r12w
0x18001121e  mov     byte ptr [rbp+arg_0+3], r15b
0x180011222  mov     dword ptr [rbp+arg_0+4], esi
0x180011225  mov     rax, [rcx]
0x180011228  mov     rdx, [rbp+arg_0]
0x18001122c  mov     rax, [rax+28h]
0x180011230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011235  mov     rcx, [rbp+var_8]; this
  ... truncated ...
```
