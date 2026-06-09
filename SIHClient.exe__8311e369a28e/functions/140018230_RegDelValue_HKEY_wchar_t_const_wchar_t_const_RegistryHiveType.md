# RegDelValue(HKEY__ *,wchar_t const *,wchar_t const *,RegistryHiveType)

- ea: `0x140018230`
- end: `0x1400182f4`
- name: `?RegDelValue@@YAJPEAUHKEY__@@PEB_W1W4RegistryHiveType@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400203ac`

## callees

- `0x1400176fc`
- `0x140018230`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400182cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400182cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018290`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018290`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400182b2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400182b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegDelValue(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  signed int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  REGSAM samDesired; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  samDesired = 2;
  v5 = SetRegistryType(a1, &samDesired);
  if ( v5 >= 0 )
  {
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    if ( v6 )
    {
      v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        return (unsigned int)v6;
    }
    else
    {
      v7 = RegDeleteValueW(hKey, a3);
      if ( v7 )
      {
        v5 = (unsigned __int16)v7 | 0x80070000;
        if ( v7 <= 0 )
          v5 = v7;
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140018230  mov     r11, rsp
0x140018233  mov     [r11+8], rbx
0x140018237  mov     [r11+20h], rsi
0x14001823b  push    rdi
0x14001823c  sub     rsp, 50h
0x140018240  mov     rax, cs:__security_cookie
0x140018247  xor     rax, rsp
0x14001824a  mov     [rsp+58h+var_18], rax
0x14001824f  mov     rsi, rdx
0x140018252  mov     qword ptr [r11-20h], 0
0x14001825a  lea     rdx, [r11-28h]
0x14001825e  mov     [rsp+58h+samDesired], 2
0x140018266  mov     rdi, r8
0x140018269  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x14001826e  mov     ebx, eax
0x140018270  test    eax, eax
0x140018272  js      short loc_1400182D5
0x140018274  mov     r9d, [rsp+58h+samDesired]; samDesired
0x140018279  lea     rax, [rsp+58h+hKey]
0x14001827e  xor     r8d, r8d; ulOptions
0x140018281  mov     [rsp+58h+phkResult], rax; phkResult
0x140018286  mov     rdx, rsi; lpSubKey
0x140018289  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018290  call    cs:__imp_RegOpenKeyExW
0x140018296  test    eax, eax
0x140018298  jz      short loc_1400182AA
0x14001829a  movzx   ebx, ax
0x14001829d  or      ebx, 80070000h
0x1400182a3  test    eax, eax
0x1400182a5  cmovle  ebx, eax
0x1400182a8  jmp     short loc_1400182D5
0x1400182aa  mov     rcx, [rsp+58h+hKey]; hKey
0x1400182af  mov     rdx, rdi; lpValueName
0x1400182b2  call    cs:__imp_RegDeleteValueW
0x1400182b8  test    eax, eax
0x1400182ba  jz      short loc_1400182CA
0x1400182bc  movzx   ebx, ax
0x1400182bf  or      ebx, 80070000h
0x1400182c5  test    eax, eax
0x1400182c7  cmovle  ebx, eax
0x1400182ca  mov     rcx, [rsp+58h+hKey]; hKey
0x1400182cf  call    cs:__imp_RegCloseKey
0x1400182d5  mov     eax, ebx
0x1400182d7  mov     rcx, [rsp+58h+var_18]
0x1400182dc  xor     rcx, rsp; StackCookie
0x1400182df  call    __security_check_cookie
0x1400182e4  mov     rbx, [rsp+58h+arg_0]
0x1400182e9  mov     rsi, [rsp+58h+arg_18]
0x1400182ee  add     rsp, 50h
0x1400182f2  pop     rdi
0x1400182f3  retn
```
