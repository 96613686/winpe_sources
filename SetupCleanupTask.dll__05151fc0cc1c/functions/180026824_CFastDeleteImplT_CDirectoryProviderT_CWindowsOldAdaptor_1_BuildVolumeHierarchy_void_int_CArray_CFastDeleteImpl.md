# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::BuildVolumeHierarchy(void *,int *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault> * *,CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault> * *)

- ea: `0x180026824`
- end: `0x180026d61`
- name: `?BuildVolumeHierarchy@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEAHPEAPEAV?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAPEAV?$CSortedArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@@Z`
- size: `1341`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callers

- `0x18002bae0`

## callees

- `0x180001784`
- `0x180002b38`
- `0x18000638c`
- `0x180025a68`
- `0x180025f00`
- `0x180025f90`
- `0x18002620c`
- `0x180026824`
- `0x180027008`
- `0x180027d04`
- `0x180027e90`
- `0x1800288c8`
- `0x1800293a4`
- `0x18002aed4`
- `0x18002c9fc`
- `0x18002cb7c`
- `0x180032310`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026d1f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026cff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800269af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800269af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800269de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800269de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800269cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026cbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026cde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800269cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026cbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026cde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026ccc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026cec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026ccc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026cec`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026a52`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026a52`
- `WDSCORE!CurrentIP` at `0x180026bb2`
- `WDSCORE!CurrentIP` at `0x180026bb2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180026c1e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180026c1e`

## string_xrefs

- `0x180026c07`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x180026bdc`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::BuildVolumeHierarchy`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::BuildVolumeHierarchy(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  unsigned int v4; // r15d
  __int64 v5; // rdi
  _QWORD *v6; // rbx
  unsigned int *v7; // rsi
  _QWORD *v8; // rax
  _QWORD *v9; // r13
  int VolumeNameForPath; // eax
  unsigned int v11; // r12d
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // r14
  char *FileW; // r14
  HANDLE ProcessHeap; // rax
  void *v17; // rcx
  char *v18; // r14
  signed int v19; // eax
  int v20; // r15d
  __int64 v21; // r14
  int v22; // ecx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // r15
  __int64 v26; // r14
  __int64 v27; // rdx
  __int64 v28; // rcx
  DWORD v29; // r15d
  __int64 v30; // r14
  struct tagLOG_PARTIAL_MSG *v31; // rax
  _QWORD *v32; // rcx
  signed int LastError; // eax
  void *v34; // r14
  HANDLE v35; // rax
  HANDLE v36; // rax
  int v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  int i; // [rsp+78h] [rbp-88h]
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h]
  _QWORD *v44; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h]
  _DWORD *v46; // [rsp+A0h] [rbp-60h]
  _QWORD *v47; // [rsp+A8h] [rbp-58h]
  _QWORD *v48; // [rsp+B0h] [rbp-50h]
  _OWORD InBuffer[2]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = 0;
  v48 = a4;
  v47 = a3;
  v5 = -1;
  v46 = a2;
  v6 = 0;
  v39 = 0;
  v40 = 0;
  v7 = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  v43 = 0;
  BytesReturned = 0;
  v38 = 0;
  v8 = operator new(0x10u);
  v9 = v8;
  if ( v8 )
  {
    *v8 = 0;
    v8[1] = 0;
  }
  else
  {
    v9 = 0;
  }
  v44 = v9;
  if ( !v9 )
  {
    v12 = 2147942414LL;
    v11 = -2147024882;
    goto LABEL_52;
  }
  VolumeNameForPath = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::SetSize(
                        v9,
                        0x20000);
  v11 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
    goto LABEL_6;
  v13 = operator new(0x10u);
  v6 = v13;
  if ( !v13 )
  {
    v11 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
    v6 = 0;
    goto LABEL_53;
  }
  *v13 = 0;
  v13[1] = 0;
  VolumeNameForPath = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(
                        v13,
                        0x20000);
  v11 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
    goto LABEL_6;
  VolumeNameForPath = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(
                        &v39,
                        0x20000);
  v11 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
    goto LABEL_6;
  VolumeNameForPath = CMiscHelpersT<CEmptyType>::ExpandFileName(L"%systemdrive%");
  v11 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
    goto LABEL_6;
  VolumeNameForPath = CFileUtilsT<CEmptyType>::GetVolumeNameForPath(v43, FileName);
  v11 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
    goto LABEL_6;
  v14 = -1;
  do
    ++v14;
  while ( FileName[v14] );
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( (_DWORD)v14 && FileName[(unsigned int)(v14 - 1)] == 92 )
  {
    if ( 2 * (unsigned __int64)(unsigned int)(v14 - 1) >= 0x208 )
      _report_rangecheckfailure();
    FileName[(unsigned int)(v14 - 1)] = 0;
  }
  FileW = (char *)CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x20000080u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    goto LABEL_35;
  }
  DWORD1(InBuffer[0]) = 63;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x400000u);
  if ( !v7 )
  {
    v11 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
    v5 = (__int64)FileW;
    v7 = 0;
    goto LABEL_53;
  }
  v11 = 0;
  v5 = (__int64)FileW;
LABEL_22:
  v17 = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    v17 = FileW;
  if ( DeviceIoControl(v17, 0x90277u, InBuffer, 0x20u, v7, 0x400000u, &BytesReturned, 0) )
  {
    if ( *v7 )
    {
      v18 = (char *)v7 + v7[1];
      while ( 1 )
      {
        VolumeNameForPath = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessFileEntry(v18, v9, &v39);
        v11 = VolumeNameForPath;
        if ( VolumeNameForPath < 0 )
          break;
        ++v4;
        v18 += *((unsigned int *)v18 + 1);
        if ( v4 >= *v7 )
        {
          DWORD1(InBuffer[0]) &= ~1u;
          FileW = (char *)v5;
          v4 = 0;
          goto LABEL_22;
        }
      }
LABEL_6:
      v12 = (unsigned int)VolumeNameForPath;
LABEL_52:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
      goto LABEL_53;
    }
    goto LABEL_36;
  }
  v19 = GetLastError();
  if ( v19 != 38 )
  {
    if ( v19 > 0 )
      v11 = (unsigned __int16)v19 | 0x80070000;
    else
      v11 = v19;
    if ( (v11 & 0x80000000) == 0 )
      goto LABEL_53;
LABEL_35:
    v12 = v11;
    goto LABEL_52;
  }
LABEL_36:
  v20 = HIDWORD(v39);
  v21 = v40;
  if ( HIDWORD(v39) )
    std::_Sort<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex *,__int64,bool (*)(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex const &,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex const &)>(
      v40,
      v40 + 16LL * SHIDWORD(v39),
      (16LL * SHIDWORD(v39)) >> 4);
  v22 = v39;
  v39 = *v6;
  v23 = v6[1];
  v6[1] = 0;
  *((_DWORD *)v6 + 1) = v20;
  *(_DWORD *)v6 = v22;
  v40 = v23;
  v24 = 0;
  v6[1] = v21;
  for ( i = 0; v24 < *((_DWORD *)v9 + 1); i = v24 )
  {
    v25 = v9[1];
    v26 = v25 + ((__int64)v24 << 6);
    v45 = v26;
    v27 = *(_QWORD *)(v26 + 24);
    if ( v27 )
    {
      if ( (unsigned __int8)CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Find(
                              v6,
                              v27,
                              &v38) )
      {
        v28 = v25 + ((__int64)*(int *)(v6[1] + 16LL * v38 + 8) << 6);
        *(_QWORD *)(v26 + 24) = v28;
        VolumeNameForPath = CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Append(
                              v28 + 48,
                              v26);
        v11 = VolumeNameForPath;
        if ( VolumeNameForPath < 0 )
          goto LABEL_6;
      }
      else
      {
        v29 = GetLastError();
        v30 = CurrentIP();
        v31 = ConstructPartialMsgW(0x2000000u, "Cannot find %d from the indexes", *(_QWORD *)(v45 + 24));
        WdsSetupLogMessageW(
          v31,
          0,
          L"D",
          0,
          852,
          L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
          L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::BuildVolumeHierarchy",
          v30,
          v29,
          0,
          0);
      }
    }
    v24 = i + 1;
  }
  v32 = v48;
  v44 = 0;
  *v46 = 0;
  *v47 = v9;
  *v32 = v6;
  v6 = 0;
LABEL_53:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  if ( v43 )
  {
    v34 = (void *)(v43 - 4);
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v34);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v7 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v7);
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v5);
  CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(&v39);
  if ( v6 )
  {
    CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(v6);
    operator delete(v6);
  }
  SP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>>>::~SP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>,SP_CPP<CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>>>(&v44);
  return v11;
}

```

