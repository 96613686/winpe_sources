# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x180054304`
- end: `0x1800544f0`
- name: `?write_stored_string_tchar@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800149cc`
- `0x180032370`
- `0x180054304`
- `0x1800559b8`
- `0x180057e0c`
- `0x1800582c0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(
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
0x180054304  mov     rax, rsp
0x180054307  push    rsi
0x180054308  push    rdi
0x180054309  push    r14
0x18005430b  sub     rsp, 50h
0x18005430f  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180054317  mov     [rax+10h], rbx
0x18005431b  mov     [rax+18h], rbp
0x18005431f  mov     rax, cs:__security_cookie
0x180054326  xor     rax, rsp
0x180054329  mov     [rsp+68h+var_20], rax
0x18005432e  mov     rbx, rcx
0x180054331  lea     rdi, [rcx+48h]
0x180054335  cmp     byte ptr [rcx+4Ch], 0
0x180054339  jz      loc_180054488
0x18005433f  cmp     dword ptr [rdi], 0
0x180054342  jle     loc_180054488
0x180054348  mov     rsi, [rcx+8]
0x18005434c  cmp     byte ptr [rsi+28h], 0
0x180054350  jnz     short loc_18005435A
0x180054352  mov     rcx, rsi; this
0x180054355  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18005435a  mov     r14, [rbx+40h]
0x18005435e  mov     rax, [rsi+18h]
0x180054362  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054369  jnz     loc_1800543F8
0x18005436f  and     qword ptr [rsp+68h+var_28], 0
0x180054375  xor     ebp, ebp
0x180054377  cmp     [rdi], ebp
0x180054379  jz      loc_1800544CC
0x18005437f  lea     rsi, [rbx+20h]
0x180054383  movzx   edx, word ptr [r14]; char *
0x180054387  lea     r14, [r14+2]
0x18005438b  mov     r9, [rbx+8]; struct _Mbstatet *
0x18005438f  lea     r8, [rsp+68h+var_28]; char16_t
0x180054394  lea     rcx, [rsp+68h+var_30]; this
0x180054399  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x18005439e  mov     r8, rax
0x1800543a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800543a5  jz      short loc_1800543F0
0x1800543a7  lea     r10, [rbx+460h]
0x1800543ae  mov     rdx, [rbx+8]
0x1800543b2  mov     rax, [r10]
0x1800543b5  mov     ecx, [rax+14h]
0x1800543b8  nop
0x1800543b9  shr     ecx, 0Ch
0x1800543bc  test    cl, 1
0x1800543bf  jz      short loc_1800543D0
0x1800543c1  mov     rax, [r10]
0x1800543c4  cmp     qword ptr [rax+8], 0
0x1800543c9  jnz     short loc_1800543D0
0x1800543cb  add     [rsi], r8d
0x1800543ce  jmp     short loc_1800543E5
0x1800543d0  mov     [rsp+68h+var_48], rdx
0x1800543d5  mov     r9, rsi
0x1800543d8  lea     rdx, [rsp+68h+var_30]
0x1800543dd  mov     rcx, r10
0x1800543e0  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800543e5  inc     ebp
0x1800543e7  cmp     ebp, [rdi]
0x1800543e9  jnz     short loc_180054383
0x1800543eb  jmp     loc_1800544CC
0x1800543f0  or      dword ptr [rsi], 0FFFFFFFFh
0x1800543f3  jmp     loc_1800544CC
0x1800543f8  xor     esi, esi
0x1800543fa  cmp     [rdi], esi
0x1800543fc  jz      loc_1800544CC
0x180054402  and     [rsp+68h+var_30], 0
0x180054407  movzx   r9d, word ptr [r14]
0x18005440b  lea     r14, [r14+2]
0x18005440f  mov     rax, [rbx+8]
0x180054413  mov     [rsp+68h+var_48], rax
0x180054418  mov     r8d, 6
0x18005441e  lea     rdx, [rsp+68h+var_28]
0x180054423  lea     rcx, [rsp+68h+var_30]
0x180054428  call    _wctomb_internal
0x18005442d  test    eax, eax
0x18005442f  jnz     short loc_180054482
0x180054431  mov     r8d, [rsp+68h+var_30]
0x180054436  test    r8d, r8d
0x180054439  jz      short loc_180054482
0x18005443b  lea     r10, [rbx+460h]
0x180054442  mov     rdx, [rbx+8]
0x180054446  lea     r9, [rbx+20h]
0x18005444a  mov     rax, [r10]
0x18005444d  mov     ecx, [rax+14h]
0x180054450  nop
0x180054451  shr     ecx, 0Ch
0x180054454  test    cl, 1
0x180054457  jz      short loc_180054468
0x180054459  mov     rax, [r10]
0x18005445c  cmp     qword ptr [rax+8], 0
0x180054461  jnz     short loc_180054468
0x180054463  add     [r9], r8d
0x180054466  jmp     short loc_18005447A
0x180054468  mov     [rsp+68h+var_48], rdx
0x18005446d  lea     rdx, [rsp+68h+var_28]
0x180054472  mov     rcx, r10
0x180054475  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x18005447a  inc     esi
0x18005447c  cmp     esi, [rdi]
0x18005447e  jnz     short loc_180054402
0x180054480  jmp     short loc_1800544CC
0x180054482  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054486  jmp     short loc_1800544CC
0x180054488  lea     r10, [rcx+460h]
0x18005448f  mov     rdx, [rcx+8]
0x180054493  lea     r9, [rcx+20h]
0x180054497  mov     r8d, [rdi]
0x18005449a  mov     r11, [rcx+40h]
0x18005449e  mov     rax, [r10]
0x1800544a1  mov     ecx, [rax+14h]
0x1800544a4  nop
0x1800544a5  shr     ecx, 0Ch
0x1800544a8  test    cl, 1
0x1800544ab  jz      short loc_1800544BC
0x1800544ad  mov     rax, [r10]
0x1800544b0  cmp     qword ptr [rax+8], 0
0x1800544b5  jnz     short loc_1800544BC
0x1800544b7  add     [r9], r8d
0x1800544ba  jmp     short loc_1800544CC
0x1800544bc  mov     [rsp+68h+var_48], rdx
0x1800544c1  mov     rdx, r11
0x1800544c4  mov     rcx, r10
0x1800544c7  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800544cc  mov     al, 1
0x1800544ce  mov     rcx, [rsp+68h+var_20]
0x1800544d3  xor     rcx, rsp; StackCookie
0x1800544d6  call    __security_check_cookie
0x1800544db  lea     r11, [rsp+68h+var_18]
0x1800544e0  mov     rbx, [r11+28h]
0x1800544e4  mov     rbp, [r11+30h]
0x1800544e8  mov     rsp, r11
0x1800544eb  pop     r14
0x1800544ed  pop     rdi
0x1800544ee  pop     rsi
0x1800544ef  retn
```
