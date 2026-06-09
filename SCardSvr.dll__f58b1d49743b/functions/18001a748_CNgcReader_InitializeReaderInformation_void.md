# CNgcReader::InitializeReaderInformation(void)

- ea: `0x18001a748`
- end: `0x18001af35`
- name: `?InitializeReaderInformation@CNgcReader@@IEAAXXZ`
- size: `2029`
- prototype: `void __fastcall(CNgcReader *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002c070`

## callees

- `0x1800022b0`
- `0x1800044e0`
- `0x18000d7a0`
- `0x180012740`
- `0x1800136a0`
- `0x180014b88`
- `0x180015044`
- `0x18001a748`
- `0x18001b304`
- `0x18001b380`
- `0x18001b3fc`
- `0x18001b5cc`
- `0x18001b7b0`
- `0x180023168`
- `0x18002b654`
- `0x18002b980`
- `0x18002c160`
- `0x18003261b`
- `0x1800326d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001aec5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001aec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ace0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ace0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aea7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ad9d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001ad4c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001ad4c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ad1d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ad1d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001accb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001accb`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18001a8e2`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18001a8e2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001a7ed`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001a7ed`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18001a9d1`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18001aa56`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18001a9d1`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x18001aa56`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18001ab36`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x18001ab36`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001a969`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001a969`

## string_xrefs

- `0x18001a785`: `CNgcReader::InitializeReaderInformation`

## pseudocode

```c
void __fastcall CNgcReader::InitializeReaderInformation(CNgcReader *this)
{
  DWORD LastError; // ebx
  const unsigned __int8 *v3; // rcx
  __int64 v4; // rax
  const unsigned __int16 *v5; // rax
  DWORD v6; // ebx
  const unsigned __int8 *v7; // rcx
  DWORD v8; // eax
  const unsigned __int8 *v9; // rcx
  ulong v10; // ebx
  DWORD v11; // eax
  const unsigned __int8 *v12; // rcx
  ulong v13; // ebx
  WCHAR *v14; // r14
  const WCHAR *v15; // r8
  DWORD v16; // ebx
  const unsigned __int8 *v17; // rcx
  unsigned int v18; // ebx
  const WCHAR *v19; // rdx
  const unsigned __int8 *v20; // rcx
  DWORD v21; // ebx
  const unsigned __int8 *v22; // rcx
  int DevicePropertyString; // eax
  const unsigned __int8 *v24; // rcx
  ulong v25; // ebx
  unsigned __int8 *v26; // rdi
  DWORD LengthSid; // esi
  int v28; // eax
  const unsigned __int8 *v29; // rcx
  ulong v30; // ebx
  const WCHAR *v31; // rax
  BOOL v32; // ebx
  DWORD v33; // ebx
  const unsigned __int8 *v34; // rcx
  DWORD v35; // ebx
  const unsigned __int8 *v36; // rcx
  PSID v37; // rcx
  unsigned int v38; // ebx
  const unsigned __int8 *v39; // rax
  unsigned int v40; // ebx
  const unsigned __int8 *v41; // rax
  int v42; // eax
  ulong pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v44; // [rsp+44h] [rbp-BCh] BYREF
  PSID pSid; // [rsp+48h] [rbp-B8h] BYREF
  void **v46; // [rsp+50h] [rbp-B0h] BYREF
  void *DeviceInfoList; // [rsp+58h] [rbp-A8h]
  int v48; // [rsp+60h] [rbp-A0h] BYREF
  int v49; // [rsp+64h] [rbp-9Ch] BYREF
  int v50; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v51[8]; // [rsp+70h] [rbp-90h] BYREF
  void *Block; // [rsp+78h] [rbp-88h]
  unsigned int v53; // [rsp+80h] [rbp-80h]
  unsigned int v54; // [rsp+84h] [rbp-7Ch]
  void **v55; // [rsp+88h] [rbp-78h] BYREF
  PSID pDestinationSid; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  _QWORD *v58; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v59[3]; // [rsp+A8h] [rbp-58h] BYREF
  void **v60; // [rsp+C0h] [rbp-40h] BYREF
  int v61; // [rsp+C8h] [rbp-38h]
  void **v62; // [rsp+D0h] [rbp-30h]
  __int64 v63; // [rsp+D8h] [rbp-28h]
  __int64 v64; // [rsp+E0h] [rbp-20h]
  void **v65; // [rsp+E8h] [rbp-18h]
  __int64 v66; // [rsp+F0h] [rbp-10h]
  __int64 v67; // [rsp+F8h] [rbp-8h]
  void **v68; // [rsp+100h] [rbp+0h] BYREF
  int v69; // [rsp+108h] [rbp+8h]
  void **v70; // [rsp+110h] [rbp+10h]
  __int64 v71; // [rsp+118h] [rbp+18h]
  __int64 v72; // [rsp+120h] [rbp+20h]
  void **v73; // [rsp+128h] [rbp+28h]
  __int64 v74; // [rsp+130h] [rbp+30h]
  __int64 v75; // [rsp+138h] [rbp+38h]
  PSID *p_pSid; // [rsp+140h] [rbp+40h] BYREF
  PSID Sid; // [rsp+148h] [rbp+48h] BYREF
  char v78; // [rsp+150h] [rbp+50h]
  void **v79; // [rsp+160h] [rbp+60h] BYREF
  int v80; // [rsp+168h] [rbp+68h]
  void **v81; // [rsp+170h] [rbp+70h]
  __int64 v82; // [rsp+178h] [rbp+78h]
  __int64 v83; // [rsp+180h] [rbp+80h]
  void **v84; // [rsp+188h] [rbp+88h]
  __int64 v85; // [rsp+190h] [rbp+90h]
  __int64 v86; // [rsp+198h] [rbp+98h]
  void **v87; // [rsp+1A0h] [rbp+A0h] BYREF
  int v88; // [rsp+1A8h] [rbp+A8h]
  void **v89; // [rsp+1B0h] [rbp+B0h]
  __int64 v90; // [rsp+1B8h] [rbp+B8h]
  __int64 v91; // [rsp+1C0h] [rbp+C0h]
  void **v92; // [rsp+1C8h] [rbp+C8h]
  __int64 v93; // [rsp+1D0h] [rbp+D0h]
  __int64 v94; // [rsp+1D8h] [rbp+D8h]
  __int128 v95; // [rsp+1E0h] [rbp+E0h] BYREF
  _OWORD v96[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v97[3]; // [rsp+210h] [rbp+110h] BYREF
  char v98[40]; // [rsp+240h] [rbp+140h] BYREF

  v48 = 0;
  strcpy(v98, "CNgcReader::InitializeReaderInformation");
  v59[0] = v98;
  v59[1] = &v48;
  lambda_4caac312490eee3d9b8c6297e37ead8e_::operator()(v59);
  v48 = 1;
  v58 = v59;
  v46 = &Microsoft::WRL::Wrappers::HandleT<DeviceInfoListHandleTraits>::`vftable';
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( !DeviceInfoList )
  {
    LastError = GetLastError();
    CalaisError(v3, 0x263u, LastError, 0, 0, 0);
    pExceptionObject = LastError;
    throw &pExceptionObject;
  }
  v87 = &CTextString::`vftable';
  v89 = &CBuffer::`vftable';
  v90 = 0;
  v91 = 0;
  v92 = &CBuffer::`vftable';
  v93 = 0;
  v94 = 0;
  v88 = 3;
  v4 = (*(__int64 (__fastcall **)(CNgcReader *))(*(_QWORD *)this + 40LL))(this);
  CTextString::operator=(&v87, v4);
  memset(v96, 0, sizeof(v96));
  LODWORD(v96[0]) = 32;
  v5 = CTextString::Unicode((CTextString *)&v87);
  if ( !(unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, v5, 0, v96) )
  {
    v6 = GetLastError();
    CalaisError(v7, 0x263u, v6, 0, 0, 0);
    pExceptionObject = v6;
    throw &pExceptionObject;
  }
  memset(v97, 0, sizeof(v97));
  LODWORD(v97[0]) = 48;
  if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v96, 0, 0, 0, v97) )
  {
    v8 = GetLastError();
    v10 = v8;
    if ( v8 != 122 )
    {
      CalaisError(v9, 0x263u, v8, 0, 0, 0);
      pExceptionObject = v10;
      throw &pExceptionObject;
    }
  }
  v44 = 0;
  if ( !(unsigned int)DevObjGetDeviceInstanceId(DeviceInfoList, v97, 0, 0, &v44) )
  {
    v11 = GetLastError();
    v13 = v11;
    if ( v11 != 122 )
    {
      CalaisError(v12, 0x263u, v11, 0, 0, 0);
      pExceptionObject = v13;
      throw &pExceptionObject;
    }
  }
  CBuffer::CBuffer((CBuffer *)v51, 2 * v44);
  v14 = (WCHAR *)&Data;
  v15 = &Data;
  if ( v54 )
    v15 = (const WCHAR *)Block;
  if ( !(unsigned int)DevObjGetDeviceInstanceId(DeviceInfoList, v97, v15, v54, &v44) )
  {
    v16 = GetLastError();
    CalaisError(v17, 0x263u, v16, 0, 0, 0);
    pExceptionObject = v16;
    throw &pExceptionObject;
  }
  v18 = v44;
  CBuffer::Presize((CBuffer *)v51, v44, 0);
  v53 = v18;
  v68 = &CTextString::`vftable';
  v70 = &CBuffer::`vftable';
  v71 = 0;
  v72 = 0;
  v73 = &CBuffer::`vftable';
  v74 = 0;
  v75 = 0;
  v69 = 3;
  v19 = &Data;
  if ( v54 )
    v19 = (const WCHAR *)Block;
  CTextString::operator=(&v68, v19);
  v49 = 0;
  v95 = 0;
  v50 = 0;
  if ( !(unsigned int)DevObjGetDeviceInterfaceProperty(
                        DeviceInfoList,
                        v96,
                        DEVPKEY_Device_NgcContainerId,
                        &v49,
                        &v95,
                        16,
                        &v50,
                        0) )
  {
    v21 = GetLastError();
    CalaisError(v22, 0x263u, v21, 0, 0, 0);
    pExceptionObject = v21;
    throw &pExceptionObject;
  }
  if ( v49 != 13 || v50 != 16 )
  {
    CalaisError(v20, 0x263u, 13, 0, 0, 0);
    pExceptionObject = 13;
    throw &pExceptionObject;
  }
  v60 = &CTextString::`vftable';
  v62 = &CBuffer::`vftable';
  v63 = 0;
  v64 = 0;
  v65 = &CBuffer::`vftable';
  v66 = 0;
  v67 = 0;
  v61 = 3;
  DevicePropertyString = CNgcReader::GetDevicePropertyString(
                           DeviceInfoList,
                           (struct _DO_DEVINFO_DATA *)v97,
                           &DEVPKEY_Device_NgcContainerName,
                           (struct CTextString *)&v60);
  v25 = DevicePropertyString;
  if ( DevicePropertyString )
  {
    CalaisError(v24, 0x263u, DevicePropertyString, 0, 0, 0);
    pExceptionObject = v25;
    throw &pExceptionObject;
  }
  v79 = &CTextString::`vftable';
  v81 = &CBuffer::`vftable';
  v82 = 0;
  v83 = 0;
  v84 = &CBuffer::`vftable';
  v85 = 0;
  v86 = 0;
  v80 = 3;
  v55 = &CBuffer::`vftable';
  v26 = 0;
  pDestinationSid = 0;
  LengthSid = 0;
  v57 = 0;
  v28 = CNgcReader::GetDevicePropertyString(
          DeviceInfoList,
          (struct _DO_DEVINFO_DATA *)v97,
          &DEVPKEY_Device_NgcOwnerSid,
          (struct CTextString *)&v79);
  v30 = v28;
  if ( v28 != 1168 )
  {
    if ( v28 )
    {
      CalaisError(v29, 0x263u, v28, 0, 0, 0);
      pExceptionObject = v30;
      throw &pExceptionObject;
    }
    pSid = 0;
    p_pSid = &pSid;
    Sid = 0;
    v78 = 1;
    v31 = CTextString::Unicode((CTextString *)&v79);
    v32 = ConvertStringSidToSidW(v31, &Sid);
    wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_pSid);
    if ( !v32 )
    {
      v33 = GetLastError();
      CalaisError(v34, 0x263u, v33, 0, 0, 0);
      pExceptionObject = v33;
      throw &pExceptionObject;
    }
    LengthSid = GetLengthSid(pSid);
    CBuffer::Presize((CBuffer *)&v55, LengthSid, 0);
    LODWORD(v57) = LengthSid;
    v26 = (unsigned __int8 *)pDestinationSid;
    if ( HIDWORD(v57) )
      v14 = (WCHAR *)pDestinationSid;
    if ( !CopySid(LengthSid, v14, pSid) )
    {
      v35 = GetLastError();
      CalaisError(v36, 0x263u, v35, 0, 0, 0);
      pExceptionObject = v35;
      throw &pExceptionObject;
    }
    v37 = pSid;
    pSid = 0;
    if ( v37 )
      LocalFree(v37);
  }
  CLockWrite::CLockWrite((CLockWrite *)&pSid, (CNgcReader *)((char *)this + 56));
  *(_OWORD *)((char *)this + 760) = v95;
  v38 = 2 * CTextString::Length((CTextString *)&v68) + 2;
  v39 = (const unsigned __int8 *)CTextString::Unicode((CTextString *)&v68);
  CBuffer::Set((CNgcReader *)((char *)this + 800), v39, v38);
  v40 = 2 * CTextString::Length((CTextString *)&v60) + 2;
  v41 = (const unsigned __int8 *)CTextString::Unicode((CTextString *)&v60);
  CBuffer::Set((CNgcReader *)((char *)this + 824), v41, v40);
  CBuffer::Set((CNgcReader *)((char *)this + 848), v26, LengthSid);
  CLockWrite::~CLockWrite((CLockWrite *)&pSid);
  if ( v26 )
    operator delete[](v26);
  CTextString::~CTextString((CTextString *)&v79);
  CTextString::~CTextString((CTextString *)&v60);
  CTextString::~CTextString((CTextString *)&v68);
  if ( Block )
    operator delete[](Block);
  CTextString::~CTextString((CTextString *)&v87);
  v46 = &Microsoft::WRL::Wrappers::HandleT<DeviceInfoListHandleTraits>::`vftable';
  if ( DeviceInfoList )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<DeviceInfoListHandleTraits>::InternalClose(&v46) )
    {
      v42 = GetLastError();
      if ( v42 > 0 )
        v42 = (unsigned __int16)v42 | 0x80070000;
      RaiseException(v42, 1u, 0, 0);
      __debugbreak();
    }
    DeviceInfoList = 0;
  }
  WppTraceUnwinder__lambda_4caac312490eee3d9b8c6297e37ead8e____::_WppTraceUnwinder__lambda_4caac312490eee3d9b8c6297e37ead8e____(&v58);
}

```

