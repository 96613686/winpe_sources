# sub_1801FCCA4

- ea: `0x1801fcca4`
- end: `0x1801fcd3d`
- name: `sub_1801FCCA4`
- size: `153`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180273af0`
- `0x180273b70`
- `0x180273d50`
- `0x180273da0`
- `0x180273f90`
- `0x180274370`

## callees

- `0x180002b7c`
- `0x1800daa88`
- `0x18013e6f8`
- `0x18013e9e0`
- `0x18013ea4c`
- `0x1801fcca4`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801fcd1a`
- `KERNEL32!CompareStringW` at `0x1801fcd1a`

## pseudocode

```c
bool __fastcall sub_1801FCCA4(__int64 a1)
{
  const WCHAR *lpString2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rax
  bool v5; // bl
  char v7; // [rsp+48h] [rbp+10h] BYREF

  sub_18013E9E0((__int64)&v7, L"ByLayer");
  if ( (unsigned __int8)sub_1800DAA88(&v7) )
    sub_18013E6F8(&v7);
  lpString2 = *(const WCHAR **)(sub_180002B7C(&v7) + 16);
  if ( (unsigned __int8)sub_1800DAA88(a1) )
    sub_18013E6F8(v3);
  v4 = sub_180002B7C(a1);
  v5 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v4 + 16), -1, lpString2, -1) == 2;
  sub_18013EA4C(&v7);
  return v5;
}

```

## disassembly

```asm
0x1801fcca4  mov     [rsp+arg_0], rbx
0x1801fcca9  push    rdi
0x1801fccaa  sub     rsp, 30h
0x1801fccae  mov     rbx, rcx
0x1801fccb1  lea     rdx, aBylayer_0; "ByLayer"
0x1801fccb8  lea     rcx, [rsp+38h+arg_8]
0x1801fccbd  call    sub_18013E9E0
0x1801fccc2  lea     rcx, [rsp+38h+arg_8]
0x1801fccc7  call    sub_1800DAA88
0x1801fcccc  test    al, al
0x1801fccce  jz      short loc_1801FCCDA
0x1801fccd0  lea     rcx, [rsp+38h+arg_8]
0x1801fccd5  call    sub_18013E6F8
0x1801fccda  lea     rcx, [rsp+38h+arg_8]
0x1801fccdf  call    sub_180002B7C
0x1801fcce4  mov     rdi, [rax+10h]
0x1801fcce8  mov     rcx, rbx
0x1801fcceb  call    sub_1800DAA88
0x1801fccf0  test    al, al
0x1801fccf2  jz      short loc_1801FCCF9
0x1801fccf4  call    sub_18013E6F8
0x1801fccf9  mov     rcx, rbx
0x1801fccfc  call    sub_180002B7C
0x1801fcd01  or      r9d, 0FFFFFFFFh; cchCount1
0x1801fcd05  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1801fcd0a  mov     [rsp+38h+lpString2], rdi; lpString2
0x1801fcd0f  mov     r8, [rax+10h]; lpString1
0x1801fcd13  lea     edx, [r9+2]; dwCmpFlags
0x1801fcd17  lea     ecx, [rdx+7Eh]; Locale
0x1801fcd1a  call    cs:CompareStringW
0x1801fcd20  cmp     eax, 2
0x1801fcd23  setz    bl
0x1801fcd26  lea     rcx, [rsp+38h+arg_8]
0x1801fcd2b  call    sub_18013EA4C
0x1801fcd30  mov     al, bl
0x1801fcd32  mov     rbx, [rsp+38h+arg_0]
0x1801fcd37  add     rsp, 30h
0x1801fcd3b  pop     rdi
0x1801fcd3c  retn
```
