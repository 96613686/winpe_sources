# RtlStringCchPrintfW

- ea: `0x18000aa84`
- end: `0x18000ab08`
- name: `RtlStringCchPrintfW`
- size: `132`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f00`
- `0x1800090a0`

## callees

- `0x18000aa84`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000aac3`
- `msvcrt!_vsnwprintf` at `0x18000aac3`

## pseudocode

```c
__int64 RtlStringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
        v4 = -2147483643;
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
      v4 = -1073741811;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x18000aa84  mov     [rsp+arg_10], r8
0x18000aa89  mov     qword ptr [rsp+Args], r9
0x18000aa8e  push    rbx
0x18000aa8f  push    rdi
0x18000aa90  sub     rsp, 38h
0x18000aa94  mov     rax, rdx
0x18000aa97  mov     rdi, rcx
0x18000aa9a  test    rdx, rdx
0x18000aa9d  jz      short loc_18000AAF0
0x18000aa9f  cmp     rax, 7FFFFFFFh
0x18000aaa5  jbe     short loc_18000AAAE
0x18000aaa7  mov     edx, 0C000000Dh
0x18000aaac  jmp     short loc_18000AAFA
0x18000aaae  lea     rbx, [rdx-1]
0x18000aab2  mov     [rsp+48h+var_28], 0
0x18000aabb  mov     rdx, rbx; BufferCount
0x18000aabe  lea     r9, [rsp+48h+Args]; Args
0x18000aac3  call    cs:__imp__vsnwprintf
0x18000aac9  test    eax, eax
0x18000aacb  js      short loc_18000AAE3
0x18000aacd  cdqe
0x18000aacf  cmp     rax, rbx
0x18000aad2  ja      short loc_18000AAE3
0x18000aad4  xor     edx, edx
0x18000aad6  cmp     rax, rbx
0x18000aad9  jnz     short loc_18000AAFF
0x18000aadb  xor     eax, eax
0x18000aadd  mov     [rdi+rbx*2], ax
0x18000aae1  jmp     short loc_18000AAFF
0x18000aae3  xor     eax, eax
0x18000aae5  mov     edx, 80000005h
0x18000aaea  mov     [rdi+rbx*2], ax
0x18000aaee  jmp     short loc_18000AAFF
0x18000aaf0  mov     edx, 0C000000Dh
0x18000aaf5  test    rax, rax
0x18000aaf8  jz      short loc_18000AAFF
0x18000aafa  xor     ecx, ecx
0x18000aafc  mov     [rdi], cx
0x18000aaff  mov     eax, edx
0x18000ab01  add     rsp, 38h
0x18000ab05  pop     rdi
0x18000ab06  pop     rbx
0x18000ab07  retn
```
