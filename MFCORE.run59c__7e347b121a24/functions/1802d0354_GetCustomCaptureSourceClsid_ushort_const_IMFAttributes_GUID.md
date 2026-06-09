# GetCustomCaptureSourceClsid(ushort const *,IMFAttributes *,_GUID *)

- ea: `0x1802d0354`
- end: `0x1802d0953`
- name: `?GetCustomCaptureSourceClsid@@YAJPEBGPEAUIMFAttributes@@PEAU_GUID@@@Z`
- size: `1535`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, struct IMFAttributes *, struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18017b2c8`

## callees

- `0x180050d6c`
- `0x1800caaac`
- `0x1800cac5c`
- `0x1800d56f4`
- `0x180115b2c`
- `0x180115c28`
- `0x1801243fc`
- `0x18015fae4`
- `0x180258390`
- `0x1802583a8`
- `0x180258480`
- `0x180259174`
- `0x1802592a0`
- `0x1802d0354`
- `0x18030ee0c`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d0631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d068e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d07ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d0631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d068e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802d07ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802d067a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802d07dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802d067a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1802d07dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d08ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d08ea`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1802d0862`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1802d0862`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1802d05d5`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x1802d05d5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1802d05ec`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1802d05ec`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1802d06ed`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1802d06ed`

## string_xrefs

- `0x1802d0660`: `CustomCaptureSourceClsid`
- `0x1802d07c6`: `CustomCaptureSourceClsid`

## pseudocode

```c
__int64 __fastcall GetCustomCaptureSourceClsid(LPCWSTR pszDeviceInterface, struct IMFAttributes *a2, struct _GUID *a3)
{
  char v6; // r14
  void *pvData; // r12
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  GuidTrace *v12; // rax
  const char *String; // rax
  GuidTrace *v14; // rax
  const char *v15; // rax
  CONFIGRET v16; // eax
  signed int v17; // eax
  signed int LastError; // eax
  signed int v19; // eax
  GuidTrace *v20; // rax
  const char *v21; // rax
  signed int v22; // eax
  const char *v23; // r9
  bool v25; // [rsp+40h] [rbp-C0h] BYREF
  bool v26; // [rsp+41h] [rbp-BFh] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY phkDeviceInterface; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h] BYREF
  ULONG PropertyBufferSize[2]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v33[40]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t PropertyBuffer[264]; // [rsp+90h] [rbp-70h] BYREF

  PropertyType = 0;
  phkDeviceInterface = 0;
  v28 = 0;
  v6 = 0;
  v31 = 0;
  pvData = 0;
  v25 = 0;
  v26 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = -2147024809;
    if ( g_wppLevels < 8u )
      goto LABEL_71;
    v10 = 221;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, 0, v8);
    goto LABEL_67;
  }
  if ( !pszDeviceInterface )
  {
    v8 = -2147024809;
    v9 = -2147024809;
    if ( g_wppLevels < 8u )
      goto LABEL_71;
    v10 = 222;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v9 = -2147467261;
    if ( g_wppLevels < 8u )
      goto LABEL_71;
    v11 = 223;
    goto LABEL_12;
  }
  v9 = 0;
  *a3 = GUID_00000000_0000_0000_0000_000000000000;
  if ( (unsigned __int8)byte_1803CECED >= 8u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      224,
      &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
      pszDeviceInterface);
  if ( (int)FSIsNetworkCamera(pszDeviceInterface, &v25) >= 0 && v25
    || ((int (__fastcall *)(struct IMFAttributes *, void *, int *))a2->lpVtbl->GetStringLength)(
         a2,
         &MF_DEVSOURCE_ATTRIBUTE_SOURCE_STREAM_URL,
         &v28) >= 0
    || ((int (__fastcall *)(struct IMFAttributes *, void *, int *))a2->lpVtbl->GetStringLength)(
         a2,
         &MF_DEVSOURCE_ATTRIBUTE_SOURCE_XADDRESS,
         &v31) >= 0 )
  {
    *a3 = CLSID_FrameServerNetworkCameraSource;
    if ( (unsigned __int8)byte_1803CECED >= 8u )
    {
      if ( v25 )
      {
        v23 = "refstring";
      }
      else
      {
        v23 = "stream_url";
        if ( !v28 )
          v23 = "xaddress";
      }
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 225, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, v23);
    }
    goto LABEL_67;
  }
  if ( ((int (__fastcall *)(struct IMFAttributes *, void *, struct _GUID *))a2->lpVtbl->GetGUID)(
         a2,
         &MF_DEVSOURCE_CUSTOM_SOURCE_CLSID,
         a3) >= 0 )
  {
    if ( (unsigned __int8)byte_1803CECED >= 8u )
    {
      v12 = GuidTrace::GuidTrace((GuidTrace *)v33, a3);
      String = GuidTrace::GetString(v12);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 226, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, String);
      v6 = 1;
    }
    if ( (v6 & 1) != 0 )
      FSString::~FSString((FSString *)v33);
    goto LABEL_67;
  }
  if ( (int)FSIsDshowFIlterToMFBridge(pszDeviceInterface, &v26) >= 0 )
  {
    *a3 = CLSID_MFDShowReverseBridgeSource;
    if ( (unsigned __int8)byte_1803CECED >= 8u )
    {
      v14 = GuidTrace::GuidTrace((GuidTrace *)v33, a3);
      v15 = GuidTrace::GetString(v14);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 227, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, v15);
      v6 = 2;
    }
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      FSString::~FSString((FSString *)v33);
    }
  }
  v16 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, &phkDeviceInterface, 0);
  if ( v16 )
  {
    v17 = CM_MapCrToWin32Err(v16, 0xDu);
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    if ( (unsigned __int8)byte_1803CECED >= 8u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        228,
        &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids,
        (unsigned int)v17);
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_67;
  }
  pcbData = 0;
  if ( RegGetValueW(phkDeviceInterface, 0, L"CustomCaptureSourceClsid", 2u, 0, 0, &pcbData) )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    PropertyType = 18;
    memset_0(PropertyBuffer, 0, 0x208u);
    *(_QWORD *)PropertyBufferSize = 518;
    if ( !CM_Get_Device_Interface_PropertyW(
            pszDeviceInterface,
            &DEVPKEY_DeviceInterface_ReferenceString,
            &PropertyType,
            (PBYTE)PropertyBuffer,
            PropertyBufferSize,
            0)
      && !wcsicmp(PropertyBuffer, L"{F5E9E279-06E1-4094-96C4-B43B37852EB2}") )
    {
      *a3 = CLSID_FrameServerNetworkCameraSource;
      if ( (unsigned __int8)byte_1803CECED >= 8u )
      {
        v6 |= 4u;
        v20 = GuidTrace::GuidTrace((GuidTrace *)v33, a3);
        v21 = GuidTrace::GetString(v20);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 229, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, v21);
      }
      if ( (v6 & 4) != 0 )
        FSString::~FSString((FSString *)v33);
      v9 = 0;
    }
    goto LABEL_67;
  }
  if ( pcbData >= 2 )
  {
    pvData = operator new(pcbData);
    if ( !pvData )
    {
      v9 = -2147024882;
      if ( g_wppLevels < 8u )
        goto LABEL_67;
      v11 = 230;
      goto LABEL_12;
    }
    if ( !RegGetValueW(phkDeviceInterface, 0, L"CustomCaptureSourceClsid", 2u, 0, pvData, &pcbData) )
      goto LABEL_56;
    v22 = GetLastError();
    v9 = v22;
    if ( v22 > 0 )
      v9 = (unsigned __int16)v22 | 0x80070000;
    if ( (v9 & 0x80000000) == 0 )
    {
LABEL_56:
      *((_WORD *)pvData + ((unsigned __int64)pcbData >> 1) - 1) = 0;
      if ( (unsigned __int8)byte_1803CECED >= 8u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 232, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, pvData);
      v8 = IIDFromString((LPCOLESTR)pvData, a3);
      v9 = v8;
      if ( v8 >= 0 || g_wppLevels < 8u )
        goto LABEL_67;
      v10 = 233;
      goto LABEL_4;
    }
    if ( g_wppLevels >= 8u )
    {
      v11 = 231;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, 0, v9);
    }
  }
