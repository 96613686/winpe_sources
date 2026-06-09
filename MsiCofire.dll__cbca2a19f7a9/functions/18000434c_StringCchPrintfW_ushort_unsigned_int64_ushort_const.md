# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000434c`
- end: `0x1800043d0`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ff8`
- `0x18000425c`

## callees

- `0x18000434c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000438b`
- `msvcrt!_vsnwprintf` at `0x18000438b`

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
0x18000434c  mov     [rsp+arg_10], r8
0x180004351  mov     qword ptr [rsp+Args], r9
0x180004356  push    rbx
0x180004357  push    rdi
0x180004358  sub     rsp, 38h
0x18000435c  mov     rax, rdx
0x18000435f  mov     rdi, rcx
0x180004362  test    rdx, rdx
0x180004365  jz      short loc_1800043B8
0x180004367  cmp     rax, 7FFFFFFFh
0x18000436d  jbe     short loc_180004376
0x18000436f  mov     edx, 80070057h
0x180004374  jmp     short loc_1800043C2
0x180004376  lea     rbx, [rdx-1]
0x18000437a  mov     [rsp+48h+var_28], 0
0x180004383  mov     rdx, rbx; BufferCount
0x180004386  lea     r9, [rsp+48h+Args]; Args
0x18000438b  call    cs:__imp__vsnwprintf
0x180004391  test    eax, eax
0x180004393  js      short loc_1800043AB
0x180004395  cdqe
0x180004397  cmp     rax, rbx
0x18000439a  ja      short loc_1800043AB
0x18000439c  xor     edx, edx
0x18000439e  cmp     rax, rbx
0x1800043a1  jnz     short loc_1800043C7
0x1800043a3  xor     eax, eax
0x1800043a5  mov     [rdi+rbx*2], ax
0x1800043a9  jmp     short loc_1800043C7
0x1800043ab  xor     eax, eax
0x1800043ad  mov     edx, 8007007Ah
0x1800043b2  mov     [rdi+rbx*2], ax
0x1800043b6  jmp     short loc_1800043C7
0x1800043b8  mov     edx, 80070057h
0x1800043bd  test    rax, rax
0x1800043c0  jz      short loc_1800043C7
0x1800043c2  xor     ecx, ecx
0x1800043c4  mov     [rdi], cx
0x1800043c7  mov     eax, edx
0x1800043c9  add     rsp, 38h
0x1800043cd  pop     rdi
0x1800043ce  pop     rbx
0x1800043cf  retn
```
