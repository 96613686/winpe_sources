# FwHyperVRuleFieldParserDirection(ushort const *,_tag_FW_HYPERV_RULE1 *)

- ea: `0x180026710`
- end: `0x180026785`
- name: `?FwHyperVRuleFieldParserDirection@@YAJPEBGPEAU_tag_FW_HYPERV_RULE1@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_HYPERV_RULE1 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026710`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026736`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026765`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026736`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026765`

## pseudocode

```c
__int64 __fastcall FwHyperVRuleFieldParserDirection(LPCWCH lpString1, struct _tag_FW_HYPERV_RULE1 *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"In", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 9) = 1;
    return 0;
  }
  if ( CompareStringOrdinal(lpString1, -1, L"Out", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 9) = 2;
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180026710  mov     [rsp+arg_0], rbx
0x180026715  push    rdi
0x180026716  sub     rsp, 30h
0x18002671a  or      r9d, 0FFFFFFFFh; cchCount2
0x18002671e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180026726  mov     rbx, rdx
0x180026729  lea     r8, aIn; "In"
0x180026730  or      edx, r9d; cchCount1
0x180026733  mov     rdi, rcx
0x180026736  call    cs:__imp_CompareStringOrdinal
0x18002673c  cmp     eax, 2
0x18002673f  jnz     short loc_18002674C
0x180026741  mov     dword ptr [rbx+24h], 1
0x180026748  xor     eax, eax
0x18002674a  jmp     short loc_18002677A
0x18002674c  or      r9d, 0FFFFFFFFh; cchCount2
0x180026750  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180026758  or      edx, r9d; cchCount1
0x18002675b  lea     r8, aOut; "Out"
0x180026762  mov     rcx, rdi; lpString1
0x180026765  call    cs:__imp_CompareStringOrdinal
0x18002676b  cmp     eax, 2
0x18002676e  jnz     short loc_180026775
0x180026770  mov     [rbx+24h], eax
0x180026773  jmp     short loc_180026748
0x180026775  mov     eax, 8000FFFFh
0x18002677a  mov     rbx, [rsp+38h+arg_0]
0x18002677f  add     rsp, 30h
0x180026783  pop     rdi
0x180026784  retn
```
