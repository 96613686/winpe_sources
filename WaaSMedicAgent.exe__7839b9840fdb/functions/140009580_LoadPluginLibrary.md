# LoadPluginLibrary

- ea: `0x140009580`
- end: `0x1400097d6`
- name: `LoadPluginLibrary`
- size: `598`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x14000644c`
- `0x140007f3c`
- `0x140008c64`
- `0x140009580`
- `0x14000b470`
- `0x14000f000`
- `0x14000f160`
- `0x14000f6f4`
- `0x14000f744`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400096e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400096e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400095dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000979f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400097ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400095dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000979f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400097ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400095cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400095cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000962f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000962f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097c5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140009619`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140009619`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400096d2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400096d2`

## string_xrefs

- `0x140009649`: `CreateFile failed wih error: 0x%08x`

## pseudocode

```c
__int64 __fastcall LoadPluginLibrary(__int64 a1, const WCHAR *a2, unsigned __int16 **a3)
{
  int v3; // eax
  unsigned int IsTrustedLibrary; // edi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rbx
  unsigned __int16 *v8; // rdx
  char *FileW; // rsi
  signed int LastError; // eax
  HANDLE v11; // rax
  WaasMedic *v12; // rcx
  HMODULE LibraryW; // rax
  unsigned __int16 **v14; // r8
  int v15; // eax
  const char *v16; // rbp
  const unsigned __int16 *v17; // rcx
  HANDLE v18; // rax
  HANDLE v19; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-48h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID lpMem; // [rsp+80h] [rbp+18h] BYREF

  lpMem = 0;
  v3 = WaasMedic::SafeExpandEnvironmentString(a2, (const unsigned __int16 *)&lpMem, a3);
  IsTrustedLibrary = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\enduser\\waasmedic\\sandbox\\server\\worker.cpp",
      (const char *)(unsigned int)v3,
      dwCreationDisposition);
    v5 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    return IsTrustedLibrary;
  }
  v7 = (WCHAR *)lpMem;
  FileW = (char *)CreateFileW((LPCWSTR)lpMem, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    IsTrustedLibrary = WaasMedic::IsTrustedLibrary(v7, v8);
    if ( (IsTrustedLibrary & 0x80000000) == 0 )
    {
      if ( WaasMedic::IsTestSigningEnabled(v12) )
        LibraryW = LoadLibraryW(v7);
      else
        LibraryW = LoadLibraryExW(v7, 0, 0x880u);
      g_hPluginCollection = LibraryW;
      v15 = WaasMedic::SafeAllocString((WaasMedic *)v7, (const unsigned __int16 *)&g_pszCapsuleName, v14);
      if ( v15 < 0 )
        LogLevelW(3u, L"Failed to allocate string for capsule name: %s.  hr=0x%08x", v7, (unsigned int)v15);
      v16 = (const char *)&SandboxAction::Plugin::init;
      v17 = (const unsigned __int16 *)&SandboxAction::Plugin::init;
      LOBYTE(lpMem) = 0;
      if ( (unsigned __int64)qword_1400208C8 > 7 )
        v17 = (const unsigned __int16 *)SandboxAction::Plugin::init;
      IsTrustedLibrary = ExecuteAction(v17, &dword_1400158BC, (unsigned __int8 *)&lpMem);
      if ( (IsTrustedLibrary & 0x80000000) == 0 )
      {
        if ( v7 )
        {
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v7);
        }
        IsTrustedLibrary = 0;
        goto LABEL_31;
      }
      if ( (unsigned __int64)qword_1400208C8 > 7 )
        v16 = SandboxAction::Plugin::init;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecore\\enduser\\waasmedic\\sandbox\\server\\worker.cpp",
        (const char *)IsTrustedLibrary,
        (int)"%ws failed",
        v16);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\enduser\\waasmedic\\sandbox\\server\\worker.cpp",
        (const char *)IsTrustedLibrary,
        (int)"IsTrustedLibrary failed",
        dwFlagsAndAttributes);
    }
    if ( v7 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v7);
    }
LABEL_31:
    CloseHandle(FileW);
    return IsTrustedLibrary;
  }
  LastError = GetLastError();
  IsTrustedLibrary = LastError;
  if ( LastError > 0 )
    IsTrustedLibrary = (unsigned __int16)LastError | 0x80070000;
  if ( (IsTrustedLibrary & 0x80000000) == 0 )
    IsTrustedLibrary = -2147024786;
  LogLevelW(2u, L"CreateFile failed wih error: 0x%08x", IsTrustedLibrary);
  if ( v7 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v7);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_31;
  return IsTrustedLibrary;
}

```

