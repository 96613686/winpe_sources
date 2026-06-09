# StringCbPrintfW

- ea: `0x180004bc0`
- end: `0x180004c44`
- name: `StringCbPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ca4`

## callees

- `0x180004bc0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180004bff`
- `msvcrt!_vsnwprintf` at `0x180004bff`

## pseudocode

```c
HRESULT StringCbPrintfW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t v4; // rax
  HRESULT v5; // edx
  unsigned __int64 v6; // rbx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v4 = cbDest >> 1;
  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( v4 <= 0x7FFFFFFF )
  {
    v6 = v4 - 1;
    v7 = _vsnwprintf(pszDest, v4 - 1, pszFormat, Args);
    if ( v7 < 0 || v7 > v6 )
    {
      v5 = -2147024774;
      pszDest[v6] = 0;
    }
    else
    {
      v5 = 0;
      if ( v7 == v6 )
        pszDest[v6] = 0;
    }
  }
  else
  {
    v5 = -2147024809;
    *pszDest = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180004bc0  mov     [rsp+arg_10], r8
0x180004bc5  mov     qword ptr [rsp+Args], r9
0x180004bca  push    rbx
0x180004bcb  push    rdi
0x180004bcc  sub     rsp, 38h
0x180004bd0  mov     rax, rdx
0x180004bd3  mov     rdi, rcx
0x180004bd6  shr     rax, 1
0x180004bd9  jz      short loc_180004C2C
0x180004bdb  cmp     rax, 7FFFFFFFh
0x180004be1  jbe     short loc_180004BEA
0x180004be3  mov     edx, 80070057h
0x180004be8  jmp     short loc_180004C36
0x180004bea  lea     rbx, [rax-1]
0x180004bee  mov     [rsp+48h+var_28], 0
0x180004bf7  mov     rdx, rbx; BufferCount
0x180004bfa  lea     r9, [rsp+48h+Args]; Args
0x180004bff  call    cs:__imp__vsnwprintf
0x180004c05  test    eax, eax
0x180004c07  js      short loc_180004C1F
0x180004c09  cdqe
0x180004c0b  cmp     rax, rbx
0x180004c0e  ja      short loc_180004C1F
0x180004c10  xor     edx, edx
0x180004c12  cmp     rax, rbx
0x180004c15  jnz     short loc_180004C3B
0x180004c17  xor     eax, eax
0x180004c19  mov     [rdi+rbx*2], ax
0x180004c1d  jmp     short loc_180004C3B
0x180004c1f  xor     eax, eax
0x180004c21  mov     edx, 8007007Ah
0x180004c26  mov     [rdi+rbx*2], ax
0x180004c2a  jmp     short loc_180004C3B
0x180004c2c  mov     edx, 80070057h
0x180004c31  test    rax, rax
0x180004c34  jz      short loc_180004C3B
0x180004c36  xor     ecx, ecx
0x180004c38  mov     [rdi], cx
0x180004c3b  mov     eax, edx
0x180004c3d  add     rsp, 38h
0x180004c41  pop     rdi
0x180004c42  pop     rbx
0x180004c43  retn
```
