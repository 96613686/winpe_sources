# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x180005a70`
- end: `0x180005ae3`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `115`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005750`

## callees

- `0x180005a70`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005adb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005adb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005aae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005aae`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::Open(HKEY *this, HKEY a2, const wchar_t *a3)
{
  LSTATUS result; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &phkResult);
  if ( !result )
  {
    if ( *this )
      result = RegCloseKey(*this);
    *this = phkResult;
  }
  return result;
}

```

## disassembly

```asm
0x180005a70  push    rbx
0x180005a72  sub     rsp, 40h
0x180005a76  mov     rax, cs:__security_cookie
0x180005a7d  xor     rax, rsp
0x180005a80  mov     [rsp+48h+var_10], rax
0x180005a85  mov     rbx, rcx
0x180005a88  mov     [rsp+48h+var_18], 0
0x180005a91  lea     rcx, [rsp+48h+var_18]
0x180005a96  mov     rdx, r8; lpSubKey
0x180005a99  mov     [rsp+48h+phkResult], rcx; phkResult
0x180005a9e  mov     r9d, 20019h; samDesired
0x180005aa4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005aab  xor     r8d, r8d; ulOptions
0x180005aae  call    cs:__imp_RegOpenKeyExW
0x180005ab4  test    eax, eax
0x180005ab6  jnz     short loc_180005AC8
0x180005ab8  mov     rcx, [rbx]; hKey
0x180005abb  test    rcx, rcx
0x180005abe  jnz     short loc_180005ADB
0x180005ac0  mov     rcx, [rsp+48h+var_18]
0x180005ac5  mov     [rbx], rcx
0x180005ac8  mov     rcx, [rsp+48h+var_10]
0x180005acd  xor     rcx, rsp; StackCookie
0x180005ad0  call    __security_check_cookie
0x180005ad5  add     rsp, 40h
0x180005ad9  pop     rbx
0x180005ada  retn
0x180005adb  call    cs:__imp_RegCloseKey
0x180005ae1  jmp     short loc_180005AC0
```
