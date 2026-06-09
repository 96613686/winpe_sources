# _RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1_::operator()

- ea: `0x1800a54d8`
- end: `0x1800a59cd`
- name: `_RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1_::operator()`
- size: `1269`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a9550`

## callees

- `0x1800040e8`
- `0x180026e68`
- `0x1800279a0`
- `0x18003a08c`
- `0x180044b1c`
- `0x18004f89c`
- `0x18005aa6c`
- `0x18006db98`
- `0x18007103c`
- `0x180084f50`
- `0x180090c14`
- `0x180092970`
- `0x1800a29a4`
- `0x1800a54d8`
- `0x1800a7830`
- `0x1800a7e5c`
- `0x1800a8c40`
- `0x1800b7b14`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800a581a`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800a581a`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800a57df`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800a57df`

## string_xrefs

- `0x1800a5551`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a55d5`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a5605`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a582c`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a585d`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a5899`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`
- `0x1800a58d5`: `onecoreuap\net\wcm\service\base\server\routepolicyondemand.cpp`

## pseudocode

```c
unsigned int __fastcall RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  _QWORD **v4; // rsi
  struct RoutePolicyOnDemand::InterfaceInfo ***v5; // rdx
  struct RoutePolicyOnDemand::InterfaceInfo **v6; // r14
  __int64 v7; // r9
  __int64 v8; // rdx
  struct RoutePolicyOnDemand::InterfaceInfo **v10; // rcx
  struct RoutePolicyOnDemand::InterfaceInfo **v11; // r8
  struct RoutePolicyOnDemand::InterfaceInfo *v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int128 *v15; // r12
  const char *v16; // r9
  struct Request **i; // rdi
  struct Request *v18; // rcx
  __int128 v19; // xmm0
  RoutePolicyOnDemand *v20; // rcx
  PVOID *k; // r8
  unsigned int v22; // eax
  signed int v23; // r15d
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned int v26; // eax
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  __int64 v30; // r8
  __int64 v31; // r9
  struct Request **j; // rdi
  struct RoutePolicyOnDemand::InterfaceInfo *v33; // rax
  struct Request *v34; // rcx
  __int128 v35; // xmm0
  unsigned int v36; // [rsp+20h] [rbp-49h]
  unsigned int v37; // [rsp+20h] [rbp-49h]
  _QWORD v38[2]; // [rsp+40h] [rbp-29h] BYREF
  struct _GUID v39; // [rsp+50h] [rbp-19h] BYREF
  _DWORD v40[2]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v41; // [rsp+68h] [rbp-1h]
  unsigned int v42; // [rsp+78h] [rbp+Fh] BYREF
  int v43; // [rsp+7Ch] [rbp+13h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = (_QWORD **)a1;
  v5 = *(struct RoutePolicyOnDemand::InterfaceInfo ****)a1;
  v6 = **(struct RoutePolicyOnDemand::InterfaceInfo ****)a1;
  if ( v6 == *(struct RoutePolicyOnDemand::InterfaceInfo ***)(*(_QWORD *)a1 + 8LL) )
  {
LABEL_5:
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v42 = *((_DWORD *)v4 + 6);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        a1,
        (unsigned int)&dword_180118A04,
        a3,
        a4,
        (__int64)&v42);
    }
    v7 = 1168;
    v8 = 966;
    return wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)v8,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
             (const char *)v7,
             v36);
  }
  LODWORD(a1) = *(_DWORD *)(a1 + 24);
  while ( *((_DWORD *)*v6 + 24) != (_DWORD)a1 )
  {
    v6 += 2;
    if ( v6 == v5[1] )
      goto LABEL_5;
  }
  v10 = v5[3];
  v11 = v5[4];
  if ( v10 == v11 )
  {
LABEL_13:
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v42 = *((_DWORD *)v4 + 6);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)&byte_180118A7F,
        (_DWORD)v11,
        a4,
        (__int64)&v42);
    }
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x3D5,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      (const char *)0x4C7,
      v36);
    v43 = 0;
    v14 = CspManager::ReleaseConnection(v13, v4 + 1, &v43);
    if ( v14 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x3D9,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)v14,
        v37);
    std::vector<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>::erase(*v4, &v39, v6);
    return std::_Erase_remove_if_std::vector_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect____std::allocator_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect__________RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1_::operator()_::_2_::_lambda_6___(
             *v4 + 6,
             v6);
  }
  v12 = *v6;
  while ( *((struct RoutePolicyOnDemand::InterfaceInfo **)*v10 + 14) != v12 )
  {
    v10 += 2;
    if ( v10 == v11 )
      goto LABEL_13;
  }
  if ( *((_BYTE *)v12 + 120) )
  {
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v43 = *((_DWORD *)v4 + 6);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)byte_1801188ED,
        (_DWORD)v11,
        a4,
        (__int64)&v43);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v12);
    v7 = 1247;
    v8 = 1002;
    return wil::details::in1diag3::Log_Win32(
             retaddr,
             (void *)v8,
             (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
             (const char *)v7,
             v36);
  }
  if ( (unsigned int)dword_18013A120 <= 4 )
  {
    v15 = (__int128 *)(v4 + 1);
  }
  else
  {
    v38[0] = (char *)v4 + 36;
    v15 = (__int128 *)(v4 + 1);
    *(_QWORD *)&v39.Data1 = v4 + 1;
    v43 = *((_DWORD *)v4 + 8);
    v42 = *((_DWORD *)v4 + 6);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
      (_DWORD)v10,
      (unsigned int)&byte_180118967,
      (_DWORD)v11,
      a4,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v39,
      (__int64)v38);
  }
  v16 = (const char *)*((unsigned int *)v4 + 8);
  if ( (_DWORD)v16 == -1073479642 )
  {
    for ( i = (struct Request **)(*v4)[3]; i != (struct Request **)(*v4)[4]; i += 2 )
    {
      v18 = *i;
      if ( *((struct RoutePolicyOnDemand::InterfaceInfo **)*i + 14) == *v6 )
      {
        if ( *((_QWORD *)v18 + 16) )
        {
          if ( (unsigned int)dword_18013A120 > 4 )
          {
            *(_QWORD *)&v39.Data1 = *i;
            v38[0] = v4 + 1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
              (_DWORD)v18,
              (unsigned int)&dword_1801187CC,
              (_DWORD)v11,
              (_DWORD)v16,
              (__int64)v38,
              (__int64)&v39);
          }
          RoutePolicyOnDemand::CompleteRequest((RoutePolicyOnDemand *)*v4, *i, -2147023727, 0);
        }
        std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::reset((char *)*i + 112);
      }
    }
    std::vector<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>::erase(*v4, &v39, v6);
    return std::_Erase_remove_if_std::vector_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect____std::allocator_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect__________RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1_::operator()_::_2_::_lambda_6___(
             *v4 + 6,
             v6);
  }
  if ( !(_DWORD)v16 )
  {
    v19 = *v15;
LABEL_45:
    *((_OWORD *)*v6 + 2) = v19;
    v22 = ConvertInterfaceGuidToLuid((const GUID *)*v6 + 2, (PNET_LUID)*v6 + 3);
    v23 = v22;
    if ( v22 )
    {
      v24 = 1084;
    }
    else
    {
      v22 = ConvertInterfaceLuidToIndex((const NET_LUID *)*v6 + 3, (PNET_IFINDEX)*v6 + 4);
      v23 = v22;
      if ( !v22 )
      {
        v29 = RoutePolicyOnDemand::HandleL2Connected((RoutePolicyOnDemand *)*v4, *v6);
        v23 = v29;
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x442,
            (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
            (const char *)(unsigned int)v29,
            v36);
        if ( !v23 )
        {
          *((_BYTE *)*v6 + 120) = 1;
          LOBYTE(v31) = 1;
          LOBYTE(v30) = 1;
          return RouteManager::SetL2Connected((char *)*v6 + 32, 3, v30, v31);
        }
        goto LABEL_51;
      }
      v24 = 1087;
    }
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      (const char *)v22,
      v36);
