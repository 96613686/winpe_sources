# HrRegSetDWORDW

- ea: `0x18000bce0`
- end: `0x18000bd14`
- name: `HrRegSetDWORDW`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000bce0`

## import_xrefs

- `SHLWAPI!SHSetValueW` at `0x18000bcfd`
- `SHLWAPI!SHSetValueW` at `0x18000bcfd`

## pseudocode

```c
LSTATUS __fastcall HrRegSetDWORDW(HKEY a1, const WCHAR *a2, const WCHAR *a3, int a4)
{
  LSTATUS result; // eax
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  result = SHSetValueW(a1, a2, a3, 4u, &v5, 4u);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000bce0  mov     r11, rsp
0x18000bce3  mov     [r11+20h], r9d
0x18000bce7  sub     rsp, 38h
0x18000bceb  mov     r9d, 4; dwType
0x18000bcf1  lea     rax, [r11+20h]
0x18000bcf5  mov     [r11-10h], r9d
0x18000bcf9  mov     [r11-18h], rax
0x18000bcfd  call    cs:__imp_SHSetValueW
0x18000bd03  test    eax, eax
0x18000bd05  jle     short loc_18000BD0F
0x18000bd07  movzx   eax, ax
0x18000bd0a  or      eax, 80070000h
0x18000bd0f  add     rsp, 38h
0x18000bd13  retn
```
