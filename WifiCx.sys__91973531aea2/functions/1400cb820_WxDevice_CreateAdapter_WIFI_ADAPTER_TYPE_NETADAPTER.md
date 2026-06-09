# WxDevice::CreateAdapter(_WIFI_ADAPTER_TYPE,NETADAPTER__ * *)

- ea: `0x1400cb820`
- end: `0x1400cbbd4`
- name: `?CreateAdapter@WxDevice@@QEAAJW4_WIFI_ADAPTER_TYPE@@PEAPEAUNETADAPTER__@@@Z`
- size: `948`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1400695e0`
- `0x1400cdce8`

## callees

- `0x14000c778`
- `0x14001eed0`
- `0x140061338`
- `0x14006ab94`
- `0x14008c238`
- `0x1400cac7c`
- `0x1400cb630`
- `0x1400cb820`
- `0x1400cf9c0`
- `0x1400dfd40`

## string_xrefs

- `0x1400cb9ba`: `adapterExtensionInit`

## pseudocode

```c
__int64 __fastcall WxDevice::CreateAdapter(__int64 a1, int a2, __int64 *a3)
{
  __int64 *v5; // r12
  __int64 v6; // rax
  int v7; // edx
  int v8; // r8d
  __int64 v9; // rbx
  int v10; // r9d
  const char *v11; // rax
  int v12; // eax
  int v13; // r14d
  PNET_DRIVER_GLOBALS v14; // rcx
  struct _NETADAPTEREXT_INIT *v15; // rax
  __int64 v16; // rax
  int v17; // edx
  int v18; // r8d
  __int64 v19; // rbx
  int v20; // eax
  int v21; // r9d
  __int64 v22; // r13
  __int64 v23; // rax
  CPort *v24; // r15
  int v25; // r12d
  char v27; // [rsp+30h] [rbp-50h]
  __int64 v28; // [rsp+40h] [rbp-40h] BYREF
  __int128 v29; // [rsp+48h] [rbp-38h] BYREF
  __int128 v30; // [rsp+58h] [rbp-28h]
  __int128 v31; // [rsp+68h] [rbp-18h]
  __int64 *v32; // [rsp+78h] [rbp-8h]
  __int64 v33; // [rsp+C0h] [rbp+40h] BYREF
  __int64 *v34; // [rsp+D0h] [rbp+50h]
  _DWORD *v35; // [rsp+D8h] [rbp+58h] BYREF

  v34 = a3;
  v5 = a3;
  v6 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD))NetFunctions)(NetDriverGlobals, *(_QWORD *)(a1 + 8));
  v28 = v6;
  v9 = v6;
  if ( !v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = 25;
      v11 = "adapterInit.get()";
LABEL_18:
      WPP_RECORDER_SF_qs(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v8,
        v10,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
        *(_QWORD *)(a1 + 8),
        (__int64)v11);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  v35 = 0;
  v29 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v29) = -1;
    else
      LODWORD(v29) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v29) = 56;
  }
  *((_QWORD *)&v30 + 1) = 0x100000001LL;
  v32 = off_14010E230;
  v12 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, __int128 *, _DWORD **))qword_140110E78)(
          NetDriverGlobals,
          v6,
          &v29,
          &v35);
  v13 = v12;
  if ( v12 >= 0 )
  {
    if ( !v35 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = (_DWORD)v35 + 27;
        v11 = "pWifiAdapterAttributes";
        goto LABEL_18;
      }
LABEL_19:
      v13 = -1073741670;
      goto LABEL_41;
    }
    v14 = NetDriverGlobals;
    *v35 = a2;
    v15 = (struct _NETADAPTEREXT_INIT *)((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_140110C98)(v14, v9);
    if ( !v15 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = 28;
        v11 = "adapterExtensionInit";
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    CxConfigureAdapterExtensionInit(v15);
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(a1 + 40))(*(_QWORD *)(a1 + 8), v9);
    v16 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_140110C90)(NetDriverGlobals, v9);
    v33 = v16;
    v19 = v16;
    if ( v13 )
    {
      if ( v16 )
      {
        v22 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
                WdfDriverGlobals,
                *(_QWORD *)(a1 + 8),
                off_14010E308);
        v23 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                WdfDriverGlobals,
                v19,
                off_14010EB80);
        v24 = (CPort *)(v23 + 392);
        if ( v23 != -392 )
        {
          if ( *(_DWORD *)(v23 + 544) )
          {
            v25 = CAdapter::RemovePort((CAdapter *)(v22 + 56), (struct CPort *)(v23 + 392));
            CPort::Uninitialize(v24);
            if ( v25 != -1073676261 && v25 )
              __int2c();
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v17) = 2;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v17,
                1,
                29,
                (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
                *((_DWORD *)v24 + 38));
            }
            v5 = v34;
          }
        }
      }
      if ( v13 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_39:
          wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v33);
          goto LABEL_41;
        }
        v21 = 30;
        v27 = v13;
