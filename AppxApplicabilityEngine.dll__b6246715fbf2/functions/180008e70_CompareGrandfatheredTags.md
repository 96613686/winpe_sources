# CompareGrandfatheredTags

- ea: `0x180008e70`
- end: `0x180008e96`
- name: `CompareGrandfatheredTags`
- size: `38`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e88`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008e88`

## pseudocode

```c
__int64 __fastcall CompareGrandfatheredTags(const WCHAR *a1, LPCWCH *a2)
{
  return (unsigned int)(CompareStringOrdinal(a1, -1, *a2, -1, 1) - 2);
}

```

## disassembly

```asm
0x180008e70  sub     rsp, 38h
0x180008e74  mov     r8, [rdx]; lpString2
0x180008e77  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008e7d  mov     edx, r9d; cchCount1
0x180008e80  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180008e88  call    cs:__imp_CompareStringOrdinal
0x180008e8e  sub     eax, 2
0x180008e91  add     rsp, 38h
0x180008e95  retn
```
