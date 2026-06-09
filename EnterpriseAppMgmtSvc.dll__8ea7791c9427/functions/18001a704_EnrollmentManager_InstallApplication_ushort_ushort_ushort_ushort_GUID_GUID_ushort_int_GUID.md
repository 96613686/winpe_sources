# EnrollmentManager::InstallApplication(ushort *,ushort *,ushort *,ushort *,_GUID,_GUID,ushort *,int,_GUID *)

- ea: `0x18001a704`
- end: `0x18001add2`
- name: `?InstallApplication@EnrollmentManager@@SAJPEAG000U_GUID@@10HPEAU2@@Z`
- size: `1742`
- prototype: `__int64 __fastcall(wchar_t *String2, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _GUID *Buf1, struct _GUID *, unsigned __int16 *, int, struct _GUID *)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180007a80`
- `0x180013328`

## callees

- `0x180006780`
- `0x1800067d8`
- `0x180006858`
- `0x180013bb0`
- `0x1800186dc`
- `0x1800199e4`
- `0x18001a3d4`
- `0x18001a52c`
- `0x18001a704`
- `0x18001add8`
- `0x18001bf0c`
- `0x1800277d0`
- `0x180027a18`
- `0x180027cbc`
- `0x180027d1c`
- `0x1800280e8`
- `0x1800287d0`
- `0x180029f88`
- `0x18002eb84`
- `0x180031510`
- `0x180066da6`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ada0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ada0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a91b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a91b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a83c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a83c`
- `dsclient!DSCopyFromSharedFile` at `0x18001aa00`
- `dsclient!DSCopyFromSharedFile` at `0x18001aa00`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001aa8d`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001aa8d`

## string_xrefs

- `0x18001a9dd`: `DeleteLocalFile Failed`
- `0x18001a88a`: `EnrollmentManager::InstallApplication- Cannot have more than one queued active install request that is waiting on user confirmation.`
- `0x18001aaa8`: `CopyFileW Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EnrollmentManager::InstallApplication(
        wchar_t *String2,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct _GUID *Buf1,
        struct _GUID *a6,
        unsigned __int16 *a7,
        int a8,
        struct _GUID *a9)
{
  unsigned int v12; // edx
  int RequestId; // ebx
  __int64 v14; // rcx
  __int64 v15; // r9
  const wchar_t *v16; // r8
  int InstallationStateOfRemoteUri; // eax
  __int64 v18; // rcx
  __int64 v19; // rsi
  __int64 v20; // rax
  const WCHAR *v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  LPCWSTR *v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  const WCHAR *v27; // rdx
  __int64 v28; // rax
  LPCWSTR *v29; // rax
  LPCWSTR *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  EnterpriseWorkerThread *v34; // rax
  unsigned __int8 v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v38; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+4Ch] [rbp-B4h] BYREF
  GUID rguid; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch] BYREF
  int v45; // [rsp+68h] [rbp-98h] BYREF
  int v46; // [rsp+6Ch] [rbp-94h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v48; // [rsp+78h] [rbp-88h]
  struct _GUID *v49; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v50; // [rsp+88h] [rbp-78h]
  struct EnterpriseDB *DBInstance; // [rsp+90h] [rbp-70h]
  LPCWSTR lpNewFileName[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v53; // [rsp+B0h] [rbp-50h]
  BSTR bstrString[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v55[16]; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID *v56; // [rsp+E0h] [rbp-20h]
  __int64 v57; // [rsp+E8h] [rbp-18h]
  unsigned int *v58; // [rsp+F0h] [rbp-10h]
  __int64 v59; // [rsp+F8h] [rbp-8h]
  unsigned int *v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  BSTR *v62; // [rsp+110h] [rbp+10h]
  __int64 v63; // [rsp+118h] [rbp+18h]
  __int16 v64; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID *v65; // [rsp+128h] [rbp+28h] BYREF
  int v66; // [rsp+130h] [rbp+30h]
  __int16 v67; // [rsp+138h] [rbp+38h]
  int *v68; // [rsp+140h] [rbp+40h]
  int v69; // [rsp+148h] [rbp+48h]
  __int16 v70; // [rsp+150h] [rbp+50h]
  struct _FILETIME *p_SystemTimeAsFileTime; // [rsp+158h] [rbp+58h]
  int v72; // [rsp+160h] [rbp+60h]
  __int16 v73; // [rsp+168h] [rbp+68h]
  struct _FILETIME *v74; // [rsp+170h] [rbp+70h]
  int v75; // [rsp+178h] [rbp+78h]
  __int16 v76; // [rsp+180h] [rbp+80h]
  wchar_t *v77; // [rsp+188h] [rbp+88h]
  int v78; // [rsp+190h] [rbp+90h]
  __int16 v79; // [rsp+198h] [rbp+98h]
  LPCWSTR *v80; // [rsp+1A0h] [rbp+A0h]
  int v81; // [rsp+1A8h] [rbp+A8h]
  __int16 v82; // [rsp+1B0h] [rbp+B0h]
  unsigned int *v83; // [rsp+1B8h] [rbp+B8h]
  int v84; // [rsp+1C0h] [rbp+C0h]
  __int16 v85; // [rsp+1C8h] [rbp+C8h]
  int *v86; // [rsp+1D0h] [rbp+D0h]
  int v87; // [rsp+1D8h] [rbp+D8h]
  __int16 v88; // [rsp+1E0h] [rbp+E0h]
  int *v89; // [rsp+1E8h] [rbp+E8h]
  int v90; // [rsp+1F0h] [rbp+F0h]
  __int16 v91; // [rsp+1F8h] [rbp+F8h]
  int *v92; // [rsp+200h] [rbp+100h]
  int v93; // [rsp+208h] [rbp+108h]
  __int16 v94; // [rsp+210h] [rbp+110h]
  unsigned __int16 *v95; // [rsp+218h] [rbp+118h]
  int v96; // [rsp+220h] [rbp+120h]
  __int16 v97; // [rsp+228h] [rbp+128h]
  struct _GUID *v98; // [rsp+230h] [rbp+130h]
  int v99; // [rsp+238h] [rbp+138h]
  __int16 v100; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v101; // [rsp+248h] [rbp+148h]
  int v102; // [rsp+250h] [rbp+150h]
  __int16 v103; // [rsp+258h] [rbp+158h]
  unsigned __int8 *v104; // [rsp+260h] [rbp+160h]
  int v105; // [rsp+268h] [rbp+168h]
  __int16 v106; // [rsp+270h] [rbp+170h]
  struct _GUID *v107; // [rsp+278h] [rbp+178h]
  int v108; // [rsp+280h] [rbp+180h]
  __int16 v109; // [rsp+288h] [rbp+188h]
  unsigned __int16 *v110; // [rsp+290h] [rbp+190h]
  int v111; // [rsp+298h] [rbp+198h]
  __int16 v112; // [rsp+2A0h] [rbp+1A0h]
  int *v113; // [rsp+2A8h] [rbp+1A8h]
  int v114; // [rsp+2B0h] [rbp+1B0h]

  v50 = a4;
  v48 = a3;
  v49 = Buf1;
  memset_0(&v65, 0, 0x220u);
  v37 = 1;
  v40 = 1;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  SystemTimeAsFileTime = 0;
  v46 = 1;
  v36 = 0;
  v53 = 7;
  lpNewFileName[2] = 0;
  LOWORD(lpNewFileName[0]) = 0;
  std::wstring::assign(lpNewFileName, (void *)&Src);
  v38 = 0;
  v39 = 0;
  *(GUID *)bstrString = GUID_NULL;
  v41 = 0;
  if ( !String2 || !a3 || !a7 || !a9 )
  {
    RequestId = -2147024809;
    goto LABEL_70;
  }
  SQMIncrement(0x81Cu, v12);
  v37 = a8 == 0;
  DBInstance = EnterpriseConfig::GetDBInstance();
  if ( !DBInstance )
  {
    RequestId = -2147024882;
    goto LABEL_70;
  }
  RequestId = EnterpriseConfig::GenerateRequestId(a9);
  if ( RequestId >= 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    RequestId = EnrollmentManager::PurgeXAPRequestTable(&v38, &v39);
    if ( RequestId >= 0 )
    {
      if ( v38 > 0x19 )
      {
LABEL_11:
        RequestId = -2147467259;
        goto LABEL_70;
      }
      if ( a8 && v39 )
      {
        if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
          goto LABEL_11;
        v15 = 2147500037LL;
        v16 = L"EnrollmentManager::InstallApplication- Cannot have more than one queued active install request that is wai"
               "ting on user confirmation.";
LABEL_16:
        McTemplateU0zq_EventWriteTransfer(v14, EnterpriseAppMgmtSvcError, v16, v15);
        goto LABEL_11;
      }
      if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
      {
        InstallationStateOfRemoteUri = EnrollmentManager::GetInstallationStateOfRemoteUri(
                                         String2,
                                         (enum _ENTERPRISE_APP_INSTALL_STATE *)&v40,
                                         (struct _GUID *)bstrString);
      }
      else
      {
        rguid = *Buf1;
        InstallationStateOfRemoteUri = EnrollmentManager::GetInstallationStateOfProductId(
                                         &rguid,
                                         (enum _ENTERPRISE_APP_INSTALL_STATE *)&v40,
                                         (struct _GUID *)bstrString);
      }
      if ( !InstallationStateOfRemoteUri )
      {
        if ( (unsigned int)(v40 - 5) > 2 )
        {
          bstrString[0] = 0;
          rguid = *Buf1;
          RequestId = ConvertGuidToBstr(&rguid, bstrString);
          if ( RequestId >= 0 )
          {
            if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x20) != 0 )
              McTemplateU0z_EventWriteTransfer(v18, EnterpriseAppMgmtXapRequestAlreadyInProgress, bstrString[0]);
            RequestId = -2147024567;
          }
          SysFreeString(bstrString[0]);
          goto LABEL_70;
        }
        rguid = *(GUID *)bstrString;
        RequestId = EnrollmentManager::DeleteRecord(1, &rguid);
        if ( RequestId < 0 )
          goto LABEL_70;
      }
      v19 = -1;
      if ( !a2 )
        goto LABEL_75;
      v20 = -1;
      do
        ++v20;
      while ( a2[v20] );
      if ( !v20 )
      {
LABEL_75:
        if ( !(unsigned int)RemoteUrl(String2) )
        {
          RequestId = DetermineInstallFileType(String2, (enum EnterpriseFileType *)&v41);
          if ( RequestId < 0 )
            goto LABEL_70;
          rguid = *a9;
          RequestId = GenerateDestinationFileName(&rguid, lpNewFileName);
          if ( RequestId < 0 )
            goto LABEL_70;
          v27 = (const WCHAR *)lpNewFileName;
          if ( v53 >= 8 )
            v27 = lpNewFileName[0];
          if ( !CopyFileW(String2, v27, 0) )
          {
            if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
              goto LABEL_11;
            v15 = (unsigned int)RequestId;
            v16 = L"CopyFileW Failed";
            goto LABEL_16;
          }
        }
        v26 = v37;
        goto LABEL_52;
      }
      rguid = *a9;
      RequestId = GenerateDestinationFileName(&rguid, lpNewFileName);
      if ( RequestId >= 0 )
      {
        v21 = (const WCHAR *)lpNewFileName;
        if ( v53 >= 8 )
          v21 = lpNewFileName[0];
        v22 = DeleteLocalFile(v21);
        if ( v22 < 0 && (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            v23,
            EnterpriseAppMgmtSvcError,
            L"DeleteLocalFile Failed",
            (unsigned int)v22);
        v24 = lpNewFileName;
        if ( v53 >= 8 )
          v24 = (LPCWSTR *)lpNewFileName[0];
        RequestId = DSCopyFromSharedFile(a2, v24);
        if ( RequestId >= 0 )
        {
          v26 = v37;
          if ( v37 )
          {
            v26 = 3;
            v37 = 3;
            v36 = 50;
          }
LABEL_52:
          if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x10) != 0 )
          {
            LODWORD(bstrString[0]) = v36;
            v38 = 0;
            v39 = v26;
            v56 = a9;
            v57 = 16;
            v58 = &v39;
            v59 = 4;
            v60 = &v38;
            v61 = 4;
            v62 = bstrString;
            v63 = 4;
            McGenEventWrite_EventWriteTransfer(v26, EnterpriseAppMgmtSvcXapStateChange, v25, 5, v55);
          }
          v64 = 0;
          v65 = a9;
          v66 = 16;
          v67 = 4;
          v68 = &v43;
          v69 = 1;
          v70 = 1;
          p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
          v72 = 8;
          v73 = 2;
          v74 = &SystemTimeAsFileTime;
          v75 = 8;
          v76 = 5;
          v77 = String2;
          v28 = -1;
          do
            ++v28;
          while ( String2[v28] );
          v78 = 2 * v28 + 2;
          v79 = 6;
          v29 = lpNewFileName;
          if ( v53 >= 8 )
            v29 = (LPCWSTR *)lpNewFileName[0];
          v80 = v29;
          v30 = lpNewFileName;
          if ( v53 >= 8 )
            v30 = (LPCWSTR *)lpNewFileName[0];
          v31 = -1;
          do
            ++v31;
          while ( *((_WORD *)v30 + v31) );
          v81 = 2 * v31 + 2;
          v82 = 7;
          v83 = &v37;
          v84 = 1;
          v85 = 8;
          v86 = &v44;
          v87 = 4;
          v88 = 10;
          v89 = &v45;
          v90 = 4;
          v91 = 11;
          v92 = &v46;
          v93 = 1;
          v94 = 12;
          v95 = v48;
          v32 = -1;
          do
            ++v32;
          while ( v48[v32] );
          v96 = 2 * v32 + 2;
          v97 = 13;
          v98 = v49;
          v99 = 16;
          v100 = 14;
          v101 = a7;
          v33 = -1;
          do
            ++v33;
          while ( a7[v33] );
          v102 = 2 * v33 + 2;
          v103 = 15;
          v104 = &v36;
          v105 = 1;
          v106 = 3;
          v107 = a6;
          v108 = 16;
          v109 = 21;
          v110 = v50;
          do
            ++v19;
          while ( v50[v19] );
          v111 = 2 * v19 + 2;
          v112 = 22;
          v113 = &v41;
          v114 = 1;
          RequestId = EnterpriseDB::InsertRecord(DBInstance, 1, &v64, 17);
          if ( RequestId >= 0 )
          {
            v34 = (EnterpriseWorkerThread *)tlx::_LazyImpl<EnterpriseWorkerThread,tlx::lazy_construct<EnterpriseWorkerThread>,tlx::static_lazy<EnterpriseWorkerThread,0,tlx::lazy_construct<EnterpriseWorkerThread>>>::get();
            RequestId = EnterpriseWorkerThread::Wakeup(v34);
          }
        }
      }
    }
  }
