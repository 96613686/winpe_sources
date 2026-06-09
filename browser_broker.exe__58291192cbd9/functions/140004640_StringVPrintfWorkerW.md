# StringVPrintfWorkerW

- ea: `0x140004640`
- end: `0x14000468d`
- name: `StringVPrintfWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_LPCWSTR pszFormat, va_list argList)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003c18`
- `0x140004584`

## callees

- `0x140001fb0`
- `0x140004640`

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
  v7 = vsnwprintf(pszDest, cchDest - 1, pszFormat, argList);
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
0x140004640  mov     [rsp+arg_0], rbx
0x140004645  push    rdi
0x140004646  sub     rsp, 20h
0x14000464a  lea     rbx, [rdx-1]
0x14000464e  mov     r8, r9; Format
0x140004651  mov     r9, [rsp+28h+argList]; Args
0x140004656  mov     rdx, rbx; BufferCount
0x140004659  mov     rdi, rcx
0x14000465c  call    _vsnwprintf
0x140004661  test    eax, eax
0x140004663  js      short loc_140004675
0x140004665  cdqe
0x140004667  cmp     rax, rbx
0x14000466a  ja      short loc_140004675
0x14000466c  xor     ecx, ecx
0x14000466e  cmp     rax, rbx
0x140004671  jnz     short loc_140004680
0x140004673  jmp     short loc_14000467A
0x140004675  mov     ecx, 8007007Ah
0x14000467a  xor     eax, eax
0x14000467c  mov     [rdi+rbx*2], ax
0x140004680  mov     rbx, [rsp+28h+arg_0]
0x140004685  mov     eax, ecx
0x140004687  add     rsp, 20h
0x14000468b  pop     rdi
0x14000468c  retn
```
