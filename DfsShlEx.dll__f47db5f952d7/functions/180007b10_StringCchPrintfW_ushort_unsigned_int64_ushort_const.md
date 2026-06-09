# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007b10`
- end: `0x180007b94`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007368`
- `0x180007818`
- `0x180008428`
- `0x1800086d4`
- `0x180008920`

## callees

- `0x180007b10`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180007b4f`
- `msvcrt!_vsnwprintf` at `0x180007b4f`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180007b10  mov     [rsp+arg_10], r8
0x180007b15  mov     qword ptr [rsp+Args], r9
0x180007b1a  push    rbx
0x180007b1b  push    rdi
0x180007b1c  sub     rsp, 38h
0x180007b20  mov     rax, rdx
0x180007b23  mov     rdi, rcx
0x180007b26  test    rdx, rdx
0x180007b29  jz      short loc_180007B7C
0x180007b2b  cmp     rax, 7FFFFFFFh
0x180007b31  jbe     short loc_180007B3A
0x180007b33  mov     edx, 80070057h
0x180007b38  jmp     short loc_180007B86
0x180007b3a  lea     rbx, [rdx-1]
0x180007b3e  mov     [rsp+48h+var_28], 0
0x180007b47  mov     rdx, rbx; BufferCount
0x180007b4a  lea     r9, [rsp+48h+Args]; Args
0x180007b4f  call    cs:__imp__vsnwprintf
0x180007b55  test    eax, eax
0x180007b57  js      short loc_180007B6F
0x180007b59  cdqe
0x180007b5b  cmp     rax, rbx
0x180007b5e  ja      short loc_180007B6F
0x180007b60  xor     edx, edx
0x180007b62  cmp     rax, rbx
0x180007b65  jnz     short loc_180007B8B
0x180007b67  xor     eax, eax
0x180007b69  mov     [rdi+rbx*2], ax
0x180007b6d  jmp     short loc_180007B8B
0x180007b6f  xor     eax, eax
0x180007b71  mov     edx, 8007007Ah
0x180007b76  mov     [rdi+rbx*2], ax
0x180007b7a  jmp     short loc_180007B8B
0x180007b7c  mov     edx, 80070057h
0x180007b81  test    rax, rax
0x180007b84  jz      short loc_180007B8B
0x180007b86  xor     ecx, ecx
0x180007b88  mov     [rdi], cx
0x180007b8b  mov     eax, edx
0x180007b8d  add     rsp, 38h
0x180007b91  pop     rdi
0x180007b92  pop     rbx
0x180007b93  retn
```
