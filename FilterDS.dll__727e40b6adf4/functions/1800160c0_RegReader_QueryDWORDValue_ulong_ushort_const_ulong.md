# RegReader::QueryDWORDValue(ulong &,ushort const *,ulong)

- ea: `0x1800160c0`
- end: `0x18001611c`
- name: `?QueryDWORDValue@RegReader@@QEAAJAEAKPEBGK@Z`
- size: `92`
- prototype: `LSTATUS __fastcall(HKEY *this, BYTE *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001094c`
- `0x180015054`

## callees

- `0x1800160c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800160fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800160fb`

## pseudocode

```c
LSTATUS __fastcall RegReader::QueryDWORDValue(HKEY *this, BYTE *a2, const unsigned __int16 *a3, unsigned int a4)
{
  HKEY v4; // rcx
  LSTATUS result; // eax
  DWORD v8[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v9; // [rsp+50h] [rbp+8h] BYREF

  v4 = *this;
  v8[0] = 4;
  v9 = 4;
  result = RegQueryValueExW(v4, a3, 0, v8, a2, &v9);
  if ( result )
  {
    *(_DWORD *)a2 = a4;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800160c0  mov     r11, rsp
0x1800160c3  mov     [r11+10h], rbx
0x1800160c7  push    rdi
0x1800160c8  sub     rsp, 40h
0x1800160cc  mov     rcx, [rcx]; hKey
0x1800160cf  mov     rbx, rdx
0x1800160d2  mov     edx, 4
0x1800160d7  mov     rax, r8
0x1800160da  mov     [rsp+48h+var_18], edx
0x1800160de  mov     edi, r9d
0x1800160e1  mov     [rsp+48h+arg_0], edx
0x1800160e5  lea     r9, [r11-18h]; lpType
0x1800160e9  lea     rdx, [r11+8]
0x1800160ed  xor     r8d, r8d; lpReserved
0x1800160f0  mov     [r11-20h], rdx
0x1800160f4  mov     rdx, rax; lpValueName
0x1800160f7  mov     [r11-28h], rbx
0x1800160fb  call    cs:__imp_RegQueryValueExW
0x180016101  test    eax, eax
0x180016103  jz      short loc_180016111
0x180016105  mov     [rbx], edi
0x180016107  jle     short loc_180016111
0x180016109  movzx   eax, ax
0x18001610c  or      eax, 80070000h
0x180016111  mov     rbx, [rsp+48h+arg_8]
0x180016116  add     rsp, 40h
0x18001611a  pop     rdi
0x18001611b  retn
```