## disassembly

```asm
0x180026824  mov     [rsp-8+arg_0], rbx
0x180026829  push    rbp
0x18002682a  push    rsi
0x18002682b  push    rdi
0x18002682c  push    r12
0x18002682e  push    r13
0x180026830  push    r14
0x180026832  push    r15
0x180026834  lea     rbp, [rsp-200h]
0x18002683c  sub     rsp, 300h
0x180026843  mov     rax, cs:__security_cookie
0x18002684a  xor     rax, rsp
0x18002684d  mov     [rbp+230h+var_40], rax
0x180026854  xor     r15d, r15d
0x180026857  mov     [rbp+230h+var_280], r9
0x18002685b  xorps   xmm0, xmm0
0x18002685e  mov     [rbp+230h+var_288], r8
0x180026862  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026866  mov     [rbp+230h+var_290], rdx
0x18002686a  mov     ebx, r15d
0x18002686d  mov     [rsp+330h+var_2C8], r15
0x180026872  mov     [rsp+330h+var_2C0], r15
0x180026877  mov     esi, r15d
0x18002687a  movups  [rbp+230h+InBuffer], xmm0
0x18002687e  lea     ecx, [rdi+11h]; Size
0x180026881  mov     [rbp+230h+var_2A8], r15
0x180026885  movups  [rbp+230h+var_268], xmm0
0x180026889  mov     [rbp+230h+BytesReturned], r15d
0x18002688d  mov     [rsp+330h+var_2D0], r15d
0x180026892  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026897  mov     r13, rax
0x18002689a  test    rax, rax
0x18002689d  jz      short loc_1800268A8
0x18002689f  mov     [rax], r15
0x1800268a2  mov     [rax+8], r15
0x1800268a6  jmp     short loc_1800268AB
0x1800268a8  mov     r13, r15
0x1800268ab  mov     [rbp+230h+var_2A0], r13
0x1800268af  test    r13, r13
0x1800268b2  jz      loc_180026C9C
0x1800268b8  mov     r14d, 20000h
0x1800268be  mov     rcx, r13
0x1800268c1  mov     edx, r14d
0x1800268c4  call    ?SetSize@?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1800268c9  mov     r12d, eax
0x1800268cc  test    eax, eax
0x1800268ce  jns     short loc_1800268D7
0x1800268d0  mov     ecx, eax
0x1800268d2  jmp     loc_180026CA4
0x1800268d7  mov     ecx, 10h; Size
0x1800268dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800268e1  mov     rbx, rax
0x1800268e4  test    rax, rax
0x1800268e7  jz      loc_180026C8A
0x1800268ed  mov     edx, r14d
0x1800268f0  mov     [rax], r15
0x1800268f3  mov     rcx, rax
0x1800268f6  mov     [rax+8], r15
0x1800268fa  call    ?SetSize@?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1800268ff  mov     r12d, eax
0x180026902  test    eax, eax
0x180026904  js      short loc_1800268D0
0x180026906  mov     edx, r14d
0x180026909  lea     rcx, [rsp+330h+var_2C8]
0x18002690e  call    ?SetSize@?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180026913  mov     r12d, eax
0x180026916  test    eax, eax
0x180026918  js      short loc_1800268D0
0x18002691a  lea     rdx, [rbp+230h+var_2A8]
0x18002691e  lea     rcx, Src; "%systemdrive%"
0x180026925  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x18002692a  mov     r12d, eax
0x18002692d  test    eax, eax
0x18002692f  js      short loc_1800268D0
0x180026931  mov     rcx, [rbp+230h+var_2A8]
0x180026935  lea     rdx, [rbp+230h+FileName]
0x180026939  call    ?GetVolumeNameForPath@?$CFileUtilsT@VCEmptyType@@@@SAJPEBGPEAGK@Z; CFileUtilsT<CEmptyType>::GetVolumeNameForPath(ushort const *,ushort *,ulong)
0x18002693e  mov     r12d, eax
0x180026941  test    eax, eax
0x180026943  js      short loc_1800268D0
0x180026945  lea     rax, [rbp+230h+FileName]
0x180026949  mov     r14, rdi
0x18002694c  inc     r14
0x18002694f  cmp     [rax+r14*2], r15w
0x180026954  jnz     short loc_18002694C
0x180026956  xor     ecx, ecx
0x180026958  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002695d  xor     ecx, ecx
0x18002695f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180026964  test    r14d, r14d
0x180026967  jz      short loc_18002698B
0x180026969  lea     ecx, [r14-1]
0x18002696d  add     rcx, rcx
0x180026970  cmp     [rbp+rcx+230h+FileName], 5Ch ; '\'
0x180026976  jnz     short loc_18002698B
0x180026978  cmp     rcx, 208h
0x18002697f  jnb     loc_180026D5B
0x180026985  mov     [rbp+rcx+230h+FileName], r15w
0x18002698b  mov     [rsp+330h+hTemplateFile], r15; hTemplateFile
0x180026990  lea     rcx, [rbp+230h+FileName]; lpFileName
0x180026994  mov     r8d, 3; dwShareMode
0x18002699a  mov     [rsp+330h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x1800269a2  xor     r9d, r9d; lpSecurityAttributes
0x1800269a5  mov     [rsp+330h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800269aa  mov     edx, 80000000h; dwDesiredAccess
0x1800269af  call    cs:__imp_CreateFileW
0x1800269b5  mov     r14, rax
0x1800269b8  lea     rcx, [rax-1]
0x1800269bc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800269c0  ja      loc_180026C5C
0x1800269c6  mov     dword ptr [rbp+230h+InBuffer+4], 3Fh ; '?'
0x1800269cd  call    cs:__imp_GetProcessHeap
0x1800269d3  xor     edx, edx; dwFlags
0x1800269d5  mov     r8d, 400000h; dwBytes
0x1800269db  mov     rcx, rax; hHeap
0x1800269de  call    cs:__imp_HeapAlloc
0x1800269e4  mov     rsi, rax
0x1800269e7  test    rax, rax
0x1800269ea  jnz     short loc_180026A04
0x1800269ec  mov     ecx, 8007000Eh
0x1800269f1  mov     r12d, ecx
0x1800269f4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800269f9  mov     rdi, r14
0x1800269fc  mov     rsi, r15
0x1800269ff  jmp     loc_180026CA9
0x180026a04  mov     r12d, r15d
0x180026a07  mov     rdi, r14
0x180026a0a  test    rsi, rsi
0x180026a0d  mov     [rsp+330h+lpOverlapped], r15; lpOverlapped
0x180026a12  lea     rax, [rdi-1]
0x180026a16  mov     rdx, r15
0x180026a19  cmovnz  rdx, rsi
0x180026a1d  lea     r8, [rbp+230h+InBuffer]; lpInBuffer
0x180026a21  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026a25  mov     rcx, r15
0x180026a28  mov     r9d, 20h ; ' '; nInBufferSize
0x180026a2e  setnbe  al
0x180026a31  test    al, al
0x180026a33  lea     rax, [rbp+230h+BytesReturned]
0x180026a37  mov     [rsp+330h+hTemplateFile], rax; lpBytesReturned
0x180026a3c  mov     [rsp+330h+dwFlagsAndAttributes], 400000h; nOutBufferSize
0x180026a44  cmovz   rcx, r14; hDevice
0x180026a48  mov     qword ptr [rsp+330h+dwCreationDisposition], rdx; lpOutBuffer
0x180026a4d  mov     edx, 90277h; dwIoControlCode
0x180026a52  call    cs:__imp_DeviceIoControl
0x180026a58  test    eax, eax
0x180026a5a  jz      short loc_180026AA6
0x180026a5c  cmp     [rsi], r15d
0x180026a5f  jz      short loc_180026AD6
0x180026a61  mov     r14d, [rsi+4]
0x180026a65  add     r14, rsi
0x180026a68  cmp     dword ptr [rsi], 0
0x180026a6b  jbe     short loc_180026A97
0x180026a6d  lea     r8, [rsp+330h+var_2C8]
0x180026a72  mov     rdx, r13
0x180026a75  mov     rcx, r14
0x180026a78  call    ?ProcessFileEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBU_FILE_LAYOUT_ENTRY@@PEAV?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAV?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::ProcessFileEntry(_FILE_LAYOUT_ENTRY const *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault> *,CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,CAdaptorDefault,CPoliciesDefault> *)
0x180026a7d  mov     r12d, eax
0x180026a80  test    eax, eax
0x180026a82  js      loc_1800268D0
0x180026a88  mov     eax, [r14+4]
0x180026a8c  inc     r15d
0x180026a8f  add     r14, rax
0x180026a92  cmp     r15d, [rsi]
0x180026a95  jb      short loc_180026A6D
0x180026a97  and     dword ptr [rbp+230h+InBuffer+4], 0FFFFFFFEh
0x180026a9b  mov     r14, rdi
0x180026a9e  xor     r15d, r15d
0x180026aa1  jmp     loc_180026A0A
0x180026aa6  call    cs:__imp_GetLastError
0x180026aac  cmp     eax, 26h ; '&'
0x180026aaf  jz      short loc_180026AD6
0x180026ab1  test    eax, eax
0x180026ab3  jg      short loc_180026ABA
0x180026ab5  mov     r12d, eax
0x180026ab8  jmp     short loc_180026AC5
0x180026aba  movzx   r12d, ax
0x180026abe  or      r12d, 80070000h
0x180026ac5  test    r12d, r12d
0x180026ac8  jns     loc_180026CA9
0x180026ace  mov     ecx, r12d
0x180026ad1  jmp     loc_180026CA4
0x180026ad6  movsxd  r15, dword ptr [rsp+330h+var_2C8+4]
0x180026adb  mov     r14, [rsp+330h+var_2C0]
0x180026ae0  test    r15d, r15d
0x180026ae3  jz      short loc_180026B01
0x180026ae5  mov     rdx, r15
0x180026ae8  mov     rcx, r14
0x180026aeb  shl     rdx, 4
0x180026aef  add     rdx, r14
0x180026af2  mov     r8, rdx
0x180026af5  sub     r8, r14
0x180026af8  sar     r8, 4
0x180026afc  call    ??$_Sort@PEAUCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_JP6A_NAEBU12@0@Z@std@@YAXPEAUCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@0_JP6A_NAEBU12@2@Z@Z; std::_Sort<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex *,__int64,bool (*)(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex const &,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex const &)>(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex *,__int64,bool (*)(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex const &,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex const &))
0x180026b01  mov     eax, [rbx]
0x180026b03  mov     ecx, dword ptr [rsp+330h+var_2C8]
0x180026b07  mov     dword ptr [rsp+330h+var_2C8], eax
0x180026b0b  mov     eax, [rbx+4]
0x180026b0e  mov     dword ptr [rsp+330h+var_2C8+4], eax
0x180026b12  mov     rax, [rbx+8]
0x180026b16  mov     qword ptr [rbx+8], 0
0x180026b1e  mov     [rbx+4], r15d
0x180026b22  xor     r15d, r15d
0x180026b25  mov     [rbx], ecx
0x180026b27  mov     [rsp+330h+var_2C0], rax
0x180026b2c  mov     eax, r15d
0x180026b2f  mov     [rbx+8], r14
0x180026b33  mov     [rsp+330h+var_2B8], eax
0x180026b37  cmp     [r13+4], r15d
0x180026b3b  jle     loc_180026C3B
0x180026b41  mov     r15, [r13+8]
0x180026b45  movsxd  r14, eax
0x180026b48  shl     r14, 6
0x180026b4c  add     r14, r15
0x180026b4f  mov     [rbp+230h+var_298], r14
0x180026b53  mov     rdx, [r14+18h]
0x180026b57  test    rdx, rdx
0x180026b5a  jz      loc_180026C24
0x180026b60  lea     r8, [rsp+330h+var_2D0]
0x180026b65  mov     rcx, rbx
0x180026b68  call    ?Find@?$CSortedArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_N_KPEAH@Z; CSortedArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Find(unsigned __int64,int *)
0x180026b6d  test    al, al
0x180026b6f  jz      short loc_180026BA9
0x180026b71  mov     rcx, [rbx+8]
0x180026b75  mov     rdx, r14
0x180026b78  movsxd  rax, [rsp+330h+var_2D0]
0x180026b7d  add     rax, rax
0x180026b80  movsxd  rcx, dword ptr [rcx+rax*8+8]
0x180026b85  shl     rcx, 6
0x180026b89  add     rcx, r15
0x180026b8c  mov     [r14+18h], rcx
0x180026b90  add     rcx, 30h ; '0'
0x180026b94  call    ?Append@?$CArray@PEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@PEAU12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJPEAUCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@@Z; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *,CAdaptorDefault,CPoliciesDefault>::Append(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry *)
0x180026b99  xor     r15d, r15d
0x180026b9c  mov     r12d, eax
0x180026b9f  test    eax, eax
0x180026ba1  js      loc_1800268D0
0x180026ba7  jmp     short loc_180026C27
0x180026ba9  call    cs:__imp_GetLastError
0x180026baf  mov     r15d, eax
0x180026bb2  call    cs:__imp_CurrentIP
0x180026bb8  mov     r8, [rbp+230h+var_298]
0x180026bbc  lea     rdx, aCannotFindDFro; "Cannot find %d from the indexes"
0x180026bc3  mov     ecx, 2000000h; unsigned int
0x180026bc8  mov     r14, rax
0x180026bcb  mov     r8, [r8+18h]
0x180026bcf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180026bd4  mov     [rsp+330h+var_2E0], 0
0x180026bdc  lea     rcx, aCfastdeleteimp_2; "CFastDeleteImplT<class CDirectoryProvid"...
0x180026be3  mov     [rsp+330h+var_2E8], 0
0x180026bec  lea     r8, aD_0; "D"
0x180026bf3  mov     [rsp+330h+var_2F0], r15d
0x180026bf8  xor     r9d, r9d
0x180026bfb  mov     [rsp+330h+lpOverlapped], r14
0x180026c00  xor     edx, edx
0x180026c02  mov     [rsp+330h+hTemplateFile], rcx
0x180026c07  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x180026c0e  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], rcx
0x180026c13  mov     rcx, rax
0x180026c16  mov     [rsp+330h+dwCreationDisposition], 354h
0x180026c1e  call    cs:__imp_WdsSetupLogMessageW
0x180026c24  xor     r15d, r15d
0x180026c27  mov     eax, [rsp+330h+var_2B8]
0x180026c2b  inc     eax
0x180026c2d  mov     [rsp+330h+var_2B8], eax
0x180026c31  cmp     eax, [r13+4]
0x180026c35  jl      loc_180026B41
0x180026c3b  mov     rax, [rbp+230h+var_290]
0x180026c3f  mov     rcx, [rbp+230h+var_280]
0x180026c43  mov     [rbp+230h+var_2A0], r15
0x180026c47  mov     [rax], r15d
0x180026c4a  mov     rax, [rbp+230h+var_288]
0x180026c4e  mov     [rax], r13
0x180026c51  mov     rax, rbx
0x180026c54  mov     [rcx], rax
0x180026c57  mov     rbx, r15
0x180026c5a  jmp     short loc_180026CA9
0x180026c5c  call    cs:__imp_GetLastError
0x180026c62  mov     r12d, eax
0x180026c65  test    eax, eax
0x180026c67  jnz     short loc_180026C74
0x180026c69  mov     r12d, 80004005h
0x180026c6f  jmp     loc_180026ACE
0x180026c74  jle     loc_180026ACE
0x180026c7a  movzx   r12d, ax
0x180026c7e  or      r12d, 80070000h
0x180026c85  jmp     loc_180026ACE
0x180026c8a  mov     ecx, 8007000Eh
0x180026c8f  mov     r12d, ecx
0x180026c92  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180026c97  mov     rbx, r15
0x180026c9a  jmp     short loc_180026CA9
0x180026c9c  mov     ecx, 8007000Eh
0x180026ca1  mov     r12d, ecx
0x180026ca4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180026ca9  mov     ecx, r12d
0x180026cac  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180026cb1  mov     rax, [rbp+230h+var_2A8]
0x180026cb5  test    rax, rax
0x180026cb8  jz      short loc_180026CD9
  ... truncated ...
```
