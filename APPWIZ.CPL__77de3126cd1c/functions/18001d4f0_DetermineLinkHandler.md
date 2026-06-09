# DetermineLinkHandler

- ea: `0x18001d4f0`
- end: `0x18001d661`
- name: `DetermineLinkHandler`
- size: `369`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned __int16 *@<rdx>, int, LPWSTR, int, __int64, int, __int64, __int64, struct INewShortcutHookW **, struct INewShortcutHookA **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c5cc`
- `0x18002dd80`

## callees

- `0x18001c984`
- `0x18001d4f0`
- `0x1800582e0`

## import_xrefs

- `SHELL32!__imp_SHCLSIDFromString` at `0x18001d5a5`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18001d5a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d584`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d584`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001d621`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001d621`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d634`

## pseudocode

```c
LSTATUS __fastcall DetermineLinkHandler(
        unsigned int a1,
        unsigned __int16 *a2,
        __int64 a3,
        const WCHAR *a4,
        int a5,
        LPWSTR a6,
        int a7,
        unsigned __int16 *a8,
        int a9,
        const WCHAR *a10,
        HWND a11,
        struct INewShortcutHookW **a12,
        struct INewShortcutHookA **a13)
{
  DWORD v13; // ebx
  LSTATUS result; // eax
  DWORD i; // edx
  unsigned int v19; // r9d
  unsigned int lpType; // [rsp+28h] [rbp-D8h]
  unsigned int lpcbData; // [rsp+38h] [rbp-C8h]
  unsigned int v22; // [rsp+48h] [rbp-B8h]
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HWND v25; // [rsp+80h] [rbp-80h]
  LPCWCH lpWideCharStr; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v27; // [rsp+90h] [rbp-70h]
  CLSID pclsid; // [rsp+98h] [rbp-68h] BYREF
  WCHAR psz[40]; // [rsp+B0h] [rbp-50h] BYREF

  v13 = 0;
  v27 = a8;
  lpWideCharStr = a10;
  v25 = a11;
  *a12 = 0;
  hKey = 0;
  *a13 = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\NewShortcutHandlers",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    for ( i = 0; ; i = v13 )
    {
      cchValueName = 39;
      if ( RegEnumValueW(hKey, i, psz, &cchValueName, 0, 0, 0, 0) )
        break;
      pclsid = 0;
      if ( !SHCLSIDFromString(psz, &pclsid)
        && !(unsigned int)QueryNewLinkHandler(
                            &pclsid,
                            a1,
                            a2,
                            v19,
                            a4,
                            lpType,
                            a6,
                            lpcbData,
                            v27,
                            v22,
                            lpWideCharStr,
                            v25,
                            a12,
                            a13) )
      {
        break;
      }
      ++v13;
    }
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18001d4f0  mov     [rsp-8+arg_10], rbx
0x18001d4f5  push    rbp
0x18001d4f6  push    rsi
0x18001d4f7  push    rdi
0x18001d4f8  push    r12
0x18001d4fa  push    r13
0x18001d4fc  push    r14
0x18001d4fe  push    r15
0x18001d500  lea     rbp, [rsp-10h]
0x18001d505  sub     rsp, 110h
0x18001d50c  mov     rax, cs:__security_cookie
0x18001d513  xor     rax, rsp
0x18001d516  mov     [rbp+40h+var_40], rax
0x18001d51a  mov     rax, [rbp+40h+arg_38]
0x18001d521  xor     ebx, ebx
0x18001d523  mov     rdi, [rbp+40h+arg_58]
0x18001d52a  mov     r12, r9
0x18001d52d  mov     rsi, [rbp+40h+arg_60]
0x18001d534  mov     r15, rdx
0x18001d537  mov     r13, [rbp+40h+arg_28]
0x18001d53b  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001d542  mov     [rbp+40h+var_B0], rax
0x18001d546  mov     r14d, ecx
0x18001d549  mov     rax, [rbp+40h+arg_48]
0x18001d550  mov     r9d, 20019h; samDesired
0x18001d556  mov     [rbp+40h+var_B8], rax
0x18001d55a  xor     r8d, r8d; ulOptions
0x18001d55d  mov     rax, [rbp+40h+arg_50]
0x18001d564  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d56b  mov     [rbp+40h+var_C0], rax
0x18001d56f  lea     rax, [rsp+140h+hKey]
0x18001d574  mov     [rdi], rbx
0x18001d577  mov     [rsp+140h+phkResult], rax; phkResult
0x18001d57c  mov     [rsp+140h+hKey], rbx
0x18001d581  mov     [rsi], rbx
0x18001d584  call    cs:__imp_RegOpenKeyExW
0x18001d58a  test    eax, eax
0x18001d58c  jnz     loc_18001D63A
0x18001d592  xor     edx, edx
0x18001d594  jmp     short loc_18001D5F5
0x18001d596  xorps   xmm0, xmm0
0x18001d599  lea     rdx, [rbp+40h+pclsid]; pclsid
0x18001d59d  lea     rcx, [rbp+40h+psz]; psz
0x18001d5a1  movups  xmmword ptr [rbp+40h+pclsid.Data1], xmm0
0x18001d5a5  call    cs:__imp_SHCLSIDFromString
0x18001d5ab  test    eax, eax
0x18001d5ad  jnz     short loc_18001D5F1
0x18001d5af  mov     rax, [rbp+40h+var_C0]
0x18001d5b3  lea     rcx, [rbp+40h+pclsid]; struct _GUID *
0x18001d5b7  mov     [rsp+140h+var_D8], rsi; struct INewShortcutHookA **
0x18001d5bc  mov     r8, r15; unsigned __int16 *
0x18001d5bf  mov     [rsp+140h+var_E0], rdi; struct INewShortcutHookW **
0x18001d5c4  mov     edx, r14d; unsigned int
0x18001d5c7  mov     [rsp+140h+var_E8], rax; HWND
0x18001d5cc  mov     rax, [rbp+40h+var_B8]
0x18001d5d0  mov     [rsp+140h+lpWideCharStr], rax; lpWideCharStr
0x18001d5d5  mov     rax, [rbp+40h+var_B0]
0x18001d5d9  mov     [rsp+140h+var_100], rax; unsigned __int16 *
0x18001d5de  mov     [rsp+140h+lpData], r13; LPWSTR
0x18001d5e3  mov     [rsp+140h+phkResult], r12; LPCWCH
0x18001d5e8  call    ?QueryNewLinkHandler@@YAJPEBU_GUID@@KPEAGK1K1K1K1PEAUHWND__@@PEAPEAUINewShortcutHookW@@PEAPEAUINewShortcutHookA@@@Z; QueryNewLinkHandler(_GUID const *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,HWND__ *,INewShortcutHookW * *,INewShortcutHookA * *)
0x18001d5ed  test    eax, eax
0x18001d5ef  jz      short loc_18001D62F
0x18001d5f1  inc     ebx
0x18001d5f3  mov     edx, ebx; dwIndex
0x18001d5f5  mov     rcx, [rsp+140h+hKey]; hKey
0x18001d5fa  lea     r9, [rsp+140h+cchValueName]; lpcchValueName
0x18001d5ff  xor     eax, eax
0x18001d601  mov     [rsp+140h+cchValueName], 27h ; '''
0x18001d609  mov     [rsp+140h+lpcbData], rax; unsigned int
0x18001d60e  lea     r8, [rbp+40h+psz]; lpValueName
0x18001d612  mov     [rsp+140h+lpData], rax; lpData
0x18001d617  mov     [rsp+140h+lpType], rax; unsigned int
0x18001d61c  mov     [rsp+140h+phkResult], rax; lpReserved
0x18001d621  call    cs:__imp_RegEnumValueW
0x18001d627  test    eax, eax
0x18001d629  jz      loc_18001D596
0x18001d62f  mov     rcx, [rsp+140h+hKey]; hKey
0x18001d634  call    cs:__imp_RegCloseKey
0x18001d63a  mov     rcx, [rbp+40h+var_40]
0x18001d63e  xor     rcx, rsp; StackCookie
0x18001d641  call    __security_check_cookie
0x18001d646  mov     rbx, [rsp+140h+arg_10]
0x18001d64e  add     rsp, 110h
0x18001d655  pop     r15
0x18001d657  pop     r14
0x18001d659  pop     r13
0x18001d65b  pop     r12
0x18001d65d  pop     rdi
0x18001d65e  pop     rsi
0x18001d65f  pop     rbp
0x18001d660  retn
```
