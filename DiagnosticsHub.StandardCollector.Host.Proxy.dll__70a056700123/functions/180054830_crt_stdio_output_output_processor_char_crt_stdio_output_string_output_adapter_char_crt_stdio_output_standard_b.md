# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x180054830`
- end: `0x1800549d0`
- name: `?write_stored_string_tchar@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800149cc`
- `0x180032370`
- `0x180054830`
- `0x18005586c`
- `0x180057e0c`
- `0x1800582c0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(
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
0x180054830  mov     rax, rsp
0x180054833  push    rdi
0x180054834  push    r12
0x180054836  push    r13
0x180054838  push    r14
0x18005483a  push    r15
0x18005483c  sub     rsp, 50h
0x180054840  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054848  mov     [rax+10h], rbx
0x18005484c  mov     [rax+18h], rbp
0x180054850  mov     [rax+20h], rsi
0x180054854  mov     rax, cs:__security_cookie
0x18005485b  xor     rax, rsp
0x18005485e  mov     [rsp+78h+var_30], rax
0x180054863  mov     rbx, rcx
0x180054866  lea     rsi, [rcx+48h]
0x18005486a  xor     edi, edi
0x18005486c  cmp     [rcx+4Ch], dil
0x180054870  jz      loc_180054983
0x180054876  cmp     [rsi], edi
0x180054878  jle     loc_180054983
0x18005487e  mov     rbp, [rcx+8]
0x180054882  cmp     [rbp+28h], dil
0x180054886  jnz     short loc_180054890
0x180054888  mov     rcx, rbp; this
0x18005488b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054890  mov     r15, [rbx+40h]
0x180054894  mov     rax, [rbp+18h]
0x180054898  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005489f  jnz     short loc_180054904
0x1800548a1  mov     qword ptr [rsp+78h+var_38], rdi
0x1800548a6  cmp     [rsi], edi
0x1800548a8  jz      loc_1800549A3
0x1800548ae  movzx   edx, word ptr [r15]; char *
0x1800548b2  lea     r15, [r15+2]
0x1800548b6  mov     r9, [rbx+8]; struct _Mbstatet *
0x1800548ba  lea     r8, [rsp+78h+var_38]; char16_t
0x1800548bf  lea     rcx, [rsp+78h+var_40]; this
0x1800548c4  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x1800548c9  mov     r8, rax
0x1800548cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800548d0  jz      short loc_1800548FB
0x1800548d2  lea     rcx, [rbx+460h]
0x1800548d9  mov     rax, [rbx+8]
0x1800548dd  mov     [rsp+78h+var_58], rax
0x1800548e2  lea     r9, [rbx+20h]
0x1800548e6  lea     rdx, [rsp+78h+var_40]
0x1800548eb  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800548f0  inc     edi
0x1800548f2  cmp     edi, [rsi]
0x1800548f4  jnz     short loc_1800548AE
0x1800548f6  jmp     loc_1800549A3
0x1800548fb  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800548ff  jmp     loc_1800549A3
0x180054904  mov     r12d, edi
0x180054907  cmp     [rsi], edi
0x180054909  jz      loc_1800549A3
0x18005490f  lea     rbp, [rbx+20h]
0x180054913  mov     [rsp+78h+var_40], edi
0x180054917  movzx   r9d, word ptr [r15]
0x18005491b  lea     r15, [r15+2]
0x18005491f  lea     r14, [rbx+20h]
0x180054923  mov     rax, [rbx+8]
0x180054927  mov     [rsp+78h+var_58], rax
0x18005492c  mov     r8d, 6
0x180054932  lea     rdx, [rsp+78h+var_38]
0x180054937  lea     rcx, [rsp+78h+var_40]
0x18005493c  call    _wctomb_internal
0x180054941  test    eax, eax
0x180054943  jnz     short loc_18005497D
0x180054945  mov     r14, rbp
0x180054948  mov     r8d, [rsp+78h+var_40]
0x18005494d  test    r8d, r8d
0x180054950  jz      short loc_18005497D
0x180054952  lea     rbp, [rbx+20h]
0x180054956  lea     rcx, [rbx+460h]
0x18005495d  mov     rax, [rbx+8]
0x180054961  mov     [rsp+78h+var_58], rax
0x180054966  mov     r9, rbp
0x180054969  lea     rdx, [rsp+78h+var_38]
0x18005496e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054973  inc     r12d
0x180054976  cmp     r12d, [rsi]
0x180054979  jnz     short loc_180054913
0x18005497b  jmp     short loc_1800549A3
0x18005497d  or      dword ptr [r14], 0FFFFFFFFh
0x180054981  jmp     short loc_1800549A3
0x180054983  lea     r9, [rcx+20h]
0x180054987  add     rcx, 460h
0x18005498e  mov     rax, [rbx+8]
0x180054992  mov     [rsp+78h+var_58], rax
0x180054997  mov     r8d, [rsi]
0x18005499a  mov     rdx, [rbx+40h]
0x18005499e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800549a3  mov     al, 1
0x1800549a5  mov     rcx, [rsp+78h+var_30]
0x1800549aa  xor     rcx, rsp; StackCookie
0x1800549ad  call    __security_check_cookie
0x1800549b2  lea     r11, [rsp+78h+var_28]
0x1800549b7  mov     rbx, [r11+38h]
0x1800549bb  mov     rbp, [r11+40h]
0x1800549bf  mov     rsi, [r11+48h]
0x1800549c3  mov     rsp, r11
0x1800549c6  pop     r15
0x1800549c8  pop     r14
0x1800549ca  pop     r13
0x1800549cc  pop     r12
0x1800549ce  pop     rdi
0x1800549cf  retn
```