LABEL_51:
    v42 = 0;
    v26 = CspManager::ReleaseConnection(v25, v15, &v42);
    if ( v26 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x44E,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
        (const char *)v26,
        v36);
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    goto LABEL_60;
  }
  if ( (_DWORD)v16 != -1073479646 )
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x433,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\routepolicyondemand.cpp",
      v16,
      v36);
    v23 = -2147024831;
LABEL_60:
    for ( j = (struct Request **)(*v4)[3]; ; j += 2 )
    {
      v33 = *v6;
      if ( j == (struct Request **)(*v4)[4] )
        break;
      v34 = *j;
      if ( *((struct RoutePolicyOnDemand::InterfaceInfo **)*j + 14) == v33 )
      {
        if ( *((_QWORD *)v34 + 16) )
        {
          if ( (unsigned int)dword_18013A120 > 4 )
          {
            *(_QWORD *)&v39.Data1 = *j;
            v38[0] = v15;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
              (_DWORD)v34,
              (unsigned int)byte_18011886D,
              v27,
              v28,
              (__int64)v38,
              (__int64)&v39);
          }
          RoutePolicyOnDemand::CompleteRequest((RoutePolicyOnDemand *)*v4, *j, v23, 0);
        }
        std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::reset((char *)*j + 112);
      }
    }
    v35 = *(_OWORD *)v33;
    v40[0] = 4;
    v40[1] = 1;
    v41 = v35;
    v39 = GUID_NULL;
    NetworkingTriageScenario::OnDemand::OnDemandConnectionCanceledAction(
      (const struct NetworkingTriageScenario::OnDemand::RequiredFields *)v40,
      "ConnectionFailed",
      &v39,
      0,
      0);
    std::vector<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>::erase(*v4, &v39, v6);
    return std::_Erase_remove_if_std::vector_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect____std::allocator_std::unique_ptr_RoutePolicyOnDemand::Disconnect_std::default_delete_RoutePolicyOnDemand::Disconnect__________RoutePolicyOnDemand::HandleConnectionCompleteNotificationInternal_::_3_::_lambda_1_::operator()_::_2_::_lambda_6___(
             *v4 + 6,
             v6);
  }
  v20 = (RoutePolicyOnDemand *)*v4;
  for ( k = (PVOID *)**v4; ; k += 2 )
  {
    if ( k == *((PVOID **)v20 + 1) )
    {
      v19 = *(_OWORD *)((char *)v4 + 36);
      goto LABEL_45;
    }
    if ( *((_QWORD **)*k + 4) == *(_QWORD **)((char *)v4 + 36) && *((_QWORD **)*k + 5) == *(_QWORD **)((char *)v4 + 44) )
      break;
  }
  RoutePolicyOnDemand::UpdateRequestsWithExistingSession(v20, v6, k, -1073479646);
  return std::vector<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>::erase(*v4, &v39, v6);
}

