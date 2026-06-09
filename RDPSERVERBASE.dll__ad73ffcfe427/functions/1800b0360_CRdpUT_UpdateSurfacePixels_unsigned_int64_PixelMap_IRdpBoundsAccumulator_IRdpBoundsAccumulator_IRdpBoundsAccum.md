# CRdpUT::UpdateSurfacePixels(unsigned __int64,PixelMap *,IRdpBoundsAccumulator *,IRdpBoundsAccumulator *,IRdpBoundsAccumulator *)

- ea: `0x1800b0360`
- end: `0x1800b0a2e`
- name: `?UpdateSurfacePixels@CRdpUT@@UEAAJ_KPEAVPixelMap@@PEAVIRdpBoundsAccumulator@@22@Z`
- size: `1742`
- prototype: `int(CRdpUT *__hidden this, unsigned __int64, struct PixelMap *, struct IRdpBoundsAccumulator *, struct IRdpBoundsAccumulator *, struct IRdpBoundsAccumulator *)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update`

## callees

- `0x18000ce04`
- `0x18000ce34`
- `0x180023384`
- `0x18002aafc`
- `0x18002da8c`
- `0x18002ef00`
- `0x18004f5bc`
- `0x180052930`
- `0x180076090`
- `0x180079770`
- `0x18007cf90`
- `0x18007e9e0`
- `0x1800ad560`
- `0x1800b0360`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x1800b0451`: `IID_IRdpUpdateTracker`
- `0x1800b04ae`: `IID_IRdpUpdateTracker`
- `0x1800b0561`: `IID_IRdpUpdateTracker`
- `0x1800b0611`: `IID_IRdpUpdateTracker`
- `0x1800b067d`: `IID_IRdpUpdateTracker`
- `0x1800b07e9`: `IID_IRdpUpdateTracker`
- `0x1800b0846`: `IID_IRdpUpdateTracker`
- `0x1800b0933`: `IID_IRdpUpdateTracker`
- `0x1800b0985`: `IID_IRdpUpdateTracker`
- `0x1800b0444`: `UpdateTrackerError_UpdateSurfacePixelsNullPointer`
- `0x1800b04a1`: `UpdateTrackerError_UpdateSurfacePixelsGetSurfaceInfoFail`
- `0x1800b0554`: `UpdateTrackerError_UpdateSurfacePixelsMapSurfaceDataFail`
- `0x1800b0604`: `UpdateTrackerError_UpdateSurfacePixelsBALogicFail`
- `0x1800b0670`: `UpdateTrackerError_UpdateSurfacePixelsBALogicFail`
- `0x1800b07dc`: `UpdateTrackerError_UpdateSurfacePixelsBALogicFail`
- `0x1800b0839`: `UpdateTrackerError_UpdateSurfacePixelsBALogicFail`
- `0x1800b0926`: `UpdateTrackerError_UpdateSurfacePixelsBALogicFail`
- `0x1800b0978`: `UpdateTrackerError_UpdateSurfacePixelsBALogicFail`
- `0x1800b0652`: `failed to create CopyBA`
- `0x1800b06be`: `failed to create DeltaShrinkBA`

## pseudocode

```c
__int64 __fastcall CRdpUT::UpdateSurfacePixels(
        CRdpUT *this,
        __int64 a2,
        struct PixelMap *a3,
        struct IRdpBoundsAccumulator *a4,
        struct IRdpBoundsAccumulator *a5,
        struct IRdpBoundsAccumulator *a6)
{
  __int64 v6; // rbx
  __int64 v11; // rdi
  unsigned int v12; // esi
  signed int v13; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v15; // edx
  const char *v16; // rcx
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  __int64 v20; // rbx
  __int64 v21; // r15
  unsigned int v22; // eax
  unsigned int i; // r14d
  signed int v24; // eax
  signed int v25; // eax
  unsigned int v26; // r15d
  unsigned int j; // r14d
  signed int v28; // eax
  signed int v29; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v34[4]; // [rsp+68h] [rbp-98h] BYREF
  char *v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v38[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-60h]
  struct IRdpBoundsAccumulator *v40; // [rsp+B0h] [rbp-50h]
  struct IRdpBoundsAccumulator *v41; // [rsp+B8h] [rbp-48h]
  unsigned int v42[4]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 *v43[2]; // [rsp+D0h] [rbp-30h]
  int v44[4]; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+F0h] [rbp-10h]
  __int128 v46; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v47; // [rsp+108h] [rbp+8h] BYREF
  __int128 v48; // [rsp+118h] [rbp+18h]
  __int128 v49; // [rsp+128h] [rbp+28h]

  v6 = 0;
  v40 = a5;
  v41 = a4;
  v33 = 0;
  v45 = 0;
  v38[0] = 0;
  v38[1] = 0;
  v37 = 0;
  v11 = 0;
  v36 = 0;
  v47 = 0;
  v35 = (char *)this + 152;
  v48 = 0;
  v49 = 0;
  *(_OWORD *)v42 = 0;
  *(_OWORD *)v43 = 0;
  *(_OWORD *)v44 = 0;
  v39 = 0;
  *(_OWORD *)v34 = 0;
  v46 = 0;
  CTSCriticalSection::Lock((CRdpUT *)((char *)this + 152));
  if ( *((_QWORD *)this + 9) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v33);
    v33 = *((_QWORD *)this + 9);
    v11 = v33;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v33);
    v6 = v11;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v35);
  if ( !v6 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_UpdateSurfacePixelsNullPointer",
      (char *)0x648,
      0x80004003,
      v31);
    v12 = -2147418113;
    goto LABEL_58;
  }
  *((_QWORD *)&v46 + 1) = *(_QWORD *)a3;
  *(_QWORD *)&v46 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v6 + 56LL))(v6, a2, &v47);
  v12 = v13;
  if ( v13 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v6 + 64LL))(
            v6,
            a2,
            &v46,
            2 - (unsigned int)(DWORD2(v48) != 0));
    v12 = v17;
    if ( v17 >= 0 )
    {
      PixelMap::Attach((PixelMap *)v38, v43[1], v44[0], v42[2], v42[3], (int)v43[0], 0x20u, 0, 0, v42[2], v42[3]);
      v18 = RgnlibBA_CreateInstance(&v37);
      v12 = v18;
      if ( v18 >= 0 )
      {
        v19 = RgnlibBA_CreateInstance(&v36);
        v12 = v19;
        if ( v19 >= 0 )
        {
          v20 = v36;
          (*(void (__fastcall **)(__int64, struct IRdpBoundsAccumulator *))(*(_QWORD *)v36 + 48LL))(v36, a4);
          (*(void (__fastcall **)(__int64, struct IRdpBoundsAccumulator *))(*(_QWORD *)v20 + 56LL))(v20, v40);
          v21 = v37;
          (*(void (__fastcall **)(__int64, struct IRdpBoundsAccumulator *))(*(_QWORD *)v37 + 48LL))(v37, v41);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 56LL))(v21, v20);
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 136LL))(v21) )
          {
            v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 176LL))(v21);
            LODWORD(v35) = v22;
            for ( i = 0; i < v22; ++i )
            {
              v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v21 + 184LL))(v21, i, v34);
              v12 = v24;
              if ( v24 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
                  "UpdateTrackerError_UpdateSurfacePixelsBALogicFail",
                  (char *)0x687,
                  v24,
                  v32);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_58;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v15 = 91;
