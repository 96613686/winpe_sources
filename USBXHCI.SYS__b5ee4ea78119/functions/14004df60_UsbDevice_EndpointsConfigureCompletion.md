# UsbDevice_EndpointsConfigureCompletion

- ea: `0x14004df60`
- end: `0x14004e8bf`
- name: `UsbDevice_EndpointsConfigureCompletion`
- size: `2399`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002568`
- `0x14000c264`
- `0x1400216b8`
- `0x14002499c`
- `0x140024e18`
- `0x140024f24`
- `0x140029840`
- `0x14002b2c0`
- `0x14002b648`
- `0x14002ff50`
- `0x140034840`
- `0x140035d48`
- `0x1400392d4`
- `0x14003bc3c`
- `0x14003f090`
- `0x14003f310`
- `0x14004df60`
- `0x14004e8c8`
- `0x140059970`
- `0x1400599b0`
- `0x140059d80`

## string_xrefs

- `0x14004e480`: `Configure Endpoints command failed when only disabling endpoints`

## pseudocode

```c
__int64 __fastcall UsbDevice_EndpointsConfigureCompletion(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v6; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int16 v10; // ax
  __int64 v11; // rax
  int v12; // r8d
  __int64 v13; // rsi
  _BYTE *v14; // rdi
  int v15; // eax
  int v16; // edx
  int v17; // edx
  char v18; // r14
  int v19; // edi
  char v20; // al
  __int64 v21; // r10
  __int64 v22; // rcx
  int v23; // r8d
  __int64 v24; // rcx
  int v25; // edx
  int v26; // edx
  unsigned int i; // r15d
  __int64 v28; // rax
  int v29; // edx
  char v30; // al
  unsigned int j; // r14d
  __int64 v32; // rax
  unsigned int k; // r15d
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r14
  __int64 v37; // rcx
  unsigned int v38; // r15d
  unsigned int *m; // r14
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 result; // rax
  unsigned int n; // edi
  __int64 v44; // rax
  __int64 v45; // rax
  unsigned int *v46; // r15
  unsigned int *v47; // rdi
  int DeviceSpeed; // eax
  __int64 v49; // rcx
  int v50; // eax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  char v54; // al
  int v55; // edx
  unsigned int v56; // eax
  __int64 v57; // rdx
  unsigned int ii; // edi
  __int64 v59; // rax
  char v60; // r8
  __int64 *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  int v66; // eax
  __int64 v67; // rcx
  char v68; // [rsp+40h] [rbp-29h]
  _QWORD v69[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v70; // [rsp+58h] [rbp-11h]
  __int64 v71; // [rsp+60h] [rbp-9h]
  _OWORD v72[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v73; // [rsp+88h] [rbp+1Fh]

  v3 = *(_QWORD *)(a1 + 48);
  v73 = 0;
  memset(v72, 0, sizeof(v72));
  v6 = *(_QWORD *)(v3 + 8);
  v8 = *(_QWORD *)(v3 + 448);
  LODWORD(v69[0]) = 0;
  v68 = 0;
  v9 = *(_QWORD *)(v6 + 88);
  v71 = *(_QWORD *)(v6 + 144);
  v70 = v9;
  v69[1] = v8;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount > 0x33 )
    {
      LOWORD(v72[0]) = *(_WORD *)(WdfStructures + 408);
      goto LABEL_7;
    }
    v10 = -1;
  }
  else
  {
    v10 = 40;
  }
  LOWORD(v72[0]) = v10;
LABEL_7:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    v8,
    v72);
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
          WdfDriverGlobals,
          v8,
          off_14006BF00);
  v13 = *((_QWORD *)&v72[0] + 1);
  v14 = (_BYTE *)v11;
  if ( a2 == 3 )
  {
    v15 = *(_DWORD *)(*((_QWORD *)&v72[0] + 1) + 24LL);
    if ( !v15 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = *(unsigned __int8 *)(v3 + 143);
        LOBYTE(v16) = 4;
        WPP_RECORDER_SF_dqd(
          *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
          v16,
          12,
          66,
          (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
          *(_BYTE *)(v3 + 143),
          *(_QWORD *)v3,
          *(_DWORD *)(*((_QWORD *)&v72[0] + 1) + 40LL));
      }
      goto LABEL_33;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = *(unsigned __int8 *)(v3 + 143);
      LOBYTE(v17) = 4;
      WPP_RECORDER_SF_dqd(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v17,
        12,
        67,
        (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
        *(_BYTE *)(v3 + 143),
        *(_QWORD *)v3,
        v15);
    }
LABEL_13:
    v18 = 1;
    v19 = -1073741823;
    goto LABEL_35;
  }
  v20 = *(_BYTE *)(a1 + 60);
  if ( v20 == 1 )
  {
    v21 = *(_QWORD *)(*(_QWORD *)(v3 + 8) + 136LL);
    if ( *(_BYTE *)(v21 + 80)
      && ((v22 = *(_QWORD *)(*(_QWORD *)(v21 + 88) + 8LL), *(_BYTE *)(v3 + 664)) && *(_DWORD *)(v22 + 1052) == 2
       || *(_DWORD *)(v22 + 1052) == 1) )
    {
      XilDeviceSlot_SendQuerySlotContextInfoRequest(v21 + 16, v3, 0, v69);
    }
    else
    {
      v24 = v3 + 624;
      if ( !*(_BYTE *)(v3 + 665) )
        v24 = v3 + 616;
      XilCoreUsbDevice_GetDeviceContextBufferVA(v24);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = *(unsigned __int8 *)(a1 + 61);
      LOBYTE(v25) = 4;
      WPP_RECORDER_SF_dqL(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), v25, v23, 68);
    }
    *(_DWORD *)(v13 + 76) = *(_DWORD *)(a1 + 64);
    if ( *v14 || v14[1] )
    {
      v19 = -1073741823;
LABEL_34:
      v18 = 0;
LABEL_35:
      for ( i = 0; i < *(_DWORD *)(v13 + 40); ++i )
      {
        v28 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
                WdfDriverGlobals,
                *(_QWORD *)(*(_QWORD *)(v13 + 48) + 8LL * i),
                off_14006C068);
        Endpoint_Disable(v28, 0);
      }
      if ( v18 != 1 )
        goto LABEL_56;
      goto LABEL_54;
    }
    v68 = 1;