LABEL_38:
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          v18,
          v21,
          (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
          v19,
          v27);
        goto LABEL_39;
      }
    }
    else if ( !v16 )
    {
      __int2c();
    }
    v20 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64))qword_140110BE0)(NetDriverGlobals, v19);
    v13 = v20;
    if ( v20 >= 0 )
    {
      v33 = 0;
      *v5 = v19;
      wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(&v33);
      v13 = 0;
      goto LABEL_41;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_39;
    v21 = 31;
    v27 = v20;
    goto LABEL_38;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      26,
      (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
      *(_QWORD *)(a1 + 8),
      v12);
  }
LABEL_41:
  wil::details::unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&void NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&void NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>(&v28);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400cb820  mov     [rsp-38h+arg_8], rbx
0x1400cb825  mov     [rsp-38h+arg_10], r8
0x1400cb82a  push    rbp
0x1400cb82b  push    rsi
0x1400cb82c  push    rdi
0x1400cb82d  push    r12
0x1400cb82f  push    r13
0x1400cb831  push    r14
0x1400cb833  push    r15
0x1400cb835  mov     rbp, rsp
0x1400cb838  sub     rsp, 80h
0x1400cb83f  mov     rax, cs:NetFunctions
0x1400cb846  mov     edi, edx
0x1400cb848  mov     rdx, [rcx+8]
0x1400cb84c  mov     r15, rcx
0x1400cb84f  mov     rcx, cs:NetDriverGlobals
0x1400cb856  mov     r12, r8
0x1400cb859  call    _guard_dispatch_icall
0x1400cb85e  mov     [rbp+var_40], rax
0x1400cb862  mov     rbx, rax
0x1400cb865  test    rax, rax
0x1400cb868  jnz     short loc_1400CB88E
0x1400cb86a  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cb871  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cb878  jz      loc_1400CB9EB
0x1400cb87e  lea     r9d, [rax+19h]
0x1400cb882  lea     rax, aAdapterinitGet; "adapterInit.get()"
0x1400cb889  jmp     loc_1400CB9C1
0x1400cb88e  xorps   xmm0, xmm0
0x1400cb891  mov     [rbp+arg_18], 0
0x1400cb899  xor     eax, eax
0x1400cb89b  cmp     cs:WdfClientVersionHigherThanFramework, al
0x1400cb8a1  movups  [rbp+var_38], xmm0
0x1400cb8a5  mov     [rbp+var_8], rax
0x1400cb8a9  movups  [rbp+var_28], xmm0
0x1400cb8ad  movups  [rbp+var_18], xmm0
0x1400cb8b1  jz      short loc_1400CB8D7
0x1400cb8b3  cmp     cs:WdfStructureCount, 26h ; '&'
0x1400cb8ba  jbe     short loc_1400CB8CE
0x1400cb8bc  mov     rax, cs:WdfStructures
0x1400cb8c3  mov     ecx, [rax+130h]
0x1400cb8c9  mov     dword ptr [rbp+var_38], ecx
0x1400cb8cc  jmp     short loc_1400CB8DE
0x1400cb8ce  mov     dword ptr [rbp+var_38], 0FFFFFFFFh
0x1400cb8d5  jmp     short loc_1400CB8DE
0x1400cb8d7  mov     dword ptr [rbp+var_38], 38h ; '8'
0x1400cb8de  mov     rcx, cs:NetDriverGlobals
0x1400cb8e5  lea     r9, [rbp+arg_18]
0x1400cb8e9  mov     eax, 1
0x1400cb8ee  lea     r8, [rbp+var_38]
0x1400cb8f2  mov     dword ptr [rbp+var_28+8], eax
0x1400cb8f5  mov     rdx, rbx
0x1400cb8f8  mov     dword ptr [rbp+var_28+0Ch], eax
0x1400cb8fb  mov     rax, cs:off_14010E230
0x1400cb902  mov     [rbp+var_8], rax
0x1400cb906  mov     rax, cs:qword_140110E78
0x1400cb90d  call    _guard_dispatch_icall
0x1400cb912  mov     r14d, eax
0x1400cb915  test    eax, eax
0x1400cb917  jns     short loc_1400CB963
0x1400cb919  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cb920  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cb927  jz      loc_1400CBBAC
0x1400cb92d  mov     rcx, [r15+8]
0x1400cb931  lea     rsi, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cb938  mov     dword ptr [rsp+80h+var_50], eax
0x1400cb93c  mov     r9d, 1Ah
0x1400cb942  mov     [rsp+80h+var_58], rcx
0x1400cb947  mov     dl, 2
0x1400cb949  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb950  mov     [rsp+80h+var_60], rsi
0x1400cb955  mov     rcx, [rcx+40h]
0x1400cb959  call    WPP_RECORDER_SF_qD
0x1400cb95e  jmp     loc_1400CBBAC
0x1400cb963  mov     rax, [rbp+arg_18]
0x1400cb967  test    rax, rax
0x1400cb96a  jnz     short loc_1400CB989
0x1400cb96c  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cb973  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cb97a  jz      short loc_1400CB9EB
0x1400cb97c  lea     r9d, [rax+1Bh]
0x1400cb980  lea     rax, aPwifiadapterat; "pWifiAdapterAttributes"
0x1400cb987  jmp     short loc_1400CB9C1
0x1400cb989  mov     rcx, cs:NetDriverGlobals
0x1400cb990  mov     rdx, rbx
0x1400cb993  mov     [rax], edi
0x1400cb995  mov     rax, cs:qword_140110C98
0x1400cb99c  call    _guard_dispatch_icall
0x1400cb9a1  test    rax, rax
0x1400cb9a4  jnz     short loc_1400CB9F6
0x1400cb9a6  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cb9ad  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cb9b4  jz      short loc_1400CB9EB
0x1400cb9b6  lea     r9d, [rax+1Ch]
0x1400cb9ba  lea     rax, aAdapterextensi; "adapterExtensionInit"
0x1400cb9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb9c8  lea     rsi, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cb9cf  mov     qword ptr [rsp+80h+var_50], rax
0x1400cb9d4  mov     rax, [r15+8]
0x1400cb9d8  mov     [rsp+80h+var_58], rax
0x1400cb9dd  mov     rcx, [rcx+40h]
0x1400cb9e1  mov     [rsp+80h+var_60], rsi
0x1400cb9e6  call    WPP_RECORDER_SF_qs
0x1400cb9eb  mov     r14d, 0C000009Ah
0x1400cb9f1  jmp     loc_1400CBBAC
0x1400cb9f6  mov     rcx, rax; struct _NETADAPTEREXT_INIT *
0x1400cb9f9  call    ?CxConfigureAdapterExtensionInit@@YAXPEAU_NETADAPTEREXT_INIT@@@Z; CxConfigureAdapterExtensionInit(_NETADAPTEREXT_INIT *)
0x1400cb9fe  mov     rax, [r15+28h]
0x1400cba02  mov     rdx, rbx
0x1400cba05  mov     rcx, [r15+8]
0x1400cba09  call    _guard_dispatch_icall
0x1400cba0e  mov     rcx, cs:NetDriverGlobals
0x1400cba15  mov     r14d, eax
0x1400cba18  mov     rax, cs:qword_140110C90
0x1400cba1f  mov     rdx, rbx
0x1400cba22  call    _guard_dispatch_icall
0x1400cba27  mov     [rbp+arg_0], rax
0x1400cba2b  mov     rbx, rax
0x1400cba2e  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400cba35  lea     rsi, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cba3c  test    r14d, r14d
0x1400cba3f  jnz     short loc_1400CBA85
0x1400cba41  test    rax, rax
0x1400cba44  jnz     short loc_1400CBA48
0x1400cba46  int     2Ch; Windows NT - assertion failure
0x1400cba48  mov     rax, cs:qword_140110BE0
0x1400cba4f  mov     rdx, rbx
0x1400cba52  mov     rcx, cs:NetDriverGlobals
0x1400cba59  call    _guard_dispatch_icall
0x1400cba5e  mov     r14d, eax
0x1400cba61  test    eax, eax
0x1400cba63  jns     loc_1400CBB94
0x1400cba69  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cba70  jz      loc_1400CBB89
0x1400cba76  mov     r9d, 1Fh
0x1400cba7c  mov     dword ptr [rsp+80h+var_50], eax
0x1400cba80  jmp     loc_1400CBB6D
0x1400cba85  test    rbx, rbx
0x1400cba88  jz      loc_1400CBB50
0x1400cba8e  mov     rax, cs:WdfFunctions_01031
0x1400cba95  mov     r8, cs:off_14010E308
0x1400cba9c  mov     rdx, [r15+8]
0x1400cbaa0  mov     rcx, cs:WdfDriverGlobals
0x1400cbaa7  mov     rax, [rax+650h]
0x1400cbaae  call    _guard_dispatch_icall
0x1400cbab3  mov     rcx, cs:WdfFunctions_01031
0x1400cbaba  mov     r13, rax
0x1400cbabd  mov     r8, cs:off_14010EB80
0x1400cbac4  mov     rdx, rbx
0x1400cbac7  mov     rax, [rcx+650h]
0x1400cbace  mov     rcx, cs:WdfDriverGlobals
0x1400cbad5  call    _guard_dispatch_icall
0x1400cbada  lea     r15, [rax+188h]
0x1400cbae1  test    r15, r15
0x1400cbae4  jz      short loc_1400CBB50
0x1400cbae6  cmp     dword ptr [r15+98h], 0
0x1400cbaee  jz      short loc_1400CBB50
0x1400cbaf0  lea     rcx, [r13+38h]; this
0x1400cbaf4  mov     rdx, r15; struct CPort *
0x1400cbaf7  call    ?RemovePort@CAdapter@@QEAAHPEAVCPort@@@Z; CAdapter::RemovePort(CPort *)
0x1400cbafc  mov     rcx, r15; this
0x1400cbaff  mov     r12d, eax
0x1400cbb02  call    ?Uninitialize@CPort@@QEAAXXZ; CPort::Uninitialize(void)
0x1400cbb07  cmp     r12d, 0C001001Bh
0x1400cbb0e  jz      short loc_1400CBB17
0x1400cbb10  test    r12d, r12d
0x1400cbb13  jz      short loc_1400CBB17
0x1400cbb15  int     2Ch; Windows NT - assertion failure
0x1400cbb17  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbb1e  jz      short loc_1400CBB4C
0x1400cbb20  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbb27  mov     r9d, 1Dh
0x1400cbb2d  mov     eax, [r15+98h]
0x1400cbb34  mov     dl, 2
0x1400cbb36  mov     dword ptr [rsp+80h+var_58], eax
0x1400cbb3a  mov     [rsp+80h+var_60], rsi
0x1400cbb3f  mov     rcx, [rcx+40h]
0x1400cbb43  lea     r8d, [r9-1Ch]
0x1400cbb47  call    WPP_RECORDER_SF_d
0x1400cbb4c  mov     r12, [rbp+arg_10]
0x1400cbb50  test    r14d, r14d
0x1400cbb53  jns     loc_1400CBA48
0x1400cbb59  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400cbb60  jz      short loc_1400CBB89
0x1400cbb62  mov     r9d, 1Eh
0x1400cbb68  mov     dword ptr [rsp+80h+var_50], r14d
0x1400cbb6d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbb74  mov     dl, 2
0x1400cbb76  mov     [rsp+80h+var_58], rbx
0x1400cbb7b  mov     [rsp+80h+var_60], rsi
0x1400cbb80  mov     rcx, [rcx+40h]
0x1400cbb84  call    WPP_RECORDER_SF_qD
0x1400cbb89  lea     rcx, [rbp+arg_0]
0x1400cbb8d  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400cbb92  jmp     short loc_1400CBBAC
0x1400cbb94  lea     rcx, [rbp+arg_0]
0x1400cbb98  mov     [rbp+arg_0], 0
0x1400cbba0  mov     [r12], rbx
0x1400cbba4  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400cbba9  xor     r14d, r14d
0x1400cbbac  lea     rcx, [rbp+var_40]
0x1400cbbb0  call    ??1?$unique_storage@U?$resource_policy@PEAU_NETADAPTER_INIT@@P6AXPEAU1@@Z$1?NetAdapterInitFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_NETADAPTER_INIT *,void (*)(_NETADAPTER_INIT *),&NetAdapterInitFree(_NETADAPTER_INIT *),wistd::integral_constant<unsigned __int64,0>,_NETADAPTER_INIT *,_NETADAPTER_INIT *,0,std::nullptr_t>>(void)
0x1400cbbb5  mov     rbx, [rsp+80h+arg_8]
0x1400cbbbd  mov     eax, r14d
0x1400cbbc0  add     rsp, 80h
0x1400cbbc7  pop     r15
0x1400cbbc9  pop     r14
0x1400cbbcb  pop     r13
0x1400cbbcd  pop     r12
0x1400cbbcf  pop     rdi
0x1400cbbd0  pop     rsi
0x1400cbbd1  pop     rbp
0x1400cbbd2  retn
```
