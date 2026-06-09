# CSession::_InitCurrentNodes(void)

- ea: `0x18000e228`
- end: `0x18000eab3`
- name: `?_InitCurrentNodes@CSession@@AEAAJXZ`
- size: `2187`
- prototype: `__int64 __fastcall(CSession *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d754`

## callees

- `0x180001444`
- `0x180002228`
- `0x180006d40`
- `0x1800071d4`
- `0x180009c38`
- `0x18000c900`
- `0x18000d27c`
- `0x18000d8d0`
- `0x18000e228`
- `0x18000f75c`
- `0x18000f7c8`
- `0x18000fd90`
- `0x180010150`
- `0x18001dfd6`
- `0x18001e020`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e7c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e93e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e94d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e961`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e7c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e93e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e94d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e54b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e54b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea58`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e39b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e46d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ea76`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e39b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e46d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ea76`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18000e4ee`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18000e4ee`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18000e62d`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18000e74f`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18000e84d`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18000e62d`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18000e74f`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18000e84d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000e5d1`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000e5d1`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e541`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000e541`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000e2d2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000e2d2`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000e3bf`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000e3bf`

## pseudocode

```c
__int64 __fastcall CSession::_InitCurrentNodes(CSession *this)
{
  __int64 DeviceInfoList; // rax
  signed int LastError; // eax
  __int64 v3; // rcx
  unsigned int v4; // edi
  int v5; // eax
  signed int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  signed int v10; // eax
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  int v13; // edx
  _QWORD *v14; // rcx
  signed int v16; // eax
  __int64 v17; // rcx
  signed int v18; // eax
  __int64 v19; // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // rdi
  int DeviceInterfaceProperty; // eax
  __int64 v23; // rcx
  signed int v24; // eax
  __int64 v25; // rcx
  int v26; // edx
  __int64 v27; // rcx
  signed int v28; // eax
  __int64 v29; // rcx
  int v30; // edx
  int v31; // r8d
  int v32; // r9d
  CInformationNode *v33; // rax
  CInformationNode *v34; // rdx
  CInformationNode *v35; // r12
  signed int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  int v39; // [rsp+40h] [rbp-118h] BYREF
  unsigned __int64 v40; // [rsp+44h] [rbp-114h] BYREF
  void **v41; // [rsp+50h] [rbp-108h] BYREF
  __int64 v42; // [rsp+58h] [rbp-100h]
  unsigned int v43; // [rsp+60h] [rbp-F8h] BYREF
  unsigned int v44; // [rsp+64h] [rbp-F4h] BYREF
  unsigned int i; // [rsp+68h] [rbp-F0h]
  int v46; // [rsp+6Ch] [rbp-ECh] BYREF
  _QWORD *v47; // [rsp+70h] [rbp-E8h]
  CInformationNode *v48; // [rsp+78h] [rbp-E0h] BYREF
  _QWORD *v49; // [rsp+80h] [rbp-D8h] BYREF
  CSession *v50; // [rsp+88h] [rbp-D0h]
  CSession *v51; // [rsp+90h] [rbp-C8h]
  _QWORD v52[3]; // [rsp+98h] [rbp-C0h] BYREF
  _OWORD Buf1[2]; // [rsp+B0h] [rbp-A8h] BYREF
  _OWORD v54[3]; // [rsp+D0h] [rbp-88h] BYREF
  char v55[32]; // [rsp+100h] [rbp-58h] BYREF

  v50 = this;
  v51 = this;
  v39 = 0;
  v46 = 0;
  strcpy(v55, "CSession::_InitCurrentNodes");
  v52[0] = v55;
  v52[1] = &v46;
  v52[2] = &v39;
  lambda_d2c068ce23932ef35b13eead3a64477f_::operator()(v52);
  v46 = 1;
  v49 = v52;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v41 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
  v42 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v39 = LastError;
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v39);
    }
    v4 = v39;
    v41 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
    if ( v42 == -1 )
      goto LABEL_26;
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v41) )
      goto LABEL_25;
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    RaiseException(v5, 1u, 0, 0);
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION, 0, 16, 0, 0) )
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v39 = v6;
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v39);
    }
    v4 = v39;
    v41 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
    if ( v42 == -1 )
      goto LABEL_26;
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v41) )
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      RaiseException(v8, 1u, 0, 0);
      __debugbreak();
    }
LABEL_25:
    v42 = -1;
LABEL_26:
    WppTraceUnwinder__lambda_d2c068ce23932ef35b13eead3a64477f____::_WppTraceUnwinder__lambda_d2c068ce23932ef35b13eead3a64477f____(&v49);
    return v4;
  }
  memset(v54, 0, sizeof(v54));
  LODWORD(v54[0]) = 48;
  memset(Buf1, 0, sizeof(Buf1));
  LODWORD(Buf1[0]) = 32;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInfo(v42, i, v54); ++i )
  {
    v40 = 0;
    v43 = 0;
    if ( !(unsigned int)DevObjGetDeviceProperty(v42, v54, &DEVPKEY_Device_SessionId, (char *)&v40 + 4, &v43, 4, &v40, 0) )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      v39 = v10;
      WppTraceIndent(v11, 2);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v13 = 41;
LABEL_96:
        WPP_SF_sd(
          v12[2],
          v13,
          (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
          (_DWORD)WPP_pszIndent,
          v39);
      }
      goto LABEL_97;
    }
    if ( v43 != *(_DWORD *)v50 )
      continue;
    do
    {
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v42, v54, &GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION, 0, Buf1) )
        goto LABEL_47;
    }
    while ( memcmp_0((char *)Buf1 + 4, &GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION, 0x10u) );
    if ( !(unsigned int)DevObjGetDeviceInterfaceProperty(
                          v42,
                          Buf1,
                          &DEVPKEY_Device_ReaderName,
                          (char *)&v40 + 4,
                          0,
                          0,
                          &v40,
                          0) )
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v39 = v16;
      if ( v16 != -2147024774 )
      {
        WppTraceIndent(v17, 2);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
            (_DWORD)WPP_pszIndent,
            v39);
        }
LABEL_47:
        if ( v39 )
          goto LABEL_92;
        v18 = GetLastError();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        v39 = v18;
        WppTraceIndent(v19, 2);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v13 = 47;
          goto LABEL_96;
        }
        goto LABEL_97;
      }
      v39 = 0;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v47 = 0;
      v20 = operator new[]((unsigned int)v40);
      v21 = 0;
      if ( v20 )
        v21 = v20;
      v47 = v21;
      DeviceInterfaceProperty = DevObjGetDeviceInterfaceProperty(
                                  v42,
                                  Buf1,
                                  &DEVPKEY_Device_ReaderName,
                                  (char *)&v40 + 4,
                                  v21,
                                  v40,
                                  &v40,
                                  0);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v39 = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000E973);
LABEL_90:
        v14 = v47;
        if ( !v47 )
        {
LABEL_92:
          WppTraceIndent(v14, 2);
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v13 = 48;
            goto LABEL_96;
          }
          goto LABEL_97;
        }
        operator delete(v47);
        goto LABEL_47;
      }
    }
    if ( !DeviceInterfaceProperty )
    {
      v24 = GetLastError();
      if ( v24 > 0 )
        v24 = (unsigned __int16)v24 | 0x80070000;
      v39 = v24;
      WppTraceIndent(v25, 2);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v26 = 43;
        goto LABEL_65;
      }
      goto LABEL_66;
    }
    WppTraceIndent(v23, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        (__int64)v21);
    }
    v44 = 0;
    if ( !(unsigned int)DevObjGetDeviceInterfaceProperty(
                          v42,
                          Buf1,
                          &DEVPKEY_Device_ReaderKind,
                          (char *)&v40 + 4,
                          &v44,
                          1,
                          &v40,
                          0) )
    {
      v28 = GetLastError();
      if ( v28 > 0 )
        v28 = (unsigned __int16)v28 | 0x80070000;
      v39 = v28;
      WppTraceIndent(v29, 2);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v26 = 45;
LABEL_65:
        WPP_SF_sd(
          v14[2],
          v26,
          (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
          (_DWORD)WPP_pszIndent,
          v39);
      }
LABEL_66:
      if ( v21 )
        operator delete(v21);
      goto LABEL_47;
    }
    WppTraceIndent(v27, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v32, v44);
    }
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      v33 = (CInformationNode *)operator new(0x60u);
      v48 = v33;
      if ( v33 )
        v34 = (CInformationNode *)CInformationNode::CInformationNode((__int64)v33, (__int64)v21, v44, v43);
      else
        v34 = 0;
      v48 = v34;
      std::list<std::unique_ptr<CInformationNode>>::push_back((char *)v51 + 424, &v48);
      v35 = v48;
      if ( v48 )
      {
        CInformationNode::~CInformationNode(v48);
        operator delete(v35);
      }
      if ( v21 )
        operator delete(v21);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v39 = -2147024882;
        __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18000E955);
        goto LABEL_90;
      }
    }
LABEL_97:
    v39 = 0;
  }
  v36 = GetLastError();
  if ( v36 > 0 )
    v36 = (unsigned __int16)v36 | 0x80070000;
  v39 = v36;
  if ( v36 != -2147024637 )
  {
    WppTraceIndent(v37, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)&WPP_c994ce8613043ca68e2941225ff180e5_Traceguids,
        (_DWORD)WPP_pszIndent,
        v39);
    }
  }
  v39 = 0;
  v41 = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable';
  if ( v42 != -1 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(&v41) )
    {
      v38 = GetLastError();
      if ( v38 > 0 )
        v38 = (unsigned __int16)v38 | 0x80070000;
      RaiseException(v38, 1u, 0, 0);
      __debugbreak();
    }
    v42 = -1;
  }
  WppTraceUnwinder__lambda_d2c068ce23932ef35b13eead3a64477f____::_WppTraceUnwinder__lambda_d2c068ce23932ef35b13eead3a64477f____(&v49);
  return 0;
}

```

