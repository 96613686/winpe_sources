# FwFieldParserAction(ushort const *,_tag_FW_RULE *)

- ea: `0x18000f5b0`
- end: `0x18000f672`
- name: `?FwFieldParserAction@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f5b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f5d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f5fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f652`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f5d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f5fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f652`

## pseudocode

```c
__int64 __fastcall FwFieldParserAction(LPCWCH lpString1, struct _tag_FW_RULE *a2)
{
  if ( CompareStringOrdinal(lpString1, -1, L"Block", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 72) = 2;
    return 0;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"Allow", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 72) = 3;
    return 0;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"ByPass", -1, 1) == 2 )
  {
    *((_DWORD *)a2 + 72) = 1;
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
0x18000f5b0  mov     [rsp+arg_0], rbx
0x18000f5b5  push    rdi
0x18000f5b6  sub     rsp, 30h
0x18000f5ba  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f5c0  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f5c8  mov     rbx, rdx
0x18000f5cb  lea     r8, aBlock; "Block"
0x18000f5d2  mov     edx, r9d; cchCount1
0x18000f5d5  mov     rdi, rcx
0x18000f5d8  call    cs:__imp_CompareStringOrdinal
0x18000f5de  cmp     eax, 2
0x18000f5e1  jz      short loc_18000F620
0x18000f5e3  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f5e9  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f5f1  mov     edx, r9d; cchCount1
0x18000f5f4  lea     r8, aAllow; "Allow"
0x18000f5fb  mov     rcx, rdi; lpString1
0x18000f5fe  call    cs:__imp_CompareStringOrdinal
0x18000f604  cmp     eax, 2
0x18000f607  jnz     short loc_18000F637
0x18000f609  mov     dword ptr [rbx+120h], 3
0x18000f613  xor     eax, eax
0x18000f615  mov     rbx, [rsp+38h+arg_0]
0x18000f61a  add     rsp, 30h
0x18000f61e  pop     rdi
0x18000f61f  retn
0x18000f620  mov     dword ptr [rbx+120h], 2
0x18000f62a  xor     eax, eax
0x18000f62c  mov     rbx, [rsp+38h+arg_0]
0x18000f631  add     rsp, 30h
0x18000f635  pop     rdi
0x18000f636  retn
0x18000f637  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000f63d  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000f645  mov     edx, r9d; cchCount1
0x18000f648  lea     r8, aBypass; "ByPass"
0x18000f64f  mov     rcx, rdi; lpString1
0x18000f652  call    cs:__imp_CompareStringOrdinal
0x18000f658  cmp     eax, 2
0x18000f65b  jnz     short loc_18000F66B
0x18000f65d  mov     dword ptr [rbx+120h], 1
0x18000f667  xor     eax, eax
0x18000f669  jmp     short loc_18000F615
0x18000f66b  mov     eax, 8000FFFFh
0x18000f670  jmp     short loc_18000F615
```
