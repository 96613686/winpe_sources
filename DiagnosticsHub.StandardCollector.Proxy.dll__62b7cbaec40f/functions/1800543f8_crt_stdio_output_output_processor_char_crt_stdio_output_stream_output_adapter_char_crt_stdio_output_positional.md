# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::positional_parameter_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x1800543f8`
- end: `0x1800545e4`
- name: `?write_stored_string_tchar@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$positional_parameter_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002810`
- `0x18001512c`
- `0x1800543f8`
- `0x180055c98`
- `0x1800580ec`
- `0x1800585a0`

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
0x1800543f8  mov     rax, rsp
0x1800543fb  push    rsi
0x1800543fc  push    rdi
0x1800543fd  push    r14
0x1800543ff  sub     rsp, 50h
0x180054403  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18005440b  mov     [rax+10h], rbx
0x18005440f  mov     [rax+18h], rbp
0x180054413  mov     rax, cs:__security_cookie
0x18005441a  xor     rax, rsp
0x18005441d  mov     [rsp+68h+var_20], rax
0x180054422  mov     rbx, rcx
0x180054425  lea     rdi, [rcx+48h]
0x180054429  cmp     byte ptr [rcx+4Ch], 0
0x18005442d  jz      loc_18005457C
0x180054433  cmp     dword ptr [rdi], 0
0x180054436  jle     loc_18005457C
0x18005443c  mov     rsi, [rcx+8]
0x180054440  cmp     byte ptr [rsi+28h], 0
0x180054444  jnz     short loc_18005444E
0x180054446  mov     rcx, rsi; this
0x180054449  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18005444e  mov     r14, [rbx+40h]
0x180054452  mov     rax, [rsi+18h]
0x180054456  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005445d  jnz     loc_1800544EC
0x180054463  and     qword ptr [rsp+68h+var_28], 0
0x180054469  xor     ebp, ebp
0x18005446b  cmp     [rdi], ebp
0x18005446d  jz      loc_1800545C0
0x180054473  lea     rsi, [rbx+20h]
0x180054477  movzx   edx, word ptr [r14]; char *
0x18005447b  lea     r14, [r14+2]
0x18005447f  mov     r9, [rbx+8]; struct _Mbstatet *
0x180054483  lea     r8, [rsp+68h+var_28]; char16_t
0x180054488  lea     rcx, [rsp+68h+var_30]; this
0x18005448d  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180054492  mov     r8, rax
0x180054495  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054499  jz      short loc_1800544E4
0x18005449b  lea     r10, [rbx+460h]
0x1800544a2  mov     rdx, [rbx+8]
0x1800544a6  mov     rax, [r10]
0x1800544a9  mov     ecx, [rax+14h]
0x1800544ac  nop
0x1800544ad  shr     ecx, 0Ch
0x1800544b0  test    cl, 1
0x1800544b3  jz      short loc_1800544C4
0x1800544b5  mov     rax, [r10]
0x1800544b8  cmp     qword ptr [rax+8], 0
0x1800544bd  jnz     short loc_1800544C4
0x1800544bf  add     [rsi], r8d
0x1800544c2  jmp     short loc_1800544D9
0x1800544c4  mov     [rsp+68h+var_48], rdx
0x1800544c9  mov     r9, rsi
0x1800544cc  lea     rdx, [rsp+68h+var_30]
0x1800544d1  mov     rcx, r10
0x1800544d4  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800544d9  inc     ebp
0x1800544db  cmp     ebp, [rdi]
0x1800544dd  jnz     short loc_180054477
0x1800544df  jmp     loc_1800545C0
0x1800544e4  or      dword ptr [rsi], 0FFFFFFFFh
0x1800544e7  jmp     loc_1800545C0
0x1800544ec  xor     esi, esi
0x1800544ee  cmp     [rdi], esi
0x1800544f0  jz      loc_1800545C0
0x1800544f6  and     [rsp+68h+var_30], 0
0x1800544fb  movzx   r9d, word ptr [r14]
0x1800544ff  lea     r14, [r14+2]
0x180054503  mov     rax, [rbx+8]
0x180054507  mov     [rsp+68h+var_48], rax
0x18005450c  mov     r8d, 6
0x180054512  lea     rdx, [rsp+68h+var_28]
0x180054517  lea     rcx, [rsp+68h+var_30]
0x18005451c  call    _wctomb_internal
0x180054521  test    eax, eax
0x180054523  jnz     short loc_180054576
0x180054525  mov     r8d, [rsp+68h+var_30]
0x18005452a  test    r8d, r8d
0x18005452d  jz      short loc_180054576
0x18005452f  lea     r10, [rbx+460h]
0x180054536  mov     rdx, [rbx+8]
0x18005453a  lea     r9, [rbx+20h]
0x18005453e  mov     rax, [r10]
0x180054541  mov     ecx, [rax+14h]
0x180054544  nop
0x180054545  shr     ecx, 0Ch
0x180054548  test    cl, 1
0x18005454b  jz      short loc_18005455C
0x18005454d  mov     rax, [r10]
0x180054550  cmp     qword ptr [rax+8], 0
0x180054555  jnz     short loc_18005455C
0x180054557  add     [r9], r8d
0x18005455a  jmp     short loc_18005456E
0x18005455c  mov     [rsp+68h+var_48], rdx
0x180054561  lea     rdx, [rsp+68h+var_28]
0x180054566  mov     rcx, r10
0x180054569  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x18005456e  inc     esi
0x180054570  cmp     esi, [rdi]
0x180054572  jnz     short loc_1800544F6
0x180054574  jmp     short loc_1800545C0
0x180054576  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005457a  jmp     short loc_1800545C0
0x18005457c  lea     r10, [rcx+460h]
0x180054583  mov     rdx, [rcx+8]
0x180054587  lea     r9, [rcx+20h]
0x18005458b  mov     r8d, [rdi]
0x18005458e  mov     r11, [rcx+40h]
0x180054592  mov     rax, [r10]
0x180054595  mov     ecx, [rax+14h]
0x180054598  nop
0x180054599  shr     ecx, 0Ch
0x18005459c  test    cl, 1
0x18005459f  jz      short loc_1800545B0
0x1800545a1  mov     rax, [r10]
0x1800545a4  cmp     qword ptr [rax+8], 0
0x1800545a9  jnz     short loc_1800545B0
0x1800545ab  add     [r9], r8d
0x1800545ae  jmp     short loc_1800545C0
0x1800545b0  mov     [rsp+68h+var_48], rdx
0x1800545b5  mov     rdx, r11
0x1800545b8  mov     rcx, r10
0x1800545bb  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800545c0  mov     al, 1
0x1800545c2  mov     rcx, [rsp+68h+var_20]
0x1800545c7  xor     rcx, rsp; StackCookie
0x1800545ca  call    __security_check_cookie
0x1800545cf  lea     r11, [rsp+68h+var_18]
0x1800545d4  mov     rbx, [r11+28h]
0x1800545d8  mov     rbp, [r11+30h]
0x1800545dc  mov     rsp, r11
0x1800545df  pop     r14
0x1800545e1  pop     rdi
0x1800545e2  pop     rsi
0x1800545e3  retn
```
