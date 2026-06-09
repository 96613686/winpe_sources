# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x1800555e8`
- end: `0x180055819`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800149cc`
- `0x18001b18c`
- `0x18001b4b0`
- `0x1800555e8`
- `0x180055910`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(
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
0x1800555e8  push    rbp
0x1800555ea  push    rsi
0x1800555eb  push    rdi
0x1800555ec  push    r14
0x1800555ee  push    r15
0x1800555f0  sub     rsp, 40h
0x1800555f4  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800555fd  mov     [rsp+68h+arg_8], rbx
0x180055602  mov     rbx, rcx
0x180055605  lea     rdi, [rcx+48h]
0x180055609  xor     r15d, r15d
0x18005560c  cmp     [rcx+4Ch], r15b
0x180055610  jnz     loc_1800557E6
0x180055616  cmp     [rdi], r15d
0x180055619  jle     loc_1800557E6
0x18005561f  mov     rsi, [rcx+8]
0x180055623  cmp     [rsi+28h], r15b
0x180055627  jnz     short loc_180055631
0x180055629  mov     rcx, rsi; this
0x18005562c  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180055631  mov     rax, [rsi+18h]
0x180055635  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005563c  jnz     loc_18005574B
0x180055642  mov     rax, [rbx+40h]
0x180055646  mov     [rsp+68h+arg_18], rax
0x18005564e  mov     [rsp+68h+arg_10], r15
0x180055656  mov     esi, r15d
0x180055659  cmp     [rdi], r15d
0x18005565c  jz      loc_180055806
0x180055662  mov     [rsp+68h+arg_0], r15d
0x180055667  mov     rax, [rbx+8]
0x18005566b  mov     [rsp+68h+var_48], rax; struct _Mbstatet *
0x180055670  lea     r9, [rsp+68h+arg_10]; unsigned __int64
0x180055678  mov     r8d, 2; char **
0x18005567e  lea     rdx, [rsp+68h+arg_18]; wchar_t *
0x180055686  lea     rcx, [rsp+68h+arg_0]; this
0x18005568b  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180055690  mov     rdx, rax
0x180055693  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055697  jz      loc_180055742
0x18005569d  movzx   r8d, word ptr [rsp+68h+arg_0]
0x1800556a3  mov     rcx, [rbx+460h]
0x1800556aa  mov     rax, [rcx+8]
0x1800556ae  cmp     [rcx+10h], rax
0x1800556b2  jnz     short loc_1800556C5
0x1800556b4  cmp     [rcx+18h], r15b
0x1800556b8  jz      short loc_1800556BF
0x1800556ba  inc     dword ptr [rbx+20h]
0x1800556bd  jmp     short loc_1800556E5
0x1800556bf  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800556c3  jmp     short loc_1800556E5
0x1800556c5  inc     dword ptr [rbx+20h]
0x1800556c8  inc     qword ptr [rcx+10h]
0x1800556cc  mov     rax, [rbx+460h]
0x1800556d3  mov     rcx, [rax]
0x1800556d6  mov     [rcx], r8w
0x1800556da  mov     rax, [rbx+460h]
0x1800556e1  add     qword ptr [rax], 2
0x1800556e5  cmp     rdx, 2
0x1800556e9  jnz     short loc_180055733
0x1800556eb  movzx   edx, word ptr [rsp+68h+arg_0+2]
0x1800556f0  mov     rcx, [rbx+460h]
0x1800556f7  mov     rax, [rcx+8]
0x1800556fb  cmp     [rcx+10h], rax
0x1800556ff  jnz     short loc_180055712
0x180055701  cmp     [rcx+18h], r15b
0x180055705  jz      short loc_18005570C
0x180055707  inc     dword ptr [rbx+20h]
0x18005570a  jmp     short loc_180055731
0x18005570c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055710  jmp     short loc_180055731
0x180055712  inc     dword ptr [rbx+20h]
0x180055715  inc     qword ptr [rcx+10h]
0x180055719  mov     rax, [rbx+460h]
0x180055720  mov     rcx, [rax]
0x180055723  mov     [rcx], dx
0x180055726  mov     rax, [rbx+460h]
0x18005572d  add     qword ptr [rax], 2
0x180055731  inc     esi
0x180055733  inc     esi
0x180055735  cmp     esi, [rdi]
0x180055737  jnz     loc_180055662
0x18005573d  jmp     loc_180055806
0x180055742  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055746  jmp     loc_180055806
0x18005574b  mov     rsi, [rbx+8]
0x18005574f  cmp     [rsi+28h], r15b
0x180055753  jnz     short loc_18005575D
0x180055755  mov     rcx, rsi; this
0x180055758  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18005575d  mov     r14, [rbx+40h]
0x180055761  mov     ebp, r15d
0x180055764  cmp     [rdi], r15d
0x180055767  jz      loc_180055806
0x18005576d  mov     word ptr [rsp+68h+arg_0], r15w
0x180055773  mov     rax, [rsi+18h]
0x180055777  movsxd  r8, dword ptr [rax+8]; char *
0x18005577b  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x18005577f  mov     rdx, r14; wchar_t *
0x180055782  lea     rcx, [rsp+68h+arg_0]; this
0x180055787  call    _mbtowc_internal
0x18005578c  movsxd  r8, eax
0x18005578f  test    eax, eax
0x180055791  jle     short loc_180055742
0x180055793  movzx   r9d, word ptr [rsp+68h+arg_0]
0x180055799  mov     rdx, [rbx+460h]
0x1800557a0  mov     rcx, [rdx+8]
0x1800557a4  cmp     [rdx+10h], rcx
0x1800557a8  jnz     short loc_1800557BB
0x1800557aa  cmp     [rdx+18h], r15b
0x1800557ae  jz      short loc_1800557B5
0x1800557b0  inc     dword ptr [rbx+20h]
0x1800557b3  jmp     short loc_1800557DB
0x1800557b5  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800557b9  jmp     short loc_1800557DB
0x1800557bb  inc     dword ptr [rbx+20h]
0x1800557be  inc     qword ptr [rdx+10h]
0x1800557c2  mov     rax, [rbx+460h]
0x1800557c9  mov     rcx, [rax]
0x1800557cc  mov     [rcx], r9w
0x1800557d0  mov     rax, [rbx+460h]
0x1800557d7  add     qword ptr [rax], 2
0x1800557db  add     r14, r8
0x1800557de  inc     ebp
0x1800557e0  cmp     ebp, [rdi]
0x1800557e2  jnz     short loc_18005576D
0x1800557e4  jmp     short loc_180055806
0x1800557e6  add     rcx, 460h
0x1800557ed  lea     r9, [rbx+20h]
0x1800557f1  mov     rax, [rbx+8]
0x1800557f5  mov     [rsp+68h+var_48], rax
0x1800557fa  mov     r8d, [rdi]
0x1800557fd  mov     rdx, [rbx+40h]
0x180055801  call    ?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x180055806  mov     al, 1
0x180055808  mov     rbx, [rsp+68h+arg_8]
0x18005580d  add     rsp, 40h
0x180055811  pop     r15
0x180055813  pop     r14
0x180055815  pop     rdi
0x180055816  pop     rsi
0x180055817  pop     rbp
0x180055818  retn
```
