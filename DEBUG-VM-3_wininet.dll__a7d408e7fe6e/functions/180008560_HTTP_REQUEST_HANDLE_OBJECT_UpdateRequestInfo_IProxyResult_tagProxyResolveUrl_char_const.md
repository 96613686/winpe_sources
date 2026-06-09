# HTTP_REQUEST_HANDLE_OBJECT::UpdateRequestInfo(IProxyResult *,tagProxyResolveUrl *,char const *)

- ea: `0x180008560`
- end: `0x180009ce1`
- name: `?UpdateRequestInfo@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEAUIProxyResult@@PEAUtagProxyResolveUrl@@PEBD@Z`
- size: `6017`
- prototype: `unsigned int __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, struct IProxyResult *, struct tagProxyResolveUrl *, const char *)`
- caller_count: `1`
- callee_count: `45`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180031150`

## callees

- `0x180008560`
- `0x180009cf0`
- `0x18000cd64`
- `0x18000d360`
- `0x1800100d0`
- `0x180012a40`
- `0x180016c48`
- `0x1800178dc`
- `0x180030588`
- `0x18003602c`
- `0x1800701d0`
- `0x1800c14f4`
- `0x1800c1c50`
- `0x1800ca050`
- `0x1800ca1b4`
- `0x1800ca2d0`
- `0x1800cccbc`
- `0x1800cd7a0`
- `0x1800da530`
- `0x1800dadac`
- `0x1800e3b34`
- `0x1800f20bc`
- `0x180114434`
- `0x180117e30`
- `0x180117f9c`
- `0x18011fcc8`
- `0x18012ae0c`
- `0x180136824`
- `0x180136c6c`
- `0x1801487c8`
- `0x18014a7a0`
- `0x18014a7e0`
- `0x18014b3b4`
- `0x180154882`
- `0x1801d4be8`
- `0x1801d7fb4`
- `0x1801e1790`
- `0x1801e2c8c`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e67a8`
- `0x1801e7d84`
- `0x1801e7e14`
- `0x1801e8ab4`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008897`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008897`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009999`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009999`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a97`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008631`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000869f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008754`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800087c2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008631`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000869f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180008754`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800087c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e0a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180009047`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180009047`
- `ntdll!RtlNtStatusToDosError` at `0x1800090a5`
- `ntdll!RtlNtStatusToDosError` at `0x1800090a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800089fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008ddb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008773`

## string_xrefs

- `0x180009159`: `no-cache`
- `0x180009354`: `no-cache`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::UpdateRequestInfo(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        struct IProxyResult *a2,
        const WCHAR **a3,
        const char *a4)
{
  const char *v5; // r12
  const WCHAR *v7; // rax
  unsigned int v8; // r15d
  char *v9; // rsi
  CHAR *v10; // rbx
  CHAR *v11; // rdi
  __int64 v12; // r14
  signed int v13; // r15d
  unsigned int v14; // eax
  CHAR *v15; // rax
  signed int v16; // eax
  signed int LastError; // eax
  const WCHAR *v18; // rax
  unsigned int v19; // eax
  CHAR *v20; // rax
  CHAR *v21; // rbx
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rbx
  unsigned int v25; // eax
  int v26; // r9d
  char *v27; // rcx
  _QWORD *v28; // rax
  _DWORD *v29; // rdx
  unsigned int v30; // r15d
  unsigned __int8 *v31; // r8
  int v32; // edx
  unsigned __int8 v33; // al
  int v34; // edx
  __int64 v35; // r8
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // r11
  int v39; // ecx
  char *v40; // r15
  unsigned int v41; // r9d
  __int64 *v42; // rdx
  unsigned int i; // r10d
  unsigned int v44; // eax
  char *v45; // r8
  int v46; // eax
  char *v47; // r15
  int v48; // ecx
  int v49; // eax
  unsigned int v50; // r15d
  int v51; // edx
  int v52; // ecx
  int v53; // r8d
  void *v54; // r8
  __int64 v55; // r9
  size_t v56; // rbx
  struct CServerInfo *v57; // rcx
  unsigned int v58; // edx
  unsigned int ServerInfo; // eax
  void *v60; // rcx
  CHttpHeaders *v62; // r12
  _QWORD *v63; // r14
  HTTP_REQUEST_HANDLE_OBJECT *v64; // rcx
  __int64 v65; // rbx
  unsigned int v66; // r10d
  __int64 v67; // rbx
  __int64 v68; // rcx
  int v69; // eax
  unsigned int v70; // ecx
  __int64 v71; // r8
  CHAR v72; // dl
  _QWORD *v73; // rbx
  unsigned int v74; // r12d
  _QWORD *v75; // rcx
  unsigned int v76; // edx
  _QWORD *v77; // r14
  __int64 v78; // rcx
  int v79; // eax
  signed int v80; // ebx
  __int64 v81; // r12
  __int64 v82; // r14
  ULONG v83; // eax
  unsigned int v84; // r14d
  int v85; // eax
  int v86; // ebx
  unsigned int v87; // ebx
  int v88; // eax
  unsigned int v89; // r9d
  __int64 v90; // rdx
  CHAR v91; // cl
  _QWORD *v92; // r14
  HTTP_REQUEST_HANDLE_OBJECT *v93; // rcx
  __int64 v94; // rbx
  _QWORD *v95; // rcx
  _QWORD *v96; // rax
  int v97; // eax
  int v98; // eax
  unsigned int v99; // eax
  unsigned int v100; // eax
  bool v101; // sf
  bool v102; // sf
  int v103; // eax
  int v104; // eax
  __int64 v105; // rcx
  int v106; // eax
  int v107; // edx
  int v108; // ecx
  int v109; // r8d
  const char *v110; // rax
  int v111; // r10d
  unsigned int AuthState; // eax
  void *v113; // [rsp+50h] [rbp-B0h]
  __int64 v114; // [rsp+50h] [rbp-B0h]
  int Sizea; // [rsp+58h] [rbp-A8h]
  unsigned int Size; // [rsp+58h] [rbp-A8h]
  unsigned int Size_4; // [rsp+5Ch] [rbp-A4h]
  unsigned int Size_4a; // [rsp+5Ch] [rbp-A4h]
  CHAR *lpMultiByteStr; // [rsp+60h] [rbp-A0h]
  CHAR *v120; // [rsp+60h] [rbp-A0h]
  const CHAR *v121; // [rsp+60h] [rbp-A0h]
  int cbMultiByte; // [rsp+70h] [rbp-90h]
  int v123; // [rsp+70h] [rbp-90h]
  int v124; // [rsp+70h] [rbp-90h]
  size_t v125; // [rsp+78h] [rbp-88h]
  size_t v126; // [rsp+78h] [rbp-88h]
  char *v127; // [rsp+78h] [rbp-88h]
  _QWORD *v128; // [rsp+78h] [rbp-88h]
  unsigned int v129[2]; // [rsp+80h] [rbp-80h] BYREF
  void *v130; // [rsp+88h] [rbp-78h] BYREF
  struct IProxyResult *v131; // [rsp+90h] [rbp-70h]
  unsigned int v132; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v133; // [rsp+9Ch] [rbp-64h] BYREF
  LPCWCH lpWideCharStr; // [rsp+A0h] [rbp-60h]
  __int16 v135[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v136; // [rsp+ACh] [rbp-54h] BYREF
  int v137; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  int v139; // [rsp+C0h] [rbp-40h] BYREF
  int v140[3]; // [rsp+C4h] [rbp-3Ch] BYREF
  char Src[272]; // [rsp+D0h] [rbp-30h] BYREF

  v131 = a2;
  v130 = a3;
  v5 = a4;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_qsq(
      1025,
      64,
      (unsigned int)&WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids,
      (_DWORD)a2,
      (__int64)a4,
      (__int64)a3);
  v7 = a3[1];
  pv = 0;
  v8 = 0;
  v136 = 0;
  v9 = 0;
  v135[0] = 0;
  v137 = 0;
  v10 = 0;
  v139 = 0;
  v11 = 0;
  v140[0] = 0;
  v129[0] = 0;
  lpWideCharStr = v7;
  lpMultiByteStr = 0;
  if ( !v7 )
    goto LABEL_96;
  v12 = -1;
  v13 = -2147024882;
  if ( GlobalSafeToAssumeUTF8 )
  {
    v14 = WideCharToMultiByte(0xFDE9u, 0, v7, -1, 0, 0, 0, 0);
    cbMultiByte = v14;
    if ( v14 )
    {
      v125 = v14;
      v15 = (CHAR *)CoTaskMemAlloc(v14);
      lpMultiByteStr = v15;
      if ( v15 )
      {
        memset_0(v15, 0, v125);
        if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
        {
          v16 = 0;
LABEL_9:
          v10 = lpMultiByteStr;
LABEL_13:
          v11 = v10;
          goto LABEL_14;
        }
        LastError = WxGetLastError();
        v102 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v102 = LastError < 0;
        }
        if ( !v102 )
          LastError = -2147418113;
        Sizea = LastError;
        CoTaskMemFree(lpMultiByteStr);
        v16 = Sizea;
        if ( Sizea >= 0 )
          goto LABEL_13;
      }
      else
      {
        v16 = -2147024882;
      }
    }
    else
    {
      v16 = WxGetLastError();
      v101 = v16 < 0;
      if ( v16 > 0 )
      {
        v16 = (unsigned __int16)v16 | 0x80070000;
        v101 = v16 < 0;
      }
      if ( !v101 )
        v16 = -2147418113;
    }
  }
  else
  {
    v16 = WxNewStringWtoACchCp<WxCoTaskAllocator>(v7);
    if ( v16 >= 0 )
      goto LABEL_9;
  }
LABEL_14:
  if ( v16 < 0 )
  {
    v8 = 0;
    goto LABEL_96;
  }
  v18 = (const WCHAR *)*((_QWORD *)v130 + 2);
  lpWideCharStr = v18;
  if ( !v18 )
  {
    v8 = 0;
    goto LABEL_96;
  }
  if ( GlobalSafeToAssumeUTF8 )
  {
    v19 = WideCharToMultiByte(0xFDE9u, 0, v18, -1, 0, 0, 0, 0);
    v123 = v19;
    if ( v19 )
    {
      v126 = v19;
      v20 = (CHAR *)CoTaskMemAlloc(v19);
      v120 = v20;
      if ( v20 )
      {
        memset_0(v20, 0, v126);
        if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, v120, v123, 0, 0) )
        {
          v21 = v120;
          v13 = 0;
LABEL_24:
          v9 = v21;
          goto LABEL_25;
        }
        v104 = WxGetLastError();
        v13 = v104;
        if ( v104 > 0 )
          v13 = (unsigned __int16)v104 | 0x80070000;
        if ( v13 >= 0 )
          v13 = -2147418113;
        CoTaskMemFree(v120);
      }
    }
    else
    {
      v103 = WxGetLastError();
      v13 = v103;
      if ( v103 > 0 )
        v13 = (unsigned __int16)v103 | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147418113;
    }
  }
  else
  {
    v21 = 0;
    v13 = WxNewStringWtoACchCp<WxCoTaskAllocator>(v18);
    if ( v13 >= 0 )
      goto LABEL_24;
  }
LABEL_25:
  if ( v13 < 0 )
  {
    v8 = 0;
    goto LABEL_96;
  }
  v22 = (*(__int64 (__fastcall **)(struct IProxyResult *, int *))(*(_QWORD *)v131 + 24LL))(v131, &v137);
  if ( v22 < 0 )
    goto LABEL_255;
  v23 = *(_QWORD *)v131;
  if ( !v137 )
  {
    v22 = (*(__int64 (__fastcall **)(struct IProxyResult *, int *, int *))(v23 + 32))(v131, &v139, v140);
    if ( v22 >= 0 )
      goto LABEL_29;
LABEL_255:
    v8 = WX_WIN32_FROM_HR((unsigned int)v22);
    goto LABEL_96;
  }
  v98 = (*(__int64 (__fastcall **)(struct IProxyResult *, int *, LPVOID *, __int16 *))(v23 + 48))(
          v131,
          &v136,
          &pv,
          v135);
  if ( v98 < 0 )
  {
    v8 = WX_WIN32_FROM_HR((unsigned int)v98);
    goto LABEL_96;
  }
  v8 = HostWCharToCharEx((LPCWSTR)pv, -1, (__int64)v129);
  if ( v8 )
    goto LABEL_96;
LABEL_29:
  if ( v136 == 8 )
  {
    if ( pv )
      WxCoTaskAllocator::Free(&pv);
    v139 = 1;
    v140[0] = 0;
  }
  if ( *((_DWORD *)this + 248) && (*((_DWORD *)this + 1319) & 0x200) == 0 && (!v137 || ((v136 - 4) & 0xFFFFFFFB) == 0) )
  {
    v8 = 12019;
    goto LABEL_96;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 3024));
  v24 = -1;
  if ( !v5 )
    v5 = v9;
  do
    ++v24;
  while ( v5[v24] );
  v25 = *((_DWORD *)this + 766);
  v124 = v25;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v106 = MapHttpMethodType(v25);
    WPP_SF_ssdsd(v108, v107, v109, v106, (__int64)v5, v24, 0, 0);
    v25 = v124;
  }
  if ( *((_QWORD *)this + 371) )
  {
    if ( v25 == -1 )
    {
      v29 = (_DWORD *)((char *)this + 2888);
      v26 = *((_DWORD *)this + 722);
      v28 = (_QWORD *)((char *)this + 2880);
      v27 = (char *)*((_QWORD *)this + 360);
      Size_4 = v26;
      goto LABEL_41;
    }
    if ( v25 <= 0x1E )
    {
      _mm_lfence();
      v26 = dword_1801F1D50[6 * v25];
      Size_4 = v26;
      if ( v26 != -1 )
      {
        v27 = (&off_1801F1D58)[3 * (int)v25];
        v28 = (_QWORD *)((char *)this + 2880);
        v29 = (_DWORD *)((char *)this + 2888);
LABEL_41:
        v127 = v27;
        v121 = (const CHAR *)*((_QWORD *)this + 364);
        Size = *((_DWORD *)this + 730);
        *v28 = 0;
        v30 = 0;
        *v29 = 0;
        *((_DWORD *)this + 718) += -2 - *((_DWORD *)this + 744);
        *((_QWORD *)this + 362) = 0;
        *((_DWORD *)this + 726) = 0;
        *((_QWORD *)this + 364) = 0;
        *((_DWORD *)this + 730) = 0;
        v132 = 0;
        v133 = 0;
        if ( v27 )
        {
          v31 = (unsigned __int8 *)v27;
          v32 = v26;
          if ( v26 )
          {
            while ( 1 )
            {
              v33 = *v31;
              if ( *v31 != 9 && v33 != 32 )
                break;
              if ( !--v32 )
                goto LABEL_52;
              ++v31;
            }
            if ( v32 )
            {
              while ( v33 > 0x20u && v33 < 0x7Fu )
              {
                if ( !--v32 )
                  goto LABEL_52;
                v33 = *++v31;
              }
              while ( (unsigned int)IsLWS(*v31) )
              {
                v31 = (unsigned __int8 *)(v35 + 1);
                if ( v34 == 1 )
                  goto LABEL_52;
              }
              v30 = -2147024809;
            }
          }
        }
LABEL_52:
        v36 = WX_WIN32_FROM_HR(v30);
        v37 = (unsigned int)v36;
        if ( v36 > 0 )
          v37 = (unsigned __int16)v36 | 0x80070000;
        if ( (int)v37 < 0 )
          goto LABEL_68;
        v38 = *((_QWORD *)this + 358);
        v39 = 0;
        v40 = 0;
        v41 = v24 + Size_4 + Size + 2;
        LODWORD(lpWideCharStr) = v41;
        v113 = 0;
        v130 = 0;
        if ( v41 > *(_DWORD *)(v38 + 4) )
        {
          v39 = 1;
        }
        else
        {
          v42 = *(__int64 **)(v38 + 8);
          for ( i = 0; i < 0xA && v42 != (__int64 *)(v38 + 8); ++i )
          {
            v44 = *((_DWORD *)v42 + 4);
            if ( v44 >= v41 )
            {
              v45 = (char *)v42[3];
              *((_DWORD *)v42 + 4) = v44 - v41;
              v42[3] = (__int64)&v45[v41];
              if ( v45 )
              {
                v40 = v45;
                v130 = v45;
                goto LABEL_62;
              }
              break;
            }
            v42 = (__int64 *)*v42;
          }
          v39 = 1;
LABEL_62:
          v113 = v40;
        }
        if ( v39 )
        {
          v97 = WxFastHeapAllocator::CreateAllocationEntry((WxFastHeapAllocator *)v38, v41, &v130);
          v37 = (unsigned int)v97;
          if ( v97 < 0 )
          {
LABEL_68:
            v49 = WX_WIN32_FROM_HR(v37);
            v50 = v49;
            if ( v49 > 0 )
              v50 = (unsigned __int16)v49 | 0x80070000;
            goto LABEL_70;
          }
          v40 = (char *)v130;
          v113 = v130;
        }
        v46 = _ParseHttpVersion(v121, Size, &v132, &v133);
        LODWORD(v130) = v46;
        v37 = (unsigned int)v46;
        if ( v46 > 0 )
        {
          v37 = (unsigned __int16)v46 | 0x80070000;
          LODWORD(v130) = (unsigned __int16)v46 | 0x80070000;
        }
        if ( (int)v37 >= 0 )
        {
          memcpy_0(v40, v127, Size_4);
          v40[Size_4] = 32;
          v47 = &v40[Size_4 + 1];
          memcpy_0(v47, v5, (unsigned int)v24);
          v47[(unsigned int)v24] = 32;
          memcpy_0(&v47[(unsigned int)v24 + 1], v121, Size);
          v48 = (int)lpWideCharStr;
          *((_QWORD *)this + 364) = &v47[(unsigned int)v24 + 1];
          v12 = -1;
          *((_DWORD *)this + 744) = v48;
          *((_DWORD *)this + 722) = Size_4;
          *((_DWORD *)this + 718) += v48 + 2;
          v37 = (unsigned int)v130;
          *((_QWORD *)this + 360) = v113;
          *((_QWORD *)this + 371) = v113;
          *((_DWORD *)this + 739) = v132;
          *((_DWORD *)this + 740) = v133;
          *((_QWORD *)this + 362) = v47;
          *((_DWORD *)this + 726) = v24;
          *((_DWORD *)this + 730) = Size;
        }
        goto LABEL_68;
      }
    }
  }
  v50 = -2147024809;
LABEL_70:
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v99 = WX_WIN32_FROM_HR(v50);
    WPP_SF_d(1025, 48, &WPP_764547bcea91352f6757a10208e155bd_Traceguids, v99);
  }
  if ( !(unsigned int)WX_WIN32_FROM_HR(v50) )
    *((_DWORD *)this + 766) = v124;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_dsddsd(v52, v51, v53, *((_DWORD *)this + 1323), *((_QWORD *)this + 660), *((_WORD *)this + 2644), -1, 0, 0);
  v54 = (void *)*((_QWORD *)this + 660);
  if ( v54 )
    HeapFree(g_hWxProcessHeap, 0, v54);
  *((_QWORD *)this + 660) = 0;
  *((_WORD *)this + 2644) = 0;
  *((_DWORD *)this + 1323) = -1;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    WPP_SF_d(1025, 27, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, 0);
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_qqq(
        1025,
        30,
        (unsigned int)&WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids,
        (_DWORD)this,
        *((_QWORD *)this + 664),
        0);
  }
  v55 = *((_QWORD *)this + 664);
  if ( v55 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_q(1025, 31, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, v55);
    v105 = *((_QWORD *)this + 664);
    if ( v105 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
      *((_QWORD *)this + 664) = 0;
    }
  }
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_(1025, 32, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids);
  if ( *((_QWORD *)this + 122) && v11 )
  {
    do
      ++v12;
    while ( v11[v12] );
    v56 = (unsigned int)v12;
    if ( (unsigned int)v12 > 0x100 )
      v56 = 256;
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_sd(1032, 47, (unsigned int)&WPP_ebf5ebc2fb2b37980c6e0149dcb01477_Traceguids, (_DWORD)v11, v12);
    v57 = (struct CServerInfo *)*((_QWORD *)this + 122);
    if ( v57 )
      ReleaseServerInfo(v57);
    memcpy_0(Src, v11, v56);
    if ( v56 >= 0x101 )
      _report_rangecheckfailure();
    v58 = *((_DWORD *)this + 161);
    Src[v56] = 0;
    ServerInfo = GetServerInfo(Src, v58, (struct CServerInfo **)this + 122);
    v8 = ServerInfo;
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_d(1032, 48, &WPP_ebf5ebc2fb2b37980c6e0149dcb01477_Traceguids, ServerInfo);
    if ( v8 )
      goto LABEL_95;
  }
  v62 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
  if ( *((_DWORD *)this + 1288) )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sd(
        1025,
        82,
        (unsigned int)&WPP_764547bcea91352f6757a10208e155bd_Traceguids,
        (unsigned int)"Connection",
        23);
    v92 = (_QWORD *)((char *)this + 1656);
    v93 = (HTTP_REQUEST_HANDLE_OBJECT *)*((_QWORD *)this + 207);
    v94 = (__int64)v93 - 16;
    if ( v93 == (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1656) )
      v94 = 0;
    while ( v94 )
    {
      CHttpHeaders::_RemoveHeaderFromLists(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        (struct _HEADER_LIST_ENTRY *)v94);
      if ( *(_DWORD *)(v94 + 72) )
      {
        WxHeapFree<char>(v94 + 56);
        *(_DWORD *)(v94 + 64) = 0;
      }
      v94 = *v92 - 16LL;
      if ( (_QWORD *)*v92 == v92 )
        v94 = 0;
    }
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_(1025, 83, &WPP_764547bcea91352f6757a10208e155bd_Traceguids);
    v66 = 69;
  }
  else
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sd(
        1025,
        82,
        (unsigned int)&WPP_764547bcea91352f6757a10208e155bd_Traceguids,
        (unsigned int)"Proxy-Connection",
        69);
    v63 = (_QWORD *)((char *)this + 2392);
    v64 = (HTTP_REQUEST_HANDLE_OBJECT *)*((_QWORD *)this + 299);
    v65 = (__int64)v64 - 16;
    if ( v64 == (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 2392) )
      v65 = 0;
    while ( v65 )
    {
      CHttpHeaders::_RemoveHeaderFromLists(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        (struct _HEADER_LIST_ENTRY *)v65);
      if ( *(_DWORD *)(v65 + 72) )
      {
        WxHeapFree<char>(v65 + 56);
        *(_DWORD *)(v65 + 64) = 0;
      }
      v65 = *v63 - 16LL;
      if ( (_QWORD *)*v63 == v63 )
        v65 = 0;
    }
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_(1025, 83, &WPP_764547bcea91352f6757a10208e155bd_Traceguids);
    v66 = 23;
  }
  v67 = 16LL * v66;
  v68 = v66;
  Size_4a = v66;
  v114 = v66;
  if ( *(HTTP_REQUEST_HANDLE_OBJECT **)((char *)this + v67 + 1288) != (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + v67 + 1288) )
  {
    *((_DWORD *)this + 317) |= 0x400000u;
    *((_DWORD *)this + 1289) = 1;
  }
  v69 = *((_DWORD *)this + 317);
  v8 = 0;
  if ( GlobalDisableKeepAlive )
  {
    HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(this, 0x17u);
    HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(this, 0x45u);
    if ( (unsigned int)HTTP_REQUEST_HANDLE_OBJECT::IsRequestHttp1_1(this) )
      CHttpHeaders::ReplaceHeaderByIndex(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        0x17u,
        "Close",
        5u,
        0,
        0x20000000u);
    *((_DWORD *)this + 317) &= ~0x400000u;
    v69 = *((_DWORD *)this + 317);
    v66 = Size_4a;
    v68 = v114;
  }
  if ( (v69 & 0x400000) != 0 )
  {
    *((_DWORD *)this + 1289) = 1;
    v70 = 10;
    do
    {
      v71 = v70 - 1;
      v72 = aKeepAlive[v71];
      if ( v72 != 9 && v72 != 32 )
        break;
      --v70;
    }
    while ( (_DWORD)v71 );
    CHttpHeaders::_ReplaceHeader(
      (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
      v66,
      0,
      0,
      "Keep-Alive",
      v70,
      0,
      0x10000000u);
    v66 = Size_4a;
    v68 = v114;
  }
  if ( *((_DWORD *)this + 739) <= 1u && (*((_DWORD *)this + 739) != 1 || !*((_DWORD *)this + 740)) )
    goto LABEL_168;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    v110 = InternetMapHttpOption(v66);
    WPP_SF_ds(1025, 68, (unsigned int)&WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, v111, (__int64)v110);
    v68 = v114;
  }
  v129[0] = 0;
  v73 = (_QWORD *)((char *)this + v67 + 1288);
  v74 = 0;
  v128 = v73;
  while ( 1 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sd(
        1025,
        43,
        (unsigned int)&WPP_764547bcea91352f6757a10208e155bd_Traceguids,
        *((_QWORD *)&GlobalKnownHeaders + 3 * v68),
        v74);
    v75 = (_QWORD *)*v73;
    v76 = v74;
    HIDWORD(v131) = 0;
    v77 = v75 - 2;
    if ( v75 == v73 )
      v77 = 0;
    if ( v74 )
    {
      while ( v77 )
      {
        v95 = (_QWORD *)v77[2];
        v96 = 0;
        if ( v95 != v73 )
          v96 = v95 - 2;
        v77 = v96;
        if ( !--v76 )
          goto LABEL_137;
      }
    }
    else
    {
LABEL_137:
      if ( v77 )
        goto LABEL_139;
    }
    HIDWORD(v131) = 2854;
LABEL_139:
    v78 = 2148282230LL;
    if ( v77 )
      v78 = 0;
    v79 = WX_WIN32_FROM_HR(v78);
    v80 = v79;
    if ( v79 > 0 )
      v80 = (unsigned __int16)v79 | 0x80070000;
    if ( v80 < 0 )
    {
      HIDWORD(v131) = 4850;
      v81 = 16;
      v82 = 24;
    }
    else
    {
      v81 = (__int64)(v77 + 7);
      v82 = (__int64)(v77 + 8);
    }
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      v100 = WX_WIN32_FROM_HR((unsigned int)v80);
      WPP_SF_d(1025, 44, &WPP_764547bcea91352f6757a10208e155bd_Traceguids, v100);
    }
    if ( (v80 & 0x1FFF0000) == 0xC0000 )
    {
      v80 = (unsigned __int16)v80;
    }
    else
    {
      if ( v80 >= 0 )
        goto LABEL_149;
      if ( (v80 & 0x1FFF0000) == 0x70000
        || (v80 & 0x10000000) != 0 && (v83 = RtlNtStatusToDosError(v80 & 0xEFFFFFFF)) != 0 && v83 != 317 )
      {
LABEL_161:
        v84 = 0;
        v85 = 1;
        goto LABEL_162;
      }
    }
    if ( v80 )
      goto LABEL_161;
LABEL_149:
    if ( *(_DWORD *)v82 == 5 && !StrCmpNICA(*(LPCSTR *)v81, "Close", 5) )
      break;
    v73 = v128;
    v74 = v129[0] + 1;
    v68 = v114;
    ++v129[0];
  }
  v85 = 1;
  v84 = 1;
LABEL_162:
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    WPP_SF_d(1025, 69, &WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, v84);
    v85 = 1;
  }
  v86 = *((_DWORD *)this + 317);
  if ( v84 || (*((_DWORD *)this + 1319) & 0x200) != 0 )
  {
    HTTP_REQUEST_HANDLE_OBJECT::RemoveAllRequestHeadersByName(this, Size_4a);
    if ( (*((_DWORD *)this + 1319) & 0x200) != 0
      || HTTP_REQUEST_HANDLE_OBJECT::GetAuthState(this) && HTTP_REQUEST_HANDLE_OBJECT::GetAuthState(this) != 1 )
    {
      if ( (xmmword_180266B60 & 2) != 0 )
      {
        AuthState = HTTP_REQUEST_HANDLE_OBJECT::GetAuthState(this);
        WPP_SF_d(1025, 66, &WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, AuthState);
      }
      *((_DWORD *)this + 310) = 1;
      v62 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
    }
    else
    {
      v62 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
      CHttpHeaders::ReplaceHeaderByIndex(
        (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280),
        Size_4a,
        "Close",
        5u,
        0,
        0x20000000u);
    }
    v85 = 0;
    v87 = v86 & 0xFFBFFFFF;
  }
  else
  {
    v87 = v86 | 0x400000;
    v62 = (HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 1280);
  }
  *((_DWORD *)this + 1289) = v85;
  *((_DWORD *)this + 317) = v87;
LABEL_168:
  v88 = *((_DWORD *)this + 191);
  if ( *((_DWORD *)this + 766) == 2 && !*((_QWORD *)this + 86) )
    v88 |= 0x80000000;
  if ( (v88 & 0x80000100) != 0 )
  {
    if ( *((_DWORD *)this + 1288) )
      goto LABEL_204;
    if ( (v88 & 0x800) != 0 )
      goto LABEL_95;
    if ( !GlobalEnableHttp1_1 )
    {
LABEL_204:
      CHttpHeaders::ReplaceHeaderByIndex(v62, 0x11u, "no-cache", 8u, 0, 0x10000000u);
    }
    else
    {
      v89 = 8;
      do
      {
        v90 = v89 - 1;
        v91 = aNoCache[v90];
        if ( v91 != 9 && v91 != 32 )
          break;
        --v89;
      }
      while ( (_DWORD)v90 );
      CHttpHeaders::_ReplaceHeader(v62, 0x31u, 0, 0, "no-cache", v89, 0, 0x10000000u);
    }
  }
LABEL_95:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 3024));
LABEL_96:
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_d(1025, 67, &WPP_a44987b8b888323f305e96f3eb0a32b0_Traceguids, v8);
  v60 = pv;
  if ( pv )
  {
    pv = 0;
    CoTaskMemFree(v60);
  }
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v11 )
    CoTaskMemFree(v11);
  return v8;
}

```