## disassembly

```asm
0x18001a748  mov     [rsp-8+arg_8], rbx
0x18001a74d  mov     [rsp-8+arg_10], rsi
0x18001a752  push    rbp
0x18001a753  push    rdi
0x18001a754  push    r12
0x18001a756  push    r13
0x18001a758  push    r14
0x18001a75a  lea     rbp, [rsp-170h]
0x18001a762  sub     rsp, 270h
0x18001a769  mov     rax, cs:__security_cookie
0x18001a770  xor     rax, rsp
0x18001a773  mov     [rbp+190h+var_28], rax
0x18001a77a  mov     r12, rcx
0x18001a77d  xor     r13d, r13d
0x18001a780  mov     [rsp+290h+var_230], r13d
0x18001a785  movups  xmm0, xmmword ptr cs:aCngcreaderInit_1; "CNgcReader::InitializeReaderInformation"
0x18001a78c  movups  xmmword ptr [rbp+190h+var_50], xmm0
0x18001a793  movups  xmm1, xmmword ptr cs:aCngcreaderInit_1+10h; "ializeReaderInformation"
0x18001a79a  movups  xmmword ptr [rbp+190h+var_50+10h], xmm1
0x18001a7a1  movsd   xmm0, qword ptr cs:aCngcreaderInit_1+20h; "rmation"
0x18001a7a9  movsd   qword ptr [rbp+190h+var_50+20h], xmm0
0x18001a7b1  lea     rax, [rbp+190h+var_50]
0x18001a7b8  mov     [rbp+190h+var_1E8], rax
0x18001a7bc  lea     rax, [rsp+290h+var_230]
0x18001a7c1  mov     [rbp+190h+var_1E0], rax
0x18001a7c5  lea     rcx, [rbp+190h+var_1E8]
0x18001a7c9  call    _lambda_4caac312490eee3d9b8c6297e37ead8e___operator__
0x18001a7ce  mov     [rsp+290h+var_230], 1
0x18001a7d6  lea     rax, [rbp+190h+var_1E8]
0x18001a7da  mov     [rbp+190h+var_1F0], rax
0x18001a7de  mov     [rsp+290h+var_270], r13
0x18001a7e3  xor     r9d, r9d
0x18001a7e6  xor     r8d, r8d
0x18001a7e9  xor     edx, edx
0x18001a7eb  xor     ecx, ecx
0x18001a7ed  call    cs:__imp_DevObjCreateDeviceInfoList
0x18001a7f3  lea     rcx, ??_7?$HandleT@UDeviceInfoListHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<DeviceInfoListHandleTraits>::`vftable'
0x18001a7fa  mov     [rsp+290h+var_240], rcx
0x18001a7ff  mov     [rsp+290h+var_238], rax
0x18001a804  test    rax, rax
0x18001a807  jnz     short loc_18001A841
0x18001a809  call    cs:__imp_GetLastError
0x18001a80f  mov     ebx, eax
0x18001a811  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001a816  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001a81b  xor     r9d, r9d; unsigned __int16 *
0x18001a81e  mov     r8d, eax; unsigned int
0x18001a821  mov     edx, 263h; unsigned int
0x18001a826  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001a82b  mov     [rsp+290h+pExceptionObject], ebx
0x18001a82f  lea     rdx, _TI1K; pThrowInfo
0x18001a836  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001a83b  call    _CxxThrowException_0
0x18001a841  lea     rsi, ??_7CTextString@@6B@; const CTextString::`vftable'
0x18001a848  mov     [rbp+190h+var_F0], rsi
0x18001a84f  lea     rdi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001a856  mov     [rbp+190h+var_E0], rdi
0x18001a85d  mov     [rbp+190h+var_D8], r13
0x18001a864  mov     [rbp+190h+var_D0], r13
0x18001a86b  mov     [rbp+190h+var_C8], rdi
0x18001a872  mov     [rbp+190h+var_C0], r13
0x18001a879  mov     [rbp+190h+var_B8], r13
0x18001a880  mov     [rbp+190h+var_E8], 3
0x18001a88a  mov     rax, [r12]
0x18001a88e  mov     rcx, r12
0x18001a891  mov     rax, [rax+28h]
0x18001a895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a89a  mov     rdx, rax
0x18001a89d  lea     rcx, [rbp+190h+var_F0]
0x18001a8a4  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18001a8a9  xorps   xmm0, xmm0
0x18001a8ac  movups  [rbp+190h+var_A0], xmm0
0x18001a8b3  movups  [rbp+190h+var_90], xmm0
0x18001a8ba  mov     dword ptr [rbp+190h+var_A0], 20h ; ' '
0x18001a8c4  lea     rcx, [rbp+190h+var_F0]; this
0x18001a8cb  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18001a8d0  lea     r9, [rbp+190h+var_A0]
0x18001a8d7  xor     r8d, r8d
0x18001a8da  mov     rdx, rax
0x18001a8dd  mov     rcx, [rsp+290h+var_238]
0x18001a8e2  call    cs:__imp_DevObjOpenDeviceInterface
0x18001a8e8  test    eax, eax
0x18001a8ea  jnz     short loc_18001A924
0x18001a8ec  call    cs:__imp_GetLastError
0x18001a8f2  mov     ebx, eax
0x18001a8f4  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001a8f9  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001a8fe  xor     r9d, r9d; unsigned __int16 *
0x18001a901  mov     r8d, eax; unsigned int
0x18001a904  mov     edx, 263h; unsigned int
0x18001a909  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001a90e  mov     [rsp+290h+pExceptionObject], ebx
0x18001a912  lea     rdx, _TI1K; pThrowInfo
0x18001a919  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001a91e  call    _CxxThrowException_0
0x18001a924  xorps   xmm0, xmm0
0x18001a927  movups  [rbp+190h+var_80], xmm0
0x18001a92e  movups  [rbp+190h+var_70], xmm0
0x18001a935  movups  [rbp+190h+var_60], xmm0
0x18001a93c  mov     dword ptr [rbp+190h+var_80], 30h ; '0'
0x18001a946  lea     rax, [rbp+190h+var_80]
0x18001a94d  mov     [rsp+290h+var_268], rax
0x18001a952  mov     [rsp+290h+var_270], r13
0x18001a957  xor     r9d, r9d
0x18001a95a  xor     r8d, r8d
0x18001a95d  lea     rdx, [rbp+190h+var_A0]
0x18001a964  mov     rcx, [rsp+290h+var_238]
0x18001a969  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18001a96f  test    eax, eax
0x18001a971  jnz     short loc_18001A9B0
0x18001a973  call    cs:__imp_GetLastError
0x18001a979  mov     ebx, eax
0x18001a97b  cmp     eax, 7Ah ; 'z'
0x18001a97e  jz      short loc_18001A9B0
0x18001a980  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001a985  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001a98a  xor     r9d, r9d; unsigned __int16 *
0x18001a98d  mov     r8d, eax; unsigned int
0x18001a990  mov     edx, 263h; unsigned int
0x18001a995  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001a99a  mov     [rsp+290h+pExceptionObject], ebx
0x18001a99e  lea     rdx, _TI1K; pThrowInfo
0x18001a9a5  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001a9aa  call    _CxxThrowException_0
0x18001a9b0  mov     [rsp+290h+var_24C], r13d
0x18001a9b5  lea     rax, [rsp+290h+var_24C]
0x18001a9ba  mov     [rsp+290h+var_270], rax
0x18001a9bf  xor     r9d, r9d
0x18001a9c2  xor     r8d, r8d
0x18001a9c5  lea     rdx, [rbp+190h+var_80]
0x18001a9cc  mov     rcx, [rsp+290h+var_238]
0x18001a9d1  call    cs:__imp_DevObjGetDeviceInstanceId
0x18001a9d7  test    eax, eax
0x18001a9d9  jnz     short loc_18001AA18
0x18001a9db  call    cs:__imp_GetLastError
0x18001a9e1  mov     ebx, eax
0x18001a9e3  cmp     eax, 7Ah ; 'z'
0x18001a9e6  jz      short loc_18001AA18
0x18001a9e8  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001a9ed  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001a9f2  xor     r9d, r9d; unsigned __int16 *
0x18001a9f5  mov     r8d, eax; unsigned int
0x18001a9f8  mov     edx, 263h; unsigned int
0x18001a9fd  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001aa02  mov     [rsp+290h+pExceptionObject], ebx
0x18001aa06  lea     rdx, _TI1K; pThrowInfo
0x18001aa0d  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001aa12  call    _CxxThrowException_0
0x18001aa18  mov     edx, [rsp+290h+var_24C]
0x18001aa1c  add     edx, edx; unsigned int
0x18001aa1e  lea     rcx, [rsp+290h+var_220]; this
0x18001aa23  call    ??0CBuffer@@QEAA@K@Z; CBuffer::CBuffer(ulong)
0x18001aa28  nop
0x18001aa29  mov     r9d, [rbp+190h+var_20C]
0x18001aa2d  lea     r14, Data
0x18001aa34  mov     r8, r14
0x18001aa37  test    r9d, r9d
0x18001aa3a  cmovnz  r8, [rsp+290h+Block]
0x18001aa40  lea     rax, [rsp+290h+var_24C]
0x18001aa45  mov     [rsp+290h+var_270], rax
0x18001aa4a  lea     rdx, [rbp+190h+var_80]
0x18001aa51  mov     rcx, [rsp+290h+var_238]
0x18001aa56  call    cs:__imp_DevObjGetDeviceInstanceId
0x18001aa5c  test    eax, eax
0x18001aa5e  jnz     short loc_18001AA98
0x18001aa60  call    cs:__imp_GetLastError
0x18001aa66  mov     ebx, eax
0x18001aa68  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001aa6d  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001aa72  xor     r9d, r9d; unsigned __int16 *
0x18001aa75  mov     r8d, eax; unsigned int
0x18001aa78  mov     edx, 263h; unsigned int
0x18001aa7d  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001aa82  mov     [rsp+290h+pExceptionObject], ebx
0x18001aa86  lea     rdx, _TI1K; pThrowInfo
0x18001aa8d  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001aa92  call    _CxxThrowException_0
0x18001aa98  mov     ebx, [rsp+290h+var_24C]
0x18001aa9c  xor     r8d, r8d; int
0x18001aa9f  mov     edx, ebx; unsigned int
0x18001aaa1  lea     rcx, [rsp+290h+var_220]; this
0x18001aaa6  call    ?Presize@CBuffer@@QEAAPEAEKH@Z; CBuffer::Presize(ulong,int)
0x18001aaab  mov     [rbp+190h+var_210], ebx
0x18001aaae  mov     [rbp+190h+var_190], rsi
0x18001aab2  mov     [rbp+190h+var_180], rdi
0x18001aab6  mov     [rbp+190h+var_178], r13
0x18001aaba  mov     [rbp+190h+var_170], r13
0x18001aabe  mov     [rbp+190h+var_168], rdi
0x18001aac2  mov     [rbp+190h+var_160], r13
0x18001aac6  mov     [rbp+190h+var_158], r13
0x18001aaca  mov     [rbp+190h+var_188], 3
0x18001aad1  mov     rdx, r14
0x18001aad4  cmp     [rbp+190h+var_20C], r13d
0x18001aad8  cmova   rdx, [rsp+290h+Block]
0x18001aade  lea     rcx, [rbp+190h+var_190]
0x18001aae2  call    ??4CTextString@@QEAAPEBGPEBG@Z; CTextString::operator=(ushort const *)
0x18001aae7  mov     [rsp+290h+var_22C], r13d
0x18001aaec  xorps   xmm0, xmm0
0x18001aaef  movups  [rbp+190h+var_B0], xmm0
0x18001aaf6  mov     [rsp+290h+var_228], r13d
0x18001aafb  mov     [rsp+290h+var_258], r13d
0x18001ab00  lea     rax, [rsp+290h+var_228]
0x18001ab05  mov     [rsp+290h+var_260], rax
0x18001ab0a  mov     dword ptr [rsp+290h+var_268], 10h
0x18001ab12  lea     rax, [rbp+190h+var_B0]
0x18001ab19  mov     [rsp+290h+var_270], rax
0x18001ab1e  lea     r9, [rsp+290h+var_22C]
0x18001ab23  lea     r8, DEVPKEY_Device_NgcContainerId
0x18001ab2a  lea     rdx, [rbp+190h+var_A0]
0x18001ab31  mov     rcx, [rsp+290h+var_238]
0x18001ab36  call    cs:__imp_DevObjGetDeviceInterfaceProperty
0x18001ab3c  test    eax, eax
0x18001ab3e  jnz     short loc_18001AB78
0x18001ab40  call    cs:__imp_GetLastError
0x18001ab46  mov     ebx, eax
0x18001ab48  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001ab4d  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001ab52  xor     r9d, r9d; unsigned __int16 *
0x18001ab55  mov     r8d, eax; unsigned int
0x18001ab58  mov     edx, 263h; unsigned int
0x18001ab5d  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001ab62  mov     [rsp+290h+pExceptionObject], ebx
0x18001ab66  lea     rdx, _TI1K; pThrowInfo
0x18001ab6d  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001ab72  call    _CxxThrowException_0
0x18001ab78  mov     ebx, 0Dh
0x18001ab7d  cmp     [rsp+290h+var_22C], ebx
0x18001ab81  jnz     loc_18001AF05
0x18001ab87  cmp     [rsp+290h+var_228], 10h
0x18001ab8c  jnz     loc_18001AF05
0x18001ab92  mov     [rbp+190h+var_1D0], rsi
0x18001ab96  mov     [rbp+190h+var_1C0], rdi
0x18001ab9a  mov     [rbp+190h+var_1B8], r13
0x18001ab9e  mov     [rbp+190h+var_1B0], r13
0x18001aba2  mov     [rbp+190h+var_1A8], rdi
0x18001aba6  mov     [rbp+190h+var_1A0], r13
0x18001abaa  mov     [rbp+190h+var_198], r13
0x18001abae  mov     [rbp+190h+var_1C8], 3
0x18001abb5  lea     r9, [rbp+190h+var_1D0]; struct CTextString *
0x18001abb9  lea     r8, DEVPKEY_Device_NgcContainerName; struct _DEVPROPKEY *
0x18001abc0  lea     rdx, [rbp+190h+var_80]; struct _DO_DEVINFO_DATA *
0x18001abc7  mov     rcx, [rsp+290h+var_238]; void *
0x18001abcc  call    ?GetDevicePropertyString@CNgcReader@@KAKPEAXPEAU_DO_DEVINFO_DATA@@PEBU_DEVPROPKEY@@PEAVCTextString@@@Z; CNgcReader::GetDevicePropertyString(void *,_DO_DEVINFO_DATA *,_DEVPROPKEY const *,CTextString *)
0x18001abd1  mov     ebx, eax
0x18001abd3  test    eax, eax
0x18001abd5  jz      short loc_18001AC07
0x18001abd7  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001abdc  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001abe1  xor     r9d, r9d; unsigned __int16 *
0x18001abe4  mov     r8d, eax; unsigned int
0x18001abe7  mov     edx, 263h; unsigned int
0x18001abec  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001abf1  mov     [rsp+290h+pExceptionObject], ebx
0x18001abf5  lea     rdx, _TI1K; pThrowInfo
0x18001abfc  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001ac01  call    _CxxThrowException_0
0x18001ac07  mov     [rbp+190h+var_130], rsi
0x18001ac0b  mov     [rbp+190h+var_120], rdi
0x18001ac0f  mov     [rbp+190h+var_118], r13
0x18001ac13  mov     [rbp+190h+var_110], r13
0x18001ac1a  mov     [rbp+190h+var_108], rdi
0x18001ac21  mov     [rbp+190h+var_100], r13
0x18001ac28  mov     [rbp+190h+var_F8], r13
0x18001ac2f  mov     [rbp+190h+var_128], 3
0x18001ac36  mov     [rbp+190h+var_208], rdi
0x18001ac3a  mov     rdi, r13
0x18001ac3d  mov     [rbp+190h+pDestinationSid], r13
0x18001ac41  mov     esi, r13d
0x18001ac44  mov     [rbp+190h+var_1F8], r13
0x18001ac48  lea     r9, [rbp+190h+var_130]; struct CTextString *
0x18001ac4c  lea     r8, DEVPKEY_Device_NgcOwnerSid; struct _DEVPROPKEY *
0x18001ac53  lea     rdx, [rbp+190h+var_80]; struct _DO_DEVINFO_DATA *
0x18001ac5a  mov     rcx, [rsp+290h+var_238]; void *
0x18001ac5f  call    ?GetDevicePropertyString@CNgcReader@@KAKPEAXPEAU_DO_DEVINFO_DATA@@PEBU_DEVPROPKEY@@PEAVCTextString@@@Z; CNgcReader::GetDevicePropertyString(void *,_DO_DEVINFO_DATA *,_DEVPROPKEY const *,CTextString *)
0x18001ac64  mov     ebx, eax
0x18001ac66  cmp     eax, 490h
0x18001ac6b  jz      loc_18001ADA3
0x18001ac71  test    eax, eax
0x18001ac73  jz      short loc_18001ACA5
0x18001ac75  mov     [rsp+290h+var_268], r13; unsigned __int16 *
0x18001ac7a  mov     [rsp+290h+var_270], r13; unsigned __int16 *
0x18001ac7f  xor     r9d, r9d; unsigned __int16 *
0x18001ac82  mov     r8d, eax; unsigned int
0x18001ac85  mov     edx, 263h; unsigned int
0x18001ac8a  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001ac8f  mov     [rsp+290h+pExceptionObject], ebx
0x18001ac93  lea     rdx, _TI1K; pThrowInfo
0x18001ac9a  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x18001ac9f  call    _CxxThrowException_0
0x18001aca5  mov     [rsp+290h+pSid], r13
0x18001acaa  lea     rax, [rsp+290h+pSid]
0x18001acaf  mov     [rbp+190h+var_150], rax
0x18001acb3  mov     [rbp+190h+Sid], r13
0x18001acb7  mov     [rbp+190h+var_140], 1
0x18001acbb  lea     rcx, [rbp+190h+var_130]; this
0x18001acbf  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18001acc4  lea     rdx, [rbp+190h+Sid]; Sid
0x18001acc8  mov     rcx, rax; StringSid
0x18001accb  call    cs:__imp_ConvertStringSidToSidW
0x18001acd1  mov     ebx, eax
  ... truncated ...
```
