# ExecuteGlobal(CHitObj *,CIntrinsicObjects const &,ActiveEngineInfo *)

- ea: `0x180043a54`
- end: `0x180044348`
- name: `?ExecuteGlobal@@YAJPEAVCHitObj@@AEBVCIntrinsicObjects@@PEAUActiveEngineInfo@@@Z`
- size: `2292`
- prototype: `__int64 __fastcall(struct CHitObj *, const struct CIntrinsicObjects *, struct ActiveEngineInfo *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000faa0`

## callees

- `0x1800099a0`
- `0x180009f90`
- `0x18000f080`
- `0x180019e7c`
- `0x18004348c`
- `0x1800437dc`
- `0x180043894`
- `0x180043974`
- `0x180043a54`
- `0x180044350`
- `0x1800444b8`
- `0x180044784`
- `0x180044870`
- `0x180044930`
- `0x180044b70`
- `0x180044c30`
- `0x180044d1c`
- `0x180044ddc`
- `0x18004501c`
- `0x18004746c`
- `0x18005b1e0`
- `0x18005e020`
- `0x180064010`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18004413a`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18004413a`
- `ADVAPI32!RevertToSelf` at `0x180044213`
- `ADVAPI32!RevertToSelf` at `0x180044213`
- `comsvcs!CoEnterServiceDomain` at `0x180043bc9`
- `comsvcs!CoEnterServiceDomain` at `0x180043bc9`
- `comsvcs!CoLeaveServiceDomain` at `0x1800442e7`
- `comsvcs!CoLeaveServiceDomain` at `0x1800442e7`
- `KERNEL32!HeapAlloc` at `0x180043b8e`
- `KERNEL32!HeapAlloc` at `0x180043b8e`
- `KERNEL32!GetACP` at `0x180043ac7`
- `KERNEL32!GetACP` at `0x180043b21`
- `KERNEL32!GetACP` at `0x180043ac7`
- `KERNEL32!GetACP` at `0x180043b21`

## pseudocode

