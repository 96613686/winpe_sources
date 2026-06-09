# CPolicyComponent::_SearchForKey(ushort const *,KEY_LIST_ENTRY const * *)

- ea: `0x180001920`
- end: `0x180001a17`
- name: `?_SearchForKey@CPolicyComponent@@AEAAJPEBGPEAPEBUKEY_LIST_ENTRY@@@Z`
- size: `247`
- prototype: `int(CPolicyComponent *__hidden this, const unsigned __int16 *, const struct KEY_LIST_ENTRY **)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000170c`
- `0x180001870`

## callees

- `0x180001920`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001986`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800019dc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001986`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800019dc`

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
0x180001920  mov     [rsp+arg_0], rcx
0x180001925  push    rbx
0x180001926  push    rsi
0x180001927  push    rdi
0x180001928  push    r12
0x18000192a  push    r14
0x18000192c  push    r15
0x18000192e  sub     rsp, 48h
0x180001932  mov     r15, r8
0x180001935  mov     r14, rdx
0x180001938  mov     qword ptr [r8], 0
0x18000193f  mov     esi, 9Eh
0x180001944  mov     edi, 0FFFFFFFFh
0x180001949  lea     r12, ?gc_rgKeyList@@3QBUKEY_LIST_ENTRY@@B; KEY_LIST_ENTRY const near * const gc_rgKeyList
0x180001950  mov     eax, esi
0x180001952  sub     eax, edi
0x180001954  jns     short loc_180001958
0x180001956  inc     eax
0x180001958  sar     eax, 1
0x18000195a  lea     ebx, [rax+rdi]
0x18000195d  movsxd  rax, ebx
0x180001960  lea     r8, [rax+rax*2]
0x180001964  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000196c  mov     [rsp+78h+lpString2], r14; lpString2
0x180001971  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001977  mov     r8, [r12+r8*8+8]; lpString1
0x18000197c  mov     edx, 1; dwCmpFlags
0x180001981  mov     ecx, 7Fh; Locale
0x180001986  call    cs:__imp_CompareStringW
0x18000198d  nop     dword ptr [rax+rax+00h]
0x180001992  cmp     eax, 3
0x180001995  cmovnz  edi, ebx
0x180001998  cmovnz  ebx, esi
0x18000199b  mov     esi, ebx
0x18000199d  mov     eax, ebx
0x18000199f  sub     eax, edi
0x1800019a1  cmp     eax, 1
0x1800019a4  jg      short loc_180001950
0x1800019a6  cmp     edi, 0FFFFFFFFh
0x1800019a9  jz      short loc_1800019ED
0x1800019ab  movsxd  rax, edi
0x1800019ae  lea     r8, [rax+rax*2]
0x1800019b2  lea     rbx, ds:0[r8*8]
0x1800019ba  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800019c2  mov     [rsp+78h+lpString2], r14; lpString2
0x1800019c7  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800019cd  mov     r8, [rbx+r12+8]; lpString1
0x1800019d2  mov     edx, 1; dwCmpFlags
0x1800019d7  mov     ecx, 7Fh; Locale
0x1800019dc  call    cs:__imp_CompareStringW
0x1800019e3  nop     dword ptr [rax+rax+00h]
0x1800019e8  cmp     eax, 2
0x1800019eb  jz      short loc_180001A03
0x1800019ed  mov     ecx, 88982F41h
0x1800019f2  mov     eax, ecx
0x1800019f4  add     rsp, 48h
0x1800019f8  pop     r15
0x1800019fa  pop     r14
0x1800019fc  pop     r12
0x1800019fe  pop     rdi
0x1800019ff  pop     rsi
0x180001a00  pop     rbx
0x180001a01  retn
0x180001a03  xor     ecx, ecx
0x180001a05  lea     rax, [rbx+r12]
0x180001a09  mov     [r15], rax
0x180001a0c  jmp     short loc_1800019F2
0x180001a0e  mov     eax, dword ptr [rsp+78h+arg_0]
0x180001a15  jmp     short loc_1800019F4
```
