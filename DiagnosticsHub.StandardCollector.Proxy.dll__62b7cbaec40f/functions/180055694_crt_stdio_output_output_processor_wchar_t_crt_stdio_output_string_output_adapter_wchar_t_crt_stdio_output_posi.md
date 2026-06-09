# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x180055694`
- end: `0x1800558c5`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18001512c`
- `0x18001b8ec`
- `0x18001bc10`
- `0x180055694`
- `0x180055bf0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(
        __int64 a1)
{
  int *v2; // rdi
  __int64 v3; // rsi
  int v4; // esi
  __int64 v5; // rdx
  __int16 v6; // r8
  __int64 v7; // rcx
  __int16 v8; // dx
  __int64 v9; // rcx
  __int64 v10; // rsi
  wchar_t *v11; // r14
  int v12; // ebp
  int v13; // eax
  __int16 v14; // r9
  __int64 v15; // rdx
  int v17; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v18; // [rsp+80h] [rbp+18h] BYREF
  __int64 v19; // [rsp+88h] [rbp+20h] BYREF

  v2 = (int *)(a1 + 72);
  if ( *(_BYTE *)(a1 + 76) || *v2 <= 0 )
  {
    __crt_stdio_output::string_output_adapter<wchar_t>::write_string(
      a1 + 1120,
      *(_QWORD *)(a1 + 64),
      (unsigned int)*v2,
      a1 + 32,
      *(_QWORD *)(a1 + 8));
    return 1;
  }
  v3 = *(_QWORD *)(a1 + 8);
  if ( !*(_BYTE *)(v3 + 40) )
    __crt_cached_ptd_host::update_locale_slow(*(__crt_cached_ptd_host **)(a1 + 8));
  if ( *(_DWORD *)(*(_QWORD *)(v3 + 24) + 12LL) == 65001 )
  {
    v19 = *(_QWORD *)(a1 + 64);
    v18 = 0;
    v4 = 0;
    if ( *v2 )
    {
      while ( 1 )
      {
        v17 = 0;
        v5 = __crt_mbstring::__mbsrtowcs_utf8(
               (__crt_mbstring *)&v17,
               (wchar_t *)&v19,
               (const char **)2,
               (unsigned __int64)&v18,
               *(struct _Mbstatet **)(a1 + 8));
        if ( v5 == -1 )
          break;
        v6 = v17;
        v7 = *(_QWORD *)(a1 + 1120);
        if ( *(_QWORD *)(v7 + 16) == *(_QWORD *)(v7 + 8) )
        {
          if ( *(_BYTE *)(v7 + 24) )
            ++*(_DWORD *)(a1 + 32);
          else
            *(_DWORD *)(a1 + 32) = -1;
        }
        else
        {
          ++*(_DWORD *)(a1 + 32);
          ++*(_QWORD *)(v7 + 16);
          ***(_WORD ***)(a1 + 1120) = v6;
          **(_QWORD **)(a1 + 1120) += 2LL;
        }
        if ( v5 == 2 )
        {
          v8 = HIWORD(v17);
          v9 = *(_QWORD *)(a1 + 1120);
          if ( *(_QWORD *)(v9 + 16) == *(_QWORD *)(v9 + 8) )
          {
            if ( *(_BYTE *)(v9 + 24) )
              ++*(_DWORD *)(a1 + 32);
            else
              *(_DWORD *)(a1 + 32) = -1;
          }
          else
          {
            ++*(_DWORD *)(a1 + 32);
            ++*(_QWORD *)(v9 + 16);
            ***(_WORD ***)(a1 + 1120) = v8;
            **(_QWORD **)(a1 + 1120) += 2LL;
          }
          ++v4;
        }
        if ( ++v4 == *v2 )
          return 1;
      }
LABEL_22:
      *(_DWORD *)(a1 + 32) = -1;
    }
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 8);
    if ( !*(_BYTE *)(v10 + 40) )
      __crt_cached_ptd_host::update_locale_slow(*(__crt_cached_ptd_host **)(a1 + 8));
    v11 = *(wchar_t **)(a1 + 64);
    v12 = 0;
    if ( *v2 )
    {
      while ( 1 )
      {
        LOWORD(v17) = 0;
        v13 = mbtowc_internal(
                (__crt_mbstring *)&v17,
                v11,
                (char *)*(int *)(*(_QWORD *)(v10 + 24) + 8LL),
                *(__crt_cached_ptd_host **)(a1 + 8));
        if ( v13 <= 0 )
          break;
        v14 = v17;
        v15 = *(_QWORD *)(a1 + 1120);
        if ( *(_QWORD *)(v15 + 16) == *(_QWORD *)(v15 + 8) )
        {
          if ( *(_BYTE *)(v15 + 24) )
            ++*(_DWORD *)(a1 + 32);
          else
            *(_DWORD *)(a1 + 32) = -1;
        }
        else
        {
          ++*(_DWORD *)(a1 + 32);
          ++*(_QWORD *)(v15 + 16);
          ***(_WORD ***)(a1 + 1120) = v14;
          **(_QWORD **)(a1 + 1120) += 2LL;
        }
        v11 = (wchar_t *)((char *)v11 + v13);
        if ( ++v12 == *v2 )
          return 1;
      }
      goto LABEL_22;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180055694  push    rbp
0x180055696  push    rsi
0x180055697  push    rdi
0x180055698  push    r14
0x18005569a  push    r15
0x18005569c  sub     rsp, 40h
0x1800556a0  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800556a9  mov     [rsp+68h+arg_8], rbx
0x1800556ae  mov     rbx, rcx
0x1800556b1  lea     rdi, [rcx+48h]
0x1800556b5  xor     r15d, r15d
0x1800556b8  cmp     [rcx+4Ch], r15b
0x1800556bc  jnz     loc_180055892
0x1800556c2  cmp     [rdi], r15d
0x1800556c5  jle     loc_180055892
0x1800556cb  mov     rsi, [rcx+8]
0x1800556cf  cmp     [rsi+28h], r15b
0x1800556d3  jnz     short loc_1800556DD
0x1800556d5  mov     rcx, rsi; this
0x1800556d8  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800556dd  mov     rax, [rsi+18h]
0x1800556e1  cmp     dword ptr [rax+0Ch], 0FDE9h
0x1800556e8  jnz     loc_1800557F7
0x1800556ee  mov     rax, [rbx+40h]
0x1800556f2  mov     [rsp+68h+arg_18], rax
0x1800556fa  mov     [rsp+68h+arg_10], r15
0x180055702  mov     esi, r15d
0x180055705  cmp     [rdi], r15d
0x180055708  jz      loc_1800558B2
0x18005570e  mov     [rsp+68h+arg_0], r15d
0x180055713  mov     rax, [rbx+8]
0x180055717  mov     [rsp+68h+var_48], rax; struct _Mbstatet *
0x18005571c  lea     r9, [rsp+68h+arg_10]; unsigned __int64
0x180055724  mov     r8d, 2; char **
0x18005572a  lea     rdx, [rsp+68h+arg_18]; wchar_t *
0x180055732  lea     rcx, [rsp+68h+arg_0]; this
0x180055737  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18005573c  mov     rdx, rax
0x18005573f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055743  jz      loc_1800557EE
0x180055749  movzx   r8d, word ptr [rsp+68h+arg_0]
0x18005574f  mov     rcx, [rbx+460h]
0x180055756  mov     rax, [rcx+8]
0x18005575a  cmp     [rcx+10h], rax
0x18005575e  jnz     short loc_180055771
0x180055760  cmp     [rcx+18h], r15b
0x180055764  jz      short loc_18005576B
0x180055766  inc     dword ptr [rbx+20h]
0x180055769  jmp     short loc_180055791
0x18005576b  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005576f  jmp     short loc_180055791
0x180055771  inc     dword ptr [rbx+20h]
0x180055774  inc     qword ptr [rcx+10h]
0x180055778  mov     rax, [rbx+460h]
0x18005577f  mov     rcx, [rax]
0x180055782  mov     [rcx], r8w
0x180055786  mov     rax, [rbx+460h]
0x18005578d  add     qword ptr [rax], 2
0x180055791  cmp     rdx, 2
0x180055795  jnz     short loc_1800557DF
0x180055797  movzx   edx, word ptr [rsp+68h+arg_0+2]
0x18005579c  mov     rcx, [rbx+460h]
0x1800557a3  mov     rax, [rcx+8]
0x1800557a7  cmp     [rcx+10h], rax
0x1800557ab  jnz     short loc_1800557BE
0x1800557ad  cmp     [rcx+18h], r15b
0x1800557b1  jz      short loc_1800557B8
0x1800557b3  inc     dword ptr [rbx+20h]
0x1800557b6  jmp     short loc_1800557DD
0x1800557b8  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800557bc  jmp     short loc_1800557DD
0x1800557be  inc     dword ptr [rbx+20h]
0x1800557c1  inc     qword ptr [rcx+10h]
0x1800557c5  mov     rax, [rbx+460h]
0x1800557cc  mov     rcx, [rax]
0x1800557cf  mov     [rcx], dx
0x1800557d2  mov     rax, [rbx+460h]
0x1800557d9  add     qword ptr [rax], 2
0x1800557dd  inc     esi
0x1800557df  inc     esi
0x1800557e1  cmp     esi, [rdi]
0x1800557e3  jnz     loc_18005570E
0x1800557e9  jmp     loc_1800558B2
0x1800557ee  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800557f2  jmp     loc_1800558B2
0x1800557f7  mov     rsi, [rbx+8]
0x1800557fb  cmp     [rsi+28h], r15b
0x1800557ff  jnz     short loc_180055809
0x180055801  mov     rcx, rsi; this
0x180055804  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180055809  mov     r14, [rbx+40h]
0x18005580d  mov     ebp, r15d
0x180055810  cmp     [rdi], r15d
0x180055813  jz      loc_1800558B2
0x180055819  mov     word ptr [rsp+68h+arg_0], r15w
0x18005581f  mov     rax, [rsi+18h]
0x180055823  movsxd  r8, dword ptr [rax+8]; char *
0x180055827  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x18005582b  mov     rdx, r14; wchar_t *
0x18005582e  lea     rcx, [rsp+68h+arg_0]; this
0x180055833  call    _mbtowc_internal
0x180055838  movsxd  r8, eax
0x18005583b  test    eax, eax
0x18005583d  jle     short loc_1800557EE
0x18005583f  movzx   r9d, word ptr [rsp+68h+arg_0]
0x180055845  mov     rdx, [rbx+460h]
0x18005584c  mov     rcx, [rdx+8]
0x180055850  cmp     [rdx+10h], rcx
0x180055854  jnz     short loc_180055867
0x180055856  cmp     [rdx+18h], r15b
0x18005585a  jz      short loc_180055861
0x18005585c  inc     dword ptr [rbx+20h]
0x18005585f  jmp     short loc_180055887
0x180055861  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055865  jmp     short loc_180055887
0x180055867  inc     dword ptr [rbx+20h]
0x18005586a  inc     qword ptr [rdx+10h]
0x18005586e  mov     rax, [rbx+460h]
0x180055875  mov     rcx, [rax]
0x180055878  mov     [rcx], r9w
0x18005587c  mov     rax, [rbx+460h]
0x180055883  add     qword ptr [rax], 2
0x180055887  add     r14, r8
0x18005588a  inc     ebp
0x18005588c  cmp     ebp, [rdi]
0x18005588e  jnz     short loc_180055819
0x180055890  jmp     short loc_1800558B2
0x180055892  add     rcx, 460h
0x180055899  lea     r9, [rbx+20h]
0x18005589d  mov     rax, [rbx+8]
0x1800558a1  mov     [rsp+68h+var_48], rax
0x1800558a6  mov     r8d, [rdi]
0x1800558a9  mov     rdx, [rbx+40h]
0x1800558ad  call    ?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x1800558b2  mov     al, 1
0x1800558b4  mov     rbx, [rsp+68h+arg_8]
0x1800558b9  add     rsp, 40h
0x1800558bd  pop     r15
0x1800558bf  pop     r14
0x1800558c1  pop     rdi
0x1800558c2  pop     rsi
0x1800558c3  pop     rbp
0x1800558c4  retn
```
