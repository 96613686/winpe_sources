# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x1800547d0`
- end: `0x180054970`
- name: `?write_stored_string_tchar@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002810`
- `0x18001512c`
- `0x1800547d0`
- `0x180055b4c`
- `0x1800580ec`
- `0x1800585a0`

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
0x1800547d0  mov     rax, rsp
0x1800547d3  push    rdi
0x1800547d4  push    r12
0x1800547d6  push    r13
0x1800547d8  push    r14
0x1800547da  push    r15
0x1800547dc  sub     rsp, 50h
0x1800547e0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800547e8  mov     [rax+10h], rbx
0x1800547ec  mov     [rax+18h], rbp
0x1800547f0  mov     [rax+20h], rsi
0x1800547f4  mov     rax, cs:__security_cookie
0x1800547fb  xor     rax, rsp
0x1800547fe  mov     [rsp+78h+var_30], rax
0x180054803  mov     rbx, rcx
0x180054806  lea     rsi, [rcx+48h]
0x18005480a  xor     edi, edi
0x18005480c  cmp     [rcx+4Ch], dil
0x180054810  jz      loc_180054923
0x180054816  cmp     [rsi], edi
0x180054818  jle     loc_180054923
0x18005481e  mov     rbp, [rcx+8]
0x180054822  cmp     [rbp+28h], dil
0x180054826  jnz     short loc_180054830
0x180054828  mov     rcx, rbp; this
0x18005482b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054830  mov     r15, [rbx+40h]
0x180054834  mov     rax, [rbp+18h]
0x180054838  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005483f  jnz     short loc_1800548A4
0x180054841  mov     qword ptr [rsp+78h+var_38], rdi
0x180054846  cmp     [rsi], edi
0x180054848  jz      loc_180054943
0x18005484e  movzx   edx, word ptr [r15]; char *
0x180054852  lea     r15, [r15+2]
0x180054856  mov     r9, [rbx+8]; struct _Mbstatet *
0x18005485a  lea     r8, [rsp+78h+var_38]; char16_t
0x18005485f  lea     rcx, [rsp+78h+var_40]; this
0x180054864  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180054869  mov     r8, rax
0x18005486c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054870  jz      short loc_18005489B
0x180054872  lea     rcx, [rbx+460h]
0x180054879  mov     rax, [rbx+8]
0x18005487d  mov     [rsp+78h+var_58], rax
0x180054882  lea     r9, [rbx+20h]
0x180054886  lea     rdx, [rsp+78h+var_40]
0x18005488b  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054890  inc     edi
0x180054892  cmp     edi, [rsi]
0x180054894  jnz     short loc_18005484E
0x180054896  jmp     loc_180054943
0x18005489b  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005489f  jmp     loc_180054943
0x1800548a4  mov     r12d, edi
0x1800548a7  cmp     [rsi], edi
0x1800548a9  jz      loc_180054943
0x1800548af  lea     rbp, [rbx+20h]
0x1800548b3  mov     [rsp+78h+var_40], edi
0x1800548b7  movzx   r9d, word ptr [r15]
0x1800548bb  lea     r15, [r15+2]
0x1800548bf  lea     r14, [rbx+20h]
0x1800548c3  mov     rax, [rbx+8]
0x1800548c7  mov     [rsp+78h+var_58], rax
0x1800548cc  mov     r8d, 6
0x1800548d2  lea     rdx, [rsp+78h+var_38]
0x1800548d7  lea     rcx, [rsp+78h+var_40]
0x1800548dc  call    _wctomb_internal
0x1800548e1  test    eax, eax
0x1800548e3  jnz     short loc_18005491D
0x1800548e5  mov     r14, rbp
0x1800548e8  mov     r8d, [rsp+78h+var_40]
0x1800548ed  test    r8d, r8d
0x1800548f0  jz      short loc_18005491D
0x1800548f2  lea     rbp, [rbx+20h]
0x1800548f6  lea     rcx, [rbx+460h]
0x1800548fd  mov     rax, [rbx+8]
0x180054901  mov     [rsp+78h+var_58], rax
0x180054906  mov     r9, rbp
0x180054909  lea     rdx, [rsp+78h+var_38]
0x18005490e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054913  inc     r12d
0x180054916  cmp     r12d, [rsi]
0x180054919  jnz     short loc_1800548B3
0x18005491b  jmp     short loc_180054943
0x18005491d  or      dword ptr [r14], 0FFFFFFFFh
0x180054921  jmp     short loc_180054943
0x180054923  lea     r9, [rcx+20h]
0x180054927  add     rcx, 460h
0x18005492e  mov     rax, [rbx+8]
0x180054932  mov     [rsp+78h+var_58], rax
0x180054937  mov     r8d, [rsi]
0x18005493a  mov     rdx, [rbx+40h]
0x18005493e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054943  mov     al, 1
0x180054945  mov     rcx, [rsp+78h+var_30]
0x18005494a  xor     rcx, rsp; StackCookie
0x18005494d  call    __security_check_cookie
0x180054952  lea     r11, [rsp+78h+var_28]
0x180054957  mov     rbx, [r11+38h]
0x18005495b  mov     rbp, [r11+40h]
0x18005495f  mov     rsi, [r11+48h]
0x180054963  mov     rsp, r11
0x180054966  pop     r15
0x180054968  pop     r14
0x18005496a  pop     r13
0x18005496c  pop     r12
0x18005496e  pop     rdi
0x18005496f  retn
```
