# ShellProgramConfiguration::GetForWindowsEdition<-2147483646>(ushort const *)

- ea: `0x18002e970`
- end: `0x18002e9f8`
- name: `??$GetForWindowsEdition@$0?HPPPPPPO@@ShellProgramConfiguration@@SA?AU0@PEBG@Z`
- size: `136`
- prototype: `PHKEY __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019bd8`

## callees

- `0x18001bbe0`
- `0x18002eb00`
- `0x18002f0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e9d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e9d2`

## pseudocode

```c
PHKEY __fastcall ShellProgramConfiguration::GetForWindowsEdition<-2147483646>(PHKEY phkResult)
{
  bool v2; // cc
  const WCHAR *v3; // rdx
  LPCWSTR lpSubKey[4]; // [rsp+40h] [rbp-38h] BYREF

  wil::str_printf<std::wstring>(lpSubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\%s", L"TabTip");
  v2 = lpSubKey[3] <= (LPCWSTR)7;
  v3 = (const WCHAR *)lpSubKey;
  *phkResult = 0;
  if ( !v2 )
    v3 = lpSubKey[0];
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, phkResult);
  std::wstring::_Tidy_deallocate(lpSubKey);
  return phkResult;
}

```

## disassembly

```asm
0x18002e970  push    rbx
0x18002e972  sub     rsp, 70h
0x18002e976  mov     rax, cs:__security_cookie
0x18002e97d  xor     rax, rsp
0x18002e980  mov     [rsp+78h+var_18], rax
0x18002e985  mov     rbx, rcx
0x18002e988  mov     [rsp+78h+var_40], rcx
0x18002e98d  lea     rcx, [rsp+78h+lpSubKey]
0x18002e992  lea     r8, aTabtip; "TabTip"
0x18002e999  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002e9a0  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x18002e9a5  cmp     [rsp+78h+var_20], 7
0x18002e9ab  lea     rdx, [rsp+78h+lpSubKey]
0x18002e9b0  mov     r9d, 20019h; samDesired
0x18002e9b6  mov     qword ptr [rbx], 0
0x18002e9bd  cmova   rdx, [rsp+78h+lpSubKey]; lpSubKey
0x18002e9c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e9ca  xor     r8d, r8d; ulOptions
0x18002e9cd  mov     [rsp+78h+phkResult], rbx; phkResult
0x18002e9d2  call    cs:__imp_RegOpenKeyExW
0x18002e9d8  lea     rcx, [rsp+78h+lpSubKey]
0x18002e9dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e9e2  mov     rax, rbx
0x18002e9e5  mov     rcx, [rsp+78h+var_18]
0x18002e9ea  xor     rcx, rsp; StackCookie
0x18002e9ed  call    __security_check_cookie
0x18002e9f2  add     rsp, 70h
0x18002e9f6  pop     rbx
0x18002e9f7  retn
```