```

## disassembly

```asm
0x1800a54d8  push    rbp
0x1800a54da  push    rsi
0x1800a54db  push    rdi
0x1800a54dc  push    r12
0x1800a54de  push    r14
0x1800a54e0  push    r15
0x1800a54e2  lea     rbp, [rsp-2Fh]
0x1800a54e7  sub     rsp, 98h
0x1800a54ee  mov     rax, cs:__security_cookie
0x1800a54f5  xor     rax, rsp
0x1800a54f8  mov     [rbp+57h+var_40], rax
0x1800a54fc  mov     rsi, rcx
0x1800a54ff  mov     rdx, [rcx]
0x1800a5502  mov     r14, [rdx]
0x1800a5505  cmp     r14, [rdx+8]
0x1800a5509  jz      short loc_1800A5520
0x1800a550b  mov     ecx, [rcx+18h]
0x1800a550e  mov     rax, [r14]
0x1800a5511  cmp     [rax+60h], ecx
0x1800a5514  jz      short loc_1800A557F
0x1800a5516  add     r14, 10h
0x1800a551a  cmp     r14, [rdx+8]
0x1800a551e  jnz     short loc_1800A550E
0x1800a5520  mov     eax, cs:dword_18013A120
0x1800a5526  cmp     eax, 5
0x1800a5529  jbe     short loc_1800A5546
0x1800a552b  mov     eax, [rsi+18h]
0x1800a552e  mov     [rbp+57h+var_48], eax
0x1800a5531  lea     rax, [rbp+57h+var_48]
0x1800a5535  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x1800a553a  lea     rdx, dword_180118A04
0x1800a5541  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800a5546  mov     r9d, 490h; char *
0x1800a554c  mov     edx, 3C6h; void *
0x1800a5551  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a5558  mov     rcx, [rbp+5Fh]; this
0x1800a555c  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800a5561  nop
0x1800a5562  mov     rcx, [rbp+57h+var_40]
0x1800a5566  xor     rcx, rsp; StackCookie
0x1800a5569  call    __security_check_cookie
0x1800a556e  add     rsp, 98h
0x1800a5575  pop     r15
0x1800a5577  pop     r14
0x1800a5579  pop     r12
0x1800a557b  pop     rdi
0x1800a557c  pop     rsi
0x1800a557d  pop     rbp
0x1800a557e  retn
0x1800a557f  mov     rcx, [rdx+18h]
0x1800a5583  mov     r8, [rdx+20h]
0x1800a5587  cmp     rcx, r8
0x1800a558a  jz      short loc_1800A55A5
0x1800a558c  mov     rdx, rax
0x1800a558f  mov     rax, [rcx]
0x1800a5592  cmp     [rax+70h], rdx
0x1800a5596  jz      loc_1800A5639
0x1800a559c  add     rcx, 10h
0x1800a55a0  cmp     rcx, r8
0x1800a55a3  jnz     short loc_1800A558F
0x1800a55a5  mov     eax, cs:dword_18013A120
0x1800a55ab  cmp     eax, 5
0x1800a55ae  jbe     short loc_1800A55CB
0x1800a55b0  mov     eax, [rsi+18h]
0x1800a55b3  mov     [rbp+57h+var_48], eax
0x1800a55b6  lea     rax, [rbp+57h+var_48]
0x1800a55ba  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x1800a55bf  lea     rdx, byte_180118A7F
0x1800a55c6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800a55cb  mov     rcx, [rbp+5Fh]; this
0x1800a55cf  mov     r9d, 4C7h; char *
0x1800a55d5  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a55dc  mov     edx, 3D5h; void *
0x1800a55e1  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800a55e6  mov     [rbp+57h+var_44], 0
0x1800a55ed  lea     rdx, [rsi+8]
0x1800a55f1  lea     r8, [rbp+57h+var_44]
0x1800a55f5  call    ?ReleaseConnection@CspManager@@YAKW4_WCM_MEDIA_TYPE@@AEBU_GUID@@PEAK@Z; CspManager::ReleaseConnection(_WCM_MEDIA_TYPE,_GUID const &,ulong *)
0x1800a55fa  test    eax, eax
0x1800a55fc  jz      short loc_1800A5616
0x1800a55fe  mov     rcx, [rbp+5Fh]; this
0x1800a5602  mov     r9d, eax; char *
0x1800a5605  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a560c  mov     edx, 3D9h; void *
0x1800a5611  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800a5616  mov     r8, r14
0x1800a5619  lea     rdx, [rbp+57h+var_70]
0x1800a561d  mov     rcx, [rsi]
0x1800a5620  call    ?erase@?$vector@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@V?$allocator@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@std@@@std@@@2@@Z; std::vector<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>>>)
0x1800a5625  mov     rcx, [rsi]
0x1800a5628  add     rcx, 30h ; '0'
0x1800a562c  mov     rdx, r14
0x1800a562f  call    std___Erase_remove_if_std__vector_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect____std__allocator_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect__________RoutePolicyOnDemand__HandleConnectionCompleteNotificationInternal____3____lambda_1___operator______2____lambda_6___
0x1800a5634  jmp     loc_1800A5562
0x1800a5639  cmp     byte ptr [rdx+78h], 0
0x1800a563d  mov     eax, cs:dword_18013A120
0x1800a5643  jz      short loc_1800A567A
0x1800a5645  cmp     eax, 5
0x1800a5648  jbe     short loc_1800A5665
0x1800a564a  mov     eax, [rsi+18h]
0x1800a564d  mov     [rbp+57h+var_44], eax
0x1800a5650  lea     rax, [rbp+57h+var_44]
0x1800a5654  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800a5659  lea     rdx, byte_1801188ED
0x1800a5660  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800a5665  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a566a  mov     r9d, 4DFh
0x1800a5670  mov     edx, 3EAh
0x1800a5675  jmp     loc_1800A5551
0x1800a567a  cmp     eax, 4
0x1800a567d  jbe     short loc_1800A56CD
0x1800a567f  lea     rax, [rsi+24h]
0x1800a5683  mov     [rbp+57h+var_80], rax
0x1800a5687  lea     r12, [rsi+8]
0x1800a568b  mov     qword ptr [rbp+57h+var_70.Data1], r12
0x1800a568f  mov     eax, [rsi+20h]
0x1800a5692  mov     [rbp+57h+var_44], eax
0x1800a5695  mov     eax, [rsi+18h]
0x1800a5698  mov     [rbp+57h+var_48], eax
0x1800a569b  lea     rax, [rbp+57h+var_80]
0x1800a569f  mov     [rsp+0C0h+var_88], rax
0x1800a56a4  lea     rax, [rbp+57h+var_70]
0x1800a56a8  mov     [rsp+0C0h+var_90], rax
0x1800a56ad  lea     rax, [rbp+57h+var_44]
0x1800a56b1  mov     [rsp+0C0h+var_98], rax
0x1800a56b6  lea     rax, [rbp+57h+var_48]
0x1800a56ba  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800a56bf  lea     rdx, byte_180118967
0x1800a56c6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x1800a56cb  jmp     short loc_1800A56D1
0x1800a56cd  lea     r12, [rsi+8]
0x1800a56d1  mov     r9d, [rsi+20h]; char *
0x1800a56d5  cmp     r9d, 0C0040026h
0x1800a56dc  jnz     loc_1800A5786
0x1800a56e2  mov     rdi, [rsi]
0x1800a56e5  mov     rdi, [rdi+18h]
0x1800a56e9  mov     rcx, [rsi]
0x1800a56ec  cmp     rdi, [rcx+20h]
0x1800a56f0  jz      short loc_1800A5766
0x1800a56f2  mov     rcx, [rdi]
0x1800a56f5  mov     rax, [r14]
0x1800a56f8  cmp     [rcx+70h], rax
0x1800a56fc  jnz     short loc_1800A5760
0x1800a56fe  cmp     qword ptr [rcx+80h], 0
0x1800a5706  jz      short loc_1800A5754
0x1800a5708  mov     eax, cs:dword_18013A120
0x1800a570e  cmp     eax, 4
0x1800a5711  jbe     short loc_1800A5740
0x1800a5713  mov     rax, [rdi]
0x1800a5716  mov     qword ptr [rbp+57h+var_70.Data1], rax
0x1800a571a  lea     rax, [rsi+8]
0x1800a571e  mov     [rbp+57h+var_80], rax
0x1800a5722  lea     rax, [rbp+57h+var_70]
0x1800a5726  mov     [rsp+0C0h+var_98], rax
0x1800a572b  lea     rax, [rbp+57h+var_80]
0x1800a572f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800a5734  lea     rdx, dword_1801187CC
0x1800a573b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x1800a5740  xor     r9d, r9d; union _NET_LUID_LH
0x1800a5743  mov     r8d, 80070491h; int
0x1800a5749  mov     rdx, [rdi]; struct Request *
0x1800a574c  mov     rcx, [rsi]; this
0x1800a574f  call    ?CompleteRequest@RoutePolicyOnDemand@@AEAAXAEAURequest@1@JT_NET_LUID_LH@@@Z; RoutePolicyOnDemand::CompleteRequest(RoutePolicyOnDemand::Request &,long,_NET_LUID_LH)
0x1800a5754  mov     rcx, [rdi]
0x1800a5757  add     rcx, 70h ; 'p'
0x1800a575b  call    ?reset@?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAXXZ; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::reset(void)
0x1800a5760  add     rdi, 10h
0x1800a5764  jmp     short loc_1800A56E9
0x1800a5766  mov     r8, r14
0x1800a5769  lea     rdx, [rbp+57h+var_70]
0x1800a576d  call    ?erase@?$vector@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@V?$allocator@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@std@@@std@@@2@@Z; std::vector<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>>>)
0x1800a5772  mov     rcx, [rsi]
0x1800a5775  add     rcx, 30h ; '0'
0x1800a5779  mov     rdx, r14
0x1800a577c  call    std___Erase_remove_if_std__vector_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect____std__allocator_std__unique_ptr_RoutePolicyOnDemand__Disconnect_std__default_delete_RoutePolicyOnDemand__Disconnect__________RoutePolicyOnDemand__HandleConnectionCompleteNotificationInternal____3____lambda_1___operator______2____lambda_6___
0x1800a5781  jmp     loc_1800A5562
0x1800a5786  test    r9d, r9d
0x1800a5789  jnz     short loc_1800A5792
0x1800a578b  movups  xmm0, xmmword ptr [r12]
0x1800a5790  jmp     short loc_1800A57CC
0x1800a5792  cmp     r9d, 0C0040022h
0x1800a5799  jnz     loc_1800A58D1
0x1800a579f  mov     rcx, [rsi]
0x1800a57a2  mov     r8, [rcx]
0x1800a57a5  jmp     short loc_1800A57C2
0x1800a57a7  mov     rdx, [r8]
0x1800a57aa  mov     rax, [rdx+20h]
0x1800a57ae  cmp     rax, [rsi+24h]
0x1800a57b2  jnz     short loc_1800A57BE
0x1800a57b4  mov     rax, [rdx+28h]
0x1800a57b8  cmp     rax, [rsi+2Ch]
0x1800a57bc  jz      short loc_1800A57F3
0x1800a57be  add     r8, 10h
0x1800a57c2  cmp     r8, [rcx+8]
0x1800a57c6  jnz     short loc_1800A57A7
0x1800a57c8  movups  xmm0, xmmword ptr [rsi+24h]
0x1800a57cc  mov     rax, [r14]
0x1800a57cf  movdqu  xmmword ptr [rax+20h], xmm0
0x1800a57d4  mov     rcx, [r14]
0x1800a57d7  lea     rdx, [rcx+18h]; InterfaceLuid
0x1800a57db  add     rcx, 20h ; ' '; InterfaceGuid
0x1800a57df  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800a57e5  mov     r15d, eax
0x1800a57e8  test    eax, eax
0x1800a57ea  jz      short loc_1800A580F
0x1800a57ec  mov     edx, 43Ch
0x1800a57f1  jmp     short loc_1800A582C
0x1800a57f3  mov     rdx, r14
0x1800a57f6  call    ?UpdateRequestsWithExistingSession@RoutePolicyOnDemand@@AEAAXAEBV?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@0@Z; RoutePolicyOnDemand::UpdateRequestsWithExistingSession(std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &,std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo> const &)
0x1800a57fb  mov     r8, r14
0x1800a57fe  lea     rdx, [rbp+57h+var_70]
0x1800a5802  mov     rcx, [rsi]
0x1800a5805  call    ?erase@?$vector@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@V?$allocator@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@@std@@@std@@@2@@Z; std::vector<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>>>>)
0x1800a580a  jmp     loc_1800A5562
0x1800a580f  mov     rcx, [r14]
0x1800a5812  lea     rdx, [rcx+10h]; InterfaceIndex
0x1800a5816  add     rcx, 18h; InterfaceLuid
0x1800a581a  call    cs:__imp_ConvertInterfaceLuidToIndex
0x1800a5820  mov     r15d, eax
0x1800a5823  test    eax, eax
0x1800a5825  jz      short loc_1800A5880
0x1800a5827  mov     edx, 43Fh; void *
0x1800a582c  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a5833  mov     r9d, eax; char *
0x1800a5836  mov     rcx, [rbp+5Fh]; this
0x1800a583a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800a583f  mov     [rbp+57h+var_48], 0
0x1800a5846  lea     r8, [rbp+57h+var_48]
0x1800a584a  mov     rdx, r12
0x1800a584d  call    ?ReleaseConnection@CspManager@@YAKW4_WCM_MEDIA_TYPE@@AEBU_GUID@@PEAK@Z; CspManager::ReleaseConnection(_WCM_MEDIA_TYPE,_GUID const &,ulong *)
0x1800a5852  test    eax, eax
0x1800a5854  jz      short loc_1800A586E
0x1800a5856  mov     rcx, [rbp+5Fh]; this
0x1800a585a  mov     r9d, eax; char *
0x1800a585d  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a5864  mov     edx, 44Eh; void *
0x1800a5869  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800a586e  test    r15d, r15d
0x1800a5871  jle     short loc_1800A58EC
0x1800a5873  movzx   r15d, r15w
0x1800a5877  or      r15d, 80070000h
0x1800a587e  jmp     short loc_1800A58EC
0x1800a5880  mov     rdx, [r14]; struct RoutePolicyOnDemand::InterfaceInfo *
0x1800a5883  mov     rcx, [rsi]; this
0x1800a5886  call    ?HandleL2Connected@RoutePolicyOnDemand@@AEAAJAEAUInterfaceInfo@1@@Z; RoutePolicyOnDemand::HandleL2Connected(RoutePolicyOnDemand::InterfaceInfo &)
0x1800a588b  mov     r15d, eax
0x1800a588e  test    eax, eax
0x1800a5890  jns     short loc_1800A58AA
0x1800a5892  mov     rcx, [rbp+5Fh]; this
0x1800a5896  mov     r9d, eax; char *
0x1800a5899  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a58a0  mov     edx, 442h; void *
0x1800a58a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a58aa  test    r15d, r15d
0x1800a58ad  jnz     short loc_1800A583F
0x1800a58af  mov     rax, [r14]
0x1800a58b2  mov     byte ptr [rax+78h], 1
0x1800a58b6  mov     rcx, [r14]
0x1800a58b9  add     rcx, 20h ; ' '
0x1800a58bd  mov     r9b, 1
0x1800a58c0  mov     r8b, r9b
0x1800a58c3  lea     edx, [r15+3]
0x1800a58c7  call    ?SetL2Connected@RouteManager@@SAXPEBU_GUID@@W4_WCM_MEDIA_TYPE@@_N2@Z; RouteManager::SetL2Connected(_GUID const *,_WCM_MEDIA_TYPE,bool,bool)
0x1800a58cc  jmp     loc_1800A5562
0x1800a58d1  mov     rcx, [rbp+5Fh]; this
0x1800a58d5  lea     r8, aOnecoreuapNetW_19; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800a58dc  mov     edx, 433h; void *
0x1800a58e1  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800a58e6  mov     r15d, 80070041h
0x1800a58ec  mov     rdi, [rsi]
0x1800a58ef  mov     rdi, [rdi+18h]
0x1800a58f3  mov     rax, [rsi]
0x1800a58f6  cmp     rdi, [rax+20h]
0x1800a58fa  mov     rax, [r14]
0x1800a58fd  jz      short loc_1800A5969
0x1800a58ff  mov     rcx, [rdi]
0x1800a5902  cmp     [rcx+70h], rax
0x1800a5906  jnz     short loc_1800A5963
0x1800a5908  cmp     qword ptr [rcx+80h], 0
0x1800a5910  jz      short loc_1800A5957
0x1800a5912  mov     eax, cs:dword_18013A120
0x1800a5918  cmp     eax, 4
0x1800a591b  jbe     short loc_1800A5946
0x1800a591d  mov     rax, [rdi]
0x1800a5920  mov     qword ptr [rbp+57h+var_70.Data1], rax
0x1800a5924  mov     [rbp+57h+var_80], r12
0x1800a5928  lea     rax, [rbp+57h+var_70]
0x1800a592c  mov     [rsp+0C0h+var_98], rax
0x1800a5931  lea     rax, [rbp+57h+var_80]
0x1800a5935  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800a593a  lea     rdx, byte_18011886D
0x1800a5941  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x1800a5946  xor     r9d, r9d; union _NET_LUID_LH
0x1800a5949  mov     r8d, r15d; int
0x1800a594c  mov     rdx, [rdi]; struct Request *
0x1800a594f  mov     rcx, [rsi]; this
0x1800a5952  call    ?CompleteRequest@RoutePolicyOnDemand@@AEAAXAEAURequest@1@JT_NET_LUID_LH@@@Z; RoutePolicyOnDemand::CompleteRequest(RoutePolicyOnDemand::Request &,long,_NET_LUID_LH)
0x1800a5957  mov     rcx, [rdi]
0x1800a595a  add     rcx, 70h ; 'p'
0x1800a595e  call    ?reset@?$shared_ptr@UInterfaceInfo@RoutePolicyOnDemand@@@std@@QEAAXXZ; std::shared_ptr<RoutePolicyOnDemand::InterfaceInfo>::reset(void)
  ... truncated ...
```
