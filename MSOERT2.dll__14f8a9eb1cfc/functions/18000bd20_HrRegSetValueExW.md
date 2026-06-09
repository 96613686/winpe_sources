# HrRegSetValueExW

- ea: `0x18000bd20`
- end: `0x18000bd4d`
- name: `HrRegSetValueExW`
- size: `45`
- prototype: `__int64 __fastcall(int, int, int, int, BYTE *, DWORD)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000bd20`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000bd36`
- `ADVAPI32!RegSetValueExW` at `0x18000bd36`

## pseudocode

```c
LSTATUS __fastcall HrRegSetValueExW(HKEY a1, const WCHAR *a2, DWORD a3, DWORD a4, BYTE *lpData, DWORD cbData)
{
  LSTATUS result; // eax

  result = RegSetValueExW(a1, a2, a3, a4, lpData, cbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000bd20  sub     rsp, 38h
0x18000bd24  mov     eax, [rsp+38h+arg_28]
0x18000bd28  mov     [rsp+38h+cbData], eax; cbData
0x18000bd2c  mov     rax, [rsp+38h+arg_20]
0x18000bd31  mov     [rsp+38h+lpData], rax; lpData
0x18000bd36  call    cs:__imp_RegSetValueExW
0x18000bd3c  test    eax, eax
0x18000bd3e  jle     short loc_18000BD48
0x18000bd40  movzx   eax, ax
0x18000bd43  or      eax, 80070000h
0x18000bd48  add     rsp, 38h
0x18000bd4c  retn
```
