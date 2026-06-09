# Accommodation::QueryDWORDValue(ATL::CRegKey &,ushort *,ulong &,ulong)

- ea: `0x1400119d8`
- end: `0x140011a3a`
- name: `?QueryDWORDValue@Accommodation@@CAHAEAVCRegKey@ATL@@PEAGAEAKK@Z`
- size: `98`
- prototype: `__int64 __fastcall(HKEY *, unsigned __int16 *, BYTE *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400116c4`

## callees

- `0x1400119d8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140011a13`
- `ADVAPI32!RegQueryValueExW` at `0x140011a13`

## pseudocode

```c
__int64 __fastcall Accommodation::QueryDWORDValue(HKEY *a1, unsigned __int16 *a2, BYTE *a3, unsigned int a4)
{
  HKEY v4; // rcx
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+20h] BYREF

  *(_DWORD *)a3 = a4;
  v4 = *a1;
  v9 = 0;
  v8 = 4;
  if ( !RegQueryValueExW(v4, a2, 0, &v9, a3, &v8) && v9 == 4 )
    return 1;
  *(_DWORD *)a3 = a4;
  return 0;
}

```

## disassembly

```asm
0x1400119d8  mov     r11, rsp
0x1400119db  mov     [r11+10h], rbx
0x1400119df  push    rdi
0x1400119e0  sub     rsp, 30h
0x1400119e4  mov     [r8], r9d
0x1400119e7  lea     rax, [r11+8]
0x1400119eb  mov     rcx, [rcx]; hKey
0x1400119ee  mov     rbx, r8
0x1400119f1  mov     edi, r9d
0x1400119f4  mov     [r11-10h], rax
0x1400119f8  lea     r9, [r11+20h]; lpType
0x1400119fc  mov     [r11-18h], rbx
0x140011a00  xor     r8d, r8d; lpReserved
0x140011a03  mov     [rsp+38h+arg_18], 0
0x140011a0b  mov     [rsp+38h+arg_0], 4
0x140011a13  call    cs:__imp_RegQueryValueExW
0x140011a19  test    eax, eax
0x140011a1b  jnz     short loc_140011A2B
0x140011a1d  cmp     [rsp+38h+arg_18], 4
0x140011a22  jnz     short loc_140011A2B
0x140011a24  mov     eax, 1
0x140011a29  jmp     short loc_140011A2F
0x140011a2b  mov     [rbx], edi
0x140011a2d  xor     eax, eax
0x140011a2f  mov     rbx, [rsp+38h+arg_8]
0x140011a34  add     rsp, 30h
0x140011a38  pop     rdi
0x140011a39  retn
```