```c
__int64 __fastcall ExecuteGlobal(struct CHitObj *a1, struct CScriptingNamespace **a2, struct ActiveEngineInfo *a3)
{
  int v3; // r14d
  struct CScriptingNamespace **v5; // r13
  struct CHitObj *v6; // rbx
  __int64 v7; // rax
  int v8; // r12d
  signed int v9; // ebp
  void (__fastcall *v10)(struct CHitObj *); // rax
  const unsigned __int16 *v11; // rcx
  signed int Engines; // edi
  CTemplate *v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rsi
  __int64 v16; // rcx
  IUnknown *v17; // rax
  CASPObjectContext *v18; // rax
  IUnknown *v19; // rcx
  int v20; // r13d
  unsigned int v21; // r8d
  int v22; // r8d
  int v23; // eax
  int v24; // ecx
  struct CAppln *v25; // rdx
  __int64 v26; // rsi
  const struct _GUID *v27; // rdx
  int v28; // eax
  const struct _GUID *v29; // rdx
  const struct _GUID *v30; // rdx
  const struct _GUID *v31; // rdx
  const struct _GUID *v32; // rdx
  unsigned __int64 v33; // r14
  __int64 v34; // rcx
  __int64 v35; // rcx
  const struct _GUID *v36; // rdx
  int v37; // eax
  const struct _GUID *v38; // rdx
  const struct _GUID *v39; // rdx
  const struct _GUID *v40; // rdx
  const struct _GUID *v41; // rdx
  int v42; // edi
  __int64 v43; // rcx
  int v44; // eax
  int v45; // esi
  __int64 v46; // rcx
  int v47; // eax
  int v48; // esi
  __int64 v49; // rcx
  int v50; // eax
  __int64 v51; // rax
  BOOL v52; // r14d
  int v53; // ebp
  __int64 v54; // rax
  DWORD v55; // ecx
  __int64 v56; // rcx
  int v57; // esi
  signed int v58; // eax
  int v59; // esi
  signed int v60; // eax
  unsigned int v61; // edx
  CHitObj *v62; // rcx
  int v63; // eax
  __int64 v64; // rax
  UINT v66; // [rsp+30h] [rbp-78h]
  CTemplate *v67; // [rsp+38h] [rbp-70h] BYREF
  int v68; // [rsp+40h] [rbp-68h]
  int v69; // [rsp+44h] [rbp-64h] BYREF
  UINT ACP; // [rsp+48h] [rbp-60h]
  int v71; // [rsp+4Ch] [rbp-5Ch]
  int v72; // [rsp+50h] [rbp-58h]
  CASPObjectContext *v73; // [rsp+58h] [rbp-50h]
  __int64 v74; // [rsp+60h] [rbp-48h]
  int v77; // [rsp+C8h] [rbp+20h]

  v3 = 0;
  v67 = 0;
  v5 = a2;
  v69 = 0;
  v6 = a1;
  v7 = *(_QWORD *)a1;
  v8 = 0;
  LOBYTE(v68) = 0;
  v9 = 0;
  v77 = 0;
  v71 = 0;
  v10 = *(void (__fastcall **)(struct CHitObj *))(v7 + 8);
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v10(a1);
  ACP = *((_DWORD *)v6 + 41);
  if ( !ACP )
    ACP = GetACP();
  if ( (*((_BYTE *)v6 + 8) & 2) != 0 )
    v11 = *(const unsigned __int16 **)(*((_QWORD *)v6 + 3) + 128LL);
  else
    v11 = 0;
  Engines = LoadTemplate(v11, (CIsapiReqInfo **)v6, &v67, (const struct CIntrinsicObjects *)v5, 1, &v69);
  if ( Engines < 0 )
  {
    v13 = v67;
    goto LABEL_150;
  }
  v66 = *((_DWORD *)v6 + 41);
  if ( !v66 )
    v66 = GetACP();
  v13 = v67;
  if ( (*((_BYTE *)v6 + 8) & 0x10) != 0 )
  {
    v14 = *((_QWORD *)v67 + 54);
    if ( v14 )
    {
      v15 = *((_QWORD *)v6 + 3);
      v16 = *(_QWORD *)(v15 + 336);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      *(_QWORD *)(v15 + 336) = v14;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v13 = v67;
    }
  }
  if ( !*((_DWORD *)v13 + 99) )
    goto LABEL_18;
  v17 = (IUnknown *)HeapAlloc(g_hDenaliHeap, 0, 0x38u);
  if ( !v17 )
  {
    v73 = 0;
    goto LABEL_22;
  }
  v18 = CASPObjectContext::CASPObjectContext(v17);
  v73 = v18;
  if ( !v18 )
  {
LABEL_22:
    Engines = -2147024882;
    goto LABEL_149;
  }
  v74 = *((_QWORD *)v6 + 7);
  *((_QWORD *)v6 + 7) = v18;
  v73 = v18;
LABEL_18:
  v19 = (IUnknown *)*((_QWORD *)v13 + 60);
  if ( !v19 )
    goto LABEL_23;
  Engines = CoEnterServiceDomain(v19);
  if ( Engines >= 0 )
  {
    v72 = 1;
LABEL_23:
    v20 = 0;
    if ( (unsigned int)CHitObj::FIsBrowserRequest(v6) )
    {
      v3 = (v21 >> 4) & 1;
      if ( v3 )
      {
        v77 = 1;
        *((_DWORD *)v6 + 2) = v21 | 0x200;
      }
    }
    else
    {
      v22 = v21 & 0xF0000;
      if ( v22 == 0x20000 )
      {
        v20 = 1;
      }
      else if ( v22 == 0x40000 )
      {
        v8 = 1;
      }
    }
    if ( (*(_BYTE *)(*((_QWORD *)v6 + 3) + 72LL) & 0x20) != 0 )
    {
      v23 = CTemplate::NotifyDebuggerOnPageEvent(v13, 1);
      v24 = (unsigned __int8)v68;
      if ( v23 >= 0 )
        v24 = 1;
      v68 = v24;
    }
    Engines = AllocAndLoadEngines(v6, v13, a3, a2[4], 1);
    if ( Engines < 0 )
      goto LABEL_147;
    if ( !v69 )
    {
      v25 = (struct CAppln *)*((_QWORD *)v6 + 3);
      if ( (*((_BYTE *)v25 + 72) & 0x20) != 0 )
        CTemplate::AttachTo(v13, v25);
    }
    if ( !*((_WORD *)v13 + 88) )
      goto LABEL_147;
    v26 = *((_QWORD *)v6 + 8);
    if ( v3 )
    {
      *((_DWORD *)v6 + 2) &= 0xF1FFFFFF;
      *((_DWORD *)v6 + 2) |= 0x1000000u;
      if ( v26
        && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                           *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                           4u) )
      {
        AspReqEvents::ASP_START_APPLICATION_ONSTART::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v27);
      }
      Engines = -2147467259;
      if ( *((int *)a3 + 1) <= 0 )
      {
LABEL_49:
        if ( (*(_BYTE *)(*((_QWORD *)a2[1] + 7) + 280LL) & 1) == 0 )
        {
          if ( v26 )
          {
            if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                                 2u) )
              AspReqEvents::ASP_APPLICATION_ONSTART_ERROR::RaiseEvent(
                *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                v29,
                Engines);
            if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                                 4u) )
              AspReqEvents::ASP_END_APPLICATION_ONSTART::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v30);
          }
LABEL_55:
          v13 = v67;
          goto LABEL_147;
        }
      }
      else
      {
        do
        {
          v28 = CallScriptFunctionOfEngine(a3, v9, L"Application_OnStart", 0);
          Engines = v28;
          if ( v28 >= 0 )
            break;
          if ( v28 != -2147352570 && v28 != -2147352573 )
            goto LABEL_49;
          ++v9;
        }
        while ( v9 < *((_DWORD *)a3 + 1) );
      }
      v9 = 0;
      if ( v77 )
      {
        *((_DWORD *)v6 + 2) &= ~0x200u;
        v77 = 0;
      }
      v71 = 1;
      if ( v26 )
      {
        if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                             *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                             4u) )
          AspReqEvents::ASP_APPLICATION_ONSTART_SUCCESS::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v31);
        if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                             *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                             4u) )
          AspReqEvents::ASP_END_APPLICATION_ONSTART::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v32);
      }
      Engines = 0;
    }
    if ( (*((_BYTE *)v6 + 8) & 4) != 0 )
    {
      if ( v3 )
      {
        if ( *((int *)a3 + 1) > 0 )
        {
          do
          {
            v33 = (unsigned __int64)(unsigned __int16)v9 << 6;
            v34 = *(_QWORD *)(*((_QWORD *)a3 + 1) + v33 + 16);
            Engines = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, _QWORD))(*(_QWORD *)v34 + 16LL))(
                        v34,
                        L"Response",
                        0);
            if ( Engines < 0 )
              goto LABEL_146;
            v35 = *(_QWORD *)(v33 + *((_QWORD *)a3 + 1) + 16);
            Engines = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, _QWORD))(*(_QWORD *)v35 + 16LL))(
                        v35,
                        L"Request",
                        0);
            if ( Engines < 0 )
              goto LABEL_55;
            LOWORD(v9) = v9 + 1;
          }
          while ( (unsigned __int16)v9 < *((int *)a3 + 1) );
        }
        v9 = 0;
      }
      *((_DWORD *)v6 + 2) &= 0xF2FFFFFF;
      *((_DWORD *)v6 + 2) |= 0x2000000u;
      if ( v26
        && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                           *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                           4u) )
      {
        AspReqEvents::ASP_START_SESSION_ONSTART::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v36);
      }
      Engines = -2147467259;
      if ( *((int *)a3 + 1) <= 0 )
      {
LABEL_80:
        v5 = a2;
        if ( (*(_BYTE *)(*((_QWORD *)a2[1] + 7) + 280LL) & 1) == 0 )
        {
          *(_DWORD *)(*((_QWORD *)v6 + 2) + 32LL) |= 4u;
          if ( v26 )
          {
            if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                                 2u) )
              AspReqEvents::ASP_SESSION_ONSTART_ERROR::RaiseEvent(
                *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                v38,
                Engines);
            if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                                 *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                                 4u) )
              AspReqEvents::ASP_END_SESSION_ONSTART::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v39);
          }
LABEL_86:
          v13 = v67;
LABEL_148:
          v8 = v77;
          goto LABEL_149;
        }
      }
      else
      {
        while ( 1 )
        {
          v37 = CallScriptFunctionOfEngine(a3, v9, L"Session_OnStart", 0);
          Engines = v37;
          if ( v37 >= 0 )
            break;
          if ( v37 != -2147352570 && v37 != -2147352573 )
            goto LABEL_80;
          if ( ++v9 >= *((_DWORD *)a3 + 1) )
            goto LABEL_92;
        }
        *(_DWORD *)(*((_QWORD *)v6 + 2) + 32LL) |= 8u;
        if ( v26 )
        {
          if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                               *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                               4u) )
            AspReqEvents::ASP_SESSION_ONSTART_SUCCESS::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v40);
          if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                               *(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8),
                               4u) )
            AspReqEvents::ASP_END_SESSION_ONSTART::RaiseEvent(*(struct _EXTENSION_CONTROL_BLOCK **)(v26 + 8), v41);
        }
LABEL_92:
        v5 = a2;
      }
      v42 = 0;
      if ( *((int *)a3 + 1) > 0 )
      {
        while ( 1 )
        {
          v43 = *(_QWORD *)(((__int64)v42 << 6) + *((_QWORD *)a3 + 1) + 16);
          v44 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v43 + 32LL))(
                  v43,
                  L"Session_OnEnd");
          if ( v44 >= 0 )
            break;
          if ( (v44 == -2147352570 || v44 == -2147352573) && ++v42 < *((_DWORD *)a3 + 1) )
            continue;
          goto LABEL_100;
        }
        *(_DWORD *)(*((_QWORD *)v6 + 2) + 32LL) |= 0x10u;
      }
LABEL_100:
      Engines = 0;
      goto LABEL_86;
    }
    if ( v20 )
    {
      v45 = 0;
      if ( *((int *)a3 + 1) <= 0 )
      {
LABEL_107:
        v20 = 0;
      }
      else
      {
        while ( 1 )
        {
          v46 = *(_QWORD *)(((__int64)v45 << 6) + *((_QWORD *)a3 + 1) + 16);
          v47 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v46 + 32LL))(
                  v46,
                  L"Session_OnEnd");
          if ( v47 >= 0 )
            break;
          if ( (v47 == -2147352570 || v47 == -2147352573) && ++v45 < *((_DWORD *)a3 + 1) )
            continue;
          goto LABEL_107;
        }
      }
    }
    if ( v8 )
    {
      v48 = 0;
      if ( *((int *)a3 + 1) <= 0 )
      {
LABEL_114:
        v8 = 0;
      }
      else
      {
        while ( 1 )
        {
          v49 = *(_QWORD *)(((__int64)v48 << 6) + *((_QWORD *)a3 + 1) + 16);
          v50 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v49 + 32LL))(
                  v49,
                  L"Application_OnEnd");
          if ( v50 >= 0 )
            break;
          if ( (v50 == -2147352570 || v50 == -2147352573) && ++v48 < *((_DWORD *)a3 + 1) )
            continue;
          goto LABEL_114;
        }
      }
    }
    if ( !v20 && !v8 )
      goto LABEL_146;
    v51 = *((_QWORD *)v6 + 29);
    v52 = 0;
    v53 = 1;
    if ( !v51 )
      v51 = *(_QWORD *)(*((_QWORD *)v6 + 3) + 152LL);
    if ( *(_DWORD *)(v51 + 128) )
    {
      v54 = *((_QWORD *)v6 + 29);
      if ( !v54 )
        v54 = *(_QWORD *)(*((_QWORD *)v6 + 3) + 152LL);
      if ( *(_QWORD *)(v54 + 136) == -1 )
      {
        v55 = -1073741803;
LABEL_128:
        MSG_Error(v55, *(const unsigned __int16 **)(*((_QWORD *)v6 + 3) + 96LL));
        v53 = 0;
        goto LABEL_130;
      }
      v56 = *((_QWORD *)v6 + 29);
      if ( !v56 )
        v56 = *(_QWORD *)(*((_QWORD *)v6 + 3) + 152LL);
      v52 = ImpersonateLoggedOnUser(*(HANDLE *)(v56 + 136));
      if ( !v52 )
      {
        v55 = -1073741802;
        goto LABEL_128;
      }
      v52 = 1;
    }
LABEL_130:
    if ( v20 )
    {
      if ( v53 )
      {
        *((_DWORD *)v6 + 2) &= 0xF8FFFFFF;
        v57 = 0;
        *((_DWORD *)v6 + 2) |= 0x8000000u;
        Engines = -2147467259;
        if ( *((int *)a3 + 1) > 0 )
        {
          do
          {
            v58 = CallScriptFunctionOfEngine(a3, v57, L"Session_OnEnd", 0);
            Engines = v58;
            if ( v58 != -2147352573 && v58 != -2147352570 )
              break;
            ++v57;
          }
          while ( v57 < *((_DWORD *)a3 + 1) );
          v6 = a1;
        }
      }
    }
    if ( v8 )
    {
      if ( v53 )
      {
        *((_DWORD *)v6 + 2) &= 0xF4FFFFFF;
        v59 = 0;
        *((_DWORD *)v6 + 2) |= 0x4000000u;
        Engines = -2147467259;
        if ( *((int *)a3 + 1) > 0 )
        {
          do
          {
            v60 = CallScriptFunctionOfEngine(a3, v59, L"Application_OnEnd", 0);
            Engines = v60;
            if ( v60 != -2147352573 && v60 != -2147352570 )
              break;
            ++v59;
          }
          while ( v59 < *((_DWORD *)a3 + 1) );
          v6 = a1;
        }
      }
    }
    if ( v52 )
      RevertToSelf();
LABEL_146:
    v13 = v67;
LABEL_147:
    v5 = a2;
    goto LABEL_148;
  }
LABEL_149:
  v9 = v66;
LABEL_150:
  if ( v9 != ACP && (!(unsigned int)CHitObj::FHasSession(v6) || (*(_DWORD *)(*((_QWORD *)v6 + 2) + 32LL) & 0x2000) == 0) )
    CHitObj::SetCodePage(v62, v61);
  if ( v8 )
    *((_DWORD *)v6 + 2) &= ~0x200u;
  v63 = *((_DWORD *)v6 + 2);
  if ( Engines < 0 && Engines != -2147430398 && (v63 & 0x10) != 0 && !v71 )
  {
    *((_DWORD *)v6 + 2) = v63 | 0x40;
    v64 = *((_QWORD *)v6 + 2);
    if ( v64 )
      *(_DWORD *)(v64 + 32) |= 4u;
  }
  *((_DWORD *)v6 + 2) &= 0xF0FFFFFF;
  CScriptingNamespace::UnInit(v5[4]);
  if ( v13 )
  {
    if ( *((_WORD *)v13 + 88) )
      DeAllocAndFreeEngines(a3, *((struct CAppln **)v6 + 3));
    if ( (_BYTE)v68 )
      CTemplate::NotifyDebuggerOnPageEvent(v13, 0);
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v13 + 3) + 16LL))((__int64)v13 + 24);
  }
  if ( v72 )
    CoLeaveServiceDomain(0);
  if ( Engines == -2147352570 || Engines == -2147352573 )
    Engines = 0;
  if ( v74 )
    *((_QWORD *)v6 + 7) = v74;
  if ( v73 )
    (*(void (__fastcall **)(CASPObjectContext *))(*(_QWORD *)v73 + 16LL))(v73);
  return (unsigned int)Engines;
}

```

