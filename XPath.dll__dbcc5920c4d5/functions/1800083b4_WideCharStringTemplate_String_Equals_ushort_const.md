# WideCharStringTemplate<String>::Equals(ushort const *)

- ea: `0x1800083b4`
- end: `0x1800083f3`
- name: `?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z`
- size: `63`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`
- `0x180005dc0`
- `0x1800060e0`
- `0x18000615c`
- `0x1800061ac`
- `0x1800061fc`
- `0x180008f04`
- `0x180009448`
- `0x180009c58`
- `0x18000b2f0`
- `0x18000cdd0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800083e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800083e2`

## pseudocode

```c
bool __fastcall WideCharStringTemplate<String>::Equals(const WCHAR **a1, const WCHAR *a2)
{
  const WCHAR *v2; // rax
  const WCHAR *v3; // r8

  v2 = &qword_180016F98;
  v3 = &qword_180016F98;
  if ( a2 )
    v3 = a2;
  if ( *a1 )
    v2 = *a1;
  return CompareStringOrdinal(v2, -1, v3, -1, 0) == 2;
}

```

## disassembly

```asm
0x1800083b4  sub     rsp, 38h
0x1800083b8  test    rdx, rdx
0x1800083bb  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x1800083c3  lea     rax, qword_180016F98
0x1800083ca  mov     r8, rax
0x1800083cd  cmovnz  r8, rdx; lpString2
0x1800083d1  cmp     qword ptr [rcx], 0
0x1800083d5  cmovnz  rax, [rcx]
0x1800083d9  or      edx, 0FFFFFFFFh; cchCount1
0x1800083dc  mov     r9d, edx; cchCount2
0x1800083df  mov     rcx, rax; lpString1
0x1800083e2  call    cs:__imp_CompareStringOrdinal
0x1800083e8  cmp     eax, 2
0x1800083eb  setz    al
0x1800083ee  add     rsp, 38h
0x1800083f2  retn
```
