# RunComServerFlowWork(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x14001f420`
- end: `0x14001fbc7`
- name: `?RunComServerFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1959`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, _DWORD *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000a330`
- `0x14000a3d0`
- `0x14000a470`
- `0x14000a510`
- `0x14000a570`
- `0x14000a630`
- `0x14000a6e4`
- `0x14000a744`
- `0x14000a7a4`
- `0x14000e624`
- `0x140011590`
- `0x14001a2a0`
- `0x14001a2cc`
- `0x14001f420`
- `0x14002a8d8`
- `0x14002dd70`
- `0x14002de74`
- `0x14007d010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x14001f43c`
- `KERNEL32!TlsGetValue` at `0x14001f43c`
- `KERNEL32!TlsSetValue` at `0x14001f46a`
- `KERNEL32!TlsSetValue` at `0x14001f46a`
- `ole32!CreateClassMoniker` at `0x14001f5ba`
- `ole32!CreateClassMoniker` at `0x14001f66e`
- `ole32!CreateClassMoniker` at `0x14001f725`
- `ole32!CreateClassMoniker` at `0x14001f7cb`
- `ole32!CreateClassMoniker` at `0x14001f882`
- `ole32!CreateClassMoniker` at `0x14001f918`
- `ole32!CreateClassMoniker` at `0x14001f9ae`
- `ole32!CreateClassMoniker` at `0x14001fa44`
- `ole32!CreateClassMoniker` at `0x14001facc`
- `ole32!CreateClassMoniker` at `0x14001f5ba`
- `ole32!CreateClassMoniker` at `0x14001f66e`
- `ole32!CreateClassMoniker` at `0x14001f725`
- `ole32!CreateClassMoniker` at `0x14001f7cb`
- `ole32!CreateClassMoniker` at `0x14001f882`
- `ole32!CreateClassMoniker` at `0x14001f918`
- `ole32!CreateClassMoniker` at `0x14001f9ae`
- `ole32!CreateClassMoniker` at `0x14001fa44`
- `ole32!CreateClassMoniker` at `0x14001facc`
- `ole32!GetRunningObjectTable` at `0x14001f506`
- `ole32!GetRunningObjectTable` at `0x14001f506`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14001f4dc`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14001f4dc`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14001fba0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14001fba0`

## pseudocode

