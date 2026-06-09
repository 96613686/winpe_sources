# StringVPrintfWorkerW

- ea: `0x180002e60`
- end: `0x180002ee4`
- name: `StringVPrintfWorkerW`
- size: `132`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b80`
- `0x180002bd0`
- `0x180002ef0`

## callees

- `0x180002e50`
- `0x180002e60`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002ea4`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x180002ea4`

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
0x180002e60  mov     [rsp+arg_0], rbx
0x180002e65  mov     [rsp+arg_8], rbp
0x180002e6a  mov     [rsp+arg_10], rsi
0x180002e6f  push    rdi
0x180002e70  sub     rsp, 30h
0x180002e74  mov     rbx, r9
0x180002e77  lea     rdi, [rdx-1]
0x180002e7b  mov     rsi, rcx
0x180002e7e  xor     ebp, ebp
0x180002e80  call    __local_stdio_printf_options
0x180002e85  mov     r9, rbx; Format
0x180002e88  mov     r8, rdi; BufferCount
0x180002e8b  mov     rdx, rsi; Buffer
0x180002e8e  mov     rcx, [rax]
0x180002e91  mov     rax, [rsp+38h+argList]
0x180002e96  or      rcx, 1; Options
0x180002e9a  mov     [rsp+38h+ArgList], rax; ArgList
0x180002e9f  mov     [rsp+38h+Locale], rbp; Locale
0x180002ea4  call    cs:__imp___stdio_common_vswprintf
0x180002eaa  test    eax, eax
0x180002eac  mov     ecx, 0FFFFFFFFh
0x180002eb1  cmovs   eax, ecx
0x180002eb4  test    eax, eax
0x180002eb6  js      short loc_180002EC6
0x180002eb8  movsxd  rcx, eax
0x180002ebb  cmp     rcx, rdi
0x180002ebe  ja      short loc_180002EC6
0x180002ec0  mov     eax, ebp
0x180002ec2  jz      short loc_180002ECB
0x180002ec4  jmp     short loc_180002ECF
0x180002ec6  mov     eax, 8007007Ah
0x180002ecb  mov     [rsi+rdi*2], bp
0x180002ecf  mov     rbx, [rsp+38h+arg_0]
0x180002ed4  mov     rbp, [rsp+38h+arg_8]
0x180002ed9  mov     rsi, [rsp+38h+arg_10]
0x180002ede  add     rsp, 30h
0x180002ee2  pop     rdi
0x180002ee3  retn
```
