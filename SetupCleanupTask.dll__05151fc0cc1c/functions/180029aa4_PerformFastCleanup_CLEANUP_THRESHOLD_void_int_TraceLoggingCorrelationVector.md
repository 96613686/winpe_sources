# PerformFastCleanup(CLEANUP_THRESHOLD,void *,int,TraceLoggingCorrelationVector *)

- ea: `0x180029aa4`
- end: `0x18002a3bd`
- name: `?PerformFastCleanup@@YAJW4CLEANUP_THRESHOLD@@PEAXHPEAVTraceLoggingCorrelationVector@@@Z`
- size: `2329`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, TraceLoggingCorrelationVector *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180006838`

## callees

- `0x180001008`
- `0x18000113c`
- `0x18000c700`
- `0x180027008`
- `0x180027d04`
- `0x1800293a4`
- `0x180029aa4`
- `0x18002bae0`
- `0x18002ff00`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029df5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029df5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029e55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029e55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029e25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c72`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029bb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029c17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029bb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029c17`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18002a2a0`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18002a2a0`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180029b4f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180029c68`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180029b4f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180029c68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029cad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029e60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029b93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029cad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029e60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029ba2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029cbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029e6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029ba2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029cbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029e6e`

## pseudocode

```c
__int64 __fastcall PerformFastCleanup(__int64 a1, __int64 a2, __int64 a3, TraceLoggingCorrelationVector *a4)
{
  __int64 v4; // r13
  TraceLoggingCorrelationVector *v5; // r15
  DWORD v6; // edi
  int v7; // eax
  signed int v8; // r14d
  __int64 v9; // rcx
  signed int LastError; // eax
  int v11; // eax
  DWORD v12; // ebx
  __int64 v13; // r8
  int v14; // eax
  union _ULARGE_INTEGER v15; // rbx
  __int64 v16; // rcx
  signed int v17; // eax
  HANDLE ProcessHeap; // rax
  struct _FILETIME v19; // rdi
  struct _FILETIME v20; // rsi
  unsigned __int64 v21; // rbx
  int v22; // r12d
  unsigned __int64 v23; // r15
  __int64 v24; // rcx
  int v25; // ebx
  TraceLoggingCorrelationVector *v26; // rsi
  int v27; // eax
  void *QuadPart; // rbx
  LSTATUS v29; // eax
  bool v30; // cc
  HANDLE v31; // rax
  unsigned __int64 v32; // rax
  __int64 v33; // rax
  unsigned __int64 v34; // rax
  DWORD v35; // ebx
  REGHANDLE v36; // rcx
  DWORD v38; // [rsp+50h] [rbp-B0h]
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+58h] [rbp-A8h] BYREF
  union _ULARGE_INTEGER v41; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  TraceLoggingCorrelationVector *v43; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpDirectoryName; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h] BYREF
  union _ULARGE_INTEGER v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR v50; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME v51; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp-48h] BYREF
  char Destination[32]; // [rsp+C0h] [rbp-40h] BYREF
  LPCWSTR *p_lpDirectoryName; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  union _ULARGE_INTEGER *v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  BYTE *v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+108h] [rbp+8h]
  union _ULARGE_INTEGER *v60; // [rsp+110h] [rbp+10h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  union _ULARGE_INTEGER *v62; // [rsp+120h] [rbp+20h]
  __int64 v63; // [rsp+128h] [rbp+28h]
  void *v64; // [rsp+130h] [rbp+30h]
  __int64 v65; // [rsp+138h] [rbp+38h]
  union _ULARGE_INTEGER *v66; // [rsp+140h] [rbp+40h]
  __int64 v67; // [rsp+148h] [rbp+48h]
  _BYTE v68[32]; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v69; // [rsp+170h] [rbp+70h]
  __int64 v70; // [rsp+178h] [rbp+78h]
  TraceLoggingCorrelationVector **v71; // [rsp+180h] [rbp+80h]
  __int64 v72; // [rsp+188h] [rbp+88h]
  union _ULARGE_INTEGER *p_TotalNumberOfFreeBytes; // [rsp+190h] [rbp+90h]
  __int64 v74; // [rsp+198h] [rbp+98h]
  void *v75; // [rsp+1A0h] [rbp+A0h]
  __int64 v76; // [rsp+1A8h] [rbp+A8h]
  void *v77; // [rsp+1B0h] [rbp+B0h]
  __int64 v78; // [rsp+1B8h] [rbp+B8h]
  void *v79; // [rsp+1C0h] [rbp+C0h]
  __int64 v80; // [rsp+1C8h] [rbp+C8h]
  void *p_cbData; // [rsp+1D0h] [rbp+D0h]
  __int64 v82; // [rsp+1D8h] [rbp+D8h]
  char *v83; // [rsp+1E0h] [rbp+E0h]
  int v84; // [rsp+1E8h] [rbp+E8h]
  int v85; // [rsp+1ECh] [rbp+ECh]

  v43 = a4;
  SystemTimeAsFileTime = 0;
  v4 = -1;
  v51 = 0;
  v48.QuadPart = 0;
  v45 = 0x7FFFFFFF00000000LL;
  v5 = a4;
  v49 = -1;
  LODWORD(v46) = 0x7FFFFFFF;
  TraceLoggingRegister_EventRegister_EventSetInformation(&dword_180051050);
  lpDirectoryName = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  v6 = 1;
  v7 = CMiscHelpersT<CEmptyType>::ExpandFileName(L"%systemdrive%\\");
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_11;
  }
  if ( !GetDiskFreeSpaceExW(lpDirectoryName, 0, 0, &TotalNumberOfFreeBytes) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    v9 = (unsigned int)v8;
    goto LABEL_3;
  }
  v48 = TotalNumberOfFreeBytes;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v11 = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::Run(
          1,
          3,
          0,
          1,
          v5,
          (__int64)&v46,
          (__int64)&v45 + 4,
          (__int64)&v49,
          (__int64)&v45);
  v38 = v11;
  v12 = v11;
  if ( v11 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
    goto LABEL_85;
  }
  GetSystemTimeAsFileTime(&v51);
  if ( v8 >= 0 )
  {
    lpDirectoryName = 0;
    TotalNumberOfFreeBytes.QuadPart = 0;
    v41.QuadPart = 0;
    v14 = CMiscHelpersT<CEmptyType>::ExpandFileName(L"%systemdrive%\\");
    v15 = TotalNumberOfFreeBytes;
    v8 = v14;
    if ( v14 >= 0 )
    {
      if ( GetDiskFreeSpaceExW((LPCWSTR)TotalNumberOfFreeBytes.QuadPart, 0, 0, &v41) )
      {
        lpDirectoryName = (LPCWSTR)v41.QuadPart;
LABEL_24:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
        if ( v15.QuadPart )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, (LPVOID)(v15.QuadPart - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        if ( v8 < 0 )
        {
          v6 = 2;
          goto LABEL_83;
        }
        v19 = v51;
        v20 = SystemTimeAsFileTime;
        if ( *(_QWORD *)&v51 < *(unsigned __int64 *)&SystemTimeAsFileTime )
          v21 = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v51;
        else
          v21 = *(_QWORD *)&v51 - *(_QWORD *)&SystemTimeAsFileTime;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v22 = 0;
        v23 = v21 / 0x989680;
        if ( v21 / 0x989680 == (int)(v21 / 0x989680) )
        {
          v25 = 0;
          if ( (v23 & 0x80000000) != 0LL )
          {
            v25 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v25);
          v8 = v25;
          if ( v25 >= 0 )
          {
            v22 = v23;
LABEL_38:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
            if ( v8 >= 0 )
            {
              if ( *(_QWORD *)&v20 > *(unsigned __int64 *)&v19 )
                v22 = -v22;
              v26 = 0;
            }
            else
            {
              v26 = 0;
              v22 = 0;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
            if ( v8 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
            if ( v8 < 0 )
            {
              v5 = v43;
              v6 = 3;
            }
            else
            {
              cbData = 8;
              v41.QuadPart = 0;
              TotalNumberOfFreeBytes.QuadPart = 0;
              *(_QWORD *)Data = 0;
              v27 = StrAllocatingPrintf(&v41, L"SYSTEM\\Setup\\SQM\\DWORD64\\%08x", 12364);
              QuadPart = (void *)v41.QuadPart;
              v8 = v27;
              if ( v27 >= 0 )
              {
                if ( (v29 = RegOpenKeyExW(
                              HKEY_LOCAL_MACHINE,
                              (LPCWSTR)v41.QuadPart,
                              0,
                              0x20019u,
                              (PHKEY)&TotalNumberOfFreeBytes),
                      v30 = v29 <= 0,
                      !v29)
                  && (v29 = RegQueryValueExW((HKEY)TotalNumberOfFreeBytes.QuadPart, L"VALUE", 0, 0, Data, &cbData),
                      v30 = v29 <= 0,
                      !v29)
                  || (!v30 ? (v8 = (unsigned __int16)v29 | 0x80070000) : (v8 = v29), v8 >= 0) )
                {
                  v26 = *(TraceLoggingCorrelationVector **)Data;
                }
              }
              if ( TotalNumberOfFreeBytes.QuadPart )
                RegCloseKey((HKEY)TotalNumberOfFreeBytes.QuadPart);
              if ( QuadPart )
              {
                v31 = GetProcessHeap();
                HeapFree(v31, 0, QuadPart);
              }
              v5 = v43;
              if ( v26 )
              {
                if ( v8 >= 0 )
                {
                  v6 = 5;
                  if ( v43 )
                  {
                    if ( (unsigned int)dword_180051050 > 5
                      && (qword_180051060 & 0x400000000000LL) != 0
                      && (qword_180051068 & 0x400000000000LL) == qword_180051068 )
                    {
                      TraceLoggingCorrelationVector::ToString(v43, Destination);
                      cbData = v45;
                      *(_DWORD *)Data = v22;
                      if ( v49 == -1 )
                        LODWORD(v32) = -1;
                      else
                        v32 = (unsigned __int64)v49 >> 20;
                      v41.LowPart = v32;
                      TotalNumberOfFreeBytes.QuadPart = (ULONGLONG)lpDirectoryName;
                      v50 = (LPCWSTR)v48.QuadPart;
                      v33 = -1;
                      v43 = v26;
                      v47 = 0x1000000;
                      do
                        ++v33;
                      while ( Destination[v33] );
                      v85 = 0;
                      v84 = v33 + 1;
                      v83 = Destination;
                      p_cbData = &cbData;
                      v82 = 4;
                      v79 = Data;
                      v77 = &v41;
                      v75 = &v43;
                      p_TotalNumberOfFreeBytes = &TotalNumberOfFreeBytes;
                      v71 = (TraceLoggingCorrelationVector **)&v50;
                      v69 = &v47;
                      v80 = 4;
                      v78 = 4;
                      v76 = 8;
                      v74 = 8;
                      v72 = 8;
                      v70 = 8;
                      tlgWriteTransfer_EventWriteTransfer(&dword_180051050, &dword_180047234, 0, 0, 10, v68);
                    }
                  }
                  else
                  {
                    if ( (unsigned int)dword_180051050 <= 5
                      || (qword_180051060 & 0x400000000000LL) == 0
                      || (qword_180051068 & 0x400000000000LL) != qword_180051068 )
                    {
                      goto LABEL_94;
                    }
                    v41.LowPart = v45;
                    *(_DWORD *)Data = v22;
                    if ( v49 == -1 )
                      LODWORD(v34) = -1;
                    else
                      v34 = (unsigned __int64)v49 >> 20;
                    cbData = v34;
                    v50 = lpDirectoryName;
                    v66 = &v41;
                    v64 = Data;
                    v62 = (union _ULARGE_INTEGER *)&cbData;
                    v60 = (union _ULARGE_INTEGER *)&v47;
                    v58 = (BYTE *)&v50;
                    v56 = &v48;
                    p_lpDirectoryName = &lpDirectoryName;
                    v47 = (__int64)v26;
                    lpDirectoryName = (LPCWSTR)0x1000000;
                    v67 = 4;
                    v65 = 4;
                    v63 = 4;
                    v61 = 8;
                    v59 = 8;
                    v57 = 8;
                    v55 = 8;
                    tlgWriteTransfer_EventWriteTransfer(&dword_180051050, word_18004717A, 0, 0, 9, Destination);
                  }
                  goto LABEL_83;
                }
              }
              else
              {
                v8 = -2147024883;
              }
              v6 = 4;
            }
LABEL_83:
            v12 = v38;
            goto LABEL_84;
          }
          v24 = (unsigned int)v25;
        }
        else
        {
          v8 = -2147024362;
          v24 = 2147942934LL;
        }
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
        goto LABEL_38;
      }
      v17 = GetLastError();
      v8 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v8 = (unsigned __int16)v17 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      v16 = (unsigned int)v8;
    }
    else
    {
      v16 = (unsigned int)v14;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    goto LABEL_24;
  }
LABEL_84:
  v13 = 0x400000000000LL;
LABEL_85:
  if ( v5 )
  {
    if ( (unsigned int)dword_180051050 > 5 && (qword_180051060 & v13) != 0 && (v13 & qword_180051068) == qword_180051068 )
    {
      TraceLoggingCorrelationVector::ToString(v5, Destination);
      cbData = HIDWORD(v45);
      TotalNumberOfFreeBytes.LowPart = v46;
      v41.LowPart = v6;
      *(_DWORD *)Data = v8;
      LODWORD(v43) = v12;
      v47 = 0x1000000;
      do
        ++v4;
      while ( Destination[v4] );
      p_cbData = Destination;
      v80 = 4;
      v82 = (unsigned int)(v4 + 1);
      v78 = 4;
      v79 = &v41;
      v76 = 4;
      v77 = Data;
      v74 = 4;
      v75 = &cbData;
      p_TotalNumberOfFreeBytes = &TotalNumberOfFreeBytes;
      v71 = &v43;
      v69 = &v47;
      v72 = 4;
      v70 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_180051050, &word_1800470CE, 0, 0, 9, v68);
    }
    goto LABEL_92;
  }
LABEL_94:
  if ( (unsigned int)dword_180051050 > 5
    && (qword_180051060 & 0x400000000000LL) != 0
    && (qword_180051068 & 0x400000000000LL) == qword_180051068 )
  {
    v35 = v38;
    v41.LowPart = HIDWORD(v45);
    *(_DWORD *)Data = v46;
    v64 = &v43;
    v62 = &TotalNumberOfFreeBytes;
    v60 = &v41;
    v58 = Data;
    v56 = (union _ULARGE_INTEGER *)&cbData;
    p_lpDirectoryName = (LPCWSTR *)&v47;
    v55 = 8;
    LODWORD(v43) = v6;
    TotalNumberOfFreeBytes.LowPart = v8;
    cbData = v38;
    v47 = 0x1000000;
    v65 = 4;
    v63 = 4;
    v61 = 4;
    v59 = 4;
    v57 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180051050, byte_18004702D, 0, 0, 8, Destination);
    goto LABEL_93;
  }
LABEL_92:
  v35 = v38;
LABEL_93:
  v36 = qword_180051070;
  dword_180051050 = 0;
  qword_180051070 = 0;
  EventUnregister(v36);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v35);
  return v35;
}

