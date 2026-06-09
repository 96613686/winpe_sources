# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x180054c60`
- end: `0x180054eed`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800149cc`
- `0x18001b18c`
- `0x18001b4b0`
- `0x180054c60`
- `0x180055a88`
- `0x1800585c8`

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
0x180054c60  mov     rax, rsp
0x180054c63  push    rbp
0x180054c64  push    rsi
0x180054c65  push    rdi
0x180054c66  push    r12
0x180054c68  push    r13
0x180054c6a  push    r14
0x180054c6c  push    r15
0x180054c6e  sub     rsp, 40h
0x180054c72  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054c7a  mov     [rax+10h], rbx
0x180054c7e  mov     rbx, rcx
0x180054c81  lea     rdi, [rcx+48h]
0x180054c85  xor     r13d, r13d
0x180054c88  cmp     [rcx+4Ch], r13b
0x180054c8c  jnz     loc_180054E90
0x180054c92  cmp     [rdi], r13d
0x180054c95  jle     loc_180054E90
0x180054c9b  mov     rsi, [rcx+8]
0x180054c9f  mov     rbp, rdi
0x180054ca2  cmp     [rsi+28h], r13b
0x180054ca6  jnz     short loc_180054CB4
0x180054ca8  mov     rcx, rsi; this
0x180054cab  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054cb0  lea     rbp, [rbx+48h]
0x180054cb4  mov     rax, [rsi+18h]
0x180054cb8  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054cbf  jnz     loc_180054DDA
0x180054cc5  mov     rax, [rbx+40h]
0x180054cc9  mov     [rsp+78h+arg_18], rax
0x180054cd1  mov     [rsp+78h+arg_10], r13
0x180054cd9  mov     esi, r13d
0x180054cdc  cmp     [rdi], r13d
0x180054cdf  jz      loc_180054ED3
0x180054ce5  mov     r12d, 0FFFFh
0x180054ceb  mov     [rsp+78h+arg_0], r13d
0x180054cf3  mov     rax, [rbx+8]
0x180054cf7  mov     [rsp+78h+var_58], rax; struct _Mbstatet *
0x180054cfc  lea     r9, [rsp+78h+arg_10]; unsigned __int64
0x180054d04  mov     r8d, 2; char **
0x180054d0a  lea     rdx, [rsp+78h+arg_18]; wchar_t *
0x180054d12  lea     rcx, [rsp+78h+arg_0]; this
0x180054d1a  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180054d1f  mov     rbp, rax
0x180054d22  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054d26  jz      loc_180054DD1
0x180054d2c  mov     r8, [rbx+8]
0x180054d30  movzx   ecx, word ptr [rsp+78h+arg_0]
0x180054d38  mov     rax, [rbx+460h]
0x180054d3f  mov     edx, [rax+14h]
0x180054d42  nop
0x180054d43  shr     edx, 0Ch
0x180054d46  test    dl, 1
0x180054d49  jz      short loc_180054D58
0x180054d4b  mov     rax, [rbx+460h]
0x180054d52  cmp     [rax+8], r13
0x180054d56  jz      short loc_180054D6A
0x180054d58  mov     rdx, [rbx+460h]
0x180054d5f  call    _fputwc_nolock_internal
0x180054d64  cmp     ax, r12w
0x180054d68  jz      short loc_180054D6F
0x180054d6a  inc     dword ptr [rbx+20h]
0x180054d6d  jmp     short loc_180054D73
0x180054d6f  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054d73  cmp     rbp, 2
0x180054d77  jnz     short loc_180054DC2
0x180054d79  mov     r8, [rbx+8]
0x180054d7d  movzx   ecx, word ptr [rsp+78h+arg_0+2]
0x180054d85  mov     rax, [rbx+460h]
0x180054d8c  mov     edx, [rax+14h]
0x180054d8f  nop
0x180054d90  shr     edx, 0Ch
0x180054d93  test    dl, 1
0x180054d96  jz      short loc_180054DA5
0x180054d98  mov     rax, [rbx+460h]
0x180054d9f  cmp     [rax+8], r13
0x180054da3  jz      short loc_180054DB7
0x180054da5  mov     rdx, [rbx+460h]
0x180054dac  call    _fputwc_nolock_internal
0x180054db1  cmp     ax, r12w
0x180054db5  jz      short loc_180054DBC
0x180054db7  inc     dword ptr [rbx+20h]
0x180054dba  jmp     short loc_180054DC0
0x180054dbc  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054dc0  inc     esi
0x180054dc2  inc     esi
0x180054dc4  cmp     esi, [rdi]
0x180054dc6  jnz     loc_180054CEB
0x180054dcc  jmp     loc_180054ED3
0x180054dd1  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054dd5  jmp     loc_180054ED3
0x180054dda  mov     rsi, [rbx+8]
0x180054dde  mov     r15, rdi
0x180054de1  cmp     [rsi+28h], r13b
0x180054de5  jnz     short loc_180054DF2
0x180054de7  mov     rcx, rsi; this
0x180054dea  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054def  mov     r15, rbp
0x180054df2  mov     r14, [rbx+40h]
0x180054df6  mov     ebp, r13d
0x180054df9  cmp     [rdi], r13d
0x180054dfc  jz      loc_180054ED3
0x180054e02  mov     r12d, 0FFFFh
0x180054e08  mov     word ptr [rsp+78h+arg_0], r13w
0x180054e11  mov     rax, [rsi+18h]
0x180054e15  movsxd  r8, dword ptr [rax+8]; char *
0x180054e19  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x180054e1d  mov     rdx, r14; wchar_t *
0x180054e20  lea     rcx, [rsp+78h+arg_0]; this
0x180054e28  call    _mbtowc_internal
0x180054e2d  movsxd  rdi, eax
0x180054e30  test    eax, eax
0x180054e32  jle     short loc_180054DD1
0x180054e34  mov     r8, [rbx+8]
0x180054e38  movzx   r9d, word ptr [rsp+78h+arg_0]
0x180054e41  mov     rcx, [rbx+460h]
0x180054e48  mov     edx, [rcx+14h]
0x180054e4b  nop
0x180054e4c  shr     edx, 0Ch
0x180054e4f  test    dl, 1
0x180054e52  jz      short loc_180054E61
0x180054e54  mov     rax, [rbx+460h]
0x180054e5b  cmp     [rax+8], r13
0x180054e5f  jz      short loc_180054E77
0x180054e61  mov     rdx, [rbx+460h]
0x180054e68  movzx   ecx, r9w
0x180054e6c  call    _fputwc_nolock_internal
0x180054e71  cmp     ax, r12w
0x180054e75  jz      short loc_180054E7C
0x180054e77  inc     dword ptr [rbx+20h]
0x180054e7a  jmp     short loc_180054E80
0x180054e7c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054e80  add     r14, rdi
0x180054e83  inc     ebp
0x180054e85  cmp     ebp, [r15]
0x180054e88  jnz     loc_180054E08
0x180054e8e  jmp     short loc_180054ED3
0x180054e90  lea     r10, [rcx+460h]
0x180054e97  mov     rdx, [rcx+8]
0x180054e9b  lea     r9, [rcx+20h]
0x180054e9f  mov     r8d, [rdi]
0x180054ea2  mov     r11, [rcx+40h]
0x180054ea6  mov     rax, [r10]
0x180054ea9  mov     ecx, [rax+14h]
0x180054eac  nop
0x180054ead  shr     ecx, 0Ch
0x180054eb0  test    cl, 1
0x180054eb3  jz      short loc_180054EC3
0x180054eb5  mov     rax, [r10]
0x180054eb8  cmp     [rax+8], r13
0x180054ebc  jnz     short loc_180054EC3
0x180054ebe  add     [r9], r8d
0x180054ec1  jmp     short loc_180054ED3
0x180054ec3  mov     [rsp+78h+var_58], rdx
0x180054ec8  mov     rdx, r11
0x180054ecb  mov     rcx, r10
0x180054ece  call    ?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x180054ed3  mov     al, 1
0x180054ed5  mov     rbx, [rsp+78h+arg_8]
0x180054edd  add     rsp, 40h
0x180054ee1  pop     r15
0x180054ee3  pop     r14
0x180054ee5  pop     r13
0x180054ee7  pop     r12
0x180054ee9  pop     rdi
0x180054eea  pop     rsi
0x180054eeb  pop     rbp
0x180054eec  retn
```
