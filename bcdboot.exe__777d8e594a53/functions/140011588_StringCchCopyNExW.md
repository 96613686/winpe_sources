# StringCchCopyNExW

- ea: `0x140011588`
- end: `0x140011667`
- name: `StringCchCopyNExW`
- size: `223`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002c14`
- `0x140011b18`

## callees

- `0x140011588`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNExW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  HRESULT v10; // edx
  size_t v11; // r8
  STRSAFE_LPWSTR v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // r9
  STRSAFE_LPWSTR v15; // rcx

  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF || cchToCopy >= 0x7FFFFFFF )
  {
    v10 = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v11 = cchDest;
    v12 = pszDest;
    v13 = 0;
    do
    {
      if ( !cchToCopy )
        break;
      if ( !*pszSrc )
        break;
      *v12++ = *pszSrc++;
      --cchToCopy;
      ++v13;
      --v11;
    }
    while ( v11 );
    v14 = v13 - 1;
    if ( v11 )
      v14 = v13;
    v15 = v12 - 1;
    v10 = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v15 = v12;
    *v15 = 0;
    if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024774 )
    {
      if ( ppszDestEnd )
        *ppszDestEnd = &pszDest[v14];
      if ( pcchRemaining )
        *pcchRemaining = cchDest - v14;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140011588  mov     [rsp+arg_0], rbx
0x14001158d  mov     [rsp+arg_8], rdi
0x140011592  xor     edi, edi
0x140011594  mov     rax, r8
0x140011597  mov     r10, rdx
0x14001159a  mov     r11, rcx
0x14001159d  test    rdx, rdx
0x1400115a0  jz      loc_14001164C
0x1400115a6  mov     ecx, 7FFFFFFFh
0x1400115ab  cmp     rdx, rcx
0x1400115ae  jbe     short loc_1400115BA
0x1400115b0  mov     edx, 80070057h
0x1400115b5  jmp     loc_140011656
0x1400115ba  cmp     r9, rcx
0x1400115bd  jnb     short loc_1400115B0
0x1400115bf  mov     r8, r10
0x1400115c2  mov     rbx, r11
0x1400115c5  mov     rcx, rdi
0x1400115c8  test    r9, r9
0x1400115cb  jz      short loc_1400115EC
0x1400115cd  movzx   edx, word ptr [rax]
0x1400115d0  test    dx, dx
0x1400115d3  jz      short loc_1400115EC
0x1400115d5  mov     [rbx], dx
0x1400115d8  add     rax, 2
0x1400115dc  add     rbx, 2
0x1400115e0  dec     r9
0x1400115e3  inc     rcx
0x1400115e6  sub     r8, 1
0x1400115ea  jnz     short loc_1400115C8
0x1400115ec  test    r8, r8
0x1400115ef  lea     r9, [rcx-1]
0x1400115f3  mov     rax, r8
0x1400115f6  cmovnz  r9, rcx
0x1400115fa  neg     rax
0x1400115fd  lea     rcx, [rbx-2]
0x140011601  sbb     edx, edx
0x140011603  not     edx
0x140011605  and     edx, 8007007Ah
0x14001160b  test    r8, r8
0x14001160e  cmovnz  rcx, rbx
0x140011612  mov     [rcx], di
0x140011615  mov     ecx, 80000000h
0x14001161a  lea     eax, [rdx+rcx]
0x14001161d  test    ecx, eax
0x14001161f  jnz     short loc_140011629
0x140011621  cmp     edx, 8007007Ah
0x140011627  jnz     short loc_14001165A
0x140011629  mov     rcx, [rsp+arg_20]
0x14001162e  test    rcx, rcx
0x140011631  jz      short loc_14001163A
0x140011633  lea     rax, [r11+r9*2]
0x140011637  mov     [rcx], rax
0x14001163a  mov     rax, [rsp+arg_28]
0x14001163f  test    rax, rax
0x140011642  jz      short loc_14001165A
0x140011644  sub     r10, r9
0x140011647  mov     [rax], r10
0x14001164a  jmp     short loc_14001165A
0x14001164c  mov     edx, 80070057h
0x140011651  test    r10, r10
0x140011654  jz      short loc_14001165A
0x140011656  mov     [r11], di
0x14001165a  mov     rbx, [rsp+arg_0]
0x14001165f  mov     eax, edx
0x140011661  mov     rdi, [rsp+arg_8]
0x140011666  retn
```
