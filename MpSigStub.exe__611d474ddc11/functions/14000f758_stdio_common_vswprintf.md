# __stdio_common_vswprintf

- ea: `0x14000f758`
- end: `0x14000f9b1`
- name: `__stdio_common_vswprintf`
- size: `601`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14003d440`
- `0x1400a66f8`
- `0x1400a82d0`

## callees

- `0x1400042e0`
- `0x140004614`
- `0x14000da5c`
- `0x14000f758`
- `0x1400107c4`
- `0x14001bf00`

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
0x14000f758  push    rbp
0x14000f75a  push    rbx
0x14000f75b  push    rsi
0x14000f75c  push    rdi
0x14000f75d  push    r12
0x14000f75f  push    r14
0x14000f761  push    r15
0x14000f763  lea     rbp, [rsp-410h]
0x14000f76b  sub     rsp, 510h
0x14000f772  mov     rax, cs:__security_cookie
0x14000f779  xor     rax, rsp
0x14000f77c  mov     [rbp+440h+var_40], rax
0x14000f783  mov     rax, [rbp+440h+Locale]
0x14000f78a  xor     r12d, r12d
0x14000f78d  mov     [rsp+540h+var_4F0], r12
0x14000f792  mov     rbx, r8
0x14000f795  mov     [rsp+540h+var_4E0], r12b
0x14000f79a  mov     rsi, rdx
0x14000f79d  mov     [rsp+540h+var_4C8], r12b
0x14000f7a2  mov     r15, rcx
0x14000f7a5  mov     [rbp+440h+var_4C0], r12b
0x14000f7a9  mov     [rbp+440h+var_4B8], r12b
0x14000f7ad  test    rax, rax
0x14000f7b0  jz      short loc_14000F7B7
0x14000f7b2  movups  xmm0, xmmword ptr [rax]
0x14000f7b5  jmp     short loc_14000F7C7
0x14000f7b7  cmp     cs:dword_1400D6988, r12d
0x14000f7be  jnz     short loc_14000F7D2
0x14000f7c0  movups  xmm0, xmmword ptr cs:off_1400D5158
0x14000f7c7  mov     [rsp+540h+var_4C8], 1
0x14000f7cc  movdqu  [rsp+540h+var_4D8], xmm0
0x14000f7d2  test    r9, r9
0x14000f7d5  jnz     short loc_14000F809
0x14000f7d7  lea     rax, [rsp+540h+var_4F0]
0x14000f7dc  mov     [rbp+440h+var_4C0], 1
0x14000f7e0  mov     [rsp+540h+var_518], rax; __crt_cached_ptd_host *
0x14000f7e5  xor     r9d, r9d; LineNo
0x14000f7e8  xor     r8d, r8d; FileName
0x14000f7eb  mov     [rsp+540h+var_520], r12; uintptr_t
0x14000f7f0  xor     edx, edx; FunctionName
0x14000f7f2  mov     [rsp+540h+var_4C4], 16h
0x14000f7fa  xor     ecx, ecx; Expression
0x14000f7fc  call    sub_140004614
0x14000f801  or      edi, 0FFFFFFFFh
0x14000f804  jmp     loc_14000F94E
0x14000f809  test    rbx, rbx
0x14000f80c  jz      short loc_14000F813
0x14000f80e  test    rsi, rsi
0x14000f811  jz      short loc_14000F7D7
0x14000f813  mov     r14, r15
0x14000f816  mov     [rsp+540h+var_4F7], r12d
0x14000f81b  mov     [rsp+540h+var_4F3], r12w
0x14000f821  mov     [rsp+540h+var_4F1], r12b
0x14000f826  mov     [rsp+540h+var_510], rsi
0x14000f82b  mov     [rsp+540h+var_508], rbx
0x14000f830  mov     [rsp+540h+var_500], r12
0x14000f835  and     r14d, 2
0x14000f839  jnz     short loc_14000F845
0x14000f83b  mov     [rsp+540h+var_4F8], r12b
0x14000f840  test    rsi, rsi
0x14000f843  jnz     short loc_14000F84A
0x14000f845  mov     [rsp+540h+var_4F8], 1
0x14000f84a  lea     rax, [rsp+540h+var_4F0]
0x14000f84f  mov     [rbp+440h+var_490], r12d
0x14000f853  mov     [rbp+440h+var_4A8], rax
0x14000f857  lea     rcx, [rbp+440h+var_4B0]
0x14000f85b  lea     rax, [rsp+540h+var_510]
0x14000f860  mov     [rbp+440h+var_48C], r12b
0x14000f864  mov     [rbp+440h+var_50], rax
0x14000f86b  xorps   xmm0, xmm0
0x14000f86e  mov     rax, [rbp+440h+ArgList]
0x14000f875  mov     [rbp+440h+var_498], rax
0x14000f879  mov     [rbp+440h+var_488], r12
0x14000f87d  mov     [rbp+440h+var_480], r12d
0x14000f881  mov     [rbp+440h+var_478], r12b
0x14000f885  mov     [rbp+440h+var_476], r12w
0x14000f88a  mov     [rbp+440h+var_468], r12d
0x14000f88e  mov     [rbp+440h+var_464], r12b
0x14000f892  movdqa  xmmword ptr [rbp+440h+Block], xmm0
0x14000f89a  mov     [rbp+440h+var_4B0], r15
0x14000f89e  mov     [rbp+440h+var_4A0], r9
0x14000f8a2  mov     [rbp+440h+var_48], r12d
0x14000f8a9  call    ?process@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@QEAAHXZ
0x14000f8ae  movsxd  rdi, eax
0x14000f8b1  test    rsi, rsi
0x14000f8b4  jz      loc_14000F942
0x14000f8ba  test    r15b, 1
0x14000f8be  jz      short loc_14000F8EF
0x14000f8c0  test    rbx, rbx
0x14000f8c3  jnz     short loc_14000F8DA
0x14000f8c5  test    eax, eax
0x14000f8c7  jz      short loc_14000F8DA
0x14000f8c9  mov     rcx, [rbp+440h+Block+8]; Block
0x14000f8d0  call    _free_base
0x14000f8d5  jmp     loc_14000F801
0x14000f8da  mov     rax, [rsp+540h+var_500]
0x14000f8df  cmp     rax, rbx
0x14000f8e2  jnz     short loc_14000F93D
0x14000f8e4  test    edi, edi
0x14000f8e6  js      short loc_14000F942
0x14000f8e8  cmp     rdi, rbx
0x14000f8eb  jbe     short loc_14000F942
0x14000f8ed  jmp     short loc_14000F8C9
0x14000f8ef  test    r14, r14
0x14000f8f2  jz      short loc_14000F915
0x14000f8f4  test    rbx, rbx
0x14000f8f7  jz      short loc_14000F942
0x14000f8f9  test    eax, eax
0x14000f8fb  jns     short loc_14000F903
0x14000f8fd  mov     [rsi], r12w
0x14000f901  jmp     short loc_14000F942
0x14000f903  mov     rax, [rsp+540h+var_500]
0x14000f908  cmp     rax, rbx
0x14000f90b  jnz     short loc_14000F93D
0x14000f90d  mov     [rsi+rbx*2-2], r12w
0x14000f913  jmp     short loc_14000F942
0x14000f915  test    rbx, rbx
0x14000f918  jz      short loc_14000F8C9
0x14000f91a  mov     rax, [rsp+540h+var_500]
0x14000f91f  cmp     rax, rbx
0x14000f922  jnz     short loc_14000F93D
0x14000f924  mov     rcx, [rbp+440h+Block+8]; Block
0x14000f92b  mov     [rsi+rbx*2-2], r12w
0x14000f931  call    _free_base
0x14000f936  mov     edi, 0FFFFFFFEh
0x14000f93b  jmp     short loc_14000F94E
0x14000f93d  mov     [rsi+rax*2], r12w
0x14000f942  mov     rcx, [rbp+440h+Block+8]; Block
0x14000f949  call    _free_base
0x14000f94e  cmp     [rsp+540h+var_4C8], 2
0x14000f953  jnz     short loc_14000F961
0x14000f955  mov     rax, [rsp+540h+var_4F0]
0x14000f95a  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x14000f961  cmp     [rbp+440h+var_4C0], r12b
0x14000f965  jz      short loc_14000F978
0x14000f967  mov     ebx, [rsp+540h+var_4C4]
0x14000f96b  lea     rcx, [rsp+540h+var_4F0]
0x14000f970  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14000f975  mov     [rax+20h], ebx
0x14000f978  cmp     [rbp+440h+var_4B8], r12b
0x14000f97c  jz      short loc_14000F98E
0x14000f97e  mov     ebx, [rbp+440h+var_4BC]
0x14000f981  lea     rcx, [rsp+540h+var_4F0]
0x14000f986  call    unknown_libname_44; Microsoft VisualC 64bit universal runtime
0x14000f98b  mov     [rax+24h], ebx
0x14000f98e  mov     eax, edi
0x14000f990  mov     rcx, [rbp+440h+var_40]
0x14000f997  xor     rcx, rsp; StackCookie
0x14000f99a  call    __security_check_cookie
0x14000f99f  add     rsp, 510h
0x14000f9a6  pop     r15
0x14000f9a8  pop     r14
0x14000f9aa  pop     r12
0x14000f9ac  pop     rdi
0x14000f9ad  pop     rsi
0x14000f9ae  pop     rbx
0x14000f9af  pop     rbp
0x14000f9b0  retn
```