LABEL_41:
                v16 = "GetRectAt failed";
                goto LABEL_10;
              }
              PixelMap::BitBlt((PixelMap *)v38, a3, v34[0], v34[1], v34[2] - v34[0], v34[3] - v34[1], v34[0], v34[1]);
              v25 = (*(__int64 (__fastcall **)(struct IRdpBoundsAccumulator *, unsigned int *))(*(_QWORD *)a6 + 40LL))(
                      a6,
                      v34);
              v12 = v25;
              if ( v25 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
                  "UpdateTrackerError_UpdateSurfacePixelsBALogicFail",
                  (char *)0x698,
                  v25,
                  v32);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_58;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v15 = 92;
LABEL_36:
                v16 = "EncodingBA->AddRect";
                goto LABEL_10;
              }
              v22 = (unsigned int)v35;
            }
          }
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v20 + 136LL))(v20) )
          {
            v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 176LL))(v20);
            for ( j = 0; j < v26; ++j )
            {
              v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v20 + 184LL))(v20, j, v34);
              v12 = v28;
              if ( v28 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
                  "UpdateTrackerError_UpdateSurfacePixelsBALogicFail",
                  (char *)0x6A4,
                  v28,
                  v32);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v15 = 93;
                  goto LABEL_41;
                }
                goto LABEL_58;
              }
              CopyPixelsAndDeltaShrink((struct PixelMap *)v38, a3, (struct RdpRect *)v34);
              v29 = (*(__int64 (__fastcall **)(struct IRdpBoundsAccumulator *, unsigned int *))(*(_QWORD *)a6 + 40LL))(
                      a6,
                      v34);
              v12 = v29;
              if ( v29 < 0 )
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
                  "UpdateTrackerError_UpdateSurfacePixelsBALogicFail",
                  (char *)0x6B0,
                  v29,
                  v32);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v15 = 94;
                  goto LABEL_36;
                }
                goto LABEL_58;
              }
            }
          }
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 72LL))(v11, v42);
          if ( DWORD1(v48) )
            PixelMap::RevertIteration(a3);
        }
        else
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
            "UpdateTrackerError_UpdateSurfacePixelsBALogicFail",
            (char *)0x675,
            v19,
            v32);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v15 = 90;
            v16 = "failed to create DeltaShrinkBA";
            goto LABEL_10;
          }
        }
      }
      else
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
          "UpdateTrackerError_UpdateSurfacePixelsBALogicFail",
          (char *)0x671,
          v18,
          v32);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 89;
          v16 = "failed to create CopyBA";
          goto LABEL_10;
        }
      }
    }
    else
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
        "UpdateTrackerError_UpdateSurfacePixelsMapSurfaceDataFail",
        (char *)0x661,
        v17,
        (int)v42);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 88;
        v16 = "Failed to map the surface data";
        goto LABEL_10;
      }
    }
  }
  else
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_UpdateSurfacePixelsGetSurfaceInfoFail",
      (char *)0x656,
      v13,
      v31);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 87;
      v16 = "FAILED GetSurfaceInfo";
