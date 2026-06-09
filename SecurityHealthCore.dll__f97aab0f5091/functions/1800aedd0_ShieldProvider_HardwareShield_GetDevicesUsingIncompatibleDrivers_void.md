# ShieldProvider::HardwareShield::GetDevicesUsingIncompatibleDrivers(void)

- ea: `0x1800aedd0`
- end: `0x1800af3ef`
- name: `?GetDevicesUsingIncompatibleDrivers@HardwareShield@ShieldProvider@@AEAAJXZ`
- size: `1567`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800962b0`
- `0x1800966d0`

## callees

- `0x180004710`
- `0x18000517c`
- `0x18000af28`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x1800882a8`
- `0x1800aedd0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800af19f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800af1b4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800af1d7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800af19f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800af1b4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800af1d7`
- `ole32!CoTaskMemFree` at `0x1800aeeca`
- `ole32!CoTaskMemFree` at `0x1800aef3c`
- `ole32!CoTaskMemFree` at `0x1800af2f1`
- `ole32!CoTaskMemFree` at `0x1800af362`
- `ole32!CoTaskMemFree` at `0x1800af370`
- `ole32!CoTaskMemFree` at `0x1800af3b3`
- `ole32!CoTaskMemFree` at `0x1800af3c6`
- `ole32!CoTaskMemFree` at `0x1800aeeca`
- `ole32!CoTaskMemFree` at `0x1800aef3c`
- `ole32!CoTaskMemFree` at `0x1800af2f1`
- `ole32!CoTaskMemFree` at `0x1800af362`
- `ole32!CoTaskMemFree` at `0x1800af370`
- `ole32!CoTaskMemFree` at `0x1800af3b3`
- `ole32!CoTaskMemFree` at `0x1800af3c6`
- `SETUPAPI!CM_Locate_DevNodeW` at `0x1800aef75`
- `SETUPAPI!CM_Locate_DevNodeW` at `0x1800aef75`
- `SETUPAPI!CM_Get_Device_ID_List_SizeW` at `0x1800aee15`
- `SETUPAPI!CM_Get_Device_ID_List_SizeW` at `0x1800aee15`
- `SETUPAPI!CM_Get_Device_ID_ListW` at `0x1800aeee4`
- `SETUPAPI!CM_Get_Device_ID_ListW` at `0x1800aeee4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af00d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af082`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af10d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af258`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af00d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af082`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af10d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1800af258`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800aee24`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800aeeee`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800aef82`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af01c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af08c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af11a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af265`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800aee24`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800aeeee`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800aef82`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af01c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af08c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af11a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800af265`

## pseudocode

```c
__int64 __fastcall ShieldProvider::HardwareShield::GetDevicesUsingIncompatibleDrivers(
        ShieldProvider::HardwareShield *this)
{
  ShieldProvider::HardwareShield *v1; // r14
  CONFIGRET Device_ID_List_SizeW; // eax
  signed int v3; // eax
  unsigned int v4; // ebx
  int v6; // eax
  WCHAR *v7; // rbx
  CONFIGRET Device_ID_ListW; // eax
  signed int v9; // eax
  unsigned int v10; // edi
  WCHAR *v11; // rdi
  CONFIGRET v12; // eax
  signed int v13; // eax
  bool v14; // sf
  CONFIGRET DevNode_PropertyW; // eax
  signed int v16; // eax
  bool v17; // sf
  CONFIGRET v18; // eax
  signed int v19; // eax
  bool v20; // sf
  int v21; // eax
  PBYTE v22; // rdi
  CONFIGRET v23; // eax
  signed int v24; // eax
  bool v25; // sf
  __int64 v26; // rsi
  __int64 v27; // r14
  const wchar_t *v28; // r13
  bool v29; // al
  bool v30; // zf
  __int64 v31; // rcx
  CONFIGRET v32; // eax
  signed int v33; // eax
  bool v34; // sf
  int v35; // eax
  unsigned int v36; // r13d
  __int64 v37; // rax
  DEVPROPTYPE PropertyType; // [rsp+30h] [rbp-D0h] BYREF
  ULONG PropertyBufferSize; // [rsp+34h] [rbp-CCh] BYREF
  DEVNODE pdnDevInst; // [rsp+38h] [rbp-C8h] BYREF
  ULONG pulLen; // [rsp+3Ch] [rbp-C4h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v43; // [rsp+48h] [rbp-B8h]
  PBYTE v44; // [rsp+50h] [rbp-B0h] BYREF
  ShieldProvider::HardwareShield *v45; // [rsp+58h] [rbp-A8h]
  _BYTE v46[16]; // [rsp+60h] [rbp-A0h] BYREF
  char v47; // [rsp+70h] [rbp-90h]
  wchar_t PropertyBuffer[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v49[264]; // [rsp+290h] [rbp+190h] BYREF

  v1 = this;
  v45 = this;
  pulLen = 0;
  Device_ID_List_SizeW = CM_Get_Device_ID_List_SizeW(&pulLen, 0, 0);
  v3 = CM_MapCrToWin32Err(Device_ID_List_SizeW, 0x54Fu);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, v4);
    return v4;
  }
  pv = 0;
  v6 = CommonUtil::UtilCoTaskMemAllocArray<unsigned short>(&pv, pulLen);
  v4 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v6);
    if ( pv )
      CoTaskMemFree(pv);
    return v4;
  }
  v7 = (WCHAR *)pv;
  Device_ID_ListW = CM_Get_Device_ID_ListW(0, (PZZWSTR)pv, pulLen, 0);
  v9 = CM_MapCrToWin32Err(Device_ID_ListW, 0x54Fu);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( (v10 & 0x80000000) == 0 )
  {
    v11 = v7;
    v43 = v7;
    while ( *v11 )
    {
      pdnDevInst = 0;
      v12 = CM_Locate_DevNodeW(&pdnDevInst, v11, 1u);
      v13 = CM_MapCrToWin32Err(v12, 0x54Fu);
      v14 = v13 < 0;
      if ( v13 > 0 )
      {
        v13 = (unsigned __int16)v13 | 0x80070000;
        v14 = v13 < 0;
      }
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            153,
            &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
            (unsigned int)v13);
      }
      else
      {
        PropertyType = 0;
        memset_0(PropertyBuffer, 0, 0x208u);
        PropertyBufferSize = 260;
        DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                              pdnDevInst,
                              &DEVPKEY_Device_DriverInfPath,
                              &PropertyType,
                              (PBYTE)PropertyBuffer,
                              &PropertyBufferSize,
                              0);
        v16 = CM_MapCrToWin32Err(DevNode_PropertyW, 0x54Fu);
        v17 = v16 < 0;
        if ( v16 > 0 )
        {
          v16 = (unsigned __int16)v16 | 0x80070000;
          v17 = v16 < 0;
        }
        if ( (v17 || PropertyType != 18)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            154,
            &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
            (unsigned int)v16);
        }
        v18 = CM_Get_DevNode_PropertyW(
                pdnDevInst,
                &DEVPKEY_Device_DriverExtendedInfs,
                &PropertyType,
                0,
                &PropertyBufferSize,
                0);
        v19 = CM_MapCrToWin32Err(v18, 0x54Fu);
        v20 = v19 < 0;
        if ( v19 > 0 )
        {
          v19 = (unsigned __int16)v19 | 0x80070000;
          v20 = v19 < 0;
        }
        if ( v20 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            155,
            &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
            (unsigned int)v19);
        v44 = 0;
        v21 = CommonUtil::UtilCoTaskMemAllocArray<unsigned short>(&v44, PropertyBufferSize);
        v10 = v21;
        if ( v21 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              156,
              &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
              (unsigned int)v21);
          if ( v44 )
            CoTaskMemFree(v44);
          goto LABEL_20;
        }
        v22 = v44;
        v23 = CM_Get_DevNode_PropertyW(
                pdnDevInst,
                &DEVPKEY_Device_DriverExtendedInfs,
                &PropertyType,
                v44,
                &PropertyBufferSize,
                0);
        v24 = CM_MapCrToWin32Err(v23, 0x54Fu);
        v25 = v24 < 0;
        if ( v24 > 0 )
        {
          v24 = (unsigned __int16)v24 | 0x80070000;
          v25 = v24 < 0;
        }
        if ( (v25 || PropertyType != 8210)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            157,
            &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
            (unsigned int)v24);
        }
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
          v46,
          &stru_18013A040);
        v26 = *((_QWORD *)v1 + 41);
        v27 = *((_QWORD *)v1 + 42);
        v47 = 1;
        while ( v26 != v27 )
        {
          if ( _wcsicmp((const wchar_t *)(v26 + 524), &word_1800F4E78) )
          {
            v28 = (const wchar_t *)v22;
            v29 = _wcsicmp((const wchar_t *)(v26 + 524), PropertyBuffer) == 0;
            if ( *(_WORD *)v22 )
            {
              do
              {
                if ( v29 || (v30 = _wcsicmp((const wchar_t *)(v26 + 524), v28) == 0, v29 = 0, v30) )
                  v29 = 1;
                v31 = -1;
                do
                  ++v31;
                while ( v28[v31] );
                v28 += v31 + 1;
              }
              while ( *v28 );
              v7 = (WCHAR *)pv;
            }
            if ( v29 )
            {
              memset_0(v49, 0, 0x208u);
              PropertyBufferSize = 260;
              v32 = CM_Get_DevNode_PropertyW(
                      pdnDevInst,
                      &DEVPKEY_NAME,
                      &PropertyType,
                      (PBYTE)v49,
                      &PropertyBufferSize,
                      0);
              v33 = CM_MapCrToWin32Err(v32, 0x54Fu);
              v34 = v33 < 0;
              if ( v33 > 0 )
              {
                v33 = (unsigned __int16)v33 | 0x80070000;
                v34 = v33 < 0;
              }
              if ( (v34 || PropertyType != 18)
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  158,
                  &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
                  (unsigned int)v33);
              }
              v35 = StringCchCopyW((unsigned __int16 *)(v26 + 1612), 0x104u, v49);
              v36 = v35;
              if ( v35 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    159,
                    &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
                    (unsigned int)v35);
                CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v46);
                if ( v22 )
                  CoTaskMemFree(v22);
                if ( v7 )
                  CoTaskMemFree(v7);
                return v36;
              }
            }
          }
          v26 += 2148;
        }
        v47 = 0;
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v46);
        if ( v22 )
          CoTaskMemFree(v22);
        v1 = v45;
        v11 = v43;
      }
      v37 = -1;
      do
        ++v37;
      while ( v11[v37] );
      v11 += v37 + 1;
      v43 = v11;
    }
    if ( v7 )
      CoTaskMemFree(v7);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, v10);
