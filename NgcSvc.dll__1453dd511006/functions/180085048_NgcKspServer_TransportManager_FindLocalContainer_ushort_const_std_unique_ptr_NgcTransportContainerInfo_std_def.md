# NgcKspServer::TransportManager::FindLocalContainer(ushort const *,std::unique_ptr<NgcTransportContainerInfo,std::default_delete<NgcTransportContainerInfo>> *)

- ea: `0x180085048`
- end: `0x18008530b`
- name: `?FindLocalContainer@TransportManager@NgcKspServer@@SAJPEBGPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@Z`
- size: `707`
- prototype: ``
- caller_count: `13`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006cb40`
- `0x18006d0a8`
- `0x18006d340`
- `0x18006df20`
- `0x18006e128`
- `0x18006e554`
- `0x18006f620`
- `0x18006ffbc`
- `0x1800702f8`
- `0x1800706b0`
- `0x1800708b8`
- `0x1800717f4`
- `0x18007bb38`

## callees

- `0x1800049e0`
- `0x180005e90`
- `0x18000782c`
- `0x180011810`
- `0x180012260`
- `0x180028420`
- `0x180028d18`
- `0x180029dd0`
- `0x18002c9d8`
- `0x18002ee84`
- `0x180031c3c`
- `0x180034cf8`
- `0x180046d90`
- `0x180048394`
- `0x180085048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008508f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008508f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085204`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008528f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800852f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008528f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800852f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008507a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008507a`

## string_xrefs

