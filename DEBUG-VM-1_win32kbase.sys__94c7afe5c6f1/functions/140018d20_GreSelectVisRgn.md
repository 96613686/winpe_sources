# GreSelectVisRgn

- ea: `0x140018d20`
- end: `0x140019663`
- name: `GreSelectVisRgn`
- size: `2371`
- prototype: ``
- caller_count: `3`
- callee_count: `38`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400b0ff0`
- `0x1400b1300`
- `0x1400b1f6c`

## callees

- `0x14000f600`
- `0x14001043c`
- `0x140010c18`
- `0x140013ff0`
- `0x140017420`
- `0x140017a90`
- `0x1400185b0`
- `0x140018d20`
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

- `ntoskrnl!PsGetCurrentProcessId` at `0x140018e53`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140018e53`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140018d8a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140018fe0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140018d8a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140018fe0`
- `WIN32K!W32GetSessionState` at `0x140018d5f`
- `WIN32K!W32GetSessionState` at `0x140018e5f`
- `WIN32K!W32GetSessionState` at `0x140018f45`
- `WIN32K!W32GetSessionState` at `0x1400190b1`
- `WIN32K!W32GetSessionState` at `0x140019172`
- `WIN32K!W32GetSessionState` at `0x140019223`
- `WIN32K!W32GetSessionState` at `0x14001944b`
- `WIN32K!W32GetSessionState` at `0x140018d5f`
- `WIN32K!W32GetSessionState` at `0x140018e5f`
- `WIN32K!W32GetSessionState` at `0x140018f45`
- `WIN32K!W32GetSessionState` at `0x1400190b1`
- `WIN32K!W32GetSessionState` at `0x140019172`
- `WIN32K!W32GetSessionState` at `0x140019223`
- `WIN32K!W32GetSessionState` at `0x14001944b`

## pseudocode

```c
__int64 __fastcall GreSelectVisRgn(__int64 a1, HRGN a2, int a3)
{
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct Gre::Base::SESSION_GLOBALS *v10; // r15
  HSEMAPHORE v11; // r13
  DC *v12; // rcx
  unsigned int v13; // r12d
  struct _ENTRY *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 SessionState; // rax
  __int64 v26; // rax
  DC *v27; // rbx
  __int64 v28; // rsi
  volatile signed __int16 *v29; // rdi
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r11
  __int64 v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  int v38; // r9d
  LONG v39; // r8d
  int v40; // r10d
  LONG v41; // edx
  bool v42; // zf
  __int64 v43; // rax
  int v44; // ebx
  int v45; // edi
  volatile signed __int16 *v46; // rsi
  int v47; // r8d
  DC *v48; // rbx
  DC *v49; // rcx
  struct _ENTRY *v50; // rax
  DC *v51; // rbx
  __int64 v52; // rcx
  struct _GRETHREAD *v53; // rax
  __int64 v54; // rax
  _QWORD **v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 result; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  DC *v62; // rbx
  __int64 *v63; // rax
  int v64; // esi
  LONG v65; // ebx
  __int64 v66; // rax
  bool v67; // cc
  LONG v68; // r9d
  __int64 v69; // rax
  unsigned int sizeScan; // eax
  const struct BaseRustExports *v71; // rbx
  const struct REGION_CORE *v72; // rdi
  HSURF v73; // rdx
  volatile signed __int16 *v74; // [rsp+30h] [rbp-A9h] BYREF
  __int128 v75; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v76; // [rsp+48h] [rbp-91h]
  __int64 v77; // [rsp+58h] [rbp-81h]
  DC *v78; // [rsp+60h] [rbp-79h] BYREF
  int v79; // [rsp+68h] [rbp-71h]
  struct Gre::Base::SESSION_GLOBALS *v80; // [rsp+70h] [rbp-69h]
  __int64 v81; // [rsp+78h] [rbp-61h]
  __int128 v82; // [rsp+80h] [rbp-59h] BYREF
  __int128 v83; // [rsp+90h] [rbp-49h]
  unsigned __int64 v84; // [rsp+A0h] [rbp-39h] BYREF
  volatile signed __int16 *v85; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v86; // [rsp+B0h] [rbp-29h] BYREF
  _QWORD **v87; // [rsp+B8h] [rbp-21h]
  int v88; // [rsp+D8h] [rbp-1h]
  struct _RECTL v89; // [rsp+E0h] [rbp+7h] BYREF

  LODWORD(v84) = a3;
  v78 = 0;
  v79 = 0;
  v80 = *(struct Gre::Base::SESSION_GLOBALS **)(W32GetSessionState(a1) + 88);
  v81 = 0;
  v78 = 0;
  v79 = 0;
  v82 = 0;
  v83 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v7 = *CurrentThreadWin32Thread;
  else
    v7 = 0;
  v8 = (v7 + 8) & -(__int64)(v7 != 0);
  *(_QWORD *)&v83 = &v78;
  *((_QWORD *)&v83 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v8 )
  {
    v9 = *(_QWORD *)(((v7 + 8) & -(__int64)(v7 != 0)) + 0x58);
    if ( *(_QWORD *)(v9 + 8) != v8 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v82 = *(_QWORD *)(v8 + 88);
    *((_QWORD *)&v82 + 1) = v8 + 88;
    *(_QWORD *)(v9 + 8) = &v82;
    *(_QWORD *)(v8 + 88) = &v82;
  }
  else
  {
    *((_QWORD *)&v82 + 1) = &v82;
    *(_QWORD *)&v82 = &v82;
  }
  LOBYTE(v6) = 1;
  v78 = (DC *)HmgShareLock(v80, a1, v6, 1);
  if ( v78 )
  {
    v10 = v80;
    v11 = (HSEMAPHORE)(*(_QWORD *)v80 + 1248LL);
    GreAcquireSemaphoreInternal(v11);
    GrepAcquireLockValidate<11>();
    v12 = v78;
    v13 = 1;
    *((_DWORD *)v78 + 9) |= 0x10u;
    v14 = DC::PentryFromPobj(v12, v10);
    *((_BYTE *)v14 + 15) |= 4u;
    if ( !a2 )
    {
      DC::vReleaseVis(v78, v10);
      DC::bSetDefaultRegion(v78);
      goto LABEL_54;
    }
    PsGetCurrentProcessId();
    v16 = *(_QWORD **)(W32GetSessionState(v15) + 88);
    v74 = (volatile signed __int16 *)(*v16 + 1512LL);
    GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v17, v74);
    HANDLELOCK::HANDLELOCK(&v75, v16, a2, 1);
    if ( DWORD2(v75) )
    {
      v18 = v75;
      if ( *(_BYTE *)(v75 + 14) == 4
        && *(_WORD *)(v75 + 12) == WORD1(a2)
        && ((v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v76 + 8) + 96LL))(
                     *(_QWORD *)(v76 + 8),
                     *(unsigned int *)v75),
             GreGetCurrentThread(),
             !*(_WORD *)(v19 + 12))
         || *(struct _KTHREAD **)(v19 + 16) == KeGetCurrentThread()) )
      {
        v22 = *(_DWORD *)(v18 + 8) & 0xFFFFFFFE;
        if ( v22 && (unsigned int)HmgIncProcessHandleCount(0, v20, v21) )
        {
          HmgDecProcessHandleCount(v16, v22);
          HANDLELOCK::Pid((HANDLELOCK *)&v75, 0);
          *(_WORD *)(v19 + 14) &= ~0x10u;
        }
      }
      else
      {
        BYTE13(v75) = 1;
      }
      HANDLELOCK::vUnlock((HANDLELOCK *)&v75);
    }
    HANDLELOCK::~HANDLELOCK((HANDLELOCK *)&v75);
    SEMOBJ<20>::vUnlock(&v74);
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v85, a2, 0, 0);
    if ( !v85 )
      goto LABEL_65;
    v24 = *(_QWORD *)v78;
    SessionState = W32GetSessionState(v23);
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(SessionState + 88) + 8LL) + 16LL))(
            *(_QWORD *)(*(_QWORD *)(SessionState + 88) + 8LL),
            (unsigned __int16)v24 | ((unsigned int)v24 >> 8) & 0xFF0000);
    if ( v26
      && *(_BYTE *)(v26 + 14) == 1
      && *(_WORD *)(v26 + 12) == WORD1(v24)
      && (*(_DWORD *)(v26 + 8) & 0xFFFFFFFE) == 0x80000012
      || (v27 = v78, (*((_DWORD *)v78 + 9) & 0x100000) == 0)
      || (v28 = *((_QWORD *)v78 + 6)) == 0
      || (v29 = v85) == 0 )
    {
LABEL_40:
      v44 = v84;
      v45 = 1;
      if ( (_DWORD)v84 == 1 )
      {
        v46 = v85;
        if ( (unsigned int)RGNOBJAPI::bDeleteHandle((RGNOBJAPI *)&v85) )
        {
          v85 = 0;
          goto LABEL_43;
        }
        v13 = 0;
LABEL_71:
        if ( !v13 && v44 == 1 )
        {
LABEL_47:
          if ( !v88 )
            RGNOBJ::UpdateUserRgn((RGNOBJ *)&v85);
          if ( v85 )
            _InterlockedDecrement16(v85 + 6);
          v54 = v86;
          if ( *(__int64 **)(v86 + 8) != &v86 )
            goto LABEL_5;
          v55 = v87;
          if ( *v87 != &v86 )
            goto LABEL_5;
          *v87 = (_QWORD *)v86;
          *(_QWORD *)(v54 + 8) = v55;
LABEL_54:
          if ( v11 )
          {
            if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
              McTemplateK0pz_EtwWriteTransfer(
                (_DWORD)v55,
                (unsigned int)&LockRelease,
                v47,
                (_DWORD)v11,
                (__int64)L"VisRgnPublish");
            GrepReleaseLockValidate<11>();
            GreReleaseSemaphoreSharedInternal(v11);
          }
          if ( v78 )
          {
            v56 = W32GetSessionState(v55);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v56 + 88), v78);
            v78 = 0;
          }
          v57 = v82;
          if ( *(__int128 **)(v82 + 8) == &v82 )
          {
            v58 = *((_QWORD *)&v82 + 1);
            if ( **((__int128 ***)&v82 + 1) == &v82 )
            {
              **((_QWORD **)&v82 + 1) = v82;
              result = v13;
              *(_QWORD *)(v57 + 8) = v58;
              return result;
            }
          }
LABEL_5:
          __fastfail(3u);
        }
        if ( !v45 )
        {
LABEL_44:
          v51 = v78;
          GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v78 + 1112));
          *((_QWORD *)v78 + 142) = v46;
          *((_DWORD *)v46 + 18) = _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(W32GetSessionState(v52)
                                                                                              + 88)
                                                                                  + 4248LL));
          v53 = GreGetCurrentThreadCrossSessionCheck();
          if ( v53 )
            *(_QWORD *)v53 &= ~0x4000000000uLL;
          GrePushLock::ReleaseLock((DC *)((char *)v51 + 1112));
          goto LABEL_47;
        }