LABEL_67:
  if ( phkDeviceInterface )
    CloseHandle(phkDeviceInterface);
  if ( pvData )
    operator delete(pvData);
LABEL_71:
  if ( (unsigned __int8)byte_1803CECED >= 8u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 234, &WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1802d0354  push    rbp
0x1802d0356  push    rbx
0x1802d0357  push    rsi
0x1802d0358  push    r12
0x1802d035a  push    r13
0x1802d035c  push    r14
0x1802d035e  push    r15
0x1802d0360  lea     rbp, [rsp-1B0h]
0x1802d0368  sub     rsp, 2B0h
0x1802d036f  mov     rax, cs:__security_cookie
0x1802d0376  xor     rax, rsp
0x1802d0379  mov     [rbp+1E0h+var_40], rax
0x1802d0380  xor     eax, eax
0x1802d0382  mov     r15, r8
0x1802d0385  mov     [rsp+2E0h+PropertyType], eax
0x1802d0389  mov     rsi, rdx
0x1802d038c  mov     [rsp+2E0h+phkDeviceInterface], rax
0x1802d0391  mov     r13, rcx
0x1802d0394  mov     [rsp+2E0h+var_298], eax
0x1802d0398  mov     r14d, eax
0x1802d039b  mov     [rsp+2E0h+var_288], eax
0x1802d039f  mov     r12d, eax
0x1802d03a2  mov     [rsp+2E0h+var_2A0], al
0x1802d03a6  mov     [rsp+2E0h+var_29F], al
0x1802d03aa  test    rdx, rdx
0x1802d03ad  jnz     short loc_1802D03EB
0x1802d03af  mov     eax, 80070057h
0x1802d03b4  mov     ebx, eax
0x1802d03b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1802d03bd  jb      loc_1802D0903
0x1802d03c3  mov     edx, 0DDh
0x1802d03c8  mov     [rsp+2E0h+ulFlags], eax
0x1802d03cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1802d03d3  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1802d03da  xor     r9d, r9d
0x1802d03dd  mov     rcx, [rcx+10h]
0x1802d03e1  call    WPP_SF_qD
0x1802d03e6  jmp     loc_1802D08E0
0x1802d03eb  test    r13, r13
0x1802d03ee  jnz     short loc_1802D040B
0x1802d03f0  mov     eax, 80070057h
0x1802d03f5  mov     ebx, eax
0x1802d03f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1802d03fe  jb      loc_1802D0903
0x1802d0404  mov     edx, 0DEh
0x1802d0409  jmp     short loc_1802D03C8
0x1802d040b  test    r15, r15
0x1802d040e  jnz     short loc_1802D042D
0x1802d0410  mov     ebx, 80004003h
0x1802d0415  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1802d041c  jb      loc_1802D0903
0x1802d0422  mov     edx, 0DFh
0x1802d0427  mov     [rsp+2E0h+ulFlags], ebx
0x1802d042b  jmp     short loc_1802D03CC
0x1802d042d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1802d0434  mov     ebx, eax
0x1802d0436  movdqu  xmmword ptr [r8], xmm0
0x1802d043b  cmp     cs:byte_1803CECED, 8
0x1802d0442  jb      short loc_1802D0466
0x1802d0444  mov     rcx, cs:WPP_GLOBAL_Control
0x1802d044b  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1802d0452  mov     edx, 0E0h
0x1802d0457  mov     r9, r13
0x1802d045a  mov     rcx, [rcx+0D8h]
0x1802d0461  call    WPP_SF_S
0x1802d0466  lea     rdx, [rsp+2E0h+var_2A0]; bool *
0x1802d046b  mov     rcx, r13; pszDeviceInterface
0x1802d046e  call    ?FSIsNetworkCamera@@YAJPEBGPEA_N@Z; FSIsNetworkCamera(ushort const *,bool *)
0x1802d0473  test    eax, eax
0x1802d0475  js      short loc_1802D0481
0x1802d0477  cmp     [rsp+2E0h+var_2A0], bl
0x1802d047b  jnz     loc_1802D0887
0x1802d0481  mov     rax, [rsi]
0x1802d0484  lea     r8, [rsp+2E0h+var_298]
0x1802d0489  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_STREAM_URL
0x1802d0490  mov     rcx, rsi
0x1802d0493  mov     rax, [rax+58h]
0x1802d0497  call    cs:__guard_dispatch_icall_fptr
0x1802d049d  test    eax, eax
0x1802d049f  jns     loc_1802D0887
0x1802d04a5  mov     rax, [rsi]
0x1802d04a8  lea     r8, [rsp+2E0h+var_288]
0x1802d04ad  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_XADDRESS
0x1802d04b4  mov     rcx, rsi
0x1802d04b7  mov     rax, [rax+58h]
0x1802d04bb  call    cs:__guard_dispatch_icall_fptr
0x1802d04c1  test    eax, eax
0x1802d04c3  jns     loc_1802D0887
0x1802d04c9  mov     rax, [rsi]
0x1802d04cc  lea     rdx, MF_DEVSOURCE_CUSTOM_SOURCE_CLSID
0x1802d04d3  mov     r8, r15
0x1802d04d6  mov     rcx, rsi
0x1802d04d9  mov     rax, [rax+50h]
0x1802d04dd  call    cs:__guard_dispatch_icall_fptr
0x1802d04e3  test    eax, eax
0x1802d04e5  js      short loc_1802D0546
0x1802d04e7  cmp     cs:byte_1803CECED, 8
0x1802d04ee  jb      short loc_1802D052D
0x1802d04f0  mov     rdx, r15; struct _GUID *
0x1802d04f3  lea     rcx, [rsp+2E0h+var_278]; this
0x1802d04f8  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1802d04fd  mov     rcx, rax; this
0x1802d0500  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1802d0505  mov     rcx, cs:WPP_GLOBAL_Control
0x1802d050c  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1802d0513  mov     edx, 0E2h
0x1802d0518  mov     r9, rax
0x1802d051b  mov     rcx, [rcx+0D8h]
0x1802d0522  call    WPP_SF_s
0x1802d0527  mov     r14d, 1
0x1802d052d  test    r14b, 1
0x1802d0531  jz      loc_1802D08E0
0x1802d0537  lea     rcx, [rsp+2E0h+var_278]; this
0x1802d053c  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1802d0541  jmp     loc_1802D08E0
0x1802d0546  lea     rdx, [rsp+2E0h+var_29F]; bool *
0x1802d054b  mov     rcx, r13; pszDeviceInterface
0x1802d054e  call    ?FSIsDshowFIlterToMFBridge@@YAJPEBGPEA_N@Z; FSIsDshowFIlterToMFBridge(ushort const *,bool *)
0x1802d0553  mov     esi, 2
0x1802d0558  test    eax, eax
0x1802d055a  js      short loc_1802D05BE
0x1802d055c  movups  xmm0, xmmword ptr cs:CLSID_MFDShowReverseBridgeSource.Data1
0x1802d0563  movdqu  xmmword ptr [r15], xmm0
0x1802d0568  cmp     cs:byte_1803CECED, 8
0x1802d056f  jb      short loc_1802D05AB
0x1802d0571  mov     rdx, r15; struct _GUID *
0x1802d0574  lea     rcx, [rsp+2E0h+var_278]; this
0x1802d0579  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1802d057e  mov     rcx, rax; this
0x1802d0581  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1802d0586  mov     rcx, cs:WPP_GLOBAL_Control
0x1802d058d  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1802d0594  mov     edx, 0E3h
0x1802d0599  mov     r9, rax
0x1802d059c  mov     rcx, [rcx+0D8h]
0x1802d05a3  call    WPP_SF_s
0x1802d05a8  mov     r14d, esi
0x1802d05ab  test    sil, r14b
0x1802d05ae  jz      short loc_1802D05BE
0x1802d05b0  and     r14d, 0FFFFFFFDh
0x1802d05b4  lea     rcx, [rsp+2E0h+var_278]; this
0x1802d05b9  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1802d05be  lea     r9, [rsp+2E0h+phkDeviceInterface]; phkDeviceInterface
0x1802d05c3  mov     [rsp+2E0h+ulFlags], ebx; ulFlags
0x1802d05c7  mov     edx, 20019h; samDesired
0x1802d05cc  mov     r8d, 1; Disposition
0x1802d05d2  mov     rcx, r13; pszDeviceInterface
0x1802d05d5  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x1802d05dc  nop     dword ptr [rax+rax+00h]
0x1802d05e1  test    eax, eax
0x1802d05e3  jz      short loc_1802D0651
0x1802d05e5  mov     edx, 0Dh; DefaultErr
0x1802d05ea  mov     ecx, eax; CmReturnCode
0x1802d05ec  call    cs:__imp_CM_MapCrToWin32Err
0x1802d05f3  nop     dword ptr [rax+rax+00h]
0x1802d05f8  mov     esi, 80070000h
0x1802d05fd  test    eax, eax
0x1802d05ff  jle     short loc_1802D0606
0x1802d0601  movzx   eax, ax
0x1802d0604  or      eax, esi
0x1802d0606  cmp     cs:byte_1803CECED, 8
0x1802d060d  jb      short loc_1802D0631
0x1802d060f  mov     rcx, cs:WPP_GLOBAL_Control
0x1802d0616  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1802d061d  mov     edx, 0E4h
0x1802d0622  mov     r9d, eax
0x1802d0625  mov     rcx, [rcx+0D8h]
0x1802d062c  call    WPP_SF_d
0x1802d0631  call    cs:__imp_GetLastError
0x1802d0638  nop     dword ptr [rax+rax+00h]
0x1802d063d  mov     ebx, eax
0x1802d063f  test    eax, eax
0x1802d0641  jle     loc_1802D08E0
0x1802d0647  movzx   ebx, ax
0x1802d064a  or      ebx, esi
0x1802d064c  jmp     loc_1802D08E0
0x1802d0651  mov     rcx, [rsp+2E0h+phkDeviceInterface]; hkey
0x1802d0656  lea     rax, [rsp+2E0h+var_29C]
0x1802d065b  mov     [rsp+2E0h+pcbData], rax; pcbData
0x1802d0660  lea     r8, aCustomcaptures; "CustomCaptureSourceClsid"
0x1802d0667  mov     [rsp+2E0h+pvData], rbx; pvData
0x1802d066c  mov     r9d, esi; dwFlags
0x1802d066f  xor     edx, edx; lpSubKey
0x1802d0671  mov     qword ptr [rsp+2E0h+ulFlags], rbx; pdwType
0x1802d0676  mov     [rsp+2E0h+var_29C], ebx
0x1802d067a  call    cs:__imp_RegGetValueW
0x1802d0681  nop     dword ptr [rax+rax+00h]
0x1802d0686  test    eax, eax
0x1802d0688  jz      loc_1802D0780
0x1802d068e  call    cs:__imp_GetLastError
0x1802d0695  nop     dword ptr [rax+rax+00h]
0x1802d069a  mov     ebx, eax
0x1802d069c  test    eax, eax
0x1802d069e  jle     short loc_1802D06A9
0x1802d06a0  movzx   ebx, ax
0x1802d06a3  or      ebx, 80070000h
0x1802d06a9  xor     edx, edx; Val
0x1802d06ab  mov     [rsp+2E0h+PropertyType], 12h
0x1802d06b3  mov     r8d, 208h; Size
0x1802d06b9  lea     rcx, [rbp+1E0h+PropertyBuffer]; void *
0x1802d06bd  call    memset_0
0x1802d06c2  lea     rax, [rsp+2E0h+PropertyBufferSize]
0x1802d06c7  mov     dword ptr [rsp+2E0h+pvData], r12d; ulFlags
0x1802d06cc  lea     r9, [rbp+1E0h+PropertyBuffer]; PropertyBuffer
0x1802d06d0  mov     qword ptr [rsp+2E0h+ulFlags], rax; PropertyBufferSize
0x1802d06d5  lea     r8, [rsp+2E0h+PropertyType]; PropertyType
0x1802d06da  mov     qword ptr [rsp+2E0h+PropertyBufferSize], 206h
0x1802d06e3  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x1802d06ea  mov     rcx, r13; pszDeviceInterface
0x1802d06ed  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1802d06f4  nop     dword ptr [rax+rax+00h]
0x1802d06f9  test    eax, eax
0x1802d06fb  jnz     loc_1802D08E0
0x1802d0701  lea     rdx, aF5e9e27906e140; "{F5E9E279-06E1-4094-96C4-B43B37852EB2}"
0x1802d0708  lea     rcx, [rbp+1E0h+PropertyBuffer]; String1
0x1802d070c  call    _wcsicmp
0x1802d0711  test    eax, eax
0x1802d0713  jnz     loc_1802D08E0
0x1802d0719  movups  xmm0, xmmword ptr cs:CLSID_FrameServerNetworkCameraSource.Data1
0x1802d0720  movdqu  xmmword ptr [r15], xmm0
0x1802d0725  cmp     cs:byte_1803CECED, 8
0x1802d072c  jb      short loc_1802D0769
0x1802d072e  mov     rdx, r15; struct _GUID *
0x1802d0731  lea     rcx, [rsp+2E0h+var_278]; this
0x1802d0736  or      r14d, 4
0x1802d073a  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1802d073f  mov     rcx, rax; this
0x1802d0742  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1802d0747  mov     rcx, cs:WPP_GLOBAL_Control
0x1802d074e  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1802d0755  mov     edx, 0E5h
0x1802d075a  mov     r9, rax
0x1802d075d  mov     rcx, [rcx+0D8h]
0x1802d0764  call    WPP_SF_s
0x1802d0769  test    r14b, 4
0x1802d076d  jz      short loc_1802D0779
0x1802d076f  lea     rcx, [rsp+2E0h+var_278]; this
0x1802d0774  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1802d0779  xor     ebx, ebx
0x1802d077b  jmp     loc_1802D08E0
0x1802d0780  cmp     [rsp+2E0h+var_29C], esi
0x1802d0784  jb      loc_1802D08E0
0x1802d078a  mov     ecx, [rsp+2E0h+var_29C]; Size
0x1802d078e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802d0793  mov     r12, rax
0x1802d0796  test    rax, rax
0x1802d0799  jnz     short loc_1802D07B7
0x1802d079b  mov     ebx, 8007000Eh
0x1802d07a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1802d07a7  jb      loc_1802D08E0
0x1802d07ad  mov     edx, 0E6h
0x1802d07b2  jmp     loc_1802D0427
0x1802d07b7  mov     rcx, [rsp+2E0h+phkDeviceInterface]; hkey
0x1802d07bc  lea     rax, [rsp+2E0h+var_29C]
0x1802d07c1  mov     [rsp+2E0h+pcbData], rax; pcbData
0x1802d07c6  lea     r8, aCustomcaptures; "CustomCaptureSourceClsid"
0x1802d07cd  mov     [rsp+2E0h+pvData], r12; pvData
0x1802d07d2  mov     r9d, esi; dwFlags
0x1802d07d5  xor     edx, edx; lpSubKey
0x1802d07d7  mov     qword ptr [rsp+2E0h+ulFlags], rbx; pdwType
0x1802d07dc  call    cs:__imp_RegGetValueW
0x1802d07e3  nop     dword ptr [rax+rax+00h]
0x1802d07e8  test    eax, eax
0x1802d07ea  jz      short loc_1802D0822
0x1802d07ec  call    cs:__imp_GetLastError
0x1802d07f3  nop     dword ptr [rax+rax+00h]
0x1802d07f8  mov     ebx, eax
0x1802d07fa  test    eax, eax
0x1802d07fc  jle     short loc_1802D0807
0x1802d07fe  movzx   ebx, ax
0x1802d0801  or      ebx, 80070000h
0x1802d0807  test    ebx, ebx
0x1802d0809  jns     short loc_1802D0822
0x1802d080b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1802d0812  jb      loc_1802D08E0
0x1802d0818  mov     edx, 0E7h
0x1802d081d  jmp     loc_1802D0427
0x1802d0822  mov     ecx, [rsp+2E0h+var_29C]
0x1802d0826  shr     rcx, 1
0x1802d0829  xor     eax, eax
0x1802d082b  mov     [r12+rcx*2-2], ax
0x1802d0831  cmp     cs:byte_1803CECED, 8
0x1802d0838  jb      short loc_1802D085C
0x1802d083a  mov     rcx, cs:WPP_GLOBAL_Control
0x1802d0841  lea     r8, WPP_94c3afff24df3cc4adf97e6ddace8cbc_Traceguids
0x1802d0848  mov     edx, 0E8h
0x1802d084d  mov     r9, r12
0x1802d0850  mov     rcx, [rcx+0D8h]
0x1802d0857  call    WPP_SF_S
0x1802d085c  mov     rdx, r15; lpiid
0x1802d085f  mov     rcx, r12; lpsz
0x1802d0862  call    cs:__imp_IIDFromString
0x1802d0869  nop     dword ptr [rax+rax+00h]
0x1802d086e  mov     ebx, eax
0x1802d0870  test    eax, eax
0x1802d0872  jns     short loc_1802D08E0
0x1802d0874  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1802d087b  jb      short loc_1802D08E0
0x1802d087d  mov     edx, 0E9h
0x1802d0882  jmp     loc_1802D03C8
  ... truncated ...
```
