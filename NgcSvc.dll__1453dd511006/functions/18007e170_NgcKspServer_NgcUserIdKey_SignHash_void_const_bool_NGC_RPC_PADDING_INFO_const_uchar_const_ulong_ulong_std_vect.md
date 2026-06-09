# NgcKspServer::NgcUserIdKey::SignHash(void * const,bool,_NGC_RPC_PADDING_INFO const *,uchar const *,ulong,ulong,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x18007e170`
- end: `0x18007e992`
- name: `?SignHash@NgcUserIdKey@NgcKspServer@@UEAAJQEAX_NPEBU_NGC_RPC_PADDING_INFO@@PEBEKKPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `2082`
- prototype: `__int64 __usercall@<rax>(NgcKspServer::NgcUserIdKey *this@<rcx>, __int64, int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d28`
- `0x18000782c`
- `0x180010990`
- `0x180016400`
- `0x180022f90`
- `0x180028d18`
- `0x18002eee8`
- `0x180035698`
- `0x18003d8c0`
- `0x18003e12c`
- `0x180046d90`
- `0x180048394`
- `0x18006930c`
- `0x180078a9c`
- `0x18007d164`
- `0x18007e170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e1d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007e1d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e263`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e312`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e5be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e698`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e758`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e803`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e8ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e953`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e263`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e312`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e5be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e698`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e758`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e803`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e8ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007e953`

## string_xrefs

- `0x18007e20a`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007e2be`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007e404`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007e54b`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007e625`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007e71d`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall NgcKspServer::NgcUserIdKey::SignHash(
        RTL_SRWLOCK *this,
        void *a2,
        bool a3,
        __int64 *a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8)
{
  RTL_SRWLOCK *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 *v17; // rax
  char *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  char IsEnabled; // al
  __int64 v22; // r14
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  __int128 *v26; // rax
  int v28; // [rsp+28h] [rbp-E0h]
  RTL_SRWLOCK *v29; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v31; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A8h]
  __int128 v33; // [rsp+68h] [rbp-A0h] BYREF
  __m256i v34; // [rsp+78h] [rbp-90h] BYREF
  char *v35; // [rsp+98h] [rbp-70h] BYREF
  __int128 v36; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v37; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v38[24]; // [rsp+C0h] [rbp-48h] BYREF
  RTL_SRWLOCK *v39; // [rsp+D8h] [rbp-30h]
  void **v40; // [rsp+E0h] [rbp-28h]
  bool *v41; // [rsp+E8h] [rbp-20h]
  unsigned int *v42; // [rsp+F0h] [rbp-18h]
  char **v43; // [rsp+F8h] [rbp-10h]
  char v44; // [rsp+100h] [rbp-8h]
  _OWORD v45[5]; // [rsp+108h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]
  char *v47; // [rsp+168h] [rbp+60h] BYREF
  void *v48; // [rsp+170h] [rbp+68h] BYREF
  bool v49; // [rsp+178h] [rbp+70h] BYREF

  v49 = a3;
  v48 = a2;
  LODWORD(v47) = 0;
  v39 = this;
  v40 = &v48;
  v41 = &v49;
  v42 = &a7;
  v43 = &v47;
  v44 = 1;
  v10 = this + 34;
  AcquireSRWLockShared(this + 34);
  v29 = v10;
  if ( !LOBYTE(this[37].Ptr) )
  {
    LODWORD(v47) = -2146893813;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x14FC,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v47,
        v28);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v29) = (_DWORD)v47;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180102297,
        0,
        0,
        (__int64)&v29);
    }
    v11 = (int)v47;
    v12 = (unsigned int)v47;
    if ( v10 )
    {
      ReleaseSRWLockShared(v10);
      v11 = (int)v47;
    }
LABEL_8:
    NgcKspServer::NgcUserIdKey::EventWriteSignHash((NgcKspServer::NgcUserIdKey *)this, v48, v49, a7, v11);
    return v12;
  }
  v13 = 2;
  if ( ((__int64)this[29].Ptr & 2) == 0 )
  {
    LODWORD(v47) = -2146893821;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x150E,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v47,
        v28);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v29) = (_DWORD)v47;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180102267,
        0,
        0,
        (__int64)&v29);
    }
    v11 = (int)v47;
    v12 = (unsigned int)v47;
    if ( v10 )
    {
      ReleaseSRWLockShared(v10);
      v11 = (int)v47;
    }
    goto LABEL_8;
  }
  memset(&v34.m256i_u64[1], 0, 24);
  v35 = 0;
  v31 = 0;
  v32 = 0;
  std::vector<unsigned char>::assign<unsigned char const *,0>(&v31, a5, a5 + a6);
  v33 = 0;
  v34.m256i_i64[0] = 0;
  v36 = 0;
  v30 = 0;
  memset(v45, 0, 48);
  LOBYTE(v14) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl'::`2'::impl,
    v14);
  v16 = a7;
  if ( (a7 & 0xA) == 0 )
  {
    LOBYTE(v15) = 3;
    LOBYTE(v16) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
      v16,
      v15);
    v16 = a7;
    if ( (a7 & 0xFFFFFFBF) != 0 )
    {
      if ( (a7 & 0xFFF0FFFF) != 0 )
      {
        LODWORD(v47) = -2146893815;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x15A3,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)v47,
            v28);
        }
        else if ( (unsigned int)dword_180122070 > 2 )
        {
          LODWORD(v29) = (_DWORD)v47;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_1801021A7,
            0,
            0,
            (__int64)&v29);
        }
        v12 = (unsigned int)v47;
        std::vector<unsigned char>::_Tidy(&v33);
        std::vector<unsigned char>::_Tidy(&v31);
        std::vector<unsigned char>::_Tidy(&v34.m256i_u64[1]);
        if ( v10 )
          ReleaseSRWLockShared(v10);
