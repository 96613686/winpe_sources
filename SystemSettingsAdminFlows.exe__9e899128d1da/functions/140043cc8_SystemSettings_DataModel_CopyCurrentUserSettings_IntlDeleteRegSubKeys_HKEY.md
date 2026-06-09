# SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegSubKeys(HKEY__ *)

- ea: `0x140043cc8`
- end: `0x140043d5c`
- name: `?IntlDeleteRegSubKeys@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@@Z`
- size: `148`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400445f0`
- `0x1400446a4`

## callees

- `0x140005f30`
- `0x140043cc8`

## import_xrefs

- `KERNEL32!RegEnumKeyExW` at `0x140043d39`
- `KERNEL32!RegEnumKeyExW` at `0x140043d39`
- `SHLWAPI!SHDeleteKeyW` at `0x140043cf8`
- `SHLWAPI!SHDeleteKeyW` at `0x140043cf8`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegSubKeys(HKEY hKey)
{
  HKEY i; // rbx
  DWORD cchName[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR pszSubKey[256]; // [rsp+50h] [rbp-218h] BYREF

  if ( hKey )
  {
    for ( i = hKey; ; hKey = i )
    {
      cchName[0] = 256;
      if ( RegEnumKeyExW(hKey, 0, pszSubKey, cchName, 0, 0, 0, 0) )
        break;
      SHDeleteKeyW(i, pszSubKey);
    }
  }
}

```

## disassembly

```asm
0x140043cc8  test    rcx, rcx
0x140043ccb  jz      locret_140043D5B
0x140043cd1  push    rbx
0x140043cd2  sub     rsp, 260h
0x140043cd9  mov     rax, cs:__security_cookie
0x140043ce0  xor     rax, rsp
0x140043ce3  mov     [rsp+268h+var_18], rax
0x140043ceb  mov     rbx, rcx
0x140043cee  jmp     short loc_140043D01
0x140043cf0  lea     rdx, [rsp+268h+pszSubKey]; pszSubKey
0x140043cf5  mov     rcx, rbx; hkey
0x140043cf8  call    cs:__imp_SHDeleteKeyW
0x140043cfe  mov     rcx, rbx; hKey
0x140043d01  mov     [rsp+268h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140043d0a  lea     r9, [rsp+268h+cchName]; lpcchName
0x140043d0f  mov     [rsp+268h+lpcchClass], 0; lpcchClass
0x140043d18  lea     r8, [rsp+268h+pszSubKey]; lpName
0x140043d1d  mov     [rsp+268h+lpClass], 0; lpClass
0x140043d26  xor     edx, edx; dwIndex
0x140043d28  mov     [rsp+268h+lpReserved], 0; lpReserved
0x140043d31  mov     [rsp+268h+cchName], 100h
0x140043d39  call    cs:__imp_RegEnumKeyExW
0x140043d3f  test    eax, eax
0x140043d41  jz      short loc_140043CF0
0x140043d43  mov     rcx, [rsp+268h+var_18]
0x140043d4b  xor     rcx, rsp; StackCookie
0x140043d4e  call    __security_check_cookie
0x140043d53  add     rsp, 260h
0x140043d5a  pop     rbx
0x140043d5b  retn
```
