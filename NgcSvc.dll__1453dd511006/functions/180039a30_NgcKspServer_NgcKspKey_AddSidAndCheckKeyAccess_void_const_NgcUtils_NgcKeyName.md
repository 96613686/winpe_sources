# NgcKspServer::NgcKspKey::AddSidAndCheckKeyAccess(void * const,NgcUtils::NgcKeyName &)

- ea: `0x180039a30`
- end: `0x180039d6f`
- name: `?AddSidAndCheckKeyAccess@NgcKspKey@NgcKspServer@@KAJQEAXAEAVNgcKeyName@NgcUtils@@@Z`
- size: `831`
- prototype: `__int64 __fastcall(void *const, struct NgcUtils::NgcKeyName *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800126d0`
- `0x1800768f8`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180021f00`
- `0x1800281e0`
- `0x1800288a0`
- `0x180028d18`
- `0x18002a3bc`
- `0x18002c9d8`
- `0x180031c3c`
- `0x180034cf8`
- `0x180039a30`
- `0x180046d90`
- `0x18008f2dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c48`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039bda`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039bda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039c21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039c21`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039b47`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039b47`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180039c3e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180039c3e`

## string_xrefs

- `0x180039b7b`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x180039c67`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x180039d04`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcKspServer::NgcKspKey::AddSidAndCheckKeyAccess(void *const a1, struct NgcUtils::NgcKeyName *a2)
{
  __int64 v4; // rax
  wchar_t *v5; // rsi
  _QWORD *v6; // rbx
  int v7; // r9d
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rdx
  int v11; // r9d
  int v12; // eax
  unsigned __int8 *v13; // rdx
  BOOL v14; // ebx
  signed int LastError; // ebx
  DWORD LengthSid; // eax
  PSID v17; // rcx
  signed int v18; // ebx
  int v19; // r9d
  unsigned int v21; // [rsp+20h] [rbp-50h]
  unsigned int v22; // [rsp+20h] [rbp-50h]
  PSID *p_pSid; // [rsp+40h] [rbp-30h] BYREF
  PSID Sid; // [rsp+48h] [rbp-28h] BYREF
  char v25; // [rsp+50h] [rbp-20h]
  _BYTE v26[24]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  signed int v28; // [rsp+A8h] [rbp+38h] BYREF
  LPCWSTR StringSid; // [rsp+B0h] [rbp+40h] BYREF
  PSID pSid; // [rsp+B8h] [rbp+48h] BYREF

  v4 = *((_QWORD *)a2 + 1);
  if ( *((_QWORD *)a2 + 7) )
  {
    v5 = (wchar_t *)((char *)a2 + 40);
    if ( *((_QWORD *)a2 + 8) > 7u )
      v5 = *(wchar_t **)v5;
  }
  else
  {
    v5 = 0;
  }
  if ( *((_QWORD *)a2 + 11) )
  {
    v6 = (_QWORD *)((char *)a2 + 72);
    if ( *((_QWORD *)a2 + 12) > 7u )
      v6 = (_QWORD *)*v6;
  }
  else
  {
    v6 = 0;
  }
  StringSid = 0;
  if ( *(_QWORD *)a2 == v4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &StringSid,
        0);
      v8 = NgcKspCheckKeyAccessRight(a1, 1, 0, v7, v5, (__int64)v6, (LPWSTR *)&StringSid);
      v9 = v8;
      if ( v8 < 0 )
      {
        v10 = 1243;
LABEL_38:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          (const char *)(unsigned int)v8,
          v22);
        goto LABEL_44;
      }
      goto LABEL_16;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    v12 = NgcKspCheckKeyAccessRight(a1, 1, 0, v11, v5, (__int64)v6, (LPWSTR *)&StringSid);
    v9 = v12;
    if ( v12 >= 0 )
    {
LABEL_16:
      pSid = 0;
      p_pSid = &pSid;
      Sid = 0;
      v25 = 1;
      v14 = ConvertStringSidToSidW(StringSid, &Sid);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_pSid);
      if ( v14 )
      {
        LengthSid = GetLengthSid(pSid);
        std::vector<unsigned char>::vector<unsigned char>(v26, pSid, (char *)pSid + LengthSid);
        v9 = NgcUtils::NgcKeyName::SetSid(a2, v26);
        std::vector<unsigned char>::_Tidy(v26);
      }
      else
      {
        LastError = GetLastError();
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Win32(
            retaddr,
            (void *)0x4F9,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)LastError,
            v22);
        }
        else if ( (unsigned int)dword_180122070 > 2 )
        {
          v28 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_180104293,
            0,
            0,
            (__int64)&v28);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v9 = HResultToSecurityStatus(LastError);
      }
      v17 = pSid;
      pSid = 0;
      if ( v17 )
        LocalFree(v17);
      goto LABEL_44;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_44;
    v28 = v12;
    v13 = (unsigned __int8 *)&word_1801042C6;
