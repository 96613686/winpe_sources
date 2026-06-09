# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000e000`
- end: `0x18000e084`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e090`
- `0x18000e828`
- `0x18000ea1c`
- `0x18000eb9c`
- `0x18000ec8c`
- `0x18000ee14`
- `0x18000f2b8`
- `0x18000f744`
- `0x18000fca8`
- `0x180010e70`

## callees

- `0x18000e000`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000e03f`
- `msvcrt!_vsnwprintf` at `0x18000e03f`

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
0x18000e000  mov     [rsp+arg_10], r8
0x18000e005  mov     qword ptr [rsp+Args], r9
0x18000e00a  push    rbx
0x18000e00b  push    rdi
0x18000e00c  sub     rsp, 38h
0x18000e010  mov     rax, rdx
0x18000e013  mov     rdi, rcx
0x18000e016  test    rdx, rdx
0x18000e019  jz      short loc_18000E06C
0x18000e01b  cmp     rax, 7FFFFFFFh
0x18000e021  jbe     short loc_18000E02A
0x18000e023  mov     edx, 80070057h
0x18000e028  jmp     short loc_18000E076
0x18000e02a  lea     rbx, [rdx-1]
0x18000e02e  mov     [rsp+48h+var_28], 0
0x18000e037  mov     rdx, rbx; BufferCount
0x18000e03a  lea     r9, [rsp+48h+Args]; Args
0x18000e03f  call    cs:__imp__vsnwprintf
0x18000e045  test    eax, eax
0x18000e047  js      short loc_18000E05F
0x18000e049  cdqe
0x18000e04b  cmp     rax, rbx
0x18000e04e  ja      short loc_18000E05F
0x18000e050  xor     edx, edx
0x18000e052  cmp     rax, rbx
0x18000e055  jnz     short loc_18000E07B
0x18000e057  xor     eax, eax
0x18000e059  mov     [rdi+rbx*2], ax
0x18000e05d  jmp     short loc_18000E07B
0x18000e05f  xor     eax, eax
0x18000e061  mov     edx, 8007007Ah
0x18000e066  mov     [rdi+rbx*2], ax
0x18000e06a  jmp     short loc_18000E07B
0x18000e06c  mov     edx, 80070057h
0x18000e071  test    rax, rax
0x18000e074  jz      short loc_18000E07B
0x18000e076  xor     ecx, ecx
0x18000e078  mov     [rdi], cx
0x18000e07b  mov     eax, edx
0x18000e07d  add     rsp, 38h
0x18000e081  pop     rdi
0x18000e082  pop     rbx
0x18000e083  retn
```