LABEL_43:
        v48 = v78;
        v49 = v78;
        *((_DWORD *)v78 + 9) |= 0x10u;
        v50 = DC::PentryFromPobj(v49, v10);
        *((_BYTE *)v50 + 15) |= 4u;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v48 + 1112));
        v74 = (volatile signed __int16 *)*((_QWORD *)v48 + 142);
        *(_QWORD *)&v89.left = v48;
        LOBYTE(v89.right) = 1;
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v74);
        *((_QWORD *)v48 + 142) = *((_QWORD *)v10 + 533);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v89);
        goto LABEL_44;
      }
      if ( (_DWORD)v84 != 2 )
      {
        if ( (_DWORD)v84 != 4 )
        {
          v46 = 0;
          goto LABEL_43;
        }
        v62 = v78;
        GreInnermostPushLock::AcquireLockExclusive((DC *)((char *)v78 + 1112));
        *(_QWORD *)&v89.left = v62;
        LOBYTE(v89.right) = 1;
        v46 = (volatile signed __int16 *)*((_QWORD *)v78 + 142);
        if ( v46 )
        {
          if ( v46 != *((volatile signed __int16 **)v10 + 533) )
          {
            v74 = (volatile signed __int16 *)*((_QWORD *)v78 + 142);
            RGNOBJAPI::bSwap((__int64 **)&v85, (__int64 **)&v74);
            v46 = v74;
            v45 = 0;
LABEL_80:
            _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(&v89);
            v44 = v84;
            goto LABEL_71;
          }
        }
        else
        {
          v46 = (volatile signed __int16 *)*((_QWORD *)v10 + 533);
        }
        v13 = 0;
        goto LABEL_80;
      }
      sizeScan = REGION_CORE::get_sizeScan((REGION_CORE *)(v85 + 12));
      v74 = 0;
      RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v74, sizeScan);
      v46 = v74;
      if ( v74 )
      {
        if ( WPP_MAIN_CB.Dpc.ProcessorHistory )
        {
          v71 = *(const struct BaseRustExports **)WPP_MAIN_CB.Dpc.ProcessorHistory;
          v72 = (const struct REGION_CORE *)((unsigned __int64)(v74 + 12) & -(__int64)(v74 != 0));
          (*(void (__fastcall **)(const struct REGION_CORE *, unsigned __int64, __int64))(*(_QWORD *)WPP_MAIN_CB.Dpc.ProcessorHistory
                                                                                        + 48LL))(
            v72,
            (unsigned __int64)(v85 + 12) & -(__int64)(v85 != 0),
            -(__int64)v85);
          RgnCaptureLiveMemoryDumpOnZeroSizedScan(v71, v72);
        }
        else
        {
          v84 = (unsigned __int64)(v74 + 12) & -(__int64)(v74 != 0);
          v74 = (volatile signed __int16 *)((unsigned __int64)(v85 + 12) & -(__int64)(v85 != 0));
          RGNCOREOBJ::vCopy((RGNCOREOBJ *)&v84, (const struct RGNCOREOBJ *)&v74);
        }
        goto LABEL_43;
      }
