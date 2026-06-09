# BasicUiaUtils::IsWinPE(void)

- ea: `0x18007f048`
- end: `0x18007f0b5`
- name: `?IsWinPE@BasicUiaUtils@@SA_NXZ`
- size: `109`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c980`
- `0x18002c958`

## callees

- `0x18007f048`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f09c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f09c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f081`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f081`

## pseudocode

```c
bool BasicUiaUtils::IsWinPE(void)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !BasicUiaUtils::s_isWinPEDetermined )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey) && hKey )
    {
      BasicUiaUtils::s_isWinPE = 1;
      RegCloseKey(hKey);
    }
    BasicUiaUtils::s_isWinPEDetermined = 1;
  }
  return BasicUiaUtils::s_isWinPE;
}

```

## disassembly

```asm
0x18007f048  sub     rsp, 38h
0x18007f04c  mov     al, cs:?s_isWinPEDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isWinPEDetermined
0x18007f052  nop
0x18007f053  test    al, al
0x18007f055  jnz     short loc_18007F0AA
0x18007f057  lea     rax, [rsp+38h+hKey]
0x18007f05c  mov     [rsp+38h+hKey], 0
0x18007f065  mov     r9d, 20019h; samDesired
0x18007f06b  mov     [rsp+38h+phkResult], rax; phkResult
0x18007f070  xor     r8d, r8d; ulOptions
0x18007f073  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x18007f07a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f081  call    cs:__imp_RegOpenKeyExW
0x18007f087  test    eax, eax
0x18007f089  jnz     short loc_18007F0A2
0x18007f08b  mov     rcx, [rsp+38h+hKey]; hKey
0x18007f090  test    rcx, rcx
0x18007f093  jz      short loc_18007F0A2
0x18007f095  mov     cs:?s_isWinPE@BasicUiaUtils@@2_NA, 1; bool BasicUiaUtils::s_isWinPE
0x18007f09c  call    cs:__imp_RegCloseKey
0x18007f0a2  nop
0x18007f0a3  mov     cs:?s_isWinPEDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isWinPEDetermined
0x18007f0aa  mov     al, cs:?s_isWinPE@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isWinPE
0x18007f0b0  add     rsp, 38h
0x18007f0b4  retn
```
