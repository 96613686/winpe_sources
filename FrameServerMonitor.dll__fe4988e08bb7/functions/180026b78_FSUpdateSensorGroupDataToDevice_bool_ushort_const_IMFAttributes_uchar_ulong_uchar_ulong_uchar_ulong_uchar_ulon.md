# FSUpdateSensorGroupDataToDevice(bool,ushort const *,IMFAttributes *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,ulong,FSMFileTime const &,FSMFileTime const &)

- ea: `0x180026b78`
- end: `0x1800272f1`
- name: `?FSUpdateSensorGroupDataToDevice@@YAJ_NPEBGPEAUIMFAttributes@@PEAEK3K3K3KKAEBUFSMFileTime@@4@Z`
- size: `1913`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, struct IMFAttributes *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, signed int, unsigned __int8 *, ULONG, unsigned int, const struct FSMFileTime *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, installer_update`

## callers

- `0x180013274`
- `0x18002257c`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180004f34`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000cadc`
- `0x18000d1e0`
- `0x18000d3d8`
- `0x18000d498`
- `0x18000e4e8`
- `0x180026b78`
- `0x1800272f8`
- `0x180027804`
- `0x180027858`
- `0x18002fa3c`
- `0x18002fa70`
- `0x18003f908`
- `0x1800426d8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180026e36`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180026e36`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180026e61`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180026e61`
- `MFPlat!MFGetAttributesAsBlob` at `0x180026ed7`
- `MFPlat!MFGetAttributesAsBlob` at `0x180026ed7`

## pseudocode

