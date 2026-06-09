# CARPUninstallStringLauncher::RemoveBrokenItemFromInstalledProgramsList(int,ushort const *)

- ea: `0x18001bfc0`
- end: `0x18001c039`
- name: `?RemoveBrokenItemFromInstalledProgramsList@CARPUninstallStringLauncher@@UEAAJHPEBG@Z`
- size: `121`
- prototype: `__int64 __fastcall(CARPUninstallStringLauncher *this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001bfc0`

## import_xrefs

- `SHCORE!SHDeleteKeyW` at `0x18001c015`
- `SHCORE!SHDeleteKeyW` at `0x18001c015`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c003`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c026`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c026`

## string_xrefs

- `0x18001bfe7`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c
__int64 __fastcall CARPUninstallStringLauncher::RemoveBrokenItemFromInstalledProgramsList(
        CARPUninstallStringLauncher *this,
        int a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // ebx
  HKEY hkey; // [rsp+58h] [rbp+20h] BYREF

  hkey = 0;
  v4 = -2147467259;
  if ( !RegOpenKeyExW(
          (HKEY)((a2 != 0) - 0x7FFFFFFFLL),
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall",
          0,
          0x20006u,
          &hkey) )
  {
    v4 = SHDeleteKeyW(hkey, a3) != 0 ? 0x80004005 : 0;
    RegCloseKey(hkey);
  }
  return v4;
}

```

## disassembly

```asm
0x18001bfc0  mov     r11, rsp
0x18001bfc3  mov     [r11+8], rbx
0x18001bfc7  push    rdi
0x18001bfc8  sub     rsp, 30h
0x18001bfcc  neg     edx
0x18001bfce  mov     qword ptr [r11+20h], 0
0x18001bfd6  mov     rdi, r8
0x18001bfd9  lea     rax, [r11+20h]
0x18001bfdd  sbb     rcx, rcx
0x18001bfe0  mov     [r11-18h], rax
0x18001bfe4  neg     rcx
0x18001bfe7  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001bfee  add     rcx, 0FFFFFFFF80000001h; hKey
0x18001bff5  mov     r9d, 20006h; samDesired
0x18001bffb  xor     r8d, r8d; ulOptions
0x18001bffe  mov     ebx, 80004005h
0x18001c003  call    cs:__imp_RegOpenKeyExW
0x18001c009  test    eax, eax
0x18001c00b  jnz     short loc_18001C02C
0x18001c00d  mov     rcx, [rsp+38h+hkey]; hkey
0x18001c012  mov     rdx, rdi; pszSubKey
0x18001c015  call    cs:__imp_SHDeleteKeyW
0x18001c01b  neg     eax
0x18001c01d  sbb     ecx, ecx
0x18001c01f  and     ebx, ecx
0x18001c021  mov     rcx, [rsp+38h+hkey]; hKey
0x18001c026  call    cs:__imp_RegCloseKey
0x18001c02c  mov     eax, ebx
0x18001c02e  mov     rbx, [rsp+38h+arg_0]
0x18001c033  add     rsp, 30h
0x18001c037  pop     rdi
0x18001c038  retn
```