- `0x1800850ae`: `onecore\ds\security\ngc\kspsvc\svc\transportmanager.cpp`
- `0x180085160`: `onecore\ds\security\ngc\kspsvc\svc\transportmanager.cpp`
- `0x180085234`: `onecore\ds\security\ngc\kspsvc\svc\transportmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcKspServer::TransportManager::FindLocalContainer(const WCHAR *a1, __int64 *a2)
{
  BOOL v3; // ebx
  signed int LastError; // ebx
  struct NgcKspServer::TransportManager *v5; // rax
  _QWORD *v6; // rax
  int v7; // edi
  __int64 *i; // rbx
  struct NgcKspServer::TransportManager *v9; // rax
  _QWORD *v10; // rax
  PSID v11; // rcx
  PSID v13; // rcx
  bool v14; // zf
  unsigned int v15; // [rsp+20h] [rbp-40h]
  __int64 v16; // [rsp+30h] [rbp-30h] BYREF
  std::_Ref_count_base *v17; // [rsp+38h] [rbp-28h]
  PSID Sid[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v21; // [rsp+90h] [rbp+30h] BYREF
  PSID pSid1; // [rsp+98h] [rbp+38h] BYREF

  pSid1 = 0;
  Sid[0] = &pSid1;
  Sid[1] = 0;
  LOBYTE(v19) = 1;
  v3 = ConvertStringSidToSidW(a1, &Sid[1]);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)Sid);
  if ( !v3 )
  {
    LastError = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\transportmanager.cpp",
        (const char *)(unsigned int)LastError,
        v15);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      v21 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)word_180105BBA,
        0,
        0,
        (__int64)&v21);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_34;
  }
  *(_OWORD *)Sid = 0;
  v19 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    v5 = NgcKspServer::TransportManager::Instance();
    v6 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v5, &v16);
    LastError = NgcLocalTransport::LocalTransport::EnumContainers(*v6, Sid);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\transportmanager.cpp",
        (const char *)(unsigned int)LastError,
        v15);
LABEL_33:
      std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(Sid);
LABEL_34:
      v13 = pSid1;
      v14 = pSid1 == 0;
      pSid1 = 0;
      if ( !v14 )
        LocalFree(v13);
      return (unsigned int)LastError;
    }
    v7 = 0;
  }
  else
  {
    v9 = NgcKspServer::TransportManager::Instance();
    v10 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v9, &v16);
    v7 = NgcLocalTransport::LocalTransport::EnumContainers(*v10, Sid);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v21 = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180105B87,
          0,
          0,
          (__int64)&v21);
      }
      LastError = HResultToSecurityStatus(v7);
      goto LABEL_33;
    }
  }
  v16 = 0;
  for ( i = (__int64 *)Sid[0]; ; ++i )
  {
    if ( i == Sid[1] )
      goto LABEL_24;
    if ( EqualSid(pSid1, *(PSID *)(*i + 16)) )
      break;
  }
  std::unique_ptr<NgcTransportContainerInfo>::operator=<std::default_delete<NgcTransportContainerInfo>,0>(&v16, i);
  if ( !v16 )
  {
LABEL_24:
    LastError = -2147023728;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\transportmanager.cpp",
        (const char *)0x80070490LL,
        v15);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      v21 = -2147023728;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)word_180105B5A,
        0,
        0,
        (__int64)&v21);
    }
    std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(&v16);
    goto LABEL_33;
  }
  std::unique_ptr<NgcTransportContainerInfo>::operator=<std::default_delete<NgcTransportContainerInfo>,0>(a2, &v16);
  std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(&v16);
  std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(Sid);
  v11 = pSid1;
  pSid1 = 0;
  if ( v11 )
    LocalFree(v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180085048  mov     [rsp-18h+arg_0], rbx
0x18008504d  push    rbp
0x18008504e  push    rsi
0x18008504f  push    rdi
0x180085050  mov     rbp, rsp
0x180085053  sub     rsp, 60h
0x180085057  mov     rsi, rdx
0x18008505a  mov     [rbp+pSid1], 0
0x180085062  lea     rax, [rbp+pSid1]
0x180085066  mov     [rbp+Sid], rax
0x18008506a  mov     [rbp+Sid+8], 0
0x180085072  mov     byte ptr [rbp+var_10], 1
0x180085076  lea     rdx, [rbp+Sid+8]; Sid
0x18008507a  call    cs:__imp_ConvertStringSidToSidW
0x180085080  mov     ebx, eax
0x180085082  lea     rcx, [rbp+Sid]
0x180085086  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18008508b  test    ebx, ebx
0x18008508d  jnz     short loc_180085107
0x18008508f  call    cs:__imp_GetLastError
0x180085095  mov     ebx, eax
0x180085097  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18008509e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800850a3  test    al, al
0x1800850a5  jz      short loc_1800850C1
0x1800850a7  mov     rcx, [rbp+18h]; this
0x1800850ab  mov     r9d, ebx; char *
0x1800850ae  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800850b5  mov     edx, 13Ch; void *
0x1800850ba  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800850bf  jmp     short loc_1800850F1
0x1800850c1  mov     eax, cs:dword_180122070
0x1800850c7  cmp     eax, 2
0x1800850ca  jbe     short loc_1800850F1
0x1800850cc  mov     [rbp+arg_10], ebx
0x1800850cf  lea     rax, [rbp+arg_10]
0x1800850d3  mov     qword ptr [rsp+60h+var_40], rax
0x1800850d8  xor     r9d, r9d
0x1800850db  xor     r8d, r8d
0x1800850de  lea     rdx, word_180105BBA
0x1800850e5  lea     rcx, dword_180122070
0x1800850ec  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800850f1  test    ebx, ebx
0x1800850f3  jle     loc_1800852E2
0x1800850f9  movzx   ebx, bx
0x1800850fc  or      ebx, 80070000h
0x180085102  jmp     loc_1800852E2
0x180085107  xorps   xmm0, xmm0
0x18008510a  movdqu  xmmword ptr [rbp+Sid], xmm0
0x18008510f  mov     [rbp+var_10], 0
0x180085117  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18008511e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180085123  test    al, al
0x180085125  jz      short loc_180085189
0x180085127  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18008512c  lea     rdx, [rbp+var_30]
0x180085130  mov     rcx, rax
0x180085133  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x180085138  nop
0x180085139  lea     rdx, [rbp+Sid]
0x18008513d  mov     rcx, [rax]
0x180085140  call    ?EnumContainers@LocalTransport@NgcLocalTransport@@UEAAJPEAV?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@@Z; NgcLocalTransport::LocalTransport::EnumContainers(std::vector<std::unique_ptr<NgcTransportContainerInfo>> *)
0x180085145  mov     ebx, eax
0x180085147  mov     rcx, [rbp+var_28]; this
0x18008514b  test    rcx, rcx
0x18008514e  jz      short loc_180085155
0x180085150  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180085155  test    ebx, ebx
0x180085157  jns     short loc_180085176
0x180085159  mov     rcx, [rbp+18h]; this
0x18008515d  mov     r9d, ebx; char *
0x180085160  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180085167  mov     edx, 14Dh; void *
0x18008516c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085171  jmp     loc_1800852D8
0x180085176  xor     edi, edi
0x180085178  mov     [rbp+var_30], 0
0x180085180  mov     rbx, [rbp+Sid]
0x180085184  jmp     loc_180085212
0x180085189  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18008518e  lea     rdx, [rbp+var_30]
0x180085192  mov     rcx, rax
0x180085195  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18008519a  nop
0x18008519b  lea     rdx, [rbp+Sid]
0x18008519f  mov     rcx, [rax]
0x1800851a2  call    ?EnumContainers@LocalTransport@NgcLocalTransport@@UEAAJPEAV?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@@Z; NgcLocalTransport::LocalTransport::EnumContainers(std::vector<std::unique_ptr<NgcTransportContainerInfo>> *)
0x1800851a7  mov     edi, eax
0x1800851a9  mov     rcx, [rbp+var_28]; this
0x1800851ad  test    rcx, rcx
0x1800851b0  jz      short loc_1800851B7
0x1800851b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800851b7  test    edi, edi
0x1800851b9  jns     short loc_180085178
0x1800851bb  mov     ecx, cs:dword_180122070
0x1800851c1  cmp     ecx, 2
0x1800851c4  jbe     short loc_1800851EB
0x1800851c6  mov     [rbp+arg_10], edi
0x1800851c9  lea     rax, [rbp+arg_10]
0x1800851cd  mov     qword ptr [rsp+60h+var_40], rax
0x1800851d2  xor     r9d, r9d
0x1800851d5  xor     r8d, r8d
0x1800851d8  lea     rdx, byte_180105B87
0x1800851df  lea     rcx, dword_180122070
0x1800851e6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800851eb  mov     ecx, edi; int
0x1800851ed  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x1800851f2  mov     ebx, eax
0x1800851f4  jmp     loc_1800852D8
0x1800851f9  mov     rdx, [rbx]
0x1800851fc  mov     rdx, [rdx+10h]; pSid2
0x180085200  mov     rcx, [rbp+pSid1]; pSid1
0x180085204  call    cs:__imp_EqualSid
0x18008520a  test    eax, eax
0x18008520c  jnz     short loc_18008524A
0x18008520e  add     rbx, 8
0x180085212  cmp     rbx, [rbp+Sid+8]
0x180085216  jnz     short loc_1800851F9
0x180085218  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18008521f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180085224  mov     ebx, 80070490h
0x180085229  test    al, al
0x18008522b  jz      short loc_180085299
0x18008522d  mov     rcx, [rbp+18h]; this
0x180085231  mov     r9d, ebx; char *
0x180085234  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18008523b  mov     edx, 16Eh; void *
0x180085240  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180085245  jmp     loc_1800852CE
0x18008524a  mov     rdx, rbx
0x18008524d  lea     rcx, [rbp+var_30]
0x180085251  call    ??$?4U?$default_delete@UNgcTransportContainerInfo@@@std@@$0A@@?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<NgcTransportContainerInfo>::operator=<std::default_delete<NgcTransportContainerInfo>,0>(std::unique_ptr<NgcTransportContainerInfo> &&)
0x180085256  cmp     [rbp+var_30], 0
0x18008525b  jz      short loc_180085218
0x18008525d  lea     rdx, [rbp+var_30]
0x180085261  mov     rcx, rsi
0x180085264  call    ??$?4U?$default_delete@UNgcTransportContainerInfo@@@std@@$0A@@?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<NgcTransportContainerInfo>::operator=<std::default_delete<NgcTransportContainerInfo>,0>(std::unique_ptr<NgcTransportContainerInfo> &&)
0x180085269  nop
0x18008526a  lea     rcx, [rbp+var_30]
0x18008526e  call    ??1?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(void)
0x180085273  nop
0x180085274  lea     rcx, [rbp+Sid]
0x180085278  call    ?_Tidy@?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(void)
0x18008527d  nop
0x18008527e  mov     rcx, [rbp+pSid1]; hMem
0x180085282  mov     [rbp+pSid1], 0
0x18008528a  test    rcx, rcx
0x18008528d  jz      short loc_180085295
0x18008528f  call    cs:__imp_LocalFree
0x180085295  mov     eax, edi
0x180085297  jmp     short loc_1800852FB
0x180085299  mov     eax, cs:dword_180122070
0x18008529f  cmp     eax, 2
0x1800852a2  jbe     short loc_1800852CE
0x1800852a4  mov     [rbp+arg_10], 80070490h
0x1800852ab  lea     rax, [rbp+arg_10]
0x1800852af  mov     qword ptr [rsp+60h+var_40], rax
0x1800852b4  xor     r9d, r9d
0x1800852b7  xor     r8d, r8d
0x1800852ba  lea     rdx, word_180105B5A
0x1800852c1  lea     rcx, dword_180122070
0x1800852c8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800852cd  nop
0x1800852ce  lea     rcx, [rbp+var_30]
0x1800852d2  call    ??1?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(void)
0x1800852d7  nop
0x1800852d8  lea     rcx, [rbp+Sid]
0x1800852dc  call    ?_Tidy@?$vector@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::unique_ptr<NgcTransportContainerInfo>>::_Tidy(void)
0x1800852e1  nop
0x1800852e2  mov     rcx, [rbp+pSid1]; hMem
0x1800852e6  test    rcx, rcx
0x1800852e9  mov     [rbp+pSid1], 0
0x1800852f1  jz      short loc_1800852F9
0x1800852f3  call    cs:__imp_LocalFree
0x1800852f9  mov     eax, ebx
0x1800852fb  mov     rbx, [rsp+60h+arg_0]
0x180085303  add     rsp, 60h
0x180085307  pop     rdi
0x180085308  pop     rsi
0x180085309  pop     rbp
0x18008530a  retn
```
