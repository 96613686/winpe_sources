# PerflogReadModuleLevel(HINSTANCE__ *)

- ea: `0x18004161c`
- end: `0x18004178b`
- name: `?PerflogReadModuleLevel@@YAXPEAUHINSTANCE__@@@Z`
- size: `367`
- prototype: `void __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180041558`

## callees

- `0x18004161c`
- `0x180041794`
- `0x180074160`
- `0x1800c8220`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800416a8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800416a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004166d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004166d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180041687`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180041687`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041700`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041700`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041740`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041740`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041766`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041766`

## pseudocode

```c
void __fastcall PerflogReadModuleLevel(HINSTANCE a1)
{
  HMODULE ModuleHandleW; // rax
  wchar_t *v2; // rax
  WCHAR *v3; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[1024]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[1024]; // [rsp+850h] [rbp+750h] BYREF

  hKey = 0;
  ModuleHandleW = a1;
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( !a1 )
    ModuleHandleW = GetModuleHandleW(0);
  if ( (GetModuleFileNameW(ModuleHandleW, Filename, 0x400u) & 0xFFFFFBFF) != 0 )
  {
    v2 = wcsrchr(Filename, 0x5Cu);
    v3 = v2 ? v2 + 1 : Filename;
    StringCchPrintfW(SubKey, 0x400u, L"SOFTWARE\\Debug\\%s", v3);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"PERFLOG", 0, &Type, Data, &cbData) && Type == 4 )
        PerflogModuleLevel = *(_DWORD *)Data;
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x18004161c  push    rbp
0x18004161e  lea     rbp, [rsp-0F60h]
0x180041626  mov     eax, 1060h
0x18004162b  call    _alloca_probe
0x180041630  sub     rsp, rax
0x180041633  mov     rax, cs:__security_cookie
0x18004163a  xor     rax, rsp
0x18004163d  mov     [rbp+0F60h+var_10], rax
0x180041644  mov     [rsp+1060h+hKey], 0
0x18004164d  mov     rax, rcx
0x180041650  mov     [rsp+1060h+cbData], 0
0x180041658  mov     [rsp+1060h+Type], 0
0x180041660  mov     dword ptr [rsp+1060h+Data], 0
0x180041668  test    rcx, rcx
0x18004166b  jnz     short loc_180041679
0x18004166d  call    cs:__imp_GetModuleHandleW
0x180041674  nop     dword ptr [rax+rax+00h]
0x180041679  mov     r8d, 400h; nSize
0x18004167f  lea     rdx, [rsp+1060h+Filename]; lpFilename
0x180041684  mov     rcx, rax; hModule
0x180041687  call    cs:__imp_GetModuleFileNameW
0x18004168e  nop     dword ptr [rax+rax+00h]
0x180041693  test    eax, 0FFFFFBFFh
0x180041698  jz      loc_180041772
0x18004169e  mov     edx, 5Ch ; '\'; Ch
0x1800416a3  lea     rcx, [rsp+1060h+Filename]; Str
0x1800416a8  call    cs:__imp_wcsrchr
0x1800416af  nop     dword ptr [rax+rax+00h]
0x1800416b4  test    rax, rax
0x1800416b7  jnz     short loc_1800416C0
0x1800416b9  lea     rax, [rsp+1060h+Filename]
0x1800416be  jmp     short loc_1800416C4
0x1800416c0  add     rax, 2
0x1800416c4  mov     r9, rax
0x1800416c7  lea     r8, aSoftwareDebugS; "SOFTWARE\\Debug\\%s"
0x1800416ce  mov     edx, 400h; unsigned __int64
0x1800416d3  lea     rcx, [rbp+0F60h+SubKey]; Buffer
0x1800416da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800416df  lea     rax, [rsp+1060h+hKey]
0x1800416e4  mov     r9d, 1; samDesired
0x1800416ea  xor     r8d, r8d; ulOptions
0x1800416ed  mov     [rsp+1060h+phkResult], rax; phkResult
0x1800416f2  lea     rdx, [rbp+0F60h+SubKey]; lpSubKey
0x1800416f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041700  call    cs:__imp_RegOpenKeyExW
0x180041707  nop     dword ptr [rax+rax+00h]
0x18004170c  test    eax, eax
0x18004170e  jnz     short loc_180041772
0x180041710  mov     rcx, [rsp+1060h+hKey]; hKey
0x180041715  lea     rax, [rsp+1060h+cbData]
0x18004171a  mov     [rsp+1060h+lpcbData], rax; lpcbData
0x18004171f  lea     r9, [rsp+1060h+Type]; lpType
0x180041724  lea     rax, [rsp+1060h+Data]
0x180041729  mov     [rsp+1060h+cbData], 4
0x180041731  xor     r8d, r8d; lpReserved
0x180041734  mov     [rsp+1060h+phkResult], rax; lpData
0x180041739  lea     rdx, aPerflog; "PERFLOG"
0x180041740  call    cs:__imp_RegQueryValueExW
0x180041747  nop     dword ptr [rax+rax+00h]
0x18004174c  test    eax, eax
0x18004174e  jnz     short loc_180041761
0x180041750  cmp     [rsp+1060h+Type], 4
0x180041755  jnz     short loc_180041761
0x180041757  mov     eax, dword ptr [rsp+1060h+Data]
0x18004175b  mov     cs:?PerflogModuleLevel@@3KA, eax; ulong PerflogModuleLevel
0x180041761  mov     rcx, [rsp+1060h+hKey]; hKey
0x180041766  call    cs:__imp_RegCloseKey
0x18004176d  nop     dword ptr [rax+rax+00h]
0x180041772  mov     rcx, [rbp+0F60h+var_10]
0x180041779  xor     rcx, rsp; StackCookie
0x18004177c  call    __security_check_cookie
0x180041781  add     rsp, 1060h
0x180041788  pop     rbp
0x180041789  retn
```
