# _GetLegacyAlgId

- ea: `0x180017b84`
- end: `0x180017bc7`
- name: `_GetLegacyAlgId`
- size: `67`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014854`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017ba6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180017ba6`

## pseudocode

```c
__int64 __fastcall GetLegacyAlgId(PCNZWCH lpString1)
{
  int v1; // eax
  unsigned int v2; // ecx

  v1 = CompareStringW(0, 1u, lpString1, -1, L"SHA1", -1);
  v2 = 0;
  if ( v1 == 2 )
    return 32772;
  return v2;
}

```

## disassembly

```asm
0x180017b84  sub     rsp, 38h
0x180017b88  or      r9d, 0FFFFFFFFh; cchCount1
0x180017b8c  lea     rax, aSha1; "SHA1"
0x180017b93  mov     r8, rcx; lpString1
0x180017b96  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180017b9b  xor     ecx, ecx; Locale
0x180017b9d  mov     [rsp+38h+lpString2], rax; lpString2
0x180017ba2  lea     edx, [r9+2]; dwCmpFlags
0x180017ba6  call    cs:__imp_CompareStringW
0x180017bad  nop     dword ptr [rax+rax+00h]
0x180017bb2  xor     ecx, ecx
0x180017bb4  mov     edx, 8004h
0x180017bb9  cmp     eax, 2
0x180017bbc  cmovz   ecx, edx
0x180017bbf  mov     eax, ecx
0x180017bc1  add     rsp, 38h
0x180017bc5  retn
```
