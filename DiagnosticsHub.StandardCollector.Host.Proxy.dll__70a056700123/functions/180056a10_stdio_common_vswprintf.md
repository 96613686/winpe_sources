# __stdio_common_vswprintf

- ea: `0x180056a10`
- end: `0x180056c69`
- name: `__stdio_common_vswprintf`
- size: `601`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x180045c3c`
- `0x180056a10`

## pseudocode

```c
int __cdecl _stdio_common_vswprintf(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  char v8; // r15
  __crt_locale_pointers v9; // xmm0
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
  __crt_locale_pointers v25; // [rsp+68h] [rbp-98h]
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
  char v36; // [rsp+C8h] [rbp-38h]
  __int16 v37; // [rsp+CAh] [rbp-36h]
  int v38; // [rsp+D8h] [rbp-28h]
  char v39; // [rsp+DCh] [rbp-24h]
  void *Block[2]; // [rsp+4E0h] [rbp+3E0h]
  _QWORD *v41; // [rsp+4F0h] [rbp+3F0h]
  int v42; // [rsp+4F8h] [rbp+3F8h]

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
  if ( !_acrt_locale_changed_data )
  {
    v9 = *(__crt_locale_pointers *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
LABEL_6:
  if ( !Format || BufferCount && !Buffer )
  {
    v28 = 1;
    v27 = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v23);
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
  v41 = v17;
  v31[3] = ArgList;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  *(_OWORD *)Block = 0;
  v31[0] = Options;
  v31[2] = Format;
  v42 = 0;
  v11 = __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(v31);
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
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v23) + 8) = v14;
  }
  if ( v30 )
  {
    v15 = v29;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v23) + 9) = v15;
  }
  return v10;
}

