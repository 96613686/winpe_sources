# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800072b0`
- end: `0x180007333`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046d8`
- `0x18000c9a0`
- `0x18000ca74`
- `0x18000cba8`
- `0x18000cc13`

## callees

- `0x1800020e8`
- `0x1800072b0`

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
0x1800072b0  mov     [rsp+arg_10], r8
0x1800072b5  mov     qword ptr [rsp+Args], r9
0x1800072ba  push    rbx
0x1800072bb  push    rdi
0x1800072bc  sub     rsp, 38h
0x1800072c0  mov     rax, rdx
0x1800072c3  mov     rdi, rcx
0x1800072c6  test    rdx, rdx
0x1800072c9  jz      short loc_18000731B
0x1800072cb  cmp     rax, 7FFFFFFFh
0x1800072d1  jbe     short loc_1800072DA
0x1800072d3  mov     edx, 80070057h
0x1800072d8  jmp     short loc_180007325
0x1800072da  lea     rbx, [rdx-1]
0x1800072de  mov     [rsp+48h+var_28], 0
0x1800072e7  mov     rdx, rbx; BufferCount
0x1800072ea  lea     r9, [rsp+48h+Args]; Args
0x1800072ef  call    _vsnwprintf
0x1800072f4  test    eax, eax
0x1800072f6  js      short loc_18000730E
0x1800072f8  cdqe
0x1800072fa  cmp     rax, rbx
0x1800072fd  ja      short loc_18000730E
0x1800072ff  xor     edx, edx
0x180007301  cmp     rax, rbx
0x180007304  jnz     short loc_18000732A
0x180007306  xor     eax, eax
0x180007308  mov     [rdi+rbx*2], ax
0x18000730c  jmp     short loc_18000732A
0x18000730e  xor     eax, eax
0x180007310  mov     edx, 8007007Ah
0x180007315  mov     [rdi+rbx*2], ax
0x180007319  jmp     short loc_18000732A
0x18000731b  mov     edx, 80070057h
0x180007320  test    rax, rax
0x180007323  jz      short loc_18000732A
0x180007325  xor     ecx, ecx
0x180007327  mov     [rdi], cx
0x18000732a  mov     eax, edx
0x18000732c  add     rsp, 38h
0x180007330  pop     rdi
0x180007331  pop     rbx
0x180007332  retn
```
