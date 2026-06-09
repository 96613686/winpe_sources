# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x180054118`
- end: `0x180054304`
- name: `?write_stored_string_tchar@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800149cc`
- `0x180032370`
- `0x180054118`
- `0x1800559b8`
- `0x180057e0c`
- `0x1800582c0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(
        __int64 a1)
{
  int *v2; // rdi
  __int64 v3; // rsi
  unsigned __int16 *v4; // r14
  int v5; // ebp
  _DWORD *v6; // rsi
  char *v7; // rdx
  unsigned __int64 v8; // rax
  int v9; // esi
  __int64 v10; // r9
  _DWORD *v11; // r9
  _QWORD *v12; // r10
  _DWORD *v13; // r9
  int v14; // r8d
  struct __crt_cached_ptd_host *v16; // [rsp+20h] [rbp-48h]
  int v17; // [rsp+38h] [rbp-30h] BYREF
  char16_t v18[4]; // [rsp+40h] [rbp-28h] BYREF

  v2 = (int *)(a1 + 72);
  if ( *(_BYTE *)(a1 + 76) && *v2 > 0 )
  {
    v3 = *(_QWORD *)(a1 + 8);
    if ( !*(_BYTE *)(v3 + 40) )
      __crt_cached_ptd_host::update_locale_slow(*(__crt_cached_ptd_host **)(a1 + 8));
    v4 = *(unsigned __int16 **)(a1 + 64);
    if ( *(_DWORD *)(*(_QWORD *)(v3 + 24) + 12LL) == 65001 )
    {
      *(_QWORD *)v18 = 0;
      v5 = 0;
      if ( *v2 )
      {
        v6 = (_DWORD *)(a1 + 32);
        while ( 1 )
        {
          v7 = (char *)*v4++;
          v8 = __crt_mbstring::__c16rtomb_utf8(
                 (__crt_mbstring *)&v17,
                 v7,
                 (struct __crt_cached_ptd_host *)v18,
                 *(struct _Mbstatet **)(a1 + 8),
                 v16);
          if ( v8 == -1 )
            break;
          if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 1120) + 8LL) )
            __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(
              (_QWORD *)(a1 + 1120),
              (char *)&v17,
              v8,
              (_DWORD *)(a1 + 32),
              *(_QWORD *)(a1 + 8));
          else
            *v6 += v8;
          if ( ++v5 == *v2 )
            return 1;
        }
        *v6 = -1;
      }
    }
    else
    {
      v9 = 0;
      if ( *v2 )
      {
        while ( 1 )
        {
          v17 = 0;
          v10 = *v4++;
          if ( (unsigned int)wctomb_internal(&v17, v18, 6, v10, *(_QWORD *)(a1 + 8)) || !v17 )
            break;
          v11 = (_DWORD *)(a1 + 32);
          if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 1120) + 8LL) )
            __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(
              (_QWORD *)(a1 + 1120),
              (char *)v18,
              v17,
              v11,
              *(_QWORD *)(a1 + 8));
          else
            *v11 += v17;
          if ( ++v9 == *v2 )
            return 1;
        }
        *(_DWORD *)(a1 + 32) = -1;
      }
    }
  }
  else
  {
    v12 = (_QWORD *)(a1 + 1120);
    v13 = (_DWORD *)(a1 + 32);
    v14 = *v2;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*v12 + 8LL) )
      __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(
        v12,
        *(char **)(a1 + 64),
        v14,
        v13,
        *(_QWORD *)(a1 + 8));
    else
      *v13 += v14;
  }
  return 1;
}

```

## disassembly

