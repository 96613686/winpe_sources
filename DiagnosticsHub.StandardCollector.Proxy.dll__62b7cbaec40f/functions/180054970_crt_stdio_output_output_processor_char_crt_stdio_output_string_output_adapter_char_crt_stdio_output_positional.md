# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x180054970`
- end: `0x180054b10`
- name: `?write_stored_string_tchar@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002810`
- `0x18001512c`
- `0x180054970`
- `0x180055b4c`
- `0x1800580ec`
- `0x1800585a0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(
        __int64 a1)
{
  int *v2; // rsi
  int v3; // edi
  __int64 v4; // rbp
  unsigned __int16 *v5; // r15
  char *v6; // rdx
  unsigned __int64 v7; // r8
  int v8; // r12d
  _DWORD *v9; // rbp
  __int64 v10; // r9
  _DWORD *v11; // r14
  struct __crt_cached_ptd_host *v13; // [rsp+20h] [rbp-58h]
  unsigned int v14; // [rsp+38h] [rbp-40h] BYREF
  char16_t v15[4]; // [rsp+40h] [rbp-38h] BYREF

  v2 = (int *)(a1 + 72);
  v3 = 0;
  if ( *(_BYTE *)(a1 + 76) && *v2 > 0 )
  {
    v4 = *(_QWORD *)(a1 + 8);
    if ( !*(_BYTE *)(v4 + 40) )
      __crt_cached_ptd_host::update_locale_slow(*(__crt_cached_ptd_host **)(a1 + 8));
    v5 = *(unsigned __int16 **)(a1 + 64);
    if ( *(_DWORD *)(*(_QWORD *)(v4 + 24) + 12LL) == 65001 )
    {
      *(_QWORD *)v15 = 0;
      if ( *v2 )
      {
        while ( 1 )
        {
          v6 = (char *)*v5++;
          v7 = __crt_mbstring::__c16rtomb_utf8(
                 (__crt_mbstring *)&v14,
                 v6,
                 (struct __crt_cached_ptd_host *)v15,
                 *(struct _Mbstatet **)(a1 + 8),
                 v13);
          if ( v7 == -1 )
            break;
          __crt_stdio_output::string_output_adapter<char>::write_string(
            a1 + 1120,
            &v14,
            v7,
            a1 + 32,
            *(_QWORD *)(a1 + 8));
          if ( ++v3 == *v2 )
            return 1;
        }
        *(_DWORD *)(a1 + 32) = -1;
      }
    }
    else
    {
      v8 = 0;
      if ( *v2 )
      {
        v9 = (_DWORD *)(a1 + 32);
        while ( 1 )
        {
          v14 = 0;
          v10 = *v5++;
          v11 = (_DWORD *)(a1 + 32);
          if ( (unsigned int)wctomb_internal(&v14, v15, 6, v10, *(_QWORD *)(a1 + 8)) )
            break;
          v11 = v9;
          if ( !v14 )
            break;
          v9 = (_DWORD *)(a1 + 32);
          __crt_stdio_output::string_output_adapter<char>::write_string(
            a1 + 1120,
            v15,
            v14,
            a1 + 32,
            *(_QWORD *)(a1 + 8));
          if ( ++v8 == *v2 )
            return 1;
        }
        *v11 = -1;
      }
    }
  }
  else
  {
    __crt_stdio_output::string_output_adapter<char>::write_string(
      a1 + 1120,
      *(_QWORD *)(a1 + 64),
      (unsigned int)*v2,
      a1 + 32,
      *(_QWORD *)(a1 + 8));
  }
  return 1;
}

```

## disassembly

