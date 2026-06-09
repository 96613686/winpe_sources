# IsWinPEHost(void)

- ea: `0x180086690`
- end: `0x180086722`
- name: `?IsWinPEHost@@YAHXZ`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800898e8`

## callees

- `0x180086690`
- `0x18008aa9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800866c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800866c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800866eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800866eb`

## string_xrefs

- `0x180086709`: `%s: Cannot open reg key %s. Assuming the host is NOT WinPE. RegOpenKeyExW error code: 0x%08x.`
- `0x1800866da`: `%s: Successfully opened reg key %s. Assuming the host is WinPE.`

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
0x180086690  push    rbx
0x180086692  sub     rsp, 30h
0x180086696  lea     rax, [rsp+38h+hKey]
0x18008669b  mov     [rsp+38h+hKey], 0
0x1800866a4  mov     r9d, 20019h; samDesired
0x1800866aa  mov     [rsp+38h+phkResult], rax; phkResult
0x1800866af  xor     r8d, r8d; ulOptions
0x1800866b2  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x1800866b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800866c0  call    cs:__imp_RegOpenKeyExW
0x1800866c6  mov     ebx, eax
0x1800866c8  test    eax, eax
0x1800866ca  jnz     short loc_1800866F3
0x1800866cc  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x1800866d3  lea     rdx, aIswinpehost; "IsWinPEHost"
0x1800866da  lea     rcx, aSSuccessfullyO; "%s: Successfully opened reg key %s. Ass"...
0x1800866e1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800866e6  mov     rcx, [rsp+38h+hKey]; hKey
0x1800866eb  call    cs:__imp_RegCloseKey
0x1800866f1  jmp     short loc_180086715
0x1800866f3  cmp     ebx, 2
0x1800866f6  jz      short loc_180086715
0x1800866f8  mov     r9d, ebx
0x1800866fb  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x180086702  lea     rdx, aIswinpehost; "IsWinPEHost"
0x180086709  lea     rcx, aSCannotOpenReg_3; "%s: Cannot open reg key %s. Assuming th"...
0x180086710  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180086715  xor     eax, eax
0x180086717  test    ebx, ebx
0x180086719  setz    al
0x18008671c  add     rsp, 30h
0x180086720  pop     rbx
0x180086721  retn
```
