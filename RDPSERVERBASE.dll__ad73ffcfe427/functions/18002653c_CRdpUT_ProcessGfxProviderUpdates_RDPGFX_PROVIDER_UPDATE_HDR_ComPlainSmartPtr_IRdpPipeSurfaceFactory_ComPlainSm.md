# CRdpUT::ProcessGfxProviderUpdates(_RDPGFX_PROVIDER_UPDATE_HDR *,ComPlainSmartPtr<IRdpPipeSurfaceFactory> &,ComPlainSmartPtr<IRdpGFXRecorder> &,uint,int *)

- ea: `0x18002653c`
- end: `0x180026d27`
- name: `?ProcessGfxProviderUpdates@CRdpUT@@IEAAJPEAU_RDPGFX_PROVIDER_UPDATE_HDR@@AEAV?$ComPlainSmartPtr@VIRdpPipeSurfaceFactory@@@@AEAV?$ComPlainSmartPtr@UIRdpGFXRecorder@@@@IPEAH@Z`
- size: `2027`
- prototype: `__int64 __usercall@<rax>(CRdpUT *this@<rcx>, struct _RDPGFX_PROVIDER_UPDATE_HDR *@<rdx>, int, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800276f0`
- `0x1800af710`

## callees

- `0x18001dd38`
- `0x18002653c`
- `0x180076090`
- `0x180079770`
- `0x18007a664`
- `0x1800aef64`
- `0x1800af030`
- `0x1800af2f0`
- `0x1800af694`
- `0x1800afc90`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x180026585`: `IID_IRdpUpdateTracker`
- `0x18002667b`: `IID_IRdpUpdateTracker`
- `0x1800266f0`: `IID_IRdpUpdateTracker`
- `0x18002678b`: `IID_IRdpUpdateTracker`
- `0x180026837`: `IID_IRdpUpdateTracker`
- `0x180026904`: `IID_IRdpUpdateTracker`
- `0x1800269d4`: `IID_IRdpUpdateTracker`
- `0x180026a76`: `IID_IRdpUpdateTracker`
- `0x180026b56`: `IID_IRdpUpdateTracker`
- `0x180026c02`: `IID_IRdpUpdateTracker`
- `0x180026cad`: `IID_IRdpUpdateTracker`
- `0x180026578`: `UpdateTrackerError_LockContextDataAndProcessUpdatesRecordUpdateFail`
- `0x1800265c1`: `Recorder RecordUpdate failed`
- `0x18002677e`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessGraphicsUpdateFail`
- `0x1800267cc`: `Failed to process update`
- `0x18002666e`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessVideoHintUpdateFail`
- `0x1800266bc`: `ProcessVideoHintUpdate() failed`
- `0x180026b49`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessMMRHintUpdateFail`
- `0x180026b97`: `ProcessMMRHintUpdate() failed`
- `0x1800269c7`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessSetDesktopLayoutFail`
- `0x1800266e3`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessCreateSurfaceFail`
- `0x180026731`: `Failed ProcessCreateSurface`
- `0x1800268f7`: `UpdateTrackerError_LockContextDataAndProcessUpdatesDeleteRdpSurfaceFail`
- `0x180026945`: `failed DeleteSurface`
- `0x18002682a`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceWithOutputFail`
- `0x180026ca0`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceWithOutputFail`
- `0x180026a69`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceToWindowFail`
- `0x180026bf5`: `UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceToWindowFail`

## pseudocode

```c
__int64 __fastcall CRdpUT::ProcessGfxProviderUpdates(
        CRdpUT *this,
        struct _RDPGFX_PROVIDER_UPDATE_HDR *a2,
        struct IRdpPipeSurfaceFactory **a3,
        _QWORD *a4,
        int a5,
        _DWORD *a6)
{
  unsigned int v9; // ebx
  signed int v10; // eax
  unsigned int v11; // eax
  CRdpUT *v12; // rcx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  signed int v17; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v19; // edx
  const char *v20; // rcx
  signed int Surface; // eax
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  CRdpUT *v25; // rcx
  signed int v26; // eax
  signed int v27; // eax
  __int128 v28; // xmm1
  signed int v29; // eax
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  unsigned int v35; // eax
  signed int v36; // eax
  signed int v37; // eax
  CRdpUT *v38; // rcx
  CRdpUT *v39; // rcx
  int v40; // ecx
  int v41; // ecx
  signed int v42; // eax
  signed int v43; // eax
  signed int v44; // eax
  int v46; // [rsp+20h] [rbp-58h]
  int v47; // [rsp+20h] [rbp-58h]
  int v48; // [rsp+20h] [rbp-58h]
  int v49; // [rsp+20h] [rbp-58h]
  int v50; // [rsp+20h] [rbp-58h]

  v9 = 0;
  if ( !*a4 || (v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 40LL))(*a4), v9 = v10, v10 >= 0) )
  {
    v12 = (CRdpUT *)*((unsigned int *)a2 + 1);
    if ( (int)v12 <= 18 )
    {
      if ( (_DWORD)v12 == 18 )
        goto LABEL_32;
      if ( (int)v12 <= 11 )
      {
        if ( (_DWORD)v12 == 11 )
        {
          Surface = CRdpUT::ProcessCreateSurface(this, *a3, a2);
          v9 = Surface;
          if ( Surface >= 0 )
            goto LABEL_96;
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
            "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessCreateSurfaceFail",
            (char *)0x312,
            Surface,
            v46);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_96;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 57;
          v20 = "Failed ProcessCreateSurface";
          goto LABEL_95;
        }
        v13 = (_DWORD)v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 3;
          if ( !v14 )
            goto LABEL_16;
          v15 = v14 - 1;
          if ( !v15 )
            goto LABEL_16;
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( (unsigned int)(v16 - 1) <= 1 )
            {
LABEL_16:
              (*(void (__fastcall **)(char *, struct _RDPGFX_PROVIDER_UPDATE_HDR *))(*((_QWORD *)this + 21) + 8LL))(
                (char *)this + 168,
                a2);
LABEL_96:
              *((_DWORD *)this + 76) = a5;
              return v9;
            }
LABEL_75:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids);
            }
            goto LABEL_96;
          }
          v17 = CRdpUT::ProcessVideoHintUpdate(this, a2);
          v9 = v17;
          if ( v17 >= 0 )
            goto LABEL_96;
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
            "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessVideoHintUpdateFail",
            (char *)0x2E7,
            v17,
            v46);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_96;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 54;
          v20 = "ProcessVideoHintUpdate() failed";
