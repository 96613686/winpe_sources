# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007a3c`
- end: `0x180007ac7`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004cb4`
- `0x18000a2b2`
- `0x18000a3aa`
- `0x18000a4de`
- `0x18000a549`

## callees

- `0x180007a3c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180007a7b`
- `msvcrt!_vsnwprintf` at `0x180007a7b`

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
0x180007a3c  mov     [rsp+arg_10], r8
0x180007a41  mov     qword ptr [rsp+Args], r9
0x180007a46  push    rbx
0x180007a47  push    rdi
0x180007a48  sub     rsp, 38h
0x180007a4c  mov     rax, rdx
0x180007a4f  mov     rdi, rcx
0x180007a52  test    rdx, rdx
0x180007a55  jz      short loc_180007AAE
0x180007a57  cmp     rax, 7FFFFFFFh
0x180007a5d  jbe     short loc_180007A66
0x180007a5f  mov     edx, 80070057h
0x180007a64  jmp     short loc_180007AB8
0x180007a66  lea     rbx, [rdx-1]
0x180007a6a  mov     [rsp+48h+var_28], 0
0x180007a73  mov     rdx, rbx; BufferCount
0x180007a76  lea     r9, [rsp+48h+Args]; Args
0x180007a7b  call    cs:__imp__vsnwprintf
0x180007a82  nop     dword ptr [rax+rax+00h]
0x180007a87  test    eax, eax
0x180007a89  js      short loc_180007AA1
0x180007a8b  cdqe
0x180007a8d  cmp     rax, rbx
0x180007a90  ja      short loc_180007AA1
0x180007a92  xor     edx, edx
0x180007a94  cmp     rax, rbx
0x180007a97  jnz     short loc_180007ABD
0x180007a99  xor     eax, eax
0x180007a9b  mov     [rdi+rbx*2], ax
0x180007a9f  jmp     short loc_180007ABD
0x180007aa1  xor     eax, eax
0x180007aa3  mov     edx, 8007007Ah
0x180007aa8  mov     [rdi+rbx*2], ax
0x180007aac  jmp     short loc_180007ABD
0x180007aae  mov     edx, 80070057h
0x180007ab3  test    rax, rax
0x180007ab6  jz      short loc_180007ABD
0x180007ab8  xor     ecx, ecx
0x180007aba  mov     [rdi], cx
0x180007abd  mov     eax, edx
0x180007abf  add     rsp, 38h
0x180007ac3  pop     rdi
0x180007ac4  pop     rbx
0x180007ac5  retn
```
