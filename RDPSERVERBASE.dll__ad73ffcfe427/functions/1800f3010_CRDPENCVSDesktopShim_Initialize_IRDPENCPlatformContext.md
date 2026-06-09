# CRDPENCVSDesktopShim::Initialize(IRDPENCPlatformContext *)

- ea: `0x1800f3010`
- end: `0x1800f35b7`
- name: `?Initialize@CRDPENCVSDesktopShim@@UEAAJPEAUIRDPENCPlatformContext@@@Z`
- size: `1447`
- prototype: `__int64 __fastcall(CRDPENCVSDesktopShim *__hidden this, struct IRDPENCPlatformContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f02a0`

## callees

- `0x18000ce04`
- `0x18000ce34`
- `0x18000e4ec`
- `0x18000f660`
- `0x180076090`
- `0x180077770`
- `0x180079724`
- `0x180079770`
- `0x1800f3010`
- `0x1800f3618`
- `0x1800f3a88`
- `0x18019c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f30d5`
- `OLEAUT32!__imp_VariantInit` at `0x1800f30d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800f310d`
- `OLEAUT32!__imp_VariantClear` at `0x1800f310d`

## string_xrefs

- `0x1800f3311`: `RDPCodecCache::NSCodec`
- `0x1800f33dd`: `RDPCodecCache::ImgCaCodec`
- `0x1800f30e2`: `CRDPENCVSDesktopShim::EnableCodecCache`
- `0x1800f3183`: `RDPCodecCache::Factory`
- `0x1800f323e`: `Failed to create planar compressor cache`
- `0x1800f3289`: `Failed to save planar compressor cache to property store`
- `0x1800f324a`: `RDPCodecCache::Planar`
- `0x1800f3350`: `Failed to save NSCodec compressor cache to property store`
- `0x1800f3305`: `Failed to create NSCodec compressor cache`
- `0x1800f341f`: `Failed to save ImgCACodec compressor cache to property store`
- `0x1800f33d1`: `Failed to create ImgCACodec compressor cache`
- `0x1800f3537`: `gfxplugin`

## pseudocode