LABEL_95:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)v20,
            v9);
          goto LABEL_96;
        }
        goto LABEL_32;
      }
      v22 = (_DWORD)v12 - 12;
      if ( !v22 )
      {
        v29 = (*(__int64 (__fastcall **)(struct IRdpPipeSurfaceFactory *, _QWORD))(*(_QWORD *)*a3 + 40LL))(
                *a3,
                *((_QWORD *)a2 + 1));
        v9 = v29;
        if ( v29 >= 0 )
          goto LABEL_96;
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
          "UpdateTrackerError_LockContextDataAndProcessUpdatesDeleteRdpSurfaceFail",
          (char *)0x31C,
          v29,
          v46);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_96;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 58;
        v20 = "failed DeleteSurface";
        goto LABEL_95;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        *(_OWORD *)((char *)this + 236) = *((_OWORD *)a2 + 67);
        *(_OWORD *)((char *)this + 252) = *((_OWORD *)a2 + 68);
        *(_OWORD *)((char *)this + 268) = *((_OWORD *)a2 + 69);
        v28 = *((_OWORD *)a2 + 70);
        *((_DWORD *)this + 75) = 1;
        *(_OWORD *)((char *)this + 284) = v28;
        goto LABEL_96;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        *a6 = 1;
        goto LABEL_96;
      }
      v25 = (CRdpUT *)(unsigned int)(v24 - 2);
      if ( (_DWORD)v25 )
      {
        if ( (_DWORD)v25 != 1 )
          goto LABEL_75;
        goto LABEL_32;
      }
      v27 = CRdpUT::ProcessAssociateSurface(
              v25,
              *a3,
              (*((_DWORD *)a2 + 270) != 0) - 1LL,
              *((_QWORD *)a2 + 1),
              *((_DWORD *)a2 + 268),
              *((_DWORD *)a2 + 269),
              0,
              0,
              0,
              0);
      v9 = v27;
      if ( v27 >= 0 )
        goto LABEL_96;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
        "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceWithOutputFail",
        (char *)0x334,
        v27,
        v47);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_96;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 59;