```c
__int64 __fastcall FSUpdateSensorGroupDataToDevice(
        __int64 a1,
        unsigned __int16 *a2,
        struct IMFAttributes *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        signed int a9,
        unsigned __int8 *a10,
        ULONG a11,
        unsigned int a12,
        const struct FSMFileTime *a13,
        struct _FILETIME *a14)
{
  char v14; // bl
  const struct std::nothrow_t *v18; // rdx
  FileTimeTrace *v19; // rax
  const char *String; // rbx
  FileTimeTrace *v21; // rax
  int v22; // edi
  int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  const struct std::nothrow_t *unique; // rax
  unsigned __int8 *v30; // rbx
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  unsigned __int8 *v33; // r15
  unsigned __int8 *v34; // r12
  bool v35; // cl
  unsigned __int8 Level; // al
  __int64 v37; // rdx
  unsigned int v39; // [rsp+28h] [rbp-D8h]
  int v40; // [rsp+30h] [rbp-D0h]
  const char *v41; // [rsp+38h] [rbp-C8h]
  UINT32 pcbBufSize; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  UINT8 *pBuf; // [rsp+78h] [rbp-88h] BYREF
  IMFAttributes *pAttributes; // [rsp+80h] [rbp-80h]
  unsigned __int8 *v47; // [rsp+88h] [rbp-78h]
  struct _FILETIME *v48; // [rsp+90h] [rbp-70h]
  __int64 v49; // [rsp+98h] [rbp-68h] BYREF
  struct FSMFileTime *v50; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v51; // [rsp+A8h] [rbp-58h] BYREF
  void **v52; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v53[24]; // [rsp+B8h] [rbp-48h] BYREF
  void **v54; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v55[24]; // [rsp+D8h] [rbp-28h] BYREF
  struct _DEVPROPKEY v56; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int8 v57[4]; // [rsp+110h] [rbp+10h] BYREF
  int v58; // [rsp+114h] [rbp+14h]
  __int128 v59; // [rsp+118h] [rbp+18h]
  __int128 v60; // [rsp+128h] [rbp+28h]
  __int128 v61; // [rsp+138h] [rbp+38h]
  __int128 v62; // [rsp+148h] [rbp+48h]
  __int64 v63; // [rsp+158h] [rbp+58h]
  UINT32 v64; // [rsp+160h] [rbp+60h]
  int v65; // [rsp+164h] [rbp+64h]
  signed int v66; // [rsp+168h] [rbp+68h]
  int v67; // [rsp+16Ch] [rbp+6Ch]
  unsigned __int16 v68[72]; // [rsp+170h] [rbp+70h] BYREF

  v14 = 0;
  v48 = a14;
  pAttributes = a3;
  v51 = a2;
  v50 = a13;
  v47 = a10;
  memset_0(v57, 0, 0x60u);
  v56.pid = 3;
  v43 = 0;
  pcbBufSize = 0;
  pBuf = 0;
  v56.fmtid = (DEVPROPGUID)SensorGroupFMTGUID;
  v44 = 0;
  memset_0(v68, 0, 0x82u);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v19 = FileTimeTrace::FileTimeTrace((FileTimeTrace *)&v54, v48);
    String = FSString::GetString((FileTimeTrace *)((char *)v19 + 8));
    v21 = FileTimeTrace::FileTimeTrace((FileTimeTrace *)&v52, (const struct _FILETIME *)a13);
    v41 = FSString::GetString((FileTimeTrace *)((char *)v21 + 8));
    WPP_SF_Sqqdss(*((_QWORD *)WPP_GLOBAL_Control + 27), (char)a3, (char)a4, v40, (__int64)v41, (__int64)String);
    v14 = 3;
  }
  if ( (v14 & 2) != 0 )
  {
    v14 &= ~2u;
    v52 = &SensorGroupBlobHeaderTrace::`vftable';
    FSString::~FSString((FSString *)v53, v18);
  }
  if ( (v14 & 1) != 0 )
  {
    v54 = &SensorGroupBlobHeaderTrace::`vftable';
    FSString::~FSString((FSString *)v55, v18);
  }
  if ( !a2 )
  {
    v22 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v24 = 27;
    goto LABEL_82;
  }
  if ( !a3 )
  {
    v22 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v24 = 28;
    goto LABEL_82;
  }
  if ( !a4 )
  {
    v22 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v24 = 29;
    goto LABEL_82;
  }
  v22 = FSConvertBinaryToHexString(a4, 0x20u, v68, 0x41u, 0);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 31;
    goto LABEL_19;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 32, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, v68);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 27), 33, v26, 32, a6);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 27), 34, v27, (unsigned int)a9, a8);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 27), 35, v28, a11, v47);
  GetSystemTimePreciseAsFileTime(&v44);
  if ( (unsigned int)(a9 - 584) > 0x7FFFFDB6 || *((_DWORD *)a8 + 4) > a9 )
  {
    v22 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v24 = 36;
LABEL_82:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, 0, v23);
LABEL_83:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v37 = 51;
      goto LABEL_85;
    }
    goto LABEL_86;
  }
  v22 = MFGetAttributesAsBlobSize(pAttributes, &pcbBufSize);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 37;
    goto LABEL_19;
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v49, pcbBufSize);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&pBuf, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v49);
  v30 = pBuf;
  if ( !pBuf )
  {
    v22 = -2147024882;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 38;
    goto LABEL_19;
  }
  v22 = MFGetAttributesAsBlob(pAttributes, pBuf, pcbBufSize);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 39;
    goto LABEL_19;
  }
  v31 = *(_OWORD *)a4;
  v32 = *((_OWORD *)a4 + 1);
  *(_DWORD *)v57 = 1;
  v65 = 1;
  v58 = 96;
  v63 = 0;
  v59 = v31;
  v64 = pcbBufSize;
  v60 = v32;
  v66 = a9;
  v61 = v31;
  v67 = 0;
  v62 = v32;
  v22 = FSSetDeviceInterfaceProperty(a2, &v56, 0x1003u, v57, 0x60u);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 40;
    goto LABEL_19;
  }
  v22 = StringCchLengthW(a2, 0x7FFFFFFFu, &v43);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 41;
    goto LABEL_19;
  }
  v56.pid = 4;
  v22 = FSSetDeviceInterfaceProperty(a2, &v56, 0x12u, (unsigned __int8 *const)a2, 2 * (int)v43 + 2);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 42;
    goto LABEL_19;
  }
  v56.pid = 5;
  v22 = FSSetDeviceInterfaceProperty(a2, &v56, 0x1003u, v30, pcbBufSize);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 43;
    goto LABEL_19;
  }
  v56.pid = 6;
  memset_0(a8 + 32, 0, 0x208u);
  v22 = StringCchCopyW((unsigned __int16 *)a8 + 16, 0x104u, a2);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 44;
    goto LABEL_19;
  }
  *((_DWORD *)a8 + 7) = v43;
  *(_OWORD *)(a8 + 552) = *(_OWORD *)a4;
  *(_OWORD *)(a8 + 568) = *((_OWORD *)a4 + 1);
  v22 = FSSetDeviceInterfaceProperty(a2, &v56, 0x1003u, a8, a9);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 45;
    goto LABEL_19;
  }
  if ( a11 )
  {
    if ( !v47 )
    {
      v22 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v24 = 46;
      goto LABEL_82;
    }
    v56.pid = 9;
    v22 = FSSetDeviceInterfaceProperty(a2, &v56, 0x1003u, v47, a11);
    if ( v22 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_83;
      v25 = 47;
      goto LABEL_19;
    }
  }
  v33 = (unsigned __int8 *)&v44;
  v34 = (unsigned __int8 *)&v44;
  v56.pid = 17;
  if ( *(_QWORD *)v50 )
    v33 = (unsigned __int8 *)v50;
  if ( *v48 )
    v34 = (unsigned __int8 *)v48;
  v22 = FSSetDeviceInterfaceProperty(a2, &v56, 0x10u, v34, 8u);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 48;
    goto LABEL_19;
  }
  v56.pid = 18;
  v22 = FSSetDeviceInterfaceProperty(a2, &v56, 0x10u, v33, 8u);
  if ( v22 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_83;
    v25 = 49;
LABEL_19:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, 0, v22);
    goto LABEL_83;
  }
  v22 = FSUpdateSensorGroupDataToRegistry(
          v35,
          v68,
          a2,
          (const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003 *)v57,
          (const unsigned __int16 **)&v51,
          v39,
          v30,
          pcbBufSize,
          a8,
          a9,
          (const struct FSMFileTime *)v33,
          (const struct FSMFileTime *)v34);
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v22 < 0 )
  {
    if ( Level )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        50,
        &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids,
        (unsigned int)v22);
    v22 = 0;
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  }
  if ( Level >= 8u )
  {
    v37 = 52;
LABEL_85:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v37,
      &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids,
      (unsigned int)v22);
  }
LABEL_86:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180026b78  mov     [rsp-8+arg_0], rbx
0x180026b7d  push    rbp
0x180026b7e  push    rsi
0x180026b7f  push    rdi
0x180026b80  push    r12
0x180026b82  push    r13
0x180026b84  push    r14
0x180026b86  push    r15
0x180026b88  lea     rbp, [rsp-110h]
0x180026b90  sub     rsp, 210h
0x180026b97  mov     rax, cs:__security_cookie
0x180026b9e  xor     rax, rsp
0x180026ba1  mov     [rbp+140h+var_40], rax
0x180026ba8  mov     rax, [rbp+140h+arg_68]
0x180026baf  lea     rcx, [rbp+140h+var_130]; void *
0x180026bb3  mov     r12, [rbp+140h+arg_60]
0x180026bba  xor     ebx, ebx
0x180026bbc  mov     r14, [rbp+140h+arg_28]
0x180026bc3  mov     rdi, r8
0x180026bc6  mov     r13, [rbp+140h+arg_38]
0x180026bcd  mov     rsi, rdx
0x180026bd0  mov     [rbp+140h+var_1B0], rax
0x180026bd4  mov     r15, r9
0x180026bd7  mov     rax, [rbp+140h+arg_48]
0x180026bde  mov     [rbp+140h+pAttributes], r8
0x180026be2  lea     r8d, [rbx+60h]; Size
0x180026be6  mov     [rbp+140h+var_198], rdx
0x180026bea  xor     edx, edx; Val
0x180026bec  mov     [rbp+140h+var_1A0], r12
0x180026bf0  mov     [rbp+140h+var_1B8], rax
0x180026bf4  mov     [rsp+240h+pcbBufSize], ebx
0x180026bf8  call    memset_0
0x180026bfd  movups  xmm0, cs:SensorGroupFMTGUID
0x180026c04  xor     eax, eax
0x180026c06  mov     [rbp+140h+var_150.pid], 3
0x180026c0d  xor     edx, edx; Val
0x180026c0f  mov     [rsp+240h+var_1D8], rax
0x180026c14  mov     r8d, 82h; Size
0x180026c1a  mov     [rsp+240h+pcbBufSize], eax
0x180026c1e  lea     rcx, [rbp+140h+var_D0]; void *
0x180026c22  mov     [rsp+240h+pBuf], rax
0x180026c27  movdqu  xmmword ptr [rbp+140h+var_150.fmtid.Data1], xmm0
0x180026c2c  mov     [rsp+240h+var_1D0], rax
0x180026c31  call    memset_0
0x180026c36  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180026c3b  cmp     al, 8
0x180026c3d  jb      short loc_180026CA7
0x180026c3f  mov     rdx, [rbp+140h+var_1B0]; struct _FILETIME *
0x180026c43  lea     rcx, [rbp+140h+var_170]; this
0x180026c47  call    ??0FileTimeTrace@@QEAA@PEBU_FILETIME@@@Z; FileTimeTrace::FileTimeTrace(_FILETIME const *)
0x180026c4c  lea     rcx, [rax+8]; this
0x180026c50  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180026c55  lea     rcx, [rbp+140h+var_190]; this
0x180026c59  mov     rdx, r12; struct _FILETIME *
0x180026c5c  mov     rbx, rax
0x180026c5f  call    ??0FileTimeTrace@@QEAA@PEBU_FILETIME@@@Z; FileTimeTrace::FileTimeTrace(_FILETIME const *)
0x180026c64  lea     rcx, [rax+8]; this
0x180026c68  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180026c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c74  lea     r9, aNullptr; "<nullptr>"
0x180026c7b  mov     [rsp+240h+var_200], rbx; __int64
0x180026c80  test    rsi, rsi
0x180026c83  mov     qword ptr [rsp+240h+var_208], rax; __int64
0x180026c88  cmovnz  r9, rsi
0x180026c8c  mov     qword ptr [rsp+240h+var_218], r15; unsigned int
0x180026c91  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180026c98  mov     qword ptr [rsp+240h+var_220], rdi; char
0x180026c9d  call    WPP_SF_Sqqdss
0x180026ca2  mov     ebx, 3
0x180026ca7  lea     r12, ??_7SensorGroupBlobHeaderTrace@@6B@; const SensorGroupBlobHeaderTrace::`vftable'
0x180026cae  test    bl, 2
0x180026cb1  jz      short loc_180026CC3
0x180026cb3  and     ebx, 0FFFFFFFDh
0x180026cb6  mov     [rbp+140h+var_190], r12
0x180026cba  lea     rcx, [rbp+140h+var_188]; this
0x180026cbe  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180026cc3  test    bl, 1
0x180026cc6  jz      short loc_180026CD5
0x180026cc8  lea     rcx, [rbp+140h+var_168]; this
0x180026ccc  mov     [rbp+140h+var_170], r12
0x180026cd0  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180026cd5  test    rsi, rsi
0x180026cd8  jnz     short loc_180026CF6
0x180026cda  mov     ecx, 80070057h
0x180026cdf  mov     edi, ecx
0x180026ce1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026ce6  cmp     al, 1
0x180026ce8  jb      loc_180027290
0x180026cee  lea     edx, [rsi+1Bh]
0x180026cf1  jmp     loc_180027272
0x180026cf6  test    rdi, rdi
0x180026cf9  jnz     short loc_180026D19
0x180026cfb  mov     ecx, 80070057h
0x180026d00  mov     edi, ecx
0x180026d02  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026d07  cmp     al, 1
0x180026d09  jb      loc_180027290
0x180026d0f  mov     edx, 1Ch
0x180026d14  jmp     loc_180027272
0x180026d19  test    r15, r15
0x180026d1c  jnz     short loc_180026D3B
0x180026d1e  mov     ecx, 80070057h
0x180026d23  mov     edi, ecx
0x180026d25  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026d2a  cmp     al, 1
0x180026d2c  jb      loc_180027290
0x180026d32  lea     edx, [r15+1Dh]
0x180026d36  jmp     loc_180027272
0x180026d3b  mov     r9d, 41h ; 'A'; unsigned int
0x180026d41  mov     qword ptr [rsp+240h+var_220], 0; unsigned int *
0x180026d4a  lea     r8, [rbp+140h+var_D0]; unsigned __int16 *
0x180026d4e  mov     rcx, r15; unsigned __int8 *
0x180026d51  lea     ebx, [r9-21h]
0x180026d55  mov     edx, ebx; unsigned int
0x180026d57  call    ?FSConvertBinaryToHexString@@YAJPEAEKPEAGKPEAK@Z; FSConvertBinaryToHexString(uchar *,ulong,ushort *,ulong,ulong *)
0x180026d5c  mov     edi, eax
0x180026d5e  test    eax, eax
0x180026d60  jns     short loc_180026D7B
0x180026d62  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026d67  cmp     al, 1
0x180026d69  jb      loc_180027290
0x180026d6f  lea     edx, [rbx-1]
0x180026d72  mov     [rsp+240h+var_220], edi
0x180026d76  jmp     loc_180027276
0x180026d7b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180026d80  cmp     al, 8
0x180026d82  jb      short loc_180026DA4
0x180026d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d8b  lea     r9, [rbp+140h+var_D0]
0x180026d8f  mov     edx, ebx
0x180026d91  lea     r8, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x180026d98  mov     rcx, [rcx+0D8h]
0x180026d9f  call    WPP_SF_S
0x180026da4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180026da9  cmp     al, 8
0x180026dab  jb      short loc_180026DCD
0x180026dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180026db4  mov     edx, 21h ; '!'
0x180026db9  mov     r9d, ebx
0x180026dbc  mov     qword ptr [rsp+240h+var_220], r14
0x180026dc1  mov     rcx, [rcx+0D8h]
0x180026dc8  call    WPP_SF_Dq
0x180026dcd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180026dd2  mov     r14d, [rbp+140h+arg_40]
0x180026dd9  cmp     al, 8
0x180026ddb  jb      short loc_180026DFD
0x180026ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180026de4  mov     edx, 22h ; '"'
0x180026de9  mov     r9d, r14d
0x180026dec  mov     qword ptr [rsp+240h+var_220], r13
0x180026df1  mov     rcx, [rcx+0D8h]
0x180026df8  call    WPP_SF_Dq
0x180026dfd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180026e02  mov     r12d, [rbp+140h+arg_50]
0x180026e09  cmp     al, 8
0x180026e0b  jb      short loc_180026E31
0x180026e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e14  mov     edx, 23h ; '#'
0x180026e19  mov     rax, [rbp+140h+var_1B8]
0x180026e1d  mov     r9d, r12d
0x180026e20  mov     qword ptr [rsp+240h+var_220], rax
0x180026e25  mov     rcx, [rcx+0D8h]
0x180026e2c  call    WPP_SF_Dq
0x180026e31  lea     rcx, [rsp+240h+var_1D0]
0x180026e36  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180026e3c  lea     eax, [r14-248h]
0x180026e43  cmp     eax, 7FFFFDB6h
0x180026e48  ja      loc_18002725D
0x180026e4e  cmp     [r13+10h], r14d
0x180026e52  jg      loc_18002725D
0x180026e58  mov     rcx, [rbp+140h+pAttributes]; pAttributes
0x180026e5c  lea     rdx, [rsp+240h+pcbBufSize]; pcbBufSize
0x180026e61  call    cs:__imp_MFGetAttributesAsBlobSize
0x180026e67  mov     edi, eax
0x180026e69  test    eax, eax
0x180026e6b  jns     short loc_180026E84
0x180026e6d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026e72  cmp     al, 1
0x180026e74  jb      loc_180027290
0x180026e7a  mov     edx, 25h ; '%'
0x180026e7f  jmp     loc_180026D72
0x180026e84  mov     edx, [rsp+240h+pcbBufSize]
0x180026e88  lea     rcx, [rbp+140h+var_1A8]
0x180026e8c  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180026e91  mov     rdx, rax
0x180026e94  lea     rcx, [rsp+240h+pBuf]
0x180026e99  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180026e9e  lea     rcx, [rbp+140h+var_1A8]
0x180026ea2  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180026ea7  mov     rbx, [rsp+240h+pBuf]
0x180026eac  test    rbx, rbx
0x180026eaf  jnz     short loc_180026ECB
0x180026eb1  mov     edi, 8007000Eh
0x180026eb6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026ebb  cmp     al, 1
0x180026ebd  jb      loc_180027290
0x180026ec3  lea     edx, [rbx+26h]
0x180026ec6  jmp     loc_180026D72
0x180026ecb  mov     r8d, [rsp+240h+pcbBufSize]; cbBufSize
0x180026ed0  mov     rdx, rbx; pBuf
0x180026ed3  mov     rcx, [rbp+140h+pAttributes]; pAttributes
0x180026ed7  call    cs:__imp_MFGetAttributesAsBlob
0x180026edd  mov     edi, eax
0x180026edf  test    eax, eax
0x180026ee1  jns     short loc_180026EFA
0x180026ee3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026ee8  cmp     al, 1
0x180026eea  jb      loc_180027290
0x180026ef0  mov     edx, 27h ; '''
0x180026ef5  jmp     loc_180026D72
0x180026efa  movups  xmm0, xmmword ptr [r15]
0x180026efe  mov     eax, [rsp+240h+pcbBufSize]
0x180026f02  mov     ecx, 1
0x180026f07  movups  xmm1, xmmword ptr [r15+10h]
0x180026f0c  mov     dword ptr [rbp+140h+var_130], ecx
0x180026f0f  lea     r9, [rbp+140h+var_130]; unsigned __int8 *
0x180026f13  mov     [rbp+140h+var_DC], ecx
0x180026f16  lea     rdx, [rbp+140h+var_150]; struct _DEVPROPKEY *
0x180026f1a  mov     rcx, rsi; unsigned __int16 *
0x180026f1d  mov     [rbp+140h+var_12C], 60h ; '`'
0x180026f24  mov     r8d, 1003h; unsigned int
0x180026f2a  mov     [rbp+140h+var_E8], 0
0x180026f32  movups  [rbp+140h+var_128], xmm0
0x180026f36  mov     [rbp+140h+var_E0], eax
0x180026f39  movups  [rbp+140h+var_118], xmm1
0x180026f3d  mov     [rbp+140h+var_D8], r14d
0x180026f41  movups  [rbp+140h+var_108], xmm0
0x180026f45  mov     [rbp+140h+var_D4], 0
0x180026f4c  movups  [rbp+140h+var_F8], xmm1
0x180026f50  mov     [rsp+240h+var_220], 60h ; '`'; ULONG
0x180026f58  call    ?FSSetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@KQEAEK@Z; FSSetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar * const,ulong)
0x180026f5d  mov     edi, eax
0x180026f5f  test    eax, eax
0x180026f61  jns     short loc_180026F7A
0x180026f63  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026f68  cmp     al, 1
0x180026f6a  jb      loc_180027290
0x180026f70  mov     edx, 28h ; '('
0x180026f75  jmp     loc_180026D72
0x180026f7a  lea     r8, [rsp+240h+var_1D8]; unsigned __int64 *
0x180026f7f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180026f84  mov     rcx, rsi; unsigned __int16 *
0x180026f87  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180026f8c  mov     edi, eax
0x180026f8e  test    eax, eax
0x180026f90  jns     short loc_180026FA9
0x180026f92  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026f97  cmp     al, 1
0x180026f99  jb      loc_180027290
0x180026f9f  mov     edx, 29h ; ')'
0x180026fa4  jmp     loc_180026D72
0x180026fa9  mov     rax, [rsp+240h+var_1D8]
0x180026fae  lea     rdx, [rbp+140h+var_150]; struct _DEVPROPKEY *
0x180026fb2  mov     r9, rsi; unsigned __int8 *
0x180026fb5  mov     [rbp+140h+var_150.pid], 4
0x180026fbc  mov     r8d, 12h; unsigned int
0x180026fc2  mov     rcx, rsi; unsigned __int16 *
0x180026fc5  lea     eax, ds:2[rax*2]
0x180026fcc  mov     [rsp+240h+var_220], eax; ULONG
0x180026fd0  call    ?FSSetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@KQEAEK@Z; FSSetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar * const,ulong)
0x180026fd5  mov     edi, eax
0x180026fd7  test    eax, eax
0x180026fd9  jns     short loc_180026FF2
0x180026fdb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026fe0  cmp     al, 1
0x180026fe2  jb      loc_180027290
0x180026fe8  mov     edx, 2Ah ; '*'
0x180026fed  jmp     loc_180026D72
0x180026ff2  mov     eax, [rsp+240h+pcbBufSize]
0x180026ff6  lea     rdx, [rbp+140h+var_150]; struct _DEVPROPKEY *
0x180026ffa  mov     r9, rbx; unsigned __int8 *
0x180026ffd  mov     [rsp+240h+var_220], eax; ULONG
0x180027001  mov     r8d, 1003h; unsigned int
0x180027007  mov     [rbp+140h+var_150.pid], 5
0x18002700e  mov     rcx, rsi; unsigned __int16 *
0x180027011  call    ?FSSetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@KQEAEK@Z; FSSetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,ulong,uchar * const,ulong)
0x180027016  mov     edi, eax
0x180027018  test    eax, eax
0x18002701a  jns     short loc_180027033
0x18002701c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180027021  cmp     al, 1
0x180027023  jb      loc_180027290
0x180027029  mov     edx, 2Bh ; '+'
0x18002702e  jmp     loc_180026D72
0x180027033  xor     edx, edx; Val
0x180027035  mov     [rbp+140h+var_150.pid], 6
0x18002703c  mov     r8d, 208h; Size
0x180027042  lea     rcx, [r13+20h]; void *
0x180027046  call    memset_0
0x18002704b  mov     r8, rsi; unsigned __int16 *
0x18002704e  lea     rcx, [r13+20h]; unsigned __int16 *
0x180027052  mov     edx, 104h; unsigned __int64
0x180027057  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002705c  mov     edi, eax
0x18002705e  test    eax, eax
0x180027060  jns     short loc_180027079
0x180027062  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180027067  cmp     al, 1
0x180027069  jb      loc_180027290
0x18002706f  mov     edx, 2Ch ; ','
  ... truncated ...
```
