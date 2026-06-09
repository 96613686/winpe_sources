# IsWinPEHost(void)

- ea: `0x1800795d8`
- end: `0x18007966a`
- name: `?IsWinPEHost@@YAHXZ`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18007c080`

## callees

- `0x1800795d8`
- `0x18007d22c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079608`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079608`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079633`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079633`

## string_xrefs

- `0x180079622`: `%s: Successfully opened reg key %s. Assuming the host is WinPE.`
- `0x180079651`: `%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.`

## pseudocode

```c
_BOOL8 IsWinPEHost(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 != 2 )
      Logger::TraceVerbose(
        L"%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.",
        L"IsWinPEHost",
        L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT",
        v0);
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Successfully opened reg key %s. Assuming the host is WinPE.",
      L"IsWinPEHost",
      L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT");
    RegCloseKey(hKey);
  }
  return v1 == 0;
}

```

## disassembly

```asm
0x1800795d8  push    rbx
0x1800795da  sub     rsp, 30h
0x1800795de  lea     rax, [rsp+38h+hKey]
0x1800795e3  mov     [rsp+38h+hKey], 0
0x1800795ec  mov     r9d, 20019h; samDesired
0x1800795f2  mov     [rsp+38h+phkResult], rax; phkResult
0x1800795f7  xor     r8d, r8d; ulOptions
0x1800795fa  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x180079601  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180079608  call    cs:__imp_RegOpenKeyExW
0x18007960e  mov     ebx, eax
0x180079610  test    eax, eax
0x180079612  jnz     short loc_18007963B
0x180079614  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18007961b  lea     rdx, aIswinpehost; "IsWinPEHost"
0x180079622  lea     rcx, aSSuccessfullyO; "%s: Successfully opened reg key %s. Ass"...
0x180079629  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007962e  mov     rcx, [rsp+38h+hKey]; hKey
0x180079633  call    cs:__imp_RegCloseKey
0x180079639  jmp     short loc_18007965D
0x18007963b  cmp     ebx, 2
0x18007963e  jz      short loc_18007965D
0x180079640  mov     r9d, ebx
0x180079643  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18007964a  lea     rdx, aIswinpehost; "IsWinPEHost"
0x180079651  lea     rcx, aSCannotOpenReg_3; "%s: Cannot open reg key %s. Assuming th"...
0x180079658  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007965d  xor     eax, eax
0x18007965f  test    ebx, ebx
0x180079661  setz    al
0x180079664  add     rsp, 30h
0x180079668  pop     rbx
0x180079669  retn
```
