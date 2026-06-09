# StringExHandleOtherFlagsW

- ea: `0x180005f4c`
- end: `0x180005fe9`
- name: `StringExHandleOtherFlagsW`
- size: `157`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, size_t cchOriginalDestLength, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d88`

## callees

- `0x180005f4c`
- `0x1800060d9`

## pseudocode

```c
HRESULT __stdcall StringExHandleOtherFlagsW(
        STRSAFE_LPWSTR pszDest,
        size_t cbDest,
        size_t cchOriginalDestLength,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  size_t v6; // rdi
  wchar_t *v10; // rcx

  v6 = cbDest >> 1;
  if ( cbDest >> 1 && (dwFlags & 0x1000) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pszDest = 0;
    *pcchRemaining = v6;
  }
  if ( (dwFlags & 0x400) == 0 )
  {
LABEL_7:
    if ( !v6 )
      return 0;
    goto LABEL_8;
  }
  memset_0(pszDest, (unsigned __int8)dwFlags, cbDest);
  if ( !(_BYTE)dwFlags )
  {
    *ppszDestEnd = pszDest;
    *pcchRemaining = v6;
    goto LABEL_7;
  }
  if ( !v6 )
    return 0;
  *pcchRemaining = 1;
  v10 = &pszDest[v6 - 1];
  *ppszDestEnd = v10;
  *v10 = 0;
LABEL_8:
  if ( (dwFlags & 0x800) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pszDest = 0;
    *pcchRemaining = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180005f4c  push    rbx
0x180005f4e  push    rsi
0x180005f4f  push    rdi
0x180005f50  push    r14
0x180005f52  push    r15
0x180005f54  sub     rsp, 20h
0x180005f58  mov     r15, [rsp+48h+pcchRemaining]
0x180005f5d  mov     rdi, rdx
0x180005f60  shr     rdi, 1
0x180005f63  mov     r14, r9
0x180005f66  mov     rsi, rcx
0x180005f69  jz      short loc_180005F80
0x180005f6b  test    [rsp+48h+dwFlags], 1000h
0x180005f73  jz      short loc_180005F80
0x180005f75  xor     eax, eax
0x180005f77  mov     [r9], rcx
0x180005f7a  mov     [rcx], ax
0x180005f7d  mov     [r15], rdi
0x180005f80  test    [rsp+48h+dwFlags], 400h
0x180005f88  jz      short loc_180005FA3
0x180005f8a  movzx   ebx, byte ptr [rsp+48h+dwFlags]
0x180005f8f  mov     r8, rdx; Size
0x180005f92  mov     edx, ebx; Val
0x180005f94  call    memset_0
0x180005f99  test    ebx, ebx
0x180005f9b  jnz     short loc_180005FCB
0x180005f9d  mov     [r14], rsi
0x180005fa0  mov     [r15], rdi
0x180005fa3  test    rdi, rdi
0x180005fa6  jz      short loc_180005FBD
0x180005fa8  test    [rsp+48h+dwFlags], 800h
0x180005fb0  jz      short loc_180005FBD
0x180005fb2  xor     eax, eax
0x180005fb4  mov     [r14], rsi
0x180005fb7  mov     [rsi], ax
0x180005fba  mov     [r15], rdi
0x180005fbd  xor     eax, eax
0x180005fbf  add     rsp, 20h
0x180005fc3  pop     r15
0x180005fc5  pop     r14
0x180005fc7  pop     rdi
0x180005fc8  pop     rsi
0x180005fc9  pop     rbx
0x180005fca  retn
0x180005fcb  test    rdi, rdi
0x180005fce  jz      short loc_180005FBD
0x180005fd0  lea     rcx, [rsi-2]
0x180005fd4  mov     qword ptr [r15], 1
0x180005fdb  lea     rcx, [rcx+rdi*2]
0x180005fdf  xor     eax, eax
0x180005fe1  mov     [r14], rcx
0x180005fe4  mov     [rcx], ax
0x180005fe7  jmp     short loc_180005FA8
```