LABEL_20:
    if ( v7 )
      CoTaskMemFree(v7);
    return v10;
  }
}

```

## disassembly

```asm
0x1800aedd0  push    rbp
0x1800aedd2  push    rbx
0x1800aedd3  push    rsi
0x1800aedd4  push    rdi
0x1800aedd5  push    r13
0x1800aedd7  push    r14
0x1800aedd9  push    r15
0x1800aeddb  lea     rbp, [rsp-3B0h]
0x1800aede3  sub     rsp, 4B0h
0x1800aedea  mov     rax, cs:__security_cookie
0x1800aedf1  xor     rax, rsp
0x1800aedf4  mov     [rbp+3E0h+var_40], rax
0x1800aedfb  mov     r14, rcx
0x1800aedfe  mov     [rsp+4E0h+var_488], rcx
0x1800aee03  xor     r13d, r13d
0x1800aee06  lea     rcx, [rsp+4E0h+pulLen]; pulLen
0x1800aee0b  xor     r8d, r8d; ulFlags
0x1800aee0e  mov     [rsp+4E0h+pulLen], r13d
0x1800aee13  xor     edx, edx; pszFilter
0x1800aee15  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x1800aee1b  mov     edi, 54Fh
0x1800aee20  mov     ecx, eax; CmReturnCode
0x1800aee22  mov     edx, edi; DefaultErr
0x1800aee24  call    cs:__imp_CM_MapCrToWin32Err
0x1800aee2a  mov     ebx, eax
0x1800aee2c  mov     esi, 80070000h
0x1800aee31  test    eax, eax
0x1800aee33  jle     short loc_1800AEE3A
0x1800aee35  movzx   ebx, ax
0x1800aee38  or      ebx, esi
0x1800aee3a  test    ebx, ebx
0x1800aee3c  jns     short loc_1800AEE76
0x1800aee3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aee45  lea     r15, WPP_GLOBAL_Control
0x1800aee4c  cmp     rcx, r15
0x1800aee4f  jz      short loc_1800AEE6F
0x1800aee51  test    byte ptr [rcx+1Ch], 1
0x1800aee55  jz      short loc_1800AEE6F
0x1800aee57  mov     rcx, [rcx+10h]
0x1800aee5b  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aee62  mov     edx, 96h
0x1800aee67  mov     r9d, ebx
0x1800aee6a  call    WPP_SF_d
0x1800aee6f  mov     eax, ebx
0x1800aee71  jmp     loc_1800AF3CE
0x1800aee76  mov     edx, [rsp+4E0h+pulLen]
0x1800aee7a  lea     rcx, [rsp+4E0h+pv]
0x1800aee7f  mov     [rsp+4E0h+pv], r13
0x1800aee84  call    ??$UtilCoTaskMemAllocArray@G@CommonUtil@@YAJPEAPEAG_K_N@Z; CommonUtil::UtilCoTaskMemAllocArray<ushort>(ushort * *,unsigned __int64,bool)
0x1800aee89  mov     ebx, eax
0x1800aee8b  test    eax, eax
0x1800aee8d  jns     short loc_1800AEED2
0x1800aee8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aee96  lea     r15, WPP_GLOBAL_Control
0x1800aee9d  cmp     rcx, r15
0x1800aeea0  jz      short loc_1800AEEC0
0x1800aeea2  test    byte ptr [rcx+1Ch], 1
0x1800aeea6  jz      short loc_1800AEEC0
0x1800aeea8  mov     rcx, [rcx+10h]
0x1800aeeac  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aeeb3  mov     edx, 97h
0x1800aeeb8  mov     r9d, eax
0x1800aeebb  call    WPP_SF_d
0x1800aeec0  mov     rcx, [rsp+4E0h+pv]; pv
0x1800aeec5  test    rcx, rcx
0x1800aeec8  jz      short loc_1800AEE6F
0x1800aeeca  call    cs:__imp_CoTaskMemFree
0x1800aeed0  jmp     short loc_1800AEE6F
0x1800aeed2  mov     rbx, [rsp+4E0h+pv]
0x1800aeed7  xor     r9d, r9d; ulFlags
0x1800aeeda  mov     r8d, [rsp+4E0h+pulLen]; BufferLen
0x1800aeedf  mov     rdx, rbx; Buffer
0x1800aeee2  xor     ecx, ecx; pszFilter
0x1800aeee4  call    cs:__imp_CM_Get_Device_ID_ListW
0x1800aeeea  mov     ecx, eax; CmReturnCode
0x1800aeeec  mov     edx, edi; DefaultErr
0x1800aeeee  call    cs:__imp_CM_MapCrToWin32Err
0x1800aeef4  mov     edi, eax
0x1800aeef6  test    eax, eax
0x1800aeef8  jle     short loc_1800AEEFF
0x1800aeefa  movzx   edi, ax
0x1800aeefd  or      edi, esi
0x1800aeeff  test    edi, edi
0x1800aef01  jns     short loc_1800AEF49
0x1800aef03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aef0a  lea     r15, WPP_GLOBAL_Control
0x1800aef11  cmp     rcx, r15
0x1800aef14  jz      short loc_1800AEF34
0x1800aef16  test    byte ptr [rcx+1Ch], 1
0x1800aef1a  jz      short loc_1800AEF34
0x1800aef1c  mov     rcx, [rcx+10h]
0x1800aef20  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aef27  mov     edx, 98h
0x1800aef2c  mov     r9d, edi
0x1800aef2f  call    WPP_SF_d
0x1800aef34  test    rbx, rbx
0x1800aef37  jz      short loc_1800AEF42
0x1800aef39  mov     rcx, rbx; pv
0x1800aef3c  call    cs:__imp_CoTaskMemFree
0x1800aef42  mov     eax, edi
0x1800aef44  jmp     loc_1800AF3CE
0x1800aef49  mov     rdi, rbx
0x1800aef4c  mov     [rsp+4E0h+var_498], rbx
0x1800aef51  lea     r15, WPP_GLOBAL_Control
0x1800aef58  cmp     [rdi], r13w
0x1800aef5c  jz      loc_1800AF3BE
0x1800aef62  mov     r8d, 1; ulFlags
0x1800aef68  mov     [rsp+4E0h+pdnDevInst], r13d
0x1800aef6d  mov     rdx, rdi; pDeviceID
0x1800aef70  lea     rcx, [rsp+4E0h+pdnDevInst]; pdnDevInst
0x1800aef75  call    cs:__imp_CM_Locate_DevNodeW
0x1800aef7b  mov     ecx, eax; CmReturnCode
0x1800aef7d  mov     edx, 54Fh; DefaultErr
0x1800aef82  call    cs:__imp_CM_MapCrToWin32Err
0x1800aef88  test    eax, eax
0x1800aef8a  jle     short loc_1800AEF93
0x1800aef8c  movzx   eax, ax
0x1800aef8f  or      eax, esi
0x1800aef91  test    eax, eax
0x1800aef93  jns     short loc_1800AEFCC
0x1800aef95  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aef9c  cmp     rcx, r15
0x1800aef9f  jz      loc_1800AF306
0x1800aefa5  test    byte ptr [rcx+1Ch], 1
0x1800aefa9  jz      loc_1800AF306
0x1800aefaf  mov     rcx, [rcx+10h]
0x1800aefb3  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aefba  mov     edx, 99h
0x1800aefbf  mov     r9d, eax
0x1800aefc2  call    WPP_SF_d
0x1800aefc7  jmp     loc_1800AF306
0x1800aefcc  xor     edx, edx; Val
0x1800aefce  mov     [rsp+4E0h+PropertyType], r13d
0x1800aefd3  mov     r8d, 208h; Size
0x1800aefd9  lea     rcx, [rbp+3E0h+PropertyBuffer]; void *
0x1800aefdd  call    memset_0
0x1800aefe2  mov     ecx, [rsp+4E0h+pdnDevInst]; dnDevInst
0x1800aefe6  lea     rax, [rsp+4E0h+var_4AC]
0x1800aefeb  mov     [rsp+4E0h+ulFlags], r13d; ulFlags
0x1800aeff0  lea     r9, [rbp+3E0h+PropertyBuffer]; PropertyBuffer
0x1800aeff4  lea     r8, [rsp+4E0h+PropertyType]; PropertyType
0x1800aeff9  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800aeffe  lea     rdx, DEVPKEY_Device_DriverInfPath; PropertyKey
0x1800af005  mov     [rsp+4E0h+var_4AC], 104h
0x1800af00d  call    cs:__imp_CM_Get_DevNode_PropertyW
0x1800af013  mov     edi, 54Fh
0x1800af018  mov     ecx, eax; CmReturnCode
0x1800af01a  mov     edx, edi; DefaultErr
0x1800af01c  call    cs:__imp_CM_MapCrToWin32Err
0x1800af022  test    eax, eax
0x1800af024  jle     short loc_1800AF02D
0x1800af026  movzx   eax, ax
0x1800af029  or      eax, esi
0x1800af02b  test    eax, eax
0x1800af02d  js      short loc_1800AF036
0x1800af02f  cmp     [rsp+4E0h+PropertyType], 12h
0x1800af034  jz      short loc_1800AF060
0x1800af036  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af03d  cmp     rcx, r15
0x1800af040  jz      short loc_1800AF060
0x1800af042  test    byte ptr [rcx+1Ch], 1
0x1800af046  jz      short loc_1800AF060
0x1800af048  mov     rcx, [rcx+10h]
0x1800af04c  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800af053  mov     edx, 9Ah
0x1800af058  mov     r9d, eax
0x1800af05b  call    WPP_SF_d
0x1800af060  mov     ecx, [rsp+4E0h+pdnDevInst]; dnDevInst
0x1800af064  lea     rax, [rsp+4E0h+var_4AC]
0x1800af069  mov     [rsp+4E0h+ulFlags], r13d; ulFlags
0x1800af06e  lea     r8, [rsp+4E0h+PropertyType]; PropertyType
0x1800af073  xor     r9d, r9d; PropertyBuffer
0x1800af076  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800af07b  lea     rdx, DEVPKEY_Device_DriverExtendedInfs; PropertyKey
0x1800af082  call    cs:__imp_CM_Get_DevNode_PropertyW
0x1800af088  mov     ecx, eax; CmReturnCode
0x1800af08a  mov     edx, edi; DefaultErr
0x1800af08c  call    cs:__imp_CM_MapCrToWin32Err
0x1800af092  test    eax, eax
0x1800af094  jle     short loc_1800AF09D
0x1800af096  movzx   eax, ax
0x1800af099  or      eax, esi
0x1800af09b  test    eax, eax
0x1800af09d  jns     short loc_1800AF0C9
0x1800af09f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af0a6  cmp     rcx, r15
0x1800af0a9  jz      short loc_1800AF0C9
0x1800af0ab  test    byte ptr [rcx+1Ch], 1
0x1800af0af  jz      short loc_1800AF0C9
0x1800af0b1  mov     rcx, [rcx+10h]
0x1800af0b5  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800af0bc  mov     edx, 9Bh
0x1800af0c1  mov     r9d, eax
0x1800af0c4  call    WPP_SF_d
0x1800af0c9  mov     edx, [rsp+4E0h+var_4AC]
0x1800af0cd  lea     rcx, [rsp+4E0h+var_490]
0x1800af0d2  mov     [rsp+4E0h+var_490], r13
0x1800af0d7  call    ??$UtilCoTaskMemAllocArray@G@CommonUtil@@YAJPEAPEAG_K_N@Z; CommonUtil::UtilCoTaskMemAllocArray<ushort>(ushort * *,unsigned __int64,bool)
0x1800af0dc  mov     edi, eax
0x1800af0de  test    eax, eax
0x1800af0e0  js      loc_1800AF37B
0x1800af0e6  mov     rdi, [rsp+4E0h+var_490]
0x1800af0eb  lea     rax, [rsp+4E0h+var_4AC]
0x1800af0f0  mov     ecx, [rsp+4E0h+pdnDevInst]; dnDevInst
0x1800af0f4  lea     r8, [rsp+4E0h+PropertyType]; PropertyType
0x1800af0f9  mov     r9, rdi; PropertyBuffer
0x1800af0fc  mov     [rsp+4E0h+ulFlags], r13d; ulFlags
0x1800af101  lea     rdx, DEVPKEY_Device_DriverExtendedInfs; PropertyKey
0x1800af108  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800af10d  call    cs:__imp_CM_Get_DevNode_PropertyW
0x1800af113  mov     ecx, eax; CmReturnCode
0x1800af115  mov     edx, 54Fh; DefaultErr
0x1800af11a  call    cs:__imp_CM_MapCrToWin32Err
0x1800af120  test    eax, eax
0x1800af122  jle     short loc_1800AF12B
0x1800af124  movzx   eax, ax
0x1800af127  or      eax, esi
0x1800af129  test    eax, eax
0x1800af12b  js      short loc_1800AF137
0x1800af12d  cmp     [rsp+4E0h+PropertyType], 2012h
0x1800af135  jz      short loc_1800AF161
0x1800af137  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af13e  cmp     rcx, r15
0x1800af141  jz      short loc_1800AF161
0x1800af143  test    byte ptr [rcx+1Ch], 1
0x1800af147  jz      short loc_1800AF161
0x1800af149  mov     rcx, [rcx+10h]
0x1800af14d  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800af154  mov     edx, 9Dh
0x1800af159  mov     r9d, eax
0x1800af15c  call    WPP_SF_d
0x1800af161  lea     rdx, stru_18013A040
0x1800af168  lea     rcx, [rsp+4E0h+var_480]
0x1800af16d  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800af172  mov     rsi, [r14+148h]
0x1800af179  mov     r14, [r14+150h]
0x1800af180  mov     [rsp+4E0h+var_470], 1
0x1800af185  cmp     rsi, r14
0x1800af188  jz      loc_1800AF2DA
0x1800af18e  lea     r13, [rsi+20Ch]
0x1800af195  mov     rcx, r13; String1
0x1800af198  lea     rdx, word_1800F4E78; String2
0x1800af19f  call    cs:__imp__wcsicmp
0x1800af1a5  test    eax, eax
0x1800af1a7  jz      loc_1800AF2CB
0x1800af1ad  lea     rdx, [rbp+3E0h+PropertyBuffer]; String2
0x1800af1b1  mov     rcx, r13; String1
0x1800af1b4  call    cs:__imp__wcsicmp
0x1800af1ba  xor     edx, edx
0x1800af1bc  mov     r13, rdi
0x1800af1bf  test    eax, eax
0x1800af1c1  setz    al
0x1800af1c4  cmp     [rdi], dx
0x1800af1c7  jz      short loc_1800AF20B
0x1800af1c9  test    al, al
0x1800af1cb  jnz     short loc_1800AF1E5
0x1800af1cd  mov     rdx, r13; String2
0x1800af1d0  lea     rcx, [rsi+20Ch]; String1
0x1800af1d7  call    cs:__imp__wcsicmp
0x1800af1dd  xor     edx, edx
0x1800af1df  test    eax, eax
0x1800af1e1  mov     al, dl
0x1800af1e3  jnz     short loc_1800AF1E7
0x1800af1e5  mov     al, 1
0x1800af1e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800af1eb  inc     rcx
0x1800af1ee  cmp     [r13+rcx*2+0], dx
0x1800af1f4  jnz     short loc_1800AF1EB
0x1800af1f6  lea     r13, [r13+rcx*2+0]
0x1800af1fb  add     r13, 2
0x1800af1ff  cmp     [r13+0], dx
0x1800af204  jnz     short loc_1800AF1C9
0x1800af206  mov     rbx, [rsp+4E0h+pv]
0x1800af20b  xor     r13d, r13d
0x1800af20e  test    al, al
0x1800af210  jz      loc_1800AF2CE
0x1800af216  xor     edx, edx; Val
0x1800af218  lea     rcx, [rbp+3E0h+var_250]; void *
0x1800af21f  mov     r8d, 208h; Size
0x1800af225  call    memset_0
0x1800af22a  mov     ecx, [rsp+4E0h+pdnDevInst]; dnDevInst
0x1800af22e  lea     rax, [rsp+4E0h+var_4AC]
0x1800af233  mov     [rsp+4E0h+ulFlags], r13d; ulFlags
0x1800af238  lea     r9, [rbp+3E0h+var_250]; PropertyBuffer
0x1800af23f  lea     r8, [rsp+4E0h+PropertyType]; PropertyType
0x1800af244  mov     [rsp+4E0h+PropertyBufferSize], rax; PropertyBufferSize
0x1800af249  lea     rdx, DEVPKEY_NAME; PropertyKey
0x1800af250  mov     [rsp+4E0h+var_4AC], 104h
0x1800af258  call    cs:__imp_CM_Get_DevNode_PropertyW
0x1800af25e  mov     ecx, eax; CmReturnCode
0x1800af260  mov     edx, 54Fh; DefaultErr
0x1800af265  call    cs:__imp_CM_MapCrToWin32Err
0x1800af26b  test    eax, eax
0x1800af26d  jle     short loc_1800AF279
0x1800af26f  movzx   eax, ax
0x1800af272  or      eax, 80070000h
0x1800af277  test    eax, eax
0x1800af279  js      short loc_1800AF282
0x1800af27b  cmp     [rsp+4E0h+PropertyType], 12h
0x1800af280  jz      short loc_1800AF2AC
  ... truncated ...
```
