# NgcKspServer::NgcEphemeralKey::Create(void * const,ushort const *,ushort const *,bool)

- ea: `0x1800770d0`
- end: `0x1800773b0`
- name: `?Create@NgcEphemeralKey@NgcKspServer@@EEAAJQEAXPEBG1_N@Z`
- size: `736`
- prototype: `int(NgcKspServer::NgcEphemeralKey *__hidden this, void *const, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000782c`
- `0x180010a94`
- `0x180028d18`
- `0x180046d90`
- `0x1800533a4`
- `0x1800770d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077104`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180077104`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800770f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800770f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180077174`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007726e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007739b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180077174`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007726e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007739b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077140`
- `ncrypt!NCryptSetProperty` at `0x18007723c`
- `ncrypt!NCryptSetProperty` at `0x1800772ee`
- `ncrypt!NCryptSetProperty` at `0x180077346`
- `ncrypt!NCryptSetProperty` at `0x18007735d`
- `ncrypt!NCryptSetProperty` at `0x18007723c`
- `ncrypt!NCryptSetProperty` at `0x1800772ee`
- `ncrypt!NCryptSetProperty` at `0x180077346`
- `ncrypt!NCryptSetProperty` at `0x18007735d`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800771d3`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800772a5`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800771d3`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800772a5`

## string_xrefs

- `0x180077122`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x1800771e6`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x180077252`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcKspServer::NgcEphemeralKey::Create(
        NgcKspServer::NgcEphemeralKey *this,
        void *const a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  RTL_SRWLOCK *v6; // rbx
  const char *v7; // r9
  char IsEnabled; // al
  char v10; // di
  char *v11; // rcx
  SECURITY_STATUS PersistedKey; // eax
  SECURITY_STATUS v13; // edi
  char v14; // al
  NCRYPT_HANDLE v15; // rcx
  SECURITY_STATUS v16; // r14d
  __int64 v17; // rdx
  char *v18; // rdx
  char v19; // al
  NCRYPT_HANDLE v20; // rcx
  int dwLegacyKeySpec; // [rsp+20h] [rbp-28h]
  int dwLegacyKeySpeca; // [rsp+20h] [rbp-28h]
  BYTE v23[8]; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  int pbInput; // [rsp+80h] [rbp+38h] BYREF

  v6 = (RTL_SRWLOCK *)((char *)this + 272);
  AcquireSRWLockExclusive((PSRWLOCK)this + 34);
  v24[0] = v6;
  if ( (unsigned int)_o__wcsicmp(a4, L"RSA") )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)0x242B,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        v7);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v24[0]) = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&dword_180100D24,
        0,
        0,
        (__int64)v24);
    }
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
    return 2148073511LL;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v10 = *((_BYTE *)this + 264);
  v11 = (char *)this + 320;
  if ( IsEnabled )
  {
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(v11);
    PersistedKey = NCryptCreatePersistedKey(
                     *((_QWORD *)this + 39),
                     (NCRYPT_KEY_HANDLE *)this + 41,
                     a4,
                     0,
                     0,
                     v10 != 0 ? 0x40 : 0);
    v13 = PersistedKey;
    if ( PersistedKey < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2440,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)PersistedKey,
        dwLegacyKeySpec);
