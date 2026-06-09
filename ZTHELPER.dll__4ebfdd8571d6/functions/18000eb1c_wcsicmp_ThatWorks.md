# wcsicmp_ThatWorks

- ea: `0x18000eb1c`
- end: `0x18000eb76`
- name: `wcsicmp_ThatWorks`
- size: `90`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000292c`
- `0x180007b64`
- `0x180008700`

## callees

- `0x18000eb1c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000eb4e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000eb4e`

## pseudocode

```c
__int64 __fastcall wcsicmp_ThatWorks(PCNZWCH lpString1, PCNZWCH lpString2)
{
  unsigned int v2; // ebx
  int v3; // eax

  if ( lpString1 )
  {
    v2 = 1;
    if ( lpString2 )
    {
      v3 = CompareStringW(0x409u, 1u, lpString1, -1, lpString2, -1);
      if ( v3 == 2 )
      {
        return 0;
      }
      else if ( v3 == 1 )
      {
        return (unsigned int)-1;
      }
    }
  }
  else
  {
    return (unsigned int)-(lpString2 != 0);
  }
  return v2;
}

```

## disassembly

```asm
0x18000eb1c  mov     [rsp+arg_0], rbx
0x18000eb21  push    rdi
0x18000eb22  sub     rsp, 30h
0x18000eb26  test    rcx, rcx
0x18000eb29  jz      short loc_18000EB64
0x18000eb2b  mov     ebx, 1
0x18000eb30  test    rdx, rdx
0x18000eb33  jz      short loc_18000EB69
0x18000eb35  or      edi, 0FFFFFFFFh
0x18000eb38  mov     r8, rcx; lpString1
0x18000eb3b  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18000eb3f  mov     r9d, edi; cchCount1
0x18000eb42  mov     [rsp+38h+lpString2], rdx; lpString2
0x18000eb47  mov     ecx, 409h; Locale
0x18000eb4c  mov     edx, ebx; dwCmpFlags
0x18000eb4e  call    cs:__imp_CompareStringW
0x18000eb54  cmp     eax, 2
0x18000eb57  jnz     short loc_18000EB5D
0x18000eb59  xor     ebx, ebx
0x18000eb5b  jmp     short loc_18000EB69
0x18000eb5d  cmp     eax, ebx
0x18000eb5f  cmovz   ebx, edi
0x18000eb62  jmp     short loc_18000EB69
0x18000eb64  neg     rdx
0x18000eb67  sbb     ebx, ebx
0x18000eb69  mov     eax, ebx
0x18000eb6b  mov     rbx, [rsp+38h+arg_0]
0x18000eb70  add     rsp, 30h
0x18000eb74  pop     rdi
0x18000eb75  retn
```