## disassembly

```asm
0x18000e228  mov     r11, rsp
0x18000e22b  push    rbx
0x18000e22c  push    rdi
0x18000e22d  push    r12
0x18000e22f  push    r13
0x18000e231  sub     rsp, 138h
0x18000e238  mov     rax, cs:__security_cookie
0x18000e23f  xor     rax, rsp
0x18000e242  mov     [rsp+158h+var_38], rax
0x18000e24a  mov     [rsp+158h+var_D0], rcx
0x18000e252  mov     [rsp+158h+var_C8], rcx
0x18000e25a  xor     ebx, ebx
0x18000e25c  mov     [rsp+158h+var_118], ebx
0x18000e260  mov     [rsp+158h+var_EC], ebx
0x18000e264  movups  xmm0, xmmword ptr cs:aCsessionInitcu; "CSession::_InitCurrentNodes"
0x18000e26b  movups  xmmword ptr [r11-58h], xmm0
0x18000e270  movups  xmm1, xmmword ptr cs:aCsessionInitcu+0Ch; "nitCurrentNodes"
0x18000e277  movups  xmmword ptr [r11-4Ch], xmm1
0x18000e27c  lea     rax, [r11-58h]
0x18000e280  mov     [r11-0C0h], rax
0x18000e287  lea     rax, [rsp+158h+var_EC]
0x18000e28c  mov     [r11-0B8h], rax
0x18000e293  lea     rax, [rsp+158h+var_118]
0x18000e298  mov     [r11-0B0h], rax
0x18000e29f  lea     rcx, [r11-0C0h]
0x18000e2a6  call    _lambda_d2c068ce23932ef35b13eead3a64477f___operator__
0x18000e2ab  mov     [rsp+158h+var_EC], 1
0x18000e2b3  lea     rax, [rsp+158h+var_C0]
0x18000e2bb  mov     [rsp+158h+var_D8], rax
0x18000e2c3  mov     [rsp+158h+var_138], rbx
0x18000e2c8  xor     r9d, r9d
0x18000e2cb  xor     r8d, r8d
0x18000e2ce  xor     edx, edx
0x18000e2d0  xor     ecx, ecx
0x18000e2d2  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000e2d8  lea     r12, ??_7?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::`vftable'
0x18000e2df  mov     [rsp+158h+var_108], r12
0x18000e2e4  mov     [rsp+158h+var_100], rax
0x18000e2e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e2ed  jnz     loc_18000E3A2
0x18000e2f3  call    cs:__imp_GetLastError
0x18000e2f9  test    eax, eax
0x18000e2fb  jle     short loc_18000E305
0x18000e2fd  movzx   eax, ax
0x18000e300  or      eax, 80070000h
0x18000e305  mov     [rsp+158h+var_118], eax
0x18000e309  mov     edx, 2
0x18000e30e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000e313  lea     r13, WPP_GLOBAL_Control
0x18000e31a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e321  cmp     rcx, r13
0x18000e324  jz      short loc_18000E356
0x18000e326  test    byte ptr [rcx+1Ch], 1
0x18000e32a  jz      short loc_18000E356
0x18000e32c  cmp     byte ptr [rcx+19h], 2
0x18000e330  jb      short loc_18000E356
0x18000e332  mov     edx, 27h ; '''
0x18000e337  mov     eax, [rsp+158h+var_118]
0x18000e33b  mov     dword ptr [rsp+158h+var_138], eax
0x18000e33f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000e346  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000e34d  mov     rcx, [rcx+10h]
0x18000e351  call    WPP_SF_sd
0x18000e356  mov     edi, [rsp+158h+var_118]
0x18000e35a  mov     [rsp+158h+var_108], r12
0x18000e35f  cmp     [rsp+158h+var_100], 0FFFFFFFFFFFFFFFFh
0x18000e365  jz      loc_18000E47D
0x18000e36b  lea     rcx, [rsp+158h+var_108]
0x18000e370  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x18000e375  test    al, al
0x18000e377  jnz     loc_18000E474
0x18000e37d  call    cs:__imp_GetLastError
0x18000e383  test    eax, eax
0x18000e385  jle     short loc_18000E38F
0x18000e387  movzx   eax, ax
0x18000e38a  or      eax, 80070000h
0x18000e38f  xor     r9d, r9d; lpArguments
0x18000e392  xor     r8d, r8d; nNumberOfArguments
0x18000e395  lea     edx, [r9+1]; dwExceptionFlags
0x18000e399  mov     ecx, eax; dwExceptionCode
0x18000e39b  call    cs:__imp_RaiseException
0x18000e3a1  nop
0x18000e3a2  mov     [rsp+158h+var_130], rbx
0x18000e3a7  mov     [rsp+158h+var_138], rbx
0x18000e3ac  mov     r9d, 10h
0x18000e3b2  xor     r8d, r8d
0x18000e3b5  lea     rdx, GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION
0x18000e3bc  mov     rcx, rax
0x18000e3bf  call    cs:__imp_DevObjGetClassDevs
0x18000e3c5  test    eax, eax
0x18000e3c7  jnz     loc_18000E491
0x18000e3cd  call    cs:__imp_GetLastError
0x18000e3d3  test    eax, eax
0x18000e3d5  jle     short loc_18000E3DF
0x18000e3d7  movzx   eax, ax
0x18000e3da  or      eax, 80070000h
0x18000e3df  mov     [rsp+158h+var_118], eax
0x18000e3e3  mov     edx, 2
0x18000e3e8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000e3ed  lea     r13, WPP_GLOBAL_Control
0x18000e3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3fb  cmp     rcx, r13
0x18000e3fe  jz      short loc_18000E430
0x18000e400  test    byte ptr [rcx+1Ch], 1
0x18000e404  jz      short loc_18000E430
0x18000e406  cmp     byte ptr [rcx+19h], 2
0x18000e40a  jb      short loc_18000E430
0x18000e40c  mov     edx, 28h ; '('
0x18000e411  mov     eax, [rsp+158h+var_118]
0x18000e415  mov     dword ptr [rsp+158h+var_138], eax
0x18000e419  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000e420  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000e427  mov     rcx, [rcx+10h]
0x18000e42b  call    WPP_SF_sd
0x18000e430  mov     edi, [rsp+158h+var_118]
0x18000e434  mov     [rsp+158h+var_108], r12
0x18000e439  cmp     [rsp+158h+var_100], 0FFFFFFFFFFFFFFFFh
0x18000e43f  jz      short loc_18000E47D
0x18000e441  lea     rcx, [rsp+158h+var_108]
0x18000e446  call    ?InternalClose@?$HandleT@USwDeviceInfoListTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceInfoListTraits>::InternalClose(void)
0x18000e44b  test    al, al
0x18000e44d  jnz     short loc_18000E474
0x18000e44f  call    cs:__imp_GetLastError
0x18000e455  test    eax, eax
0x18000e457  jle     short loc_18000E461
0x18000e459  movzx   eax, ax
0x18000e45c  or      eax, 80070000h
0x18000e461  xor     r9d, r9d; lpArguments
0x18000e464  xor     r8d, r8d; nNumberOfArguments
0x18000e467  lea     edx, [r9+1]; dwExceptionFlags
0x18000e46b  mov     ecx, eax; dwExceptionCode
0x18000e46d  call    cs:__imp_RaiseException
0x18000e473  int     3; Trap to Debugger
0x18000e474  mov     [rsp+158h+var_100], 0FFFFFFFFFFFFFFFFh
0x18000e47d  lea     rcx, [rsp+158h+var_D8]
0x18000e485  call    WppTraceUnwinder__lambda_d2c068ce23932ef35b13eead3a64477f_______WppTraceUnwinder__lambda_d2c068ce23932ef35b13eead3a64477f____
0x18000e48a  mov     eax, edi
0x18000e48c  jmp     loc_18000EA95
0x18000e491  xorps   xmm0, xmm0
0x18000e494  movups  [rsp+158h+var_88], xmm0
0x18000e49c  movups  [rsp+158h+var_78], xmm0
0x18000e4a4  movups  [rsp+158h+var_68], xmm0
0x18000e4ac  mov     dword ptr [rsp+158h+var_88], 30h ; '0'
0x18000e4b7  movups  [rsp+158h+Buf1], xmm0
0x18000e4bf  movups  [rsp+158h+var_98], xmm0
0x18000e4c7  mov     dword ptr [rsp+158h+Buf1], 20h ; ' '
0x18000e4d2  mov     [rsp+158h+var_F0], ebx
0x18000e4d6  lea     r13, WPP_GLOBAL_Control
0x18000e4dd  lea     r8, [rsp+158h+var_88]
0x18000e4e5  mov     edx, [rsp+158h+var_F0]
0x18000e4e9  mov     rcx, [rsp+158h+var_100]
0x18000e4ee  call    cs:__imp_DevObjEnumDeviceInfo
0x18000e4f4  test    eax, eax
0x18000e4f6  jz      loc_18000E9CF
0x18000e4fc  mov     dword ptr [rsp+158h+var_114+4], ebx
0x18000e500  mov     dword ptr [rsp+158h+var_114], ebx
0x18000e504  mov     [rsp+158h+var_F8], ebx
0x18000e508  mov     [rsp+158h+var_120], ebx
0x18000e50c  lea     rax, [rsp+158h+var_114]
0x18000e511  mov     [rsp+158h+var_128], rax
0x18000e516  mov     dword ptr [rsp+158h+var_130], 4
0x18000e51e  lea     rax, [rsp+158h+var_F8]
0x18000e523  mov     [rsp+158h+var_138], rax
0x18000e528  lea     r9, [rsp+158h+var_114+4]
0x18000e52d  lea     r8, DEVPKEY_Device_SessionId
0x18000e534  lea     rdx, [rsp+158h+var_88]
0x18000e53c  mov     rcx, [rsp+158h+var_100]
0x18000e541  call    cs:__imp_DevObjGetDeviceProperty
0x18000e547  test    eax, eax
0x18000e549  jnz     short loc_18000E599
0x18000e54b  call    cs:__imp_GetLastError
0x18000e551  test    eax, eax
0x18000e553  jle     short loc_18000E55D
0x18000e555  movzx   eax, ax
0x18000e558  or      eax, 80070000h
0x18000e55d  mov     [rsp+158h+var_118], eax
0x18000e561  mov     edx, 2
0x18000e566  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000e56b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e572  cmp     rcx, r13
0x18000e575  jz      loc_18000E9C2
0x18000e57b  test    byte ptr [rcx+1Ch], 1
0x18000e57f  jz      loc_18000E9C2
0x18000e585  cmp     byte ptr [rcx+19h], 3
0x18000e589  jb      loc_18000E9C2
0x18000e58f  mov     edx, 29h ; ')'
0x18000e594  jmp     loc_18000E9A3
0x18000e599  mov     rax, [rsp+158h+var_D0]
0x18000e5a1  mov     ecx, [rax]
0x18000e5a3  cmp     [rsp+158h+var_F8], ecx
0x18000e5a7  jnz     loc_18000E9C6
0x18000e5ad  lea     rax, [rsp+158h+Buf1]
0x18000e5b5  mov     [rsp+158h+var_138], rax
0x18000e5ba  xor     r9d, r9d
0x18000e5bd  lea     r8, GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION
0x18000e5c4  lea     rdx, [rsp+158h+var_88]
0x18000e5cc  mov     rcx, [rsp+158h+var_100]
0x18000e5d1  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18000e5d7  test    eax, eax
0x18000e5d9  jz      loc_18000E6A2
0x18000e5df  mov     r8d, 10h; Size
0x18000e5e5  lea     rdx, GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION; Buf2
0x18000e5ec  lea     rcx, [rsp+158h+Buf1+4]; Buf1
0x18000e5f4  call    memcmp_0
0x18000e5f9  test    eax, eax
0x18000e5fb  jnz     short loc_18000E5AD
0x18000e5fd  mov     [rsp+158h+var_120], ebx
0x18000e601  lea     rax, [rsp+158h+var_114]
0x18000e606  mov     [rsp+158h+var_128], rax
0x18000e60b  mov     dword ptr [rsp+158h+var_130], ebx
0x18000e60f  mov     [rsp+158h+var_138], rbx
0x18000e614  lea     r9, [rsp+158h+var_114+4]
0x18000e619  lea     r8, DEVPKEY_Device_ReaderName
0x18000e620  lea     rdx, [rsp+158h+Buf1]
0x18000e628  mov     rcx, [rsp+158h+var_100]
0x18000e62d  call    cs:__imp_DevObjGetDeviceInterfaceProperty
0x18000e633  test    eax, eax
0x18000e635  jnz     loc_18000E6FE
0x18000e63b  call    cs:__imp_GetLastError
0x18000e641  test    eax, eax
0x18000e643  jle     short loc_18000E64D
0x18000e645  movzx   eax, ax
0x18000e648  or      eax, 80070000h
0x18000e64d  mov     [rsp+158h+var_118], eax
0x18000e651  cmp     eax, 8007007Ah
0x18000e656  jz      loc_18000E6FA
0x18000e65c  mov     edx, 2
0x18000e661  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000e666  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e66d  cmp     rcx, r13
0x18000e670  jz      short loc_18000E6A2
0x18000e672  test    byte ptr [rcx+1Ch], 1
0x18000e676  jz      short loc_18000E6A2
0x18000e678  cmp     byte ptr [rcx+19h], 3
0x18000e67c  jb      short loc_18000E6A2
0x18000e67e  mov     edx, 2Ah ; '*'
0x18000e683  mov     eax, [rsp+158h+var_118]
0x18000e687  mov     dword ptr [rsp+158h+var_138], eax
0x18000e68b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000e692  lea     r8, WPP_c994ce8613043ca68e2941225ff180e5_Traceguids
0x18000e699  mov     rcx, [rcx+10h]
0x18000e69d  call    WPP_SF_sd
0x18000e6a2  cmp     [rsp+158h+var_118], ebx
0x18000e6a6  jnz     loc_18000E97C
0x18000e6ac  call    cs:__imp_GetLastError
0x18000e6b2  test    eax, eax
0x18000e6b4  jle     short loc_18000E6BE
0x18000e6b6  movzx   eax, ax
0x18000e6b9  or      eax, 80070000h
0x18000e6be  mov     [rsp+158h+var_118], eax
0x18000e6c2  mov     edx, 2
0x18000e6c7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000e6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6d3  cmp     rcx, r13
0x18000e6d6  jz      loc_18000E9C2
0x18000e6dc  test    byte ptr [rcx+1Ch], 1
0x18000e6e0  jz      loc_18000E9C2
0x18000e6e6  cmp     byte ptr [rcx+19h], 3
0x18000e6ea  jb      loc_18000E9C2
0x18000e6f0  mov     edx, 2Fh ; '/'
0x18000e6f5  jmp     loc_18000E9A3
0x18000e6fa  mov     [rsp+158h+var_118], ebx
0x18000e6fe  mov     [rsp+158h+var_E8], rbx
0x18000e703  mov     ecx, dword ptr [rsp+158h+var_114]; unsigned __int64
0x18000e707  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e70c  mov     rdi, rbx
0x18000e70f  test    rax, rax
0x18000e712  cmovnz  rdi, rax
0x18000e716  mov     [rsp+158h+var_E8], rdi
0x18000e71b  mov     eax, dword ptr [rsp+158h+var_114]
0x18000e71f  mov     [rsp+158h+var_120], ebx
0x18000e723  lea     rcx, [rsp+158h+var_114]
0x18000e728  mov     [rsp+158h+var_128], rcx
0x18000e72d  mov     dword ptr [rsp+158h+var_130], eax
0x18000e731  mov     [rsp+158h+var_138], rdi
0x18000e736  lea     r9, [rsp+158h+var_114+4]
0x18000e73b  lea     r8, DEVPKEY_Device_ReaderName
0x18000e742  lea     rdx, [rsp+158h+Buf1]
0x18000e74a  mov     rcx, [rsp+158h+var_100]
0x18000e74f  call    cs:__imp_DevObjGetDeviceInterfaceProperty
0x18000e755  test    eax, eax
0x18000e757  jnz     short loc_18000E7CD
0x18000e759  call    cs:__imp_GetLastError
0x18000e75f  test    eax, eax
0x18000e761  jle     short loc_18000E76B
0x18000e763  movzx   eax, ax
0x18000e766  or      eax, 80070000h
0x18000e76b  mov     [rsp+158h+var_118], eax
0x18000e76f  mov     edx, 2
0x18000e774  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000e779  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e780  cmp     rcx, r13
0x18000e783  jz      short loc_18000E7B6
0x18000e785  test    byte ptr [rcx+1Ch], 1
0x18000e789  jz      short loc_18000E7B6
0x18000e78b  cmp     byte ptr [rcx+19h], 3
0x18000e78f  jb      short loc_18000E7B6
0x18000e791  mov     edx, 2Bh ; '+'
0x18000e796  mov     eax, [rsp+158h+var_118]
0x18000e79a  mov     dword ptr [rsp+158h+var_138], eax
  ... truncated ...
```
