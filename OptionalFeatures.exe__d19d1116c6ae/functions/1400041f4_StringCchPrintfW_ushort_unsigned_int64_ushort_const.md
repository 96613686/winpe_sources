# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400041f4`
- end: `0x140004278`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400024f4`

## callees

- `0x1400041f4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140004233`
- `msvcrt!_vsnwprintf` at `0x140004233`

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
0x1400041f4  mov     [rsp+arg_10], r8
0x1400041f9  mov     qword ptr [rsp+Args], r9
0x1400041fe  push    rbx
0x1400041ff  push    rdi
0x140004200  sub     rsp, 38h
0x140004204  mov     rax, rdx
0x140004207  mov     rdi, rcx
0x14000420a  test    rdx, rdx
0x14000420d  jz      short loc_140004260
0x14000420f  cmp     rax, 7FFFFFFFh
0x140004215  jbe     short loc_14000421E
0x140004217  mov     edx, 80070057h
0x14000421c  jmp     short loc_14000426A
0x14000421e  lea     rbx, [rdx-1]
0x140004222  mov     [rsp+48h+var_28], 0
0x14000422b  mov     rdx, rbx; BufferCount
0x14000422e  lea     r9, [rsp+48h+Args]; Args
0x140004233  call    cs:__imp__vsnwprintf
0x140004239  test    eax, eax
0x14000423b  js      short loc_140004253
0x14000423d  cdqe
0x14000423f  cmp     rax, rbx
0x140004242  ja      short loc_140004253
0x140004244  xor     edx, edx
0x140004246  cmp     rax, rbx
0x140004249  jnz     short loc_14000426F
0x14000424b  xor     eax, eax
0x14000424d  mov     [rdi+rbx*2], ax
0x140004251  jmp     short loc_14000426F
0x140004253  xor     eax, eax
0x140004255  mov     edx, 8007007Ah
0x14000425a  mov     [rdi+rbx*2], ax
0x14000425e  jmp     short loc_14000426F
0x140004260  mov     edx, 80070057h
0x140004265  test    rax, rax
0x140004268  jz      short loc_14000426F
0x14000426a  xor     ecx, ecx
0x14000426c  mov     [rdi], cx
0x14000426f  mov     eax, edx
0x140004271  add     rsp, 38h
0x140004275  pop     rdi
0x140004276  pop     rbx
0x140004277  retn
```
