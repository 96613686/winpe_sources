# StringVPrintfWorkerW

- ea: `0x180006c1c`
- end: `0x180006c6a`
- name: `StringVPrintfWorkerW`
- size: `78`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006130`
- `0x180006b28`

## callees

- `0x180006c1c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006c38`
- `msvcrt!_vsnwprintf` at `0x180006c38`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCWSTR pszFormat,
        va_list argList)
{
  size_t v5; // rbx
  int v7; // eax
  HRESULT v8; // ecx

  v5 = cchDest - 1;
  v7 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, argList);
  if ( v7 < 0 || v7 > v5 )
  {
    v8 = -2147024774;
LABEL_6:
    pszDest[v5] = 0;
    return v8;
  }
  v8 = 0;
  if ( v7 == v5 )
    goto LABEL_6;
  return v8;
}

```

## disassembly

```asm
0x180006c1c  mov     [rsp+arg_0], rbx
0x180006c21  push    rdi
0x180006c22  sub     rsp, 20h
0x180006c26  lea     rbx, [rdx-1]
0x180006c2a  mov     r8, r9; Format
0x180006c2d  mov     r9, [rsp+28h+argList]; Args
0x180006c32  mov     rdx, rbx; BufferCount
0x180006c35  mov     rdi, rcx
0x180006c38  call    cs:__imp__vsnwprintf
0x180006c3e  test    eax, eax
0x180006c40  js      short loc_180006C52
0x180006c42  cdqe
0x180006c44  cmp     rax, rbx
0x180006c47  ja      short loc_180006C52
0x180006c49  xor     ecx, ecx
0x180006c4b  cmp     rax, rbx
0x180006c4e  jnz     short loc_180006C5D
0x180006c50  jmp     short loc_180006C57
0x180006c52  mov     ecx, 8007007Ah
0x180006c57  xor     eax, eax
0x180006c59  mov     [rdi+rbx*2], ax
0x180006c5d  mov     rbx, [rsp+28h+arg_0]
0x180006c62  mov     eax, ecx
0x180006c64  add     rsp, 20h
0x180006c68  pop     rdi
0x180006c69  retn
```
