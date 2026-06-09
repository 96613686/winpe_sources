# CDeviceHandler::_InstallDevice(_DEV_OBJECT const *)

- ea: `0x1800094c8`
- end: `0x180009f3c`
- name: `?_InstallDevice@CDeviceHandler@@AEAAJPEBU_DEV_OBJECT@@@Z`
- size: `2676`
- prototype: `__int64 __fastcall(CDeviceHandler *__hidden this, const struct _DEV_OBJECT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008ea8`

## callees

- `0x1800022f4`
- `0x180002514`
- `0x1800041ec`
- `0x1800057dc`
- `0x180008c5c`
- `0x1800094c8`
- `0x18000a4b0`
- `0x18000a508`
- `0x18000a588`
- `0x18000a644`
- `0x18000a66c`
- `0x18000a778`
- `0x18000fe40`
- `0x180010a80`
- `0x1800137f6`
- `0x180013840`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x180009e1c`
- `ntdll!WinSqmAddToStreamEx` at `0x180009e1c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000956e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000957f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800095ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009aa0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000956e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000957f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800095ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009aa0`
- `SHLWAPI!StrCmpNIW` at `0x180009d50`
- `SHLWAPI!StrCmpNIW` at `0x180009d74`
- `SHLWAPI!StrCmpNIW` at `0x180009d8e`
- `SHLWAPI!StrCmpNIW` at `0x180009d50`
- `SHLWAPI!StrCmpNIW` at `0x180009d74`
- `SHLWAPI!StrCmpNIW` at `0x180009d8e`

## pseudocode

```c
__int64 __fastcall CDeviceHandler::_InstallDevice(CDeviceHandler *this, const struct _DEV_OBJECT *a2)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // r13
  int v5; // r12d
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // r14
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // rsi
  unsigned int v10; // r9d
  __int64 v11; // rdx
  unsigned int v12; // r8d
  unsigned int v13; // r11d
  __int64 v14; // r10
  const WCHAR *lpString2; // rdi
  int v16; // ecx
  const WCHAR *v17; // rcx
  const WCHAR *v18; // rcx
  _QWORD *v19; // rcx
  __int64 *v20; // r8
  __int64 *v21; // r9
  __int64 *v23; // r8
  __int64 *v24; // rdx
  __int64 *v25; // r8
  __int64 *v26; // r9
  CDeviceHandler *v27; // rcx
  unsigned __int16 *v28; // rdi
  GUID *v29; // r13
  int v30; // eax
  struct _GUID v31; // xmm6
  GUID *v32; // rsi
  _DWORD *v33; // rax
  __int64 v34; // r8
  unsigned int v35; // r9d
  struct _GUID v36; // xmm0
  NcdAutoSetupTelemetry *v37; // rcx
  __int64 v38; // rdi
  unsigned __int64 v39; // rsi
  unsigned __int16 *v40; // rax
  unsigned int v41; // ecx
  __int64 v42; // rax
  int v43; // eax
  int v44; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v45; // [rsp+78h] [rbp-88h]
  unsigned int v46; // [rsp+7Ch] [rbp-84h]
  int v47; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpValueName; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v49; // [rsp+90h] [rbp-70h]
  PCWSTR psz1; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v51; // [rsp+A0h] [rbp-60h]
  struct _GUID v52; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v53; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v54[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-20h]
  int v56; // [rsp+E8h] [rbp-18h]
  int v57; // [rsp+ECh] [rbp-14h]
  __int64 v58; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v59; // [rsp+F8h] [rbp-8h]
  int *v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  unsigned __int16 v62[32]; // [rsp+110h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  v3 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
  v4 = 0;
  v44 = 0;
  v5 = 0;
  *(_QWORD *)&v53.Data1 = 0;
  v6 = 0;
  v51 = 0;
  v7 = 0;
  psz1 = 0;
  *(_QWORD *)&v52.Data1 = 0;
  v46 = 0;
  v8 = 0;
  v45 = 0;
  v9 = 0;
  lpValueName = 0;
  v47 = 0;
  v49 = v3;
  EventActivityIdControl(1u, &ActivityId);
  EventActivityIdControl(3u, &Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    EventActivityIdControl(2u, &Buf1);
  v10 = *((_DWORD *)a2 + 4);
  if ( v10 )
  {
    v11 = *((_QWORD *)a2 + 3);
    v12 = 0;
    v13 = 0;
    v14 = 0;
    lpString2 = 0;
    do
    {
      v16 = *(_DWORD *)(v11 + 48 * v14 + 16);
      switch ( v16 )
      {
        case 8194:
          if ( *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_PNPX_ModelName
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 18
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 2u
            && *(_QWORD *)(v11 + 48 * v14 + 40) )
          {
            v6 = *(unsigned __int16 **)(v11 + 48 * v14 + 40);
          }
          break;
        case 8192:
          if ( *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_PNPX_Manufacturer
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 18
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 2u
            && *(_QWORD *)(v11 + 48 * v14 + 40) )
          {
            v51 = *(unsigned __int16 **)(v11 + 48 * v14 + 40);
          }
          break;
        case 12292:
          if ( *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_PNPX_DeviceCategory
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 8210
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 4u )
          {
            v17 = *(const WCHAR **)(v11 + 48 * v14 + 40);
            if ( v17 )
            {
              v46 = *(_DWORD *)(v11 + 48 * v14 + 36);
              psz1 = v17;
              *(_QWORD *)&v52.Data1 = v17;
            }
          }
          break;
        case 90:
          if ( *(_QWORD *)(v11 + 48 * v14) == *(_QWORD *)&PKEY_DeviceDisplay_Category.fmtid.Data1
            && *(_QWORD *)(v11 + 48 * v14 + 8) == *(_QWORD *)PKEY_DeviceDisplay_Category.fmtid.Data4
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 8210
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 4u )
          {
            v18 = *(const WCHAR **)(v11 + 48 * v14 + 40);
            if ( v18 )
            {
              v8 = *(unsigned __int16 **)(v11 + 48 * v14 + 40);
              v45 = *(_DWORD *)(v11 + 48 * v14 + 36);
              lpString2 = v18;
            }
          }
          break;
        case 12297:
          if ( *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_PNPX_IpAddress
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 8210
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 4u
            && *(_QWORD *)(v11 + 48 * v14 + 40) )
          {
            v9 = *(unsigned __int16 **)(v11 + 48 * v14 + 40);
          }
          break;
        case 4101:
          if ( *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_PNPX_ID
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 18
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 2u
            && *(_QWORD *)(v11 + 48 * v14 + 40) )
          {
            lpValueName = *(LPCWSTR *)(v11 + 48 * v14 + 40);
          }
          break;
        case 2:
          if ( *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_Aep_ContainerId
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 13
            && *(_DWORD *)(v11 + 48 * v14 + 36) == 16
            && *(_QWORD *)(v11 + 48 * v14 + 40) )
          {
            *(_QWORD *)&v53.Data1 = *(_QWORD *)(v11 + 48 * v14 + 40);
          }
          break;
        case 4:
          if ( *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_Aep_FriendlyName
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 18
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 2u
            && *(_QWORD *)(v11 + 48 * v14 + 40) )
          {
            v7 = *(unsigned __int16 **)(v11 + 48 * v14 + 40);
          }
          break;
        default:
          if ( v16 == 4097
            && *(_OWORD *)(v11 + 48 * v14) == DEVPKEY_PNPX_Types
            && !*(_DWORD *)(v11 + 48 * v14 + 20)
            && !*(_QWORD *)(v11 + 48 * v14 + 24)
            && *(_DWORD *)(v11 + 48 * v14 + 32) == 8210
            && *(_DWORD *)(v11 + 48 * v14 + 36) >= 4u
            && *(_QWORD *)(v11 + 48 * v14 + 40) )
          {
            v12 = *(_DWORD *)(v11 + 48 * v14 + 36);
            v4 = *(unsigned __int16 **)(v11 + 48 * v14 + 40);
          }
          break;
      }
      ++v13;
      ++v14;
    }
    while ( v13 < v10 );
    v5 = v44;
    if ( v4 )
    {
      v19 = WPP_GLOBAL_Control;
      goto LABEL_88;
    }
  }
  else
  {
    lpString2 = 0;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
    v19 = WPP_GLOBAL_Control;
  }
  v12 = 0;
LABEL_88:
  if ( !*(_QWORD *)&v52.Data1 && !lpString2 )
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 )
    {
      WPP_SF_(v19[2], 55, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) == 0 )
      goto LABEL_100;
    v20 = &qword_180015D38;
    v21 = &qword_180015D38;
    if ( v6 )
      v21 = (__int64 *)v6;
    if ( v7 )
      v20 = (__int64 *)v7;
    McTemplateU0zz_EventWriteTransfer(v19, DeviceCategoryPropertyMissingDisqualified, v20, v21);
