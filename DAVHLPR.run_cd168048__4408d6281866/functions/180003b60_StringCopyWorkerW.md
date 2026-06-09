# StringCopyWorkerW

- ea: `0x180003b60`
- end: `0x180003bd7`
- name: `StringCopyWorkerW`
- size: `119`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800048b0`
- `0x180005ce4`
- `0x180005d38`

## callees

- `0x180003b60`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v7; // rcx
  size_t i; // r10
  size_t v10; // r8
  STRSAFE_LPWSTR v11; // rdx
  HRESULT result; // eax

  v7 = 0;
  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
    ++v7;
  }
  v10 = v7 - 1;
  v11 = pszDest - 1;
  result = -2147024774;
  if ( i )
  {
    v10 = v7;
    v11 = pszDest;
    result = 0;
  }
  *v11 = 0;
  if ( pcchNewDestLength )
    *pcchNewDestLength = v10;
  return result;
}

```

## disassembly

```asm
0x180003b60  mov     [rsp+arg_0], rbx
0x180003b65  mov     r11, rcx
0x180003b68  mov     rbx, r8
0x180003b6b  xor     ecx, ecx
0x180003b6d  mov     r10, rdx
0x180003b70  test    rdx, rdx
0x180003b73  jz      short loc_180003BA6
0x180003b75  mov     rax, [rsp+arg_20]
0x180003b7a  nop     word ptr [rax+rax+00h]
0x180003b80  test    rax, rax
0x180003b83  jz      short loc_180003BA6
0x180003b85  movzx   edx, word ptr [r9]
0x180003b89  test    dx, dx
0x180003b8c  jz      short loc_180003BA6
0x180003b8e  mov     [r11], dx
0x180003b92  add     r9, 2
0x180003b96  add     r11, 2
0x180003b9a  dec     rax
0x180003b9d  inc     rcx
0x180003ba0  sub     r10, 1
0x180003ba4  jnz     short loc_180003B80
0x180003ba6  test    r10, r10
0x180003ba9  lea     r8, [rcx-1]
0x180003bad  lea     rdx, [r11-2]
0x180003bb1  mov     eax, 8007007Ah
0x180003bb6  cmovnz  r8, rcx
0x180003bba  xor     ecx, ecx
0x180003bbc  test    r10, r10
0x180003bbf  cmovnz  rdx, r11
0x180003bc3  cmovnz  eax, ecx
0x180003bc6  mov     [rdx], cx
0x180003bc9  test    rbx, rbx
0x180003bcc  jz      short loc_180003BD1
0x180003bce  mov     [rbx], r8
0x180003bd1  mov     rbx, [rsp+arg_0]
0x180003bd6  retn
```
