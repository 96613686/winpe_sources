# CRDPENCSessionManagerShim::CreateRDPConnection(IRDPENCNetStream *,ulong,ulong,IUnknown *)

- ea: `0x1800f8ed0`
- end: `0x1800f96a9`
- name: `?CreateRDPConnection@CRDPENCSessionManagerShim@@UEAAJPEAUIRDPENCNetStream@@KKPEAUIUnknown@@@Z`
- size: `2009`
- prototype: `__int64 __fastcall(CRDPENCSessionManagerShim *__hidden this, struct IRDPENCNetStream *, unsigned int, unsigned int, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000116c`
- `0x18000cdac`
- `0x18000ce04`
- `0x18000ce34`
- `0x180076090`
- `0x180079770`
- `0x180082560`
- `0x18008258c`
- `0x1800f8ed0`
- `0x1800fb328`
- `0x18019c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f91c3`
- `OLEAUT32!__imp_VariantInit` at `0x1800f9256`
- `OLEAUT32!__imp_VariantInit` at `0x1800f9351`
- `OLEAUT32!__imp_VariantInit` at `0x1800f9467`
- `OLEAUT32!__imp_VariantInit` at `0x1800f91c3`
- `OLEAUT32!__imp_VariantInit` at `0x1800f9256`
- `OLEAUT32!__imp_VariantInit` at `0x1800f9351`
- `OLEAUT32!__imp_VariantInit` at `0x1800f9467`

## string_xrefs

- `0x1800f95bb`: `Failed to create the connection`
- `0x1800f9086`: `fAllowAdvancedCompression`
- `0x1800f90ce`: `Failed to set the property CONN_ALLOW_ADVANCEDCOMPRESSION`
- `0x1800f91f0`: `CreateRDPConnection`
- `0x1800f9611`: `CreateRDPConnection`

## pseudocode

