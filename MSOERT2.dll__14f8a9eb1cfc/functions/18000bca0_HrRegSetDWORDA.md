# HrRegSetDWORDA

- ea: `0x18000bca0`
- end: `0x18000bcd4`
- name: `HrRegSetDWORDA`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000bca0`

## import_xrefs

- `SHLWAPI!SHSetValueA` at `0x18000bcbd`
- `SHLWAPI!SHSetValueA` at `0x18000bcbd`

## pseudocode

```c
LSTATUS __fastcall HrRegSetDWORDA(HKEY a1, const CHAR *a2, const CHAR *a3, int a4)
{
  LSTATUS result; // eax
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  result = SHSetValueA(a1, a2, a3, 4u, &v5, 4u);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000bca0  mov     r11, rsp
0x18000bca3  mov     [r11+20h], r9d
0x18000bca7  sub     rsp, 38h
0x18000bcab  mov     r9d, 4; dwType
0x18000bcb1  lea     rax, [r11+20h]
0x18000bcb5  mov     [r11-10h], r9d
0x18000bcb9  mov     [r11-18h], rax
0x18000bcbd  call    cs:__imp_SHSetValueA
0x18000bcc3  test    eax, eax
0x18000bcc5  jle     short loc_18000BCCF
0x18000bcc7  movzx   eax, ax
0x18000bcca  or      eax, 80070000h
0x18000bccf  add     rsp, 38h
0x18000bcd3  retn
```
