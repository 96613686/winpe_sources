# CServiceModule::MonitorThreadProc(void *)

- ea: `0x18000f5d0`
- end: `0x18000f9f7`
- name: `?MonitorThreadProc@CServiceModule@@SAKPEAX@Z`
- size: `1063`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x18000ea80`
- `0x18000ed70`
- `0x18000f5d0`
- `0x18000fa00`
- `0x1800110e0`
- `0x180012dc0`
- `0x1800133e0`
- `0x180019a40`
- `0x18001bbe0`
- `0x18001f394`
- `0x180026e80`
- `0x18002b3a8`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000f628`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000f628`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000f630`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000f630`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000f91f`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18000f91f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f7dc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f7dc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000f777`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000f777`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f63d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f63d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18000f8db`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18000f8db`

## string_xrefs

- `0x18000f60e`: `PENSERVICE_CServiceModule::MonitorThreadProc`
- `0x18000f823`: `PENSERVICE_CServiceModule::MonitorThreadProc`
- `0x18000f8ba`: `PENSERVICE_CServiceModule::MonitorThreadProc`
- `0x18000f945`: `PENSERVICE_CServiceModule::MonitorThreadProc`
- `0x18000f9c3`: `PENSERVICE_CServiceModule::MonitorThreadProc`

## pseudocode

