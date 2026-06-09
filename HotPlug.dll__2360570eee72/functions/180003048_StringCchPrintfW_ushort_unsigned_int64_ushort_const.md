# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003048`
- end: `0x1800030cc`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002de8`
- `0x180002e58`
- `0x180004664`
- `0x180004c20`
- `0x180004e60`
- `0x180005528`
- `0x180005724`
- `0x18000672c`
- `0x1800073b0`
- `0x180007558`
- `0x180007888`
- `0x180007f1c`

## callees

- `0x180003048`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180003087`
- `msvcrt!_vsnwprintf` at `0x180003087`

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
0x180003048  mov     [rsp+arg_10], r8
0x18000304d  mov     qword ptr [rsp+Args], r9
0x180003052  push    rbx
0x180003053  push    rdi
0x180003054  sub     rsp, 38h
0x180003058  mov     rax, rdx
0x18000305b  mov     rdi, rcx
0x18000305e  test    rdx, rdx
0x180003061  jz      short loc_1800030B4
0x180003063  cmp     rax, 7FFFFFFFh
0x180003069  jbe     short loc_180003072
0x18000306b  mov     edx, 80070057h
0x180003070  jmp     short loc_1800030BE
0x180003072  lea     rbx, [rdx-1]
0x180003076  mov     [rsp+48h+var_28], 0
0x18000307f  mov     rdx, rbx; BufferCount
0x180003082  lea     r9, [rsp+48h+Args]; Args
0x180003087  call    cs:__imp__vsnwprintf
0x18000308d  test    eax, eax
0x18000308f  js      short loc_1800030A7
0x180003091  cdqe
0x180003093  cmp     rax, rbx
0x180003096  ja      short loc_1800030A7
0x180003098  xor     edx, edx
0x18000309a  cmp     rax, rbx
0x18000309d  jnz     short loc_1800030C3
0x18000309f  xor     eax, eax
0x1800030a1  mov     [rdi+rbx*2], ax
0x1800030a5  jmp     short loc_1800030C3
0x1800030a7  xor     eax, eax
0x1800030a9  mov     edx, 8007007Ah
0x1800030ae  mov     [rdi+rbx*2], ax
0x1800030b2  jmp     short loc_1800030C3
0x1800030b4  mov     edx, 80070057h
0x1800030b9  test    rax, rax
0x1800030bc  jz      short loc_1800030C3
0x1800030be  xor     ecx, ecx
0x1800030c0  mov     [rdi], cx
0x1800030c3  mov     eax, edx
0x1800030c5  add     rsp, 38h
0x1800030c9  pop     rdi
0x1800030ca  pop     rbx
0x1800030cb  retn
```
