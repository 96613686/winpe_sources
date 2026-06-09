# StringCchCatW

- ea: `0x180008878`
- end: `0x180008933`
- name: `StringCchCatW`
- size: `187`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004044`
- `0x1800079e0`
- `0x18000c508`
- `0x18000c8e4`

## callees

- `0x180008878`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // r10
  size_t v5; // r11
  STRSAFE_LPWSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // rax
  size_t v9; // r9
  wchar_t *i; // rax
  wchar_t *v11; // rcx

  v3 = 2147483646;
  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v5 = cchDest;
  v6 = pszDest;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (cchDest - v5) & -(__int64)(v5 != 0);
  if ( v5 )
  {
    v9 = cchDest - v8;
    for ( i = &pszDest[v8]; v9; --v9 )
    {
      if ( !v3 )
        break;
      if ( !*pszSrc )
        break;
      *i++ = *pszSrc++;
      --v3;
    }
    v11 = i - 1;
    if ( v9 )
      v11 = i;
    v7 = v9 == 0 ? 0x8007007A : 0;
    *v11 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180008878  mov     [rsp+arg_0], rbx
0x18000887d  mov     [rsp+arg_8], rdi
0x180008882  lea     rax, [rdx-1]
0x180008886  mov     r10d, 7FFFFFFEh
0x18000888c  mov     r9, rdx
0x18000888f  mov     rbx, rcx
0x180008892  cmp     rax, r10
0x180008895  ja      loc_180008921
0x18000889b  mov     r11, rdx
0x18000889e  mov     rax, rcx
0x1800088a1  xor     edi, edi
0x1800088a3  cmp     [rax], di
0x1800088a6  jz      short loc_1800088B2
0x1800088a8  add     rax, 2
0x1800088ac  sub     r11, 1
0x1800088b0  jnz     short loc_1800088A3
0x1800088b2  mov     rax, r11
0x1800088b5  mov     rcx, r9
0x1800088b8  neg     rax
0x1800088bb  mov     rax, r11
0x1800088be  sbb     edx, edx
0x1800088c0  sub     rcx, r11
0x1800088c3  not     edx
0x1800088c5  and     edx, 80070057h
0x1800088cb  neg     rax
0x1800088ce  sbb     rax, rax
0x1800088d1  and     rax, rcx
0x1800088d4  test    r11, r11
0x1800088d7  jz      short loc_180008926
0x1800088d9  sub     r9, rax
0x1800088dc  lea     rax, [rbx+rax*2]
0x1800088e0  jz      short loc_180008904
0x1800088e2  test    r10, r10
0x1800088e5  jz      short loc_180008904
0x1800088e7  movzx   ecx, word ptr [r8]
0x1800088eb  test    cx, cx
0x1800088ee  jz      short loc_180008904
0x1800088f0  mov     [rax], cx
0x1800088f3  add     r8, 2
0x1800088f7  add     rax, 2
0x1800088fb  dec     r10
0x1800088fe  sub     r9, 1
0x180008902  jnz     short loc_1800088E2
0x180008904  test    r9, r9
0x180008907  lea     rcx, [rax-2]
0x18000890b  cmovnz  rcx, rax
0x18000890f  neg     r9
0x180008912  sbb     edx, edx
0x180008914  not     edx
0x180008916  and     edx, 8007007Ah
0x18000891c  mov     [rcx], di
0x18000891f  jmp     short loc_180008926
0x180008921  mov     edx, 80070057h
0x180008926  mov     rbx, [rsp+arg_0]
0x18000892b  mov     eax, edx
0x18000892d  mov     rdi, [rsp+arg_8]
0x180008932  retn
```
