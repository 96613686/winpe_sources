# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006934`
- end: `0x1800069b8`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d80`
- `0x180010f58`
- `0x180011324`
- `0x1800165d0`

## callees

- `0x180006934`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006973`
- `msvcrt!_vsnwprintf` at `0x180006973`

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
0x180006934  mov     [rsp+arg_10], r8
0x180006939  mov     qword ptr [rsp+Args], r9
0x18000693e  push    rbx
0x18000693f  push    rdi
0x180006940  sub     rsp, 38h
0x180006944  mov     rax, rdx
0x180006947  mov     rdi, rcx
0x18000694a  test    rdx, rdx
0x18000694d  jz      short loc_1800069A0
0x18000694f  cmp     rax, 7FFFFFFFh
0x180006955  jbe     short loc_18000695E
0x180006957  mov     edx, 80070057h
0x18000695c  jmp     short loc_1800069AA
0x18000695e  lea     rbx, [rdx-1]
0x180006962  mov     [rsp+48h+var_28], 0
0x18000696b  mov     rdx, rbx; BufferCount
0x18000696e  lea     r9, [rsp+48h+Args]; Args
0x180006973  call    cs:__imp__vsnwprintf
0x180006979  test    eax, eax
0x18000697b  js      short loc_180006993
0x18000697d  cdqe
0x18000697f  cmp     rax, rbx
0x180006982  ja      short loc_180006993
0x180006984  xor     edx, edx
0x180006986  cmp     rax, rbx
0x180006989  jnz     short loc_1800069AF
0x18000698b  xor     eax, eax
0x18000698d  mov     [rdi+rbx*2], ax
0x180006991  jmp     short loc_1800069AF
0x180006993  xor     eax, eax
0x180006995  mov     edx, 8007007Ah
0x18000699a  mov     [rdi+rbx*2], ax
0x18000699e  jmp     short loc_1800069AF
0x1800069a0  mov     edx, 80070057h
0x1800069a5  test    rax, rax
0x1800069a8  jz      short loc_1800069AF
0x1800069aa  xor     ecx, ecx
0x1800069ac  mov     [rdi], cx
0x1800069af  mov     eax, edx
0x1800069b1  add     rsp, 38h
0x1800069b5  pop     rdi
0x1800069b6  pop     rbx
0x1800069b7  retn
```
