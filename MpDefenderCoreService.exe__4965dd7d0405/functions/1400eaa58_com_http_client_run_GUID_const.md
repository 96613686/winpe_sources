# com::http::client::run(_GUID const *)

- ea: `0x1400eaa58`
- end: `0x1400eb834`
- name: `?run@client@http@com@@YAJPEBU_GUID@@@Z`
- size: `3548`
- prototype: `__int64 __fastcall(com::http::client *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14007ce1c`

## callees

- `0x140001434`
- `0x14003a0f4`
- `0x14003a5c0`
- `0x14007e088`
- `0x140084a18`
- `0x1400e975c`
- `0x1400e9b7c`
- `0x1400ea130`
- `0x1400eaa58`
- `0x14013e720`
- `0x14013e974`
- `0x14013e9d4`
- `0x14013f020`
- `0x14013f148`
- `0x140158284`
- `0x140166250`
- `0x140166990`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400eb45f`
- `ole32!CoTaskMemFree` at `0x1400eb48a`
- `ole32!CoTaskMemFree` at `0x1400eb498`
- `ole32!CoTaskMemFree` at `0x1400eb4a1`
- `ole32!CoTaskMemFree` at `0x1400eb4af`
- `ole32!CoTaskMemFree` at `0x1400eb4bd`
- `ole32!CoTaskMemFree` at `0x1400eb4c6`
- `ole32!CoTaskMemFree` at `0x1400eb6cd`
- `ole32!CoTaskMemFree` at `0x1400eb6f8`
- `ole32!CoTaskMemFree` at `0x1400eb706`
- `ole32!CoTaskMemFree` at `0x1400eb70f`
- `ole32!CoTaskMemFree` at `0x1400eb71d`
- `ole32!CoTaskMemFree` at `0x1400eb72b`
- `ole32!CoTaskMemFree` at `0x1400eb734`
- `ole32!CoTaskMemFree` at `0x1400eb45f`
- `ole32!CoTaskMemFree` at `0x1400eb48a`
- `ole32!CoTaskMemFree` at `0x1400eb498`
- `ole32!CoTaskMemFree` at `0x1400eb4a1`
- `ole32!CoTaskMemFree` at `0x1400eb4af`
- `ole32!CoTaskMemFree` at `0x1400eb4bd`
- `ole32!CoTaskMemFree` at `0x1400eb4c6`
- `ole32!CoTaskMemFree` at `0x1400eb6cd`
- `ole32!CoTaskMemFree` at `0x1400eb6f8`
- `ole32!CoTaskMemFree` at `0x1400eb706`
- `ole32!CoTaskMemFree` at `0x1400eb70f`
- `ole32!CoTaskMemFree` at `0x1400eb71d`
- `ole32!CoTaskMemFree` at `0x1400eb72b`
- `ole32!CoTaskMemFree` at `0x1400eb734`
- `ole32!CoCreateInstance` at `0x1400eaba3`
- `ole32!CoCreateInstance` at `0x1400eaba3`
- `KERNEL32!WaitForSingleObject` at `0x1400ead9c`
- `KERNEL32!WaitForSingleObject` at `0x1400eb431`
- `KERNEL32!WaitForSingleObject` at `0x1400ead9c`
- `KERNEL32!WaitForSingleObject` at `0x1400eb431`
- `KERNEL32!CloseHandle` at `0x1400eb4ee`
- `KERNEL32!CloseHandle` at `0x1400eb5f1`
- `KERNEL32!CloseHandle` at `0x1400eb764`
- `KERNEL32!CloseHandle` at `0x1400eb4ee`
- `KERNEL32!CloseHandle` at `0x1400eb5f1`
- `KERNEL32!CloseHandle` at `0x1400eb764`
- `KERNEL32!GetLastError` at `0x1400eb691`
- `KERNEL32!GetLastError` at `0x1400eb691`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall com::http::client::run(com::http::client *this, const struct _GUID *a2)
{
  com::http *v2; // rcx
  int v3; // ebx
  __int64 v4; // rdx
  LPVOID v6; // rcx
  __int64 v7; // rdx
  LPVOID v8; // rdi
  volatile signed __int32 *v9; // r14
  LPVOID v10; // rbx
  __int64 v11; // rdx
  HANDLE v12; // r13
  Microsoft::Applications::Events::HttpClient_WinInet *v13; // r12
  _BYTE *v14; // rbx
  unsigned __int64 v15; // rdx
  bool v16; // si
  void *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rdi
  unsigned __int64 v20; // r8
  Microsoft::Applications::Events::HttpClient_WinInet *v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // esi
  unsigned __int64 v24; // rdi
  __int64 v25; // rax
  __int64 v26; // r13
  unsigned int v27; // edi
  _BYTE *v28; // rdx
  size_t v29; // r8
  unsigned int *v30; // rdi
  bool v31; // al
  const char *v32; // rcx
  const char *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  _BYTE *v38; // rdx
  __int64 v39; // rdi
  const char *v40; // rcx
  const char *v41; // r8
  const char *v42; // r9
  __int64 v43; // rax
  int v44; // eax
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rax
  unsigned int v48; // eax
  void *v49; // rsi
  void (__fastcall ***v50)(_QWORD, __int64); // rax
  void (__fastcall ***v51)(_QWORD, __int64); // rcx
  unsigned int j; // edi
  void *v53; // rcx
  void *v54; // r15
  void *v55; // rsi
  _QWORD *v56; // rdi
  void *v57; // r14
  void *v58; // rcx
  volatile signed __int32 *v59; // rbx
  __int64 v60; // rdx
  _BYTE *v61; // rdx
  __int64 v62; // rdx
  signed int LastError; // eax
  unsigned int v64; // edi
  unsigned int i; // edi
  void *v66; // rcx
  void *v67; // r15
  void *v68; // rsi
  _QWORD *v69; // rdi
  void *v70; // r14
  void *v71; // rcx
  volatile signed __int32 *v72; // rbx
  __int64 v73; // rdx
  char v74; // [rsp+38h] [rbp-D0h] BYREF
  char v75; // [rsp+39h] [rbp-CFh] BYREF
  bool v76; // [rsp+3Ah] [rbp-CEh] BYREF
  __int64 v77; // [rsp+40h] [rbp-C8h] BYREF
  volatile signed __int32 *v78; // [rsp+48h] [rbp-C0h]
  void (__fastcall ***v79)(_QWORD, __int64); // [rsp+50h] [rbp-B8h] BYREF
  LPVOID v80; // [rsp+58h] [rbp-B0h]
  int v81; // [rsp+60h] [rbp-A8h] BYREF
  int v82; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v83; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID *v84; // [rsp+70h] [rbp-98h]
  LPVOID ppv; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v86; // [rsp+80h] [rbp-88h]
  __int64 v87; // [rsp+88h] [rbp-80h]
  char *v88; // [rsp+90h] [rbp-78h] BYREF
  __int64 v89; // [rsp+98h] [rbp-70h] BYREF
  HANDLE hHandle; // [rsp+A0h] [rbp-68h] BYREF
  HRESULT v91; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID v92; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v93[56]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE *v94; // [rsp+F0h] [rbp-18h]
  _BYTE v95[56]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE *v96; // [rsp+130h] [rbp+28h]
  __m256i v97; // [rsp+138h] [rbp+30h] BYREF
  char *v98; // [rsp+158h] [rbp+50h]
  __int64 v99; // [rsp+160h] [rbp+58h]
  char *v100; // [rsp+168h] [rbp+60h]
  __int64 v101; // [rsp+170h] [rbp+68h]
  int *v102; // [rsp+178h] [rbp+70h]
  __int64 v103; // [rsp+180h] [rbp+78h]
  __int64 *v104; // [rsp+188h] [rbp+80h]
  __int64 v105; // [rsp+190h] [rbp+88h]
  struct _EVENT_DATA_DESCRIPTOR v106; // [rsp+198h] [rbp+90h] BYREF
  const char *v107; // [rsp+1B8h] [rbp+B0h]
  __int64 v108; // [rsp+1C0h] [rbp+B8h]
  const char *v109; // [rsp+1C8h] [rbp+C0h]
  int v110; // [rsp+1D0h] [rbp+C8h]
  int v111; // [rsp+1D4h] [rbp+CCh]
  const char *v112; // [rsp+1D8h] [rbp+D0h]
  int v113; // [rsp+1E0h] [rbp+D8h]
  int v114; // [rsp+1E4h] [rbp+DCh]
  bool *v115; // [rsp+1E8h] [rbp+E0h]
  __int64 v116; // [rsp+1F0h] [rbp+E8h]
  int *v117; // [rsp+1F8h] [rbp+F0h]
  __int64 v118; // [rsp+200h] [rbp+F8h]
  struct _EVENT_DATA_DESCRIPTOR v119; // [rsp+208h] [rbp+100h] BYREF
  struct _EVENT_DATA_DESCRIPTOR *v120; // [rsp+240h] [rbp+138h]

  if ( (unsigned int)dword_1401D96E0 > 4 && (byte_1401D96F0 & 1) != 0 && (qword_1401D96F8 & 1) == qword_1401D96F8 )
    tlgWriteTransfer_EventWriteTransfer(
      (int)&dword_1401D96E0,
      (int)&byte_1401BA6CF,
      0,
      0,
      2u,
      (PEVENT_DATA_DESCRIPTOR)&v97);
  v91 = 0;
  v119.Ptr = (ULONGLONG)&std::_Func_impl_no_alloc<_lambda_3e079bf40fa09c522011e0ccffb7ca47_,void,>::`vftable';
  *(_QWORD *)&v119.Size = &v91;
  v120 = &v119;
  com::http::scope_exit::scope_exit(v93, &v119);
  v3 = com::http::register_marshalling(v2);
  v91 = v3;
  if ( v3 < 0 )
  {
    if ( v94 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v94 )
      {
        LOBYTE(v4) = v94 != v93;
        (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v94 + 32LL))(v94, v4);
      }
    }
    return (unsigned int)v3;
  }
  v92 = 0;
  v84 = &v92;
  ppv = 0;
  v91 = CoCreateInstance(&rclsid, 0, 4u, &IID_IHttpRequestQueue, &ppv);
  v6 = v92;
  v92 = ppv;
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  v3 = v91;
  if ( v91 < 0 )
  {
    if ( v92 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v92 + 16LL))(v92);
    if ( v94 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v94 )
      {
        LOBYTE(v7) = v94 != v93;
        (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v94 + 32LL))(v94, v7);
      }
    }
    return (unsigned int)v3;
  }
  v8 = 0;
  v80 = 0;
  v9 = 0;
  v78 = 0;
  v10 = v92;
  if ( v92 )
  {
    v9 = (volatile signed __int32 *)operator new(0x18u);
    v78 = v9;
    *((_DWORD *)v9 + 2) = 1;
    *((_DWORD *)v9 + 3) = 1;
    *(_QWORD *)v9 = &std::_Ref_count_resource<IHttpRequestQueue *,com::deleter_t<IHttpRequestQueue>>::`vftable';
    *((_QWORD *)v9 + 2) = v10;
    v8 = v10;
    v80 = v10;
    v92 = 0;
  }
  hHandle = 0;
  v3 = (*(__int64 (__fastcall **)(LPVOID, HANDLE *))(*(_QWORD *)v8 + 32LL))(v8, &hHandle);
  v91 = v3;
  if ( v3 < 0 )
  {
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v9)((void *)v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    if ( v92 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v92 + 16LL))(v92);
    if ( v94 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v94 )
      {
        LOBYTE(v11) = v94 != v93;
        (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v94 + 32LL))(v94, v11);
      }
    }
    return (unsigned int)v3;
  }
  v12 = hHandle;
  v84 = (LPVOID *)hHandle;
  if ( (unsigned int)dword_1401D96E0 > 4 && (byte_1401D96F0 & 1) != 0 && (qword_1401D96F8 & 1) == qword_1401D96F8 )
    tlgWriteTransfer_EventWriteTransfer(
      (int)&dword_1401D96E0,
      (int)&byte_1401BA525,
      0,
      0,
      2u,
      (PEVENT_DATA_DESCRIPTOR)&v97);
  v13 = 0;
  v14 = 0;
  if ( WaitForSingleObject(v12, 0xFFFFFFFF) )
  {
LABEL_164:
    LastError = GetLastError();
    v64 = LastError;
    LODWORD(v77) = LastError;
    if ( LastError > 0 )
    {
      v64 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v77) = v64;
    }
    if ( v14 )
    {
      for ( i = 0; i < *((_DWORD *)v14 + 4); ++i )
      {
        v66 = *(void **)(*((_QWORD *)v14 + 3) + 8LL * i);
        if ( v66 )
          CoTaskMemFree(v66);
      }
      v67 = (void *)*((_QWORD *)v14 + 3);
      v68 = (void *)*((_QWORD *)v14 + 5);
      v69 = (_QWORD *)*((_QWORD *)v14 + 1);
      if ( v69 )
      {
        v70 = (void *)v69[1];
        v71 = (void *)v69[2];
        if ( v71 )
          CoTaskMemFree(v71);
        if ( v70 )
          CoTaskMemFree(v70);
        CoTaskMemFree(v69);
      }
      if ( v68 )
        CoTaskMemFree(v68);
      if ( v67 )
        CoTaskMemFree(v67);
      CoTaskMemFree(v14);
      v64 = v77;
    }
    if ( v13 )
      (**(void (__fastcall ***)(Microsoft::Applications::Events::HttpClient_WinInet *, __int64))v13)(v13, 1);
    if ( v12 )
      CloseHandle(v12);
    v72 = v78;
    if ( v78 )
    {
      if ( _InterlockedExchangeAdd(v78 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
        if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
      }
    }
    if ( v92 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v92 + 16LL))(v92);
    if ( v94 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v94 + 16LL))(v94);
      if ( v94 )
      {
        LOBYTE(v73) = v94 != v93;
        (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v94 + 32LL))(v94, v73);
      }
    }
    return v64;
  }
  while ( 1 )
  {
    if ( v14 )
      goto LABEL_85;
    if ( (unsigned int)dword_1401D96E0 > 4 && (byte_1401D96F0 & 1) != 0 && (qword_1401D96F8 & 1) == qword_1401D96F8 )
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1401D96E0, (int)&byte_1401BA76F, 0, 0, 2u, &v119);
    v97.m256i_i64[0] = (__int64)&std::_Func_impl_no_alloc<_lambda_47e483d324359776db742391f7e95409_,void,>::`vftable';
    v97.m256i_i64[1] = (__int64)&v91;
    v101 = (__int64)&v97;
    com::http::scope_exit::scope_exit(v95, &v97);
    v88 = 0;
    v3 = (*(__int64 (__fastcall **)(LPVOID, char **))(*(_QWORD *)v8 + 24LL))(v8, &v88);
    v91 = v3;
    if ( v3 < 0 )
      break;
    v14 = v88;
    v15 = (unsigned __int64)*((unsigned int *)v88 + 8) >> 5;
    v86 = v15;
    if ( (unsigned int)dword_1401D96E0 > 4 && (byte_1401D96F0 & 1) != 0 && (qword_1401D96F8 & 1) == qword_1401D96F8 )
    {
      LODWORD(v77) = v15;
      v81 = *((_DWORD *)v88 + 4);
      v74 = v88[1];
      v75 = *v88;
      v104 = &v77;
      v105 = 4;
      v102 = &v81;
      v103 = 4;
      v100 = &v74;
      v101 = 1;
      v98 = &v75;
      v99 = 1;
      tlgWriteTransfer_EventWriteTransfer(
        (int)&dword_1401D96E0,
        (int)&word_1401BA716,
        0,
        0,
        6u,
        (PEVENT_DATA_DESCRIPTOR)&v97);
    }
    v16 = v14[2] != 0;
    v17 = operator new(0xB0u);
    memset(v17, 0, 0xB0u);
    v19 = Microsoft::Applications::Events::HttpClient_WinInet::HttpClient_WinInet(
            (Microsoft::Applications::Events::HttpClient_WinInet *)v17,
            v16);
    v21 = v13;
    v13 = (Microsoft::Applications::Events::HttpClient_WinInet *)v19;
    if ( v21 )
      (**(void (__fastcall ***)(Microsoft::Applications::Events::HttpClient_WinInet *, __int64))v21)(v21, 1);
    LOBYTE(v18) = v14[1] != 0;
    v22 = *(_QWORD *)(v19 + 168);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 72LL))(v22, v18);
      v22 = *(_QWORD *)(v19 + 168);
    }
    else
    {
      *(_BYTE *)(v19 + 113) = v18;
    }
    LOBYTE(v18) = *v14 != 0;
    if ( v22 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 56LL))(v22, v18);
    else
      *(_BYTE *)(v19 + 112) = v18;
    v87 = *((_QWORD *)v14 + 5);
    v23 = 0;
    v24 = v86;
    if ( v86 )
    {
      v25 = 0;
      v26 = v87;
      do
      {
        v97 = *(__m256i *)(32 * v25 + v26);
        Microsoft::Applications::Events::HttpClient_WinInet::AddCustomRootCertSHA256Thumbprint(v13, &v97);
        v25 = ++v23;
      }
      while ( v23 < v24 );
      v12 = v84;
      v9 = v78;
    }
    v27 = 0;
    if ( *((_DWORD *)v14 + 4) )
    {
      do
      {
        LODWORD(v22) = v27;
        v28 = *(_BYTE **)(*((_QWORD *)v14 + 3) + 8LL * v27);
        if ( v28 )
        {
          memset(&v97, 0, sizeof(v97));
          v29 = -1;
          do
            ++v29;
          while ( v28[v29] );
          std::string::_Construct<1,char const *>(&v97, v28, v29);
          Microsoft::Applications::Events::HttpClient_WinInet::AddCustomTrustedSubjectOrg(v13, &v97);
          std::string::_Tidy_deallocate(&v97);
        }
        ++v27;
      }
      while ( v27 < *((_DWORD *)v14 + 4) );
      v9 = v78;
    }
    v30 = (unsigned int *)*((_QWORD *)v88 + 1);
    if ( v30 )
    {
      v97.m256i_i64[0] = *v30;
      *(_OWORD *)&v97.m256i_u64[1] = 0;
      *(_OWORD *)&v97.m256i_u64[1] = *(_OWORD *)(v30 + 2);
      v31 = Microsoft::Applications::Events::HttpClient_WinInet::SetGlobalOption(v22, &v97, v20);
      if ( (unsigned int)dword_1401D96E0 > 4 && (byte_1401D96F0 & 1) != 0 && (qword_1401D96F8 & 1) == qword_1401D96F8 )
      {
        v76 = v31;
        v32 = (const char *)*((_QWORD *)v30 + 2);
        v33 = (const char *)*((_QWORD *)v30 + 1);
        LODWORD(v77) = *v30;
        v115 = &v76;
        v116 = 1;
        if ( v32 )
        {
          v34 = -1;
          do
            ++v34;
          while ( v32[v34] );
          v35 = v34 + 1;
        }
        else
        {
          v32 = qword_140194AF8;
          v35 = 1;
        }
        v112 = v32;
        v113 = v35;
        v114 = 0;
        if ( v33 )
        {
          v36 = -1;
          do
            ++v36;
          while ( v33[v36] );
          v37 = v36 + 1;
        }
        else
        {
          v33 = qword_140194AF8;
          v37 = 1;
        }
        v109 = v33;
        v110 = v37;
        v111 = 0;
        v107 = (const char *)&v77;
        v108 = 4;
        tlgWriteTransfer_EventWriteTransfer((int)&dword_1401D96E0, (int)&byte_1401BA5F3, 0, 0, 6u, &v106);
      }
    }
    if ( v96 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v96 + 16LL))(v96);
      if ( v96 )
      {
        v38 = v95;
        LOBYTE(v38) = v96 != v95;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v96 + 32LL))(v96, v38);
      }
    }
    v8 = v80;
