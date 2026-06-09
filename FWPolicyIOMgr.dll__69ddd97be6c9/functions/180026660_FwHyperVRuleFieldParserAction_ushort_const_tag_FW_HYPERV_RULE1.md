# FwHyperVRuleFieldParserAction(ushort const *,_tag_FW_HYPERV_RULE1 *)

- ea: `0x180026660`
- end: `0x1800266db`
- name: `?FwHyperVRuleFieldParserAction@@YAJPEBGPEAU_tag_FW_HYPERV_RULE1@@@Z`
- size: `123`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_HYPERV_RULE1 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026660`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026686`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800266b4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026686`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800266b4`

## pseudocode

```c
__int64 __fastcall FwHyperVRuleFieldParserAction(LPCWCH lpString1, struct _tag_FW_HYPERV_RULE1 *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"Block", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 64) = 2;
    return 0;
  }
  if ( CompareStringOrdinal(lpString1, -1, L"Allow", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 64) = 3;
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180026660  mov     [rsp+arg_0], rbx
0x180026665  push    rdi
0x180026666  sub     rsp, 30h
0x18002666a  or      r9d, 0FFFFFFFFh; cchCount2
0x18002666e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180026676  mov     rbx, rdx
0x180026679  lea     r8, aBlock; "Block"
0x180026680  or      edx, r9d; cchCount1
0x180026683  mov     rdi, rcx
0x180026686  call    cs:__imp_CompareStringOrdinal
0x18002668c  cmp     eax, 2
0x18002668f  jnz     short loc_18002669B
0x180026691  mov     [rbx+100h], eax
0x180026697  xor     eax, eax
0x180026699  jmp     short loc_1800266D0
0x18002669b  or      r9d, 0FFFFFFFFh; cchCount2
0x18002669f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800266a7  or      edx, r9d; cchCount1
0x1800266aa  lea     r8, aAllow; "Allow"
0x1800266b1  mov     rcx, rdi; lpString1
0x1800266b4  call    cs:__imp_CompareStringOrdinal
0x1800266ba  cmp     eax, 2
0x1800266bd  jnz     short loc_1800266CB
0x1800266bf  mov     dword ptr [rbx+100h], 3
0x1800266c9  jmp     short loc_180026697
0x1800266cb  mov     eax, 8000FFFFh
0x1800266d0  mov     rbx, [rsp+38h+arg_0]
0x1800266d5  add     rsp, 30h
0x1800266d9  pop     rdi
0x1800266da  retn
```