LABEL_99:
    v19 = WPP_GLOBAL_Control;
LABEL_100:
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
      WPP_SF_S(v19[2], 58, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids, v49);
    goto LABEL_103;
  }
  if ( !v9 )
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 )
    {
      WPP_SF_(v19[2], 54, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) == 0 )
      goto LABEL_100;
    v24 = DeviceIpAddressPropertyMissingDisqualified;
LABEL_128:
    v25 = &qword_180015D38;
    v26 = &qword_180015D38;
    if ( v6 )
      v26 = (__int64 *)v6;
    if ( v7 )
      v25 = (__int64 *)v7;
    McTemplateU0zz_EventWriteTransfer(v19, v24, v25, v26);
    goto LABEL_133;
  }
  if ( !lpValueName )
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 )
    {
      WPP_SF_(v19[2], 53, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) == 0 )
      goto LABEL_100;
    v24 = DevicePnpxIdPropertyMissingDisqualified;
    goto LABEL_128;
  }
  if ( v7 )
  {
    v5 = STCheckDeviceQualification(
           v51,
           v6,
           v7,
           (unsigned __int16 *)lpValueName,
           (unsigned __int16 *)psz1,
           *(unsigned __int8 **)&v52.Data1,
           v46,
           v8,
           lpString2,
           v45,
           v4,
           v12 >> 1,
           v9,
           &v47);
  }
  else
  {
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 )
    {
      WPP_SF_(v19[2], 52, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) == 0 )
      goto LABEL_100;
    v23 = &qword_180015D38;
    if ( v6 )
      v23 = (__int64 *)v6;
    McTemplateU0z_EventWriteTransfer(v19, DeviceFriendlyNamePropertyMissingDisqualified, v23);
  }
