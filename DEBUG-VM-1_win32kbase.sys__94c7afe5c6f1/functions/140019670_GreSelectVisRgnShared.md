# GreSelectVisRgnShared

- ea: `0x140019670`
- end: `0x140019fc9`
- name: `GreSelectVisRgnShared`
- size: `2393`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000f600`
- `0x14001043c`
- `0x140010c18`
- `0x140013ff0`
- `0x140017420`
- `0x140017a90`
- `0x1400185b0`
- `0x140019670`
- `0x140019fd0`
- `0x14001a030`
- `0x14001b910`
- `0x14001bca0`
- `0x14001bf60`
- `0x14001c2d0`
- `0x14001c340`
- `0x14001c970`
- `0x14001ca10`
- `0x14001cb30`
- `0x14001d250`
- `0x14001df40`
- `0x14001e1e0`
- `0x14001e2b4`
- `0x14001ef1c`
- `0x14001f340`
- `0x14001f570`
- `0x140020728`
- `0x140020758`
- `0x140020a34`
- `0x140021710`
- `0x1400393dc`
- `0x14003f8c0`
- `0x14003fe30`
- `0x1400944f0`
- `0x14015319c`
- `0x140190650`
- `0x1401b4578`
- `0x140238b10`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400197f3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400197f3`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400196de`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019982`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400196de`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140019982`
- `WIN32K!W32GetSessionState` at `0x1400196b3`
- `WIN32K!W32GetSessionState` at `0x1400197ff`
- `WIN32K!W32GetSessionState` at `0x1400198e7`
- `WIN32K!W32GetSessionState` at `0x140019a56`
- `WIN32K!W32GetSessionState` at `0x140019b10`
- `WIN32K!W32GetSessionState` at `0x140019bc5`
- `WIN32K!W32GetSessionState` at `0x140019d81`
- `WIN32K!W32GetSessionState` at `0x1400196b3`
- `WIN32K!W32GetSessionState` at `0x1400197ff`
- `WIN32K!W32GetSessionState` at `0x1400198e7`
- `WIN32K!W32GetSessionState` at `0x140019a56`
- `WIN32K!W32GetSessionState` at `0x140019b10`
- `WIN32K!W32GetSessionState` at `0x140019bc5`
- `WIN32K!W32GetSessionState` at `0x140019d81`

## pseudocode