LABEL_94:
      v20 = "Failed to associate the surface to the output";
      goto LABEL_95;
    }
    if ( (int)v12 > 25 )
    {
      v38 = (CRdpUT *)(unsigned int)((_DWORD)v12 - 26);
      if ( !(_DWORD)v38 )
      {
        v44 = CRdpUT::ProcessAssociateSurface(
                v38,
                *a3,
                (*((_DWORD *)a2 + 270) != 0) - 1LL,
                *((_QWORD *)a2 + 1),
                *((_DWORD *)a2 + 268),
                *((_DWORD *)a2 + 269),
                0,
                0,
                *((_DWORD *)a2 + 271),
                *((_DWORD *)a2 + 272));
        v9 = v44;
        if ( v44 >= 0 )
          goto LABEL_96;
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
          "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceWithOutputFail",
          (char *)0x34C,
          v44,
          v50);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_96;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 60;
        goto LABEL_94;
      }
      v39 = (CRdpUT *)(unsigned int)((_DWORD)v38 - 1);
      if ( (_DWORD)v39 )
      {
        v40 = (_DWORD)v39 - 1;
        if ( v40 )
        {
          v41 = v40 - 1;
          if ( v41 )
          {
            if ( v41 != 1 )
              goto LABEL_75;
            v42 = CRdpUT::ProcessMMRHintUpdate(this, a2);
            v9 = v42;
            if ( v42 >= 0 )
              goto LABEL_96;
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
              "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessMMRHintUpdateFail",
              (char *)0x2EF,
              v42,
              v46);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_96;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v19 = 55;
            v20 = "ProcessMMRHintUpdate() failed";
            goto LABEL_95;
          }
        }
