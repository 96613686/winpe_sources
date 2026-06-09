# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006410`
- end: `0x180006494`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006360`

## callees

- `0x180006410`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000644f`
- `msvcrt!_vsnwprintf` at `0x18000644f`

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
0x180006410  mov     [rsp+arg_10], r8
0x180006415  mov     qword ptr [rsp+Args], r9
0x18000641a  push    rbx
0x18000641b  push    rdi
0x18000641c  sub     rsp, 38h
0x180006420  mov     rax, rdx
0x180006423  mov     rdi, rcx
0x180006426  test    rdx, rdx
0x180006429  jz      short loc_18000647C
0x18000642b  cmp     rax, 7FFFFFFFh
0x180006431  jbe     short loc_18000643A
0x180006433  mov     edx, 80070057h
0x180006438  jmp     short loc_180006486
0x18000643a  lea     rbx, [rdx-1]
0x18000643e  mov     [rsp+48h+var_28], 0
0x180006447  mov     rdx, rbx; BufferCount
0x18000644a  lea     r9, [rsp+48h+Args]; Args
0x18000644f  call    cs:__imp__vsnwprintf
0x180006455  test    eax, eax
0x180006457  js      short loc_18000646F
0x180006459  cdqe
0x18000645b  cmp     rax, rbx
0x18000645e  ja      short loc_18000646F
0x180006460  xor     edx, edx
0x180006462  cmp     rax, rbx
0x180006465  jnz     short loc_18000648B
0x180006467  xor     eax, eax
0x180006469  mov     [rdi+rbx*2], ax
0x18000646d  jmp     short loc_18000648B
0x18000646f  xor     eax, eax
0x180006471  mov     edx, 8007007Ah
0x180006476  mov     [rdi+rbx*2], ax
0x18000647a  jmp     short loc_18000648B
0x18000647c  mov     edx, 80070057h
0x180006481  test    rax, rax
0x180006484  jz      short loc_18000648B
0x180006486  xor     ecx, ecx
0x180006488  mov     [rdi], cx
0x18000648b  mov     eax, edx
0x18000648d  add     rsp, 38h
0x180006491  pop     rdi
0x180006492  pop     rbx
0x180006493  retn
```