LABEL_133:
  if ( !v47 )
    goto LABEL_99;
  v27 = (CDeviceHandler *)WPP_GLOBAL_Control;
  v28 = v49;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids, v49);
  v29 = *(GUID **)&v53.Data1;
  v30 = CDeviceHandler::_AssociateAep(v27, v28, *(struct _GUID **)&v53.Data1);
  v31 = Buf1;
  v32 = &GUID_NULL;
  v5 = v30;
  if ( v29 )
    v32 = v29;
  v33 = (_DWORD *)*((_QWORD *)NcdAutoSetupTelemetry::Instance() + 1);
  if ( v33 && *v33 )
  {
    NcdAutoSetupTelemetry::Instance();
    v36 = *v32;
    v53 = v31;
    v52 = v36;
    NcdAutoSetupTelemetry::AssociateAep_(v37, v28, &v52, &v53, v5);
  }
  if ( !v8 )
    v8 = (unsigned __int16 *)psz1;
  v38 = -1;
  if ( v8 )
  {
    v39 = -1;
    do
      ++v39;
    while ( v8[v39] );
    if ( (v39 >= 8 && !StrCmpNIW(v8, L"Printers", 8)
       || v39 >= 3 && (!StrCmpNIW(v8, L"MFP", 3) || !StrCmpNIW(v8, L"FAX", 3)))
      && (int)StringCchPrintfW(v62, 0x20u, L"%u", (unsigned int)v5) >= 0 )
    {
      v40 = v62;
      v54[0] = 16;
      if ( !v62[0] )
        v40 = L"(null)";
      v54[2] = 3;
      v54[1] = 1;
      v55 = 0x100000010LL;
      v56 = 1;
      v58 = 0x200000010LL;
      v59 = v40;
      WinSqmAddToStreamEx(0, 10886, 3, v54, 0);
    }
  }
  if ( v5 >= 0 )
  {
    STInsertDeviceInSkipList(lpValueName, 0);
    ++g_dwCurrentAutoSetupCount;
  }
  else
  {
    if ( (Microsoft_Windows_NcdAutoSetupEnableBits & 1) != 0 )
    {
      v44 = v5;
      v41 = 10;
      if ( v7 )
      {
        v42 = -1;
        do
          ++v42;
        while ( v7[v42] );
        v43 = 2 * v42 + 2;
      }
      else
      {
        v7 = L"NULL";
        v43 = 10;
      }
      v55 = (__int64)v7;
      v56 = v43;
      v57 = 0;
      if ( v6 )
      {
        do
          ++v38;
        while ( v6[v38] );
        v41 = 2 * v38 + 2;
      }
      else
      {
        v6 = L"NULL";
      }
      v59 = (unsigned __int16 *)v41;
      v60 = &v44;
      v58 = (__int64)v6;
      v61 = 4;
      McGenEventWrite_EventWriteTransfer(4, DeviceAssociationFailure, v34, 4, v54);
    }
    SqmDeviceQualification(0, 3u, v5, v35, v8, v51);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
    STInsertDeviceInSkipList(lpValueName, 1);
  }