LABEL_33:
    v19 = 0;
    goto LABEL_34;
  }
  if ( v20 == 11 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = *(unsigned __int8 *)(a1 + 61);
      LOBYTE(v26) = 4;
      WPP_RECORDER_SF_dq(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v26,
        12,
        69,
        (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
        *(_BYTE *)(a1 + 61),
        *(_QWORD *)v3);
    }
    if ( !*(_DWORD *)(v13 + 24) )
      goto LABEL_33;
    goto LABEL_13;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v29 = *(unsigned __int8 *)(a1 + 61);
    LOBYTE(v29) = 2;
    WPP_RECORDER_SF_dqL(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), v29, v12, 70);
  }
  v30 = *(_BYTE *)(a1 + 60);
  switch ( v30 )
  {
    case 8:
    case 35:
      if ( *(_DWORD *)(v13 + 24) )
        *(_DWORD *)(v13 + 72) |= 1u;
      break;
    case 7:
      if ( *(_DWORD *)(v13 + 24) )
        *(_DWORD *)(v13 + 72) |= 2u;
      break;
    case 29:
      if ( *(_DWORD *)(v13 + 24) )
        *(_DWORD *)(v13 + 72) |= 4u;
      *(_DWORD *)(v13 + 76) = *(_DWORD *)(a1 + 64);
      break;
  }
  if ( !*(_DWORD *)(v13 + 40) )
  {
    v19 = -1073741823;
LABEL_54:
    for ( j = 0; j < *(_DWORD *)(v13 + 24); ++j )
    {
      v32 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
              WdfDriverGlobals,
              *(_QWORD *)(*(_QWORD *)(v13 + 32) + 8LL * j),
              off_14006C068);
      Endpoint_Disable(v32, 0);
    }