```c
void __fastcall RunComServerFlowWork(struct _TP_CALLBACK_INSTANCE *a1, _DWORD *a2, struct _TP_WORK *a3)
{
  __int64 *Value; // rax
  __int64 *p_TlsValue; // r14
  const char *v6; // rdx
  unsigned int v7; // ecx
  __int64 v8; // rcx
  int v9; // edi
  HRESULT RunningObjectTable; // eax
  char v11; // si
  _DWORD *v12; // rbx
  HRESULT v13; // eax
  int v14; // eax
  _DWORD *v15; // rbx
  HRESULT v16; // eax
  __int64 (__fastcall *v17)(_DWORD *, GUID *, __int64 *); // rsi
  int v18; // eax
  int v19; // eax
  _DWORD *v20; // rbx
  HRESULT v21; // eax
  int v22; // eax
  HRESULT v23; // eax
  __int64 (__fastcall *v24)(_DWORD *, GUID *, __int64 *); // rsi
  int v25; // eax
  int v26; // eax
  _DWORD *v27; // rbx
  HRESULT v28; // eax
  int v29; // eax
  _DWORD *v30; // rbx
  HRESULT v31; // eax
  int v32; // eax
  _DWORD *v33; // rbx
  HRESULT v34; // eax
  int v35; // eax
  _DWORD *v36; // rbx
  HRESULT v37; // eax
  int v38; // eax
  _DWORD *v39; // rbx
  HRESULT v40; // eax
  int v41; // eax
  unsigned int v42; // edx
  __int64 v43; // r15
  LPMONIKER ppmk; // [rsp+38h] [rbp-38h] BYREF
  LPRUNNINGOBJECTTABLE pprot; // [rsp+40h] [rbp-30h] BYREF
  __int64 v46; // [rsp+48h] [rbp-28h] BYREF
  _DWORD *v47; // [rsp+50h] [rbp-20h] BYREF
  __int64 TlsValue; // [rsp+58h] [rbp-18h] BYREF
  __int64 *v49; // [rsp+60h] [rbp-10h]
  unsigned int v50; // [rsp+A8h] [rbp+38h] BYREF
  DWORD v51; // [rsp+B8h] [rbp+48h] BYREF

  Value = (__int64 *)TlsGetValue(__g_tracingTlsSlot);
  p_TlsValue = Value;
  v51 = -1;
  TlsValue = 0;
  if ( Value )
  {
    v49 = Value;
  }
  else
  {
    p_TlsValue = &TlsValue;
    v51 = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
    v49 = &TlsValue;
  }
  ++*(_DWORD *)p_TlsValue;
  v6 = "                                                                                                                 "
       "                                                                                                                 "
       "                                                                                                                 "
       "                                                                                                                 "
       "                            ";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v7 = 5 * *(_DWORD *)p_TlsValue;
    if ( v7 > 0x1E1 )
      v8 = 0;
    else
      v8 = 479LL - v7;
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      &WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      &asc_1400849C0[v8]);
  }
  v9 = RoInitialize(1, v6);
  if ( v9 < 0 )
  {
    v11 = v9;
    goto LABEL_81;
  }
  pprot = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pprot);
  RunningObjectTable = GetRunningObjectTable(0, &pprot);
  v11 = RunningObjectTable;
  if ( RunningObjectTable >= 0 )
  {
    ppmk = 0;
    v50 = 0;
    switch ( *a2 )
    {
      case 0x17:
        Microsoft::WRL::Details::Make<CCorpDeviceAdminHelper,>(&v47);
        v39 = v47;
        if ( v47 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          v40 = CreateClassMoniker(&GUID_e0ba3bf5_25ef_459f_9ee0_855fd3666692, &ppmk);
          v11 = v40;
          if ( v40 >= 0 )
          {
            v41 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _DWORD *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                    pprot,
                    2,
                    v39,
                    ppmk,
                    &v50);
            v11 = v41;
            if ( v41 >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              ComServerMain();
              v11 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, _QWORD))pprot->lpVtbl->Revoke)(pprot, v50);
            }
          }
        }
        else
        {
          v11 = 14;
        }
        break;
      case 0x1B:
        Microsoft::WRL::Details::Make<CLanguagePackInstaller,>(&v47);
        v36 = v47;
        if ( v47 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          v37 = CreateClassMoniker(&CLSID_LanguagePackInstaller, &ppmk);
          v11 = v37;
          if ( v37 >= 0 )
          {
            v38 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _DWORD *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                    pprot,
                    3,
                    v36,
                    ppmk,
                    &v50);
            v11 = v38;
            if ( v38 >= 0 )
            {
              v36[6] = v50;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              ComServerMain();
            }
          }
        }
        else
        {
          v11 = 14;
        }
        break;
      case 0x2C:
        Microsoft::WRL::Details::Make<COptionalFeaturesAdminHelper,>(&v47);
        v33 = v47;
        if ( v47 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          v34 = CreateClassMoniker(&GUID_cecad1b6_9620_4295_93c6_85b305d82ae4, &ppmk);
          v11 = v34;
          if ( v34 >= 0 )
          {
            v35 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _DWORD *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                    pprot,
                    2,
                    v33,
                    ppmk,
                    &v50);
            v11 = v35;
            if ( v35 >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              ComServerMain();
              v11 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, _QWORD))pprot->lpVtbl->Revoke)(pprot, v50);
            }
          }
        }
        else
        {
          v11 = 14;
        }
        break;
      case 0x66:
        Microsoft::WRL::Details::Make<CCleanmgrAdminHelper,>(&v47);
        v30 = v47;
        if ( v47 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          v31 = CreateClassMoniker(&GUID_a7246883_0625_4321_94d2_a9b121e7e63a, &ppmk);
          v11 = v31;
          if ( v31 >= 0 )
          {
            v32 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _DWORD *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                    pprot,
                    2,
                    v30,
                    ppmk,
                    &v50);
            v11 = v32;
            if ( v32 >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              ComServerMain();
              v11 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, _QWORD))pprot->lpVtbl->Revoke)(pprot, v50);
            }
          }
        }
        else
        {
          v11 = 14;
        }
        break;
      case 0x6B:
        Microsoft::WRL::Details::Make<AssignedAccessAdminHelperImpl,>(&v47);
        v27 = v47;
        if ( v47 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          v28 = CreateClassMoniker(&GUID_fe4cf608_415e_4e78_b3d4_f421e52e2c2b, &ppmk);
          v11 = v28;
          if ( v28 >= 0 )
          {
            v29 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _DWORD *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                    pprot,
                    2,
                    v27,
                    ppmk,
                    &v50);
            v11 = v29;
            if ( v29 >= 0 )
            {
              Microsoft::WRL::ComPtr<AssignedAccessAdminHelperImpl>::InternalRelease(&v47);
              ComServerMain();
              v11 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, _QWORD))pprot->lpVtbl->Revoke)(pprot, v50);
            }
          }
        }
        else
        {
          v11 = 14;
        }
        Microsoft::WRL::ComPtr<AssignedAccessAdminHelperImpl>::InternalRelease(&v47);
        goto LABEL_78;
      case 0x75:
        Microsoft::WRL::Details::Make<CStorageAdminHelper,>(&v47);
        v46 = 0;
        v15 = v47;
        if ( !v47 )
        {
          v11 = 14;
          goto LABEL_30;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
        v23 = CreateClassMoniker(&GUID_e2593ae1_78fc_4123_9501_00577f079bfe, &ppmk);
        v11 = v23;
        if ( v23 < 0 )
          goto LABEL_30;
        v24 = **(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v15;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        v25 = v24(v15, &GUID_00000000_0000_0000_c000_000000000046, &v46);
        v11 = v25;
        if ( v25 < 0 )
          goto LABEL_30;
        v26 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, __int64, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                pprot,
                3,
                v46,
                ppmk,
                &v50);
        v11 = v26;
        if ( v26 < 0 )
          goto LABEL_30;
        goto LABEL_34;
      case 0x8A:
        Microsoft::WRL::Details::Make<CLanguageManager,>(&v47);
        v20 = v47;
        if ( v47 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          v21 = CreateClassMoniker(&CLSID_LanguageManager, &ppmk);
          v11 = v21;
          if ( v21 >= 0 )
          {
            v22 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _DWORD *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                    pprot,
                    3,
                    v20,
                    ppmk,
                    &v50);
            v11 = v22;
            if ( v22 >= 0 )
            {
              v20[6] = v50;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              ComServerMain();
            }
          }
        }
        else
        {
          v11 = 14;
        }
        break;
      case 0x8D:
        Microsoft::WRL::Details::Make<CInstalledUpdatesAdminHelper,>(&v47);
        v46 = 0;
        v15 = v47;
        if ( !v47 )
        {
          v11 = 14;
LABEL_30:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
LABEL_78:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          goto LABEL_79;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
        v16 = CreateClassMoniker(&GUID_c4eb3961_23df_4455_bc4a_eadf66a29fe9, &ppmk);
        v11 = v16;
        if ( v16 < 0 )
          goto LABEL_30;
        v17 = **(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v15;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        v18 = v17(v15, &GUID_00000000_0000_0000_c000_000000000046, &v46);
        v11 = v18;
        if ( v18 < 0 )
          goto LABEL_30;
        v19 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, __int64, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                pprot,
                3,
                v46,
                ppmk,
                &v50);
        v11 = v19;
        if ( v19 < 0 )
          goto LABEL_30;
LABEL_34:
        v15[8] = v50;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
        ComServerMain();
        goto LABEL_30;
      default:
        if ( *a2 != 158
          || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerMachineModelRegistration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PerMachineModelRegistration>::GetImpl'::`2'::impl) )
        {
          goto LABEL_78;
        }
        Microsoft::WRL::Details::Make<AIComponentsAdminHelper,>(&v47);
        v12 = v47;
        if ( v47 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppmk);
          v13 = CreateClassMoniker(&GUID_fd1f5005_976d_4555_b728_10b511c18614, &ppmk);
          v11 = v13;
          if ( v13 >= 0 )
          {
            v14 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, __int64, _DWORD *, LPMONIKER, unsigned int *))pprot->lpVtbl->Register)(
                    pprot,
                    2,
                    v12,
                    ppmk,
                    &v50);
            v11 = v14;
            if ( v14 >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              ComServerMain();
              v11 = ((__int64 (__fastcall *)(LPRUNNINGOBJECTTABLE, _QWORD))pprot->lpVtbl->Revoke)(pprot, v50);
            }
          }
        }
        else
        {
          v11 = 14;
        }
        break;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    goto LABEL_78;
  }
