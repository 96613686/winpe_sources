# EnrollmentManager::InstallApplication(ushort *,ushort *,ushort *,ushort *,_GUID,_GUID,ushort *,int,_GUID *)

- ea: `0x18001b9f4`
- end: `0x18001c0e5`
- name: `?InstallApplication@EnrollmentManager@@SAJPEAG000U_GUID@@10HPEAU2@@Z`
- size: `1777`
- prototype: `__int64 __usercall@<rax>(wchar_t *String2@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, struct _GUID *Buf1, struct _GUID *, unsigned __int16 *, int, struct _GUID *)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180007d30`
- `0x180013dd8`

## callees

- `0x1800069dc`
- `0x180006a3c`
- `0x180006ac0`
- `0x180014684`
- `0x18001954c`
- `0x18001ac50`
- `0x18001b69c`
- `0x18001b7fc`
- `0x18001b9f4`
- `0x18001c0ec`
- `0x18001d160`
- `0x180029910`
- `0x180029b94`
- `0x180029e60`
- `0x180029ed0`
- `0x18002a2e0`
- `0x18002aac8`
- `0x18002c194`
- `0x18003153c`
- `0x180034348`
- `0x18006c8c6`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001c0ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c0ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc11`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb2c`
- `dsclient!DSCopyFromSharedFile` at `0x18001bcfc`
- `dsclient!DSCopyFromSharedFile` at `0x18001bcfc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001bd93`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001bd93`

## string_xrefs

- `0x18001bcd9`: `DeleteLocalFile Failed`
- `0x18001bb80`: `EnrollmentManager::InstallApplication- Cannot have more than one queued active install request that is waiting on user confirmation.`
- `0x18001bdb4`: `CopyFileW Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  LPCWSTR *v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rcx
  const WCHAR *v28; // rdx
  __int64 v29; // rax
  LPCWSTR *v30; // rax
  LPCWSTR *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  EnterpriseWorkerThread *v36; // rax
  unsigned __int8 v38; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v39; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v40; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+4Ch] [rbp-B4h] BYREF
  GUID rguid; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+64h] [rbp-9Ch] BYREF
  int v47; // [rsp+68h] [rbp-98h] BYREF
  int v48; // [rsp+6Ch] [rbp-94h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v50; // [rsp+78h] [rbp-88h]
  struct _GUID *v51; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v52; // [rsp+88h] [rbp-78h]
  struct EnterpriseDB *DBInstance; // [rsp+90h] [rbp-70h]
  LPCWSTR lpNewFileName[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v55; // [rsp+B0h] [rbp-50h]
  BSTR bstrString[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID *v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  unsigned int *v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  unsigned int *v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  BSTR *v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  __int16 v65; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID *v66; // [rsp+128h] [rbp+28h] BYREF
  int v67; // [rsp+130h] [rbp+30h]
  __int16 v68; // [rsp+138h] [rbp+38h]
  int *v69; // [rsp+140h] [rbp+40h]
  int v70; // [rsp+148h] [rbp+48h]
  __int16 v71; // [rsp+150h] [rbp+50h]
  struct _FILETIME *p_SystemTimeAsFileTime; // [rsp+158h] [rbp+58h]
  int v73; // [rsp+160h] [rbp+60h]
  __int16 v74; // [rsp+168h] [rbp+68h]
  struct _FILETIME *v75; // [rsp+170h] [rbp+70h]
  int v76; // [rsp+178h] [rbp+78h]
  __int16 v77; // [rsp+180h] [rbp+80h]
  wchar_t *v78; // [rsp+188h] [rbp+88h]
  int v79; // [rsp+190h] [rbp+90h]
  __int16 v80; // [rsp+198h] [rbp+98h]
  LPCWSTR *v81; // [rsp+1A0h] [rbp+A0h]
  int v82; // [rsp+1A8h] [rbp+A8h]
  __int16 v83; // [rsp+1B0h] [rbp+B0h]
  unsigned int *v84; // [rsp+1B8h] [rbp+B8h]
  int v85; // [rsp+1C0h] [rbp+C0h]
  __int16 v86; // [rsp+1C8h] [rbp+C8h]
  int *v87; // [rsp+1D0h] [rbp+D0h]
  int v88; // [rsp+1D8h] [rbp+D8h]
  __int16 v89; // [rsp+1E0h] [rbp+E0h]
  int *v90; // [rsp+1E8h] [rbp+E8h]
  int v91; // [rsp+1F0h] [rbp+F0h]
  __int16 v92; // [rsp+1F8h] [rbp+F8h]
  int *v93; // [rsp+200h] [rbp+100h]
  int v94; // [rsp+208h] [rbp+108h]
  __int16 v95; // [rsp+210h] [rbp+110h]
  unsigned __int16 *v96; // [rsp+218h] [rbp+118h]
  int v97; // [rsp+220h] [rbp+120h]
  __int16 v98; // [rsp+228h] [rbp+128h]
  struct _GUID *v99; // [rsp+230h] [rbp+130h]
  int v100; // [rsp+238h] [rbp+138h]
  __int16 v101; // [rsp+240h] [rbp+140h]
  unsigned __int16 *v102; // [rsp+248h] [rbp+148h]
  int v103; // [rsp+250h] [rbp+150h]
  __int16 v104; // [rsp+258h] [rbp+158h]
  unsigned __int8 *v105; // [rsp+260h] [rbp+160h]
  int v106; // [rsp+268h] [rbp+168h]
  __int16 v107; // [rsp+270h] [rbp+170h]
  struct _GUID *v108; // [rsp+278h] [rbp+178h]
  int v109; // [rsp+280h] [rbp+180h]
  __int16 v110; // [rsp+288h] [rbp+188h]
  unsigned __int16 *v111; // [rsp+290h] [rbp+190h]
  int v112; // [rsp+298h] [rbp+198h]
  __int16 v113; // [rsp+2A0h] [rbp+1A0h]
  int *v114; // [rsp+2A8h] [rbp+1A8h]
  int v115; // [rsp+2B0h] [rbp+1B0h]

  v52 = a4;
  v50 = a3;
  v51 = Buf1;
  memset_0(&v66, 0, 0x220u);
  v39 = 1;
  v42 = 1;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  SystemTimeAsFileTime = 0;
  v48 = 1;
  v38 = 0;
  v55 = 7;
  lpNewFileName[2] = 0;
  LOWORD(lpNewFileName[0]) = 0;
  std::wstring::assign(lpNewFileName, (void *)&Src);
  v40 = 0;
  v41 = 0;
  *(GUID *)bstrString = GUID_NULL;
  v43 = 0;
  if ( !String2 || !a3 || !a7 || !a9 )
  {
    RequestId = -2147024809;
    goto LABEL_70;
  }
  SQMIncrement(0x81Cu, v12);
  v39 = a8 == 0;
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
    RequestId = EnrollmentManager::PurgeXAPRequestTable(&v40, &v41);
    if ( RequestId >= 0 )
    {
      if ( v40 > 0x19 )
      {
LABEL_11:
        RequestId = -2147467259;
        goto LABEL_70;
      }
      if ( a8 && v41 )
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
                                         (enum _ENTERPRISE_APP_INSTALL_STATE *)&v42,
                                         (struct _GUID *)bstrString);
      }
      else
      {
        rguid = *Buf1;
        InstallationStateOfRemoteUri = EnrollmentManager::GetInstallationStateOfProductId(
                                         &rguid,
                                         (enum _ENTERPRISE_APP_INSTALL_STATE *)&v42,
                                         (struct _GUID *)bstrString);
      }
      if ( !InstallationStateOfRemoteUri )
      {
        if ( (unsigned int)(v42 - 5) > 2 )
        {
          bstrString[0] = 0;
          rguid = *Buf1;
          RequestId = ConvertGuidToBstr(&rguid, bstrString);
          if ( RequestId >= 0 )
          {
            if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x20) != 0 )
              McTemplateU0z_EventWriteTransfer(v19, EnterpriseAppMgmtXapRequestAlreadyInProgress, bstrString[0]);
            RequestId = -2147024567;
          }
          SysFreeString(bstrString[0]);
          goto LABEL_70;
        }
        rguid = *(GUID *)bstrString;
        RequestId = EnrollmentManager::DeleteRecord(1, &rguid, v18);
        if ( RequestId < 0 )
          goto LABEL_70;
      }
      v20 = -1;
      if ( !a2 )
        goto LABEL_75;
      v21 = -1;
      do
        ++v21;
      while ( a2[v21] );
      if ( !v21 )
      {
LABEL_75:
        if ( !(unsigned int)RemoteUrl(String2) )
        {
          RequestId = DetermineInstallFileType(String2, (enum EnterpriseFileType *)&v43);
          if ( RequestId < 0 )
            goto LABEL_70;
          rguid = *a9;
          RequestId = GenerateDestinationFileName(&rguid, lpNewFileName);
          if ( RequestId < 0 )
            goto LABEL_70;
          v28 = (const WCHAR *)lpNewFileName;
          if ( v55 >= 8 )
            v28 = lpNewFileName[0];
          if ( !CopyFileW(String2, v28, 0) )
          {
            if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
              goto LABEL_11;
            v15 = (unsigned int)RequestId;
            v16 = L"CopyFileW Failed";
            goto LABEL_16;
          }
        }
        v27 = v39;
        goto LABEL_52;
      }
      rguid = *a9;
      RequestId = GenerateDestinationFileName(&rguid, lpNewFileName);
      if ( RequestId >= 0 )
      {
        v22 = (const WCHAR *)lpNewFileName;
        if ( v55 >= 8 )
          v22 = lpNewFileName[0];
        v23 = DeleteLocalFile(v22);
        if ( v23 < 0 && (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            v24,
            EnterpriseAppMgmtSvcError,
            L"DeleteLocalFile Failed",
            (unsigned int)v23);
        v25 = lpNewFileName;
        if ( v55 >= 8 )
          v25 = (LPCWSTR *)lpNewFileName[0];
        RequestId = DSCopyFromSharedFile(a2, v25);
        if ( RequestId >= 0 )
        {
          v27 = v39;
          if ( v39 )
          {
            v27 = 3;
            v39 = 3;
            v38 = 50;
          }
LABEL_52:
          if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x10) != 0 )
          {
            LODWORD(bstrString[0]) = v38;
            v40 = 0;
            v41 = v27;
            v57 = a9;
            v58 = 16;
            v59 = &v41;
            v60 = 4;
            v61 = &v40;
            v62 = 4;
            v63 = bstrString;
            v64 = 4;
            McGenEventWrite_EventWriteTransfer(v27, EnterpriseAppMgmtSvcXapStateChange, v26, 5);
          }
          v65 = 0;
          v66 = a9;
          v67 = 16;
          v68 = 4;
          v69 = &v45;
          v70 = 1;
          v71 = 1;
          p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
          v73 = 8;
          v74 = 2;
          v75 = &SystemTimeAsFileTime;
          v76 = 8;
          v77 = 5;
          v78 = String2;
          v29 = -1;
          do
            ++v29;
          while ( String2[v29] );
          v79 = 2 * v29 + 2;
          v80 = 6;
          v30 = lpNewFileName;
          if ( v55 >= 8 )
            v30 = (LPCWSTR *)lpNewFileName[0];
          v81 = v30;
          v31 = lpNewFileName;
          if ( v55 >= 8 )
            v31 = (LPCWSTR *)lpNewFileName[0];
          v32 = -1;
          do
            ++v32;
          while ( *((_WORD *)v31 + v32) );
          v82 = 2 * v32 + 2;
          v83 = 7;
          v84 = &v39;
          v85 = 1;
          v86 = 8;
          v87 = &v46;
          v88 = 4;
          v89 = 10;
          v90 = &v47;
          v91 = 4;
          v92 = 11;
          v93 = &v48;
          v94 = 1;
          v95 = 12;
          v96 = v50;
          v33 = -1;
          do
            ++v33;
          while ( v50[v33] );
          v97 = 2 * v33 + 2;
          v98 = 13;
          v99 = v51;
          v100 = 16;
          v101 = 14;
          v102 = a7;
          v34 = -1;
          do
            ++v34;
          while ( a7[v34] );
          v103 = 2 * v34 + 2;
          v104 = 15;
          v105 = &v38;
          v106 = 1;
          v107 = 3;
          v108 = a6;
          v109 = 16;
          v110 = 21;
          v111 = v52;
          do
            ++v20;
          while ( v52[v20] );
          v112 = 2 * v20 + 2;
          v113 = 22;
          v114 = &v43;
          v115 = 1;
          RequestId = EnterpriseDB::InsertRecord((__int64)DBInstance, 1, (__int64)&v65, 0x11u);
          if ( RequestId >= 0 )
          {
            v36 = (EnterpriseWorkerThread *)tlx::_LazyImpl<EnterpriseWorkerThread,tlx::lazy_construct<EnterpriseWorkerThread>,tlx::static_lazy<EnterpriseWorkerThread,0,tlx::lazy_construct<EnterpriseWorkerThread>>>::get(v35);
            RequestId = EnterpriseWorkerThread::Wakeup(v36);
          }
        }
      }
    }
  }
