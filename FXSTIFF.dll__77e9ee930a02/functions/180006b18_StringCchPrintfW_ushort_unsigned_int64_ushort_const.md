# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006b18`
- end: `0x180006ba3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ed0`
- `0x180011648`
- `0x180011a14`
- `0x1800172f4`

## callees

- `0x180006b18`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006b57`
- `msvcrt!_vsnwprintf` at `0x180006b57`

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
0x180006b18  mov     [rsp+arg_10], r8
0x180006b1d  mov     qword ptr [rsp+Args], r9
0x180006b22  push    rbx
0x180006b23  push    rdi
0x180006b24  sub     rsp, 38h
0x180006b28  mov     rax, rdx
0x180006b2b  mov     rdi, rcx
0x180006b2e  test    rdx, rdx
0x180006b31  jz      short loc_180006B8A
0x180006b33  cmp     rax, 7FFFFFFFh
0x180006b39  jbe     short loc_180006B42
0x180006b3b  mov     edx, 80070057h
0x180006b40  jmp     short loc_180006B94
0x180006b42  lea     rbx, [rdx-1]
0x180006b46  mov     [rsp+48h+var_28], 0
0x180006b4f  mov     rdx, rbx; BufferCount
0x180006b52  lea     r9, [rsp+48h+Args]; Args
0x180006b57  call    cs:__imp__vsnwprintf
0x180006b5e  nop     dword ptr [rax+rax+00h]
0x180006b63  test    eax, eax
0x180006b65  js      short loc_180006B7D
0x180006b67  cdqe
0x180006b69  cmp     rax, rbx
0x180006b6c  ja      short loc_180006B7D
0x180006b6e  xor     edx, edx
0x180006b70  cmp     rax, rbx
0x180006b73  jnz     short loc_180006B99
0x180006b75  xor     eax, eax
0x180006b77  mov     [rdi+rbx*2], ax
0x180006b7b  jmp     short loc_180006B99
0x180006b7d  xor     eax, eax
0x180006b7f  mov     edx, 8007007Ah
0x180006b84  mov     [rdi+rbx*2], ax
0x180006b88  jmp     short loc_180006B99
0x180006b8a  mov     edx, 80070057h
0x180006b8f  test    rax, rax
0x180006b92  jz      short loc_180006B99
0x180006b94  xor     ecx, ecx
0x180006b96  mov     [rdi], cx
0x180006b99  mov     eax, edx
0x180006b9b  add     rsp, 38h
0x180006b9f  pop     rdi
0x180006ba0  pop     rbx
0x180006ba1  retn
```