LABEL_79:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pprot);
LABEL_81:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v42 = 5 * *(_DWORD *)p_TlsValue;
    if ( v42 > 0x1E1 )
      v43 = 0;
    else
      v43 = 479LL - v42;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      103,
      (unsigned int)&WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      (unsigned int)&asc_1400849C0[v43],
      v11);
  }
  if ( v9 >= 0 )
    RoUninitialize();
  --*(_DWORD *)p_TlsValue;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v51);
}

```

## disassembly

```asm
0x14001f420  mov     [rsp-28h+arg_0], rbx
0x14001f425  push    rbp
0x14001f426  push    rsi
0x14001f427  push    rdi
0x14001f428  push    r14
0x14001f42a  push    r15
0x14001f42c  mov     rbp, rsp
0x14001f42f  sub     rsp, 70h
0x14001f433  mov     rbx, rdx
0x14001f436  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001f43c  call    cs:__imp_TlsGetValue
0x14001f442  mov     r14, rax
0x14001f445  mov     [rbp+arg_18], 0FFFFFFFFh
0x14001f44c  mov     [rbp+TlsValue], 0
0x14001f454  test    rax, rax
0x14001f457  jnz     short loc_14001F476
0x14001f459  lea     r14, [rbp+TlsValue]
0x14001f45d  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001f463  mov     [rbp+arg_18], ecx
0x14001f466  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x14001f46a  call    cs:__imp_TlsSetValue
0x14001f470  mov     [rbp+var_10], r14
0x14001f474  jmp     short loc_14001F47A
0x14001f476  mov     [rbp+var_10], rax
0x14001f47a  inc     dword ptr [r14]
0x14001f47d  lea     rax, WPP_GLOBAL_Control
0x14001f484  mov     r15d, 1DFh
0x14001f48a  lea     rdx, asc_1400849C0; "                                       "...
0x14001f491  mov     r10, cs:WPP_GLOBAL_Control
0x14001f498  cmp     r10, rax
0x14001f49b  jz      short loc_14001F4D7
0x14001f49d  test    byte ptr [r10+1Ch], 80h
0x14001f4a2  jz      short loc_14001F4D7
0x14001f4a4  mov     eax, [r14]
0x14001f4a7  lea     ecx, [rax+rax*4]
0x14001f4aa  cmp     ecx, 1E1h
0x14001f4b0  ja      short loc_14001F4BC
0x14001f4b2  mov     eax, ecx
0x14001f4b4  mov     ecx, r15d
0x14001f4b7  sub     rcx, rax
0x14001f4ba  jmp     short loc_14001F4BE
0x14001f4bc  xor     ecx, ecx
0x14001f4be  lea     r9, [rcx+rdx]
0x14001f4c2  mov     edx, 66h ; 'f'
0x14001f4c7  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x14001f4ce  mov     rcx, [r10+10h]
0x14001f4d2  call    WPP_SF_s
0x14001f4d7  mov     ecx, 1
0x14001f4dc  call    cs:__imp_RoInitialize
0x14001f4e2  mov     edi, eax
0x14001f4e4  mov     [rbp+var_40], eax
0x14001f4e7  test    eax, eax
0x14001f4e9  js      loc_14001FB45
0x14001f4ef  mov     [rbp+pprot], 0
0x14001f4f7  lea     rcx, [rbp+pprot]
0x14001f4fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f500  lea     rdx, [rbp+pprot]; pprot
0x14001f504  xor     ecx, ecx; reserved
0x14001f506  call    cs:__imp_GetRunningObjectTable
0x14001f50c  mov     esi, eax
0x14001f50e  test    eax, eax
0x14001f510  js      loc_14001FB3A
0x14001f516  mov     [rbp+ppmk], 0
0x14001f51e  mov     [rbp+arg_8], 0
0x14001f525  mov     eax, [rbx]
0x14001f527  sub     eax, 17h
0x14001f52a  jz      loc_14001FA9E
0x14001f530  sub     eax, 4
0x14001f533  jz      loc_14001FA16
0x14001f539  sub     eax, 11h
0x14001f53c  jz      loc_14001F980
0x14001f542  sub     eax, 3Ah ; ':'
0x14001f545  jz      loc_14001F8EA
0x14001f54b  sub     eax, 5
0x14001f54e  jz      loc_14001F854
0x14001f554  sub     eax, 0Ah
0x14001f557  jz      loc_14001F77F
0x14001f55d  sub     eax, 15h
0x14001f560  jz      loc_14001F6F7
0x14001f566  sub     eax, 3
0x14001f569  jz      loc_14001F622
0x14001f56f  cmp     eax, 11h
0x14001f572  jnz     loc_14001FB30
0x14001f578  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerMachineModelRegistration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerMachineModelRegistration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerMachineModelRegistration> `wil::Feature<__WilFeatureTraits_Feature_PerMachineModelRegistration>::GetImpl(void)'::`2'::impl
0x14001f57f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PerMachineModelRegistration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerMachineModelRegistration>::__private_IsEnabled(void)
0x14001f584  test    al, al
0x14001f586  jz      loc_14001FB30
0x14001f58c  lea     rcx, [rbp+var_20]
0x14001f590  call    ??$Make@VAIComponentsAdminHelper@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAIComponentsAdminHelper@@@12@XZ; Microsoft::WRL::Details::Make<AIComponentsAdminHelper,>(void)
0x14001f595  nop
0x14001f596  mov     rbx, [rbp+var_20]
0x14001f59a  test    rbx, rbx
0x14001f59d  jnz     short loc_14001F5A6
0x14001f59f  mov     esi, 8007000Eh
0x14001f5a4  jmp     short loc_14001F614
0x14001f5a6  lea     rcx, [rbp+ppmk]
0x14001f5aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f5af  lea     rdx, [rbp+ppmk]; ppmk
0x14001f5b3  lea     rcx, _GUID_fd1f5005_976d_4555_b728_10b511c18614; rclsid
0x14001f5ba  call    cs:__imp_CreateClassMoniker
0x14001f5c0  mov     esi, eax
0x14001f5c2  test    eax, eax
0x14001f5c4  js      short loc_14001F614
0x14001f5c6  mov     rcx, [rbp+pprot]
0x14001f5ca  mov     rax, [rcx]
0x14001f5cd  lea     rdx, [rbp+arg_8]
0x14001f5d1  mov     [rsp+70h+var_50], rdx
0x14001f5d6  mov     r9, [rbp+ppmk]
0x14001f5da  mov     r8, rbx
0x14001f5dd  mov     edx, 2
0x14001f5e2  mov     rax, [rax+18h]
0x14001f5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5eb  mov     esi, eax
0x14001f5ed  test    eax, eax
0x14001f5ef  js      short loc_14001F614
0x14001f5f1  lea     rcx, [rbp+var_20]
0x14001f5f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f5fa  call    ?ComServerMain@@YAXXZ; ComServerMain(void)
0x14001f5ff  mov     rcx, [rbp+pprot]
0x14001f603  mov     rax, [rcx]
0x14001f606  mov     edx, [rbp+arg_8]
0x14001f609  mov     rax, [rax+20h]
0x14001f60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f612  mov     esi, eax
0x14001f614  lea     rcx, [rbp+var_20]
0x14001f618  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f61d  jmp     loc_14001FB30
0x14001f622  lea     rcx, [rbp+var_20]
0x14001f626  call    ??$Make@VCInstalledUpdatesAdminHelper@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInstalledUpdatesAdminHelper@@@12@XZ; Microsoft::WRL::Details::Make<CInstalledUpdatesAdminHelper,>(void)
0x14001f62b  nop
0x14001f62c  mov     [rbp+var_28], 0
0x14001f634  mov     rbx, [rbp+var_20]
0x14001f638  test    rbx, rbx
0x14001f63b  jnz     short loc_14001F65A
0x14001f63d  mov     esi, 8007000Eh
0x14001f642  lea     rcx, [rbp+var_28]
0x14001f646  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f64b  nop
0x14001f64c  lea     rcx, [rbp+var_20]
0x14001f650  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f655  jmp     loc_14001FB30
0x14001f65a  lea     rcx, [rbp+ppmk]
0x14001f65e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f663  lea     rdx, [rbp+ppmk]; ppmk
0x14001f667  lea     rcx, _GUID_c4eb3961_23df_4455_bc4a_eadf66a29fe9; rclsid
0x14001f66e  call    cs:__imp_CreateClassMoniker
0x14001f674  mov     esi, eax
0x14001f676  test    eax, eax
0x14001f678  js      short loc_14001F642
0x14001f67a  mov     rax, [rbx]
0x14001f67d  mov     rsi, [rax]
0x14001f680  lea     rcx, [rbp+var_28]
0x14001f684  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f689  lea     r8, [rbp+var_28]
0x14001f68d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14001f694  mov     rcx, rbx
0x14001f697  mov     rax, rsi
0x14001f69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f69f  mov     esi, eax
0x14001f6a1  test    eax, eax
0x14001f6a3  js      short loc_14001F642
0x14001f6a5  mov     rcx, [rbp+pprot]
0x14001f6a9  mov     rax, [rcx]
0x14001f6ac  lea     rdx, [rbp+arg_8]
0x14001f6b0  mov     [rsp+70h+var_50], rdx
0x14001f6b5  mov     r9, [rbp+ppmk]
0x14001f6b9  mov     r8, [rbp+var_28]
0x14001f6bd  mov     edx, 3
0x14001f6c2  mov     rax, [rax+18h]
0x14001f6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f6cb  mov     esi, eax
0x14001f6cd  test    eax, eax
0x14001f6cf  js      loc_14001F642
0x14001f6d5  mov     eax, [rbp+arg_8]
0x14001f6d8  mov     [rbx+20h], eax
0x14001f6db  lea     rcx, [rbp+var_28]
0x14001f6df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f6e4  lea     rcx, [rbp+var_20]
0x14001f6e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f6ed  call    ?ComServerMain@@YAXXZ; ComServerMain(void)
0x14001f6f2  jmp     loc_14001F642
0x14001f6f7  lea     rcx, [rbp+var_20]
0x14001f6fb  call    ??$Make@VCLanguageManager@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCLanguageManager@@@12@XZ; Microsoft::WRL::Details::Make<CLanguageManager,>(void)
0x14001f700  nop
0x14001f701  mov     rbx, [rbp+var_20]
0x14001f705  test    rbx, rbx
0x14001f708  jnz     short loc_14001F711
0x14001f70a  mov     esi, 8007000Eh
0x14001f70f  jmp     short loc_14001F771
0x14001f711  lea     rcx, [rbp+ppmk]
0x14001f715  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f71a  lea     rdx, [rbp+ppmk]; ppmk
0x14001f71e  lea     rcx, CLSID_LanguageManager; rclsid
0x14001f725  call    cs:__imp_CreateClassMoniker
0x14001f72b  mov     esi, eax
0x14001f72d  test    eax, eax
0x14001f72f  js      short loc_14001F771
0x14001f731  mov     rcx, [rbp+pprot]
0x14001f735  mov     rax, [rcx]
0x14001f738  lea     rdx, [rbp+arg_8]
0x14001f73c  mov     [rsp+70h+var_50], rdx
0x14001f741  mov     r9, [rbp+ppmk]
0x14001f745  mov     r8, rbx
0x14001f748  mov     edx, 3
0x14001f74d  mov     rax, [rax+18h]
0x14001f751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f756  mov     esi, eax
0x14001f758  test    eax, eax
0x14001f75a  js      short loc_14001F771
0x14001f75c  mov     eax, [rbp+arg_8]
0x14001f75f  mov     [rbx+18h], eax
0x14001f762  lea     rcx, [rbp+var_20]
0x14001f766  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f76b  call    ?ComServerMain@@YAXXZ; ComServerMain(void)
0x14001f770  nop
0x14001f771  lea     rcx, [rbp+var_20]
0x14001f775  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f77a  jmp     loc_14001FB30
0x14001f77f  lea     rcx, [rbp+var_20]
0x14001f783  call    ??$Make@VCStorageAdminHelper@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCStorageAdminHelper@@@12@XZ; Microsoft::WRL::Details::Make<CStorageAdminHelper,>(void)
0x14001f788  nop
0x14001f789  mov     [rbp+var_28], 0
0x14001f791  mov     rbx, [rbp+var_20]
0x14001f795  test    rbx, rbx
0x14001f798  jnz     short loc_14001F7B7
0x14001f79a  mov     esi, 8007000Eh
0x14001f79f  lea     rcx, [rbp+var_28]
0x14001f7a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f7a8  nop
0x14001f7a9  lea     rcx, [rbp+var_20]
0x14001f7ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f7b2  jmp     loc_14001FB30
0x14001f7b7  lea     rcx, [rbp+ppmk]
0x14001f7bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f7c0  lea     rdx, [rbp+ppmk]; ppmk
0x14001f7c4  lea     rcx, _GUID_e2593ae1_78fc_4123_9501_00577f079bfe; rclsid
0x14001f7cb  call    cs:__imp_CreateClassMoniker
0x14001f7d1  mov     esi, eax
0x14001f7d3  test    eax, eax
0x14001f7d5  js      short loc_14001F79F
0x14001f7d7  mov     rax, [rbx]
0x14001f7da  mov     rsi, [rax]
0x14001f7dd  lea     rcx, [rbp+var_28]
0x14001f7e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f7e6  lea     r8, [rbp+var_28]
0x14001f7ea  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14001f7f1  mov     rcx, rbx
0x14001f7f4  mov     rax, rsi
0x14001f7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f7fc  mov     esi, eax
0x14001f7fe  test    eax, eax
0x14001f800  js      short loc_14001F79F
0x14001f802  mov     rcx, [rbp+pprot]
0x14001f806  mov     rax, [rcx]
0x14001f809  lea     rdx, [rbp+arg_8]
0x14001f80d  mov     [rsp+70h+var_50], rdx
0x14001f812  mov     r9, [rbp+ppmk]
0x14001f816  mov     r8, [rbp+var_28]
0x14001f81a  mov     edx, 3
0x14001f81f  mov     rax, [rax+18h]
0x14001f823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f828  mov     esi, eax
0x14001f82a  test    eax, eax
0x14001f82c  js      loc_14001F79F
0x14001f832  mov     eax, [rbp+arg_8]
0x14001f835  mov     [rbx+20h], eax
0x14001f838  lea     rcx, [rbp+var_28]
0x14001f83c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f841  lea     rcx, [rbp+var_20]
0x14001f845  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f84a  call    ?ComServerMain@@YAXXZ; ComServerMain(void)
0x14001f84f  jmp     loc_14001F79F
0x14001f854  lea     rcx, [rbp+var_20]
0x14001f858  call    ??$Make@VAssignedAccessAdminHelperImpl@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAssignedAccessAdminHelperImpl@@@12@XZ; Microsoft::WRL::Details::Make<AssignedAccessAdminHelperImpl,>(void)
0x14001f85d  nop
0x14001f85e  mov     rbx, [rbp+var_20]
0x14001f862  test    rbx, rbx
0x14001f865  jnz     short loc_14001F86E
0x14001f867  mov     esi, 8007000Eh
0x14001f86c  jmp     short loc_14001F8DC
0x14001f86e  lea     rcx, [rbp+ppmk]
0x14001f872  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001f877  lea     rdx, [rbp+ppmk]; ppmk
0x14001f87b  lea     rcx, _GUID_fe4cf608_415e_4e78_b3d4_f421e52e2c2b; rclsid
0x14001f882  call    cs:__imp_CreateClassMoniker
0x14001f888  mov     esi, eax
0x14001f88a  test    eax, eax
0x14001f88c  js      short loc_14001F8DC
0x14001f88e  mov     rcx, [rbp+pprot]
0x14001f892  mov     rax, [rcx]
0x14001f895  lea     rdx, [rbp+arg_8]
0x14001f899  mov     [rsp+70h+var_50], rdx
0x14001f89e  mov     r9, [rbp+ppmk]
0x14001f8a2  mov     r8, rbx
0x14001f8a5  mov     edx, 2
0x14001f8aa  mov     rax, [rax+18h]
0x14001f8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f8b3  mov     esi, eax
0x14001f8b5  test    eax, eax
0x14001f8b7  js      short loc_14001F8DC
  ... truncated ...
```
