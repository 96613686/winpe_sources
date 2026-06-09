# CRdpUT::LockContextDataAndProcessUpdates(int *,int *)

- ea: `0x1800276f0`
- end: `0x180027dc0`
- name: `?LockContextDataAndProcessUpdates@CRdpUT@@UEAAJPEAH0@Z`
- size: `1744`
- prototype: `__int64 __fastcall(CRdpUT *__hidden this, int *, int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update`

## callees

- `0x18000ce04`
- `0x18000ce34`
- `0x18002653c`
- `0x180026ed8`
- `0x1800276f0`
- `0x180029610`
- `0x18002aafc`
- `0x18002b14c`
- `0x1800420c8`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007a404`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x180027a91`: `onecore\termsrv\rdpplatform\gfxpipe\server\updatetracker.cpp`
- `0x180027a98`: `CRdpUT::LockContextDataAndProcessUpdates`
- `0x180027a28`: `UpdateTrackerError_LockContextDataAndProcessUpdatesRefreshAndLockContextDataFail`
- `0x180027860`: `IID_IRdpUpdateTracker`
- `0x1800278e7`: `IID_IRdpUpdateTracker`
- `0x180027a35`: `IID_IRdpUpdateTracker`
- `0x180027b1c`: `IID_IRdpUpdateTracker`
- `0x180027c2a`: `IID_IRdpUpdateTracker`
- `0x180027cd0`: `IID_IRdpUpdateTracker`
- `0x180027856`: `UpdateTrackerError_LockContextDataAndProcessUpdatesNullPointer`
- `0x1800278dd`: `UpdateTrackerError_LockContextDataAndProcessUpdatesNullPointer`
- `0x18002792e`: `pfGraphicsUpdateAvailable`
- `0x180027a76`: `Failed to refresh the update context`
- `0x180027b0f`: `UpdateTrackerError_LockContextDataAndProcessUpdatesSignalStartOfUpdatesFail`
- `0x180027b5d`: `Recorder SignalStartOfUpdates failed`
- `0x180027bef`: `ProcessGfxProviderUpdates failed`
- `0x180027c1d`: `UpdateTrackerError_LockContextDataAndProcessUpdatesFlushOrdersFail`
- `0x180027cc3`: `UpdateTrackerError_LockContextDataAndProcessUpdatesSignalEndOfUpdatesFail`

## pseudocode

