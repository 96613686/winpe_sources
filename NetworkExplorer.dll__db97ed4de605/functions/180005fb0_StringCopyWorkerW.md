# StringCopyWorkerW

- ea: `0x180005fb0`
- end: `0x18000602a`
- name: `StringCopyWorkerW`
- size: `122`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bdbc`

## callees

- `0x180005fb0`

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
  size_t v8; // r10
  __int64 i; // rax
  size_t v10; // r8
  STRSAFE_LPWSTR v11; // rdx
  HRESULT result; // eax

  v7 = 0;
  v8 = cchDest;
  for ( i = 2147483646; v8; --v8 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
    ++v7;
  }
  v10 = v7 - 1;
  v11 = pszDest - 1;
  result = -2147024774;
  if ( v8 )
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
0x180005fb0  mov     [rsp+arg_0], rbx
0x180005fb5  mov     r11, rcx
0x180005fb8  mov     rbx, r8
0x180005fbb  xor     ecx, ecx
0x180005fbd  mov     r10, rdx
0x180005fc0  mov     eax, 7FFFFFFEh
0x180005fc5  test    rdx, rdx
0x180005fc8  jz      short loc_180005FF7
0x180005fca  nop     word ptr [rax+rax+00h]
0x180005fd0  test    rax, rax
0x180005fd3  jz      short loc_180005FF7
0x180005fd5  movzx   r8d, word ptr [r9]
0x180005fd9  test    r8w, r8w
0x180005fdd  jz      short loc_180005FF7
0x180005fdf  mov     [r11], r8w
0x180005fe3  add     r9, 2
0x180005fe7  add     r11, 2
0x180005feb  dec     rax
0x180005fee  inc     rcx
0x180005ff1  sub     r10, 1
0x180005ff5  jnz     short loc_180005FD0
0x180005ff7  test    r10, r10
0x180005ffa  lea     r8, [rcx-1]
0x180005ffe  lea     rdx, [r11-2]
0x180006002  mov     eax, 8007007Ah
0x180006007  cmovnz  r8, rcx
0x18000600b  xor     ecx, ecx
0x18000600d  test    r10, r10
0x180006010  cmovnz  rdx, r11
0x180006014  cmovnz  eax, ecx
0x180006017  mov     [rdx], cx
0x18000601a  test    rbx, rbx
0x18000601d  jnz     short loc_180006025
0x18000601f  mov     rbx, [rsp+arg_0]
0x180006024  retn
0x180006025  mov     [rbx], r8
0x180006028  jmp     short loc_18000601F
```
