# FIsHTMLFile

- ea: `0x18000b1d0`
- end: `0x18000b283`
- name: `FIsHTMLFile`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b1d0`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x18000b224`
- `KERNEL32!CompareStringA` at `0x18000b25f`
- `KERNEL32!CompareStringA` at `0x18000b224`
- `KERNEL32!CompareStringA` at `0x18000b25f`

## pseudocode

```c
_BOOL8 __fastcall FIsHTMLFile(__int64 a1)
{
  __int64 v2; // rbx

  if ( !a1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( *(_BYTE *)(a1 + v2) );
  if ( (int)v2 > 4 && CompareStringA(0x7Fu, 1u, (PCNZCH)(a1 + (int)v2 - 4), -1, ".htm", -1) == 2 )
    return 1;
  return (int)v2 > 5 && CompareStringA(0x7Fu, 1u, (PCNZCH)(a1 + (int)v2 - 5), -1, ".html", -1) == 2;
}

```

## disassembly

```asm
0x18000b1d0  mov     [rsp+arg_0], rbx
0x18000b1d5  mov     [rsp+arg_8], rsi
0x18000b1da  push    rdi
0x18000b1db  sub     rsp, 30h
0x18000b1df  mov     rdi, rcx
0x18000b1e2  test    rcx, rcx
0x18000b1e5  jz      loc_18000B271
0x18000b1eb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b1ef  mov     rbx, rsi
0x18000b1f2  inc     rbx
0x18000b1f5  cmp     byte ptr [rcx+rbx], 0
0x18000b1f9  jnz     short loc_18000B1F2
0x18000b1fb  cmp     ebx, 4
0x18000b1fe  jle     short loc_18000B236
0x18000b200  lea     ecx, [rbx-4]
0x18000b203  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18000b207  movsxd  r8, ecx
0x18000b20a  mov     edx, 1; dwCmpFlags
0x18000b20f  lea     rcx, String2; ".htm"
0x18000b216  add     r8, rdi; lpString1
0x18000b219  mov     [rsp+38h+lpString2], rcx; lpString2
0x18000b21e  mov     r9d, esi; cchCount1
0x18000b221  lea     ecx, [rdx+7Eh]; Locale
0x18000b224  call    cs:__imp_CompareStringA
0x18000b22a  cmp     eax, 2
0x18000b22d  jnz     short loc_18000B236
0x18000b22f  mov     eax, 1
0x18000b234  jmp     short loc_18000B273
0x18000b236  cmp     ebx, 5
0x18000b239  jle     short loc_18000B271
0x18000b23b  mov     edx, 1; dwCmpFlags
0x18000b240  mov     [rsp+38h+cchCount2], esi; cchCount2
0x18000b244  lea     eax, [rbx-5]
0x18000b247  mov     r9d, esi; cchCount1
0x18000b24a  movsxd  r8, eax
0x18000b24d  lea     rax, aHtml_0; ".html"
0x18000b254  add     r8, rdi; lpString1
0x18000b257  mov     [rsp+38h+lpString2], rax; lpString2
0x18000b25c  lea     ecx, [rdx+7Eh]; Locale
0x18000b25f  call    cs:__imp_CompareStringA
0x18000b265  xor     ecx, ecx
0x18000b267  cmp     eax, 2
0x18000b26a  setz    cl
0x18000b26d  mov     eax, ecx
0x18000b26f  jmp     short loc_18000B273
0x18000b271  xor     eax, eax
0x18000b273  mov     rbx, [rsp+38h+arg_0]
0x18000b278  mov     rsi, [rsp+38h+arg_8]
0x18000b27d  add     rsp, 30h
0x18000b281  pop     rdi
0x18000b282  retn
```
