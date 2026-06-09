# sub_1801FCDDC

- ea: `0x1801fcddc`
- end: `0x1801fce75`
- name: `sub_1801FCDDC`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18025d140`

## callees

- `0x180002b7c`
- `0x1800daa88`
- `0x18013e6f8`
- `0x18013e9e0`
- `0x18013ea4c`
- `0x1801fcddc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801fce52`
- `KERNEL32!CompareStringW` at `0x1801fce52`

## pseudocode

```c
bool __fastcall sub_1801FCDDC(__int64 a1)
{
  const WCHAR *lpString2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rax
  bool v5; // bl
  char v7; // [rsp+48h] [rbp+10h] BYREF

  sub_18013E9E0((__int64)&v7, L"0");
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
0x1801fcddc  mov     [rsp+arg_0], rbx
0x1801fcde1  push    rdi
0x1801fcde2  sub     rsp, 30h
0x1801fcde6  mov     rbx, rcx
0x1801fcde9  lea     rdx, a0_0; "0"
0x1801fcdf0  lea     rcx, [rsp+38h+arg_8]
0x1801fcdf5  call    sub_18013E9E0
0x1801fcdfa  lea     rcx, [rsp+38h+arg_8]
0x1801fcdff  call    sub_1800DAA88
0x1801fce04  test    al, al
0x1801fce06  jz      short loc_1801FCE12
0x1801fce08  lea     rcx, [rsp+38h+arg_8]
0x1801fce0d  call    sub_18013E6F8
0x1801fce12  lea     rcx, [rsp+38h+arg_8]
0x1801fce17  call    sub_180002B7C
0x1801fce1c  mov     rdi, [rax+10h]
0x1801fce20  mov     rcx, rbx
0x1801fce23  call    sub_1800DAA88
0x1801fce28  test    al, al
0x1801fce2a  jz      short loc_1801FCE31
0x1801fce2c  call    sub_18013E6F8
0x1801fce31  mov     rcx, rbx
0x1801fce34  call    sub_180002B7C
0x1801fce39  or      r9d, 0FFFFFFFFh; cchCount1
0x1801fce3d  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1801fce42  mov     [rsp+38h+lpString2], rdi; lpString2
0x1801fce47  mov     r8, [rax+10h]; lpString1
0x1801fce4b  lea     edx, [r9+2]; dwCmpFlags
0x1801fce4f  lea     ecx, [rdx+7Eh]; Locale
0x1801fce52  call    cs:CompareStringW
0x1801fce58  cmp     eax, 2
0x1801fce5b  setz    bl
0x1801fce5e  lea     rcx, [rsp+38h+arg_8]
0x1801fce63  call    sub_18013EA4C
0x1801fce68  mov     al, bl
0x1801fce6a  mov     rbx, [rsp+38h+arg_0]
0x1801fce6f  add     rsp, 30h
0x1801fce73  pop     rdi
0x1801fce74  retn
```
