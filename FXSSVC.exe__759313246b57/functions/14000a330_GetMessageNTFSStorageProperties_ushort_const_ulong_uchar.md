# GetMessageNTFSStorageProperties(ushort const *,ulong,uchar *)

- ea: `0x14000a330`
- end: `0x14000b0e9`
- name: `?GetMessageNTFSStorageProperties@@YAHPEBGKPEAE@Z`
- size: `3513`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400154f4`

## callees

- `0x140002946`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004f64`
- `0x140006d38`
- `0x1400078a4`
- `0x14000a330`
- `0x140052624`
- `0x14006af2c`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000a439`
- `KERNEL32!GetLastError` at `0x14000a4a8`
- `KERNEL32!GetLastError` at `0x14000ae72`
- `KERNEL32!GetLastError` at `0x14000aeb8`
- `KERNEL32!GetLastError` at `0x14000aef8`
- `KERNEL32!GetLastError` at `0x14000af3b`
- `KERNEL32!GetLastError` at `0x14000a439`
- `KERNEL32!GetLastError` at `0x14000a4a8`
- `KERNEL32!GetLastError` at `0x14000ae72`
- `KERNEL32!GetLastError` at `0x14000aeb8`
- `KERNEL32!GetLastError` at `0x14000aef8`
- `KERNEL32!GetLastError` at `0x14000af3b`
- `KERNEL32!SetLastError` at `0x14000b09c`
- `KERNEL32!SetLastError` at `0x14000b09c`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a955`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a9df`
- `KERNEL32!FileTimeToSystemTime` at `0x14000aac9`
- `KERNEL32!FileTimeToSystemTime` at `0x14000ab00`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a955`
- `KERNEL32!FileTimeToSystemTime` at `0x14000a9df`
- `KERNEL32!FileTimeToSystemTime` at `0x14000aac9`
- `KERNEL32!FileTimeToSystemTime` at `0x14000ab00`
- `KERNEL32!FindFirstFileW` at `0x14000a3f9`
- `KERNEL32!FindFirstFileW` at `0x14000a3f9`
- `KERNEL32!FindClose` at `0x14000a479`
- `KERNEL32!FindClose` at `0x14000a479`
- `KERNEL32!LocalFree` at `0x14000b0b0`
- `KERNEL32!LocalFree` at `0x14000b0b0`
- `msvcrt!wcsrchr` at `0x14000adf3`
- `msvcrt!wcsrchr` at `0x14000adf3`
- `ole32!FreePropVariantArray` at `0x14000b04a`
- `ole32!FreePropVariantArray` at `0x14000b04a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetMessageNTFSStorageProperties(const unsigned __int16 *a1, unsigned int a2, unsigned __int8 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rsi
  size_t v7; // rdi
  void *v8; // r12
  ULONG v10; // r13d
  HANDLE FirstFileW; // rcx
  DWORD LastError; // eax
  DWORD v13; // eax
  int v14; // eax
  DWORD v15; // ebx
  unsigned int v16; // edi
  int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // r9
  CMapDeviceId *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  int v40; // eax
  int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v46; // eax
  int v47; // eax
  PROPVARIANT v48; // rax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  wchar_t *v52; // rax
  CFaxArchiving *v53; // rcx
  void **v54; // r9
  const unsigned __int16 *v55; // rdx
  unsigned int ComponentsFromArchiveFileName; // eax
  DWORD v57; // eax
  int v58; // ecx
  HRESULT v59; // eax
  FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  int v61; // [rsp+40h] [rbp-C0h]
  void *v62; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+50h] [rbp-B0h] BYREF
  struct IPropertySetStorage *v64; // [rsp+58h] [rbp-A8h] BYREF
  int Src; // [rsp+60h] [rbp-A0h] BYREF
  int v66; // [rsp+64h] [rbp-9Ch]
  unsigned __int64 v67[2]; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+78h] [rbp-88h]
  int v69; // [rsp+7Ch] [rbp-84h]
  int v70; // [rsp+80h] [rbp-80h]
  DWORD nFileSizeLow; // [rsp+90h] [rbp-70h]
  int v73; // [rsp+94h] [rbp-6Ch]
  struct _SYSTEMTIME v82; // [rsp+D8h] [rbp-28h] BYREF
  struct _SYSTEMTIME v83; // [rsp+E8h] [rbp-18h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+F8h] [rbp-8h] BYREF
  struct _SYSTEMTIME v85; // [rsp+108h] [rbp+8h] BYREF
  int v87; // [rsp+120h] [rbp+20h]
  int v88; // [rsp+124h] [rbp+24h]
  BOOL v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  BOOL v96; // [rsp+158h] [rbp+58h]
  int v97; // [rsp+15Ch] [rbp+5Ch]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+160h] [rbp+60h] BYREF
  PROPVARIANT rgvars[88]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v3 = 0;
  v4 = a2;
  v64 = 0;
  v63 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  v7 = 256;
  memset_0(&Src, 0, 0x100u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileTime = 0;
  v8 = 0;
  v62 = 0;
  if ( (unsigned int)v4 >= 2 )
    return 87;
  v61 = 0;
  v10 = 0;
  FirstFileW = FindFirstFileW(a1, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        LastError,
        (__int64)a1);
    }
  }
  else
  {
    v66 |= 0x10u;
    nFileSizeLow = FindFileData.nFileSizeLow;
    if ( !FindClose(FirstFileW)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v13);
    }
  }
  v14 = FaxStgOpenStorageEx(a1, 0x20u, &v64);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v14);
    }
    v15 = 110;
    goto LABEL_23;
  }
  v17 = ((__int64 (__fastcall *)(struct IPropertySetStorage *, __int64 *, __int64, __int64 *))v64->lpVtbl->Open)(
          v64,
          qword_140092760,
          16,
          &v63);
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (_DWORD)a1,
        v17);
    }
    v15 = 110;
    goto LABEL_30;
  }
  v10 = *((_DWORD *)qword_140092950 + v4);
  if ( v10 > 0x1D )
  {
    v15 = 1359;
LABEL_30:
    v16 = 0;
    goto LABEL_201;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, PROPVARIANT *))(*(_QWORD *)v63 + 24LL))(
          v63,
          v10,
          qword_140092960,
          rgvars);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v18);
    }
    v15 = 30;
    goto LABEL_23;
  }
  v61 = 1;
  if ( !v10 )
  {
LABEL_165:
    v52 = wcsrchr(a1, 0x5Cu);
    v54 = &v62;
    if ( !(_DWORD)v4 )
      v54 = 0;
    v55 = v52 + 1;
    if ( !v52 )
      v55 = 0;
    ComponentsFromArchiveFileName = CFaxArchiving::ExtractComponentsFromArchiveFileName(v53, v55, v67, v54);
    v15 = ComponentsFromArchiveFileName;
    if ( ComponentsFromArchiveFileName )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          113,
          &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
          ComponentsFromArchiveFileName);
      }
      v8 = v62;
      v16 = 0;
    }
    else
    {
      v8 = v62;
      v58 = v66 | 0x80000;
      v66 |= 0x80000u;
      if ( (_DWORD)v4 )
      {
        v96 = v62 == 0;
        v66 = v58 | 0x400000;
      }
      else
      {
        v7 = 232;
      }
      Src = v7;
      memcpy_0(a3, &Src, v7);
      v16 = 1;
    }
    goto LABEL_201;
  }
  while ( 1 )
  {
    if ( !LOWORD(rgvars[3 * v3]) )
      goto LABEL_164;
    v19 = qword_140092960[2 * v3 + 1];
    if ( v19 > 0xC8 )
      break;
    if ( v19 == 200 )
    {
      if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
      {
        v25 = 8;
        v15 = 8;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_200;
        }
        v27 = 106;
LABEL_83:
        WPP_SF_d(*((_QWORD *)v26 + 2), v27, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v25);
        goto LABEL_23;
      }
    }
    else if ( v19 > 0x70 )
    {
      if ( v19 > 0x76 )
      {
        v42 = v19 - 119;
        if ( v42 )
        {
          v43 = v42 - 1;
          if ( v43 )
          {
            v44 = v43 - 1;
            if ( v44 )
            {
              v45 = v44 - 1;
              if ( v45 )
              {
                if ( v45 == 1 )
                {
                  v46 = (int)rgvars[3 * v3 + 1];
                  v66 |= 0x800000u;
                  v97 = v46;
                }
                goto LABEL_164;
              }
              if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
              {
                v25 = 8;
                v15 = 8;
                v26 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_200;
                }
                v27 = 112;
                goto LABEL_83;
              }
            }
            else
            {
              v47 = (int)rgvars[3 * v3 + 1];
              v66 |= 0x200000u;
              v94 = v47;
            }
          }
          else
          {
            v93 = LOWORD(rgvars[3 * v3 + 1]) == 0xFFFF;
          }
        }
        else
        {
          v48 = rgvars[3 * v3 + 1];
          v66 |= 0x100000u;
          v67[1] = (unsigned __int64)v48;
        }
      }
      else if ( v19 == 118 )
      {
        if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 111;
          goto LABEL_83;
        }
      }
      else
      {
        v36 = v19 - 113;
        if ( !v36 )
        {
          FileTime = (FILETIME)rgvars[3 * v3 + 1];
          if ( FileTimeToSystemTime(&FileTime, &v83) )
          {
            v66 |= 0x400u;
            goto LABEL_164;
          }
          v57 = GetLastError();
          v15 = v57;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = 103;
            goto LABEL_179;
          }
          goto LABEL_23;
        }
        v37 = v36 - 1;
        if ( !v37 )
        {
          FileTime = (FILETIME)rgvars[3 * v3 + 1];
          if ( FileTimeToSystemTime(&FileTime, &v82) )
          {
            v66 |= 0x200u;
            goto LABEL_164;
          }
          v57 = GetLastError();
          v15 = v57;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = 104;
            goto LABEL_179;
          }
          goto LABEL_23;
        }
        v38 = v37 - 1;
        if ( v38 )
        {
          v39 = v38 - 1;
          if ( v39 )
          {
            if ( v39 == 1 )
            {
              v40 = (int)rgvars[3 * v3 + 1];
              v66 |= 8u;
              v70 = v40;
            }
          }
          else
          {
            v41 = (int)rgvars[3 * v3 + 1];
            v66 |= 4u;
            v69 = v41;
          }
        }
        else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 105;
          goto LABEL_83;
        }
      }
    }
    else
    {
      if ( v19 == 112 )
      {
        FileTime = (FILETIME)rgvars[3 * v3 + 1];
        if ( FileTimeToSystemTime(&FileTime, &v85) )
        {
          v66 |= 0x1000u;
          goto LABEL_164;
        }
        v57 = GetLastError();
        v15 = v57;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v27 = 102;
          goto LABEL_179;
        }
LABEL_23:
        v16 = 0;
        goto LABEL_201;
      }
      if ( v19 > 0x6A )
      {
        v28 = v19 - 107;
        if ( !v28 )
        {
          v35 = (int)rgvars[3 * v3 + 1];
          v66 |= 0x4000u;
          v88 = v35;
          goto LABEL_164;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v34 = (int)rgvars[3 * v3 + 1];
          v66 |= 0x2000u;
          v87 = v34;
          goto LABEL_164;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
          v33 = (int)rgvars[3 * v3 + 1];
          v66 |= 0x20u;
          v73 = v33;
          goto LABEL_164;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          v32 = (int)rgvars[3 * v3 + 1];
          v66 |= 2u;
          v68 = v32;
          goto LABEL_164;
        }
        if ( v31 == 1 )
        {
          FileTime = (FILETIME)rgvars[3 * v3 + 1];
          if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
          {
            v66 |= 0x800u;
            goto LABEL_164;
          }
          v57 = GetLastError();
          v15 = v57;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = 101;
LABEL_179:
            v25 = v57;
            goto LABEL_83;
          }
          goto LABEL_23;
        }
      }
      else if ( v19 == 106 )
      {
        if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 100;
          goto LABEL_83;
        }
      }
      else
      {
        v20 = v19 - 100;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                v24 = v23 - 1;
                if ( v24 )
                {
                  if ( v24 == 1 && !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
                  {
                    v25 = 8;
                    v15 = 8;
                    v26 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
                      goto LABEL_200;
                    }
                    v27 = 99;
                    goto LABEL_83;
                  }
                }
                else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
                {
                  v25 = 8;
                  v15 = 8;
                  v26 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    goto LABEL_200;
                  }
                  v27 = 98;
                  goto LABEL_83;
                }
              }
              else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
              {
                v25 = 8;
                v15 = 8;
                v26 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_200;
                }
                v27 = 97;
                goto LABEL_83;
              }
            }
            else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
            {
              v25 = 8;
              v15 = 8;
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_200;
              }
              v27 = 96;
              goto LABEL_83;
            }
          }
          else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
          {
            v25 = 8;
            v15 = 8;
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_200;
            }
            v27 = 95;
            goto LABEL_83;
          }
        }
        else if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
        {
          v25 = 8;
          v15 = 8;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_200;
          }
          v27 = 94;
          goto LABEL_83;
        }
      }
    }
LABEL_164:
    if ( ++v3 >= v10 )
      goto LABEL_165;
  }
  v49 = v19 - 201;
  if ( !v49 )
  {
    if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    {
      v25 = 8;
      v15 = 8;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = 107;
        goto LABEL_83;
      }
      goto LABEL_200;
    }
    goto LABEL_164;
  }
  v50 = v49 - 99;
  if ( !v50 )
  {
    if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    {
      v25 = 8;
      v15 = 8;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = 110;
        goto LABEL_83;
      }
      goto LABEL_200;
    }
    goto LABEL_164;
  }
  v51 = v50 - 1;
  if ( !v51 )
  {
    if ( !StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    {
      v25 = 8;
      v15 = 8;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = 108;
        goto LABEL_83;
      }
      goto LABEL_200;
    }
    goto LABEL_164;
  }
  if ( v51 != 1 )
    goto LABEL_164;
  if ( StringDup((unsigned __int16 *)rgvars[3 * v3 + 1]) )
    goto LABEL_164;
  v25 = 8;
  v15 = 8;
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v27 = 109;
    goto LABEL_83;
  }
LABEL_200:
  v16 = 0;
LABEL_201:
  if ( v63 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  if ( v64 )
    ((void (__fastcall *)(struct IPropertySetStorage *))v64->lpVtbl->Release)(v64);
  if ( v61 == 1 )
  {
    v59 = FreePropVariantArray(v10, rgvars);
    if ( v59 < 0
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v59);
    }
  }
  if ( !v16 )
  {
    FreeMessageBuffer1((struct _FAX_MESSAGE_1 *)&Src, 0);
    SetLastError(v15);
  }
  if ( v8 )
    LocalFree(v8);
  return v16;
}

```

