# FwFieldParserActive(ushort const *,_tag_FW_RULE *)

- ea: `0x18000f380`
- end: `0x18000f40e`
- name: `?FwFieldParserActive@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f380`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f3a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f3e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f3a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f3e3`

## pseudocode

```c
__int64 __fastcall FwFieldParserActive(LPCWCH lpString1, struct _tag_FW_RULE *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"TRUE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 146) |= 1u;
    return 0;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"FALSE", -1, 1) == 2 )
  {
    *((_WORD *)a2 + 146) &= ~1u;
    return 0;
  }
  else
  {
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18000f380  mov     [rsp+arg_0], rbx
0x18000f385  push    rdi
0x18000f386  sub     rsp, 30h
0x18000f38a  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f390  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f398  mov     rbx, rdx
0x18000f39b  lea     r8, String2; "TRUE"
0x18000f3a2  mov     edx, r9d; cchCount1
0x18000f3a5  mov     rdi, rcx
0x18000f3a8  call    cs:__imp_CompareStringOrdinal
0x18000f3ae  cmp     eax, 2
0x18000f3b1  jnz     short loc_18000F3C8
0x18000f3b3  or      word ptr [rbx+124h], 1
0x18000f3bb  xor     eax, eax
0x18000f3bd  mov     rbx, [rsp+38h+arg_0]
0x18000f3c2  add     rsp, 30h
0x18000f3c6  pop     rdi
0x18000f3c7  retn
0x18000f3c8  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f3ce  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f3d6  mov     edx, r9d; cchCount1
0x18000f3d9  lea     r8, aFalse; "FALSE"
0x18000f3e0  mov     rcx, rdi; lpString1
0x18000f3e3  call    cs:__imp_CompareStringOrdinal
0x18000f3e9  cmp     eax, 2
0x18000f3ec  jnz     short loc_18000F407
0x18000f3ee  mov     eax, 0FFFEh
0x18000f3f3  and     [rbx+124h], ax
0x18000f3fa  mov     rbx, [rsp+38h+arg_0]
0x18000f3ff  xor     eax, eax
0x18000f401  add     rsp, 30h
0x18000f405  pop     rdi
0x18000f406  retn
0x18000f407  mov     eax, 8000FFFFh
0x18000f40c  jmp     short loc_18000F3BD
```
