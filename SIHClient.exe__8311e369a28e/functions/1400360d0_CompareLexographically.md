# CompareLexographically

- ea: `0x1400360d0`
- end: `0x140036124`
- name: `CompareLexographically`
- size: `84`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400360d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400360f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400360f2`

## pseudocode

```c
__int64 __fastcall CompareLexographically(PCNZWCH *a1, PCNZWCH *a2)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx

  v2 = CompareStringW(0x7Fu, 1u, *a1, -1, *a2, -1);
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( !v3 )
      return 0xFFFFFFFFLL;
    v4 = v3 - 1;
    if ( !v4 )
      return 0;
    if ( v4 == 1 )
      return 1;
  }
  return 4294967294LL;
}

```

## disassembly

```asm
0x1400360d0  sub     rsp, 38h
0x1400360d4  mov     rax, [rdx]
0x1400360d7  or      r9d, 0FFFFFFFFh; cchCount1
0x1400360db  mov     r8, [rcx]; lpString1
0x1400360de  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400360e6  mov     [rsp+38h+lpString2], rax; lpString2
0x1400360eb  lea     edx, [r9+2]; dwCmpFlags
0x1400360ef  lea     ecx, [rdx+7Eh]; Locale
0x1400360f2  call    cs:__imp_CompareStringW
0x1400360f8  mov     ecx, eax
0x1400360fa  test    eax, eax
0x1400360fc  jz      short loc_14003611A
0x1400360fe  sub     ecx, 1
0x140036101  jz      short loc_140036115
0x140036103  sub     ecx, 1
0x140036106  jz      short loc_140036111
0x140036108  cmp     ecx, 1
0x14003610b  jnz     short loc_14003611A
0x14003610d  mov     eax, ecx
0x14003610f  jmp     short loc_14003611F
0x140036111  xor     eax, eax
0x140036113  jmp     short loc_14003611F
0x140036115  or      eax, 0FFFFFFFFh
0x140036118  jmp     short loc_14003611F
0x14003611a  mov     eax, 0FFFFFFFEh
0x14003611f  add     rsp, 38h
0x140036123  retn
```