```

## disassembly

```asm
0x180056a10  push    rbp
0x180056a12  push    rbx
0x180056a13  push    rsi
0x180056a14  push    rdi
0x180056a15  push    r12
0x180056a17  push    r14
0x180056a19  push    r15
0x180056a1b  lea     rbp, [rsp-410h]
0x180056a23  sub     rsp, 510h
0x180056a2a  mov     rax, cs:__security_cookie
0x180056a31  xor     rax, rsp
0x180056a34  mov     [rbp+440h+var_40], rax
0x180056a3b  mov     rax, [rbp+440h+Locale]
0x180056a42  xor     r12d, r12d
0x180056a45  mov     [rsp+540h+var_4F0], r12
0x180056a4a  mov     rbx, r8
0x180056a4d  mov     [rsp+540h+var_4E0], r12b
0x180056a52  mov     rsi, rdx
0x180056a55  mov     [rsp+540h+var_4C8], r12b
0x180056a5a  mov     r15, rcx
0x180056a5d  mov     [rbp+440h+var_4C0], r12b
0x180056a61  mov     [rbp+440h+var_4B8], r12b
0x180056a65  test    rax, rax
0x180056a68  jz      short loc_180056A6F
0x180056a6a  movups  xmm0, xmmword ptr [rax]
0x180056a6d  jmp     short loc_180056A7F
0x180056a6f  cmp     cs:__acrt_locale_changed_data, r12d
0x180056a76  jnz     short loc_180056A8A
0x180056a78  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056a7f  mov     [rsp+540h+var_4C8], 1
0x180056a84  movdqu  [rsp+540h+var_4D8], xmm0
0x180056a8a  test    r9, r9
0x180056a8d  jnz     short loc_180056AC1
0x180056a8f  lea     rax, [rsp+540h+var_4F0]
0x180056a94  mov     [rbp+440h+var_4C0], 1
0x180056a98  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x180056a9d  xor     r9d, r9d; LineNo
0x180056aa0  xor     r8d, r8d; FileName
0x180056aa3  mov     [rsp+540h+var_520], r12; uintptr_t
0x180056aa8  xor     edx, edx; FunctionName
0x180056aaa  mov     [rsp+540h+var_4C4], 16h
0x180056ab2  xor     ecx, ecx; Expression
0x180056ab4  call    _invalid_parameter_internal
0x180056ab9  or      edi, 0FFFFFFFFh
0x180056abc  jmp     loc_180056C06
0x180056ac1  test    rbx, rbx
0x180056ac4  jz      short loc_180056ACB
0x180056ac6  test    rsi, rsi
0x180056ac9  jz      short loc_180056A8F
0x180056acb  mov     r14, r15
0x180056ace  mov     [rsp+540h+var_4F7], r12d
0x180056ad3  mov     [rsp+540h+var_4F3], r12w
0x180056ad9  mov     [rsp+540h+var_4F1], r12b
0x180056ade  mov     [rsp+540h+var_510], rsi
0x180056ae3  mov     [rsp+540h+var_508], rbx
0x180056ae8  mov     [rsp+540h+var_500], r12
0x180056aed  and     r14d, 2
0x180056af1  jnz     short loc_180056AFD
0x180056af3  mov     [rsp+540h+var_4F8], r12b
0x180056af8  test    rsi, rsi
0x180056afb  jnz     short loc_180056B02
0x180056afd  mov     [rsp+540h+var_4F8], 1
0x180056b02  lea     rax, [rsp+540h+var_4F0]
0x180056b07  mov     [rbp+440h+var_490], r12d
0x180056b0b  mov     [rbp+440h+var_4A8], rax
0x180056b0f  lea     rcx, [rbp+440h+var_4B0]
0x180056b13  lea     rax, [rsp+540h+var_510]
0x180056b18  mov     [rbp+440h+var_48C], r12b
0x180056b1c  mov     [rbp+440h+var_50], rax
0x180056b23  xorps   xmm0, xmm0
0x180056b26  mov     rax, [rbp+440h+ArgList]
0x180056b2d  mov     [rbp+440h+var_498], rax
0x180056b31  mov     [rbp+440h+var_488], r12
0x180056b35  mov     [rbp+440h+var_480], r12d
0x180056b39  mov     [rbp+440h+var_478], r12b
0x180056b3d  mov     [rbp+440h+var_476], r12w
0x180056b42  mov     [rbp+440h+var_468], r12d
0x180056b46  mov     [rbp+440h+var_464], r12b
0x180056b4a  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x180056b52  mov     [rbp+440h+var_4B0], r15
0x180056b56  mov     [rbp+440h+var_4A0], r9
0x180056b5a  mov     [rbp+440h+var_48], r12d
0x180056b61  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x180056b66  movsxd  rdi, eax
0x180056b69  test    rsi, rsi
0x180056b6c  jz      loc_180056BFA
0x180056b72  test    r15b, 1
0x180056b76  jz      short loc_180056BA7
0x180056b78  test    rbx, rbx
0x180056b7b  jnz     short loc_180056B92
0x180056b7d  test    eax, eax
0x180056b7f  jz      short loc_180056B92
0x180056b81  mov     rcx, [rbp+440h+Block+8]; Block
0x180056b88  call    _free_base
0x180056b8d  jmp     loc_180056AB9
0x180056b92  mov     rax, [rsp+540h+var_500]
0x180056b97  cmp     rax, rbx
0x180056b9a  jnz     short loc_180056BF5
0x180056b9c  test    edi, edi
0x180056b9e  js      short loc_180056BFA
0x180056ba0  cmp     rdi, rbx
0x180056ba3  jbe     short loc_180056BFA
0x180056ba5  jmp     short loc_180056B81
0x180056ba7  test    r14, r14
0x180056baa  jz      short loc_180056BCD
0x180056bac  test    rbx, rbx
0x180056baf  jz      short loc_180056BFA
0x180056bb1  test    eax, eax
0x180056bb3  jns     short loc_180056BBB
0x180056bb5  mov     [rsi], r12w
0x180056bb9  jmp     short loc_180056BFA
0x180056bbb  mov     rax, [rsp+540h+var_500]
0x180056bc0  cmp     rax, rbx
0x180056bc3  jnz     short loc_180056BF5
0x180056bc5  mov     [rsi+rbx*2-2], r12w
0x180056bcb  jmp     short loc_180056BFA
0x180056bcd  test    rbx, rbx
0x180056bd0  jz      short loc_180056B81
0x180056bd2  mov     rax, [rsp+540h+var_500]
0x180056bd7  cmp     rax, rbx
0x180056bda  jnz     short loc_180056BF5
0x180056bdc  mov     rcx, [rbp+440h+Block+8]; Block
0x180056be3  mov     [rsi+rbx*2-2], r12w
0x180056be9  call    _free_base
0x180056bee  mov     edi, 0FFFFFFFEh
0x180056bf3  jmp     short loc_180056C06
0x180056bf5  mov     [rsi+rax*2], r12w
0x180056bfa  mov     rcx, [rbp+440h+Block+8]; Block
0x180056c01  call    _free_base
0x180056c06  cmp     [rsp+540h+var_4C8], 2
0x180056c0b  jnz     short loc_180056C19
0x180056c0d  mov     rax, [rsp+540h+var_4F0]
0x180056c12  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x180056c19  cmp     [rbp+440h+var_4C0], r12b
0x180056c1d  jz      short loc_180056C30
0x180056c1f  mov     ebx, [rsp+540h+var_4C4]
0x180056c23  lea     rcx, [rsp+540h+var_4F0]; this
0x180056c28  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056c2d  mov     [rax+20h], ebx
0x180056c30  cmp     [rbp+440h+var_4B8], r12b
0x180056c34  jz      short loc_180056C46
0x180056c36  mov     ebx, [rbp+440h+var_4BC]
0x180056c39  lea     rcx, [rsp+540h+var_4F0]; this
0x180056c3e  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056c43  mov     [rax+24h], ebx
0x180056c46  mov     eax, edi
0x180056c48  mov     rcx, [rbp+440h+var_40]
0x180056c4f  xor     rcx, rsp; StackCookie
0x180056c52  call    __security_check_cookie
0x180056c57  add     rsp, 510h
0x180056c5e  pop     r15
0x180056c60  pop     r14
0x180056c62  pop     r12
0x180056c64  pop     rdi
0x180056c65  pop     rsi
0x180056c66  pop     rbx
0x180056c67  pop     rbp
0x180056c68  retn
```