```c
__int64 __fastcall GreSelectVisRgnShared(__int64 a1, HRGN a2, int a3)
{
  int v3; // r13d
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 result; // rax
  struct Gre::Base::SESSION_GLOBALS *v14; // r15
  HSEMAPHORE v15; // r12
  DC *v16; // rcx
  unsigned int v17; // ebx
  struct _ENTRY *v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // r14
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // r13
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // ebx
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 SessionState; // rax
  __int64 v30; // rax
  DC *v31; // rbx
  __int64 v32; // r14
  volatile signed __int16 *v33; // rdi
  _QWORD *v34; // rax
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // r9
  __int64 v40; // r11
  __int64 v41; // rax
  int v42; // eax
  int v43; // r8d
  LONG v44; // edx
  int v45; // r10d
  bool v46; // zf
  __int64 v47; // rax
  volatile signed __int16 *v48; // r14
  int v49; // r8d
  DC *v50; // rbx
  DC *v51; // rcx
  struct _ENTRY *v52; // rax
  DC *v53; // rbx
  __int64 v54; // rcx
  struct _GRETHREAD *v55; // rax
  __int64 v56; // rax
  _QWORD **v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rdx
  DC *v61; // rbx
  int v62; // ebx
  LONG v63; // edi
  LONG v64; // ebx
  __int64 *v65; // r11
  __int64 v66; // r11
  bool v67; // cc
  __int64 v68; // rax
  unsigned int sizeScan; // eax
  const struct REGION_CORE *v70; // rdi
  __int64 v71; // rbx
  __int64 *v72; // rdx
  __int64 *v73; // rdx
  HSURF v74; // rdx
  volatile signed __int16 *v75; // [rsp+30h] [rbp-A9h] BYREF
  int v76; // [rsp+38h] [rbp-A1h]
  __int128 v77; // [rsp+40h] [rbp-99h] BYREF
  __int128 v78; // [rsp+50h] [rbp-89h]
  __int64 v79; // [rsp+60h] [rbp-79h]
  __int64 v80; // [rsp+68h] [rbp-71h] BYREF
  DC *v81; // [rsp+70h] [rbp-69h] BYREF
  int v82; // [rsp+78h] [rbp-61h]
  struct Gre::Base::SESSION_GLOBALS *v83; // [rsp+80h] [rbp-59h]
  __int64 v84; // [rsp+88h] [rbp-51h]
  __int128 v85; // [rsp+90h] [rbp-49h] BYREF
  __int128 v86; // [rsp+A0h] [rbp-39h]
  volatile signed __int16 *v87; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v88; // [rsp+B8h] [rbp-21h] BYREF
  _QWORD **v89; // [rsp+C0h] [rbp-19h]
  int v90; // [rsp+E0h] [rbp+7h]
  struct _RECTL v91; // [rsp+E8h] [rbp+Fh] BYREF

  LODWORD(v75) = a3;
  v81 = 0;
  v3 = a3;
  v82 = 0;
  v83 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(a1) + 88);
  v84 = 0;
  v81 = 0;
  v82 = 0;
  v85 = 0;
  v86 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( !CurrentThreadWin32Thread || (v7 = *CurrentThreadWin32Thread) == 0 )
  {
    *(_QWORD *)&v86 = &v81;
    *((_QWORD *)&v86 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_120;
  }
  *(_QWORD *)&v86 = &v81;
  *((_QWORD *)&v86 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  v8 = v7 + 8;
  if ( !v8 )
  {
LABEL_120:
    *((_QWORD *)&v85 + 1) = &v85;
    *(_QWORD *)&v85 = &v85;
    goto LABEL_7;
  }
  v9 = *(_QWORD *)(v8 + 88);
  v10 = (_QWORD *)(v8 + 88);
  if ( *(_QWORD **)(v9 + 8) != v10 )
    goto LABEL_5;
  *(_QWORD *)&v85 = v9;
  *((_QWORD *)&v85 + 1) = v10;
  *(_QWORD *)(v9 + 8) = &v85;
  *v10 = &v85;
LABEL_7:
  v81 = (DC *)HmgShareLock(v83, a1, 1, 1);
  if ( !v81 )
  {
    v11 = v85;
    if ( *(__int128 **)(v85 + 8) == &v85 )
    {
      v12 = *((_QWORD *)&v85 + 1);
      if ( **((__int128 ***)&v85 + 1) == &v85 )
      {
        **((_QWORD **)&v85 + 1) = v85;
        *(_QWORD *)(v11 + 8) = v12;
        return 0;
      }
    }
LABEL_5:
    __fastfail(3u);
  }
  v14 = v83;
  v15 = (HSEMAPHORE)(*(_QWORD *)v83 + 1248LL);
  GreAcquireSemaphoreInternal(v15);
  GrepAcquireLockValidate<11>();
  v16 = v81;
  v17 = 1;
  v76 = 1;
  *((_DWORD *)v81 + 9) |= 0x10u;
  v18 = DC::PentryFromPobj(v16, v14);
  *((_BYTE *)v18 + 15) |= 4u;
  if ( !a2 )
  {
    DC::vReleaseVis(v81, v14);
    DC::bSetDefaultRegion(v81);
    goto LABEL_58;
  }
  PsGetCurrentProcessId();
  v20 = *(_QWORD **)(W32GetSessionState(v19) + 88);
  v80 = *v20 + 1512LL;
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v21, v80);
  HANDLELOCK::HANDLELOCK(&v77, v20, a2, 1);
  if ( DWORD2(v77) )
  {
    v22 = v77;
    if ( *(_BYTE *)(v77 + 14) == 4 && *(_WORD *)(v77 + 12) == WORD1(a2) )
    {
      v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v78 + 8) + 96LL))(
              *(_QWORD *)(v78 + 8),
              *(unsigned int *)v77);
      GreGetCurrentThread();
      if ( !*(_WORD *)(v23 + 12) || *(struct _KTHREAD **)(v23 + 16) == KeGetCurrentThread() )
      {
        v26 = *(_DWORD *)(v22 + 8) & 0xFFFFFFFE;
        if ( v26 && (unsigned int)HmgIncProcessHandleCount(0, v24, v25) )
        {
          HmgDecProcessHandleCount(v20, v26);
          HANDLELOCK::Pid((HANDLELOCK *)&v77, 0);
          *(_WORD *)(v23 + 14) &= ~0x10u;
        }
        v3 = (int)v75;
        goto LABEL_18;
      }
      v3 = (int)v75;
    }
    BYTE13(v77) = 1;
LABEL_18:
    HANDLELOCK::vUnlock((HANDLELOCK *)&v77);
  }
  HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v77);
  SEMOBJ<20>::vUnlock(&v80);
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v87, a2, 0, 0);
  if ( !v87 )
    goto LABEL_66;
  v28 = *(_QWORD *)v81;
  SessionState = W32GetSessionState(v27);
  v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
          *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
          (unsigned __int16)v28 | ((unsigned int)v28 >> 8) & 0xFF0000);
  if ( v30
    && *(_BYTE *)(v30 + 14) == 1
    && *(_WORD *)(v30 + 12) == WORD1(v28)
    && (*(_DWORD *)(v30 + 8) & 0xFFFFFFFE) == 0x80000012 )
  {
    goto LABEL_44;
  }
  v31 = v81;
  if ( (*((_DWORD *)v81 + 9) & 0x100000) == 0 )
    goto LABEL_44;
  v32 = *((_QWORD *)v81 + 6);
  if ( !v32 )
    goto LABEL_44;
  v33 = v87;
  if ( !v87 )
    goto LABEL_44;
  v77 = 0;
  v78 = 0;
  v34 = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( !v34 || !*v34 )
  {
    v36 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    *(_QWORD *)&v78 = &v77;
    *((_QWORD *)&v78 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    goto LABEL_129;
  }
  v35 = *v34 + 8LL;
  *(_QWORD *)&v78 = &v77;
  v36 = (unsigned __int64)UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  *((_QWORD *)&v78 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
  if ( !v35 )
  {
LABEL_129:
    *((_QWORD *)&v77 + 1) = &v77;
    *(_QWORD *)&v77 = &v77;
    goto LABEL_32;
  }
  v37 = *(_QWORD *)(v35 + 88);
  v38 = (_QWORD *)(v35 + 88);
  if ( *(_QWORD **)(v37 + 8) != v38 )
    goto LABEL_5;
  *(_QWORD *)&v77 = v37;
  *((_QWORD *)&v77 + 1) = v38;
  *(_QWORD *)(v37 + 8) = &v77;
  v36 = (unsigned __int64)&v77;
  *v38 = &v77;
LABEL_32:
  v39 = 0;
  v46 = (*((_DWORD *)v31 + 9) & 0x40000) == 0;
  v79 = 0;
  if ( v46 )
  {
    v40 = *((_QWORD *)v31 + 62);
    v41 = 0;
  }
  else
  {
    v74 = (HSURF)*((_QWORD *)v31 + 268);
    if ( v74 )
    {
      SURFREF::vLock((SURFREF *)&v77, v74);
      v39 = v79;
      v40 = v79;
      v41 = v79;
    }
    else
    {
      v40 = *(_QWORD *)(v32 + 2544);
      v41 = 0;
    }
  }
  if ( !v40 )
  {
    v46 = v41 == 0;
LABEL_41:
    if ( v46 )
    {
LABEL_43:
      PopThreadGuardedObject(&v77);
      goto LABEL_44;
    }
LABEL_42:
    v47 = W32GetSessionState(v36);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v47 + 88), v79);
    goto LABEL_43;
  }
  if ( (*(_DWORD *)(v32 + 40) & 0x20000) != 0 && *(int *)(v40 + 160) < 0
    || (v42 = *((_DWORD *)v31 + 9), (v42 & 0x1000) != 0) && (v42 & 0x4000) == 0
    || (v43 = *((_DWORD *)v33 + 13), v44 = *((_DWORD *)v33 + 15), v43 == v44)
    || (v45 = *((_DWORD *)v33 + 14), v36 = *((unsigned int *)v33 + 16), v45 == (_DWORD)v36)
    || v43 == 0x7FFFFFFF && (_DWORD)v36 == 0x80000000 && v45 == 0x7FFFFFFF && v44 == (_DWORD)v36 )
  {
    v46 = v39 == 0;
    goto LABEL_41;
  }
  v63 = *((_DWORD *)v33 + 13);
  v64 = v45;
  if ( (*(_DWORD *)(v40 + 164) & 0x800) != 0 )
    v65 = (__int64 *)(v40 + 716);
  else
    v65 = (__int64 *)(v40 + 56);
  v66 = *v65;
  if ( v43 >= v44 )
  {
    if ( v43 > v44 )
    {
      v63 = v44;
      v44 = v43;
    }
    v67 = v45 <= (int)v36;
    goto LABEL_91;
  }
  v67 = v45 <= (int)v36;
  if ( v45 >= (int)v36 )
  {
LABEL_91:
    if ( !v67 )
    {
      v64 = v36;
      v36 = (unsigned int)v45;
    }
    goto LABEL_93;
  }
  if ( v43 < 0 )
  {
LABEL_93:
    if ( v63 < 0 )
      v63 = 0;
LABEL_95:
    if ( v64 < 0 )
      v64 = 0;
    if ( (int)v66 < v44 )
      v44 = v66;
    if ( SHIDWORD(v66) >= (int)v36 )
      goto LABEL_101;
    goto LABEL_100;
  }
  if ( (int)v66 < v44 || v45 < 0 )
    goto LABEL_95;
  if ( SHIDWORD(v66) >= (int)v36 )
  {
    if ( !v39 )
      goto LABEL_43;
    goto LABEL_42;
  }
LABEL_100:
  v36 = HIDWORD(v66);
LABEL_101:
  if ( v44 < v63 )
  {
    v63 = v44;
  }
  else if ( (int)v36 < v64 )
  {
    v64 = v36;
  }
  v91.left = v63;
  v91.top = v64;
  v91.right = v44;
  v91.bottom = v36;
  if ( v39 )
  {
    v68 = W32GetSessionState(v36);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v68 + 88), v79);
  }
  PopThreadGuardedObject(&v77);
  RGNOBJ::vSet((RGNOBJ *)&v87, &v91);
LABEL_44:
  if ( v3 != 1 )
  {
    if ( v3 != 2 )
    {
      if ( v3 != 4 )
      {
        v48 = 0;
        goto LABEL_47;
      }
      v61 = v81;
      GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v81 + 1112));
      *(_QWORD *)&v91.left = v61;
      LOBYTE(v91.right) = 1;
      v48 = (volatile signed __int16 *)*((_QWORD *)v81 + 142);
      if ( v48 )
      {
        if ( v48 != *((volatile signed __int16 **)v14 + 533) )
        {
          v75 = (volatile signed __int16 *)*((_QWORD *)v81 + 142);
          RGNOBJAPI::bSwap((__int64 **)&v87, (__int64 **)&v75);
          v48 = v75;
          v62 = 0;
          goto LABEL_75;
        }
      }
      else
      {
        v48 = (volatile signed __int16 *)*((_QWORD *)v14 + 533);
      }
      v62 = 1;
      v76 = 0;
LABEL_75:
      _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v91);
      if ( !v62 )
        goto LABEL_48;
      goto LABEL_47;
    }
    sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v87 + 12));
    v75 = 0;
    RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v75, sizeScan);
    v48 = v75;
    if ( v75 )
    {
      if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
      {
        v70 = (const struct REGION_CORE *)(v75 + 12);
        v71 = *(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory;
        v72 = (__int64 *)(v87 + 12);
        if ( !v87 )
          v72 = 0;
        (*(void (__fastcall **)(const struct REGION_CORE *, __int64 *, volatile signed __int16 *))(v71 + 48))(
          v70,
          v72,
          v87);
        RgnCaptureLiveMemoryDumpOnZeroSizedScan((const struct BaseRustExports *)v71, v70);
      }
      else
      {
        v75 += 12;
        v73 = (__int64 *)(v87 + 12);
        if ( !v87 )
          v73 = 0;
        v80 = (__int64)v73;
        RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v75, (const struct RGNCOREOBJ *)&v80);
      }
      goto LABEL_47;
    }
LABEL_66:
    v48 = (volatile signed __int16 *)*((_QWORD *)v14 + 533);
    goto LABEL_47;
  }
  v48 = v87;
  if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v87) )
  {
    v87 = 0;
LABEL_47:
    v50 = v81;
    v51 = v81;
    *((_DWORD *)v81 + 9) |= 0x10u;
    v52 = DC::PentryFromPobj(v51, v14);
    *((_BYTE *)v52 + 15) |= 4u;
    GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v50 + 1112));
    v80 = *((_QWORD *)v50 + 142);
    *(_QWORD *)&v91.left = v50;
    LOBYTE(v91.right) = 1;
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v80);
    *((_QWORD *)v50 + 142) = *((_QWORD *)v14 + 533);
    _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v91);
LABEL_48:
    v53 = v81;
    GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v81 + 1112));
    *((_QWORD *)v81 + 142) = v48;
    *((_DWORD *)v48 + 18) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(v54) + 88)
                                                                            + 4248LL));
    v55 = GreGetCurrentThreadCrossSessionCheck();
    if ( v55 )
      *(_QWORD *)v55 &= ~0x4000000000uLL;
    GrePushLock::ReleaseLock((DC *)((char *)v53 + 1112));
    v17 = v76;
    goto LABEL_51;
  }
  v17 = 0;
LABEL_51:
  if ( !v90 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v87);
  if ( v87 )
    _InterlockedDecrement16(v87 + 6);
  v56 = v88;
  if ( *(__int64 **)(v88 + 8) != &v88 )
    goto LABEL_5;
  v57 = v89;
  if ( *v89 != &v88 )
    goto LABEL_5;
  *v89 = (_QWORD *)v88;
  *(_QWORD *)(v56 + 8) = v57;
LABEL_58:
  if ( v15 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (_DWORD)v57,
        (unsigned int)&LockRelease,
        v49,
        (_DWORD)v15,
        (__int64)L"VisRgnPublish");
    GrepReleaseLockValidate<11>();
    GreReleaseSemaphoreSharedInternal(v15);
  }
  if ( v81 )
  {
    v58 = W32GetSessionState(v57);
    HmgDecrementShareReferenceCount(*(_QWORD *)(v58 + 88), v81);
    v81 = 0;
  }
  v59 = v85;
  if ( *(__int128 **)(v85 + 8) != &v85 )
    goto LABEL_5;
  v60 = *((_QWORD *)&v85 + 1);
  if ( **((__int128 ***)&v85 + 1) != &v85 )
    goto LABEL_5;
  **((_QWORD **)&v85 + 1) = v85;
  result = v17;
  *(_QWORD *)(v59 + 8) = v60;
  return result;
}

```