LABEL_56:
    if ( v68 == 1 )
    {
      for ( k = 0; k < *(_DWORD *)(v13 + 24); *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v36 + 152) + 176) = v36 )
      {
        v34 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
                WdfDriverGlobals,
                *(_QWORD *)(*(_QWORD *)(v13 + 32) + 8LL * k),
                off_14006C068);
        v36 = v34;
        v37 = *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v34 + 152) + 176);
        if ( v37 && v37 != v34 )
        {
          LOBYTE(v35) = 1;
          Endpoint_Disable(v37, v35);
          *(_QWORD *)(v3 + 8LL * *(unsigned int *)(v36 + 152) + 176) = 0;
        }
        ++k;
      }
    }
    if ( v19 >= 0 )
    {
      v38 = 0;
      for ( m = *(unsigned int **)(v13 + 88); v38 < *(_DWORD *)(v13 + 84); m = (unsigned int *)((char *)m + *m) )
      {
        UsbDevice_GetEndpointOffloadInformation(v3, v13, m);
        ++v38;
      }
    }
    UsbDevice_SetConfigureRequestStatus(v3, (unsigned int)v19);
    if ( v19 < 0 )
      v41 = 2;
    else
      v41 = 1;
    return UsbDevice_QueueConfigureEndpointEvent(v40, v41);
  }
  if ( !*(_DWORD *)(v13 + 24) || *v14 == 1 || v14[1] == 1 )
  {
    UsbDevice_SetConfigureRequestStatus(v3, 3221225473LL);
    Controller_HwVerifierBreakIfEnabled(
      *(_QWORD *)(v3 + 8),
      *(_QWORD *)v3,
      0,
      0x80000,
      (__int64)"Configure Endpoints command failed when only disabling endpoints",
      a1 + 24,
      a3);
    return Controller_ReportFatalError(*(_QWORD *)(v3 + 8), 2, 4119, 0, 0, 0, 0);
  }
  v14[1] = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dqq(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), *(unsigned __int8 *)(v3 + 143), v12, 71);
  for ( n = 0; n < *(_DWORD *)(v13 + 24); ++n )
  {
    v44 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
            WdfDriverGlobals,
            *(_QWORD *)(*(_QWORD *)(v13 + 32) + 8LL * n),
            off_14006C068);
    Endpoint_Disable(v44, 0);
  }
  v45 = v3 + 656;
  if ( !*(_BYTE *)(v3 + 665) )
    v45 = v3 + 648;
  if ( *(_QWORD *)v45 )
    v46 = *(unsigned int **)(*(_QWORD *)v45 + 16LL);
  else
    v46 = 0;
  if ( (*(_DWORD *)(v70 + 104) & 4) != 0 )
  {
    memset(v46, 0, 0x840u);
    v47 = v46 + 16;
  }
  else
  {
    memset(v46, 0, 0x420u);
    v47 = v46 + 8;
  }
  v46[1] |= 1u;
  if ( *(_BYTE *)(v3 + 144) )
  {
    *v47 |= 0x4000000u;
    *((_BYTE *)v47 + 7) = *(_BYTE *)(v3 + 148);
    if ( *(_DWORD *)(v3 + 20) == 2 )
    {
      if ( *(_DWORD *)(v3 + 152) > 1u )
        *v47 |= 0x2000000u;
      v47[2] ^= (v47[2] ^ (*(_DWORD *)(v3 + 156) << 16)) & 0x30000;
    }
  }
  if ( (*(_DWORD *)(*(_QWORD *)(v3 + 8) + 744LL) & 0x20000000) != 0 )
  {
    v69[0] = (unsigned int)Feature_UISCSF__private_featureState;
    if ( (Feature_UISCSF__private_featureState & 0x10) == 0 )
    {
      LODWORD(v69[0]) = Feature_UISCSF__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(Feature_UISCSF__private_descriptor, v69[0], 3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v69[0], 3, Feature_UISCSF__private_descriptor);
    }
    DeviceSpeed = UsbDevice_GetDeviceSpeedEx(v3);
    if ( DeviceSpeed )
    {
      v50 = DeviceSpeed - 1;
      if ( v50 )
      {
        v51 = v50 - 1;
        if ( v51 )
        {
          v52 = v51 - 1;
          if ( v52 )
          {
            v53 = v52 - 1;
            if ( v53 )
            {
              result = (unsigned int)(v53 - 1);
              if ( (_DWORD)result )
              {
                if ( (_DWORD)result != 1 )
                {
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    v54 = UsbDevice_GetDeviceSpeedEx(v49);
                    v55 = *(unsigned __int8 *)(v3 + 143);
                    LOBYTE(v55) = 2;
                    return WPP_RECORDER_SF_DD(
                             *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
                             v55,
                             12,
                             72,
                             (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
                             *(_BYTE *)(v3 + 143),
                             v54);
                  }
                  return result;
                }
                v56 = *v47 & 0xFF0FFFFF | 0x700000;
              }
              else
              {
                v56 = *v47 & 0xFF0FFFFF | 0x600000;
              }
            }
            else
            {
              v56 = *v47 & 0xFF0FFFFF | 0x500000;
            }
          }
          else
          {
            v56 = *v47 & 0xFF0FFFFF | 0x400000;
          }
        }
        else
        {
          v56 = *v47 & 0xFF0FFFFF | 0x300000;
        }
      }
      else
      {
        v56 = *v47 & 0xFF0FFFFF | 0x100000;
      }
    }
    else
    {
      v56 = *v47 & 0xFF0FFFFF | 0x200000;
    }
    *v47 = v56;
  }
  if ( _bittest64((const signed __int64 *)(*(_QWORD *)(v3 + 8) + 736LL), 0x3Du) )
  {
    if ( !*(_BYTE *)(v3 + 144) )
    {
      v57 = *(_QWORD *)(v3 + 24);
      if ( v57 )
      {
        if ( *(int *)(v3 + 20) < 2
          && *(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                           WdfDriverGlobals,
                           v57,
                           off_14006C1A8)
                       + 152) > 1u )
        {
          *v47 |= 0x2000000u;
        }
      }
    }
  }
  for ( ii = 0; ii < *(_DWORD *)(v13 + 40); *v46 |= 1 << *(_DWORD *)(v59 + 152) )
    v59 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01033 + 1616))(
            WdfDriverGlobals,
            *(_QWORD *)(*(_QWORD *)(v13 + 48) + 8LL * ii++),
            off_14006C068);
  memset((void *)(v3 + 464), 0, 0x60u);
  *(_DWORD *)(v3 + 500) = 12288;
  *(_QWORD *)(v3 + 504) = UsbDevice_EndpointsConfigureCompletion;
  *(_BYTE *)(v3 + 503) = *(_BYTE *)(v3 + 143);
  *(_QWORD *)(v3 + 512) = v3;
  v60 = *(_BYTE *)(v3 + 665);
  if ( v60 )
  {
    v61 = (__int64 *)(v3 + 656);
    v62 = v3 + 656;
    v63 = v3 + 648;
  }
  else
  {
    v61 = (__int64 *)(v3 + 648);
    v63 = v3 + 648;
    v62 = v3 + 656;
  }
  v64 = *v61;
  if ( v64 )
    v65 = *(_QWORD *)(v64 + 24);
  else
    v65 = 0;
  *(_QWORD *)(v3 + 488) = v65;
  *(_QWORD *)(v3 + 536) = v46;
  if ( v60 )
    v63 = v62;
  if ( *(_QWORD *)v63 )
    v66 = *(_DWORD *)(*(_QWORD *)v63 + 44LL);
  else
    v66 = 0;
  v67 = v71;
  *(_DWORD *)(v3 + 544) = v66;
  *(_DWORD *)(v3 + 548) = 1;
  *(_QWORD *)(v3 + 552) = v3;
  return Command_SendCommand(v67, v3 + 464);
}

