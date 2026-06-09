# IsMatchingCid(ushort const *,WamAccountInfo const &)

- ea: `0x180024994`
- end: `0x180024a1f`
- name: `?IsMatchingCid@@YA_NPEBGAEBVWamAccountInfo@@@Z`
- size: `139`
- prototype: `bool __fastcall(LPCWCH lpString1, const struct WamAccountInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800180d0`

## callees

- `0x180024994`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800249c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800249c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a04`

## pseudocode

```c
bool __fastcall IsMatchingCid(LPCWCH lpString1, const struct WamAccountInfo *a2)
{
  const WCHAR *v4; // r8
  const WCHAR *v6; // r8

  if ( *((_QWORD *)a2 + 14) )
  {
    v4 = (const WCHAR *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v4 = *(const WCHAR **)v4;
    if ( CompareStringOrdinal(lpString1, -1, v4, -1, 1) == 2 )
      return 1;
  }
  if ( !*((_QWORD *)a2 + 18) )
    return 0;
  v6 = (const WCHAR *)((char *)a2 + 128);
  if ( *((_QWORD *)a2 + 19) > 7u )
    v6 = *(const WCHAR **)v6;
  return CompareStringOrdinal(lpString1, -1, v6, -1, 1) == 2;
}

```

## disassembly

```asm
0x180024994  mov     [rsp+arg_0], rbx
0x180024999  push    rdi
0x18002499a  sub     rsp, 30h
0x18002499e  cmp     qword ptr [rdx+70h], 0
0x1800249a3  mov     rbx, rdx
0x1800249a6  mov     rdi, rcx
0x1800249a9  jz      short loc_1800249D7
0x1800249ab  lea     r8, [rdx+60h]
0x1800249af  cmp     qword ptr [r8+18h], 7
0x1800249b4  jbe     short loc_1800249B9
0x1800249b6  mov     r8, [r8]; lpString2
0x1800249b9  or      r9d, 0FFFFFFFFh; cchCount2
0x1800249bd  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800249c5  or      edx, r9d; cchCount1
0x1800249c8  call    cs:__imp_CompareStringOrdinal
0x1800249ce  cmp     eax, 2
0x1800249d1  jnz     short loc_1800249D7
0x1800249d3  mov     al, 1
0x1800249d5  jmp     short loc_180024A14
0x1800249d7  cmp     qword ptr [rbx+90h], 0
0x1800249df  jz      short loc_180024A12
0x1800249e1  lea     r8, [rbx+80h]
0x1800249e8  cmp     qword ptr [r8+18h], 7
0x1800249ed  jbe     short loc_1800249F2
0x1800249ef  mov     r8, [r8]; lpString2
0x1800249f2  or      r9d, 0FFFFFFFFh; cchCount2
0x1800249f6  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800249fe  or      edx, r9d; cchCount1
0x180024a01  mov     rcx, rdi; lpString1
0x180024a04  call    cs:__imp_CompareStringOrdinal
0x180024a0a  cmp     eax, 2
0x180024a0d  setz    al
0x180024a10  jmp     short loc_180024A14
0x180024a12  xor     al, al
0x180024a14  mov     rbx, [rsp+38h+arg_0]
0x180024a19  add     rsp, 30h
0x180024a1d  pop     rdi
0x180024a1e  retn
```
