# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x140004664`
- end: `0x1400046e7`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b28`
- `0x140008f9c`
- `0x14000936c`
- `0x14000f81c`

## callees

- `0x140003044`
- `0x140004664`

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
0x140004664  mov     [rsp+arg_10], r8
0x140004669  mov     qword ptr [rsp+Args], r9
0x14000466e  push    rbx
0x14000466f  push    rdi
0x140004670  sub     rsp, 38h
0x140004674  mov     rax, rdx
0x140004677  mov     rdi, rcx
0x14000467a  test    rdx, rdx
0x14000467d  jz      short loc_1400046CF
0x14000467f  cmp     rax, 7FFFFFFFh
0x140004685  jbe     short loc_14000468E
0x140004687  mov     edx, 80070057h
0x14000468c  jmp     short loc_1400046D9
0x14000468e  lea     rbx, [rdx-1]
0x140004692  mov     [rsp+48h+var_28], 0
0x14000469b  mov     rdx, rbx; BufferCount
0x14000469e  lea     r9, [rsp+48h+Args]; Args
0x1400046a3  call    _vsnwprintf
0x1400046a8  test    eax, eax
0x1400046aa  js      short loc_1400046C2
0x1400046ac  cdqe
0x1400046ae  cmp     rax, rbx
0x1400046b1  ja      short loc_1400046C2
0x1400046b3  xor     edx, edx
0x1400046b5  cmp     rax, rbx
0x1400046b8  jnz     short loc_1400046DE
0x1400046ba  xor     eax, eax
0x1400046bc  mov     [rdi+rbx*2], ax
0x1400046c0  jmp     short loc_1400046DE
0x1400046c2  xor     eax, eax
0x1400046c4  mov     edx, 8007007Ah
0x1400046c9  mov     [rdi+rbx*2], ax
0x1400046cd  jmp     short loc_1400046DE
0x1400046cf  mov     edx, 80070057h
0x1400046d4  test    rax, rax
0x1400046d7  jz      short loc_1400046DE
0x1400046d9  xor     ecx, ecx
0x1400046db  mov     [rdi], cx
0x1400046de  mov     eax, edx
0x1400046e0  add     rsp, 38h
0x1400046e4  pop     rdi
0x1400046e5  pop     rbx
0x1400046e6  retn
```
