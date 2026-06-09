# FSUpdateSensorGroupDataToRegistry(bool,ushort const *,ushort const *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003 const &,ushort const * *,ulong,uchar const *,ulong,uchar const *,ulong,FSMFileTime const &,FSMFileTime const &)

- ea: `0x1800272f8`
- end: `0x1800277fd`
- name: `?FSUpdateSensorGroupDataToRegistry@@YAJ_NPEBG1AEBU__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003@@PEAPEBGKPEBEK4KAEBUFSMFileTime@@5@Z`
- size: `1285`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003 *, const unsigned __int16 **, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, FILETIME *lpFileTime, FILETIME *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180026b78`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180004f78`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000cadc`
- `0x18000d3d8`
- `0x1800272f8`
- `0x180027990`

## import_xrefs

- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x1800273cb`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x18002742b`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x180027492`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x1800274d0`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x18002750e`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x1800275d7`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x180027695`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x180027743`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x1800273cb`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x18002742b`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x180027492`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x1800274d0`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x18002750e`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x1800275d7`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x180027695`
- `MFSENSORGROUP!MFWriteSensorGroupDataToRegistry` at `0x180027743`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027539`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027602`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027539`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027602`

## pseudocode

```c
__int64 __fastcall FSUpdateSensorGroupDataToRegistry(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0003 *a4,
        const unsigned __int16 **a5,
        unsigned int a6,
        const unsigned __int8 *a7,
        unsigned int a8,
        const unsigned __int8 *a9,
        unsigned int a10,
        FILETIME *lpFileTime,
        FILETIME *a12)
{
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // ebx
  __int64 v18; // rdx
  unsigned __int8 Level; // al
  const unsigned __int16 **v20; // r12
  __int64 i; // rdi
  const unsigned __int16 *v22; // rcx
  int v23; // r14d
  __int64 v24; // rdx
  __int64 v26; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+28h] [rbp-D8h]
  __int64 v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+38h] [rbp-C8h]
  __int64 v32; // [rsp+40h] [rbp-C0h]
  __int64 v33; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  FILETIME *v36; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 **v37; // [rsp+68h] [rbp-98h]
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v39[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v40; // [rsp+90h] [rbp-70h]
  __int128 v41; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v42[264]; // [rsp+B0h] [rbp-50h] BYREF

  v37 = a5;
  v36 = a12;
  v34 = 0;
  SystemTime = 0;
  v35 = 1;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v41 = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v15, v16);
  v17 = MFWriteSensorGroupDataToRegistry(a2, 0, 21, 4, &v35, 4);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
LABEL_7:
      Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
LABEL_48:
      if ( Level )
      {
        v24 = 24;
LABEL_52:
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v24,
          &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids,
          (unsigned int)v17);
      }
      return (unsigned int)v17;
    }
    v18 = 11;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, 0, v17);
    goto LABEL_7;
  }
  v17 = MFWriteSensorGroupDataToRegistry(a2, 0, 3, 3, a4, 96);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 12;
    goto LABEL_6;
  }
  v17 = StringCchLengthW(a3, 0x7FFFFFFFu, &v34);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 13;
    goto LABEL_6;
  }
  v17 = MFWriteSensorGroupDataToRegistry(a2, 0, 4, 1, a3, 2 * (int)v34 + 2);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 14;
    goto LABEL_6;
  }
  v17 = MFWriteSensorGroupDataToRegistry(a2, 0, 5, 3, a7, a8);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 15;
    goto LABEL_6;
  }
  v17 = MFWriteSensorGroupDataToRegistry(a2, 0, 6, 3, a9, a10);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 16;
    goto LABEL_6;
  }
  FileTimeToSystemTime(lpFileTime, &SystemTime);
  LODWORD(v28) = SystemTime.wDay;
  LODWORD(v26) = SystemTime.wMonth;
  v17 = StringCchPrintfW(
          v39,
          0x18u,
          L"%04u-%02u-%02u %02u:%02u:%02u.%03u",
          SystemTime.wYear,
          v26,
          v28,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 17;
    goto LABEL_6;
  }
  v17 = MFWriteSensorGroupDataToRegistry(a2, 0, 20, 1, v39, 48);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 18;
    goto LABEL_6;
  }
  FileTimeToSystemTime(v36, &SystemTime);
  LODWORD(v33) = SystemTime.wMilliseconds;
  LODWORD(v32) = SystemTime.wSecond;
  LODWORD(v31) = SystemTime.wMinute;
  LODWORD(v30) = SystemTime.wHour;
  LODWORD(v29) = SystemTime.wDay;
  LODWORD(v27) = SystemTime.wMonth;
  v17 = StringCchPrintfW(
          v39,
          0x18u,
          L"%04u-%02u-%02u %02u:%02u:%02u.%03u",
          SystemTime.wYear,
          v27,
          v29,
          v30,
          v31,
          v32,
          v33);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 19;
    goto LABEL_6;
  }
  v17 = MFWriteSensorGroupDataToRegistry(a2, 0, 19, 1, v39, 48);
  if ( v17 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v18 = 20;
    goto LABEL_6;
  }
  v20 = v37;
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    memset_0(v42, 0, 0x208u);
    v22 = v20[i];
    v34 = 0;
    v17 = StringCchLengthW(v22, 0x7FFFFFFFu, &v34);
    if ( v17 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_7;
      v18 = 21;
      goto LABEL_6;
    }
    v23 = v34 + 1;
    v17 = StringCchPrintfW(v42, 0x104u, L"Device%d", 0);
    if ( v17 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_7;
      v18 = 22;
      goto LABEL_6;
    }
    v17 = MFWriteSensorGroupDataToRegistry(a2, v42, 0, 1, v20[i], 2 * v23);
    if ( v17 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v18 = 23;
        goto LABEL_6;
      }
      break;
    }
  }
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v17 < 0 )
    goto LABEL_48;
  if ( Level >= 8u )
  {
    v24 = 25;
    goto LABEL_52;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800272f8  mov     [rsp-8+arg_0], rbx
0x1800272fd  push    rbp
0x1800272fe  push    rsi
0x1800272ff  push    rdi
0x180027300  push    r12
0x180027302  push    r13
0x180027304  push    r14
0x180027306  push    r15
0x180027308  lea     rbp, [rsp-1D0h]
0x180027310  sub     rsp, 2D0h
0x180027317  mov     rax, cs:__security_cookie
0x18002731e  xor     rax, rsp
0x180027321  mov     [rbp+200h+var_40], rax
0x180027328  mov     rax, [rbp+200h+arg_20]
0x18002732f  xorps   xmm1, xmm1
0x180027332  mov     r15, [rbp+200h+arg_30]
0x180027339  xorps   xmm0, xmm0
0x18002733c  mov     r12, [rbp+200h+arg_40]
0x180027343  mov     r14, r9
0x180027346  mov     r13, [rbp+200h+lpFileTime]
0x18002734d  mov     rdi, r8
0x180027350  mov     [rsp+300h+var_298], rax
0x180027355  mov     rsi, rdx
0x180027358  mov     rax, [rbp+200h+arg_58]
0x18002735f  mov     [rsp+300h+var_2A0], rax
0x180027364  mov     [rsp+300h+var_2B0], 0
0x18002736d  movups  xmmword ptr [rsp+300h+SystemTime.wYear], xmm0
0x180027372  mov     [rsp+300h+var_2A8], 1
0x18002737a  movups  xmmword ptr [rbp+200h+var_280], xmm1
0x18002737e  movups  [rbp+200h+var_270], xmm1
0x180027382  movups  [rbp+200h+var_260], xmm1
0x180027386  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18002738b  cmp     al, 8
0x18002738d  jb      short loc_1800273AC
0x18002738f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027396  mov     [rsp+300h+var_2D8], r8; __int64
0x18002739b  mov     [rsp+300h+var_2E0], rdx; __int64
0x1800273a0  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800273a7  call    WPP_SF_dSS
0x1800273ac  mov     ecx, 4
0x1800273b1  lea     rax, [rsp+300h+var_2A8]
0x1800273b6  mov     dword ptr [rsp+300h+var_2D8], ecx
0x1800273ba  mov     r9d, ecx
0x1800273bd  xor     edx, edx
0x1800273bf  mov     [rsp+300h+var_2E0], rax
0x1800273c4  lea     r8d, [rcx+11h]
0x1800273c8  mov     rcx, rsi
0x1800273cb  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x1800273d1  mov     ebx, eax
0x1800273d3  test    eax, eax
0x1800273d5  jns     short loc_18002740D
0x1800273d7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800273dc  cmp     al, 1
0x1800273de  jb      short loc_180027403
0x1800273e0  mov     edx, 0Bh
0x1800273e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273ec  lea     r8, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x1800273f3  xor     r9d, r9d
0x1800273f6  mov     dword ptr [rsp+300h+var_2E0], ebx
0x1800273fa  mov     rcx, [rcx+10h]
0x1800273fe  call    WPP_SF_qD
0x180027403  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180027408  jmp     loc_1800277A0
0x18002740d  mov     dword ptr [rsp+300h+var_2D8], 60h ; '`'
0x180027415  xor     edx, edx
0x180027417  mov     [rsp+300h+var_2E0], r14
0x18002741c  mov     rcx, rsi
0x18002741f  mov     r14d, 3
0x180027425  mov     r9d, r14d
0x180027428  mov     r8d, r14d
0x18002742b  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x180027431  mov     ebx, eax
0x180027433  test    eax, eax
0x180027435  jns     short loc_180027446
0x180027437  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002743c  cmp     al, 1
0x18002743e  jb      short loc_180027403
0x180027440  lea     edx, [r14+9]
0x180027444  jmp     short loc_1800273E5
0x180027446  lea     r8, [rsp+300h+var_2B0]; unsigned __int64 *
0x18002744b  mov     edx, 7FFFFFFFh; unsigned __int64
0x180027450  mov     rcx, rdi; unsigned __int16 *
0x180027453  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180027458  mov     ebx, eax
0x18002745a  test    eax, eax
0x18002745c  jns     short loc_180027471
0x18002745e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180027463  cmp     al, 1
0x180027465  jb      short loc_180027403
0x180027467  mov     edx, 0Dh
0x18002746c  jmp     loc_1800273E5
0x180027471  mov     eax, dword ptr [rsp+300h+var_2B0]
0x180027475  xor     edx, edx
0x180027477  mov     rcx, rsi
0x18002747a  lea     eax, ds:2[rax*2]
0x180027481  mov     dword ptr [rsp+300h+var_2D8], eax
0x180027485  lea     r9d, [rdx+1]
0x180027489  lea     r8d, [rdx+4]
0x18002748d  mov     [rsp+300h+var_2E0], rdi
0x180027492  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x180027498  mov     ebx, eax
0x18002749a  test    eax, eax
0x18002749c  jns     short loc_1800274B5
0x18002749e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800274a3  cmp     al, 1
0x1800274a5  jb      loc_180027403
0x1800274ab  mov     edx, 0Eh
0x1800274b0  jmp     loc_1800273E5
0x1800274b5  mov     eax, [rbp+200h+arg_38]
0x1800274bb  xor     edx, edx
0x1800274bd  mov     dword ptr [rsp+300h+var_2D8], eax
0x1800274c1  mov     r9d, r14d
0x1800274c4  mov     rcx, rsi
0x1800274c7  mov     [rsp+300h+var_2E0], r15
0x1800274cc  lea     r8d, [rdx+5]
0x1800274d0  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x1800274d6  mov     ebx, eax
0x1800274d8  test    eax, eax
0x1800274da  jns     short loc_1800274F3
0x1800274dc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800274e1  cmp     al, 1
0x1800274e3  jb      loc_180027403
0x1800274e9  mov     edx, 0Fh
0x1800274ee  jmp     loc_1800273E5
0x1800274f3  mov     eax, [rbp+200h+arg_48]
0x1800274f9  xor     edx, edx
0x1800274fb  mov     dword ptr [rsp+300h+var_2D8], eax
0x1800274ff  mov     r9d, r14d
0x180027502  mov     rcx, rsi
0x180027505  mov     [rsp+300h+var_2E0], r12
0x18002750a  lea     r8d, [rdx+6]
0x18002750e  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x180027514  mov     ebx, eax
0x180027516  test    eax, eax
0x180027518  jns     short loc_180027531
0x18002751a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002751f  cmp     al, 1
0x180027521  jb      loc_180027403
0x180027527  mov     edx, 10h
0x18002752c  jmp     loc_1800273E5
0x180027531  lea     rdx, [rsp+300h+SystemTime]; lpSystemTime
0x180027536  mov     rcx, r13; lpFileTime
0x180027539  call    cs:__imp_FileTimeToSystemTime
0x18002753f  movzx   ecx, [rsp+300h+SystemTime.wSecond]
0x180027544  movzx   edx, [rsp+300h+SystemTime.wMinute]
0x180027549  movzx   r8d, [rsp+300h+SystemTime.wHour]
0x18002754f  movzx   eax, [rsp+300h+SystemTime.wMilliseconds]
0x180027554  movzx   r10d, [rsp+300h+SystemTime.wDay]
0x18002755a  movzx   r11d, [rsp+300h+SystemTime.wMonth]
0x180027560  movzx   r9d, [rsp+300h+SystemTime.wYear]
0x180027566  mov     dword ptr [rsp+300h+var_2B8], eax
0x18002756a  mov     dword ptr [rsp+300h+var_2C0], ecx
0x18002756e  lea     rcx, [rbp+200h+var_280]; unsigned __int16 *
0x180027572  mov     dword ptr [rsp+300h+var_2C8], edx
0x180027576  mov     edx, 18h; unsigned __int64
0x18002757b  mov     dword ptr [rsp+300h+var_2D0], r8d
0x180027580  lea     r8, a04u02u02u02u02; "%04u-%02u-%02u %02u:%02u:%02u.%03u"
0x180027587  mov     dword ptr [rsp+300h+var_2D8], r10d
0x18002758c  mov     dword ptr [rsp+300h+var_2E0], r11d
0x180027591  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027596  mov     ebx, eax
0x180027598  test    eax, eax
0x18002759a  jns     short loc_1800275B3
0x18002759c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800275a1  cmp     al, 1
0x1800275a3  jb      loc_180027403
0x1800275a9  mov     edx, 11h
0x1800275ae  jmp     loc_1800273E5
0x1800275b3  mov     r14d, 30h ; '0'
0x1800275b9  lea     rax, [rbp+200h+var_280]
0x1800275bd  mov     dword ptr [rsp+300h+var_2D8], r14d
0x1800275c2  xor     edx, edx
0x1800275c4  mov     rcx, rsi
0x1800275c7  mov     [rsp+300h+var_2E0], rax
0x1800275cc  lea     edi, [r14-1Ch]
0x1800275d0  mov     r8d, edi
0x1800275d3  lea     r9d, [r14-2Fh]
0x1800275d7  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x1800275dd  mov     ebx, eax
0x1800275df  test    eax, eax
0x1800275e1  jns     short loc_1800275F8
0x1800275e3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800275e8  cmp     al, 1
0x1800275ea  jb      loc_180027403
0x1800275f0  lea     edx, [rdi-2]
0x1800275f3  jmp     loc_1800273E5
0x1800275f8  mov     rcx, [rsp+300h+var_2A0]; lpFileTime
0x1800275fd  lea     rdx, [rsp+300h+SystemTime]; lpSystemTime
0x180027602  call    cs:__imp_FileTimeToSystemTime
0x180027608  movzx   ecx, [rsp+300h+SystemTime.wSecond]
0x18002760d  lea     r8, a04u02u02u02u02; "%04u-%02u-%02u %02u:%02u:%02u.%03u"
0x180027614  movzx   edx, [rsp+300h+SystemTime.wMinute]
0x180027619  movzx   eax, [rsp+300h+SystemTime.wMilliseconds]
0x18002761e  movzx   r10d, [rsp+300h+SystemTime.wHour]
0x180027624  movzx   r11d, [rsp+300h+SystemTime.wDay]
0x18002762a  movzx   ebx, [rsp+300h+SystemTime.wMonth]
0x18002762f  movzx   r9d, [rsp+300h+SystemTime.wYear]
0x180027635  mov     dword ptr [rsp+300h+var_2B8], eax
0x180027639  mov     dword ptr [rsp+300h+var_2C0], ecx
0x18002763d  lea     rcx, [rbp+200h+var_280]; unsigned __int16 *
0x180027641  mov     dword ptr [rsp+300h+var_2C8], edx
0x180027645  mov     edx, 18h; unsigned __int64
0x18002764a  mov     dword ptr [rsp+300h+var_2D0], r10d
0x18002764f  mov     dword ptr [rsp+300h+var_2D8], r11d
0x180027654  mov     dword ptr [rsp+300h+var_2E0], ebx
0x180027658  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002765d  mov     ebx, eax
0x18002765f  test    eax, eax
0x180027661  jns     short loc_18002767A
0x180027663  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180027668  cmp     al, 1
0x18002766a  jb      loc_180027403
0x180027670  mov     edx, 13h
0x180027675  jmp     loc_1800273E5
0x18002767a  xor     edx, edx
0x18002767c  mov     dword ptr [rsp+300h+var_2D8], r14d
0x180027681  lea     rax, [rbp+200h+var_280]
0x180027685  mov     rcx, rsi
0x180027688  mov     [rsp+300h+var_2E0], rax
0x18002768d  lea     r9d, [rdx+1]
0x180027691  lea     r8d, [rdx+13h]
0x180027695  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x18002769b  mov     ebx, eax
0x18002769d  test    eax, eax
0x18002769f  jns     short loc_1800276B5
0x1800276a1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800276a6  cmp     al, 1
0x1800276a8  jb      loc_180027403
0x1800276ae  mov     edx, edi
0x1800276b0  jmp     loc_1800273E5
0x1800276b5  mov     r12, [rsp+300h+var_298]
0x1800276ba  xor     edi, edi
0x1800276bc  cmp     edi, 1
0x1800276bf  jnb     loc_180027797
0x1800276c5  xor     edx, edx; Val
0x1800276c7  lea     rcx, [rbp+200h+var_250]; void *
0x1800276cb  mov     r8d, 208h; Size
0x1800276d1  call    memset_0
0x1800276d6  mov     rcx, [r12+rdi*8]; unsigned __int16 *
0x1800276da  lea     r8, [rsp+300h+var_2B0]; unsigned __int64 *
0x1800276df  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800276e4  mov     [rsp+300h+var_2B0], 0
0x1800276ed  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800276f2  mov     ebx, eax
0x1800276f4  test    eax, eax
0x1800276f6  js      loc_180027780
0x1800276fc  mov     r14, [rsp+300h+var_2B0]
0x180027701  lea     r8, aDeviceD; "Device%d"
0x180027708  mov     r9d, edi
0x18002770b  lea     rcx, [rbp+200h+var_250]; unsigned __int16 *
0x18002770f  mov     edx, 104h; unsigned __int64
0x180027714  inc     r14
0x180027717  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002771c  mov     ebx, eax
0x18002771e  test    eax, eax
0x180027720  js      short loc_180027769
0x180027722  lea     eax, [r14+r14]
0x180027726  mov     r9d, 1
0x18002772c  mov     dword ptr [rsp+300h+var_2D8], eax
0x180027730  lea     rdx, [rbp+200h+var_250]
0x180027734  mov     rax, [r12+rdi*8]
0x180027738  xor     r8d, r8d
0x18002773b  mov     rcx, rsi
0x18002773e  mov     [rsp+300h+var_2E0], rax
0x180027743  call    cs:__imp_MFWriteSensorGroupDataToRegistry
0x180027749  mov     ebx, eax
0x18002774b  test    eax, eax
0x18002774d  js      short loc_180027756
0x18002774f  inc     edi
0x180027751  jmp     loc_1800276BC
0x180027756  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002775b  cmp     al, 1
0x18002775d  jb      short loc_180027797
0x18002775f  mov     edx, 17h
0x180027764  jmp     loc_1800273E5
0x180027769  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002776e  cmp     al, 1
0x180027770  jb      loc_180027403
0x180027776  mov     edx, 16h
0x18002777b  jmp     loc_1800273E5
0x180027780  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180027785  cmp     al, 1
0x180027787  jb      loc_180027403
0x18002778d  mov     edx, 15h
0x180027792  jmp     loc_1800273E5
0x180027797  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18002779c  test    ebx, ebx
0x18002779e  jns     short loc_1800277AB
0x1800277a0  cmp     al, 1
0x1800277a2  jb      short loc_1800277D1
0x1800277a4  mov     edx, 18h
0x1800277a9  jmp     short loc_1800277B4
0x1800277ab  cmp     al, 8
0x1800277ad  jb      short loc_1800277D1
0x1800277af  mov     edx, 19h
0x1800277b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277bb  lea     r8, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x1800277c2  mov     r9d, ebx
0x1800277c5  mov     rcx, [rcx+0D8h]
0x1800277cc  call    WPP_SF_d
  ... truncated ...
```
