# __stdio_common_vswprintf

- ea: `0x180056cf0`
- end: `0x180056f49`
- name: `__stdio_common_vswprintf`
- size: `601`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002810`
- `0x18000774c`
- `0x180007b48`
- `0x180008040`
- `0x180045f1c`
- `0x180056cf0`

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
0x180056cf0  push    rbp
0x180056cf2  push    rbx
0x180056cf3  push    rsi
0x180056cf4  push    rdi
0x180056cf5  push    r12
0x180056cf7  push    r14
0x180056cf9  push    r15
0x180056cfb  lea     rbp, [rsp-410h]
0x180056d03  sub     rsp, 510h
0x180056d0a  mov     rax, cs:__security_cookie
0x180056d11  xor     rax, rsp
0x180056d14  mov     [rbp+440h+var_40], rax
0x180056d1b  mov     rax, [rbp+440h+Locale]
0x180056d22  xor     r12d, r12d
0x180056d25  mov     [rsp+540h+var_4F0], r12
0x180056d2a  mov     rbx, r8
0x180056d2d  mov     [rsp+540h+var_4E0], r12b
0x180056d32  mov     rsi, rdx
0x180056d35  mov     [rsp+540h+var_4C8], r12b
0x180056d3a  mov     r15, rcx
0x180056d3d  mov     [rbp+440h+var_4C0], r12b
0x180056d41  mov     [rbp+440h+var_4B8], r12b
0x180056d45  test    rax, rax
0x180056d48  jz      short loc_180056D4F
0x180056d4a  movups  xmm0, xmmword ptr [rax]
0x180056d4d  jmp     short loc_180056D5F
0x180056d4f  cmp     cs:__acrt_locale_changed_data, r12d
0x180056d56  jnz     short loc_180056D6A
0x180056d58  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x180056d5f  mov     [rsp+540h+var_4C8], 1
0x180056d64  movdqu  [rsp+540h+var_4D8], xmm0
0x180056d6a  test    r9, r9
0x180056d6d  jnz     short loc_180056DA1
0x180056d6f  lea     rax, [rsp+540h+var_4F0]
0x180056d74  mov     [rbp+440h+var_4C0], 1
0x180056d78  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x180056d7d  xor     r9d, r9d; LineNo
0x180056d80  xor     r8d, r8d; FileName
0x180056d83  mov     [rsp+540h+var_520], r12; uintptr_t
0x180056d88  xor     edx, edx; FunctionName
0x180056d8a  mov     [rsp+540h+var_4C4], 16h
0x180056d92  xor     ecx, ecx; Expression
0x180056d94  call    _invalid_parameter_internal
0x180056d99  or      edi, 0FFFFFFFFh
0x180056d9c  jmp     loc_180056EE6
0x180056da1  test    rbx, rbx
0x180056da4  jz      short loc_180056DAB
0x180056da6  test    rsi, rsi
0x180056da9  jz      short loc_180056D6F
0x180056dab  mov     r14, r15
0x180056dae  mov     [rsp+540h+var_4F7], r12d
0x180056db3  mov     [rsp+540h+var_4F3], r12w
0x180056db9  mov     [rsp+540h+var_4F1], r12b
0x180056dbe  mov     [rsp+540h+var_510], rsi
0x180056dc3  mov     [rsp+540h+var_508], rbx
0x180056dc8  mov     [rsp+540h+var_500], r12
0x180056dcd  and     r14d, 2
0x180056dd1  jnz     short loc_180056DDD
0x180056dd3  mov     [rsp+540h+var_4F8], r12b
0x180056dd8  test    rsi, rsi
0x180056ddb  jnz     short loc_180056DE2
0x180056ddd  mov     [rsp+540h+var_4F8], 1
0x180056de2  lea     rax, [rsp+540h+var_4F0]
0x180056de7  mov     [rbp+440h+var_490], r12d
0x180056deb  mov     [rbp+440h+var_4A8], rax
0x180056def  lea     rcx, [rbp+440h+var_4B0]
0x180056df3  lea     rax, [rsp+540h+var_510]
0x180056df8  mov     [rbp+440h+var_48C], r12b
0x180056dfc  mov     [rbp+440h+var_50], rax
0x180056e03  xorps   xmm0, xmm0
0x180056e06  mov     rax, [rbp+440h+ArgList]
0x180056e0d  mov     [rbp+440h+var_498], rax
0x180056e11  mov     [rbp+440h+var_488], r12
0x180056e15  mov     [rbp+440h+var_480], r12d
0x180056e19  mov     [rbp+440h+var_478], r12b
0x180056e1d  mov     [rbp+440h+var_476], r12w
0x180056e22  mov     [rbp+440h+var_468], r12d
0x180056e26  mov     [rbp+440h+var_464], r12b
0x180056e2a  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x180056e32  mov     [rbp+440h+var_4B0], r15
0x180056e36  mov     [rbp+440h+var_4A0], r9
0x180056e3a  mov     [rbp+440h+var_48], r12d
0x180056e41  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ; __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::process(void)
0x180056e46  movsxd  rdi, eax
0x180056e49  test    rsi, rsi
0x180056e4c  jz      loc_180056EDA
0x180056e52  test    r15b, 1
0x180056e56  jz      short loc_180056E87
0x180056e58  test    rbx, rbx
0x180056e5b  jnz     short loc_180056E72
0x180056e5d  test    eax, eax
0x180056e5f  jz      short loc_180056E72
0x180056e61  mov     rcx, [rbp+440h+Block+8]; Block
0x180056e68  call    _free_base
0x180056e6d  jmp     loc_180056D99
0x180056e72  mov     rax, [rsp+540h+var_500]
0x180056e77  cmp     rax, rbx
0x180056e7a  jnz     short loc_180056ED5
0x180056e7c  test    edi, edi
0x180056e7e  js      short loc_180056EDA
0x180056e80  cmp     rdi, rbx
0x180056e83  jbe     short loc_180056EDA
0x180056e85  jmp     short loc_180056E61
0x180056e87  test    r14, r14
0x180056e8a  jz      short loc_180056EAD
0x180056e8c  test    rbx, rbx
0x180056e8f  jz      short loc_180056EDA
0x180056e91  test    eax, eax
0x180056e93  jns     short loc_180056E9B
0x180056e95  mov     [rsi], r12w
0x180056e99  jmp     short loc_180056EDA
0x180056e9b  mov     rax, [rsp+540h+var_500]
0x180056ea0  cmp     rax, rbx
0x180056ea3  jnz     short loc_180056ED5
0x180056ea5  mov     [rsi+rbx*2-2], r12w
0x180056eab  jmp     short loc_180056EDA
0x180056ead  test    rbx, rbx
0x180056eb0  jz      short loc_180056E61
0x180056eb2  mov     rax, [rsp+540h+var_500]
0x180056eb7  cmp     rax, rbx
0x180056eba  jnz     short loc_180056ED5
0x180056ebc  mov     rcx, [rbp+440h+Block+8]; Block
0x180056ec3  mov     [rsi+rbx*2-2], r12w
0x180056ec9  call    _free_base
0x180056ece  mov     edi, 0FFFFFFFEh
0x180056ed3  jmp     short loc_180056EE6
0x180056ed5  mov     [rsi+rax*2], r12w
0x180056eda  mov     rcx, [rbp+440h+Block+8]; Block
0x180056ee1  call    _free_base
0x180056ee6  cmp     [rsp+540h+var_4C8], 2
0x180056eeb  jnz     short loc_180056EF9
0x180056eed  mov     rax, [rsp+540h+var_4F0]
0x180056ef2  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x180056ef9  cmp     [rbp+440h+var_4C0], r12b
0x180056efd  jz      short loc_180056F10
0x180056eff  mov     ebx, [rsp+540h+var_4C4]
0x180056f03  lea     rcx, [rsp+540h+var_4F0]; this
0x180056f08  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056f0d  mov     [rax+20h], ebx
0x180056f10  cmp     [rbp+440h+var_4B8], r12b
0x180056f14  jz      short loc_180056F26
0x180056f16  mov     ebx, [rbp+440h+var_4BC]
0x180056f19  lea     rcx, [rsp+540h+var_4F0]; this
0x180056f1e  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x180056f23  mov     [rax+24h], ebx
0x180056f26  mov     eax, edi
0x180056f28  mov     rcx, [rbp+440h+var_40]
0x180056f2f  xor     rcx, rsp; StackCookie
0x180056f32  call    __security_check_cookie
0x180056f37  add     rsp, 510h
0x180056f3e  pop     r15
0x180056f40  pop     r14
0x180056f42  pop     r12
0x180056f44  pop     rdi
0x180056f45  pop     rsi
0x180056f46  pop     rbx
0x180056f47  pop     rbp
0x180056f48  retn
```
