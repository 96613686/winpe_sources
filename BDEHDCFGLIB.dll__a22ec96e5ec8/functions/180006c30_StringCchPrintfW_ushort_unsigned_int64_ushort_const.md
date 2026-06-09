# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006c30`
- end: `0x180006cb4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000634c`
- `0x180007624`
- `0x180007ec8`
- `0x180008ca0`
- `0x180008e4c`
- `0x180009000`
- `0x1800093e0`
- `0x18000ed1c`
- `0x18000fb40`
- `0x1800113dc`

## callees

- `0x180006c30`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006c6f`
- `msvcrt!_vsnwprintf` at `0x180006c6f`

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
0x180006c30  mov     [rsp+arg_10], r8
0x180006c35  mov     qword ptr [rsp+Args], r9
0x180006c3a  push    rbx
0x180006c3b  push    rdi
0x180006c3c  sub     rsp, 38h
0x180006c40  mov     rax, rdx
0x180006c43  mov     rdi, rcx
0x180006c46  test    rdx, rdx
0x180006c49  jz      short loc_180006C9C
0x180006c4b  cmp     rax, 7FFFFFFFh
0x180006c51  jbe     short loc_180006C5A
0x180006c53  mov     edx, 80070057h
0x180006c58  jmp     short loc_180006CA6
0x180006c5a  lea     rbx, [rdx-1]
0x180006c5e  mov     [rsp+48h+var_28], 0
0x180006c67  mov     rdx, rbx; BufferCount
0x180006c6a  lea     r9, [rsp+48h+Args]; Args
0x180006c6f  call    cs:__imp__vsnwprintf
0x180006c75  test    eax, eax
0x180006c77  js      short loc_180006C8F
0x180006c79  cdqe
0x180006c7b  cmp     rax, rbx
0x180006c7e  ja      short loc_180006C8F
0x180006c80  xor     edx, edx
0x180006c82  cmp     rax, rbx
0x180006c85  jnz     short loc_180006CAB
0x180006c87  xor     eax, eax
0x180006c89  mov     [rdi+rbx*2], ax
0x180006c8d  jmp     short loc_180006CAB
0x180006c8f  xor     eax, eax
0x180006c91  mov     edx, 8007007Ah
0x180006c96  mov     [rdi+rbx*2], ax
0x180006c9a  jmp     short loc_180006CAB
0x180006c9c  mov     edx, 80070057h
0x180006ca1  test    rax, rax
0x180006ca4  jz      short loc_180006CAB
0x180006ca6  xor     ecx, ecx
0x180006ca8  mov     [rdi], cx
0x180006cab  mov     eax, edx
0x180006cad  add     rsp, 38h
0x180006cb1  pop     rdi
0x180006cb2  pop     rbx
0x180006cb3  retn
```
