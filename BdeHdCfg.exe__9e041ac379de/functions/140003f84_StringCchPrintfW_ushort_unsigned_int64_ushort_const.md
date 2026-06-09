# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140003f84`
- end: `0x140004008`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002930`
- `0x140002a00`
- `0x140003884`

## callees

- `0x140003f84`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140003fc3`
- `msvcrt!_vsnwprintf` at `0x140003fc3`

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
0x140003f84  mov     [rsp+arg_10], r8
0x140003f89  mov     qword ptr [rsp+Args], r9
0x140003f8e  push    rbx
0x140003f8f  push    rdi
0x140003f90  sub     rsp, 38h
0x140003f94  mov     rax, rdx
0x140003f97  mov     rdi, rcx
0x140003f9a  test    rdx, rdx
0x140003f9d  jz      short loc_140003FF0
0x140003f9f  cmp     rax, 7FFFFFFFh
0x140003fa5  jbe     short loc_140003FAE
0x140003fa7  mov     edx, 80070057h
0x140003fac  jmp     short loc_140003FFA
0x140003fae  lea     rbx, [rdx-1]
0x140003fb2  mov     [rsp+48h+var_28], 0
0x140003fbb  mov     rdx, rbx; BufferCount
0x140003fbe  lea     r9, [rsp+48h+Args]; Args
0x140003fc3  call    cs:__imp__vsnwprintf
0x140003fc9  test    eax, eax
0x140003fcb  js      short loc_140003FE3
0x140003fcd  cdqe
0x140003fcf  cmp     rax, rbx
0x140003fd2  ja      short loc_140003FE3
0x140003fd4  xor     edx, edx
0x140003fd6  cmp     rax, rbx
0x140003fd9  jnz     short loc_140003FFF
0x140003fdb  xor     eax, eax
0x140003fdd  mov     [rdi+rbx*2], ax
0x140003fe1  jmp     short loc_140003FFF
0x140003fe3  xor     eax, eax
0x140003fe5  mov     edx, 8007007Ah
0x140003fea  mov     [rdi+rbx*2], ax
0x140003fee  jmp     short loc_140003FFF
0x140003ff0  mov     edx, 80070057h
0x140003ff5  test    rax, rax
0x140003ff8  jz      short loc_140003FFF
0x140003ffa  xor     ecx, ecx
0x140003ffc  mov     [rdi], cx
0x140003fff  mov     eax, edx
0x140004001  add     rsp, 38h
0x140004005  pop     rdi
0x140004006  pop     rbx
0x140004007  retn
```
