# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006a30`
- end: `0x180006ab4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003df0`
- `0x18000c946`
- `0x18000ca3e`
- `0x18000cb72`
- `0x18000cbdd`

## callees

- `0x180006a30`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006a6f`
- `msvcrt!_vsnwprintf` at `0x180006a6f`

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
0x180006a30  mov     [rsp+arg_10], r8
0x180006a35  mov     qword ptr [rsp+Args], r9
0x180006a3a  push    rbx
0x180006a3b  push    rdi
0x180006a3c  sub     rsp, 38h
0x180006a40  mov     rax, rdx
0x180006a43  mov     rdi, rcx
0x180006a46  test    rdx, rdx
0x180006a49  jz      short loc_180006A9C
0x180006a4b  cmp     rax, 7FFFFFFFh
0x180006a51  jbe     short loc_180006A5A
0x180006a53  mov     edx, 80070057h
0x180006a58  jmp     short loc_180006AA6
0x180006a5a  lea     rbx, [rdx-1]
0x180006a5e  mov     [rsp+48h+var_28], 0
0x180006a67  mov     rdx, rbx; BufferCount
0x180006a6a  lea     r9, [rsp+48h+Args]; Args
0x180006a6f  call    cs:__imp__vsnwprintf
0x180006a75  test    eax, eax
0x180006a77  js      short loc_180006A8F
0x180006a79  cdqe
0x180006a7b  cmp     rax, rbx
0x180006a7e  ja      short loc_180006A8F
0x180006a80  xor     edx, edx
0x180006a82  cmp     rax, rbx
0x180006a85  jnz     short loc_180006AAB
0x180006a87  xor     eax, eax
0x180006a89  mov     [rdi+rbx*2], ax
0x180006a8d  jmp     short loc_180006AAB
0x180006a8f  xor     eax, eax
0x180006a91  mov     edx, 8007007Ah
0x180006a96  mov     [rdi+rbx*2], ax
0x180006a9a  jmp     short loc_180006AAB
0x180006a9c  mov     edx, 80070057h
0x180006aa1  test    rax, rax
0x180006aa4  jz      short loc_180006AAB
0x180006aa6  xor     ecx, ecx
0x180006aa8  mov     [rdi], cx
0x180006aab  mov     eax, edx
0x180006aad  add     rsp, 38h
0x180006ab1  pop     rdi
0x180006ab2  pop     rbx
0x180006ab3  retn
```
