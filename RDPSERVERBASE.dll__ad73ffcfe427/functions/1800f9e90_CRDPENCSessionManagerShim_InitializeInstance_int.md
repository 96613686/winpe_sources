# CRDPENCSessionManagerShim::InitializeInstance(int)

- ea: `0x1800f9e90`
- end: `0x1800fa75b`
- name: `?InitializeInstance@CRDPENCSessionManagerShim@@UEAAJH@Z`
- size: `2251`
- prototype: `__int64 __fastcall(CRDPENCSessionManagerShim *__hidden this, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000116c`
- `0x18000ce04`
- `0x18000ce34`
- `0x1800439a0`
- `0x180044000`
- `0x180076090`
- `0x180079724`
- `0x180079770`
- `0x18007af60`
- `0x1800f9e90`
- `0x180132c84`
- `0x180132d04`
- `0x18019c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f9f36`
- `OLEAUT32!__imp_VariantInit` at `0x1800f9f36`
- `OLEAUT32!__imp_VariantClear` at `0x1800fa6ab`
- `OLEAUT32!__imp_VariantClear` at `0x1800fa6ab`

## string_xrefs

- `0x1800fa321`: `gfxplugin`
- `0x1800fa125`: `Failed to create the coreConnectionManager`
- `0x1800fa190`: `Failed to create the ENC VC plugin`
- `0x1800fa2b0`: `Failed to Initalize instance: VCPlugin `
- `0x1800fa259`: `Failed to QI for IID_IRDPCOREChannelPluginFactory`
- `0x1800fa3eb`: `Failed to register GFX plugin factory`
- `0x1800fa30a`: `Failed to register VC plugin factory`
- `0x1800fa4bf`: `Failed to create the licensing plugin factory`
- `0x1800fa42d`: `No gfx plugin registered`
- `0x1800fa5cd`: `Failed to register command plugin factory`
- `0x1800fa573`: `Failed to create Command Channel Factory`
- `0x1800fa675`: `Failed to register basic input plugin factory`
- `0x1800fa62a`: `Failed to create the basic input plugin factory`

## pseudocode

