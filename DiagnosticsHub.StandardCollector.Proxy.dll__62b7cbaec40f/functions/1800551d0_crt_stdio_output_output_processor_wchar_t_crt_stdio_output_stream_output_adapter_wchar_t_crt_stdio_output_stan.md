# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x1800551d0`
- end: `0x18005545d`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001512c`
- `0x18001b8ec`
- `0x18001bc10`
- `0x1800551d0`
- `0x180055d68`
- `0x1800588a8`

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
0x1800551d0  mov     rax, rsp
0x1800551d3  push    rbp
0x1800551d4  push    rsi
0x1800551d5  push    rdi
0x1800551d6  push    r12
0x1800551d8  push    r13
0x1800551da  push    r14
0x1800551dc  push    r15
0x1800551de  sub     rsp, 40h
0x1800551e2  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800551ea  mov     [rax+10h], rbx
0x1800551ee  mov     rbx, rcx
0x1800551f1  lea     rdi, [rcx+48h]
0x1800551f5  xor     r13d, r13d
0x1800551f8  cmp     [rcx+4Ch], r13b
0x1800551fc  jnz     loc_180055400
0x180055202  cmp     [rdi], r13d
0x180055205  jle     loc_180055400
0x18005520b  mov     rsi, [rcx+8]
0x18005520f  mov     rbp, rdi
0x180055212  cmp     [rsi+28h], r13b
0x180055216  jnz     short loc_180055224
0x180055218  mov     rcx, rsi; this
0x18005521b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180055220  lea     rbp, [rbx+48h]
0x180055224  mov     rax, [rsi+18h]
0x180055228  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005522f  jnz     loc_18005534A
0x180055235  mov     rax, [rbx+40h]
0x180055239  mov     [rsp+78h+arg_18], rax
0x180055241  mov     [rsp+78h+arg_10], r13
0x180055249  mov     esi, r13d
0x18005524c  cmp     [rdi], r13d
0x18005524f  jz      loc_180055443
0x180055255  mov     r12d, 0FFFFh
0x18005525b  mov     [rsp+78h+arg_0], r13d
0x180055263  mov     rax, [rbx+8]
0x180055267  mov     [rsp+78h+var_58], rax; struct _Mbstatet *
0x18005526c  lea     r9, [rsp+78h+arg_10]; unsigned __int64
0x180055274  mov     r8d, 2; char **
0x18005527a  lea     rdx, [rsp+78h+arg_18]; wchar_t *
0x180055282  lea     rcx, [rsp+78h+arg_0]; this
0x18005528a  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18005528f  mov     rbp, rax
0x180055292  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055296  jz      loc_180055341
0x18005529c  mov     r8, [rbx+8]
0x1800552a0  movzx   ecx, word ptr [rsp+78h+arg_0]
0x1800552a8  mov     rax, [rbx+460h]
0x1800552af  mov     edx, [rax+14h]
0x1800552b2  nop
0x1800552b3  shr     edx, 0Ch
0x1800552b6  test    dl, 1
0x1800552b9  jz      short loc_1800552C8
0x1800552bb  mov     rax, [rbx+460h]
0x1800552c2  cmp     [rax+8], r13
0x1800552c6  jz      short loc_1800552DA
0x1800552c8  mov     rdx, [rbx+460h]
0x1800552cf  call    _fputwc_nolock_internal
0x1800552d4  cmp     ax, r12w
0x1800552d8  jz      short loc_1800552DF
0x1800552da  inc     dword ptr [rbx+20h]
0x1800552dd  jmp     short loc_1800552E3
0x1800552df  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800552e3  cmp     rbp, 2
0x1800552e7  jnz     short loc_180055332
0x1800552e9  mov     r8, [rbx+8]
0x1800552ed  movzx   ecx, word ptr [rsp+78h+arg_0+2]
0x1800552f5  mov     rax, [rbx+460h]
0x1800552fc  mov     edx, [rax+14h]
0x1800552ff  nop
0x180055300  shr     edx, 0Ch
0x180055303  test    dl, 1
0x180055306  jz      short loc_180055315
0x180055308  mov     rax, [rbx+460h]
0x18005530f  cmp     [rax+8], r13
0x180055313  jz      short loc_180055327
0x180055315  mov     rdx, [rbx+460h]
0x18005531c  call    _fputwc_nolock_internal
0x180055321  cmp     ax, r12w
0x180055325  jz      short loc_18005532C
0x180055327  inc     dword ptr [rbx+20h]
0x18005532a  jmp     short loc_180055330
0x18005532c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055330  inc     esi
0x180055332  inc     esi
0x180055334  cmp     esi, [rdi]
0x180055336  jnz     loc_18005525B
0x18005533c  jmp     loc_180055443
0x180055341  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055345  jmp     loc_180055443
0x18005534a  mov     rsi, [rbx+8]
0x18005534e  mov     r15, rdi
0x180055351  cmp     [rsi+28h], r13b
0x180055355  jnz     short loc_180055362
0x180055357  mov     rcx, rsi; this
0x18005535a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18005535f  mov     r15, rbp
0x180055362  mov     r14, [rbx+40h]
0x180055366  mov     ebp, r13d
0x180055369  cmp     [rdi], r13d
0x18005536c  jz      loc_180055443
0x180055372  mov     r12d, 0FFFFh
0x180055378  mov     word ptr [rsp+78h+arg_0], r13w
0x180055381  mov     rax, [rsi+18h]
0x180055385  movsxd  r8, dword ptr [rax+8]; char *
0x180055389  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x18005538d  mov     rdx, r14; wchar_t *
0x180055390  lea     rcx, [rsp+78h+arg_0]; this
0x180055398  call    _mbtowc_internal
0x18005539d  movsxd  rdi, eax
0x1800553a0  test    eax, eax
0x1800553a2  jle     short loc_180055341
0x1800553a4  mov     r8, [rbx+8]
0x1800553a8  movzx   r9d, word ptr [rsp+78h+arg_0]
0x1800553b1  mov     rcx, [rbx+460h]
0x1800553b8  mov     edx, [rcx+14h]
0x1800553bb  nop
0x1800553bc  shr     edx, 0Ch
0x1800553bf  test    dl, 1
0x1800553c2  jz      short loc_1800553D1
0x1800553c4  mov     rax, [rbx+460h]
0x1800553cb  cmp     [rax+8], r13
0x1800553cf  jz      short loc_1800553E7
0x1800553d1  mov     rdx, [rbx+460h]
0x1800553d8  movzx   ecx, r9w
0x1800553dc  call    _fputwc_nolock_internal
0x1800553e1  cmp     ax, r12w
0x1800553e5  jz      short loc_1800553EC
0x1800553e7  inc     dword ptr [rbx+20h]
0x1800553ea  jmp     short loc_1800553F0
0x1800553ec  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800553f0  add     r14, rdi
0x1800553f3  inc     ebp
0x1800553f5  cmp     ebp, [r15]
0x1800553f8  jnz     loc_180055378
0x1800553fe  jmp     short loc_180055443
0x180055400  lea     r10, [rcx+460h]
0x180055407  mov     rdx, [rcx+8]
0x18005540b  lea     r9, [rcx+20h]
0x18005540f  mov     r8d, [rdi]
0x180055412  mov     r11, [rcx+40h]
0x180055416  mov     rax, [r10]
0x180055419  mov     ecx, [rax+14h]
0x18005541c  nop
0x18005541d  shr     ecx, 0Ch
0x180055420  test    cl, 1
0x180055423  jz      short loc_180055433
0x180055425  mov     rax, [r10]
0x180055428  cmp     [rax+8], r13
0x18005542c  jnz     short loc_180055433
0x18005542e  add     [r9], r8d
0x180055431  jmp     short loc_180055443
0x180055433  mov     [rsp+78h+var_58], rdx
0x180055438  mov     rdx, r11
0x18005543b  mov     rcx, r10
0x18005543e  call    ?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x180055443  mov     al, 1
0x180055445  mov     rbx, [rsp+78h+arg_8]
0x18005544d  add     rsp, 40h
0x180055451  pop     r15
0x180055453  pop     r14
0x180055455  pop     r13
0x180055457  pop     r12
0x180055459  pop     rdi
0x18005545a  pop     rsi
0x18005545b  pop     rbp
0x18005545c  retn
```