LABEL_32:
        v26 = CRdpUT::ProcessGraphicsUpdate(this, a2);
        v9 = v26;
        if ( v26 >= 0 )
          goto LABEL_96;
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
          "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessGraphicsUpdateFail",
          (char *)0x2DF,
          v26,
          v46);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_96;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 53;
        v20 = "Failed to process update";
        goto LABEL_95;
      }
      v43 = CRdpUT::ProcessAssociateSurface(
              v39,
              *a3,
              *((_QWORD *)a2 + 134),
              *((_QWORD *)a2 + 1),
              0,
              0,
              *((_DWORD *)a2 + 270),
              *((_DWORD *)a2 + 271),
              *((_DWORD *)a2 + 272),
              *((_DWORD *)a2 + 273));
      v9 = v43;
      if ( v43 >= 0 )
        goto LABEL_96;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
        "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceToWindowFail",
        (char *)0x376,
        v43,
        v49);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_96;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 62;
    }
    else
    {
      if ( (_DWORD)v12 != 25 )
      {
        v30 = (_DWORD)v12 - 19;
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( v31 )
          {
            v32 = v31 - 1;
            if ( v32 )
            {
              v33 = v32 - 1;
              if ( v33 )
              {
                v34 = v33 - 1;
                if ( v34 )
                {
                  if ( v34 == 1 )
                  {
                    v35 = *((_DWORD *)a2 + 268);
                    if ( v35 > *((_DWORD *)this + 494) )
                      *((_DWORD *)this + 494) = v35;
                    goto LABEL_96;
                  }
                  goto LABEL_75;
                }
                v36 = CRdpUT::ProcessSetDesktopLayout(this, a2);
                v9 = v36;
                if ( v36 >= 0 )
                  goto LABEL_96;
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
                  "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessSetDesktopLayoutFail",
                  (char *)0x308,
                  v36,
                  v46);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_96;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v19 = 56;
                v20 = "Failed to process a SetDesktopSize";
                goto LABEL_95;
              }
            }
          }
        }
        goto LABEL_32;
      }
      v37 = CRdpUT::ProcessAssociateSurface(
              v12,
              *a3,
              *((_QWORD *)a2 + 134),
              *((_QWORD *)a2 + 1),
              0,
              0,
              *((_DWORD *)a2 + 270),
              *((_DWORD *)a2 + 271),
              0,
              0);
      v9 = v37;
      if ( v37 >= 0 )
        goto LABEL_96;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
        "UpdateTrackerError_LockContextDataAndProcessUpdatesProcessAssociateSurfaceToWindowFail",
        (char *)0x361,
        v37,
        v48);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_96;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 61;
    }
    v20 = "Failed to associate the surface to the window";
    goto LABEL_95;
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
    "UpdateTrackerError_LockContextDataAndProcessUpdatesRecordUpdateFail",
    (char *)0x2CE,
    v10,
    v46);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
      v11,
      (__int64)"Recorder RecordUpdate failed",
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18002653c  push    rbx
0x18002653e  push    rbp
0x18002653f  push    rdi
0x180026540  push    r14
0x180026542  push    r15
0x180026544  sub     rsp, 50h
0x180026548  xor     r15d, r15d
0x18002654b  mov     rbp, rcx
0x18002654e  mov     rcx, [r9]
0x180026551  mov     r14, r8
0x180026554  mov     rdi, rdx
0x180026557  mov     ebx, r15d
0x18002655a  test    rcx, rcx
0x18002655d  jz      loc_1800265F4
0x180026563  mov     rax, [rcx]
0x180026566  mov     rax, [rax+28h]
0x18002656a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002656f  mov     ebx, eax
0x180026571  test    eax, eax
0x180026573  jns     short loc_1800265F4
0x180026575  mov     r9d, eax; unsigned int
0x180026578  lea     rdx, aUpdatetrackere_3; "UpdateTrackerError_LockContextDataAndPr"...
0x18002657f  mov     r8d, 2CEh; char *
0x180026585  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18002658c  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180026591  mov     rcx, cs:WPP_GLOBAL_Control
0x180026598  lea     rax, WPP_GLOBAL_Control
0x18002659f  cmp     rcx, rax
0x1800265a2  jz      loc_180026D19
0x1800265a8  test    byte ptr [rcx+1Ch], 8
0x1800265ac  jz      loc_180026D19
0x1800265b2  cmp     byte ptr [rcx+19h], 2
0x1800265b6  jb      loc_180026D19
0x1800265bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800265c1  lea     rcx, aRecorderRecord; "Recorder RecordUpdate failed"
0x1800265c8  mov     [rsp+78h+var_50], ebx
0x1800265cc  mov     qword ptr [rsp+78h+var_58], rcx
0x1800265d1  lea     edx, [r15+34h]
0x1800265d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265dc  lea     r8, WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids
0x1800265e3  mov     r9d, eax
0x1800265e6  mov     rcx, [rcx+10h]
0x1800265ea  call    WPP_SF_DsD
0x1800265ef  jmp     loc_180026D19
0x1800265f4  mov     ecx, [rdi+4]; this
0x1800265f7  cmp     ecx, 12h
0x1800265fa  jg      loc_180026951
0x180026600  jz      loc_180026766
0x180026606  cmp     ecx, 0Bh
0x180026609  jg      loc_18002673D
0x18002660f  jz      loc_1800266C8
0x180026615  sub     ecx, 1
0x180026618  jz      loc_180026766
0x18002661e  sub     ecx, 3
0x180026621  jz      short loc_18002663B
0x180026623  sub     ecx, 1
0x180026626  jz      short loc_18002663B
0x180026628  sub     ecx, 1
0x18002662b  jz      short loc_180026656
0x18002662d  sub     ecx, 1
0x180026630  jz      short loc_18002663B
0x180026632  cmp     ecx, 1
0x180026635  jnz     loc_180026AEC
0x18002663b  lea     rcx, [rbp+0A8h]
0x180026642  mov     rdx, rdi
0x180026645  mov     rax, [rcx]
0x180026648  mov     rax, [rax+8]
0x18002664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026651  jmp     loc_180026D0C
0x180026656  mov     rdx, rdi; struct _RDPGFX_PROVIDER_UPDATE_HDR *
0x180026659  mov     rcx, rbp; this
0x18002665c  call    ?ProcessVideoHintUpdate@CRdpUT@@IEAAJPEAU_RDPGFX_PROVIDER_UPDATE_HDR@@@Z; CRdpUT::ProcessVideoHintUpdate(_RDPGFX_PROVIDER_UPDATE_HDR *)
0x180026661  mov     ebx, eax
0x180026663  test    eax, eax
0x180026665  jns     loc_180026D0C
0x18002666b  mov     r9d, eax; unsigned int
0x18002666e  lea     rdx, aUpdatetrackere_2; "UpdateTrackerError_LockContextDataAndPr"...
0x180026675  mov     r8d, 2E7h; char *
0x18002667b  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x180026682  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180026687  mov     rcx, cs:WPP_GLOBAL_Control
0x18002668e  lea     rax, WPP_GLOBAL_Control
0x180026695  cmp     rcx, rax
0x180026698  jz      loc_180026D0C
0x18002669e  test    byte ptr [rcx+1Ch], 8
0x1800266a2  jz      loc_180026D0C
0x1800266a8  cmp     byte ptr [rcx+19h], 2
0x1800266ac  jb      loc_180026D0C
0x1800266b2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800266b7  mov     edx, 36h ; '6'
0x1800266bc  lea     rcx, aProcessvideohi; "ProcessVideoHintUpdate() failed"
0x1800266c3  jmp     loc_180026CE9
0x1800266c8  mov     rdx, [r14]; struct IRdpPipeSurfaceFactory *
0x1800266cb  mov     r8, rdi; struct _RDPGFX_PROVIDER_CREATE_SURFACE_UPDATE *
0x1800266ce  mov     rcx, rbp; this
0x1800266d1  call    ?ProcessCreateSurface@CRdpUT@@IEAAJPEAVIRdpPipeSurfaceFactory@@PEAU_RDPGFX_PROVIDER_CREATE_SURFACE_UPDATE@@@Z; CRdpUT::ProcessCreateSurface(IRdpPipeSurfaceFactory *,_RDPGFX_PROVIDER_CREATE_SURFACE_UPDATE *)
0x1800266d6  mov     ebx, eax
0x1800266d8  test    eax, eax
0x1800266da  jns     loc_180026D0C
0x1800266e0  mov     r9d, eax; unsigned int
0x1800266e3  lea     rdx, aUpdatetrackere_7; "UpdateTrackerError_LockContextDataAndPr"...
0x1800266ea  mov     r8d, 312h; char *
0x1800266f0  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800266f7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800266fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180026703  lea     rax, WPP_GLOBAL_Control
0x18002670a  cmp     rcx, rax
0x18002670d  jz      loc_180026D0C
0x180026713  test    byte ptr [rcx+1Ch], 8
0x180026717  jz      loc_180026D0C
0x18002671d  cmp     byte ptr [rcx+19h], 2
0x180026721  jb      loc_180026D0C
0x180026727  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002672c  mov     edx, 39h ; '9'
0x180026731  lea     rcx, aFailedProcessc; "Failed ProcessCreateSurface"
0x180026738  jmp     loc_180026CE9
0x18002673d  sub     ecx, 0Ch
0x180026740  jz      loc_1800268D7
0x180026746  sub     ecx, 1
0x180026749  jz      loc_180026890
0x18002674f  sub     ecx, 1
0x180026752  jz      loc_18002687D
0x180026758  sub     ecx, 2; this
0x18002675b  jz      short loc_1800267D8
0x18002675d  cmp     ecx, 1
0x180026760  jnz     loc_180026AEC
0x180026766  mov     rdx, rdi; struct _RDPGFX_PROVIDER_UPDATE_HDR *
0x180026769  mov     rcx, rbp; this
0x18002676c  call    ?ProcessGraphicsUpdate@CRdpUT@@IEAAJPEAU_RDPGFX_PROVIDER_UPDATE_HDR@@@Z; CRdpUT::ProcessGraphicsUpdate(_RDPGFX_PROVIDER_UPDATE_HDR *)
0x180026771  mov     ebx, eax
0x180026773  test    eax, eax
0x180026775  jns     loc_180026D0C
0x18002677b  mov     r9d, eax; unsigned int
0x18002677e  lea     rdx, aUpdatetrackere_16; "UpdateTrackerError_LockContextDataAndPr"...
0x180026785  mov     r8d, 2DFh; char *
0x18002678b  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x180026792  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180026797  mov     rcx, cs:WPP_GLOBAL_Control
0x18002679e  lea     rax, WPP_GLOBAL_Control
0x1800267a5  cmp     rcx, rax
0x1800267a8  jz      loc_180026D0C
0x1800267ae  test    byte ptr [rcx+1Ch], 8
0x1800267b2  jz      loc_180026D0C
0x1800267b8  cmp     byte ptr [rcx+19h], 2
0x1800267bc  jb      loc_180026D0C
0x1800267c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800267c7  mov     edx, 35h ; '5'
0x1800267cc  lea     rcx, aFailedToProces_6; "Failed to process update"
0x1800267d3  jmp     loc_180026CE9
0x1800267d8  mov     eax, [rdi+438h]
0x1800267de  mov     r9, [rdi+8]; unsigned __int64
0x1800267e2  neg     eax
0x1800267e4  mov     eax, [rdi+434h]
0x1800267ea  mov     rdx, [r14]; struct IRdpPipeSurfaceFactory *
0x1800267ed  sbb     r8, r8
0x1800267f0  mov     [rsp+78h+var_30], r15d; unsigned int
0x1800267f5  neg     r8
0x1800267f8  mov     [rsp+78h+var_38], r15d; unsigned int
0x1800267fd  dec     r8; unsigned __int64
0x180026800  mov     [rsp+78h+var_40], r15d; unsigned int
0x180026805  mov     [rsp+78h+var_48], r15d; unsigned int
0x18002680a  mov     [rsp+78h+var_50], eax; unsigned int
0x18002680e  mov     eax, [rdi+430h]
0x180026814  mov     [rsp+78h+var_58], eax; int
0x180026818  call    ?ProcessAssociateSurface@CRdpUT@@IEAAJPEAVIRdpPipeSurfaceFactory@@_K1IIIIII@Z; CRdpUT::ProcessAssociateSurface(IRdpPipeSurfaceFactory *,unsigned __int64,unsigned __int64,uint,uint,uint,uint,uint,uint)
0x18002681d  mov     ebx, eax
0x18002681f  test    eax, eax
0x180026821  jns     loc_180026D0C
0x180026827  mov     r9d, eax; unsigned int
0x18002682a  lea     rdx, aUpdatetrackere_15; "UpdateTrackerError_LockContextDataAndPr"...
0x180026831  mov     r8d, 334h; char *
0x180026837  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18002683e  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180026843  mov     rcx, cs:WPP_GLOBAL_Control
0x18002684a  lea     rax, WPP_GLOBAL_Control
0x180026851  cmp     rcx, rax
0x180026854  jz      loc_180026D0C
0x18002685a  test    byte ptr [rcx+1Ch], 8
0x18002685e  jz      loc_180026D0C
0x180026864  cmp     byte ptr [rcx+19h], 2
0x180026868  jb      loc_180026D0C
0x18002686e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180026873  mov     edx, 3Bh ; ';'
0x180026878  jmp     loc_180026CE2
0x18002687d  mov     rax, [rsp+78h+arg_28]
0x180026885  mov     dword ptr [rax], 1
0x18002688b  jmp     loc_180026D0C
0x180026890  movups  xmm0, xmmword ptr [rdi+430h]
0x180026897  movups  xmmword ptr [rbp+0ECh], xmm0
0x18002689e  movups  xmm1, xmmword ptr [rdi+440h]
0x1800268a5  movups  xmmword ptr [rbp+0FCh], xmm1
0x1800268ac  movups  xmm0, xmmword ptr [rdi+450h]
0x1800268b3  movups  xmmword ptr [rbp+10Ch], xmm0
0x1800268ba  movups  xmm1, xmmword ptr [rdi+460h]
0x1800268c1  mov     dword ptr [rbp+12Ch], 1
0x1800268cb  movups  xmmword ptr [rbp+11Ch], xmm1
0x1800268d2  jmp     loc_180026D0C
0x1800268d7  mov     rcx, [r14]
0x1800268da  mov     rdx, [rdi+8]
0x1800268de  mov     rax, [rcx]
0x1800268e1  mov     rax, [rax+28h]
0x1800268e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268ea  mov     ebx, eax
0x1800268ec  test    eax, eax
0x1800268ee  jns     loc_180026D0C
0x1800268f4  mov     r9d, eax; unsigned int
0x1800268f7  lea     rdx, aUpdatetrackere_20; "UpdateTrackerError_LockContextDataAndPr"...
0x1800268fe  mov     r8d, 31Ch; char *
0x180026904  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18002690b  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180026910  mov     rcx, cs:WPP_GLOBAL_Control
0x180026917  lea     rax, WPP_GLOBAL_Control
0x18002691e  cmp     rcx, rax
0x180026921  jz      loc_180026D0C
0x180026927  test    byte ptr [rcx+1Ch], 8
0x18002692b  jz      loc_180026D0C
0x180026931  cmp     byte ptr [rcx+19h], 2
0x180026935  jb      loc_180026D0C
0x18002693b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180026940  mov     edx, 3Ah ; ':'
0x180026945  lea     rcx, aFailedDeletesu; "failed DeleteSurface"
0x18002694c  jmp     loc_180026CE9
0x180026951  cmp     ecx, 19h
0x180026954  jg      loc_180026AC3
0x18002695a  jz      loc_180026A21
0x180026960  sub     ecx, 13h
0x180026963  jz      loc_180026766
0x180026969  sub     ecx, 1
0x18002696c  jz      loc_180026766
0x180026972  sub     ecx, 1
0x180026975  jz      loc_180026766
0x18002697b  sub     ecx, 1
0x18002697e  jz      loc_180026766
0x180026984  sub     ecx, 1
0x180026987  jz      short loc_1800269AF
0x180026989  cmp     ecx, 1
0x18002698c  jnz     loc_180026AEC
0x180026992  mov     eax, [rdi+430h]
0x180026998  cmp     eax, [rbp+7B8h]
0x18002699e  jbe     loc_180026D0C
0x1800269a4  mov     [rbp+7B8h], eax
0x1800269aa  jmp     loc_180026D0C
0x1800269af  mov     rdx, rdi; struct _RDPGFX_PROVIDER_SET_DESKTOP_LAYOUT *
0x1800269b2  mov     rcx, rbp; this
0x1800269b5  call    ?ProcessSetDesktopLayout@CRdpUT@@IEAAJPEAU_RDPGFX_PROVIDER_SET_DESKTOP_LAYOUT@@@Z; CRdpUT::ProcessSetDesktopLayout(_RDPGFX_PROVIDER_SET_DESKTOP_LAYOUT *)
0x1800269ba  mov     ebx, eax
0x1800269bc  test    eax, eax
0x1800269be  jns     loc_180026D0C
0x1800269c4  mov     r9d, eax; unsigned int
0x1800269c7  lea     rdx, aUpdatetrackere_4; "UpdateTrackerError_LockContextDataAndPr"...
0x1800269ce  mov     r8d, 308h; char *
0x1800269d4  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800269db  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800269e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269e7  lea     rax, WPP_GLOBAL_Control
0x1800269ee  cmp     rcx, rax
0x1800269f1  jz      loc_180026D0C
0x1800269f7  test    byte ptr [rcx+1Ch], 8
0x1800269fb  jz      loc_180026D0C
0x180026a01  cmp     byte ptr [rcx+19h], 2
0x180026a05  jb      loc_180026D0C
0x180026a0b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180026a10  mov     edx, 38h ; '8'
0x180026a15  lea     rcx, aFailedToProces_0; "Failed to process a SetDesktopSize"
0x180026a1c  jmp     loc_180026CE9
0x180026a21  mov     eax, [rdi+43Ch]
0x180026a27  mov     r9, [rdi+8]; unsigned __int64
0x180026a2b  mov     r8, [rdi+430h]; unsigned __int64
0x180026a32  mov     rdx, [r14]; struct IRdpPipeSurfaceFactory *
0x180026a35  mov     [rsp+78h+var_30], r15d; unsigned int
0x180026a3a  mov     [rsp+78h+var_38], r15d; unsigned int
0x180026a3f  mov     [rsp+78h+var_40], eax; unsigned int
0x180026a43  mov     eax, [rdi+438h]
0x180026a49  mov     [rsp+78h+var_48], eax; unsigned int
0x180026a4d  mov     [rsp+78h+var_50], r15d; unsigned int
0x180026a52  mov     [rsp+78h+var_58], r15d; int
0x180026a57  call    ?ProcessAssociateSurface@CRdpUT@@IEAAJPEAVIRdpPipeSurfaceFactory@@_K1IIIIII@Z; CRdpUT::ProcessAssociateSurface(IRdpPipeSurfaceFactory *,unsigned __int64,unsigned __int64,uint,uint,uint,uint,uint,uint)
0x180026a5c  mov     ebx, eax
0x180026a5e  test    eax, eax
0x180026a60  jns     loc_180026D0C
0x180026a66  mov     r9d, eax; unsigned int
0x180026a69  lea     rdx, aUpdatetrackere_21; "UpdateTrackerError_LockContextDataAndPr"...
0x180026a70  mov     r8d, 361h; char *
0x180026a76  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x180026a7d  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180026a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a89  lea     rax, WPP_GLOBAL_Control
0x180026a90  cmp     rcx, rax
0x180026a93  jz      loc_180026D0C
0x180026a99  test    byte ptr [rcx+1Ch], 8
0x180026a9d  jz      loc_180026D0C
0x180026aa3  cmp     byte ptr [rcx+19h], 2
0x180026aa7  jb      loc_180026D0C
0x180026aad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180026ab2  mov     edx, 3Dh ; '='
0x180026ab7  lea     rcx, aFailedToAssoci; "Failed to associate the surface to the "...
0x180026abe  jmp     loc_180026CE9
0x180026ac3  sub     ecx, 1Ah; this
0x180026ac6  jz      loc_180026C48
0x180026acc  sub     ecx, 1; this
  ... truncated ...
```
