# __stdio_common_vsprintf

- ea: `0x140010784`
- end: `0x1400109d5`
- name: `__stdio_common_vsprintf`
- size: `593`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002f34`

## callees

- `0x140005c20`
- `0x14000bb70`
- `0x14000bea4`
- `0x14000e8d4`
- `0x140010784`
- `0x140013e10`

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
0x140010784  push    rbp
0x140010786  push    rbx
0x140010787  push    rsi
0x140010788  push    rdi
0x140010789  push    r12
0x14001078b  push    r14
0x14001078d  push    r15
0x14001078f  lea     rbp, [rsp-410h]
0x140010797  sub     rsp, 510h
0x14001079e  mov     rax, cs:__security_cookie
0x1400107a5  xor     rax, rsp
0x1400107a8  mov     [rbp+440h+var_40], rax
0x1400107af  mov     rax, [rbp+440h+Locale]
0x1400107b6  xor     r12d, r12d
0x1400107b9  mov     [rsp+540h+var_4F0], r12
0x1400107be  mov     rbx, r8
0x1400107c1  mov     [rsp+540h+var_4E0], r12b
0x1400107c6  mov     rsi, rdx
0x1400107c9  mov     [rsp+540h+var_4C8], r12b
0x1400107ce  mov     r15, rcx
0x1400107d1  mov     [rbp+440h+var_4C0], r12b
0x1400107d5  mov     [rbp+440h+var_4B8], r12b
0x1400107d9  test    rax, rax
0x1400107dc  jz      short loc_1400107E3
0x1400107de  movups  xmm0, xmmword ptr [rax]
0x1400107e1  jmp     short loc_1400107F3
0x1400107e3  cmp     cs:__acrt_locale_changed_data, r12d
0x1400107ea  jnz     short loc_1400107FE
0x1400107ec  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x1400107f3  mov     [rsp+540h+var_4C8], 1
0x1400107f8  movdqu  [rsp+540h+var_4D8], xmm0
0x1400107fe  test    r9, r9
0x140010801  jnz     short loc_140010835
0x140010803  lea     rax, [rsp+540h+var_4F0]
0x140010808  mov     [rbp+440h+var_4C0], 1
0x14001080c  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x140010811  xor     r9d, r9d; LineNo
0x140010814  xor     r8d, r8d; FileName
0x140010817  mov     [rsp+540h+var_520], r12; uintptr_t
0x14001081c  xor     edx, edx; FunctionName
0x14001081e  mov     [rsp+540h+var_4C4], 16h
0x140010826  xor     ecx, ecx; Expression
0x140010828  call    _invalid_parameter_internal
0x14001082d  or      edi, 0FFFFFFFFh
0x140010830  jmp     loc_140010972
0x140010835  test    rbx, rbx
0x140010838  jz      short loc_14001083F
0x14001083a  test    rsi, rsi
0x14001083d  jz      short loc_140010803
0x14001083f  mov     r14, r15
0x140010842  mov     [rsp+540h+var_4F7], r12d
0x140010847  mov     [rsp+540h+var_4F3], r12w
0x14001084d  mov     [rsp+540h+var_4F1], r12b
0x140010852  mov     [rsp+540h+var_510], rsi
0x140010857  mov     [rsp+540h+var_508], rbx
0x14001085c  mov     [rsp+540h+var_500], r12
0x140010861  and     r14d, 2
0x140010865  jnz     short loc_140010871
0x140010867  mov     [rsp+540h+var_4F8], r12b
0x14001086c  test    rsi, rsi
0x14001086f  jnz     short loc_140010876
0x140010871  mov     [rsp+540h+var_4F8], 1
0x140010876  lea     rax, [rsp+540h+var_4F0]
0x14001087b  mov     [rbp+440h+var_490], r12d
0x14001087f  mov     [rbp+440h+var_4A8], rax
0x140010883  lea     rcx, [rbp+440h+var_4B0]
0x140010887  lea     rax, [rsp+540h+var_510]
0x14001088c  mov     [rbp+440h+var_48C], r12b
0x140010890  mov     [rbp+440h+var_50], rax
0x140010897  xorps   xmm0, xmm0
0x14001089a  mov     rax, [rbp+440h+ArgList]
0x1400108a1  mov     [rbp+440h+var_498], rax
0x1400108a5  mov     [rbp+440h+var_488], r12
0x1400108a9  mov     [rbp+440h+var_480], r12d
0x1400108ad  mov     [rbp+440h+var_478], r12w
0x1400108b2  mov     [rbp+440h+var_468], r12d
0x1400108b6  mov     [rbp+440h+var_464], r12b
0x1400108ba  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x1400108c2  mov     [rbp+440h+var_4B0], r15
0x1400108c6  mov     [rbp+440h+var_4A0], r9
0x1400108ca  mov     [rbp+440h+var_48], r12d
0x1400108d1  call    ?process@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ
0x1400108d6  movsxd  rdi, eax
0x1400108d9  test    rsi, rsi
0x1400108dc  jz      loc_140010966
0x1400108e2  test    r15b, 1
0x1400108e6  jz      short loc_140010917
0x1400108e8  test    rbx, rbx
0x1400108eb  jnz     short loc_140010902
0x1400108ed  test    eax, eax
0x1400108ef  jz      short loc_140010902
0x1400108f1  mov     rcx, [rbp+440h+Block+8]; Block
0x1400108f8  call    _free_base
0x1400108fd  jmp     loc_14001082D
0x140010902  mov     rax, [rsp+540h+var_500]
0x140010907  cmp     rax, rbx
0x14001090a  jnz     short loc_140010962
0x14001090c  test    edi, edi
0x14001090e  js      short loc_140010966
0x140010910  cmp     rdi, rbx
0x140010913  jbe     short loc_140010966
0x140010915  jmp     short loc_1400108F1
0x140010917  test    r14, r14
0x14001091a  jz      short loc_14001093B
0x14001091c  test    rbx, rbx
0x14001091f  jz      short loc_140010966
0x140010921  test    eax, eax
0x140010923  jns     short loc_14001092A
0x140010925  mov     [rsi], r12b
0x140010928  jmp     short loc_140010966
0x14001092a  mov     rax, [rsp+540h+var_500]
0x14001092f  cmp     rax, rbx
0x140010932  jnz     short loc_140010962
0x140010934  mov     [rbx+rsi-1], r12b
0x140010939  jmp     short loc_140010966
0x14001093b  test    rbx, rbx
0x14001093e  jz      short loc_1400108F1
0x140010940  mov     rax, [rsp+540h+var_500]
0x140010945  cmp     rax, rbx
0x140010948  jnz     short loc_140010962
0x14001094a  mov     rcx, [rbp+440h+Block+8]; Block
0x140010951  mov     [rbx+rsi-1], r12b
0x140010956  call    _free_base
0x14001095b  mov     edi, 0FFFFFFFEh
0x140010960  jmp     short loc_140010972
0x140010962  mov     [rax+rsi], r12b
0x140010966  mov     rcx, [rbp+440h+Block+8]; Block
0x14001096d  call    _free_base
0x140010972  cmp     [rsp+540h+var_4C8], 2
0x140010977  jnz     short loc_140010985
0x140010979  mov     rax, [rsp+540h+var_4F0]
0x14001097e  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x140010985  cmp     [rbp+440h+var_4C0], r12b
0x140010989  jz      short loc_14001099C
0x14001098b  mov     ebx, [rsp+540h+var_4C4]
0x14001098f  lea     rcx, [rsp+540h+var_4F0]; this
0x140010994  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ
0x140010999  mov     [rax+20h], ebx
0x14001099c  cmp     [rbp+440h+var_4B8], r12b
0x1400109a0  jz      short loc_1400109B2
0x1400109a2  mov     ebx, [rbp+440h+var_4BC]
0x1400109a5  lea     rcx, [rsp+540h+var_4F0]; this
0x1400109aa  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ
0x1400109af  mov     [rax+24h], ebx
0x1400109b2  mov     eax, edi
0x1400109b4  mov     rcx, [rbp+440h+var_40]
0x1400109bb  xor     rcx, rsp; StackCookie
0x1400109be  call    __security_check_cookie
0x1400109c3  add     rsp, 510h
0x1400109ca  pop     r15
0x1400109cc  pop     r14
0x1400109ce  pop     r12
0x1400109d0  pop     rdi
0x1400109d1  pop     rsi
0x1400109d2  pop     rbx
0x1400109d3  pop     rbp
0x1400109d4  retn
```
