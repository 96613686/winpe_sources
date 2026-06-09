# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005550`
- end: `0x1800055d3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003018`
- `0x18000a0e8`
- `0x18000a1e0`
- `0x18000a314`
- `0x18000a37f`

## callees

- `0x180002064`
- `0x180005550`

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
0x180005550  mov     [rsp+arg_10], r8
0x180005555  mov     qword ptr [rsp+Args], r9
0x18000555a  push    rbx
0x18000555b  push    rdi
0x18000555c  sub     rsp, 38h
0x180005560  mov     rax, rdx
0x180005563  mov     rdi, rcx
0x180005566  test    rdx, rdx
0x180005569  jz      short loc_1800055BB
0x18000556b  cmp     rax, 7FFFFFFFh
0x180005571  jbe     short loc_18000557A
0x180005573  mov     edx, 80070057h
0x180005578  jmp     short loc_1800055C5
0x18000557a  lea     rbx, [rdx-1]
0x18000557e  mov     [rsp+48h+var_28], 0
0x180005587  mov     rdx, rbx; BufferCount
0x18000558a  lea     r9, [rsp+48h+Args]; Args
0x18000558f  call    _vsnwprintf
0x180005594  test    eax, eax
0x180005596  js      short loc_1800055AE
0x180005598  cdqe
0x18000559a  cmp     rax, rbx
0x18000559d  ja      short loc_1800055AE
0x18000559f  xor     edx, edx
0x1800055a1  cmp     rax, rbx
0x1800055a4  jnz     short loc_1800055CA
0x1800055a6  xor     eax, eax
0x1800055a8  mov     [rdi+rbx*2], ax
0x1800055ac  jmp     short loc_1800055CA
0x1800055ae  xor     eax, eax
0x1800055b0  mov     edx, 8007007Ah
0x1800055b5  mov     [rdi+rbx*2], ax
0x1800055b9  jmp     short loc_1800055CA
0x1800055bb  mov     edx, 80070057h
0x1800055c0  test    rax, rax
0x1800055c3  jz      short loc_1800055CA
0x1800055c5  xor     ecx, ecx
0x1800055c7  mov     [rdi], cx
0x1800055ca  mov     eax, edx
0x1800055cc  add     rsp, 38h
0x1800055d0  pop     rdi
0x1800055d1  pop     rbx
0x1800055d2  retn
```
