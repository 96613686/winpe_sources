# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x1800544f0`
- end: `0x180054690`
- name: `?write_stored_string_tchar@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800149cc`
- `0x180032370`
- `0x1800544f0`
- `0x18005586c`
- `0x180057e0c`
- `0x1800582c0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(
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
0x1800544f0  mov     rax, rsp
0x1800544f3  push    rdi
0x1800544f4  push    r12
0x1800544f6  push    r13
0x1800544f8  push    r14
0x1800544fa  push    r15
0x1800544fc  sub     rsp, 50h
0x180054500  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054508  mov     [rax+10h], rbx
0x18005450c  mov     [rax+18h], rbp
0x180054510  mov     [rax+20h], rsi
0x180054514  mov     rax, cs:__security_cookie
0x18005451b  xor     rax, rsp
0x18005451e  mov     [rsp+78h+var_30], rax
0x180054523  mov     rbx, rcx
0x180054526  lea     rsi, [rcx+48h]
0x18005452a  xor     edi, edi
0x18005452c  cmp     [rcx+4Ch], dil
0x180054530  jz      loc_180054643
0x180054536  cmp     [rsi], edi
0x180054538  jle     loc_180054643
0x18005453e  mov     rbp, [rcx+8]
0x180054542  cmp     [rbp+28h], dil
0x180054546  jnz     short loc_180054550
0x180054548  mov     rcx, rbp; this
0x18005454b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054550  mov     r15, [rbx+40h]
0x180054554  mov     rax, [rbp+18h]
0x180054558  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005455f  jnz     short loc_1800545C4
0x180054561  mov     qword ptr [rsp+78h+var_38], rdi
0x180054566  cmp     [rsi], edi
0x180054568  jz      loc_180054663
0x18005456e  movzx   edx, word ptr [r15]; char *
0x180054572  lea     r15, [r15+2]
0x180054576  mov     r9, [rbx+8]; struct _Mbstatet *
0x18005457a  lea     r8, [rsp+78h+var_38]; char16_t
0x18005457f  lea     rcx, [rsp+78h+var_40]; this
0x180054584  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180054589  mov     r8, rax
0x18005458c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054590  jz      short loc_1800545BB
0x180054592  lea     rcx, [rbx+460h]
0x180054599  mov     rax, [rbx+8]
0x18005459d  mov     [rsp+78h+var_58], rax
0x1800545a2  lea     r9, [rbx+20h]
0x1800545a6  lea     rdx, [rsp+78h+var_40]
0x1800545ab  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800545b0  inc     edi
0x1800545b2  cmp     edi, [rsi]
0x1800545b4  jnz     short loc_18005456E
0x1800545b6  jmp     loc_180054663
0x1800545bb  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800545bf  jmp     loc_180054663
0x1800545c4  mov     r12d, edi
0x1800545c7  cmp     [rsi], edi
0x1800545c9  jz      loc_180054663
0x1800545cf  lea     rbp, [rbx+20h]
0x1800545d3  mov     [rsp+78h+var_40], edi
0x1800545d7  movzx   r9d, word ptr [r15]
0x1800545db  lea     r15, [r15+2]
0x1800545df  lea     r14, [rbx+20h]
0x1800545e3  mov     rax, [rbx+8]
0x1800545e7  mov     [rsp+78h+var_58], rax
0x1800545ec  mov     r8d, 6
0x1800545f2  lea     rdx, [rsp+78h+var_38]
0x1800545f7  lea     rcx, [rsp+78h+var_40]
0x1800545fc  call    _wctomb_internal
0x180054601  test    eax, eax
0x180054603  jnz     short loc_18005463D
0x180054605  mov     r14, rbp
0x180054608  mov     r8d, [rsp+78h+var_40]
0x18005460d  test    r8d, r8d
0x180054610  jz      short loc_18005463D
0x180054612  lea     rbp, [rbx+20h]
0x180054616  lea     rcx, [rbx+460h]
0x18005461d  mov     rax, [rbx+8]
0x180054621  mov     [rsp+78h+var_58], rax
0x180054626  mov     r9, rbp
0x180054629  lea     rdx, [rsp+78h+var_38]
0x18005462e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054633  inc     r12d
0x180054636  cmp     r12d, [rsi]
0x180054639  jnz     short loc_1800545D3
0x18005463b  jmp     short loc_180054663
0x18005463d  or      dword ptr [r14], 0FFFFFFFFh
0x180054641  jmp     short loc_180054663
0x180054643  lea     r9, [rcx+20h]
0x180054647  add     rcx, 460h
0x18005464e  mov     rax, [rbx+8]
0x180054652  mov     [rsp+78h+var_58], rax
0x180054657  mov     r8d, [rsi]
0x18005465a  mov     rdx, [rbx+40h]
0x18005465e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054663  mov     al, 1
0x180054665  mov     rcx, [rsp+78h+var_30]
0x18005466a  xor     rcx, rsp; StackCookie
0x18005466d  call    __security_check_cookie
0x180054672  lea     r11, [rsp+78h+var_28]
0x180054677  mov     rbx, [r11+38h]
0x18005467b  mov     rbp, [r11+40h]
0x18005467f  mov     rsi, [r11+48h]
0x180054683  mov     rsp, r11
0x180054686  pop     r15
0x180054688  pop     r14
0x18005468a  pop     r13
0x18005468c  pop     r12
0x18005468e  pop     rdi
0x18005468f  retn
```