LABEL_103:
  EventActivityIdControl(2u, &ActivityId);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800094c8  mov     rax, rsp
0x1800094cb  push    rbp
0x1800094cc  push    rbx
0x1800094cd  push    rsi
0x1800094ce  push    rdi
0x1800094cf  push    r12
0x1800094d1  push    r13
0x1800094d3  push    r14
0x1800094d5  push    r15
0x1800094d7  lea     rbp, [rsp-78h]
0x1800094dc  sub     rsp, 178h
0x1800094e3  movaps  xmmword ptr [rax-58h], xmm6
0x1800094e7  mov     rax, cs:__security_cookie
0x1800094ee  xor     rax, rsp
0x1800094f1  mov     [rbp+0B0h+var_60], rax
0x1800094f5  mov     rdi, rdx
0x1800094f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094ff  lea     rax, WPP_GLOBAL_Control
0x180009506  cmp     rcx, rax
0x180009509  jz      short loc_180009526
0x18000950b  test    byte ptr [rcx+1Ch], 20h
0x18000950f  jz      short loc_180009526
0x180009511  mov     rcx, [rcx+10h]
0x180009515  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x18000951c  mov     edx, 32h ; '2'
0x180009521  call    WPP_SF_
0x180009526  mov     rax, [rdi+8]
0x18000952a  xor     edx, edx
0x18000952c  mov     r13d, edx
0x18000952f  mov     [rsp+1B0h+var_140], edx
0x180009533  mov     r12d, edx
0x180009536  mov     qword ptr [rbp+0B0h+var_F0.Data1], rdx
0x18000953a  mov     ebx, edx
0x18000953c  mov     [rbp+0B0h+var_110], rdx
0x180009540  mov     r14d, edx
0x180009543  mov     [rbp+0B0h+psz1], rdx
0x180009547  mov     qword ptr [rbp+0B0h+var_100.Data1], rdx
0x18000954b  lea     ecx, [r13+1]; ControlCode
0x18000954f  mov     [rsp+1B0h+var_134], edx
0x180009553  mov     r15d, edx
0x180009556  mov     [rsp+1B0h+var_138], edx
0x18000955a  mov     esi, edx
0x18000955c  mov     [rbp+0B0h+lpValueName], rdx
0x180009560  mov     [rbp+0B0h+var_130], edx
0x180009563  lea     rdx, ActivityId; ActivityId
0x18000956a  mov     [rbp+0B0h+var_120], rax
0x18000956e  call    cs:__imp_EventActivityIdControl
0x180009574  lea     rdx, Buf1; ActivityId
0x18000957b  lea     ecx, [r13+3]; ControlCode
0x18000957f  call    cs:__imp_EventActivityIdControl
0x180009585  lea     r8d, [r13+10h]; Size
0x180009589  lea     rdx, GUID_NULL; Buf2
0x180009590  lea     rcx, Buf1; Buf1
0x180009597  call    memcmp_0
0x18000959c  test    eax, eax
0x18000959e  jz      short loc_1800095B1
0x1800095a0  lea     rdx, Buf1; ActivityId
0x1800095a7  lea     ecx, [r13+2]; ControlCode
0x1800095ab  call    cs:__imp_EventActivityIdControl
0x1800095b1  mov     r9d, [rdi+10h]
0x1800095b5  test    r9d, r9d
0x1800095b8  jz      loc_1800099B8
0x1800095be  mov     rdx, [rdi+18h]
0x1800095c2  xor     r8d, r8d
0x1800095c5  mov     r12, qword ptr cs:DEVPKEY_PNPX_ModelName+8
0x1800095cc  xor     r11d, r11d
0x1800095cf  xor     r10d, r10d
0x1800095d2  mov     rdi, rbx
0x1800095d5  lea     rax, [r10+r10*2]
0x1800095d9  add     rax, rax
0x1800095dc  mov     ecx, [rdx+rax*8+10h]
0x1800095e0  cmp     ecx, 2002h
0x1800095e6  jnz     short loc_180009647
0x1800095e8  mov     rcx, qword ptr cs:DEVPKEY_PNPX_ModelName
0x1800095ef  cmp     [rdx+rax*8], rcx
0x1800095f3  jnz     loc_180009996
0x1800095f9  cmp     [rdx+rax*8+8], r12
0x1800095fe  jnz     loc_180009996
0x180009604  cmp     dword ptr [rdx+rax*8+14h], 0
0x180009609  jnz     loc_180009996
0x18000960f  cmp     qword ptr [rdx+rax*8+18h], 0
0x180009615  jnz     loc_180009996
0x18000961b  cmp     dword ptr [rdx+rax*8+20h], 12h
0x180009620  jnz     loc_180009996
0x180009626  cmp     dword ptr [rdx+rax*8+24h], 2
0x18000962b  jb      loc_180009996
0x180009631  mov     rcx, [rdx+rax*8+28h]
0x180009636  test    rcx, rcx
0x180009639  jz      loc_180009996
0x18000963f  mov     rbx, rcx
0x180009642  jmp     loc_180009996
0x180009647  cmp     ecx, 2000h
0x18000964d  jnz     short loc_1800096B6
0x18000964f  mov     rcx, qword ptr cs:DEVPKEY_PNPX_Manufacturer
0x180009656  cmp     [rdx+rax*8], rcx
0x18000965a  jnz     loc_180009996
0x180009660  mov     rcx, qword ptr cs:DEVPKEY_PNPX_Manufacturer+8
0x180009667  cmp     [rdx+rax*8+8], rcx
0x18000966c  jnz     loc_180009996
0x180009672  cmp     dword ptr [rdx+rax*8+14h], 0
0x180009677  jnz     loc_180009996
0x18000967d  cmp     qword ptr [rdx+rax*8+18h], 0
0x180009683  jnz     loc_180009996
0x180009689  cmp     dword ptr [rdx+rax*8+20h], 12h
0x18000968e  jnz     loc_180009996
0x180009694  cmp     dword ptr [rdx+rax*8+24h], 2
0x180009699  jb      loc_180009996
0x18000969f  mov     rcx, [rdx+rax*8+28h]
0x1800096a4  test    rcx, rcx
0x1800096a7  jz      loc_180009996
0x1800096ad  mov     [rbp+0B0h+var_110], rcx
0x1800096b1  jmp     loc_180009996
0x1800096b6  cmp     ecx, 3004h
0x1800096bc  jnz     short loc_180009734
0x1800096be  mov     rcx, qword ptr cs:DEVPKEY_PNPX_DeviceCategory
0x1800096c5  cmp     [rdx+rax*8], rcx
0x1800096c9  jnz     loc_180009996
0x1800096cf  mov     rcx, qword ptr cs:DEVPKEY_PNPX_DeviceCategory+8
0x1800096d6  cmp     [rdx+rax*8+8], rcx
0x1800096db  jnz     loc_180009996
0x1800096e1  cmp     dword ptr [rdx+rax*8+14h], 0
0x1800096e6  jnz     loc_180009996
0x1800096ec  cmp     qword ptr [rdx+rax*8+18h], 0
0x1800096f2  jnz     loc_180009996
0x1800096f8  cmp     dword ptr [rdx+rax*8+20h], 2012h
0x180009700  jnz     loc_180009996
0x180009706  cmp     dword ptr [rdx+rax*8+24h], 4
0x18000970b  jb      loc_180009996
0x180009711  mov     rcx, [rdx+rax*8+28h]
0x180009716  test    rcx, rcx
0x180009719  jz      loc_180009996
0x18000971f  mov     eax, [rdx+rax*8+24h]
0x180009723  mov     [rsp+1B0h+var_134], eax
0x180009727  mov     [rbp+0B0h+psz1], rcx
0x18000972b  mov     qword ptr [rbp+0B0h+var_100.Data1], rcx
0x18000972f  jmp     loc_180009996
0x180009734  cmp     ecx, 5Ah ; 'Z'
0x180009737  jnz     short loc_1800097AD
0x180009739  mov     rcx, qword ptr cs:PKEY_DeviceDisplay_Category.fmtid.Data1
0x180009740  cmp     [rdx+rax*8], rcx
0x180009744  jnz     loc_180009996
0x18000974a  mov     rcx, qword ptr cs:PKEY_DeviceDisplay_Category.fmtid.Data4
0x180009751  cmp     [rdx+rax*8+8], rcx
0x180009756  jnz     loc_180009996
0x18000975c  cmp     dword ptr [rdx+rax*8+14h], 0
0x180009761  jnz     loc_180009996
0x180009767  cmp     qword ptr [rdx+rax*8+18h], 0
0x18000976d  jnz     loc_180009996
0x180009773  cmp     dword ptr [rdx+rax*8+20h], 2012h
0x18000977b  jnz     loc_180009996
0x180009781  cmp     dword ptr [rdx+rax*8+24h], 4
0x180009786  jb      loc_180009996
0x18000978c  mov     rcx, [rdx+rax*8+28h]
0x180009791  test    rcx, rcx
0x180009794  jz      loc_180009996
0x18000979a  mov     eax, [rdx+rax*8+24h]
0x18000979e  mov     r15, rcx
0x1800097a1  mov     [rsp+1B0h+var_138], eax
0x1800097a5  mov     rdi, rcx
0x1800097a8  jmp     loc_180009996
0x1800097ad  cmp     ecx, 3009h
0x1800097b3  jnz     short loc_18000981E
0x1800097b5  mov     rcx, qword ptr cs:DEVPKEY_PNPX_IpAddress
0x1800097bc  cmp     [rdx+rax*8], rcx
0x1800097c0  jnz     loc_180009996
0x1800097c6  mov     rcx, qword ptr cs:DEVPKEY_PNPX_IpAddress+8
0x1800097cd  cmp     [rdx+rax*8+8], rcx
0x1800097d2  jnz     loc_180009996
0x1800097d8  cmp     dword ptr [rdx+rax*8+14h], 0
0x1800097dd  jnz     loc_180009996
0x1800097e3  cmp     qword ptr [rdx+rax*8+18h], 0
0x1800097e9  jnz     loc_180009996
0x1800097ef  cmp     dword ptr [rdx+rax*8+20h], 2012h
0x1800097f7  jnz     loc_180009996
0x1800097fd  cmp     dword ptr [rdx+rax*8+24h], 4
0x180009802  jb      loc_180009996
0x180009808  mov     rcx, [rdx+rax*8+28h]
0x18000980d  test    rcx, rcx
0x180009810  jz      loc_180009996
0x180009816  mov     rsi, rcx
0x180009819  jmp     loc_180009996
0x18000981e  cmp     ecx, 1005h
0x180009824  jnz     short loc_18000988D
0x180009826  mov     rcx, qword ptr cs:DEVPKEY_PNPX_ID
0x18000982d  cmp     [rdx+rax*8], rcx
0x180009831  jnz     loc_180009996
0x180009837  mov     rcx, qword ptr cs:DEVPKEY_PNPX_ID+8
0x18000983e  cmp     [rdx+rax*8+8], rcx
0x180009843  jnz     loc_180009996
0x180009849  cmp     dword ptr [rdx+rax*8+14h], 0
0x18000984e  jnz     loc_180009996
0x180009854  cmp     qword ptr [rdx+rax*8+18h], 0
0x18000985a  jnz     loc_180009996
0x180009860  cmp     dword ptr [rdx+rax*8+20h], 12h
0x180009865  jnz     loc_180009996
0x18000986b  cmp     dword ptr [rdx+rax*8+24h], 2
0x180009870  jb      loc_180009996
0x180009876  mov     rcx, [rdx+rax*8+28h]
0x18000987b  test    rcx, rcx
0x18000987e  jz      loc_180009996
0x180009884  mov     [rbp+0B0h+lpValueName], rcx
0x180009888  jmp     loc_180009996
0x18000988d  cmp     ecx, 2
0x180009890  jnz     short loc_1800098F9
0x180009892  mov     rcx, qword ptr cs:DEVPKEY_Aep_ContainerId
0x180009899  cmp     [rdx+rax*8], rcx
0x18000989d  jnz     loc_180009996
0x1800098a3  mov     rcx, qword ptr cs:DEVPKEY_Aep_ContainerId+8
0x1800098aa  cmp     [rdx+rax*8+8], rcx
0x1800098af  jnz     loc_180009996
0x1800098b5  cmp     dword ptr [rdx+rax*8+14h], 0
0x1800098ba  jnz     loc_180009996
0x1800098c0  cmp     qword ptr [rdx+rax*8+18h], 0
0x1800098c6  jnz     loc_180009996
0x1800098cc  cmp     dword ptr [rdx+rax*8+20h], 0Dh
0x1800098d1  jnz     loc_180009996
0x1800098d7  cmp     dword ptr [rdx+rax*8+24h], 10h
0x1800098dc  jnz     loc_180009996
0x1800098e2  mov     rcx, [rdx+rax*8+28h]
0x1800098e7  test    rcx, rcx
0x1800098ea  jz      loc_180009996
0x1800098f0  mov     qword ptr [rbp+0B0h+var_F0.Data1], rcx
0x1800098f4  jmp     loc_180009996
0x1800098f9  cmp     ecx, 4
0x1800098fc  jnz     short loc_180009941
0x1800098fe  mov     rcx, qword ptr cs:DEVPKEY_Aep_FriendlyName
0x180009905  cmp     [rdx+rax*8], rcx
0x180009909  jnz     loc_180009996
0x18000990f  mov     rcx, qword ptr cs:DEVPKEY_Aep_FriendlyName+8
0x180009916  cmp     [rdx+rax*8+8], rcx
0x18000991b  jnz     short loc_180009996
0x18000991d  cmp     dword ptr [rdx+rax*8+14h], 0
0x180009922  jnz     short loc_180009996
0x180009924  cmp     dword ptr [rdx+rax*8+20h], 12h
0x180009929  jnz     short loc_180009996
0x18000992b  cmp     dword ptr [rdx+rax*8+24h], 2
0x180009930  jb      short loc_180009996
0x180009932  mov     rcx, [rdx+rax*8+28h]
0x180009937  test    rcx, rcx
0x18000993a  jz      short loc_180009996
0x18000993c  mov     r14, rcx
0x18000993f  jmp     short loc_180009996
0x180009941  cmp     ecx, 1001h
0x180009947  jnz     short loc_180009996
0x180009949  mov     rcx, qword ptr cs:DEVPKEY_PNPX_Types
0x180009950  cmp     [rdx+rax*8], rcx
0x180009954  jnz     short loc_180009996
0x180009956  mov     rcx, qword ptr cs:DEVPKEY_PNPX_Types+8
0x18000995d  cmp     [rdx+rax*8+8], rcx
0x180009962  jnz     short loc_180009996
0x180009964  cmp     dword ptr [rdx+rax*8+14h], 0
0x180009969  jnz     short loc_180009996
0x18000996b  cmp     qword ptr [rdx+rax*8+18h], 0
0x180009971  jnz     short loc_180009996
0x180009973  cmp     dword ptr [rdx+rax*8+20h], 2012h
0x18000997b  jnz     short loc_180009996
0x18000997d  cmp     dword ptr [rdx+rax*8+24h], 4
0x180009982  jb      short loc_180009996
0x180009984  mov     rcx, [rdx+rax*8+28h]
0x180009989  test    rcx, rcx
0x18000998c  jz      short loc_180009996
0x18000998e  mov     r8d, [rdx+rax*8+24h]
0x180009993  mov     r13, rcx
0x180009996  inc     r11d
0x180009999  inc     r10
0x18000999c  cmp     r11d, r9d
0x18000999f  jb      loc_1800095D5
0x1800099a5  mov     r12d, [rsp+1B0h+var_140]
0x1800099aa  test    r13, r13
0x1800099ad  jz      short loc_1800099BB
0x1800099af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099b6  jmp     short loc_1800099F3
0x1800099b8  mov     rdi, rbx
0x1800099bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099c2  lea     rax, WPP_GLOBAL_Control
0x1800099c9  cmp     rcx, rax
0x1800099cc  jz      short loc_1800099F0
0x1800099ce  test    byte ptr [rcx+1Ch], 4
0x1800099d2  jz      short loc_1800099F0
0x1800099d4  mov     rcx, [rcx+10h]
0x1800099d8  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x1800099df  mov     edx, 33h ; '3'
0x1800099e4  call    WPP_SF_
0x1800099e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099f0  xor     r8d, r8d
0x1800099f3  mov     rax, qword ptr [rbp+0B0h+var_100.Data1]
0x1800099f7  test    rax, rax
0x1800099fa  jnz     loc_180009AFF
0x180009a00  test    rdi, rdi
0x180009a03  jnz     loc_180009AFF
0x180009a09  lea     rax, WPP_GLOBAL_Control
0x180009a10  cmp     rcx, rax
0x180009a13  jz      short loc_180009A35
0x180009a15  test    byte ptr [rcx+1Ch], 4
0x180009a19  jz      short loc_180009A35
0x180009a1b  mov     rcx, [rcx+10h]
0x180009a1f  lea     edx, [rdi+37h]
0x180009a22  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180009a29  call    WPP_SF_
0x180009a2e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
