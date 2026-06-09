# Speller::WordLessThan(Speller::CSuggestion,Speller::CSuggestion)

- ea: `0x1800927e0`
- end: `0x180092888`
- name: `?WordLessThan@Speller@@YA_NVCSuggestion@1@0@Z`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800927e0`
- `0x18009e2da`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180092813`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180092843`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180092813`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180092843`

## pseudocode

```c
bool __fastcall Speller::WordLessThan(__int64 a1, __int64 lpString2)
{
  int v4; // eax
  int v5; // eax
  size_t v6; // r8

  v4 = CompareStringW(0x400u, 1u, (PCNZWCH)a1, *(_DWORD *)(a1 + 132), (PCNZWCH)lpString2, *(_DWORD *)(lpString2 + 132));
  if ( v4 == 1 )
    return 1;
  if ( v4 != 2 )
    return 0;
  v5 = CompareStringW(0x400u, 0, (PCNZWCH)a1, *(_DWORD *)(a1 + 132), (PCNZWCH)lpString2, *(_DWORD *)(lpString2 + 132));
  if ( v5 == 1 )
    return 1;
  if ( v5 != 2 )
    return 0;
  v6 = *(unsigned int *)(a1 + 132);
  if ( (int)v6 >= *(_DWORD *)(lpString2 + 132) )
  {
    if ( (_DWORD)v6 == *(_DWORD *)(lpString2 + 132) )
      return wcsncmp_0((const wchar_t *)a1, (const wchar_t *)lpString2, v6) < 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800927e0  mov     [rsp+arg_10], rbx
0x1800927e5  push    rdi
0x1800927e6  sub     rsp, 30h
0x1800927ea  mov     eax, [rdx+84h]
0x1800927f0  mov     rdi, rdx
0x1800927f3  mov     r9d, [rcx+84h]; cchCount1
0x1800927fa  mov     rbx, rcx
0x1800927fd  mov     [rsp+38h+cchCount2], eax; cchCount2
0x180092801  mov     r8, rcx; lpString1
0x180092804  mov     [rsp+38h+lpString2], rdx; lpString2
0x180092809  mov     ecx, 400h; Locale
0x18009280e  mov     edx, 1; dwCmpFlags
0x180092813  call    cs:__imp_CompareStringW
0x180092819  cmp     eax, 1
0x18009281c  jz      short loc_18009287B
0x18009281e  cmp     eax, 2
0x180092821  jnz     short loc_180092877
0x180092823  mov     eax, [rdi+84h]
0x180092829  mov     r8, rbx; lpString1
0x18009282c  mov     r9d, [rbx+84h]; cchCount1
0x180092833  xor     edx, edx; dwCmpFlags
0x180092835  mov     [rsp+38h+cchCount2], eax; cchCount2
0x180092839  mov     ecx, 400h; Locale
0x18009283e  mov     [rsp+38h+lpString2], rdi; lpString2
0x180092843  call    cs:__imp_CompareStringW
0x180092849  cmp     eax, 1
0x18009284c  jz      short loc_18009287B
0x18009284e  cmp     eax, 2
0x180092851  jnz     short loc_180092877
0x180092853  mov     r8d, [rbx+84h]; MaxCount
0x18009285a  cmp     r8d, [rdi+84h]
0x180092861  jl      short loc_18009287B
0x180092863  jnz     short loc_180092877
0x180092865  mov     rdx, rdi; String2
0x180092868  mov     rcx, rbx; String1
0x18009286b  call    wcsncmp_0
0x180092870  test    eax, eax
0x180092872  sets    al
0x180092875  jmp     short loc_18009287D
0x180092877  xor     al, al
0x180092879  jmp     short loc_18009287D
0x18009287b  mov     al, 1
0x18009287d  mov     rbx, [rsp+38h+arg_10]
0x180092882  add     rsp, 30h
0x180092886  pop     rdi
0x180092887  retn
```