```asm
0x180054970  mov     rax, rsp
0x180054973  push    rdi
0x180054974  push    r12
0x180054976  push    r13
0x180054978  push    r14
0x18005497a  push    r15
0x18005497c  sub     rsp, 50h
0x180054980  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054988  mov     [rax+10h], rbx
0x18005498c  mov     [rax+18h], rbp
0x180054990  mov     [rax+20h], rsi
0x180054994  mov     rax, cs:__security_cookie
0x18005499b  xor     rax, rsp
0x18005499e  mov     [rsp+78h+var_30], rax
0x1800549a3  mov     rbx, rcx
0x1800549a6  lea     rsi, [rcx+48h]
0x1800549aa  xor     edi, edi
0x1800549ac  cmp     [rcx+4Ch], dil
0x1800549b0  jz      loc_180054AC3
0x1800549b6  cmp     [rsi], edi
0x1800549b8  jle     loc_180054AC3
0x1800549be  mov     rbp, [rcx+8]
0x1800549c2  cmp     [rbp+28h], dil
0x1800549c6  jnz     short loc_1800549D0
0x1800549c8  mov     rcx, rbp; this
0x1800549cb  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800549d0  mov     r15, [rbx+40h]
0x1800549d4  mov     rax, [rbp+18h]
0x1800549d8  cmp     dword ptr [rax+0Ch], 0FDE9h
0x1800549df  jnz     short loc_180054A44
0x1800549e1  mov     qword ptr [rsp+78h+var_38], rdi
0x1800549e6  cmp     [rsi], edi
0x1800549e8  jz      loc_180054AE3
0x1800549ee  movzx   edx, word ptr [r15]; char *
0x1800549f2  lea     r15, [r15+2]
0x1800549f6  mov     r9, [rbx+8]; struct _Mbstatet *
0x1800549fa  lea     r8, [rsp+78h+var_38]; char16_t
0x1800549ff  lea     rcx, [rsp+78h+var_40]; this
0x180054a04  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180054a09  mov     r8, rax
0x180054a0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054a10  jz      short loc_180054A3B
0x180054a12  lea     rcx, [rbx+460h]
0x180054a19  mov     rax, [rbx+8]
0x180054a1d  mov     [rsp+78h+var_58], rax
0x180054a22  lea     r9, [rbx+20h]
0x180054a26  lea     rdx, [rsp+78h+var_40]
0x180054a2b  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054a30  inc     edi
0x180054a32  cmp     edi, [rsi]
0x180054a34  jnz     short loc_1800549EE
0x180054a36  jmp     loc_180054AE3
0x180054a3b  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054a3f  jmp     loc_180054AE3
0x180054a44  mov     r12d, edi
0x180054a47  cmp     [rsi], edi
0x180054a49  jz      loc_180054AE3
0x180054a4f  lea     rbp, [rbx+20h]
0x180054a53  mov     [rsp+78h+var_40], edi
0x180054a57  movzx   r9d, word ptr [r15]
0x180054a5b  lea     r15, [r15+2]
0x180054a5f  lea     r14, [rbx+20h]
0x180054a63  mov     rax, [rbx+8]
0x180054a67  mov     [rsp+78h+var_58], rax
0x180054a6c  mov     r8d, 6
0x180054a72  lea     rdx, [rsp+78h+var_38]
0x180054a77  lea     rcx, [rsp+78h+var_40]
0x180054a7c  call    _wctomb_internal
0x180054a81  test    eax, eax
0x180054a83  jnz     short loc_180054ABD
0x180054a85  mov     r14, rbp
0x180054a88  mov     r8d, [rsp+78h+var_40]
0x180054a8d  test    r8d, r8d
0x180054a90  jz      short loc_180054ABD
0x180054a92  lea     rbp, [rbx+20h]
0x180054a96  lea     rcx, [rbx+460h]
0x180054a9d  mov     rax, [rbx+8]
0x180054aa1  mov     [rsp+78h+var_58], rax
0x180054aa6  mov     r9, rbp
0x180054aa9  lea     rdx, [rsp+78h+var_38]
0x180054aae  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054ab3  inc     r12d
0x180054ab6  cmp     r12d, [rsi]
0x180054ab9  jnz     short loc_180054A53
0x180054abb  jmp     short loc_180054AE3
0x180054abd  or      dword ptr [r14], 0FFFFFFFFh
0x180054ac1  jmp     short loc_180054AE3
0x180054ac3  lea     r9, [rcx+20h]
0x180054ac7  add     rcx, 460h
0x180054ace  mov     rax, [rbx+8]
0x180054ad2  mov     [rsp+78h+var_58], rax
0x180054ad7  mov     r8d, [rsi]
0x180054ada  mov     rdx, [rbx+40h]
0x180054ade  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054ae3  mov     al, 1
0x180054ae5  mov     rcx, [rsp+78h+var_30]
0x180054aea  xor     rcx, rsp; StackCookie
0x180054aed  call    __security_check_cookie
0x180054af2  lea     r11, [rsp+78h+var_28]
0x180054af7  mov     rbx, [r11+38h]
0x180054afb  mov     rbp, [r11+40h]
0x180054aff  mov     rsi, [r11+48h]
0x180054b03  mov     rsp, r11
0x180054b06  pop     r15
0x180054b08  pop     r14
0x180054b0a  pop     r13
0x180054b0c  pop     r12
0x180054b0e  pop     rdi
0x180054b0f  retn
```
