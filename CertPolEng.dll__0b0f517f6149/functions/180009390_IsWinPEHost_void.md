# IsWinPEHost(void)

- ea: `0x180009390`
- end: `0x18000941d`
- name: `?IsWinPEHost@@YAHXZ`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008950`

## callees

- `0x180009390`
- `0x18000b32c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800093be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800093be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093e7`

## string_xrefs

- `0x1800093d6`: `%s: Successfully opened reg key %s. Assuming the host is WinPE.`
- `0x18000940a`: `%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.`

## pseudocode

```c
__int64 IsWinPEHost(void)
{
  unsigned int v0; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  if ( v0 )
  {
    if ( v0 != 2 )
      Logger::TraceVerbose(
        L"%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.",
        L"IsWinPEHost",
        L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT",
        v0);
    return 0;
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Successfully opened reg key %s. Assuming the host is WinPE.",
      L"IsWinPEHost",
      L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT");
    RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x180009390  sub     rsp, 38h
0x180009394  lea     rax, [rsp+38h+hKey]
0x180009399  mov     [rsp+38h+hKey], 0
0x1800093a2  mov     r9d, 20019h; samDesired
0x1800093a8  mov     [rsp+38h+phkResult], rax; phkResult
0x1800093ad  xor     r8d, r8d; ulOptions
0x1800093b0  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x1800093b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800093be  call    cs:__imp_RegOpenKeyExW
0x1800093c4  test    eax, eax
0x1800093c6  jnz     short loc_1800093F4
0x1800093c8  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x1800093cf  lea     rdx, aIswinpehost; "IsWinPEHost"
0x1800093d6  lea     rcx, aSSuccessfullyO; "%s: Successfully opened reg key %s. Ass"...
0x1800093dd  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800093e2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800093e7  call    cs:__imp_RegCloseKey
0x1800093ed  mov     eax, 1
0x1800093f2  jmp     short loc_180009418
0x1800093f4  cmp     eax, 2
0x1800093f7  jz      short loc_180009416
0x1800093f9  mov     r9d, eax
0x1800093fc  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x180009403  lea     rdx, aIswinpehost; "IsWinPEHost"
0x18000940a  lea     rcx, aSCannotOpenReg_2; "%s: Cannot open reg key %s. Assuming th"...
0x180009411  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180009416  xor     eax, eax
0x180009418  add     rsp, 38h
0x18000941c  retn
```