```c
__int64 __fastcall CServiceModule::MonitorThreadProc(void *a1)
{
  unsigned int v1; // eax
  CServiceModule *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // r9d
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // r9d
  DWORD v9; // esi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  DWORD v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // r9d
  __int64 v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // r9d
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // edi
  __int64 i; // rbx
  struct CServiceModule::ScmEvent *v31; // rbx
  PSLIST_ENTRY v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  struct _SLIST_ENTRY *Next; // rcx
  struct CServiceModule::ScmEvent *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int v39; // r9d
  __int64 v40; // rcx
  ControllerDetector *v41; // rdx
  __int128 v43; // [rsp+30h] [rbp-79h]
  int v44; // [rsp+40h] [rbp-69h]
  __int128 v45; // [rsp+50h] [rbp-59h] BYREF
  __int128 v46; // [rsp+60h] [rbp-49h]
  __int128 v47; // [rsp+70h] [rbp-39h]
  __int128 v48; // [rsp+80h] [rbp-29h] BYREF
  __int128 v49; // [rsp+90h] [rbp-19h]
  __int128 v50; // [rsp+A0h] [rbp-9h]
  HANDLE Handles[2]; // [rsp+B0h] [rbp+7h] BYREF
  __int128 v52; // [rsp+C0h] [rbp+17h]
  __int64 v53; // [rsp+D0h] [rbp+27h]

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      139,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::MonitorThreadProc");
  v1 = _time64(0);
  _o_srand(v1);
  SetEvent(qword_1800412B0);
  CServiceModule::_SetServiceTypeAutoStart(v2);
  CServiceModule::StartTabletPCRegistryWatcher((CServiceModule *)&_Module);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          v3,
                          v4,
                          v5) )
    CServiceModule::StartControllerWatcher((CServiceModule *)&_Module);
  *(_OWORD *)Handles = 0;
  v53 = 0;
  v52 = 0;
  v44 = 0;
  v43 = 0;
  v9 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          v6,
                          v7,
                          v8) )
  {
    if ( hEvent )
    {
      Handles[0] = hEvent;
      v9 = 1;
    }
    if ( qword_1800412C0 )
    {
      v10 = v9++;
      Handles[v10] = (HANDLE)qword_1800412C0;
      *((_DWORD *)&v43 + v10) = 1;
    }
    if ( qword_1800412D8 )
    {
      v11 = v9++;
      Handles[v11] = (HANDLE)qword_1800412D8;
      *((_DWORD *)&v43 + v11) = 2;
    }
    if ( qword_1800412A0 )
    {
      v12 = v9++;
      Handles[v12] = (HANDLE)qword_1800412A0;
      *((_DWORD *)&v43 + v12) = 3;
    }
    if ( qword_1800412D0 )
    {
      v13 = v9++;
      Handles[v13] = qword_1800412D0;
      *((_DWORD *)&v43 + v13) = 4;
    }
  }
  else
  {
    Handles[0] = hEvent;
    Handles[1] = (HANDLE)qword_1800412C0;
    *(_QWORD *)&v52 = qword_1800412D8;
    *((_QWORD *)&v52 + 1) = qword_1800412A0;
    LOBYTE(v9) = qword_1800412A0 != 0;
    v9 += 3;
  }
  while ( 1 )
  {
    v14 = WaitForMultipleObjectsEx(v9, Handles, 0, 0xFFFFFFFF, 1);
    v18 = v14;
    if ( v14 == -1 )
      break;
    if ( v14 < 5 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                              (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                              v15,
                              v16,
                              v17) )
        LODWORD(v18) = *((_DWORD *)&v43 + v18);
      if ( (_DWORD)v18 )
      {
        v22 = v18 - 1;
        if ( !v22 )
          goto LABEL_47;
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            if ( v24 == 1 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                                      (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                                      v19,
                                      v20,
                                      v21) )
              {
                ResetEvent(qword_1800412D0);
                v46 = 0;
                LODWORD(v46) = 11;
                v45 = 0;
                v47 = 0;
                CServiceModule::_ProcessScmEvent(
                  (struct _GUID *)&_Module,
                  (struct CServiceModule::ScmEvent *)&v45,
                  v25,
                  v26);
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
            {
              WPP_SF_s(
                *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
                143,
                WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
                "PENSERVICE_CServiceModule::MonitorThreadProc");
            }
            CServiceModule::StartTabletPCRegistryWatcher((CServiceModule *)&_Module);
            v49 = 0;
            LODWORD(v49) = 11;
            v48 = 0;
            v50 = 0;
            CServiceModule::_ProcessScmEvent(
              (struct _GUID *)&_Module,
              (struct CServiceModule::ScmEvent *)&v48,
              v27,
              v28);
          }
        }
        else
        {
          v29 = dword_18004134C;
          for ( i = 0; (int)i < v29; i = (unsigned int)(i + 1) )
            CServiceModule::_ProcessSessionEvents((CServiceModule *)&_Module, (struct CPenSession *)(*off_180041340)[i]);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_s(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            142,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::MonitorThreadProc");
        v31 = 0;
        v32 = InterlockedFlushSList(&ListHead);
        if ( v32 )
        {
          do
          {
            Next = v32->Next;
            v32->Next = (struct _SLIST_ENTRY *)v31;
            v31 = (struct CServiceModule::ScmEvent *)v32;
            v32 = Next;
          }
          while ( Next );
        }
        while ( v31 )
        {
          CServiceModule::_ProcessScmEvent((struct _GUID *)&_Module, v31, v33, v34);
          v36 = v31;
          v31 = *(struct CServiceModule::ScmEvent **)v31;
          _aligned_free(v36);
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      140,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::MonitorThreadProc");
LABEL_47:
  SafeCloseKey(&qword_180041298);
  SH<void *,SH_HANDLE>::Reset(&qword_1800412A0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                          (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                          v37,
                          v38,
                          v39) )
  {
    v41 = (ControllerDetector *)qword_1800414B0;
    qword_1800414B0 = 0;
    if ( v41 )
      std::default_delete<ControllerDetector>::operator()(v40, v41);
    SH<void *,SH_HANDLE>::Reset(&qword_1800412D0);
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      144,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::MonitorThreadProc");
  return 0;
}

```

## disassembly