```c
__int64 __fastcall CRdpUT::LockContextDataAndProcessUpdates(CRdpUT *this, int *a2, int *a3)
{
  CTSCriticalSection *v3; // r15
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rcx
  struct IRdpPipeSurfaceFactory *v12; // rcx
  __int64 v13; // rcx
  int v14; // r15d
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v19; // edx
  const char *v20; // rcx
  __int64 v21; // rax
  signed int v22; // eax
  __int64 v23; // rcx
  int v24; // r13d
  signed int v25; // eax
  int v26; // r13d
  struct _RDPGFX_PROVIDER_UPDATE_HDR *v27; // rax
  _DWORD *v28; // r12
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // r14d
  unsigned int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  struct IRdpPipeSurfaceFactory *v35; // rcx
  int v37; // [rsp+20h] [rbp-30h]
  __int64 v38; // [rsp+30h] [rbp-20h] BYREF
  struct IRdpPipeSurfaceFactory *v39; // [rsp+38h] [rbp-18h] BYREF
  __int64 v40; // [rsp+40h] [rbp-10h] BYREF
  int i; // [rsp+90h] [rbp+40h] BYREF
  __int64 v42; // [rsp+98h] [rbp+48h]
  unsigned int v43; // [rsp+A8h] [rbp+58h]

  v42 = (__int64)a2;
  v3 = (CRdpUT *)((char *)this + 152);
  v39 = 0;
  v38 = 0;
  v40 = 0;
  v43 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  CTSCriticalSection::Lock((CRdpUT *)((char *)this + 152));
  v10 = *((_QWORD *)this + 9);
  if ( v10 )
  {
    v7 = *((_QWORD *)this + 9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  }
  v11 = *((_QWORD *)this + 13);
  if ( v11 )
  {
    v8 = *((_QWORD *)this + 13);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  }
  if ( *((struct IRdpPipeSurfaceFactory **)this + 14) != v39 )
  {
    v12 = (struct IRdpPipeSurfaceFactory *)*((_QWORD *)this + 14);
    v39 = v12;
    if ( v12 )
      (*(void (__fastcall **)(struct IRdpPipeSurfaceFactory *))(*(_QWORD *)v12 + 8LL))(v12);
  }
  if ( *((_QWORD *)this + 15) != v38 )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v38);
    v38 = *((_QWORD *)this + 15);
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v38);
  }
  v13 = *((_QWORD *)this + 16);
  if ( v13 )
  {
    v9 = (__int64 *)*((_QWORD *)this + 16);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  }
  *((_QWORD *)this + 242) = 0;
  *((_QWORD *)this + 243) = 0;
  *((_QWORD *)this + 245) = 0;
  *((_DWORD *)this + 488) = 0;
  *((_DWORD *)this + 492) = 0;
  *((_DWORD *)this + 494) = 0;
  *((_QWORD *)this + 248) = 0;
  *((_DWORD *)this + 498) = 0;
  if ( v3 )
    CTSCriticalSection::UnLock(v3);
  if ( !v7 || !v8 || !v39 )
  {
    v14 = -2147418113;
    goto LABEL_71;
  }
  if ( a2 )
  {
    if ( a3 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 160LL))(v8, &v40);
      if ( v14 >= 0 )
      {
        *a2 = 0;
        *a3 = 1;
        *((_DWORD *)this + 493) = 0;
        CRdpUT::UnBlockHybridDriver(this);
        if ( v9 )
        {
          v21 = *v9;
          i = 1;
          if ( (*(int (__fastcall **)(__int64 *, int *))(v21 + 24))(v9, &i) >= 0 && !i )
            *a3 = 0;
        }
        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
        v14 = v22;
        if ( v22 >= 0 )
        {
          Rdp::Modern::Utils::NoSTL::CInflightRecorder::push0(
            (CRdpUT *)((char *)this + 2056),
            L"LockContextData",
            "CRdpUT::LockContextDataAndProcessUpdates",
            "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\updatetracker.cpp",
            0x1CBu);
          *((_DWORD *)this + 77) = 1;
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 80LL))(v7)
            && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v40 + 80LL))(v40) )
          {
            v14 = 0;
            goto LABEL_71;
          }
          v23 = v38;
          v43 = 1;
          *a3 = 1;
          v24 = *((_DWORD *)this + 76);
          if ( !v23 || (v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23), v14 = v25, v25 >= 0) )
          {
            v26 = v24 + 1;
            v27 = (struct _RDPGFX_PROVIDER_UPDATE_HDR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 88LL))(v7);
            v28 = (_DWORD *)v42;
            while ( 1 )
            {
              if ( !v27 )
              {
                for ( i = 0; ; LODWORD(v27) = i )
                {
                  if ( (_DWORD)v27 )
                  {
                    if ( !*((_DWORD *)this + 494) )
                      *((_DWORD *)this + 494) = *((_DWORD *)this + 498);
                    goto LABEL_71;
                  }
                  v29 = CRdpUT::FlushOrders(this, &i);
                  v14 = v29;
                  if ( v29 < 0 )
                    break;
                }
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
                  "UpdateTrackerError_LockContextDataAndProcessUpdatesFlushOrdersFail",
                  (char *)0x212,
                  v29,
                  v37);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v19 = 42;
                  v20 = "failed to flush orders";
                  goto LABEL_33;
                }
                goto LABEL_71;
              }
              v14 = CRdpUT::ProcessGfxProviderUpdates(this, v27, &v39, &v38, v26, v28);
              if ( v14 < 0 )
                break;
              v27 = (struct _RDPGFX_PROVIDER_UPDATE_HDR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9)
                                                                                            + 88LL))(*((_QWORD *)this + 9));
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v19 = 41;
              v20 = "ProcessGfxProviderUpdates failed";
              goto LABEL_33;
            }
            goto LABEL_71;
          }
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
            "UpdateTrackerError_LockContextDataAndProcessUpdatesSignalStartOfUpdatesFail",
            (char *)0x1F0,
            v25,
            v37);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_71;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 40;
          v20 = "Recorder SignalStartOfUpdates failed";
        }
        else
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
            "UpdateTrackerError_LockContextDataAndProcessUpdatesRefreshAndLockContextDataFail",
            (char *)0x1C9,
            v22,
            v37);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_71;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 39;
          v20 = "Failed to refresh the update context";
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_71;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 38;
        v20 = "Failed to get Base Encoder";
      }
LABEL_33:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v20,
        v14);
      goto LABEL_71;
    }
    v14 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_LockContextDataAndProcessUpdatesNullPointer",
      (char *)0x1A5,
      0x80004003,
      v37);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 37;
      v17 = "pfGraphicsUpdateAvailable";
      goto LABEL_22;
    }
  }
  else
  {
    v14 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_LockContextDataAndProcessUpdatesNullPointer",
      (char *)0x1A3,
      0x80004003,
      v37);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 36;
      v17 = "pfFlushRequired";
LABEL_22:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
        v15,
        (__int64)v17);
    }
  }
LABEL_71:
  if ( v38 )
  {
    v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v38 + 48LL))(v38, *((_QWORD *)this + 9), v43);
    v31 = v30;
    if ( v30 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
        "UpdateTrackerError_LockContextDataAndProcessUpdatesSignalEndOfUpdatesFail",
        (char *)0x227,
        v30,
        v37);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v32 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids, v32);
      }
      v14 = v31;
    }
  }
  v33 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
  v34 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(struct IRdpPipeSurfaceFactory *))(*(_QWORD *)v35 + 16LL))(v35);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800276f0  mov     [rsp-38h+arg_10], rbx
0x1800276f5  mov     [rsp-38h+arg_8], rdx
0x1800276fa  push    rbp
0x1800276fb  push    rsi
0x1800276fc  push    rdi
0x1800276fd  push    r12
0x1800276ff  push    r13
0x180027701  push    r14
0x180027703  push    r15
0x180027705  mov     rbp, rsp
0x180027708  sub     rsp, 50h
0x18002770c  xor     eax, eax
0x18002770e  lea     r15, [rcx+98h]
0x180027715  mov     r14, rcx
0x180027718  mov     [rbp+var_18], rax
0x18002771c  mov     rcx, r15; this
0x18002771f  mov     [rbp+var_20], rax
0x180027723  mov     r12, r8
0x180027726  mov     [rbp+var_10], rax
0x18002772a  mov     r13, rdx
0x18002772d  mov     [rbp+arg_18], eax
0x180027730  mov     ebx, eax
0x180027732  mov     edi, eax
0x180027734  mov     esi, eax
0x180027736  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002773b  mov     rcx, [r14+48h]
0x18002773f  test    rcx, rcx
0x180027742  jz      short loc_180027753
0x180027744  mov     rax, [rcx]
0x180027747  mov     rbx, rcx
0x18002774a  mov     rax, [rax+8]
0x18002774e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027753  mov     rcx, [r14+68h]
0x180027757  test    rcx, rcx
0x18002775a  jz      short loc_18002776B
0x18002775c  mov     rax, [rcx]
0x18002775f  mov     rdi, rcx
0x180027762  mov     rax, [rax+8]
0x180027766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002776b  mov     rcx, [rbp+var_18]
0x18002776f  cmp     [r14+70h], rcx
0x180027773  jz      short loc_1800277A3
0x180027775  test    rcx, rcx
0x180027778  jz      short loc_18002778A
0x18002777a  mov     [rbp+var_18], rsi
0x18002777e  mov     rax, [rcx]
0x180027781  mov     rax, [rax+10h]
0x180027785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002778a  mov     rcx, [r14+70h]
0x18002778e  mov     [rbp+var_18], rcx
0x180027792  test    rcx, rcx
0x180027795  jz      short loc_1800277A3
0x180027797  mov     rax, [rcx]
0x18002779a  mov     rax, [rax+8]
0x18002779e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277a3  mov     rax, [rbp+var_20]
0x1800277a7  cmp     [r14+78h], rax
0x1800277ab  jz      short loc_1800277C7
0x1800277ad  lea     rcx, [rbp+var_20]
0x1800277b1  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800277b6  mov     rax, [r14+78h]
0x1800277ba  lea     rcx, [rbp+var_20]
0x1800277be  mov     [rbp+var_20], rax
0x1800277c2  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800277c7  mov     rcx, [r14+80h]
0x1800277ce  test    rcx, rcx
0x1800277d1  jz      short loc_1800277E2
0x1800277d3  mov     rax, [rcx]
0x1800277d6  mov     rsi, rcx
0x1800277d9  mov     rax, [rax+8]
0x1800277dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277e2  xor     ecx, ecx
0x1800277e4  mov     [r14+790h], rcx
0x1800277eb  mov     [r14+798h], rcx
0x1800277f2  mov     [r14+7A8h], rcx
0x1800277f9  mov     [r14+7A0h], ecx
0x180027800  mov     [r14+7B0h], ecx
0x180027807  mov     [r14+7B8h], ecx
0x18002780e  mov     [r14+7C0h], rcx
0x180027815  mov     [r14+7C8h], ecx
0x18002781c  test    r15, r15
0x18002781f  jz      short loc_18002782B
0x180027821  mov     rcx, r15; this
0x180027824  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180027829  xor     ecx, ecx
0x18002782b  test    rbx, rbx
0x18002782e  jz      loc_180027C8C
0x180027834  test    rdi, rdi
0x180027837  jz      loc_180027C8C
0x18002783d  cmp     [rbp+var_18], rcx
0x180027841  jz      loc_180027C8C
0x180027847  test    r13, r13
0x18002784a  jnz     loc_1800278D2
0x180027850  mov     r15d, 80004003h
0x180027856  lea     rdx, aUpdatetrackere_6; "UpdateTrackerError_LockContextDataAndPr"...
0x18002785d  mov     r9d, r15d; unsigned int
0x180027860  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x180027867  mov     r8d, 1A3h; char *
0x18002786d  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180027872  mov     rax, cs:WPP_GLOBAL_Control
0x180027879  lea     r13, WPP_GLOBAL_Control
0x180027880  cmp     rax, r13
0x180027883  jz      loc_180027C99
0x180027889  test    byte ptr [rax+1Ch], 8
0x18002788d  jz      loc_180027C99
0x180027893  cmp     byte ptr [rax+19h], 2
0x180027897  jb      loc_180027C99
0x18002789d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800278a2  mov     edx, 24h ; '$'
0x1800278a7  lea     rcx, aPfflushrequire; "pfFlushRequired"
0x1800278ae  mov     qword ptr [rsp+50h+var_30], rcx
0x1800278b3  lea     r8, WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids
0x1800278ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278c1  mov     r9d, eax
0x1800278c4  mov     rcx, [rcx+10h]
0x1800278c8  call    WPP_SF_Ds
0x1800278cd  jmp     loc_180027C99
0x1800278d2  test    r12, r12
0x1800278d5  jnz     short loc_18002793A
0x1800278d7  mov     r15d, 80004003h
0x1800278dd  lea     rdx, aUpdatetrackere_6; "UpdateTrackerError_LockContextDataAndPr"...
0x1800278e4  mov     r9d, r15d; unsigned int
0x1800278e7  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x1800278ee  mov     r8d, 1A5h; char *
0x1800278f4  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800278f9  mov     rax, cs:WPP_GLOBAL_Control
0x180027900  lea     r13, WPP_GLOBAL_Control
0x180027907  cmp     rax, r13
0x18002790a  jz      loc_180027C99
0x180027910  test    byte ptr [rax+1Ch], 8
0x180027914  jz      loc_180027C99
0x18002791a  cmp     byte ptr [rax+19h], 2
0x18002791e  jb      loc_180027C99
0x180027924  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027929  lea     edx, [r12+25h]
0x18002792e  lea     rcx, aPfgraphicsupda; "pfGraphicsUpdateAvailable"
0x180027935  jmp     loc_1800278AE
0x18002793a  mov     rax, [rdi]
0x18002793d  lea     rdx, [rbp+var_10]
0x180027941  mov     rcx, rdi
0x180027944  mov     rax, [rax+0A0h]
0x18002794b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027950  mov     r15d, eax
0x180027953  test    eax, eax
0x180027955  jns     short loc_1800279BC
0x180027957  mov     rax, cs:WPP_GLOBAL_Control
0x18002795e  lea     r13, WPP_GLOBAL_Control
0x180027965  cmp     rax, r13
0x180027968  jz      loc_180027C99
0x18002796e  test    byte ptr [rax+1Ch], 8
0x180027972  jz      loc_180027C99
0x180027978  cmp     byte ptr [rax+19h], 2
0x18002797c  jb      loc_180027C99
0x180027982  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027987  mov     edx, 26h ; '&'
0x18002798c  lea     rcx, aFailedToGetBas_1; "Failed to get Base Encoder"
0x180027993  mov     dword ptr [rsp+50h+var_28], r15d
0x180027998  lea     r8, WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids
0x18002799f  mov     qword ptr [rsp+50h+var_30], rcx
0x1800279a4  mov     r9d, eax
0x1800279a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279ae  mov     rcx, [rcx+10h]
0x1800279b2  call    WPP_SF_DsD
0x1800279b7  jmp     loc_180027C99
0x1800279bc  mov     dword ptr [r13+0], 0
0x1800279c4  mov     rcx, r14; this
0x1800279c7  mov     r13d, 1
0x1800279cd  mov     [r12], r13d
0x1800279d1  mov     dword ptr [r14+7B4h], 0
0x1800279dc  call    ?UnBlockHybridDriver@CRdpUT@@IEAAXXZ; CRdpUT::UnBlockHybridDriver(void)
0x1800279e1  test    rsi, rsi
0x1800279e4  jz      short loc_180027A0F
0x1800279e6  mov     rax, [rsi]
0x1800279e9  lea     rdx, [rbp+arg_0]
0x1800279ed  mov     rcx, rsi
0x1800279f0  mov     [rbp+arg_0], r13d
0x1800279f4  mov     rax, [rax+18h]
0x1800279f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279fd  test    eax, eax
0x1800279ff  js      short loc_180027A0F
0x180027a01  cmp     [rbp+arg_0], 0
0x180027a05  jnz     short loc_180027A0F
0x180027a07  mov     dword ptr [r12], 0
0x180027a0f  mov     rax, [rbx]
0x180027a12  mov     rcx, rbx
0x180027a15  mov     rax, [rax+18h]
0x180027a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a1e  mov     r15d, eax
0x180027a21  test    eax, eax
0x180027a23  jns     short loc_180027A82
0x180027a25  mov     r9d, eax; unsigned int
0x180027a28  lea     rdx, aUpdatetrackere_23; "UpdateTrackerError_LockContextDataAndPr"...
0x180027a2f  mov     r8d, 1C9h; char *
0x180027a35  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x180027a3c  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180027a41  mov     rax, cs:WPP_GLOBAL_Control
0x180027a48  lea     r13, WPP_GLOBAL_Control
0x180027a4f  cmp     rax, r13
0x180027a52  jz      loc_180027C99
0x180027a58  test    byte ptr [rax+1Ch], 8
0x180027a5c  jz      loc_180027C99
0x180027a62  cmp     byte ptr [rax+19h], 2
0x180027a66  jb      loc_180027C99
0x180027a6c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027a71  mov     edx, 27h ; '''
0x180027a76  lea     rcx, aFailedToRefres; "Failed to refresh the update context"
0x180027a7d  jmp     loc_180027993
0x180027a82  lea     rcx, [r14+808h]; this
0x180027a89  mov     [rsp+50h+var_30], 1CBh; int
0x180027a91  lea     r9, aOnecoreTermsrv_27; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180027a98  lea     r8, aCrdputLockcont_0; "CRdpUT::LockContextDataAndProcessUpdate"...
0x180027a9f  lea     rdx, aLockcontextdat; "LockContextData"
0x180027aa6  call    ?push0@CInflightRecorder@NoSTL@Utils@Modern@Rdp@@QEAAXPEAGPEAD1I@Z; Rdp::Modern::Utils::NoSTL::CInflightRecorder::push0(ushort *,char *,char *,uint)
0x180027aab  mov     [r14+134h], r13d
0x180027ab2  mov     rcx, rbx
0x180027ab5  mov     rax, [rbx]
0x180027ab8  mov     rax, [rax+50h]
0x180027abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ac1  test    eax, eax
0x180027ac3  jnz     short loc_180027AE1
0x180027ac5  mov     rcx, [rbp+var_10]
0x180027ac9  mov     rax, [rcx]
0x180027acc  mov     rax, [rax+50h]
0x180027ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ad5  test    eax, eax
0x180027ad7  jnz     short loc_180027AE1
0x180027ad9  xor     r15d, r15d
0x180027adc  jmp     loc_180027C92
0x180027ae1  mov     rcx, [rbp+var_20]
0x180027ae5  mov     [rbp+arg_18], r13d
0x180027ae9  mov     [r12], r13d
0x180027aed  mov     r13d, [r14+130h]
0x180027af4  test    rcx, rcx
0x180027af7  jz      short loc_180027B69
0x180027af9  mov     rax, [rcx]
0x180027afc  mov     rax, [rax+20h]
0x180027b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b05  mov     r15d, eax
0x180027b08  test    eax, eax
0x180027b0a  jns     short loc_180027B69
0x180027b0c  mov     r9d, eax; unsigned int
0x180027b0f  lea     rdx, aUpdatetrackere_18; "UpdateTrackerError_LockContextDataAndPr"...
0x180027b16  mov     r8d, 1F0h; char *
0x180027b1c  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x180027b23  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180027b28  mov     rax, cs:WPP_GLOBAL_Control
0x180027b2f  lea     r13, WPP_GLOBAL_Control
0x180027b36  cmp     rax, r13
0x180027b39  jz      loc_180027C99
0x180027b3f  test    byte ptr [rax+1Ch], 8
0x180027b43  jz      loc_180027C99
0x180027b49  cmp     byte ptr [rax+19h], 2
0x180027b4d  jb      loc_180027C99
0x180027b53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027b58  mov     edx, 28h ; '('
0x180027b5d  lea     rcx, aRecorderSignal; "Recorder SignalStartOfUpdates failed"
0x180027b64  jmp     loc_180027993
0x180027b69  mov     rax, [rbx]
0x180027b6c  inc     r13d
0x180027b6f  mov     rcx, rbx
0x180027b72  mov     rax, [rax+58h]
0x180027b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b7b  mov     r12, [rbp+arg_8]
0x180027b7f  test    rax, rax
0x180027b82  jz      short loc_180027BFB
0x180027b84  mov     [rsp+50h+var_28], r12; __int64
0x180027b89  lea     r9, [rbp+var_20]
0x180027b8d  lea     r8, [rbp+var_18]
0x180027b91  mov     [rsp+50h+var_30], r13d; int
0x180027b96  mov     rdx, rax; struct _RDPGFX_PROVIDER_UPDATE_HDR *
0x180027b99  mov     rcx, r14; this
0x180027b9c  call    ?ProcessGfxProviderUpdates@CRdpUT@@IEAAJPEAU_RDPGFX_PROVIDER_UPDATE_HDR@@AEAV?$ComPlainSmartPtr@VIRdpPipeSurfaceFactory@@@@AEAV?$ComPlainSmartPtr@UIRdpGFXRecorder@@@@IPEAH@Z; CRdpUT::ProcessGfxProviderUpdates(_RDPGFX_PROVIDER_UPDATE_HDR *,ComPlainSmartPtr<IRdpPipeSurfaceFactory> &,ComPlainSmartPtr<IRdpGFXRecorder> &,uint,int *)
0x180027ba1  mov     r15d, eax
0x180027ba4  test    eax, eax
0x180027ba6  js      short loc_180027BBA
0x180027ba8  mov     rcx, [r14+48h]
0x180027bac  mov     rax, [rcx]
0x180027baf  mov     rax, [rax+58h]
0x180027bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bb8  jmp     short loc_180027B7F
0x180027bba  mov     rax, cs:WPP_GLOBAL_Control
0x180027bc1  lea     r13, WPP_GLOBAL_Control
0x180027bc8  cmp     rax, r13
0x180027bcb  jz      loc_180027C99
0x180027bd1  test    byte ptr [rax+1Ch], 8
0x180027bd5  jz      loc_180027C99
0x180027bdb  cmp     byte ptr [rax+19h], 2
0x180027bdf  jb      loc_180027C99
0x180027be5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027bea  mov     edx, 29h ; ')'
0x180027bef  lea     rcx, aProcessgfxprov; "ProcessGfxProviderUpdates failed"
0x180027bf6  jmp     loc_180027993
0x180027bfb  mov     [rbp+arg_0], eax
0x180027bfe  test    eax, eax
0x180027c00  jnz     short loc_180027C6B
0x180027c02  lea     rdx, [rbp+arg_0]; int *
0x180027c06  mov     rcx, r14; this
0x180027c09  call    ?FlushOrders@CRdpUT@@IEAAJPEAH@Z; CRdpUT::FlushOrders(int *)
0x180027c0e  mov     r15d, eax
0x180027c11  test    eax, eax
  ... truncated ...
```