```c
__int64 __fastcall CRDPENCSessionManagerShim::CreateRDPConnection(
        CRDPENCSessionManagerShim *this,
        struct IRDPENCNetStream *a2,
        __int64 a3,
        __int64 a4,
        struct IUnknown *a5)
{
  __int64 v7; // rbx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v13; // edx
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  __int64 v17; // rcx
  int v18; // ebx
  unsigned int v19; // eax
  int v20; // ebx
  unsigned int v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // rcx
  __int64 v30; // [rsp+28h] [rbp-89h]
  int v31; // [rsp+28h] [rbp-89h]
  __int64 v32; // [rsp+50h] [rbp-61h] BYREF
  int v33; // [rsp+58h] [rbp-59h] BYREF
  __int64 v34; // [rsp+60h] [rbp-51h] BYREF
  __int64 v35; // [rsp+68h] [rbp-49h] BYREF
  const char *v36; // [rsp+70h] [rbp-41h] BYREF
  const char *v37; // [rsp+78h] [rbp-39h] BYREF
  const char *v38; // [rsp+80h] [rbp-31h] BYREF
  __int64 v39; // [rsp+88h] [rbp-29h] BYREF
  VARIANTARG v40; // [rsp+90h] [rbp-21h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-1h] BYREF
  VARIANTARG v43; // [rsp+C8h] [rbp+17h] BYREF
  int v44; // [rsp+110h] [rbp+5Fh] BYREF

  v41 = 0;
  v35 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v35);
  v34 = 0;
  v39 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v43, 0, sizeof(v43));
  memset(&v40, 0, sizeof(v40));
  CTSReaderWriterLock::ReadLock((CRDPENCSessionManagerShim *)((char *)this + 168));
  v7 = 0;
  if ( (*((_BYTE *)this + 36) & 4) == 0 && *((_QWORD *)this + 26) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v39);
    v7 = *((_QWORD *)this + 26);
    v39 = v7;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v39);
  }
  CTSReaderWriterLock::ReadUnlock((CRDPENCSessionManagerShim *)((char *)this + 168));
  if ( v7 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IRDPENCNetStream *, __int64 *, _QWORD))(*(_QWORD *)v7 + 24LL))(
            v7,
            &CLSID_RDPCoreConnection,
            a2,
            &v35,
            0);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 37;
      v31 = v11;
LABEL_81:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)WPP_74da7902196636370942c8c90025961d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed to create the connection",
        v31);
LABEL_82:
      CRDPENCSessionManagerShim::OnSessionError(this, v11, 0xFFFFFFFF);
      goto LABEL_85;
    }
    if ( !v35 )
    {
      v11 = -2147467259;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 47;
      v31 = -2147467259;
      goto LABEL_81;
    }
    v32 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 80LL))(v35, &v34);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 38;
        v16 = "Failed to get Prperty  bag from connection";
LABEL_16:
        LODWORD(v30) = v11;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          (unsigned int)WPP_74da7902196636370942c8c90025961d_Traceguids,
          v14,
          (__int64)v16,
          v30);
        goto LABEL_17;
      }
      goto LABEL_17;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v34 + 64LL))(
            v34,
            L"fAllowAdvancedCompression",
            1);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 39;
        v16 = "Failed to set the property CONN_ALLOW_ADVANCEDCOMPRESSION";
        goto LABEL_16;
      }
LABEL_17:
      v17 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      goto LABEL_82;
    }
    if ( (**(int (__fastcall ***)(struct IRDPENCNetStream *, GUID *, __int64 *))a2)(
           a2,
           &IID_IRDPENCCONSecurityFilterStream,
           &v32) >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v34 + 64LL))(
              v34,
              L"RDPENCSTACK_ENCRYPTED_STREAM",
              1);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 40;
          v16 = "Failed to set the property RDPENC_STACK_PROP_ENCRYPTED_STREAM";
          goto LABEL_16;
        }
        goto LABEL_17;
      }
    }
    if ( a5 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v34 + 80LL))(
              v34,
              L"MultiTransportListener");
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 41;
          v16 = "Failed to set the property CONN_PROPERTY_MULTITRANSPORTLISTENER";
          goto LABEL_16;
        }
        goto LABEL_17;
      }
    }
    VariantInit(&pvarg);
    v18 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 25) + 24LL))(
            *((_QWORD *)this + 25),
            L"GfxPipeline::AVC444ModePreferred",
            &pvarg);
    if ( v18 >= 0 )
    {
      if ( pvarg.vt == 11 && pvarg.iVal == -1 )
      {
        VariantInit(&v40);
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 25) + 24LL))(
               *((_QWORD *)this + 25),
               L"GfxPipeline::ForceLyncProfile",
               &v40) >= 0
          && v40.vt == 11
          && v40.iVal == -1
          && (unsigned int)CallbackContext > 2 )
        {
          v36 = "CreateRDPConnection";
          v38 = "Cannot have set both AVC full screen and lync profile at the same time. The lync profile will prevail.";
          v44 = 503;
          v37 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\sessmgrshim.cpp";
          v33 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v22,
            (unsigned int)byte_1802855FB,
            v23,
            v24,
            (__int64)&v38,
            (__int64)&v33,
            (__int64)&v37,
            (__int64)&v44,
            (__int64)&v36);
        }
        v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v34 + 64LL))(
                v34,
                L"GfxPipeline::AVC444ModePreferred",
                1);
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = RdpWppGetCurrentThreadActivityIdPrefix();
            v15 = 43;
            v16 = "Failed to set AVC444 full screen mode property";
            goto LABEL_16;
          }
          goto LABEL_17;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_74da7902196636370942c8c90025961d_Traceguids,
        v19,
        (__int64)"Failed to get AVC444 full screen preferred property. Ignoring this failure, it is an optional property.",
        v18);
    }
    VariantInit(&v43);
    v20 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 25) + 24LL))(
            *((_QWORD *)this + 25),
            L"GfxPipeline::HEVCHardwareEncodePreferred",
            &v43);
    if ( v20 >= 0 )
    {
      if ( v43.vt == 11 && v43.iVal == -1 )
      {
        VariantInit(&v40);
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 25) + 24LL))(
               *((_QWORD *)this + 25),
               L"GfxPipeline::ForceLyncProfile",
               &v40) >= 0
          && v40.vt == 11
          && v40.iVal == -1
          && (unsigned int)CallbackContext > 2 )
        {
          v38 = "CreateRDPConnection";
          v36 = "Cannot have set both HEVC and lync profile at the same time. The lync profile will prevail.";
          v44 = 527;
          v37 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\sessmgrshim.cpp";
          v33 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v25,
            (unsigned int)byte_180285571,
            v26,
            v27,
            (__int64)&v36,
            (__int64)&v33,
            (__int64)&v37,
            (__int64)&v44,
            (__int64)&v38);
        }
        v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v34 + 64LL))(
                v34,
                L"GfxPipeline::HEVCHardwareEncodePreferred",
                1);
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = RdpWppGetCurrentThreadActivityIdPrefix();
            v15 = 45;
            v16 = "Failed to set HEVC full screen mode property";
            goto LABEL_16;
          }
          goto LABEL_17;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v30) = v20;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)WPP_74da7902196636370942c8c90025961d_Traceguids,
        v21,
        (__int64)"Failed to get HEVC preferred property. Ignoring this failure, it is an optional property.",
        v30);
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v35 + 40LL))(
            v35,
            ((unsigned __int64)this + 112) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
            0);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 46;
        v16 = "Failed to connect  ";
        goto LABEL_16;
      }
      goto LABEL_17;
    }
    v28 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
  }
  else
  {
    v11 = 0;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v44 = 545;
      v36 = "Ignoring session creaton event dispatched after termination";
      v38 = "CreateRDPConnection";
      v37 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\sessmgrshim.cpp";
      v33 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v8,
        (unsigned int)&word_1802855B6,
        v9,
        v10,
        (__int64)&v36,
        (__int64)&v33,
        (__int64)&v37,
        (__int64)&v44,
        (__int64)&v38);
    }
  }
LABEL_85:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v39);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v34);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v35);
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v41);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800f8ed0  mov     [rsp-8+arg_8], rbx
0x1800f8ed5  mov     [rsp-8+arg_10], rsi
0x1800f8eda  push    rbp
0x1800f8edb  push    rdi
0x1800f8edc  push    r12
0x1800f8ede  push    r14
0x1800f8ee0  push    r15
0x1800f8ee2  lea     rbp, [rsp-2Fh]
0x1800f8ee7  sub     rsp, 0E0h
0x1800f8eee  mov     r14, rcx
0x1800f8ef1  xor     r12d, r12d
0x1800f8ef4  lea     rcx, [rbp+4Fh+var_98]
0x1800f8ef8  mov     [rbp+4Fh+var_58], r12
0x1800f8efc  mov     [rbp+4Fh+var_98], r12
0x1800f8f00  mov     rdi, rdx
0x1800f8f03  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800f8f08  xor     eax, eax
0x1800f8f0a  mov     [rbp+4Fh+var_A0], r12
0x1800f8f0e  xorps   xmm0, xmm0
0x1800f8f11  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x1800f8f15  xorps   xmm1, xmm1
0x1800f8f18  mov     qword ptr [rbp+4Fh+var_38+10h], rax
0x1800f8f1c  lea     rsi, [r14+0A8h]
0x1800f8f23  mov     qword ptr [rbp+4Fh+var_70+10h], rax
0x1800f8f27  mov     rcx, rsi; this
0x1800f8f2a  mov     [rbp+4Fh+var_78], r12
0x1800f8f2e  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x1800f8f32  movups  xmmword ptr [rbp+4Fh+var_38], xmm1
0x1800f8f36  movups  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800f8f3a  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x1800f8f3f  test    byte ptr [r14+24h], 4
0x1800f8f44  mov     ebx, r12d
0x1800f8f47  jnz     short loc_1800F8F6F
0x1800f8f49  cmp     [r14+0D0h], r12
0x1800f8f50  jz      short loc_1800F8F6F
0x1800f8f52  lea     rcx, [rbp+4Fh+var_78]
0x1800f8f56  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f8f5b  mov     rbx, [r14+0D0h]
0x1800f8f62  lea     rcx, [rbp+4Fh+var_78]
0x1800f8f66  mov     [rbp+4Fh+var_78], rbx
0x1800f8f6a  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800f8f6f  mov     rcx, rsi; this
0x1800f8f72  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x1800f8f77  test    rbx, rbx
0x1800f8f7a  jz      loc_1800F95F1
0x1800f8f80  mov     rax, [rbx]
0x1800f8f83  lea     r9, [rbp+4Fh+var_98]
0x1800f8f87  mov     r8, rdi
0x1800f8f8a  mov     [rsp+100h+var_E0], r12
0x1800f8f8f  lea     rdx, CLSID_RDPCoreConnection
0x1800f8f96  mov     rcx, rbx
0x1800f8f99  mov     rax, [rax+18h]
0x1800f8f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8fa2  mov     ebx, eax
0x1800f8fa4  test    eax, eax
0x1800f8fa6  jns     short loc_1800F8FE6
0x1800f8fa8  mov     rax, cs:WPP_GLOBAL_Control
0x1800f8faf  lea     rdi, WPP_GLOBAL_Control
0x1800f8fb6  cmp     rax, rdi
0x1800f8fb9  jz      loc_1800F95E1
0x1800f8fbf  test    byte ptr [rax+1Ch], 8
0x1800f8fc3  jz      loc_1800F95E1
0x1800f8fc9  cmp     byte ptr [rax+19h], 2
0x1800f8fcd  jb      loc_1800F95E1
0x1800f8fd3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f8fd8  mov     edx, 25h ; '%'
0x1800f8fdd  mov     dword ptr [rsp+100h+var_D8], ebx
0x1800f8fe1  jmp     loc_1800F95BB
0x1800f8fe6  mov     rcx, [rbp+4Fh+var_98]
0x1800f8fea  test    rcx, rcx
0x1800f8fed  jz      loc_1800F9585
0x1800f8ff3  mov     [rbp+4Fh+var_B0], r12
0x1800f8ff7  lea     rdx, [rbp+4Fh+var_A0]
0x1800f8ffb  mov     rax, [rcx]
0x1800f8ffe  mov     rax, [rax+50h]
0x1800f9002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9007  mov     ebx, eax
0x1800f9009  test    eax, eax
0x1800f900b  jns     short loc_1800F9082
0x1800f900d  mov     rax, cs:WPP_GLOBAL_Control
0x1800f9014  lea     rdi, WPP_GLOBAL_Control
0x1800f901b  cmp     rax, rdi
0x1800f901e  jz      short loc_1800F9060
0x1800f9020  test    byte ptr [rax+1Ch], 8
0x1800f9024  jz      short loc_1800F9060
0x1800f9026  cmp     byte ptr [rax+19h], 2
0x1800f902a  jb      short loc_1800F9060
0x1800f902c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f9031  mov     edx, 26h ; '&'
0x1800f9036  lea     rcx, aFailedToGetPrp; "Failed to get Prperty  bag from connect"...
0x1800f903d  mov     dword ptr [rsp+100h+var_D8], ebx
0x1800f9041  lea     r8, WPP_74da7902196636370942c8c90025961d_Traceguids
0x1800f9048  mov     [rsp+100h+var_E0], rcx
0x1800f904d  mov     r9d, eax
0x1800f9050  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9057  mov     rcx, [rcx+10h]
0x1800f905b  call    WPP_SF_DsD
0x1800f9060  mov     rcx, [rbp+4Fh+var_B0]
0x1800f9064  test    rcx, rcx
0x1800f9067  jz      loc_1800F95E1
0x1800f906d  mov     [rbp+4Fh+var_B0], r12
0x1800f9071  mov     rax, [rcx]
0x1800f9074  mov     rax, [rax+10h]
0x1800f9078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f907d  jmp     loc_1800F95E1
0x1800f9082  mov     rcx, [rbp+4Fh+var_A0]
0x1800f9086  lea     rdx, aFallowadvanced; "fAllowAdvancedCompression"
0x1800f908d  mov     esi, 1
0x1800f9092  mov     r8d, esi
0x1800f9095  mov     rax, [rcx]
0x1800f9098  mov     rax, [rax+40h]
0x1800f909c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f90a1  mov     ebx, eax
0x1800f90a3  test    eax, eax
0x1800f90a5  jns     short loc_1800F90DA
0x1800f90a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800f90ae  lea     rdi, WPP_GLOBAL_Control
0x1800f90b5  cmp     rax, rdi
0x1800f90b8  jz      short loc_1800F9060
0x1800f90ba  test    byte ptr [rax+1Ch], 8
0x1800f90be  jz      short loc_1800F9060
0x1800f90c0  cmp     byte ptr [rax+19h], 2
0x1800f90c4  jb      short loc_1800F9060
0x1800f90c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f90cb  lea     edx, [rsi+26h]
0x1800f90ce  lea     rcx, aFailedToSetThe; "Failed to set the property CONN_ALLOW_A"...
0x1800f90d5  jmp     loc_1800F903D
0x1800f90da  mov     rax, [rdi]
0x1800f90dd  lea     r8, [rbp+4Fh+var_B0]
0x1800f90e1  lea     rdx, IID_IRDPENCCONSecurityFilterStream
0x1800f90e8  mov     rcx, rdi
0x1800f90eb  mov     rax, [rax]
0x1800f90ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f90f3  test    eax, eax
0x1800f90f5  js      short loc_1800F9158
0x1800f90f7  mov     rcx, [rbp+4Fh+var_A0]
0x1800f90fb  lea     rdx, aRdpencstackEnc_0; "RDPENCSTACK_ENCRYPTED_STREAM"
0x1800f9102  mov     r8d, esi
0x1800f9105  mov     rax, [rcx]
0x1800f9108  mov     rax, [rax+40h]
0x1800f910c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9111  mov     ebx, eax
0x1800f9113  test    eax, eax
0x1800f9115  jns     short loc_1800F9158
0x1800f9117  mov     rax, cs:WPP_GLOBAL_Control
0x1800f911e  lea     rdi, WPP_GLOBAL_Control
0x1800f9125  cmp     rax, rdi
0x1800f9128  jz      loc_1800F9060
0x1800f912e  test    byte ptr [rax+1Ch], 8
0x1800f9132  jz      loc_1800F9060
0x1800f9138  cmp     byte ptr [rax+19h], 2
0x1800f913c  jb      loc_1800F9060
0x1800f9142  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f9147  mov     edx, 28h ; '('
0x1800f914c  lea     rcx, aFailedToSetThe_9; "Failed to set the property RDPENC_STACK"...
0x1800f9153  jmp     loc_1800F903D
0x1800f9158  mov     r8, [rbp+4Fh+arg_20]
0x1800f915c  test    r8, r8
0x1800f915f  jz      short loc_1800F91BF
0x1800f9161  mov     rcx, [rbp+4Fh+var_A0]
0x1800f9165  lea     rdx, aMultitransport_1; "MultiTransportListener"
0x1800f916c  mov     rax, [rcx]
0x1800f916f  mov     rax, [rax+50h]
0x1800f9173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9178  mov     ebx, eax
0x1800f917a  test    eax, eax
0x1800f917c  jns     short loc_1800F91BF
0x1800f917e  mov     rax, cs:WPP_GLOBAL_Control
0x1800f9185  lea     rdi, WPP_GLOBAL_Control
0x1800f918c  cmp     rax, rdi
0x1800f918f  jz      loc_1800F9060
0x1800f9195  test    byte ptr [rax+1Ch], 8
0x1800f9199  jz      loc_1800F9060
0x1800f919f  cmp     byte ptr [rax+19h], 2
0x1800f91a3  jb      loc_1800F9060
0x1800f91a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f91ae  mov     edx, 29h ; ')'
0x1800f91b3  lea     rcx, aFailedToSetThe_17; "Failed to set the property CONN_PROPERT"...
0x1800f91ba  jmp     loc_1800F903D
0x1800f91bf  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x1800f91c3  call    cs:__imp_VariantInit
0x1800f91c9  mov     rcx, [r14+0C8h]
0x1800f91d0  lea     r8, [rbp+4Fh+pvarg]
0x1800f91d4  lea     rdx, aGfxpipelineAvc_2; "GfxPipeline::AVC444ModePreferred"
0x1800f91db  mov     rax, [rcx]
0x1800f91de  mov     rax, [rax+18h]
0x1800f91e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f91e7  lea     rdi, WPP_GLOBAL_Control
0x1800f91ee  mov     ebx, eax
0x1800f91f0  lea     rsi, aCreaterdpconne; "CreateRDPConnection"
0x1800f91f7  lea     r15, aOnecoreTermsrv_42; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800f91fe  test    eax, eax
0x1800f9200  jns     loc_1800F9337
0x1800f9206  mov     rax, cs:WPP_GLOBAL_Control
0x1800f920d  cmp     rax, rdi
0x1800f9210  jz      short loc_1800F9252
0x1800f9212  test    byte ptr [rax+1Ch], 8
0x1800f9216  jz      short loc_1800F9252
0x1800f9218  cmp     byte ptr [rax+19h], 2
0x1800f921c  jb      short loc_1800F9252
0x1800f921e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f9223  lea     rcx, aFailedToGetAvc; "Failed to get AVC444 full screen prefer"...
0x1800f922a  mov     dword ptr [rsp+100h+var_D8], ebx
0x1800f922e  mov     [rsp+100h+var_E0], rcx
0x1800f9233  lea     r8, WPP_74da7902196636370942c8c90025961d_Traceguids
0x1800f923a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9241  mov     edx, 2Ah ; '*'
0x1800f9246  mov     r9d, eax
0x1800f9249  mov     rcx, [rcx+10h]
0x1800f924d  call    WPP_SF_DsD
0x1800f9252  lea     rcx, [rbp+4Fh+var_38]; pvarg
0x1800f9256  call    cs:__imp_VariantInit
0x1800f925c  mov     rcx, [r14+0C8h]
0x1800f9263  lea     r8, [rbp+4Fh+var_38]
0x1800f9267  lea     rdx, aGfxpipelineHev; "GfxPipeline::HEVCHardwareEncodePreferre"...
0x1800f926e  mov     rax, [rcx]
0x1800f9271  mov     rax, [rax+18h]
0x1800f9275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f927a  mov     ebx, eax
0x1800f927c  test    eax, eax
0x1800f927e  jns     loc_1800F944D
0x1800f9284  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f928b  cmp     rcx, rdi
0x1800f928e  jz      short loc_1800F92D0
0x1800f9290  test    byte ptr [rcx+1Ch], 8
0x1800f9294  jz      short loc_1800F92D0
0x1800f9296  cmp     byte ptr [rcx+19h], 2
0x1800f929a  jb      short loc_1800F92D0
0x1800f929c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f92a1  lea     rcx, aFailedToGetHev; "Failed to get HEVC preferred property. "...
0x1800f92a8  mov     dword ptr [rsp+100h+var_D8], ebx
0x1800f92ac  mov     [rsp+100h+var_E0], rcx
0x1800f92b1  lea     r8, WPP_74da7902196636370942c8c90025961d_Traceguids
0x1800f92b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f92bf  mov     edx, 2Ch ; ','
0x1800f92c4  mov     r9d, eax
0x1800f92c7  mov     rcx, [rcx+10h]
0x1800f92cb  call    WPP_SF_DsD
0x1800f92d0  mov     rcx, [rbp+4Fh+var_98]
0x1800f92d4  lea     r8, [r14+70h]
0x1800f92d8  mov     rax, r14
0x1800f92db  neg     rax
0x1800f92de  mov     r9, [rcx]
0x1800f92e1  sbb     rdx, rdx
0x1800f92e4  and     rdx, r8
0x1800f92e7  xor     r8d, r8d
0x1800f92ea  mov     rax, [r9+28h]
0x1800f92ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f92f3  mov     ebx, eax
0x1800f92f5  test    eax, eax
0x1800f92f7  jns     loc_1800F9563
0x1800f92fd  mov     rax, cs:WPP_GLOBAL_Control
0x1800f9304  cmp     rax, rdi
0x1800f9307  jz      loc_1800F9060
0x1800f930d  test    byte ptr [rax+1Ch], 8
0x1800f9311  jz      loc_1800F9060
0x1800f9317  cmp     byte ptr [rax+19h], 2
0x1800f931b  jb      loc_1800F9060
0x1800f9321  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f9326  mov     edx, 2Eh ; '.'
0x1800f932b  lea     rcx, aFailedToConnec; "Failed to connect  "
0x1800f9332  jmp     loc_1800F903D
0x1800f9337  cmp     word ptr [rbp+4Fh+pvarg], 0Bh
0x1800f933c  jnz     loc_1800F9252
0x1800f9342  cmp     word ptr [rbp+4Fh+pvarg+8], 0FFFFh
0x1800f9347  jnz     loc_1800F9252
0x1800f934d  lea     rcx, [rbp+4Fh+var_70]; pvarg
0x1800f9351  call    cs:__imp_VariantInit
0x1800f9357  mov     rcx, [r14+0C8h]
0x1800f935e  lea     r8, [rbp+4Fh+var_70]
0x1800f9362  lea     rdx, aGfxpipelineFor; "GfxPipeline::ForceLyncProfile"
0x1800f9369  mov     rax, [rcx]
0x1800f936c  mov     rax, [rax+18h]
0x1800f9370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9375  test    eax, eax
0x1800f9377  js      short loc_1800F93EC
0x1800f9379  cmp     word ptr [rbp+4Fh+var_70], 0Bh
0x1800f937e  jnz     short loc_1800F93EC
0x1800f9380  cmp     word ptr [rbp+4Fh+var_70+8], 0FFFFh
0x1800f9385  jnz     short loc_1800F93EC
0x1800f9387  mov     eax, cs:CallbackContext
0x1800f938d  cmp     eax, 2
0x1800f9390  jbe     short loc_1800F93EC
0x1800f9392  lea     rax, aCannotHaveSetB_0; "Cannot have set both AVC full screen an"...
0x1800f9399  mov     [rbp+4Fh+var_90], rsi
0x1800f939d  mov     [rbp+4Fh+var_80], rax
0x1800f93a1  lea     rdx, byte_1802855FB
0x1800f93a8  lea     rax, [rbp+4Fh+var_90]
0x1800f93ac  mov     [rbp+4Fh+arg_0], 1F7h
0x1800f93b3  mov     [rsp+100h+var_C0], rax
0x1800f93b8  lea     rax, [rbp+4Fh+arg_0]
0x1800f93bc  mov     [rsp+100h+var_C8], rax
0x1800f93c1  lea     rax, [rbp+4Fh+var_88]
0x1800f93c5  mov     [rsp+100h+var_D0], rax
0x1800f93ca  lea     rax, [rbp+4Fh+var_A8]
0x1800f93ce  mov     [rsp+100h+var_D8], rax
0x1800f93d3  lea     rax, [rbp+4Fh+var_80]
0x1800f93d7  mov     [rsp+100h+var_E0], rax
0x1800f93dc  mov     [rbp+4Fh+var_88], r15
0x1800f93e0  mov     [rbp+4Fh+var_A8], 80004005h
  ... truncated ...
```