## disassembly

```asm
0x140009580  mov     rax, rsp
0x140009583  push    rbx
0x140009584  push    rbp
0x140009585  push    rsi
0x140009586  push    rdi
0x140009587  sub     rsp, 48h
0x14000958b  mov     rcx, rdx; lpSrc
0x14000958e  mov     qword ptr [rax+18h], 0
0x140009596  lea     rdx, [rax+18h]; unsigned __int16 *
0x14000959a  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x14000959f  mov     edi, eax
0x1400095a1  test    eax, eax
0x1400095a3  jns     short loc_1400095E8
0x1400095a5  mov     rcx, [rsp+68h]; this
0x1400095aa  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\sandbox\\s"...
0x1400095b1  mov     r9d, eax; char *
0x1400095b4  mov     edx, 95h; void *
0x1400095b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400095be  mov     rbx, [rsp+68h+lpMem]
0x1400095c6  test    rbx, rbx
0x1400095c9  jz      loc_1400097CB
0x1400095cf  call    cs:__imp_GetProcessHeap
0x1400095d5  mov     r8, rbx; lpMem
0x1400095d8  xor     edx, edx; dwFlags
0x1400095da  mov     rcx, rax; hHeap
0x1400095dd  call    cs:__imp_HeapFree
0x1400095e3  jmp     loc_1400097CB
0x1400095e8  mov     rbx, [rsp+68h+lpMem]
0x1400095f0  mov     ebp, 3
0x1400095f5  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1400095fe  xor     r9d, r9d; lpSecurityAttributes
0x140009601  mov     [rsp+68h+dwFlagsAndAttributes], 80h; char *
0x140009609  mov     edx, 80000000h; dwDesiredAccess
0x14000960e  mov     rcx, rbx; lpFileName
0x140009611  mov     [rsp+68h+dwCreationDisposition], ebp; dwCreationDisposition
0x140009615  lea     r8d, [rbp-2]; dwShareMode
0x140009619  call    cs:__imp_CreateFileW
0x14000961f  mov     rsi, rax
0x140009622  lea     rcx, [rax+1]
0x140009626  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14000962d  jnz     short loc_14000968E
0x14000962f  call    cs:__imp_GetLastError
0x140009635  mov     edi, eax
0x140009637  test    eax, eax
0x140009639  jle     short loc_140009644
0x14000963b  movzx   edi, ax
0x14000963e  or      edi, 80070000h
0x140009644  mov     eax, 8007006Eh
0x140009649  lea     rdx, aCreatefileFail; "CreateFile failed wih error: 0x%08x"
0x140009650  test    edi, edi
0x140009652  mov     ecx, 2; unsigned __int8
0x140009657  cmovns  edi, eax
0x14000965a  mov     r8d, edi
0x14000965d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140009662  test    rbx, rbx
0x140009665  jz      short loc_14000967B
0x140009667  call    cs:__imp_GetProcessHeap
0x14000966d  mov     r8, rbx; lpMem
0x140009670  xor     edx, edx; dwFlags
0x140009672  mov     rcx, rax; hHeap
0x140009675  call    cs:__imp_HeapFree
0x14000967b  lea     rcx, [rsi-1]
0x14000967f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140009683  ja      loc_1400097CB
0x140009689  jmp     loc_1400097C2
0x14000968e  mov     rcx, rbx; lpwstrFilename
0x140009691  call    ?IsTrustedLibrary@WaasMedic@@YAJPEAG@Z; WaasMedic::IsTrustedLibrary(ushort *)
0x140009696  mov     edi, eax
0x140009698  test    eax, eax
0x14000969a  jns     short loc_1400096C6
0x14000969c  mov     rcx, [rsp+68h]; this
0x1400096a1  lea     rax, aIstrustedlibra; "IsTrustedLibrary failed"
0x1400096a8  mov     r9d, edi; char *
0x1400096ab  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; int
0x1400096b0  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\sandbox\\s"...
0x1400096b7  mov     edx, 0AAh; void *
0x1400096bc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400096c1  jmp     loc_14000978C
0x1400096c6  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x1400096cb  mov     rcx, rbx; lpLibFileName
0x1400096ce  test    al, al
0x1400096d0  jz      short loc_1400096DA
0x1400096d2  call    cs:__imp_LoadLibraryW
0x1400096d8  jmp     short loc_1400096E8
0x1400096da  xor     edx, edx; hFile
0x1400096dc  mov     r8d, 880h; dwFlags
0x1400096e2  call    cs:__imp_LoadLibraryExW
0x1400096e8  lea     rdx, ?g_pszCapsuleName@@3PEAGEA; unsigned __int16 *
0x1400096ef  mov     cs:?g_hPluginCollection@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hPluginCollection
0x1400096f6  mov     rcx, rbx; this
0x1400096f9  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x1400096fe  test    eax, eax
0x140009700  jns     short loc_140009716
0x140009702  mov     r9d, eax
0x140009705  lea     rdx, aFailedToAlloca_1; "Failed to allocate string for capsule n"...
0x14000970c  mov     r8, rbx
0x14000970f  mov     ecx, ebp; unsigned __int8
0x140009711  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140009716  cmp     cs:qword_1400208C8, 7
0x14000971e  lea     rbp, ?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::init
0x140009725  mov     rcx, rbp
0x140009728  mov     byte ptr [rsp+68h+lpMem], 0
0x140009730  cmova   rcx, cs:?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; unsigned __int16 *
0x140009738  lea     r8, [rsp+68h+lpMem]; unsigned __int8 *
0x140009740  lea     rdx, dword_1400158BC; unsigned __int16 *
0x140009747  call    ?ExecuteAction@@YAJPEBG0PEAE@Z; ExecuteAction(ushort const *,ushort const *,uchar *)
0x14000974c  mov     edi, eax
0x14000974e  test    eax, eax
0x140009750  jns     short loc_1400097A7
0x140009752  cmp     cs:qword_1400208C8, 7
0x14000975a  lea     rax, aWsFailed; "%ws failed"
0x140009761  mov     rcx, [rsp+68h]; this
0x140009766  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\sandbox\\s"...
0x14000976d  cmova   rbp, cs:?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::init
0x140009775  mov     r9d, edi; char *
0x140009778  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbp; char *
0x14000977d  mov     edx, 0BDh; void *
0x140009782  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; int
0x140009787  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000978c  test    rbx, rbx
0x14000978f  jz      short loc_1400097C2
0x140009791  call    cs:__imp_GetProcessHeap
0x140009797  mov     r8, rbx; lpMem
0x14000979a  xor     edx, edx; dwFlags
0x14000979c  mov     rcx, rax; hHeap
0x14000979f  call    cs:__imp_HeapFree
0x1400097a5  jmp     short loc_1400097C2
0x1400097a7  test    rbx, rbx
0x1400097aa  jz      short loc_1400097C0
0x1400097ac  call    cs:__imp_GetProcessHeap
0x1400097b2  mov     r8, rbx; lpMem
0x1400097b5  xor     edx, edx; dwFlags
0x1400097b7  mov     rcx, rax; hHeap
0x1400097ba  call    cs:__imp_HeapFree
0x1400097c0  xor     edi, edi
0x1400097c2  mov     rcx, rsi; hObject
0x1400097c5  call    cs:__imp_CloseHandle
0x1400097cb  mov     eax, edi
0x1400097cd  add     rsp, 48h
0x1400097d1  pop     rdi
0x1400097d2  pop     rsi
0x1400097d3  pop     rbp
0x1400097d4  pop     rbx
0x1400097d5  retn
```
