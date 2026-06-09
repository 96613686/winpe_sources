# StringVPrintfWorkerW

- ea: `0x14000f120`
- end: `0x14000f1a9`
- name: `StringVPrintfWorkerW`
- size: `137`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400012a0`
- `0x1400013a8`

## callees

- `0x1400011e8`
- `0x14000f120`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000f165`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000f165`

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
  if ( v10 < 0 )
    v10 = -1;
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
0x14000f120  mov     [rsp+arg_0], rbx
0x14000f125  mov     [rsp+arg_8], rsi
0x14000f12a  mov     [rsp+arg_10], rdi
0x14000f12f  push    r14
0x14000f131  sub     rsp, 30h
0x14000f135  mov     rbx, r9
0x14000f138  lea     rsi, [rdx-1]
0x14000f13c  mov     r14, rcx
0x14000f13f  xor     edi, edi
0x14000f141  call    __local_stdio_printf_options
0x14000f146  mov     r9, rbx; Format
0x14000f149  mov     r8, rsi; BufferCount
0x14000f14c  mov     rdx, r14; Buffer
0x14000f14f  mov     rcx, [rax]
0x14000f152  mov     rax, [rsp+38h+argList]
0x14000f157  or      rcx, 1; Options
0x14000f15b  mov     [rsp+38h+ArgList], rax; ArgList
0x14000f160  mov     [rsp+38h+Locale], rdi; Locale
0x14000f165  call    cs:__imp___stdio_common_vswprintf
0x14000f16b  or      ecx, 0FFFFFFFFh
0x14000f16e  test    eax, eax
0x14000f170  cmovs   eax, ecx
0x14000f173  test    eax, eax
0x14000f175  js      short loc_14000F187
0x14000f177  cdqe
0x14000f179  cmp     rax, rsi
0x14000f17c  ja      short loc_14000F187
0x14000f17e  jnz     short loc_14000F191
0x14000f180  mov     [r14+rsi*2], di
0x14000f185  jmp     short loc_14000F191
0x14000f187  mov     [r14+rsi*2], di
0x14000f18c  mov     edi, 8007007Ah
0x14000f191  mov     rbx, [rsp+38h+arg_0]
0x14000f196  mov     eax, edi
0x14000f198  mov     rdi, [rsp+38h+arg_10]
0x14000f19d  mov     rsi, [rsp+38h+arg_8]
0x14000f1a2  add     rsp, 30h
0x14000f1a6  pop     r14
0x14000f1a8  retn
```
