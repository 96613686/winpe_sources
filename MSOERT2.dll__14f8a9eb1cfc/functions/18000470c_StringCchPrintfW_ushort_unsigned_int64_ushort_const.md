# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000470c`
- end: `0x180004790`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dc0`
- `0x180003f80`
- `0x180006ac0`
- `0x180006e30`
- `0x180007ba8`
- `0x18000a220`
- `0x18000af00`
- `0x18000b770`
- `0x18000ca70`
- `0x180011230`

## callees

- `0x18000470c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000474b`
- `msvcrt!_vsnwprintf` at `0x18000474b`

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
0x18000470c  mov     [rsp+arg_10], r8
0x180004711  mov     qword ptr [rsp+Args], r9
0x180004716  push    rbx
0x180004717  push    rdi
0x180004718  sub     rsp, 38h
0x18000471c  mov     rax, rdx
0x18000471f  mov     rdi, rcx
0x180004722  test    rdx, rdx
0x180004725  jz      short loc_180004778
0x180004727  cmp     rax, 7FFFFFFFh
0x18000472d  jbe     short loc_180004736
0x18000472f  mov     edx, 80070057h
0x180004734  jmp     short loc_180004782
0x180004736  lea     rbx, [rdx-1]
0x18000473a  mov     [rsp+48h+var_28], 0
0x180004743  mov     rdx, rbx; BufferCount
0x180004746  lea     r9, [rsp+48h+Args]; Args
0x18000474b  call    cs:__imp__vsnwprintf
0x180004751  test    eax, eax
0x180004753  js      short loc_18000476B
0x180004755  cdqe
0x180004757  cmp     rax, rbx
0x18000475a  ja      short loc_18000476B
0x18000475c  xor     edx, edx
0x18000475e  cmp     rax, rbx
0x180004761  jnz     short loc_180004787
0x180004763  xor     eax, eax
0x180004765  mov     [rdi+rbx*2], ax
0x180004769  jmp     short loc_180004787
0x18000476b  xor     eax, eax
0x18000476d  mov     edx, 8007007Ah
0x180004772  mov     [rdi+rbx*2], ax
0x180004776  jmp     short loc_180004787
0x180004778  mov     edx, 80070057h
0x18000477d  test    rax, rax
0x180004780  jz      short loc_180004787
0x180004782  xor     ecx, ecx
0x180004784  mov     [rdi], cx
0x180004787  mov     eax, edx
0x180004789  add     rsp, 38h
0x18000478d  pop     rdi
0x18000478e  pop     rbx
0x18000478f  retn
```
