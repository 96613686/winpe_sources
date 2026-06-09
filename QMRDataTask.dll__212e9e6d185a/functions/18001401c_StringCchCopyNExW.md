# StringCchCopyNExW

- ea: `0x18001401c`
- end: `0x1800140fb`
- name: `StringCchCopyNExW`
- size: `223`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001331c`

## callees

- `0x18001401c`

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
0x18001401c  mov     [rsp+arg_0], rbx
0x180014021  mov     [rsp+arg_8], rdi
0x180014026  xor     edi, edi
0x180014028  mov     rax, r8
0x18001402b  mov     r10, rdx
0x18001402e  mov     r11, rcx
0x180014031  test    rdx, rdx
0x180014034  jz      loc_1800140E0
0x18001403a  mov     ecx, 7FFFFFFFh
0x18001403f  cmp     rdx, rcx
0x180014042  jbe     short loc_18001404E
0x180014044  mov     edx, 80070057h
0x180014049  jmp     loc_1800140EA
0x18001404e  cmp     r9, rcx
0x180014051  jnb     short loc_180014044
0x180014053  mov     r8, r10
0x180014056  mov     rbx, r11
0x180014059  mov     rcx, rdi
0x18001405c  test    r9, r9
0x18001405f  jz      short loc_180014080
0x180014061  movzx   edx, word ptr [rax]
0x180014064  test    dx, dx
0x180014067  jz      short loc_180014080
0x180014069  mov     [rbx], dx
0x18001406c  add     rax, 2
0x180014070  add     rbx, 2
0x180014074  dec     r9
0x180014077  inc     rcx
0x18001407a  sub     r8, 1
0x18001407e  jnz     short loc_18001405C
0x180014080  test    r8, r8
0x180014083  lea     r9, [rcx-1]
0x180014087  mov     rax, r8
0x18001408a  cmovnz  r9, rcx
0x18001408e  neg     rax
0x180014091  lea     rcx, [rbx-2]
0x180014095  sbb     edx, edx
0x180014097  not     edx
0x180014099  and     edx, 8007007Ah
0x18001409f  test    r8, r8
0x1800140a2  cmovnz  rcx, rbx
0x1800140a6  mov     [rcx], di
0x1800140a9  mov     ecx, 80000000h
0x1800140ae  lea     eax, [rdx+rcx]
0x1800140b1  test    ecx, eax
0x1800140b3  jnz     short loc_1800140BD
0x1800140b5  cmp     edx, 8007007Ah
0x1800140bb  jnz     short loc_1800140EE
0x1800140bd  mov     rcx, [rsp+arg_20]
0x1800140c2  test    rcx, rcx
0x1800140c5  jz      short loc_1800140CE
0x1800140c7  lea     rax, [r11+r9*2]
0x1800140cb  mov     [rcx], rax
0x1800140ce  mov     rax, [rsp+arg_28]
0x1800140d3  test    rax, rax
0x1800140d6  jz      short loc_1800140EE
0x1800140d8  sub     r10, r9
0x1800140db  mov     [rax], r10
0x1800140de  jmp     short loc_1800140EE
0x1800140e0  mov     edx, 80070057h
0x1800140e5  test    r10, r10
0x1800140e8  jz      short loc_1800140EE
0x1800140ea  mov     [r11], di
0x1800140ee  mov     rbx, [rsp+arg_0]
0x1800140f3  mov     eax, edx
0x1800140f5  mov     rdi, [rsp+arg_8]
0x1800140fa  retn
```
