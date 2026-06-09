# FwFieldParserEdge(ushort const *,_tag_FW_RULE *)

- ea: `0x180013b70`
- end: `0x180013bef`
- name: `?FwFieldParserEdge@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013b70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013b96`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013bcf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013b96`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013bcf`

## pseudocode

```c
__int64 __fastcall FwFieldParserEdge(LPCWCH lpString1, struct _tag_FW_RULE *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"TRUE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 146) |= 8u;
    return 0;
  }
  if ( CompareStringOrdinal(lpString1, -1, L"FALSE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 146) &= ~8u;
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180013b70  mov     [rsp+arg_0], rbx
0x180013b75  push    rdi
0x180013b76  sub     rsp, 30h
0x180013b7a  or      r9d, 0FFFFFFFFh; cchCount2
0x180013b7e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180013b86  mov     rbx, rdx
0x180013b89  lea     r8, String2; "TRUE"
0x180013b90  or      edx, r9d; cchCount1
0x180013b93  mov     rdi, rcx
0x180013b96  call    cs:__imp_CompareStringOrdinal
0x180013b9c  cmp     eax, 2
0x180013b9f  jnz     short loc_180013BB6
0x180013ba1  or      word ptr [rbx+124h], 8
0x180013ba9  xor     eax, eax
0x180013bab  mov     rbx, [rsp+38h+arg_0]
0x180013bb0  add     rsp, 30h
0x180013bb4  pop     rdi
0x180013bb5  retn
0x180013bb6  or      r9d, 0FFFFFFFFh; cchCount2
0x180013bba  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180013bc2  or      edx, r9d; cchCount1
0x180013bc5  lea     r8, aFalse; "FALSE"
0x180013bcc  mov     rcx, rdi; lpString1
0x180013bcf  call    cs:__imp_CompareStringOrdinal
0x180013bd5  cmp     eax, 2
0x180013bd8  jnz     short loc_180013BE8
0x180013bda  mov     eax, 0FFF7h
0x180013bdf  and     [rbx+124h], ax
0x180013be6  jmp     short loc_180013BA9
0x180013be8  mov     eax, 8000FFFFh
0x180013bed  jmp     short loc_180013BAB
```
