# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005284`
- end: `0x140005307`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d28`
- `0x140006194`
- `0x1400071ae`
- `0x1400072a6`
- `0x1400073da`
- `0x140007445`

## callees

- `0x140001e8c`
- `0x140005284`

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
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
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
0x140005284  mov     [rsp+arg_10], r8
0x140005289  mov     qword ptr [rsp+Args], r9
0x14000528e  push    rbx
0x14000528f  push    rdi
0x140005290  sub     rsp, 38h
0x140005294  mov     rax, rdx
0x140005297  mov     rdi, rcx
0x14000529a  test    rdx, rdx
0x14000529d  jz      short loc_1400052EF
0x14000529f  cmp     rax, 7FFFFFFFh
0x1400052a5  jbe     short loc_1400052AE
0x1400052a7  mov     edx, 80070057h
0x1400052ac  jmp     short loc_1400052F9
0x1400052ae  lea     rbx, [rdx-1]
0x1400052b2  mov     [rsp+48h+var_28], 0
0x1400052bb  mov     rdx, rbx; BufferCount
0x1400052be  lea     r9, [rsp+48h+Args]; Args
0x1400052c3  call    _vsnwprintf
0x1400052c8  test    eax, eax
0x1400052ca  js      short loc_1400052E2
0x1400052cc  cdqe
0x1400052ce  cmp     rax, rbx
0x1400052d1  ja      short loc_1400052E2
0x1400052d3  xor     edx, edx
0x1400052d5  cmp     rax, rbx
0x1400052d8  jnz     short loc_1400052FE
0x1400052da  xor     eax, eax
0x1400052dc  mov     [rdi+rbx*2], ax
0x1400052e0  jmp     short loc_1400052FE
0x1400052e2  xor     eax, eax
0x1400052e4  mov     edx, 8007007Ah
0x1400052e9  mov     [rdi+rbx*2], ax
0x1400052ed  jmp     short loc_1400052FE
0x1400052ef  mov     edx, 80070057h
0x1400052f4  test    rax, rax
0x1400052f7  jz      short loc_1400052FE
0x1400052f9  xor     ecx, ecx
0x1400052fb  mov     [rdi], cx
0x1400052fe  mov     eax, edx
0x140005300  add     rsp, 38h
0x140005304  pop     rdi
0x140005305  pop     rbx
0x140005306  retn
```
