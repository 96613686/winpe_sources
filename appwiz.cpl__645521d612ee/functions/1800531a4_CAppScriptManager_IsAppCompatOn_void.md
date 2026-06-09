# CAppScriptManager::IsAppCompatOn(void)

- ea: `0x1800531a4`
- end: `0x180053237`
- name: `?IsAppCompatOn@CAppScriptManager@@AEAAHXZ`
- size: `147`
- prototype: `__int64 __fastcall(CAppScriptManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053cf0`

## callees

- `0x1800531a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800531df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800531df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053217`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053217`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053229`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053229`

## string_xrefs

- `0x1800531f8`: `TSAppCompat`

## pseudocode

```c
__int64 __fastcall CAppScriptManager::IsAppCompatOn(CAppScriptManager *this)
{
  unsigned int v1; // ebx
  unsigned int Data; // [rsp+40h] [rbp+8h] BYREF
  int v4; // [rsp+44h] [rbp+Ch]
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v4 = HIDWORD(this);
  hKey = 0;
  v1 = 0;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TSAppCompat", 0, 0, (LPBYTE)&Data, &cbData) )
      v1 = Data;
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x1800531a4  mov     rax, rsp
0x1800531a7  mov     [rax+8], rcx
0x1800531ab  push    rbx
0x1800531ac  sub     rsp, 30h
0x1800531b0  mov     qword ptr [rax+18h], 0
0x1800531b8  xor     ebx, ebx
0x1800531ba  mov     dword ptr [rax+8], 0
0x1800531c1  lea     rax, [rax+18h]
0x1800531c5  xor     r8d, r8d; ulOptions
0x1800531c8  mov     [rsp+38h+phkResult], rax; phkResult
0x1800531cd  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x1800531d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800531db  lea     r9d, [rbx+1]; samDesired
0x1800531df  call    cs:__imp_RegOpenKeyExW
0x1800531e5  test    eax, eax
0x1800531e7  jnz     short loc_18005322F
0x1800531e9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800531ee  lea     rax, [rsp+38h+cbData]
0x1800531f3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800531f8  lea     rdx, aTsappcompat; "TSAppCompat"
0x1800531ff  lea     rax, [rsp+38h+Data]
0x180053204  mov     [rsp+38h+cbData], 4
0x18005320c  xor     r9d, r9d; lpType
0x18005320f  mov     [rsp+38h+phkResult], rax; lpData
0x180053214  xor     r8d, r8d; lpReserved
0x180053217  call    cs:__imp_RegQueryValueExW
0x18005321d  mov     rcx, [rsp+38h+hKey]; hKey
0x180053222  test    eax, eax
0x180053224  cmovz   ebx, [rsp+38h+Data]
0x180053229  call    cs:__imp_RegCloseKey
0x18005322f  mov     eax, ebx
0x180053231  add     rsp, 30h
0x180053235  pop     rbx
0x180053236  retn
```