LABEL_59:
        NgcKspServer::NgcUserIdKey::EventWriteSignHash((NgcKspServer::NgcUserIdKey *)this, v48, v49, a7, (int)v47);
        return v12;
      }
      v17 = (__int64 *)v30;
      if ( (a7 & 0x10000) != 0 )
        v17 = a4;
      *(_QWORD *)&v30 = v17;
      v13 = (a7 & 0x10000) != 0 ? 3 : 9;
      *((_QWORD *)&v30 + 1) = &v31;
      *((_QWORD *)&v36 + 1) = &v30;
      LOBYTE(v36) = (a7 & 0x20000) != 0;
      BYTE1(v36) = (a7 & 0x40000) != 0;
      v18 = (char *)&v36;
      goto LABEL_66;
    }
  }
  if ( (v16 & 0xFFFFFFB7) != 0 && (v16 & 0xFFFFFFBD) != 0 )
  {
    LOBYTE(v15) = 3;
    LOBYTE(v16) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
      v16,
      v15);
    if ( (a7 & 0xFFFFFFBF) != 0 )
    {
      LODWORD(v47) = -2146893815;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x1538,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          (const char *)(unsigned int)v47,
          v28);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(v29) = (_DWORD)v47;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&byte_18010223F,
          0,
          0,
          (__int64)&v29);
      }
      v12 = (unsigned int)v47;
      std::vector<unsigned char>::_Tidy(&v33);
      std::vector<unsigned char>::_Tidy(&v31);
      std::vector<unsigned char>::_Tidy(&v34.m256i_u64[1]);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      goto LABEL_59;
    }
  }
  if ( NgcKspServer::NgcUserIdKey::IsFidoKey((NgcKspServer::NgcUserIdKey *)this) && !LOBYTE(this[73].Ptr) )
  {
    LODWORD(v47) = -2146893821;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x154B,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v47,
        v28);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v29) = (_DWORD)v47;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_18010220B,
        0,
        0,
        (__int64)&v29);
    }
    v12 = (unsigned int)v47;
    std::vector<unsigned char>::_Tidy(&v33);
    std::vector<unsigned char>::_Tidy(&v31);
    std::vector<unsigned char>::_Tidy(&v34.m256i_u64[1]);
    if ( v10 )
      ReleaseSRWLockShared(v10);
    goto LABEL_59;
  }
  LOBYTE(this[73].Ptr) = 0;
  if ( (a7 & 2) == 0 )
  {
    if ( (a7 & 8) != 0 )
    {
      *(_QWORD *)&v45[0] = *a4;
      DWORD2(v45[0]) = *((_DWORD *)a4 + 2);
    }
    else
    {
      LOBYTE(v20) = 3;
      LOBYTE(v19) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl'::`2'::impl,
        v19,
        v20);
      v13 = 5;
    }
    v26 = &v31;
    goto LABEL_65;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v22 = *a4;
  if ( !IsEnabled )
  {
    v25 = std::vector<unsigned char>::vector<unsigned char>(v38, &v31);
    LODWORD(v47) = NgcKspServer::NgcUserIdKey::RsaBuildFullHashWithDigest(v25, v22, &v33);
    if ( (int)v47 < 0 )
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(v29) = (_DWORD)v47;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1801021D3,
          0,
          0,
          (__int64)&v29);
      }
      v12 = (unsigned int)v47;
      std::vector<unsigned char>::_Tidy(&v33);
      std::vector<unsigned char>::_Tidy(&v31);
      std::vector<unsigned char>::_Tidy(&v34.m256i_u64[1]);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      goto LABEL_59;
    }
    goto LABEL_60;
  }
  v23 = std::vector<unsigned char>::vector<unsigned char>(v38, &v31);
  v24 = NgcKspServer::NgcUserIdKey::RsaBuildFullHashWithDigest(v23, v22, &v33);
  v12 = v24;
  if ( v24 >= 0 )
  {
LABEL_60:
    v13 = 1;
    v26 = &v33;
LABEL_65:
    *((_QWORD *)&v30 + 1) = v26;
    *(_QWORD *)&v30 = v45;
    v18 = (char *)&v30;
LABEL_66:
    v35 = v18;
    v37 = &v34.m256i_i64[1];
    *(_QWORD *)((char *)NgcKspServer::PinCacheManager::Instance() + 84) = 0;
    v12 = NgcKspServer::NgcUserIdKey::PerformOperationWithGesture((__int64)this, v48, v49, v13, &v35, (__int64)&v37);
    LODWORD(v47) = v12;
    if ( (v12 & 0x80000000) == 0 )
    {
      std::vector<unsigned char>::operator=(a8, &v34.m256i_u64[1]);
      v12 = (unsigned int)v47;
      std::vector<unsigned char>::_Tidy(&v33);
      std::vector<unsigned char>::_Tidy(&v31);
      std::vector<unsigned char>::_Tidy(&v34.m256i_u64[1]);
      if ( v10 )
        ReleaseSRWLockShared(v10);
    }
    else
    {
      std::vector<unsigned char>::_Tidy(&v33);
      std::vector<unsigned char>::_Tidy(&v31);
      std::vector<unsigned char>::_Tidy(&v34.m256i_u64[1]);
      if ( v10 )
        ReleaseSRWLockShared(v10);
    }
    NgcKspServer::NgcUserIdKey::EventWriteSignHash((NgcKspServer::NgcUserIdKey *)this, v48, v49, a7, (int)v47);
    return v12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1561,
    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
    (const char *)(unsigned int)v24,
    v28);
  std::vector<unsigned char>::_Tidy(&v33);
  std::vector<unsigned char>::_Tidy(&v31);
  std::vector<unsigned char>::_Tidy(&v34.m256i_u64[1]);
  if ( v10 )
    ReleaseSRWLockShared(v10);
  NgcKspServer::NgcUserIdKey::EventWriteSignHash((NgcKspServer::NgcUserIdKey *)this, v48, v49, a7, (int)v47);
  return v12;
}

