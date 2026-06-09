# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x14000a6dc`
- end: `0x14000a75f`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140003cdc`
- `0x140007cf0`
- `0x140010778`
- `0x140010b80`
- `0x14001aaa4`

## callees

- `0x140003684`
- `0x14000a6dc`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
0x14000a6dc  mov     [rsp+arg_10], r8
0x14000a6e1  mov     qword ptr [rsp+Args], r9
0x14000a6e6  push    rbx
0x14000a6e7  push    rdi
0x14000a6e8  sub     rsp, 38h
0x14000a6ec  mov     rax, rdx
0x14000a6ef  mov     rdi, rcx
0x14000a6f2  test    rdx, rdx
0x14000a6f5  jz      short loc_14000A747
0x14000a6f7  cmp     rax, 7FFFFFFFh
0x14000a6fd  jbe     short loc_14000A706
0x14000a6ff  mov     edx, 80070057h
0x14000a704  jmp     short loc_14000A751
0x14000a706  lea     rbx, [rdx-1]
0x14000a70a  mov     [rsp+48h+var_28], 0
0x14000a713  mov     rdx, rbx; BufferCount
0x14000a716  lea     r9, [rsp+48h+Args]; Args
0x14000a71b  call    _vsnwprintf
0x14000a720  test    eax, eax
0x14000a722  js      short loc_14000A73A
0x14000a724  cdqe
0x14000a726  cmp     rax, rbx
0x14000a729  ja      short loc_14000A73A
0x14000a72b  xor     edx, edx
0x14000a72d  cmp     rax, rbx
0x14000a730  jnz     short loc_14000A756
0x14000a732  xor     eax, eax
0x14000a734  mov     [rdi+rbx*2], ax
0x14000a738  jmp     short loc_14000A756
0x14000a73a  xor     eax, eax
0x14000a73c  mov     edx, 8007007Ah
0x14000a741  mov     [rdi+rbx*2], ax
0x14000a745  jmp     short loc_14000A756
0x14000a747  mov     edx, 80070057h
0x14000a74c  test    rax, rax
0x14000a74f  jz      short loc_14000A756
0x14000a751  xor     ecx, ecx
0x14000a753  mov     [rdi], cx
0x14000a756  mov     eax, edx
0x14000a758  add     rsp, 38h
0x14000a75c  pop     rdi
0x14000a75d  pop     rbx
0x14000a75e  retn
```
