# __crt_stdio_output::output_processor<char,__crt_stdio_output::stream_output_adapter<char>,__crt_stdio_output::standard_base<char,__crt_stdio_output::stream_output_adapter<char>>>::write_stored_string_tchar(char)

- ea: `0x1800545e4`
- end: `0x1800547d0`
- name: `?write_stored_string_tchar@?$output_processor@DV?$stream_output_adapter@D@__crt_stdio_output@@V?$standard_base@DV?$stream_output_adapter@D@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_ND@Z`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002810`
- `0x18001512c`
- `0x1800545e4`
- `0x180055c98`
- `0x1800580ec`
- `0x1800585a0`

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
0x1800545e4  mov     rax, rsp
0x1800545e7  push    rsi
0x1800545e8  push    rdi
0x1800545e9  push    r14
0x1800545eb  sub     rsp, 50h
0x1800545ef  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800545f7  mov     [rax+10h], rbx
0x1800545fb  mov     [rax+18h], rbp
0x1800545ff  mov     rax, cs:__security_cookie
0x180054606  xor     rax, rsp
0x180054609  mov     [rsp+68h+var_20], rax
0x18005460e  mov     rbx, rcx
0x180054611  lea     rdi, [rcx+48h]
0x180054615  cmp     byte ptr [rcx+4Ch], 0
0x180054619  jz      loc_180054768
0x18005461f  cmp     dword ptr [rdi], 0
0x180054622  jle     loc_180054768
0x180054628  mov     rsi, [rcx+8]
0x18005462c  cmp     byte ptr [rsi+28h], 0
0x180054630  jnz     short loc_18005463A
0x180054632  mov     rcx, rsi; this
0x180054635  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18005463a  mov     r14, [rbx+40h]
0x18005463e  mov     rax, [rsi+18h]
0x180054642  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054649  jnz     loc_1800546D8
0x18005464f  and     qword ptr [rsp+68h+var_28], 0
0x180054655  xor     ebp, ebp
0x180054657  cmp     [rdi], ebp
0x180054659  jz      loc_1800547AC
0x18005465f  lea     rsi, [rbx+20h]
0x180054663  movzx   edx, word ptr [r14]; char *
0x180054667  lea     r14, [r14+2]
0x18005466b  mov     r9, [rbx+8]; struct _Mbstatet *
0x18005466f  lea     r8, [rsp+68h+var_28]; char16_t
0x180054674  lea     rcx, [rsp+68h+var_30]; this
0x180054679  call    ?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)
0x18005467e  mov     r8, rax
0x180054681  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054685  jz      short loc_1800546D0
0x180054687  lea     r10, [rbx+460h]
0x18005468e  mov     rdx, [rbx+8]
0x180054692  mov     rax, [r10]
0x180054695  mov     ecx, [rax+14h]
0x180054698  nop
0x180054699  shr     ecx, 0Ch
0x18005469c  test    cl, 1
0x18005469f  jz      short loc_1800546B0
0x1800546a1  mov     rax, [r10]
0x1800546a4  cmp     qword ptr [rax+8], 0
0x1800546a9  jnz     short loc_1800546B0
0x1800546ab  add     [rsi], r8d
0x1800546ae  jmp     short loc_1800546C5
0x1800546b0  mov     [rsp+68h+var_48], rdx
0x1800546b5  mov     r9, rsi
0x1800546b8  lea     rdx, [rsp+68h+var_30]
0x1800546bd  mov     rcx, r10
0x1800546c0  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800546c5  inc     ebp
0x1800546c7  cmp     ebp, [rdi]
0x1800546c9  jnz     short loc_180054663
0x1800546cb  jmp     loc_1800547AC
0x1800546d0  or      dword ptr [rsi], 0FFFFFFFFh
0x1800546d3  jmp     loc_1800547AC
0x1800546d8  xor     esi, esi
0x1800546da  cmp     [rdi], esi
0x1800546dc  jz      loc_1800547AC
0x1800546e2  and     [rsp+68h+var_30], 0
0x1800546e7  movzx   r9d, word ptr [r14]
0x1800546eb  lea     r14, [r14+2]
0x1800546ef  mov     rax, [rbx+8]
0x1800546f3  mov     [rsp+68h+var_48], rax
0x1800546f8  mov     r8d, 6
0x1800546fe  lea     rdx, [rsp+68h+var_28]
0x180054703  lea     rcx, [rsp+68h+var_30]
0x180054708  call    _wctomb_internal
0x18005470d  test    eax, eax
0x18005470f  jnz     short loc_180054762
0x180054711  mov     r8d, [rsp+68h+var_30]
0x180054716  test    r8d, r8d
0x180054719  jz      short loc_180054762
0x18005471b  lea     r10, [rbx+460h]
0x180054722  mov     rdx, [rbx+8]
0x180054726  lea     r9, [rbx+20h]
0x18005472a  mov     rax, [r10]
0x18005472d  mov     ecx, [rax+14h]
0x180054730  nop
0x180054731  shr     ecx, 0Ch
0x180054734  test    cl, 1
0x180054737  jz      short loc_180054748
0x180054739  mov     rax, [r10]
0x18005473c  cmp     qword ptr [rax+8], 0
0x180054741  jnz     short loc_180054748
0x180054743  add     [r9], r8d
0x180054746  jmp     short loc_18005475A
0x180054748  mov     [rsp+68h+var_48], rdx
0x18005474d  lea     rdx, [rsp+68h+var_28]
0x180054752  mov     rcx, r10
0x180054755  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x18005475a  inc     esi
0x18005475c  cmp     esi, [rdi]
0x18005475e  jnz     short loc_1800546E2
0x180054760  jmp     short loc_1800547AC
0x180054762  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054766  jmp     short loc_1800547AC
0x180054768  lea     r10, [rcx+460h]
0x18005476f  mov     rdx, [rcx+8]
0x180054773  lea     r9, [rcx+20h]
0x180054777  mov     r8d, [rdi]
0x18005477a  mov     r11, [rcx+40h]
0x18005477e  mov     rax, [r10]
0x180054781  mov     ecx, [rax+14h]
0x180054784  nop
0x180054785  shr     ecx, 0Ch
0x180054788  test    cl, 1
0x18005478b  jz      short loc_18005479C
0x18005478d  mov     rax, [r10]
0x180054790  cmp     qword ptr [rax+8], 0
0x180054795  jnz     short loc_18005479C
0x180054797  add     [r9], r8d
0x18005479a  jmp     short loc_1800547AC
0x18005479c  mov     [rsp+68h+var_48], rdx
0x1800547a1  mov     rdx, r11
0x1800547a4  mov     rcx, r10
0x1800547a7  call    ?write_string_impl@?$output_adapter_common@DV?$stream_output_adapter@D@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEBDHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<char,__crt_stdio_output::stream_output_adapter<char>>::write_string_impl(char const * const,int,int * const,__crt_cached_ptd_host &)
0x1800547ac  mov     al, 1
0x1800547ae  mov     rcx, [rsp+68h+var_20]
0x1800547b3  xor     rcx, rsp; StackCookie
0x1800547b6  call    __security_check_cookie
0x1800547bb  lea     r11, [rsp+68h+var_18]
0x1800547c0  mov     rbx, [r11+28h]
0x1800547c4  mov     rbp, [r11+30h]
0x1800547c8  mov     rsp, r11
0x1800547cb  pop     r14
0x1800547cd  pop     rdi
0x1800547ce  pop     rsi
0x1800547cf  retn
```
