# CBthActiveConnector::_IsActiveConnectEnabled(ushort const *)

- ea: `0x180007880`
- end: `0x180007f22`
- name: `?_IsActiveConnectEnabled@CBthActiveConnector@@AEAAHPEBG@Z`
- size: `1698`
- prototype: `int(CBthActiveConnector *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004620`

## callees

- `0x180007880`
- `0x180007f28`
- `0x1800097d0`
- `0x18000e080`
- `0x18000e59c`
- `0x1800116ac`
- `0x1800117a0`
- `0x180011834`
- `0x180011918`
- `0x180011cc0`
- `0x180011d80`
- `0x180011db0`
- `0x180011de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007d92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007d92`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007998`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e9a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007b1e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007b1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007b8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007b8d`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180007952`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800079cf`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180007952`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800079cf`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180007921`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180007921`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x1800078e8`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x1800078e8`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800078be`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800078be`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180007e92`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180007e92`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_BOOL8 __fastcall CBthActiveConnector::_IsActiveConnectEnabled(CBthActiveConnector *this, const unsigned __int16 *a2)
{
  BOOL v3; // r15d
  HDEVINFO DeviceInfoList; // rax
  void *v5; // r12
  __int64 v6; // rdi
  signed int LastError; // ebx
  WCHAR *v8; // rbx
  char v9; // dl
  size_t v10; // r9
  size_t v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // r14
  LPCWSTR v15; // rdi
  LSTATUS v16; // ecx
  HKEY v17; // rax
  LSTATUS Value; // eax
  CPnPNotification *v19; // rcx
  int v20; // edx
  int v21; // r9d
  __int64 v22; // r9
  CPnPNotification *v23; // r10
  __int64 v24; // rdx
  signed int v25; // eax
  signed int v26; // eax
  __int64 v27; // r9
  bool v28; // sf
  CPnPNotification *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r9
  signed int v32; // eax
  CPnPNotification *v33; // rcx
  __int64 v34; // rdx
  signed int v35; // eax
  bool v36; // sf
  signed int v37; // eax
  bool v38; // sf
  signed int v39; // eax
  __int64 v40; // r9
  bool v41; // sf
  size_t Size; // [rsp+50h] [rbp-A8h] BYREF
  DWORD DeviceInstanceIdSize; // [rsp+58h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+5Ch] [rbp-9Ch] BYREF
  int v46; // [rsp+60h] [rbp-98h]
  HKEY hKey; // [rsp+68h] [rbp-90h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-88h] BYREF
  int v49; // [rsp+78h] [rbp-80h] BYREF
  HDEVINFO v50; // [rsp+80h] [rbp-78h]
  WCHAR *v51; // [rsp+88h] [rbp-70h]
  _QWORD v52[3]; // [rsp+90h] [rbp-68h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+A8h] [rbp-50h] BYREF

  v3 = 0;
  v46 = 0;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  v5 = DeviceInfoList;
  v50 = DeviceInfoList;
  v6 = -1;
  if ( DeviceInfoList != (HDEVINFO)-1LL )
  {
    if ( SetupDiOpenDeviceInterfaceW(DeviceInfoList, a2, 0, 0) )
    {
      DeviceInfoData.cbSize = 32;
      memset(&DeviceInfoData.ClassGuid, 0, 28);
      if ( SetupDiEnumDeviceInfo(v5, 0, &DeviceInfoData) )
      {
        LastError = 0;
        DeviceInstanceIdSize = 0;
        if ( !SetupDiGetDeviceInstanceIdW(v5, &DeviceInfoData, 0, 0, &DeviceInstanceIdSize) )
        {
          LastError = GetLastError();
          if ( LastError == 122 )
          {
            v8 = 0;
            Size = 0;
            if ( (int)ATL::AtlMultiply<unsigned __int64>(&Size, DeviceInstanceIdSize, 2) >= 0
              && (v8 = (WCHAR *)malloc(Size), (v51 = v8) != 0) )
            {
              if ( SetupDiGetDeviceInstanceIdW(v5, &DeviceInfoData, v8, DeviceInstanceIdSize, &DeviceInstanceIdSize) )
              {
                try
                {
                  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&Size, &ATL::g_strmgr);
                  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                                           &Size,
                                           v8) )
                  {
                    do
                      ++v6;
                    while ( v8[v6] );
                    ATL::CSimpleStringT<unsigned short,0>::SetString(&Size, v8, (unsigned int)v6);
                  }
                  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&lpSubKey, &ATL::g_strmgr);
                  memset(v52, 0, sizeof(v52));
                  v9 = 0;
                  v10 = Size;
                  v11 = Size;
                  v12 = *(_DWORD *)(Size - 16);
                  LODWORD(v13) = 0;
                  while ( (int)v13 < (int)v12 )
                  {
                    v14 = (int)v13;
                    if ( *(_WORD *)(v11 + 2LL * (int)v13) == 92 )
                    {
                      if ( !v9 )
                      {
                        if ( (((*(_DWORD *)(v10 - 12) - v12) | (1 - *(_DWORD *)(v10 - 8))) & 0x80000000) != 0 )
                        {
                          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&Size, v12);
                          v10 = Size;
                        }
                        v9 = 1;
                        v11 = v10;
                      }
                      *(_WORD *)(v11 + 2 * v14) = 35;
                      v10 = Size;
                    }
                    v13 = (2 * v14 + 2) >> 1;
                  }
                  if ( v9 )
                    ATL::CSimpleStringT<unsigned short,0>::SetLength(&Size, v12);
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                    &lpSubKey,
                    L"%ws\\%ws",
                    L"Software\\Microsoft\\Windows Portable Devices\\Devices");
                  dwDisposition = 0;
                  hKey = 0;
                  v15 = lpSubKey;
                  v16 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
                  if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v52), v17 = hKey, v52[0] = hKey, v16) )
                  {
                    v22 = (unsigned __int16)v16 | 0x80070000;
                    v25 = v16;
                    if ( v16 > 0 )
                      v25 = (unsigned __int16)v16 | 0x80070000;
                    if ( v25 >= 0 )
                      goto LABEL_52;
                    v23 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                    {
                      goto LABEL_52;
                    }
                    v24 = 33;
                    goto LABEL_49;
                  }
                  dwDisposition = 0;
                  LODWORD(hKey) = 0;
                  LODWORD(lpSubKey) = 4;
                  Value = RegQueryValueExW(
                            v17,
                            L"EnableActiveConnect",
                            0,
                            (LPDWORD)&hKey,
                            (LPBYTE)&dwDisposition,
                            (LPDWORD)&lpSubKey);
                  if ( Value )
                  {
                    if ( Value == 2 )
                    {
                      v3 = 1;
                      v46 = 1;
                      v19 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
                      {
                        goto LABEL_52;
                      }
                      v20 = 31;
LABEL_31:
                      WPP_SF_Sd(
                        *((_QWORD *)v19 + 2),
                        v20,
                        (unsigned int)&WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
                        (unsigned int)L"EnableActiveConnect",
                        v3);
LABEL_52:
                      ATL::CRegKey::Close((ATL::CRegKey *)v52);
                      ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
                      ATL::CStringData::Release((ATL::CStringData *)(Size - 24));
                      goto LABEL_108;
                    }
                    v21 = (unsigned __int16)Value;
                    v16 = Value;
                    if ( Value <= 0 )
                    {
                      v22 = (unsigned __int16)Value | 0x80070000;
                      goto LABEL_37;
                    }
                  }
                  else
                  {
                    if ( (_DWORD)hKey == 4 )
                    {
                      v3 = dwDisposition != 0;
                      v46 = v3;
                      v19 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
                      {
                        goto LABEL_52;
                      }
                      v20 = 30;
                      goto LABEL_31;
                    }
                    v21 = 13;
                    v16 = 13;
                  }
                  v22 = v21 | 0x80070000;
