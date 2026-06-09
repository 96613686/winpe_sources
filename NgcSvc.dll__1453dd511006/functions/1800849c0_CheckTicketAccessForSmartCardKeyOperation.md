# CheckTicketAccessForSmartCardKeyOperation

- ea: `0x1800849c0`
- end: `0x180084d55`
- name: `CheckTicketAccessForSmartCardKeyOperation`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180083020`

## callees

- `0x180021950`
- `0x1800281e0`
- `0x1800288a0`
- `0x180028d18`
- `0x180031c3c`
- `0x180034cf8`
- `0x180046d90`
- `0x180048394`
- `0x1800849c0`
- `0x180086980`
- `0x180087340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084be9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180084bb3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180084bb3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084ac6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084bdf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084ac6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180084bdf`

## string_xrefs

- `0x180084a07`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`
- `0x180084aef`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`
- `0x180084c08`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`
- `0x180084ca8`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckTicketAccessForSmartCardKeyOperation(__int64 a1, __int64 a2, _DWORD *a3, _BYTE *a4)
{
  int ManagedPolicy; // edi
  int IsPassportTicketsWithSmartCardNodeEnabled; // eax
  int v9; // ecx
  struct NgcPolicy *v10; // r8
  enum PolicyManager::PolicyType *v11; // r9
  signed int LastError; // edi
  int v13; // r15d
  BOOL v14; // eax
  const WCHAR *v15; // r9
  unsigned int v16; // [rsp+20h] [rbp-60h]
  int v17; // [rsp+20h] [rbp-60h]
  LPWSTR v18; // [rsp+30h] [rbp-50h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 v20[2]; // [rsp+40h] [rbp-40h] BYREF
  int v21; // [rsp+44h] [rbp-3Ch]
  __int64 v22; // [rsp+48h] [rbp-38h]
  char v23; // [rsp+50h] [rbp-30h]
  int v24; // [rsp+54h] [rbp-2Ch]
  int v25; // [rsp+58h] [rbp-28h]
  __int128 v26; // [rsp+5Ch] [rbp-24h]
  int v27; // [rsp+6Ch] [rbp-14h]
  __int64 v28; // [rsp+70h] [rbp-10h]
  int v29; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int v31; // [rsp+B8h] [rbp+38h] BYREF
  _DWORD *v32; // [rsp+C0h] [rbp+40h]
  _BYTE *v33; // [rsp+C8h] [rbp+48h]

  v33 = a4;
  v32 = a3;
  if ( *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
  {
    ManagedPolicy = -2146893785;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
        (const char *)0x80090027LL,
        v16);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      v31 = -2146893785;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180105975,
        0,
        0,
        (__int64)&v31);
    }
    return (unsigned int)ManagedPolicy;
  }
  v31 = 2;
  IsPassportTicketsWithSmartCardNodeEnabled = PolicyManager::IsPassportTicketsWithSmartCardNodeEnabled(
                                                (PolicyManager *)&v31,
                                                (enum _NGC_ENABLED_STATE *)a2);
  if ( IsPassportTicketsWithSmartCardNodeEnabled >= 0 )
  {
    v9 = v31;
  }
  else
  {
    if ( (unsigned int)dword_180122070 > 3 )
    {
      v31 = IsPassportTicketsWithSmartCardNodeEnabled;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180105933,
        0,
        0,
        (__int64)&v31);
    }
    v9 = 2;
  }
  if ( v9 )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( !ConvertSidToStringSidW(*(PSID *)a2, &StringSid) )
    {
      LastError = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x144,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
          (const char *)(unsigned int)LastError,
          v16);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v31 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1801058C9,
          0,
          0,
          (__int64)&v31);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ManagedPolicy = HResultToSecurityStatus(LastError);
      goto LABEL_39;
    }
    LOBYTE(v20[0]) = 0;
    v13 = 1;
    v21 = 1;
    v22 = 1;
    v23 = 0;
    v24 = 8;
    v25 = 127;
    v26 = 0;
    v27 = 2;
    v28 = 1;
    v29 = 0;
    ManagedPolicy = PolicyManager::GetManagedPolicy((PolicyManager *)StringSid, v20, v10, v11);
    if ( ManagedPolicy < 0 )
    {
LABEL_39:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
      return (unsigned int)ManagedPolicy;
    }
    *v32 = v22;
    v14 = EqualSid(*(PSID *)a2, *(PSID *)(a1 + 24));
    *v33 = v14;
    v18 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v18,
      0);
    if ( ConvertSidToStringSidW(*(PSID *)(a1 + 24), &v18) )
    {
      if ( (_DWORD)v22 == 2 )
      {
        v15 = 0;
      }
      else
      {
        v15 = v18;
        v13 = 0;
      }
      ManagedPolicy = I_CheckNgcApiAccessRight(*(void **)(a1 + 48), (__int64)L"sharedUserCertificates", 0, v15, v13);
      if ( ManagedPolicy >= 0 )
        goto LABEL_38;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x182,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
          (const char *)(unsigned int)ManagedPolicy,
          v17);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v31 = ManagedPolicy;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180105855,
          0,
          0,
          (__int64)&v31);
      }
    }
    else
    {
      ManagedPolicy = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x16C,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
          (const char *)(unsigned int)ManagedPolicy,
          v16);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v31 = ManagedPolicy;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&word_180105896,
          0,
          0,
          (__int64)&v31);
      }
      if ( ManagedPolicy > 0 )
        ManagedPolicy = (unsigned __int16)ManagedPolicy | 0x80070000;
    }
    ManagedPolicy = HResultToSecurityStatus(ManagedPolicy);
