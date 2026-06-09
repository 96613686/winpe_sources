# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x180053f2c`
- end: `0x180054118`
- name: `?write_stored_string_tchar@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800149cc`
- `0x180032370`
- `0x180053f2c`
- `0x1800559b8`
- `0x180057e0c`
- `0x1800582c0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(
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
0x180053f2c  mov     rax, rsp
0x180053f2f  push    rsi
0x180053f30  push    rdi
0x180053f31  push    r14
0x180053f33  sub     rsp, 50h
0x180053f37  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180053f3f  mov     [rax+10h], rbx
0x180053f43  mov     [rax+18h], rbp
0x180053f47  mov     rax, cs:__security_cookie
0x180053f4e  xor     rax, rsp
0x180053f51  mov     [rsp+68h+var_20], rax
0x180053f56  mov     rbx, rcx
0x180053f59  lea     rdi, [rcx+48h]
0x180053f5d  cmp     byte ptr [rcx+4Ch], 0
0x180053f61  jz      loc_1800540B0
0x180053f67  cmp     dword ptr [rdi], 0
0x180053f6a  jle     loc_1800540B0
0x180053f70  mov     rsi, [rcx+8]
0x180053f74  cmp     byte ptr [rsi+28h], 0
0x180053f78  jnz     short loc_180053F82
0x180053f7a  mov     rcx, rsi; this
0x180053f7d  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180053f82  mov     r14, [rbx+40h]
0x180053f86  mov     rax, [rsi+18h]
0x180053f8a  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180053f91  jnz     loc_180054020
0x180053f97  and     qword ptr [rsp+68h+var_28], 0
0x180053f9d  xor     ebp, ebp
0x180053f9f  cmp     [rdi], ebp
0x180053fa1  jz      loc_1800540F4
0x180053fa7  lea     rsi, [rbx+20h]
0x180053fab  movzx   edx, word ptr [r14]; char *
0x180053faf  lea     r14, [r14+2]
0x180053fb3  mov     r9, [rbx+8]; struct _Mbstatet *
0x180053fb7  lea     r8, [rsp+68h+var_28]; char16_t
0x180053fbc  lea     rcx, [rsp+68h+var_30]; this
0x180053fc1  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180053fc6  mov     r8, rax
0x180053fc9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180053fcd  jz      short loc_180054018
0x180053fcf  lea     r10, [rbx+460h]
0x180053fd6  mov     rdx, [rbx+8]
0x180053fda  mov     rax, [r10]
0x180053fdd  mov     ecx, [rax+14h]
0x180053fe0  nop
0x180053fe1  shr     ecx, 0Ch
0x180053fe4  test    cl, 1
0x180053fe7  jz      short loc_180053FF8
0x180053fe9  mov     rax, [r10]
0x180053fec  cmp     qword ptr [rax+8], 0
0x180053ff1  jnz     short loc_180053FF8
0x180053ff3  add     [rsi], r8d
0x180053ff6  jmp     short loc_18005400D
0x180053ff8  mov     [rsp+68h+var_48], rdx
0x180053ffd  mov     r9, rsi
0x180054000  lea     rdx, [rsp+68h+var_30]
0x180054005  mov     rcx, r10
0x180054008  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x18005400d  inc     ebp
0x18005400f  cmp     ebp, [rdi]
0x180054011  jnz     short loc_180053FAB
0x180054013  jmp     loc_1800540F4
0x180054018  or      dword ptr [rsi], 0FFFFFFFFh
0x18005401b  jmp     loc_1800540F4
0x180054020  xor     esi, esi
0x180054022  cmp     [rdi], esi
0x180054024  jz      loc_1800540F4
0x18005402a  and     [rsp+68h+var_30], 0
0x18005402f  movzx   r9d, word ptr [r14]
0x180054033  lea     r14, [r14+2]
0x180054037  mov     rax, [rbx+8]
0x18005403b  mov     [rsp+68h+var_48], rax
0x180054040  mov     r8d, 6
0x180054046  lea     rdx, [rsp+68h+var_28]
0x18005404b  lea     rcx, [rsp+68h+var_30]
0x180054050  call    _wctomb_internal
0x180054055  test    eax, eax
0x180054057  jnz     short loc_1800540AA
0x180054059  mov     r8d, [rsp+68h+var_30]
0x18005405e  test    r8d, r8d
0x180054061  jz      short loc_1800540AA
0x180054063  lea     r10, [rbx+460h]
0x18005406a  mov     rdx, [rbx+8]
0x18005406e  lea     r9, [rbx+20h]
0x180054072  mov     rax, [r10]
0x180054075  mov     ecx, [rax+14h]
0x180054078  nop
0x180054079  shr     ecx, 0Ch
0x18005407c  test    cl, 1
0x18005407f  jz      short loc_180054090
0x180054081  mov     rax, [r10]
0x180054084  cmp     qword ptr [rax+8], 0
0x180054089  jnz     short loc_180054090
0x18005408b  add     [r9], r8d
0x18005408e  jmp     short loc_1800540A2
0x180054090  mov     [rsp+68h+var_48], rdx
0x180054095  lea     rdx, [rsp+68h+var_28]
0x18005409a  mov     rcx, r10
0x18005409d  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800540a2  inc     esi
0x1800540a4  cmp     esi, [rdi]
0x1800540a6  jnz     short loc_18005402A
0x1800540a8  jmp     short loc_1800540F4
0x1800540aa  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800540ae  jmp     short loc_1800540F4
0x1800540b0  lea     r10, [rcx+460h]
0x1800540b7  mov     rdx, [rcx+8]
0x1800540bb  lea     r9, [rcx+20h]
0x1800540bf  mov     r8d, [rdi]
0x1800540c2  mov     r11, [rcx+40h]
0x1800540c6  mov     rax, [r10]
0x1800540c9  mov     ecx, [rax+14h]
0x1800540cc  nop
0x1800540cd  shr     ecx, 0Ch
0x1800540d0  test    cl, 1
0x1800540d3  jz      short loc_1800540E4
0x1800540d5  mov     rax, [r10]
0x1800540d8  cmp     qword ptr [rax+8], 0
0x1800540dd  jnz     short loc_1800540E4
0x1800540df  add     [r9], r8d
0x1800540e2  jmp     short loc_1800540F4
0x1800540e4  mov     [rsp+68h+var_48], rdx
0x1800540e9  mov     rdx, r11
0x1800540ec  mov     rcx, r10
0x1800540ef  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800540f4  mov     al, 1
0x1800540f6  mov     rcx, [rsp+68h+var_20]
0x1800540fb  xor     rcx, rsp; StackCookie
0x1800540fe  call    __security_check_cookie
0x180054103  lea     r11, [rsp+68h+var_18]
0x180054108  mov     rbx, [r11+28h]
0x18005410c  mov     rbp, [r11+30h]
0x180054110  mov     rsp, r11
0x180054113  pop     r14
0x180054115  pop     rdi
0x180054116  pop     rsi
0x180054117  retn
```
