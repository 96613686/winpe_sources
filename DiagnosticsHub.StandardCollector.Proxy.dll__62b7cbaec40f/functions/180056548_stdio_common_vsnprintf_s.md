# __stdio_common_vsnprintf_s

- ea: `0x180056548`
- end: `0x180056709`
- name: `__stdio_common_vsnprintf_s`
- size: `449`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, size_t MaxCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000774c`
- `0x180007b48`
- `0x180033cc4`
- `0x180056548`

## pseudocode

```c
int __cdecl _stdio_common_vsnprintf_s(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        size_t MaxCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  __crt_locale_pointers v10; // xmm0
  int v11; // edi
  __int64 v12; // rbx
  int v13; // eax
  int v14; // ebx
  int v15; // ebx
  _QWORD v17[2]; // [rsp+30h] [rbp-40h] BYREF
  char v18; // [rsp+40h] [rbp-30h]
  __crt_locale_pointers v19; // [rsp+48h] [rbp-28h]
  char v20; // [rsp+58h] [rbp-18h]
  __int64 v21; // [rsp+5Ch] [rbp-14h]
  int v22; // [rsp+64h] [rbp-Ch]
  char v23; // [rsp+68h] [rbp-8h]

  v17[0] = 0;
  v18 = 0;
  v20 = 0;
  BYTE4(v21) = 0;
  v23 = 0;
  if ( Locale )
  {
    v10 = *Locale;
  }
  else
  {
    if ( _acrt_locale_changed_data )
      goto LABEL_6;
    v10 = *(__crt_locale_pointers *)&_acrt_initial_locale_pointers;
  }
  v20 = 1;
  v19 = v10;
LABEL_6:
  if ( !Format )
    goto LABEL_25;
  if ( MaxCount )
  {
    if ( Buffer )
      goto LABEL_12;
LABEL_25:
    BYTE4(v21) = 1;
    LODWORD(v21) = 22;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v17);
    v11 = -1;
    goto LABEL_26;
  }
  if ( !Buffer )
  {
    if ( !BufferCount )
    {
      v11 = 0;
      goto LABEL_26;
    }
    goto LABEL_25;
  }
LABEL_12:
  if ( !BufferCount )
    goto LABEL_25;
  v11 = -1;
  v12 = v21;
  if ( BufferCount > MaxCount )
  {
    v13 = common_vsprintf___crt_stdio_output::format_validation_base_char_(
            Options,
            Buffer,
            MaxCount + 1,
            (__int64)Format,
            (__crt_cached_ptd_host *)v17,
            (__int64)ArgList);
    if ( v13 == -2 )
    {
LABEL_15:
      if ( BYTE4(v21) && (_DWORD)v21 == 34 )
        v21 = v12;
      goto LABEL_26;
    }
    goto LABEL_21;
  }
  v13 = common_vsprintf___crt_stdio_output::format_validation_base_char_(
          Options,
          Buffer,
          BufferCount,
          (__int64)Format,
          (__crt_cached_ptd_host *)v17,
          (__int64)ArgList);
  Buffer[BufferCount - 1] = 0;
  if ( v13 != -2 )
  {
LABEL_21:
    if ( v13 >= 0 )
    {
      v11 = v13;
      goto LABEL_26;
    }
    goto LABEL_22;
  }
  if ( MaxCount == -1 )
    goto LABEL_15;
LABEL_22:
  *Buffer = 0;
  if ( v13 == -2 )
  {
    BYTE4(v21) = 1;
    LODWORD(v21) = 34;
    invalid_parameter_internal(0, 0, 0, 0, 0, (__crt_cached_ptd_host *)v17);
  }
LABEL_26:
  if ( v20 == 2 )
    *(_DWORD *)(v17[0] + 936LL) &= ~2u;
  if ( BYTE4(v21) )
  {
    v14 = v21;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v17) + 8) = v14;
  }
  if ( v23 )
  {
    v15 = v22;
    *((_DWORD *)__crt_cached_ptd_host::get_raw_ptd((__crt_cached_ptd_host *)v17) + 9) = v15;
  }
  return v11;
}

