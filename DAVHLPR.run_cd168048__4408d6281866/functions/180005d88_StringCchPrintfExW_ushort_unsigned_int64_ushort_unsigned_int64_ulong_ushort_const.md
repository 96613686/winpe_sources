# StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)

- ea: `0x180005d88`
- end: `0x180005f45`
- name: `?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ`
- size: `445`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ba0`
- `0x180003300`

## callees

- `0x180005d88`
- `0x180005f4c`
- `0x1800060d9`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180005ecc`
- `msvcrt!_vsnwprintf` at `0x180005ecc`

## pseudocode

```c
__int64 StringCchPrintfExW(
        wchar_t *Buffer,
        size_t a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        DWORD dwFlags,
        const unsigned __int16 *a6,
        ...)
{
  bool v8; // cc
  int v9; // ebx
  const unsigned __int16 *v10; // r8
  STRSAFE_LPWSTR v11; // r13
  size_t v12; // r15
  unsigned __int64 v14; // rsi
  int v15; // eax
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-18h] BYREF
  size_t pcchRemaining[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned __int64 *v19; // [rsp+A8h] [rbp+60h]
  va_list Args; // [rsp+C0h] [rbp+78h] BYREF

  va_start(Args, a6);
  v19 = a4;
  if ( (dwFlags & 0x100) != 0 )
  {
    if ( !Buffer && a2 )
    {
LABEL_7:
      v9 = -2147024809;
      if ( a2 )
        *Buffer = 0;
      return (unsigned int)v9;
    }
    v8 = a2 <= 0x7FFFFFFF;
  }
  else
  {
    v8 = a2 - 1 <= 0x7FFFFFFE;
  }
  if ( !v8 )
    goto LABEL_7;
  v10 = a6;
  v11 = Buffer;
  ppszDestEnd = Buffer;
  v12 = a2;
  pcchRemaining[0] = a2;
  if ( (dwFlags & 0x100) != 0 && !a6 )
    v10 = (const unsigned __int16 *)&Format;
  if ( (dwFlags & 0xFFFFE000) != 0 )
  {
    v9 = -2147024809;
    if ( a2 )
      *Buffer = 0;
    goto LABEL_15;
  }
  if ( !a2 )
  {
    v9 = 0;
    if ( !*v10 )
      goto LABEL_20;
    v9 = Buffer != 0 ? -2147024774 : -2147024809;
    goto LABEL_15;
  }
  pcchRemaining[0] = 0;
  v14 = a2 - 1;
  v15 = _vsnwprintf(Buffer, a2 - 1, v10, Args);
  if ( v15 < 0 || v15 > v14 )
  {
    v9 = -2147024774;
  }
  else
  {
    v9 = 0;
    if ( v15 != v14 )
    {
      v14 = v15;
      goto LABEL_34;
    }
  }
  Buffer[v14] = 0;
LABEL_34:
  v12 = a2 - v14;
  v11 = &Buffer[v14];
  ppszDestEnd = v11;
  pcchRemaining[0] = a2 - v14;
  if ( v9 >= 0 )
  {
    if ( (dwFlags & 0x200) != 0 && v12 > 1 && 2 * v12 > 2 )
      memset_0(v11 + 1, (unsigned __int8)dwFlags, 2 * v12 - 2);
    goto LABEL_19;
  }
LABEL_15:
  if ( (dwFlags & 0x1C00) != 0 && a2 )
  {
    StringExHandleOtherFlagsW(Buffer, 2 * a2, (size_t)v10, &ppszDestEnd, pcchRemaining, dwFlags);
    v11 = ppszDestEnd;
    v12 = pcchRemaining[0];
  }
  if ( v9 == -2147024774 )
  {
LABEL_19:
    a4 = v19;
LABEL_20:
    if ( a3 )
      *a3 = v11;
    if ( a4 )
      *a4 = v12;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005d88  mov     [rsp-40h+arg_18], r9
0x180005d8d  mov     [rsp-40h+arg_10], r8
0x180005d92  push    rbp
0x180005d93  push    rbx
0x180005d94  push    rsi
0x180005d95  push    rdi
0x180005d96  push    r12
0x180005d98  push    r13
0x180005d9a  push    r14
0x180005d9c  push    r15
0x180005d9e  mov     rbp, rsp
0x180005da1  sub     rsp, 48h
0x180005da5  mov     r12d, [rbp+arg_20]
0x180005da9  mov     r14, rcx
0x180005dac  mov     ecx, r12d
0x180005daf  xor     esi, esi
0x180005db1  mov     rdi, rdx
0x180005db4  and     ecx, 100h
0x180005dba  jz      short loc_180005DCF
0x180005dbc  test    r14, r14
0x180005dbf  jnz     short loc_180005DC6
0x180005dc1  test    rdx, rdx
0x180005dc4  jnz     short loc_180005DDB
0x180005dc6  cmp     rdi, 7FFFFFFFh
0x180005dcd  jmp     short loc_180005DD9
0x180005dcf  lea     rax, [rdx-1]
0x180005dd3  cmp     rax, 7FFFFFFEh
0x180005dd9  jbe     short loc_180005DF2
0x180005ddb  mov     ebx, 80070057h
0x180005de0  test    rdi, rdi
0x180005de3  jz      loc_180005E83
0x180005de9  mov     [r14], si
0x180005ded  jmp     loc_180005E83
0x180005df2  mov     r8, [rbp+arg_28]
0x180005df6  mov     r13, r14
0x180005df9  mov     [rbp+ppszDestEnd], r14
0x180005dfd  mov     r15, rdi
0x180005e00  mov     [rbp+var_10], rdi
0x180005e04  test    ecx, ecx
0x180005e06  jz      short loc_180005E18
0x180005e08  test    r8, r8
0x180005e0b  jnz     short loc_180005E18
0x180005e0d  lea     r8, Format; Format
0x180005e14  mov     [rbp+arg_28], r8
0x180005e18  test    r12d, 0FFFFE000h
0x180005e1f  jz      short loc_180005E96
0x180005e21  mov     ebx, 80070057h
0x180005e26  test    rdi, rdi
0x180005e29  jz      short loc_180005E2F
0x180005e2b  mov     [r14], si
0x180005e2f  test    r12d, 1C00h
0x180005e36  jz      short loc_180005E63
0x180005e38  test    rdi, rdi
0x180005e3b  jz      short loc_180005E63
0x180005e3d  lea     rax, [rbp+var_10]
0x180005e41  mov     [rsp+48h+dwFlags], r12d; dwFlags
0x180005e46  lea     rdx, [rdi+rdi]; cbDest
0x180005e4a  mov     [rsp+48h+pcchRemaining], rax; pcchRemaining
0x180005e4f  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x180005e53  mov     rcx, r14; pszDest
0x180005e56  call    StringExHandleOtherFlagsW
0x180005e5b  mov     r13, [rbp+ppszDestEnd]
0x180005e5f  mov     r15, [rbp+var_10]
0x180005e63  cmp     ebx, 8007007Ah
0x180005e69  jnz     short loc_180005E83
0x180005e6b  mov     r9, [rbp+arg_18]
0x180005e6f  mov     rax, [rbp+arg_10]
0x180005e73  test    rax, rax
0x180005e76  jz      short loc_180005E7B
0x180005e78  mov     [rax], r13
0x180005e7b  test    r9, r9
0x180005e7e  jz      short loc_180005E83
0x180005e80  mov     [r9], r15
0x180005e83  mov     eax, ebx
0x180005e85  add     rsp, 48h
0x180005e89  pop     r15
0x180005e8b  pop     r14
0x180005e8d  pop     r13
0x180005e8f  pop     r12
0x180005e91  pop     rdi
0x180005e92  pop     rsi
0x180005e93  pop     rbx
0x180005e94  pop     rbp
0x180005e95  retn
0x180005e96  test    rdi, rdi
0x180005e99  jnz     short loc_180005EBA
0x180005e9b  mov     ebx, esi
0x180005e9d  cmp     [r8], si
0x180005ea1  jz      short loc_180005E6F
0x180005ea3  mov     rax, r14
0x180005ea6  mov     ebx, 80070057h
0x180005eab  neg     rax
0x180005eae  sbb     ecx, ecx
0x180005eb0  and     ecx, 23h
0x180005eb3  add     ebx, ecx
0x180005eb5  jmp     loc_180005E2F
0x180005eba  mov     [rbp+var_10], rsi
0x180005ebe  lea     r9, [rbp+Args]; Args
0x180005ec2  lea     rsi, [rdx-1]
0x180005ec6  mov     rcx, r14; Buffer
0x180005ec9  mov     rdx, rsi; BufferCount
0x180005ecc  call    cs:__imp__vsnwprintf
0x180005ed2  test    eax, eax
0x180005ed4  js      short loc_180005EE9
0x180005ed6  cdqe
0x180005ed8  cmp     rax, rsi
0x180005edb  ja      short loc_180005EE9
0x180005edd  xor     ebx, ebx
0x180005edf  cmp     rax, rsi
0x180005ee2  jz      short loc_180005EEE
0x180005ee4  mov     rsi, rax
0x180005ee7  jmp     short loc_180005EF5
0x180005ee9  mov     ebx, 8007007Ah
0x180005eee  xor     eax, eax
0x180005ef0  mov     [r14+rsi*2], ax
0x180005ef5  sub     r15, rsi
0x180005ef8  lea     r13, [r14+rsi*2]
0x180005efc  mov     [rbp+ppszDestEnd], r13
0x180005f00  mov     [rbp+var_10], r15
0x180005f04  test    ebx, ebx
0x180005f06  js      loc_180005E2F
0x180005f0c  bt      r12d, 9
0x180005f11  jnb     loc_180005E6B
0x180005f17  cmp     r15, 1
0x180005f1b  jbe     loc_180005E6B
0x180005f21  lea     r8, [r15+r15]
0x180005f25  cmp     r8, 2
0x180005f29  jbe     loc_180005E6B
0x180005f2f  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180005f33  movzx   edx, r12b; Val
0x180005f37  lea     rcx, [r13+2]; void *
0x180005f3b  call    memset_0
0x180005f40  jmp     loc_180005E6B
```
