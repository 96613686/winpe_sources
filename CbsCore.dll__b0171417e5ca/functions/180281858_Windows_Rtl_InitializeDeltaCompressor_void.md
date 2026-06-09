# Windows::Rtl::InitializeDeltaCompressor(void *)

- ea: `0x180281858`
- end: `0x180281a88`
- name: `?InitializeDeltaCompressor@Rtl@Windows@@YAJPEAX@Z`
- size: `560`
- prototype: `__int64 __fastcall(Windows::Rtl *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c516c`

## callees

- `0x180019bdc`
- `0x18008f280`
- `0x1800eb920`
- `0x180119e78`
- `0x180281858`
- `0x180281ae0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1802818db`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1802818db`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802819a3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802819c4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802819e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180281a06`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180281a27`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180281a48`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802819a3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802819c4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802819e5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180281a06`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180281a27`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180281a48`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180281937`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180281965`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180281937`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180281965`

## string_xrefs

- `0x180281999`: `CreateDeltaB`
- `0x1802818d2`: `UpdateCompression.dll`
- `0x1802818f8`: `UpdateCompression.dll`
- `0x18028195c`: `UpdateCompression.dll`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::InitializeDeltaCompressor(Windows::Rtl *this, void *a2)
{
  int Win32PathOfSiblingFile; // ebx
  HMODULE Library; // rax
  int v5; // eax
  unsigned int v6; // ecx
  __int128 v7; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-20h]
  HMODULE phModule; // [rsp+38h] [rbp-18h] BYREF

  if ( !byte_1803B43E8
    || !hModule
    || !qword_1803B4400
    || !qword_1803B43F8
    || !qword_1803B4408
    || !qword_1803B43D8
    || !qword_1803B43E0
    || !qword_1803B4410 )
  {
    phModule = 0;
    if ( GetModuleHandleExW(0, L"UpdateCompression.dll", &phModule) )
    {
      Library = phModule;
    }
    else
    {
      lpLibFileName = 0;
      v7 = 0;
      Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(&dword_1803AF5CC, L"UpdateCompression.dll", &v7);
      if ( Win32PathOfSiblingFile < 0 )
      {
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v7);
        return ConvertHResultToNtStatus((unsigned int)Win32PathOfSiblingFile);
      }
      phModule = LoadLibraryExW(lpLibFileName, 0, 0);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v7);
      Library = phModule;
      if ( phModule )
        goto LABEL_16;
      Library = LoadLibraryExW(L"UpdateCompression.dll", 0, 0);
      phModule = Library;
    }
    if ( !Library )
    {
      Library = hModule;
      goto LABEL_18;
    }
LABEL_16:
    hModule = Library;
LABEL_18:
    if ( Library )
    {
      qword_1803B4400 = (__int64)GetProcAddress(Library, "CreateDeltaB");
      qword_1803B43F8 = (__int64)GetProcAddress(hModule, "ApplyDeltaB");
      qword_1803B4408 = (__int64)GetProcAddress(hModule, "ApplyDeltaGetReverseB");
      qword_1803B43D8 = (__int64)GetProcAddress(hModule, "GetDeltaInfoExB");
      qword_1803B43E0 = (__int64)GetProcAddress(hModule, "GetDeltaSignatureB");
      qword_1803B4410 = (__int64)GetProcAddress(hModule, "DeltaFree");
    }
    byte_1803B43E8 = 1;
  }
  v5 = anonymous_namespace_::ValidateDeltaBufferCompressorInitialized(this, a2);
  v6 = 0;
  if ( v5 < 0 )
    return (unsigned int)v5;
  return v6;
}

```

## disassembly

