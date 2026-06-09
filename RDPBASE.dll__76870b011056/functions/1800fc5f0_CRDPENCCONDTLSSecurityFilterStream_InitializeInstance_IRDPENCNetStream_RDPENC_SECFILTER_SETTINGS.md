# CRDPENCCONDTLSSecurityFilterStream::InitializeInstance(IRDPENCNetStream *,RDPENC_SECFILTER_SETTINGS *)

- ea: `0x1800fc5f0`
- end: `0x1800fcd56`
- name: `?InitializeInstance@CRDPENCCONDTLSSecurityFilterStream@@UEAAJPEAUIRDPENCNetStream@@PEAURDPENC_SECFILTER_SETTINGS@@@Z`
- size: `1894`
- prototype: `__int64 __fastcall(CRDPENCCONDTLSSecurityFilterStream *__hidden this, struct IRDPENCNetStream *, struct RDPENC_SECFILTER_SETTINGS *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002550`
- `0x180019a80`
- `0x180019ab0`
- `0x180038984`
- `0x180046690`
- `0x180046a84`
- `0x18004a888`
- `0x1800711c8`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x1800f9f88`
- `0x1800fa1f8`
- `0x1800fa848`
- `0x1800fc5f0`
- `0x1800fe620`
- `0x1801614c4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fcaba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fcaba`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800fcc23`
- `ntdll!RtlIpv6StringToAddressW` at `0x1800fcc23`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800fcbf9`
- `ntdll!RtlIpv4StringToAddressW` at `0x1800fcbf9`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800fc93d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800fc93d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800fcab0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800fcab0`

## string_xrefs

- `0x1800fc88c`: `StringCchCopy failed`
- `0x1800fc6ec`: `Failed to create Context Pool`
- `0x1800fc750`: `StringCbCopy failed`
- `0x1800fccb1`: `Failed to create session allowed thread`
- `0x1800fc650`: `CRDPENCCONDTLSSecurityFilterStream::InitializeInstance`
- `0x1800fccfa`: `Failed to start session allowed thread`

## pseudocode