LABEL_37:
                  v23 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  {
                    goto LABEL_52;
                  }
                  v24 = 32;
LABEL_49:
                  if ( v16 <= 0 )
                    v22 = (unsigned int)v16;
                  WPP_SF_d(*((_QWORD *)v23 + 2), v24, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v22);
                  goto LABEL_52;
                }
                catch ( ATL::CAtlException v49 )
                {
                  if ( v49 < 0
                    && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      34,
                      &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
                      (unsigned int)v49);
                  }
                  v3 = v46;
                  v5 = v50;
                  v8 = v51;
                  goto LABEL_65;
                }
LABEL_108:
                goto LABEL_65;
              }
              v26 = GetLastError();
              v27 = (unsigned int)v26;
              v28 = v26 < 0;
              if ( v26 > 0 )
                v28 = 1;
              if ( !v28 )
                goto LABEL_65;
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
                goto LABEL_65;
              }
              if ( v26 > 0 )
                v27 = (unsigned __int16)v26 | 0x80070000;
              v30 = 35;
            }
            else
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
                goto LABEL_65;
              }
              v30 = 36;
              v27 = 2147942414LL;
            }
            WPP_SF_d(*((_QWORD *)v29 + 2), v30, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v27);
LABEL_65:
            free(v8);
LABEL_91:
            SetupDiDestroyDeviceInfoList(v5);
            return v3;
          }
        }
        v31 = (unsigned __int16)LastError | 0x80070000;
        v32 = LastError;
        if ( LastError > 0 )
          v32 = (unsigned __int16)LastError | 0x80070000;
        if ( v32 >= 0 )
          goto LABEL_91;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_91;
        }
        if ( LastError <= 0 )
          v31 = (unsigned int)LastError;
        v34 = 37;
      }
      else
      {
        v35 = GetLastError();
        v31 = (unsigned int)v35;
        v36 = v35 < 0;
        if ( v35 > 0 )
          v36 = 1;
        if ( !v36 )
          goto LABEL_91;
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          goto LABEL_91;
        }
        if ( v35 > 0 )
          v31 = (unsigned __int16)v35 | 0x80070000;
        v34 = 38;
      }
    }
    else
    {
      v37 = GetLastError();
      v31 = (unsigned int)v37;
      v38 = v37 < 0;
      if ( v37 > 0 )
        v38 = 1;
      if ( !v38 )
        goto LABEL_91;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_91;
      }
      if ( v37 > 0 )
        v31 = (unsigned __int16)v37 | 0x80070000;
      v34 = 39;
    }
    WPP_SF_d(*((_QWORD *)v33 + 2), v34, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v31);
    goto LABEL_91;
  }
  v39 = GetLastError();
  v40 = (unsigned int)v39;
  v41 = v39 < 0;
  if ( v39 > 0 )
    v41 = 1;
  if ( v41
    && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    if ( v39 > 0 )
      v40 = (unsigned __int16)v39 | 0x80070000;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v40);
  }
  return v3;
}