LABEL_65:
      v46 = (volatile signed __int16 *)*((_QWORD *)v10 + 533);
      goto LABEL_43;
    }
    v75 = 0;
    v76 = 0;
    v30 = (__int64 *)PsGetCurrentThreadWin32Thread();
    if ( v30 )
      v31 = *v30;
    else
      v31 = 0;
    v32 = (v31 + 8) & -(__int64)(v31 != 0);
    *(_QWORD *)&v76 = &v75;
    *((_QWORD *)&v76 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v32 )
    {
      v33 = *(_QWORD *)(((v31 + 8) & -(__int64)(v31 != 0)) + 0x58);
      if ( *(_QWORD *)(v33 + 8) != v32 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v75 = *(_QWORD *)(v32 + 88);
      *((_QWORD *)&v75 + 1) = v32 + 88;
      *(_QWORD *)(v33 + 8) = &v75;
      *(_QWORD *)(v32 + 88) = &v75;
    }
    else
    {
      *((_QWORD *)&v75 + 1) = &v75;
      *(_QWORD *)&v75 = &v75;
    }
    v42 = (*((_DWORD *)v27 + 9) & 0x40000) == 0;
    v34 = 0;
    v77 = 0;
    if ( v42 )
    {
      v35 = *((_QWORD *)v27 + 62);
    }
    else
    {
      v73 = (HSURF)*((_QWORD *)v27 + 268);
      if ( v73 )
      {
        SURFREF::vLock((SURFREF *)&v75, v73);
        v34 = v77;
        v35 = v77;
        v36 = v77;
LABEL_31:
        if ( !v35 )
        {
          v42 = v36 == 0;
          goto LABEL_37;
        }
        if ( (*(_DWORD *)(v28 + 40) & 0x20000) != 0 && *(int *)(v35 + 160) < 0
          || (v37 = *((_DWORD *)v27 + 9), (v37 & 0x1000) != 0) && (v37 & 0x4000) == 0
          || (v38 = *((_DWORD *)v29 + 13), v39 = *((_DWORD *)v29 + 15), v38 == v39)
          || (v40 = *((_DWORD *)v29 + 14), v41 = *((_DWORD *)v29 + 16), v40 == v41)
          || v38 == 0x7FFFFFFF && v41 == 0x80000000 && v40 == 0x7FFFFFFF && v39 == 0x80000000 )
        {
LABEL_36:
          v42 = v34 == 0;
LABEL_37:
          if ( !v42 )
          {
            v43 = W32GetSessionState(v35);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v43 + 88), v77);
          }
          PopThreadGuardedObject(&v75);
          goto LABEL_40;
        }
        v63 = (__int64 *)(v35 + 716);
        v64 = *((_DWORD *)v29 + 13);
        v65 = *((_DWORD *)v29 + 14);
        if ( (*(_DWORD *)(v35 + 164) & 0x800) == 0 )
          v63 = (__int64 *)(v35 + 56);
        v66 = *v63;
        if ( v38 >= v39 )
        {
          if ( v38 > v39 )
          {
            v64 = *((_DWORD *)v29 + 15);
            v39 = *((_DWORD *)v29 + 13);
          }
          v67 = v40 <= v41;
        }
        else
        {
          v67 = v40 <= v41;
          if ( v40 < v41 )
          {
            if ( v38 >= 0 && (int)v66 >= v39 && v40 >= 0 && SHIDWORD(v66) >= v41 )
              goto LABEL_36;
LABEL_96:
            v68 = 0;
            if ( v64 >= 0 )
              v68 = v64;
            if ( v65 < 0 )
              v65 = 0;
            if ( (int)v66 < v39 )
              v39 = v66;
            if ( SHIDWORD(v66) < v41 )
              v41 = HIDWORD(v66);
            if ( v39 < v68 )
            {
              v68 = v39;
            }
            else if ( v41 < v65 )
            {
              v65 = v41;
            }
            v89.left = v68;
            v89.top = v65;
            v89.right = v39;
            v89.bottom = v41;
            if ( v34 )
            {
              v69 = W32GetSessionState(v35);
              HmgDecrementShareReferenceCount(*(_QWORD *)(v69 + 88), v77);
            }
            PopThreadGuardedObject(&v75);
            RGNOBJ::vSet((RGNOBJ *)&v85, &v89);
            goto LABEL_40;
          }
        }
        if ( !v67 )
        {
          v65 = *((_DWORD *)v29 + 16);
          v41 = *((_DWORD *)v29 + 14);
        }
        goto LABEL_96;
      }
      v35 = *(_QWORD *)(v28 + 2544);
    }
    v36 = 0;
    goto LABEL_31;
  }
  v60 = v82;
  if ( *(__int128 **)(v82 + 8) != &v82 )
    goto LABEL_5;
  v61 = *((_QWORD *)&v82 + 1);
  if ( **((__int128 ***)&v82 + 1) != &v82 )
    goto LABEL_5;
  **((_QWORD **)&v82 + 1) = v82;
  *(_QWORD *)(v60 + 8) = v61;
  return 0;
}