```asm
0x180054118  mov     rax, rsp
0x18005411b  push    rsi
0x18005411c  push    rdi
0x18005411d  push    r14
0x18005411f  sub     rsp, 50h
0x180054123  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18005412b  mov     [rax+10h], rbx
0x18005412f  mov     [rax+18h], rbp
0x180054133  mov     rax, cs:__security_cookie
0x18005413a  xor     rax, rsp
0x18005413d  mov     [rsp+68h+var_20], rax
0x180054142  mov     rbx, rcx
0x180054145  lea     rdi, [rcx+48h]
0x180054149  cmp     byte ptr [rcx+4Ch], 0
0x18005414d  jz      loc_18005429C
0x180054153  cmp     dword ptr [rdi], 0
0x180054156  jle     loc_18005429C
0x18005415c  mov     rsi, [rcx+8]
0x180054160  cmp     byte ptr [rsi+28h], 0
0x180054164  jnz     short loc_18005416E
0x180054166  mov     rcx, rsi; this
0x180054169  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18005416e  mov     r14, [rbx+40h]
0x180054172  mov     rax, [rsi+18h]
0x180054176  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005417d  jnz     loc_18005420C
0x180054183  and     qword ptr [rsp+68h+var_28], 0
0x180054189  xor     ebp, ebp
0x18005418b  cmp     [rdi], ebp
0x18005418d  jz      loc_1800542E0
0x180054193  lea     rsi, [rbx+20h]
0x180054197  movzx   edx, word ptr [r14]; char *
0x18005419b  lea     r14, [r14+2]
0x18005419f  mov     r9, [rbx+8]; struct _Mbstatet *
0x1800541a3  lea     r8, [rsp+68h+var_28]; char16_t
0x1800541a8  lea     rcx, [rsp+68h+var_30]; this
0x1800541ad  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x1800541b2  mov     r8, rax
0x1800541b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800541b9  jz      short loc_180054204
0x1800541bb  lea     r10, [rbx+460h]
0x1800541c2  mov     rdx, [rbx+8]
0x1800541c6  mov     rax, [r10]
0x1800541c9  mov     ecx, [rax+14h]
0x1800541cc  nop
0x1800541cd  shr     ecx, 0Ch
0x1800541d0  test    cl, 1
0x1800541d3  jz      short loc_1800541E4
0x1800541d5  mov     rax, [r10]
0x1800541d8  cmp     qword ptr [rax+8], 0
0x1800541dd  jnz     short loc_1800541E4
0x1800541df  add     [rsi], r8d
0x1800541e2  jmp     short loc_1800541F9
0x1800541e4  mov     [rsp+68h+var_48], rdx
0x1800541e9  mov     r9, rsi
0x1800541ec  lea     rdx, [rsp+68h+var_30]
0x1800541f1  mov     rcx, r10
0x1800541f4  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800541f9  inc     ebp
0x1800541fb  cmp     ebp, [rdi]
0x1800541fd  jnz     short loc_180054197
0x1800541ff  jmp     loc_1800542E0
0x180054204  or      dword ptr [rsi], 0FFFFFFFFh
0x180054207  jmp     loc_1800542E0
0x18005420c  xor     esi, esi
0x18005420e  cmp     [rdi], esi
0x180054210  jz      loc_1800542E0
0x180054216  and     [rsp+68h+var_30], 0
0x18005421b  movzx   r9d, word ptr [r14]
0x18005421f  lea     r14, [r14+2]
0x180054223  mov     rax, [rbx+8]
0x180054227  mov     [rsp+68h+var_48], rax
0x18005422c  mov     r8d, 6
0x180054232  lea     rdx, [rsp+68h+var_28]
0x180054237  lea     rcx, [rsp+68h+var_30]
0x18005423c  call    _wctomb_internal
0x180054241  test    eax, eax
0x180054243  jnz     short loc_180054296
0x180054245  mov     r8d, [rsp+68h+var_30]
0x18005424a  test    r8d, r8d
0x18005424d  jz      short loc_180054296
0x18005424f  lea     r10, [rbx+460h]
0x180054256  mov     rdx, [rbx+8]
0x18005425a  lea     r9, [rbx+20h]
0x18005425e  mov     rax, [r10]
0x180054261  mov     ecx, [rax+14h]
0x180054264  nop
0x180054265  shr     ecx, 0Ch
0x180054268  test    cl, 1
0x18005426b  jz      short loc_18005427C
0x18005426d  mov     rax, [r10]
0x180054270  cmp     qword ptr [rax+8], 0
0x180054275  jnz     short loc_18005427C
0x180054277  add     [r9], r8d
0x18005427a  jmp     short loc_18005428E
0x18005427c  mov     [rsp+68h+var_48], rdx
0x180054281  lea     rdx, [rsp+68h+var_28]
0x180054286  mov     rcx, r10
0x180054289  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x18005428e  inc     esi
0x180054290  cmp     esi, [rdi]
0x180054292  jnz     short loc_180054216
0x180054294  jmp     short loc_1800542E0
0x180054296  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005429a  jmp     short loc_1800542E0
0x18005429c  lea     r10, [rcx+460h]
0x1800542a3  mov     rdx, [rcx+8]
0x1800542a7  lea     r9, [rcx+20h]
0x1800542ab  mov     r8d, [rdi]
0x1800542ae  mov     r11, [rcx+40h]
0x1800542b2  mov     rax, [r10]
0x1800542b5  mov     ecx, [rax+14h]
0x1800542b8  nop
0x1800542b9  shr     ecx, 0Ch
0x1800542bc  test    cl, 1
0x1800542bf  jz      short loc_1800542D0
0x1800542c1  mov     rax, [r10]
0x1800542c4  cmp     qword ptr [rax+8], 0
0x1800542c9  jnz     short loc_1800542D0
0x1800542cb  add     [r9], r8d
0x1800542ce  jmp     short loc_1800542E0
0x1800542d0  mov     [rsp+68h+var_48], rdx
0x1800542d5  mov     rdx, r11
0x1800542d8  mov     rcx, r10
0x1800542db  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800542e0  mov     al, 1
0x1800542e2  mov     rcx, [rsp+68h+var_20]
0x1800542e7  xor     rcx, rsp; StackCookie
0x1800542ea  call    __security_check_cookie
0x1800542ef  lea     r11, [rsp+68h+var_18]
0x1800542f4  mov     rbx, [r11+28h]
0x1800542f8  mov     rbp, [r11+30h]
0x1800542fc  mov     rsp, r11
0x1800542ff  pop     r14
0x180054301  pop     rdi
0x180054302  pop     rsi
0x180054303  retn
```