```c
__int64 __fastcall CRDPENCVSDesktopShim::Initialize(CRDPENCVSDesktopShim *this, struct IRDPENCPlatformContext *a2)
{
  unsigned int v4; // eax
  int v5; // edi
  _QWORD *v6; // rdi
  int v7; // r12d
  int v8; // eax
  char v9; // r12
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  int v13; // eax
  int v14; // eax
  char v15; // r12
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  int v19; // eax
  int v20; // eax
  char v21; // r12
  unsigned int v22; // eax
  int v23; // edx
  const char *v24; // rcx
  int v25; // eax
  int v26; // eax
  char v27; // r12
  unsigned int v28; // eax
  int v29; // edi
  unsigned int v30; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v32; // edx
  const char *v33; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF
  __int64 v36; // [rsp+A0h] [rbp+48h] BYREF

  v36 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (unsigned int)CTSCriticalSection::Initialize((CRDPENCVSDesktopShim *)((char *)this + 104)) )
  {
    v6 = (_QWORD *)((char *)this + 160);
    *((_DWORD *)this + 21) |= 2u;
    v7 = 0;
    if ( a2 != *((struct IRDPENCPlatformContext **)this + 20) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 160);
      *v6 = a2;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 160);
    }
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(*(_QWORD *)*v6 + 24LL))(
           *v6,
           L"CRDPENCVSDesktopShim::EnableCodecCache",
           &pvarg) >= 0
      && pvarg.vt == 11 )
    {
      LOBYTE(v7) = pvarg.iVal == -1;
    }
    VariantClear(&pvarg);
    if ( !v7 )
    {
LABEL_57:
      v5 = CRDPENCVSDesktopShim::InitializeAudioManager(this);
      if ( v5 >= 0 )
      {
        v5 = CRDPENCVSDesktopShim::InitializeCollabTouchManager(this);
        if ( v5 >= 0 )
        {
          v5 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 11))(
                 *((_QWORD *)this + 11),
                 &IID_IUnknown,
                 &v36);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 20) + 80LL))(
                   *((_QWORD *)this + 20),
                   L"gfxplugin",
                   v36);
            if ( v5 >= 0
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_78;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v32 = 27;
            v33 = "Failed to SetProperty in platform context";
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_78;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v32 = 26;
            v33 = "Failed to QueryInterface for IUnkown interface";
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_78;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v32 = 25;
          v33 = "InitializeCollabTouchManager failed.";
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_78;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v32 = 24;
        v33 = "InitializeAudioManager failed.";
      }
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v32,
        (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v33,
        v5);
      goto LABEL_78;
    }
    v8 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 11))(
           *((_QWORD *)this + 11),
           &IID_IUnknown,
           &v36);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)*v6 + 80LL))(
              *v6,
              L"RDPCodecCache::Factory",
              v36);
      v9 = v13;
      if ( v13 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 17;
        v12 = "Failed to save our codec factory to property store";
        goto LABEL_23;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 16;
      v12 = "Failed to QI ourselves for IUnknown";
LABEL_23:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
        v10,
        (__int64)v12,
        v9);
    }
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v36, 0);
    v14 = RDPAPI_CreateInstance(*v6, &CLSID_RDPCompressorCache, &IID_IUnknown, &v36);
    v15 = v14;
    if ( v14 >= 0 )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)*v6 + 80LL))(
              *v6,
              L"RDPCodecCache::Planar",
              v36);
      v15 = v19;
      if ( v19 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 19;
        v18 = "Failed to save planar compressor cache to property store";
        goto LABEL_34;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 18;
      v18 = "Failed to create planar compressor cache";
LABEL_34:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
        v16,
        (__int64)v18,
        v15);
    }
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v36, 0);
    v20 = RDPAPI_CreateInstance(*v6, &CLSID_RDPNsCodecCompressorCache, &IID_IUnknown, &v36);
    v21 = v20;
    if ( v20 >= 0 )
    {
      v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)*v6 + 80LL))(
              *v6,
              L"RDPCodecCache::NSCodec",
              v36);
      v21 = v25;
      if ( v25 >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 21;
      v24 = "Failed to save NSCodec compressor cache to property store";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 20;
      v24 = "Failed to create NSCodec compressor cache";
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
      v22,
      (__int64)v24,
      v21);
LABEL_46:
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v36, 0);
    v26 = RDPAPI_CreateInstance(*v6, &CLSID_RDPCACCodecCompressorCache, &IID_IRdpImageCompressor, &v36);
    v27 = v26;
    if ( v26 >= 0 )
    {
      v29 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)*v6 + 80LL))(
              *v6,
              L"RDPCodecCache::ImgCaCodec",
              v36);
      if ( v29 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
          v30,
          (__int64)"Failed to save ImgCACodec compressor cache to property store",
          v29);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
        v28,
        (__int64)"Failed to create ImgCACodec compressor cache",
        v27);
    }
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v36, 0);
    goto LABEL_57;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids, v4, -2147467259);
  }
  v5 = -2147467259;
LABEL_78:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v36);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800f3010  push    rbp
0x1800f3012  push    rbx
0x1800f3013  push    rsi
0x1800f3014  push    rdi
0x1800f3015  push    r12
0x1800f3017  push    r13
0x1800f3019  push    r14
0x1800f301b  push    r15
0x1800f301d  mov     rbp, rsp
0x1800f3020  sub     rsp, 58h
0x1800f3024  mov     r13, rcx
0x1800f3027  mov     [rbp+arg_0], 0
0x1800f302f  xorps   xmm0, xmm0
0x1800f3032  xor     eax, eax
0x1800f3034  add     rcx, 68h ; 'h'; this
0x1800f3038  mov     qword ptr [rbp+pvarg+10h], rax
0x1800f303c  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800f3040  mov     rsi, rdx
0x1800f3043  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800f3048  test    eax, eax
0x1800f304a  jnz     short loc_1800F30A6
0x1800f304c  mov     rax, cs:WPP_GLOBAL_Control
0x1800f3053  lea     r14, WPP_GLOBAL_Control
0x1800f305a  cmp     rax, r14
0x1800f305d  jz      short loc_1800F309C
0x1800f305f  mov     sil, 8
0x1800f3062  test    [rax+1Ch], sil
0x1800f3066  jz      short loc_1800F309C
0x1800f3068  mov     ebx, 2
0x1800f306d  cmp     [rax+19h], bl
0x1800f3070  jb      short loc_1800F309C
0x1800f3072  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f3077  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f307e  lea     edx, [rbx+0Ch]
0x1800f3081  mov     r9d, eax
0x1800f3084  mov     dword ptr [rsp+58h+var_38], 80004005h
0x1800f308c  lea     r8, WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids
0x1800f3093  mov     rcx, [rcx+10h]
0x1800f3097  call    WPP_SF_Dd
0x1800f309c  mov     edi, 80004005h
0x1800f30a1  jmp     loc_1800F359B
0x1800f30a6  mov     ebx, 2
0x1800f30ab  lea     rdi, [r13+0A0h]
0x1800f30b2  or      [r13+54h], ebx
0x1800f30b6  xor     r12d, r12d
0x1800f30b9  cmp     rsi, [rdi]
0x1800f30bc  jz      short loc_1800F30D1
0x1800f30be  mov     rcx, rdi
0x1800f30c1  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f30c6  mov     rcx, rdi
0x1800f30c9  mov     [rdi], rsi
0x1800f30cc  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800f30d1  lea     rcx, [rbp+pvarg]; pvarg
0x1800f30d5  call    cs:__imp_VariantInit
0x1800f30db  mov     rcx, [rdi]
0x1800f30de  lea     r8, [rbp+pvarg]
0x1800f30e2  lea     rdx, aCrdpencvsdeskt; "CRDPENCVSDesktopShim::EnableCodecCache"
0x1800f30e9  mov     rax, [rcx]
0x1800f30ec  mov     rax, [rax+18h]
0x1800f30f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f30f5  test    eax, eax
0x1800f30f7  js      short loc_1800F3109
0x1800f30f9  cmp     word ptr [rbp+pvarg], 0Bh
0x1800f30fe  jnz     short loc_1800F3109
0x1800f3100  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x1800f3105  setz    r12b
0x1800f3109  lea     rcx, [rbp+pvarg]; pvarg
0x1800f310d  call    cs:__imp_VariantClear
0x1800f3113  lea     r14, WPP_GLOBAL_Control
0x1800f311a  mov     sil, 8
0x1800f311d  lea     r15, WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids
0x1800f3124  test    r12d, r12d
0x1800f3127  jz      loc_1800F344C
0x1800f312d  mov     rcx, [r13+58h]
0x1800f3131  lea     r8, [rbp+arg_0]
0x1800f3135  lea     rdx, IID_IUnknown
0x1800f313c  mov     rax, [rcx]
0x1800f313f  mov     rax, [rax]
0x1800f3142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3147  mov     r12d, eax
0x1800f314a  test    eax, eax
0x1800f314c  jns     short loc_1800F3180
0x1800f314e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3155  cmp     rcx, r14
0x1800f3158  jz      loc_1800F31E9
0x1800f315e  test    [rcx+1Ch], sil
0x1800f3162  jz      loc_1800F31E9
0x1800f3168  cmp     [rcx+19h], bl
0x1800f316b  jb      short loc_1800F31E9
0x1800f316d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f3172  mov     edx, 10h
0x1800f3177  lea     rcx, aFailedToQiOurs; "Failed to QI ourselves for IUnknown"
0x1800f317e  jmp     short loc_1800F31C9
0x1800f3180  mov     rcx, [rdi]
0x1800f3183  lea     rdx, aRdpcodeccacheF; "RDPCodecCache::Factory"
0x1800f318a  mov     r8, [rbp+arg_0]
0x1800f318e  mov     rax, [rcx]
0x1800f3191  mov     rax, [rax+50h]
0x1800f3195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f319a  mov     r12d, eax
0x1800f319d  test    eax, eax
0x1800f319f  jns     short loc_1800F31E9
0x1800f31a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f31a8  cmp     rcx, r14
0x1800f31ab  jz      short loc_1800F31E9
0x1800f31ad  test    [rcx+1Ch], sil
0x1800f31b1  jz      short loc_1800F31E9
0x1800f31b3  cmp     [rcx+19h], bl
0x1800f31b6  jb      short loc_1800F31E9
0x1800f31b8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f31bd  mov     edx, 11h
0x1800f31c2  lea     rcx, aFailedToSaveOu; "Failed to save our codec factory to pro"...
0x1800f31c9  mov     [rsp+58h+var_30], r12d
0x1800f31ce  mov     r9d, eax
0x1800f31d1  mov     [rsp+58h+var_38], rcx
0x1800f31d6  mov     r8, r15
0x1800f31d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f31e0  mov     rcx, [rcx+10h]
0x1800f31e4  call    WPP_SF_DsD
0x1800f31e9  xor     edx, edx
0x1800f31eb  lea     rcx, [rbp+arg_0]
0x1800f31ef  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800f31f4  mov     rcx, [rdi]
0x1800f31f7  lea     r9, [rbp+arg_0]
0x1800f31fb  lea     r8, IID_IUnknown
0x1800f3202  lea     rdx, CLSID_RDPCompressorCache
0x1800f3209  call    RDPAPI_CreateInstance
0x1800f320e  mov     r12d, eax
0x1800f3211  test    eax, eax
0x1800f3213  jns     short loc_1800F3247
0x1800f3215  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f321c  cmp     rcx, r14
0x1800f321f  jz      loc_1800F32B0
0x1800f3225  test    [rcx+1Ch], sil
0x1800f3229  jz      loc_1800F32B0
0x1800f322f  cmp     [rcx+19h], bl
0x1800f3232  jb      short loc_1800F32B0
0x1800f3234  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f3239  mov     edx, 12h
0x1800f323e  lea     rcx, aFailedToCreate_18; "Failed to create planar compressor cach"...
0x1800f3245  jmp     short loc_1800F3290
0x1800f3247  mov     rcx, [rdi]
0x1800f324a  lea     rdx, aRdpcodeccacheP; "RDPCodecCache::Planar"
0x1800f3251  mov     r8, [rbp+arg_0]
0x1800f3255  mov     rax, [rcx]
0x1800f3258  mov     rax, [rax+50h]
0x1800f325c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3261  mov     r12d, eax
0x1800f3264  test    eax, eax
0x1800f3266  jns     short loc_1800F32B0
0x1800f3268  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f326f  cmp     rcx, r14
0x1800f3272  jz      short loc_1800F32B0
0x1800f3274  test    [rcx+1Ch], sil
0x1800f3278  jz      short loc_1800F32B0
0x1800f327a  cmp     [rcx+19h], bl
0x1800f327d  jb      short loc_1800F32B0
0x1800f327f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f3284  mov     edx, 13h
0x1800f3289  lea     rcx, aFailedToSavePl; "Failed to save planar compressor cache "...
0x1800f3290  mov     [rsp+58h+var_30], r12d
0x1800f3295  mov     r9d, eax
0x1800f3298  mov     [rsp+58h+var_38], rcx
0x1800f329d  mov     r8, r15
0x1800f32a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f32a7  mov     rcx, [rcx+10h]
0x1800f32ab  call    WPP_SF_DsD
0x1800f32b0  xor     edx, edx
0x1800f32b2  lea     rcx, [rbp+arg_0]
0x1800f32b6  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800f32bb  mov     rcx, [rdi]
0x1800f32be  lea     r9, [rbp+arg_0]
0x1800f32c2  lea     r8, IID_IUnknown
0x1800f32c9  lea     rdx, CLSID_RDPNsCodecCompressorCache
0x1800f32d0  call    RDPAPI_CreateInstance
0x1800f32d5  mov     r12d, eax
0x1800f32d8  test    eax, eax
0x1800f32da  jns     short loc_1800F330E
0x1800f32dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f32e3  cmp     rcx, r14
0x1800f32e6  jz      loc_1800F3377
0x1800f32ec  test    [rcx+1Ch], sil
0x1800f32f0  jz      loc_1800F3377
0x1800f32f6  cmp     [rcx+19h], bl
0x1800f32f9  jb      short loc_1800F3377
0x1800f32fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f3300  mov     edx, 14h
0x1800f3305  lea     rcx, aFailedToCreate_40; "Failed to create NSCodec compressor cac"...
0x1800f330c  jmp     short loc_1800F3357
0x1800f330e  mov     rcx, [rdi]
0x1800f3311  lea     rdx, aRdpcodeccacheN; "RDPCodecCache::NSCodec"
0x1800f3318  mov     r8, [rbp+arg_0]
0x1800f331c  mov     rax, [rcx]
0x1800f331f  mov     rax, [rax+50h]
0x1800f3323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3328  mov     r12d, eax
0x1800f332b  test    eax, eax
0x1800f332d  jns     short loc_1800F3377
0x1800f332f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3336  cmp     rcx, r14
0x1800f3339  jz      short loc_1800F3377
0x1800f333b  test    [rcx+1Ch], sil
0x1800f333f  jz      short loc_1800F3377
0x1800f3341  cmp     [rcx+19h], bl
0x1800f3344  jb      short loc_1800F3377
0x1800f3346  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f334b  mov     edx, 15h
0x1800f3350  lea     rcx, aFailedToSaveNs; "Failed to save NSCodec compressor cache"...
0x1800f3357  mov     [rsp+58h+var_30], r12d
0x1800f335c  mov     r9d, eax
0x1800f335f  mov     [rsp+58h+var_38], rcx
0x1800f3364  mov     r8, r15
0x1800f3367  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f336e  mov     rcx, [rcx+10h]
0x1800f3372  call    WPP_SF_DsD
0x1800f3377  xor     edx, edx
0x1800f3379  lea     rcx, [rbp+arg_0]
0x1800f337d  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800f3382  mov     rcx, [rdi]
0x1800f3385  lea     r9, [rbp+arg_0]
0x1800f3389  lea     r8, IID_IRdpImageCompressor
0x1800f3390  lea     rdx, CLSID_RDPCACCodecCompressorCache
0x1800f3397  call    RDPAPI_CreateInstance
0x1800f339c  mov     r12d, eax
0x1800f339f  test    eax, eax
0x1800f33a1  jns     short loc_1800F33DA
0x1800f33a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f33aa  cmp     rcx, r14
0x1800f33ad  jz      loc_1800F3441
0x1800f33b3  test    [rcx+1Ch], sil
0x1800f33b7  jz      loc_1800F3441
0x1800f33bd  cmp     [rcx+19h], bl
0x1800f33c0  jb      short loc_1800F3441
0x1800f33c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f33c7  mov     edx, 16h
0x1800f33cc  mov     [rsp+58h+var_30], r12d
0x1800f33d1  lea     rcx, aFailedToCreate_113; "Failed to create ImgCACodec compressor "...
0x1800f33d8  jmp     short loc_1800F3426
0x1800f33da  mov     rcx, [rdi]
0x1800f33dd  lea     rdx, aRdpcodeccacheI; "RDPCodecCache::ImgCaCodec"
0x1800f33e4  mov     r8, [rbp+arg_0]
0x1800f33e8  mov     rax, [rcx]
0x1800f33eb  mov     rax, [rax+50h]
0x1800f33ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f33f4  mov     edi, eax
0x1800f33f6  test    eax, eax
0x1800f33f8  jns     short loc_1800F3441
0x1800f33fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3401  cmp     rcx, r14
0x1800f3404  jz      short loc_1800F3441
0x1800f3406  test    [rcx+1Ch], sil
0x1800f340a  jz      short loc_1800F3441
0x1800f340c  cmp     [rcx+19h], bl
0x1800f340f  jb      short loc_1800F3441
0x1800f3411  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f3416  mov     edx, 17h
0x1800f341b  mov     [rsp+58h+var_30], edi
0x1800f341f  lea     rcx, aFailedToSaveIm; "Failed to save ImgCACodec compressor ca"...
0x1800f3426  mov     [rsp+58h+var_38], rcx
0x1800f342b  mov     r9d, eax
0x1800f342e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3435  mov     r8, r15
0x1800f3438  mov     rcx, [rcx+10h]
0x1800f343c  call    WPP_SF_DsD
0x1800f3441  xor     edx, edx
0x1800f3443  lea     rcx, [rbp+arg_0]
0x1800f3447  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800f344c  mov     rcx, r13; this
0x1800f344f  lea     r12, [r13+58h]
0x1800f3453  call    ?InitializeAudioManager@CRDPENCVSDesktopShim@@IEAAJXZ; CRDPENCVSDesktopShim::InitializeAudioManager(void)
0x1800f3458  mov     edi, eax
0x1800f345a  test    eax, eax
0x1800f345c  jns     short loc_1800F3497
0x1800f345e  mov     rax, cs:WPP_GLOBAL_Control
0x1800f3465  cmp     rax, r14
0x1800f3468  jz      loc_1800F359B
0x1800f346e  test    [rax+1Ch], sil
0x1800f3472  jz      loc_1800F359B
0x1800f3478  cmp     [rax+19h], bl
0x1800f347b  jb      loc_1800F359B
0x1800f3481  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f3486  mov     edx, 18h
0x1800f348b  lea     rcx, aInitializeaudi; "InitializeAudioManager failed."
0x1800f3492  jmp     loc_1800F357C
0x1800f3497  mov     rcx, r13; this
0x1800f349a  call    ?InitializeCollabTouchManager@CRDPENCVSDesktopShim@@IEAAJXZ; CRDPENCVSDesktopShim::InitializeCollabTouchManager(void)
0x1800f349f  mov     edi, eax
0x1800f34a1  test    eax, eax
0x1800f34a3  jns     short loc_1800F34DE
0x1800f34a5  mov     rax, cs:WPP_GLOBAL_Control
0x1800f34ac  cmp     rax, r14
0x1800f34af  jz      loc_1800F359B
0x1800f34b5  test    [rax+1Ch], sil
0x1800f34b9  jz      loc_1800F359B
0x1800f34bf  cmp     [rax+19h], bl
0x1800f34c2  jb      loc_1800F359B
0x1800f34c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f34cd  mov     edx, 19h
0x1800f34d2  lea     rcx, aInitializecoll; "InitializeCollabTouchManager failed."
0x1800f34d9  jmp     loc_1800F357C
  ... truncated ...
```
