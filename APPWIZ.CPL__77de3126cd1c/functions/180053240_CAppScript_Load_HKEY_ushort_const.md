# CAppScript::Load(HKEY__ *,ushort const *)

- ea: `0x180053240`
- end: `0x18005331a`
- name: `?Load@CAppScript@@QEAAHPEAUHKEY__@@PEBG@Z`
- size: `218`
- prototype: `__int64 __fastcall(unsigned __int16 **this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180053320`

## callees

- `0x180053240`
- `0x180053828`
- `0x18005387c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053271`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053271`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800532ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800532ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800532f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800532f5`

## string_xrefs

- `0x18005329c`: `InstallScript`
- `0x1800532b1`: `UninstallScript`

## pseudocode

```c
__int64 __fastcall CAppScript::Load(unsigned __int16 **this, HKEY hKey, LPCWSTR lpSubKey)
{
  HKEY v4; // rcx
  HKEY hKeya; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  hKeya = 0;
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 1u, &hKeya) )
    return 0;
  RegLoadString(hKeya, L"KeyName", this);
  RegLoadString(hKeya, L"InstallScript", this + 1);
  RegLoadString(hKeya, L"UninstallScript", this + 2);
  cbData = 4;
  RegQueryValueExW(hKeya, L"NeedReboot", 0, 0, (LPBYTE)this + 24, &cbData);
  RegCloseKey(hKeya);
  if ( !*this )
    return 0;
  *((_DWORD *)this + 7) = RegIsKeyExist(v4, *this);
  return 1;
}

```

## disassembly

```asm
0x180053240  push    rbx
0x180053242  sub     rsp, 40h
0x180053246  mov     rbx, rcx
0x180053249  mov     [rsp+48h+hKey], 0
0x180053252  mov     rax, r8
0x180053255  lea     rcx, [rsp+48h+hKey]
0x18005325a  mov     r10, rdx
0x18005325d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180053262  mov     rcx, r10; hKey
0x180053265  mov     r9d, 1; samDesired
0x18005326b  xor     r8d, r8d; ulOptions
0x18005326e  mov     rdx, rax; lpSubKey
0x180053271  call    cs:__imp_RegOpenKeyExW
0x180053277  test    eax, eax
0x180053279  jnz     loc_180053312
0x18005327f  mov     rcx, [rsp+48h+hKey]; hKey
0x180053284  lea     rdx, aKeyname; "KeyName"
0x18005328b  mov     r8, rbx; unsigned __int16 **
0x18005328e  call    ?RegLoadString@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; RegLoadString(HKEY__ *,ushort const *,ushort * *)
0x180053293  mov     rcx, [rsp+48h+hKey]; hKey
0x180053298  lea     r8, [rbx+8]; unsigned __int16 **
0x18005329c  lea     rdx, aInstallscript; "InstallScript"
0x1800532a3  call    ?RegLoadString@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; RegLoadString(HKEY__ *,ushort const *,ushort * *)
0x1800532a8  mov     rcx, [rsp+48h+hKey]; hKey
0x1800532ad  lea     r8, [rbx+10h]; unsigned __int16 **
0x1800532b1  lea     rdx, aUninstallscrip; "UninstallScript"
0x1800532b8  call    ?RegLoadString@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; RegLoadString(HKEY__ *,ushort const *,ushort * *)
0x1800532bd  lea     rcx, [rsp+48h+cbData]
0x1800532c2  mov     [rsp+48h+cbData], 4
0x1800532ca  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x1800532cf  lea     rax, [rbx+18h]
0x1800532d3  mov     rcx, [rsp+48h+hKey]; hKey
0x1800532d8  lea     rdx, aNeedreboot; "NeedReboot"
0x1800532df  xor     r9d, r9d; lpType
0x1800532e2  mov     [rsp+48h+phkResult], rax; lpData
0x1800532e7  xor     r8d, r8d; lpReserved
0x1800532ea  call    cs:__imp_RegQueryValueExW
0x1800532f0  mov     rcx, [rsp+48h+hKey]; hKey
0x1800532f5  call    cs:__imp_RegCloseKey
0x1800532fb  mov     rdx, [rbx]; unsigned __int16 *
0x1800532fe  test    rdx, rdx
0x180053301  jz      short loc_180053312
0x180053303  call    ?RegIsKeyExist@@YAHPEAUHKEY__@@PEBG@Z; RegIsKeyExist(HKEY__ *,ushort const *)
0x180053308  mov     [rbx+1Ch], eax
0x18005330b  mov     eax, 1
0x180053310  jmp     short loc_180053314
0x180053312  xor     eax, eax
0x180053314  add     rsp, 40h
0x180053318  pop     rbx
0x180053319  retn
```
