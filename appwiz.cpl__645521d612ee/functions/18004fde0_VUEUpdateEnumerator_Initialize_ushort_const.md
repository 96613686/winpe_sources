# VUEUpdateEnumerator::Initialize(ushort const *)

- ea: `0x18004fde0`
- end: `0x18004feaa`
- name: `?Initialize@VUEUpdateEnumerator@@QEAAJPEBG@Z`
- size: `202`
- prototype: `__int64 __fastcall(VUEUpdateEnumerator *__hidden this, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012910`

## callees

- `0x18004fda0`
- `0x18004fde0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fe1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fe5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fe1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fe5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fe92`

## string_xrefs

- `0x18004fe02`: `Software\Microsoft\Windows\CurrentVersion\Uninstall\VUE`

## pseudocode

```c
__int64 __fastcall VUEUpdateEnumerator::Initialize(VUEUpdateEnumerator *this, LPCWSTR lpSubKey)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\VUE",
         0,
         0x20019u,
         &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    phkResult = 0;
    v6 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      v5 = VUEUpdateEnumerator::Initialize(this, phkResult);
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004fde0  mov     r11, rsp
0x18004fde3  mov     [r11+8], rbx
0x18004fde7  mov     [r11+10h], rsi
0x18004fdeb  push    rdi
0x18004fdec  sub     rsp, 30h
0x18004fdf0  mov     rsi, rdx
0x18004fdf3  mov     qword ptr [r11+20h], 0
0x18004fdfb  mov     rdi, rcx
0x18004fdfe  lea     rax, [r11+20h]
0x18004fe02  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004fe09  mov     [r11-18h], rax
0x18004fe0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004fe14  mov     r9d, 20019h; samDesired
0x18004fe1a  xor     r8d, r8d; ulOptions
0x18004fe1d  call    cs:__imp_RegOpenKeyExW
0x18004fe23  mov     ebx, eax
0x18004fe25  test    eax, eax
0x18004fe27  jle     short loc_18004FE32
0x18004fe29  movzx   ebx, ax
0x18004fe2c  or      ebx, 80070000h
0x18004fe32  test    ebx, ebx
0x18004fe34  js      short loc_18004FE98
0x18004fe36  mov     rcx, [rsp+38h+hKey]; hKey
0x18004fe3b  lea     rax, [rsp+38h+arg_10]
0x18004fe40  mov     r9d, 20019h; samDesired
0x18004fe46  mov     [rsp+38h+phkResult], rax; phkResult
0x18004fe4b  xor     r8d, r8d; ulOptions
0x18004fe4e  mov     [rsp+38h+arg_10], 0
0x18004fe57  mov     rdx, rsi; lpSubKey
0x18004fe5a  call    cs:__imp_RegOpenKeyExW
0x18004fe60  mov     ebx, eax
0x18004fe62  test    eax, eax
0x18004fe64  jle     short loc_18004FE6F
0x18004fe66  movzx   ebx, ax
0x18004fe69  or      ebx, 80070000h
0x18004fe6f  test    ebx, ebx
0x18004fe71  js      short loc_18004FE8D
0x18004fe73  mov     rdx, [rsp+38h+arg_10]; HKEY
0x18004fe78  mov     rcx, rdi; this
0x18004fe7b  call    ?Initialize@VUEUpdateEnumerator@@QEAAJPEAUHKEY__@@@Z; VUEUpdateEnumerator::Initialize(HKEY__ *)
0x18004fe80  mov     rcx, [rsp+38h+arg_10]; hKey
0x18004fe85  mov     ebx, eax
0x18004fe87  call    cs:__imp_RegCloseKey
0x18004fe8d  mov     rcx, [rsp+38h+hKey]; hKey
0x18004fe92  call    cs:__imp_RegCloseKey
0x18004fe98  mov     rsi, [rsp+38h+arg_8]
0x18004fe9d  mov     eax, ebx
0x18004fe9f  mov     rbx, [rsp+38h+arg_0]
0x18004fea4  add     rsp, 30h
0x18004fea8  pop     rdi
0x18004fea9  retn
```
