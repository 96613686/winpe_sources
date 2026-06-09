# FwFieldParserDirection(ushort const *,_tag_FW_RULE *)

- ea: `0x18000f770`
- end: `0x18000f7f4`
- name: `?FwFieldParserDirection@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f770`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f798`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f7d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f798`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f7d2`

## pseudocode

```c
__int64 __fastcall FwFieldParserDirection(LPCWCH lpString1, struct _tag_FW_RULE *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"In", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 11) = 1;
    return 0;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"Out", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 11) = 2;
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
0x18000f770  mov     [rsp+arg_0], rbx
0x18000f775  push    rdi
0x18000f776  sub     rsp, 30h
0x18000f77a  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f780  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f788  mov     rbx, rdx
0x18000f78b  lea     r8, aIn; "In"
0x18000f792  mov     edx, r9d; cchCount1
0x18000f795  mov     rdi, rcx
0x18000f798  call    cs:__imp_CompareStringOrdinal
0x18000f79e  cmp     eax, 2
0x18000f7a1  jnz     short loc_18000F7B7
0x18000f7a3  mov     dword ptr [rbx+2Ch], 1
0x18000f7aa  xor     eax, eax
0x18000f7ac  mov     rbx, [rsp+38h+arg_0]
0x18000f7b1  add     rsp, 30h
0x18000f7b5  pop     rdi
0x18000f7b6  retn
0x18000f7b7  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f7bd  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f7c5  mov     edx, r9d; cchCount1
0x18000f7c8  lea     r8, aOut; "Out"
0x18000f7cf  mov     rcx, rdi; lpString1
0x18000f7d2  call    cs:__imp_CompareStringOrdinal
0x18000f7d8  cmp     eax, 2
0x18000f7db  jnz     short loc_18000F7ED
0x18000f7dd  mov     [rbx+2Ch], eax
0x18000f7e0  xor     eax, eax
0x18000f7e2  mov     rbx, [rsp+38h+arg_0]
0x18000f7e7  add     rsp, 30h
0x18000f7eb  pop     rdi
0x18000f7ec  retn
0x18000f7ed  mov     eax, 8000FFFFh
0x18000f7f2  jmp     short loc_18000F7AC
```
