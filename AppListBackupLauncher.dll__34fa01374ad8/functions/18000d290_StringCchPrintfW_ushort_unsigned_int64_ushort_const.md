# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000d290`
- end: `0x18000d313`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800068a8`
- `0x180006c4c`
- `0x1800075b4`
- `0x18000fa50`
- `0x1800104a3`
- `0x1800105d1`
- `0x180010705`
- `0x180010770`
- `0x180010858`
- `0x18001091b`
- `0x180010977`
- `0x1800109d3`
- `0x180010ad5`
- `0x180010b98`
- `0x180010bf4`
- `0x180010c50`
- `0x180010cac`

## callees

- `0x180002e10`
- `0x18000d290`

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
0x18000d290  mov     [rsp+arg_10], r8
0x18000d295  mov     qword ptr [rsp+Args], r9
0x18000d29a  push    rbx
0x18000d29b  push    rdi
0x18000d29c  sub     rsp, 38h
0x18000d2a0  mov     rax, rdx
0x18000d2a3  mov     rdi, rcx
0x18000d2a6  test    rdx, rdx
0x18000d2a9  jz      short loc_18000D2FB
0x18000d2ab  cmp     rax, 7FFFFFFFh
0x18000d2b1  jbe     short loc_18000D2BA
0x18000d2b3  mov     edx, 80070057h
0x18000d2b8  jmp     short loc_18000D305
0x18000d2ba  lea     rbx, [rdx-1]
0x18000d2be  mov     [rsp+48h+var_28], 0
0x18000d2c7  mov     rdx, rbx; BufferCount
0x18000d2ca  lea     r9, [rsp+48h+Args]; Args
0x18000d2cf  call    _vsnwprintf
0x18000d2d4  test    eax, eax
0x18000d2d6  js      short loc_18000D2EE
0x18000d2d8  cdqe
0x18000d2da  cmp     rax, rbx
0x18000d2dd  ja      short loc_18000D2EE
0x18000d2df  xor     edx, edx
0x18000d2e1  cmp     rax, rbx
0x18000d2e4  jnz     short loc_18000D30A
0x18000d2e6  xor     eax, eax
0x18000d2e8  mov     [rdi+rbx*2], ax
0x18000d2ec  jmp     short loc_18000D30A
0x18000d2ee  xor     eax, eax
0x18000d2f0  mov     edx, 8007007Ah
0x18000d2f5  mov     [rdi+rbx*2], ax
0x18000d2f9  jmp     short loc_18000D30A
0x18000d2fb  mov     edx, 80070057h
0x18000d300  test    rax, rax
0x18000d303  jz      short loc_18000D30A
0x18000d305  xor     ecx, ecx
0x18000d307  mov     [rdi], cx
0x18000d30a  mov     eax, edx
0x18000d30c  add     rsp, 38h
0x18000d310  pop     rdi
0x18000d311  pop     rbx
0x18000d312  retn
```
