# __stdio_common_vsprintf

- ea: `0x14000f3f0`
- end: `0x14000f641`
- name: `__stdio_common_vsprintf`
- size: `593`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003a808`
- `0x1400a6654`
- `0x1400a8230`

## callees

- `0x1400042e0`
- `0x140004614`
- `0x14000d6dc`
- `0x14000f3f0`
- `0x1400107c4`
- `0x14001bf00`

## pseudocode

```c
int __cdecl _stdio_common_vsprintf(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  char v8; // r15
  struct localeinfo_struct v9; // xmm0
  size_t v10; // rdi
  int v11; // eax
  __int64 v12; // rax
  void *v13; // rcx
  int v14; // ebx
  int v15; // ebx
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h]
  char v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+49h] [rbp-B7h]
  __int16 v21; // [rsp+4Dh] [rbp-B3h]
  char v22; // [rsp+4Fh] [rbp-B1h]
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+60h] [rbp-A0h]
  struct localeinfo_struct v25; // [rsp+68h] [rbp-98h]
  char v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+7Ch] [rbp-84h]
  char v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+84h] [rbp-7Ch]
  char v30; // [rsp+88h] [rbp-78h]
  _QWORD v31[4]; // [rsp+90h] [rbp-70h] BYREF
  int v32; // [rsp+B0h] [rbp-50h]
  char v33; // [rsp+B4h] [rbp-4Ch]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  int v35; // [rsp+C0h] [rbp-40h]
  __int16 v36; // [rsp+C8h] [rbp-38h]
  int v37; // [rsp+D8h] [rbp-28h]
  char v38; // [rsp+DCh] [rbp-24h]
  void *Block[2]; // [rsp+4E0h] [rbp+3E0h]
  _QWORD *v40; // [rsp+4F0h] [rbp+3F0h]
  int v41; // [rsp+4F8h] [rbp+3F8h]

  v23[0] = 0;
  v24 = 0;
  v26 = 0;
  v8 = Options;
  v28 = 0;
  v30 = 0;
  if ( Locale )
  {
    v9 = *Locale;
LABEL_5:
    v26 = 1;
    v25 = v9;
    goto LABEL_6;
  }
  if ( !dword_1400D6988 )
  {
    v9 = *(struct localeinfo_struct *)&off_1400D5158;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || BufferCount && !Buffer )
  {
    v28 = 1;
    v27 = 22;
    sub_140004614(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v23);
LABEL_8:
    LODWORD(v10) = -1;
    goto LABEL_34;
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v17[0] = Buffer;
  v17[1] = BufferCount;
  v18 = 0;
  if ( (Options & 2) != 0 || (v19 = 0, !Buffer) )
    v19 = 1;
  v32 = 0;
  v31[1] = v23;
  v33 = 0;
  v40 = v17;
  v31[3] = ArgList;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)Block = 0;
  v31[0] = Options;
  v31[2] = Format;
  v41 = 0;
  v11 = __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(v31);
  v10 = v11;
  if ( !Buffer )
    goto LABEL_33;
  if ( (v8 & 1) != 0 )
  {
    if ( !BufferCount && v11 )
      goto LABEL_18;
    v12 = v18;
    if ( v18 == BufferCount )
    {
      if ( (v10 & 0x80000000) == 0LL && v10 > BufferCount )
        goto LABEL_18;
      goto LABEL_33;
    }
    goto LABEL_32;
  }
  if ( (v8 & 2) == 0 )
  {
    if ( !BufferCount )
    {
LABEL_18:
      free_base(Block[1]);
      goto LABEL_8;
    }
    v12 = v18;
    if ( v18 == BufferCount )
    {
      v13 = Block[1];
      Buffer[BufferCount - 1] = 0;
      free_base(v13);
      LODWORD(v10) = -2;
      goto LABEL_34;
    }
    goto LABEL_32;
  }
  if ( BufferCount )
  {
    if ( v11 < 0 )
    {
      *Buffer = 0;
      goto LABEL_33;
    }
    v12 = v18;
    if ( v18 == BufferCount )
    {
      Buffer[BufferCount - 1] = 0;
      goto LABEL_33;
    }
LABEL_32:
    Buffer[v12] = 0;
  }
LABEL_33:
  free_base(Block[1]);
LABEL_34:
  if ( v26 == 2 )
    *(_DWORD *)(v23[0] + 936LL) &= ~2u;
  if ( v28 )
  {
    v14 = v27;
    *(_DWORD *)(unknown_libname_44(v23) + 32) = v14;
  }
  if ( v30 )
  {
    v15 = v29;
    *(_DWORD *)(unknown_libname_44(v23) + 36) = v15;
  }
  return v10;
}

