# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000ce24`
- end: `0x14000cea7`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aac8`
- `0x14001373c`
- `0x140016952`
- `0x140016a4a`
- `0x140016b7e`
- `0x140016be9`
- `0x140016cd1`
- `0x140016f54`
- `0x140016fb3`
- `0x140017012`
- `0x140017117`
- `0x14001739a`
- `0x1400173f9`
- `0x140017458`
- `0x1400174b7`

## callees

- `0x140009160`
- `0x14000ce24`

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
0x14000ce24  mov     [rsp+arg_10], r8
0x14000ce29  mov     qword ptr [rsp+Args], r9
0x14000ce2e  push    rbx
0x14000ce2f  push    rdi
0x14000ce30  sub     rsp, 38h
0x14000ce34  mov     rax, rdx
0x14000ce37  mov     rdi, rcx
0x14000ce3a  test    rdx, rdx
0x14000ce3d  jz      short loc_14000CE8F
0x14000ce3f  cmp     rax, 7FFFFFFFh
0x14000ce45  jbe     short loc_14000CE4E
0x14000ce47  mov     edx, 80070057h
0x14000ce4c  jmp     short loc_14000CE99
0x14000ce4e  lea     rbx, [rdx-1]
0x14000ce52  mov     [rsp+48h+var_28], 0
0x14000ce5b  mov     rdx, rbx; BufferCount
0x14000ce5e  lea     r9, [rsp+48h+Args]; Args
0x14000ce63  call    _vsnwprintf
0x14000ce68  test    eax, eax
0x14000ce6a  js      short loc_14000CE82
0x14000ce6c  cdqe
0x14000ce6e  cmp     rax, rbx
0x14000ce71  ja      short loc_14000CE82
0x14000ce73  xor     edx, edx
0x14000ce75  cmp     rax, rbx
0x14000ce78  jnz     short loc_14000CE9E
0x14000ce7a  xor     eax, eax
0x14000ce7c  mov     [rdi+rbx*2], ax
0x14000ce80  jmp     short loc_14000CE9E
0x14000ce82  xor     eax, eax
0x14000ce84  mov     edx, 8007007Ah
0x14000ce89  mov     [rdi+rbx*2], ax
0x14000ce8d  jmp     short loc_14000CE9E
0x14000ce8f  mov     edx, 80070057h
0x14000ce94  test    rax, rax
0x14000ce97  jz      short loc_14000CE9E
0x14000ce99  xor     ecx, ecx
0x14000ce9b  mov     [rdi], cx
0x14000ce9e  mov     eax, edx
0x14000cea0  add     rsp, 38h
0x14000cea4  pop     rdi
0x14000cea5  pop     rbx
0x14000cea6  retn
```