LABEL_70:
  if ( v53 >= 8 )
    operator delete((void *)lpNewFileName[0]);
  return (unsigned int)RequestId;
}

```

## disassembly

```asm
0x18001a704  mov     [rsp-8+arg_10], rbx
0x18001a709  push    rbp
0x18001a70a  push    rsi
0x18001a70b  push    rdi
0x18001a70c  push    r12
0x18001a70e  push    r13
0x18001a710  push    r14
0x18001a712  push    r15
0x18001a714  lea     rbp, [rsp-260h]
0x18001a71c  sub     rsp, 360h
0x18001a723  mov     rax, cs:__security_cookie
0x18001a72a  xor     rax, rsp
0x18001a72d  mov     [rbp+290h+var_40], rax
0x18001a734  mov     [rbp+290h+var_308], r9
0x18001a738  mov     rbx, r8
0x18001a73b  mov     [rsp+390h+var_318], rbx
0x18001a740  mov     r12, rdx
0x18001a743  mov     r14, rcx
0x18001a746  mov     rsi, [rbp+290h+Buf1]
0x18001a74d  mov     [rbp+290h+var_310], rsi
0x18001a751  mov     r15, [rbp+290h+arg_40]
0x18001a758  xor     edx, edx; Val
0x18001a75a  mov     r8d, 220h; Size
0x18001a760  lea     rcx, [rbp+290h+var_268]; void *
0x18001a764  call    memset_0
0x18001a769  mov     eax, 1
0x18001a76e  mov     [rsp+390h+var_35C], eax
0x18001a772  mov     [rsp+390h+var_348], eax
0x18001a776  xor     edi, edi
0x18001a778  mov     [rsp+390h+var_330], edi
0x18001a77c  mov     [rsp+390h+var_32C], edi
0x18001a780  mov     [rsp+390h+var_328], edi
0x18001a784  mov     qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18001a789  mov     [rsp+390h+var_324], eax
0x18001a78d  mov     [rsp+390h+var_360], dil
0x18001a792  mov     [rbp+290h+var_2E0], 7
0x18001a79a  mov     [rbp+290h+var_2E8], rdi
0x18001a79e  mov     word ptr [rbp+290h+lpNewFileName], di
0x18001a7a2  xor     r8d, r8d
0x18001a7a5  lea     rdx, Src; Src
0x18001a7ac  lea     rcx, [rbp+290h+lpNewFileName]; void *
0x18001a7b0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001a7b5  nop
0x18001a7b6  mov     [rsp+390h+var_358], edi
0x18001a7ba  mov     [rsp+390h+var_350], edi
0x18001a7be  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001a7c5  movdqu  xmmword ptr [rbp+290h+bstrString], xmm0
0x18001a7ca  mov     [rsp+390h+var_344], edi
0x18001a7ce  test    r14, r14
0x18001a7d1  jnz     short loc_18001A7DD
0x18001a7d3  mov     ebx, 80070057h
0x18001a7d8  jmp     loc_18001AD95
0x18001a7dd  test    rbx, rbx
0x18001a7e0  jz      short loc_18001A7D3
0x18001a7e2  mov     r13, [rbp+290h+arg_30]
0x18001a7e9  test    r13, r13
0x18001a7ec  jz      short loc_18001A7D3
0x18001a7ee  test    r15, r15
0x18001a7f1  jz      short loc_18001A7D3
0x18001a7f3  mov     ecx, 81Ch; unsigned int
0x18001a7f8  call    ?SQMIncrement@@YAXKK@Z; SQMIncrement(ulong,ulong)
0x18001a7fd  mov     edi, [rbp+290h+arg_38]
0x18001a803  xor     ebx, ebx
0x18001a805  test    edi, edi
0x18001a807  jz      short loc_18001A80D
0x18001a809  mov     [rsp+390h+var_35C], ebx
0x18001a80d  call    ?GetDBInstance@EnterpriseConfig@@SAPEAVEnterpriseDB@@XZ; EnterpriseConfig::GetDBInstance(void)
0x18001a812  mov     [rbp+290h+var_300], rax
0x18001a816  test    rax, rax
0x18001a819  jnz     short loc_18001A825
0x18001a81b  mov     ebx, 8007000Eh
0x18001a820  jmp     loc_18001AD95
0x18001a825  mov     rcx, r15; struct _GUID *
0x18001a828  call    ?GenerateRequestId@EnterpriseConfig@@SAJPEAU_GUID@@@Z; EnterpriseConfig::GenerateRequestId(_GUID *)
0x18001a82d  mov     ebx, eax
0x18001a82f  test    eax, eax
0x18001a831  js      loc_18001AD95
0x18001a837  lea     rcx, [rsp+390h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a83c  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a842  lea     rdx, [rsp+390h+var_350]; unsigned int *
0x18001a847  lea     rcx, [rsp+390h+var_358]; unsigned int *
0x18001a84c  call    ?PurgeXAPRequestTable@EnrollmentManager@@SAJPEAK0@Z; EnrollmentManager::PurgeXAPRequestTable(ulong *,ulong *)
0x18001a851  mov     ebx, eax
0x18001a853  test    eax, eax
0x18001a855  js      loc_18001AD95
0x18001a85b  cmp     [rsp+390h+var_358], 19h
0x18001a860  jbe     short loc_18001A86C
0x18001a862  mov     ebx, 80004005h
0x18001a867  jmp     loc_18001AD95
0x18001a86c  xor     ebx, ebx
0x18001a86e  test    edi, edi
0x18001a870  jz      short loc_18001A89F
0x18001a872  cmp     [rsp+390h+var_350], ebx
0x18001a876  jbe     short loc_18001A89F
0x18001a878  lea     edi, [rbx+2]
0x18001a87b  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, dil
0x18001a882  jz      short loc_18001A862
0x18001a884  mov     r9d, 80004005h
0x18001a88a  lea     r8, aEnrollmentmana_1; "EnrollmentManager::InstallApplication- "...
0x18001a891  lea     rdx, EnterpriseAppMgmtSvcError
0x18001a898  call    McTemplateU0zq_EventWriteTransfer
0x18001a89d  jmp     short loc_18001A862
0x18001a89f  mov     r8d, 10h; Size
0x18001a8a5  lea     rdx, GUID_NULL; Buf2
0x18001a8ac  mov     rcx, rsi; Buf1
0x18001a8af  call    memcmp_0
0x18001a8b4  mov     edi, 2
0x18001a8b9  lea     r8, [rbp+290h+bstrString]; struct _GUID *
0x18001a8bd  lea     rdx, [rsp+390h+var_348]; enum _ENTERPRISE_APP_INSTALL_STATE *
0x18001a8c2  test    eax, eax
0x18001a8c4  jz      short loc_18001A8DB
0x18001a8c6  movaps  xmm0, xmmword ptr [rsi]
0x18001a8c9  movdqa  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001a8cf  lea     rcx, [rsp+390h+rguid]; Buf2
0x18001a8d4  call    ?GetInstallationStateOfProductId@EnrollmentManager@@SAJU_GUID@@PEAW4_ENTERPRISE_APP_INSTALL_STATE@@PEAU2@@Z; EnrollmentManager::GetInstallationStateOfProductId(_GUID,_ENTERPRISE_APP_INSTALL_STATE *,_GUID *)
0x18001a8d9  jmp     short loc_18001A8E3
0x18001a8db  mov     rcx, r14; String2
0x18001a8de  call    ?GetInstallationStateOfRemoteUri@EnrollmentManager@@SAJPEBGPEAW4_ENTERPRISE_APP_INSTALL_STATE@@PEAU_GUID@@@Z; EnrollmentManager::GetInstallationStateOfRemoteUri(ushort const *,_ENTERPRISE_APP_INSTALL_STATE *,_GUID *)
0x18001a8e3  test    eax, eax
0x18001a8e5  jnz     loc_18001A96B
0x18001a8eb  mov     eax, [rsp+390h+var_348]
0x18001a8ef  add     eax, 0FFFFFFFBh
0x18001a8f2  cmp     eax, edi
0x18001a8f4  jbe     short loc_18001A946
0x18001a8f6  mov     [rbp+290h+bstrString], rbx
0x18001a8fa  movaps  xmm0, xmmword ptr [rsi]
0x18001a8fd  movdqa  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001a903  lea     rdx, [rbp+290h+bstrString]; unsigned __int16 **
0x18001a907  lea     rcx, [rsp+390h+rguid]; rguid
0x18001a90c  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x18001a911  mov     ebx, eax
0x18001a913  test    eax, eax
0x18001a915  jns     short loc_18001A926
0x18001a917  mov     rcx, [rbp+290h+bstrString]; bstrString
0x18001a91b  call    cs:__imp_SysFreeString
0x18001a921  jmp     loc_18001AD95
0x18001a926  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 20h
0x18001a92d  jz      short loc_18001A93F
0x18001a92f  mov     r8, [rbp+290h+bstrString]
0x18001a933  lea     rdx, EnterpriseAppMgmtXapRequestAlreadyInProgress
0x18001a93a  call    McTemplateU0z_EventWriteTransfer
0x18001a93f  mov     ebx, 80070149h
0x18001a944  jmp     short loc_18001A917
0x18001a946  movaps  xmm0, xmmword ptr [rbp+290h+bstrString]
0x18001a94a  movdqa  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001a950  lea     rdx, [rsp+390h+rguid]
0x18001a955  mov     ecx, 1
0x18001a95a  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x18001a95f  mov     ebx, eax
0x18001a961  test    eax, eax
0x18001a963  js      loc_18001AD95
0x18001a969  xor     ebx, ebx
0x18001a96b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001a96f  test    r12, r12
0x18001a972  jz      loc_18001AA2F
0x18001a978  mov     rax, rsi
0x18001a97b  inc     rax
0x18001a97e  cmp     [r12+rax*2], bx
0x18001a983  jnz     short loc_18001A97B
0x18001a985  test    rax, rax
0x18001a988  jz      loc_18001AA2F
0x18001a98e  movups  xmm0, xmmword ptr [r15]
0x18001a992  movdqu  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001a998  mov     r8d, 4
0x18001a99e  lea     rdx, [rbp+290h+lpNewFileName]; void *
0x18001a9a2  lea     rcx, [rsp+390h+rguid]; rclsid
0x18001a9a7  call    ?GenerateDestinationFileName@@YAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EnterpriseFileType@@@Z; GenerateDestinationFileName(_GUID,std::wstring &,EnterpriseFileType)
0x18001a9ac  mov     ebx, eax
0x18001a9ae  test    eax, eax
0x18001a9b0  js      loc_18001AD95
0x18001a9b6  lea     rcx, [rbp+290h+lpNewFileName]
0x18001a9ba  mov     ebx, 8
0x18001a9bf  cmp     [rbp+290h+var_2E0], rbx
0x18001a9c3  cmovnb  rcx, [rbp+290h+lpNewFileName]; lpFileName
0x18001a9c8  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x18001a9cd  test    eax, eax
0x18001a9cf  jns     short loc_18001A9F0
0x18001a9d1  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, dil
0x18001a9d8  jz      short loc_18001A9F0
0x18001a9da  mov     r9d, eax
0x18001a9dd  lea     r8, aDeletelocalfil_0; "DeleteLocalFile Failed"
0x18001a9e4  lea     rdx, EnterpriseAppMgmtSvcError
0x18001a9eb  call    McTemplateU0zq_EventWriteTransfer
0x18001a9f0  lea     rdx, [rbp+290h+lpNewFileName]
0x18001a9f4  cmp     [rbp+290h+var_2E0], rbx
0x18001a9f8  cmovnb  rdx, [rbp+290h+lpNewFileName]
0x18001a9fd  mov     rcx, r12
0x18001aa00  call    cs:__imp_DSCopyFromSharedFile
0x18001aa06  mov     ebx, eax
0x18001aa08  test    eax, eax
0x18001aa0a  js      loc_18001AD95
0x18001aa10  mov     ecx, [rsp+390h+var_35C]
0x18001aa14  xor     ebx, ebx
0x18001aa16  test    ecx, ecx
0x18001aa18  jz      loc_18001AABA
0x18001aa1e  lea     ecx, [rbx+3]
0x18001aa21  mov     [rsp+390h+var_35C], ecx
0x18001aa25  mov     [rsp+390h+var_360], 32h ; '2'
0x18001aa2a  jmp     loc_18001AABA
0x18001aa2f  mov     rcx, r14; pwszUrl
0x18001aa32  call    ?RemoteUrl@@YAHPEBG@Z; RemoteUrl(ushort const *)
0x18001aa37  test    eax, eax
0x18001aa39  jnz     short loc_18001AAB6
0x18001aa3b  lea     rdx, [rsp+390h+var_344]; enum EnterpriseFileType *
0x18001aa40  mov     rcx, r14; unsigned __int16 *
0x18001aa43  call    ?DetermineInstallFileType@@YAJPEBGPEAW4EnterpriseFileType@@@Z; DetermineInstallFileType(ushort const *,EnterpriseFileType *)
0x18001aa48  mov     ebx, eax
0x18001aa4a  test    eax, eax
0x18001aa4c  js      loc_18001AD95
0x18001aa52  movups  xmm0, xmmword ptr [r15]
0x18001aa56  movdqu  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001aa5c  mov     r8d, [rsp+390h+var_344]
0x18001aa61  lea     rdx, [rbp+290h+lpNewFileName]; void *
0x18001aa65  lea     rcx, [rsp+390h+rguid]; rclsid
0x18001aa6a  call    ?GenerateDestinationFileName@@YAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EnterpriseFileType@@@Z; GenerateDestinationFileName(_GUID,std::wstring &,EnterpriseFileType)
0x18001aa6f  mov     ebx, eax
0x18001aa71  test    eax, eax
0x18001aa73  js      loc_18001AD95
0x18001aa79  lea     rdx, [rbp+290h+lpNewFileName]
0x18001aa7d  cmp     [rbp+290h+var_2E0], 8
0x18001aa82  cmovnb  rdx, [rbp+290h+lpNewFileName]; lpNewFileName
0x18001aa87  xor     r8d, r8d; bFailIfExists
0x18001aa8a  mov     rcx, r14; lpExistingFileName
0x18001aa8d  call    cs:__imp_CopyFileW
0x18001aa93  cmp     eax, 1
0x18001aa96  jz      short loc_18001AAB4
0x18001aa98  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, dil
0x18001aa9f  jz      loc_18001A862
0x18001aaa5  mov     r9d, ebx
0x18001aaa8  lea     r8, aCopyfilewFaile; "CopyFileW Failed"
0x18001aaaf  jmp     loc_18001A891
0x18001aab4  xor     ebx, ebx
0x18001aab6  mov     ecx, [rsp+390h+var_35C]
0x18001aaba  mov     r12d, 5
0x18001aac0  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 10h
0x18001aac7  jz      short loc_18001AB2F
0x18001aac9  movzx   eax, [rsp+390h+var_360]
0x18001aace  mov     dword ptr [rbp+290h+bstrString], eax
0x18001aad1  mov     [rsp+390h+var_358], ebx
0x18001aad5  mov     [rsp+390h+var_350], ecx
0x18001aad9  mov     [rbp+290h+var_2B0], r15
0x18001aadd  mov     [rbp+290h+var_2A8], 10h
0x18001aae5  lea     rax, [rsp+390h+var_350]
0x18001aaea  mov     [rbp+290h+var_2A0], rax
0x18001aaee  mov     [rbp+290h+var_298], 4
0x18001aaf6  lea     rax, [rsp+390h+var_358]
0x18001aafb  mov     [rbp+290h+var_290], rax
0x18001aaff  mov     [rbp+290h+var_288], 4
0x18001ab07  lea     rax, [rbp+290h+bstrString]
0x18001ab0b  mov     [rbp+290h+var_280], rax
0x18001ab0f  mov     [rbp+290h+var_278], 4
0x18001ab17  lea     rax, [rbp+290h+var_2C0]
0x18001ab1b  mov     [rsp+390h+var_370], rax
0x18001ab20  mov     r9d, r12d
0x18001ab23  lea     rdx, EnterpriseAppMgmtSvcXapStateChange
0x18001ab2a  call    McGenEventWrite_EventWriteTransfer
0x18001ab2f  mov     [rbp+290h+var_270], bx
0x18001ab33  mov     [rbp+290h+var_268], r15
0x18001ab37  mov     [rbp+290h+var_260], 10h
0x18001ab3e  mov     r8d, 4
0x18001ab44  mov     [rbp+290h+var_258], r8w
0x18001ab49  lea     rax, [rsp+390h+var_330]
0x18001ab4e  mov     [rbp+290h+var_250], rax
0x18001ab52  lea     edx, [r8-3]
0x18001ab56  mov     [rbp+290h+var_248], edx
0x18001ab59  mov     [rbp+290h+var_240], dx
0x18001ab5d  lea     rax, [rsp+390h+SystemTimeAsFileTime]
0x18001ab62  mov     [rbp+290h+var_238], rax
0x18001ab66  lea     r9d, [r8+4]
0x18001ab6a  mov     [rbp+290h+var_230], r9d
0x18001ab6e  mov     [rbp+290h+var_228], di
0x18001ab72  lea     rax, [rsp+390h+SystemTimeAsFileTime]
0x18001ab77  mov     [rbp+290h+var_220], rax
0x18001ab7b  mov     [rbp+290h+var_218], r9d
0x18001ab7f  mov     [rbp+290h+var_210], r12w
0x18001ab87  mov     [rbp+290h+var_208], r14
0x18001ab8e  mov     rax, rsi
0x18001ab91  inc     rax
0x18001ab94  cmp     [r14+rax*2], bx
0x18001ab99  jnz     short loc_18001AB91
0x18001ab9b  lea     eax, ds:2[rax*2]
0x18001aba2  mov     [rbp+290h+var_200], eax
0x18001aba8  mov     eax, 6
0x18001abad  mov     [rbp+290h+var_1F8], ax
0x18001abb4  lea     rax, [rbp+290h+lpNewFileName]
0x18001abb8  cmp     [rbp+290h+var_2E0], r9
0x18001abbc  cmovnb  rax, [rbp+290h+lpNewFileName]
0x18001abc1  mov     [rbp+290h+var_1F0], rax
0x18001abc8  lea     rcx, [rbp+290h+lpNewFileName]
0x18001abcc  cmovnb  rcx, [rbp+290h+lpNewFileName]
0x18001abd1  mov     rax, rsi
0x18001abd4  inc     rax
0x18001abd7  cmp     [rcx+rax*2], bx
0x18001abdb  jnz     short loc_18001ABD4
0x18001abdd  lea     eax, ds:2[rax*2]
0x18001abe4  mov     [rbp+290h+var_1E8], eax
0x18001abea  mov     eax, 7
0x18001abef  mov     [rbp+290h+var_1E0], ax
0x18001abf6  lea     rax, [rsp+390h+var_35C]
0x18001abfb  mov     [rbp+290h+var_1D8], rax
  ... truncated ...
```
