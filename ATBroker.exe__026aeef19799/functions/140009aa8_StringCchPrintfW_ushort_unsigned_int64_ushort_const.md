# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140009aa8`
- end: `0x140009b2c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400040c8`
- `0x140004498`
- `0x14000d498`
- `0x14000d778`
- `0x140011f08`
- `0x1400127f8`

## callees

- `0x140009aa8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140009ae7`
- `msvcrt!_vsnwprintf` at `0x140009ae7`

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
0x140009aa8  mov     [rsp+arg_10], r8
0x140009aad  mov     qword ptr [rsp+Args], r9
0x140009ab2  push    rbx
0x140009ab3  push    rdi
0x140009ab4  sub     rsp, 38h
0x140009ab8  mov     rax, rdx
0x140009abb  mov     rdi, rcx
0x140009abe  test    rdx, rdx
0x140009ac1  jz      short loc_140009B14
0x140009ac3  cmp     rax, 7FFFFFFFh
0x140009ac9  jbe     short loc_140009AD2
0x140009acb  mov     edx, 80070057h
0x140009ad0  jmp     short loc_140009B1E
0x140009ad2  lea     rbx, [rdx-1]
0x140009ad6  mov     [rsp+48h+var_28], 0
0x140009adf  mov     rdx, rbx; BufferCount
0x140009ae2  lea     r9, [rsp+48h+Args]; Args
0x140009ae7  call    cs:__imp__vsnwprintf
0x140009aed  test    eax, eax
0x140009aef  js      short loc_140009B07
0x140009af1  cdqe
0x140009af3  cmp     rax, rbx
0x140009af6  ja      short loc_140009B07
0x140009af8  xor     edx, edx
0x140009afa  cmp     rax, rbx
0x140009afd  jnz     short loc_140009B23
0x140009aff  xor     eax, eax
0x140009b01  mov     [rdi+rbx*2], ax
0x140009b05  jmp     short loc_140009B23
0x140009b07  xor     eax, eax
0x140009b09  mov     edx, 8007007Ah
0x140009b0e  mov     [rdi+rbx*2], ax
0x140009b12  jmp     short loc_140009B23
0x140009b14  mov     edx, 80070057h
0x140009b19  test    rax, rax
0x140009b1c  jz      short loc_140009B23
0x140009b1e  xor     ecx, ecx
0x140009b20  mov     [rdi], cx
0x140009b23  mov     eax, edx
0x140009b25  add     rsp, 38h
0x140009b29  pop     rdi
0x140009b2a  pop     rbx
0x140009b2b  retn
```
