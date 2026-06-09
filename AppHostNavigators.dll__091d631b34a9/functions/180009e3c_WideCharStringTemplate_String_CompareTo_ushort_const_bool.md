# WideCharStringTemplate<String>::CompareTo(ushort const *,bool)

- ea: `0x180009e3c`
- end: `0x180009e78`
- name: `?CompareTo@?$WideCharStringTemplate@VString@@@@QEBAJPEBG_N@Z`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002700`
- `0x180009160`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180009e6a`
- `KERNEL32!CompareStringOrdinal` at `0x180009e6a`

## pseudocode

```c
__int64 __fastcall WideCharStringTemplate<String>::CompareTo(const WCHAR **a1, const WCHAR *a2)
{
  const WCHAR *v2; // rax
  const WCHAR *v3; // r8

  v2 = &qword_1800181B0;
  v3 = &qword_1800181B0;
  if ( a2 )
    v3 = a2;
  if ( *a1 )
    v2 = *a1;
  return (unsigned int)(CompareStringOrdinal(v2, -1, v3, -1, 1) - 2);
}

```

## disassembly

```asm
0x180009e3c  sub     rsp, 38h
0x180009e40  test    rdx, rdx
0x180009e43  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180009e4b  lea     rax, qword_1800181B0
0x180009e52  mov     r8, rax
0x180009e55  cmovnz  r8, rdx; lpString2
0x180009e59  cmp     qword ptr [rcx], 0
0x180009e5d  cmovnz  rax, [rcx]
0x180009e61  or      edx, 0FFFFFFFFh; cchCount1
0x180009e64  mov     r9d, edx; cchCount2
0x180009e67  mov     rcx, rax; lpString1
0x180009e6a  call    cs:__imp_CompareStringOrdinal
0x180009e70  sub     eax, 2
0x180009e73  add     rsp, 38h
0x180009e77  retn
```
