# RawDllMain

- ea: `0x18000f6e0`
- end: `0x18000f7f1`
- name: `RawDllMain`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000e800`
- `0x18000e8e0`
- `0x18000f3b0`
- `0x18000f650`
- `0x18000f6e0`
- `0x180011480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000f710`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000f71d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000f710`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000f71d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000f6fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000f6fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f7b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000f7b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000f79f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000f79f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x18000f700`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x18000f700`
- `KERNEL32!LocalAlloc` at `0x18000f730`
- `KERNEL32!LocalAlloc` at `0x18000f730`
- `KERNEL32!LocalFree` at `0x18000f751`
- `KERNEL32!LocalFree` at `0x18000f751`
- `USER32!MessageBoxA` at `0x18000f7d2`
- `USER32!MessageBoxA` at `0x18000f7d2`

## string_xrefs

- `0x18000f6f3`: `MSVCRT.DLL`
- `0x18000f798`: `MSVCRT.DLL`
- `0x18000f7c9`: `This application or DLL can not be loaded on Windows 95 or on Windows 3.1.  It takes advantage of Unicode features only available on Windows NT.`

## pseudocode

```c
__int64 __fastcall RawDllMain(__int64 a1, int a2)
{
  UINT v2; // eax
  HLOCAL v3; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 Data; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  struct CNoTrackObject *DataNA; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  HMODULE ModuleHandleA; // rax
  __int64 v16; // rbx
  __int64 v17; // [rsp+20h] [rbp-18h] BYREF

  if ( a2 != 1 )
  {
    if ( !a2 )
    {
      DataNA = CThreadLocalObject::GetDataNA((CThreadLocalObject *)&_afxThreadState);
      if ( DataNA )
      {
        v16 = *((_QWORD *)DataNA + 2);
        *(_QWORD *)(CThreadLocal<_AFX_THREAD_STATE>::GetData(v14, v13) + 8) = v16;
      }
      AfxCriticalTerm();
      ModuleHandleA = GetModuleHandleA("MSVCRT.DLL");
      if ( ModuleHandleA )
        FreeLibrary(ModuleHandleA);
      AfxTlsRelease();
    }
    return 1;
  }
  LoadLibraryExA("MSVCRT.DLL", 0, 0x800u);
  if ( (GetVersion() & 0x80000000) != 0 )
  {
    MessageBoxA(
      0,
      "This application or DLL can not be loaded on Windows 95 or on Windows 3.1.  It takes advantage of Unicode features"
      " only available on Windows NT.",
      "MFC Runtime Module",
      0x10u);
    return 0;
  }
  v2 = SetErrorMode(0);
  SetErrorMode(v2 | 0x8001);
  ++_afxTlsRef;
  v3 = LocalAlloc(0, 0x2000u);
  if ( !v3 )
    return 0;
  LocalFree(v3);
  if ( !(unsigned int)AfxCriticalInit() )
    return 0;
  try
  {
    Data = CThreadLocal<_AFX_THREAD_STATE>::GetData(v6, v5);
    v10 = CThreadLocal<_AFX_THREAD_STATE>::GetData(v9, v8);
    v11 = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(v10 + 8) = &off_180127250;
    *(_QWORD *)(Data + 16) = v11;
  }
  catch ( CMemoryException *v17 )
  {
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000f6e0  push    rbx
0x18000f6e2  sub     rsp, 30h
0x18000f6e6  cmp     edx, 1
0x18000f6e9  jnz     short loc_18000F743
0x18000f6eb  xor     edx, edx; hFile
0x18000f6ed  mov     r8d, 800h; dwFlags
0x18000f6f3  lea     rcx, LibFileName; "MSVCRT.DLL"
0x18000f6fa  call    cs:__imp_LoadLibraryExA
0x18000f700  call    cs:__imp_GetVersion
0x18000f706  test    eax, eax
0x18000f708  js      loc_18000F7BC
0x18000f70e  xor     ecx, ecx; uMode
0x18000f710  call    cs:__imp_SetErrorMode
0x18000f716  or      eax, 8001h
0x18000f71b  mov     ecx, eax; uMode
0x18000f71d  call    cs:__imp_SetErrorMode
0x18000f723  inc     cs:?_afxTlsRef@@3JA; long _afxTlsRef
0x18000f729  mov     edx, 2000h; uBytes
0x18000f72e  xor     ecx, ecx; uFlags
0x18000f730  call    cs:__imp_LocalAlloc
0x18000f736  test    rax, rax
0x18000f739  jnz     short loc_18000F74E
0x18000f73b  xor     eax, eax
0x18000f73d  add     rsp, 30h
0x18000f741  pop     rbx
0x18000f742  retn
0x18000f743  test    edx, edx
0x18000f745  jz      short loc_18000F782
0x18000f747  mov     eax, 1
0x18000f74c  jmp     short loc_18000F73D
0x18000f74e  mov     rcx, rax; hMem
0x18000f751  call    cs:__imp_LocalFree
0x18000f757  call    ?AfxCriticalInit@@YAHXZ; AfxCriticalInit(void)
0x18000f75c  test    eax, eax
0x18000f75e  jz      short loc_18000F73B
0x18000f760  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x18000f765  mov     rbx, rax
0x18000f768  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x18000f76d  mov     rcx, [rax+8]
0x18000f771  lea     rdx, off_180127250
0x18000f778  mov     [rax+8], rdx
0x18000f77c  mov     [rbx+10h], rcx
0x18000f780  jmp     short loc_18000F747
0x18000f782  lea     rcx, ?_afxThreadState@@3V?$CThreadLocal@V_AFX_THREAD_STATE@@@@A; this
0x18000f789  call    ?GetDataNA@CThreadLocalObject@@QEAAPEAVCNoTrackObject@@XZ; CThreadLocalObject::GetDataNA(void)
0x18000f78e  test    rax, rax
0x18000f791  jnz     short loc_18000F7E2
0x18000f793  call    ?AfxCriticalTerm@@YAXXZ; AfxCriticalTerm(void)
0x18000f798  lea     rcx, LibFileName; "MSVCRT.DLL"
0x18000f79f  call    cs:__imp_GetModuleHandleA
0x18000f7a5  test    rax, rax
0x18000f7a8  jnz     short loc_18000F7B1
0x18000f7aa  call    ?AfxTlsRelease@@YAXXZ; AfxTlsRelease(void)
0x18000f7af  jmp     short loc_18000F747
0x18000f7b1  mov     rcx, rax; hLibModule
0x18000f7b4  call    cs:__imp_FreeLibrary
0x18000f7ba  jmp     short loc_18000F7AA
0x18000f7bc  mov     r9d, 10h; uType
0x18000f7c2  lea     r8, Caption; "MFC Runtime Module"
0x18000f7c9  lea     rdx, Text; "This application or DLL can not be load"...
0x18000f7d0  xor     ecx, ecx; hWnd
0x18000f7d2  call    cs:__imp_MessageBoxA
0x18000f7d8  jmp     loc_18000F73B
0x18000f7dd  jmp     loc_18000F73B
0x18000f7e2  mov     rbx, [rax+10h]
0x18000f7e6  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x18000f7eb  mov     [rax+8], rbx
0x18000f7ef  jmp     short loc_18000F793
```