```

## disassembly

```asm
0x14004df60  mov     [rsp-8+arg_8], rbx
0x14004df65  mov     [rsp-8+arg_18], rsi
0x14004df6a  push    rbp
0x14004df6b  push    rdi
0x14004df6c  push    r12
0x14004df6e  push    r14
0x14004df70  push    r15
0x14004df72  lea     rbp, [rsp-37h]
0x14004df77  sub     rsp, 0A0h
0x14004df7e  mov     rax, cs:__security_cookie
0x14004df85  xor     rax, rsp
0x14004df88  mov     [rbp+57h+var_30], rax
0x14004df8c  mov     rbx, [rcx+30h]
0x14004df90  xor     eax, eax
0x14004df92  mov     [rbp+57h+var_38], rax
0x14004df96  xorps   xmm0, xmm0
0x14004df99  movups  [rbp+57h+var_58], xmm0
0x14004df9d  mov     r14d, edx
0x14004dfa0  xor     edx, edx
0x14004dfa2  cmp     cs:WdfClientVersionHigherThanFramework, dl
0x14004dfa8  mov     r15, rcx
0x14004dfab  movups  [rbp+57h+var_48], xmm0
0x14004dfaf  mov     rax, [rbx+8]
0x14004dfb3  mov     r12, r8
0x14004dfb6  mov     rdi, [rbx+1C0h]
0x14004dfbd  mov     dword ptr [rbp+57h+var_78], edx
0x14004dfc0  mov     [rbp+57h+var_80], dl
0x14004dfc3  mov     rcx, [rax+58h]
0x14004dfc7  mov     rax, [rax+90h]
0x14004dfce  mov     [rbp+57h+var_60], rax
0x14004dfd2  mov     [rbp+57h+var_68], rcx
0x14004dfd6  mov     [rbp+57h+var_70], rdi
0x14004dfda  jz      short loc_14004E000
0x14004dfdc  cmp     cs:WdfStructureCount, 33h ; '3'
0x14004dfe3  jbe     short loc_14004DFF9
0x14004dfe5  mov     rax, cs:WdfStructures
0x14004dfec  movzx   ecx, word ptr [rax+198h]
0x14004dff3  mov     word ptr [rbp+57h+var_58], cx
0x14004dff7  jmp     short loc_14004E009
0x14004dff9  mov     eax, 0FFFFh
0x14004dffe  jmp     short loc_14004E005
0x14004e000  mov     eax, 28h ; '('
0x14004e005  mov     word ptr [rbp+57h+var_58], ax
0x14004e009  mov     rax, cs:WdfFunctions_01033
0x14004e010  lea     r8, [rbp+57h+var_58]
0x14004e014  mov     rcx, cs:WdfDriverGlobals
0x14004e01b  mov     rdx, rdi
0x14004e01e  mov     rax, [rax+850h]
0x14004e025  call    _guard_dispatch_icall
0x14004e02a  mov     rax, cs:WdfFunctions_01033
0x14004e031  mov     rdx, rdi
0x14004e034  mov     r8, cs:off_14006BF00
0x14004e03b  mov     rcx, cs:WdfDriverGlobals
0x14004e042  mov     rax, [rax+650h]
0x14004e049  call    _guard_dispatch_icall
0x14004e04e  mov     rsi, qword ptr [rbp+57h+var_58+8]
0x14004e052  mov     rdi, rax
0x14004e055  cmp     r14d, 3
0x14004e059  jnz     loc_14004E119
0x14004e05f  mov     eax, [rsi+18h]
0x14004e062  xor     r12d, r12d
0x14004e065  test    eax, eax
0x14004e067  jnz     short loc_14004E0C0
0x14004e069  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004e070  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004e077  jz      loc_14004E24B
0x14004e07d  movzx   edx, byte ptr [rbx+8Fh]
0x14004e084  lea     r9d, [rax+42h]
0x14004e088  mov     eax, [rsi+28h]
0x14004e08b  lea     r8d, [r12+0Ch]
0x14004e090  mov     rcx, [rbx+8]
0x14004e094  mov     dword ptr [rsp+0C0h+var_88], eax
0x14004e098  mov     rax, [rbx]
0x14004e09b  mov     [rsp+0C0h+var_90], rax
0x14004e0a0  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x14004e0a7  mov     rcx, [rcx+48h]
0x14004e0ab  mov     dword ptr [rsp+0C0h+var_98], edx
0x14004e0af  mov     dl, 4
0x14004e0b1  mov     [rsp+0C0h+var_A0], rax
0x14004e0b6  call    WPP_RECORDER_SF_dqd
0x14004e0bb  jmp     loc_14004E24B
0x14004e0c0  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004e0c7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004e0ce  jz      short loc_14004E10C
0x14004e0d0  movzx   edx, byte ptr [rbx+8Fh]
0x14004e0d7  mov     r9d, 43h ; 'C'
0x14004e0dd  mov     rcx, [rbx+8]
0x14004e0e1  mov     dword ptr [rsp+0C0h+var_88], eax
0x14004e0e5  mov     rax, [rbx]
0x14004e0e8  mov     [rsp+0C0h+var_90], rax
0x14004e0ed  lea     r8d, [r9-37h]
0x14004e0f1  mov     rcx, [rcx+48h]
0x14004e0f5  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x14004e0fc  mov     dword ptr [rsp+0C0h+var_98], edx
0x14004e100  mov     dl, 4
0x14004e102  mov     [rsp+0C0h+var_A0], rax
0x14004e107  call    WPP_RECORDER_SF_dqd
0x14004e10c  mov     r14b, 1
0x14004e10f  mov     edi, 0C0000001h
0x14004e114  jmp     loc_14004E251
0x14004e119  movzx   eax, byte ptr [r15+3Ch]
0x14004e11e  cmp     al, 1
0x14004e120  jnz     loc_14004E1F0
0x14004e126  mov     rax, [rbx+8]
0x14004e12a  xor     r12d, r12d
0x14004e12d  mov     r10, [rax+88h]
0x14004e134  cmp     [r10+50h], r12b
0x14004e138  jz      short loc_14004E175
0x14004e13a  mov     rax, [r10+58h]
0x14004e13e  mov     rcx, [rax+8]
0x14004e142  cmp     [rbx+298h], r12b
0x14004e149  jz      short loc_14004E154
0x14004e14b  cmp     dword ptr [rcx+41Ch], 2
0x14004e152  jz      short loc_14004E15D
0x14004e154  cmp     dword ptr [rcx+41Ch], 1
0x14004e15b  jnz     short loc_14004E175
0x14004e15d  lea     r9, [rbp+57h+var_78]
0x14004e161  xor     r8d, r8d
0x14004e164  mov     rdx, rbx
0x14004e167  lea     rcx, [r10+10h]
0x14004e16b  call    XilDeviceSlot_SendQuerySlotContextInfoRequest
0x14004e170  mov     eax, dword ptr [rbp+57h+var_78]
0x14004e173  jmp     short loc_14004E197
0x14004e175  lea     rcx, [rbx+270h]
0x14004e17c  cmp     [rbx+299h], r12b
0x14004e183  jnz     short loc_14004E18C
0x14004e185  lea     rcx, [rbx+268h]
0x14004e18c  call    XilCoreUsbDevice_GetDeviceContextBufferVA
0x14004e191  mov     eax, [rax+0Ch]
0x14004e194  shr     eax, 1Bh
0x14004e197  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004e19e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004e1a5  jz      short loc_14004E1D1
0x14004e1a7  movzx   edx, byte ptr [r15+3Dh]
0x14004e1ac  mov     r9d, 44h ; 'D'
0x14004e1b2  mov     rcx, [rbx+8]
0x14004e1b6  mov     dword ptr [rsp+0C0h+var_88], eax
0x14004e1ba  mov     rax, [rbx]
0x14004e1bd  mov     [rsp+0C0h+var_90], rax
0x14004e1c2  mov     rcx, [rcx+48h]
0x14004e1c6  mov     dword ptr [rsp+0C0h+var_98], edx
0x14004e1ca  mov     dl, 4
0x14004e1cc  call    WPP_RECORDER_SF_dqL
0x14004e1d1  mov     eax, [r15+40h]
0x14004e1d5  mov     [rsi+4Ch], eax
0x14004e1d8  cmp     [rdi], r12b
0x14004e1db  jnz     short loc_14004E1E9
0x14004e1dd  cmp     [rdi+1], r12b
0x14004e1e1  jnz     short loc_14004E1E9
0x14004e1e3  mov     [rbp+57h+var_80], 1
0x14004e1e7  jmp     short loc_14004E24B
0x14004e1e9  mov     edi, 0C0000001h
0x14004e1ee  jmp     short loc_14004E24E
0x14004e1f0  cmp     al, 0Bh
0x14004e1f2  jnz     loc_14004E2A8
0x14004e1f8  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004e1ff  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004e206  jz      short loc_14004E23E
0x14004e208  mov     rax, [rbx]
0x14004e20b  mov     r9d, 45h ; 'E'
0x14004e211  movzx   edx, byte ptr [r15+3Dh]
0x14004e216  mov     rcx, [rbx+8]
0x14004e21a  mov     [rsp+0C0h+var_90], rax
0x14004e21f  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x14004e226  mov     dword ptr [rsp+0C0h+var_98], edx
0x14004e22a  lea     r8d, [r9-39h]
0x14004e22e  mov     dl, 4
0x14004e230  mov     [rsp+0C0h+var_A0], rax
0x14004e235  mov     rcx, [rcx+48h]
0x14004e239  call    WPP_RECORDER_SF_dq
0x14004e23e  xor     r12d, r12d
0x14004e241  cmp     [rsi+18h], r12d
0x14004e245  ja      loc_14004E10C
0x14004e24b  mov     edi, r12d
0x14004e24e  mov     r14b, r12b
0x14004e251  mov     r15d, r12d
0x14004e254  cmp     [rsi+28h], r12d
0x14004e258  jbe     short loc_14004E299
0x14004e25a  mov     rdx, [rsi+30h]
0x14004e25e  mov     rax, cs:WdfFunctions_01033
0x14004e265  mov     r8, cs:off_14006C068
0x14004e26c  mov     ecx, r15d
0x14004e26f  mov     rax, [rax+650h]
0x14004e276  mov     rdx, [rdx+rcx*8]
0x14004e27a  mov     rcx, cs:WdfDriverGlobals
0x14004e281  call    _guard_dispatch_icall
0x14004e286  xor     edx, edx
0x14004e288  mov     rcx, rax
0x14004e28b  call    Endpoint_Disable
0x14004e290  inc     r15d
0x14004e293  cmp     r15d, [rsi+28h]
0x14004e297  jb      short loc_14004E25A
0x14004e299  cmp     r14b, 1
0x14004e29d  jnz     loc_14004E379
0x14004e2a3  jmp     loc_14004E331
0x14004e2a8  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004e2af  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004e2b6  jz      short loc_14004E2E2
0x14004e2b8  movzx   edx, byte ptr [r15+3Dh]
0x14004e2bd  mov     r9d, 46h ; 'F'
0x14004e2c3  mov     rcx, [rbx+8]
0x14004e2c7  mov     dword ptr [rsp+0C0h+var_88], eax
0x14004e2cb  mov     rax, [rbx]
0x14004e2ce  mov     [rsp+0C0h+var_90], rax
0x14004e2d3  mov     rcx, [rcx+48h]
0x14004e2d7  mov     dword ptr [rsp+0C0h+var_98], edx
0x14004e2db  mov     dl, 2
0x14004e2dd  call    WPP_RECORDER_SF_dqL
0x14004e2e2  mov     al, [r15+3Ch]
0x14004e2e6  cmp     al, 8
0x14004e2e8  jz      short loc_14004E315
0x14004e2ea  cmp     al, 23h ; '#'
0x14004e2ec  jz      short loc_14004E315
0x14004e2ee  cmp     al, 7
0x14004e2f0  jnz     short loc_14004E2FE
0x14004e2f2  cmp     dword ptr [rsi+18h], 0
0x14004e2f6  jz      short loc_14004E31F
0x14004e2f8  or      dword ptr [rsi+48h], 2
0x14004e2fc  jmp     short loc_14004E31F
0x14004e2fe  cmp     al, 1Dh
0x14004e300  jnz     short loc_14004E31F
0x14004e302  cmp     dword ptr [rsi+18h], 0
0x14004e306  jz      short loc_14004E30C
0x14004e308  or      dword ptr [rsi+48h], 4
0x14004e30c  mov     eax, [r15+40h]
0x14004e310  mov     [rsi+4Ch], eax
0x14004e313  jmp     short loc_14004E31F
0x14004e315  cmp     dword ptr [rsi+18h], 0
0x14004e319  jz      short loc_14004E31F
0x14004e31b  or      dword ptr [rsi+48h], 1
0x14004e31f  cmp     dword ptr [rsi+28h], 0
0x14004e323  jnz     loc_14004E44F
0x14004e329  mov     edi, 0C0000001h
0x14004e32e  xor     r12d, r12d
0x14004e331  mov     r14d, r12d
0x14004e334  cmp     [rsi+18h], r12d
0x14004e338  jbe     short loc_14004E379
0x14004e33a  mov     rdx, [rsi+20h]
0x14004e33e  mov     rax, cs:WdfFunctions_01033
0x14004e345  mov     r8, cs:off_14006C068
0x14004e34c  mov     ecx, r14d
0x14004e34f  mov     rax, [rax+650h]
0x14004e356  mov     rdx, [rdx+rcx*8]
0x14004e35a  mov     rcx, cs:WdfDriverGlobals
0x14004e361  call    _guard_dispatch_icall
0x14004e366  xor     edx, edx
0x14004e368  mov     rcx, rax
0x14004e36b  call    Endpoint_Disable
0x14004e370  inc     r14d
0x14004e373  cmp     r14d, [rsi+18h]
0x14004e377  jb      short loc_14004E33A
0x14004e379  cmp     [rbp+57h+var_80], 1
0x14004e37d  jnz     short loc_14004E3FD
0x14004e37f  mov     r15d, r12d
0x14004e382  cmp     [rsi+18h], r12d
0x14004e386  jbe     short loc_14004E3FD
0x14004e388  mov     rdx, [rsi+20h]
0x14004e38c  mov     rax, cs:WdfFunctions_01033
0x14004e393  mov     r8, cs:off_14006C068
0x14004e39a  mov     ecx, r15d
0x14004e39d  mov     rax, [rax+650h]
0x14004e3a4  mov     rdx, [rdx+rcx*8]
0x14004e3a8  mov     rcx, cs:WdfDriverGlobals
0x14004e3af  call    _guard_dispatch_icall
0x14004e3b4  mov     r14, rax
0x14004e3b7  mov     ecx, [rax+98h]
0x14004e3bd  mov     rcx, [rbx+rcx*8+0B0h]
0x14004e3c5  test    rcx, rcx
0x14004e3c8  jz      short loc_14004E3E5
0x14004e3ca  cmp     rcx, rax
0x14004e3cd  jz      short loc_14004E3E5
0x14004e3cf  mov     dl, 1
0x14004e3d1  call    Endpoint_Disable
0x14004e3d6  mov     ecx, [r14+98h]
0x14004e3dd  mov     [rbx+rcx*8+0B0h], r12
0x14004e3e5  mov     eax, [r14+98h]
0x14004e3ec  inc     r15d
0x14004e3ef  mov     [rbx+rax*8+0B0h], r14
0x14004e3f7  cmp     r15d, [rsi+18h]
0x14004e3fb  jb      short loc_14004E388
0x14004e3fd  test    edi, edi
0x14004e3ff  js      short loc_14004E42B
0x14004e401  mov     r15d, r12d
0x14004e404  mov     r14, [rsi+58h]
0x14004e408  cmp     [rsi+54h], r12d
0x14004e40c  jbe     short loc_14004E42B
0x14004e40e  mov     r8, r14
0x14004e411  mov     rdx, rsi
0x14004e414  mov     rcx, rbx
0x14004e417  call    UsbDevice_GetEndpointOffloadInformation
0x14004e41c  mov     eax, [r14]
0x14004e41f  inc     r15d
0x14004e422  add     r14, rax
0x14004e425  cmp     r15d, [rsi+54h]
0x14004e429  jb      short loc_14004E40E
0x14004e42b  mov     edx, edi
0x14004e42d  mov     rcx, rbx
0x14004e430  call    UsbDevice_SetConfigureRequestStatus
0x14004e435  test    edi, edi
0x14004e437  js      short loc_14004E448
  ... truncated ...
```
