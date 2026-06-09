# RtlStringCbPrintfW

- ea: `0x140001214`
- end: `0x14000128e`
- name: `RtlStringCbPrintfW`
- size: `122`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000337c`
- `0x140018804`
- `0x140019058`
- `0x14001e1e0`
- `0x14001ec38`

## callees

- `0x140001214`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x14000124b`
- `ntoskrnl!_vsnwprintf` at `0x14000124b`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  size_t v4; // rdx
  NTSTATUS result; // eax
  unsigned __int64 v6; // rdi
  int v7; // eax
  bool v8; // zf
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v4 = cbDest >> 1;
  if ( !v4 )
    return -1073741811;
  if ( v4 <= 0x7FFFFFFF )
  {
    v6 = v4 - 1;
    v7 = _vsnwprintf(pszDest, v4 - 1, pszFormat, Args);
    if ( v7 < 0 || (v8 = v7 == v6, v7 > v6) )
    {
      pszDest[v6] = 0;
      return -2147483643;
    }
    else
    {
      result = 0;
      if ( v8 )
        pszDest[v6] = 0;
    }
  }
  else
  {
    result = -1073741811;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001214  mov     [rsp+arg_10], r8
0x140001219  mov     qword ptr [rsp+Args], r9
0x14000121e  push    rbx
0x14000121f  push    rsi
0x140001220  push    rdi
0x140001221  sub     rsp, 30h
0x140001225  xor     ebx, ebx
0x140001227  mov     rsi, rcx
0x14000122a  shr     rdx, 1
0x14000122d  jz      short loc_140001278
0x14000122f  cmp     rdx, 7FFFFFFFh
0x140001236  jbe     short loc_14000123F
0x140001238  mov     eax, 0C000000Dh
0x14000123d  jmp     short loc_140001282
0x14000123f  lea     rdi, [rdx-1]
0x140001243  mov     rdx, rdi; Count
0x140001246  lea     r9, [rsp+48h+Args]; Args
0x14000124b  call    cs:__imp__vsnwprintf
0x140001252  nop     dword ptr [rax+rax+00h]
0x140001257  test    eax, eax
0x140001259  js      short loc_14000126D
0x14000125b  movsxd  rcx, eax
0x14000125e  cmp     rcx, rdi
0x140001261  ja      short loc_14000126D
0x140001263  mov     eax, ebx
0x140001265  jnz     short loc_140001285
0x140001267  mov     [rsi+rdi*2], bx
0x14000126b  jmp     short loc_140001285
0x14000126d  mov     [rsi+rdi*2], bx
0x140001271  mov     eax, 80000005h
0x140001276  jmp     short loc_140001285
0x140001278  mov     eax, 0C000000Dh
0x14000127d  test    rdx, rdx
0x140001280  jz      short loc_140001285
0x140001282  mov     [rcx], bx
0x140001285  add     rsp, 30h
0x140001289  pop     rdi
0x14000128a  pop     rsi
0x14000128b  pop     rbx
0x14000128c  retn
```