## disassembly

```asm
0x140019670  mov     [rsp-8+arg_10], rbx
0x140019675  push    rbp
0x140019676  push    rsi
0x140019677  push    rdi
0x140019678  push    r12
0x14001967a  push    r13
0x14001967c  push    r14
0x14001967e  push    r15
0x140019680  lea     rbp, [rsp-27h]
0x140019685  sub     rsp, 100h
0x14001968c  mov     rax, cs:__security_cookie
0x140019693  xor     rax, rsp
0x140019696  mov     [rbp+57h+var_38], rax
0x14001969a  xor     r14d, r14d
0x14001969d  mov     dword ptr [rsp+130h+var_100], r8d
0x1400196a2  mov     [rbp+57h+var_C0], r14
0x1400196a6  mov     r13d, r8d
0x1400196a9  mov     [rbp+57h+var_B8], r14d
0x1400196ad  mov     rdi, rdx
0x1400196b0  mov     rbx, rcx
0x1400196b3  call    cs:__imp_W32GetSessionState
0x1400196ba  nop     dword ptr [rax+rax+00h]
0x1400196bf  xorps   xmm0, xmm0
0x1400196c2  mov     rcx, [rax+58h]
0x1400196c6  mov     [rbp+57h+var_B0], rcx
0x1400196ca  mov     [rbp+57h+var_A8], r14
0x1400196ce  mov     [rbp+57h+var_C0], r14
0x1400196d2  mov     [rbp+57h+var_B8], r14d
0x1400196d6  movups  [rbp+57h+var_A0], xmm0
0x1400196da  movups  [rbp+57h+var_90], xmm0
0x1400196de  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400196e5  nop     dword ptr [rax+rax+00h]
0x1400196ea  test    rax, rax
0x1400196ed  jz      loc_140019E7D
0x1400196f3  mov     rax, [rax]
0x1400196f6  test    rax, rax
0x1400196f9  jz      loc_140019E7D
0x1400196ff  lea     rcx, [rbp+57h+var_C0]
0x140019703  mov     qword ptr [rbp+57h+var_90], rcx
0x140019707  lea     rcx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x14001970e  mov     qword ptr [rbp+57h+var_90+8], rcx
0x140019712  add     rax, 8
0x140019716  jz      loc_140019E90
0x14001971c  mov     rcx, [rax+58h]
0x140019720  add     rax, 58h ; 'X'
0x140019724  cmp     [rcx+8], rax
0x140019728  jz      short loc_140019731
0x14001972a  mov     ecx, 3
0x14001972f  int     29h; Win8: RtlFailFast(ecx)
0x140019731  mov     qword ptr [rbp+57h+var_A0], rcx
0x140019735  lea     rdx, [rbp+57h+var_A0]
0x140019739  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14001973d  mov     [rcx+8], rdx
0x140019741  lea     rcx, [rbp+57h+var_A0]
0x140019745  mov     [rax], rcx
0x140019748  mov     rcx, [rbp+57h+var_B0]
0x14001974c  mov     esi, 1
0x140019751  mov     r9d, esi
0x140019754  movzx   r8d, sil
0x140019758  mov     rdx, rbx
0x14001975b  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140019760  mov     [rbp+57h+var_C0], rax
0x140019764  test    rax, rax
0x140019767  jnz     short loc_1400197B5
0x140019769  mov     rax, qword ptr [rbp+57h+var_A0]
0x14001976d  lea     rcx, [rbp+57h+var_A0]
0x140019771  cmp     [rax+8], rcx
0x140019775  jnz     short loc_14001972A
0x140019777  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x14001977b  lea     rdx, [rbp+57h+var_A0]
0x14001977f  cmp     [rcx], rdx
0x140019782  jnz     short loc_14001972A
0x140019784  mov     [rcx], rax
0x140019787  mov     [rax+8], rcx
0x14001978b  xor     eax, eax
0x14001978d  mov     rcx, [rbp+57h+var_38]
0x140019791  xor     rcx, rsp; StackCookie
0x140019794  call    __security_check_cookie
0x140019799  mov     rbx, [rsp+130h+arg_10]
0x1400197a1  add     rsp, 100h
0x1400197a8  pop     r15
0x1400197aa  pop     r14
0x1400197ac  pop     r13
0x1400197ae  pop     r12
0x1400197b0  pop     rdi
0x1400197b1  pop     rsi
0x1400197b2  pop     rbp
0x1400197b3  retn
0x1400197b5  mov     r15, [rbp+57h+var_B0]
0x1400197b9  mov     r12, [r15]
0x1400197bc  add     r12, 4E0h
0x1400197c3  mov     rcx, r12; Resource
0x1400197c6  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x1400197cb  call    ??$GrepAcquireLockValidate@$0L@@@YAXXZ; GrepAcquireLockValidate<11>(void)
0x1400197d0  mov     rcx, [rbp+57h+var_C0]; this
0x1400197d4  mov     ebx, esi
0x1400197d6  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x1400197d9  mov     [rsp+130h+var_F8], ebx
0x1400197dd  or      dword ptr [rcx+24h], 10h
0x1400197e1  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x1400197e6  or      byte ptr [rax+0Fh], 4
0x1400197ea  test    rdi, rdi
0x1400197ed  jz      loc_140019DEC
0x1400197f3  call    cs:__imp_PsGetCurrentProcessId
0x1400197fa  nop     dword ptr [rax+rax+00h]
0x1400197ff  call    cs:__imp_W32GetSessionState
0x140019806  nop     dword ptr [rax+rax+00h]
0x14001980b  mov     r14, [rax+58h]
0x14001980f  mov     rdx, [r14]
0x140019812  add     rdx, 5E8h
0x140019819  mov     [rbp+57h+var_C8], rdx
0x14001981d  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140019822  mov     r9d, esi
0x140019825  lea     rcx, [rsp+130h+var_F0]
0x14001982a  mov     r8, rdi
0x14001982d  mov     rdx, r14
0x140019830  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x140019835  cmp     dword ptr [rsp+130h+var_F0+8], 0
0x14001983a  jz      short loc_1400198B0
0x14001983c  mov     rbx, qword ptr [rsp+130h+var_F0]
0x140019841  cmp     byte ptr [rbx+0Eh], 4
0x140019845  jnz     loc_140019F83
0x14001984b  movzx   eax, byte ptr [rbx+0Ch]
0x14001984f  movzx   ecx, byte ptr [rbx+0Dh]
0x140019853  shl     cx, 8
0x140019857  or      cx, ax
0x14001985a  mov     eax, edi
0x14001985c  shr     eax, 10h
0x14001985f  cmp     cx, ax
0x140019862  jnz     loc_140019F83
0x140019868  mov     rax, qword ptr [rsp+130h+var_E0]
0x14001986d  mov     edx, [rbx]
0x14001986f  mov     rcx, [rax+8]
0x140019873  mov     rax, [rcx]
0x140019876  mov     rax, [rax+60h]
0x14001987a  call    _guard_dispatch_icall
0x14001987f  mov     r13, rax
0x140019882  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140019887  movzx   ecx, word ptr [r13+0Ch]
0x14001988c  test    cx, cx
0x14001988f  jnz     loc_140019F6B
0x140019895  mov     ebx, [rbx+8]
0x140019898  and     ebx, 0FFFFFFFEh
0x14001989b  jnz     loc_140019C1F
0x1400198a1  mov     r13d, dword ptr [rsp+130h+var_100]
0x1400198a6  lea     rcx, [rsp+130h+var_F0]; this
0x1400198ab  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x1400198b0  lea     rcx, [rsp+130h+var_F0]; this
0x1400198b5  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x1400198ba  lea     rcx, [rbp+57h+var_C8]
0x1400198be  call    ?vUnlock@?$SEMOBJ@$0BE@@@QEAAXXZ; SEMOBJ<20>::vUnlock(void)
0x1400198c3  xor     r9d, r9d; int
0x1400198c6  lea     rcx, [rbp+57h+var_80]; this
0x1400198ca  xor     r8d, r8d; int
0x1400198cd  mov     rdx, rdi; HRGN
0x1400198d0  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x1400198d5  cmp     [rbp+57h+var_80], 0
0x1400198da  jz      loc_140019C13
0x1400198e0  mov     rax, [rbp+57h+var_C0]
0x1400198e4  mov     rbx, [rax]
0x1400198e7  call    cs:__imp_W32GetSessionState
0x1400198ee  nop     dword ptr [rax+rax+00h]
0x1400198f3  mov     edx, ebx
0x1400198f5  shr     edx, 8
0x1400198f8  and     edx, 0FF0000h
0x1400198fe  mov     rcx, [rax+58h]
0x140019902  movzx   eax, bx
0x140019905  or      edx, eax
0x140019907  mov     rcx, [rcx+8]
0x14001990b  mov     r8, [rcx]
0x14001990e  mov     rax, [r8+10h]
0x140019912  call    _guard_dispatch_icall
0x140019917  test    rax, rax
0x14001991a  jz      short loc_14001994A
0x14001991c  cmp     [rax+0Eh], sil
0x140019920  jnz     short loc_14001994A
0x140019922  movzx   edx, byte ptr [rax+0Dh]
0x140019926  movzx   ecx, byte ptr [rax+0Ch]
0x14001992a  shl     dx, 8
0x14001992e  or      dx, cx
0x140019931  shr     ebx, 10h
0x140019934  cmp     dx, bx
0x140019937  jnz     short loc_14001994A
0x140019939  mov     eax, [rax+8]
0x14001993c  and     eax, 0FFFFFFFEh
0x14001993f  cmp     eax, 80000012h
0x140019944  jz      loc_140019A79
0x14001994a  mov     rbx, [rbp+57h+var_C0]
0x14001994e  test    dword ptr [rbx+24h], 100000h
0x140019955  jz      loc_140019A79
0x14001995b  mov     r14, [rbx+30h]
0x14001995f  test    r14, r14
0x140019962  jz      loc_140019A79
0x140019968  mov     rdi, [rbp+57h+var_80]
0x14001996c  test    rdi, rdi
0x14001996f  jz      loc_140019A79
0x140019975  xorps   xmm0, xmm0
0x140019978  movups  [rsp+130h+var_F0], xmm0
0x14001997d  movups  [rsp+130h+var_E0], xmm0
0x140019982  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140019989  nop     dword ptr [rax+rax+00h]
0x14001998e  test    rax, rax
0x140019991  jz      loc_140019F01
0x140019997  mov     rcx, [rax]
0x14001999a  test    rcx, rcx
0x14001999d  jz      loc_140019F01
0x1400199a3  lea     rax, [rcx+8]
0x1400199a7  lea     rcx, [rsp+130h+var_F0]
0x1400199ac  mov     qword ptr [rsp+130h+var_E0], rcx
0x1400199b1  lea     rcx, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400199b8  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x1400199bd  test    rax, rax
0x1400199c0  jz      loc_140019F17
0x1400199c6  mov     rcx, [rax+58h]
0x1400199ca  add     rax, 58h ; 'X'
0x1400199ce  cmp     [rcx+8], rax
0x1400199d2  jnz     loc_14001972A
0x1400199d8  mov     qword ptr [rsp+130h+var_F0], rcx
0x1400199dd  lea     rdx, [rsp+130h+var_F0]
0x1400199e2  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1400199e7  mov     [rcx+8], rdx
0x1400199eb  lea     rcx, [rsp+130h+var_F0]
0x1400199f0  mov     [rax], rcx
0x1400199f3  xor     r9d, r9d
0x1400199f6  test    dword ptr [rbx+24h], 40000h
0x1400199fd  mov     [rbp+57h+var_D0], r9
0x140019a01  jnz     loc_140019F38
0x140019a07  mov     r11, [rbx+1F0h]
0x140019a0e  xor     eax, eax
0x140019a10  test    r11, r11
0x140019a13  jz      short loc_140019A51
0x140019a15  test    dword ptr [r14+28h], 20000h
0x140019a1d  jnz     loc_140019DBF
0x140019a23  mov     eax, [rbx+24h]
0x140019a26  bt      eax, 0Ch
0x140019a2a  jb      loc_140019F8D
0x140019a30  mov     r8d, [rdi+34h]
0x140019a34  mov     edx, [rdi+3Ch]
0x140019a37  cmp     r8d, edx
0x140019a3a  jz      short loc_140019A4C
0x140019a3c  mov     r10d, [rdi+38h]
0x140019a40  mov     ecx, [rdi+40h]
0x140019a43  cmp     r10d, ecx
0x140019a46  jnz     loc_140019CDB
0x140019a4c  test    r9, r9
0x140019a4f  jmp     short loc_140019A54
0x140019a51  test    rax, rax
0x140019a54  jz      short loc_140019A6F
0x140019a56  call    cs:__imp_W32GetSessionState
0x140019a5d  nop     dword ptr [rax+rax+00h]
0x140019a62  mov     rdx, [rbp+57h+var_D0]
0x140019a66  mov     rcx, [rax+58h]
0x140019a6a  call    HmgDecrementShareReferenceCount
0x140019a6f  lea     rcx, [rsp+130h+var_F0]
0x140019a74  call    PopThreadGuardedObject
0x140019a79  cmp     r13d, esi
0x140019a7c  jnz     loc_140019C5E
0x140019a82  mov     r14, [rbp+57h+var_80]
0x140019a86  lea     rcx, [rbp+57h+var_80]; this
0x140019a8a  call    ?bDeleteHandle@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteHandle(void)
0x140019a8f  test    eax, eax
0x140019a91  jz      loc_140019C53
0x140019a97  mov     [rbp+57h+var_80], 0
0x140019a9f  mov     rbx, [rbp+57h+var_C0]
0x140019aa3  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x140019aa6  mov     rcx, rbx; this
0x140019aa9  or      dword ptr [rbx+24h], 10h
0x140019aad  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140019ab2  lea     rcx, [rbx+458h]; this
0x140019ab9  or      byte ptr [rax+0Fh], 4
0x140019abd  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140019ac2  mov     rax, [rbx+470h]
0x140019ac9  lea     rcx, [rbp+57h+var_C8]; this
0x140019acd  mov     [rbp+57h+var_C8], rax
0x140019ad1  mov     qword ptr [rbp+57h+var_48.left], rbx
0x140019ad5  mov     byte ptr [rbp+57h+var_48.right], sil
0x140019ad9  call    ?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140019ade  mov     rax, [r15+10A8h]
0x140019ae5  lea     rcx, [rbp+57h+var_48]
0x140019ae9  mov     [rbx+470h], rax
0x140019af0  call    ?reset@?$lambda_call@V_lambda_1_@?1??AcquireDcVisRgnExclusive@DC@@QEAA@XZ@@details@wil@@QEAAXXZ; wil::details::lambda_call<`DC::AcquireDcVisRgnExclusive(void)'::`2'::_lambda_1_>::reset(void)
0x140019af5  mov     rbx, [rbp+57h+var_C0]
0x140019af9  lea     rcx, [rbx+458h]; this
0x140019b00  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140019b05  mov     rax, [rbp+57h+var_C0]
0x140019b09  mov     [rax+470h], r14
0x140019b10  call    cs:__imp_W32GetSessionState
0x140019b17  nop     dword ptr [rax+rax+00h]
0x140019b1c  mov     rdx, [rax+58h]
0x140019b20  lock xadd [rdx+1098h], esi
0x140019b28  inc     esi
0x140019b2a  mov     [r14+48h], esi
0x140019b2e  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x140019b33  test    rax, rax
0x140019b36  jz      short loc_140019B45
0x140019b38  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x140019b42  and     [rax], rcx
0x140019b45  lea     rcx, [rbx+458h]; this
0x140019b4c  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x140019b51  mov     ebx, [rsp+130h+var_F8]
  ... truncated ...
```