LABEL_38:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v18);
    goto LABEL_39;
  }
  if ( (unsigned int)dword_180122070 > 4 )
  {
    v31 = -2146893783;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_1801058F9,
      0,
      0,
      (__int64)&v31);
  }
  return 2148073513LL;
}

```

## disassembly

```asm
0x1800849c0  mov     [rsp-28h+arg_18], r9
0x1800849c5  mov     [rsp-28h+arg_10], r8
0x1800849ca  push    rbp
0x1800849cb  push    rdi
0x1800849cc  push    r12
0x1800849ce  push    r13
0x1800849d0  push    r15
0x1800849d2  mov     rbp, rsp
0x1800849d5  sub     rsp, 80h
0x1800849dc  mov     r12, rdx
0x1800849df  mov     r13, rcx
0x1800849e2  mov     rax, [rdx+8]
0x1800849e6  cmp     [rdx], rax
0x1800849e9  jnz     short loc_180084A55
0x1800849eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800849f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800849f7  mov     edi, 80090027h
0x1800849fc  test    al, al
0x1800849fe  jz      short loc_180084A1A
0x180084a00  mov     rcx, [rbp+28h]; this
0x180084a04  mov     r9d, edi; char *
0x180084a07  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180084a0e  mov     edx, 10Ah; void *
0x180084a13  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180084a18  jmp     short loc_180084A4E
0x180084a1a  mov     eax, cs:dword_180122070
0x180084a20  cmp     eax, 2
0x180084a23  jbe     short loc_180084A4E
0x180084a25  mov     [rbp+arg_8], 80090027h
0x180084a2c  lea     rcx, [rbp+arg_8]
0x180084a30  mov     qword ptr [rsp+80h+var_60], rcx
0x180084a35  xor     r9d, r9d
0x180084a38  xor     r8d, r8d
0x180084a3b  lea     rdx, byte_180105975
0x180084a42  lea     rcx, dword_180122070
0x180084a49  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084a4e  mov     eax, edi
0x180084a50  jmp     loc_180084D45
0x180084a55  mov     [rbp+arg_8], 2
0x180084a5c  lea     rcx, [rbp+arg_8]; this
0x180084a60  call    ?IsPassportTicketsWithSmartCardNodeEnabled@PolicyManager@@YAJPEAW4_NGC_ENABLED_STATE@@@Z; PolicyManager::IsPassportTicketsWithSmartCardNodeEnabled(_NGC_ENABLED_STATE *)
0x180084a65  test    eax, eax
0x180084a67  jns     short loc_180084AA0
0x180084a69  mov     ecx, cs:dword_180122070
0x180084a6f  cmp     ecx, 3
0x180084a72  jbe     short loc_180084A99
0x180084a74  mov     [rbp+arg_8], eax
0x180084a77  lea     rax, [rbp+arg_8]
0x180084a7b  mov     qword ptr [rsp+80h+var_60], rax
0x180084a80  xor     r9d, r9d
0x180084a83  xor     r8d, r8d
0x180084a86  lea     rdx, byte_180105933
0x180084a8d  lea     rcx, dword_180122070
0x180084a94  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084a99  mov     ecx, 2
0x180084a9e  jmp     short loc_180084AA3
0x180084aa0  mov     ecx, [rbp+arg_8]
0x180084aa3  test    ecx, ecx
0x180084aa5  jz      loc_180084D0C
0x180084aab  mov     [rbp+StringSid], 0
0x180084ab3  xor     edx, edx
0x180084ab5  lea     rcx, [rbp+StringSid]
0x180084ab9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180084abe  lea     rdx, [rbp+StringSid]; StringSid
0x180084ac2  mov     rcx, [r12]; Sid
0x180084ac6  call    cs:__imp_ConvertSidToStringSidW
0x180084acc  test    eax, eax
0x180084ace  jnz     short loc_180084B4D
0x180084ad0  call    cs:__imp_GetLastError
0x180084ad6  mov     edi, eax
0x180084ad8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180084adf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180084ae4  test    al, al
0x180084ae6  jz      short loc_180084B02
0x180084ae8  mov     rcx, [rbp+28h]; this
0x180084aec  mov     r9d, edi; char *
0x180084aef  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180084af6  mov     edx, 144h; void *
0x180084afb  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180084b00  jmp     short loc_180084B32
0x180084b02  mov     eax, cs:dword_180122070
0x180084b08  cmp     eax, 2
0x180084b0b  jbe     short loc_180084B32
0x180084b0d  mov     [rbp+arg_8], edi
0x180084b10  lea     rax, [rbp+arg_8]
0x180084b14  mov     qword ptr [rsp+80h+var_60], rax
0x180084b19  xor     r9d, r9d
0x180084b1c  xor     r8d, r8d
0x180084b1f  lea     rdx, byte_1801058C9
0x180084b26  lea     rcx, dword_180122070
0x180084b2d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084b32  test    edi, edi
0x180084b34  jle     short loc_180084B3F
0x180084b36  movzx   edi, di
0x180084b39  or      edi, 80070000h
0x180084b3f  mov     ecx, edi; int
0x180084b41  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180084b46  mov     edi, eax
0x180084b48  jmp     loc_180084CFE
0x180084b4d  mov     byte ptr [rbp+var_40], 0
0x180084b51  mov     r15d, 1
0x180084b57  mov     [rbp+var_3C], r15d
0x180084b5b  mov     [rbp+var_38], r15
0x180084b5f  mov     [rbp+var_30], 0
0x180084b63  mov     [rbp+var_2C], 8
0x180084b6a  mov     [rbp+var_28], 7Fh
0x180084b71  xorps   xmm0, xmm0
0x180084b74  movdqu  [rbp+var_24], xmm0
0x180084b79  mov     [rbp+var_14], 2
0x180084b80  mov     [rbp+var_10], r15
0x180084b84  mov     [rbp+var_8], 0
0x180084b8b  lea     rdx, [rbp+var_40]; unsigned __int16 *
0x180084b8f  mov     rcx, [rbp+StringSid]; this
0x180084b93  call    ?GetManagedPolicy@PolicyManager@@YAJPEBGPEAVNgcPolicy@2@PEAW4PolicyType@1@@Z; PolicyManager::GetManagedPolicy(ushort const *,NgcPolicy::NgcPolicy *,PolicyManager::PolicyType *)
0x180084b98  mov     edi, eax
0x180084b9a  test    eax, eax
0x180084b9c  js      loc_180084CFE
0x180084ba2  mov     eax, dword ptr [rbp+var_38]
0x180084ba5  mov     rcx, [rbp+arg_10]
0x180084ba9  mov     [rcx], eax
0x180084bab  mov     rdx, [r13+18h]; pSid2
0x180084baf  mov     rcx, [r12]; pSid1
0x180084bb3  call    cs:__imp_EqualSid
0x180084bb9  test    eax, eax
0x180084bbb  setnz   al
0x180084bbe  mov     rcx, [rbp+arg_18]
0x180084bc2  mov     [rcx], al
0x180084bc4  mov     [rbp+var_50], 0
0x180084bcc  xor     edx, edx
0x180084bce  lea     rcx, [rbp+var_50]
0x180084bd2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180084bd7  lea     rdx, [rbp+var_50]; StringSid
0x180084bdb  mov     rcx, [r13+18h]; Sid
0x180084bdf  call    cs:__imp_ConvertSidToStringSidW
0x180084be5  test    eax, eax
0x180084be7  jnz     short loc_180084C61
0x180084be9  call    cs:__imp_GetLastError
0x180084bef  mov     edi, eax
0x180084bf1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180084bf8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180084bfd  test    al, al
0x180084bff  jz      short loc_180084C1B
0x180084c01  mov     rcx, [rbp+28h]; this
0x180084c05  mov     r9d, edi; char *
0x180084c08  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180084c0f  mov     edx, 16Ch; void *
0x180084c14  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180084c19  jmp     short loc_180084C4B
0x180084c1b  mov     eax, cs:dword_180122070
0x180084c21  cmp     eax, 2
0x180084c24  jbe     short loc_180084C4B
0x180084c26  mov     [rbp+arg_8], edi
0x180084c29  lea     rax, [rbp+arg_8]
0x180084c2d  mov     qword ptr [rsp+80h+var_60], rax
0x180084c32  xor     r9d, r9d
0x180084c35  xor     r8d, r8d
0x180084c38  lea     rdx, word_180105896
0x180084c3f  lea     rcx, dword_180122070
0x180084c46  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084c4b  test    edi, edi
0x180084c4d  jle     loc_180084CEB
0x180084c53  movzx   edi, di
0x180084c56  or      edi, 80070000h
0x180084c5c  jmp     loc_180084CEB
0x180084c61  cmp     dword ptr [rbp+var_38], 2
0x180084c65  jnz     short loc_180084C6C
0x180084c67  xor     r9d, r9d
0x180084c6a  jmp     short loc_180084C73
0x180084c6c  mov     r9, [rbp+var_50]
0x180084c70  xor     r15d, r15d
0x180084c73  mov     [rsp+80h+var_60], r15d; int
0x180084c78  xor     r8d, r8d
0x180084c7b  lea     rdx, aSharedusercert; "sharedUserCertificates"
0x180084c82  mov     rcx, [r13+30h]
0x180084c86  call    I_CheckNgcApiAccessRight
0x180084c8b  mov     edi, eax
0x180084c8d  test    eax, eax
0x180084c8f  jns     short loc_180084CF4
0x180084c91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180084c98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180084c9d  test    al, al
0x180084c9f  jz      short loc_180084CBB
0x180084ca1  mov     rcx, [rbp+28h]; this
0x180084ca5  mov     r9d, edi; char *
0x180084ca8  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180084caf  mov     edx, 182h; void *
0x180084cb4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180084cb9  jmp     short loc_180084CEB
0x180084cbb  mov     eax, cs:dword_180122070
0x180084cc1  cmp     eax, 2
0x180084cc4  jbe     short loc_180084CEB
0x180084cc6  mov     [rbp+arg_8], edi
0x180084cc9  lea     rax, [rbp+arg_8]
0x180084ccd  mov     qword ptr [rsp+80h+var_60], rax
0x180084cd2  xor     r9d, r9d
0x180084cd5  xor     r8d, r8d
0x180084cd8  lea     rdx, byte_180105855
0x180084cdf  lea     rcx, dword_180122070
0x180084ce6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084ceb  mov     ecx, edi; int
0x180084ced  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180084cf2  mov     edi, eax
0x180084cf4  lea     rcx, [rbp+var_50]; void *
0x180084cf8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180084cfd  nop
0x180084cfe  lea     rcx, [rbp+StringSid]; void *
0x180084d02  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180084d07  jmp     loc_180084A4E
0x180084d0c  mov     eax, cs:dword_180122070
0x180084d12  cmp     eax, 4
0x180084d15  jbe     short loc_180084D40
0x180084d17  mov     [rbp+arg_8], 80090029h
0x180084d1e  lea     rax, [rbp+arg_8]
0x180084d22  mov     qword ptr [rsp+80h+var_60], rax
0x180084d27  xor     r9d, r9d
0x180084d2a  xor     r8d, r8d
0x180084d2d  lea     rdx, byte_1801058F9
0x180084d34  lea     rcx, dword_180122070
0x180084d3b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180084d40  mov     eax, 80090029h
0x180084d45  add     rsp, 80h
0x180084d4c  pop     r15
0x180084d4e  pop     r13
0x180084d50  pop     r12
0x180084d52  pop     rdi
0x180084d53  pop     rbp
0x180084d54  retn
```
