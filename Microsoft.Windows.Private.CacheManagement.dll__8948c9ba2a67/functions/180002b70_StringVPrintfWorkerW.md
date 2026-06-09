# StringVPrintfWorkerW

- ea: `0x180002b70`
- end: `0x180002bf4`
- name: `StringVPrintfWorkerW`
- size: `132`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002720`
- `0x180002c00`
- `0x18000f5f0`
- `0x1800128d0`

## callees

- `0x180002b60`
- `0x180002b70`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002bb4`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002bb4`

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
0x180002b70  mov     [rsp+arg_0], rbx
0x180002b75  mov     [rsp+arg_8], rbp
0x180002b7a  mov     [rsp+arg_10], rsi
0x180002b7f  push    rdi
0x180002b80  sub     rsp, 30h
0x180002b84  mov     rbx, r9
0x180002b87  lea     rdi, [rdx-1]
0x180002b8b  mov     rsi, rcx
0x180002b8e  xor     ebp, ebp
0x180002b90  call    __local_stdio_printf_options
0x180002b95  mov     r9, rbx; Format
0x180002b98  mov     r8, rdi; BufferCount
0x180002b9b  mov     rdx, rsi; Buffer
0x180002b9e  mov     rcx, [rax]
0x180002ba1  mov     rax, [rsp+38h+argList]
0x180002ba6  or      rcx, 1; Options
0x180002baa  mov     [rsp+38h+ArgList], rax; ArgList
0x180002baf  mov     [rsp+38h+Locale], rbp; Locale
0x180002bb4  call    cs:__imp___stdio_common_vswprintf
0x180002bba  test    eax, eax
0x180002bbc  mov     ecx, 0FFFFFFFFh
0x180002bc1  cmovs   eax, ecx
0x180002bc4  test    eax, eax
0x180002bc6  js      short loc_180002BD6
0x180002bc8  movsxd  rcx, eax
0x180002bcb  cmp     rcx, rdi
0x180002bce  ja      short loc_180002BD6
0x180002bd0  mov     eax, ebp
0x180002bd2  jz      short loc_180002BDB
0x180002bd4  jmp     short loc_180002BDF
0x180002bd6  mov     eax, 8007007Ah
0x180002bdb  mov     [rsi+rdi*2], bp
0x180002bdf  mov     rbx, [rsp+38h+arg_0]
0x180002be4  mov     rbp, [rsp+38h+arg_8]
0x180002be9  mov     rsi, [rsp+38h+arg_10]
0x180002bee  add     rsp, 30h
0x180002bf2  pop     rdi
0x180002bf3  retn
```
