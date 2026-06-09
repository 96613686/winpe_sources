# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002f2c`
- end: `0x180002fb0`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033c0`
- `0x180006714`
- `0x180008544`
- `0x18000a4c4`
- `0x18000fbdc`
- `0x18000fd5c`
- `0x180010eac`

## callees

- `0x180002f2c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002f6b`
- `msvcrt!_vsnwprintf` at `0x180002f6b`

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
0x180002f2c  mov     [rsp+arg_10], r8
0x180002f31  mov     qword ptr [rsp+Args], r9
0x180002f36  push    rbx
0x180002f37  push    rdi
0x180002f38  sub     rsp, 38h
0x180002f3c  mov     rax, rdx
0x180002f3f  mov     rdi, rcx
0x180002f42  test    rdx, rdx
0x180002f45  jz      short loc_180002F98
0x180002f47  cmp     rax, 7FFFFFFFh
0x180002f4d  jbe     short loc_180002F56
0x180002f4f  mov     edx, 80070057h
0x180002f54  jmp     short loc_180002FA2
0x180002f56  lea     rbx, [rdx-1]
0x180002f5a  mov     [rsp+48h+var_28], 0
0x180002f63  mov     rdx, rbx; BufferCount
0x180002f66  lea     r9, [rsp+48h+Args]; Args
0x180002f6b  call    cs:__imp__vsnwprintf
0x180002f71  test    eax, eax
0x180002f73  js      short loc_180002F8B
0x180002f75  cdqe
0x180002f77  cmp     rax, rbx
0x180002f7a  ja      short loc_180002F8B
0x180002f7c  xor     edx, edx
0x180002f7e  cmp     rax, rbx
0x180002f81  jnz     short loc_180002FA7
0x180002f83  xor     eax, eax
0x180002f85  mov     [rdi+rbx*2], ax
0x180002f89  jmp     short loc_180002FA7
0x180002f8b  xor     eax, eax
0x180002f8d  mov     edx, 8007007Ah
0x180002f92  mov     [rdi+rbx*2], ax
0x180002f96  jmp     short loc_180002FA7
0x180002f98  mov     edx, 80070057h
0x180002f9d  test    rax, rax
0x180002fa0  jz      short loc_180002FA7
0x180002fa2  xor     ecx, ecx
0x180002fa4  mov     [rdi], cx
0x180002fa7  mov     eax, edx
0x180002fa9  add     rsp, 38h
0x180002fad  pop     rdi
0x180002fae  pop     rbx
0x180002faf  retn
```
