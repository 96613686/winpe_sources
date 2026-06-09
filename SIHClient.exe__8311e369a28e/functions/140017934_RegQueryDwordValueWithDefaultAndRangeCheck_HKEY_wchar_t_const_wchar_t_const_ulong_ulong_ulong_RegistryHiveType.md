# RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)

- ea: `0x140017934`
- end: `0x1400179ed`
- name: `?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `28`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003ee0`
- `0x140004174`
- `0x14000423c`
- `0x140004a7c`
- `0x1400052ec`
- `0x140015f20`
- `0x140016108`
- `0x1400167cc`
- `0x140016c54`
- `0x140017020`
- `0x14001bbec`
- `0x14002012c`
- `0x1400241c0`
- `0x140024764`
- `0x1400254e8`
- `0x140025c80`
- `0x14002bc28`
- `0x14002c6e0`
- `0x14002cbd8`
- `0x14002d138`
- `0x140032cc0`
- `0x1400333b4`
- `0x1400338f4`
- `0x140033f60`
- `0x14003401c`
- `0x140038fa4`
- `0x14003b7b8`
- `0x14003e34c`

## callees

- `0x1400176fc`
- `0x1400178a4`
- `0x140017934`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400179d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400179d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001798f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001798f`

## pseudocode

```c
__int64 __fastcall RegQueryDwordValueWithDefaultAndRangeCheck(
        int a1,
        const WCHAR *a2,
        const wchar_t *a3,
        REGSAM a4,
        __int64 a5,
        REGSAM a6)
{
  REGSAM v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  REGSAM samDesired; // [rsp+38h] [rbp-30h] BYREF

  samDesired = 1;
  if ( (int)SetRegistryType(a1, &samDesired) >= 0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey) )
    {
      v9 = a4;
      samDesired = a4;
      if ( hKey )
      {
        if ( RegQueryDwordValue(hKey, a3, &samDesired) < 0 || (v9 = samDesired, samDesired > a6) )
          v9 = a4;
      }
      a4 = v9;
      RegCloseKey(hKey);
    }
  }
  return a4;
}

```

## disassembly

```asm
0x140017934  push    rbx
0x140017936  push    rsi
0x140017937  push    rdi
0x140017938  sub     rsp, 50h
0x14001793c  mov     rax, cs:__security_cookie
0x140017943  xor     rax, rsp
0x140017946  mov     [rsp+68h+var_28], rax
0x14001794b  mov     rsi, rdx
0x14001794e  mov     [rsp+68h+samDesired], 1
0x140017956  lea     rdx, [rsp+68h+samDesired]
0x14001795b  mov     ebx, r9d
0x14001795e  mov     rdi, r8
0x140017961  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x140017966  test    eax, eax
0x140017968  js      short loc_1400179D6
0x14001796a  mov     r9d, [rsp+68h+samDesired]; samDesired
0x14001796f  lea     rax, [rsp+68h+hKey]
0x140017974  xor     r8d, r8d; ulOptions
0x140017977  mov     [rsp+68h+phkResult], rax; phkResult
0x14001797c  mov     rdx, rsi; lpSubKey
0x14001797f  mov     [rsp+68h+hKey], 0
0x140017988  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001798f  call    cs:__imp_RegOpenKeyExW
0x140017995  test    eax, eax
0x140017997  jnz     short loc_1400179D6
0x140017999  mov     rcx, [rsp+68h+hKey]; HKEY
0x14001799e  mov     eax, ebx
0x1400179a0  mov     [rsp+68h+samDesired], ebx
0x1400179a4  test    rcx, rcx
0x1400179a7  jz      short loc_1400179C9
0x1400179a9  lea     r8, [rsp+68h+samDesired]; unsigned int *
0x1400179ae  mov     rdx, rdi; wchar_t *
0x1400179b1  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x1400179b6  test    eax, eax
0x1400179b8  js      short loc_1400179C7
0x1400179ba  mov     eax, [rsp+68h+samDesired]
0x1400179be  cmp     eax, [rsp+68h+arg_28]
0x1400179c5  jbe     short loc_1400179C9
0x1400179c7  mov     eax, ebx
0x1400179c9  mov     rcx, [rsp+68h+hKey]; hKey
0x1400179ce  mov     ebx, eax
0x1400179d0  call    cs:__imp_RegCloseKey
0x1400179d6  mov     eax, ebx
0x1400179d8  mov     rcx, [rsp+68h+var_28]
0x1400179dd  xor     rcx, rsp; StackCookie
0x1400179e0  call    __security_check_cookie
0x1400179e5  add     rsp, 50h
0x1400179e9  pop     rdi
0x1400179ea  pop     rsi
0x1400179eb  pop     rbx
0x1400179ec  retn
```
