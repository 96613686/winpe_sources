# FwFieldParserRServerNameEFlag(ushort const *,_tag_FW_RULE *)

- ea: `0x1800114a0`
- end: `0x18001151f`
- name: `?FwFieldParserRServerNameEFlag@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800114a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800114ff`

## pseudocode

```c
__int64 __fastcall FwFieldParserRServerNameEFlag(LPCWCH lpString1, struct _tag_FW_RULE *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"TRUE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 212) |= 0x10u;
    return 0;
  }
  if ( CompareStringOrdinal(lpString1, -1, L"FALSE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 212) &= ~0x10u;
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800114a0  mov     [rsp+arg_0], rbx
0x1800114a5  push    rdi
0x1800114a6  sub     rsp, 30h
0x1800114aa  or      r9d, 0FFFFFFFFh; cchCount2
0x1800114ae  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800114b6  mov     rbx, rdx
0x1800114b9  lea     r8, String2; "TRUE"
0x1800114c0  or      edx, r9d; cchCount1
0x1800114c3  mov     rdi, rcx
0x1800114c6  call    cs:__imp_CompareStringOrdinal
0x1800114cc  cmp     eax, 2
0x1800114cf  jnz     short loc_1800114E6
0x1800114d1  or      word ptr [rbx+1A8h], 10h
0x1800114d9  xor     eax, eax
0x1800114db  mov     rbx, [rsp+38h+arg_0]
0x1800114e0  add     rsp, 30h
0x1800114e4  pop     rdi
0x1800114e5  retn
0x1800114e6  or      r9d, 0FFFFFFFFh; cchCount2
0x1800114ea  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800114f2  or      edx, r9d; cchCount1
0x1800114f5  lea     r8, aFalse; "FALSE"
0x1800114fc  mov     rcx, rdi; lpString1
0x1800114ff  call    cs:__imp_CompareStringOrdinal
0x180011505  cmp     eax, 2
0x180011508  jnz     short loc_180011518
0x18001150a  mov     eax, 0FFEFh
0x18001150f  and     [rbx+1A8h], ax
0x180011516  jmp     short loc_1800114D9
0x180011518  mov     eax, 8000FFFFh
0x18001151d  jmp     short loc_1800114DB
```