```c
__int64 __fastcall CRDPENCSessionManagerShim::InitializeInstance(CRDPENCSessionManagerShim *this, int a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int LegacyContext; // ebx
  __int64 v6; // rbx
  __int64 *v7; // rbx
  __int64 v8; // rsi
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  struct _CERT_CONTEXT **Instance; // rax
  struct IUnknown *v14; // rcx
  _QWORD *v15; // rsi
  _QWORD *v16; // r14
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v26; // [rsp+50h] [rbp-19h] BYREF
  void *v27; // [rsp+58h] [rbp-11h] BYREF
  void *v28; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+68h] [rbp-1h] BYREF
  const char *v30; // [rsp+70h] [rbp+7h] BYREF
  const char *v31; // [rsp+78h] [rbp+Fh] BYREF
  const char *v32; // [rsp+80h] [rbp+17h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp+1Fh] BYREF
  int v34; // [rsp+D0h] [rbp+67h] BYREF
  int v35; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v36; // [rsp+E8h] [rbp+7Fh] BYREF

  v36 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v26 = 0;
  if ( (*((_BYTE *)this + 36) & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_74da7902196636370942c8c90025961d_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    LegacyContext = -2147418113;
    goto LABEL_104;
  }
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 25) + 144LL))(*((_QWORD *)this + 25));
  if ( v6 != *((_QWORD *)this + 24) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 192);
    *((_QWORD *)this + 24) = v6;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  *((_DWORD *)this + 9) |= 2u;
  v7 = (__int64 *)((char *)this + 184);
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 25) + 152LL))(*((_QWORD *)this + 25));
  if ( v8 != *((_QWORD *)this + 23) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 184);
    *v7 = v8;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 184);
  }
  if ( !*v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_74da7902196636370942c8c90025961d_Traceguids,
        v9,
        -2147467263);
    }
    LegacyContext = -2147467263;
    goto LABEL_104;
  }
  LegacyContext = RDPWDUMX_CreateLegacyContext();
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 18;
    v12 = "Failed to init the legacy stack context";
    goto LABEL_103;
  }
  if ( a2 )
  {
    Instance = (struct _CERT_CONTEXT **)SessionAuthenticationCertificateManager::GetInstance();
    LegacyContext = SessionAuthenticationCertificateManager::PrepareCertificate(Instance);
    if ( LegacyContext < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_104;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 19;
      v12 = "Failed to init the TLS stack context";
      goto LABEL_103;
    }
  }
  v14 = (struct IUnknown *)*((_QWORD *)this + 25);
  v15 = (_QWORD *)((char *)this + 208);
  *((_DWORD *)this + 59) = 1;
  LegacyContext = RDPSERVERBASE_CreateInstance(
                    v14,
                    &CLSID_RDPCoreConnectionMgr,
                    &IID_IRDPCoreConnectionMgr,
                    (void **)this + 26);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 20;
    v12 = "Failed to create the coreConnectionManager";
    goto LABEL_103;
  }
  v16 = (_QWORD *)((char *)this + 216);
  LegacyContext = RDPSERVERBASE_CreateInstance(
                    *((struct IUnknown **)this + 25),
                    &CLSID_IRDPENCVCManager,
                    &IID_IRDPENCVCManager,
                    (void **)this + 27);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 21;
    v12 = "Failed to create the ENC VC plugin";
    goto LABEL_103;
  }
  LegacyContext = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v16 + 24LL))(
                    *v16,
                    ((unsigned __int64)this + 120) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 22;
    v12 = "Failed to Initalize instance: IRDPENCVCManager ";
    goto LABEL_103;
  }
  LegacyContext = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v16)(
                    *v16,
                    &IID_IRDPCOREChannelPluginFactory,
                    &v36);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 23;
    v12 = "Failed to QI for IID_IRDPCOREChannelPluginFactory";
    goto LABEL_103;
  }
  LegacyContext = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 24;
    v12 = "Failed to Initalize instance: VCPlugin ";
    goto LABEL_103;
  }
  LegacyContext = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v15 + 64LL))(*v15, v36);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 25;
    v12 = "Failed to register VC plugin factory";
    goto LABEL_103;
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 25) + 24LL))(
         *((_QWORD *)this + 25),
         L"gfxplugin",
         &pvarg) < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v34 = 246;
      v30 = "InitializeInstance";
      v35 = -2147467259;
      v31 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\sessmgrshim.cpp";
      v32 = "No gfx plugin registered";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)qword_180285640,
        v18,
        v19,
        (__int64)&v32,
        (__int64)&v35,
        (__int64)&v31,
        (__int64)&v34,
        (__int64)&v30);
    }
  }
  else
  {
    LegacyContext = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
                      pvarg.llVal,
                      &IID_IRDPCOREChannelPluginFactory,
                      &v29);
    if ( LegacyContext < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_104;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 26;
      v12 = "Failed to QueryInterface for IUnkown interface";
      goto LABEL_103;
    }
    LegacyContext = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v15 + 64LL))(*v15, v29);
    if ( LegacyContext < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_104;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 27;
      goto LABEL_70;
    }
  }
  LegacyContext = RDPSERVERBASE_CreateInstance(
                    *((struct IUnknown **)this + 25),
                    &CLSID_RDPEncLICPluginFactory,
                    &IID_IRDPCOREChannelPluginFactory,
                    &v28);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 28;
    v12 = "Failed to create the licensing plugin factory";
    goto LABEL_103;
  }
  LegacyContext = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v15 + 64LL))(*v15, v28);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 29;
LABEL_70:
    v12 = "Failed to register GFX plugin factory";
LABEL_103:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_74da7902196636370942c8c90025961d_Traceguids,
      v10,
      (__int64)v12,
      LegacyContext);
    goto LABEL_104;
  }
  LegacyContext = RDPSERVERBASE_CreateInstance(
                    *((struct IUnknown **)this + 25),
                    &CLSID_RdpCommandChannelFactory,
                    &IID_IRDPCOREChannelPluginFactory,
                    &v27);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 30;
    v12 = "Failed to create Command Channel Factory";
    goto LABEL_103;
  }
  LegacyContext = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v15 + 64LL))(*v15, v27);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 31;
    v12 = "Failed to register command plugin factory";
    goto LABEL_103;
  }
  LegacyContext = RDPSERVERBASE_CreateInstance(
                    *((struct IUnknown **)this + 25),
                    &CLSID_RDPENCBasicInputPluginFactory,
                    &IID_IRDPCOREChannelPluginFactory,
                    &v26);
  if ( LegacyContext < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 32;
    v12 = "Failed to create the basic input plugin factory";
    goto LABEL_103;
  }
  LegacyContext = (*(__int64 (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v15 + 64LL))(*v15, v26);
  if ( LegacyContext >= 0 )
    goto LABEL_105;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 33;
    v12 = "Failed to register basic input plugin factory";
    goto LABEL_103;
  }
LABEL_104:
  CRDPENCSessionManagerShim::TerminateInstance(this);
LABEL_105:
  VariantClear(&pvarg);
  v20 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return (unsigned int)LegacyContext;
}

```

