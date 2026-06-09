# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140001d04`
- end: `0x140001d86`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `130`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ad0`
- `0x140007db0`
- `0x14000dd14`

## callees

- `0x140001d04`
- `0x14000964c`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rbx
  int v5; // eax
  unsigned int v6; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF )
    {
      v6 = -2147024809;
      *a1 = 0;
    }
    else
    {
      v4 = a2 - 1;
      v5 = vsnwprintf(a1, a2 - 1, a3, va);
      if ( v5 < 0 || v5 > v4 )
      {
        v6 = -2147024774;
        a1[v4] = 0;
      }
      else
      {
        v6 = 0;
        if ( v5 == v4 )
          a1[v4] = 0;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x140001d04  mov     r11, rsp
0x140001d07  mov     [r11+18h], r8
0x140001d0b  mov     [r11+20h], r9
0x140001d0f  push    rbx
0x140001d10  push    rdi
0x140001d11  sub     rsp, 38h
0x140001d15  mov     rax, rdx
0x140001d18  mov     rdi, rcx
0x140001d1b  test    rdx, rdx
0x140001d1e  jz      short loc_140001D75
0x140001d20  cmp     rax, 7FFFFFFFh
0x140001d26  ja      short loc_140001D6E
0x140001d28  lea     rbx, [rdx-1]
0x140001d2c  mov     qword ptr [r11-28h], 0
0x140001d34  mov     rdx, rbx; BufferCount
0x140001d37  lea     r9, [r11+20h]; Args
0x140001d3b  call    _vsnwprintf
0x140001d40  test    eax, eax
0x140001d42  jns     short loc_140001D58
0x140001d44  xor     eax, eax
0x140001d46  mov     edx, 8007007Ah
0x140001d4b  mov     [rdi+rbx*2], ax
0x140001d4f  mov     eax, edx
0x140001d51  add     rsp, 38h
0x140001d55  pop     rdi
0x140001d56  pop     rbx
0x140001d57  retn
0x140001d58  cdqe
0x140001d5a  cmp     rax, rbx
0x140001d5d  ja      short loc_140001D44
0x140001d5f  xor     edx, edx
0x140001d61  cmp     rax, rbx
0x140001d64  jnz     short loc_140001D4F
0x140001d66  xor     eax, eax
0x140001d68  mov     [rdi+rbx*2], ax
0x140001d6c  jmp     short loc_140001D4F
0x140001d6e  mov     edx, 80070057h
0x140001d73  jmp     short loc_140001D7F
0x140001d75  mov     edx, 80070057h
0x140001d7a  test    rax, rax
0x140001d7d  jz      short loc_140001D4F
0x140001d7f  xor     ecx, ecx
0x140001d81  mov     [rdi], cx
0x140001d84  jmp     short loc_140001D4F
```
