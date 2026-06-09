# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800084ac`
- end: `0x180008537`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180003648`
- `0x1800039f4`
- `0x180025df0`
- `0x180026ef0`
- `0x180027248`
- `0x180028ef0`
- `0x18002cf00`
- `0x18002e5ac`
- `0x1800309c4`
- `0x180031c24`
- `0x180032d88`
- `0x1800366d0`
- `0x180036dbc`
- `0x180036f80`
- `0x18003c0e8`

## callees

- `0x1800084ac`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800084eb`
- `msvcrt!_vsnwprintf` at `0x1800084eb`

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
0x1800084ac  mov     [rsp+arg_10], r8
0x1800084b1  mov     qword ptr [rsp+Args], r9
0x1800084b6  push    rbx
0x1800084b7  push    rdi
0x1800084b8  sub     rsp, 38h
0x1800084bc  mov     rax, rdx
0x1800084bf  mov     rdi, rcx
0x1800084c2  test    rdx, rdx
0x1800084c5  jz      short loc_18000851E
0x1800084c7  cmp     rax, 7FFFFFFFh
0x1800084cd  jbe     short loc_1800084D6
0x1800084cf  mov     edx, 80070057h
0x1800084d4  jmp     short loc_180008528
0x1800084d6  lea     rbx, [rdx-1]
0x1800084da  mov     [rsp+48h+var_28], 0
0x1800084e3  mov     rdx, rbx; BufferCount
0x1800084e6  lea     r9, [rsp+48h+Args]; Args
0x1800084eb  call    cs:__imp__vsnwprintf
0x1800084f2  nop     dword ptr [rax+rax+00h]
0x1800084f7  test    eax, eax
0x1800084f9  js      short loc_180008511
0x1800084fb  cdqe
0x1800084fd  cmp     rax, rbx
0x180008500  ja      short loc_180008511
0x180008502  xor     edx, edx
0x180008504  cmp     rax, rbx
0x180008507  jnz     short loc_18000852D
0x180008509  xor     eax, eax
0x18000850b  mov     [rdi+rbx*2], ax
0x18000850f  jmp     short loc_18000852D
0x180008511  xor     eax, eax
0x180008513  mov     edx, 8007007Ah
0x180008518  mov     [rdi+rbx*2], ax
0x18000851c  jmp     short loc_18000852D
0x18000851e  mov     edx, 80070057h
0x180008523  test    rax, rax
0x180008526  jz      short loc_18000852D
0x180008528  xor     ecx, ecx
0x18000852a  mov     [rdi], cx
0x18000852d  mov     eax, edx
0x18000852f  add     rsp, 38h
0x180008533  pop     rdi
0x180008534  pop     rbx
0x180008535  retn
```
