# CPolicyComponent::_SearchForKey(ushort const *,KEY_LIST_ENTRY const * *)

- ea: `0x1800018a0`
- end: `0x18000198a`
- name: `?_SearchForKey@CPolicyComponent@@AEAAJPEBGPEAPEBUKEY_LIST_ENTRY@@@Z`
- size: `234`
- prototype: `int(CPolicyComponent *__hidden this, const unsigned __int16 *, const struct KEY_LIST_ENTRY **)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000168c`
- `0x1800017f0`

## callees

- `0x1800018a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001906`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001956`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001906`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001956`

## pseudocode

```c
__int64 __fastcall CPolicyComponent::_SearchForKey(
        CPolicyComponent *this,
        const unsigned __int16 *a2,
        const struct KEY_LIST_ENTRY **a3)
{
  int v5; // esi
  int v6; // edi
  int v7; // ebx
  __int64 v8; // rbx
  unsigned int v9; // ecx

  *a3 = 0;
  v5 = 158;
  v6 = -1;
  do
  {
    v7 = (v5 - v6) / 2 + v6;
    if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)&gc_rgKeyList + 3 * v7 + 1), -1, a2, -1) != 3 )
    {
      v6 += (v5 - v6) / 2;
      v7 = v5;
    }
    v5 = v7;
  }
  while ( v7 - v6 > 1 );
  if ( v6 != -1
    && (v8 = 24LL * v6, CompareStringW(0x7Fu, 1u, *(PCNZWCH *)((char *)&gc_rgKeyList + v8 + 8), -1, a2, -1) == 2) )
  {
    v9 = 0;
    *a3 = (const struct KEY_LIST_ENTRY *)((char *)&gc_rgKeyList + v8);
  }
  else
  {
    return (unsigned int)-2003292351;
  }
  return v9;
}

```

## disassembly

```asm
0x1800018a0  mov     [rsp+arg_0], rcx
0x1800018a5  push    rbx
0x1800018a6  push    rsi
0x1800018a7  push    rdi
0x1800018a8  push    r12
0x1800018aa  push    r14
0x1800018ac  push    r15
0x1800018ae  sub     rsp, 48h
0x1800018b2  mov     r15, r8
0x1800018b5  mov     r14, rdx
0x1800018b8  mov     qword ptr [r8], 0
0x1800018bf  mov     esi, 9Eh
0x1800018c4  mov     edi, 0FFFFFFFFh
0x1800018c9  lea     r12, ?gc_rgKeyList@@3QBUKEY_LIST_ENTRY@@B; KEY_LIST_ENTRY const near * const gc_rgKeyList
0x1800018d0  mov     eax, esi
0x1800018d2  sub     eax, edi
0x1800018d4  jns     short loc_1800018D8
0x1800018d6  inc     eax
0x1800018d8  sar     eax, 1
0x1800018da  lea     ebx, [rax+rdi]
0x1800018dd  movsxd  rax, ebx
0x1800018e0  lea     r8, [rax+rax*2]
0x1800018e4  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800018ec  mov     [rsp+78h+lpString2], r14; lpString2
0x1800018f1  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800018f7  mov     r8, [r12+r8*8+8]; lpString1
0x1800018fc  mov     edx, 1; dwCmpFlags
0x180001901  mov     ecx, 7Fh; Locale
0x180001906  call    cs:__imp_CompareStringW
0x18000190c  cmp     eax, 3
0x18000190f  cmovnz  edi, ebx
0x180001912  cmovnz  ebx, esi
0x180001915  mov     esi, ebx
0x180001917  mov     eax, ebx
0x180001919  sub     eax, edi
0x18000191b  cmp     eax, 1
0x18000191e  jg      short loc_1800018D0
0x180001920  cmp     edi, 0FFFFFFFFh
0x180001923  jz      short loc_180001961
0x180001925  movsxd  rax, edi
0x180001928  lea     r8, [rax+rax*2]
0x18000192c  lea     rbx, ds:0[r8*8]
0x180001934  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000193c  mov     [rsp+78h+lpString2], r14; lpString2
0x180001941  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001947  mov     r8, [rbx+r12+8]; lpString1
0x18000194c  mov     edx, 1; dwCmpFlags
0x180001951  mov     ecx, 7Fh; Locale
0x180001956  call    cs:__imp_CompareStringW
0x18000195c  cmp     eax, 2
0x18000195f  jz      short loc_180001976
0x180001961  mov     ecx, 88982F41h
0x180001966  mov     eax, ecx
0x180001968  add     rsp, 48h
0x18000196c  pop     r15
0x18000196e  pop     r14
0x180001970  pop     r12
0x180001972  pop     rdi
0x180001973  pop     rsi
0x180001974  pop     rbx
0x180001975  retn
0x180001976  xor     ecx, ecx
0x180001978  lea     rax, [rbx+r12]
0x18000197c  mov     [r15], rax
0x18000197f  jmp     short loc_180001966
0x180001981  mov     eax, dword ptr [rsp+78h+arg_0]
0x180001988  jmp     short loc_180001968
```
