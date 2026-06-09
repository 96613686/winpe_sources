# __stdio_common_vsprintf

- ea: `0x1800565f0`
- end: `0x180056841`
- name: `__stdio_common_vsprintf`
- size: `593`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002db10`
- `0x18002dc84`

## callees

- `0x180006fec`
- `0x1800073e8`
- `0x1800078e0`
- `0x180032370`
- `0x1800449d0`
- `0x1800565f0`

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
0x1800565f0  push    rbp
0x1800565f2  push    rbx
0x1800565f3  push    rsi
0x1800565f4  push    rdi
0x1800565f5  push    r12
0x1800565f7  push    r14
0x1800565f9  push    r15
0x1800565fb  lea     rbp, [rsp-410h]
0x180056603  sub     rsp, 510h
0x18005660a  mov     rax, cs:__security_cookie
0x180056611  xor     rax, rsp
0x180056614  mov     [rbp+440h+var_40], rax
0x18005661b  mov     rax, [rbp+440h+Locale]
0x180056622  xor     r12d, r12d
0x180056625  mov     [rsp+540h+var_4F0], r12
0x18005662a  mov     rbx, r8
0x18005662d  mov     [rsp+540h+var_4E0], r12b
0x180056632  mov     rsi, rdx
0x180056635  mov     [rsp+540h+var_4C8], r12b
0x18005663a  mov     r15, rcx
0x18005663d  mov     [rbp+440h+var_4C0], r12b
0x180056641  mov     [rbp+440h+var_4B8], r12b
0x180056645  test    rax, rax
0x180056648  jz      short loc_18005664F
0x18005664a  movups  xmm0, xmmword ptr [rax]
0x18005664d  jmp     short loc_18005665F
0x18005664f  cmp     cs:__acrt_locale_changed_data, r12d
0x180056656  jnz     short loc_18005666A
0x180056658  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x18005665f  mov     [rsp+540h+var_4C8], 1
0x180056664  movdqu  [rsp+540h+var_4D8], xmm0
0x18005666a  test    r9, r9
0x18005666d  jnz     short loc_1800566A1
0x18005666f  lea     rax, [rsp+540h+var_4F0]
0x180056674  mov     [rbp+440h+var_4C0], 1
0x180056678  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x18005667d  xor     r9d, r9d; LineNo
0x180056680  xor     r8d, r8d; FileName
0x180056683  mov     [rsp+540h+var_520], r12; uintptr_t
0x180056688  xor     edx, edx; FunctionName
0x18005668a  mov     [rsp+540h+var_4C4], 16h
0x180056692  xor     ecx, ecx; Expression
0x180056694  call    _invalid_parameter_internal
0x180056699  or      edi, 0FFFFFFFFh
0x18005669c  jmp     loc_1800567DE
0x1800566a1  test    rbx, rbx
0x1800566a4  jz      short loc_1800566AB
0x1800566a6  test    rsi, rsi
0x1800566a9  jz      short loc_18005666F
0x1800566ab  mov     r14, r15
0x1800566ae  mov     [rsp+540h+var_4F7], r12d
0x1800566b3  mov     [rsp+540h+var_4F3], r12w
0x1800566b9  mov     [rsp+540h+var_4F1], r12b
0x1800566be  mov     [rsp+540h+var_510], rsi
0x1800566c3  mov     [rsp+540h+var_508], rbx
0x1800566c8  mov     [rsp+540h+var_500], r12
0x1800566cd  and     r14d, 2
0x1800566d1  jnz     short loc_1800566DD
0x1800566d3  mov     [rsp+540h+var_4F8], r12b
0x1800566d8  test    rsi, rsi
0x1800566db  jnz     short loc_1800566E2
0x1800566dd  mov     [rsp+540h+var_4F8], 1
0x1800566e2  lea     rax, [rsp+540h+var_4F0]
0x1800566e7  mov     [rbp+440h+var_490], r12d
0x1800566eb  mov     [rbp+440h+var_4A8], rax
0x1800566ef  lea     rcx, [rbp+440h+var_4B0]
0x1800566f3  lea     rax, [rsp+540h+var_510]
0x1800566f8  mov     [rbp+440h+var_48C], r12b
0x1800566fc  mov     [rbp+440h+var_50], rax
0x180056703  xorps   xmm0, xmm0
0x180056706  mov     rax, [rbp+440h+ArgList]
0x18005670d  mov     [rbp+440h+var_498], rax
0x180056711  mov     [rbp+440h+var_488], r12
0x180056715  mov     [rbp+440h+var_480], r12d
0x180056719  mov     [rbp+440h+var_478], r12w
0x18005671e  mov     [rbp+440h+var_468], r12d
0x180056722  mov     [rbp+440h+var_464], r12b
0x180056726  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x18005672e  mov     [rbp+440h+var_4B0], r15
0x180056732  mov     [rbp+440h+var_4A0], r9
0x180056736  mov     [rbp+440h+var_48], r12d
0x18005673d  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::process(void)
0x180056742  movsxd  rdi, eax
0x180056745  test    rsi, rsi
0x180056748  jz      loc_1800567D2
0x18005674e  test    r15b, 1
0x180056752  jz      short loc_180056783
0x180056754  test    rbx, rbx
0x180056757  jnz     short loc_18005676E
0x180056759  test    eax, eax
0x18005675b  jz      short loc_18005676E
0x18005675d  mov     rcx, [rbp+440h+Block+8]; Block
0x180056764  call    _free_base
0x180056769  jmp     loc_180056699
0x18005676e  mov     rax, [rsp+540h+var_500]
0x180056773  cmp     rax, rbx
0x180056776  jnz     short loc_1800567CE
0x180056778  test    edi, edi
0x18005677a  js      short loc_1800567D2
0x18005677c  cmp     rdi, rbx
0x18005677f  jbe     short loc_1800567D2
0x180056781  jmp     short loc_18005675D
0x180056783  test    r14, r14
0x180056786  jz      short loc_1800567A7
0x180056788  test    rbx, rbx
0x18005678b  jz      short loc_1800567D2
0x18005678d  test    eax, eax
0x18005678f  jns     short loc_180056796
0x180056791  mov     [rsi], r12b
0x180056794  jmp     short loc_1800567D2
0x180056796  mov     rax, [rsp+540h+var_500]
0x18005679b  cmp     rax, rbx
0x18005679e  jnz     short loc_1800567CE
0x1800567a0  mov     [rbx+rsi-1], r12b
0x1800567a5  jmp     short loc_1800567D2
0x1800567a7  test    rbx, rbx
0x1800567aa  jz      short loc_18005675D
0x1800567ac  mov     rax, [rsp+540h+var_500]
0x1800567b1  cmp     rax, rbx
0x1800567b4  jnz     short loc_1800567CE
0x1800567b6  mov     rcx, [rbp+440h+Block+8]; Block
0x1800567bd  mov     [rbx+rsi-1], r12b
0x1800567c2  call    _free_base
0x1800567c7  mov     edi, 0FFFFFFFEh
0x1800567cc  jmp     short loc_1800567DE
0x1800567ce  mov     [rax+rsi], r12b
0x1800567d2  mov     rcx, [rbp+440h+Block+8]; Block
0x1800567d9  call    _free_base
0x1800567de  cmp     [rsp+540h+var_4C8], 2
0x1800567e3  jnz     short loc_1800567F1
0x1800567e5  mov     rax, [rsp+540h+var_4F0]
0x1800567ea  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1800567f1  cmp     [rbp+440h+var_4C0], r12b
0x1800567f5  jz      short loc_180056808
0x1800567f7  mov     ebx, [rsp+540h+var_4C4]
0x1800567fb  lea     rcx, [rsp+540h+var_4F0]; this
0x180056800  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056805  mov     [rax+20h], ebx
0x180056808  cmp     [rbp+440h+var_4B8], r12b
0x18005680c  jz      short loc_18005681E
0x18005680e  mov     ebx, [rbp+440h+var_4BC]
0x180056811  lea     rcx, [rsp+540h+var_4F0]; this
0x180056816  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x18005681b  mov     [rax+24h], ebx
0x18005681e  mov     eax, edi
0x180056820  mov     rcx, [rbp+440h+var_40]
0x180056827  xor     rcx, rsp; StackCookie
0x18005682a  call    __security_check_cookie
0x18005682f  add     rsp, 510h
0x180056836  pop     r15
0x180056838  pop     r14
0x18005683a  pop     r12
0x18005683c  pop     rdi
0x18005683d  pop     rsi
0x18005683e  pop     rbx
0x18005683f  pop     rbp
0x180056840  retn
```
