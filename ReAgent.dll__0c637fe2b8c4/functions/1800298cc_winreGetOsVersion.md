# winreGetOsVersion

- ea: `0x1800298cc`
- end: `0x180029a47`
- name: `winreGetOsVersion`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180018870`

## callees

- `0x1800059fc`
- `0x18000c6f0`
- `0x18000ffcc`
- `0x1800298cc`
- `0x180031e88`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029977`
- `KERNEL32!GetLastError` at `0x180029977`
- `KERNEL32!GetVersionExW` at `0x18002996d`
- `KERNEL32!GetVersionExW` at `0x18002996d`
- `ole32!CoTaskMemFree` at `0x180029a1d`
- `ole32!CoTaskMemFree` at `0x180029a1d`

## string_xrefs

- `0x180029937`: `failed to allocate path`
- `0x180029920`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180029995`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800299df`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800299f6`: `failed to create temporary string`

## pseudocode

```c
__int64 __fastcall winreGetOsVersion(unsigned __int16 **a1)
{
  unsigned int v2; // eax
  unsigned __int16 *v3; // rbx
  __int64 LastError; // rdi
  int v5; // esi
  __int64 v7; // [rsp+28h] [rbp-170h]
  LPVOID pv[2]; // [rsp+30h] [rbp-168h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-158h] BYREF

  memset_0(&VersionInformation, 0, 0x11Cu);
  pv[0] = 0;
  v2 = winreAllocPath(pv);
  v3 = (unsigned __int16 *)pv[0];
  LODWORD(LastError) = v2;
  if ( v2 )
  {
    UnattendLogW(
      2,
      L"winreGetOsVersion %s (0x%x) in file %S line %d",
      L"failed to allocate path",
      v2,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      299);
    goto LABEL_9;
  }
  if ( !(unsigned int)winreGetPrereleaseVersion((LPBYTE)pv[0]) )
    goto LABEL_11;
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
  {
    LastError = GetLastError();
    UnattendLogW(
      2,
      L"winreGetOsVersion %s (0x%x) in file %S line %d",
      L"failed to get version info",
      LastError,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      315);
    goto LABEL_8;
  }
  v5 = StringCchPrintfW(
         v3,
         0x12Eu,
         L"%u.%u.%u.",
         VersionInformation.dwMajorVersion,
         VersionInformation.dwMinorVersion,
         VersionInformation.dwBuildNumber);
  if ( v5 >= 0 )
  {
LABEL_11:
    *a1 = v3;
    return (unsigned int)LastError;
  }
  LODWORD(v7) = 322;
  UnattendLogW(
    2,
    L"winreGetOsVersion %s (0x%x) in file %S line %d",
    L"failed to create temporary string",
    (unsigned int)v5,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    v7);
  LODWORD(LastError) = (unsigned __int16)v5;
LABEL_8:
  if ( !(_DWORD)LastError )
    goto LABEL_11;
LABEL_9:
  if ( v3 )
    CoTaskMemFree(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800298cc  push    rbx
0x1800298ce  push    rsi
0x1800298cf  push    rdi
0x1800298d0  push    r14
0x1800298d2  sub     rsp, 178h
0x1800298d9  mov     rax, cs:__security_cookie
0x1800298e0  xor     rax, rsp
0x1800298e3  mov     [rsp+198h+var_38], rax
0x1800298eb  mov     r14, rcx
0x1800298ee  mov     esi, 11Ch
0x1800298f3  mov     r8d, esi; Size
0x1800298f6  lea     rcx, [rsp+198h+VersionInformation]; void *
0x1800298fb  xor     edx, edx; Val
0x1800298fd  call    memset_0
0x180029902  lea     rcx, [rsp+198h+pv]
0x180029907  mov     [rsp+198h+pv], 0
0x180029910  call    winreAllocPath
0x180029915  mov     rbx, [rsp+198h+pv]
0x18002991a  mov     edi, eax
0x18002991c  test    eax, eax
0x18002991e  jz      short loc_180029954
0x180029920  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180029927  mov     dword ptr [rsp+198h+var_170], 12Bh
0x18002992f  mov     r9d, edi
0x180029932  mov     [rsp+198h+var_178], rax
0x180029937  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002993e  mov     ecx, 2
0x180029943  lea     rdx, aWinregetosvers; "winreGetOsVersion %s (0x%x) in file %S "...
0x18002994a  call    UnattendLogW
0x18002994f  jmp     loc_180029A15
0x180029954  mov     rcx, rbx; lpData
0x180029957  call    winreGetPrereleaseVersion
0x18002995c  test    eax, eax
0x18002995e  jz      loc_180029A25
0x180029964  lea     rcx, [rsp+198h+VersionInformation]; lpVersionInformation
0x180029969  mov     [rsp+198h+VersionInformation.dwOSVersionInfoSize], esi
0x18002996d  call    cs:__imp_GetVersionExW
0x180029973  test    eax, eax
0x180029975  jnz     short loc_1800299B0
0x180029977  call    cs:__imp_GetLastError
0x18002997d  mov     dword ptr [rsp+198h+var_170], 13Bh
0x180029985  lea     r8, aFailedToGetVer; "failed to get version info"
0x18002998c  mov     edi, eax
0x18002998e  lea     rdx, aWinregetosvers; "winreGetOsVersion %s (0x%x) in file %S "...
0x180029995  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002999c  mov     r9d, edi
0x18002999f  mov     ecx, 2
0x1800299a4  mov     [rsp+198h+var_178], rax
0x1800299a9  call    UnattendLogW
0x1800299ae  jmp     short loc_180029A11
0x1800299b0  mov     eax, [rsp+198h+VersionInformation.dwBuildNumber]
0x1800299b4  lea     r8, aUUU; "%u.%u.%u."
0x1800299bb  mov     r9d, [rsp+198h+VersionInformation.dwMajorVersion]
0x1800299c0  mov     edx, 12Eh; unsigned __int64
0x1800299c5  mov     dword ptr [rsp+198h+var_170], eax
0x1800299c9  mov     rcx, rbx; unsigned __int16 *
0x1800299cc  mov     eax, [rsp+198h+VersionInformation.dwMinorVersion]
0x1800299d0  mov     dword ptr [rsp+198h+var_178], eax
0x1800299d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800299d9  mov     esi, eax
0x1800299db  test    eax, eax
0x1800299dd  jns     short loc_180029A25
0x1800299df  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800299e6  mov     dword ptr [rsp+198h+var_170], 142h
0x1800299ee  mov     r9d, esi
0x1800299f1  mov     [rsp+198h+var_178], rax
0x1800299f6  lea     r8, aFailedToCreate; "failed to create temporary string"
0x1800299fd  mov     ecx, 2
0x180029a02  lea     rdx, aWinregetosvers; "winreGetOsVersion %s (0x%x) in file %S "...
0x180029a09  call    UnattendLogW
0x180029a0e  movzx   edi, si
0x180029a11  test    edi, edi
0x180029a13  jz      short loc_180029A25
0x180029a15  test    rbx, rbx
0x180029a18  jz      short loc_180029A28
0x180029a1a  mov     rcx, rbx; pv
0x180029a1d  call    cs:__imp_CoTaskMemFree
0x180029a23  jmp     short loc_180029A28
0x180029a25  mov     [r14], rbx
0x180029a28  mov     eax, edi
0x180029a2a  mov     rcx, [rsp+198h+var_38]
0x180029a32  xor     rcx, rsp; StackCookie
0x180029a35  call    __security_check_cookie
0x180029a3a  add     rsp, 178h
0x180029a41  pop     r14
0x180029a43  pop     rdi
0x180029a44  pop     rsi
0x180029a45  pop     rbx
0x180029a46  retn
```