```

## disassembly

```asm
0x18007e170  mov     rax, rsp
0x18007e173  mov     [rax+20h], rbx
0x18007e177  mov     [rax+18h], r8b
0x18007e17b  mov     [rax+10h], rdx
0x18007e17f  push    rbp
0x18007e180  push    rsi
0x18007e181  push    rdi
0x18007e182  push    r14
0x18007e184  push    r15
0x18007e186  lea     rbp, [rax-58h]
0x18007e18a  sub     rsp, 130h
0x18007e191  mov     r14, r9
0x18007e194  mov     rsi, rcx
0x18007e197  xor     r15d, r15d
0x18007e19a  mov     dword ptr [rbp+50h+arg_0], r15d
0x18007e19e  mov     [rbp+50h+var_80], rcx
0x18007e1a2  lea     rax, [rbp+50h+arg_8]
0x18007e1a6  mov     [rbp+50h+var_78], rax
0x18007e1aa  lea     rax, [rbp+50h+arg_10]
0x18007e1ae  mov     [rbp+50h+var_70], rax
0x18007e1b2  lea     rax, [rbp+50h+arg_30]
0x18007e1b9  mov     [rbp+50h+var_68], rax
0x18007e1bd  lea     rax, [rbp+50h+arg_0]
0x18007e1c1  mov     [rbp+50h+var_60], rax
0x18007e1c5  mov     [rbp+50h+var_58], 1
0x18007e1c9  lea     rbx, [rcx+110h]
0x18007e1d0  mov     rcx, rbx; SRWLock
0x18007e1d3  call    cs:__imp_AcquireSRWLockShared
0x18007e1d9  mov     qword ptr [rsp+150h+var_120], rbx
0x18007e1de  cmp     [rsi+128h], r15b
0x18007e1e5  jnz     loc_18007E28D
0x18007e1eb  mov     dword ptr [rbp+50h+arg_0], 8009000Bh
0x18007e1f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007e1f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007e1fe  test    al, al
0x18007e200  jz      short loc_18007E21D
0x18007e202  mov     rcx, [rbp+58h]; this
0x18007e206  mov     r9d, dword ptr [rbp+50h+arg_0]; char *
0x18007e20a  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007e211  mov     edx, 14FCh; void *
0x18007e216  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007e21b  jmp     short loc_18007E256
0x18007e21d  mov     eax, cs:dword_180122070
0x18007e223  mov     edi, 2
0x18007e228  cmp     eax, edi
0x18007e22a  jbe     short loc_18007E256
0x18007e22c  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e22f  mov     dword ptr [rsp+150h+var_120], eax
0x18007e233  lea     rax, [rsp+150h+var_120]
0x18007e238  mov     qword ptr [rsp+150h+var_130], rax
0x18007e23d  xor     r9d, r9d
0x18007e240  xor     r8d, r8d
0x18007e243  lea     rdx, byte_180102297
0x18007e24a  lea     rcx, dword_180122070
0x18007e251  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007e256  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e259  mov     edi, eax
0x18007e25b  test    rbx, rbx
0x18007e25e  jz      short loc_18007E26C
0x18007e260  mov     rcx, rbx; SRWLock
0x18007e263  call    cs:__imp_ReleaseSRWLockShared
0x18007e269  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e26c  mov     [rsp+150h+var_130], eax; int
0x18007e270  mov     r9d, [rbp+50h+arg_30]; unsigned int
0x18007e277  mov     r8b, [rbp+50h+arg_10]; bool
0x18007e27b  mov     rdx, [rbp+50h+arg_8]; void *
0x18007e27f  mov     rcx, rsi; this
0x18007e282  call    ?EventWriteSignHash@NgcUserIdKey@NgcKspServer@@AEAAXQEAX_NKJ@Z; NgcKspServer::NgcUserIdKey::EventWriteSignHash(void * const,bool,ulong,long)
0x18007e287  nop
0x18007e288  jmp     loc_18007E979
0x18007e28d  mov     edi, 2
0x18007e292  test    [rsi+0E8h], dil
0x18007e299  jnz     loc_18007E33C
0x18007e29f  mov     dword ptr [rbp+50h+arg_0], 80090003h
0x18007e2a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007e2ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007e2b2  test    al, al
0x18007e2b4  jz      short loc_18007E2D1
0x18007e2b6  mov     rcx, [rbp+58h]; this
0x18007e2ba  mov     r9d, dword ptr [rbp+50h+arg_0]; char *
0x18007e2be  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007e2c5  mov     edx, 150Eh; void *
0x18007e2ca  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007e2cf  jmp     short loc_18007E305
0x18007e2d1  mov     eax, cs:dword_180122070
0x18007e2d7  cmp     eax, edi
0x18007e2d9  jbe     short loc_18007E305
0x18007e2db  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e2de  mov     dword ptr [rsp+150h+var_120], eax
0x18007e2e2  lea     rax, [rsp+150h+var_120]
0x18007e2e7  mov     qword ptr [rsp+150h+var_130], rax
0x18007e2ec  xor     r9d, r9d
0x18007e2ef  xor     r8d, r8d
0x18007e2f2  lea     rdx, byte_180102267
0x18007e2f9  lea     rcx, dword_180122070
0x18007e300  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007e305  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e308  mov     edi, eax
0x18007e30a  test    rbx, rbx
0x18007e30d  jz      short loc_18007E31B
0x18007e30f  mov     rcx, rbx; SRWLock
0x18007e312  call    cs:__imp_ReleaseSRWLockShared
0x18007e318  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e31b  mov     [rsp+150h+var_130], eax; int
0x18007e31f  mov     r9d, [rbp+50h+arg_30]; unsigned int
0x18007e326  mov     r8b, [rbp+50h+arg_10]; bool
0x18007e32a  mov     rdx, [rbp+50h+arg_8]; void *
0x18007e32e  mov     rcx, rsi; this
0x18007e331  call    ?EventWriteSignHash@NgcUserIdKey@NgcKspServer@@AEAAXQEAX_NKJ@Z; NgcKspServer::NgcUserIdKey::EventWriteSignHash(void * const,bool,ulong,long)
0x18007e336  nop
0x18007e337  jmp     loc_18007E979
0x18007e33c  xorps   xmm0, xmm0
0x18007e33f  movdqu  xmmword ptr [rsp+150h+var_E0+8], xmm0
0x18007e345  mov     [rbp+50h+var_C8], r15
0x18007e349  mov     [rbp+50h+var_C0], r15
0x18007e34d  movdqu  [rsp+150h+var_110+8], xmm0
0x18007e353  mov     qword ptr [rsp+150h+var_F8], r15
0x18007e358  mov     r8d, [rbp+50h+arg_28]
0x18007e35f  mov     rdx, [rbp+50h+arg_20]
0x18007e366  add     r8, rdx
0x18007e369  lea     rcx, [rsp+150h+var_110+8]
0x18007e36e  call    ??$assign@PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEBE0@Z; std::vector<uchar>::assign<uchar const *,0>(uchar const *,uchar const *)
0x18007e373  xorps   xmm0, xmm0
0x18007e376  movdqu  [rsp+150h+var_F8+8], xmm0
0x18007e37c  mov     qword ptr [rsp+150h+var_E0], r15
0x18007e381  movups  [rbp+50h+var_B8], xmm0
0x18007e385  xorps   xmm1, xmm1
0x18007e388  movups  [rsp+150h+var_120+8], xmm1
0x18007e38d  movups  [rbp+50h+var_50], xmm0
0x18007e391  movups  [rbp+50h+var_40], xmm0
0x18007e395  movups  [rbp+50h+var_30], xmm0
0x18007e399  mov     dl, 1
0x18007e39b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS> `wil::Feature<__WilFeatureTraits_Feature_SignRsaPadPSS>::GetImpl(void)'::`2'::impl
0x18007e3a2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SignRsaPadPSS@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SignRsaPadPSS>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007e3a7  mov     edx, [rbp+50h+arg_30]
0x18007e3ad  test    dl, 0Ah
0x18007e3b0  jnz     loc_18007E4F1
0x18007e3b6  mov     r8b, 3
0x18007e3b9  mov     dl, 1
0x18007e3bb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers> `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl(void)'::`2'::impl
0x18007e3c2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007e3c7  mov     edx, [rbp+50h+arg_30]
0x18007e3cd  test    edx, 0FFFFFFBFh
0x18007e3d3  jz      loc_18007E4F1
0x18007e3d9  test    edx, 0FFF0FFFFh
0x18007e3df  jz      loc_18007E4A2
0x18007e3e5  mov     dword ptr [rbp+50h+arg_0], 80090009h
0x18007e3ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007e3f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007e3f8  test    al, al
0x18007e3fa  jz      short loc_18007E417
0x18007e3fc  mov     rcx, [rbp+58h]; this
0x18007e400  mov     r9d, dword ptr [rbp+50h+arg_0]; char *
0x18007e404  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007e40b  mov     edx, 15A3h; void *
0x18007e410  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007e415  jmp     short loc_18007E44B
0x18007e417  mov     eax, cs:dword_180122070
0x18007e41d  cmp     eax, edi
0x18007e41f  jbe     short loc_18007E44B
0x18007e421  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e424  mov     dword ptr [rsp+150h+var_120], eax
0x18007e428  lea     rax, [rsp+150h+var_120]
0x18007e42d  mov     qword ptr [rsp+150h+var_130], rax
0x18007e432  xor     r9d, r9d
0x18007e435  xor     r8d, r8d
0x18007e438  lea     rdx, byte_1801021A7
0x18007e43f  lea     rcx, dword_180122070
0x18007e446  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007e44b  mov     edi, dword ptr [rbp+50h+arg_0]
0x18007e44e  lea     rcx, [rsp+150h+var_F8+8]
0x18007e453  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007e458  nop
0x18007e459  lea     rcx, [rsp+150h+var_110+8]
0x18007e45e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007e463  nop
0x18007e464  lea     rcx, [rsp+150h+var_E0+8]
0x18007e469  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007e46e  nop
0x18007e46f  test    rbx, rbx
0x18007e472  jz      short loc_18007E47E
0x18007e474  mov     rcx, rbx; SRWLock
0x18007e477  call    cs:__imp_ReleaseSRWLockShared
0x18007e47d  nop
0x18007e47e  mov     ecx, dword ptr [rbp+50h+arg_0]
0x18007e481  mov     [rsp+150h+var_130], ecx; int
0x18007e485  mov     r9d, [rbp+50h+arg_30]; unsigned int
0x18007e48c  mov     r8b, [rbp+50h+arg_10]; bool
0x18007e490  mov     rdx, [rbp+50h+arg_8]; void *
0x18007e494  mov     rcx, rsi; this
0x18007e497  call    ?EventWriteSignHash@NgcUserIdKey@NgcKspServer@@AEAAXQEAX_NKJ@Z; NgcKspServer::NgcUserIdKey::EventWriteSignHash(void * const,bool,ulong,long)
0x18007e49c  nop
0x18007e49d  jmp     loc_18007E979
0x18007e4a2  mov     ecx, edx
0x18007e4a4  and     ecx, 10000h
0x18007e4aa  mov     rax, qword ptr [rsp+150h+var_120+8]
0x18007e4af  cmovnz  rax, r14
0x18007e4b3  mov     qword ptr [rsp+150h+var_120+8], rax
0x18007e4b8  neg     ecx
0x18007e4ba  sbb     edi, edi
0x18007e4bc  and     edi, 0FFFFFFFAh
0x18007e4bf  add     edi, 9
0x18007e4c2  lea     rax, [rsp+150h+var_110+8]
0x18007e4c7  mov     qword ptr [rsp+150h+var_110], rax
0x18007e4cc  lea     rax, [rsp+150h+var_120+8]
0x18007e4d1  mov     qword ptr [rbp+50h+var_B8+8], rax
0x18007e4d5  mov     eax, edx
0x18007e4d7  shr     eax, 11h
0x18007e4da  and     al, 1
0x18007e4dc  mov     byte ptr [rbp+50h+var_B8], al
0x18007e4df  shr     edx, 12h
0x18007e4e2  and     dl, 1
0x18007e4e5  mov     byte ptr [rbp+50h+var_B8+1], dl
0x18007e4e8  lea     rax, [rbp+50h+var_B8]
0x18007e4ec  jmp     loc_18007E881
0x18007e4f1  test    edx, 0FFFFFFB7h
0x18007e4f7  setnz   cl
0x18007e4fa  test    edx, 0FFFFFFBDh
0x18007e500  setnz   al
0x18007e503  test    al, cl
0x18007e505  jz      loc_18007E5E9
0x18007e50b  mov     r8b, 3
0x18007e50e  mov     dl, 1
0x18007e510  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers> `wil::Feature<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::GetImpl(void)'::`2'::impl
0x18007e517  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NgcWebAuthnEccSupportedInIsoContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007e51c  test    [rbp+50h+arg_30], 0FFFFFFBFh
0x18007e526  jz      loc_18007E5E9
0x18007e52c  mov     dword ptr [rbp+50h+arg_0], 80090009h
0x18007e533  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007e53a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007e53f  test    al, al
0x18007e541  jz      short loc_18007E55E
0x18007e543  mov     rcx, [rbp+58h]; this
0x18007e547  mov     r9d, dword ptr [rbp+50h+arg_0]; char *
0x18007e54b  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007e552  mov     edx, 1538h; void *
0x18007e557  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007e55c  jmp     short loc_18007E592
0x18007e55e  mov     eax, cs:dword_180122070
0x18007e564  cmp     eax, edi
0x18007e566  jbe     short loc_18007E592
0x18007e568  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e56b  mov     dword ptr [rsp+150h+var_120], eax
0x18007e56f  lea     rax, [rsp+150h+var_120]
0x18007e574  mov     qword ptr [rsp+150h+var_130], rax
0x18007e579  xor     r9d, r9d
0x18007e57c  xor     r8d, r8d
0x18007e57f  lea     rdx, byte_18010223F
0x18007e586  lea     rcx, dword_180122070
0x18007e58d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007e592  mov     edi, dword ptr [rbp+50h+arg_0]
0x18007e595  lea     rcx, [rsp+150h+var_F8+8]
0x18007e59a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007e59f  nop
0x18007e5a0  lea     rcx, [rsp+150h+var_110+8]
0x18007e5a5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007e5aa  nop
0x18007e5ab  lea     rcx, [rsp+150h+var_E0+8]
0x18007e5b0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007e5b5  nop
0x18007e5b6  test    rbx, rbx
0x18007e5b9  jz      short loc_18007E5C5
0x18007e5bb  mov     rcx, rbx; SRWLock
0x18007e5be  call    cs:__imp_ReleaseSRWLockShared
0x18007e5c4  nop
0x18007e5c5  mov     ecx, dword ptr [rbp+50h+arg_0]
0x18007e5c8  mov     [rsp+150h+var_130], ecx; int
0x18007e5cc  mov     r9d, [rbp+50h+arg_30]; unsigned int
0x18007e5d3  mov     r8b, [rbp+50h+arg_10]; bool
0x18007e5d7  mov     rdx, [rbp+50h+arg_8]; void *
0x18007e5db  mov     rcx, rsi; this
0x18007e5de  call    ?EventWriteSignHash@NgcUserIdKey@NgcKspServer@@AEAAXQEAX_NKJ@Z; NgcKspServer::NgcUserIdKey::EventWriteSignHash(void * const,bool,ulong,long)
0x18007e5e3  nop
0x18007e5e4  jmp     loc_18007E979
0x18007e5e9  mov     rcx, rsi; this
0x18007e5ec  call    ?IsFidoKey@NgcUserIdKey@NgcKspServer@@AEAA_NXZ; NgcKspServer::NgcUserIdKey::IsFidoKey(void)
0x18007e5f1  test    al, al
0x18007e5f3  jz      loc_18007E6C3
0x18007e5f9  cmp     [rsi+248h], r15b
0x18007e600  jnz     loc_18007E6C3
0x18007e606  mov     dword ptr [rbp+50h+arg_0], 80090003h
0x18007e60d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007e614  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007e619  test    al, al
0x18007e61b  jz      short loc_18007E638
0x18007e61d  mov     rcx, [rbp+58h]; this
0x18007e621  mov     r9d, dword ptr [rbp+50h+arg_0]; char *
0x18007e625  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007e62c  mov     edx, 154Bh; void *
0x18007e631  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007e636  jmp     short loc_18007E66C
0x18007e638  mov     eax, cs:dword_180122070
0x18007e63e  cmp     eax, edi
0x18007e640  jbe     short loc_18007E66C
0x18007e642  mov     eax, dword ptr [rbp+50h+arg_0]
0x18007e645  mov     dword ptr [rsp+150h+var_120], eax
0x18007e649  lea     rax, [rsp+150h+var_120]
0x18007e64e  mov     qword ptr [rsp+150h+var_130], rax
0x18007e653  xor     r9d, r9d
0x18007e656  xor     r8d, r8d
  ... truncated ...
```
