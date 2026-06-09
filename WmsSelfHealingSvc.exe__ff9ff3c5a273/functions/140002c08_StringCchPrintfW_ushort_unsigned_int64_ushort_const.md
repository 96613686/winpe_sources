# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140002c08`
- end: `0x140002c8c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e2c`
- `0x1400076e0`
- `0x140008510`

## callees

- `0x140002c08`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140002c47`
- `msvcrt!_vsnwprintf` at `0x140002c47`

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
0x140002c08  mov     [rsp+arg_10], r8
0x140002c0d  mov     qword ptr [rsp+Args], r9
0x140002c12  push    rbx
0x140002c13  push    rdi
0x140002c14  sub     rsp, 38h
0x140002c18  mov     rax, rdx
0x140002c1b  mov     rdi, rcx
0x140002c1e  test    rdx, rdx
0x140002c21  jz      short loc_140002C74
0x140002c23  cmp     rax, 7FFFFFFFh
0x140002c29  jbe     short loc_140002C32
0x140002c2b  mov     edx, 80070057h
0x140002c30  jmp     short loc_140002C7E
0x140002c32  lea     rbx, [rdx-1]
0x140002c36  mov     [rsp+48h+var_28], 0
0x140002c3f  mov     rdx, rbx; BufferCount
0x140002c42  lea     r9, [rsp+48h+Args]; Args
0x140002c47  call    cs:__imp__vsnwprintf
0x140002c4d  test    eax, eax
0x140002c4f  js      short loc_140002C67
0x140002c51  cdqe
0x140002c53  cmp     rax, rbx
0x140002c56  ja      short loc_140002C67
0x140002c58  xor     edx, edx
0x140002c5a  cmp     rax, rbx
0x140002c5d  jnz     short loc_140002C83
0x140002c5f  xor     eax, eax
0x140002c61  mov     [rdi+rbx*2], ax
0x140002c65  jmp     short loc_140002C83
0x140002c67  xor     eax, eax
0x140002c69  mov     edx, 8007007Ah
0x140002c6e  mov     [rdi+rbx*2], ax
0x140002c72  jmp     short loc_140002C83
0x140002c74  mov     edx, 80070057h
0x140002c79  test    rax, rax
0x140002c7c  jz      short loc_140002C83
0x140002c7e  xor     ecx, ecx
0x140002c80  mov     [rdi], cx
0x140002c83  mov     eax, edx
0x140002c85  add     rsp, 38h
0x140002c89  pop     rdi
0x140002c8a  pop     rbx
0x140002c8b  retn
```
