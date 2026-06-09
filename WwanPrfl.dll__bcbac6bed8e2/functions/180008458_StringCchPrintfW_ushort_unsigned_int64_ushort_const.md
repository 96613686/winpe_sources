# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180008458`
- end: `0x1800084db`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b08`
- `0x180003eac`
- `0x18000e050`
- `0x18000e0e0`

## callees

- `0x180002040`
- `0x180008458`

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
0x180008458  mov     [rsp+arg_10], r8
0x18000845d  mov     qword ptr [rsp+Args], r9
0x180008462  push    rbx
0x180008463  push    rdi
0x180008464  sub     rsp, 38h
0x180008468  mov     rax, rdx
0x18000846b  mov     rdi, rcx
0x18000846e  test    rdx, rdx
0x180008471  jz      short loc_1800084C3
0x180008473  cmp     rax, 7FFFFFFFh
0x180008479  jbe     short loc_180008482
0x18000847b  mov     edx, 80070057h
0x180008480  jmp     short loc_1800084CD
0x180008482  lea     rbx, [rdx-1]
0x180008486  mov     [rsp+48h+var_28], 0
0x18000848f  mov     rdx, rbx; BufferCount
0x180008492  lea     r9, [rsp+48h+Args]; Args
0x180008497  call    _vsnwprintf
0x18000849c  test    eax, eax
0x18000849e  js      short loc_1800084B6
0x1800084a0  cdqe
0x1800084a2  cmp     rax, rbx
0x1800084a5  ja      short loc_1800084B6
0x1800084a7  xor     edx, edx
0x1800084a9  cmp     rax, rbx
0x1800084ac  jnz     short loc_1800084D2
0x1800084ae  xor     eax, eax
0x1800084b0  mov     [rdi+rbx*2], ax
0x1800084b4  jmp     short loc_1800084D2
0x1800084b6  xor     eax, eax
0x1800084b8  mov     edx, 8007007Ah
0x1800084bd  mov     [rdi+rbx*2], ax
0x1800084c1  jmp     short loc_1800084D2
0x1800084c3  mov     edx, 80070057h
0x1800084c8  test    rax, rax
0x1800084cb  jz      short loc_1800084D2
0x1800084cd  xor     ecx, ecx
0x1800084cf  mov     [rdi], cx
0x1800084d2  mov     eax, edx
0x1800084d4  add     rsp, 38h
0x1800084d8  pop     rdi
0x1800084d9  pop     rbx
0x1800084da  retn
```
