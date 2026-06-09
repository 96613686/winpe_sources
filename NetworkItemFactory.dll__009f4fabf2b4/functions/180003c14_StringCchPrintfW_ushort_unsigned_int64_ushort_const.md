# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003c14`
- end: `0x180003c98`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000433c`
- `0x18000442c`

## callees

- `0x180003c14`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180003c53`
- `msvcrt!_vsnwprintf` at `0x180003c53`

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
0x180003c14  mov     [rsp+arg_10], r8
0x180003c19  mov     qword ptr [rsp+Args], r9
0x180003c1e  push    rbx
0x180003c1f  push    rdi
0x180003c20  sub     rsp, 38h
0x180003c24  mov     rax, rdx
0x180003c27  mov     rdi, rcx
0x180003c2a  test    rdx, rdx
0x180003c2d  jz      short loc_180003C80
0x180003c2f  cmp     rax, 7FFFFFFFh
0x180003c35  jbe     short loc_180003C3E
0x180003c37  mov     edx, 80070057h
0x180003c3c  jmp     short loc_180003C8A
0x180003c3e  lea     rbx, [rdx-1]
0x180003c42  mov     [rsp+48h+var_28], 0
0x180003c4b  mov     rdx, rbx; BufferCount
0x180003c4e  lea     r9, [rsp+48h+Args]; Args
0x180003c53  call    cs:__imp__vsnwprintf
0x180003c59  test    eax, eax
0x180003c5b  js      short loc_180003C73
0x180003c5d  cdqe
0x180003c5f  cmp     rax, rbx
0x180003c62  ja      short loc_180003C73
0x180003c64  xor     edx, edx
0x180003c66  cmp     rax, rbx
0x180003c69  jnz     short loc_180003C8F
0x180003c6b  xor     eax, eax
0x180003c6d  mov     [rdi+rbx*2], ax
0x180003c71  jmp     short loc_180003C8F
0x180003c73  xor     eax, eax
0x180003c75  mov     edx, 8007007Ah
0x180003c7a  mov     [rdi+rbx*2], ax
0x180003c7e  jmp     short loc_180003C8F
0x180003c80  mov     edx, 80070057h
0x180003c85  test    rax, rax
0x180003c88  jz      short loc_180003C8F
0x180003c8a  xor     ecx, ecx
0x180003c8c  mov     [rdi], cx
0x180003c8f  mov     eax, edx
0x180003c91  add     rsp, 38h
0x180003c95  pop     rdi
0x180003c96  pop     rbx
0x180003c97  retn
```
