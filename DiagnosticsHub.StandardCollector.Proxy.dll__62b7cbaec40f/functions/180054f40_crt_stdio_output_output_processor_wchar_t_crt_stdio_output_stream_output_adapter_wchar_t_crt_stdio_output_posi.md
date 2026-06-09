# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x180054f40`
- end: `0x1800551cd`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001512c`
- `0x18001b8ec`
- `0x18001bc10`
- `0x180054f40`
- `0x180055d68`
- `0x1800588a8`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(
        __int64 a1)
{
  int *v2; // rdi
  __int64 v3; // rsi
  int *v4; // rbp
  int v5; // esi
  __int64 v6; // rbp
  __int64 v7; // rsi
  int *v8; // r15
  wchar_t *v9; // r14
  int v10; // ebp
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // r10
  _DWORD *v14; // r9
  int v15; // r8d
  int v17; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int64 v18; // [rsp+90h] [rbp+18h] BYREF
  __int64 v19; // [rsp+98h] [rbp+20h] BYREF

  v2 = (int *)(a1 + 72);
  if ( *(_BYTE *)(a1 + 76) || *v2 <= 0 )
  {
    v13 = a1 + 1120;
    v14 = (_DWORD *)(a1 + 32);
    v15 = *v2;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)v13 + 8LL) )
      __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(
        v13,
        *(_QWORD *)(a1 + 64),
        v15,
        (_DWORD)v14,
        *(_QWORD *)(a1 + 8));
    else
      *v14 += v15;
  }
  else
  {
    v3 = *(_QWORD *)(a1 + 8);
    v4 = (int *)(a1 + 72);
    if ( !*(_BYTE *)(v3 + 40) )
    {
      __crt_cached_ptd_host::update_locale_slow(*(__crt_cached_ptd_host **)(a1 + 8));
      v4 = (int *)(a1 + 72);
    }
    if ( *(_DWORD *)(*(_QWORD *)(v3 + 24) + 12LL) == 65001 )
    {
      v19 = *(_QWORD *)(a1 + 64);
      v18 = 0;
      v5 = 0;
      if ( *v2 )
      {
        while ( 1 )
        {
          v17 = 0;
          v6 = __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v17,
                 (wchar_t *)&v19,
                 (const char **)2,
                 (unsigned __int64)&v18,
                 *(struct _Mbstatet **)(a1 + 8));
          if ( v6 == -1 )
            break;
          if ( ((*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 1120) + 8LL))
            && (unsigned __int16)fputwc_nolock_internal(
                                   (unsigned __int16)v17,
                                   *(_QWORD *)(a1 + 1120),
                                   *(_QWORD *)(a1 + 8)) == 0xFFFF )
          {
            *(_DWORD *)(a1 + 32) = -1;
          }
          else
          {
            ++*(_DWORD *)(a1 + 32);
          }
          if ( v6 == 2 )
          {
            if ( ((*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 1120) + 8LL))
              && (unsigned __int16)fputwc_nolock_internal(HIWORD(v17), *(_QWORD *)(a1 + 1120), *(_QWORD *)(a1 + 8)) == 0xFFFF )
            {
              *(_DWORD *)(a1 + 32) = -1;
            }
            else
            {
              ++*(_DWORD *)(a1 + 32);
            }
            ++v5;
          }
          if ( ++v5 == *v2 )
            return 1;
        }
LABEL_22:
        *(_DWORD *)(a1 + 32) = -1;
      }
    }
    else
    {
      v7 = *(_QWORD *)(a1 + 8);
      v8 = v2;
      if ( !*(_BYTE *)(v7 + 40) )
      {
        __crt_cached_ptd_host::update_locale_slow(*(__crt_cached_ptd_host **)(a1 + 8));
        v8 = v4;
      }
      v9 = *(wchar_t **)(a1 + 64);
      v10 = 0;
      if ( *v2 )
      {
        while ( 1 )
        {
          LOWORD(v17) = 0;
          v11 = mbtowc_internal(
                  (__crt_mbstring *)&v17,
                  v9,
                  (char *)*(int *)(*(_QWORD *)(v7 + 24) + 8LL),
                  *(__crt_cached_ptd_host **)(a1 + 8));
          v12 = v11;
          if ( v11 <= 0 )
            break;
          if ( ((*(_DWORD *)(*(_QWORD *)(a1 + 1120) + 20LL) & 0x1000) == 0 || *(_QWORD *)(*(_QWORD *)(a1 + 1120) + 8LL))
            && (unsigned __int16)fputwc_nolock_internal(
                                   (unsigned __int16)v17,
                                   *(_QWORD *)(a1 + 1120),
                                   *(_QWORD *)(a1 + 8)) == 0xFFFF )
          {
            *(_DWORD *)(a1 + 32) = -1;
          }
          else
          {
            ++*(_DWORD *)(a1 + 32);
          }
          v9 = (wchar_t *)((char *)v9 + v12);
          if ( ++v10 == *v8 )
            return 1;
        }
        goto LABEL_22;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180054f40  mov     rax, rsp
0x180054f43  push    rbp
0x180054f44  push    rsi
0x180054f45  push    rdi
0x180054f46  push    r12
0x180054f48  push    r13
0x180054f4a  push    r14
0x180054f4c  push    r15
0x180054f4e  sub     rsp, 40h
0x180054f52  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054f5a  mov     [rax+10h], rbx
0x180054f5e  mov     rbx, rcx
0x180054f61  lea     rdi, [rcx+48h]
0x180054f65  xor     r13d, r13d
0x180054f68  cmp     [rcx+4Ch], r13b
0x180054f6c  jnz     loc_180055170
0x180054f72  cmp     [rdi], r13d
0x180054f75  jle     loc_180055170
0x180054f7b  mov     rsi, [rcx+8]
0x180054f7f  mov     rbp, rdi
0x180054f82  cmp     [rsi+28h], r13b
0x180054f86  jnz     short loc_180054F94
0x180054f88  mov     rcx, rsi; this
0x180054f8b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054f90  lea     rbp, [rbx+48h]
0x180054f94  mov     rax, [rsi+18h]
0x180054f98  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054f9f  jnz     loc_1800550BA
0x180054fa5  mov     rax, [rbx+40h]
0x180054fa9  mov     [rsp+78h+arg_18], rax
0x180054fb1  mov     [rsp+78h+arg_10], r13
0x180054fb9  mov     esi, r13d
0x180054fbc  cmp     [rdi], r13d
0x180054fbf  jz      loc_1800551B3
0x180054fc5  mov     r12d, 0FFFFh
0x180054fcb  mov     [rsp+78h+arg_0], r13d
0x180054fd3  mov     rax, [rbx+8]
0x180054fd7  mov     [rsp+78h+var_58], rax; struct _Mbstatet *
0x180054fdc  lea     r9, [rsp+78h+arg_10]; unsigned __int64
0x180054fe4  mov     r8d, 2; char **
0x180054fea  lea     rdx, [rsp+78h+arg_18]; wchar_t *
0x180054ff2  lea     rcx, [rsp+78h+arg_0]; this
0x180054ffa  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180054fff  mov     rbp, rax
0x180055002  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055006  jz      loc_1800550B1
0x18005500c  mov     r8, [rbx+8]
0x180055010  movzx   ecx, word ptr [rsp+78h+arg_0]
0x180055018  mov     rax, [rbx+460h]
0x18005501f  mov     edx, [rax+14h]
0x180055022  nop
0x180055023  shr     edx, 0Ch
0x180055026  test    dl, 1
0x180055029  jz      short loc_180055038
0x18005502b  mov     rax, [rbx+460h]
0x180055032  cmp     [rax+8], r13
0x180055036  jz      short loc_18005504A
0x180055038  mov     rdx, [rbx+460h]
0x18005503f  call    _fputwc_nolock_internal
0x180055044  cmp     ax, r12w
0x180055048  jz      short loc_18005504F
0x18005504a  inc     dword ptr [rbx+20h]
0x18005504d  jmp     short loc_180055053
0x18005504f  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055053  cmp     rbp, 2
0x180055057  jnz     short loc_1800550A2
0x180055059  mov     r8, [rbx+8]
0x18005505d  movzx   ecx, word ptr [rsp+78h+arg_0+2]
0x180055065  mov     rax, [rbx+460h]
0x18005506c  mov     edx, [rax+14h]
0x18005506f  nop
0x180055070  shr     edx, 0Ch
0x180055073  test    dl, 1
0x180055076  jz      short loc_180055085
0x180055078  mov     rax, [rbx+460h]
0x18005507f  cmp     [rax+8], r13
0x180055083  jz      short loc_180055097
0x180055085  mov     rdx, [rbx+460h]
0x18005508c  call    _fputwc_nolock_internal
0x180055091  cmp     ax, r12w
0x180055095  jz      short loc_18005509C
0x180055097  inc     dword ptr [rbx+20h]
0x18005509a  jmp     short loc_1800550A0
0x18005509c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800550a0  inc     esi
0x1800550a2  inc     esi
0x1800550a4  cmp     esi, [rdi]
0x1800550a6  jnz     loc_180054FCB
0x1800550ac  jmp     loc_1800551B3
0x1800550b1  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800550b5  jmp     loc_1800551B3
0x1800550ba  mov     rsi, [rbx+8]
0x1800550be  mov     r15, rdi
0x1800550c1  cmp     [rsi+28h], r13b
0x1800550c5  jnz     short loc_1800550D2
0x1800550c7  mov     rcx, rsi; this
0x1800550ca  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800550cf  mov     r15, rbp
0x1800550d2  mov     r14, [rbx+40h]
0x1800550d6  mov     ebp, r13d
0x1800550d9  cmp     [rdi], r13d
0x1800550dc  jz      loc_1800551B3
0x1800550e2  mov     r12d, 0FFFFh
0x1800550e8  mov     word ptr [rsp+78h+arg_0], r13w
0x1800550f1  mov     rax, [rsi+18h]
0x1800550f5  movsxd  r8, dword ptr [rax+8]; char *
0x1800550f9  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x1800550fd  mov     rdx, r14; wchar_t *
0x180055100  lea     rcx, [rsp+78h+arg_0]; this
0x180055108  call    _mbtowc_internal
0x18005510d  movsxd  rdi, eax
0x180055110  test    eax, eax
0x180055112  jle     short loc_1800550B1
0x180055114  mov     r8, [rbx+8]
0x180055118  movzx   r9d, word ptr [rsp+78h+arg_0]
0x180055121  mov     rcx, [rbx+460h]
0x180055128  mov     edx, [rcx+14h]
0x18005512b  nop
0x18005512c  shr     edx, 0Ch
0x18005512f  test    dl, 1
0x180055132  jz      short loc_180055141
0x180055134  mov     rax, [rbx+460h]
0x18005513b  cmp     [rax+8], r13
0x18005513f  jz      short loc_180055157
0x180055141  mov     rdx, [rbx+460h]
0x180055148  movzx   ecx, r9w
0x18005514c  call    _fputwc_nolock_internal
0x180055151  cmp     ax, r12w
0x180055155  jz      short loc_18005515C
0x180055157  inc     dword ptr [rbx+20h]
0x18005515a  jmp     short loc_180055160
0x18005515c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055160  add     r14, rdi
0x180055163  inc     ebp
0x180055165  cmp     ebp, [r15]
0x180055168  jnz     loc_1800550E8
0x18005516e  jmp     short loc_1800551B3
0x180055170  lea     r10, [rcx+460h]
0x180055177  mov     rdx, [rcx+8]
0x18005517b  lea     r9, [rcx+20h]
0x18005517f  mov     r8d, [rdi]
0x180055182  mov     r11, [rcx+40h]
0x180055186  mov     rax, [r10]
0x180055189  mov     ecx, [rax+14h]
0x18005518c  nop
0x18005518d  shr     ecx, 0Ch
0x180055190  test    cl, 1
0x180055193  jz      short loc_1800551A3
0x180055195  mov     rax, [r10]
0x180055198  cmp     [rax+8], r13
0x18005519c  jnz     short loc_1800551A3
0x18005519e  add     [r9], r8d
0x1800551a1  jmp     short loc_1800551B3
0x1800551a3  mov     [rsp+78h+var_58], rdx
0x1800551a8  mov     rdx, r11
0x1800551ab  mov     rcx, r10
0x1800551ae  call    ?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x1800551b3  mov     al, 1
0x1800551b5  mov     rbx, [rsp+78h+arg_8]
0x1800551bd  add     rsp, 40h
0x1800551c1  pop     r15
0x1800551c3  pop     r14
0x1800551c5  pop     r13
0x1800551c7  pop     r12
0x1800551c9  pop     rdi
0x1800551ca  pop     rsi
0x1800551cb  pop     rbp
0x1800551cc  retn
```