```

## disassembly

```asm
0x14000f3f0  push    rbp
0x14000f3f2  push    rbx
0x14000f3f3  push    rsi
0x14000f3f4  push    rdi
0x14000f3f5  push    r12
0x14000f3f7  push    r14
0x14000f3f9  push    r15
0x14000f3fb  lea     rbp, [rsp-410h]
0x14000f403  sub     rsp, 510h
0x14000f40a  mov     rax, cs:__security_cookie
0x14000f411  xor     rax, rsp
0x14000f414  mov     [rbp+440h+var_40], rax
0x14000f41b  mov     rax, [rbp+440h+Locale]
0x14000f422  xor     r12d, r12d
0x14000f425  mov     [rsp+540h+var_4F0], r12
0x14000f42a  mov     rbx, r8
0x14000f42d  mov     [rsp+540h+var_4E0], r12b
0x14000f432  mov     rsi, rdx
0x14000f435  mov     [rsp+540h+var_4C8], r12b
0x14000f43a  mov     r15, rcx
0x14000f43d  mov     [rbp+440h+var_4C0], r12b
0x14000f441  mov     [rbp+440h+var_4B8], r12b
0x14000f445  test    rax, rax
0x14000f448  jz      short loc_14000F44F
0x14000f44a  movups  xmm0, xmmword ptr [rax]
0x14000f44d  jmp     short loc_14000F45F
0x14000f44f  cmp     cs:dword_1400D6988, r12d
0x14000f456  jnz     short loc_14000F46A
0x14000f458  movups  xmm0, xmmword ptr cs:off_1400D5158
0x14000f45f  mov     [rsp+540h+var_4C8], 1
0x14000f464  movdqu  [rsp+540h+var_4D8], xmm0
0x14000f46a  test    r9, r9
0x14000f46d  jnz     short loc_14000F4A1
0x14000f46f  lea     rax, [rsp+540h+var_4F0]
0x14000f474  mov     [rbp+440h+var_4C0], 1
0x14000f478  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x14000f47d  xor     r9d, r9d; LineNo
0x14000f480  xor     r8d, r8d; FileName
0x14000f483  mov     [rsp+540h+var_520], r12; uintptr_t
0x14000f488  xor     edx, edx; FunctionName
0x14000f48a  mov     [rsp+540h+var_4C4], 16h
0x14000f492  xor     ecx, ecx; Expression
0x14000f494  call    sub_140004614
0x14000f499  or      edi, 0FFFFFFFFh
0x14000f49c  jmp     loc_14000F5DE
0x14000f4a1  test    rbx, rbx
0x14000f4a4  jz      short loc_14000F4AB
0x14000f4a6  test    rsi, rsi
0x14000f4a9  jz      short loc_14000F46F
0x14000f4ab  mov     r14, r15
0x14000f4ae  mov     [rsp+540h+var_4F7], r12d
0x14000f4b3  mov     [rsp+540h+var_4F3], r12w
0x14000f4b9  mov     [rsp+540h+var_4F1], r12b
0x14000f4be  mov     [rsp+540h+var_510], rsi
0x14000f4c3  mov     [rsp+540h+var_508], rbx
0x14000f4c8  mov     [rsp+540h+var_500], r12
0x14000f4cd  and     r14d, 2
0x14000f4d1  jnz     short loc_14000F4DD
0x14000f4d3  mov     [rsp+540h+var_4F8], r12b
0x14000f4d8  test    rsi, rsi
0x14000f4db  jnz     short loc_14000F4E2
0x14000f4dd  mov     [rsp+540h+var_4F8], 1
0x14000f4e2  lea     rax, [rsp+540h+var_4F0]
0x14000f4e7  mov     [rbp+440h+var_490], r12d
0x14000f4eb  mov     [rbp+440h+var_4A8], rax
0x14000f4ef  lea     rcx, [rbp+440h+var_4B0]
0x14000f4f3  lea     rax, [rsp+540h+var_510]
0x14000f4f8  mov     [rbp+440h+var_48C], r12b
0x14000f4fc  mov     [rbp+440h+var_50], rax
0x14000f503  xorps   xmm0, xmm0
0x14000f506  mov     rax, [rbp+440h+ArgList]
0x14000f50d  mov     [rbp+440h+var_498], rax
0x14000f511  mov     [rbp+440h+var_488], r12
0x14000f515  mov     [rbp+440h+var_480], r12d
0x14000f519  mov     [rbp+440h+var_478], r12w
0x14000f51e  mov     [rbp+440h+var_468], r12d
0x14000f522  mov     [rbp+440h+var_464], r12b
0x14000f526  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x14000f52e  mov     [rbp+440h+var_4B0], r15
0x14000f532  mov     [rbp+440h+var_4A0], r9
0x14000f536  mov     [rbp+440h+var_48], r12d
0x14000f53d  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ
0x14000f542  movsxd  rdi, eax
0x14000f545  test    rsi, rsi
0x14000f548  jz      loc_14000F5D2
0x14000f54e  test    r15b, 1
0x14000f552  jz      short loc_14000F583
0x14000f554  test    rbx, rbx
0x14000f557  jnz     short loc_14000F56E
0x14000f559  test    eax, eax
0x14000f55b  jz      short loc_14000F56E
0x14000f55d  mov     rcx, [rbp+440h+Block+8]; Block
0x14000f564  call    _free_base
0x14000f569  jmp     loc_14000F499
0x14000f56e  mov     rax, [rsp+540h+var_500]
0x14000f573  cmp     rax, rbx
0x14000f576  jnz     short loc_14000F5CE
0x14000f578  test    edi, edi
0x14000f57a  js      short loc_14000F5D2
0x14000f57c  cmp     rdi, rbx
0x14000f57f  jbe     short loc_14000F5D2
0x14000f581  jmp     short loc_14000F55D
0x14000f583  test    r14, r14
0x14000f586  jz      short loc_14000F5A7
0x14000f588  test    rbx, rbx
0x14000f58b  jz      short loc_14000F5D2
0x14000f58d  test    eax, eax
0x14000f58f  jns     short loc_14000F596
0x14000f591  mov     [rsi], r12b
0x14000f594  jmp     short loc_14000F5D2
0x14000f596  mov     rax, [rsp+540h+var_500]
0x14000f59b  cmp     rax, rbx
0x14000f59e  jnz     short loc_14000F5CE
0x14000f5a0  mov     [rbx+rsi-1], r12b
0x14000f5a5  jmp     short loc_14000F5D2
0x14000f5a7  test    rbx, rbx
0x14000f5aa  jz      short loc_14000F55D
0x14000f5ac  mov     rax, [rsp+540h+var_500]
0x14000f5b1  cmp     rax, rbx
0x14000f5b4  jnz     short loc_14000F5CE
0x14000f5b6  mov     rcx, [rbp+440h+Block+8]; Block
0x14000f5bd  mov     [rbx+rsi-1], r12b
0x14000f5c2  call    _free_base
0x14000f5c7  mov     edi, 0FFFFFFFEh
0x14000f5cc  jmp     short loc_14000F5DE
0x14000f5ce  mov     [rax+rsi], r12b
0x14000f5d2  mov     rcx, [rbp+440h+Block+8]; Block
0x14000f5d9  call    _free_base
0x14000f5de  cmp     [rsp+540h+var_4C8], 2
0x14000f5e3  jnz     short loc_14000F5F1
0x14000f5e5  mov     rax, [rsp+540h+var_4F0]
0x14000f5ea  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x14000f5f1  cmp     [rbp+440h+var_4C0], r12b
0x14000f5f5  jz      short loc_14000F608
0x14000f5f7  mov     ebx, [rsp+540h+var_4C4]
0x14000f5fb  lea     rcx, [rsp+540h+var_4F0]
0x14000f600  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14000f605  mov     [rax+20h], ebx
0x14000f608  cmp     [rbp+440h+var_4B8], r12b
0x14000f60c  jz      short loc_14000F61E
0x14000f60e  mov     ebx, [rbp+440h+var_4BC]
0x14000f611  lea     rcx, [rsp+540h+var_4F0]
0x14000f616  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14000f61b  mov     [rax+24h], ebx
0x14000f61e  mov     eax, edi
0x14000f620  mov     rcx, [rbp+440h+var_40]
0x14000f627  xor     rcx, rsp; StackCookie
0x14000f62a  call    __security_check_cookie
0x14000f62f  add     rsp, 510h
0x14000f636  pop     r15
0x14000f638  pop     r14
0x14000f63a  pop     r12
0x14000f63c  pop     rdi
0x14000f63d  pop     rsi
0x14000f63e  pop     rbx
0x14000f63f  pop     rbp
0x14000f640  retn
```
