# _anonymous_namespace_::ValidateSamePath_0

- ea: `0x18002d698`
- end: `0x18002d77f`
- name: `_anonymous_namespace_::ValidateSamePath_0`
- size: `231`
- prototype: `__int64 __fastcall(wchar_t *String1, wchar_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d780`
- `0x18002dfd0`

## callees

- `0x18002d698`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18002d755`
- `KERNEL32!CompareStringOrdinal` at `0x18002d755`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d6dc`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d6f4`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d6dc`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d6f4`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002d6b7`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002d6c3`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002d6b7`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002d6c3`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ValidateSamePath_0(wchar_t *String1, wchar_t *a2)
{
  size_t v4; // rdi
  size_t v5; // rsi
  int v6; // ebx
  int v7; // eax
  bool v8; // cf
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  size_t v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rcx
  size_t v15; // rsi

  v4 = wcslen(String1);
  v5 = wcslen(a2);
  v6 = wcsncmp(String1, L"\\\\?\\", 4u);
  v7 = wcsncmp(a2, L"\\\\?\\", 4u);
  v8 = v6 != 0;
  v9 = 1;
  v10 = v8 ? 0 : 4;
  v11 = v10;
  if ( String1[v4 - 1] == 92 )
    v11 = v10 + 1;
  v12 = v4 - v11;
  v13 = v7 == 0 ? 4 : 0;
  v14 = v13;
  if ( a2[v5 - 1] == 92 )
    v14 = v13 + 1;
  v15 = v5 - v14;
  if ( v12 == v15 && CompareStringOrdinal(&String1[v10], v12, &a2[v13], v15, 1) == 2 )
    return 0;
  return v9;
}

```

## disassembly

```asm
0x18002d698  mov     rax, rsp
0x18002d69b  mov     [rax+8], rbx
0x18002d69f  mov     [rax+10h], rsi
0x18002d6a3  mov     [rax+18h], rdi
0x18002d6a7  mov     [rax+20h], r14
0x18002d6ab  push    r15
0x18002d6ad  sub     rsp, 30h
0x18002d6b1  mov     r14, rdx
0x18002d6b4  mov     r15, rcx
0x18002d6b7  call    cs:__imp_wcslen
0x18002d6bd  mov     rcx, r14; String
0x18002d6c0  mov     rdi, rax
0x18002d6c3  call    cs:__imp_wcslen
0x18002d6c9  mov     r8d, 4; MaxCount
0x18002d6cf  lea     rdx, asc_180056FA0; "\\\\?\\"
0x18002d6d6  mov     rcx, r15; String1
0x18002d6d9  mov     rsi, rax
0x18002d6dc  call    cs:__imp_wcsncmp
0x18002d6e2  mov     r8d, 4; MaxCount
0x18002d6e8  lea     rdx, asc_180056FA0; "\\\\?\\"
0x18002d6ef  mov     rcx, r14; String1
0x18002d6f2  mov     ebx, eax
0x18002d6f4  call    cs:__imp_wcsncmp
0x18002d6fa  neg     ebx
0x18002d6fc  mov     ebx, 1
0x18002d701  sbb     r9, r9
0x18002d704  not     r9
0x18002d707  and     r9d, 4
0x18002d70b  cmp     word ptr [r15+rdi*2-2], 5Ch ; '\'
0x18002d712  mov     edx, r9d
0x18002d715  lea     rcx, [r9+1]
0x18002d719  cmovz   rdx, rcx
0x18002d71d  sub     rdi, rdx
0x18002d720  neg     eax
0x18002d722  sbb     rdx, rdx
0x18002d725  not     rdx
0x18002d728  and     edx, 4
0x18002d72b  cmp     word ptr [r14+rsi*2-2], 5Ch ; '\'
0x18002d732  mov     ecx, edx
0x18002d734  lea     rax, [rdx+1]
0x18002d738  cmovz   rcx, rax
0x18002d73c  sub     rsi, rcx
0x18002d73f  cmp     rdi, rsi
0x18002d742  jnz     short loc_18002D762
0x18002d744  lea     r8, [r14+rdx*2]; lpString2
0x18002d748  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x18002d74c  lea     rcx, [r15+r9*2]; lpString1
0x18002d750  mov     edx, edi; cchCount1
0x18002d752  mov     r9d, esi; cchCount2
0x18002d755  call    cs:__imp_CompareStringOrdinal
0x18002d75b  cmp     eax, 2
0x18002d75e  jnz     short loc_18002D762
0x18002d760  xor     ebx, ebx
0x18002d762  mov     rsi, [rsp+38h+arg_8]
0x18002d767  mov     eax, ebx
0x18002d769  mov     rbx, [rsp+38h+arg_0]
0x18002d76e  mov     rdi, [rsp+38h+arg_10]
0x18002d773  mov     r14, [rsp+38h+arg_18]
0x18002d778  add     rsp, 30h
0x18002d77c  pop     r15
0x18002d77e  retn
```