```c
__int64 __fastcall CRDPENCCONDTLSSecurityFilterStream::InitializeInstance(
        CRDPENCCONDTLSSecurityFilterStream *this,
        struct IRDPENCNetStream *a2,
        struct RDPENC_SECFILTER_SETTINGS *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r9d
  _QWORD *v9; // r12
  signed int Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // edx
  const char *v13; // rcx
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // rcx
  size_t v16; // r11
  unsigned __int64 v17; // rbx
  size_t v18; // rax
  unsigned __int16 *v19; // rax
  __int64 v20; // rbx
  const CERT_CONTEXT *v21; // rcx
  unsigned int v22; // eax
  void *v23; // rax
  const unsigned __int16 *v24; // rcx
  unsigned __int64 v25; // rbx
  unsigned __int16 *v26; // rax
  void *v27; // rax
  signed int LastError; // eax
  const WCHAR *v29; // rcx
  _DWORD *v30; // rbx
  unsigned __int64 v32; // [rsp+30h] [rbp-89h] BYREF
  unsigned __int64 v33; // [rsp+38h] [rbp-81h] BYREF
  LPCWSTR Terminator; // [rsp+40h] [rbp-79h] BYREF
  const char *v35; // [rsp+48h] [rbp-71h] BYREF
  struct in_addr Addr[4]; // [rsp+50h] [rbp-69h] BYREF

  v32 = 0;
  v33 = 0;
  Terminator = 0;
  memset_0(Addr, 0, 0x80u);
  if ( (unsigned int)CallbackContext > 4 )
  {
    v35 = "CRDPENCCONDTLSSecurityFilterStream::InitializeInstance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)&word_1801C4E46,
      0,
      v8,
      (__int64)&v35);
  }
  v9 = (_QWORD *)((char *)this + 248);
  if ( a2 != *((struct IRDPENCNetStream **)this + 31) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 248);
    *v9 = a2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 248);
  }
  *(_QWORD *)((char *)this + 236) = 0;
  Instance = CTSObjectPool<CRDPDTLSSecFilterContext>::CreateInstance(v7, v6, (char *)this + 328);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 17;
    v13 = "Failed to create Context Pool";
    goto LABEL_102;
  }
  v14 = (unsigned __int16 *)((char *)this + 112);
  if ( *(_QWORD *)a3 )
  {
    Instance = StringCbCopyW(v14, 0x42u, *(const unsigned __int16 **)a3);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 18;
      goto LABEL_16;
    }
  }
  else
  {
    Instance = StringCbCopyW(v14, 0x42u, L"DefaultListener");
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 19;
LABEL_16:
      v13 = "StringCbCopy failed";
LABEL_102:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        (unsigned int)WPP_310100a96f023abf06e7a5d6677d258d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v13,
        Instance);
      goto LABEL_103;
    }
  }
  v15 = (unsigned __int16 *)*((_QWORD *)a3 + 2);
  if ( v15 )
  {
    Instance = StringCchLengthW(v15, 0x104u, &v32);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 20;
      goto LABEL_28;
    }
    v17 = v32 + 1;
    v18 = 2 * (v32 + 1);
    if ( !is_mul_ok(v32 + 1, 2u) )
      v18 = v16;
    v19 = (unsigned __int16 *)operator new(v18);
    *((_QWORD *)this + 23) = v19;
    if ( !v19 )
    {
LABEL_32:
      Instance = -2147024882;
LABEL_103:
      CRDPENCCONDTLSSecurityFilterStream::Terminate((CRDPENCCONDTLSSecurityFilterStream *)((char *)this - 56));
      return (unsigned int)Instance;
    }
    Instance = StringCchCopyW(v19, v17, *((const unsigned __int16 **)a3 + 2));
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 21;
      goto LABEL_38;
    }
  }
  v20 = *((_QWORD *)a3 + 3);
  if ( v20 != *((_QWORD *)this + 35) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 280);
    *((_QWORD *)this + 35) = v20;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  }
  *((_DWORD *)this + 48) = *((_DWORD *)a3 + 8);
  *((_BYTE *)this + 196) = *((_BYTE *)a3 + 36);
  *((_BYTE *)this + 197) = *((_BYTE *)a3 + 37);
  Instance = CRDPENCCONDTLSSecurityFilterStream::AdjustEncryptionLevel(
               (CRDPENCCONDTLSSecurityFilterStream *)v15,
               (unsigned __int8 *)this + 197);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 22;
    v13 = "AdjustEncryptionLevel failed";
    goto LABEL_102;
  }
  v21 = (const CERT_CONTEXT *)*((_QWORD *)a3 + 6);
  if ( v21 )
    *((_QWORD *)this + 25) = CertDuplicateCertificateContext(v21);
  if ( *((_QWORD *)this + 25) )
  {
    *((_DWORD *)this + 54) = 20;
    v27 = operator new(0x14u);
    *((_QWORD *)this + 26) = v27;
    if ( !v27 )
      goto LABEL_32;
    if ( !CertGetCertificateContextProperty(*((PCCERT_CONTEXT *)this + 25), 3u, v27, (DWORD *)this + 54) )
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 25;
        v13 = "CertGetCertificateContextProperty failed";
        goto LABEL_102;
      }
    }
  }
  else
  {
    if ( *((_QWORD *)a3 + 7) )
    {
      v22 = *((_DWORD *)a3 + 16);
      if ( v22 )
      {
        *((_DWORD *)this + 54) = v22;
        v23 = operator new(v22);
        *((_QWORD *)this + 26) = v23;
        if ( !v23 )
          goto LABEL_32;
        memcpy_0(v23, *((const void **)a3 + 7), *((unsigned int *)this + 54));
      }
    }
    v24 = (const unsigned __int16 *)*((_QWORD *)a3 + 9);
    if ( v24 )
    {
      Instance = StringCchLengthW(v24, 0x104u, &v33);
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 23;
LABEL_28:
        v13 = "StringCchLength failed";
        goto LABEL_102;
      }
      v25 = v33 + 1;
      v26 = (unsigned __int16 *)operator new(saturated_mul(v33 + 1, 2u));
      *((_QWORD *)this + 28) = v26;
      if ( !v26 )
        goto LABEL_32;
      Instance = StringCchCopyW(v26, v25, *((const unsigned __int16 **)a3 + 9));
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 24;
LABEL_38:
        v13 = "StringCchCopy failed";
        goto LABEL_102;
      }
    }
  }
  if ( *((_DWORD *)a3 + 3) )
  {
    *((_DWORD *)this + 58) = 1;
    Instance = CRDPENCCONDTLSSecurityFilterStream::ActivateInternal((CRDPENCCONDTLSSecurityFilterStream *)((char *)this - 64));
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 26;
      v13 = "ActivateInternal failed";
      goto LABEL_102;
    }
  }
  Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v9)(*v9, &IID_IRDPENCNetStreamEx, (char *)this + 256);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 27;
    v13 = "Failed to query for NetStreamEx interface!";
    goto LABEL_102;
  }
  v29 = (const WCHAR *)*((_QWORD *)a3 + 11);
  if ( v29 )
  {
    v30 = (_DWORD *)((char *)this + 400);
    if ( RtlIpv4StringToAddressW(v29, 1u, &Terminator, Addr) )
    {
      if ( RtlIpv6StringToAddressW(*((PCWSTR *)a3 + 11), &Terminator, (struct in6_addr *)Addr) )
      {
        memset_0((char *)this + 400, 0, 0x80u);
      }
      else
      {
        *(_OWORD *)((char *)this + 408) = *(_OWORD *)&Addr[0].S_un.S_un_b.s_b1;
        *v30 = 23;
        *((_DWORD *)this + 98) = 28;
      }
    }
    else
    {
      *((struct in_addr *)this + 101) = Addr[0];
      *v30 = 2;
      *((_DWORD *)this + 98) = 16;
    }
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(void *), _QWORD, char *))(**((_QWORD **)this + 33)
                                                                                            + 56LL))(
               *((_QWORD *)this + 33),
               CRDPENCCONDTLSSecurityFilterStream::STATIC_OnReadCompletedCallbackThreadProc,
               *((_QWORD *)this + 33),
               (char *)this + 288);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 28;
    v13 = "Failed to create session allowed thread";
    goto LABEL_102;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 36) + 32LL))(*((_QWORD *)this + 36), 0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_103;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 29;
    v13 = "Failed to start session allowed thread";
    goto LABEL_102;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800fc5f0  mov     [rsp-8+arg_8], rbx
0x1800fc5f5  push    rbp
0x1800fc5f6  push    rsi
0x1800fc5f7  push    rdi
0x1800fc5f8  push    r12
0x1800fc5fa  push    r13
0x1800fc5fc  push    r14
0x1800fc5fe  push    r15
0x1800fc600  lea     rbp, [rsp-27h]
0x1800fc605  sub     rsp, 0E0h
0x1800fc60c  mov     rax, cs:__security_cookie
0x1800fc613  xor     rax, rsp
0x1800fc616  mov     [rbp+57h+var_40], rax
0x1800fc61a  xor     r15d, r15d
0x1800fc61d  mov     r14, r8
0x1800fc620  mov     rbx, rdx
0x1800fc623  mov     [rsp+110h+var_E0], r15
0x1800fc628  mov     rsi, rcx
0x1800fc62b  mov     [rsp+110h+var_D8], r15
0x1800fc630  xor     edx, edx; Val
0x1800fc632  mov     [rbp+57h+Terminator], r15
0x1800fc636  mov     r8d, 80h; Size
0x1800fc63c  lea     rcx, [rbp+57h+Addr]; void *
0x1800fc640  call    memset_0
0x1800fc645  mov     eax, cs:CallbackContext
0x1800fc64b  cmp     eax, 4
0x1800fc64e  jbe     short loc_1800FC67A
0x1800fc650  lea     rax, aCrdpenccondtls_5; "CRDPENCCONDTLSSecurityFilterStream::Ini"...
0x1800fc657  xor     r8d, r8d
0x1800fc65a  mov     [rbp+57h+var_C8], rax
0x1800fc65e  lea     rdx, word_1801C4E46
0x1800fc665  lea     rax, [rbp+57h+var_C8]
0x1800fc669  lea     rcx, CallbackContext
0x1800fc670  mov     [rsp+110h+var_F0], rax
0x1800fc675  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800fc67a  lea     r12, [rsi+0F8h]
0x1800fc681  cmp     rbx, [r12]
0x1800fc685  jz      short loc_1800FC69B
0x1800fc687  mov     rcx, r12; void *
0x1800fc68a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800fc68f  mov     rcx, r12
0x1800fc692  mov     [r12], rbx
0x1800fc696  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800fc69b  lea     r8, [rsi+148h]
0x1800fc6a2  mov     [rsi+0ECh], r15
0x1800fc6a9  call    ?CreateInstance@?$CTSObjectPool@VCRDPDTLSSecFilterContext@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPDTLSSecFilterContext>::CreateInstance(uint,uint,CTSObjectPool<CRDPDTLSSecFilterContext> * *,int)
0x1800fc6ae  mov     ebx, eax
0x1800fc6b0  test    eax, eax
0x1800fc6b2  jns     short loc_1800FC6F8
0x1800fc6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fc6bb  lea     rax, WPP_GLOBAL_Control
0x1800fc6c2  cmp     rcx, rax
0x1800fc6c5  jz      loc_1800FCD24
0x1800fc6cb  test    byte ptr [rcx+1Ch], 8
0x1800fc6cf  jz      loc_1800FCD24
0x1800fc6d5  mov     edi, 2
0x1800fc6da  cmp     [rcx+19h], dil
0x1800fc6de  jb      loc_1800FCD24
0x1800fc6e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fc6e9  lea     edx, [rdi+0Fh]
0x1800fc6ec  lea     rcx, aFailedToCreate_85; "Failed to create Context Pool"
0x1800fc6f3  jmp     loc_1800FCD01
0x1800fc6f8  mov     r8, [r14]; unsigned __int16 *
0x1800fc6fb  lea     rcx, [rsi+70h]; unsigned __int16 *
0x1800fc6ff  mov     edx, 42h ; 'B'; unsigned __int64
0x1800fc704  test    r8, r8
0x1800fc707  jz      short loc_1800FC75C
0x1800fc709  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fc70e  mov     ebx, eax
0x1800fc710  test    eax, eax
0x1800fc712  jns     loc_1800FC7A8
0x1800fc718  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fc71f  lea     rax, WPP_GLOBAL_Control
0x1800fc726  cmp     rcx, rax
0x1800fc729  jz      loc_1800FCD24
0x1800fc72f  test    byte ptr [rcx+1Ch], 8
0x1800fc733  jz      loc_1800FCD24
0x1800fc739  mov     edi, 2
0x1800fc73e  cmp     [rcx+19h], dil
0x1800fc742  jb      loc_1800FCD24
0x1800fc748  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fc74d  lea     edx, [rdi+10h]
0x1800fc750  lea     rcx, aStringcbcopyFa; "StringCbCopy failed"
0x1800fc757  jmp     loc_1800FCD01
0x1800fc75c  lea     r8, aDefaultlistene; "DefaultListener"
0x1800fc763  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fc768  mov     ebx, eax
0x1800fc76a  test    eax, eax
0x1800fc76c  jns     short loc_1800FC7A8
0x1800fc76e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fc775  lea     rax, WPP_GLOBAL_Control
0x1800fc77c  cmp     rcx, rax
0x1800fc77f  jz      loc_1800FCD24
0x1800fc785  test    byte ptr [rcx+1Ch], 8
0x1800fc789  jz      loc_1800FCD24
0x1800fc78f  mov     edi, 2
0x1800fc794  cmp     [rcx+19h], dil
0x1800fc798  jb      loc_1800FCD24
0x1800fc79e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fc7a3  lea     edx, [rdi+11h]
0x1800fc7a6  jmp     short loc_1800FC750
0x1800fc7a8  mov     rcx, [r14+10h]; unsigned __int16 *
0x1800fc7ac  or      r11, 0FFFFFFFFFFFFFFFFh
0x1800fc7b0  mov     edi, 2
0x1800fc7b5  test    rcx, rcx
0x1800fc7b8  jz      loc_1800FC898
0x1800fc7be  lea     r8, [rsp+110h+var_E0]; unsigned __int64 *
0x1800fc7c3  mov     edx, 104h; unsigned __int64
0x1800fc7c8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800fc7cd  mov     ebx, eax
0x1800fc7cf  test    eax, eax
0x1800fc7d1  jns     short loc_1800FC812
0x1800fc7d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fc7da  lea     rax, WPP_GLOBAL_Control
0x1800fc7e1  cmp     rcx, rax
0x1800fc7e4  jz      loc_1800FCD24
0x1800fc7ea  test    byte ptr [rcx+1Ch], 8
0x1800fc7ee  jz      loc_1800FCD24
0x1800fc7f4  cmp     [rcx+19h], dil
0x1800fc7f8  jb      loc_1800FCD24
0x1800fc7fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fc803  lea     edx, [rdi+12h]
0x1800fc806  lea     rcx, aStringcchlengt_3; "StringCchLength failed"
0x1800fc80d  jmp     loc_1800FCD01
0x1800fc812  mov     rbx, [rsp+110h+var_E0]
0x1800fc817  mov     rax, rdi
0x1800fc81a  inc     rbx
0x1800fc81d  mul     rbx
0x1800fc820  cmovb   rax, r11
0x1800fc824  mov     rcx, rax; Size
0x1800fc827  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fc82c  mov     [rsi+0B8h], rax
0x1800fc833  test    rax, rax
0x1800fc836  jnz     short loc_1800FC842
0x1800fc838  mov     ebx, 8007000Eh
0x1800fc83d  jmp     loc_1800FCD24
0x1800fc842  mov     r8, [r14+10h]; unsigned __int16 *
0x1800fc846  mov     rdx, rbx; unsigned __int64
0x1800fc849  mov     rcx, rax; unsigned __int16 *
0x1800fc84c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fc851  mov     ebx, eax
0x1800fc853  test    eax, eax
0x1800fc855  jns     short loc_1800FC898
0x1800fc857  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fc85e  lea     rax, WPP_GLOBAL_Control
0x1800fc865  cmp     rcx, rax
0x1800fc868  jz      loc_1800FCD24
0x1800fc86e  test    byte ptr [rcx+1Ch], 8
0x1800fc872  jz      loc_1800FCD24
0x1800fc878  cmp     [rcx+19h], dil
0x1800fc87c  jb      loc_1800FCD24
0x1800fc882  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fc887  mov     edx, 15h
0x1800fc88c  lea     rcx, aStringcchcopyF_0; "StringCchCopy failed"
0x1800fc893  jmp     loc_1800FCD01
0x1800fc898  mov     rbx, [r14+18h]
0x1800fc89c  lea     r15, [rsi+118h]
0x1800fc8a3  cmp     rbx, [r15]
0x1800fc8a6  jz      short loc_1800FC8C7
0x1800fc8a8  mov     rcx, r15; void *
0x1800fc8ab  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800fc8b0  mov     [r15], rbx
0x1800fc8b3  test    rbx, rbx
0x1800fc8b6  jz      short loc_1800FC8C7
0x1800fc8b8  mov     rax, [rbx]
0x1800fc8bb  mov     rcx, rbx
0x1800fc8be  mov     rax, [rax+8]
0x1800fc8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc8c7  mov     eax, [r14+20h]
0x1800fc8cb  lea     rdx, [rsi+0C5h]; unsigned __int8 *
0x1800fc8d2  mov     [rsi+0C0h], eax
0x1800fc8d8  mov     al, [r14+24h]
0x1800fc8dc  mov     [rsi+0C4h], al
0x1800fc8e2  mov     al, [r14+25h]
0x1800fc8e6  mov     [rdx], al
0x1800fc8e8  call    ?AdjustEncryptionLevel@CRDPENCCONDTLSSecurityFilterStream@@AEAAJPEAE@Z; CRDPENCCONDTLSSecurityFilterStream::AdjustEncryptionLevel(uchar *)
0x1800fc8ed  mov     ebx, eax
0x1800fc8ef  test    eax, eax
0x1800fc8f1  jns     short loc_1800FC934
0x1800fc8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fc8fa  lea     rax, WPP_GLOBAL_Control
0x1800fc901  cmp     rcx, rax
0x1800fc904  jz      loc_1800FCD24
0x1800fc90a  test    byte ptr [rcx+1Ch], 8
0x1800fc90e  jz      loc_1800FCD24
0x1800fc914  cmp     [rcx+19h], dil
0x1800fc918  jb      loc_1800FCD24
0x1800fc91e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fc923  mov     edx, 16h
0x1800fc928  lea     rcx, aAdjustencrypti; "AdjustEncryptionLevel failed"
0x1800fc92f  jmp     loc_1800FCD01
0x1800fc934  mov     rcx, [r14+30h]; pCertContext
0x1800fc938  test    rcx, rcx
0x1800fc93b  jz      short loc_1800FC94A
0x1800fc93d  call    cs:__imp_CertDuplicateCertificateContext
0x1800fc943  mov     [rsi+0C8h], rax
0x1800fc94a  cmp     qword ptr [rsi+0C8h], 0
0x1800fc952  jnz     loc_1800FCA77
0x1800fc958  cmp     qword ptr [r14+38h], 0
0x1800fc95d  jz      short loc_1800FC997
0x1800fc95f  mov     eax, [r14+40h]
0x1800fc963  test    eax, eax
0x1800fc965  jz      short loc_1800FC997
0x1800fc967  mov     ecx, eax; Size
0x1800fc969  mov     [rsi+0D8h], eax
0x1800fc96f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fc974  mov     [rsi+0D0h], rax
0x1800fc97b  test    rax, rax
0x1800fc97e  jz      loc_1800FC838
0x1800fc984  mov     r8d, [rsi+0D8h]; Size
0x1800fc98b  mov     rcx, rax; void *
0x1800fc98e  mov     rdx, [r14+38h]; Src
0x1800fc992  call    memcpy_0
0x1800fc997  mov     rcx, [r14+48h]; unsigned __int16 *
0x1800fc99b  test    rcx, rcx
0x1800fc99e  jz      loc_1800FCB14
0x1800fc9a4  lea     r8, [rsp+110h+var_D8]; unsigned __int64 *
0x1800fc9a9  mov     edx, 104h; unsigned __int64
0x1800fc9ae  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800fc9b3  mov     ebx, eax
0x1800fc9b5  test    eax, eax
0x1800fc9b7  jns     short loc_1800FC9F3
0x1800fc9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fc9c0  lea     rax, WPP_GLOBAL_Control
0x1800fc9c7  cmp     rcx, rax
0x1800fc9ca  jz      loc_1800FCD24
0x1800fc9d0  test    byte ptr [rcx+1Ch], 8
0x1800fc9d4  jz      loc_1800FCD24
0x1800fc9da  cmp     [rcx+19h], dil
0x1800fc9de  jb      loc_1800FCD24
0x1800fc9e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fc9e9  mov     edx, 17h
0x1800fc9ee  jmp     loc_1800FC806
0x1800fc9f3  mov     rbx, [rsp+110h+var_D8]
0x1800fc9f8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800fc9ff  inc     rbx
0x1800fca02  mov     rax, rdi
0x1800fca05  mul     rbx
0x1800fca08  cmovb   rax, rcx
0x1800fca0c  mov     rcx, rax; Size
0x1800fca0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fca14  mov     [rsi+0E0h], rax
0x1800fca1b  test    rax, rax
0x1800fca1e  jz      loc_1800FC838
0x1800fca24  mov     r8, [r14+48h]; unsigned __int16 *
0x1800fca28  mov     rdx, rbx; unsigned __int64
0x1800fca2b  mov     rcx, rax; unsigned __int16 *
0x1800fca2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fca33  mov     ebx, eax
0x1800fca35  test    eax, eax
0x1800fca37  jns     loc_1800FCB14
0x1800fca3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fca44  lea     rax, WPP_GLOBAL_Control
0x1800fca4b  cmp     rcx, rax
0x1800fca4e  jz      loc_1800FCD24
0x1800fca54  test    byte ptr [rcx+1Ch], 8
0x1800fca58  jz      loc_1800FCD24
0x1800fca5e  cmp     [rcx+19h], dil
0x1800fca62  jb      loc_1800FCD24
0x1800fca68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fca6d  mov     edx, 18h
0x1800fca72  jmp     loc_1800FC88C
0x1800fca77  lea     rbx, [rsi+0D8h]
0x1800fca7e  mov     ecx, 14h; Size
0x1800fca83  mov     dword ptr [rbx], 14h
0x1800fca89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fca8e  mov     [rsi+0D0h], rax
0x1800fca95  test    rax, rax
0x1800fca98  jz      loc_1800FC838
0x1800fca9e  mov     rcx, [rsi+0C8h]; pCertContext
0x1800fcaa5  mov     r9, rbx; pcbData
0x1800fcaa8  mov     r8, rax; pvData
0x1800fcaab  mov     edx, 3; dwPropId
0x1800fcab0  call    cs:__imp_CertGetCertificateContextProperty
0x1800fcab6  test    eax, eax
0x1800fcab8  jnz     short loc_1800FCB14
0x1800fcaba  call    cs:__imp_GetLastError
0x1800fcac0  mov     ebx, eax
0x1800fcac2  test    eax, eax
0x1800fcac4  jle     short loc_1800FCACF
0x1800fcac6  movzx   ebx, ax
0x1800fcac9  or      ebx, 80070000h
0x1800fcacf  test    ebx, ebx
0x1800fcad1  jns     short loc_1800FCB14
0x1800fcad3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fcada  lea     rax, WPP_GLOBAL_Control
0x1800fcae1  cmp     rcx, rax
0x1800fcae4  jz      loc_1800FCD24
0x1800fcaea  test    byte ptr [rcx+1Ch], 8
0x1800fcaee  jz      loc_1800FCD24
0x1800fcaf4  cmp     [rcx+19h], dil
0x1800fcaf8  jb      loc_1800FCD24
0x1800fcafe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fcb03  mov     edx, 19h
0x1800fcb08  lea     rcx, aCertgetcertifi_0; "CertGetCertificateContextProperty faile"...
0x1800fcb0f  jmp     loc_1800FCD01
0x1800fcb14  cmp     dword ptr [r14+0Ch], 0
0x1800fcb19  jz      short loc_1800FCB75
0x1800fcb1b  lea     rcx, [rsi-40h]; this
0x1800fcb1f  mov     dword ptr [rsi+0E8h], 1
  ... truncated ...
```
