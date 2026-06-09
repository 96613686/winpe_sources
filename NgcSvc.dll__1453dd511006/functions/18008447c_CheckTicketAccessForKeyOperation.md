# CheckTicketAccessForKeyOperation

- ea: `0x18008447c`
- end: `0x180084762`
- name: `CheckTicketAccessForKeyOperation`
- size: `742`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800832d0`

## callees

- `0x18000782c`
- `0x180021950`
- `0x180021f00`
- `0x1800281e0`
- `0x1800288a0`
- `0x180028d18`
- `0x18002d740`
- `0x18002dc0c`
- `0x180031c3c`
- `0x180034cf8`
- `0x180046d90`
- `0x180048394`
- `0x18008447c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084624`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008461a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008461a`

## string_xrefs

- `0x1800844f7`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`
- `0x18008457b`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`
- `0x180084643`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`
- `0x1800846e2`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckTicketAccessForKeyOperation(void *a1, __int64 a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // ebx
  wchar_t *v9; // rsi
  _QWORD *v10; // rbx
  signed int LastError; // ebx
  int v12; // r9d
  int v13; // eax
  unsigned int v15; // [rsp+20h] [rbp-60h]
  int v16; // [rsp+20h] [rbp-60h]
  _QWORD v17[8]; // [rsp+40h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v19; // [rsp+B0h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+B8h] [rbp+38h] BYREF

  NgcUtils::RpcCallerInfo::RpcCallerInfo((NgcUtils::RpcCallerInfo *)v17, a1);
  if ( v17[0] == v17[1] )
    goto LABEL_9;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    v4 = I_CheckNgcApiAccessRight(a1, (__int64)L"userSigninSupport", 1, 0, 0);
    v5 = HResultToSecurityStatus(v4);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
        (const char *)(unsigned int)v5,
        v15);
      goto LABEL_38;
    }
    goto LABEL_9;
  }
  v7 = I_CheckNgcApiAccessRight(a1, (__int64)L"userSigninSupport", 1, 0, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
LABEL_9:
    if ( *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
    {
      v6 = -2146893785;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
          (const char *)0x80090027LL,
          v15);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v19 = -2146893785;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180105AAF,
          0,
          0,
          (__int64)&v19);
      }
    }
    else
    {
      if ( *(_QWORD *)(a2 + 56) )
      {
        v9 = (wchar_t *)(a2 + 40);
        if ( *(_QWORD *)(a2 + 64) > 7u )
          v9 = *(wchar_t **)v9;
      }
      else
      {
        v9 = 0;
      }
      if ( *(_QWORD *)(a2 + 88) )
      {
        v10 = (_QWORD *)(a2 + 72);
        if ( *(_QWORD *)(a2 + 96) > 7u )
          v10 = (_QWORD *)*v10;
      }
      else
      {
        v10 = 0;
      }
      StringSid = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &StringSid,
        0);
      if ( ConvertSidToStringSidW(*(PSID *)a2, &StringSid) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v13 = NgcKspCheckKeyAccessRight(a1, 1, StringSid, v12, v9, (__int64)v10, 0);
          v6 = v13;
          if ( v13 >= 0 )
            v6 = 0;
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x75,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
              (const char *)(unsigned int)v13,
              v16);
        }
        else
        {
          v6 = NgcKspCheckKeyAccessRight(a1, 1, StringSid, v12, v9, (__int64)v10, 0);
          if ( v6 < 0 && (unsigned int)dword_180122070 > 2 )
          {
            v19 = v6;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_180122070,
              (unsigned __int8 *)byte_180105A51,
              0,
              0,
              (__int64)&v19);
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Win32(
            retaddr,
            (void *)0x5F,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
            (const char *)(unsigned int)LastError,
            v15);
        }
        else if ( (unsigned int)dword_180122070 > 2 )
        {
          v19 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)word_180105A82,
            0,
            0,
            (__int64)&v19);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = HResultToSecurityStatus(LastError);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    }
    goto LABEL_38;
  }
  if ( (unsigned int)dword_180122070 > 2 )
  {
    v19 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_180105AF1,
      0,
      0,
      (__int64)&v19);
  }
  v6 = HResultToSecurityStatus(v8);
LABEL_38:
  NgcUtils::RpcCallerInfo::~RpcCallerInfo((NgcUtils::RpcCallerInfo *)v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008447c  mov     [rsp-18h+arg_0], rbx
0x180084481  mov     [rsp-18h+arg_8], rsi
0x180084486  push    rbp
0x180084487  push    rdi
0x180084488  push    r14
0x18008448a  mov     rbp, rsp
0x18008448d  sub     rsp, 80h
0x180084494  mov     rdi, rdx
0x180084497  mov     r14, rcx
0x18008449a  mov     rdx, rcx; void *
0x18008449d  lea     rcx, [rbp+var_40]; this
0x1800844a1  call    ??0RpcCallerInfo@NgcUtils@@QEAA@QEAX@Z; NgcUtils::RpcCallerInfo::RpcCallerInfo(void * const)
0x1800844a6  nop
0x1800844a7  mov     rax, [rbp+var_38]
0x1800844ab  cmp     [rbp+var_40], rax
0x1800844af  jz      loc_180084556
0x1800844b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800844bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800844c1  mov     [rsp+80h+var_60], 0; int
0x1800844c9  xor     r9d, r9d
0x1800844cc  lea     r8d, [r9+1]
0x1800844d0  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x1800844d7  mov     rcx, r14
0x1800844da  test    al, al
0x1800844dc  jz      short loc_18008450D
0x1800844de  call    I_CheckNgcApiAccessRight
0x1800844e3  mov     ecx, eax; int
0x1800844e5  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x1800844ea  mov     ebx, eax
0x1800844ec  test    eax, eax
0x1800844ee  jns     short loc_180084556
0x1800844f0  mov     rcx, [rbp+18h]; this
0x1800844f4  mov     r9d, eax; char *
0x1800844f7  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800844fe  mov     edx, 30h ; '0'; void *
0x180084503  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084508  jmp     loc_18008473F
0x18008450d  call    I_CheckNgcApiAccessRight
0x180084512  mov     ebx, eax
0x180084514  test    eax, eax
0x180084516  jns     short loc_180084556
0x180084518  mov     ecx, cs:dword_180122070
0x18008451e  cmp     ecx, 2
0x180084521  jbe     short loc_180084548
0x180084523  mov     [rbp+arg_10], eax
0x180084526  lea     rax, [rbp+arg_10]
0x18008452a  mov     qword ptr [rsp+80h+var_60], rax
0x18008452f  xor     r9d, r9d
0x180084532  xor     r8d, r8d
0x180084535  lea     rdx, byte_180105AF1
0x18008453c  lea     rcx, dword_180122070
0x180084543  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084548  mov     ecx, ebx; int
0x18008454a  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18008454f  mov     ebx, eax
0x180084551  jmp     loc_18008473F
0x180084556  mov     rax, [rdi+8]
0x18008455a  cmp     [rdi], rax
0x18008455d  jnz     short loc_1800845CE
0x18008455f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180084566  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18008456b  mov     ebx, 80090027h
0x180084570  test    al, al
0x180084572  jz      short loc_180084591
0x180084574  mov     rcx, [rbp+18h]; this
0x180084578  mov     r9d, ebx; char *
0x18008457b  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180084582  mov     edx, 49h ; 'I'; void *
0x180084587  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008458c  jmp     loc_18008473F
0x180084591  mov     eax, cs:dword_180122070
0x180084597  cmp     eax, 2
0x18008459a  jbe     loc_18008473F
0x1800845a0  mov     [rbp+arg_10], 80090027h
0x1800845a7  lea     rax, [rbp+arg_10]
0x1800845ab  mov     qword ptr [rsp+80h+var_60], rax
0x1800845b0  xor     r9d, r9d
0x1800845b3  xor     r8d, r8d
0x1800845b6  lea     rdx, byte_180105AAF
0x1800845bd  lea     rcx, dword_180122070
0x1800845c4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800845c9  jmp     loc_18008473F
0x1800845ce  cmp     qword ptr [rdi+38h], 0
0x1800845d3  jnz     short loc_1800845D9
0x1800845d5  xor     esi, esi
0x1800845d7  jmp     short loc_1800845E7
0x1800845d9  lea     rsi, [rdi+28h]
0x1800845dd  cmp     qword ptr [rsi+18h], 7
0x1800845e2  jbe     short loc_1800845E7
0x1800845e4  mov     rsi, [rsi]
0x1800845e7  cmp     qword ptr [rdi+58h], 0
0x1800845ec  jnz     short loc_1800845F2
0x1800845ee  xor     ebx, ebx
0x1800845f0  jmp     short loc_180084600
0x1800845f2  lea     rbx, [rdi+48h]
0x1800845f6  cmp     qword ptr [rbx+18h], 7
0x1800845fb  jbe     short loc_180084600
0x1800845fd  mov     rbx, [rbx]
0x180084600  mov     [rbp+StringSid], 0
0x180084608  xor     edx, edx
0x18008460a  lea     rcx, [rbp+StringSid]
0x18008460e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180084613  lea     rdx, [rbp+StringSid]; StringSid
0x180084617  mov     rcx, [rdi]; Sid
0x18008461a  call    cs:__imp_ConvertSidToStringSidW
0x180084620  test    eax, eax
0x180084622  jnz     short loc_1800846A1
0x180084624  call    cs:__imp_GetLastError
0x18008462a  mov     ebx, eax
0x18008462c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180084633  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180084638  test    al, al
0x18008463a  jz      short loc_180084656
0x18008463c  mov     rcx, [rbp+18h]; this
0x180084640  mov     r9d, ebx; char *
0x180084643  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18008464a  mov     edx, 5Fh ; '_'; void *
0x18008464f  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180084654  jmp     short loc_180084686
0x180084656  mov     eax, cs:dword_180122070
0x18008465c  cmp     eax, 2
0x18008465f  jbe     short loc_180084686
0x180084661  mov     [rbp+arg_10], ebx
0x180084664  lea     rax, [rbp+arg_10]
0x180084668  mov     qword ptr [rsp+80h+var_60], rax
0x18008466d  xor     r9d, r9d
0x180084670  xor     r8d, r8d
0x180084673  lea     rdx, word_180105A82
0x18008467a  lea     rcx, dword_180122070
0x180084681  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084686  test    ebx, ebx
0x180084688  jle     short loc_180084693
0x18008468a  movzx   ebx, bx
0x18008468d  or      ebx, 80070000h
0x180084693  mov     ecx, ebx; int
0x180084695  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18008469a  mov     ebx, eax
0x18008469c  jmp     loc_180084735
0x1800846a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800846a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800846ad  mov     [rsp+80h+var_50], 0
0x1800846b6  mov     r8, [rbp+StringSid]
0x1800846ba  mov     edx, 1
0x1800846bf  mov     rcx, r14
0x1800846c2  mov     [rsp+80h+var_58], rbx
0x1800846c7  mov     qword ptr [rsp+80h+var_60], rsi; int
0x1800846cc  test    al, al
0x1800846ce  jz      short loc_1800846F9
0x1800846d0  call    NgcKspCheckKeyAccessRight
0x1800846d5  mov     ebx, eax
0x1800846d7  test    eax, eax
0x1800846d9  jns     short loc_1800846F5
0x1800846db  mov     rcx, [rbp+18h]; this
0x1800846df  mov     r9d, eax; char *
0x1800846e2  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800846e9  mov     edx, 75h ; 'u'; void *
0x1800846ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800846f3  jmp     short loc_180084735
0x1800846f5  xor     ebx, ebx
0x1800846f7  jmp     short loc_180084735
0x1800846f9  call    NgcKspCheckKeyAccessRight
0x1800846fe  mov     ebx, eax
0x180084700  test    eax, eax
0x180084702  jns     short loc_180084735
0x180084704  mov     eax, cs:dword_180122070
0x18008470a  cmp     eax, 2
0x18008470d  jbe     short loc_180084735
0x18008470f  mov     [rbp+arg_10], ebx
0x180084712  lea     rax, [rbp+arg_10]
0x180084716  mov     qword ptr [rsp+80h+var_60], rax
0x18008471b  xor     r9d, r9d
0x18008471e  xor     r8d, r8d
0x180084721  lea     rdx, byte_180105A51
0x180084728  lea     rcx, dword_180122070
0x18008472f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084734  nop
0x180084735  lea     rcx, [rbp+StringSid]; void *
0x180084739  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008473e  nop
0x18008473f  lea     rcx, [rbp+var_40]; this
0x180084743  call    ??1RpcCallerInfo@NgcUtils@@QEAA@XZ; NgcUtils::RpcCallerInfo::~RpcCallerInfo(void)
0x180084748  mov     eax, ebx
0x18008474a  lea     r11, [rsp+80h+var_s0]
0x180084752  mov     rbx, [r11+20h]
0x180084756  mov     rsi, [r11+28h]
0x18008475a  mov     rsp, r11
0x18008475d  pop     r14
0x18008475f  pop     rdi
0x180084760  pop     rbp
0x180084761  retn
```
