# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x180054690`
- end: `0x180054830`
- name: `?write_stored_string_tchar@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800149cc`
- `0x180032370`
- `0x180054690`
- `0x18005586c`
- `0x180057e0c`
- `0x1800582c0`

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
0x180054690  mov     rax, rsp
0x180054693  push    rdi
0x180054694  push    r12
0x180054696  push    r13
0x180054698  push    r14
0x18005469a  push    r15
0x18005469c  sub     rsp, 50h
0x1800546a0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800546a8  mov     [rax+10h], rbx
0x1800546ac  mov     [rax+18h], rbp
0x1800546b0  mov     [rax+20h], rsi
0x1800546b4  mov     rax, cs:__security_cookie
0x1800546bb  xor     rax, rsp
0x1800546be  mov     [rsp+78h+var_30], rax
0x1800546c3  mov     rbx, rcx
0x1800546c6  lea     rsi, [rcx+48h]
0x1800546ca  xor     edi, edi
0x1800546cc  cmp     [rcx+4Ch], dil
0x1800546d0  jz      loc_1800547E3
0x1800546d6  cmp     [rsi], edi
0x1800546d8  jle     loc_1800547E3
0x1800546de  mov     rbp, [rcx+8]
0x1800546e2  cmp     [rbp+28h], dil
0x1800546e6  jnz     short loc_1800546F0
0x1800546e8  mov     rcx, rbp; this
0x1800546eb  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800546f0  mov     r15, [rbx+40h]
0x1800546f4  mov     rax, [rbp+18h]
0x1800546f8  cmp     dword ptr [rax+0Ch], 0FDE9h
0x1800546ff  jnz     short loc_180054764
0x180054701  mov     qword ptr [rsp+78h+var_38], rdi
0x180054706  cmp     [rsi], edi
0x180054708  jz      loc_180054803
0x18005470e  movzx   edx, word ptr [r15]; char *
0x180054712  lea     r15, [r15+2]
0x180054716  mov     r9, [rbx+8]; struct _Mbstatet *
0x18005471a  lea     r8, [rsp+78h+var_38]; char16_t
0x18005471f  lea     rcx, [rsp+78h+var_40]; this
0x180054724  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180054729  mov     r8, rax
0x18005472c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054730  jz      short loc_18005475B
0x180054732  lea     rcx, [rbx+460h]
0x180054739  mov     rax, [rbx+8]
0x18005473d  mov     [rsp+78h+var_58], rax
0x180054742  lea     r9, [rbx+20h]
0x180054746  lea     rdx, [rsp+78h+var_40]
0x18005474b  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054750  inc     edi
0x180054752  cmp     edi, [rsi]
0x180054754  jnz     short loc_18005470E
0x180054756  jmp     loc_180054803
0x18005475b  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005475f  jmp     loc_180054803
0x180054764  mov     r12d, edi
0x180054767  cmp     [rsi], edi
0x180054769  jz      loc_180054803
0x18005476f  lea     rbp, [rbx+20h]
0x180054773  mov     [rsp+78h+var_40], edi
0x180054777  movzx   r9d, word ptr [r15]
0x18005477b  lea     r15, [r15+2]
0x18005477f  lea     r14, [rbx+20h]
0x180054783  mov     rax, [rbx+8]
0x180054787  mov     [rsp+78h+var_58], rax
0x18005478c  mov     r8d, 6
0x180054792  lea     rdx, [rsp+78h+var_38]
0x180054797  lea     rcx, [rsp+78h+var_40]
0x18005479c  call    _wctomb_internal
0x1800547a1  test    eax, eax
0x1800547a3  jnz     short loc_1800547DD
0x1800547a5  mov     r14, rbp
0x1800547a8  mov     r8d, [rsp+78h+var_40]
0x1800547ad  test    r8d, r8d
0x1800547b0  jz      short loc_1800547DD
0x1800547b2  lea     rbp, [rbx+20h]
0x1800547b6  lea     rcx, [rbx+460h]
0x1800547bd  mov     rax, [rbx+8]
0x1800547c1  mov     [rsp+78h+var_58], rax
0x1800547c6  mov     r9, rbp
0x1800547c9  lea     rdx, [rsp+78h+var_38]
0x1800547ce  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800547d3  inc     r12d
0x1800547d6  cmp     r12d, [rsi]
0x1800547d9  jnz     short loc_180054773
0x1800547db  jmp     short loc_180054803
0x1800547dd  or      dword ptr [r14], 0FFFFFFFFh
0x1800547e1  jmp     short loc_180054803
0x1800547e3  lea     r9, [rcx+20h]
0x1800547e7  add     rcx, 460h
0x1800547ee  mov     rax, [rbx+8]
0x1800547f2  mov     [rsp+78h+var_58], rax
0x1800547f7  mov     r8d, [rsi]
0x1800547fa  mov     rdx, [rbx+40h]
0x1800547fe  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054803  mov     al, 1
0x180054805  mov     rcx, [rsp+78h+var_30]
0x18005480a  xor     rcx, rsp; StackCookie
0x18005480d  call    __security_check_cookie
0x180054812  lea     r11, [rsp+78h+var_28]
0x180054817  mov     rbx, [r11+38h]
0x18005481b  mov     rbp, [r11+40h]
0x18005481f  mov     rsi, [r11+48h]
0x180054823  mov     rsp, r11
0x180054826  pop     r15
0x180054828  pop     r14
0x18005482a  pop     r13
0x18005482c  pop     r12
0x18005482e  pop     rdi
0x18005482f  retn
```
