# AppManager::InstallPreLoadedApplication(ushort *,ushort *,ushort *,_GUID,_GUID,int,ushort *,ushort *,_GUID *)

- ea: `0x180013400`
- end: `0x180013a60`
- name: `?InstallPreLoadedApplication@AppManager@@QEAAJPEAG00U_GUID@@1H00PEAU2@@Z`
- size: `1632`
- prototype: `__int64 __fastcall(AppManager *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _GUID *, struct _GUID *, int, unsigned __int16 *, unsigned __int16 *, IID *rclsid)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004ec0`

## callees

- `0x180005de8`
- `0x1800067d8`
- `0x18000702c`
- `0x180012d54`
- `0x180013400`
- `0x180013bb0`
- `0x1800186dc`
- `0x1800199e4`
- `0x18001a3d4`
- `0x18001add8`
- `0x1800277d0`
- `0x180027a18`
- `0x180027cbc`
- `0x180027f30`
- `0x180027fe8`
- `0x180029f88`
- `0x18002eb84`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180013559`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180013559`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013a35`
- `OLEAUT32!__imp_SysFreeString` at `0x180013736`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a19`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a24`
- `OLEAUT32!__imp_SysFreeString` at `0x180013736`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a19`
- `OLEAUT32!__imp_SysFreeString` at `0x180013a24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001356d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001356d`
- `dsclient!DSCopyFromSharedFile` at `0x180013642`
- `dsclient!DSCopyFromSharedFile` at `0x18001365c`
- `dsclient!DSCopyFromSharedFile` at `0x180013642`
- `dsclient!DSCopyFromSharedFile` at `0x18001365c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppManager::InstallPreLoadedApplication(
        AppManager *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct _GUID *a5,
        struct _GUID *a6,
        int a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        IID *rclsid)
{
  OLECHAR *v13; // rbx
  int RequestId; // edi
  void **v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  EnterpriseWorkerThread *v22; // rax
  unsigned __int16 **v24; // [rsp+30h] [rbp-D0h]
  char v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+44h] [rbp-BCh] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+4Ch] [rbp-B4h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+5Ch] [rbp-A4h] BYREF
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-80h] BYREF
  DevPlat::Shared *v37; // [rsp+88h] [rbp-78h] BYREF
  GUID rguid; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v39; // [rsp+A0h] [rbp-60h] BYREF
  struct EnterpriseDB *DBInstance; // [rsp+B0h] [rbp-50h]
  struct _GUID v41; // [rsp+C0h] [rbp-40h] BYREF
  GUID v42; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v43; // [rsp+E0h] [rbp-20h] BYREF
  IID *v44; // [rsp+E8h] [rbp-18h] BYREF
  int v45; // [rsp+F0h] [rbp-10h]
  __int16 v46; // [rsp+F8h] [rbp-8h]
  struct _FILETIME *p_SystemTimeAsFileTime; // [rsp+100h] [rbp+0h]
  int v48; // [rsp+108h] [rbp+8h]
  __int16 v49; // [rsp+110h] [rbp+10h]
  struct _FILETIME *v50; // [rsp+118h] [rbp+18h]
  int v51; // [rsp+120h] [rbp+20h]
  __int16 v52; // [rsp+128h] [rbp+28h]
  __int64 v53; // [rsp+130h] [rbp+30h]
  int v54; // [rsp+138h] [rbp+38h]
  __int16 v55; // [rsp+140h] [rbp+40h]
  WCHAR *v56; // [rsp+148h] [rbp+48h]
  int v57; // [rsp+150h] [rbp+50h]
  __int16 v58; // [rsp+158h] [rbp+58h]
  int *v59; // [rsp+160h] [rbp+60h]
  int v60; // [rsp+168h] [rbp+68h]
  __int16 v61; // [rsp+170h] [rbp+70h]
  int *v62; // [rsp+178h] [rbp+78h]
  int v63; // [rsp+180h] [rbp+80h]
  __int16 v64; // [rsp+188h] [rbp+88h]
  int *v65; // [rsp+190h] [rbp+90h]
  int v66; // [rsp+198h] [rbp+98h]
  __int16 v67; // [rsp+1A0h] [rbp+A0h]
  int *v68; // [rsp+1A8h] [rbp+A8h]
  int v69; // [rsp+1B0h] [rbp+B0h]
  __int16 v70; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 *v71; // [rsp+1C0h] [rbp+C0h]
  int v72; // [rsp+1C8h] [rbp+C8h]
  __int16 v73; // [rsp+1D0h] [rbp+D0h]
  struct _GUID *v74; // [rsp+1D8h] [rbp+D8h]
  int v75; // [rsp+1E0h] [rbp+E0h]
  __int16 v76; // [rsp+1E8h] [rbp+E8h]
  char *v77; // [rsp+1F0h] [rbp+F0h]
  int v78; // [rsp+1F8h] [rbp+F8h]
  __int16 v79; // [rsp+200h] [rbp+100h]
  struct _GUID *v80; // [rsp+208h] [rbp+108h]
  int v81; // [rsp+210h] [rbp+110h]
  __int16 v82; // [rsp+218h] [rbp+118h]
  struct _GUID *v83; // [rsp+220h] [rbp+120h]
  int v84; // [rsp+228h] [rbp+128h]
  __int16 v85; // [rsp+230h] [rbp+130h]
  unsigned __int16 *v86; // [rsp+238h] [rbp+138h]
  int v87; // [rsp+240h] [rbp+140h]
  __int16 v88; // [rsp+248h] [rbp+148h]
  WCHAR *v89; // [rsp+250h] [rbp+150h]
  int v90; // [rsp+258h] [rbp+158h]
  __int16 v91; // [rsp+260h] [rbp+160h]
  int *v92; // [rsp+268h] [rbp+168h]
  int v93; // [rsp+270h] [rbp+170h]
  __int16 v94; // [rsp+278h] [rbp+178h]
  GUID *v95; // [rsp+280h] [rbp+180h]
  int v96; // [rsp+288h] [rbp+188h]
  __int16 v97; // [rsp+290h] [rbp+190h]
  int *v98; // [rsp+298h] [rbp+198h]
  int v99; // [rsp+2A0h] [rbp+1A0h]
  WCHAR FileName[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR v101[264]; // [rsp+520h] [rbp+420h] BYREF
  wchar_t Destination[264]; // [rsp+730h] [rbp+630h] BYREF

  *(_QWORD *)v39.Data4 = a2;
  memset_0(&v44, 0, 0x220u);
  v30 = 3;
  v26 = 1;
  v34 = 1;
  v31 = 0;
  v32 = 0;
  SystemTimeAsFileTime = 0;
  v33 = 1;
  v25 = 50;
  pv = 0;
  memset_0(Destination, 0, 0x208u);
  v28 = 260;
  memset_0(FileName, 0, 0x208u);
  memset_0(v101, 0, 0x208u);
  v41 = GUID_NULL;
  v42 = GUID_NULL;
  *(_QWORD *)&v39.Data1 = 0;
  rguid = GUID_NULL;
  v27 = 0;
  v13 = 0;
  v37 = 0;
  if ( !a2 || !a3 || !a4 || !a8 || !a9 || !rclsid )
  {
    RequestId = -2147024809;
    goto LABEL_42;
  }
  DBInstance = EnterpriseConfig::GetDBInstance();
  if ( !DBInstance )
  {
    RequestId = -2147024882;
    goto LABEL_42;
  }
  RequestId = EnterpriseConfig::GenerateRequestId(rclsid);
  if ( RequestId >= 0 )
  {
    v15 = tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
    RequestId = StringFromCLSID(rclsid, (LPOLESTR *)v15);
    if ( RequestId >= 0 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      RequestId = GetSharedFolder(Destination, &v28);
      if ( RequestId >= 0 )
      {
        RequestId = StringCchPrintfW(FileName, 0x104u, L"%s\\%s%s", Destination, pv, L".XAP");
        if ( RequestId >= 0 )
        {
          RequestId = StringCchPrintfW(v101, 0x104u, L"%s\\%s%s", Destination, pv, L".XML");
          if ( RequestId >= 0 )
          {
            RequestId = DeleteLocalFile(FileName);
            if ( RequestId >= 0 )
            {
              RequestId = DeleteLocalFile(v101);
              if ( RequestId >= 0 )
              {
                RequestId = DSCopyFromSharedFile(a3, FileName);
                if ( RequestId >= 0 )
                {
                  RequestId = DSCopyFromSharedFile(a9, v101);
                  if ( RequestId >= 0 )
                  {
                    RequestId = ATL::CComBSTR::Append((const void **)&v37, FileName);
                    v13 = (OLECHAR *)v37;
                    if ( RequestId >= 0 )
                    {
                      LODWORD(v24) = 0;
                      RequestId = GetEnterpriseInformationFromUnknownApplicationPackage(
                                    v37,
                                    &v41,
                                    &v39,
                                    0,
                                    0,
                                    (enum EnterpriseFileType *)&v27,
                                    v24);
                      if ( RequestId >= 0 )
                      {
                        RequestId = EnrollmentManager::PurgeXAPRequestTable((unsigned int *)bstrString, &v28);
                        if ( RequestId >= 0 )
                        {
                          *(struct _GUID *)bstrString = v41;
                          if ( !(unsigned int)EnrollmentManager::GetInstallationStateOfProductId(
                                                (struct _GUID *)bstrString,
                                                (enum _ENTERPRISE_APP_INSTALL_STATE *)&v26,
                                                &rguid) )
                          {
                            if ( (unsigned int)(v26 - 5) > 2 )
                            {
                              bstrString[0] = 0;
                              rguid = v41;
                              RequestId = ConvertGuidToBstr(&rguid, bstrString);
                              if ( RequestId >= 0 )
                              {
                                if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x20) != 0 )
                                  McTemplateU0z_EventWriteTransfer(
                                    v16,
                                    EnterpriseAppMgmtXapRequestAlreadyInProgress,
                                    bstrString[0]);
                                RequestId = -2147024567;
                              }
                              SysFreeString(bstrString[0]);
                              goto LABEL_42;
                            }
                            RequestId = EnrollmentManager::DeleteRecord(1u, (__int128 *)&rguid);
                            if ( RequestId < 0 )
                              goto LABEL_42;
                          }
                          v43 = 0;
                          v44 = rclsid;
                          v45 = 16;
                          v46 = 1;
                          p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
                          v48 = 8;
                          v49 = 2;
                          v50 = &SystemTimeAsFileTime;
                          v51 = 8;
                          v52 = 5;
                          v53 = *(_QWORD *)v39.Data4;
                          v17 = -1;
                          v18 = -1;
                          do
                            ++v18;
                          while ( *(_WORD *)(*(_QWORD *)v39.Data4 + 2 * v18) );
                          v54 = 2 * v18 + 2;
                          v55 = 6;
                          v56 = FileName;
                          v19 = -1;
                          do
                            ++v19;
                          while ( FileName[v19] );
                          v57 = 2 * v19 + 2;
                          v58 = 7;
                          v59 = &v30;
                          v60 = 1;
                          v61 = 8;
                          v62 = &v31;
                          v63 = 4;
                          v64 = 10;
                          v65 = &v32;
                          v66 = 4;
                          v67 = 11;
                          v68 = &v33;
                          v69 = 1;
                          v70 = 12;
                          v71 = a4;
                          v20 = -1;
                          do
                            ++v20;
                          while ( a4[v20] );
                          v72 = 2 * v20 + 2;
                          v73 = 13;
                          v74 = &v41;
                          v75 = 16;
                          v76 = 15;
                          v77 = &v25;
                          v78 = 1;
                          v79 = 17;
                          v80 = a5;
                          v81 = 16;
                          v82 = 18;
                          v83 = a6;
                          v84 = 16;
                          v85 = 19;
                          v86 = a8;
                          v21 = -1;
                          do
                            ++v21;
                          while ( a8[v21] );
                          v87 = 2 * v21 + 2;
                          v88 = 20;
                          v89 = v101;
                          do
                            ++v17;
                          while ( v101[v17] );
                          v90 = 2 * v17 + 2;
                          v91 = 4;
                          v92 = &v34;
                          v93 = 1;
                          v94 = 3;
                          v95 = &v42;
                          v96 = 16;
                          v97 = 22;
                          v98 = &v27;
                          v99 = 1;
                          RequestId = EnterpriseDB::InsertRecord(DBInstance, 1, &v43, 19);
                          if ( RequestId >= 0 )
                          {
                            v22 = (EnterpriseWorkerThread *)tlx::_LazyImpl<EnterpriseWorkerThread,tlx::lazy_construct<EnterpriseWorkerThread>,tlx::static_lazy<EnterpriseWorkerThread,0,tlx::lazy_construct<EnterpriseWorkerThread>>>::get();
                            RequestId = EnterpriseWorkerThread::Wakeup(v22);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_42:
  SysFreeString(v13);
  SysFreeString(*(BSTR *)&v39.Data1);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)RequestId;
}

```

