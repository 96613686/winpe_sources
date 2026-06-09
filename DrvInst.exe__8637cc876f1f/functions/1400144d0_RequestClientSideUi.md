# RequestClientSideUi

- ea: `0x1400144d0`
- end: `0x1400146da`
- name: `RequestClientSideUi`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140014e08`

## callees

- `0x140009794`
- `0x1400144d0`
- `0x140045eea`
- `0x140045f30`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014639`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014639`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400146ab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400146ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400145b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400145b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014647`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140014547`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140014547`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400145e4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400145e4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400145a8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1400145a8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400145f2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400145f2`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400145d6`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014624`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001466d`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400145d6`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014624`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001466d`

## string_xrefs

- `0x14001456c`: `pnpui.dll`
- `0x14001460e`: `Cannot locate pnpui.dll to display UI. Error = 0x%08X`
- `0x14001462f`: `InstallSecurityPromptLUA`

## pseudocode

```c
__int64 __fastcall RequestClientSideUi(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6, __int64 a7)
{
  UINT SystemDirectoryW; // eax
  DWORD LastError; // ebx
  HANDLE FirstFileW; // rax
  HMODULE LibraryW; // rax
  HMODULE v15; // rdi
  FARPROC ProcAddress; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-6B8h] BYREF
  wchar_t pszDest[264]; // [rsp+290h] [rbp-468h] BYREF
  WCHAR Buffer[264]; // [rsp+4A0h] [rbp-258h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a3 && a6 )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( SystemDirectoryW )
    {
      if ( SystemDirectoryW > 0x104 || StringCchPrintfW(pszDest, 0x104u, L"%ws\\%ws", Buffer, L"pnpui.dll") < 0 )
      {
        return 13;
      }
      else
      {
        FirstFileW = FindFirstFileW(pszDest, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          DevRtlWriteTextLog(a7, 256, 4, "PnpUi not present, proceeding as noninteractive");
        }
        else
        {
          FindClose(FirstFileW);
          LibraryW = LoadLibraryW(pszDest);
          v15 = LibraryW;
          if ( LibraryW )
          {
            ProcAddress = GetProcAddress(LibraryW, "InstallSecurityPromptLUA");
            if ( ProcAddress )
            {
              LastError = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, int, __int64, __int64))ProcAddress)(
                            a1,
                            a2,
                            a3,
                            a4,
                            a5,
                            a6,
                            a7);
            }
            else
            {
              LastError = GetLastError();
              DevRtlWriteTextLog(a7, 256, 1, "Cannot locate function to display UI. Error = 0x%08X", LastError);
            }
            FreeLibrary(v15);
          }
          else
          {
            LastError = GetLastError();
            DevRtlWriteTextLog(a7, 256, 1, "Cannot locate pnpui.dll to display UI. Error = 0x%08X", LastError);
          }
        }
      }
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x1400144d0  push    rbx
0x1400144d2  push    rbp
0x1400144d3  push    rsi
0x1400144d4  push    rdi
0x1400144d5  push    r14
0x1400144d7  push    r15
0x1400144d9  sub     rsp, 6C8h
0x1400144e0  mov     rax, cs:__security_cookie
0x1400144e7  xor     rax, rsp
0x1400144ea  mov     [rsp+6F8h+var_48], rax
0x1400144f2  mov     rsi, [rsp+6F8h+arg_28]
0x1400144fa  mov     rbx, r8
0x1400144fd  mov     r14, rdx
0x140014500  mov     rbp, rcx
0x140014503  xor     edx, edx; Val
0x140014505  lea     rcx, [rsp+6F8h+FindFileData]; void *
0x14001450a  mov     r8d, 250h; Size
0x140014510  mov     r15, r9
0x140014513  call    memset_0
0x140014518  lea     rax, [rbp-1]
0x14001451c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140014520  ja      loc_1400146B3
0x140014526  test    rbx, rbx
0x140014529  jz      loc_1400146B3
0x14001452f  test    rsi, rsi
0x140014532  jz      loc_1400146B3
0x140014538  mov     edi, 104h
0x14001453d  lea     rcx, [rsp+6F8h+Buffer]; lpBuffer
0x140014545  mov     edx, edi; uSize
0x140014547  call    cs:__imp_GetSystemDirectoryW
0x14001454d  test    eax, eax
0x14001454f  jnz     short loc_14001455E
0x140014551  call    cs:__imp_GetLastError
0x140014557  mov     ebx, eax
0x140014559  jmp     loc_1400146B8
0x14001455e  cmp     eax, edi
0x140014560  jbe     short loc_14001456C
0x140014562  mov     ebx, 0Dh
0x140014567  jmp     loc_1400146B8
0x14001456c  lea     rax, aPnpuiDll; "pnpui.dll"
0x140014573  mov     rdx, rdi; cchDest
0x140014576  lea     r9, [rsp+6F8h+Buffer]
0x14001457e  mov     [rsp+6F8h+var_6D8], rax
0x140014583  lea     r8, aWsWs_0; "%ws\\%ws"
0x14001458a  lea     rcx, [rsp+6F8h+pszDest]; pszDest
0x140014592  call    StringCchPrintfW
0x140014597  test    eax, eax
0x140014599  js      short loc_140014562
0x14001459b  lea     rdx, [rsp+6F8h+FindFileData]; lpFindFileData
0x1400145a0  lea     rcx, [rsp+6F8h+pszDest]; lpFileName
0x1400145a8  call    cs:__imp_FindFirstFileW
0x1400145ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400145b2  jnz     short loc_1400145E1
0x1400145b4  call    cs:__imp_GetLastError
0x1400145ba  mov     rcx, [rsp+6F8h+arg_30]
0x1400145c2  lea     r9, aPnpuiNotPresen; "PnpUi not present, proceeding as nonint"...
0x1400145c9  mov     edx, 100h
0x1400145ce  mov     r8d, 4
0x1400145d4  mov     ebx, eax
0x1400145d6  call    cs:__imp_DevRtlWriteTextLog
0x1400145dc  jmp     loc_1400146B8
0x1400145e1  mov     rcx, rax; hFindFile
0x1400145e4  call    cs:__imp_FindClose
0x1400145ea  lea     rcx, [rsp+6F8h+pszDest]; lpLibFileName
0x1400145f2  call    cs:__imp_LoadLibraryW
0x1400145f8  mov     rdi, rax
0x1400145fb  test    rax, rax
0x1400145fe  jnz     short loc_14001462F
0x140014600  call    cs:__imp_GetLastError
0x140014606  mov     rcx, [rsp+6F8h+arg_30]
0x14001460e  lea     r9, aCannotLocatePn; "Cannot locate pnpui.dll to display UI. "...
0x140014615  mov     edx, 100h
0x14001461a  mov     dword ptr [rsp+6F8h+var_6D8], eax
0x14001461e  lea     r8d, [rdi+1]
0x140014622  mov     ebx, eax
0x140014624  call    cs:__imp_DevRtlWriteTextLog
0x14001462a  jmp     loc_1400146B8
0x14001462f  lea     rdx, aInstallsecurit; "InstallSecurityPromptLUA"
0x140014636  mov     rcx, rdi; hModule
0x140014639  call    cs:__imp_GetProcAddress
0x14001463f  mov     r10, rax
0x140014642  test    rax, rax
0x140014645  jnz     short loc_140014675
0x140014647  call    cs:__imp_GetLastError
0x14001464d  mov     rcx, [rsp+6F8h+arg_30]
0x140014655  lea     r9, aCannotLocateFu; "Cannot locate function to display UI. E"...
0x14001465c  mov     edx, 100h
0x140014661  mov     dword ptr [rsp+6F8h+var_6D8], eax
0x140014665  mov     r8d, 1
0x14001466b  mov     ebx, eax
0x14001466d  call    cs:__imp_DevRtlWriteTextLog
0x140014673  jmp     short loc_1400146A8
0x140014675  mov     rax, [rsp+6F8h+arg_30]
0x14001467d  mov     r9, r15
0x140014680  mov     [rsp+6F8h+var_6C8], rax
0x140014685  mov     r8, rbx
0x140014688  mov     eax, [rsp+6F8h+arg_20]
0x14001468f  mov     rdx, r14
0x140014692  mov     [rsp+6F8h+var_6D0], rsi
0x140014697  mov     rcx, rbp
0x14001469a  mov     dword ptr [rsp+6F8h+var_6D8], eax
0x14001469e  mov     rax, r10
0x1400146a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146a6  mov     ebx, eax
0x1400146a8  mov     rcx, rdi; hLibModule
0x1400146ab  call    cs:__imp_FreeLibrary
0x1400146b1  jmp     short loc_1400146B8
0x1400146b3  mov     ebx, 57h ; 'W'
0x1400146b8  mov     eax, ebx
0x1400146ba  mov     rcx, [rsp+6F8h+var_48]
0x1400146c2  xor     rcx, rsp; StackCookie
0x1400146c5  call    __security_check_cookie
0x1400146ca  add     rsp, 6C8h
0x1400146d1  pop     r15
0x1400146d3  pop     r14
0x1400146d5  pop     rdi
0x1400146d6  pop     rsi
0x1400146d7  pop     rbp
0x1400146d8  pop     rbx
0x1400146d9  retn
```
