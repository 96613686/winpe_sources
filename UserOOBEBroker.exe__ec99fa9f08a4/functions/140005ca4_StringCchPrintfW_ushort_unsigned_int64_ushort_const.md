# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005ca4`
- end: `0x140005d28`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140003960`
- `0x140008710`
- `0x14000a54c`
- `0x14000e376`
- `0x14000e46e`
- `0x14000e5a2`
- `0x14000e60d`

## callees

- `0x140005ca4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140005ce3`
- `msvcrt!_vsnwprintf` at `0x140005ce3`

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
0x140005ca4  mov     [rsp+arg_10], r8
0x140005ca9  mov     qword ptr [rsp+Args], r9
0x140005cae  push    rbx
0x140005caf  push    rdi
0x140005cb0  sub     rsp, 38h
0x140005cb4  mov     rax, rdx
0x140005cb7  mov     rdi, rcx
0x140005cba  test    rdx, rdx
0x140005cbd  jz      short loc_140005D10
0x140005cbf  cmp     rax, 7FFFFFFFh
0x140005cc5  jbe     short loc_140005CCE
0x140005cc7  mov     edx, 80070057h
0x140005ccc  jmp     short loc_140005D1A
0x140005cce  lea     rbx, [rdx-1]
0x140005cd2  mov     [rsp+48h+var_28], 0
0x140005cdb  mov     rdx, rbx; BufferCount
0x140005cde  lea     r9, [rsp+48h+Args]; Args
0x140005ce3  call    cs:__imp__vsnwprintf
0x140005ce9  test    eax, eax
0x140005ceb  js      short loc_140005D03
0x140005ced  cdqe
0x140005cef  cmp     rax, rbx
0x140005cf2  ja      short loc_140005D03
0x140005cf4  xor     edx, edx
0x140005cf6  cmp     rax, rbx
0x140005cf9  jnz     short loc_140005D1F
0x140005cfb  xor     eax, eax
0x140005cfd  mov     [rdi+rbx*2], ax
0x140005d01  jmp     short loc_140005D1F
0x140005d03  xor     eax, eax
0x140005d05  mov     edx, 8007007Ah
0x140005d0a  mov     [rdi+rbx*2], ax
0x140005d0e  jmp     short loc_140005D1F
0x140005d10  mov     edx, 80070057h
0x140005d15  test    rax, rax
0x140005d18  jz      short loc_140005D1F
0x140005d1a  xor     ecx, ecx
0x140005d1c  mov     [rdi], cx
0x140005d1f  mov     eax, edx
0x140005d21  add     rsp, 38h
0x140005d25  pop     rdi
0x140005d26  pop     rbx
0x140005d27  retn
```