LABEL_10:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v16,
        v12);
    }
  }
LABEL_58:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v36);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v37);
  PixelMap::~PixelMap((PixelMap *)v38);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v33);
  return v12;
}

```

## disassembly

```asm
0x1800b0360  mov     [rsp-8+arg_0], rbx
0x1800b0365  push    rbp
0x1800b0366  push    rsi
0x1800b0367  push    rdi
0x1800b0368  push    r12
0x1800b036a  push    r13
0x1800b036c  push    r14
0x1800b036e  push    r15
0x1800b0370  lea     rbp, [rsp-40h]
0x1800b0375  sub     rsp, 140h
0x1800b037c  mov     rax, cs:__security_cookie
0x1800b0383  xor     rax, rsp
0x1800b0386  mov     [rbp+70h+var_38], rax
0x1800b038a  mov     rax, [rbp+70h+arg_20]
0x1800b0391  xor     ebx, ebx
0x1800b0393  mov     r13, [rbp+70h+arg_28]
0x1800b039a  xorps   xmm0, xmm0
0x1800b039d  xorps   xmm1, xmm1
0x1800b03a0  mov     [rbp+70h+var_C0], rax
0x1800b03a4  mov     rsi, rcx
0x1800b03a7  mov     [rbp+70h+var_B8], r9
0x1800b03ab  xor     eax, eax
0x1800b03ad  mov     [rsp+170h+var_110], rbx
0x1800b03b2  add     rcx, 98h; this
0x1800b03b9  mov     [rbp+70h+var_80], rax
0x1800b03bd  mov     r15, r9
0x1800b03c0  mov     [rbp+70h+var_E0], rbx
0x1800b03c4  mov     r12, r8
0x1800b03c7  mov     [rbp+70h+var_D8], rbx
0x1800b03cb  mov     r14, rdx
0x1800b03ce  mov     [rbp+70h+var_E8], rbx
0x1800b03d2  mov     edi, ebx
0x1800b03d4  mov     [rbp+70h+var_F0], rbx
0x1800b03d8  movups  [rbp+70h+var_68], xmm0
0x1800b03dc  mov     [rsp+170h+var_F8], rcx
0x1800b03e1  movups  [rbp+70h+var_58], xmm0
0x1800b03e5  movups  [rbp+70h+var_48], xmm0
0x1800b03e9  movups  xmmword ptr [rbp+70h+var_B0], xmm1
0x1800b03ed  movups  xmmword ptr [rbp+70h+var_A0], xmm1
0x1800b03f1  movups  xmmword ptr [rbp+70h+var_90], xmm1
0x1800b03f5  movdqu  [rbp+70h+var_D0], xmm0
0x1800b03fa  movdqu  xmmword ptr [rsp+170h+var_108], xmm1
0x1800b0400  movups  [rbp+70h+var_78], xmm0
0x1800b0404  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800b0409  cmp     [rsi+48h], rbx
0x1800b040d  jz      short loc_1800B042F
0x1800b040f  lea     rcx, [rsp+170h+var_110]
0x1800b0414  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800b0419  mov     rdi, [rsi+48h]
0x1800b041d  lea     rcx, [rsp+170h+var_110]
0x1800b0422  mov     [rsp+170h+var_110], rdi
0x1800b0427  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800b042c  mov     rbx, rdi
0x1800b042f  lea     rcx, [rsp+170h+var_F8]; this
0x1800b0434  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800b0439  test    rbx, rbx
0x1800b043c  jnz     short loc_1800B0467
0x1800b043e  mov     r9d, 80004003h; unsigned int
0x1800b0444  lea     rdx, aUpdatetrackere_22; "UpdateTrackerError_UpdateSurfacePixelsN"...
0x1800b044b  mov     r8d, 648h; char *
0x1800b0451  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800b0458  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b045d  mov     esi, 8000FFFFh
0x1800b0462  jmp     loc_1800B09E0
0x1800b0467  mov     eax, [r12]
0x1800b046b  lea     r8, [rbp+70h+var_68]
0x1800b046f  mov     dword ptr [rbp+70h+var_78+8], eax
0x1800b0472  mov     rdx, r14
0x1800b0475  mov     eax, [r12+4]
0x1800b047a  mov     rcx, rbx
0x1800b047d  mov     dword ptr [rbp+70h+var_78+0Ch], eax
0x1800b0480  mov     qword ptr [rbp+70h+var_78], 0
0x1800b0488  mov     rax, [rbx]
0x1800b048b  mov     rax, [rax+38h]
0x1800b048f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0494  mov     esi, eax
0x1800b0496  test    eax, eax
0x1800b0498  jns     loc_1800B051E
0x1800b049e  mov     r9d, eax; unsigned int
0x1800b04a1  lea     rdx, aUpdatetrackere_17; "UpdateTrackerError_UpdateSurfacePixelsG"...
0x1800b04a8  mov     r8d, 656h; char *
0x1800b04ae  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800b04b5  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b04ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b04c1  lea     rax, WPP_GLOBAL_Control
0x1800b04c8  cmp     rcx, rax
0x1800b04cb  jz      loc_1800B09E0
0x1800b04d1  test    byte ptr [rcx+1Ch], 8
0x1800b04d5  jz      loc_1800B09E0
0x1800b04db  cmp     byte ptr [rcx+19h], 2
0x1800b04df  jb      loc_1800B09E0
0x1800b04e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b04ea  mov     edx, 57h ; 'W'
0x1800b04ef  lea     rcx, aFailedGetsurfa; "FAILED GetSurfaceInfo"
0x1800b04f6  mov     [rsp+170h+var_148], esi
0x1800b04fa  lea     r8, WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids
0x1800b0501  mov     qword ptr [rsp+170h+var_150], rcx
0x1800b0506  mov     r9d, eax
0x1800b0509  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0510  mov     rcx, [rcx+10h]
0x1800b0514  call    WPP_SF_DsD
0x1800b0519  jmp     loc_1800B09E0
0x1800b051e  mov     r8d, dword ptr [rbp+70h+var_58+8]
0x1800b0522  lea     rcx, [rbp+70h+var_B0]
0x1800b0526  mov     rax, [rbx]
0x1800b0529  neg     r8d
0x1800b052c  mov     qword ptr [rsp+170h+var_150], rcx; int
0x1800b0531  lea     r8, [rbp+70h+var_78]
0x1800b0535  sbb     r9d, r9d
0x1800b0538  mov     rdx, r14
0x1800b053b  add     r9d, 2
0x1800b053f  mov     rcx, rbx
0x1800b0542  mov     rax, [rax+40h]
0x1800b0546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b054b  mov     esi, eax
0x1800b054d  test    eax, eax
0x1800b054f  jns     short loc_1800B05AE
0x1800b0551  mov     r9d, eax; unsigned int
0x1800b0554  lea     rdx, aUpdatetrackere_24; "UpdateTrackerError_UpdateSurfacePixelsM"...
0x1800b055b  mov     r8d, 661h; char *
0x1800b0561  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800b0568  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b056d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0574  lea     rax, WPP_GLOBAL_Control
0x1800b057b  cmp     rcx, rax
0x1800b057e  jz      loc_1800B09E0
0x1800b0584  test    byte ptr [rcx+1Ch], 8
0x1800b0588  jz      loc_1800B09E0
0x1800b058e  cmp     byte ptr [rcx+19h], 2
0x1800b0592  jb      loc_1800B09E0
0x1800b0598  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b059d  mov     edx, 58h ; 'X'
0x1800b05a2  lea     rcx, aFailedToMapThe; "Failed to map the surface data"
0x1800b05a9  jmp     loc_1800B04F6
0x1800b05ae  mov     ecx, [rbp+70h+var_B0+0Ch]
0x1800b05b1  mov     r9d, [rbp+70h+var_B0+8]; int
0x1800b05b5  mov     eax, dword ptr [rbp+70h+var_A0]
0x1800b05b8  mov     r8d, [rbp+70h+var_90]; int
0x1800b05bc  mov     rdx, [rbp+70h+var_A0+8]; unsigned __int8 *
0x1800b05c0  mov     [rsp+170h+var_120], ecx; int
0x1800b05c4  mov     [rsp+170h+var_128], r9d; int
0x1800b05c9  mov     [rsp+170h+var_130], 0; int
0x1800b05d1  mov     [rsp+170h+var_138], 0; int
0x1800b05d9  mov     [rsp+170h+var_140], 20h ; ' '; int
0x1800b05e1  mov     [rsp+170h+var_148], eax; int
0x1800b05e5  mov     [rsp+170h+var_150], ecx; int
0x1800b05e9  lea     rcx, [rbp+70h+var_E0]; this
0x1800b05ed  call    ?Attach@PixelMap@@QEAA_NPEAEHHHHHHHHH@Z; PixelMap::Attach(uchar *,int,int,int,int,int,int,int,int,int)
0x1800b05f2  lea     rcx, [rbp+70h+var_E8]
0x1800b05f6  call    RgnlibBA_CreateInstance
0x1800b05fb  mov     esi, eax
0x1800b05fd  test    eax, eax
0x1800b05ff  jns     short loc_1800B065E
0x1800b0601  mov     r9d, eax; unsigned int
0x1800b0604  lea     rdx, aUpdatetrackere_5; "UpdateTrackerError_UpdateSurfacePixelsB"...
0x1800b060b  mov     r8d, 671h; char *
0x1800b0611  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800b0618  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b061d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0624  lea     rax, WPP_GLOBAL_Control
0x1800b062b  cmp     rcx, rax
0x1800b062e  jz      loc_1800B09E0
0x1800b0634  test    byte ptr [rcx+1Ch], 8
0x1800b0638  jz      loc_1800B09E0
0x1800b063e  cmp     byte ptr [rcx+19h], 2
0x1800b0642  jb      loc_1800B09E0
0x1800b0648  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b064d  mov     edx, 59h ; 'Y'
0x1800b0652  lea     rcx, aFailedToCreate_94; "failed to create CopyBA"
0x1800b0659  jmp     loc_1800B04F6
0x1800b065e  lea     rcx, [rbp+70h+var_F0]
0x1800b0662  call    RgnlibBA_CreateInstance
0x1800b0667  mov     esi, eax
0x1800b0669  test    eax, eax
0x1800b066b  jns     short loc_1800B06CA
0x1800b066d  mov     r9d, eax; unsigned int
0x1800b0670  lea     rdx, aUpdatetrackere_5; "UpdateTrackerError_UpdateSurfacePixelsB"...
0x1800b0677  mov     r8d, 675h; char *
0x1800b067d  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800b0684  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b0689  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0690  lea     rax, WPP_GLOBAL_Control
0x1800b0697  cmp     rcx, rax
0x1800b069a  jz      loc_1800B09E0
0x1800b06a0  test    byte ptr [rcx+1Ch], 8
0x1800b06a4  jz      loc_1800B09E0
0x1800b06aa  cmp     byte ptr [rcx+19h], 2
0x1800b06ae  jb      loc_1800B09E0
0x1800b06b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b06b9  mov     edx, 5Ah ; 'Z'
0x1800b06be  lea     rcx, aFailedToCreate_62; "failed to create DeltaShrinkBA"
0x1800b06c5  jmp     loc_1800B04F6
0x1800b06ca  mov     rbx, [rbp+70h+var_F0]
0x1800b06ce  mov     rdx, r15
0x1800b06d1  mov     rcx, rbx
0x1800b06d4  mov     rax, [rbx]
0x1800b06d7  mov     rax, [rax+30h]
0x1800b06db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b06e0  mov     rax, [rbx]
0x1800b06e3  mov     rcx, rbx
0x1800b06e6  mov     rdx, [rbp+70h+var_C0]
0x1800b06ea  mov     rax, [rax+38h]
0x1800b06ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b06f3  mov     r15, [rbp+70h+var_E8]
0x1800b06f7  mov     rdx, [rbp+70h+var_B8]
0x1800b06fb  mov     rcx, r15
0x1800b06fe  mov     rax, [r15]
0x1800b0701  mov     rax, [rax+30h]
0x1800b0705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b070a  mov     rax, [r15]
0x1800b070d  mov     rdx, rbx
0x1800b0710  mov     rcx, r15
0x1800b0713  mov     rax, [rax+38h]
0x1800b0717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b071c  mov     rax, [r15]
0x1800b071f  mov     rcx, r15
0x1800b0722  mov     rax, [rax+88h]
0x1800b0729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b072e  test    eax, eax
0x1800b0730  jnz     loc_1800B0893
0x1800b0736  mov     rax, [r15]
0x1800b0739  mov     rcx, r15
0x1800b073c  mov     rax, [rax+0B0h]
0x1800b0743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0748  mov     dword ptr [rsp+170h+var_F8], eax
0x1800b074c  xor     r14d, r14d
0x1800b074f  cmp     r14d, eax
0x1800b0752  jnb     loc_1800B0893
0x1800b0758  mov     rcx, [r15]
0x1800b075b  lea     r8, [rsp+170h+var_108]
0x1800b0760  mov     edx, r14d
0x1800b0763  mov     rax, [rcx+0B8h]
0x1800b076a  mov     rcx, r15
0x1800b076d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0772  mov     esi, eax
0x1800b0774  test    eax, eax
0x1800b0776  js      loc_1800B0836
0x1800b077c  mov     ecx, [rsp+170h+var_108+0Ch]
0x1800b0780  mov     rdx, r12; struct PixelMap *
0x1800b0783  mov     r9d, [rsp+170h+var_108+4]; unsigned int
0x1800b0788  sub     ecx, r9d
0x1800b078b  mov     r8d, [rsp+170h+var_108]; unsigned int
0x1800b0790  mov     eax, [rsp+170h+var_108+8]
0x1800b0794  mov     [rsp+170h+var_138], r9d; unsigned int
0x1800b0799  sub     eax, r8d
0x1800b079c  mov     [rsp+170h+var_140], r8d; unsigned int
0x1800b07a1  mov     [rsp+170h+var_148], ecx; unsigned int
0x1800b07a5  lea     rcx, [rbp+70h+var_E0]; this
0x1800b07a9  mov     [rsp+170h+var_150], eax; int
0x1800b07ad  call    ?BitBlt@PixelMap@@QEBA_NAEAV1@IIIIII@Z; PixelMap::BitBlt(PixelMap &,uint,uint,uint,uint,uint,uint)
0x1800b07b2  mov     rax, [r13+0]
0x1800b07b6  lea     rdx, [rsp+170h+var_108]
0x1800b07bb  mov     rcx, r13
0x1800b07be  mov     rax, [rax+28h]
0x1800b07c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07c7  mov     esi, eax
0x1800b07c9  test    eax, eax
0x1800b07cb  js      short loc_1800B07D9
0x1800b07cd  mov     eax, dword ptr [rsp+170h+var_F8]
0x1800b07d1  inc     r14d
0x1800b07d4  jmp     loc_1800B074F
0x1800b07d9  mov     r9d, esi; unsigned int
0x1800b07dc  lea     rdx, aUpdatetrackere_5; "UpdateTrackerError_UpdateSurfacePixelsB"...
0x1800b07e3  mov     r8d, 698h; char *
0x1800b07e9  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800b07f0  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b07f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b07fc  lea     rax, WPP_GLOBAL_Control
0x1800b0803  cmp     rcx, rax
0x1800b0806  jz      loc_1800B09E0
0x1800b080c  test    byte ptr [rcx+1Ch], 8
0x1800b0810  jz      loc_1800B09E0
0x1800b0816  cmp     byte ptr [rcx+19h], 2
0x1800b081a  jb      loc_1800B09E0
0x1800b0820  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b0825  mov     edx, 5Ch ; '\'
0x1800b082a  lea     rcx, aEncodingbaAddr; "EncodingBA->AddRect"
0x1800b0831  jmp     loc_1800B04F6
0x1800b0836  mov     r9d, esi; unsigned int
0x1800b0839  lea     rdx, aUpdatetrackere_5; "UpdateTrackerError_UpdateSurfacePixelsB"...
0x1800b0840  mov     r8d, 687h; char *
0x1800b0846  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800b084d  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b0852  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0859  lea     rax, WPP_GLOBAL_Control
0x1800b0860  cmp     rcx, rax
0x1800b0863  jz      loc_1800B09E0
0x1800b0869  test    byte ptr [rcx+1Ch], 8
0x1800b086d  jz      loc_1800B09E0
0x1800b0873  cmp     byte ptr [rcx+19h], 2
0x1800b0877  jb      loc_1800B09E0
0x1800b087d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b0882  mov     edx, 5Bh ; '['
0x1800b0887  lea     rcx, aGetrectatFaile; "GetRectAt failed"
0x1800b088e  jmp     loc_1800B04F6
0x1800b0893  mov     rax, [rbx]
0x1800b0896  mov     rcx, rbx
0x1800b0899  mov     rax, [rax+88h]
0x1800b08a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b08a5  test    eax, eax
  ... truncated ...
```
