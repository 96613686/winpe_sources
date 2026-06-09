# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005154`
- end: `0x1400051e2`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `142`
- prototype: `__int64(wchar_t *Buffer, size_t, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d18`
- `0x140006064`

## callees

- `0x140001f5c`
- `0x140005154`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, size_t a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = vsnwprintf_s(Buffer, a2, a2 - 1, a3, va);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        Buffer[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          Buffer[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *Buffer = 0;
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
0x140005154  mov     [rsp+arg_10], r8
0x140005159  mov     qword ptr [rsp+arg_18], r9
0x14000515e  push    rbx
0x14000515f  push    rdi
0x140005160  sub     rsp, 48h
0x140005164  mov     rax, rdx
0x140005167  mov     rdi, rcx
0x14000516a  test    rdx, rdx
0x14000516d  jz      short loc_1400051CA
0x14000516f  cmp     rax, 7FFFFFFFh
0x140005175  jbe     short loc_14000517E
0x140005177  mov     edx, 80070057h; BufferCount
0x14000517c  jmp     short loc_1400051D4
0x14000517e  lea     rcx, [rsp+58h+arg_18]
0x140005183  mov     [rsp+58h+var_28], 0
0x14000518c  lea     rbx, [rdx-1]
0x140005190  mov     [rsp+58h+ArgList], rcx; ArgList
0x140005195  mov     r9, r8; Format
0x140005198  mov     rcx, rdi; Buffer
0x14000519b  mov     r8, rbx; MaxCount
0x14000519e  call    _vsnwprintf_s
0x1400051a3  test    eax, eax
0x1400051a5  js      short loc_1400051BD
0x1400051a7  cdqe
0x1400051a9  cmp     rax, rbx
0x1400051ac  ja      short loc_1400051BD
0x1400051ae  xor     edx, edx
0x1400051b0  cmp     rax, rbx
0x1400051b3  jnz     short loc_1400051D9
0x1400051b5  xor     eax, eax
0x1400051b7  mov     [rdi+rbx*2], ax
0x1400051bb  jmp     short loc_1400051D9
0x1400051bd  xor     eax, eax
0x1400051bf  mov     edx, 8007007Ah
0x1400051c4  mov     [rdi+rbx*2], ax
0x1400051c8  jmp     short loc_1400051D9
0x1400051ca  mov     edx, 80070057h
0x1400051cf  test    rax, rax
0x1400051d2  jz      short loc_1400051D9
0x1400051d4  xor     ecx, ecx
0x1400051d6  mov     [rdi], cx
0x1400051d9  mov     eax, edx
0x1400051db  add     rsp, 48h
0x1400051df  pop     rdi
0x1400051e0  pop     rbx
0x1400051e1  retn
```
