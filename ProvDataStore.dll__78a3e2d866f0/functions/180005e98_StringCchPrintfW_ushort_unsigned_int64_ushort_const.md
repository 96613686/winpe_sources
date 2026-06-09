# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005e98`
- end: `0x180005f1c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003670`
- `0x180009750`
- `0x18000fa60`
- `0x180011396`
- `0x18001148e`
- `0x1800115c2`
- `0x18001162d`

## callees

- `0x180005e98`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180005ed7`
- `msvcrt!_vsnwprintf` at `0x180005ed7`

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
0x180005e98  mov     [rsp+arg_10], r8
0x180005e9d  mov     qword ptr [rsp+Args], r9
0x180005ea2  push    rbx
0x180005ea3  push    rdi
0x180005ea4  sub     rsp, 38h
0x180005ea8  mov     rax, rdx
0x180005eab  mov     rdi, rcx
0x180005eae  test    rdx, rdx
0x180005eb1  jz      short loc_180005F04
0x180005eb3  cmp     rax, 7FFFFFFFh
0x180005eb9  jbe     short loc_180005EC2
0x180005ebb  mov     edx, 80070057h
0x180005ec0  jmp     short loc_180005F0E
0x180005ec2  lea     rbx, [rdx-1]
0x180005ec6  mov     [rsp+48h+var_28], 0
0x180005ecf  mov     rdx, rbx; BufferCount
0x180005ed2  lea     r9, [rsp+48h+Args]; Args
0x180005ed7  call    cs:__imp__vsnwprintf
0x180005edd  test    eax, eax
0x180005edf  js      short loc_180005EF7
0x180005ee1  cdqe
0x180005ee3  cmp     rax, rbx
0x180005ee6  ja      short loc_180005EF7
0x180005ee8  xor     edx, edx
0x180005eea  cmp     rax, rbx
0x180005eed  jnz     short loc_180005F13
0x180005eef  xor     eax, eax
0x180005ef1  mov     [rdi+rbx*2], ax
0x180005ef5  jmp     short loc_180005F13
0x180005ef7  xor     eax, eax
0x180005ef9  mov     edx, 8007007Ah
0x180005efe  mov     [rdi+rbx*2], ax
0x180005f02  jmp     short loc_180005F13
0x180005f04  mov     edx, 80070057h
0x180005f09  test    rax, rax
0x180005f0c  jz      short loc_180005F13
0x180005f0e  xor     ecx, ecx
0x180005f10  mov     [rdi], cx
0x180005f13  mov     eax, edx
0x180005f15  add     rsp, 38h
0x180005f19  pop     rdi
0x180005f1a  pop     rbx
0x180005f1b  retn
```
