# __crt_stdio_output::output_processor<char,__crt_stdio_output::string_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::string_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x180054b10`
- end: `0x180054cb0`
- name: `?write_stored_string_tchar@?$output_processor@DV?$string_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$string_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002810`
- `0x18001512c`
- `0x180054b10`
- `0x180055b4c`
- `0x1800580ec`
- `0x1800585a0`

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
0x180054b10  mov     rax, rsp
0x180054b13  push    rdi
0x180054b14  push    r12
0x180054b16  push    r13
0x180054b18  push    r14
0x180054b1a  push    r15
0x180054b1c  sub     rsp, 50h
0x180054b20  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054b28  mov     [rax+10h], rbx
0x180054b2c  mov     [rax+18h], rbp
0x180054b30  mov     [rax+20h], rsi
0x180054b34  mov     rax, cs:__security_cookie
0x180054b3b  xor     rax, rsp
0x180054b3e  mov     [rsp+78h+var_30], rax
0x180054b43  mov     rbx, rcx
0x180054b46  lea     rsi, [rcx+48h]
0x180054b4a  xor     edi, edi
0x180054b4c  cmp     [rcx+4Ch], dil
0x180054b50  jz      loc_180054C63
0x180054b56  cmp     [rsi], edi
0x180054b58  jle     loc_180054C63
0x180054b5e  mov     rbp, [rcx+8]
0x180054b62  cmp     [rbp+28h], dil
0x180054b66  jnz     short loc_180054B70
0x180054b68  mov     rcx, rbp; this
0x180054b6b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054b70  mov     r15, [rbx+40h]
0x180054b74  mov     rax, [rbp+18h]
0x180054b78  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054b7f  jnz     short loc_180054BE4
0x180054b81  mov     qword ptr [rsp+78h+var_38], rdi
0x180054b86  cmp     [rsi], edi
0x180054b88  jz      loc_180054C83
0x180054b8e  movzx   edx, word ptr [r15]; char *
0x180054b92  lea     r15, [r15+2]
0x180054b96  mov     r9, [rbx+8]; struct _Mbstatet *
0x180054b9a  lea     r8, [rsp+78h+var_38]; char16_t
0x180054b9f  lea     rcx, [rsp+78h+var_40]; this
0x180054ba4  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180054ba9  mov     r8, rax
0x180054bac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054bb0  jz      short loc_180054BDB
0x180054bb2  lea     rcx, [rbx+460h]
0x180054bb9  mov     rax, [rbx+8]
0x180054bbd  mov     [rsp+78h+var_58], rax
0x180054bc2  lea     r9, [rbx+20h]
0x180054bc6  lea     rdx, [rsp+78h+var_40]
0x180054bcb  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054bd0  inc     edi
0x180054bd2  cmp     edi, [rsi]
0x180054bd4  jnz     short loc_180054B8E
0x180054bd6  jmp     loc_180054C83
0x180054bdb  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054bdf  jmp     loc_180054C83
0x180054be4  mov     r12d, edi
0x180054be7  cmp     [rsi], edi
0x180054be9  jz      loc_180054C83
0x180054bef  lea     rbp, [rbx+20h]
0x180054bf3  mov     [rsp+78h+var_40], edi
0x180054bf7  movzx   r9d, word ptr [r15]
0x180054bfb  lea     r15, [r15+2]
0x180054bff  lea     r14, [rbx+20h]
0x180054c03  mov     rax, [rbx+8]
0x180054c07  mov     [rsp+78h+var_58], rax
0x180054c0c  mov     r8d, 6
0x180054c12  lea     rdx, [rsp+78h+var_38]
0x180054c17  lea     rcx, [rsp+78h+var_40]
0x180054c1c  call    _wctomb_internal
0x180054c21  test    eax, eax
0x180054c23  jnz     short loc_180054C5D
0x180054c25  mov     r14, rbp
0x180054c28  mov     r8d, [rsp+78h+var_40]
0x180054c2d  test    r8d, r8d
0x180054c30  jz      short loc_180054C5D
0x180054c32  lea     rbp, [rbx+20h]
0x180054c36  lea     rcx, [rbx+460h]
0x180054c3d  mov     rax, [rbx+8]
0x180054c41  mov     [rsp+78h+var_58], rax
0x180054c46  mov     r9, rbp
0x180054c49  lea     rdx, [rsp+78h+var_38]
0x180054c4e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054c53  inc     r12d
0x180054c56  cmp     r12d, [rsi]
0x180054c59  jnz     short loc_180054BF3
0x180054c5b  jmp     short loc_180054C83
0x180054c5d  or      dword ptr [r14], 0FFFFFFFFh
0x180054c61  jmp     short loc_180054C83
0x180054c63  lea     r9, [rcx+20h]
0x180054c67  add     rcx, 460h
0x180054c6e  mov     rax, [rbx+8]
0x180054c72  mov     [rsp+78h+var_58], rax
0x180054c77  mov     r8d, [rsi]
0x180054c7a  mov     rdx, [rbx+40h]
0x180054c7e  call    ?write_string@?$string_output_adapter@D@__crt_stdio_output@@QEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<char>::write_string(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054c83  mov     al, 1
0x180054c85  mov     rcx, [rsp+78h+var_30]
0x180054c8a  xor     rcx, rsp; StackCookie
0x180054c8d  call    __security_check_cookie
0x180054c92  lea     r11, [rsp+78h+var_28]
0x180054c97  mov     rbx, [r11+38h]
0x180054c9b  mov     rbp, [r11+40h]
0x180054c9f  mov     rsi, [r11+48h]
0x180054ca3  mov     rsp, r11
0x180054ca6  pop     r15
0x180054ca8  pop     r14
0x180054caa  pop     r13
0x180054cac  pop     r12
0x180054cae  pop     rdi
0x180054caf  retn
```
