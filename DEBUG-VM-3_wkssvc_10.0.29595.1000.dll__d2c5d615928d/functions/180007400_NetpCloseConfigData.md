# NetpCloseConfigData

- ea: `0x180007400`
- end: `0x18000742c`
- name: `NetpCloseConfigData`
- size: `44`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005dec`
- `0x180006e04`
- `0x1800071d8`
- `0x18002a06c`
- `0x18002abe4`

## callees

- `0x180007400`
- `0x180007604`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007416`

## pseudocode

```c
__int64 __fastcall NetpCloseConfigData(HKEY *a1)
{
  if ( !a1 )
    return 87;
  RegCloseKey(*a1);
  NetpMemoryFree(a1);
  return 0;
}

```

## disassembly

```asm
0x180007400  push    rbx
0x180007402  sub     rsp, 20h
0x180007406  mov     rbx, rcx
0x180007409  test    rcx, rcx
0x18000740c  jnz     short loc_180007413
0x18000740e  lea     eax, [rcx+57h]
0x180007411  jmp     short loc_180007426
0x180007413  mov     rcx, [rcx]; hKey
0x180007416  call    cs:__imp_RegCloseKey
0x18000741c  mov     rcx, rbx
0x18000741f  call    NetpMemoryFree
0x180007424  xor     eax, eax
0x180007426  add     rsp, 20h
0x18000742a  pop     rbx
0x18000742b  retn
```
