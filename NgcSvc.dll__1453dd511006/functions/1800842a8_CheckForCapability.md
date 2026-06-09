# CheckForCapability

- ea: `0x1800842a8`
- end: `0x180084428`
- name: `CheckForCapability`
- size: `384`
- prototype: `__int64 __fastcall(void *, LPCWSTR StringSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180084430`

## callees

- `0x180028d18`
- `0x18002c9d8`
- `0x1800320a0`
- `0x180034cf8`
- `0x180045d60`
- `0x180046d90`
- `0x1800842a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084363`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800843e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800843e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180084405`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180084355`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180084355`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800842f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800842f3`

## string_xrefs

- `0x180084380`: `onecore\ds\security\ngc\kspsvc\svc\ticketsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckForCapability(void *a1, LPCWSTR StringSid, bool *a3)
{
  DWORD LastError; // ebx
  __int64 v6; // rdx
  __int16 *v7; // rdx
  HLOCAL v8; // rcx
  HLOCAL v9; // rcx
  unsigned int v11; // [rsp+20h] [rbp-40h]
  HLOCAL hMem; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-20h] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h] BYREF
  char v16; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  int v18; // [rsp+80h] [rbp+20h] BYREF
  DWORD v19; // [rsp+88h] [rbp+28h] BYREF

  NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v13, a1);
  *a3 = 0;
  hMem = 0;
  p_hMem = &hMem;
  Sid = 0;
  v16 = 1;
  LODWORD(StringSid) = ConvertStringSidToSidW(StringSid, &Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( !(_DWORD)StringSid )
  {
    LastError = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v6 = 1064;
LABEL_9:
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ticketsrv.cpp",
        (const char *)LastError,
        v11);
      goto LABEL_13;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
    {
LABEL_13:
      if ( (int)LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = hMem;
      hMem = 0;
      if ( v8 )
        LocalFree(v8);
      goto LABEL_20;
    }
    v7 = word_1801054A2;
    goto LABEL_12;
  }
  v18 = 0;
  if ( !(unsigned int)CheckTokenCapability(-5, hMem, &v18) )
  {
    LastError = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v6 = 1086;
      goto LABEL_9;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_13;
    v7 = &word_180105476;
LABEL_12:
    v19 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)v7,
      0,
      0,
      (__int64)&v19);
    goto LABEL_13;
  }
  *a3 = v18 != 0;
  v9 = hMem;
  hMem = 0;
  if ( v9 )
    LocalFree(v9);
  LastError = 0;
LABEL_20:
  NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v13);
  return LastError;
}

```

## disassembly

```asm
0x1800842a8  mov     [rsp-8+arg_0], rbx
0x1800842ad  mov     [rsp-8+arg_8], rdi
0x1800842b2  push    rbp
0x1800842b3  mov     rbp, rsp
0x1800842b6  sub     rsp, 60h
0x1800842ba  mov     rdi, r8
0x1800842bd  mov     rbx, rdx
0x1800842c0  mov     rdx, rcx; void *
0x1800842c3  lea     rcx, [rbp+var_28]; this
0x1800842c7  call    ??0RpcCallerImpersonator@NgcUtils@@QEAA@QEAX@Z; NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator(void * const)
0x1800842cc  nop
0x1800842cd  mov     byte ptr [rdi], 0
0x1800842d0  mov     [rbp+hMem], 0
0x1800842d8  lea     rax, [rbp+hMem]
0x1800842dc  mov     [rbp+var_20], rax
0x1800842e0  mov     [rbp+Sid], 0
0x1800842e8  mov     [rbp+var_10], 1
0x1800842ec  lea     rdx, [rbp+Sid]; Sid
0x1800842f0  mov     rcx, rbx; StringSid
0x1800842f3  call    cs:__imp_ConvertStringSidToSidW
0x1800842f9  mov     ebx, eax
0x1800842fb  lea     rcx, [rbp+var_20]
0x1800842ff  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180084304  test    ebx, ebx
0x180084306  jnz     short loc_18008433F
0x180084308  call    cs:__imp_GetLastError
0x18008430e  mov     ebx, eax
0x180084310  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180084317  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18008431c  test    al, al
0x18008431e  jz      short loc_180084327
0x180084320  mov     edx, 428h
0x180084325  jmp     short loc_180084380
0x180084327  mov     eax, cs:dword_180122070
0x18008432d  cmp     eax, 2
0x180084330  jbe     loc_1800843C5
0x180084336  lea     rdx, word_1801054A2
0x18008433d  jmp     short loc_1800843A7
0x18008433f  mov     [rbp+arg_10], 0
0x180084346  lea     r8, [rbp+arg_10]
0x18008434a  mov     rdx, [rbp+hMem]
0x18008434e  mov     rcx, 0FFFFFFFFFFFFFFFBh
0x180084355  call    cs:__imp_CheckTokenCapability
0x18008435b  test    eax, eax
0x18008435d  jnz     loc_1800843EB
0x180084363  call    cs:__imp_GetLastError
0x180084369  mov     ebx, eax
0x18008436b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180084372  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180084377  test    al, al
0x180084379  jz      short loc_180084395
0x18008437b  mov     edx, 43Eh; void *
0x180084380  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180084387  mov     r9d, ebx; char *
0x18008438a  mov     rcx, [rbp+8]; this
0x18008438e  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180084393  jmp     short loc_1800843C5
0x180084395  mov     eax, cs:dword_180122070
0x18008439b  cmp     eax, 2
0x18008439e  jbe     short loc_1800843C5
0x1800843a0  lea     rdx, word_180105476
0x1800843a7  lea     rax, [rbp+arg_18]
0x1800843ab  mov     qword ptr [rsp+60h+var_40], rax
0x1800843b0  mov     [rbp+arg_18], ebx
0x1800843b3  xor     r9d, r9d
0x1800843b6  xor     r8d, r8d
0x1800843b9  lea     rcx, dword_180122070
0x1800843c0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800843c5  test    ebx, ebx
0x1800843c7  jle     short loc_1800843D2
0x1800843c9  movzx   ebx, bx
0x1800843cc  or      ebx, 80070000h
0x1800843d2  mov     rcx, [rbp+hMem]; hMem
0x1800843d6  mov     [rbp+hMem], 0
0x1800843de  test    rcx, rcx
0x1800843e1  jz      short loc_18008440D
0x1800843e3  call    cs:__imp_LocalFree
0x1800843e9  jmp     short loc_18008440D
0x1800843eb  cmp     [rbp+arg_10], 0
0x1800843ef  setnz   al
0x1800843f2  mov     [rdi], al
0x1800843f4  mov     rcx, [rbp+hMem]; hMem
0x1800843f8  mov     [rbp+hMem], 0
0x180084400  test    rcx, rcx
0x180084403  jz      short loc_18008440B
0x180084405  call    cs:__imp_LocalFree
0x18008440b  xor     ebx, ebx
0x18008440d  lea     rcx, [rbp+var_28]; this
0x180084411  call    ??1RpcCallerImpersonator@NgcUtils@@QEAA@XZ; NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator(void)
0x180084416  mov     eax, ebx
0x180084418  mov     rbx, [rsp+60h+arg_0]
0x18008441d  mov     rdi, [rsp+60h+arg_8]
0x180084422  add     rsp, 60h
0x180084426  pop     rbp
0x180084427  retn
```
