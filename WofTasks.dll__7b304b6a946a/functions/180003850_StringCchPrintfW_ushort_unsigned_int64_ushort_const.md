# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003850`
- end: `0x1800038d4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fd0`
- `0x180003f00`

## callees

- `0x180003850`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000388f`
- `msvcrt!_vsnwprintf` at `0x18000388f`

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
0x180003850  mov     [rsp+arg_10], r8
0x180003855  mov     qword ptr [rsp+Args], r9
0x18000385a  push    rbx
0x18000385b  push    rdi
0x18000385c  sub     rsp, 38h
0x180003860  mov     rax, rdx
0x180003863  mov     rdi, rcx
0x180003866  test    rdx, rdx
0x180003869  jz      short loc_1800038BC
0x18000386b  cmp     rax, 7FFFFFFFh
0x180003871  jbe     short loc_18000387A
0x180003873  mov     edx, 80070057h
0x180003878  jmp     short loc_1800038C6
0x18000387a  lea     rbx, [rdx-1]
0x18000387e  mov     [rsp+48h+var_28], 0
0x180003887  mov     rdx, rbx; BufferCount
0x18000388a  lea     r9, [rsp+48h+Args]; Args
0x18000388f  call    cs:__imp__vsnwprintf
0x180003895  test    eax, eax
0x180003897  js      short loc_1800038AF
0x180003899  cdqe
0x18000389b  cmp     rax, rbx
0x18000389e  ja      short loc_1800038AF
0x1800038a0  xor     edx, edx
0x1800038a2  cmp     rax, rbx
0x1800038a5  jnz     short loc_1800038CB
0x1800038a7  xor     eax, eax
0x1800038a9  mov     [rdi+rbx*2], ax
0x1800038ad  jmp     short loc_1800038CB
0x1800038af  xor     eax, eax
0x1800038b1  mov     edx, 8007007Ah
0x1800038b6  mov     [rdi+rbx*2], ax
0x1800038ba  jmp     short loc_1800038CB
0x1800038bc  mov     edx, 80070057h
0x1800038c1  test    rax, rax
0x1800038c4  jz      short loc_1800038CB
0x1800038c6  xor     ecx, ecx
0x1800038c8  mov     [rdi], cx
0x1800038cb  mov     eax, edx
0x1800038cd  add     rsp, 38h
0x1800038d1  pop     rdi
0x1800038d2  pop     rbx
0x1800038d3  retn
```
