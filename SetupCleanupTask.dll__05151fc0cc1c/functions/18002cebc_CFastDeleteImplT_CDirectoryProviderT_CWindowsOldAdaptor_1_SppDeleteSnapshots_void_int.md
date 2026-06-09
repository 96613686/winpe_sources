# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::SppDeleteSnapshots(void *,int *)

- ea: `0x18002cebc`
- end: `0x18002d435`
- name: `?SppDeleteSnapshots@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAXPEAH@Z`
- size: `1401`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002bae0`

## callees

- `0x18000638c`
- `0x180026598`
- `0x180027008`
- `0x180027d04`
- `0x1800293a4`
- `0x18002c658`
- `0x18002cebc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cfd3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cfd3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002cf2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002cf2d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d3f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d3f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cf6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cf6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d04f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d30e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cf7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d04f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d30e`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002d045`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002d2ac`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002d045`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18002d2ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d0f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d1c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d2e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d3ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d402`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d085`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d0f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d1c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d2e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d3ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d402`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d1d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d2f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d3c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d411`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d1d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d2f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d3c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d411`
- `WDSCORE!CurrentIP` at `0x18002d1e8`
- `WDSCORE!CurrentIP` at `0x18002d317`
- `WDSCORE!CurrentIP` at `0x18002d1e8`
- `WDSCORE!CurrentIP` at `0x18002d317`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002d24c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002d386`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002d24c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002d386`

## string_xrefs

- `0x18002d211`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002d36f`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002d0ae`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::SppDeleteSnapshots`
- `0x18002d344`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::SppDeleteSnapshots`
- `0x18002d1f2`: `Failed to delete snapshot group %s. hr = 0x%x`
- `0x18002d321`: `SppDeleteSnapshots reclaimed %dKB space.`

## pseudocode

```c
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::SppDeleteSnapshots(
        __int64 a1,
        _DWORD *a2)
{
  const char *QuadPart; // rdi
  void (__fastcall *v3)(_QWORD, _QWORD); // r15
  int v4; // eax
  signed int LowPart; // r13d
  HMODULE v6; // rbx
  LPCWSTR v7; // rsi
  union _ULARGE_INTEGER v8; // r12
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v11; // eax
  HRESULT v12; // eax
  int v13; // eax
  LPCWSTR v14; // r14
  unsigned int v15; // esi
  int v16; // ecx
  signed int v17; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v19; // ebx
  __int64 v20; // r15
  __int64 v21; // rax
  HANDLE v22; // rax
  int v23; // ecx
  union _ULARGE_INTEGER v24; // rsi
  HANDLE v25; // rax
  DWORD v26; // r14d
  __int64 v27; // rsi
  struct tagLOG_PARTIAL_MSG *v28; // rax
  int v29; // eax
  LPCWSTR v30; // r14
  unsigned int v31; // esi
  int v32; // ecx
  signed int v33; // eax
  HANDLE v34; // rax
  DWORD v35; // r14d
  __int64 v36; // rsi
  struct tagLOG_PARTIAL_MSG *v37; // rax
  HANDLE v38; // rax
  HANDLE v39; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-99h]
  __int64 v42; // [rsp+28h] [rbp-91h]
  __int64 v43; // [rsp+30h] [rbp-89h]
  __int64 v44; // [rsp+38h] [rbp-81h]
  __int64 v45; // [rsp+40h] [rbp-79h]
  __int64 v46; // [rsp+48h] [rbp-71h]
  __int64 v47; // [rsp+50h] [rbp-69h]
  __int64 v48; // [rsp+58h] [rbp-61h]
  __int64 v49; // [rsp+60h] [rbp-59h]
  __int64 v50; // [rsp+70h] [rbp-49h] BYREF
  LPVOID v51; // [rsp+78h] [rbp-41h] BYREF
  LPCWSTR lpLibFileName; // [rsp+80h] [rbp-39h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-19h]
  union _ULARGE_INTEGER v55; // [rsp+A8h] [rbp-11h]
  HMODULE v56; // [rsp+B0h] [rbp-9h]
  FARPROC ProcAddress; // [rsp+B8h] [rbp-1h]
  union _ULARGE_INTEGER v58; // [rsp+C0h] [rbp+7h]
  unsigned int v59; // [rsp+120h] [rbp+67h] BYREF
  int v60; // [rsp+124h] [rbp+6Bh]
  _DWORD *v61; // [rsp+128h] [rbp+6Fh]
  LPCWSTR lpDirectoryName; // [rsp+130h] [rbp+77h] BYREF
  union _ULARGE_INTEGER v63; // [rsp+138h] [rbp+7Fh] BYREF

  v61 = a2;
  v60 = HIDWORD(a1);
  lpLibFileName = 0;
  QuadPart = 0;
  v51 = 0;
  v3 = 0;
  v50 = 0;
  v59 = 0;
  v4 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(a1, (unsigned __int16 **)&lpLibFileName);
  LowPart = v4;
  if ( v4 < 0 )
  {
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
LABEL_58:
    v7 = lpLibFileName;
    goto LABEL_59;
  }
  v7 = lpLibFileName;
  v55.QuadPart = 0;
  v58.QuadPart = 0;
  v8.QuadPart = 0;
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  v6 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    LowPart = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        LowPart = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LowPart = -2147467259;
    }
    v6 = 0;
    goto LABEL_14;
  }
  ProcAddress = GetProcAddress(Library, "SppFreeGroupPropArray");
  v3 = (void (__fastcall *)(_QWORD, _QWORD))ProcAddress;
  if ( ProcAddress )
  {
    v12 = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, &v51);
    LowPart = v12;
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, __int64 *))(*(_QWORD *)v51 + 64LL))(v51, &v59, &v50),
          v63.LowPart = v12,
          LowPart = v12,
          v12 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
      goto LABEL_59;
    }
    lpDirectoryName = 0;
    TotalNumberOfFreeBytes[0].QuadPart = 0;
    v13 = CMiscHelpersT<CEmptyType>::ExpandFileName(
            L"%systemdrive%\\System Volume Information",
            (LPWSTR *)&lpDirectoryName);
    v14 = lpDirectoryName;
    v15 = v13;
    if ( v13 >= 0 )
    {
      if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, 0, TotalNumberOfFreeBytes) )
      {
        v55 = TotalNumberOfFreeBytes[0];
LABEL_29:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
        if ( v14 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, (LPVOID)(v14 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        if ( v59 )
        {
          v56 = v6;
          v19 = 0;
          do
          {
            v20 = 144LL * v19;
            v54 = v20;
            v21 = *(_QWORD *)v51;
            *(_OWORD *)&TotalNumberOfFreeBytes[0].LowPart = *(_OWORD *)(v20 + v50);
            LODWORD(lpDirectoryName) = (*(__int64 (__fastcall **)(LPVOID, union _ULARGE_INTEGER *))(v21 + 56))(
                                         v51,
                                         TotalNumberOfFreeBytes);
            if ( (int)lpDirectoryName < 0 )
            {
              if ( QuadPart )
              {
                v22 = GetProcessHeap();
                HeapFree(v22, 0, (LPVOID)(QuadPart - 4));
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                QuadPart = 0;
              }
              TotalNumberOfFreeBytes[0].QuadPart = 0;
              LODWORD(v49) = *(unsigned __int8 *)(v20 + v50 + 15);
              LODWORD(v48) = *(unsigned __int8 *)(v20 + v50 + 14);
              LODWORD(v47) = *(unsigned __int8 *)(v20 + v50 + 13);
              LODWORD(v46) = *(unsigned __int8 *)(v20 + v50 + 12);
              LODWORD(v45) = *(unsigned __int8 *)(v20 + v50 + 11);
              LODWORD(v44) = *(unsigned __int8 *)(v20 + v50 + 10);
              LODWORD(v43) = *(unsigned __int8 *)(v20 + v50 + 9);
              LODWORD(v42) = *(unsigned __int8 *)(v20 + v50 + 8);
              LODWORD(ppv) = *(unsigned __int16 *)(v20 + v50 + 6);
              v23 = STRAPI_Format(
                      (unsigned __int16 **)TotalNumberOfFreeBytes,
                      L"%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
                      *(unsigned int *)(v54 + v50),
                      *(unsigned __int16 *)(v54 + v50 + 4),
                      ppv,
                      v42,
                      v43,
                      v44,
                      v45,
                      v46,
                      v47,
                      v48,
                      v49);
              if ( v23 >= 0 )
              {
                QuadPart = (const char *)TotalNumberOfFreeBytes[0].QuadPart;
                v24.QuadPart = 0;
              }
              else
              {
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
                v24 = TotalNumberOfFreeBytes[0];
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
              if ( v24.QuadPart )
              {
                v25 = GetProcessHeap();
                HeapFree(v25, 0, (LPVOID)(v24.QuadPart - 4));
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              }
              v26 = GetLastError();
              v27 = CurrentIP();
              v28 = ConstructPartialMsgW(
                      0x2000000,
                      "Failed to delete snapshot group %s. hr = 0x%x",
                      QuadPart,
                      (_DWORD)lpDirectoryName);
              WdsSetupLogMessageW(
                v28,
                0,
                L"D",
                0,
                651,
                L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
                L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::SppDeleteSnapshots",
                v27,
                v26,
                0,
                0);
            }
            ++v19;
          }
          while ( v19 < v59 );
          v6 = v56;
          LowPart = v63.LowPart;
          v3 = (void (__fastcall *)(_QWORD, _QWORD))ProcAddress;
          v8 = v58;
        }
        lpDirectoryName = 0;
        v63.QuadPart = 0;
        v29 = CMiscHelpersT<CEmptyType>::ExpandFileName(
                L"%systemdrive%\\System Volume Information",
                (LPWSTR *)&lpDirectoryName);
        v30 = lpDirectoryName;
        v31 = v29;
        if ( v29 >= 0 )
        {
          if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, 0, &v63) )
          {
            v8 = v63;
            goto LABEL_54;
          }
          v33 = GetLastError();
          v31 = v33;
          if ( v33 )
          {
            if ( v33 > 0 )
              v31 = (unsigned __int16)v33 | 0x80070000;
          }
          else
          {
            v31 = -2147467259;
          }
          v32 = v31;
        }
        else
        {
          v32 = v29;
        }
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v32);
LABEL_54:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v31);
        if ( v30 )
        {
          v34 = GetProcessHeap();
          HeapFree(v34, 0, (LPVOID)(v30 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        *v61 = 0;
        goto LABEL_57;
      }
      v17 = GetLastError();
      v15 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v15 = (unsigned __int16)v17 | 0x80070000;
      }
      else
      {
        v15 = -2147467259;
      }
      v16 = v15;
    }
    else
    {
      v16 = v13;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    goto LABEL_29;
  }
  v11 = GetLastError();
  LowPart = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      LowPart = (unsigned __int16)v11 | 0x80070000;
  }
  else
  {
    LowPart = -2147467259;
  }
