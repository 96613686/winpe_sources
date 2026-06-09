# StringVPrintfWorkerW

- ea: `0x18009e100`
- end: `0x18009e188`
- name: `StringVPrintfWorkerW`
- size: `136`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009c8cc`
- `0x1800a07cc`

## callees

- `0x18009e100`
- `0x18009e90c`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x18009e145`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x18009e145`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCWSTR pszFormat,
        va_list argList)
{
  size_t v6; // rsi
  HRESULT v8; // edi
  unsigned __int64 v9; // rcx
  int v10; // eax

  v6 = cchDest - 1;
  v8 = 0;
  v9 = *_local_stdio_printf_options();
  v10 = __stdio_common_vswprintf(v9 | 1, pszDest, v6, pszFormat, 0, argList);
  if ( v10 < 0 || v10 > v6 )
  {
    pszDest[v6] = 0;
    return -2147024774;
  }
  else if ( v10 == v6 )
  {
    pszDest[v6] = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18009e100  mov     [rsp+arg_0], rbx
0x18009e105  mov     [rsp+arg_8], rsi
0x18009e10a  mov     [rsp+arg_10], rdi
0x18009e10f  push    r14
0x18009e111  sub     rsp, 30h
0x18009e115  mov     rbx, r9
0x18009e118  lea     rsi, [rdx-1]
0x18009e11c  mov     r14, rcx
0x18009e11f  xor     edi, edi
0x18009e121  call    __local_stdio_printf_options
0x18009e126  mov     r9, rbx; Format
0x18009e129  mov     r8, rsi; BufferCount
0x18009e12c  mov     rdx, r14; Buffer
0x18009e12f  mov     rcx, [rax]
0x18009e132  mov     rax, [rsp+38h+argList]
0x18009e137  or      rcx, 1; Options
0x18009e13b  mov     [rsp+38h+ArgList], rax; ArgList
0x18009e140  mov     [rsp+38h+Locale], rdi; Locale
0x18009e145  call    cs:__imp___stdio_common_vswprintf
0x18009e14c  nop     dword ptr [rax+rax+00h]
0x18009e151  test    eax, eax
0x18009e153  js      short loc_18009E165
0x18009e155  cdqe
0x18009e157  cmp     rax, rsi
0x18009e15a  ja      short loc_18009E165
0x18009e15c  jnz     short loc_18009E16F
0x18009e15e  mov     [r14+rsi*2], di
0x18009e163  jmp     short loc_18009E16F
0x18009e165  mov     [r14+rsi*2], di
0x18009e16a  mov     edi, 8007007Ah
0x18009e16f  mov     rbx, [rsp+38h+arg_0]
0x18009e174  mov     eax, edi
0x18009e176  mov     rdi, [rsp+38h+arg_10]
0x18009e17b  mov     rsi, [rsp+38h+arg_8]
0x18009e180  add     rsp, 30h
0x18009e184  pop     r14
0x18009e186  retn
```
