# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800091c0`
- end: `0x180009244`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000596c`
- `0x180005d10`

## callees

- `0x1800091c0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800091ff`
- `msvcrt!_vsnwprintf` at `0x1800091ff`

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
0x1800091c0  mov     [rsp+arg_10], r8
0x1800091c5  mov     qword ptr [rsp+Args], r9
0x1800091ca  push    rbx
0x1800091cb  push    rdi
0x1800091cc  sub     rsp, 38h
0x1800091d0  mov     rax, rdx
0x1800091d3  mov     rdi, rcx
0x1800091d6  test    rdx, rdx
0x1800091d9  jz      short loc_18000922C
0x1800091db  cmp     rax, 7FFFFFFFh
0x1800091e1  jbe     short loc_1800091EA
0x1800091e3  mov     edx, 80070057h
0x1800091e8  jmp     short loc_180009236
0x1800091ea  lea     rbx, [rdx-1]
0x1800091ee  mov     [rsp+48h+var_28], 0
0x1800091f7  mov     rdx, rbx; BufferCount
0x1800091fa  lea     r9, [rsp+48h+Args]; Args
0x1800091ff  call    cs:__imp__vsnwprintf
0x180009205  test    eax, eax
0x180009207  js      short loc_18000921F
0x180009209  cdqe
0x18000920b  cmp     rax, rbx
0x18000920e  ja      short loc_18000921F
0x180009210  xor     edx, edx
0x180009212  cmp     rax, rbx
0x180009215  jnz     short loc_18000923B
0x180009217  xor     eax, eax
0x180009219  mov     [rdi+rbx*2], ax
0x18000921d  jmp     short loc_18000923B
0x18000921f  xor     eax, eax
0x180009221  mov     edx, 8007007Ah
0x180009226  mov     [rdi+rbx*2], ax
0x18000922a  jmp     short loc_18000923B
0x18000922c  mov     edx, 80070057h
0x180009231  test    rax, rax
0x180009234  jz      short loc_18000923B
0x180009236  xor     ecx, ecx
0x180009238  mov     [rdi], cx
0x18000923b  mov     eax, edx
0x18000923d  add     rsp, 38h
0x180009241  pop     rdi
0x180009242  pop     rbx
0x180009243  retn
```
