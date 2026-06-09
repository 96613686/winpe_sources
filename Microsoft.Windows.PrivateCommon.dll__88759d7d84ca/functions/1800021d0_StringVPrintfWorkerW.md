# StringVPrintfWorkerW

- ea: `0x1800021d0`
- end: `0x180002254`
- name: `StringVPrintfWorkerW`
- size: `132`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002180`
- `0x180002260`

## callees

- `0x1800010a0`
- `0x1800021d0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002214`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002214`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCWSTR pszFormat,
        va_list argList)
{
  size_t v6; // rdi
  unsigned __int64 v8; // rcx
  int v9; // eax
  bool v10; // zf
  HRESULT result; // eax

  v6 = cchDest - 1;
  v8 = *_local_stdio_printf_options();
  v9 = __stdio_common_vswprintf(v8 | 1, pszDest, v6, pszFormat, 0, argList);
  if ( v9 < 0 )
    v9 = -1;
  if ( v9 < 0 || (v10 = v9 == v6, v9 > v6) )
  {
    result = -2147024774;
    goto LABEL_8;
  }
  result = 0;
  if ( v10 )
LABEL_8:
    pszDest[v6] = 0;
  return result;
}

```

## disassembly

```asm
0x1800021d0  mov     [rsp+arg_0], rbx
0x1800021d5  mov     [rsp+arg_8], rbp
0x1800021da  mov     [rsp+arg_10], rsi
0x1800021df  push    rdi
0x1800021e0  sub     rsp, 30h
0x1800021e4  mov     rbx, r9
0x1800021e7  lea     rdi, [rdx-1]
0x1800021eb  mov     rsi, rcx
0x1800021ee  xor     ebp, ebp
0x1800021f0  call    __local_stdio_printf_options
0x1800021f5  mov     r9, rbx; Format
0x1800021f8  mov     r8, rdi; BufferCount
0x1800021fb  mov     rdx, rsi; Buffer
0x1800021fe  mov     rcx, [rax]
0x180002201  mov     rax, [rsp+38h+argList]
0x180002206  or      rcx, 1; Options
0x18000220a  mov     [rsp+38h+ArgList], rax; ArgList
0x18000220f  mov     [rsp+38h+Locale], rbp; Locale
0x180002214  call    cs:__imp___stdio_common_vswprintf
0x18000221a  test    eax, eax
0x18000221c  mov     ecx, 0FFFFFFFFh
0x180002221  cmovs   eax, ecx
0x180002224  test    eax, eax
0x180002226  js      short loc_180002236
0x180002228  movsxd  rcx, eax
0x18000222b  cmp     rcx, rdi
0x18000222e  ja      short loc_180002236
0x180002230  mov     eax, ebp
0x180002232  jz      short loc_18000223B
0x180002234  jmp     short loc_18000223F
0x180002236  mov     eax, 8007007Ah
0x18000223b  mov     [rsi+rdi*2], bp
0x18000223f  mov     rbx, [rsp+38h+arg_0]
0x180002244  mov     rbp, [rsp+38h+arg_8]
0x180002249  mov     rsi, [rsp+38h+arg_10]
0x18000224e  add     rsp, 30h
0x180002252  pop     rdi
0x180002253  retn
```
