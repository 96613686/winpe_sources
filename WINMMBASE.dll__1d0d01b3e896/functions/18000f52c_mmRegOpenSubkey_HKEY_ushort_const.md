# mmRegOpenSubkey(HKEY__ *,ushort const *)

- ea: `0x18000f52c`
- end: `0x18000f572`
- name: `?mmRegOpenSubkey@@YAPEAUHKEY__@@PEAU1@PEBG@Z`
- size: `70`
- prototype: `HKEY __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180003460`
- `0x18000c380`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f557`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f557`

## pseudocode

```c
HKEY __fastcall mmRegOpenSubkey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v2; // eax
  HKEY v3; // rdx
  HKEY v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &v5);
  v3 = v5;
  if ( v2 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x18000f52c  mov     r11, rsp
0x18000f52f  mov     [r11+8], rcx
0x18000f533  sub     rsp, 38h
0x18000f537  lea     rax, [r11+8]
0x18000f53b  mov     qword ptr [r11+8], 0
0x18000f543  mov     r9d, 1; samDesired
0x18000f549  mov     [r11-18h], rax
0x18000f54d  xor     r8d, r8d; ulOptions
0x18000f550  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f557  call    cs:__imp_RegOpenKeyExW
0x18000f55d  mov     rdx, [rsp+38h+arg_0]
0x18000f562  xor     ecx, ecx
0x18000f564  test    eax, eax
0x18000f566  cmovnz  rdx, rcx
0x18000f56a  mov     rax, rdx
0x18000f56d  add     rsp, 38h
0x18000f571  retn
```