LABEL_14:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(LowPart);
  if ( LowPart >= 0 )
  {
LABEL_57:
    v35 = GetLastError();
    v36 = CurrentIP();
    v37 = ConstructPartialMsgW(
            0x4000000,
            "SppDeleteSnapshots reclaimed %dKB space.",
            (v8.QuadPart - v55.QuadPart) >> 10);
    WdsSetupLogMessageW(
      v37,
      0,
      L"D",
      0,
      670,
      L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
      L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::SppDeleteSnapshots",
      v36,
      v35,
      0,
      0);
    goto LABEL_58;
  }
LABEL_59:
  if ( v50 && v3 )
    v3(v59, &v50);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(LowPart);
  if ( QuadPart )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, (LPVOID)(QuadPart - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v6 )
    FreeLibrary(v6);
  if ( v7 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)LowPart;
}

```

## disassembly

```asm
0x18002cebc  mov     [rsp-8+arg_8], rdx
0x18002cec1  mov     [rsp-8+arg_0], rcx
0x18002cec6  push    rbp
0x18002cec7  push    rbx
0x18002cec8  push    rsi
0x18002cec9  push    rdi
0x18002ceca  push    r12
0x18002cecc  push    r13
0x18002cece  push    r14
0x18002ced0  push    r15
0x18002ced2  lea     rbp, [rsp-1Fh]
0x18002ced7  sub     rsp, 0D8h
0x18002cede  xor     r14d, r14d
0x18002cee1  lea     rdx, [rbp+57h+lpLibFileName]
0x18002cee5  mov     [rbp+57h+lpLibFileName], r14
0x18002cee9  mov     edi, r14d
0x18002ceec  mov     [rbp+57h+var_98], r14
0x18002cef0  mov     r15d, r14d
0x18002cef3  mov     [rbp+57h+var_A0], r14
0x18002cef7  mov     dword ptr [rbp+57h+arg_0], r14d
0x18002cefb  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x18002cf00  mov     r13d, eax
0x18002cf03  test    eax, eax
0x18002cf05  jns     short loc_18002CF16
0x18002cf07  mov     ecx, eax
0x18002cf09  mov     ebx, r14d
0x18002cf0c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002cf11  jmp     loc_18002D38F
0x18002cf16  mov     rsi, [rbp+57h+lpLibFileName]
0x18002cf1a  xor     r8d, r8d; dwFlags
0x18002cf1d  mov     rcx, rsi; lpLibFileName
0x18002cf20  mov     [rbp+57h+var_68], r14
0x18002cf24  xor     edx, edx; hFile
0x18002cf26  mov     [rbp+57h+var_50], r14
0x18002cf2a  mov     r12, r14
0x18002cf2d  call    cs:__imp_LoadLibraryExW
0x18002cf33  mov     rbx, rax
0x18002cf36  test    rax, rax
0x18002cf39  jnz     short loc_18002CF62
0x18002cf3b  call    cs:__imp_GetLastError
0x18002cf41  mov     r13d, eax
0x18002cf44  test    eax, eax
0x18002cf46  jnz     short loc_18002CF50
0x18002cf48  mov     r13d, 80004005h
0x18002cf4e  jmp     short loc_18002CF5D
0x18002cf50  jle     short loc_18002CF5D
0x18002cf52  movzx   r13d, ax
0x18002cf56  or      r13d, 80070000h
0x18002cf5d  mov     rbx, r14
0x18002cf60  jmp     short loc_18002CFA0
0x18002cf62  mov     rcx, rbx; hModule
0x18002cf65  lea     rdx, aSppfreegrouppr; "SppFreeGroupPropArray"
0x18002cf6c  call    cs:__imp_GetProcAddress
0x18002cf72  mov     [rbp+57h+var_58], rax
0x18002cf76  mov     r15, rax
0x18002cf79  test    rax, rax
0x18002cf7c  jnz     short loc_18002CFB6
0x18002cf7e  call    cs:__imp_GetLastError
0x18002cf84  mov     r13d, eax
0x18002cf87  test    eax, eax
0x18002cf89  jnz     short loc_18002CF93
0x18002cf8b  mov     r13d, 80004005h
0x18002cf91  jmp     short loc_18002CFA0
0x18002cf93  jle     short loc_18002CFA0
0x18002cf95  movzx   r13d, ax
0x18002cf99  or      r13d, 80070000h
0x18002cfa0  mov     ecx, r13d
0x18002cfa3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002cfa8  test    r13d, r13d
0x18002cfab  js      loc_18002D393
0x18002cfb1  jmp     loc_18002D30E
0x18002cfb6  xor     edx, edx; pUnkOuter
0x18002cfb8  lea     rax, [rbp+57h+var_98]
0x18002cfbc  lea     r9, IID_ISharedProtectionPoints; riid
0x18002cfc3  mov     [rsp+110h+ppv], rax; ppv
0x18002cfc8  lea     rcx, CLSID_SPP; rclsid
0x18002cfcf  lea     r8d, [rdx+1]; dwClsContext
0x18002cfd3  call    cs:__imp_CoCreateInstance
0x18002cfd9  mov     r13d, eax
0x18002cfdc  test    eax, eax
0x18002cfde  jns     short loc_18002CFEC
0x18002cfe0  mov     ecx, eax
0x18002cfe2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002cfe7  jmp     loc_18002D393
0x18002cfec  mov     rcx, [rbp+57h+var_98]
0x18002cff0  lea     r8, [rbp+57h+var_A0]
0x18002cff4  lea     rdx, [rbp+57h+arg_0]
0x18002cff8  mov     rax, [rcx]
0x18002cffb  mov     rax, [rax+40h]
0x18002cfff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d004  mov     dword ptr [rbp+57h+arg_18], eax
0x18002d007  mov     r13d, eax
0x18002d00a  test    eax, eax
0x18002d00c  js      short loc_18002CFE0
0x18002d00e  lea     rdx, [rbp+57h+lpDirectoryName]
0x18002d012  mov     [rbp+57h+lpDirectoryName], r14
0x18002d016  lea     rcx, aSystemdriveSys; "%systemdrive%\\System Volume Informatio"...
0x18002d01d  mov     qword ptr [rbp+57h+TotalNumberOfFreeBytes], r14
0x18002d021  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x18002d026  mov     r14, [rbp+57h+lpDirectoryName]
0x18002d02a  mov     esi, eax
0x18002d02c  test    eax, eax
0x18002d02e  jns     short loc_18002D039
0x18002d030  mov     ecx, eax
0x18002d032  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002d037  jmp     short loc_18002D079
0x18002d039  lea     r9, [rbp+57h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18002d03d  xor     r8d, r8d; lpTotalNumberOfBytes
0x18002d040  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18002d042  mov     rcx, r14; lpDirectoryName
0x18002d045  call    cs:__imp_GetDiskFreeSpaceExW
0x18002d04b  test    eax, eax
0x18002d04d  jnz     short loc_18002D071
0x18002d04f  call    cs:__imp_GetLastError
0x18002d055  mov     esi, eax
0x18002d057  test    eax, eax
0x18002d059  jnz     short loc_18002D062
0x18002d05b  mov     esi, 80004005h
0x18002d060  jmp     short loc_18002D06D
0x18002d062  jle     short loc_18002D06D
0x18002d064  movzx   esi, ax
0x18002d067  or      esi, 80070000h
0x18002d06d  mov     ecx, esi
0x18002d06f  jmp     short loc_18002D032
0x18002d071  mov     rax, qword ptr [rbp+57h+TotalNumberOfFreeBytes]
0x18002d075  mov     [rbp+57h+var_68], rax
0x18002d079  mov     ecx, esi
0x18002d07b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d080  test    r14, r14
0x18002d083  jz      short loc_18002D0A1
0x18002d085  call    cs:__imp_GetProcessHeap
0x18002d08b  lea     r8, [r14-4]; lpMem
0x18002d08f  xor     edx, edx; dwFlags
0x18002d091  mov     rcx, rax; hHeap
0x18002d094  call    cs:__imp_HeapFree
0x18002d09a  xor     ecx, ecx
0x18002d09c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d0a1  cmp     dword ptr [rbp+57h+arg_0], edi
0x18002d0a4  jbe     loc_18002D26D
0x18002d0aa  mov     [rbp+57h+var_60], rbx
0x18002d0ae  lea     r13, aCfastdeleteimp_4; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002d0b5  mov     ebx, edi
0x18002d0b7  mov     rcx, [rbp+57h+var_98]
0x18002d0bb  lea     rdx, [rbp+57h+TotalNumberOfFreeBytes]
0x18002d0bf  mov     eax, ebx
0x18002d0c1  lea     r15, [rax+rax*8]
0x18002d0c5  mov     rax, [rbp+57h+var_A0]
0x18002d0c9  shl     r15, 4
0x18002d0cd  mov     [rbp+57h+var_70], r15
0x18002d0d1  movups  xmm0, xmmword ptr [r15+rax]
0x18002d0d6  mov     rax, [rcx]
0x18002d0d9  movdqu  xmmword ptr [rbp+57h+TotalNumberOfFreeBytes], xmm0
0x18002d0de  mov     rax, [rax+38h]
0x18002d0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0e7  mov     dword ptr [rbp+57h+lpDirectoryName], eax
0x18002d0ea  test    eax, eax
0x18002d0ec  jns     loc_18002D252
0x18002d0f2  test    rdi, rdi
0x18002d0f5  jz      short loc_18002D115
0x18002d0f7  call    cs:__imp_GetProcessHeap
0x18002d0fd  lea     r8, [rdi-4]; lpMem
0x18002d101  xor     edx, edx; dwFlags
0x18002d103  mov     rcx, rax; hHeap
0x18002d106  call    cs:__imp_HeapFree
0x18002d10c  xor     ecx, ecx
0x18002d10e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d113  xor     edi, edi
0x18002d115  mov     r12, [rbp+57h+var_A0]
0x18002d119  mov     r9, [rbp+57h+var_70]
0x18002d11d  mov     qword ptr [rbp+57h+TotalNumberOfFreeBytes], 0
0x18002d125  movzx   eax, byte ptr [r15+r12+0Fh]
0x18002d12b  movzx   ecx, byte ptr [r15+r12+0Eh]
0x18002d131  movzx   edx, byte ptr [r15+r12+0Dh]
0x18002d137  movzx   r8d, byte ptr [r15+r12+0Ch]
0x18002d13d  movzx   r10d, byte ptr [r15+r12+0Bh]
0x18002d143  movzx   r11d, byte ptr [r15+r12+0Ah]
0x18002d149  movzx   esi, byte ptr [r15+r12+9]
0x18002d14f  movzx   r14d, byte ptr [r15+r12+8]
0x18002d155  movzx   r15d, word ptr [r15+r12+6]
0x18002d15b  movzx   r9d, word ptr [r9+r12+4]
0x18002d161  mov     [rsp+110h+var_B0], eax
0x18002d165  mov     rax, [rbp+57h+var_70]
0x18002d169  mov     dword ptr [rsp+110h+var_B8], ecx
0x18002d16d  lea     rcx, [rbp+57h+TotalNumberOfFreeBytes]; unsigned __int16 **
0x18002d171  mov     dword ptr [rsp+110h+var_C0], edx
0x18002d175  lea     rdx, a08lx04x04x02x0; "%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x18002d17c  mov     dword ptr [rsp+110h+var_C8], r8d
0x18002d181  mov     r8d, [rax+r12]
0x18002d185  mov     dword ptr [rsp+110h+var_D0], r10d
0x18002d18a  mov     dword ptr [rsp+110h+var_D8], r11d
0x18002d18f  mov     dword ptr [rsp+110h+var_E0], esi
0x18002d193  mov     dword ptr [rsp+110h+var_E8], r14d
0x18002d198  mov     dword ptr [rsp+110h+ppv], r15d
0x18002d19d  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18002d1a2  mov     ecx, eax
0x18002d1a4  test    eax, eax
0x18002d1a6  jns     short loc_18002D1B3
0x18002d1a8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002d1ad  mov     rsi, qword ptr [rbp+57h+TotalNumberOfFreeBytes]
0x18002d1b1  jmp     short loc_18002D1B9
0x18002d1b3  mov     rdi, qword ptr [rbp+57h+TotalNumberOfFreeBytes]
0x18002d1b7  xor     esi, esi
0x18002d1b9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d1be  test    rsi, rsi
0x18002d1c1  jz      short loc_18002D1DF
0x18002d1c3  call    cs:__imp_GetProcessHeap
0x18002d1c9  lea     r8, [rsi-4]; lpMem
0x18002d1cd  xor     edx, edx; dwFlags
0x18002d1cf  mov     rcx, rax; hHeap
0x18002d1d2  call    cs:__imp_HeapFree
0x18002d1d8  xor     ecx, ecx
0x18002d1da  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d1df  call    cs:__imp_GetLastError
0x18002d1e5  mov     r14d, eax
0x18002d1e8  call    cs:__imp_CurrentIP
0x18002d1ee  mov     r9d, dword ptr [rbp+57h+lpDirectoryName]
0x18002d1f2  lea     rdx, aFailedToDelete_7; "Failed to delete snapshot group %s. hr "...
0x18002d1f9  mov     r8, rdi
0x18002d1fc  mov     ecx, 2000000h; unsigned int
0x18002d201  mov     rsi, rax
0x18002d204  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002d209  mov     dword ptr [rsp+110h+var_C0], 0
0x18002d211  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x18002d218  mov     [rsp+110h+var_C8], 0
0x18002d221  lea     r8, aD_0; "D"
0x18002d228  mov     dword ptr [rsp+110h+var_D0], r14d
0x18002d22d  xor     r9d, r9d
0x18002d230  mov     [rsp+110h+var_D8], rsi
0x18002d235  xor     edx, edx
0x18002d237  mov     [rsp+110h+var_E0], r13
0x18002d23c  mov     [rsp+110h+var_E8], rcx
0x18002d241  mov     rcx, rax
0x18002d244  mov     dword ptr [rsp+110h+ppv], 28Bh
0x18002d24c  call    cs:__imp_WdsSetupLogMessageW
0x18002d252  inc     ebx
0x18002d254  cmp     ebx, dword ptr [rbp+57h+arg_0]
0x18002d257  jb      loc_18002D0B7
0x18002d25d  mov     rbx, [rbp+57h+var_60]
0x18002d261  mov     r13d, dword ptr [rbp+57h+arg_18]
0x18002d265  mov     r15, [rbp+57h+var_58]
0x18002d269  mov     r12, [rbp+57h+var_50]
0x18002d26d  lea     rdx, [rbp+57h+lpDirectoryName]
0x18002d271  mov     [rbp+57h+lpDirectoryName], 0
0x18002d279  lea     rcx, aSystemdriveSys; "%systemdrive%\\System Volume Informatio"...
0x18002d280  mov     qword ptr [rbp+57h+arg_18], 0
0x18002d288  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x18002d28d  mov     r14, [rbp+57h+lpDirectoryName]
0x18002d291  mov     esi, eax
0x18002d293  test    eax, eax
0x18002d295  jns     short loc_18002D2A0
0x18002d297  mov     ecx, eax
0x18002d299  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002d29e  jmp     short loc_18002D2DC
0x18002d2a0  lea     r9, [rbp+57h+arg_18]; lpTotalNumberOfFreeBytes
0x18002d2a4  xor     r8d, r8d; lpTotalNumberOfBytes
0x18002d2a7  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18002d2a9  mov     rcx, r14; lpDirectoryName
0x18002d2ac  call    cs:__imp_GetDiskFreeSpaceExW
0x18002d2b2  test    eax, eax
0x18002d2b4  jnz     short loc_18002D2D8
0x18002d2b6  call    cs:__imp_GetLastError
0x18002d2bc  mov     esi, eax
0x18002d2be  test    eax, eax
0x18002d2c0  jnz     short loc_18002D2C9
0x18002d2c2  mov     esi, 80004005h
0x18002d2c7  jmp     short loc_18002D2D4
0x18002d2c9  jle     short loc_18002D2D4
0x18002d2cb  movzx   esi, ax
0x18002d2ce  or      esi, 80070000h
0x18002d2d4  mov     ecx, esi
0x18002d2d6  jmp     short loc_18002D299
0x18002d2d8  mov     r12, qword ptr [rbp+57h+arg_18]
0x18002d2dc  mov     ecx, esi
0x18002d2de  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d2e3  test    r14, r14
0x18002d2e6  jz      short loc_18002D304
0x18002d2e8  call    cs:__imp_GetProcessHeap
0x18002d2ee  lea     r8, [r14-4]; lpMem
0x18002d2f2  xor     edx, edx; dwFlags
0x18002d2f4  mov     rcx, rax; hHeap
0x18002d2f7  call    cs:__imp_HeapFree
0x18002d2fd  xor     ecx, ecx
0x18002d2ff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d304  mov     rax, [rbp+57h+arg_8]
0x18002d308  mov     dword ptr [rax], 0
0x18002d30e  call    cs:__imp_GetLastError
0x18002d314  mov     r14d, eax
0x18002d317  call    cs:__imp_CurrentIP
0x18002d31d  sub     r12, [rbp+57h+var_68]
0x18002d321  lea     rdx, aSppdeletesnaps_0; "SppDeleteSnapshots reclaimed %dKB space"...
0x18002d328  shr     r12, 0Ah
0x18002d32c  mov     ecx, 4000000h; unsigned int
0x18002d331  mov     r8, r12
0x18002d334  mov     rsi, rax
0x18002d337  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002d33c  mov     dword ptr [rsp+110h+var_C0], 0
0x18002d344  lea     rcx, aCfastdeleteimp_4; "CFastDeleteImplT<class CDirectoryProvid"...
0x18002d34b  mov     [rsp+110h+var_C8], 0
0x18002d354  lea     r8, aD_0; "D"
0x18002d35b  mov     dword ptr [rsp+110h+var_D0], r14d
  ... truncated ...
```