```

## disassembly

```asm
0x180056548  mov     rax, rsp
0x18005654b  mov     [rax+8], rbx
0x18005654f  mov     [rax+10h], rsi
0x180056553  mov     [rax+18h], rdi
0x180056557  mov     [rax+20h], r12
0x18005655b  push    rbp
0x18005655c  push    r14
0x18005655e  push    r15
0x180056560  mov     rbp, rsp
0x180056563  sub     rsp, 70h
0x180056567  mov     rax, [rbp+Locale]
0x18005656b  xor     r12d, r12d
0x18005656e  mov     [rbp+var_40], r12
0x180056572  mov     r15, r9
0x180056575  mov     [rbp+var_30], r12b
0x180056579  mov     r14, r8
0x18005657c  mov     [rbp+var_18], r12b
0x180056580  mov     rsi, rdx
0x180056583  mov     byte ptr [rbp+var_14+4], r12b
0x180056587  mov     [rbp+var_8], r12b
0x18005658b  test    rax, rax
0x18005658e  jz      short loc_180056595
0x180056590  movups  xmm0, xmmword ptr [rax]
0x180056593  jmp     short loc_1800565A5
0x180056595  cmp     cs:__acrt_locale_changed_data, r12d
0x18005659c  jnz     short loc_1800565AE
0x18005659e  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x1800565a5  mov     [rbp+var_18], 1
0x1800565a9  movdqu  [rbp+var_28], xmm0
0x1800565ae  mov     r9, [rbp+Format]; int
0x1800565b2  test    r9, r9
0x1800565b5  jz      loc_180056682
0x1800565bb  test    r15, r15
0x1800565be  jnz     short loc_1800565D6
0x1800565c0  test    rsi, rsi
0x1800565c3  jnz     short loc_1800565DF
0x1800565c5  test    r14, r14
0x1800565c8  jnz     loc_180056682
0x1800565ce  mov     edi, r12d
0x1800565d1  jmp     loc_1800566AE
0x1800565d6  test    rsi, rsi
0x1800565d9  jz      loc_180056682
0x1800565df  test    r14, r14
0x1800565e2  jz      loc_180056682
0x1800565e8  mov     rax, [rbp+ArgList]
0x1800565ec  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800565f0  mov     rbx, [rbp+var_14]
0x1800565f4  mov     [rsp+70h+var_48], rax; __int64
0x1800565f9  lea     rax, [rbp+var_40]
0x1800565fd  mov     [rsp+70h+var_50], rax; __crt_cached_ptd_host *
0x180056602  cmp     r14, r15
0x180056605  jbe     short loc_180056632
0x180056607  lea     r8, [r15+1]; int
0x18005660b  call    common_vsprintf___crt_stdio_output__format_validation_base_char_
0x180056610  cmp     eax, 0FFFFFFFEh
0x180056613  jnz     short loc_180056648
0x180056615  cmp     byte ptr [rbp+var_14+4], r12b
0x180056619  jz      loc_1800566AE
0x18005661f  cmp     dword ptr [rbp+var_14], 22h ; '"'
0x180056623  jnz     loc_1800566AE
0x180056629  mov     [rbp+var_14], rbx
0x18005662d  mov     dword ptr [rbp+var_14], ebx
0x180056630  jmp     short loc_1800566AE
0x180056632  call    common_vsprintf___crt_stdio_output__format_validation_base_char_
0x180056637  mov     [rsi+r14-1], r12b
0x18005663c  cmp     eax, 0FFFFFFFEh
0x18005663f  jnz     short loc_180056648
0x180056641  cmp     r15, rdi
0x180056644  jnz     short loc_18005664C
0x180056646  jmp     short loc_180056615
0x180056648  test    eax, eax
0x18005664a  jns     short loc_18005667E
0x18005664c  mov     [rsi], r12b
0x18005664f  cmp     eax, 0FFFFFFFEh
0x180056652  jnz     short loc_1800566AE
0x180056654  lea     rax, [rbp+var_40]
0x180056658  mov     byte ptr [rbp+var_14+4], 1
0x18005665c  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x180056661  xor     r9d, r9d; LineNo
0x180056664  xor     r8d, r8d; FileName
0x180056667  mov     [rsp+70h+var_50], r12; uintptr_t
0x18005666c  xor     edx, edx; FunctionName
0x18005666e  mov     dword ptr [rbp+var_14], 22h ; '"'
0x180056675  xor     ecx, ecx; Expression
0x180056677  call    _invalid_parameter_internal
0x18005667c  jmp     short loc_1800566AE
0x18005667e  mov     edi, eax
0x180056680  jmp     short loc_1800566AE
0x180056682  lea     rax, [rbp+var_40]
0x180056686  mov     byte ptr [rbp+var_14+4], 1
0x18005668a  mov     [rsp+70h+var_48], rax; __crt_cached_ptd_host *
0x18005668f  xor     r9d, r9d; LineNo
0x180056692  xor     r8d, r8d; FileName
0x180056695  mov     [rsp+70h+var_50], r12; uintptr_t
0x18005669a  xor     edx, edx; FunctionName
0x18005669c  mov     dword ptr [rbp+var_14], 16h
0x1800566a3  xor     ecx, ecx; Expression
0x1800566a5  call    _invalid_parameter_internal
0x1800566aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800566ae  cmp     [rbp+var_18], 2
0x1800566b2  jnz     short loc_1800566BF
0x1800566b4  mov     rax, [rbp+var_40]
0x1800566b8  and     dword ptr [rax+3A8h], 0FFFFFFFDh
0x1800566bf  cmp     byte ptr [rbp+var_14+4], r12b
0x1800566c3  jz      short loc_1800566D4
0x1800566c5  mov     ebx, dword ptr [rbp+var_14]
0x1800566c8  lea     rcx, [rbp+var_40]; this
0x1800566cc  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800566d1  mov     [rax+20h], ebx
0x1800566d4  cmp     [rbp+var_8], r12b
0x1800566d8  jz      short loc_1800566E9
0x1800566da  mov     ebx, [rbp+var_C]
0x1800566dd  lea     rcx, [rbp+var_40]; this
0x1800566e1  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x1800566e6  mov     [rax+24h], ebx
0x1800566e9  lea     r11, [rsp+70h+var_s0]
0x1800566ee  mov     eax, edi
0x1800566f0  mov     rbx, [r11+20h]
0x1800566f4  mov     rsi, [r11+28h]
0x1800566f8  mov     rdi, [r11+30h]
0x1800566fc  mov     r12, [r11+38h]
0x180056700  mov     rsp, r11
0x180056703  pop     r15
0x180056705  pop     r14
0x180056707  pop     rbp
0x180056708  retn
```