```asm
0x18000f5d0  push    rbp
0x18000f5d2  push    rbx
0x18000f5d3  push    rsi
0x18000f5d4  push    rdi
0x18000f5d5  push    r14
0x18000f5d7  lea     rbp, [rsp-37h]
0x18000f5dc  sub     rsp, 0E0h
0x18000f5e3  mov     rax, cs:__security_cookie
0x18000f5ea  xor     rax, rsp
0x18000f5ed  mov     [rbp+57h+var_28], rax
0x18000f5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5f8  lea     r14, WPP_GLOBAL_Control
0x18000f5ff  cmp     rcx, r14
0x18000f602  jz      short loc_18000F626
0x18000f604  test    byte ptr [rcx+1Ch], 10h
0x18000f608  jz      short loc_18000F626
0x18000f60a  mov     rcx, [rcx+10h]
0x18000f60e  lea     r9, aPenserviceCser_13; "PENSERVICE_CServiceModule::MonitorThrea"...
0x18000f615  mov     edx, 8Bh
0x18000f61a  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f621  call    WPP_SF_s
0x18000f626  xor     ecx, ecx; Time
0x18000f628  call    cs:__imp__time64
0x18000f62e  mov     ecx, eax
0x18000f630  call    cs:__imp__o_srand
0x18000f636  mov     rcx, cs:qword_1800412B0; hEvent
0x18000f63d  call    cs:__imp_SetEvent
0x18000f643  call    ?_SetServiceTypeAutoStart@CServiceModule@@AEAAHXZ; CServiceModule::_SetServiceTypeAutoStart(void)
0x18000f648  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18000f64f  call    ?StartTabletPCRegistryWatcher@CServiceModule@@QEAA_NXZ; CServiceModule::StartTabletPCRegistryWatcher(void)
0x18000f654  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000f65b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000f660  test    al, al
0x18000f662  jz      short loc_18000F670
0x18000f664  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18000f66b  call    ?StartControllerWatcher@CServiceModule@@QEAA_NXZ; CServiceModule::StartControllerWatcher(void)
0x18000f670  xorps   xmm0, xmm0
0x18000f673  xor     eax, eax
0x18000f675  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x18000f679  mov     [rbp+57h+var_30], rax
0x18000f67d  movups  [rbp+57h+var_40], xmm0
0x18000f681  mov     [rbp+57h+var_C0], eax
0x18000f684  movups  [rbp+57h+var_D0], xmm0
0x18000f688  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000f68f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000f694  xor     esi, esi
0x18000f696  test    al, al
0x18000f698  mov     rax, cs:hEvent
0x18000f69f  jz      loc_18000F729
0x18000f6a5  test    rax, rax
0x18000f6a8  jz      short loc_18000F6B3
0x18000f6aa  mov     [rbp+57h+Handles], rax
0x18000f6ae  mov     esi, 1
0x18000f6b3  mov     rcx, cs:qword_1800412C0
0x18000f6ba  test    rcx, rcx
0x18000f6bd  jz      short loc_18000F6D0
0x18000f6bf  mov     eax, esi
0x18000f6c1  inc     esi
0x18000f6c3  mov     [rbp+rax*8+57h+Handles], rcx
0x18000f6c8  mov     dword ptr [rbp+rax*4+57h+var_D0], 1
0x18000f6d0  mov     rcx, cs:qword_1800412D8
0x18000f6d7  test    rcx, rcx
0x18000f6da  jz      short loc_18000F6ED
0x18000f6dc  mov     eax, esi
0x18000f6de  inc     esi
0x18000f6e0  mov     [rbp+rax*8+57h+Handles], rcx
0x18000f6e5  mov     dword ptr [rbp+rax*4+57h+var_D0], 2
0x18000f6ed  mov     rcx, cs:qword_1800412A0
0x18000f6f4  test    rcx, rcx
0x18000f6f7  jz      short loc_18000F70A
0x18000f6f9  mov     eax, esi
0x18000f6fb  inc     esi
0x18000f6fd  mov     [rbp+rax*8+57h+Handles], rcx
0x18000f702  mov     dword ptr [rbp+rax*4+57h+var_D0], 3
0x18000f70a  mov     rcx, cs:qword_1800412D0
0x18000f711  test    rcx, rcx
0x18000f714  jz      short loc_18000F760
0x18000f716  mov     eax, esi
0x18000f718  inc     esi
0x18000f71a  mov     [rbp+rax*8+57h+Handles], rcx
0x18000f71f  mov     dword ptr [rbp+rax*4+57h+var_D0], 4
0x18000f727  jmp     short loc_18000F760
0x18000f729  mov     [rbp+57h+Handles], rax
0x18000f72d  mov     rax, cs:qword_1800412C0
0x18000f734  mov     [rbp+57h+Handles+8], rax
0x18000f738  mov     rax, cs:qword_1800412D8
0x18000f73f  mov     qword ptr [rbp+57h+var_40], rax
0x18000f743  mov     rax, cs:qword_1800412A0
0x18000f74a  test    rax, rax
0x18000f74d  mov     qword ptr [rbp+57h+var_40+8], rax
0x18000f751  setnz   sil
0x18000f755  add     esi, 3
0x18000f758  nop     dword ptr [rax+rax+00000000h]
0x18000f760  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000f766  mov     [rsp+100h+bAlertable], 1; bAlertable
0x18000f76e  xor     r8d, r8d; bWaitAll
0x18000f771  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000f775  mov     ecx, esi; nCount
0x18000f777  call    cs:__imp_WaitForMultipleObjectsEx
0x18000f77d  mov     ebx, eax
0x18000f77f  cmp     eax, 0FFFFFFFFh
0x18000f782  jz      loc_18000F92F
0x18000f788  cmp     ebx, 5
0x18000f78b  jnb     short loc_18000F760
0x18000f78d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000f794  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000f799  test    al, al
0x18000f79b  jz      short loc_18000F7A1
0x18000f79d  mov     ebx, dword ptr [rbp+rbx*4+57h+var_D0]
0x18000f7a1  test    ebx, ebx
0x18000f7a3  jz      loc_18000F8A4
0x18000f7a9  sub     ebx, 1
0x18000f7ac  jz      loc_18000F95D
0x18000f7b2  sub     ebx, 1
0x18000f7b5  jz      loc_18000F872
0x18000f7bb  sub     ebx, 1
0x18000f7be  jz      short loc_18000F80D
0x18000f7c0  cmp     ebx, 1
0x18000f7c3  jnz     short loc_18000F760
0x18000f7c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000f7cc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000f7d1  test    al, al
0x18000f7d3  jz      short loc_18000F760
0x18000f7d5  mov     rcx, cs:qword_1800412D0; hEvent
0x18000f7dc  call    cs:__imp_ResetEvent
0x18000f7e2  xorps   xmm0, xmm0
0x18000f7e5  lea     rdx, [rbp+57h+var_B0]; struct CServiceModule::ScmEvent *
0x18000f7e9  movups  [rbp+57h+var_A0], xmm0
0x18000f7ed  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18000f7f4  mov     dword ptr [rbp+57h+var_A0], 0Bh
0x18000f7fb  movups  [rbp+57h+var_B0], xmm0
0x18000f7ff  movups  [rbp+57h+var_90], xmm0
0x18000f803  call    ?_ProcessScmEvent@CServiceModule@@AEAAJPEAUScmEvent@1@@Z; CServiceModule::_ProcessScmEvent(CServiceModule::ScmEvent *)
0x18000f808  jmp     loc_18000F760
0x18000f80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f814  cmp     rcx, r14
0x18000f817  jz      short loc_18000F83B
0x18000f819  test    byte ptr [rcx+1Ch], 10h
0x18000f81d  jz      short loc_18000F83B
0x18000f81f  mov     rcx, [rcx+10h]
0x18000f823  lea     r9, aPenserviceCser_13; "PENSERVICE_CServiceModule::MonitorThrea"...
0x18000f82a  mov     edx, 8Fh
0x18000f82f  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f836  call    WPP_SF_s
0x18000f83b  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18000f842  call    ?StartTabletPCRegistryWatcher@CServiceModule@@QEAA_NXZ; CServiceModule::StartTabletPCRegistryWatcher(void)
0x18000f847  xorps   xmm0, xmm0
0x18000f84a  lea     rdx, [rbp+57h+var_80]; struct CServiceModule::ScmEvent *
0x18000f84e  movups  [rbp+57h+var_70], xmm0
0x18000f852  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18000f859  mov     dword ptr [rbp+57h+var_70], 0Bh
0x18000f860  movups  [rbp+57h+var_80], xmm0
0x18000f864  movups  [rbp+57h+var_60], xmm0
0x18000f868  call    ?_ProcessScmEvent@CServiceModule@@AEAAJPEAUScmEvent@1@@Z; CServiceModule::_ProcessScmEvent(CServiceModule::ScmEvent *)
0x18000f86d  jmp     loc_18000F760
0x18000f872  mov     edi, cs:dword_18004134C
0x18000f878  xor     ebx, ebx
0x18000f87a  test    edi, edi
0x18000f87c  jle     loc_18000F760
0x18000f882  mov     rdx, cs:off_180041340
0x18000f889  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18000f890  mov     rdx, [rdx+rbx*8]; struct CPenSession *
0x18000f894  call    ?_ProcessSessionEvents@CServiceModule@@AEAAXPEAVCPenSession@@@Z; CServiceModule::_ProcessSessionEvents(CPenSession *)
0x18000f899  inc     ebx
0x18000f89b  cmp     ebx, edi
0x18000f89d  jl      short loc_18000F882
0x18000f89f  jmp     loc_18000F760
0x18000f8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8ab  cmp     rcx, r14
0x18000f8ae  jz      short loc_18000F8D2
0x18000f8b0  test    byte ptr [rcx+1Ch], 10h
0x18000f8b4  jz      short loc_18000F8D2
0x18000f8b6  mov     rcx, [rcx+10h]
0x18000f8ba  lea     r9, aPenserviceCser_13; "PENSERVICE_CServiceModule::MonitorThrea"...
0x18000f8c1  mov     edx, 8Eh
0x18000f8c6  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f8cd  call    WPP_SF_s
0x18000f8d2  lea     rcx, ListHead; ListHead
0x18000f8d9  xor     ebx, ebx
0x18000f8db  call    cs:__imp_InterlockedFlushSList
0x18000f8e1  test    rax, rax
0x18000f8e4  jz      short loc_18000F901
0x18000f8e6  nop     word ptr [rax+rax+00000000h]
0x18000f8f0  mov     rcx, [rax]
0x18000f8f3  mov     [rax], rbx
0x18000f8f6  mov     rbx, rax
0x18000f8f9  mov     rax, rcx
0x18000f8fc  test    rcx, rcx
0x18000f8ff  jnz     short loc_18000F8F0
0x18000f901  test    rbx, rbx
0x18000f904  jz      loc_18000F760
0x18000f90a  mov     rdx, rbx; struct CServiceModule::ScmEvent *
0x18000f90d  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18000f914  call    ?_ProcessScmEvent@CServiceModule@@AEAAJPEAUScmEvent@1@@Z; CServiceModule::_ProcessScmEvent(CServiceModule::ScmEvent *)
0x18000f919  mov     rcx, rbx; Block
0x18000f91c  mov     rbx, [rbx]
0x18000f91f  call    cs:__imp__aligned_free
0x18000f925  test    rbx, rbx
0x18000f928  jnz     short loc_18000F90A
0x18000f92a  jmp     loc_18000F760
0x18000f92f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f936  cmp     rcx, r14
0x18000f939  jz      short loc_18000F95D
0x18000f93b  test    byte ptr [rcx+1Ch], 4
0x18000f93f  jz      short loc_18000F95D
0x18000f941  mov     rcx, [rcx+10h]
0x18000f945  lea     r9, aPenserviceCser_13; "PENSERVICE_CServiceModule::MonitorThrea"...
0x18000f94c  mov     edx, 8Ch
0x18000f951  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f958  call    WPP_SF_s
0x18000f95d  lea     rcx, qword_180041298; HKEY *
0x18000f964  call    ?SafeCloseKey@@YAXPEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * *)
0x18000f969  lea     rcx, qword_1800412A0
0x18000f970  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18000f975  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000f97c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000f981  test    al, al
0x18000f983  jz      short loc_18000F9AD
0x18000f985  mov     rdx, cs:qword_1800414B0
0x18000f98c  mov     cs:qword_1800414B0, 0
0x18000f997  test    rdx, rdx
0x18000f99a  jz      short loc_18000F9A1
0x18000f99c  call    ??R?$default_delete@VControllerDetector@@@std@@QEBAXPEAVControllerDetector@@@Z; std::default_delete<ControllerDetector>::operator()(ControllerDetector *)
0x18000f9a1  lea     rcx, qword_1800412D0
0x18000f9a8  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18000f9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9b4  cmp     rcx, r14
0x18000f9b7  jz      short loc_18000F9DB
0x18000f9b9  test    byte ptr [rcx+1Ch], 10h
0x18000f9bd  jz      short loc_18000F9DB
0x18000f9bf  mov     rcx, [rcx+10h]
0x18000f9c3  lea     r9, aPenserviceCser_13; "PENSERVICE_CServiceModule::MonitorThrea"...
0x18000f9ca  mov     edx, 90h
0x18000f9cf  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f9d6  call    WPP_SF_s
0x18000f9db  xor     eax, eax
0x18000f9dd  mov     rcx, [rbp+57h+var_28]
0x18000f9e1  xor     rcx, rsp; StackCookie
0x18000f9e4  call    __security_check_cookie
0x18000f9e9  add     rsp, 0E0h
0x18000f9f0  pop     r14
0x18000f9f2  pop     rdi
0x18000f9f3  pop     rsi
0x18000f9f4  pop     rbx
0x18000f9f5  pop     rbp
0x18000f9f6  retn
```