## disassembly

```asm
0x1800f9e90  mov     [rsp-8+arg_8], rbx
0x1800f9e95  push    rbp
0x1800f9e96  push    rsi
0x1800f9e97  push    rdi
0x1800f9e98  push    r12
0x1800f9e9a  push    r14
0x1800f9e9c  lea     rbp, [rsp-37h]
0x1800f9ea1  sub     rsp, 0A0h
0x1800f9ea8  xor     eax, eax
0x1800f9eaa  mov     [rbp+57h+arg_18], 0
0x1800f9eb2  xorps   xmm0, xmm0
0x1800f9eb5  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800f9eb9  mov     r14d, edx
0x1800f9ebc  mov     [rbp+57h+var_58], rax
0x1800f9ec0  mov     rdi, rcx
0x1800f9ec3  mov     [rbp+57h+var_60], rax
0x1800f9ec7  lea     r12d, [rax+2]
0x1800f9ecb  mov     [rbp+57h+var_68], rax
0x1800f9ecf  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800f9ed3  mov     [rbp+57h+var_70], rax
0x1800f9ed7  test    [rcx+24h], r12b
0x1800f9edb  jz      short loc_1800F9F32
0x1800f9edd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9ee4  lea     rax, WPP_GLOBAL_Control
0x1800f9eeb  cmp     rcx, rax
0x1800f9eee  jz      short loc_1800F9F28
0x1800f9ef0  test    byte ptr [rcx+1Ch], 8
0x1800f9ef4  jz      short loc_1800F9F28
0x1800f9ef6  cmp     [rcx+19h], r12b
0x1800f9efa  jb      short loc_1800F9F28
0x1800f9efc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f9f01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9f08  lea     edx, [r12+0Dh]
0x1800f9f0d  mov     r9d, eax
0x1800f9f10  mov     dword ptr [rsp+0C0h+var_A0], 8000FFFFh
0x1800f9f18  lea     r8, WPP_74da7902196636370942c8c90025961d_Traceguids
0x1800f9f1f  mov     rcx, [rcx+10h]
0x1800f9f23  call    WPP_SF_Dd
0x1800f9f28  mov     ebx, 8000FFFFh
0x1800f9f2d  jmp     loc_1800FA69F
0x1800f9f32  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800f9f36  call    cs:__imp_VariantInit
0x1800f9f3c  mov     rcx, [rdi+0C8h]
0x1800f9f43  mov     rax, [rcx]
0x1800f9f46  mov     rax, [rax+90h]
0x1800f9f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9f52  lea     rsi, [rdi+0C0h]
0x1800f9f59  mov     rbx, rax
0x1800f9f5c  cmp     rax, [rsi]
0x1800f9f5f  jz      short loc_1800F9F80
0x1800f9f61  mov     rcx, rsi
0x1800f9f64  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f9f69  mov     [rsi], rbx
0x1800f9f6c  test    rbx, rbx
0x1800f9f6f  jz      short loc_1800F9F80
0x1800f9f71  mov     rcx, [rbx]
0x1800f9f74  mov     rax, [rcx+8]
0x1800f9f78  mov     rcx, rbx
0x1800f9f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9f80  or      [rdi+24h], r12d
0x1800f9f84  mov     rcx, [rdi+0C8h]
0x1800f9f8b  mov     rax, [rcx]
0x1800f9f8e  mov     rax, [rax+98h]
0x1800f9f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9f9a  lea     rbx, [rdi+0B8h]
0x1800f9fa1  mov     rsi, rax
0x1800f9fa4  cmp     rax, [rbx]
0x1800f9fa7  jz      short loc_1800F9FBC
0x1800f9fa9  mov     rcx, rbx
0x1800f9fac  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f9fb1  mov     rcx, rbx
0x1800f9fb4  mov     [rbx], rsi
0x1800f9fb7  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800f9fbc  cmp     qword ptr [rbx], 0
0x1800f9fc0  jnz     short loc_1800FA017
0x1800f9fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9fc9  lea     rax, WPP_GLOBAL_Control
0x1800f9fd0  cmp     rcx, rax
0x1800f9fd3  jz      short loc_1800FA00D
0x1800f9fd5  test    byte ptr [rcx+1Ch], 8
0x1800f9fd9  jz      short loc_1800FA00D
0x1800f9fdb  cmp     [rcx+19h], r12b
0x1800f9fdf  jb      short loc_1800FA00D
0x1800f9fe1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f9fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9fed  lea     r8, WPP_74da7902196636370942c8c90025961d_Traceguids
0x1800f9ff4  mov     edx, 11h
0x1800f9ff9  mov     dword ptr [rsp+0C0h+var_A0], 80004001h
0x1800fa001  mov     r9d, eax
0x1800fa004  mov     rcx, [rcx+10h]
0x1800fa008  call    WPP_SF_Dd
0x1800fa00d  mov     ebx, 80004001h
0x1800fa012  jmp     loc_1800FA69F
0x1800fa017  call    RDPWDUMX_CreateLegacyContext
0x1800fa01c  mov     ebx, eax
0x1800fa01e  test    eax, eax
0x1800fa020  jns     short loc_1800FA063
0x1800fa022  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa029  lea     rax, WPP_GLOBAL_Control
0x1800fa030  cmp     rcx, rax
0x1800fa033  jz      loc_1800FA69F
0x1800fa039  test    byte ptr [rcx+1Ch], 8
0x1800fa03d  jz      loc_1800FA69F
0x1800fa043  cmp     [rcx+19h], r12b
0x1800fa047  jb      loc_1800FA69F
0x1800fa04d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa052  mov     edx, 12h
0x1800fa057  lea     rcx, aFailedToInitTh; "Failed to init the legacy stack context"
0x1800fa05e  jmp     loc_1800FA67C
0x1800fa063  test    r14d, r14d
0x1800fa066  jz      short loc_1800FA0BC
0x1800fa068  call    ?GetInstance@SessionAuthenticationCertificateManager@@SAAEAV1@XZ; SessionAuthenticationCertificateManager::GetInstance(void)
0x1800fa06d  mov     rcx, rax; this
0x1800fa070  call    ?PrepareCertificate@SessionAuthenticationCertificateManager@@QEAAJXZ; SessionAuthenticationCertificateManager::PrepareCertificate(void)
0x1800fa075  mov     ebx, eax
0x1800fa077  test    eax, eax
0x1800fa079  jns     short loc_1800FA0BC
0x1800fa07b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa082  lea     rax, WPP_GLOBAL_Control
0x1800fa089  cmp     rcx, rax
0x1800fa08c  jz      loc_1800FA69F
0x1800fa092  test    byte ptr [rcx+1Ch], 8
0x1800fa096  jz      loc_1800FA69F
0x1800fa09c  cmp     [rcx+19h], r12b
0x1800fa0a0  jb      loc_1800FA69F
0x1800fa0a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa0ab  mov     edx, 13h
0x1800fa0b0  lea     rcx, aFailedToInitTh_0; "Failed to init the TLS stack context"
0x1800fa0b7  jmp     loc_1800FA67C
0x1800fa0bc  mov     rcx, [rdi+0C8h]
0x1800fa0c3  lea     rsi, [rdi+0D0h]
0x1800fa0ca  mov     r9, rsi
0x1800fa0cd  mov     dword ptr [rdi+0ECh], 1
0x1800fa0d7  lea     r8, IID_IRDPCoreConnectionMgr
0x1800fa0de  lea     rdx, CLSID_RDPCoreConnectionMgr
0x1800fa0e5  call    RDPSERVERBASE_CreateInstance
0x1800fa0ea  mov     ebx, eax
0x1800fa0ec  test    eax, eax
0x1800fa0ee  jns     short loc_1800FA131
0x1800fa0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa0f7  lea     rax, WPP_GLOBAL_Control
0x1800fa0fe  cmp     rcx, rax
0x1800fa101  jz      loc_1800FA69F
0x1800fa107  test    byte ptr [rcx+1Ch], 8
0x1800fa10b  jz      loc_1800FA69F
0x1800fa111  cmp     [rcx+19h], r12b
0x1800fa115  jb      loc_1800FA69F
0x1800fa11b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa120  mov     edx, 14h
0x1800fa125  lea     rcx, aFailedToCreate_105; "Failed to create the coreConnectionMana"...
0x1800fa12c  jmp     loc_1800FA67C
0x1800fa131  mov     rcx, [rdi+0C8h]
0x1800fa138  lea     r14, [rdi+0D8h]
0x1800fa13f  mov     r9, r14
0x1800fa142  lea     r8, IID_IRDPENCVCManager
0x1800fa149  lea     rdx, CLSID_IRDPENCVCManager
0x1800fa150  call    RDPSERVERBASE_CreateInstance
0x1800fa155  mov     ebx, eax
0x1800fa157  test    eax, eax
0x1800fa159  jns     short loc_1800FA19C
0x1800fa15b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa162  lea     rax, WPP_GLOBAL_Control
0x1800fa169  cmp     rcx, rax
0x1800fa16c  jz      loc_1800FA69F
0x1800fa172  test    byte ptr [rcx+1Ch], 8
0x1800fa176  jz      loc_1800FA69F
0x1800fa17c  cmp     [rcx+19h], r12b
0x1800fa180  jb      loc_1800FA69F
0x1800fa186  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa18b  mov     edx, 15h
0x1800fa190  lea     rcx, aFailedToCreate_59; "Failed to create the ENC VC plugin"
0x1800fa197  jmp     loc_1800FA67C
0x1800fa19c  mov     rcx, [r14]
0x1800fa19f  lea     r8, [rdi+78h]
0x1800fa1a3  mov     rax, rdi
0x1800fa1a6  neg     rax
0x1800fa1a9  mov     r9, [rcx]
0x1800fa1ac  sbb     rdx, rdx
0x1800fa1af  and     rdx, r8
0x1800fa1b2  mov     rax, [r9+18h]
0x1800fa1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa1bb  mov     ebx, eax
0x1800fa1bd  test    eax, eax
0x1800fa1bf  jns     short loc_1800FA202
0x1800fa1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa1c8  lea     rax, WPP_GLOBAL_Control
0x1800fa1cf  cmp     rcx, rax
0x1800fa1d2  jz      loc_1800FA69F
0x1800fa1d8  test    byte ptr [rcx+1Ch], 8
0x1800fa1dc  jz      loc_1800FA69F
0x1800fa1e2  cmp     [rcx+19h], r12b
0x1800fa1e6  jb      loc_1800FA69F
0x1800fa1ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa1f1  mov     edx, 16h
0x1800fa1f6  lea     rcx, aFailedToInital_1; "Failed to Initalize instance: IRDPENCVC"...
0x1800fa1fd  jmp     loc_1800FA67C
0x1800fa202  mov     rcx, [r14]
0x1800fa205  lea     r8, [rbp+57h+arg_18]
0x1800fa209  lea     r14, IID_IRDPCOREChannelPluginFactory
0x1800fa210  mov     rdx, r14
0x1800fa213  mov     rax, [rcx]
0x1800fa216  mov     rax, [rax]
0x1800fa219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa21e  mov     ebx, eax
0x1800fa220  test    eax, eax
0x1800fa222  jns     short loc_1800FA265
0x1800fa224  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa22b  lea     rax, WPP_GLOBAL_Control
0x1800fa232  cmp     rcx, rax
0x1800fa235  jz      loc_1800FA69F
0x1800fa23b  test    byte ptr [rcx+1Ch], 8
0x1800fa23f  jz      loc_1800FA69F
0x1800fa245  cmp     [rcx+19h], r12b
0x1800fa249  jb      loc_1800FA69F
0x1800fa24f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa254  mov     edx, 17h
0x1800fa259  lea     rcx, aFailedToQiForI_3; "Failed to QI for IID_IRDPCOREChannelPlu"...
0x1800fa260  jmp     loc_1800FA67C
0x1800fa265  mov     rcx, [rbp+57h+arg_18]
0x1800fa269  mov     rax, [rcx]
0x1800fa26c  mov     rax, [rax+18h]
0x1800fa270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa275  mov     ebx, eax
0x1800fa277  test    eax, eax
0x1800fa279  jns     short loc_1800FA2BC
0x1800fa27b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa282  lea     rax, WPP_GLOBAL_Control
0x1800fa289  cmp     rcx, rax
0x1800fa28c  jz      loc_1800FA69F
0x1800fa292  test    byte ptr [rcx+1Ch], 8
0x1800fa296  jz      loc_1800FA69F
0x1800fa29c  cmp     [rcx+19h], r12b
0x1800fa2a0  jb      loc_1800FA69F
0x1800fa2a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa2ab  mov     edx, 18h
0x1800fa2b0  lea     rcx, aFailedToInital; "Failed to Initalize instance: VCPlugin "
0x1800fa2b7  jmp     loc_1800FA67C
0x1800fa2bc  mov     rcx, [rsi]
0x1800fa2bf  mov     rdx, [rbp+57h+arg_18]
0x1800fa2c3  mov     rax, [rcx]
0x1800fa2c6  mov     rax, [rax+40h]
0x1800fa2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa2cf  mov     ebx, eax
0x1800fa2d1  test    eax, eax
0x1800fa2d3  jns     short loc_1800FA316
0x1800fa2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa2dc  lea     rax, WPP_GLOBAL_Control
0x1800fa2e3  cmp     rcx, rax
0x1800fa2e6  jz      loc_1800FA69F
0x1800fa2ec  test    byte ptr [rcx+1Ch], 8
0x1800fa2f0  jz      loc_1800FA69F
0x1800fa2f6  cmp     [rcx+19h], r12b
0x1800fa2fa  jb      loc_1800FA69F
0x1800fa300  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa305  mov     edx, 19h
0x1800fa30a  lea     rcx, aFailedToRegist_2; "Failed to register VC plugin factory"
0x1800fa311  jmp     loc_1800FA67C
0x1800fa316  mov     rcx, [rdi+0C8h]
0x1800fa31d  lea     r8, [rbp+57h+pvarg]
0x1800fa321  lea     rdx, aGfxplugin; "gfxplugin"
0x1800fa328  mov     rax, [rcx]
0x1800fa32b  mov     rax, [rax+18h]
0x1800fa32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa334  test    eax, eax
0x1800fa336  js      loc_1800FA3F7
0x1800fa33c  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x1800fa340  lea     r8, [rbp+57h+var_58]
0x1800fa344  mov     rdx, r14
0x1800fa347  mov     rax, [rcx]
0x1800fa34a  mov     rax, [rax]
0x1800fa34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa352  mov     ebx, eax
0x1800fa354  test    eax, eax
0x1800fa356  jns     short loc_1800FA399
0x1800fa358  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa35f  lea     rax, WPP_GLOBAL_Control
0x1800fa366  cmp     rcx, rax
0x1800fa369  jz      loc_1800FA69F
0x1800fa36f  test    byte ptr [rcx+1Ch], 8
0x1800fa373  jz      loc_1800FA69F
0x1800fa379  cmp     [rcx+19h], r12b
0x1800fa37d  jb      loc_1800FA69F
0x1800fa383  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa388  mov     edx, 1Ah
0x1800fa38d  lea     rcx, aFailedToQueryi; "Failed to QueryInterface for IUnkown in"...
0x1800fa394  jmp     loc_1800FA67C
0x1800fa399  mov     rcx, [rsi]
0x1800fa39c  mov     rdx, [rbp+57h+var_58]
0x1800fa3a0  mov     rax, [rcx]
0x1800fa3a3  mov     rax, [rax+40h]
0x1800fa3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa3ac  mov     ebx, eax
0x1800fa3ae  test    eax, eax
0x1800fa3b0  jns     loc_1800FA46A
0x1800fa3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa3bd  lea     rax, WPP_GLOBAL_Control
0x1800fa3c4  cmp     rcx, rax
0x1800fa3c7  jz      loc_1800FA69F
0x1800fa3cd  test    byte ptr [rcx+1Ch], 8
0x1800fa3d1  jz      loc_1800FA69F
  ... truncated ...
```