LABEL_43:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      v13,
      0,
      0,
      (__int64)&v28);
    goto LABEL_44;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(*(PSID *)a2, (LPWSTR *)&StringSid) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v8 = NgcKspCheckKeyAccessRight(a1, 1, StringSid, v19, v5, (__int64)v6, 0);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v9 = 0;
        goto LABEL_44;
      }
      v10 = 1330;
      goto LABEL_38;
    }
    v9 = NgcKspCheckKeyAccessRight(a1, 1, StringSid, v19, v5, (__int64)v6, 0);
    if ( v9 < 0 && (unsigned int)dword_180122070 > 2 )
    {
      v28 = v9;
      v13 = (unsigned __int8 *)byte_180104235;
      goto LABEL_43;
    }
  }
  else
  {
    v18 = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x51C,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v18,
        v21);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      v28 = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&word_180104266,
        0,
        0,
        (__int64)&v28);
    }
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    v9 = HResultToSecurityStatus(v18);
  }
LABEL_44:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180039a30  push    rbp
0x180039a32  push    rbx
0x180039a33  push    rsi
0x180039a34  push    rdi
0x180039a35  push    r14
0x180039a37  mov     rbp, rsp
0x180039a3a  sub     rsp, 70h
0x180039a3e  mov     rdi, rdx
0x180039a41  mov     r14, rcx
0x180039a44  mov     rax, [rdx+8]
0x180039a48  cmp     qword ptr [rdx+38h], 0
0x180039a4d  jnz     short loc_180039A53
0x180039a4f  xor     esi, esi
0x180039a51  jmp     short loc_180039A61
0x180039a53  lea     rsi, [rdx+28h]
0x180039a57  cmp     qword ptr [rsi+18h], 7
0x180039a5c  jbe     short loc_180039A61
0x180039a5e  mov     rsi, [rsi]
0x180039a61  cmp     qword ptr [rdx+58h], 0
0x180039a66  jnz     short loc_180039A6C
0x180039a68  xor     ebx, ebx
0x180039a6a  jmp     short loc_180039A7A
0x180039a6c  lea     rbx, [rdx+48h]
0x180039a70  cmp     qword ptr [rbx+18h], 7
0x180039a75  jbe     short loc_180039A7A
0x180039a77  mov     rbx, [rbx]
0x180039a7a  mov     [rbp+StringSid], 0
0x180039a82  cmp     [rdx], rax
0x180039a85  jnz     loc_180039C2C
0x180039a8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180039a92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180039a97  xor     edx, edx
0x180039a99  lea     rcx, [rbp+StringSid]
0x180039a9d  test    al, al
0x180039a9f  jz      short loc_180039AD8
0x180039aa1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039aa6  lea     rax, [rbp+StringSid]
0x180039aaa  mov     [rsp+70h+var_40], rax
0x180039aaf  mov     [rsp+70h+var_48], rbx
0x180039ab4  mov     qword ptr [rsp+70h+var_50], rsi; unsigned int
0x180039ab9  xor     r8d, r8d
0x180039abc  lea     edx, [r8+1]
0x180039ac0  mov     rcx, r14
0x180039ac3  call    NgcKspCheckKeyAccessRight
0x180039ac8  mov     ebx, eax
0x180039aca  test    eax, eax
0x180039acc  jns     short loc_180039B23
0x180039ace  mov     edx, 4DBh
0x180039ad3  jmp     loc_180039D04
0x180039ad8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039add  lea     rax, [rbp+StringSid]
0x180039ae1  mov     [rsp+70h+var_40], rax
0x180039ae6  mov     [rsp+70h+var_48], rbx
0x180039aeb  mov     qword ptr [rsp+70h+var_50], rsi
0x180039af0  xor     r8d, r8d
0x180039af3  lea     edx, [r8+1]
0x180039af7  mov     rcx, r14
0x180039afa  call    NgcKspCheckKeyAccessRight
0x180039aff  mov     ebx, eax
0x180039b01  test    eax, eax
0x180039b03  jns     short loc_180039B23
0x180039b05  mov     ecx, cs:dword_180122070
0x180039b0b  cmp     ecx, 2
0x180039b0e  jbe     loc_180039D59
0x180039b14  mov     [rbp+arg_8], eax
0x180039b17  lea     rdx, word_1801042C6
0x180039b1e  jmp     loc_180039D3D
0x180039b23  mov     [rbp+pSid], 0
0x180039b2b  lea     rax, [rbp+pSid]
0x180039b2f  mov     [rbp+var_30], rax
0x180039b33  mov     [rbp+Sid], 0
0x180039b3b  mov     [rbp+var_20], 1
0x180039b3f  lea     rdx, [rbp+Sid]; Sid
0x180039b43  mov     rcx, [rbp+StringSid]; StringSid
0x180039b47  call    cs:__imp_ConvertStringSidToSidW
0x180039b4d  mov     ebx, eax
0x180039b4f  lea     rcx, [rbp+var_30]
0x180039b53  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180039b58  test    ebx, ebx
0x180039b5a  jnz     short loc_180039BD6
0x180039b5c  call    cs:__imp_GetLastError
0x180039b62  mov     ebx, eax
0x180039b64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180039b6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180039b70  test    al, al
0x180039b72  jz      short loc_180039B8E
0x180039b74  mov     rcx, [rbp+28h]; this
0x180039b78  mov     r9d, ebx; char *
0x180039b7b  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180039b82  mov     edx, 4F9h; void *
0x180039b87  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180039b8c  jmp     short loc_180039BBE
0x180039b8e  mov     eax, cs:dword_180122070
0x180039b94  cmp     eax, 2
0x180039b97  jbe     short loc_180039BBE
0x180039b99  mov     [rbp+arg_8], ebx
0x180039b9c  lea     rax, [rbp+arg_8]
0x180039ba0  mov     qword ptr [rsp+70h+var_50], rax
0x180039ba5  xor     r9d, r9d
0x180039ba8  xor     r8d, r8d
0x180039bab  lea     rdx, byte_180104293
0x180039bb2  lea     rcx, dword_180122070
0x180039bb9  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180039bbe  test    ebx, ebx
0x180039bc0  jle     short loc_180039BCB
0x180039bc2  movzx   ebx, bx
0x180039bc5  or      ebx, 80070000h
0x180039bcb  mov     ecx, ebx; int
0x180039bcd  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180039bd2  mov     ebx, eax
0x180039bd4  jmp     short loc_180039C0C
0x180039bd6  mov     rcx, [rbp+pSid]; pSid
0x180039bda  call    cs:__imp_GetLengthSid
0x180039be0  mov     r8d, eax
0x180039be3  mov     rdx, [rbp+pSid]
0x180039be7  add     r8, rdx
0x180039bea  lea     rcx, [rbp+var_18]
0x180039bee  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x180039bf3  nop
0x180039bf4  lea     rdx, [rbp+var_18]
0x180039bf8  mov     rcx, rdi
0x180039bfb  call    ?SetSid@NgcKeyName@NgcUtils@@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcUtils::NgcKeyName::SetSid(std::vector<uchar> const &)
0x180039c00  mov     ebx, eax
0x180039c02  lea     rcx, [rbp+var_18]
0x180039c06  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180039c0b  nop
0x180039c0c  mov     rcx, [rbp+pSid]; hMem
0x180039c10  mov     [rbp+pSid], 0
0x180039c18  test    rcx, rcx
0x180039c1b  jz      loc_180039D59
0x180039c21  call    cs:__imp_LocalFree
0x180039c27  jmp     loc_180039D59
0x180039c2c  xor     edx, edx
0x180039c2e  lea     rcx, [rbp+StringSid]
0x180039c32  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039c37  lea     rdx, [rbp+StringSid]; StringSid
0x180039c3b  mov     rcx, [rdi]; Sid
0x180039c3e  call    cs:__imp_ConvertSidToStringSidW
0x180039c44  test    eax, eax
0x180039c46  jnz     short loc_180039CC5
0x180039c48  call    cs:__imp_GetLastError
0x180039c4e  mov     ebx, eax
0x180039c50  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180039c57  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180039c5c  test    al, al
0x180039c5e  jz      short loc_180039C7A
0x180039c60  mov     rcx, [rbp+28h]; this
0x180039c64  mov     r9d, ebx; char *
0x180039c67  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180039c6e  mov     edx, 51Ch; void *
0x180039c73  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180039c78  jmp     short loc_180039CAA
0x180039c7a  mov     eax, cs:dword_180122070
0x180039c80  cmp     eax, 2
0x180039c83  jbe     short loc_180039CAA
0x180039c85  mov     [rbp+arg_8], ebx
0x180039c88  lea     rax, [rbp+arg_8]
0x180039c8c  mov     qword ptr [rsp+70h+var_50], rax
0x180039c91  xor     r9d, r9d
0x180039c94  xor     r8d, r8d
0x180039c97  lea     rdx, word_180104266
0x180039c9e  lea     rcx, dword_180122070
0x180039ca5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180039caa  test    ebx, ebx
0x180039cac  jle     short loc_180039CB7
0x180039cae  movzx   ebx, bx
0x180039cb1  or      ebx, 80070000h
0x180039cb7  mov     ecx, ebx; int
0x180039cb9  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180039cbe  mov     ebx, eax
0x180039cc0  jmp     loc_180039D59
0x180039cc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180039ccc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180039cd1  mov     [rsp+70h+var_40], 0
0x180039cda  mov     r8, [rbp+StringSid]
0x180039cde  mov     edx, 1
0x180039ce3  mov     rcx, r14
0x180039ce6  mov     [rsp+70h+var_48], rbx
0x180039ceb  mov     qword ptr [rsp+70h+var_50], rsi; int
0x180039cf0  test    al, al
0x180039cf2  jz      short loc_180039D1D
0x180039cf4  call    NgcKspCheckKeyAccessRight
0x180039cf9  mov     ebx, eax
0x180039cfb  test    eax, eax
0x180039cfd  jns     short loc_180039D19
0x180039cff  mov     edx, 532h; void *
0x180039d04  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180039d0b  mov     r9d, eax; char *
0x180039d0e  mov     rcx, [rbp+28h]; this
0x180039d12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d17  jmp     short loc_180039D59
0x180039d19  xor     ebx, ebx
0x180039d1b  jmp     short loc_180039D59
0x180039d1d  call    NgcKspCheckKeyAccessRight
0x180039d22  mov     ebx, eax
0x180039d24  test    eax, eax
0x180039d26  jns     short loc_180039D59
0x180039d28  mov     eax, cs:dword_180122070
0x180039d2e  cmp     eax, 2
0x180039d31  jbe     short loc_180039D59
0x180039d33  mov     [rbp+arg_8], ebx
0x180039d36  lea     rdx, byte_180104235
0x180039d3d  lea     rax, [rbp+arg_8]
0x180039d41  mov     qword ptr [rsp+70h+var_50], rax
0x180039d46  xor     r9d, r9d
0x180039d49  xor     r8d, r8d
0x180039d4c  lea     rcx, dword_180122070
0x180039d53  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180039d58  nop
0x180039d59  lea     rcx, [rbp+StringSid]; void *
0x180039d5d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180039d62  mov     eax, ebx
0x180039d64  add     rsp, 70h
0x180039d68  pop     r14
0x180039d6a  pop     rdi
0x180039d6b  pop     rsi
0x180039d6c  pop     rbx
0x180039d6d  pop     rbp
0x180039d6e  retn
```
