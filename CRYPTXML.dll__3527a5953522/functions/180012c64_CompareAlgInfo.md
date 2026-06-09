# _CompareAlgInfo

- ea: `0x180012c64`
- end: `0x180012d65`
- name: `_CompareAlgInfo`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012a00`

## callees

- `0x180012c64`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012cb7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012ce4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012d17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012d45`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012cb7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012ce4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012d17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012d45`

## pseudocode

```c
__int64 __fastcall CompareAlgInfo(PCNZWCH *a1, int a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  const WCHAR *v9; // r8

  v3 = 0;
  v6 = a2 - 1;
  if ( !v6 )
    return CompareStringW(0, 1u, a1[1], -1, (PCNZWCH)a3, -1) == 2;
  v7 = v6 - 1;
  if ( !v7 )
  {
    v9 = a1[2];
    goto LABEL_10;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v9 = a1[4];
LABEL_10:
    LOBYTE(v3) = CompareStringW(0, 1u, v9, -1, (PCNZWCH)a3, -1) == 2;
    return v3;
  }
  if ( v8 == 1 && a1[5] && CompareStringW(0, 1u, a1[4], -1, *(PCNZWCH *)a3, -1) == 2 )
    return CompareStringW(0, 1u, a1[5], -1, *(PCNZWCH *)(a3 + 8), -1) == 2;
  return v3;
}

```

## disassembly

```asm
0x180012c64  push    rbx
0x180012c66  push    rbp
0x180012c67  push    rsi
0x180012c68  push    rdi
0x180012c69  push    r14
0x180012c6b  sub     rsp, 30h
0x180012c6f  xor     ebx, ebx
0x180012c71  mov     r14, r8
0x180012c74  mov     rbp, rcx
0x180012c77  sub     edx, 1
0x180012c7a  jz      loc_180012D2B
0x180012c80  sub     edx, 1
0x180012c83  jz      short loc_180012CFF
0x180012c85  sub     edx, 1; dwCmpFlags
0x180012c88  jz      short loc_180012CF9
0x180012c8a  cmp     edx, 1
0x180012c8d  jnz     loc_180012D57
0x180012c93  cmp     [rcx+28h], rbx
0x180012c97  jz      loc_180012D57
0x180012c9d  mov     rax, [r8]
0x180012ca0  or      edi, 0FFFFFFFFh
0x180012ca3  mov     r8, [rcx+20h]; lpString1
0x180012ca7  mov     r9d, edi; cchCount1
0x180012caa  mov     [rsp+58h+cchCount2], edi; cchCount2
0x180012cae  xor     ecx, ecx; Locale
0x180012cb0  mov     [rsp+58h+lpString2], rax; lpString2
0x180012cb5  mov     esi, edx
0x180012cb7  call    cs:__imp_CompareStringW
0x180012cbe  nop     dword ptr [rax+rax+00h]
0x180012cc3  cmp     eax, 2
0x180012cc6  jnz     loc_180012D57
0x180012ccc  mov     rax, [r14+8]
0x180012cd0  mov     r9d, edi; cchCount1
0x180012cd3  mov     r8, [rbp+28h]; lpString1
0x180012cd7  mov     edx, esi; dwCmpFlags
0x180012cd9  mov     [rsp+58h+cchCount2], edi; cchCount2
0x180012cdd  xor     ecx, ecx; Locale
0x180012cdf  mov     [rsp+58h+lpString2], rax; lpString2
0x180012ce4  call    cs:__imp_CompareStringW
0x180012ceb  nop     dword ptr [rax+rax+00h]
0x180012cf0  cmp     eax, 2
0x180012cf3  jnz     short loc_180012D57
0x180012cf5  mov     ebx, esi
0x180012cf7  jmp     short loc_180012D57
0x180012cf9  mov     r8, [rcx+20h]
0x180012cfd  jmp     short loc_180012D03
0x180012cff  mov     r8, [rcx+10h]; lpString1
0x180012d03  or      edi, 0FFFFFFFFh
0x180012d06  xor     ecx, ecx; Locale
0x180012d08  mov     [rsp+58h+cchCount2], edi; cchCount2
0x180012d0c  mov     r9d, edi; cchCount1
0x180012d0f  mov     [rsp+58h+lpString2], r14; lpString2
0x180012d14  lea     edx, [rdi+2]; dwCmpFlags
0x180012d17  call    cs:__imp_CompareStringW
0x180012d1e  nop     dword ptr [rax+rax+00h]
0x180012d23  cmp     eax, 2
0x180012d26  setz    bl
0x180012d29  jmp     short loc_180012D57
0x180012d2b  mov     r8, [rcx+8]; lpString1
0x180012d2f  or      edi, 0FFFFFFFFh
0x180012d32  mov     [rsp+58h+cchCount2], edi; cchCount2
0x180012d36  mov     r9d, edi; cchCount1
0x180012d39  xor     ecx, ecx; Locale
0x180012d3b  mov     [rsp+58h+lpString2], r14; lpString2
0x180012d40  lea     esi, [rdi+2]
0x180012d43  mov     edx, esi; dwCmpFlags
0x180012d45  call    cs:__imp_CompareStringW
0x180012d4c  nop     dword ptr [rax+rax+00h]
0x180012d51  cmp     eax, 2
0x180012d54  cmovz   ebx, esi
0x180012d57  mov     eax, ebx
0x180012d59  add     rsp, 30h
0x180012d5d  pop     r14
0x180012d5f  pop     rdi
0x180012d60  pop     rsi
0x180012d61  pop     rbp
0x180012d62  pop     rbx
0x180012d63  retn
```