```

## disassembly

```asm
0x180029aa4  push    rbp
0x180029aa6  push    rbx
0x180029aa7  push    rsi
0x180029aa8  push    rdi
0x180029aa9  push    r12
0x180029aab  push    r13
0x180029aad  push    r14
0x180029aaf  push    r15
0x180029ab1  lea     rbp, [rsp-108h]
0x180029ab9  sub     rsp, 208h
0x180029ac0  mov     rax, cs:__security_cookie
0x180029ac7  xor     rax, rsp
0x180029aca  mov     [rbp+140h+var_50], rax
0x180029ad1  xor     esi, esi
0x180029ad3  mov     [rsp+240h+var_1D0], r9
0x180029ad8  mov     eax, 7FFFFFFFh
0x180029add  mov     qword ptr [rbp+140h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180029ae1  or      r13, 0FFFFFFFFFFFFFFFFh
0x180029ae5  mov     qword ptr [rbp+140h+var_190.dwLowDateTime], rsi
0x180029ae9  lea     rcx, dword_180051050; CallbackContext
0x180029af0  mov     [rbp+140h+var_1A8], rsi
0x180029af4  mov     dword ptr [rbp+140h+var_1C0], esi
0x180029af7  mov     r15, r9
0x180029afa  mov     [rbp+140h+var_1A0], r13
0x180029afe  mov     dword ptr [rbp+140h+var_1B8], eax
0x180029b01  mov     dword ptr [rbp+140h+var_1C0+4], eax
0x180029b04  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x180029b09  lea     rdx, [rsp+240h+lpDirectoryName]
0x180029b0e  mov     [rsp+240h+lpDirectoryName], rsi
0x180029b13  lea     rcx, aSystemdrive_0; "%systemdrive%\\"
0x180029b1a  mov     qword ptr [rsp+240h+TotalNumberOfFreeBytes], rsi
0x180029b1f  lea     edi, [rsi+1]
0x180029b22  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x180029b27  mov     rbx, [rsp+240h+lpDirectoryName]
0x180029b2c  mov     r14d, eax
0x180029b2f  mov     r12d, 80004005h
0x180029b35  test    eax, eax
0x180029b37  jns     short loc_180029B42
0x180029b39  mov     ecx, eax
0x180029b3b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029b40  jmp     short loc_180029B86
0x180029b42  lea     r9, [rsp+240h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180029b47  xor     r8d, r8d; lpTotalNumberOfBytes
0x180029b4a  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180029b4c  mov     rcx, rbx; lpDirectoryName
0x180029b4f  call    cs:__imp_GetDiskFreeSpaceExW
0x180029b55  test    eax, eax
0x180029b57  jnz     short loc_180029B7D
0x180029b59  call    cs:__imp_GetLastError
0x180029b5f  mov     r14d, eax
0x180029b62  test    eax, eax
0x180029b64  jnz     short loc_180029B6B
0x180029b66  mov     r14d, r12d
0x180029b69  jmp     short loc_180029B78
0x180029b6b  jle     short loc_180029B78
0x180029b6d  movzx   r14d, ax
0x180029b71  or      r14d, 80070000h
0x180029b78  mov     ecx, r14d
0x180029b7b  jmp     short loc_180029B3B
0x180029b7d  mov     rax, qword ptr [rsp+240h+TotalNumberOfFreeBytes]
0x180029b82  mov     [rbp+140h+var_1A8], rax
0x180029b86  mov     ecx, r14d
0x180029b89  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029b8e  test    rbx, rbx
0x180029b91  jz      short loc_180029BAF
0x180029b93  call    cs:__imp_GetProcessHeap
0x180029b99  lea     r8, [rbx-4]; lpMem
0x180029b9d  xor     edx, edx; dwFlags
0x180029b9f  mov     rcx, rax; hHeap
0x180029ba2  call    cs:__imp_HeapFree
0x180029ba8  xor     ecx, ecx
0x180029baa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029baf  lea     rcx, [rbp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180029bb3  call    cs:__imp_GetSystemTimeAsFileTime
0x180029bb9  lea     rax, [rbp+140h+var_1C0]
0x180029bbd  xor     r8d, r8d; int
0x180029bc0  mov     [rsp+240h+var_200], rax; __int64
0x180029bc5  mov     r9d, edi; int
0x180029bc8  lea     rax, [rbp+140h+var_1A0]
0x180029bcc  mov     ecx, edi; int
0x180029bce  mov     [rsp+240h+var_208], rax; __int64
0x180029bd3  lea     rax, [rbp+140h+var_1C0+4]
0x180029bd7  mov     [rsp+240h+var_210], rax; __int64
0x180029bdc  lea     edx, [r8+3]; int
0x180029be0  lea     rax, [rbp+140h+var_1B8]
0x180029be4  mov     [rsp+240h+lpcbData], rax; __int64
0x180029be9  mov     [rsp+240h+phkResult], r15; TraceLoggingCorrelationVector *
0x180029bee  call    ?Run@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@SAJHW4CLEANUP_THRESHOLD@@PEAXHPEAVTraceLoggingCorrelationVector@@PEAK3PEA_K3@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::Run(int,CLEANUP_THRESHOLD,void *,int,TraceLoggingCorrelationVector *,ulong *,ulong *,unsigned __int64 *,ulong *)
0x180029bf3  mov     [rsp+240h+var_1F0], eax
0x180029bf7  mov     ebx, eax
0x180029bf9  mov     r8, 400000000000h
0x180029c03  test    eax, eax
0x180029c05  jns     short loc_180029C13
0x180029c07  mov     ecx, eax
0x180029c09  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029c0e  jmp     loc_18002A146
0x180029c13  lea     rcx, [rbp+140h+var_190]; lpSystemTimeAsFileTime
0x180029c17  call    cs:__imp_GetSystemTimeAsFileTime
0x180029c1d  test    r14d, r14d
0x180029c20  js      loc_18002A13C
0x180029c26  lea     rdx, [rsp+240h+TotalNumberOfFreeBytes]
0x180029c2b  mov     [rsp+240h+lpDirectoryName], rsi
0x180029c30  lea     rcx, aSystemdrive_0; "%systemdrive%\\"
0x180029c37  mov     qword ptr [rsp+240h+TotalNumberOfFreeBytes], rsi
0x180029c3c  mov     qword ptr [rsp+240h+var_1E0], rsi
0x180029c41  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x180029c46  mov     rbx, qword ptr [rsp+240h+TotalNumberOfFreeBytes]
0x180029c4b  mov     r14d, eax
0x180029c4e  test    eax, eax
0x180029c50  jns     short loc_180029C5B
0x180029c52  mov     ecx, eax
0x180029c54  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029c59  jmp     short loc_180029CA0
0x180029c5b  lea     r9, [rsp+240h+var_1E0]; lpTotalNumberOfFreeBytes
0x180029c60  xor     r8d, r8d; lpTotalNumberOfBytes
0x180029c63  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180029c65  mov     rcx, rbx; lpDirectoryName
0x180029c68  call    cs:__imp_GetDiskFreeSpaceExW
0x180029c6e  test    eax, eax
0x180029c70  jnz     short loc_180029C96
0x180029c72  call    cs:__imp_GetLastError
0x180029c78  mov     r14d, eax
0x180029c7b  test    eax, eax
0x180029c7d  jnz     short loc_180029C84
0x180029c7f  mov     r14d, r12d
0x180029c82  jmp     short loc_180029C91
0x180029c84  jle     short loc_180029C91
0x180029c86  movzx   r14d, ax
0x180029c8a  or      r14d, 80070000h
0x180029c91  mov     ecx, r14d
0x180029c94  jmp     short loc_180029C54
0x180029c96  mov     rax, qword ptr [rsp+240h+var_1E0]
0x180029c9b  mov     [rsp+240h+lpDirectoryName], rax
0x180029ca0  mov     ecx, r14d
0x180029ca3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029ca8  test    rbx, rbx
0x180029cab  jz      short loc_180029CC9
0x180029cad  call    cs:__imp_GetProcessHeap
0x180029cb3  lea     r8, [rbx-4]; lpMem
0x180029cb7  xor     edx, edx; dwFlags
0x180029cb9  mov     rcx, rax; hHeap
0x180029cbc  call    cs:__imp_HeapFree
0x180029cc2  xor     ecx, ecx
0x180029cc4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029cc9  test    r14d, r14d
0x180029ccc  js      loc_18002A133
0x180029cd2  mov     rdi, qword ptr [rbp+140h+var_190.dwLowDateTime]
0x180029cd6  mov     rsi, qword ptr [rbp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180029cda  cmp     rdi, rsi
0x180029cdd  jb      short loc_180029CE7
0x180029cdf  mov     rbx, rdi
0x180029ce2  sub     rbx, rsi
0x180029ce5  jmp     short loc_180029CED
0x180029ce7  mov     rbx, rsi
0x180029cea  sub     rbx, rdi
0x180029ced  xor     ecx, ecx
0x180029cef  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029cf4  mov     rax, 0D6BF94D5E57A42BDh
0x180029cfe  xor     r12d, r12d
0x180029d01  mul     rbx
0x180029d04  mov     r15, rdx
0x180029d07  shr     r15, 17h
0x180029d0b  movsxd  rax, r15d
0x180029d0e  cmp     r15, rax
0x180029d11  jz      short loc_180029D23
0x180029d13  mov     r14d, 80070216h
0x180029d19  mov     ecx, r14d
0x180029d1c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029d21  jmp     short loc_180029D50
0x180029d23  xor     ebx, ebx
0x180029d25  test    r15d, r15d
0x180029d28  jns     short loc_180029D3B
0x180029d2a  mov     r14d, 80070216h
0x180029d30  mov     ecx, r14d
0x180029d33  mov     ebx, r14d
0x180029d36  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029d3b  mov     ecx, ebx
0x180029d3d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029d42  mov     r14d, ebx
0x180029d45  test    ebx, ebx
0x180029d47  jns     short loc_180029D4D
0x180029d49  mov     ecx, ebx
0x180029d4b  jmp     short loc_180029D1C
0x180029d4d  mov     r12d, r15d
0x180029d50  mov     ecx, r14d
0x180029d53  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029d58  test    r14d, r14d
0x180029d5b  jns     short loc_180029D6C
0x180029d5d  xor     esi, esi
0x180029d5f  mov     ecx, r14d
0x180029d62  mov     r12d, esi
0x180029d65  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029d6a  jmp     short loc_180029D76
0x180029d6c  cmp     rsi, rdi
0x180029d6f  jbe     short loc_180029D74
0x180029d71  neg     r12d
0x180029d74  xor     esi, esi
0x180029d76  mov     ecx, r14d
0x180029d79  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029d7e  test    r14d, r14d
0x180029d81  jns     short loc_180029D8B
0x180029d83  mov     ecx, r14d
0x180029d86  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029d8b  mov     ecx, r14d
0x180029d8e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029d93  test    r14d, r14d
0x180029d96  js      loc_18002A127
0x180029d9c  xor     edi, edi
0x180029d9e  mov     [rsp+240h+cbData], 8
0x180029da6  mov     r8d, 304Ch
0x180029dac  mov     qword ptr [rsp+240h+var_1E0], rdi
0x180029db1  lea     rdx, aSystemSetupSqm; "SYSTEM\\Setup\\SQM\\DWORD64\\%08x"
0x180029db8  mov     qword ptr [rsp+240h+TotalNumberOfFreeBytes], rdi
0x180029dbd  lea     rcx, [rsp+240h+var_1E0]
0x180029dc2  mov     qword ptr [rsp+240h+Data], rdi
0x180029dc7  call    StrAllocatingPrintf
0x180029dcc  mov     rbx, qword ptr [rsp+240h+var_1E0]
0x180029dd1  mov     r14d, eax
0x180029dd4  test    eax, eax
0x180029dd6  js      short loc_180029E4B
0x180029dd8  lea     rax, [rsp+240h+TotalNumberOfFreeBytes]
0x180029ddd  mov     r9d, 20019h; samDesired
0x180029de3  xor     r8d, r8d; ulOptions
0x180029de6  mov     [rsp+240h+phkResult], rax; phkResult
0x180029deb  mov     rdx, rbx; lpSubKey
0x180029dee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029df5  call    cs:__imp_RegOpenKeyExW
0x180029dfb  test    eax, eax
0x180029dfd  jnz     short loc_180029E2F
0x180029dff  mov     rcx, qword ptr [rsp+240h+TotalNumberOfFreeBytes]; hKey
0x180029e04  lea     rax, [rsp+240h+cbData]
0x180029e09  mov     [rsp+240h+lpcbData], rax; lpcbData
0x180029e0e  lea     rdx, aValue; "VALUE"
0x180029e15  lea     rax, [rsp+240h+Data]
0x180029e1a  xor     r9d, r9d; lpType
0x180029e1d  xor     r8d, r8d; lpReserved
0x180029e20  mov     [rsp+240h+phkResult], rax; lpData
0x180029e25  call    cs:__imp_RegQueryValueExW
0x180029e2b  test    eax, eax
0x180029e2d  jz      short loc_180029E46
0x180029e2f  jg      short loc_180029E36
0x180029e31  mov     r14d, eax
0x180029e34  jmp     short loc_180029E41
0x180029e36  movzx   r14d, ax
0x180029e3a  or      r14d, 80070000h
0x180029e41  test    r14d, r14d
0x180029e44  js      short loc_180029E4B
0x180029e46  mov     rsi, qword ptr [rsp+240h+Data]
0x180029e4b  mov     rcx, qword ptr [rsp+240h+TotalNumberOfFreeBytes]; hKey
0x180029e50  test    rcx, rcx
0x180029e53  jz      short loc_180029E5B
0x180029e55  call    cs:__imp_RegCloseKey
0x180029e5b  test    rbx, rbx
0x180029e5e  jz      short loc_180029E74
0x180029e60  call    cs:__imp_GetProcessHeap
0x180029e66  mov     r8, rbx; lpMem
0x180029e69  xor     edx, edx; dwFlags
0x180029e6b  mov     rcx, rax; hHeap
0x180029e6e  call    cs:__imp_HeapFree
0x180029e74  mov     r15, [rsp+240h+var_1D0]
0x180029e79  test    rsi, rsi
0x180029e7c  jnz     short loc_180029E90
0x180029e7e  mov     r14d, 8007000Dh
0x180029e84  mov     edi, 4
0x180029e89  xor     esi, esi
0x180029e8b  jmp     loc_18002A138
0x180029e90  test    r14d, r14d
0x180029e93  js      short loc_180029E84
0x180029e95  mov     eax, cs:dword_180051050
0x180029e9b  mov     edi, 5
0x180029ea0  test    r15, r15
0x180029ea3  jz      loc_18002A015
0x180029ea9  cmp     eax, edi
0x180029eab  jbe     short loc_180029E89
0x180029ead  mov     rcx, cs:qword_180051068
0x180029eb4  mov     rdx, 400000000000h
0x180029ebe  mov     rax, cs:qword_180051060
0x180029ec5  test    rdx, rax
0x180029ec8  jz      short loc_180029E89
0x180029eca  mov     rax, rcx
0x180029ecd  and     rax, rdx
0x180029ed0  cmp     rax, rcx
0x180029ed3  jnz     short loc_180029E89
0x180029ed5  lea     rdx, [rbp+140h+Destination]; Destination
0x180029ed9  mov     rcx, r15; this
0x180029edc  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180029ee1  mov     eax, dword ptr [rbp+140h+var_1C0]
0x180029ee4  mov     [rsp+240h+cbData], eax
0x180029ee8  mov     rax, [rbp+140h+var_1A0]
0x180029eec  mov     dword ptr [rsp+240h+Data], r12d
0x180029ef1  cmp     rax, r13
0x180029ef4  jnz     short loc_180029EFB
0x180029ef6  or      eax, 0FFFFFFFFh
0x180029ef9  jmp     short loc_180029EFF
0x180029efb  shr     rax, 14h
0x180029eff  mov     dword ptr [rsp+240h+var_1E0], eax
0x180029f03  lea     rcx, [rbp+140h+Destination]
0x180029f07  mov     rax, [rsp+240h+lpDirectoryName]
0x180029f0c  mov     qword ptr [rsp+240h+TotalNumberOfFreeBytes], rax
0x180029f11  mov     rax, [rbp+140h+var_1A8]
  ... truncated ...
```
