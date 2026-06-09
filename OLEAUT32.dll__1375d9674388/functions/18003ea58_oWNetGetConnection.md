# oWNetGetConnection

- ea: `0x18003ea58`
- end: `0x18003eb81`
- name: `oWNetGetConnection`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003e788`

## callees

- `0x18003ea58`
- `0x18004d900`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003eaf1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003eaf1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003eada`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003eada`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003eb02`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003eb02`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003eb3e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003eb3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eb25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eb25`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18003ea9c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18003ea9c`

## string_xrefs

- `0x18003eae0`: `mpr.dll`

## pseudocode

```c
__int64 __fastcall oWNetGetConnection(WCHAR *a1, __int64 a2, __int64 a3)
{
  UINT DriveTypeW; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  WCHAR RootPathName[2]; // [rsp+20h] [rbp-258h] BYREF
  int v11; // [rsp+24h] [rbp-254h]
  WCHAR LibFileName[272]; // [rsp+30h] [rbp-248h] BYREF

  RootPathName[0] = *a1;
  RootPathName[1] = a1[1];
  v11 = 92;
  DriveTypeW = GetDriveTypeW(RootPathName);
  if ( DriveTypeW != 4 && DriveTypeW > 1 && DriveTypeW < 7 )
    return 2250;
  if ( g_hinstMPRDLL )
  {
    ProcAddress = (FARPROC)g_pWNetGetConnection;
  }
  else
  {
    _o_wcscpy_s(LibFileName, 268, &g_rcSystemDirectory);
    _o_wcscat_s(LibFileName, 268, L"mpr.dll");
    Library = LoadLibraryExW(LibFileName, 0, 8u);
    g_hinstMPRDLL = Library;
    if ( !Library )
      return 1222;
    ProcAddress = GetProcAddress(Library, "WNetGetConnectionW");
    g_pWNetGetConnection = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      FreeLibrary(g_hinstMPRDLL);
      g_hinstMPRDLL = 0;
      return 1222;
    }
  }
  return ((__int64 (__fastcall *)(WCHAR *, __int64, __int64))ProcAddress)(a1, a2, a3);
}

```

## disassembly

```asm
0x18003ea58  push    rbx
0x18003ea5a  push    rsi
0x18003ea5b  push    rdi
0x18003ea5c  sub     rsp, 260h
0x18003ea63  mov     rax, cs:__security_cookie
0x18003ea6a  xor     rax, rsp
0x18003ea6d  mov     [rsp+278h+var_28], rax
0x18003ea75  movzx   eax, word ptr [rcx]
0x18003ea78  mov     rbx, rcx
0x18003ea7b  mov     [rsp+278h+RootPathName], ax
0x18003ea80  mov     rsi, r8
0x18003ea83  movzx   eax, word ptr [rcx+2]
0x18003ea87  mov     rdi, rdx
0x18003ea8a  lea     rcx, [rsp+278h+RootPathName]; lpRootPathName
0x18003ea8f  mov     [rsp+278h+var_256], ax
0x18003ea94  mov     [rsp+278h+var_254], 5Ch ; '\'
0x18003ea9c  call    cs:__imp_GetDriveTypeW
0x18003eaa2  cmp     eax, 4
0x18003eaa5  jz      short loc_18003EABB
0x18003eaa7  cmp     eax, 1
0x18003eaaa  jbe     short loc_18003EABB
0x18003eaac  cmp     eax, 7
0x18003eaaf  jnb     short loc_18003EABB
0x18003eab1  mov     eax, 8CAh
0x18003eab6  jmp     loc_18003EB66
0x18003eabb  cmp     cs:g_hinstMPRDLL, 0
0x18003eac3  jnz     loc_18003EB51
0x18003eac9  lea     r8, g_rcSystemDirectory
0x18003ead0  mov     edx, 10Ch
0x18003ead5  lea     rcx, [rsp+278h+LibFileName]
0x18003eada  call    cs:__imp__o_wcscpy_s
0x18003eae0  lea     r8, aMprDll; "mpr.dll"
0x18003eae7  mov     edx, 10Ch
0x18003eaec  lea     rcx, [rsp+278h+LibFileName]
0x18003eaf1  call    cs:__imp__o_wcscat_s
0x18003eaf7  xor     edx, edx; hFile
0x18003eaf9  lea     rcx, [rsp+278h+LibFileName]; lpLibFileName
0x18003eafe  lea     r8d, [rdx+8]; dwFlags
0x18003eb02  call    cs:__imp_LoadLibraryExW
0x18003eb08  mov     cs:g_hinstMPRDLL, rax
0x18003eb0f  test    rax, rax
0x18003eb12  jnz     short loc_18003EB1B
0x18003eb14  mov     eax, 4C6h
0x18003eb19  jmp     short loc_18003EB66
0x18003eb1b  lea     rdx, aWnetgetconnect; "WNetGetConnectionW"
0x18003eb22  mov     rcx, rax; hModule
0x18003eb25  call    cs:__imp_GetProcAddress
0x18003eb2b  mov     cs:g_pWNetGetConnection, rax
0x18003eb32  test    rax, rax
0x18003eb35  jnz     short loc_18003EB58
0x18003eb37  mov     rcx, cs:g_hinstMPRDLL; hLibModule
0x18003eb3e  call    cs:__imp_FreeLibrary
0x18003eb44  mov     cs:g_hinstMPRDLL, 0
0x18003eb4f  jmp     short loc_18003EB14
0x18003eb51  mov     rax, cs:g_pWNetGetConnection
0x18003eb58  mov     r8, rsi
0x18003eb5b  mov     rdx, rdi
0x18003eb5e  mov     rcx, rbx
0x18003eb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb66  mov     rcx, [rsp+278h+var_28]
0x18003eb6e  xor     rcx, rsp; StackCookie
0x18003eb71  call    __security_check_cookie
0x18003eb76  add     rsp, 260h
0x18003eb7d  pop     rdi
0x18003eb7e  pop     rsi
0x18003eb7f  pop     rbx
0x18003eb80  retn
```