## disassembly

```asm
0x180043a54  mov     rax, rsp
0x180043a57  mov     [rax+18h], rbx
0x180043a5b  mov     [rax+10h], rdx
0x180043a5f  mov     [rax+8], rcx
0x180043a63  push    rbp
0x180043a64  push    rsi
0x180043a65  push    rdi
0x180043a66  push    r12
0x180043a68  push    r13
0x180043a6a  push    r14
0x180043a6c  push    r15
0x180043a6e  sub     rsp, 70h
0x180043a72  xor     r14d, r14d
0x180043a75  mov     r15, r8
0x180043a78  mov     [rax-70h], r14
0x180043a7c  mov     r13, rdx
0x180043a7f  mov     [rax-64h], r14d
0x180043a83  mov     rbx, rcx
0x180043a86  mov     rax, [rcx]
0x180043a89  mov     r12d, r14d
0x180043a8c  mov     byte ptr [rsp+0A8h+var_68], r14b
0x180043a91  mov     ebp, r14d
0x180043a94  mov     [rsp+0A8h+arg_18], r14d
0x180043a9c  mov     [rsp+0A8h+var_5C], r14d
0x180043aa1  mov     rax, [rax+8]
0x180043aa5  mov     [rsp+0A8h+var_58], r14d
0x180043aaa  mov     [rsp+0A8h+var_50], r14
0x180043aaf  mov     [rsp+0A8h+var_48], r14
0x180043ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ab9  mov     eax, [rbx+0A4h]
0x180043abf  mov     [rsp+0A8h+var_60], eax
0x180043ac3  test    eax, eax
0x180043ac5  jnz     short loc_180043AD1
0x180043ac7  call    cs:__imp_GetACP
0x180043acd  mov     [rsp+0A8h+var_60], eax
0x180043ad1  test    byte ptr [rbx+8], 2
0x180043ad5  jz      short loc_180043AE4
0x180043ad7  mov     rax, [rbx+18h]
0x180043adb  mov     rcx, [rax+80h]
0x180043ae2  jmp     short loc_180043AE7
0x180043ae4  mov     rcx, r14; unsigned __int16 *
0x180043ae7  lea     rax, [rsp+0A8h+var_64]
0x180043aec  mov     r9, r13; struct CIntrinsicObjects *
0x180043aef  mov     [rsp+0A8h+var_80], rax; int *
0x180043af4  lea     r8, [rsp+0A8h+var_70]; struct CTemplate **
0x180043af9  mov     rdx, rbx; struct CHitObj *
0x180043afc  mov     [rsp+0A8h+var_88], 1; int
0x180043b04  call    ?LoadTemplate@@YAJPEBGPEAVCHitObj@@PEAPEAVCTemplate@@AEBVCIntrinsicObjects@@HPEAH@Z; LoadTemplate(ushort const *,CHitObj *,CTemplate * *,CIntrinsicObjects const &,int,int *)
0x180043b09  mov     edi, eax
0x180043b0b  test    eax, eax
0x180043b0d  js      loc_18004433E
0x180043b13  mov     eax, [rbx+0A4h]
0x180043b19  mov     [rsp+0A8h+var_78], eax
0x180043b1d  test    eax, eax
0x180043b1f  jnz     short loc_180043B2B
0x180043b21  call    cs:__imp_GetACP
0x180043b27  mov     [rsp+0A8h+var_78], eax
0x180043b2b  test    byte ptr [rbx+8], 10h
0x180043b2f  mov     rsi, [rsp+0A8h+var_70]
0x180043b34  jz      short loc_180043B79
0x180043b36  mov     rdi, [rsi+1B0h]
0x180043b3d  test    rdi, rdi
0x180043b40  jz      short loc_180043B79
0x180043b42  mov     rsi, [rbx+18h]
0x180043b46  mov     rcx, [rsi+150h]
0x180043b4d  test    rcx, rcx
0x180043b50  jz      short loc_180043B5E
0x180043b52  mov     rax, [rcx]
0x180043b55  mov     rax, [rax+10h]
0x180043b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b5e  mov     [rsi+150h], rdi
0x180043b65  mov     rcx, rdi
0x180043b68  mov     rax, [rdi]
0x180043b6b  mov     rax, [rax+8]
0x180043b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b74  mov     rsi, [rsp+0A8h+var_70]
0x180043b79  cmp     [rsi+18Ch], ebp
0x180043b7f  jz      short loc_180043BBD
0x180043b81  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180043b88  xor     edx, edx; dwFlags
0x180043b8a  lea     r8d, [rdx+38h]; dwBytes
0x180043b8e  call    cs:__imp_HeapAlloc
0x180043b94  test    rax, rax
0x180043b97  jz      short loc_180043BE4
0x180043b99  mov     rcx, rax; punkOuter
0x180043b9c  call    ??0CASPObjectContext@@QEAA@XZ; CASPObjectContext::CASPObjectContext(void)
0x180043ba1  mov     [rsp+0A8h+var_50], rax
0x180043ba6  test    rax, rax
0x180043ba9  jz      short loc_180043BE9
0x180043bab  mov     rcx, [rbx+38h]
0x180043baf  mov     [rsp+0A8h+var_48], rcx
0x180043bb4  mov     [rbx+38h], rax
0x180043bb8  mov     [rsp+0A8h+var_50], rax
0x180043bbd  mov     rcx, [rsi+1E0h]; pConfigObject
0x180043bc4  test    rcx, rcx
0x180043bc7  jz      short loc_180043BF3
0x180043bc9  call    cs:__imp_CoEnterServiceDomain
0x180043bcf  mov     edi, eax
0x180043bd1  test    eax, eax
0x180043bd3  js      loc_180044231
0x180043bd9  mov     edi, 1
0x180043bde  mov     [rsp+0A8h+var_58], edi
0x180043be2  jmp     short loc_180043BF8
0x180043be4  mov     [rsp+0A8h+var_50], rbp
0x180043be9  mov     edi, 8007000Eh
0x180043bee  jmp     loc_180044231
0x180043bf3  mov     edi, 1
0x180043bf8  mov     r8d, [rbx+8]
0x180043bfc  mov     rcx, rbx; this
0x180043bff  mov     r13d, ebp
0x180043c02  call    ?FIsBrowserRequest@CHitObj@@QEBAHXZ; CHitObj::FIsBrowserRequest(void)
0x180043c07  test    eax, eax
0x180043c09  jz      short loc_180043C29
0x180043c0b  mov     r14d, r8d
0x180043c0e  shr     r14d, 4
0x180043c12  and     r14d, edi
0x180043c15  jz      short loc_180043C49
0x180043c17  bts     r8d, 9
0x180043c1c  mov     [rsp+0A8h+arg_18], edi
0x180043c23  mov     [rbx+8], r8d
0x180043c27  jmp     short loc_180043C49
0x180043c29  and     r8d, 0F0000h
0x180043c30  cmp     r8d, 20000h
0x180043c37  jnz     short loc_180043C3E
0x180043c39  mov     r13d, edi
0x180043c3c  jmp     short loc_180043C49
0x180043c3e  cmp     r8d, 40000h
0x180043c45  cmovz   r12d, edi
0x180043c49  mov     rax, [rbx+18h]
0x180043c4d  test    byte ptr [rax+48h], 20h
0x180043c51  jz      short loc_180043C6D
0x180043c53  mov     edx, edi; int
0x180043c55  mov     rcx, rsi; this
0x180043c58  call    ?NotifyDebuggerOnPageEvent@CTemplate@@QEAAJH@Z; CTemplate::NotifyDebuggerOnPageEvent(int)
0x180043c5d  mov     ecx, [rsp+0A8h+var_68]
0x180043c61  test    eax, eax
0x180043c63  movzx   ecx, cl
0x180043c66  cmovns  ecx, edi
0x180043c69  mov     [rsp+0A8h+var_68], ecx
0x180043c6d  mov     r9, [rsp+0A8h+arg_8]
0x180043c75  mov     r8, r15; struct ActiveEngineInfo *
0x180043c78  mov     rdx, rsi; struct CTemplate *
0x180043c7b  mov     [rsp+0A8h+var_88], edi; int
0x180043c7f  mov     rcx, rbx; struct CHitObj *
0x180043c82  mov     r9, [r9+20h]; struct CScriptingNamespace *
0x180043c86  call    ?AllocAndLoadEngines@@YAJPEAVCHitObj@@PEAVCTemplate@@PEAUActiveEngineInfo@@PEAVCScriptingNamespace@@H@Z; AllocAndLoadEngines(CHitObj *,CTemplate *,ActiveEngineInfo *,CScriptingNamespace *,int)
0x180043c8b  mov     edi, eax
0x180043c8d  test    eax, eax
0x180043c8f  js      loc_18004421E
0x180043c95  cmp     [rsp+0A8h+var_64], ebp
0x180043c99  jnz     short loc_180043CAD
0x180043c9b  mov     rdx, [rbx+18h]; struct CAppln *
0x180043c9f  test    byte ptr [rdx+48h], 20h
0x180043ca3  jz      short loc_180043CAD
0x180043ca5  mov     rcx, rsi; this
0x180043ca8  call    ?AttachTo@CTemplate@@QEAAJPEAVCAppln@@@Z; CTemplate::AttachTo(CAppln *)
0x180043cad  cmp     bp, [rsi+0B0h]
0x180043cb4  jz      loc_18004421E
0x180043cba  mov     rsi, [rbx+40h]
0x180043cbe  test    r14d, r14d
0x180043cc1  jz      loc_180043E01
0x180043cc7  and     dword ptr [rbx+8], 0F1FFFFFFh
0x180043cce  bts     dword ptr [rbx+8], 18h
0x180043cd3  test    rsi, rsi
0x180043cd6  jz      short loc_180043CF3
0x180043cd8  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043cdc  mov     edx, 4; unsigned int
0x180043ce1  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180043ce6  test    eax, eax
0x180043ce8  jz      short loc_180043CF3
0x180043cea  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043cee  call    ?RaiseEvent@ASP_START_APPLICATION_ONSTART@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_START_APPLICATION_ONSTART::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180043cf3  mov     edi, 80004005h
0x180043cf8  cmp     [r15+4], ebp
0x180043cfc  jle     short loc_180043D43
0x180043cfe  movzx   edx, bp; __int16
0x180043d01  lea     r8, aApplicationOns; "Application_OnStart"
0x180043d08  xor     r9d, r9d; struct CASPObjectContext *
0x180043d0b  mov     rcx, r15; struct ActiveEngineInfo *
0x180043d0e  call    ?CallScriptFunctionOfEngine@@YAJAEAUActiveEngineInfo@@FPEAGPEAVCASPObjectContext@@@Z; CallScriptFunctionOfEngine(ActiveEngineInfo &,short,ushort *,CASPObjectContext *)
0x180043d13  mov     edi, eax
0x180043d15  test    eax, eax
0x180043d17  jns     loc_180043DA6
0x180043d1d  mov     r8d, 80020006h
0x180043d23  cmp     eax, r8d
0x180043d26  jz      short loc_180043D2F
0x180043d28  cmp     eax, 80020003h
0x180043d2d  jnz     short loc_180043D43
0x180043d2f  inc     ebp
0x180043d31  cmp     ebp, [r15+4]
0x180043d35  jl      short loc_180043CFE
0x180043d37  cmp     eax, r8d
0x180043d3a  jz      short loc_180043DA6
0x180043d3c  cmp     eax, 80020003h
0x180043d41  jz      short loc_180043DA6
0x180043d43  mov     rax, [rsp+0A8h+arg_8]
0x180043d4b  mov     rax, [rax+8]
0x180043d4f  mov     rcx, [rax+38h]
0x180043d53  test    byte ptr [rcx+118h], 1
0x180043d5a  jnz     short loc_180043DA6
0x180043d5c  xor     r14d, r14d
0x180043d5f  test    rsi, rsi
0x180043d62  jz      short loc_180043D9C
0x180043d64  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043d68  lea     edx, [r14+2]; unsigned int
0x180043d6c  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180043d71  test    eax, eax
0x180043d73  jz      short loc_180043D81
0x180043d75  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043d79  mov     r8d, edi; unsigned int
0x180043d7c  call    ?RaiseEvent@ASP_APPLICATION_ONSTART_ERROR@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@K@Z; AspReqEvents::ASP_APPLICATION_ONSTART_ERROR::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ulong)
0x180043d81  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043d85  mov     edx, 4; unsigned int
0x180043d8a  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180043d8f  test    eax, eax
0x180043d91  jz      short loc_180043D9C
0x180043d93  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043d97  call    ?RaiseEvent@ASP_END_APPLICATION_ONSTART@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_END_APPLICATION_ONSTART::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180043d9c  mov     rsi, [rsp+0A8h+var_70]
0x180043da1  jmp     loc_180044221
0x180043da6  xor     ebp, ebp
0x180043da8  cmp     [rsp+0A8h+arg_18], ebp
0x180043daf  jz      short loc_180043DBD
0x180043db1  btr     dword ptr [rbx+8], 9
0x180043db6  mov     [rsp+0A8h+arg_18], ebp
0x180043dbd  mov     [rsp+0A8h+var_5C], 1
0x180043dc5  test    rsi, rsi
0x180043dc8  jz      short loc_180043DFF
0x180043dca  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043dce  mov     edi, 4
0x180043dd3  mov     edx, edi; unsigned int
0x180043dd5  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180043dda  test    eax, eax
0x180043ddc  jz      short loc_180043DE7
0x180043dde  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043de2  call    ?RaiseEvent@ASP_APPLICATION_ONSTART_SUCCESS@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_APPLICATION_ONSTART_SUCCESS::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180043de7  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043deb  mov     edx, edi; unsigned int
0x180043ded  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180043df2  test    eax, eax
0x180043df4  jz      short loc_180043DFF
0x180043df6  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043dfa  call    ?RaiseEvent@ASP_END_APPLICATION_ONSTART@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_END_APPLICATION_ONSTART::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180043dff  mov     edi, ebp
0x180043e01  test    byte ptr [rbx+8], 4
0x180043e05  jz      loc_180044022
0x180043e0b  mov     r12d, 1
0x180043e11  test    r14d, r14d
0x180043e14  jz      short loc_180043E89
0x180043e16  cmp     dword ptr [r15+4], 0
0x180043e1b  jle     short loc_180043E87
0x180043e1d  mov     rax, [r15+8]
0x180043e21  lea     rdx, aResponse; "Response"
0x180043e28  movzx   r14d, bp
0x180043e2c  xor     r8d, r8d
0x180043e2f  shl     r14, 6
0x180043e33  mov     rcx, [rax+r14+10h]
0x180043e38  mov     rax, [rcx]
0x180043e3b  mov     rax, [rax+10h]
0x180043e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e44  mov     edi, eax
0x180043e46  test    eax, eax
0x180043e48  js      loc_180044219
0x180043e4e  mov     rax, [r15+8]
0x180043e52  lea     rdx, aRequest; "Request"
0x180043e59  xor     r8d, r8d
0x180043e5c  mov     rcx, [r14+rax+10h]
0x180043e61  mov     rax, [rcx]
0x180043e64  mov     rax, [rax+10h]
0x180043e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e6d  xor     r14d, r14d
0x180043e70  mov     edi, eax
0x180043e72  test    eax, eax
0x180043e74  js      loc_180043D9C
0x180043e7a  add     bp, r12w
0x180043e7e  movzx   eax, bp
0x180043e81  cmp     eax, [r15+4]
0x180043e85  jl      short loc_180043E1D
0x180043e87  xor     ebp, ebp
0x180043e89  and     dword ptr [rbx+8], 0F2FFFFFFh
0x180043e90  bts     dword ptr [rbx+8], 19h
0x180043e95  test    rsi, rsi
0x180043e98  jz      short loc_180043EB5
0x180043e9a  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043e9e  mov     edx, 4; unsigned int
0x180043ea3  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180043ea8  test    eax, eax
0x180043eaa  jz      short loc_180043EB5
0x180043eac  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180043eb0  call    ?RaiseEvent@ASP_START_SESSION_ONSTART@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@@Z; AspReqEvents::ASP_START_SESSION_ONSTART::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *)
0x180043eb5  xor     r14d, r14d
0x180043eb8  mov     edi, 80004005h
0x180043ebd  cmp     [r15+4], r14d
0x180043ec1  jle     short loc_180043F11
0x180043ec3  movzx   edx, bp; __int16
0x180043ec6  lea     r8, aSessionOnstart; "Session_OnStart"
0x180043ecd  xor     r9d, r9d; struct CASPObjectContext *
0x180043ed0  mov     rcx, r15; struct ActiveEngineInfo *
0x180043ed3  call    ?CallScriptFunctionOfEngine@@YAJAEAUActiveEngineInfo@@FPEAGPEAVCASPObjectContext@@@Z; CallScriptFunctionOfEngine(ActiveEngineInfo &,short,ushort *,CASPObjectContext *)
0x180043ed8  mov     edi, eax
  ... truncated ...
```