```

## disassembly

```asm
0x180007880  mov     [rsp+arg_0], rbx
0x180007885  mov     [rsp+arg_10], rsi
0x18000788a  push    rdi
0x18000788b  push    r12
0x18000788d  push    r13
0x18000788f  push    r14
0x180007891  push    r15
0x180007893  sub     rsp, 0D0h
0x18000789a  mov     rax, cs:__security_cookie
0x1800078a1  xor     rax, rsp
0x1800078a4  mov     [rsp+0F8h+var_30], rax
0x1800078ac  mov     rbx, rdx
0x1800078af  xor     r13d, r13d
0x1800078b2  mov     r15d, r13d
0x1800078b5  mov     [rsp+0F8h+var_98], r13d
0x1800078ba  xor     edx, edx; hwndParent
0x1800078bc  xor     ecx, ecx; ClassGuid
0x1800078be  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800078c4  mov     r12, rax
0x1800078c7  mov     [rsp+0F8h+var_78], rax
0x1800078cf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800078d3  cmp     rax, rdi
0x1800078d6  jz      loc_180007E9A
0x1800078dc  xor     r9d, r9d; DeviceInterfaceData
0x1800078df  xor     r8d, r8d; OpenFlags
0x1800078e2  mov     rdx, rbx; DevicePath
0x1800078e5  mov     rcx, rax; DeviceInfoSet
0x1800078e8  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x1800078ee  test    eax, eax
0x1800078f0  jz      loc_180007E37
0x1800078f6  mov     [rsp+0F8h+DeviceInfoData.cbSize], 20h ; ' '
0x180007901  xorps   xmm0, xmm0
0x180007904  movups  xmmword ptr [rsp+0F8h+DeviceInfoData.ClassGuid.Data1], xmm0
0x18000790c  movups  xmmword ptr [rsp+0F8h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180007914  lea     r8, [rsp+0F8h+DeviceInfoData]; DeviceInfoData
0x18000791c  xor     edx, edx; MemberIndex
0x18000791e  mov     rcx, r12; DeviceInfoSet
0x180007921  call    cs:__imp_SetupDiEnumDeviceInfo
0x180007927  test    eax, eax
0x180007929  jz      loc_180007DE9
0x18000792f  mov     ebx, r13d
0x180007932  mov     [rsp+0F8h+DeviceInstanceIdSize], r13d
0x180007937  lea     rax, [rsp+0F8h+DeviceInstanceIdSize]
0x18000793c  mov     [rsp+0F8h+RequiredSize], rax; RequiredSize
0x180007941  xor     r9d, r9d; DeviceInstanceIdSize
0x180007944  xor     r8d, r8d; DeviceInstanceId
0x180007947  lea     rdx, [rsp+0F8h+DeviceInfoData]; DeviceInfoData
0x18000794f  mov     rcx, r12; DeviceInfoSet
0x180007952  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180007958  test    eax, eax
0x18000795a  jnz     loc_180007D9D
0x180007960  call    cs:__imp_GetLastError
0x180007966  mov     ebx, eax
0x180007968  cmp     eax, 7Ah ; 'z'
0x18000796b  jnz     loc_180007D9D
0x180007971  mov     ebx, r13d
0x180007974  mov     [rsp+0F8h+Size], r13
0x180007979  mov     edx, [rsp+0F8h+DeviceInstanceIdSize]
0x18000797d  lea     r8d, [r13+2]
0x180007981  lea     rcx, [rsp+0F8h+Size]
0x180007986  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18000798b  test    eax, eax
0x18000798d  js      loc_180007D5A
0x180007993  mov     rcx, [rsp+0F8h+Size]; Size
0x180007998  call    cs:__imp_malloc
0x18000799e  mov     rbx, rax
0x1800079a1  mov     [rsp+0F8h+var_70], rax
0x1800079a9  test    rax, rax
0x1800079ac  jz      loc_180007D5A
0x1800079b2  lea     rax, [rsp+0F8h+DeviceInstanceIdSize]
0x1800079b7  mov     [rsp+0F8h+RequiredSize], rax; RequiredSize
0x1800079bc  mov     r9d, [rsp+0F8h+DeviceInstanceIdSize]; DeviceInstanceIdSize
0x1800079c1  mov     r8, rbx; DeviceInstanceId
0x1800079c4  lea     rdx, [rsp+0F8h+DeviceInfoData]; DeviceInfoData
0x1800079cc  mov     rcx, r12; DeviceInfoSet
0x1800079cf  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x1800079d5  test    eax, eax
0x1800079d7  jz      loc_180007D10
0x1800079dd  lea     rdx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800079e4  lea     rcx, [rsp+0F8h+Size]
0x1800079e9  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x1800079ee  nop
0x1800079ef  mov     rdx, rbx
0x1800079f2  lea     rcx, [rsp+0F8h+Size]
0x1800079f7  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x1800079fc  test    al, al
0x1800079fe  jnz     short loc_180007A1B
0x180007a00  inc     rdi
0x180007a03  cmp     [rbx+rdi*2], r13w
0x180007a08  jnz     short loc_180007A00
0x180007a0a  mov     r8d, edi
0x180007a0d  mov     rdx, rbx
0x180007a10  lea     rcx, [rsp+0F8h+Size]
0x180007a15  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180007a1a  nop
0x180007a1b  lea     rdx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180007a22  lea     rcx, [rsp+0F8h+lpSubKey]
0x180007a27  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x180007a2c  nop
0x180007a2d  mov     [rsp+0F8h+var_68], r13
0x180007a35  mov     [rsp+0F8h+var_60], r13
0x180007a3d  mov     [rsp+0F8h+var_58], r13
0x180007a45  mov     dl, r13b
0x180007a48  mov     r9, [rsp+0F8h+Size]
0x180007a4d  mov     rcx, r9
0x180007a50  mov     edi, [r9-10h]
0x180007a54  mov     eax, r13d
0x180007a57  cmp     eax, edi
0x180007a59  jge     short loc_180007AAC
0x180007a5b  movsxd  r14, eax
0x180007a5e  cmp     word ptr [rcx+r14*2], 5Ch ; '\'
0x180007a64  jnz     short loc_180007A9F
0x180007a66  test    dl, dl
0x180007a68  jnz     short loc_180007A93
0x180007a6a  mov     ecx, 1
0x180007a6f  sub     ecx, [r9-8]
0x180007a73  mov     eax, [r9-0Ch]
0x180007a77  sub     eax, edi
0x180007a79  or      ecx, eax
0x180007a7b  jge     short loc_180007A8E
0x180007a7d  mov     edx, edi
0x180007a7f  lea     rcx, [rsp+0F8h+Size]
0x180007a84  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180007a89  mov     r9, [rsp+0F8h+Size]
0x180007a8e  mov     dl, 1
0x180007a90  mov     rcx, r9
0x180007a93  mov     word ptr [rcx+r14*2], 23h ; '#'
0x180007a9a  mov     r9, [rsp+0F8h+Size]
0x180007a9f  lea     rax, ds:2[r14*2]
0x180007aa7  sar     rax, 1
0x180007aaa  jmp     short loc_180007A57
0x180007aac  test    dl, dl
0x180007aae  jz      short loc_180007AC1
0x180007ab0  mov     edx, edi
0x180007ab2  lea     rcx, [rsp+0F8h+Size]
0x180007ab7  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180007abc  mov     r9, [rsp+0F8h+Size]
0x180007ac1  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows Portable D"...
0x180007ac8  lea     rdx, aWsWs; "%ws\\%ws"
0x180007acf  lea     rcx, [rsp+0F8h+lpSubKey]
0x180007ad4  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180007ad9  mov     [rsp+0F8h+dwDisposition], r13d
0x180007ade  mov     [rsp+0F8h+hKey], r13
0x180007ae3  lea     rax, [rsp+0F8h+dwDisposition]
0x180007ae8  mov     [rsp+0F8h+lpdwDisposition], rax; lpdwDisposition
0x180007aed  lea     rax, [rsp+0F8h+hKey]
0x180007af2  mov     [rsp+0F8h+phkResult], rax; phkResult
0x180007af7  mov     [rsp+0F8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180007afc  mov     [rsp+0F8h+samDesired], 2001Fh; samDesired
0x180007b04  mov     dword ptr [rsp+0F8h+RequiredSize], r13d; dwOptions
0x180007b09  xor     r9d, r9d; lpClass
0x180007b0c  xor     r8d, r8d; Reserved
0x180007b0f  mov     rdi, [rsp+0F8h+lpSubKey]
0x180007b14  mov     rdx, rdi; lpSubKey
0x180007b17  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007b1e  call    cs:__imp_RegCreateKeyExW
0x180007b24  mov     ecx, eax
0x180007b26  test    eax, eax
0x180007b28  jnz     loc_180007C80
0x180007b2e  lea     rcx, [rsp+0F8h+var_68]; this
0x180007b36  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007b3b  mov     ecx, eax
0x180007b3d  mov     rax, [rsp+0F8h+hKey]
0x180007b42  mov     [rsp+0F8h+var_68], rax
0x180007b4a  test    ecx, ecx
0x180007b4c  jnz     loc_180007C80
0x180007b52  mov     [rsp+0F8h+dwDisposition], r13d
0x180007b57  mov     dword ptr [rsp+0F8h+hKey], r13d
0x180007b5c  mov     dword ptr [rsp+0F8h+lpSubKey], 4
0x180007b64  lea     rcx, [rsp+0F8h+lpSubKey]
0x180007b69  mov     qword ptr [rsp+0F8h+samDesired], rcx; lpcbData
0x180007b6e  lea     rcx, [rsp+0F8h+dwDisposition]
0x180007b73  mov     [rsp+0F8h+RequiredSize], rcx; lpData
0x180007b78  lea     r9, [rsp+0F8h+hKey]; lpType
0x180007b7d  xor     r8d, r8d; lpReserved
0x180007b80  lea     rsi, aEnableactiveco; "EnableActiveConnect"
0x180007b87  mov     rdx, rsi; lpValueName
0x180007b8a  mov     rcx, rax; hKey
0x180007b8d  call    cs:__imp_RegQueryValueExW
0x180007b93  test    eax, eax
0x180007b95  jz      short loc_180007BFD
0x180007b97  cmp     eax, 2
0x180007b9a  jnz     short loc_180007BEA
0x180007b9c  lea     r15d, [rax-1]
0x180007ba0  mov     [rsp+0F8h+var_98], r15d
0x180007ba5  lea     rax, WPP_GLOBAL_Control
0x180007bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bb3  cmp     rcx, rax
0x180007bb6  jz      loc_180007CCD
0x180007bbc  test    dword ptr [rcx+1Ch], 800h
0x180007bc3  jz      loc_180007CCD
0x180007bc9  lea     edx, [r15+1Eh]
0x180007bcd  mov     dword ptr [rsp+0F8h+RequiredSize], r15d
0x180007bd2  mov     r9, rsi
0x180007bd5  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180007bdc  mov     rcx, [rcx+10h]
0x180007be0  call    WPP_SF_Sd
0x180007be5  jmp     loc_180007CCD
0x180007bea  movzx   r9d, ax
0x180007bee  mov     ecx, eax
0x180007bf0  test    eax, eax
0x180007bf2  jg      short loc_180007C0D
0x180007bf4  or      r9d, 80070000h
0x180007bfb  jmp     short loc_180007C18
0x180007bfd  cmp     dword ptr [rsp+0F8h+hKey], 4
0x180007c02  jz      short loc_180007C49
0x180007c04  mov     r9d, 0Dh
0x180007c0a  mov     ecx, r9d
0x180007c0d  mov     eax, r9d
0x180007c10  or      eax, 80070000h
0x180007c15  mov     r9d, eax
0x180007c18  test    eax, eax
0x180007c1a  jns     loc_180007CCD
0x180007c20  lea     rax, WPP_GLOBAL_Control
0x180007c27  mov     r10, cs:WPP_GLOBAL_Control
0x180007c2e  cmp     r10, rax
0x180007c31  jz      loc_180007CCD
0x180007c37  test    byte ptr [r10+1Ch], 2
0x180007c3c  jz      loc_180007CCD
0x180007c42  mov     edx, 20h ; ' '
0x180007c47  jmp     short loc_180007CB6
0x180007c49  mov     r15d, r13d
0x180007c4c  cmp     [rsp+0F8h+dwDisposition], r13d
0x180007c51  setnz   r15b
0x180007c55  mov     [rsp+0F8h+var_98], r15d
0x180007c5a  lea     rax, WPP_GLOBAL_Control
0x180007c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c68  cmp     rcx, rax
0x180007c6b  jz      short loc_180007CCD
0x180007c6d  test    dword ptr [rcx+1Ch], 800h
0x180007c74  jz      short loc_180007CCD
0x180007c76  mov     edx, 1Eh
0x180007c7b  jmp     loc_180007BCD
0x180007c80  movzx   r9d, cx
0x180007c84  or      r9d, 80070000h
0x180007c8b  mov     eax, ecx
0x180007c8d  test    ecx, ecx
0x180007c8f  cmovg   eax, r9d
0x180007c93  test    eax, eax
0x180007c95  jns     short loc_180007CCD
0x180007c97  lea     rax, WPP_GLOBAL_Control
0x180007c9e  mov     r10, cs:WPP_GLOBAL_Control
0x180007ca5  cmp     r10, rax
0x180007ca8  jz      short loc_180007CCD
0x180007caa  test    byte ptr [r10+1Ch], 2
0x180007caf  jz      short loc_180007CCD
0x180007cb1  mov     edx, 21h ; '!'
0x180007cb6  test    ecx, ecx
0x180007cb8  cmovle  r9d, ecx
0x180007cbc  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180007cc3  mov     rcx, [r10+10h]
0x180007cc7  call    WPP_SF_d
0x180007ccc  nop
0x180007ccd  lea     rcx, [rsp+0F8h+var_68]; this
0x180007cd5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007cda  nop
0x180007cdb  lea     rcx, [rdi-18h]; this
0x180007cdf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007ce4  nop
0x180007ce5  mov     rcx, [rsp+0F8h+Size]
0x180007cea  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007cee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007cf3  nop
0x180007cf4  jmp     loc_180007D8F
0x180007cf9  mov     r15d, [rsp+0F8h+var_98]
0x180007cfe  mov     r12, [rsp+0F8h+var_78]
0x180007d06  mov     rbx, [rsp+0F8h+var_70]
0x180007d0e  jmp     short loc_180007D8F
0x180007d10  call    cs:__imp_GetLastError
0x180007d16  mov     r9d, eax
0x180007d19  movzx   edx, ax
0x180007d1c  test    eax, eax
0x180007d1e  jle     short loc_180007D29
0x180007d20  mov     eax, edx
0x180007d22  or      eax, 80070000h
0x180007d27  test    eax, eax
0x180007d29  jns     short loc_180007D8F
0x180007d2b  lea     rax, WPP_GLOBAL_Control
0x180007d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d39  cmp     rcx, rax
0x180007d3c  jz      short loc_180007D8F
0x180007d3e  test    byte ptr [rcx+1Ch], 2
0x180007d42  jz      short loc_180007D8F
0x180007d44  test    r9d, r9d
0x180007d47  jle     short loc_180007D53
0x180007d49  mov     r9d, edx
0x180007d4c  or      r9d, 80070000h
0x180007d53  mov     edx, 23h ; '#'
0x180007d58  jmp     short loc_180007D7E
0x180007d5a  lea     rax, WPP_GLOBAL_Control
0x180007d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d68  cmp     rcx, rax
0x180007d6b  jz      short loc_180007D8F
0x180007d6d  test    byte ptr [rcx+1Ch], 2
0x180007d71  jz      short loc_180007D8F
0x180007d73  mov     edx, 24h ; '$'
0x180007d78  mov     r9d, 8007000Eh
0x180007d7e  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180007d85  mov     rcx, [rcx+10h]
0x180007d89  call    WPP_SF_d
  ... truncated ...
```