```asm
0x180281858  mov     [rsp-8+arg_0], rbx
0x18028185d  push    rbp
0x18028185e  mov     rbp, rsp
0x180281861  sub     rsp, 50h
0x180281865  mov     rax, cs:__security_cookie
0x18028186c  xor     rax, rsp
0x18028186f  mov     [rbp+var_10], rax
0x180281873  cmp     cs:byte_1803B43E8, 0
0x18028187a  jz      short loc_1802818C6
0x18028187c  cmp     cs:hModule, 0
0x180281884  jz      short loc_1802818C6
0x180281886  cmp     cs:qword_1803B4400, 0
0x18028188e  jz      short loc_1802818C6
0x180281890  cmp     cs:qword_1803B43F8, 0
0x180281898  jz      short loc_1802818C6
0x18028189a  cmp     cs:qword_1803B4408, 0
0x1802818a2  jz      short loc_1802818C6
0x1802818a4  cmp     cs:qword_1803B43D8, 0
0x1802818ac  jz      short loc_1802818C6
0x1802818ae  cmp     cs:qword_1803B43E0, 0
0x1802818b6  jz      short loc_1802818C6
0x1802818b8  cmp     cs:qword_1803B4410, 0
0x1802818c0  jnz     loc_180281A62
0x1802818c6  lea     r8, [rbp+phModule]; phModule
0x1802818ca  mov     [rbp+phModule], 0
0x1802818d2  lea     rdx, g_RGWCH_UpdateCompression_dot_dll; "UpdateCompression.dll"
0x1802818d9  xor     ecx, ecx; dwFlags
0x1802818db  call    cs:__imp_GetModuleHandleExW
0x1802818e2  nop     dword ptr [rax+rax+00h]
0x1802818e7  test    eax, eax
0x1802818e9  jnz     loc_180281977
0x1802818ef  xorps   xmm0, xmm0
0x1802818f2  lea     r8, [rbp+var_30]
0x1802818f6  xor     eax, eax
0x1802818f8  lea     rdx, g_RGWCH_UpdateCompression_dot_dll; "UpdateCompression.dll"
0x1802818ff  lea     rcx, dword_1803AF5CC
0x180281906  mov     [rbp+lpLibFileName], rax
0x18028190a  movups  [rbp+var_30], xmm0
0x18028190e  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x180281913  mov     ebx, eax
0x180281915  test    eax, eax
0x180281917  jns     short loc_18028192E
0x180281919  lea     rcx, [rbp+var_30]
0x18028191d  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180281922  mov     ecx, ebx
0x180281924  call    ConvertHResultToNtStatus
0x180281929  jmp     loc_180281A70
0x18028192e  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180281932  xor     r8d, r8d; dwFlags
0x180281935  xor     edx, edx; hFile
0x180281937  call    cs:__imp_LoadLibraryExW
0x18028193e  nop     dword ptr [rax+rax+00h]
0x180281943  lea     rcx, [rbp+var_30]
0x180281947  mov     [rbp+phModule], rax
0x18028194b  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180281950  mov     rax, [rbp+phModule]
0x180281954  test    rax, rax
0x180281957  jnz     short loc_180281980
0x180281959  xor     r8d, r8d; dwFlags
0x18028195c  lea     rcx, g_RGWCH_UpdateCompression_dot_dll; "UpdateCompression.dll"
0x180281963  xor     edx, edx; hFile
0x180281965  call    cs:__imp_LoadLibraryExW
0x18028196c  nop     dword ptr [rax+rax+00h]
0x180281971  mov     [rbp+phModule], rax
0x180281975  jmp     short loc_18028197B
0x180281977  mov     rax, [rbp+phModule]
0x18028197b  test    rax, rax
0x18028197e  jz      short loc_180281989
0x180281980  mov     cs:hModule, rax
0x180281987  jmp     short loc_180281990
0x180281989  mov     rax, cs:hModule
0x180281990  test    rax, rax
0x180281993  jz      loc_180281A5B
0x180281999  lea     rdx, aCreatedeltab; "CreateDeltaB"
0x1802819a0  mov     rcx, rax; hModule
0x1802819a3  call    cs:__imp_GetProcAddress
0x1802819aa  nop     dword ptr [rax+rax+00h]
0x1802819af  mov     rcx, cs:hModule; hModule
0x1802819b6  lea     rdx, aApplydeltab; "ApplyDeltaB"
0x1802819bd  mov     cs:qword_1803B4400, rax
0x1802819c4  call    cs:__imp_GetProcAddress
0x1802819cb  nop     dword ptr [rax+rax+00h]
0x1802819d0  mov     rcx, cs:hModule; hModule
0x1802819d7  lea     rdx, aApplydeltagetr; "ApplyDeltaGetReverseB"
0x1802819de  mov     cs:qword_1803B43F8, rax
0x1802819e5  call    cs:__imp_GetProcAddress
0x1802819ec  nop     dword ptr [rax+rax+00h]
0x1802819f1  mov     rcx, cs:hModule; hModule
0x1802819f8  lea     rdx, aGetdeltainfoex; "GetDeltaInfoExB"
0x1802819ff  mov     cs:qword_1803B4408, rax
0x180281a06  call    cs:__imp_GetProcAddress
0x180281a0d  nop     dword ptr [rax+rax+00h]
0x180281a12  mov     rcx, cs:hModule; hModule
0x180281a19  lea     rdx, aGetdeltasignat; "GetDeltaSignatureB"
0x180281a20  mov     cs:qword_1803B43D8, rax
0x180281a27  call    cs:__imp_GetProcAddress
0x180281a2e  nop     dword ptr [rax+rax+00h]
0x180281a33  mov     rcx, cs:hModule; hModule
0x180281a3a  lea     rdx, aDeltafree; "DeltaFree"
0x180281a41  mov     cs:qword_1803B43E0, rax
0x180281a48  call    cs:__imp_GetProcAddress
0x180281a4f  nop     dword ptr [rax+rax+00h]
0x180281a54  mov     cs:qword_1803B4410, rax
0x180281a5b  mov     cs:byte_1803B43E8, 1
0x180281a62  call    _anonymous_namespace___ValidateDeltaBufferCompressorInitialized
0x180281a67  xor     ecx, ecx
0x180281a69  test    eax, eax
0x180281a6b  cmovs   ecx, eax
0x180281a6e  mov     eax, ecx
0x180281a70  mov     rcx, [rbp+var_10]
0x180281a74  xor     rcx, rsp; StackCookie
0x180281a77  call    __security_check_cookie
0x180281a7c  mov     rbx, [rsp+50h+arg_0]
0x180281a81  add     rsp, 50h
0x180281a85  pop     rbp
0x180281a86  retn
```
