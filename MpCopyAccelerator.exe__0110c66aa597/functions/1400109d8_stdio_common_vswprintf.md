# __stdio_common_vswprintf

- ea: `0x1400109d8`
- end: `0x140010c31`
- name: `__stdio_common_vswprintf`
- size: `601`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140023ec8`

## callees

- `0x140005c20`
- `0x14000bb70`
- `0x14000bea4`
- `0x14000ec44`
- `0x1400109d8`
- `0x140013e10`

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
0x1400109d8  push    rbp
0x1400109da  push    rbx
0x1400109db  push    rsi
0x1400109dc  push    rdi
0x1400109dd  push    r12
0x1400109df  push    r14
0x1400109e1  push    r15
0x1400109e3  lea     rbp, [rsp-410h]
0x1400109eb  sub     rsp, 510h
0x1400109f2  mov     rax, cs:__security_cookie
0x1400109f9  xor     rax, rsp
0x1400109fc  mov     [rbp+440h+var_40], rax
0x140010a03  mov     rax, [rbp+440h+Locale]
0x140010a0a  xor     r12d, r12d
0x140010a0d  mov     [rsp+540h+var_4F0], r12
0x140010a12  mov     rbx, r8
0x140010a15  mov     [rsp+540h+var_4E0], r12b
0x140010a1a  mov     rsi, rdx
0x140010a1d  mov     [rsp+540h+var_4C8], r12b
0x140010a22  mov     r15, rcx
0x140010a25  mov     [rbp+440h+var_4C0], r12b
0x140010a29  mov     [rbp+440h+var_4B8], r12b
0x140010a2d  test    rax, rax
0x140010a30  jz      short loc_140010A37
0x140010a32  movups  xmm0, xmmword ptr [rax]
0x140010a35  jmp     short loc_140010A47
0x140010a37  cmp     cs:__acrt_locale_changed_data, r12d
0x140010a3e  jnz     short loc_140010A52
0x140010a40  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x140010a47  mov     [rsp+540h+var_4C8], 1
0x140010a4c  movdqu  [rsp+540h+var_4D8], xmm0
0x140010a52  test    r9, r9
0x140010a55  jnz     short loc_140010A89
0x140010a57  lea     rax, [rsp+540h+var_4F0]
0x140010a5c  mov     [rbp+440h+var_4C0], 1
0x140010a60  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x140010a65  xor     r9d, r9d; LineNo
0x140010a68  xor     r8d, r8d; FileName
0x140010a6b  mov     [rsp+540h+var_520], r12; uintptr_t
0x140010a70  xor     edx, edx; FunctionName
0x140010a72  mov     [rsp+540h+var_4C4], 16h
0x140010a7a  xor     ecx, ecx; Expression
0x140010a7c  call    _invalid_parameter_internal
0x140010a81  or      edi, 0FFFFFFFFh
0x140010a84  jmp     loc_140010BCE
0x140010a89  test    rbx, rbx
0x140010a8c  jz      short loc_140010A93
0x140010a8e  test    rsi, rsi
0x140010a91  jz      short loc_140010A57
0x140010a93  mov     r14, r15
0x140010a96  mov     [rsp+540h+var_4F7], r12d
0x140010a9b  mov     [rsp+540h+var_4F3], r12w
0x140010aa1  mov     [rsp+540h+var_4F1], r12b
0x140010aa6  mov     [rsp+540h+var_510], rsi
0x140010aab  mov     [rsp+540h+var_508], rbx
0x140010ab0  mov     [rsp+540h+var_500], r12
0x140010ab5  and     r14d, 2
0x140010ab9  jnz     short loc_140010AC5
0x140010abb  mov     [rsp+540h+var_4F8], r12b
0x140010ac0  test    rsi, rsi
0x140010ac3  jnz     short loc_140010ACA
0x140010ac5  mov     [rsp+540h+var_4F8], 1
0x140010aca  lea     rax, [rsp+540h+var_4F0]
0x140010acf  mov     [rbp+440h+var_490], r12d
0x140010ad3  mov     [rbp+440h+var_4A8], rax
0x140010ad7  lea     rcx, [rbp+440h+var_4B0]
0x140010adb  lea     rax, [rsp+540h+var_510]
0x140010ae0  mov     [rbp+440h+var_48C], r12b
0x140010ae4  mov     [rbp+440h+var_50], rax
0x140010aeb  xorps   xmm0, xmm0
0x140010aee  mov     rax, [rbp+440h+ArgList]
0x140010af5  mov     [rbp+440h+var_498], rax
0x140010af9  mov     [rbp+440h+var_488], r12
0x140010afd  mov     [rbp+440h+var_480], r12d
0x140010b01  mov     [rbp+440h+var_478], r12b
0x140010b05  mov     [rbp+440h+var_476], r12w
0x140010b0a  mov     [rbp+440h+var_468], r12d
0x140010b0e  mov     [rbp+440h+var_464], r12b
0x140010b12  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x140010b1a  mov     [rbp+440h+var_4B0], r15
0x140010b1e  mov     [rbp+440h+var_4A0], r9
0x140010b22  mov     [rbp+440h+var_48], r12d
0x140010b29  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ
0x140010b2e  movsxd  rdi, eax
0x140010b31  test    rsi, rsi
0x140010b34  jz      loc_140010BC2
0x140010b3a  test    r15b, 1
0x140010b3e  jz      short loc_140010B6F
0x140010b40  test    rbx, rbx
0x140010b43  jnz     short loc_140010B5A
0x140010b45  test    eax, eax
0x140010b47  jz      short loc_140010B5A
0x140010b49  mov     rcx, [rbp+440h+Block+8]; Block
0x140010b50  call    _free_base
0x140010b55  jmp     loc_140010A81
0x140010b5a  mov     rax, [rsp+540h+var_500]
0x140010b5f  cmp     rax, rbx
0x140010b62  jnz     short loc_140010BBD
0x140010b64  test    edi, edi
0x140010b66  js      short loc_140010BC2
0x140010b68  cmp     rdi, rbx
0x140010b6b  jbe     short loc_140010BC2
0x140010b6d  jmp     short loc_140010B49
0x140010b6f  test    r14, r14
0x140010b72  jz      short loc_140010B95
0x140010b74  test    rbx, rbx
0x140010b77  jz      short loc_140010BC2
0x140010b79  test    eax, eax
0x140010b7b  jns     short loc_140010B83
0x140010b7d  mov     [rsi], r12w
0x140010b81  jmp     short loc_140010BC2
0x140010b83  mov     rax, [rsp+540h+var_500]
0x140010b88  cmp     rax, rbx
0x140010b8b  jnz     short loc_140010BBD
0x140010b8d  mov     [rsi+rbx*2-2], r12w
0x140010b93  jmp     short loc_140010BC2
0x140010b95  test    rbx, rbx
0x140010b98  jz      short loc_140010B49
0x140010b9a  mov     rax, [rsp+540h+var_500]
0x140010b9f  cmp     rax, rbx
0x140010ba2  jnz     short loc_140010BBD
0x140010ba4  mov     rcx, [rbp+440h+Block+8]; Block
0x140010bab  mov     [rsi+rbx*2-2], r12w
0x140010bb1  call    _free_base
0x140010bb6  mov     edi, 0FFFFFFFEh
0x140010bbb  jmp     short loc_140010BCE
0x140010bbd  mov     [rsi+rax*2], r12w
0x140010bc2  mov     rcx, [rbp+440h+Block+8]; Block
0x140010bc9  call    _free_base
0x140010bce  cmp     [rsp+540h+var_4C8], 2
0x140010bd3  jnz     short loc_140010BE1
0x140010bd5  mov     rax, [rsp+540h+var_4F0]
0x140010bda  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x140010be1  cmp     [rbp+440h+var_4C0], r12b
0x140010be5  jz      short loc_140010BF8
0x140010be7  mov     ebx, [rsp+540h+var_4C4]
0x140010beb  lea     rcx, [rsp+540h+var_4F0]; this
0x140010bf0  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ
0x140010bf5  mov     [rax+20h], ebx
0x140010bf8  cmp     [rbp+440h+var_4B8], r12b
0x140010bfc  jz      short loc_140010C0E
0x140010bfe  mov     ebx, [rbp+440h+var_4BC]
0x140010c01  lea     rcx, [rsp+540h+var_4F0]; this
0x140010c06  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ
0x140010c0b  mov     [rax+24h], ebx
0x140010c0e  mov     eax, edi
0x140010c10  mov     rcx, [rbp+440h+var_40]
0x140010c17  xor     rcx, rsp; StackCookie
0x140010c1a  call    __security_check_cookie
0x140010c1f  add     rsp, 510h
0x140010c26  pop     r15
0x140010c28  pop     r14
0x140010c2a  pop     r12
0x140010c2c  pop     rdi
0x140010c2d  pop     rsi
0x140010c2e  pop     rbx
0x140010c2f  pop     rbp
0x140010c30  retn
```