## disassembly

```asm
0x14000a330  mov     [rsp-8+arg_18], rbx
0x14000a335  push    rbp
0x14000a336  push    rsi
0x14000a337  push    rdi
0x14000a338  push    r12
0x14000a33a  push    r13
0x14000a33c  push    r14
0x14000a33e  push    r15
0x14000a340  lea     rbp, [rsp-580h]
0x14000a348  sub     rsp, 680h
0x14000a34f  mov     rax, cs:__security_cookie
0x14000a356  xor     rax, rsp
0x14000a359  mov     [rbp+5B0h+var_40], rax
0x14000a360  xor     ebx, ebx
0x14000a362  mov     esi, edx
0x14000a364  mov     [rsp+6B0h+var_658], rbx
0x14000a369  mov     r15, r8
0x14000a36c  mov     [rsp+6B0h+var_660], rbx
0x14000a371  mov     r14, rcx
0x14000a374  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a37b  lea     rax, WPP_GLOBAL_Control
0x14000a382  cmp     rcx, rax
0x14000a385  jz      short loc_14000A3A6
0x14000a387  test    byte ptr [rcx+1Ch], 4
0x14000a38b  jz      short loc_14000A3A6
0x14000a38d  cmp     byte ptr [rcx+19h], 5
0x14000a391  jb      short loc_14000A3A6
0x14000a393  mov     rcx, [rcx+10h]
0x14000a397  lea     edx, [rbx+58h]
0x14000a39a  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000a3a1  call    WPP_SF_
0x14000a3a6  mov     edi, 100h
0x14000a3ab  lea     rcx, [rsp+6B0h+Src]; void *
0x14000a3b0  mov     r8d, edi; Size
0x14000a3b3  xor     edx, edx; Val
0x14000a3b5  call    memset_0
0x14000a3ba  xor     edx, edx; Val
0x14000a3bc  lea     rcx, [rbp+5B0h+FindFileData]; void *
0x14000a3c0  mov     r8d, 250h; Size
0x14000a3c6  call    memset_0
0x14000a3cb  mov     qword ptr [rsp+6B0h+FileTime.dwLowDateTime], rbx
0x14000a3d0  mov     r12, rbx
0x14000a3d3  mov     [rsp+6B0h+var_668], rbx
0x14000a3d8  cmp     esi, 2
0x14000a3db  jb      short loc_14000A3E7
0x14000a3dd  mov     eax, 57h ; 'W'
0x14000a3e2  jmp     loc_14000B0BE
0x14000a3e7  lea     rdx, [rbp+5B0h+FindFileData]; lpFindFileData
0x14000a3eb  mov     [rsp+6B0h+var_680], ebx
0x14000a3ef  mov     rcx, r14; lpFileName
0x14000a3f2  mov     [rsp+6B0h+var_670], ebx
0x14000a3f6  mov     r13d, ebx
0x14000a3f9  call    cs:__imp_FindFirstFileW
0x14000a400  nop     dword ptr [rax+rax+00h]
0x14000a405  mov     rcx, rax; hFindFile
0x14000a408  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a40c  jnz     short loc_14000A46B
0x14000a40e  mov     rax, cs:WPP_GLOBAL_Control
0x14000a415  lea     rcx, WPP_GLOBAL_Control
0x14000a41c  cmp     rax, rcx
0x14000a41f  jz      loc_14000A4D3
0x14000a425  test    byte ptr [rax+1Ch], 4
0x14000a429  jz      loc_14000A4D3
0x14000a42f  cmp     byte ptr [rax+19h], 2
0x14000a433  jb      loc_14000A4D3
0x14000a439  call    cs:__imp_GetLastError
0x14000a440  nop     dword ptr [rax+rax+00h]
0x14000a445  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a44c  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000a453  mov     edx, 59h ; 'Y'
0x14000a458  mov     [rsp+6B0h+var_690], r14
0x14000a45d  mov     r9d, eax
0x14000a460  mov     rcx, [rcx+10h]
0x14000a464  call    WPP_SF_DS
0x14000a469  jmp     short loc_14000A4D3
0x14000a46b  mov     eax, [rbp+5B0h+FindFileData.nFileSizeLow]
0x14000a471  or      [rsp+6B0h+var_64C], 10h
0x14000a476  mov     [rbp+5B0h+var_620], eax
0x14000a479  call    cs:__imp_FindClose
0x14000a480  nop     dword ptr [rax+rax+00h]
0x14000a485  test    eax, eax
0x14000a487  jnz     short loc_14000A4D3
0x14000a489  mov     rax, cs:WPP_GLOBAL_Control
0x14000a490  lea     rcx, WPP_GLOBAL_Control
0x14000a497  cmp     rax, rcx
0x14000a49a  jz      short loc_14000A4D3
0x14000a49c  test    byte ptr [rax+1Ch], 4
0x14000a4a0  jz      short loc_14000A4D3
0x14000a4a2  cmp     byte ptr [rax+19h], 2
0x14000a4a6  jb      short loc_14000A4D3
0x14000a4a8  call    cs:__imp_GetLastError
0x14000a4af  nop     dword ptr [rax+rax+00h]
0x14000a4b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4bb  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000a4c2  mov     edx, 5Ah ; 'Z'
0x14000a4c7  mov     r9d, eax
0x14000a4ca  mov     rcx, [rcx+10h]
0x14000a4ce  call    WPP_SF_d
0x14000a4d3  lea     r8, [rsp+6B0h+var_658]; struct IPropertySetStorage **
0x14000a4d8  mov     edx, 20h ; ' '; unsigned int
0x14000a4dd  mov     rcx, r14; unsigned __int16 *
0x14000a4e0  call    ?FaxStgOpenStorageEx@@YAJPEBGKPEAPEAUIPropertySetStorage@@@Z; FaxStgOpenStorageEx(ushort const *,ulong,IPropertySetStorage * *)
0x14000a4e5  test    eax, eax
0x14000a4e7  jns     short loc_14000A52D
0x14000a4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4f0  lea     r14, WPP_GLOBAL_Control
0x14000a4f7  cmp     rcx, r14
0x14000a4fa  jz      short loc_14000A520
0x14000a4fc  test    byte ptr [rcx+1Ch], 4
0x14000a500  jz      short loc_14000A520
0x14000a502  cmp     byte ptr [rcx+19h], 2
0x14000a506  jb      short loc_14000A520
0x14000a508  mov     rcx, [rcx+10h]
0x14000a50c  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000a513  mov     edx, 5Bh ; '['
0x14000a518  mov     r9d, eax
0x14000a51b  call    WPP_SF_d
0x14000a520  mov     ebx, 6Eh ; 'n'
0x14000a525  mov     edi, r12d
0x14000a528  jmp     loc_14000B00D
0x14000a52d  mov     rcx, [rsp+6B0h+var_658]
0x14000a532  lea     r9, [rsp+6B0h+var_660]
0x14000a537  mov     r8d, 10h
0x14000a53d  lea     rdx, qword_140092760
0x14000a544  mov     rax, [rcx]
0x14000a547  mov     rax, [rax+20h]
0x14000a54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a550  test    eax, eax
0x14000a552  jns     short loc_14000A5A3
0x14000a554  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a55b  lea     rdx, WPP_GLOBAL_Control
0x14000a562  cmp     rcx, rdx
0x14000a565  jz      short loc_14000A58F
0x14000a567  test    byte ptr [rcx+1Ch], 4
0x14000a56b  jz      short loc_14000A58F
0x14000a56d  cmp     byte ptr [rcx+19h], 2
0x14000a571  jb      short loc_14000A58F
0x14000a573  mov     rcx, [rcx+10h]
0x14000a577  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000a57e  mov     edx, 5Ch ; '\'
0x14000a583  mov     dword ptr [rsp+6B0h+var_690], eax
0x14000a587  mov     r9, r14
0x14000a58a  call    WPP_SF_Sd
0x14000a58f  mov     ebx, 6Eh ; 'n'
0x14000a594  mov     edi, r12d
0x14000a597  lea     r14, WPP_GLOBAL_Control
0x14000a59e  jmp     loc_14000B00D
0x14000a5a3  lea     r13, qword_140092950
0x14000a5aa  mov     r13d, [r13+rsi*4+0]
0x14000a5af  cmp     r13d, 1Dh
0x14000a5b3  jbe     short loc_14000A5BC
0x14000a5b5  mov     ebx, 54Fh
0x14000a5ba  jmp     short loc_14000A594
0x14000a5bc  mov     rcx, [rsp+6B0h+var_660]
0x14000a5c1  lea     r9, [rbp+5B0h+rgvars]
0x14000a5c8  lea     r8, qword_140092960
0x14000a5cf  mov     edx, r13d
0x14000a5d2  mov     rax, [rcx]
0x14000a5d5  mov     rax, [rax+18h]
0x14000a5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5de  test    eax, eax
0x14000a5e0  jns     short loc_14000A623
0x14000a5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5e9  lea     r14, WPP_GLOBAL_Control
0x14000a5f0  cmp     rcx, r14
0x14000a5f3  jz      short loc_14000A619
0x14000a5f5  test    byte ptr [rcx+1Ch], 4
0x14000a5f9  jz      short loc_14000A619
0x14000a5fb  cmp     byte ptr [rcx+19h], 2
0x14000a5ff  jb      short loc_14000A619
0x14000a601  mov     rcx, [rcx+10h]
0x14000a605  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000a60c  mov     edx, 5Dh ; ']'
0x14000a611  mov     r9d, eax
0x14000a614  call    WPP_SF_d
0x14000a619  mov     ebx, 1Eh
0x14000a61e  jmp     loc_14000A525
0x14000a623  xor     edx, edx
0x14000a625  mov     [rsp+6B0h+var_670], 1
0x14000a62d  test    r13d, r13d
0x14000a630  jz      loc_14000ADEB
0x14000a636  mov     eax, ebx
0x14000a638  lea     rcx, [rax+rax*2]
0x14000a63c  cmp     word ptr [rbp+rcx*8+5B0h+rgvars], dx
0x14000a644  jz      loc_14000ADE0
0x14000a64a  add     rax, rax
0x14000a64d  lea     r8, qword_140092960
0x14000a654  mov     eax, [r8+rax*8+8]
0x14000a659  cmp     eax, 0C8h
0x14000a65e  ja      loc_14000ACA4
0x14000a664  jz      loc_14000AC4E
0x14000a66a  cmp     eax, 70h ; 'p'
0x14000a66d  ja      loc_14000AA00
0x14000a673  jz      loc_14000A9C9
0x14000a679  cmp     eax, 6Ah ; 'j'
0x14000a67c  ja      loc_14000A91E
0x14000a682  jz      loc_14000A8CB
0x14000a688  sub     eax, 64h ; 'd'
0x14000a68b  jz      loc_14000A865
0x14000a691  sub     eax, 1
0x14000a694  jz      loc_14000A812
0x14000a69a  sub     eax, 1
0x14000a69d  jz      loc_14000A7BC
0x14000a6a3  sub     eax, 1
0x14000a6a6  jz      loc_14000A766
0x14000a6ac  sub     eax, 1
0x14000a6af  jz      short loc_14000A710
0x14000a6b1  cmp     eax, 1
0x14000a6b4  jnz     loc_14000ADE0
0x14000a6ba  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a6c2  call    StringDup
0x14000a6c7  xor     edx, edx
0x14000a6c9  mov     [rbp+5B0h+var_588], rax
0x14000a6cd  test    rax, rax
0x14000a6d0  jnz     loc_14000ADE0
0x14000a6d6  lea     r9d, [rax+8]
0x14000a6da  mov     ebx, r9d
0x14000a6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6e4  lea     r14, WPP_GLOBAL_Control
0x14000a6eb  cmp     rcx, r14
0x14000a6ee  jz      loc_14000B00B
0x14000a6f4  test    byte ptr [rcx+1Ch], 4
0x14000a6f8  jz      loc_14000B00B
0x14000a6fe  cmp     byte ptr [rcx+19h], 2
0x14000a702  jb      loc_14000B00B
0x14000a708  lea     edx, [rax+63h]
0x14000a70b  jmp     loc_14000A8B6
0x14000a710  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a718  call    StringDup
0x14000a71d  xor     edx, edx
0x14000a71f  mov     [rbp+5B0h+var_578], rax
0x14000a723  test    rax, rax
0x14000a726  jnz     loc_14000ADE0
0x14000a72c  lea     r9d, [rax+8]
0x14000a730  mov     ebx, r9d
0x14000a733  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a73a  lea     r14, WPP_GLOBAL_Control
0x14000a741  cmp     rcx, r14
0x14000a744  jz      loc_14000B00B
0x14000a74a  test    byte ptr [rcx+1Ch], 4
0x14000a74e  jz      loc_14000B00B
0x14000a754  cmp     byte ptr [rcx+19h], 2
0x14000a758  jb      loc_14000B00B
0x14000a75e  lea     edx, [rax+62h]
0x14000a761  jmp     loc_14000A8B6
0x14000a766  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a76e  call    StringDup
0x14000a773  xor     edx, edx
0x14000a775  mov     [rbp+5B0h+var_570], rax
0x14000a779  test    rax, rax
0x14000a77c  jnz     loc_14000ADE0
0x14000a782  lea     r9d, [rax+8]
0x14000a786  mov     ebx, r9d
0x14000a789  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a790  lea     r14, WPP_GLOBAL_Control
0x14000a797  cmp     rcx, r14
0x14000a79a  jz      loc_14000B00B
0x14000a7a0  test    byte ptr [rcx+1Ch], 4
0x14000a7a4  jz      loc_14000B00B
0x14000a7aa  cmp     byte ptr [rcx+19h], 2
0x14000a7ae  jb      loc_14000B00B
0x14000a7b4  lea     edx, [rax+61h]
0x14000a7b7  jmp     loc_14000A8B6
0x14000a7bc  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a7c4  call    StringDup
0x14000a7c9  xor     edx, edx
0x14000a7cb  mov     [rbp+5B0h+var_598], rax
0x14000a7cf  test    rax, rax
0x14000a7d2  jnz     loc_14000ADE0
0x14000a7d8  lea     r9d, [rax+8]
0x14000a7dc  mov     ebx, r9d
0x14000a7df  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7e6  lea     r14, WPP_GLOBAL_Control
0x14000a7ed  cmp     rcx, r14
0x14000a7f0  jz      loc_14000B00B
0x14000a7f6  test    byte ptr [rcx+1Ch], 4
0x14000a7fa  jz      loc_14000B00B
0x14000a800  cmp     byte ptr [rcx+19h], 2
0x14000a804  jb      loc_14000B00B
0x14000a80a  lea     edx, [rax+60h]
0x14000a80d  jmp     loc_14000A8B6
0x14000a812  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
0x14000a81a  call    StringDup
0x14000a81f  xor     edx, edx
0x14000a821  mov     [rbp+5B0h+var_5F8], rax
0x14000a825  test    rax, rax
0x14000a828  jnz     loc_14000ADE0
0x14000a82e  lea     r9d, [rax+8]
0x14000a832  mov     ebx, r9d
0x14000a835  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a83c  lea     r14, WPP_GLOBAL_Control
0x14000a843  cmp     rcx, r14
0x14000a846  jz      loc_14000B00B
0x14000a84c  test    byte ptr [rcx+1Ch], 4
0x14000a850  jz      loc_14000B00B
0x14000a856  cmp     byte ptr [rcx+19h], 2
0x14000a85a  jb      loc_14000B00B
0x14000a860  lea     edx, [rax+5Fh]
0x14000a863  jmp     short loc_14000A8B6
0x14000a865  mov     rcx, [rbp+rcx*8+5B0h+var_2F8]; unsigned __int16 *
  ... truncated ...
```