LABEL_70:
  if ( v55 >= 8 )
    operator delete((void *)lpNewFileName[0]);
  return (unsigned int)RequestId;
}

```

## disassembly

```asm
0x18001b9f4  mov     [rsp-8+arg_10], rbx
0x18001b9f9  push    rbp
0x18001b9fa  push    rsi
0x18001b9fb  push    rdi
0x18001b9fc  push    r12
0x18001b9fe  push    r13
0x18001ba00  push    r14
0x18001ba02  push    r15
0x18001ba04  lea     rbp, [rsp-260h]
0x18001ba0c  sub     rsp, 360h
0x18001ba13  mov     rax, cs:__security_cookie
0x18001ba1a  xor     rax, rsp
0x18001ba1d  mov     [rbp+290h+var_40], rax
0x18001ba24  mov     [rbp+290h+var_308], r9
0x18001ba28  mov     rbx, r8
0x18001ba2b  mov     [rsp+390h+var_318], rbx
0x18001ba30  mov     r12, rdx
0x18001ba33  mov     r14, rcx
0x18001ba36  mov     rsi, [rbp+290h+Buf1]
0x18001ba3d  mov     [rbp+290h+var_310], rsi
0x18001ba41  mov     r15, [rbp+290h+arg_40]
0x18001ba48  xor     edx, edx; Val
0x18001ba4a  mov     r8d, 220h; Size
0x18001ba50  lea     rcx, [rbp+290h+var_268]; void *
0x18001ba54  call    memset_0
0x18001ba59  mov     eax, 1
0x18001ba5e  mov     [rsp+390h+var_35C], eax
0x18001ba62  mov     [rsp+390h+var_348], eax
0x18001ba66  xor     edi, edi
0x18001ba68  mov     [rsp+390h+var_330], edi
0x18001ba6c  mov     [rsp+390h+var_32C], edi
0x18001ba70  mov     [rsp+390h+var_328], edi
0x18001ba74  mov     qword ptr [rsp+390h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18001ba79  mov     [rsp+390h+var_324], eax
0x18001ba7d  mov     [rsp+390h+var_360], dil
0x18001ba82  mov     [rbp+290h+var_2E0], 7
0x18001ba8a  mov     [rbp+290h+var_2E8], rdi
0x18001ba8e  mov     word ptr [rbp+290h+lpNewFileName], di
0x18001ba92  xor     r8d, r8d
0x18001ba95  lea     rdx, Src; Src
0x18001ba9c  lea     rcx, [rbp+290h+lpNewFileName]; void *
0x18001baa0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001baa5  nop
0x18001baa6  mov     [rsp+390h+var_358], edi
0x18001baaa  mov     [rsp+390h+var_350], edi
0x18001baae  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001bab5  movdqu  xmmword ptr [rbp+290h+bstrString], xmm0
0x18001baba  mov     [rsp+390h+var_344], edi
0x18001babe  test    r14, r14
0x18001bac1  jnz     short loc_18001BACD
0x18001bac3  mov     ebx, 80070057h
0x18001bac8  jmp     loc_18001C0A1
0x18001bacd  test    rbx, rbx
0x18001bad0  jz      short loc_18001BAC3
0x18001bad2  mov     r13, [rbp+290h+arg_30]
0x18001bad9  test    r13, r13
0x18001badc  jz      short loc_18001BAC3
0x18001bade  test    r15, r15
0x18001bae1  jz      short loc_18001BAC3
0x18001bae3  mov     ecx, 81Ch; unsigned int
0x18001bae8  call    ?SQMIncrement@@YAXKK@Z; SQMIncrement(ulong,ulong)
0x18001baed  mov     edi, [rbp+290h+arg_38]
0x18001baf3  xor     ebx, ebx
0x18001baf5  test    edi, edi
0x18001baf7  jz      short loc_18001BAFD
0x18001baf9  mov     [rsp+390h+var_35C], ebx
0x18001bafd  call    ?GetDBInstance@EnterpriseConfig@@SAPEAVEnterpriseDB@@XZ; EnterpriseConfig::GetDBInstance(void)
0x18001bb02  mov     [rbp+290h+var_300], rax
0x18001bb06  test    rax, rax
0x18001bb09  jnz     short loc_18001BB15
0x18001bb0b  mov     ebx, 8007000Eh
0x18001bb10  jmp     loc_18001C0A1
0x18001bb15  mov     rcx, r15; struct _GUID *
0x18001bb18  call    ?GenerateRequestId@EnterpriseConfig@@SAJPEAU_GUID@@@Z; EnterpriseConfig::GenerateRequestId(_GUID *)
0x18001bb1d  mov     ebx, eax
0x18001bb1f  test    eax, eax
0x18001bb21  js      loc_18001C0A1
0x18001bb27  lea     rcx, [rsp+390h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001bb2c  call    cs:__imp_GetSystemTimeAsFileTime
0x18001bb33  nop     dword ptr [rax+rax+00h]
0x18001bb38  lea     rdx, [rsp+390h+var_350]; unsigned int *
0x18001bb3d  lea     rcx, [rsp+390h+var_358]; unsigned int *
0x18001bb42  call    ?PurgeXAPRequestTable@EnrollmentManager@@SAJPEAK0@Z; EnrollmentManager::PurgeXAPRequestTable(ulong *,ulong *)
0x18001bb47  mov     ebx, eax
0x18001bb49  test    eax, eax
0x18001bb4b  js      loc_18001C0A1
0x18001bb51  cmp     [rsp+390h+var_358], 19h
0x18001bb56  jbe     short loc_18001BB62
0x18001bb58  mov     ebx, 80004005h
0x18001bb5d  jmp     loc_18001C0A1
0x18001bb62  xor     ebx, ebx
0x18001bb64  test    edi, edi
0x18001bb66  jz      short loc_18001BB95
0x18001bb68  cmp     [rsp+390h+var_350], ebx
0x18001bb6c  jbe     short loc_18001BB95
0x18001bb6e  lea     edi, [rbx+2]
0x18001bb71  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, dil
0x18001bb78  jz      short loc_18001BB58
0x18001bb7a  mov     r9d, 80004005h
0x18001bb80  lea     r8, aEnrollmentmana_1; "EnrollmentManager::InstallApplication- "...
0x18001bb87  lea     rdx, EnterpriseAppMgmtSvcError
0x18001bb8e  call    McTemplateU0zq_EventWriteTransfer
0x18001bb93  jmp     short loc_18001BB58
0x18001bb95  mov     r8d, 10h; Size
0x18001bb9b  lea     rdx, GUID_NULL; Buf2
0x18001bba2  mov     rcx, rsi; Buf1
0x18001bba5  call    memcmp_0
0x18001bbaa  mov     edi, 2
0x18001bbaf  lea     r8, [rbp+290h+bstrString]; struct _GUID *
0x18001bbb3  lea     rdx, [rsp+390h+var_348]; enum _ENTERPRISE_APP_INSTALL_STATE *
0x18001bbb8  test    eax, eax
0x18001bbba  jz      short loc_18001BBD1
0x18001bbbc  movaps  xmm0, xmmword ptr [rsi]
0x18001bbbf  movdqa  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001bbc5  lea     rcx, [rsp+390h+rguid]; Buf2
0x18001bbca  call    ?GetInstallationStateOfProductId@EnrollmentManager@@SAJU_GUID@@PEAW4_ENTERPRISE_APP_INSTALL_STATE@@PEAU2@@Z; EnrollmentManager::GetInstallationStateOfProductId(_GUID,_ENTERPRISE_APP_INSTALL_STATE *,_GUID *)
0x18001bbcf  jmp     short loc_18001BBD9
0x18001bbd1  mov     rcx, r14; String2
0x18001bbd4  call    ?GetInstallationStateOfRemoteUri@EnrollmentManager@@SAJPEBGPEAW4_ENTERPRISE_APP_INSTALL_STATE@@PEAU_GUID@@@Z; EnrollmentManager::GetInstallationStateOfRemoteUri(ushort const *,_ENTERPRISE_APP_INSTALL_STATE *,_GUID *)
0x18001bbd9  test    eax, eax
0x18001bbdb  jnz     loc_18001BC67
0x18001bbe1  mov     eax, [rsp+390h+var_348]
0x18001bbe5  add     eax, 0FFFFFFFBh
0x18001bbe8  cmp     eax, edi
0x18001bbea  jbe     short loc_18001BC42
0x18001bbec  mov     [rbp+290h+bstrString], rbx
0x18001bbf0  movaps  xmm0, xmmword ptr [rsi]
0x18001bbf3  movdqa  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001bbf9  lea     rdx, [rbp+290h+bstrString]; unsigned __int16 **
0x18001bbfd  lea     rcx, [rsp+390h+rguid]; rguid
0x18001bc02  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x18001bc07  mov     ebx, eax
0x18001bc09  test    eax, eax
0x18001bc0b  jns     short loc_18001BC22
0x18001bc0d  mov     rcx, [rbp+290h+bstrString]; bstrString
0x18001bc11  call    cs:__imp_SysFreeString
0x18001bc18  nop     dword ptr [rax+rax+00h]
0x18001bc1d  jmp     loc_18001C0A1
0x18001bc22  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 20h
0x18001bc29  jz      short loc_18001BC3B
0x18001bc2b  mov     r8, [rbp+290h+bstrString]
0x18001bc2f  lea     rdx, EnterpriseAppMgmtXapRequestAlreadyInProgress
0x18001bc36  call    McTemplateU0z_EventWriteTransfer
0x18001bc3b  mov     ebx, 80070149h
0x18001bc40  jmp     short loc_18001BC0D
0x18001bc42  movaps  xmm0, xmmword ptr [rbp+290h+bstrString]
0x18001bc46  movdqa  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001bc4c  lea     rdx, [rsp+390h+rguid]
0x18001bc51  mov     ecx, 1
0x18001bc56  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x18001bc5b  mov     ebx, eax
0x18001bc5d  test    eax, eax
0x18001bc5f  js      loc_18001C0A1
0x18001bc65  xor     ebx, ebx
0x18001bc67  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001bc6b  test    r12, r12
0x18001bc6e  jz      loc_18001BD31
0x18001bc74  mov     rax, rsi
0x18001bc77  inc     rax
0x18001bc7a  cmp     [r12+rax*2], bx
0x18001bc7f  jnz     short loc_18001BC77
0x18001bc81  test    rax, rax
0x18001bc84  jz      loc_18001BD31
0x18001bc8a  movups  xmm0, xmmword ptr [r15]
0x18001bc8e  movdqu  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001bc94  mov     r8d, 4
0x18001bc9a  lea     rdx, [rbp+290h+lpNewFileName]; void *
0x18001bc9e  lea     rcx, [rsp+390h+rguid]; rclsid
0x18001bca3  call    ?GenerateDestinationFileName@@YAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EnterpriseFileType@@@Z; GenerateDestinationFileName(_GUID,std::wstring &,EnterpriseFileType)
0x18001bca8  mov     ebx, eax
0x18001bcaa  test    eax, eax
0x18001bcac  js      loc_18001C0A1
0x18001bcb2  lea     rcx, [rbp+290h+lpNewFileName]
0x18001bcb6  mov     ebx, 8
0x18001bcbb  cmp     [rbp+290h+var_2E0], rbx
0x18001bcbf  cmovnb  rcx, [rbp+290h+lpNewFileName]; lpFileName
0x18001bcc4  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x18001bcc9  test    eax, eax
0x18001bccb  jns     short loc_18001BCEC
0x18001bccd  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, dil
0x18001bcd4  jz      short loc_18001BCEC
0x18001bcd6  mov     r9d, eax
0x18001bcd9  lea     r8, aDeletelocalfil_0; "DeleteLocalFile Failed"
0x18001bce0  lea     rdx, EnterpriseAppMgmtSvcError
0x18001bce7  call    McTemplateU0zq_EventWriteTransfer
0x18001bcec  lea     rdx, [rbp+290h+lpNewFileName]
0x18001bcf0  cmp     [rbp+290h+var_2E0], rbx
0x18001bcf4  cmovnb  rdx, [rbp+290h+lpNewFileName]
0x18001bcf9  mov     rcx, r12
0x18001bcfc  call    cs:__imp_DSCopyFromSharedFile
0x18001bd03  nop     dword ptr [rax+rax+00h]
0x18001bd08  mov     ebx, eax
0x18001bd0a  test    eax, eax
0x18001bd0c  js      loc_18001C0A1
0x18001bd12  mov     ecx, [rsp+390h+var_35C]
0x18001bd16  xor     ebx, ebx
0x18001bd18  test    ecx, ecx
0x18001bd1a  jz      loc_18001BDC6
0x18001bd20  lea     ecx, [rbx+3]
0x18001bd23  mov     [rsp+390h+var_35C], ecx
0x18001bd27  mov     [rsp+390h+var_360], 32h ; '2'
0x18001bd2c  jmp     loc_18001BDC6
0x18001bd31  mov     rcx, r14; pwszUrl
0x18001bd34  call    ?RemoteUrl@@YAHPEBG@Z; RemoteUrl(ushort const *)
0x18001bd39  test    eax, eax
0x18001bd3b  jnz     loc_18001BDC2
0x18001bd41  lea     rdx, [rsp+390h+var_344]; enum EnterpriseFileType *
0x18001bd46  mov     rcx, r14; unsigned __int16 *
0x18001bd49  call    ?DetermineInstallFileType@@YAJPEBGPEAW4EnterpriseFileType@@@Z; DetermineInstallFileType(ushort const *,EnterpriseFileType *)
0x18001bd4e  mov     ebx, eax
0x18001bd50  test    eax, eax
0x18001bd52  js      loc_18001C0A1
0x18001bd58  movups  xmm0, xmmword ptr [r15]
0x18001bd5c  movdqu  xmmword ptr [rsp+390h+rguid.Data1], xmm0
0x18001bd62  mov     r8d, [rsp+390h+var_344]
0x18001bd67  lea     rdx, [rbp+290h+lpNewFileName]; void *
0x18001bd6b  lea     rcx, [rsp+390h+rguid]; rclsid
0x18001bd70  call    ?GenerateDestinationFileName@@YAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4EnterpriseFileType@@@Z; GenerateDestinationFileName(_GUID,std::wstring &,EnterpriseFileType)
0x18001bd75  mov     ebx, eax
0x18001bd77  test    eax, eax
0x18001bd79  js      loc_18001C0A1
0x18001bd7f  lea     rdx, [rbp+290h+lpNewFileName]
0x18001bd83  cmp     [rbp+290h+var_2E0], 8
0x18001bd88  cmovnb  rdx, [rbp+290h+lpNewFileName]; lpNewFileName
0x18001bd8d  xor     r8d, r8d; bFailIfExists
0x18001bd90  mov     rcx, r14; lpExistingFileName
0x18001bd93  call    cs:__imp_CopyFileW
0x18001bd9a  nop     dword ptr [rax+rax+00h]
0x18001bd9f  cmp     eax, 1
0x18001bda2  jz      short loc_18001BDC0
0x18001bda4  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, dil
0x18001bdab  jz      loc_18001BB58
0x18001bdb1  mov     r9d, ebx
0x18001bdb4  lea     r8, aCopyfilewFaile; "CopyFileW Failed"
0x18001bdbb  jmp     loc_18001BB87
0x18001bdc0  xor     ebx, ebx
0x18001bdc2  mov     ecx, [rsp+390h+var_35C]
0x18001bdc6  mov     r12d, 5
0x18001bdcc  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 10h
0x18001bdd3  jz      short loc_18001BE3B
0x18001bdd5  movzx   eax, [rsp+390h+var_360]
0x18001bdda  mov     dword ptr [rbp+290h+bstrString], eax
0x18001bddd  mov     [rsp+390h+var_358], ebx
0x18001bde1  mov     [rsp+390h+var_350], ecx
0x18001bde5  mov     [rbp+290h+var_2B0], r15
0x18001bde9  mov     [rbp+290h+var_2A8], 10h
0x18001bdf1  lea     rax, [rsp+390h+var_350]
0x18001bdf6  mov     [rbp+290h+var_2A0], rax
0x18001bdfa  mov     [rbp+290h+var_298], 4
0x18001be02  lea     rax, [rsp+390h+var_358]
0x18001be07  mov     [rbp+290h+var_290], rax
0x18001be0b  mov     [rbp+290h+var_288], 4
0x18001be13  lea     rax, [rbp+290h+bstrString]
0x18001be17  mov     [rbp+290h+var_280], rax
0x18001be1b  mov     [rbp+290h+var_278], 4
0x18001be23  lea     rax, [rbp+290h+var_2C0]
0x18001be27  mov     [rsp+390h+var_370], rax
0x18001be2c  mov     r9d, r12d
0x18001be2f  lea     rdx, EnterpriseAppMgmtSvcXapStateChange
0x18001be36  call    McGenEventWrite_EventWriteTransfer
0x18001be3b  mov     [rbp+290h+var_270], bx
0x18001be3f  mov     [rbp+290h+var_268], r15
0x18001be43  mov     [rbp+290h+var_260], 10h
0x18001be4a  mov     r8d, 4
0x18001be50  mov     [rbp+290h+var_258], r8w
0x18001be55  lea     rax, [rsp+390h+var_330]
0x18001be5a  mov     [rbp+290h+var_250], rax
0x18001be5e  lea     edx, [r8-3]
0x18001be62  mov     [rbp+290h+var_248], edx
0x18001be65  mov     [rbp+290h+var_240], dx
0x18001be69  lea     rax, [rsp+390h+SystemTimeAsFileTime]
0x18001be6e  mov     [rbp+290h+var_238], rax
0x18001be72  lea     r9d, [r8+4]
0x18001be76  mov     [rbp+290h+var_230], r9d
0x18001be7a  mov     [rbp+290h+var_228], di
0x18001be7e  lea     rax, [rsp+390h+SystemTimeAsFileTime]
0x18001be83  mov     [rbp+290h+var_220], rax
0x18001be87  mov     [rbp+290h+var_218], r9d
0x18001be8b  mov     [rbp+290h+var_210], r12w
0x18001be93  mov     [rbp+290h+var_208], r14
0x18001be9a  mov     rax, rsi
0x18001be9d  inc     rax
0x18001bea0  cmp     [r14+rax*2], bx
0x18001bea5  jnz     short loc_18001BE9D
0x18001bea7  lea     eax, ds:2[rax*2]
0x18001beae  mov     [rbp+290h+var_200], eax
0x18001beb4  mov     eax, 6
0x18001beb9  mov     [rbp+290h+var_1F8], ax
0x18001bec0  lea     rax, [rbp+290h+lpNewFileName]
0x18001bec4  cmp     [rbp+290h+var_2E0], r9
0x18001bec8  cmovnb  rax, [rbp+290h+lpNewFileName]
0x18001becd  mov     [rbp+290h+var_1F0], rax
0x18001bed4  lea     rcx, [rbp+290h+lpNewFileName]
0x18001bed8  cmovnb  rcx, [rbp+290h+lpNewFileName]
0x18001bedd  mov     rax, rsi
0x18001bee0  inc     rax
0x18001bee3  cmp     [rcx+rax*2], bx
0x18001bee7  jnz     short loc_18001BEE0
0x18001bee9  lea     eax, ds:2[rax*2]
0x18001bef0  mov     [rbp+290h+var_1E8], eax
  ... truncated ...
```