```

## disassembly

```asm
0x140018d20  mov     [rsp-8+arg_10], rbx
0x140018d25  push    rbp
0x140018d26  push    rsi
0x140018d27  push    rdi
0x140018d28  push    r12
0x140018d2a  push    r13
0x140018d2c  push    r14
0x140018d2e  push    r15
0x140018d30  lea     rbp, [rsp-27h]
0x140018d35  sub     rsp, 100h
0x140018d3c  mov     rax, cs:__security_cookie
0x140018d43  xor     rax, rsp
0x140018d46  mov     [rbp+57h+var_40], rax
0x140018d4a  xor     r14d, r14d
0x140018d4d  mov     dword ptr [rbp+57h+var_90], r8d
0x140018d51  mov     [rbp+57h+var_D0], r14
0x140018d55  mov     rsi, rdx
0x140018d58  mov     [rbp+57h+var_C8], r14d
0x140018d5c  mov     rbx, rcx
0x140018d5f  call    cs:__imp_W32GetSessionState
0x140018d66  nop     dword ptr [rax+rax+00h]
0x140018d6b  xorps   xmm0, xmm0
0x140018d6e  mov     rcx, [rax+58h]
0x140018d72  mov     [rbp+57h+var_C0], rcx
0x140018d76  mov     [rbp+57h+var_B8], r14
0x140018d7a  mov     [rbp+57h+var_D0], r14
0x140018d7e  mov     [rbp+57h+var_C8], r14d
0x140018d82  movups  [rbp+57h+var_B0], xmm0
0x140018d86  movups  [rbp+57h+var_A0], xmm0
0x140018d8a  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140018d91  nop     dword ptr [rax+rax+00h]
0x140018d96  test    rax, rax
0x140018d99  jz      loc_140019597
0x140018d9f  mov     rcx, [rax]
0x140018da2  lea     rax, [rcx+8]
0x140018da6  neg     rcx
0x140018da9  sbb     rdx, rdx
0x140018dac  and     rdx, rax
0x140018daf  lea     rax, [rbp+57h+var_D0]
0x140018db3  mov     qword ptr [rbp+57h+var_A0], rax
0x140018db7  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x140018dbe  mov     qword ptr [rbp+57h+var_A0+8], rax
0x140018dc2  jz      loc_1400195C7
0x140018dc8  lea     rax, [rdx+58h]
0x140018dcc  mov     rcx, [rax]
0x140018dcf  cmp     [rcx+8], rax
0x140018dd3  jz      short loc_140018DDC
0x140018dd5  mov     ecx, 3
0x140018dda  int     29h; Win8: RtlFailFast(ecx)
0x140018ddc  mov     qword ptr [rbp+57h+var_B0], rcx
0x140018de0  lea     rdx, [rbp+57h+var_B0]
0x140018de4  mov     qword ptr [rbp+57h+var_B0+8], rax
0x140018de8  mov     [rcx+8], rdx
0x140018dec  lea     rcx, [rbp+57h+var_B0]
0x140018df0  mov     [rax], rcx
0x140018df3  mov     rcx, [rbp+57h+var_C0]
0x140018df7  mov     r9d, 1
0x140018dfd  mov     r8b, r9b
0x140018e00  mov     rdx, rbx
0x140018e03  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140018e08  mov     [rbp+57h+var_D0], rax
0x140018e0c  test    rax, rax
0x140018e0f  jz      loc_140019295
0x140018e15  mov     r15, [rbp+57h+var_C0]
0x140018e19  mov     r13, [r15]
0x140018e1c  add     r13, 4E0h
0x140018e23  mov     rcx, r13; Resource
0x140018e26  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x140018e2b  call    ??$GrepAcquireLockValidate@$0L@@@YAXXZ; GrepAcquireLockValidate<11>(void)
0x140018e30  mov     rcx, [rbp+57h+var_D0]; this
0x140018e34  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x140018e37  mov     r12d, 1
0x140018e3d  or      dword ptr [rcx+24h], 10h
0x140018e41  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140018e46  or      byte ptr [rax+0Fh], 4
0x140018e4a  test    rsi, rsi
0x140018e4d  jz      loc_1400194A7
0x140018e53  call    cs:__imp_PsGetCurrentProcessId
0x140018e5a  nop     dword ptr [rax+rax+00h]
0x140018e5f  call    cs:__imp_W32GetSessionState
0x140018e66  nop     dword ptr [rax+rax+00h]
0x140018e6b  mov     r14, [rax+58h]
0x140018e6f  mov     rdx, [r14]
0x140018e72  add     rdx, 5E8h
0x140018e79  mov     [rsp+130h+var_100], rdx
0x140018e7e  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140018e83  mov     r9d, r12d
0x140018e86  lea     rcx, [rsp+130h+var_F8]
0x140018e8b  mov     r8, rsi
0x140018e8e  mov     rdx, r14
0x140018e91  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x140018e96  cmp     dword ptr [rsp+130h+var_F8+8], 0
0x140018e9b  jz      short loc_140018F0B
0x140018e9d  mov     rbx, qword ptr [rsp+130h+var_F8]
0x140018ea2  cmp     byte ptr [rbx+0Eh], 4
0x140018ea6  jnz     loc_1400192CF
0x140018eac  movzx   eax, byte ptr [rbx+0Ch]
0x140018eb0  movzx   ecx, byte ptr [rbx+0Dh]
0x140018eb4  shl     cx, 8
0x140018eb8  or      cx, ax
0x140018ebb  mov     eax, esi
0x140018ebd  shr     eax, 10h
0x140018ec0  cmp     cx, ax
0x140018ec3  jnz     loc_1400192CF
0x140018ec9  mov     rax, qword ptr [rsp+130h+var_E8]
0x140018ece  mov     edx, [rbx]
0x140018ed0  mov     rcx, [rax+8]
0x140018ed4  mov     rax, [rcx]
0x140018ed7  mov     rax, [rax+60h]
0x140018edb  call    _guard_dispatch_icall
0x140018ee0  mov     rdi, rax
0x140018ee3  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140018ee8  movzx   ecx, word ptr [rdi+0Ch]
0x140018eec  test    cx, cx
0x140018eef  jnz     loc_14001960F
0x140018ef5  mov     ebx, [rbx+8]
0x140018ef8  and     ebx, 0FFFFFFFEh
0x140018efb  jnz     loc_1400192D9
0x140018f01  lea     rcx, [rsp+130h+var_F8]; this
0x140018f06  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140018f0b  lea     rcx, [rsp+130h+var_F8]; this
0x140018f10  call    ??1HANDLELOCK@@QEAA@XZ; HANDLELOCK::~HANDLELOCK(void)
0x140018f15  lea     rcx, [rsp+130h+var_100]
0x140018f1a  call    ?vUnlock@?$SEMOBJ@$0BE@@@QEAAXXZ; SEMOBJ<20>::vUnlock(void)
0x140018f1f  xor     r9d, r9d; int
0x140018f22  lea     rcx, [rbp+57h+var_88]; this
0x140018f26  xor     r8d, r8d; int
0x140018f29  mov     rdx, rsi; HRGN
0x140018f2c  call    ??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140018f31  xor     r14d, r14d
0x140018f34  cmp     [rbp+57h+var_88], r14
0x140018f38  jz      loc_1400192C3
0x140018f3e  mov     rax, [rbp+57h+var_D0]
0x140018f42  mov     rbx, [rax]
0x140018f45  call    cs:__imp_W32GetSessionState
0x140018f4c  nop     dword ptr [rax+rax+00h]
0x140018f51  mov     edx, ebx
0x140018f53  shr     edx, 8
0x140018f56  and     edx, 0FF0000h
0x140018f5c  mov     rcx, [rax+58h]
0x140018f60  movzx   eax, bx
0x140018f63  or      edx, eax
0x140018f65  mov     rcx, [rcx+8]
0x140018f69  mov     r8, [rcx]
0x140018f6c  mov     rax, [r8+10h]
0x140018f70  call    _guard_dispatch_icall
0x140018f75  test    rax, rax
0x140018f78  jz      short loc_140018FA8
0x140018f7a  cmp     [rax+0Eh], r12b
0x140018f7e  jnz     short loc_140018FA8
0x140018f80  movzx   edx, byte ptr [rax+0Dh]
0x140018f84  movzx   ecx, byte ptr [rax+0Ch]
0x140018f88  shl     dx, 8
0x140018f8c  or      dx, cx
0x140018f8f  shr     ebx, 10h
0x140018f92  cmp     dx, bx
0x140018f95  jnz     short loc_140018FA8
0x140018f97  mov     eax, [rax+8]
0x140018f9a  and     eax, 0FFFFFFFEh
0x140018f9d  cmp     eax, 80000012h
0x140018fa2  jz      loc_1400190D5
0x140018fa8  mov     rbx, [rbp+57h+var_D0]
0x140018fac  test    dword ptr [rbx+24h], 100000h
0x140018fb3  jz      loc_1400190D5
0x140018fb9  mov     rsi, [rbx+30h]
0x140018fbd  test    rsi, rsi
0x140018fc0  jz      loc_1400190D5
0x140018fc6  mov     rdi, [rbp+57h+var_88]
0x140018fca  test    rdi, rdi
0x140018fcd  jz      loc_1400190D5
0x140018fd3  xorps   xmm0, xmm0
0x140018fd6  movups  [rsp+130h+var_F8], xmm0
0x140018fdb  movups  [rsp+130h+var_E8], xmm0
0x140018fe0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140018fe7  nop     dword ptr [rax+rax+00h]
0x140018fec  test    rax, rax
0x140018fef  jz      loc_14001959F
0x140018ff5  mov     rcx, [rax]
0x140018ff8  lea     rax, [rcx+8]
0x140018ffc  neg     rcx
0x140018fff  sbb     rdx, rdx
0x140019002  and     rdx, rax
0x140019005  lea     rax, [rsp+130h+var_F8]
0x14001900a  mov     qword ptr [rsp+130h+var_E8], rax
0x14001900f  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x140019016  mov     qword ptr [rsp+130h+var_E8+8], rax
0x14001901b  jz      loc_1400195F6
0x140019021  lea     rax, [rdx+58h]
0x140019025  mov     rcx, [rax]
0x140019028  cmp     [rcx+8], rax
0x14001902c  jnz     loc_140018DD5
0x140019032  mov     qword ptr [rsp+130h+var_F8], rcx
0x140019037  lea     rdx, [rsp+130h+var_F8]
0x14001903c  mov     qword ptr [rsp+130h+var_F8+8], rax
0x140019041  mov     [rcx+8], rdx
0x140019045  lea     rcx, [rsp+130h+var_F8]
0x14001904a  mov     [rax], rcx
0x14001904d  test    dword ptr [rbx+24h], 40000h
0x140019054  mov     r11, r14
0x140019057  mov     [rsp+130h+var_D8], r14
0x14001905c  jnz     loc_1400195AF
0x140019062  mov     rcx, [rbx+1F0h]
0x140019069  mov     rax, r14
0x14001906c  test    rcx, rcx
0x14001906f  jz      loc_14001930C
0x140019075  test    dword ptr [rsi+28h], 20000h
0x14001907c  jnz     loc_140019481
0x140019082  mov     eax, [rbx+24h]
0x140019085  bt      eax, 0Ch
0x140019089  jb      loc_140019627
0x14001908f  mov     r9d, [rdi+34h]
0x140019093  mov     r8d, [rdi+3Ch]
0x140019097  cmp     r9d, r8d
0x14001909a  jz      short loc_1400190AC
0x14001909c  mov     r10d, [rdi+38h]
0x1400190a0  mov     edx, [rdi+40h]
0x1400190a3  cmp     r10d, edx
0x1400190a6  jnz     loc_1400193A8
0x1400190ac  test    r11, r11
0x1400190af  jz      short loc_1400190CB
0x1400190b1  call    cs:__imp_W32GetSessionState
0x1400190b8  nop     dword ptr [rax+rax+00h]
0x1400190bd  mov     rdx, [rsp+130h+var_D8]
0x1400190c2  mov     rcx, [rax+58h]
0x1400190c6  call    HmgDecrementShareReferenceCount
0x1400190cb  lea     rcx, [rsp+130h+var_F8]
0x1400190d0  call    PopThreadGuardedObject
0x1400190d5  mov     ebx, dword ptr [rbp+57h+var_90]
0x1400190d8  mov     edi, r12d
0x1400190db  mov     ecx, ebx
0x1400190dd  sub     ecx, r12d
0x1400190e0  jnz     loc_140019332
0x1400190e6  mov     rsi, [rbp+57h+var_88]
0x1400190ea  lea     rcx, [rbp+57h+var_88]; this
0x1400190ee  call    ?bDeleteHandle@RGNOBJAPI@@QEAAHXZ; RGNOBJAPI::bDeleteHandle(void)
0x1400190f3  test    eax, eax
0x1400190f5  jz      loc_140019314
0x1400190fb  mov     [rbp+57h+var_88], r14
0x1400190ff  mov     rbx, [rbp+57h+var_D0]
0x140019103  mov     rdx, r15; struct Gre::Base::SESSION_GLOBALS *
0x140019106  mov     rcx, rbx; this
0x140019109  or      dword ptr [rbx+24h], 10h
0x14001910d  call    ?PentryFromPobj@DC@@QEAAPEAU_ENTRY@@AEAUSESSION_GLOBALS@Base@Gre@@@Z; DC::PentryFromPobj(Gre::Base::SESSION_GLOBALS &)
0x140019112  lea     rcx, [rbx+458h]; this
0x140019119  or      byte ptr [rax+0Fh], 4
0x14001911d  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140019122  mov     rax, [rbx+470h]
0x140019129  lea     rcx, [rsp+130h+var_100]; this
0x14001912e  mov     [rsp+130h+var_100], rax
0x140019133  mov     qword ptr [rbp+57h+var_50.left], rbx
0x140019137  mov     byte ptr [rbp+57h+var_50.right], 1
0x14001913b  call    ?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140019140  mov     rax, [r15+10A8h]
0x140019147  lea     rcx, [rbp+57h+var_50]
0x14001914b  mov     [rbx+470h], rax
0x140019152  call    ?reset@?$lambda_call@V_lambda_1_@?1??AcquireDcVisRgnExclusive@DC@@QEAA@XZ@@details@wil@@QEAAXXZ; wil::details::lambda_call<`DC::AcquireDcVisRgnExclusive(void)'::`2'::_lambda_1_>::reset(void)
0x140019157  mov     rbx, [rbp+57h+var_D0]
0x14001915b  lea     rcx, [rbx+458h]; this
0x140019162  call    ?AcquireLockExclusive@GreInnermostPushLock@@QEAAXXZ; GreInnermostPushLock::AcquireLockExclusive(void)
0x140019167  mov     rax, [rbp+57h+var_D0]
0x14001916b  mov     [rax+470h], rsi
0x140019172  call    cs:__imp_W32GetSessionState
0x140019179  nop     dword ptr [rax+rax+00h]
0x14001917e  mov     rcx, [rax+58h]
0x140019182  mov     eax, 1
0x140019187  lock xadd [rcx+1098h], eax
0x14001918f  inc     eax
0x140019191  mov     [rsi+48h], eax
0x140019194  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x140019199  test    rax, rax
0x14001919c  jz      short loc_1400191AB
0x14001919e  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x1400191a8  and     [rax], rcx
0x1400191ab  lea     rcx, [rbx+458h]; this
0x1400191b2  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x1400191b7  cmp     [rbp+57h+var_58], r14d
0x1400191bb  jnz     short loc_1400191C6
0x1400191bd  lea     rcx, [rbp+57h+var_88]; this
0x1400191c1  call    ?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x1400191c6  mov     rax, [rbp+57h+var_88]
0x1400191ca  test    rax, rax
0x1400191cd  jz      short loc_1400191D4
0x1400191cf  lock dec word ptr [rax+0Ch]
0x1400191d4  mov     rax, [rbp+57h+var_80]
0x1400191d8  lea     rcx, [rbp+57h+var_80]
0x1400191dc  cmp     [rax+8], rcx
0x1400191e0  jnz     loc_140018DD5
0x1400191e6  mov     rcx, [rbp+57h+var_78]
0x1400191ea  lea     rdx, [rbp+57h+var_80]
0x1400191ee  cmp     [rcx], rdx
0x1400191f1  jnz     loc_140018DD5
0x1400191f7  mov     [rcx], rax
0x1400191fa  mov     [rax+8], rcx
0x1400191fe  test    r13, r13
0x140019201  jz      short loc_14001921D
0x140019203  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, r14d
0x14001920a  jnz     loc_140019636
0x140019210  call    ??$GrepReleaseLockValidate@$0L@@@YAXXZ; GrepReleaseLockValidate<11>(void)
0x140019215  mov     rcx, r13; HSEMAPHORE
0x140019218  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
  ... truncated ...
```
