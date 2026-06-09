# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140008134`
- end: `0x1400081b8`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003de0`
- `0x14000e456`
- `0x14000e58a`
- `0x14000e6be`
- `0x14000e729`

## callees

- `0x140008134`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140008173`
- `msvcrt!_vsnwprintf` at `0x140008173`

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
0x140008134  mov     [rsp+arg_10], r8
0x140008139  mov     qword ptr [rsp+Args], r9
0x14000813e  push    rbx
0x14000813f  push    rdi
0x140008140  sub     rsp, 38h
0x140008144  mov     rax, rdx
0x140008147  mov     rdi, rcx
0x14000814a  test    rdx, rdx
0x14000814d  jz      short loc_1400081A0
0x14000814f  cmp     rax, 7FFFFFFFh
0x140008155  jbe     short loc_14000815E
0x140008157  mov     edx, 80070057h
0x14000815c  jmp     short loc_1400081AA
0x14000815e  lea     rbx, [rdx-1]
0x140008162  mov     [rsp+48h+var_28], 0
0x14000816b  mov     rdx, rbx; BufferCount
0x14000816e  lea     r9, [rsp+48h+Args]; Args
0x140008173  call    cs:__imp__vsnwprintf
0x140008179  test    eax, eax
0x14000817b  js      short loc_140008193
0x14000817d  cdqe
0x14000817f  cmp     rax, rbx
0x140008182  ja      short loc_140008193
0x140008184  xor     edx, edx
0x140008186  cmp     rax, rbx
0x140008189  jnz     short loc_1400081AF
0x14000818b  xor     eax, eax
0x14000818d  mov     [rdi+rbx*2], ax
0x140008191  jmp     short loc_1400081AF
0x140008193  xor     eax, eax
0x140008195  mov     edx, 8007007Ah
0x14000819a  mov     [rdi+rbx*2], ax
0x14000819e  jmp     short loc_1400081AF
0x1400081a0  mov     edx, 80070057h
0x1400081a5  test    rax, rax
0x1400081a8  jz      short loc_1400081AF
0x1400081aa  xor     ecx, ecx
0x1400081ac  mov     [rdi], cx
0x1400081af  mov     eax, edx
0x1400081b1  add     rsp, 38h
0x1400081b5  pop     rdi
0x1400081b6  pop     rbx
0x1400081b7  retn
```
