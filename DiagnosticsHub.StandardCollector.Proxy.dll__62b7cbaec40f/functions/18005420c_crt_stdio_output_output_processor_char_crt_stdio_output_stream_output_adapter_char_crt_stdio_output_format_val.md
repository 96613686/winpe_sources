# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::format_validation_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x18005420c`
- end: `0x1800543f8`
- name: `?write_stored_string_tchar@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$format_validation_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002810`
- `0x18001512c`
- `0x18005420c`
- `0x180055c98`
- `0x1800580ec`
- `0x1800585a0`

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
0x18005420c  mov     rax, rsp
0x18005420f  push    rsi
0x180054210  push    rdi
0x180054211  push    r14
0x180054213  sub     rsp, 50h
0x180054217  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18005421f  mov     [rax+10h], rbx
0x180054223  mov     [rax+18h], rbp
0x180054227  mov     rax, cs:__security_cookie
0x18005422e  xor     rax, rsp
0x180054231  mov     [rsp+68h+var_20], rax
0x180054236  mov     rbx, rcx
0x180054239  lea     rdi, [rcx+48h]
0x18005423d  cmp     byte ptr [rcx+4Ch], 0
0x180054241  jz      loc_180054390
0x180054247  cmp     dword ptr [rdi], 0
0x18005424a  jle     loc_180054390
0x180054250  mov     rsi, [rcx+8]
0x180054254  cmp     byte ptr [rsi+28h], 0
0x180054258  jnz     short loc_180054262
0x18005425a  mov     rcx, rsi; this
0x18005425d  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054262  mov     r14, [rbx+40h]
0x180054266  mov     rax, [rsi+18h]
0x18005426a  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054271  jnz     loc_180054300
0x180054277  and     qword ptr [rsp+68h+var_28], 0
0x18005427d  xor     ebp, ebp
0x18005427f  cmp     [rdi], ebp
0x180054281  jz      loc_1800543D4
0x180054287  lea     rsi, [rbx+20h]
0x18005428b  movzx   edx, word ptr [r14]; char *
0x18005428f  lea     r14, [r14+2]
0x180054293  mov     r9, [rbx+8]; struct _Mbstatet *
0x180054297  lea     r8, [rsp+68h+var_28]; char16_t
0x18005429c  lea     rcx, [rsp+68h+var_30]; this
0x1800542a1  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x1800542a6  mov     r8, rax
0x1800542a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800542ad  jz      short loc_1800542F8
0x1800542af  lea     r10, [rbx+460h]
0x1800542b6  mov     rdx, [rbx+8]
0x1800542ba  mov     rax, [r10]
0x1800542bd  mov     ecx, [rax+14h]
0x1800542c0  nop
0x1800542c1  shr     ecx, 0Ch
0x1800542c4  test    cl, 1
0x1800542c7  jz      short loc_1800542D8
0x1800542c9  mov     rax, [r10]
0x1800542cc  cmp     qword ptr [rax+8], 0
0x1800542d1  jnz     short loc_1800542D8
0x1800542d3  add     [rsi], r8d
0x1800542d6  jmp     short loc_1800542ED
0x1800542d8  mov     [rsp+68h+var_48], rdx
0x1800542dd  mov     r9, rsi
0x1800542e0  lea     rdx, [rsp+68h+var_30]
0x1800542e5  mov     rcx, r10
0x1800542e8  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800542ed  inc     ebp
0x1800542ef  cmp     ebp, [rdi]
0x1800542f1  jnz     short loc_18005428B
0x1800542f3  jmp     loc_1800543D4
0x1800542f8  or      dword ptr [rsi], 0FFFFFFFFh
0x1800542fb  jmp     loc_1800543D4
0x180054300  xor     esi, esi
0x180054302  cmp     [rdi], esi
0x180054304  jz      loc_1800543D4
0x18005430a  and     [rsp+68h+var_30], 0
0x18005430f  movzx   r9d, word ptr [r14]
0x180054313  lea     r14, [r14+2]
0x180054317  mov     rax, [rbx+8]
0x18005431b  mov     [rsp+68h+var_48], rax
0x180054320  mov     r8d, 6
0x180054326  lea     rdx, [rsp+68h+var_28]
0x18005432b  lea     rcx, [rsp+68h+var_30]
0x180054330  call    _wctomb_internal
0x180054335  test    eax, eax
0x180054337  jnz     short loc_18005438A
0x180054339  mov     r8d, [rsp+68h+var_30]
0x18005433e  test    r8d, r8d
0x180054341  jz      short loc_18005438A
0x180054343  lea     r10, [rbx+460h]
0x18005434a  mov     rdx, [rbx+8]
0x18005434e  lea     r9, [rbx+20h]
0x180054352  mov     rax, [r10]
0x180054355  mov     ecx, [rax+14h]
0x180054358  nop
0x180054359  shr     ecx, 0Ch
0x18005435c  test    cl, 1
0x18005435f  jz      short loc_180054370
0x180054361  mov     rax, [r10]
0x180054364  cmp     qword ptr [rax+8], 0
0x180054369  jnz     short loc_180054370
0x18005436b  add     [r9], r8d
0x18005436e  jmp     short loc_180054382
0x180054370  mov     [rsp+68h+var_48], rdx
0x180054375  lea     rdx, [rsp+68h+var_28]
0x18005437a  mov     rcx, r10
0x18005437d  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x180054382  inc     esi
0x180054384  cmp     esi, [rdi]
0x180054386  jnz     short loc_18005430A
0x180054388  jmp     short loc_1800543D4
0x18005438a  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005438e  jmp     short loc_1800543D4
0x180054390  lea     r10, [rcx+460h]
0x180054397  mov     rdx, [rcx+8]
0x18005439b  lea     r9, [rcx+20h]
0x18005439f  mov     r8d, [rdi]
0x1800543a2  mov     r11, [rcx+40h]
0x1800543a6  mov     rax, [r10]
0x1800543a9  mov     ecx, [rax+14h]
0x1800543ac  nop
0x1800543ad  shr     ecx, 0Ch
0x1800543b0  test    cl, 1
0x1800543b3  jz      short loc_1800543C4
0x1800543b5  mov     rax, [r10]
0x1800543b8  cmp     qword ptr [rax+8], 0
0x1800543bd  jnz     short loc_1800543C4
0x1800543bf  add     [r9], r8d
0x1800543c2  jmp     short loc_1800543D4
0x1800543c4  mov     [rsp+68h+var_48], rdx
0x1800543c9  mov     rdx, r11
0x1800543cc  mov     rcx, r10
0x1800543cf  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800543d4  mov     al, 1
0x1800543d6  mov     rcx, [rsp+68h+var_20]
0x1800543db  xor     rcx, rsp; StackCookie
0x1800543de  call    __security_check_cookie
0x1800543e3  lea     r11, [rsp+68h+var_18]
0x1800543e8  mov     rbx, [r11+28h]
0x1800543ec  mov     rbp, [r11+30h]
0x1800543f0  mov     rsp, r11
0x1800543f3  pop     r14
0x1800543f5  pop     rdi
0x1800543f6  pop     rsi
0x1800543f7  retn
```