LABEL_85:
    v89 = 0;
    LODWORD(v77) = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v8 + 40LL))(v8, &v89);
    v91 = v77;
    if ( (int)v77 < 0 )
    {
      for ( j = 0; j < *((_DWORD *)v14 + 4); ++j )
      {
        v53 = *(void **)(*((_QWORD *)v14 + 3) + 8LL * j);
        if ( v53 )
          CoTaskMemFree(v53);
      }
      v54 = (void *)*((_QWORD *)v14 + 3);
      v55 = (void *)*((_QWORD *)v14 + 5);
      v56 = (_QWORD *)*((_QWORD *)v14 + 1);
      if ( v56 )
      {
        v57 = (void *)v56[1];
        v58 = (void *)v56[2];
        if ( v58 )
          CoTaskMemFree(v58);
        if ( v57 )
          CoTaskMemFree(v57);
        CoTaskMemFree(v56);
      }
      if ( v55 )
        CoTaskMemFree(v55);
      if ( v54 )
        CoTaskMemFree(v54);
      CoTaskMemFree(v14);
      if ( v13 )
        (**(void (__fastcall ***)(Microsoft::Applications::Events::HttpClient_WinInet *, __int64))v13)(v13, 1);
      if ( v12 )
        CloseHandle(v12);
      v59 = v78;
      if ( v78 )
      {
        if ( _InterlockedExchangeAdd(v78 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
          if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
        }
      }
      if ( v92 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v92 + 16LL))(v92);
      if ( v94 )
      {
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v94 + 16LL))(v94);
        if ( v94 )
        {
          LOBYTE(v60) = v94 != v93;
          (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v94 + 32LL))(v94, v60);
        }
      }
      return (unsigned int)v77;
    }
    v39 = v89;
    if ( (unsigned int)dword_1401D96E0 > 5 && (byte_1401D96F0 & 1) != 0 && (qword_1401D96F8 & 1) == qword_1401D96F8 )
    {
      v82 = *(_DWORD *)(v89 + 24);
      LODWORD(v83) = *(_DWORD *)(v89 + 48);
      v40 = *(const char **)(v89 + 8);
      v41 = *(const char **)(v89 + 16);
      v42 = *(const char **)v89;
      v117 = &v82;
      v118 = 4;
      v115 = (bool *)&v83;
      v116 = 4;
      if ( v40 )
      {
        v43 = -1;
        do
          ++v43;
        while ( v40[v43] );
        v44 = v43 + 1;
      }
      else
      {
        v40 = qword_140194AF8;
        v44 = 1;
      }
      v112 = v40;
      v113 = v44;
      v114 = 0;
      if ( v41 )
      {
        v45 = -1;
        do
          ++v45;
        while ( v41[v45] );
        v46 = v45 + 1;
      }
      else
      {
        v41 = qword_140194AF8;
        v46 = 1;
      }
      v109 = v41;
      v110 = v46;
      v111 = 0;
      if ( v42 )
      {
        v47 = -1;
        do
          ++v47;
        while ( v42[v47] );
        v48 = v47 + 1;
      }
      else
      {
        v42 = qword_140194AF8;
        v48 = 1;
      }
      v107 = v42;
      v108 = v48;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1401D96E0, (int)&word_1401BA54E, 0, 0, 7u, &v106);
    }
    v79 = 0;
    com::http::HttpRequest_by_HTTP_REQUEST(&v79);
    v49 = operator new(0x20u);
    v50 = v79;
    v79 = 0;
    if ( v9 )
      _InterlockedIncrement(v9 + 2);
    *(_QWORD *)v49 = &`anonymous namespace'::HttpResponseCallback::`vftable';
    *((_QWORD *)v49 + 1) = 0;
    *((_QWORD *)v49 + 2) = 0;
    if ( v9 )
      _InterlockedIncrement(v9 + 2);
    *((_QWORD *)v49 + 1) = v80;
    *((_QWORD *)v49 + 2) = v9;
    *((_QWORD *)v49 + 3) = v50;
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v9)((void *)v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    Microsoft::Applications::Events::HttpClient_WinInet::SendRequestAsync(
      v13,
      *((struct Microsoft::Applications::Events::IHttpRequest **)v49 + 3),
      (struct Microsoft::Applications::Events::IHttpResponseCallback *)v49);
    v51 = v79;
    if ( v79 )
      (**v79)(v79, 1);
    if ( v39 )
      com::http::request_deleter_t::operator()(v51, v39);
    if ( WaitForSingleObject(v12, 0xFFFFFFFF) )
      goto LABEL_164;
    v8 = v80;
  }
  if ( v96 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v96 + 16LL))(v96);
    if ( v96 )
    {
      v61 = v95;
      LOBYTE(v61) = v96 != v95;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v96 + 32LL))(v96, v61);
      v96 = 0;
    }
  }
  if ( v13 )
    (**(void (__fastcall ***)(Microsoft::Applications::Events::HttpClient_WinInet *, __int64))v13)(v13, 1);
  if ( v12 )
    CloseHandle(v12);
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v9)((void *)v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  if ( v92 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v92 + 16LL))(v92);
  if ( v94 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v94 + 16LL))(v94);
    if ( v94 )
    {
      LOBYTE(v62) = v94 != v93;
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v94 + 32LL))(v94, v62);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400eaa58  mov     rax, rsp
0x1400eaa5b  mov     [rax+8], rbx
0x1400eaa5f  mov     [rax+10h], rsi
0x1400eaa63  mov     [rax+18h], rdi
0x1400eaa67  push    rbp
0x1400eaa68  push    r12
0x1400eaa6a  push    r13
0x1400eaa6c  push    r14
0x1400eaa6e  push    r15
0x1400eaa70  lea     rbp, [rax-178h]
0x1400eaa77  sub     rsp, 250h
0x1400eaa7e  mov     rax, cs:__security_cookie
0x1400eaa85  xor     rax, rsp
0x1400eaa88  mov     [rbp+170h+var_30], rax
0x1400eaa8f  mov     r15d, 1
0x1400eaa95  lea     r12d, [r15+1]
0x1400eaa99  cmp     cs:dword_1401D96E0, 4
0x1400eaaa0  jbe     short loc_1400EAAE5
0x1400eaaa2  test    cs:byte_1401D96F0, r15b
0x1400eaaa9  jz      short loc_1400EAAE5
0x1400eaaab  mov     rax, cs:qword_1401D96F8
0x1400eaab2  and     rax, r15
0x1400eaab5  cmp     rax, cs:qword_1401D96F8
0x1400eaabc  jnz     short loc_1400EAAE5
0x1400eaabe  lea     rax, [rbp+170h+var_140]
0x1400eaac2  mov     [rsp+270h+var_248], rax; PEVENT_DATA_DESCRIPTOR
0x1400eaac7  mov     dword ptr [rsp+270h+ppv], r12d; ULONG
0x1400eaacc  xor     r9d, r9d; int
0x1400eaacf  xor     r8d, r8d; int
0x1400eaad2  lea     rdx, byte_1401BA6CF; int
0x1400eaad9  lea     rcx, dword_1401D96E0; int
0x1400eaae0  call    _tlgWriteTransfer_EventWriteTransfer
0x1400eaae5  xor     esi, esi
0x1400eaae7  mov     [rbp+170h+var_1D0], esi
0x1400eaaea  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_3e079bf40fa09c522011e0ccffb7ca47_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_3e079bf40fa09c522011e0ccffb7ca47_,void,>::`vftable'
0x1400eaaf1  mov     [rbp+170h+var_70.Ptr], rax
0x1400eaaf8  lea     rax, [rbp+170h+var_1D0]
0x1400eaafc  mov     qword ptr [rbp+170h+var_70.Size], rax
0x1400eab03  lea     rax, [rbp+170h+var_70]
0x1400eab0a  mov     [rbp+170h+var_38], rax
0x1400eab11  lea     rdx, [rbp+170h+var_70]
0x1400eab18  lea     rcx, [rbp+170h+var_1C0]
0x1400eab1c  call    ??0scope_exit@http@com@@QEAA@V?$function@$$A6AXXZ@std@@@Z; com::http::scope_exit::scope_exit(std::function<void (void)>)
0x1400eab21  call    ?register_marshalling@http@com@@YAJXZ; com::http::register_marshalling(void)
0x1400eab26  mov     ebx, eax
0x1400eab28  mov     [rbp+170h+var_1D0], eax
0x1400eab2b  test    eax, eax
0x1400eab2d  jns     short loc_1400EAB73
0x1400eab2f  mov     r8, [rbp+170h+var_188]
0x1400eab33  test    r8, r8
0x1400eab36  jz      short loc_1400EAB6C
0x1400eab38  mov     rax, [r8]
0x1400eab3b  mov     rcx, r8
0x1400eab3e  mov     rax, [rax+10h]
0x1400eab42  call    cs:__guard_dispatch_icall_fptr
0x1400eab48  mov     r8, [rbp+170h+var_188]
0x1400eab4c  test    r8, r8
0x1400eab4f  jz      short loc_1400EAB6C
0x1400eab51  mov     rcx, [r8]
0x1400eab54  mov     rax, [rcx+20h]
0x1400eab58  lea     rcx, [rbp+170h+var_1C0]
0x1400eab5c  cmp     r8, rcx
0x1400eab5f  setnz   dl
0x1400eab62  mov     rcx, r8
0x1400eab65  call    cs:__guard_dispatch_icall_fptr
0x1400eab6b  nop
0x1400eab6c  mov     eax, ebx
0x1400eab6e  jmp     loc_1400EB804
0x1400eab73  mov     [rbp+170h+var_1C8], rsi
0x1400eab77  lea     rax, [rbp+170h+var_1C8]
0x1400eab7b  mov     [rsp+270h+var_208], rax
0x1400eab80  mov     [rsp+270h+var_200], rsi
0x1400eab85  lea     rax, [rsp+270h+var_200]
0x1400eab8a  mov     [rsp+270h+ppv], rax; ppv
0x1400eab8f  lea     r9, IID_IHttpRequestQueue; riid
0x1400eab96  xor     edx, edx; pUnkOuter
0x1400eab98  lea     r8d, [rdx+4]; dwClsContext
0x1400eab9c  lea     rcx, rclsid; rclsid
0x1400eaba3  call    cs:__imp_CoCreateInstance
0x1400eaba9  mov     [rbp+170h+var_1D0], eax
0x1400eabac  mov     rdx, [rsp+270h+var_208]
0x1400eabb1  mov     rcx, [rdx]
0x1400eabb4  mov     rax, [rsp+270h+var_200]
0x1400eabb9  mov     [rdx], rax
0x1400eabbc  test    rcx, rcx
0x1400eabbf  jz      short loc_1400EABCF
0x1400eabc1  mov     rax, [rcx]
0x1400eabc4  mov     rax, [rax+10h]
0x1400eabc8  call    cs:__guard_dispatch_icall_fptr
0x1400eabce  nop
0x1400eabcf  mov     ebx, [rbp+170h+var_1D0]
0x1400eabd2  test    ebx, ebx
0x1400eabd4  jns     short loc_1400EAC2F
0x1400eabd6  mov     rcx, [rbp+170h+var_1C8]
0x1400eabda  test    rcx, rcx
0x1400eabdd  jz      short loc_1400EABED
0x1400eabdf  mov     rax, [rcx]
0x1400eabe2  mov     rax, [rax+10h]
0x1400eabe6  call    cs:__guard_dispatch_icall_fptr
0x1400eabec  nop
0x1400eabed  mov     r8, [rbp+170h+var_188]
0x1400eabf1  test    r8, r8
0x1400eabf4  jz      short loc_1400EAC2A
0x1400eabf6  mov     rax, [r8]
0x1400eabf9  mov     rcx, r8
0x1400eabfc  mov     rax, [rax+10h]
0x1400eac00  call    cs:__guard_dispatch_icall_fptr
0x1400eac06  mov     r8, [rbp+170h+var_188]
0x1400eac0a  test    r8, r8
0x1400eac0d  jz      short loc_1400EAC2A
0x1400eac0f  mov     rcx, [r8]
0x1400eac12  mov     rax, [rcx+20h]
0x1400eac16  lea     rcx, [rbp+170h+var_1C0]
0x1400eac1a  cmp     r8, rcx
0x1400eac1d  setnz   dl
0x1400eac20  mov     rcx, r8
0x1400eac23  call    cs:__guard_dispatch_icall_fptr
0x1400eac29  nop
0x1400eac2a  jmp     loc_1400EAB6C
0x1400eac2f  mov     rdi, rsi
0x1400eac32  mov     [rsp+270h+var_220], rsi
0x1400eac37  mov     r14, rsi
0x1400eac3a  mov     [rsp+270h+var_230], rsi
0x1400eac3f  mov     rbx, [rbp+170h+var_1C8]
0x1400eac43  test    rbx, rbx
0x1400eac46  jz      short loc_1400EAC7C
0x1400eac48  mov     ecx, 18h; Size
0x1400eac4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400eac52  mov     r14, rax
0x1400eac55  mov     [rsp+270h+var_230], rax
0x1400eac5a  mov     [rax+8], r15d
0x1400eac5e  mov     [rax+0Ch], r15d
0x1400eac62  lea     rax, ??_7?$_Ref_count_resource@PEAUIHttpRequestQueue@@U?$deleter_t@UIHttpRequestQueue@@@com@@@std@@6B@; const std::_Ref_count_resource<IHttpRequestQueue *,com::deleter_t<IHttpRequestQueue>>::`vftable'
0x1400eac69  mov     [r14], rax
0x1400eac6c  mov     [r14+10h], rbx
0x1400eac70  mov     rdi, rbx
0x1400eac73  mov     [rsp+270h+var_220], rbx
0x1400eac78  mov     [rbp+170h+var_1C8], rsi
0x1400eac7c  mov     [rbp+170h+hHandle], rsi
0x1400eac80  mov     rax, [rdi]
0x1400eac83  lea     rdx, [rbp+170h+hHandle]
0x1400eac87  mov     rcx, rdi
0x1400eac8a  mov     rax, [rax+20h]
0x1400eac8e  call    cs:__guard_dispatch_icall_fptr
0x1400eac94  mov     ebx, eax
0x1400eac96  mov     [rbp+170h+var_1D0], eax
0x1400eac99  test    eax, eax
0x1400eac9b  jns     loc_1400EAD3B
0x1400eaca1  test    r14, r14
0x1400eaca4  jz      short loc_1400EACE2
0x1400eaca6  or      eax, 0FFFFFFFFh
0x1400eaca9  lock xadd [r14+8], eax
0x1400eacaf  cmp     eax, 1
0x1400eacb2  jnz     short loc_1400EACE2
0x1400eacb4  mov     rax, [r14]
0x1400eacb7  mov     rcx, r14
0x1400eacba  mov     rax, [rax]
0x1400eacbd  call    cs:__guard_dispatch_icall_fptr
0x1400eacc3  or      eax, 0FFFFFFFFh
0x1400eacc6  lock xadd [r14+0Ch], eax
0x1400eaccc  cmp     eax, 1
0x1400eaccf  jnz     short loc_1400EACE2
0x1400eacd1  mov     rax, [r14]
0x1400eacd4  mov     rcx, r14
0x1400eacd7  mov     rax, [rax+8]
0x1400eacdb  call    cs:__guard_dispatch_icall_fptr
0x1400eace1  nop
0x1400eace2  mov     rcx, [rbp+170h+var_1C8]
0x1400eace6  test    rcx, rcx
0x1400eace9  jz      short loc_1400EACF9
0x1400eaceb  mov     rax, [rcx]
0x1400eacee  mov     rax, [rax+10h]
0x1400eacf2  call    cs:__guard_dispatch_icall_fptr
0x1400eacf8  nop
0x1400eacf9  mov     r8, [rbp+170h+var_188]
0x1400eacfd  test    r8, r8
0x1400ead00  jz      short loc_1400EAD36
0x1400ead02  mov     rax, [r8]
0x1400ead05  mov     rcx, r8
0x1400ead08  mov     rax, [rax+10h]
0x1400ead0c  call    cs:__guard_dispatch_icall_fptr
0x1400ead12  mov     r8, [rbp+170h+var_188]
0x1400ead16  test    r8, r8
0x1400ead19  jz      short loc_1400EAD36
0x1400ead1b  mov     rcx, [r8]
0x1400ead1e  mov     rax, [rcx+20h]
0x1400ead22  lea     rcx, [rbp+170h+var_1C0]
0x1400ead26  cmp     r8, rcx
0x1400ead29  setnz   dl
0x1400ead2c  mov     rcx, r8
0x1400ead2f  call    cs:__guard_dispatch_icall_fptr
0x1400ead35  nop
0x1400ead36  jmp     loc_1400EAB6C
0x1400ead3b  mov     r13, [rbp+170h+hHandle]
0x1400ead3f  mov     [rsp+270h+var_208], r13
0x1400ead44  cmp     cs:dword_1401D96E0, 4
0x1400ead4b  jbe     short loc_1400EAD90
0x1400ead4d  test    cs:byte_1401D96F0, r15b
0x1400ead54  jz      short loc_1400EAD90
0x1400ead56  mov     rax, cs:qword_1401D96F8
0x1400ead5d  and     rax, r15
0x1400ead60  cmp     rax, cs:qword_1401D96F8
0x1400ead67  jnz     short loc_1400EAD90
0x1400ead69  lea     rax, [rbp+170h+var_140]
0x1400ead6d  mov     [rsp+270h+var_248], rax; PEVENT_DATA_DESCRIPTOR
0x1400ead72  mov     dword ptr [rsp+270h+ppv], r12d; ULONG
0x1400ead77  xor     r9d, r9d; int
0x1400ead7a  xor     r8d, r8d; int
0x1400ead7d  lea     rdx, byte_1401BA525; int
0x1400ead84  lea     rcx, dword_1401D96E0; int
0x1400ead8b  call    _tlgWriteTransfer_EventWriteTransfer
0x1400ead90  mov     r12, rsi
0x1400ead93  mov     rbx, rsi
0x1400ead96  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400ead99  mov     rcx, r13; hHandle
0x1400ead9c  call    cs:__imp_WaitForSingleObject
0x1400eada2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400eada6  test    eax, eax
0x1400eada8  jnz     loc_1400EB691
0x1400eadae  test    rbx, rbx
0x1400eadb1  jnz     loc_1400EB1E2
0x1400eadb7  cmp     cs:dword_1401D96E0, 4
0x1400eadbe  jbe     short loc_1400EAE09
0x1400eadc0  test    cs:byte_1401D96F0, 1
0x1400eadc7  jz      short loc_1400EAE09
0x1400eadc9  mov     rax, cs:qword_1401D96F8
0x1400eadd0  and     eax, 1
0x1400eadd3  cmp     rax, cs:qword_1401D96F8
0x1400eadda  jnz     short loc_1400EAE09
0x1400eaddc  lea     rax, [rbp+170h+var_70]
0x1400eade3  mov     [rsp+270h+var_248], rax; PEVENT_DATA_DESCRIPTOR
0x1400eade8  mov     dword ptr [rsp+270h+ppv], 2; ULONG
0x1400eadf0  xor     r9d, r9d; int
0x1400eadf3  xor     r8d, r8d; int
0x1400eadf6  lea     rdx, byte_1401BA76F; int
0x1400eadfd  lea     rcx, dword_1401D96E0; int
0x1400eae04  call    _tlgWriteTransfer_EventWriteTransfer
0x1400eae09  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_47e483d324359776db742391f7e95409_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_47e483d324359776db742391f7e95409_,void,>::`vftable'
0x1400eae10  mov     [rbp+170h+var_140.Ptr], rax
0x1400eae14  lea     rax, [rbp+170h+var_1D0]
0x1400eae18  mov     qword ptr [rbp+170h+var_140.Size], rax
0x1400eae1c  lea     rax, [rbp+170h+var_140]
0x1400eae20  mov     [rbp+170h+var_108], rax
0x1400eae24  lea     rdx, [rbp+170h+var_140]
0x1400eae28  lea     rcx, [rbp+170h+var_180]
0x1400eae2c  call    ??0scope_exit@http@com@@QEAA@V?$function@$$A6AXXZ@std@@@Z; com::http::scope_exit::scope_exit(std::function<void (void)>)
0x1400eae31  mov     [rbp+170h+var_1E8], rsi
0x1400eae35  mov     rax, [rdi]
0x1400eae38  lea     rdx, [rbp+170h+var_1E8]
0x1400eae3c  mov     rcx, rdi
0x1400eae3f  mov     rax, [rax+18h]
0x1400eae43  call    cs:__guard_dispatch_icall_fptr
0x1400eae49  mov     ebx, eax
0x1400eae4b  mov     [rbp+170h+var_1D0], eax
0x1400eae4e  test    eax, eax
0x1400eae50  js      loc_1400EB595
0x1400eae56  mov     rbx, [rbp+170h+var_1E8]
0x1400eae5a  mov     edx, [rbx+20h]
0x1400eae5d  shr     rdx, 5
0x1400eae61  mov     [rsp+270h+var_1F8], rdx
0x1400eae66  mov     r8d, 4
0x1400eae6c  cmp     cs:dword_1401D96E0, r8d
0x1400eae73  jbe     loc_1400EAF21
0x1400eae79  test    cs:byte_1401D96F0, 1
0x1400eae80  jz      loc_1400EAF21
0x1400eae86  mov     rax, cs:qword_1401D96F8
0x1400eae8d  and     eax, 1
0x1400eae90  cmp     rax, cs:qword_1401D96F8
0x1400eae97  jnz     loc_1400EAF21
0x1400eae9d  mov     dword ptr [rsp+270h+var_238], edx
0x1400eaea1  mov     eax, [rbx+10h]
0x1400eaea4  mov     [rsp+270h+var_218], eax
0x1400eaea8  mov     al, [rbx+1]
0x1400eaeab  mov     byte ptr [rsp+270h+var_240], al
0x1400eaeaf  mov     al, [rbx]
0x1400eaeb1  mov     byte ptr [rsp+270h+var_240+1], al
0x1400eaeb5  lea     rax, [rsp+270h+var_238]
0x1400eaeba  mov     [rbp+170h+var_F0], rax
0x1400eaec1  mov     [rbp+170h+var_E8], r8
0x1400eaec8  lea     rax, [rsp+270h+var_218]
0x1400eaecd  mov     [rbp+170h+var_100], rax
0x1400eaed1  mov     [rbp+170h+var_F8], r8
0x1400eaed5  lea     rax, [rsp+270h+var_240]
0x1400eaeda  mov     [rbp+170h+var_110], rax
0x1400eaede  mov     [rbp+170h+var_108], 1
0x1400eaee6  lea     rax, [rsp+270h+var_240+1]
0x1400eaeeb  mov     [rbp+170h+var_120], rax
0x1400eaeef  mov     [rbp+170h+var_118], 1
0x1400eaef7  lea     rax, [rbp+170h+var_140]
0x1400eaefb  mov     [rsp+270h+var_248], rax; PEVENT_DATA_DESCRIPTOR
0x1400eaf00  mov     dword ptr [rsp+270h+ppv], 6; ULONG
0x1400eaf08  xor     r9d, r9d; int
0x1400eaf0b  xor     r8d, r8d; int
0x1400eaf0e  lea     rdx, word_1401BA716; int
0x1400eaf15  lea     rcx, dword_1401D96E0; int
0x1400eaf1c  call    _tlgWriteTransfer_EventWriteTransfer
0x1400eaf21  cmp     [rbx+2], sil
0x1400eaf25  setnz   sil
0x1400eaf29  mov     ecx, 0B0h; Size
0x1400eaf2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
  ... truncated ...
```
