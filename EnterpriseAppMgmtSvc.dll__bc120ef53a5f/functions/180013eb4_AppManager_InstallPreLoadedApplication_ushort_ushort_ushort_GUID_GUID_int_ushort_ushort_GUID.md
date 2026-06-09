# AppManager::InstallPreLoadedApplication(ushort *,ushort *,ushort *,_GUID,_GUID,int,ushort *,ushort *,_GUID *)

- ea: `0x180013eb4`
- end: `0x180014545`
- name: `?InstallPreLoadedApplication@AppManager@@QEAAJPEAG00U_GUID@@1H00PEAU2@@Z`
- size: `1681`
- prototype: `__int64 __fastcall(AppManager *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _GUID *, struct _GUID *, int, unsigned __int16 *, unsigned __int16 *, IID *rclsid)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005070`

## callees

- `0x180005ff4`
- `0x180006a3c`
- `0x1800072ac`
- `0x180013794`
- `0x180013eb4`
- `0x180014684`
- `0x18001954c`
- `0x18001ac50`
- `0x18001b69c`
- `0x18001c0ec`
- `0x180029910`
- `0x180029b94`
- `0x180029e60`
- `0x18002a10c`
- `0x18002a1c4`
- `0x18002c194`
- `0x18003153c`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001400d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001400d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014513`
- `OLEAUT32!__imp_SysFreeString` at `0x180014202`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180014202`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014027`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014027`
- `dsclient!DSCopyFromSharedFile` at `0x180014102`
- `dsclient!DSCopyFromSharedFile` at `0x180014122`
- `dsclient!DSCopyFromSharedFile` at `0x180014102`
- `dsclient!DSCopyFromSharedFile` at `0x180014122`

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
  HRESULT RequestId; // edi
  LPOLESTR *v15; // rax
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
    v15 = (LPOLESTR *)tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
    RequestId = StringFromCLSID(rclsid, v15);
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
                    RequestId = ATL::CComBSTR::Append((ATL::CComBSTR *)&v37, FileName);
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
                            RequestId = EnrollmentManager::DeleteRecord(1, &rguid, 0);
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
                          RequestId = EnterpriseDB::InsertRecord(DBInstance, 1, &v43);
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
0x180013eb4  push    rbp
0x180013eb6  push    rbx
0x180013eb7  push    rsi
0x180013eb8  push    rdi
0x180013eb9  push    r12
0x180013ebb  push    r13
0x180013ebd  push    r14
0x180013ebf  push    r15
0x180013ec1  lea     rbp, [rsp-858h]
0x180013ec9  sub     rsp, 958h
0x180013ed0  mov     rax, cs:__security_cookie
0x180013ed7  xor     rax, rsp
0x180013eda  mov     [rbp+890h+var_50], rax
0x180013ee1  mov     r13, r9
0x180013ee4  mov     r14, r8
0x180013ee7  mov     rdi, rdx
0x180013eea  mov     [rbp+890h+var_8E8], rdx
0x180013eee  mov     r15, [rbp+890h+arg_40]
0x180013ef5  mov     rsi, [rbp+890h+rclsid]
0x180013efc  xor     edx, edx; Val
0x180013efe  mov     r8d, 220h; Size
0x180013f04  lea     rcx, [rbp+890h+var_8A8]; void *
0x180013f08  call    memset_0
0x180013f0d  mov     [rsp+990h+var_938], 3
0x180013f15  mov     ecx, 1
0x180013f1a  mov     [rsp+990h+var_94C], ecx
0x180013f1e  mov     [rsp+990h+var_928], ecx
0x180013f22  xor     eax, eax
0x180013f24  mov     [rsp+990h+var_934], eax
0x180013f28  mov     [rsp+990h+var_930], eax
0x180013f2c  mov     qword ptr [rbp+890h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180013f30  mov     [rsp+990h+var_92C], ecx
0x180013f34  mov     [rsp+990h+var_950], 32h ; '2'
0x180013f39  mov     [rsp+990h+pv], rax
0x180013f3e  mov     ebx, 208h
0x180013f43  mov     r8d, ebx; Size
0x180013f46  xor     edx, edx; Val
0x180013f48  lea     rcx, [rbp+890h+Destination]; void *
0x180013f4f  call    memset_0
0x180013f54  mov     [rsp+990h+var_944], 104h
0x180013f5c  mov     r8d, ebx; Size
0x180013f5f  xor     edx, edx; Val
0x180013f61  lea     rcx, [rbp+890h+FileName]; void *
0x180013f68  call    memset_0
0x180013f6d  mov     r8d, ebx; Size
0x180013f70  xor     edx, edx; Val
0x180013f72  lea     rcx, [rbp+890h+var_470]; void *
0x180013f79  call    memset_0
0x180013f7e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180013f85  movdqu  xmmword ptr [rbp+890h+var_8D0.Data1], xmm0
0x180013f8a  movdqu  [rbp+890h+var_8C0], xmm0
0x180013f8f  xor     eax, eax
0x180013f91  mov     [rbp+890h+var_8F0], rax
0x180013f95  movdqu  xmmword ptr [rbp+890h+rguid.Data1], xmm0
0x180013f9a  mov     [rsp+990h+var_948], eax
0x180013f9e  mov     ebx, eax
0x180013fa0  mov     [rbp+890h+var_908], rax
0x180013fa4  test    rdi, rdi
0x180013fa7  jnz     short loc_180013FB3
0x180013fa9  mov     edi, 80070057h
0x180013fae  jmp     loc_1800144E8
0x180013fb3  test    r14, r14
0x180013fb6  jz      short loc_180013FA9
0x180013fb8  test    r13, r13
0x180013fbb  jz      short loc_180013FA9
0x180013fbd  mov     r12, [rbp+890h+arg_38]
0x180013fc4  test    r12, r12
0x180013fc7  jz      short loc_180013FA9
0x180013fc9  test    r15, r15
0x180013fcc  jz      short loc_180013FA9
0x180013fce  test    rsi, rsi
0x180013fd1  jz      short loc_180013FA9
0x180013fd3  call    ?GetDBInstance@EnterpriseConfig@@SAPEAVEnterpriseDB@@XZ; EnterpriseConfig::GetDBInstance(void)
0x180013fd8  mov     [rbp+890h+var_8E0], rax
0x180013fdc  test    rax, rax
0x180013fdf  jnz     short loc_180013FEB
0x180013fe1  mov     edi, 8007000Eh
0x180013fe6  jmp     loc_1800144E8
0x180013feb  mov     rcx, rsi; struct _GUID *
0x180013fee  call    ?GenerateRequestId@EnterpriseConfig@@SAJPEAU_GUID@@@Z; EnterpriseConfig::GenerateRequestId(_GUID *)
0x180013ff3  mov     edi, eax
0x180013ff5  test    eax, eax
0x180013ff7  js      loc_1800144E8
0x180013ffd  lea     rcx, [rsp+990h+pv]
0x180014002  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x180014007  mov     rdx, rax; lplpsz
0x18001400a  mov     rcx, rsi; rclsid
0x18001400d  call    cs:__imp_StringFromCLSID
0x180014014  nop     dword ptr [rax+rax+00h]
0x180014019  mov     edi, eax
0x18001401b  test    eax, eax
0x18001401d  js      loc_1800144E8
0x180014023  lea     rcx, [rbp+890h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014027  call    cs:__imp_GetSystemTimeAsFileTime
0x18001402e  nop     dword ptr [rax+rax+00h]
0x180014033  lea     rdx, [rsp+990h+var_944]; unsigned int *
0x180014038  lea     rcx, [rbp+890h+Destination]; Destination
0x18001403f  call    ?GetSharedFolder@@YAJPEAGPEAK@Z; GetSharedFolder(ushort *,ulong *)
0x180014044  mov     edi, eax
0x180014046  test    eax, eax
0x180014048  js      loc_1800144E8
0x18001404e  lea     rax, ?XAP_EXTENSION@@3QBGB; ".XAP"
0x180014055  mov     [rsp+990h+var_968], rax
0x18001405a  mov     rax, [rsp+990h+pv]
0x18001405f  mov     [rsp+990h+var_970], rax
0x180014064  lea     r9, [rbp+890h+Destination]
0x18001406b  lea     r8, aSSS_0; "%s\\%s%s"
0x180014072  mov     edx, 104h; unsigned __int64
0x180014077  lea     rcx, [rbp+890h+FileName]; unsigned __int16 *
0x18001407e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014083  mov     edi, eax
0x180014085  test    eax, eax
0x180014087  js      loc_1800144E8
0x18001408d  lea     rax, ?LICENSE_EXTENSION@@3QBGB; ".XML"
0x180014094  mov     [rsp+990h+var_968], rax
0x180014099  mov     rax, [rsp+990h+pv]
0x18001409e  mov     [rsp+990h+var_970], rax
0x1800140a3  lea     r9, [rbp+890h+Destination]
0x1800140aa  lea     r8, aSSS_0; "%s\\%s%s"
0x1800140b1  mov     edx, 104h; unsigned __int64
0x1800140b6  lea     rcx, [rbp+890h+var_470]; unsigned __int16 *
0x1800140bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800140c2  mov     edi, eax
0x1800140c4  test    eax, eax
0x1800140c6  js      loc_1800144E8
0x1800140cc  lea     rcx, [rbp+890h+FileName]; lpFileName
0x1800140d3  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x1800140d8  mov     edi, eax
0x1800140da  test    eax, eax
0x1800140dc  js      loc_1800144E8
0x1800140e2  lea     rcx, [rbp+890h+var_470]; lpFileName
0x1800140e9  call    ?DeleteLocalFile@@YAJPEBG@Z; DeleteLocalFile(ushort const *)
0x1800140ee  mov     edi, eax
0x1800140f0  test    eax, eax
0x1800140f2  js      loc_1800144E8
0x1800140f8  lea     rdx, [rbp+890h+FileName]
0x1800140ff  mov     rcx, r14
0x180014102  call    cs:__imp_DSCopyFromSharedFile
0x180014109  nop     dword ptr [rax+rax+00h]
0x18001410e  mov     edi, eax
0x180014110  test    eax, eax
0x180014112  js      loc_1800144E8
0x180014118  lea     rdx, [rbp+890h+var_470]
0x18001411f  mov     rcx, r15
0x180014122  call    cs:__imp_DSCopyFromSharedFile
0x180014129  nop     dword ptr [rax+rax+00h]
0x18001412e  mov     edi, eax
0x180014130  test    eax, eax
0x180014132  js      loc_1800144E8
0x180014138  lea     rdx, [rbp+890h+FileName]; unsigned __int16 *
0x18001413f  lea     rcx, [rbp+890h+var_908]; this
0x180014143  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180014148  mov     edi, eax
0x18001414a  xor     ecx, ecx
0x18001414c  mov     rbx, [rbp+890h+var_908]
0x180014150  test    eax, eax
0x180014152  js      loc_1800144E8
0x180014158  mov     dword ptr [rsp+990h+var_960], ecx; unsigned __int16 **
0x18001415c  lea     rax, [rsp+990h+var_948]
0x180014161  mov     [rsp+990h+var_968], rax; enum EnterpriseFileType *
0x180014166  mov     [rsp+990h+var_970], rcx; struct _GUID *
0x18001416b  xor     r9d, r9d; struct _GUID *
0x18001416e  lea     r8, [rbp+890h+var_8F0]; struct _GUID *
0x180014172  lea     rdx, [rbp+890h+var_8D0]; struct _GUID *
0x180014176  mov     rcx, rbx; this
0x180014179  call    ?GetEnterpriseInformationFromUnknownApplicationPackage@@YAJPEBGPEAU_GUID@@PEAPEAG12PEAW4EnterpriseFileType@@H@Z; GetEnterpriseInformationFromUnknownApplicationPackage(ushort const *,_GUID *,ushort * *,_GUID *,ushort * *,EnterpriseFileType *,int)
0x18001417e  mov     edi, eax
0x180014180  test    eax, eax
0x180014182  js      loc_1800144E8
0x180014188  lea     rdx, [rsp+990h+var_944]; unsigned int *
0x18001418d  lea     rcx, [rsp+990h+bstrString]; unsigned int *
0x180014192  call    ?PurgeXAPRequestTable@EnrollmentManager@@SAJPEAK0@Z; EnrollmentManager::PurgeXAPRequestTable(ulong *,ulong *)
0x180014197  mov     edi, eax
0x180014199  test    eax, eax
0x18001419b  js      loc_1800144E8
0x1800141a1  movaps  xmm0, xmmword ptr [rbp+890h+var_8D0.Data1]
0x1800141a5  movdqa  xmmword ptr [rsp+990h+bstrString], xmm0
0x1800141ab  lea     r8, [rbp+890h+rguid]; struct _GUID *
0x1800141af  lea     rdx, [rsp+990h+var_94C]; enum _ENTERPRISE_APP_INSTALL_STATE *
0x1800141b4  lea     rcx, [rsp+990h+bstrString]; Buf2
0x1800141b9  call    ?GetInstallationStateOfProductId@EnrollmentManager@@SAJU_GUID@@PEAW4_ENTERPRISE_APP_INSTALL_STATE@@PEAU2@@Z; EnrollmentManager::GetInstallationStateOfProductId(_GUID,_ENTERPRISE_APP_INSTALL_STATE *,_GUID *)
0x1800141be  mov     r14d, 2
0x1800141c4  xor     r8d, r8d
0x1800141c7  test    eax, eax
0x1800141c9  jnz     loc_180014258
0x1800141cf  mov     eax, [rsp+990h+var_94C]
0x1800141d3  add     eax, 0FFFFFFFBh
0x1800141d6  cmp     eax, r14d
0x1800141d9  jbe     short loc_180014234
0x1800141db  mov     [rsp+990h+bstrString], r8
0x1800141e0  movaps  xmm0, xmmword ptr [rbp+890h+var_8D0.Data1]
0x1800141e4  movdqa  xmmword ptr [rbp+890h+rguid.Data1], xmm0
0x1800141e9  lea     rdx, [rsp+990h+bstrString]; unsigned __int16 **
0x1800141ee  lea     rcx, [rbp+890h+rguid]; rguid
0x1800141f2  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x1800141f7  mov     edi, eax
0x1800141f9  test    eax, eax
0x1800141fb  jns     short loc_180014213
0x1800141fd  mov     rcx, [rsp+990h+bstrString]; bstrString
0x180014202  call    cs:__imp_SysFreeString
0x180014209  nop     dword ptr [rax+rax+00h]
0x18001420e  jmp     loc_1800144E8
0x180014213  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 20h
0x18001421a  jz      short loc_18001422D
0x18001421c  mov     r8, [rsp+990h+bstrString]
0x180014221  lea     rdx, EnterpriseAppMgmtXapRequestAlreadyInProgress
0x180014228  call    McTemplateU0z_EventWriteTransfer
0x18001422d  mov     edi, 80070149h
0x180014232  jmp     short loc_1800141FD
0x180014234  movaps  xmm0, xmmword ptr [rbp+890h+rguid.Data1]
0x180014238  movdqa  xmmword ptr [rbp+890h+rguid.Data1], xmm0
0x18001423d  lea     rdx, [rbp+890h+rguid]
0x180014241  mov     ecx, 1
0x180014246  call    ?DeleteRecord@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@@Z; EnrollmentManager::DeleteRecord(TABLEID,_GUID)
0x18001424b  mov     edi, eax
0x18001424d  xor     r8d, r8d
0x180014250  test    eax, eax
0x180014252  js      loc_1800144E8
0x180014258  mov     [rbp+890h+var_8B0], r8w
0x18001425d  mov     [rbp+890h+var_8A8], rsi
0x180014261  mov     r11d, 10h
0x180014267  mov     [rbp+890h+var_8A0], r11d
0x18001426b  lea     r10d, [r11-0Fh]
0x18001426f  mov     [rbp+890h+var_898], r10w
0x180014274  lea     rax, [rbp+890h+SystemTimeAsFileTime]
0x180014278  mov     [rbp+890h+var_890], rax
0x18001427c  lea     r9d, [r11-8]
0x180014280  mov     [rbp+890h+var_888], r9d
0x180014284  mov     [rbp+890h+var_880], r14w
0x180014289  lea     rax, [rbp+890h+SystemTimeAsFileTime]
0x18001428d  mov     [rbp+890h+var_878], rax
0x180014291  mov     [rbp+890h+var_870], r9d
0x180014295  lea     eax, [r11-0Bh]
0x180014299  mov     [rbp+890h+var_868], ax
0x18001429d  mov     rdx, [rbp+890h+var_8E8]
0x1800142a1  mov     [rbp+890h+var_860], rdx
0x1800142a5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800142a9  mov     rax, rcx
0x1800142ac  inc     rax
0x1800142af  cmp     [rdx+rax*2], r8w
0x1800142b4  jnz     short loc_1800142AC
0x1800142b6  lea     eax, ds:2[rax*2]
0x1800142bd  mov     [rbp+890h+var_858], eax
0x1800142c0  mov     eax, 6
0x1800142c5  mov     [rbp+890h+var_850], ax
0x1800142c9  lea     rax, [rbp+890h+FileName]
0x1800142d0  mov     [rbp+890h+var_848], rax
0x1800142d4  lea     rdx, [rbp+890h+FileName]
0x1800142db  mov     rax, rcx
0x1800142de  inc     rax
0x1800142e1  cmp     [rdx+rax*2], r8w
0x1800142e6  jnz     short loc_1800142DE
0x1800142e8  lea     eax, ds:2[rax*2]
0x1800142ef  mov     [rbp+890h+var_840], eax
0x1800142f2  mov     eax, 7
0x1800142f7  mov     [rbp+890h+var_838], ax
0x1800142fb  lea     rax, [rsp+990h+var_938]
0x180014300  mov     [rbp+890h+var_830], rax
0x180014304  mov     [rbp+890h+var_828], r10d
0x180014308  mov     [rbp+890h+var_820], r9w
0x18001430d  lea     rax, [rsp+990h+var_934]
0x180014312  mov     [rbp+890h+var_818], rax
0x180014316  mov     edx, 4
0x18001431b  mov     [rbp+890h+var_810], edx
0x180014321  lea     eax, [rdx+6]
0x180014324  mov     [rbp+890h+var_808], ax
0x18001432b  lea     rax, [rsp+990h+var_930]
0x180014330  mov     [rbp+890h+var_800], rax
0x180014337  mov     [rbp+890h+var_7F8], edx
0x18001433d  lea     eax, [rdx+7]
0x180014340  mov     [rbp+890h+var_7F0], ax
0x180014347  lea     rax, [rsp+990h+var_92C]
0x18001434c  mov     [rbp+890h+var_7E8], rax
0x180014353  mov     [rbp+890h+var_7E0], r10d
0x18001435a  lea     eax, [rdx+8]
0x18001435d  mov     [rbp+890h+var_7D8], ax
0x180014364  mov     [rbp+890h+var_7D0], r13
0x18001436b  mov     rax, rcx
0x18001436e  inc     rax
0x180014371  cmp     [r13+rax*2+0], r8w
0x180014377  jnz     short loc_18001436E
0x180014379  lea     eax, ds:2[rax*2]
0x180014380  mov     [rbp+890h+var_7C8], eax
0x180014386  mov     eax, 0Dh
0x18001438b  mov     [rbp+890h+var_7C0], ax
0x180014392  lea     rax, [rbp+890h+var_8D0]
0x180014396  mov     [rbp+890h+var_7B8], rax
0x18001439d  mov     [rbp+890h+var_7B0], r11d
0x1800143a4  mov     eax, 0Fh
0x1800143a9  mov     [rbp+890h+var_7A8], ax
0x1800143b0  lea     rax, [rsp+990h+var_950]
0x1800143b5  mov     [rbp+890h+var_7A0], rax
0x1800143bc  mov     [rbp+890h+var_798], r10d
0x1800143c3  mov     eax, 11h
0x1800143c8  mov     [rbp+890h+var_790], ax
0x1800143cf  mov     rax, [rbp+890h+arg_20]
0x1800143d6  mov     [rbp+890h+var_788], rax
0x1800143dd  mov     [rbp+890h+var_780], r11d
0x1800143e4  mov     eax, 12h
0x1800143e9  mov     [rbp+890h+var_778], ax
  ... truncated ...
```
