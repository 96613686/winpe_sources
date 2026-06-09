# CExtractIconOnHICON::_ExtractW(ushort const *,uint,HICON__ * *,HICON__ * *,uint)

- ea: `0x180024d00`
- end: `0x180024d94`
- name: `?_ExtractW@CExtractIconOnHICON@@EEAAJPEBGIPEAPEAUHICON__@@1I@Z`
- size: `148`
- prototype: `__int64 __fastcall(CExtractIconOnHICON *this, const unsigned __int16 *, int, HICON *, HICON *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012e54`
- `0x180024d00`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x180024d30`
- `SHLWAPI!StrCmpW` at `0x180024d30`
- `USER32!CopyIcon` at `0x180024d4c`
- `USER32!CopyIcon` at `0x180024d74`
- `USER32!CopyIcon` at `0x180024d4c`
- `USER32!CopyIcon` at `0x180024d74`

## pseudocode

```c
__int64 __fastcall CExtractIconOnHICON::_ExtractW(
        CExtractIconOnHICON *this,
        const unsigned __int16 *a2,
        int a3,
        HICON *a4,
        HICON *a5)
{
  unsigned int Error; // ebx
  HICON v9; // rax
  HICON v10; // rax

  Error = -2147467259;
  if ( *((_QWORD *)this + 19) )
  {
    Error = -2147024809;
    if ( StrCmpW(a2, (PCWSTR)this + 10) >= 0 && !a3 )
    {
      if ( a4 )
      {
        Error = 0;
        v9 = CopyIcon(*((HICON *)this + 19));
        *a4 = v9;
        if ( !v9 )
          Error = ResultFromKnownLastError();
      }
      if ( a5 )
      {
        Error = 0;
        v10 = CopyIcon(*((HICON *)this + 19));
        *a5 = v10;
        if ( !v10 )
          return (unsigned int)ResultFromKnownLastError();
      }
    }
  }
  return Error;
}

```

## disassembly

```asm
0x180024d00  push    rbx
0x180024d02  push    rbp
0x180024d03  push    rsi
0x180024d04  push    rdi
0x180024d05  sub     rsp, 28h
0x180024d09  cmp     qword ptr [rcx+98h], 0
0x180024d11  mov     rdi, r9
0x180024d14  mov     ebp, r8d
0x180024d17  mov     rax, rdx
0x180024d1a  mov     rsi, rcx
0x180024d1d  mov     ebx, 80004005h
0x180024d22  jz      short loc_180024D89
0x180024d24  lea     rdx, [rcx+14h]; psz2
0x180024d28  mov     ebx, 80070057h
0x180024d2d  mov     rcx, rax; psz1
0x180024d30  call    cs:__imp_StrCmpW
0x180024d36  test    eax, eax
0x180024d38  js      short loc_180024D89
0x180024d3a  test    ebp, ebp
0x180024d3c  jnz     short loc_180024D89
0x180024d3e  test    rdi, rdi
0x180024d41  jz      short loc_180024D61
0x180024d43  mov     rcx, [rsi+98h]; hIcon
0x180024d4a  xor     ebx, ebx
0x180024d4c  call    cs:__imp_CopyIcon
0x180024d52  mov     [rdi], rax
0x180024d55  test    rax, rax
0x180024d58  jnz     short loc_180024D61
0x180024d5a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180024d5f  mov     ebx, eax
0x180024d61  mov     rdi, [rsp+48h+arg_20]
0x180024d66  test    rdi, rdi
0x180024d69  jz      short loc_180024D89
0x180024d6b  mov     rcx, [rsi+98h]; hIcon
0x180024d72  xor     ebx, ebx
0x180024d74  call    cs:__imp_CopyIcon
0x180024d7a  mov     [rdi], rax
0x180024d7d  test    rax, rax
0x180024d80  jnz     short loc_180024D89
0x180024d82  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180024d87  mov     ebx, eax
0x180024d89  mov     eax, ebx
0x180024d8b  add     rsp, 28h
0x180024d8f  pop     rdi
0x180024d90  pop     rsi
0x180024d91  pop     rbp
0x180024d92  pop     rbx
0x180024d93  retn
```