## disassembly

```asm
0x180013400  push    rbp
0x180013402  push    rbx
0x180013403  push    rsi
0x180013404  push    rdi
0x180013405  push    r12
0x180013407  push    r13
0x180013409  push    r14
0x18001340b  push    r15
0x18001340d  lea     rbp, [rsp-858h]
0x180013415  sub     rsp, 958h
0x18001341c  mov     rax, cs:__security_cookie
0x180013423  xor     rax, rsp
0x180013426  mov     [rbp+890h+var_50], rax
0x18001342d  mov     r13, r9
0x180013430  mov     r14, r8
0x180013433  mov     rdi, rdx
0x180013436  mov     [rbp+890h+var_8E8], rdx
0x18001343a  mov     r15, [rbp+890h+arg_40]
0x180013441  mov     rsi, [rbp+890h+rclsid]
0x180013448  xor     edx, edx; Val
0x18001344a  mov     r8d, 220h; Size
0x180013450  lea     rcx, [rbp+890h+var_8A8]; void *
0x180013454  call    memset_0
0x180013459  mov     [rsp+990h+var_938], 3
0x180013461  mov     ecx, 1
0x180013466  mov     [rsp+990h+var_94C], ecx
0x18001346a  mov     [rsp+990h+var_928], ecx
0x18001346e  xor     eax, eax
0x180013470  mov     [rsp+990h+var_934], eax
0x180013474  mov     [rsp+990h+var_930], eax
0x180013478  mov     qword ptr [rbp+890h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001347c  mov     [rsp+990h+var_92C], ecx
0x180013480  mov     [rsp+990h+var_950], 32h ; '2'
0x180013485  mov     [rsp+990h+pv], rax
0x18001348a  mov     ebx, 208h
0x18001348f  mov     r8d, ebx; Size
0x180013492  xor     edx, edx; Val
0x180013494  lea     rcx, [rbp+890h+Destination]; void *
0x18001349b  call    memset_0
0x1800134a0  mov     [rsp+990h+var_944], 104h
0x1800134a8  mov     r8d, ebx; Size
0x1800134ab  xor     edx, edx; Val
0x1800134ad  lea     rcx, [rbp+890h+FileName]; void *
0x1800134b4  call    memset_0
0x1800134b9  mov     r8d, ebx; Size
0x1800134bc  xor     edx, edx; Val
0x1800134be  lea     rcx, [rbp+890h+var_470]; void *
0x1800134c5  call    memset_0
0x1800134ca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800134d1  movdqu  xmmword ptr [rbp+890h+var_8D0.Data1], xmm0
0x1800134d6  movdqu  [rbp+890h+var_8C0], xmm0
0x1800134db  xor     eax, eax
0x1800134dd  mov     [rbp+890h+var_8F0], rax
0x1800134e1  movdqu  xmmword ptr [rbp+890h+rguid.Data1], xmm0
0x1800134e6  mov     [rsp+990h+var_948], eax
0x1800134ea  mov     ebx, eax
0x1800134ec  mov     [rbp+890h+var_908], rax
0x1800134f0  test    rdi, rdi
0x1800134f3  jnz     short loc_1800134FF
0x1800134f5  mov     edi, 80070057h
0x1800134fa  jmp     loc_180013A16
0x1800134ff  test    r14, r14
0x180013502  jz      short loc_1800134F5
0x180013504  test    r13, r13
0x180013507  jz      short loc_1800134F5
0x180013509  mov     r12, [rbp+890h+arg_38]
0x180013510  test    r12, r12
0x180013513  jz      short loc_1800134F5
0x180013515  test    r15, r15
0x180013518  jz      short loc_1800134F5
0x18001351a  test    rsi, rsi
0x18001351d  jz      short loc_1800134F5
0x18001351f  call    ?GetDBInstance@EnterpriseConfig@@SAPEAVEnterpriseDB@@XZ; EnterpriseConfig::GetDBInstance(void)
0x180013524  mov     [rbp+890h+var_8E0], rax
0x180013528  test    rax, rax
0x18001352b  jnz     short loc_180013537
0x18001352d  mov     edi, 8007000Eh
0x180013532  jmp     loc_180013A16
0x180013537  mov     rcx, rsi; struct _GUID *
0x18001353a  call    ?GenerateRequestId@EnterpriseConfig@@SAJPEAU_GUID@@@Z; EnterpriseConfig::GenerateRequestId(_GUID *)
0x18001353f  mov     edi, eax
0x180013541  test    eax, eax
0x180013543  js      loc_180013A16
0x180013549  lea     rcx, [rsp+990h+pv]
0x18001354e  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x180013553  mov     rdx, rax; lplpsz
0x180013556  mov     rcx, rsi; rclsid
0x180013559  call    cs:__imp_StringFromCLSID
0x18001355f  mov     edi, eax
0x180013561  test    eax, eax
0x180013563  js      loc_180013A16
0x180013569  lea     rcx, [rbp+890h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001356d  call    cs:__imp_GetSystemTimeAsFileTime
0x180013573  lea     rdx, [rsp+990h+var_944]; unsigned int *
0x180013578  lea     rcx, [rbp+890h+Destination]; Destination
0x18001357f  call    ?GetSharedFolder@@YAJPEAGPEAK@Z; GetSharedFolder(ushort *,ulong *)
0x180013584  mov     edi, eax
0x180013586  test    eax, eax
0x180013588  js      loc_180013A16
0x18001358e  lea     rax, ?XAP_EXTENSION@@3QBGB; ".XAP"
0x180013595  mov     [rsp+990h+var_968], rax
0x18001359a  mov     rax, [rsp+990h+pv]
0x18001359f  mov     [rsp+990h+var_970], rax
0x1800135a4  lea     r9, [rbp+890h+Destination]
0x1800135ab  lea     r8, aSSS_0; "%s\\%s%s"
0x1800135b2  mov     edx, 104h; unsigned __int64
0x1800135b7  lea     rcx, [rbp+890h+FileName]; unsigned __int16 *
0x1800135be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800135c3  mov     edi, eax
0x1800135c5  test    eax, eax
0x1800135c7  js      loc_180013A16
0x1800135cd  lea     rax, ?LICENSE_EXTENSION@@3QBGB; ".XML"
0x1800135d4  mov     [rsp+990h+var_968], rax
0x1800135d9  mov     rax, [rsp+990h+pv]
0x1800135de  mov     [rsp+990h+var_970], rax
0x1800135e3  lea     r9, [rbp+890h+Destination]
0x1800135ea  lea     r8, aSSS_0; "%s\\%s%s"
0x1800135f1  mov     edx, 104h; unsigned __int64
0x1800135f6  lea     rcx, [rbp+890h+var_470]; unsigned __int16 *
0x1800135fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013602  mov     edi, eax
0x180013604  test    eax, eax
0x180013606  js      loc_180013A16
0x18001360c  lea     rcx, [rbp+890h+FileName]; lpFileName
0x180013613  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x180013618  mov     edi, eax
0x18001361a  test    eax, eax
0x18001361c  js      loc_180013A16
0x180013622  lea     rcx, [rbp+890h+var_470]; lpFileName
0x180013629  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x18001362e  mov     edi, eax
0x180013630  test    eax, eax
0x180013632  js      loc_180013A16
0x180013638  lea     rdx, [rbp+890h+FileName]
0x18001363f  mov     rcx, r14
0x180013642  call    cs:__imp_DSCopyFromSharedFile
0x180013648  mov     edi, eax
0x18001364a  test    eax, eax
0x18001364c  js      loc_180013A16
0x180013652  lea     rdx, [rbp+890h+var_470]
0x180013659  mov     rcx, r15
0x18001365c  call    cs:__imp_DSCopyFromSharedFile
0x180013662  mov     edi, eax
0x180013664  test    eax, eax
0x180013666  js      loc_180013A16
0x18001366c  lea     rdx, [rbp+890h+FileName]; unsigned __int16 *
0x180013673  lea     rcx, [rbp+890h+var_908]; this
0x180013677  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18001367c  mov     edi, eax
0x18001367e  xor     ecx, ecx
0x180013680  mov     rbx, [rbp+890h+var_908]
0x180013684  test    eax, eax
0x180013686  js      loc_180013A16
0x18001368c  mov     dword ptr [rsp+990h+var_960], ecx; unsigned __int16 **
0x180013690  lea     rax, [rsp+990h+var_948]
0x180013695  mov     [rsp+990h+var_968], rax; enum EnterpriseFileType *
0x18001369a  mov     [rsp+990h+var_970], rcx; struct _GUID *
0x18001369f  xor     r9d, r9d; struct _GUID *
0x1800136a2  lea     r8, [rbp+890h+var_8F0]; struct _GUID *
0x1800136a6  lea     rdx, [rbp+890h+var_8D0]; struct _GUID *
0x1800136aa  mov     rcx, rbx; this
0x1800136ad  call    ?GetEnterpriseInformationFromUnknownApplicationPackage@@YAJPEBGPEAU_GUID@@PEAPEAG12PEAW4EnterpriseFileType@@H@Z; GetEnterpriseInformationFromUnknownApplicationPackage(ushort const *,_GUID *,ushort * *,_GUID *,ushort * *,EnterpriseFileType *,int)
0x1800136b2  mov     edi, eax
0x1800136b4  test    eax, eax
0x1800136b6  js      loc_180013A16
0x1800136bc  lea     rdx, [rsp+990h+var_944]; unsigned int *
0x1800136c1  lea     rcx, [rsp+990h+bstrString]; unsigned int *
0x1800136c6  call    ?PurgeXAPRequestTable@EnrollmentManager@@SAJPEAK0@Z; EnrollmentManager::PurgeXAPRequestTable(ulong *,ulong *)
0x1800136cb  mov     edi, eax
0x1800136cd  test    eax, eax
0x1800136cf  js      loc_180013A16
0x1800136d5  movaps  xmm0, xmmword ptr [rbp+890h+var_8D0.Data1]
0x1800136d9  movdqa  xmmword ptr [rsp+990h+bstrString], xmm0
0x1800136df  lea     r8, [rbp+890h+rguid]; struct _GUID *
0x1800136e3  lea     rdx, [rsp+990h+var_94C]; enum _ENTERPRISE_APP_INSTALL_STATE *
0x1800136e8  lea     rcx, [rsp+990h+bstrString]; Buf2
0x1800136ed  call    ?GetInstallationStateOfProductId@EnrollmentManager@@SAJU_GUID@@PEAW4_ENTERPRISE_APP_INSTALL_STATE@@PEAU2@@Z; EnrollmentManager::GetInstallationStateOfProductId(_GUID,_ENTERPRISE_APP_INSTALL_STATE *,_GUID *)
0x1800136f2  mov     r14d, 2
0x1800136f8  xor     r8d, r8d
0x1800136fb  test    eax, eax
0x1800136fd  jnz     loc_180013786
0x180013703  mov     eax, [rsp+990h+var_94C]
0x180013707  add     eax, 0FFFFFFFBh
0x18001370a  cmp     eax, r14d
0x18001370d  jbe     short loc_180013762
0x18001370f  mov     [rsp+990h+bstrString], r8
0x180013714  movaps  xmm0, xmmword ptr [rbp+890h+var_8D0.Data1]
0x180013718  movdqa  xmmword ptr [rbp+890h+rguid.Data1], xmm0
0x18001371d  lea     rdx, [rsp+990h+bstrString]; unsigned __int16 **
0x180013722  lea     rcx, [rbp+890h+rguid]; rguid
0x180013726  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x18001372b  mov     edi, eax
0x18001372d  test    eax, eax
0x18001372f  jns     short loc_180013741
0x180013731  mov     rcx, [rsp+990h+bstrString]; bstrString
0x180013736  call    cs:__imp_SysFreeString
0x18001373c  jmp     loc_180013A16
0x180013741  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 20h
0x180013748  jz      short loc_18001375B
0x18001374a  mov     r8, [rsp+990h+bstrString]
0x18001374f  lea     rdx, EnterpriseAppMgmtXapRequestAlreadyInProgress
0x180013756  call    McTemplateU0z_EventWriteTransfer
0x18001375b  mov     edi, 80070149h
0x180013760  jmp     short loc_180013731
0x180013762  movaps  xmm0, xmmword ptr [rbp+890h+rguid.Data1]
0x180013766  movdqa  xmmword ptr [rbp+890h+rguid.Data1], xmm0
0x18001376b  lea     rdx, [rbp+890h+rguid]
0x18001376f  mov     ecx, 1
0x180013774  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x180013779  mov     edi, eax
0x18001377b  xor     r8d, r8d
0x18001377e  test    eax, eax
0x180013780  js      loc_180013A16
0x180013786  mov     [rbp+890h+var_8B0], r8w
0x18001378b  mov     [rbp+890h+var_8A8], rsi
0x18001378f  mov     r11d, 10h
0x180013795  mov     [rbp+890h+var_8A0], r11d
0x180013799  lea     r10d, [r11-0Fh]
0x18001379d  mov     [rbp+890h+var_898], r10w
0x1800137a2  lea     rax, [rbp+890h+SystemTimeAsFileTime]
0x1800137a6  mov     [rbp+890h+var_890], rax
0x1800137aa  lea     r9d, [r11-8]
0x1800137ae  mov     [rbp+890h+var_888], r9d
0x1800137b2  mov     [rbp+890h+var_880], r14w
0x1800137b7  lea     rax, [rbp+890h+SystemTimeAsFileTime]
0x1800137bb  mov     [rbp+890h+var_878], rax
0x1800137bf  mov     [rbp+890h+var_870], r9d
0x1800137c3  lea     eax, [r11-0Bh]
0x1800137c7  mov     [rbp+890h+var_868], ax
0x1800137cb  mov     rdx, [rbp+890h+var_8E8]
0x1800137cf  mov     [rbp+890h+var_860], rdx
0x1800137d3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800137d7  mov     rax, rcx
0x1800137da  inc     rax
0x1800137dd  cmp     [rdx+rax*2], r8w
0x1800137e2  jnz     short loc_1800137DA
0x1800137e4  lea     eax, ds:2[rax*2]
0x1800137eb  mov     [rbp+890h+var_858], eax
0x1800137ee  mov     eax, 6
0x1800137f3  mov     [rbp+890h+var_850], ax
0x1800137f7  lea     rax, [rbp+890h+FileName]
0x1800137fe  mov     [rbp+890h+var_848], rax
0x180013802  lea     rdx, [rbp+890h+FileName]
0x180013809  mov     rax, rcx
0x18001380c  inc     rax
0x18001380f  cmp     [rdx+rax*2], r8w
0x180013814  jnz     short loc_18001380C
0x180013816  lea     eax, ds:2[rax*2]
0x18001381d  mov     [rbp+890h+var_840], eax
0x180013820  mov     eax, 7
0x180013825  mov     [rbp+890h+var_838], ax
0x180013829  lea     rax, [rsp+990h+var_938]
0x18001382e  mov     [rbp+890h+var_830], rax
0x180013832  mov     [rbp+890h+var_828], r10d
0x180013836  mov     [rbp+890h+var_820], r9w
0x18001383b  lea     rax, [rsp+990h+var_934]
0x180013840  mov     [rbp+890h+var_818], rax
0x180013844  mov     edx, 4
0x180013849  mov     [rbp+890h+var_810], edx
0x18001384f  lea     eax, [rdx+6]
0x180013852  mov     [rbp+890h+var_808], ax
0x180013859  lea     rax, [rsp+990h+var_930]
0x18001385e  mov     [rbp+890h+var_800], rax
0x180013865  mov     [rbp+890h+var_7F8], edx
0x18001386b  lea     eax, [rdx+7]
0x18001386e  mov     [rbp+890h+var_7F0], ax
0x180013875  lea     rax, [rsp+990h+var_92C]
0x18001387a  mov     [rbp+890h+var_7E8], rax
0x180013881  mov     [rbp+890h+var_7E0], r10d
0x180013888  lea     eax, [rdx+8]
0x18001388b  mov     [rbp+890h+var_7D8], ax
0x180013892  mov     [rbp+890h+var_7D0], r13
0x180013899  mov     rax, rcx
0x18001389c  inc     rax
0x18001389f  cmp     [r13+rax*2+0], r8w
0x1800138a5  jnz     short loc_18001389C
0x1800138a7  lea     eax, ds:2[rax*2]
0x1800138ae  mov     [rbp+890h+var_7C8], eax
0x1800138b4  mov     eax, 0Dh
0x1800138b9  mov     [rbp+890h+var_7C0], ax
0x1800138c0  lea     rax, [rbp+890h+var_8D0]
0x1800138c4  mov     [rbp+890h+var_7B8], rax
0x1800138cb  mov     [rbp+890h+var_7B0], r11d
0x1800138d2  mov     eax, 0Fh
0x1800138d7  mov     [rbp+890h+var_7A8], ax
0x1800138de  lea     rax, [rsp+990h+var_950]
0x1800138e3  mov     [rbp+890h+var_7A0], rax
0x1800138ea  mov     [rbp+890h+var_798], r10d
0x1800138f1  mov     eax, 11h
0x1800138f6  mov     [rbp+890h+var_790], ax
0x1800138fd  mov     rax, [rbp+890h+arg_20]
0x180013904  mov     [rbp+890h+var_788], rax
0x18001390b  mov     [rbp+890h+var_780], r11d
0x180013912  mov     eax, 12h
0x180013917  mov     [rbp+890h+var_778], ax
0x18001391e  mov     rax, [rbp+890h+arg_28]
0x180013925  mov     [rbp+890h+var_770], rax
0x18001392c  mov     [rbp+890h+var_768], r11d
0x180013933  mov     r9d, 13h
0x180013939  mov     [rbp+890h+var_760], r9w
  ... truncated ...
```
