# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180005d80`
- end: `0x180005e37`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `183`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const wchar_t *, ...)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005e40`
- `0x180009a28`
- `0x18000c808`
- `0x18000d6f8`
- `0x1800162be`
- `0x1800163af`
- `0x1800164e8`
- `0x18001655e`

## callees

- `0x180005d80`
- `0x180006ac4`
- `0x18000ec31`
- `0x18000ed40`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, __int64 a2, const wchar_t *a3, ...)
{
  unsigned int v5; // edi
  size_t v6; // rsi
  unsigned __int64 *v7; // rax
  int v8; // eax
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v5 = 0;
    v6 = a2 - 1;
    v7 = _local_stdio_printf_options();
    v8 = o___stdio_common_vswprintf_0(*v7 | 1, Buffer, v6, a3, 0, va);
    if ( v8 < 0 )
      v8 = -1;
    if ( v8 < 0 || v8 > v6 )
    {
      v5 = -2147024774;
    }
    else if ( v8 != v6 )
    {
      return v5;
    }
    Buffer[v6] = 0;
    return v5;
  }
  v5 = -2147024809;
  if ( a2 )
    *Buffer = 0;
  return v5;
}

```

## disassembly

```asm
0x180005d80  mov     [rsp+arg_10], r8
0x180005d85  mov     qword ptr [rsp+arg_18], r9
0x180005d8a  push    rbx
0x180005d8b  push    rbp
0x180005d8c  push    rsi
0x180005d8d  push    rdi
0x180005d8e  push    r14
0x180005d90  push    r15
0x180005d92  sub     rsp, 48h
0x180005d96  mov     rax, cs:__security_cookie
0x180005d9d  xor     rax, rsp
0x180005da0  mov     [rsp+78h+var_40], rax
0x180005da5  lea     rax, [rdx-1]
0x180005da9  xor     ebx, ebx
0x180005dab  mov     rbp, r8
0x180005dae  mov     r14, rcx
0x180005db1  cmp     rax, 7FFFFFFEh
0x180005db7  jbe     short loc_180005DC8
0x180005db9  mov     edi, 80070057h
0x180005dbe  test    rdx, rdx
0x180005dc1  jz      short loc_180005E1B
0x180005dc3  mov     [rcx], bx
0x180005dc6  jmp     short loc_180005E1B
0x180005dc8  lea     r15, [rsp+78h+arg_18]
0x180005dd0  mov     edi, ebx
0x180005dd2  lea     rsi, [rdx-1]
0x180005dd6  call    __local_stdio_printf_options
0x180005ddb  mov     [rsp+78h+ArgList], r15; ArgList
0x180005de0  mov     r9, rbp; Format
0x180005de3  mov     r8, rsi; BufferCount
0x180005de6  mov     [rsp+78h+Locale], rbx; Locale
0x180005deb  mov     rdx, r14; Buffer
0x180005dee  mov     rcx, [rax]
0x180005df1  or      rcx, 1; Options
0x180005df5  call    _o___stdio_common_vswprintf_0
0x180005dfa  or      ecx, 0FFFFFFFFh
0x180005dfd  test    eax, eax
0x180005dff  cmovs   eax, ecx
0x180005e02  test    eax, eax
0x180005e04  js      short loc_180005E11
0x180005e06  cdqe
0x180005e08  cmp     rax, rsi
0x180005e0b  ja      short loc_180005E11
0x180005e0d  jnz     short loc_180005E1B
0x180005e0f  jmp     short loc_180005E16
0x180005e11  mov     edi, 8007007Ah
0x180005e16  mov     [r14+rsi*2], bx
0x180005e1b  mov     eax, edi
0x180005e1d  mov     rcx, [rsp+78h+var_40]
0x180005e22  xor     rcx, rsp; StackCookie
0x180005e25  call    __security_check_cookie
0x180005e2a  add     rsp, 48h
0x180005e2e  pop     r15
0x180005e30  pop     r14
0x180005e32  pop     rdi
0x180005e33  pop     rsi
0x180005e34  pop     rbp
0x180005e35  pop     rbx
0x180005e36  retn
```
