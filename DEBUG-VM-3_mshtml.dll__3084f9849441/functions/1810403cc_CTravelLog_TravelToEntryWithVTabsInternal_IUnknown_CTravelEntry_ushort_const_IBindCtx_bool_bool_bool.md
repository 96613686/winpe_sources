# CTravelLog::_TravelToEntryWithVTabsInternal(IUnknown *,CTravelEntry *,ushort const *,IBindCtx *,bool,bool,bool)

- ea: `0x1810403cc`
- end: `0x18104096a`
- name: `?_TravelToEntryWithVTabsInternal@CTravelLog@@IEAAJPEAUIUnknown@@PEAVCTravelEntry@@PEBGPEAUIBindCtx@@_N44@Z`
- size: `1438`
- prototype: `__int64 __fastcall(CTravelLog *__hidden this, struct IUnknown *, struct CTravelEntry *, const unsigned __int16 *, struct IBindCtx *, bool, bool, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18103fdc8`

## callees

- `0x1801af6e0`
- `0x1801b0510`
- `0x180300074`
- `0x1805ec7d8`
- `0x18103bd64`
- `0x18103fbc8`
- `0x1810403cc`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1810406e2`
- `KERNEL32!GetCurrentProcessId` at `0x1810406e2`
- `USER32!AllowSetForegroundWindow` at `0x1810407cd`
- `USER32!AllowSetForegroundWindow` at `0x1810407cd`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18104078e`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18104078e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181040707`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x181040707`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18104076a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18104076a`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1810405be`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x1810405be`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x181040713`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x181040859`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x181040713`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x181040859`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1810406f0`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1810406f0`
- `OLEAUT32!__imp_SysAllocString` at `0x18104066a`
- `OLEAUT32!__imp_SysAllocString` at `0x181040775`
- `OLEAUT32!__imp_SysAllocString` at `0x18104066a`
- `OLEAUT32!__imp_SysAllocString` at `0x181040775`
- `OLEAUT32!__imp_SysFreeString` at `0x1810408fe`
- `OLEAUT32!__imp_SysFreeString` at `0x181040908`
- `OLEAUT32!__imp_SysFreeString` at `0x1810408fe`
- `OLEAUT32!__imp_SysFreeString` at `0x181040908`
- `OLEAUT32!__imp_VariantInit` at `0x181040542`
- `OLEAUT32!__imp_VariantInit` at `0x181040567`
- `OLEAUT32!__imp_VariantInit` at `0x181040624`
- `OLEAUT32!__imp_VariantInit` at `0x181040542`
- `OLEAUT32!__imp_VariantInit` at `0x181040567`
- `OLEAUT32!__imp_VariantInit` at `0x181040624`
- `OLEAUT32!__imp_VariantClear` at `0x18104060d`
- `OLEAUT32!__imp_VariantClear` at `0x181040678`
- `OLEAUT32!__imp_VariantClear` at `0x18104060d`
- `OLEAUT32!__imp_VariantClear` at `0x181040678`

## pseudocode

```c
__int64 __fastcall CTravelLog::_TravelToEntryWithVTabsInternal(
        struct CTravelEntry **this,
        struct IUnknown *a2,
        struct CTravelEntry *a3,
        const unsigned __int16 *a4,
        struct IBindCtx *a5,
        bool a6,
        bool a7,
        bool a8)
{
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // rcx
  int v14; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  LONG lVal; // r15d
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v18; // rax
  int v19; // eax
  char v20; // bl
  struct CTravelEntry *v21; // rcx
  struct CTravelEntry *v22; // rcx
  OLECHAR *v23; // rax
  int v24; // ebx
  DWORD v25; // ecx
  void (__fastcall *v26)(__int64, _QWORD *); // rbx
  __int64 v28; // [rsp+48h] [rbp-C0h] BYREF
  DWORD dwProcessId[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-B0h] BYREF
  struct IEUserBroker *v31; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD psz[3]; // [rsp+70h] [rbp-98h] BYREF
  void *ppvOut; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v35; // [rsp+90h] [rbp-78h] BYREF
  VARIANTARG v36; // [rsp+A8h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-48h] BYREF
  BSTR bstrString[10]; // [rsp+D8h] [rbp-30h] BYREF
  BSTR v39; // [rsp+128h] [rbp+20h]
  _DWORD v40[3]; // [rsp+168h] [rbp+60h] BYREF
  __int64 v41; // [rsp+174h] [rbp+6Ch]
  int v42; // [rsp+17Ch] [rbp+74h]
  __int128 v43; // [rsp+180h] [rbp+78h]
  _DWORD v44[10]; // [rsp+190h] [rbp+88h] BYREF

  psz[1] = a4;
  Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
    "CTravelLog::_TravelToEntryWithVTabsInternal - STARTS TravelLog=0x%08lX",
    (_DWORD)this);
  if ( a2 )
  {
    if ( !*((_BYTE *)this + 160) )
      CTravelLog::_PrepTravelLogForVirtualTabSwitch((CTravelLog *)this, a2, a7);
    v11 = *((unsigned int *)this + 37);
    *((_BYTE *)this + 160) = 0;
    v32 = 0;
    if ( (_DWORD)v11 && (unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(v11, 0, 0, 0) )
    {
      v12 = -2147467263;
    }
    else
    {
      v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_d2649e5e_e1a3_4255_b764_d7531a794042,
              &v32);
      if ( v12 >= 0 )
      {
        v13 = v32;
        dwProcessId[0] = 0;
        if ( v32 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v32 + 24LL))(v32, dwProcessId);
          v13 = v32;
          v12 = v14;
        }
        if ( v12 >= 0 )
        {
          memset_0(bstrString, 0, 0x90u);
          lpVtbl = a2->lpVtbl;
          v28 = 0;
          lVal = 0;
          QueryInterface = lpVtbl->QueryInterface;
          v18 = TSmartPointer<ID3D11Device>::operator&(&v28);
          v19 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64))QueryInterface)(
                  a2,
                  &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
                  v18);
          v20 = 0;
          if ( v19 < 0 )
            goto LABEL_25;
          if ( *((_DWORD *)a3 + 20)
            && ((memset(&pvarg, 0, sizeof(pvarg)),
                 VariantInit(&pvarg),
                 pvarg.vt = 19,
                 pvarg.lVal = *((_DWORD *)a3 + 20),
                 memset(&v35, 0, sizeof(v35)),
                 VariantInit(&v35),
                 (*(int (__fastcall **)(__int64, GUID *, __int64, __int64, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v28 + 32LL))(
                   v28,
                   &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                   79,
                   0x4000,
                   &pvarg,
                   &v35) >= 0)
             || v35.vt == 3 && v35.lVal == -2147467260) )
          {
            v20 = 1;
          }
          else if ( LCIEIsComponentSharedFlagValueSet_FromComponentThread(4u) )
          {
            memset(&v35, 0, sizeof(v35));
            if ( (*(int (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v28 + 32LL))(
                   v28,
                   &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                   82) >= 0 )
              lVal = v35.lVal;
            VariantClear(&v35);
          }
          memset(&v36, 0, sizeof(v36));
          VariantInit(&v36);
          if ( (*(int (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v28 + 32LL))(v28, &CGID_Explorer, 120) >= 0
            && v36.vt == 8 )
          {
            v39 = SysAllocString(v36.bstrVal);
            VariantClear(&v36);
          }
          if ( !v20 )
          {
LABEL_25:
            if ( a8 )
            {
              v12 = -2147024809;
            }
            else
            {
              v21 = this[9];
              v40[0] = dwProcessId[0];
              v40[1] = (a6 << 18) + 0x4000;
              v40[2] = FindDistance(v21, a3);
              memset(v44, 0, 28);
              v41 = 0;
              v42 = 0;
              v43 = 0;
              LODWORD(v43) = GetCurrentProcessId();
              *(_QWORD *)((char *)&v43 + 4) = IsoGetIntegrity(1) & 0x7F;
              v44[0] = IEConfiguration_GetDWORD(536870929);
              *(_OWORD *)&v44[3] = *(_OWORD *)GlobalThreadState();
              if ( a7 )
              {
                v22 = this[9];
                if ( v22 )
                  v44[2] = (*(__int64 (__fastcall **)(struct CTravelEntry *))(*(_QWORD *)v22 + 240LL))(v22);
              }
              v44[1] = lVal;
              ppvOut = 0;
              IUnknown_QueryService(a2, &IID_IWebBrowserApp, &GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00, &ppvOut);
              v23 = SysAllocString((const OLECHAR *)psz[1]);
              v30 = 0;
              bstrString[0] = v23;
              v31 = 0;
              v24 = CoCreateUserBroker(&v31);
              if ( v24 >= 0 )
              {
                dwProcessId[1] = 0;
                (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v31 + 24LL))(
                  v31,
                  0,
                  0,
                  &dwProcessId[1]);
                v25 = -1;
                if ( dwProcessId[1] )
                  v25 = dwProcessId[1];
                AllowSetForegroundWindow(v25);
                psz[1] = 0;
                v24 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, _QWORD *))(*(_QWORD *)v31 + 48LL))(
                        v31,
                        &CLSID_CShdocvwBroker,
                        &IID_IUnknown,
                        &psz[1]);
                if ( v24 >= 0 )
                {
                  v24 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))psz[1])(
                          psz[1],
                          &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                          &v30);
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)psz[1] + 16LL))(psz[1]);
                }
                (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v31 + 16LL))(v31);
                if ( v24 >= 0 )
                {
                  v26 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v30 + 1256LL);
                  *(_OWORD *)&psz[1] = *(_OWORD *)GlobalThreadState();
                  v26(v30, &psz[1]);
                  v24 = (*(__int64 (__fastcall **)(__int64, BSTR *, _DWORD *, void *))(*(_QWORD *)v30 + 40LL))(
                          v30,
                          bstrString,
                          v40,
                          ppvOut);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                }
              }
              v12 = 0;
              if ( v24 != -2147467260 )
                v12 = v24;
              if ( lVal )
                (*(void (__fastcall **)(__int64, GUID *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v28 + 32LL))(
                  v28,
                  &GUID_a11452bc_e055_4e56_a151_7b16dbb4544e,
                  83,
                  0,
                  0,
                  0);
              if ( ppvOut )
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
            }
          }
          SysFreeString(bstrString[0]);
          SysFreeString(v39);
          TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(&v28);
          v13 = v32;
        }
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
  }
  else
  {
    v12 = -2147418113;
  }
  Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(
    "CTravelLog::_TravelToEntryWithVTabsInternal - ENDS TravelLog=0x%08lX hr=0x%08lX",
    (_DWORD)this,
    v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1810403cc  mov     rax, rsp
0x1810403cf  mov     [rax+20h], r9
0x1810403d3  mov     [rax+18h], r8
0x1810403d7  mov     [rax+10h], rdx
0x1810403db  mov     [rax+8], rcx
0x1810403df  push    rbp
0x1810403e0  push    rbx
0x1810403e1  push    rsi
0x1810403e2  push    rdi
0x1810403e3  push    r13
0x1810403e5  push    r14
0x1810403e7  push    r15
0x1810403e9  lea     rbp, [rax-0F8h]
0x1810403f0  sub     rsp, 1C0h
0x1810403f7  mov     rax, cs:__security_cookie
0x1810403fe  xor     rax, rsp
0x181040401  mov     [rbp+0F0h+var_40], rax
0x181040408  mov     rax, [rbp+0F0h+arg_18]
0x18104040f  lea     rcx, aCtravellogTrav_2; "CTravelLog::_TravelToEntryWithVTabsInte"...
0x181040416  mov     rsi, [rbp+0F0h+arg_0]
0x18104041d  mov     r14, [rbp+0F0h+punk]
0x181040424  mov     rdx, rsi
0x181040427  mov     r13, [rbp+0F0h+arg_10]
0x18104042e  mov     qword ptr [rsp+1F0h+psz+8], rax
0x181040433  call    ?RaiseEvent@?$VectorOptions@PEAUHSTRING__@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,0,0,0>::RaiseEvent(...)
0x181040438  xor     ebx, ebx
0x18104043a  test    r14, r14
0x18104043d  jz      loc_181040930
0x181040443  cmp     [rsi+0A0h], bl
0x181040449  jnz     short loc_18104045D
0x18104044b  mov     r8b, [rbp+0F0h+arg_30]; bool
0x181040452  mov     rdx, r14; struct IUnknown *
0x181040455  mov     rcx, rsi; this
0x181040458  call    ?_PrepTravelLogForVirtualTabSwitch@CTravelLog@@IEAAJPEAUIUnknown@@_N@Z; CTravelLog::_PrepTravelLogForVirtualTabSwitch(IUnknown *,bool)
0x18104045d  mov     ecx, [rsi+94h]
0x181040463  mov     [rsi+0A0h], bl
0x181040469  mov     [rsp+1F0h+var_190], rbx
0x18104046e  test    ecx, ecx
0x181040470  jz      short loc_18104048D
0x181040472  xor     r9d, r9d
0x181040475  xor     r8d, r8d
0x181040478  xor     edx, edx
0x18104047a  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x18104047f  test    al, al
0x181040481  jz      short loc_18104048D
0x181040483  mov     edi, 80004001h
0x181040488  jmp     loc_181040935
0x18104048d  mov     rax, [r14]
0x181040490  lea     r8, [rsp+1F0h+var_190]
0x181040495  lea     rdx, _GUID_d2649e5e_e1a3_4255_b764_d7531a794042
0x18104049c  mov     rcx, r14
0x18104049f  mov     rax, [rax]
0x1810404a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810404a7  mov     edi, eax
0x1810404a9  test    eax, eax
0x1810404ab  js      loc_181040935
0x1810404b1  mov     rcx, [rsp+1F0h+var_190]
0x1810404b6  mov     [rsp+1F0h+dwProcessId], ebx
0x1810404ba  test    rcx, rcx
0x1810404bd  jz      short loc_1810404D7
0x1810404bf  mov     rax, [rcx]
0x1810404c2  lea     rdx, [rsp+1F0h+dwProcessId]
0x1810404c7  mov     rax, [rax+18h]
0x1810404cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810404d0  mov     rcx, [rsp+1F0h+var_190]
0x1810404d5  mov     edi, eax
0x1810404d7  test    edi, edi
0x1810404d9  js      loc_18104091D
0x1810404df  xor     edx, edx; Val
0x1810404e1  lea     rcx, [rbp+0F0h+bstrString]; void *
0x1810404e5  mov     r8d, 90h; Size
0x1810404eb  call    memset_0
0x1810404f0  mov     rax, [r14]
0x1810404f3  lea     rcx, [rsp+1F0h+var_1B0]
0x1810404f8  mov     qword ptr [rsp+1F0h+var_1B0], rbx
0x1810404fd  mov     r15d, ebx
0x181040500  mov     rbx, [rax]
0x181040503  call    ??I?$TSmartPointer@UID3D11Device@@@@QEAAPEAPEAUID3D11Device@@XZ; TSmartPointer<ID3D11Device>::operator&(void)
0x181040508  mov     r8, rax
0x18104050b  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x181040512  mov     rax, rbx
0x181040515  mov     rcx, r14
0x181040518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18104051d  xor     ebx, ebx
0x18104051f  test    eax, eax
0x181040521  js      loc_181040688
0x181040527  cmp     [r13+50h], ebx
0x18104052b  jz      loc_1810405B9
0x181040531  xorps   xmm0, xmm0
0x181040534  lea     rcx, [rbp+0F0h+pvarg]; pvarg
0x181040538  xor     eax, eax
0x18104053a  movups  xmmword ptr [rbp+0F0h+pvarg], xmm0
0x18104053e  mov     qword ptr [rbp+0F0h+pvarg+10h], rax
0x181040542  call    cs:__imp_VariantInit
0x181040548  lea     eax, [rbx+13h]
0x18104054b  xorps   xmm0, xmm0
0x18104054e  mov     word ptr [rbp+0F0h+pvarg], ax
0x181040552  lea     rcx, [rbp+0F0h+var_168]; pvarg
0x181040556  mov     eax, [r13+50h]
0x18104055a  mov     dword ptr [rbp+0F0h+pvarg+8], eax
0x18104055d  xor     eax, eax
0x18104055f  mov     qword ptr [rbp+0F0h+var_168+10h], rax
0x181040563  movups  xmmword ptr [rbp+0F0h+var_168], xmm0
0x181040567  call    cs:__imp_VariantInit
0x18104056d  mov     rcx, qword ptr [rsp+1F0h+var_1B0]
0x181040572  lea     rdx, [rbp+0F0h+var_168]
0x181040576  mov     [rsp+28h], rdx
0x18104057b  lea     r8d, [rbx+4Fh]
0x18104057f  lea     rdx, [rbp+0F0h+pvarg]
0x181040583  mov     r9d, 4000h
0x181040589  mov     [rsp+1F0h+var_1D0], rdx
0x18104058e  lea     rdx, _GUID_a11452bc_e055_4e56_a151_7b16dbb4544e
0x181040595  mov     rax, [rcx]
0x181040598  mov     rax, [rax+20h]
0x18104059c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810405a1  test    eax, eax
0x1810405a3  jns     short loc_1810405B5
0x1810405a5  cmp     word ptr [rbp+0F0h+var_168], 3
0x1810405aa  jnz     short loc_1810405B9
0x1810405ac  cmp     dword ptr [rbp+0F0h+var_168+8], 80004004h
0x1810405b3  jnz     short loc_1810405B9
0x1810405b5  mov     bl, 1
0x1810405b7  jmp     short loc_181040613
0x1810405b9  mov     ecx, 4
0x1810405be  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x1810405c4  test    eax, eax
0x1810405c6  jz      short loc_181040613
0x1810405c8  mov     rcx, qword ptr [rsp+1F0h+var_1B0]
0x1810405cd  lea     rdx, [rbp+0F0h+var_168]
0x1810405d1  xor     eax, eax
0x1810405d3  mov     [rsp+28h], rdx
0x1810405d8  mov     qword ptr [rbp+0F0h+var_168+10h], rax
0x1810405dc  lea     rdx, _GUID_a11452bc_e055_4e56_a151_7b16dbb4544e
0x1810405e3  xorps   xmm0, xmm0
0x1810405e6  mov     [rsp+1F0h+var_1D0], rbx
0x1810405eb  movups  xmmword ptr [rbp+0F0h+var_168], xmm0
0x1810405ef  mov     rax, [rcx]
0x1810405f2  xor     r9d, r9d
0x1810405f5  mov     rax, [rax+20h]
0x1810405f9  lea     r8d, [r9+52h]
0x1810405fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181040602  test    eax, eax
0x181040604  lea     rcx, [rbp+0F0h+var_168]; pvarg
0x181040608  cmovns  r15d, dword ptr [rbp+0F0h+var_168+8]
0x18104060d  call    cs:__imp_VariantClear
0x181040613  xorps   xmm0, xmm0
0x181040616  lea     rcx, [rbp+0F0h+var_150]; pvarg
0x18104061a  xor     eax, eax
0x18104061c  movups  xmmword ptr [rbp+0F0h+var_150], xmm0
0x181040620  mov     qword ptr [rbp+0F0h+var_150+10h], rax
0x181040624  call    cs:__imp_VariantInit
0x18104062a  mov     rcx, qword ptr [rsp+1F0h+var_1B0]
0x18104062f  lea     rdx, [rbp+0F0h+var_150]
0x181040633  mov     [rsp+28h], rdx
0x181040638  xor     r9d, r9d
0x18104063b  lea     rdx, CGID_Explorer
0x181040642  mov     [rsp+1F0h+var_1D0], 0
0x18104064b  mov     rax, [rcx]
0x18104064e  lea     r8d, [r9+78h]
0x181040652  mov     rax, [rax+20h]
0x181040656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18104065b  test    eax, eax
0x18104065d  js      short loc_18104067E
0x18104065f  cmp     word ptr [rbp+0F0h+var_150], 8
0x181040664  jnz     short loc_18104067E
0x181040666  mov     rcx, qword ptr [rbp+0F0h+var_150+8]; psz
0x18104066a  call    cs:__imp_SysAllocString
0x181040670  lea     rcx, [rbp+0F0h+var_150]; pvarg
0x181040674  mov     [rbp+0F0h+var_D0], rax
0x181040678  call    cs:__imp_VariantClear
0x18104067e  test    bl, bl
0x181040680  jnz     loc_1810408FA
0x181040686  xor     ebx, ebx
0x181040688  cmp     [rbp+0F0h+arg_38], bl
0x18104068e  jz      short loc_18104069A
0x181040690  mov     edi, 80070057h
0x181040695  jmp     loc_1810408FA
0x18104069a  mov     eax, [rsp+1F0h+dwProcessId]
0x18104069e  mov     rdx, r13; struct CTravelEntry *
0x1810406a1  mov     rcx, [rsi+48h]; struct CTravelEntry *
0x1810406a5  mov     [rbp+0F0h+var_90], eax
0x1810406a8  movzx   eax, [rbp+0F0h+arg_28]
0x1810406af  shl     eax, 12h
0x1810406b2  add     eax, 4000h
0x1810406b7  mov     [rbp+0F0h+var_8C], eax
0x1810406ba  call    ?FindDistance@@YAHPEAVCTravelEntry@@PEBV1@@Z; FindDistance(CTravelEntry *,CTravelEntry const *)
0x1810406bf  xorps   xmm0, xmm0
0x1810406c2  mov     [rbp+0F0h+var_88], eax
0x1810406c5  movups  xmmword ptr [rbp+0F0h+var_68], xmm0
0x1810406cc  mov     [rbp+0F0h+var_84], 0
0x1810406d4  movups  xmmword ptr [rbp+0F0h+var_68+0Ch], xmm0
0x1810406db  mov     [rbp+0F0h+var_7C], ebx
0x1810406de  movups  [rbp+0F0h+var_78], xmm0
0x1810406e2  call    cs:__imp_GetCurrentProcessId
0x1810406e8  mov     ecx, 1
0x1810406ed  mov     dword ptr [rbp+0F0h+var_78], eax
0x1810406f0  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1810406f6  mov     ecx, 20000011h
0x1810406fb  mov     dword ptr [rbp+0F0h+var_78+8], ebx
0x181040701  and     eax, 7Fh
0x181040704  mov     dword ptr [rbp+0F0h+var_78+4], eax
0x181040707  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18104070d  mov     [rbp+0F0h+var_68], eax
0x181040713  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x181040719  movups  xmm0, xmmword ptr [rax]
0x18104071c  movdqu  xmmword ptr [rbp+0F0h+var_68+0Ch], xmm0
0x181040724  cmp     [rbp+0F0h+arg_30], bl
0x18104072a  jz      short loc_18104074A
0x18104072c  mov     rcx, [rsi+48h]
0x181040730  test    rcx, rcx
0x181040733  jz      short loc_18104074A
0x181040735  mov     rax, [rcx]
0x181040738  mov     rax, [rax+0F0h]
0x18104073f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181040744  mov     [rbp+0F0h+var_68+8], eax
0x18104074a  lea     r9, [rbp+0F0h+ppvOut]; ppvOut
0x18104074e  mov     [rbp+0F0h+var_68+4], r15d
0x181040755  lea     r8, _GUID_5a625ea4_a89f_4eb2_a45a_9ad4e37d4b00; riid
0x18104075c  mov     [rbp+0F0h+ppvOut], rbx
0x181040760  lea     rdx, IID_IWebBrowserApp; guidService
0x181040767  mov     rcx, r14; punk
0x18104076a  call    cs:__imp_IUnknown_QueryService
0x181040770  mov     rcx, qword ptr [rsp+1F0h+psz+8]; psz
0x181040775  call    cs:__imp_SysAllocString
0x18104077b  lea     rcx, [rsp+1F0h+var_198]
0x181040780  mov     [rsp+1F0h+var_1A0], rbx
0x181040785  mov     [rbp+0F0h+bstrString], rax
0x181040789  mov     [rsp+1F0h+var_198], rbx
0x18104078e  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x181040794  mov     ebx, eax
0x181040796  test    eax, eax
0x181040798  js      loc_1810408AA
0x18104079e  mov     rcx, [rsp+1F0h+var_198]
0x1810407a3  lea     r9, [rsp+1F0h+dwProcessId+4]
0x1810407a8  mov     [rsp+1F0h+dwProcessId+4], 0
0x1810407b0  xor     r8d, r8d
0x1810407b3  xor     edx, edx
0x1810407b5  mov     rax, [rcx]
0x1810407b8  mov     rax, [rax+18h]
0x1810407bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810407c1  mov     eax, [rsp+1F0h+dwProcessId+4]
0x1810407c5  or      ecx, 0FFFFFFFFh
0x1810407c8  test    eax, eax
0x1810407ca  cmovnz  ecx, eax; dwProcessId
0x1810407cd  call    cs:__imp_AllowSetForegroundWindow
0x1810407d3  mov     rcx, [rsp+1F0h+var_198]
0x1810407d8  lea     r9, [rsp+1F0h+psz+8]
0x1810407dd  mov     qword ptr [rsp+1F0h+psz+8], 0
0x1810407e6  lea     r8, IID_IUnknown
0x1810407ed  lea     rdx, CLSID_CShdocvwBroker
0x1810407f4  mov     rax, [rcx]
0x1810407f7  mov     rax, [rax+30h]
0x1810407fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181040800  mov     ebx, eax
0x181040802  test    eax, eax
0x181040804  js      short loc_181040835
0x181040806  mov     rcx, qword ptr [rsp+1F0h+psz+8]
0x18104080b  lea     r8, [rsp+1F0h+var_1A0]
0x181040810  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x181040817  mov     rax, [rcx]
0x18104081a  mov     rax, [rax]
0x18104081d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181040822  mov     rcx, qword ptr [rsp+1F0h+psz+8]
0x181040827  mov     ebx, eax
0x181040829  mov     rax, [rcx]
0x18104082c  mov     rax, [rax+10h]
0x181040830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181040835  mov     rcx, [rsp+1F0h+var_198]
0x18104083a  mov     rax, [rcx]
0x18104083d  mov     rax, [rax+10h]
0x181040841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181040846  test    ebx, ebx
0x181040848  js      short loc_1810408AA
0x18104084a  mov     rax, [rsp+1F0h+var_1A0]
0x18104084f  mov     rcx, [rax]
0x181040852  mov     rbx, [rcx+4E8h]
0x181040859  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18104085f  mov     rcx, [rsp+1F0h+var_1A0]
0x181040864  lea     rdx, [rsp+1F0h+psz+8]
0x181040869  movups  xmm0, xmmword ptr [rax]
0x18104086c  mov     rax, rbx
0x18104086f  movdqu  xmmword ptr [rsp+1F0h+psz+8], xmm0
0x181040875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18104087a  mov     rcx, [rsp+1F0h+var_1A0]
0x18104087f  lea     r8, [rbp+0F0h+var_90]
0x181040883  mov     r9, [rbp+0F0h+ppvOut]
0x181040887  lea     rdx, [rbp+0F0h+bstrString]
0x18104088b  mov     rax, [rcx]
0x18104088e  mov     rax, [rax+28h]
0x181040892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181040897  mov     rcx, [rsp+1F0h+var_1A0]
0x18104089c  mov     ebx, eax
0x18104089e  mov     rax, [rcx]
0x1810408a1  mov     rax, [rax+10h]
0x1810408a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810408aa  xor     edi, edi
0x1810408ac  cmp     ebx, 80004004h
0x1810408b2  cmovnz  edi, ebx
0x1810408b5  xor     ebx, ebx
0x1810408b7  test    r15d, r15d
  ... truncated ...
```
