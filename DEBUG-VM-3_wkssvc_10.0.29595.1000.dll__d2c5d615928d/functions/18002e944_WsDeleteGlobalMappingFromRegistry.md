# WsDeleteGlobalMappingFromRegistry

- ea: `0x18002e944`
- end: `0x18002e9be`
- name: `WsDeleteGlobalMappingFromRegistry`
- size: `122`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800012a0`
- `0x180001710`

## callees

- `0x18002df2c`
- `0x18002e944`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e982`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e982`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e9ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e9ab`

## pseudocode

```c
__int64 __fastcall WsDeleteGlobalMappingFromRegistry(wint_t *SourceString)
{
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY v5; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v5 = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\NetworkProvider\\GlobalMappings",
         0,
         0x2001Fu,
         &hKey);
  if ( !v2 )
  {
    v2 = FindCreateOrDeleteConnectionKey(hKey, SourceString, 2, &v5);
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x18002e944  mov     r11, rsp
0x18002e947  mov     [r11+8], rbx
0x18002e94b  push    rdi
0x18002e94c  sub     rsp, 30h
0x18002e950  mov     rdi, rcx
0x18002e953  mov     qword ptr [r11+10h], 0
0x18002e95b  lea     rax, [r11+10h]
0x18002e95f  mov     qword ptr [r11+18h], 0
0x18002e967  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e96e  mov     [r11-18h], rax
0x18002e972  mov     r9d, 2001Fh; samDesired
0x18002e978  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x18002e97f  xor     r8d, r8d; ulOptions
0x18002e982  call    cs:__imp_RegOpenKeyExW
0x18002e988  mov     ebx, eax
0x18002e98a  test    eax, eax
0x18002e98c  jnz     short loc_18002E9B1
0x18002e98e  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e993  lea     r9, [rsp+38h+arg_10]
0x18002e998  lea     r8d, [rax+2]
0x18002e99c  mov     rdx, rdi; SourceString
0x18002e99f  call    FindCreateOrDeleteConnectionKey
0x18002e9a4  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e9a9  mov     ebx, eax
0x18002e9ab  call    cs:__imp_RegCloseKey
0x18002e9b1  mov     eax, ebx
0x18002e9b3  mov     rbx, [rsp+38h+arg_0]
0x18002e9b8  add     rsp, 30h
0x18002e9bc  pop     rdi
0x18002e9bd  retn
```
