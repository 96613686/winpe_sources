# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140006e60`
- end: `0x140006ee3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400048f8`
- `0x1400087ac`
- `0x14000c164`
- `0x14000f3ec`
- `0x14001002c`
- `0x1400102f0`

## callees

- `0x1400036b4`
- `0x140006e60`

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
0x140006e60  mov     [rsp+arg_10], r8
0x140006e65  mov     qword ptr [rsp+Args], r9
0x140006e6a  push    rbx
0x140006e6b  push    rdi
0x140006e6c  sub     rsp, 38h
0x140006e70  mov     rax, rdx
0x140006e73  mov     rdi, rcx
0x140006e76  test    rdx, rdx
0x140006e79  jz      short loc_140006ECB
0x140006e7b  cmp     rax, 7FFFFFFFh
0x140006e81  jbe     short loc_140006E8A
0x140006e83  mov     edx, 80070057h
0x140006e88  jmp     short loc_140006ED5
0x140006e8a  lea     rbx, [rdx-1]
0x140006e8e  mov     [rsp+48h+var_28], 0
0x140006e97  mov     rdx, rbx; BufferCount
0x140006e9a  lea     r9, [rsp+48h+Args]; Args
0x140006e9f  call    _vsnwprintf
0x140006ea4  test    eax, eax
0x140006ea6  js      short loc_140006EBE
0x140006ea8  cdqe
0x140006eaa  cmp     rax, rbx
0x140006ead  ja      short loc_140006EBE
0x140006eaf  xor     edx, edx
0x140006eb1  cmp     rax, rbx
0x140006eb4  jnz     short loc_140006EDA
0x140006eb6  xor     eax, eax
0x140006eb8  mov     [rdi+rbx*2], ax
0x140006ebc  jmp     short loc_140006EDA
0x140006ebe  xor     eax, eax
0x140006ec0  mov     edx, 8007007Ah
0x140006ec5  mov     [rdi+rbx*2], ax
0x140006ec9  jmp     short loc_140006EDA
0x140006ecb  mov     edx, 80070057h
0x140006ed0  test    rax, rax
0x140006ed3  jz      short loc_140006EDA
0x140006ed5  xor     ecx, ecx
0x140006ed7  mov     [rdi], cx
0x140006eda  mov     eax, edx
0x140006edc  add     rsp, 38h
0x140006ee0  pop     rdi
0x140006ee1  pop     rbx
0x140006ee2  retn
```