LABEL_33:
      if ( v6 )
        ReleaseSRWLockExclusive(v6);
      return (unsigned int)v13;
    }
    v13 = 0;
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(v11);
    v13 = NCryptCreatePersistedKey(
            *((_QWORD *)this + 39),
            (NCRYPT_KEY_HANDLE *)this + 41,
            a4,
            0,
            0,
            v10 != 0 ? 0x40 : 0);
    if ( v13 < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_33;
      v18 = byte_180100CEB;
      goto LABEL_22;
    }
  }
  pbInput = 2048;
  v14 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v15 = *((_QWORD *)this + 41);
  if ( !v14 )
  {
    v13 = NCryptSetProperty(v15, L"Length", (PBYTE)&pbInput, 4u, 0);
    if ( v13 < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_33;
      v18 = byte_180100CB3;
      goto LABEL_22;
    }
    goto LABEL_26;
  }
  v16 = NCryptSetProperty(v15, L"Length", (PBYTE)&pbInput, 4u, 0);
  if ( v16 >= 0 )
  {
LABEL_26:
    *(_DWORD *)v23 = 2;
    v19 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
    v20 = *((_QWORD *)this + 41);
    if ( v19 )
    {
      v16 = NCryptSetProperty(v20, L"Key Usage", v23, 4u, 0);
      if ( v16 < 0 )
      {
        v17 = 9337;
        goto LABEL_16;
      }
LABEL_32:
      *((_DWORD *)this + 58) = 2;
      *((_WORD *)this + 148) = 256;
      goto LABEL_33;
    }
    v13 = NCryptSetProperty(v20, L"Key Usage", v23, 4u, 0);
    if ( v13 >= 0 )
      goto LABEL_32;
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_33;
    v18 = (char *)&dword_180100C7C;
LABEL_22:
    LODWORD(v24[0]) = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)v18,
      0,
      0,
      (__int64)v24);
    goto LABEL_33;
  }
  v17 = 9309;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
    (const char *)(unsigned int)v16,
    dwLegacyKeySpeca);
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800770d0  push    rbp
0x1800770d2  push    rbx
0x1800770d3  push    rsi
0x1800770d4  push    rdi
0x1800770d5  push    r14
0x1800770d7  push    r15
0x1800770d9  mov     rbp, rsp
0x1800770dc  sub     rsp, 48h
0x1800770e0  mov     r14, r9
0x1800770e3  mov     rsi, rcx
0x1800770e6  lea     rbx, [rcx+110h]
0x1800770ed  mov     rcx, rbx; SRWLock
0x1800770f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800770f6  mov     [rbp+var_10], rbx
0x1800770fa  lea     rdx, aRsa; "RSA"
0x180077101  mov     rcx, r14
0x180077104  call    cs:__imp__o__wcsicmp
0x18007710a  test    eax, eax
0x18007710c  jz      short loc_180077184
0x18007710e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180077115  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007711a  test    al, al
0x18007711c  jz      short loc_180077135
0x18007711e  mov     rcx, [rbp+30h]; this
0x180077122  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180077129  mov     edx, 242Bh; void *
0x18007712e  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180077133  jmp     short loc_18007716C
0x180077135  mov     eax, cs:dword_180122070
0x18007713b  cmp     eax, 2
0x18007713e  jbe     short loc_18007716C
0x180077140  call    cs:__imp_GetLastError
0x180077146  mov     dword ptr [rbp+var_10], eax
0x180077149  lea     rax, [rbp+var_10]
0x18007714d  mov     qword ptr [rsp+48h+dwLegacyKeySpec], rax
0x180077152  xor     r9d, r9d
0x180077155  xor     r8d, r8d
0x180077158  lea     rdx, dword_180100D24
0x18007715f  lea     rcx, dword_180122070
0x180077166  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007716b  nop
0x18007716c  test    rbx, rbx
0x18007716f  jz      short loc_18007717A
0x180077171  mov     rcx, rbx; SRWLock
0x180077174  call    cs:__imp_ReleaseSRWLockExclusive
0x18007717a  mov     eax, 80090027h
0x18007717f  jmp     loc_1800773A3
0x180077184  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007718b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180077190  mov     dil, [rsi+108h]
0x180077197  lea     rcx, [rsi+140h]
0x18007719e  lea     r15, [rcx+8]
0x1800771a2  test    al, al
0x1800771a4  jz      loc_18007727C
0x1800771aa  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x1800771af  neg     dil
0x1800771b2  sbb     eax, eax
0x1800771b4  and     eax, 40h
0x1800771b7  mov     [rsp+48h+dwFlags], eax; dwFlags
0x1800771bb  mov     [rsp+48h+dwLegacyKeySpec], 0; int
0x1800771c3  xor     r9d, r9d; pszKeyName
0x1800771c6  mov     r8, r14; pszAlgId
0x1800771c9  mov     rdx, r15; phKey
0x1800771cc  mov     rcx, [rsi+138h]; hProvider
0x1800771d3  call    cs:__imp_NCryptCreatePersistedKey
0x1800771d9  mov     edi, eax
0x1800771db  test    eax, eax
0x1800771dd  jns     short loc_1800771FC
0x1800771df  mov     rcx, [rbp+30h]; this
0x1800771e3  mov     r9d, eax; char *
0x1800771e6  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800771ed  mov     edx, 2440h; void *
0x1800771f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771f7  jmp     loc_180077393
0x1800771fc  xor     edi, edi
0x1800771fe  mov     [rbp+pbInput], 800h
0x180077205  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007720c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180077211  mov     rcx, [rsi+148h]; hObject
0x180077218  mov     [rsp+48h+dwLegacyKeySpec], 0; int
0x180077220  mov     r15d, 4
0x180077226  lea     r8, [rbp+pbInput]; pbInput
0x18007722a  lea     rdx, aLength; "Length"
0x180077231  mov     r9d, r15d; cbInput
0x180077234  test    al, al
0x180077236  jz      loc_1800772EE
0x18007723c  call    cs:__imp_NCryptSetProperty
0x180077242  mov     r14d, eax
0x180077245  test    eax, eax
0x180077247  jns     loc_180077312
0x18007724d  mov     edx, 245Dh; void *
0x180077252  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180077259  mov     r9d, r14d; char *
0x18007725c  mov     rcx, [rbp+30h]; this
0x180077260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077265  nop
0x180077266  test    rbx, rbx
0x180077269  jz      short loc_180077274
0x18007726b  mov     rcx, rbx; SRWLock
0x18007726e  call    cs:__imp_ReleaseSRWLockExclusive
0x180077274  mov     eax, r14d
0x180077277  jmp     loc_1800773A3
0x18007727c  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180077281  neg     dil
0x180077284  sbb     eax, eax
0x180077286  and     eax, 40h
0x180077289  mov     [rsp+48h+dwFlags], eax; dwFlags
0x18007728d  mov     [rsp+48h+dwLegacyKeySpec], 0; dwLegacyKeySpec
0x180077295  xor     r9d, r9d; pszKeyName
0x180077298  mov     r8, r14; pszAlgId
0x18007729b  mov     rdx, r15; phKey
0x18007729e  mov     rcx, [rsi+138h]; hProvider
0x1800772a5  call    cs:__imp_NCryptCreatePersistedKey
0x1800772ab  mov     edi, eax
0x1800772ad  test    eax, eax
0x1800772af  jns     loc_1800771FE
0x1800772b5  mov     ecx, cs:dword_180122070
0x1800772bb  cmp     ecx, 2
0x1800772be  jbe     loc_180077393
0x1800772c4  lea     rdx, byte_180100CEB
0x1800772cb  lea     rax, [rbp+var_10]
0x1800772cf  xor     r9d, r9d
0x1800772d2  mov     qword ptr [rsp+48h+dwLegacyKeySpec], rax
0x1800772d7  xor     r8d, r8d
0x1800772da  mov     dword ptr [rbp+var_10], edi
0x1800772dd  lea     rcx, dword_180122070
0x1800772e4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800772e9  jmp     loc_180077393
0x1800772ee  call    cs:__imp_NCryptSetProperty
0x1800772f4  mov     edi, eax
0x1800772f6  test    eax, eax
0x1800772f8  jns     short loc_180077312
0x1800772fa  mov     eax, cs:dword_180122070
0x180077300  cmp     eax, 2
0x180077303  jbe     loc_180077393
0x180077309  lea     rdx, byte_180100CB3
0x180077310  jmp     short loc_1800772CB
0x180077312  mov     dword ptr [rbp+var_18], 2
0x180077319  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180077320  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180077325  mov     [rsp+48h+dwLegacyKeySpec], 0; dwFlags
0x18007732d  mov     r9d, r15d; cbInput
0x180077330  lea     r8, [rbp+var_18]; pbInput
0x180077334  lea     rdx, aKeyUsage; "Key Usage"
0x18007733b  mov     rcx, [rsi+148h]; hObject
0x180077342  test    al, al
0x180077344  jz      short loc_18007735D
0x180077346  call    cs:__imp_NCryptSetProperty
0x18007734c  mov     r14d, eax
0x18007734f  test    eax, eax
0x180077351  jns     short loc_180077380
0x180077353  mov     edx, 2479h
0x180077358  jmp     loc_180077252
0x18007735d  call    cs:__imp_NCryptSetProperty
0x180077363  mov     edi, eax
0x180077365  test    eax, eax
0x180077367  jns     short loc_180077380
0x180077369  mov     eax, cs:dword_180122070
0x18007736f  cmp     eax, 2
0x180077372  jbe     short loc_180077393
0x180077374  lea     rdx, dword_180100C7C
0x18007737b  jmp     loc_1800772CB
0x180077380  mov     dword ptr [rsi+0E8h], 2
0x18007738a  mov     word ptr [rsi+128h], 100h
0x180077393  test    rbx, rbx
0x180077396  jz      short loc_1800773A1
0x180077398  mov     rcx, rbx; SRWLock
0x18007739b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800773a1  mov     eax, edi
0x1800773a3  add     rsp, 48h
0x1800773a7  pop     r15
0x1800773a9  pop     r14
0x1800773ab  pop     rdi
0x1800773ac  pop     rsi
0x1800773ad  pop     rbx
0x1800773ae  pop     rbp
0x1800773af  retn
```
