# FwFieldParserRServerNameNFlag(ushort const *,_tag_FW_RULE *)

- ea: `0x180012760`
- end: `0x1800127df`
- name: `?FwFieldParserRServerNameNFlag@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012760`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012786`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800127bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012786`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800127bf`

## pseudocode

```c
__int64 __fastcall FwFieldParserRServerNameNFlag(LPCWCH lpString1, struct _tag_FW_RULE *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"TRUE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 212) |= 0x20u;
    return 0;
  }
  if ( CompareStringOrdinal(lpString1, -1, L"FALSE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 212) &= ~0x20u;
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180012760  mov     [rsp+arg_0], rbx
0x180012765  push    rdi
0x180012766  sub     rsp, 30h
0x18001276a  or      r9d, 0FFFFFFFFh; cchCount2
0x18001276e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180012776  mov     rbx, rdx
0x180012779  lea     r8, String2; "TRUE"
0x180012780  or      edx, r9d; cchCount1
0x180012783  mov     rdi, rcx
0x180012786  call    cs:__imp_CompareStringOrdinal
0x18001278c  cmp     eax, 2
0x18001278f  jnz     short loc_1800127A6
0x180012791  or      word ptr [rbx+1A8h], 20h
0x180012799  xor     eax, eax
0x18001279b  mov     rbx, [rsp+38h+arg_0]
0x1800127a0  add     rsp, 30h
0x1800127a4  pop     rdi
0x1800127a5  retn
0x1800127a6  or      r9d, 0FFFFFFFFh; cchCount2
0x1800127aa  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800127b2  or      edx, r9d; cchCount1
0x1800127b5  lea     r8, aFalse; "FALSE"
0x1800127bc  mov     rcx, rdi; lpString1
0x1800127bf  call    cs:__imp_CompareStringOrdinal
0x1800127c5  cmp     eax, 2
0x1800127c8  jnz     short loc_1800127D8
0x1800127ca  mov     eax, 0FFDFh
0x1800127cf  and     [rbx+1A8h], ax
0x1800127d6  jmp     short loc_180012799
0x1800127d8  mov     eax, 8000FFFFh
0x1800127dd  jmp     short loc_18001279B
```
