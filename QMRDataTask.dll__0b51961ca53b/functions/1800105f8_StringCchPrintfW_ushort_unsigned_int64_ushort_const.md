# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800105f8`
- end: `0x18001067c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006108`
- `0x1800064ac`
- `0x180009ec8`
- `0x18000ebf8`
- `0x18000f270`
- `0x18000f330`

## callees

- `0x1800105f8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180010637`
- `msvcrt!_vsnwprintf` at `0x180010637`

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
0x1800105f8  mov     [rsp+arg_10], r8
0x1800105fd  mov     qword ptr [rsp+Args], r9
0x180010602  push    rbx
0x180010603  push    rdi
0x180010604  sub     rsp, 38h
0x180010608  mov     rax, rdx
0x18001060b  mov     rdi, rcx
0x18001060e  test    rdx, rdx
0x180010611  jz      short loc_180010664
0x180010613  cmp     rax, 7FFFFFFFh
0x180010619  jbe     short loc_180010622
0x18001061b  mov     edx, 80070057h
0x180010620  jmp     short loc_18001066E
0x180010622  lea     rbx, [rdx-1]
0x180010626  mov     [rsp+48h+var_28], 0
0x18001062f  mov     rdx, rbx; BufferCount
0x180010632  lea     r9, [rsp+48h+Args]; Args
0x180010637  call    cs:__imp__vsnwprintf
0x18001063d  test    eax, eax
0x18001063f  js      short loc_180010657
0x180010641  cdqe
0x180010643  cmp     rax, rbx
0x180010646  ja      short loc_180010657
0x180010648  xor     edx, edx
0x18001064a  cmp     rax, rbx
0x18001064d  jnz     short loc_180010673
0x18001064f  xor     eax, eax
0x180010651  mov     [rdi+rbx*2], ax
0x180010655  jmp     short loc_180010673
0x180010657  xor     eax, eax
0x180010659  mov     edx, 8007007Ah
0x18001065e  mov     [rdi+rbx*2], ax
0x180010662  jmp     short loc_180010673
0x180010664  mov     edx, 80070057h
0x180010669  test    rax, rax
0x18001066c  jz      short loc_180010673
0x18001066e  xor     ecx, ecx
0x180010670  mov     [rdi], cx
0x180010673  mov     eax, edx
0x180010675  add     rsp, 38h
0x180010679  pop     rdi
0x18001067a  pop     rbx
0x18001067b  retn
```
