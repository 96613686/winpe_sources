# SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegKeyValues(HKEY__ *)

- ea: `0x140043c2c`
- end: `0x140043cc0`
- name: `?IntlDeleteRegKeyValues@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@@Z`
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
- `0x140043c2c`

## import_xrefs

- `KERNEL32!RegDeleteValueW` at `0x140043c5c`
- `KERNEL32!RegDeleteValueW` at `0x140043c5c`
- `KERNEL32!RegEnumValueW` at `0x140043c9d`
- `KERNEL32!RegEnumValueW` at `0x140043c9d`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlDeleteRegKeyValues(HKEY hKey)
{
  HKEY i; // rbx
  DWORD cchValueName[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR ValueName[256]; // [rsp+50h] [rbp-218h] BYREF

  if ( hKey )
  {
    for ( i = hKey; ; hKey = i )
    {
      cchValueName[0] = 256;
      if ( RegEnumValueW(hKey, 0, ValueName, cchValueName, 0, 0, 0, 0) )
        break;
      RegDeleteValueW(i, ValueName);
    }
  }
}

```

## disassembly

```asm
0x140043c2c  test    rcx, rcx
0x140043c2f  jz      locret_140043CBF
0x140043c35  push    rbx
0x140043c36  sub     rsp, 260h
0x140043c3d  mov     rax, cs:__security_cookie
0x140043c44  xor     rax, rsp
0x140043c47  mov     [rsp+268h+var_18], rax
0x140043c4f  mov     rbx, rcx
0x140043c52  jmp     short loc_140043C65
0x140043c54  lea     rdx, [rsp+268h+ValueName]; lpValueName
0x140043c59  mov     rcx, rbx; hKey
0x140043c5c  call    cs:__imp_RegDeleteValueW
0x140043c62  mov     rcx, rbx; hKey
0x140043c65  mov     [rsp+268h+lpcbData], 0; lpcbData
0x140043c6e  lea     r9, [rsp+268h+cchValueName]; lpcchValueName
0x140043c73  mov     [rsp+268h+lpData], 0; lpData
0x140043c7c  lea     r8, [rsp+268h+ValueName]; lpValueName
0x140043c81  mov     [rsp+268h+lpType], 0; lpType
0x140043c8a  xor     edx, edx; dwIndex
0x140043c8c  mov     [rsp+268h+lpReserved], 0; lpReserved
0x140043c95  mov     [rsp+268h+cchValueName], 100h
0x140043c9d  call    cs:__imp_RegEnumValueW
0x140043ca3  test    eax, eax
0x140043ca5  jz      short loc_140043C54
0x140043ca7  mov     rcx, [rsp+268h+var_18]
0x140043caf  xor     rcx, rsp; StackCookie
0x140043cb2  call    __security_check_cookie
0x140043cb7  add     rsp, 260h
0x140043cbe  pop     rbx
0x140043cbf  retn
```
