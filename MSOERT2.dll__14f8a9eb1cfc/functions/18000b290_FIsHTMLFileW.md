# FIsHTMLFileW

- ea: `0x18000b290`
- end: `0x18000b33a`
- name: `FIsHTMLFileW`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b290`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000b2e1`
- `KERNEL32!CompareStringW` at `0x18000b31d`
- `KERNEL32!CompareStringW` at `0x18000b2e1`
- `KERNEL32!CompareStringW` at `0x18000b31d`

## pseudocode

```c
_BOOL8 __fastcall FIsHTMLFileW(__int64 a1)
{
  __int64 v2; // rbx

  if ( !a1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(a1 + 2 * v2) );
  if ( (int)v2 > 4 && CompareStringW(0x7Fu, 1u, (PCNZWCH)(a1 + 2LL * ((int)v2 - 4)), -1, L".htm", -1) == 2 )
    return 1;
  return (int)v2 > 5 && CompareStringW(0x7Fu, 1u, (PCNZWCH)(a1 + 2LL * ((int)v2 - 5)), -1, L".html", -1) == 2;
}

```

## disassembly

```asm
0x18000b290  push    rbx
0x18000b292  push    rbp
0x18000b293  push    rsi
0x18000b294  push    rdi
0x18000b295  sub     rsp, 38h
0x18000b299  xor     esi, esi
0x18000b29b  mov     rdi, rcx
0x18000b29e  test    rcx, rcx
0x18000b2a1  jz      loc_18000B32F
0x18000b2a7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b2ab  mov     rbx, rbp
0x18000b2ae  inc     rbx
0x18000b2b1  cmp     [rcx+rbx*2], si
0x18000b2b5  jnz     short loc_18000B2AE
0x18000b2b7  cmp     ebx, 4
0x18000b2ba  jle     short loc_18000B2F3
0x18000b2bc  lea     ecx, [rbx-4]
0x18000b2bf  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000b2c3  movsxd  rdx, ecx
0x18000b2c6  mov     r9d, ebp; cchCount1
0x18000b2c9  lea     rcx, aHtm; ".htm"
0x18000b2d0  mov     [rsp+58h+lpString2], rcx; lpString2
0x18000b2d5  lea     r8, [rdi+rdx*2]; lpString1
0x18000b2d9  mov     edx, 1; dwCmpFlags
0x18000b2de  lea     ecx, [rdx+7Eh]; Locale
0x18000b2e1  call    cs:__imp_CompareStringW
0x18000b2e7  cmp     eax, 2
0x18000b2ea  jnz     short loc_18000B2F3
0x18000b2ec  mov     eax, 1
0x18000b2f1  jmp     short loc_18000B331
0x18000b2f3  cmp     ebx, 5
0x18000b2f6  jle     short loc_18000B32F
0x18000b2f8  lea     eax, [rbx-5]
0x18000b2fb  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000b2ff  movsxd  rdx, eax
0x18000b302  mov     r9d, ebp; cchCount1
0x18000b305  lea     rax, aHtml; ".html"
0x18000b30c  mov     [rsp+58h+lpString2], rax; lpString2
0x18000b311  lea     r8, [rdi+rdx*2]; lpString1
0x18000b315  mov     edx, 1; dwCmpFlags
0x18000b31a  lea     ecx, [rdx+7Eh]; Locale
0x18000b31d  call    cs:__imp_CompareStringW
0x18000b323  cmp     eax, 2
0x18000b326  mov     ecx, esi
0x18000b328  setz    cl
0x18000b32b  mov     eax, ecx
0x18000b32d  jmp     short loc_18000B331
0x18000b32f  xor     eax, eax
0x18000b331  add     rsp, 38h
0x18000b335  pop     rdi
0x18000b336  pop     rsi
0x18000b337  pop     rbp
0x18000b338  pop     rbx
0x18000b339  retn
```
