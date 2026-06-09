# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002140`
- end: `0x1800021c4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cac`
- `0x1800023e0`

## callees

- `0x180002140`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000217f`
- `msvcrt!_vsnwprintf` at `0x18000217f`

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
0x180002140  mov     [rsp+arg_10], r8
0x180002145  mov     qword ptr [rsp+Args], r9
0x18000214a  push    rbx
0x18000214b  push    rdi
0x18000214c  sub     rsp, 38h
0x180002150  mov     rax, rdx
0x180002153  mov     rdi, rcx
0x180002156  test    rdx, rdx
0x180002159  jz      short loc_1800021AC
0x18000215b  cmp     rax, 7FFFFFFFh
0x180002161  jbe     short loc_18000216A
0x180002163  mov     edx, 80070057h
0x180002168  jmp     short loc_1800021B6
0x18000216a  lea     rbx, [rdx-1]
0x18000216e  mov     [rsp+48h+var_28], 0
0x180002177  mov     rdx, rbx; BufferCount
0x18000217a  lea     r9, [rsp+48h+Args]; Args
0x18000217f  call    cs:__imp__vsnwprintf
0x180002185  test    eax, eax
0x180002187  js      short loc_18000219F
0x180002189  cdqe
0x18000218b  cmp     rax, rbx
0x18000218e  ja      short loc_18000219F
0x180002190  xor     edx, edx
0x180002192  cmp     rax, rbx
0x180002195  jnz     short loc_1800021BB
0x180002197  xor     eax, eax
0x180002199  mov     [rdi+rbx*2], ax
0x18000219d  jmp     short loc_1800021BB
0x18000219f  xor     eax, eax
0x1800021a1  mov     edx, 8007007Ah
0x1800021a6  mov     [rdi+rbx*2], ax
0x1800021aa  jmp     short loc_1800021BB
0x1800021ac  mov     edx, 80070057h
0x1800021b1  test    rax, rax
0x1800021b4  jz      short loc_1800021BB
0x1800021b6  xor     ecx, ecx
0x1800021b8  mov     [rdi], cx
0x1800021bb  mov     eax, edx
0x1800021bd  add     rsp, 38h
0x1800021c1  pop     rdi
0x1800021c2  pop     rbx
0x1800021c3  retn
```
