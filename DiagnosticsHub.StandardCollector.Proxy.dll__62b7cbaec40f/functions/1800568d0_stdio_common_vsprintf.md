# __stdio_common_vsprintf

- ea: `0x1800568d0`
- end: `0x180056b21`
- name: `__stdio_common_vsprintf`
- size: `593`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002e270`
- `0x18002e3e4`

## callees

- `0x180002810`
- `0x18000774c`
- `0x180007b48`
- `0x180008040`
- `0x180044cb0`
- `0x1800568d0`

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
0x1800568d0  push    rbp
0x1800568d2  push    rbx
0x1800568d3  push    rsi
0x1800568d4  push    rdi
0x1800568d5  push    r12
0x1800568d7  push    r14
0x1800568d9  push    r15
0x1800568db  lea     rbp, [rsp-410h]
0x1800568e3  sub     rsp, 510h
0x1800568ea  mov     rax, cs:__security_cookie
0x1800568f1  xor     rax, rsp
0x1800568f4  mov     [rbp+440h+var_40], rax
0x1800568fb  mov     rax, [rbp+440h+Locale]
0x180056902  xor     r12d, r12d
0x180056905  mov     [rsp+540h+var_4F0], r12
0x18005690a  mov     rbx, r8
0x18005690d  mov     [rsp+540h+var_4E0], r12b
0x180056912  mov     rsi, rdx
0x180056915  mov     [rsp+540h+var_4C8], r12b
0x18005691a  mov     r15, rcx
0x18005691d  mov     [rbp+440h+var_4C0], r12b
0x180056921  mov     [rbp+440h+var_4B8], r12b
0x180056925  test    rax, rax
0x180056928  jz      short loc_18005692F
0x18005692a  movups  xmm0, xmmword ptr [rax]
0x18005692d  jmp     short loc_18005693F
0x18005692f  cmp     cs:__acrt_locale_changed_data, r12d
0x180056936  jnz     short loc_18005694A
0x180056938  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x18005693f  mov     [rsp+540h+var_4C8], 1
0x180056944  movdqu  [rsp+540h+var_4D8], xmm0
0x18005694a  test    r9, r9
0x18005694d  jnz     short loc_180056981
0x18005694f  lea     rax, [rsp+540h+var_4F0]
0x180056954  mov     [rbp+440h+var_4C0], 1
0x180056958  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x18005695d  xor     r9d, r9d; LineNo
0x180056960  xor     r8d, r8d; FileName
0x180056963  mov     [rsp+540h+var_520], r12; uintptr_t
0x180056968  xor     edx, edx; FunctionName
0x18005696a  mov     [rsp+540h+var_4C4], 16h
0x180056972  xor     ecx, ecx; Expression
0x180056974  call    _invalid_parameter_internal
0x180056979  or      edi, 0FFFFFFFFh
0x18005697c  jmp     loc_180056ABE
0x180056981  test    rbx, rbx
0x180056984  jz      short loc_18005698B
0x180056986  test    rsi, rsi
0x180056989  jz      short loc_18005694F
0x18005698b  mov     r14, r15
0x18005698e  mov     [rsp+540h+var_4F7], r12d
0x180056993  mov     [rsp+540h+var_4F3], r12w
0x180056999  mov     [rsp+540h+var_4F1], r12b
0x18005699e  mov     [rsp+540h+var_510], rsi
0x1800569a3  mov     [rsp+540h+var_508], rbx
0x1800569a8  mov     [rsp+540h+var_500], r12
0x1800569ad  and     r14d, 2
0x1800569b1  jnz     short loc_1800569BD
0x1800569b3  mov     [rsp+540h+var_4F8], r12b
0x1800569b8  test    rsi, rsi
0x1800569bb  jnz     short loc_1800569C2
0x1800569bd  mov     [rsp+540h+var_4F8], 1
0x1800569c2  lea     rax, [rsp+540h+var_4F0]
0x1800569c7  mov     [rbp+440h+var_490], r12d
0x1800569cb  mov     [rbp+440h+var_4A8], rax
0x1800569cf  lea     rcx, [rbp+440h+var_4B0]
0x1800569d3  lea     rax, [rsp+540h+var_510]
0x1800569d8  mov     [rbp+440h+var_48C], r12b
0x1800569dc  mov     [rbp+440h+var_50], rax
0x1800569e3  xorps   xmm0, xmm0
0x1800569e6  mov     rax, [rbp+440h+ArgList]
0x1800569ed  mov     [rbp+440h+var_498], rax
0x1800569f1  mov     [rbp+440h+var_488], r12
0x1800569f5  mov     [rbp+440h+var_480], r12d
0x1800569f9  mov     [rbp+440h+var_478], r12w
0x1800569fe  mov     [rbp+440h+var_468], r12d
0x180056a02  mov     [rbp+440h+var_464], r12b
0x180056a06  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x180056a0e  mov     [rbp+440h+var_4B0], r15
0x180056a12  mov     [rbp+440h+var_4A0], r9
0x180056a16  mov     [rbp+440h+var_48], r12d
0x180056a1d  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x180056a22  movsxd  rdi, eax
0x180056a25  test    rsi, rsi
0x180056a28  jz      loc_180056AB2
0x180056a2e  test    r15b, 1
0x180056a32  jz      short loc_180056A63
0x180056a34  test    rbx, rbx
0x180056a37  jnz     short loc_180056A4E
0x180056a39  test    eax, eax
0x180056a3b  jz      short loc_180056A4E
0x180056a3d  mov     rcx, [rbp+440h+Block+8]; Block
0x180056a44  call    _free_base
0x180056a49  jmp     loc_180056979
0x180056a4e  mov     rax, [rsp+540h+var_500]
0x180056a53  cmp     rax, rbx
0x180056a56  jnz     short loc_180056AAE
0x180056a58  test    edi, edi
0x180056a5a  js      short loc_180056AB2
0x180056a5c  cmp     rdi, rbx
0x180056a5f  jbe     short loc_180056AB2
0x180056a61  jmp     short loc_180056A3D
0x180056a63  test    r14, r14
0x180056a66  jz      short loc_180056A87
0x180056a68  test    rbx, rbx
0x180056a6b  jz      short loc_180056AB2
0x180056a6d  test    eax, eax
0x180056a6f  jns     short loc_180056A76
0x180056a71  mov     [rsi], r12b
0x180056a74  jmp     short loc_180056AB2
0x180056a76  mov     rax, [rsp+540h+var_500]
0x180056a7b  cmp     rax, rbx
0x180056a7e  jnz     short loc_180056AAE
0x180056a80  mov     [rbx+rsi-1], r12b
0x180056a85  jmp     short loc_180056AB2
0x180056a87  test    rbx, rbx
0x180056a8a  jz      short loc_180056A3D
0x180056a8c  mov     rax, [rsp+540h+var_500]
0x180056a91  cmp     rax, rbx
0x180056a94  jnz     short loc_180056AAE
0x180056a96  mov     rcx, [rbp+440h+Block+8]; Block
0x180056a9d  mov     [rbx+rsi-1], r12b
0x180056aa2  call    _free_base
0x180056aa7  mov     edi, 0FFFFFFFEh
0x180056aac  jmp     short loc_180056ABE
0x180056aae  mov     [rax+rsi], r12b
0x180056ab2  mov     rcx, [rbp+440h+Block+8]; Block
0x180056ab9  call    _free_base
0x180056abe  cmp     [rsp+540h+var_4C8], 2
0x180056ac3  jnz     short loc_180056AD1
0x180056ac5  mov     rax, [rsp+540h+var_4F0]
0x180056aca  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x180056ad1  cmp     [rbp+440h+var_4C0], r12b
0x180056ad5  jz      short loc_180056AE8
0x180056ad7  mov     ebx, [rsp+540h+var_4C4]
0x180056adb  lea     rcx, [rsp+540h+var_4F0]; this
0x180056ae0  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056ae5  mov     [rax+20h], ebx
0x180056ae8  cmp     [rbp+440h+var_4B8], r12b
0x180056aec  jz      short loc_180056AFE
0x180056aee  mov     ebx, [rbp+440h+var_4BC]
0x180056af1  lea     rcx, [rsp+540h+var_4F0]; this
0x180056af6  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056afb  mov     [rax+24h], ebx
0x180056afe  mov     eax, edi
0x180056b00  mov     rcx, [rbp+440h+var_40]
0x180056b07  xor     rcx, rsp; StackCookie
0x180056b0a  call    __security_check_cookie
0x180056b0f  add     rsp, 510h
0x180056b16  pop     r15
0x180056b18  pop     r14
0x180056b1a  pop     r12
0x180056b1c  pop     rdi
0x180056b1d  pop     rsi
0x180056b1e  pop     rbx
0x180056b1f  pop     rbp
0x180056b20  retn
```
