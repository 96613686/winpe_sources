# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x180054ef0`
- end: `0x18005517d`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800149cc`
- `0x18001b18c`
- `0x18001b4b0`
- `0x180054ef0`
- `0x180055a88`
- `0x1800585c8`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(
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
0x180054ef0  mov     rax, rsp
0x180054ef3  push    rbp
0x180054ef4  push    rsi
0x180054ef5  push    rdi
0x180054ef6  push    r12
0x180054ef8  push    r13
0x180054efa  push    r14
0x180054efc  push    r15
0x180054efe  sub     rsp, 40h
0x180054f02  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054f0a  mov     [rax+10h], rbx
0x180054f0e  mov     rbx, rcx
0x180054f11  lea     rdi, [rcx+48h]
0x180054f15  xor     r13d, r13d
0x180054f18  cmp     [rcx+4Ch], r13b
0x180054f1c  jnz     loc_180055120
0x180054f22  cmp     [rdi], r13d
0x180054f25  jle     loc_180055120
0x180054f2b  mov     rsi, [rcx+8]
0x180054f2f  mov     rbp, rdi
0x180054f32  cmp     [rsi+28h], r13b
0x180054f36  jnz     short loc_180054F44
0x180054f38  mov     rcx, rsi; this
0x180054f3b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054f40  lea     rbp, [rbx+48h]
0x180054f44  mov     rax, [rsi+18h]
0x180054f48  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054f4f  jnz     loc_18005506A
0x180054f55  mov     rax, [rbx+40h]
0x180054f59  mov     [rsp+78h+arg_18], rax
0x180054f61  mov     [rsp+78h+arg_10], r13
0x180054f69  mov     esi, r13d
0x180054f6c  cmp     [rdi], r13d
0x180054f6f  jz      loc_180055163
0x180054f75  mov     r12d, 0FFFFh
0x180054f7b  mov     [rsp+78h+arg_0], r13d
0x180054f83  mov     rax, [rbx+8]
0x180054f87  mov     [rsp+78h+var_58], rax; struct _Mbstatet *
0x180054f8c  lea     r9, [rsp+78h+arg_10]; unsigned __int64
0x180054f94  mov     r8d, 2; char **
0x180054f9a  lea     rdx, [rsp+78h+arg_18]; wchar_t *
0x180054fa2  lea     rcx, [rsp+78h+arg_0]; this
0x180054faa  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180054faf  mov     rbp, rax
0x180054fb2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054fb6  jz      loc_180055061
0x180054fbc  mov     r8, [rbx+8]
0x180054fc0  movzx   ecx, word ptr [rsp+78h+arg_0]
0x180054fc8  mov     rax, [rbx+460h]
0x180054fcf  mov     edx, [rax+14h]
0x180054fd2  nop
0x180054fd3  shr     edx, 0Ch
0x180054fd6  test    dl, 1
0x180054fd9  jz      short loc_180054FE8
0x180054fdb  mov     rax, [rbx+460h]
0x180054fe2  cmp     [rax+8], r13
0x180054fe6  jz      short loc_180054FFA
0x180054fe8  mov     rdx, [rbx+460h]
0x180054fef  call    _fputwc_nolock_internal
0x180054ff4  cmp     ax, r12w
0x180054ff8  jz      short loc_180054FFF
0x180054ffa  inc     dword ptr [rbx+20h]
0x180054ffd  jmp     short loc_180055003
0x180054fff  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055003  cmp     rbp, 2
0x180055007  jnz     short loc_180055052
0x180055009  mov     r8, [rbx+8]
0x18005500d  movzx   ecx, word ptr [rsp+78h+arg_0+2]
0x180055015  mov     rax, [rbx+460h]
0x18005501c  mov     edx, [rax+14h]
0x18005501f  nop
0x180055020  shr     edx, 0Ch
0x180055023  test    dl, 1
0x180055026  jz      short loc_180055035
0x180055028  mov     rax, [rbx+460h]
0x18005502f  cmp     [rax+8], r13
0x180055033  jz      short loc_180055047
0x180055035  mov     rdx, [rbx+460h]
0x18005503c  call    _fputwc_nolock_internal
0x180055041  cmp     ax, r12w
0x180055045  jz      short loc_18005504C
0x180055047  inc     dword ptr [rbx+20h]
0x18005504a  jmp     short loc_180055050
0x18005504c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055050  inc     esi
0x180055052  inc     esi
0x180055054  cmp     esi, [rdi]
0x180055056  jnz     loc_180054F7B
0x18005505c  jmp     loc_180055163
0x180055061  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055065  jmp     loc_180055163
0x18005506a  mov     rsi, [rbx+8]
0x18005506e  mov     r15, rdi
0x180055071  cmp     [rsi+28h], r13b
0x180055075  jnz     short loc_180055082
0x180055077  mov     rcx, rsi; this
0x18005507a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18005507f  mov     r15, rbp
0x180055082  mov     r14, [rbx+40h]
0x180055086  mov     ebp, r13d
0x180055089  cmp     [rdi], r13d
0x18005508c  jz      loc_180055163
0x180055092  mov     r12d, 0FFFFh
0x180055098  mov     word ptr [rsp+78h+arg_0], r13w
0x1800550a1  mov     rax, [rsi+18h]
0x1800550a5  movsxd  r8, dword ptr [rax+8]; char *
0x1800550a9  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x1800550ad  mov     rdx, r14; wchar_t *
0x1800550b0  lea     rcx, [rsp+78h+arg_0]; this
0x1800550b8  call    _mbtowc_internal
0x1800550bd  movsxd  rdi, eax
0x1800550c0  test    eax, eax
0x1800550c2  jle     short loc_180055061
0x1800550c4  mov     r8, [rbx+8]
0x1800550c8  movzx   r9d, word ptr [rsp+78h+arg_0]
0x1800550d1  mov     rcx, [rbx+460h]
0x1800550d8  mov     edx, [rcx+14h]
0x1800550db  nop
0x1800550dc  shr     edx, 0Ch
0x1800550df  test    dl, 1
0x1800550e2  jz      short loc_1800550F1
0x1800550e4  mov     rax, [rbx+460h]
0x1800550eb  cmp     [rax+8], r13
0x1800550ef  jz      short loc_180055107
0x1800550f1  mov     rdx, [rbx+460h]
0x1800550f8  movzx   ecx, r9w
0x1800550fc  call    _fputwc_nolock_internal
0x180055101  cmp     ax, r12w
0x180055105  jz      short loc_18005510C
0x180055107  inc     dword ptr [rbx+20h]
0x18005510a  jmp     short loc_180055110
0x18005510c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055110  add     r14, rdi
0x180055113  inc     ebp
0x180055115  cmp     ebp, [r15]
0x180055118  jnz     loc_180055098
0x18005511e  jmp     short loc_180055163
0x180055120  lea     r10, [rcx+460h]
0x180055127  mov     rdx, [rcx+8]
0x18005512b  lea     r9, [rcx+20h]
0x18005512f  mov     r8d, [rdi]
0x180055132  mov     r11, [rcx+40h]
0x180055136  mov     rax, [r10]
0x180055139  mov     ecx, [rax+14h]
0x18005513c  nop
0x18005513d  shr     ecx, 0Ch
0x180055140  test    cl, 1
0x180055143  jz      short loc_180055153
0x180055145  mov     rax, [r10]
0x180055148  cmp     [rax+8], r13
0x18005514c  jnz     short loc_180055153
0x18005514e  add     [r9], r8d
0x180055151  jmp     short loc_180055163
0x180055153  mov     [rsp+78h+var_58], rdx
0x180055158  mov     rdx, r11
0x18005515b  mov     rcx, r10
0x18005515e  call    ?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x180055163  mov     al, 1
0x180055165  mov     rbx, [rsp+78h+arg_8]
0x18005516d  add     rsp, 40h
0x180055171  pop     r15
0x180055173  pop     r14
0x180055175  pop     r13
0x180055177  pop     r12
0x180055179  pop     rdi
0x18005517a  pop     rsi
0x18005517b  pop     rbp
0x18005517c  retn
```
