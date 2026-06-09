# StringVPrintfWorkerA

- ea: `0x180004798`
- end: `0x1800047e6`
- name: `StringVPrintfWorkerA`
- size: `78`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCSTR pszFormat, va_list argList)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046b4`
- `0x180004b34`
- `0x180010640`

## callees

- `0x180004798`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x1800047b4`
- `msvcrt!_vsnprintf` at `0x1800047b4`

## pseudocode

```c
HRESULT __stdcall StringVPrintfWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_LPCSTR pszFormat,
        va_list argList)
{
  size_t v5; // rbx
  int v7; // eax
  __int64 v8; // rdx
  HRESULT result; // eax

  v5 = cchDest - 1;
  v7 = _vsnprintf(pszDest, cchDest - 1, pszFormat, argList);
  if ( v7 < 0 || (v8 = v7, v7 > v5) )
  {
    pszDest[v5] = 0;
    return -2147024774;
  }
  else
  {
    result = 0;
    if ( v8 == v5 )
      pszDest[v5] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004798  mov     [rsp+arg_0], rbx
0x18000479d  push    rdi
0x18000479e  sub     rsp, 20h
0x1800047a2  lea     rbx, [rdx-1]
0x1800047a6  mov     r8, r9; Format
0x1800047a9  mov     r9, [rsp+28h+argList]; ArgList
0x1800047ae  mov     rdx, rbx; BufferCount
0x1800047b1  mov     rdi, rcx
0x1800047b4  call    cs:__imp__vsnprintf
0x1800047ba  test    eax, eax
0x1800047bc  js      short loc_1800047D2
0x1800047be  movsxd  rdx, eax
0x1800047c1  cmp     rdx, rbx
0x1800047c4  ja      short loc_1800047D2
0x1800047c6  xor     eax, eax
0x1800047c8  cmp     rdx, rbx
0x1800047cb  jnz     short loc_1800047DB
0x1800047cd  mov     [rbx+rdi], al
0x1800047d0  jmp     short loc_1800047DB
0x1800047d2  mov     byte ptr [rbx+rdi], 0
0x1800047d6  mov     eax, 8007007Ah
0x1800047db  mov     rbx, [rsp+28h+arg_0]
0x1800047e0  add     rsp, 20h
0x1800047e4  pop     rdi
0x1800047e5  retn
```
