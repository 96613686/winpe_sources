# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000518c`
- end: `0x180005210`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003758`
- `0x180006ee0`

## callees

- `0x18000518c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800051cb`
- `msvcrt!_vsnwprintf` at `0x1800051cb`

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
0x18000518c  mov     [rsp+arg_10], r8
0x180005191  mov     qword ptr [rsp+Args], r9
0x180005196  push    rbx
0x180005197  push    rdi
0x180005198  sub     rsp, 38h
0x18000519c  mov     rax, rdx
0x18000519f  mov     rdi, rcx
0x1800051a2  test    rdx, rdx
0x1800051a5  jz      short loc_1800051F8
0x1800051a7  cmp     rax, 7FFFFFFFh
0x1800051ad  jbe     short loc_1800051B6
0x1800051af  mov     edx, 80070057h
0x1800051b4  jmp     short loc_180005202
0x1800051b6  lea     rbx, [rdx-1]
0x1800051ba  mov     [rsp+48h+var_28], 0
0x1800051c3  mov     rdx, rbx; BufferCount
0x1800051c6  lea     r9, [rsp+48h+Args]; Args
0x1800051cb  call    cs:__imp__vsnwprintf
0x1800051d1  test    eax, eax
0x1800051d3  js      short loc_1800051EB
0x1800051d5  cdqe
0x1800051d7  cmp     rax, rbx
0x1800051da  ja      short loc_1800051EB
0x1800051dc  xor     edx, edx
0x1800051de  cmp     rax, rbx
0x1800051e1  jnz     short loc_180005207
0x1800051e3  xor     eax, eax
0x1800051e5  mov     [rdi+rbx*2], ax
0x1800051e9  jmp     short loc_180005207
0x1800051eb  xor     eax, eax
0x1800051ed  mov     edx, 8007007Ah
0x1800051f2  mov     [rdi+rbx*2], ax
0x1800051f6  jmp     short loc_180005207
0x1800051f8  mov     edx, 80070057h
0x1800051fd  test    rax, rax
0x180005200  jz      short loc_180005207
0x180005202  xor     ecx, ecx
0x180005204  mov     [rdi], cx
0x180005207  mov     eax, edx
0x180005209  add     rsp, 38h
0x18000520d  pop     rdi
0x18000520e  pop     rbx
0x18000520f  retn
```