## disassembly

```asm
0x180008560  push    rbp
0x180008562  push    rbx
0x180008563  push    rsi
0x180008564  push    rdi
0x180008565  push    r12
0x180008567  push    r13
0x180008569  push    r14
0x18000856b  push    r15
0x18000856d  lea     rbp, [rsp-0F8h]
0x180008575  sub     rsp, 1F8h
0x18000857c  mov     rax, cs:__security_cookie
0x180008583  xor     rax, rsp
0x180008586  mov     [rbp+130h+var_50], rax
0x18000858d  mov     rbx, r8
0x180008590  mov     [rbp+130h+var_1A0], rdx
0x180008594  mov     [rbp+130h+var_1A8], rbx
0x180008598  mov     r12, r9
0x18000859b  mov     rax, rdx
0x18000859e  mov     r13, rcx
0x1800085a1  test    byte ptr cs:xmmword_180266B60, 2
0x1800085a8  jnz     loc_1800097F9
0x1800085ae  mov     rax, [rbx+8]
0x1800085b2  xor     edx, edx; dwFlags
0x1800085b4  mov     [rbp+130h+pv], rdx
0x1800085b8  mov     r15d, edx
0x1800085bb  mov     [rbp+130h+var_184], edx
0x1800085be  mov     esi, edx
0x1800085c0  mov     [rbp+130h+var_188], dx
0x1800085c4  mov     r14d, edx
0x1800085c7  mov     [rbp+130h+var_180], edx
0x1800085ca  mov     ebx, edx
0x1800085cc  mov     [rbp+130h+var_170], edx
0x1800085cf  mov     edi, edx
0x1800085d1  mov     [rbp+130h+var_16C], edx
0x1800085d4  mov     [rsp+230h+var_1DC], edx
0x1800085d8  mov     dword ptr [rsp+230h+Size+4], edx
0x1800085dc  mov     [rsp+230h+hMem], rdx
0x1800085e1  mov     [rbp+130h+var_1B0], edx
0x1800085e4  mov     [rbp+130h+lpWideCharStr], rax
0x1800085e8  mov     [rsp+60h], rdx
0x1800085ed  test    rax, rax
0x1800085f0  jz      loc_180009821
0x1800085f6  cmp     cs:GlobalSafeToAssumeUTF8, edx
0x1800085fc  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180008603  mov     r15d, 8007000Eh
0x180008609  jz      loc_180009406
0x18000860f  mov     [rsp+230h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x180008614  mov     r9d, r14d; cchWideChar
0x180008617  mov     [rsp+230h+lpDefaultChar], rdx; lpDefaultChar
0x18000861c  mov     r8, rax; lpWideCharStr
0x18000861f  mov     [rsp+230h+cbMultiByte], edx; cbMultiByte
0x180008623  mov     ecx, 0FDE9h; CodePage
0x180008628  mov     [rsp+230h+lpMultiByteStr], rdx; lpMultiByteStr
0x18000862d  mov     [rsp+230h+var_1DC], edx
0x180008631  call    cs:__imp_WideCharToMultiByte
0x180008637  mov     [rsp+230h+var_1C0], eax
0x18000863b  test    eax, eax
0x18000863d  jz      loc_1800096F7
0x180008643  mov     eax, eax
0x180008645  mov     ecx, eax; cb
0x180008647  mov     [rsp+230h+var_1B4], ebx
0x18000864b  mov     [rsp+78h], rax
0x180008650  call    cs:__imp_CoTaskMemAlloc
0x180008656  mov     [rsp+60h], rax
0x18000865b  test    rax, rax
0x18000865e  jz      loc_180009247
0x180008664  mov     r8, [rsp+78h]; Size
0x180008669  xor     edx, edx; Val
0x18000866b  mov     rcx, rax; void *
0x18000866e  call    memset_0
0x180008673  mov     r8, [rbp+130h+lpWideCharStr]; lpWideCharStr
0x180008677  xor     eax, eax
0x180008679  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18000867e  mov     r9d, r14d; cchWideChar
0x180008681  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x180008686  xor     edx, edx; dwFlags
0x180008688  mov     eax, [rsp+230h+var_1C0]
0x18000868c  mov     ecx, 0FDE9h; CodePage
0x180008691  mov     [rsp+230h+cbMultiByte], eax; cbMultiByte
0x180008695  mov     rax, [rsp+60h]
0x18000869a  mov     [rsp+230h+lpMultiByteStr], rax; lpMultiByteStr
0x18000869f  call    cs:__imp_WideCharToMultiByte
0x1800086a5  test    eax, eax
0x1800086a7  jz      loc_18000972B
0x1800086ad  xor     eax, eax
0x1800086af  mov     dword ptr [rsp+230h+Size], eax
0x1800086b3  mov     rbx, [rsp+60h]
0x1800086b8  jmp     short loc_1800086E5
0x1800086ba  mov     ecx, 8000FFFFh
0x1800086bf  mov     [rsp+230h+var_1DC], 15Ch
0x1800086c7  cmovns  eax, ecx
0x1800086ca  mov     rcx, [rsp+60h]; pv
0x1800086cf  mov     dword ptr [rsp+230h+Size], eax
0x1800086d3  call    cs:__imp_CoTaskMemFree
0x1800086d9  mov     eax, dword ptr [rsp+230h+Size]
0x1800086dd  test    eax, eax
0x1800086df  js      loc_18000925E
0x1800086e5  mov     rdi, rbx
0x1800086e8  xor     ebx, ebx
0x1800086ea  test    rbx, rbx
0x1800086ed  jz      short loc_1800086FC
0x1800086ef  mov     rcx, rbx; pv
0x1800086f2  call    cs:__imp_CoTaskMemFree
0x1800086f8  mov     eax, dword ptr [rsp+230h+Size]
0x1800086fc  xor     edx, edx; dwFlags
0x1800086fe  test    eax, eax
0x180008700  js      loc_18000923F
0x180008706  mov     rax, [rbp+130h+var_1A8]
0x18000870a  mov     ebx, edx
0x18000870c  mov     [rsp+60h], rdx
0x180008711  mov     rax, [rax+10h]
0x180008715  mov     [rbp+130h+lpWideCharStr], rax
0x180008719  mov     [rsp+230h+var_1DC], edx
0x18000871d  test    rax, rax
0x180008720  jz      loc_18000982E
0x180008726  cmp     cs:GlobalSafeToAssumeUTF8, edx
0x18000872c  jz      loc_180009434
0x180008732  mov     [rsp+230h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x180008737  mov     r9d, r14d; cchWideChar
0x18000873a  mov     [rsp+230h+lpDefaultChar], rdx; lpDefaultChar
0x18000873f  mov     r8, rax; lpWideCharStr
0x180008742  mov     [rsp+230h+cbMultiByte], edx; cbMultiByte
0x180008746  mov     ecx, 0FDE9h; CodePage
0x18000874b  mov     [rsp+230h+lpMultiByteStr], rdx; lpMultiByteStr
0x180008750  mov     [rsp+230h+var_1DC], edx
0x180008754  call    cs:__imp_WideCharToMultiByte
0x18000875a  mov     [rsp+230h+var_1C0], eax
0x18000875e  test    eax, eax
0x180008760  jz      loc_180009747
0x180008766  mov     eax, eax
0x180008768  mov     ecx, eax; cb
0x18000876a  mov     [rsp+230h+var_1B4], ebx
0x18000876e  mov     [rsp+78h], rax
0x180008773  call    cs:__imp_CoTaskMemAlloc
0x180008779  mov     [rsp+60h], rax
0x18000877e  test    rax, rax
0x180008781  jz      loc_18000926B
0x180008787  mov     r8, [rsp+78h]; Size
0x18000878c  xor     edx, edx; Val
0x18000878e  mov     rcx, rax; void *
0x180008791  call    memset_0
0x180008796  mov     r15, [rsp+60h]
0x18000879b  xor     eax, eax
0x18000879d  mov     r8, [rbp+130h+lpWideCharStr]; lpWideCharStr
0x1800087a1  mov     r9d, r14d; cchWideChar
0x1800087a4  mov     [rsp+230h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800087a9  xor     edx, edx; dwFlags
0x1800087ab  mov     [rsp+230h+lpDefaultChar], rax; lpDefaultChar
0x1800087b0  mov     ecx, 0FDE9h; CodePage
0x1800087b5  mov     eax, [rsp+230h+var_1C0]
0x1800087b9  mov     [rsp+230h+cbMultiByte], eax; cbMultiByte
0x1800087bd  mov     [rsp+230h+lpMultiByteStr], r15; lpMultiByteStr
0x1800087c2  call    cs:__imp_WideCharToMultiByte
0x1800087c8  test    eax, eax
0x1800087ca  jz      loc_18000977F
0x1800087d0  mov     rbx, r15
0x1800087d3  xor     r15d, r15d
0x1800087d6  jmp     short loc_180008800
0x1800087d8  mov     rcx, [rsp+60h]; pv
0x1800087dd  test    r15d, r15d
0x1800087e0  mov     eax, 8000FFFFh
0x1800087e5  mov     [rsp+230h+var_1DC], 15Ch
0x1800087ed  cmovns  r15d, eax
0x1800087f1  call    cs:__imp_CoTaskMemFree
0x1800087f7  test    r15d, r15d
0x1800087fa  js      loc_18000927B
0x180008800  mov     rsi, rbx
0x180008803  xor     ebx, ebx
0x180008805  test    rbx, rbx
0x180008808  jnz     loc_1800089F7
0x18000880e  test    r15d, r15d
0x180008811  js      loc_180009CB7
0x180008817  mov     rbx, [rbp+130h+var_1A0]
0x18000881b  lea     rdx, [rbp+130h+var_180]
0x18000881f  mov     rcx, rbx
0x180008822  mov     rax, [rbx]
0x180008825  mov     rax, [rax+18h]
0x180008829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882e  test    eax, eax
0x180008830  js      loc_18000983E
0x180008836  cmp     [rbp+130h+var_180], 0
0x18000883a  mov     r15d, 1
0x180008840  mov     rax, [rbx]
0x180008843  mov     rcx, rbx
0x180008846  jnz     loc_180009515
0x18000884c  mov     rax, [rax+20h]
0x180008850  lea     r8, [rbp+130h+var_16C]
0x180008854  lea     rdx, [rbp+130h+var_170]
0x180008858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885d  test    eax, eax
0x18000885f  js      loc_18000985C
0x180008865  cmp     [rbp+130h+var_184], 8
0x180008869  mov     rbx, [rsp+230h+hMem]
0x18000886e  jz      loc_18000979F
0x180008874  xor     edx, edx
0x180008876  cmp     dword ptr [r13+3E0h], 0
0x18000887e  jnz     loc_18000986B
0x180008884  lea     rcx, [r13+0BD0h]; lpCriticalSection
0x18000888b  mov     [rsp+60h], rdx
0x180008890  mov     r15, rdx
0x180008893  mov     dword ptr [rsp+230h+Size], edx
0x180008897  call    cs:__imp_EnterCriticalSection
0x18000889d  test    rbx, rbx
0x1800088a0  jnz     loc_180009881
0x1800088a6  test    r12, r12
0x1800088a9  mov     rbx, r14
0x1800088ac  cmovz   r12, rsi
0x1800088b0  inc     rbx
0x1800088b3  cmp     byte ptr [r12+rbx], 0
0x1800088b8  jnz     short loc_1800088B0
0x1800088ba  mov     eax, [r13+0BF8h]
0x1800088c1  mov     [rsp+230h+var_1C0], eax
0x1800088c5  test    byte ptr cs:xmmword_180266B60, 2
0x1800088cc  jnz     loc_1800098CE
0x1800088d2  xor     r10d, r10d
0x1800088d5  lea     rdx, __ImageBase
0x1800088dc  mov     [rsp+230h+var_1DC], r10d
0x1800088e1  cmp     [r13+0B98h], r10
0x1800088e8  jz      loc_18000907F
0x1800088ee  cmp     eax, r14d
0x1800088f1  jz      loc_18000932E
0x1800088f7  cmp     eax, 1Eh
0x1800088fa  ja      loc_1800092DC
0x180008900  lfence
0x180008903  cdqe
0x180008905  lea     rcx, [rax+rax*2]
0x180008909  mov     r9d, ds:rva dword_1801F1D50[rdx+rcx*8]
0x180008911  mov     dword ptr [rsp+230h+Size+4], r9d
0x180008916  cmp     r9d, 0FFFFFFFFh
0x18000891a  jz      loc_1800092DC
0x180008920  mov     rcx, ds:rva off_1801F1D58[rdx+rcx*8]; "GET" ...
0x180008928  lea     rax, [r13+0B40h]
0x18000892f  lea     rdx, [r13+0B48h]
0x180008936  mov     [rsp+78h], rcx
0x18000893b  test    r15, r15
0x18000893e  jnz     short loc_180008958
0x180008940  mov     r8, [r13+0B60h]
0x180008947  mov     [rsp+60h], r8
0x18000894c  mov     r8d, [r13+0B68h]
0x180008953  mov     dword ptr [rsp+230h+Size], r8d
0x180008958  mov     [rax], r10
0x18000895b  mov     r15d, r10d
0x18000895e  mov     [rdx], r10d
0x180008961  mov     eax, 0FFFFFFFEh
0x180008966  sub     eax, [r13+0BA0h]
0x18000896d  add     [r13+0B38h], eax
0x180008974  mov     [r13+0B50h], r10
0x18000897b  mov     [r13+0B58h], r10d
0x180008982  mov     [r13+0B60h], r10
0x180008989  mov     [r13+0B68h], r10d
0x180008990  mov     [rsp+230h+var_1DC], r10d
0x180008995  mov     [rbp+130h+var_198], r10d
0x180008999  mov     [rbp+130h+var_194], r10d
0x18000899d  mov     [rsp+230h+var_1DC], r10d
0x1800089a2  test    rcx, rcx
0x1800089a5  jz      short loc_180008A0E
0x1800089a7  mov     r8, rcx
0x1800089aa  mov     edx, r9d
0x1800089ad  test    r9d, r9d
0x1800089b0  jz      short loc_180008A0E
0x1800089b2  movzx   eax, byte ptr [r8]
0x1800089b6  cmp     al, 9
0x1800089b8  jz      loc_180008E12
0x1800089be  cmp     al, 20h ; ' '
0x1800089c0  jz      loc_180008E12
0x1800089c6  test    edx, edx
0x1800089c8  jz      short loc_180008A0E
0x1800089ca  nop     word ptr [rax+rax+00h]
0x1800089d0  cmp     al, 20h ; ' '
0x1800089d2  jbe     short loc_1800089DC
0x1800089d4  cmp     al, 7Fh
0x1800089d6  jb      short loc_180008A05
0x1800089d8  test    edx, edx
0x1800089da  jz      short loc_180008A0E
0x1800089dc  movzx   ecx, byte ptr [r8]; unsigned __int8
0x1800089e0  call    ?IsLWS@@YAHE@Z; IsLWS(uchar)
0x1800089e5  test    eax, eax
0x1800089e7  jz      loc_1800098FC
0x1800089ed  inc     r8
0x1800089f0  add     edx, 0FFFFFFFFh
0x1800089f3  jnz     short loc_1800089DC
0x1800089f5  jmp     short loc_180008A0E
0x1800089f7  mov     rcx, rbx; pv
0x1800089fa  call    cs:__imp_CoTaskMemFree
0x180008a00  jmp     loc_18000880E
0x180008a05  add     edx, 0FFFFFFFFh
0x180008a08  jnz     loc_180009072
0x180008a0e  mov     ecx, r15d
0x180008a11  call    WX_WIN32_FROM_HR
0x180008a16  mov     ecx, eax
0x180008a18  test    eax, eax
0x180008a1a  jle     short loc_180008A25
0x180008a1c  movzx   ecx, ax
0x180008a1f  or      ecx, 80070000h
0x180008a25  test    ecx, ecx
0x180008a27  js      loc_180009378
0x180008a2d  mov     r11, [r13+0B30h]
0x180008a34  xor     eax, eax
0x180008a36  mov     r9d, dword ptr [rsp+230h+Size]
0x180008a3b  mov     ecx, eax
  ... truncated ...
```
