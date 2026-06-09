# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x180054cb0`
- end: `0x180054f3d`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001512c`
- `0x18001b8ec`
- `0x18001bc10`
- `0x180054cb0`
- `0x180055d68`
- `0x1800588a8`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(
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
0x180054cb0  mov     rax, rsp
0x180054cb3  push    rbp
0x180054cb4  push    rsi
0x180054cb5  push    rdi
0x180054cb6  push    r12
0x180054cb8  push    r13
0x180054cba  push    r14
0x180054cbc  push    r15
0x180054cbe  sub     rsp, 40h
0x180054cc2  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180054cca  mov     [rax+10h], rbx
0x180054cce  mov     rbx, rcx
0x180054cd1  lea     rdi, [rcx+48h]
0x180054cd5  xor     r13d, r13d
0x180054cd8  cmp     [rcx+4Ch], r13b
0x180054cdc  jnz     loc_180054EE0
0x180054ce2  cmp     [rdi], r13d
0x180054ce5  jle     loc_180054EE0
0x180054ceb  mov     rsi, [rcx+8]
0x180054cef  mov     rbp, rdi
0x180054cf2  cmp     [rsi+28h], r13b
0x180054cf6  jnz     short loc_180054D04
0x180054cf8  mov     rcx, rsi; this
0x180054cfb  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054d00  lea     rbp, [rbx+48h]
0x180054d04  mov     rax, [rsi+18h]
0x180054d08  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054d0f  jnz     loc_180054E2A
0x180054d15  mov     rax, [rbx+40h]
0x180054d19  mov     [rsp+78h+arg_18], rax
0x180054d21  mov     [rsp+78h+arg_10], r13
0x180054d29  mov     esi, r13d
0x180054d2c  cmp     [rdi], r13d
0x180054d2f  jz      loc_180054F23
0x180054d35  mov     r12d, 0FFFFh
0x180054d3b  mov     [rsp+78h+arg_0], r13d
0x180054d43  mov     rax, [rbx+8]
0x180054d47  mov     [rsp+78h+var_58], rax; struct _Mbstatet *
0x180054d4c  lea     r9, [rsp+78h+arg_10]; unsigned __int64
0x180054d54  mov     r8d, 2; char **
0x180054d5a  lea     rdx, [rsp+78h+arg_18]; wchar_t *
0x180054d62  lea     rcx, [rsp+78h+arg_0]; this
0x180054d6a  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180054d6f  mov     rbp, rax
0x180054d72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054d76  jz      loc_180054E21
0x180054d7c  mov     r8, [rbx+8]
0x180054d80  movzx   ecx, word ptr [rsp+78h+arg_0]
0x180054d88  mov     rax, [rbx+460h]
0x180054d8f  mov     edx, [rax+14h]
0x180054d92  nop
0x180054d93  shr     edx, 0Ch
0x180054d96  test    dl, 1
0x180054d99  jz      short loc_180054DA8
0x180054d9b  mov     rax, [rbx+460h]
0x180054da2  cmp     [rax+8], r13
0x180054da6  jz      short loc_180054DBA
0x180054da8  mov     rdx, [rbx+460h]
0x180054daf  call    _fputwc_nolock_internal
0x180054db4  cmp     ax, r12w
0x180054db8  jz      short loc_180054DBF
0x180054dba  inc     dword ptr [rbx+20h]
0x180054dbd  jmp     short loc_180054DC3
0x180054dbf  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054dc3  cmp     rbp, 2
0x180054dc7  jnz     short loc_180054E12
0x180054dc9  mov     r8, [rbx+8]
0x180054dcd  movzx   ecx, word ptr [rsp+78h+arg_0+2]
0x180054dd5  mov     rax, [rbx+460h]
0x180054ddc  mov     edx, [rax+14h]
0x180054ddf  nop
0x180054de0  shr     edx, 0Ch
0x180054de3  test    dl, 1
0x180054de6  jz      short loc_180054DF5
0x180054de8  mov     rax, [rbx+460h]
0x180054def  cmp     [rax+8], r13
0x180054df3  jz      short loc_180054E07
0x180054df5  mov     rdx, [rbx+460h]
0x180054dfc  call    _fputwc_nolock_internal
0x180054e01  cmp     ax, r12w
0x180054e05  jz      short loc_180054E0C
0x180054e07  inc     dword ptr [rbx+20h]
0x180054e0a  jmp     short loc_180054E10
0x180054e0c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054e10  inc     esi
0x180054e12  inc     esi
0x180054e14  cmp     esi, [rdi]
0x180054e16  jnz     loc_180054D3B
0x180054e1c  jmp     loc_180054F23
0x180054e21  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054e25  jmp     loc_180054F23
0x180054e2a  mov     rsi, [rbx+8]
0x180054e2e  mov     r15, rdi
0x180054e31  cmp     [rsi+28h], r13b
0x180054e35  jnz     short loc_180054E42
0x180054e37  mov     rcx, rsi; this
0x180054e3a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054e3f  mov     r15, rbp
0x180054e42  mov     r14, [rbx+40h]
0x180054e46  mov     ebp, r13d
0x180054e49  cmp     [rdi], r13d
0x180054e4c  jz      loc_180054F23
0x180054e52  mov     r12d, 0FFFFh
0x180054e58  mov     word ptr [rsp+78h+arg_0], r13w
0x180054e61  mov     rax, [rsi+18h]
0x180054e65  movsxd  r8, dword ptr [rax+8]; char *
0x180054e69  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x180054e6d  mov     rdx, r14; wchar_t *
0x180054e70  lea     rcx, [rsp+78h+arg_0]; this
0x180054e78  call    _mbtowc_internal
0x180054e7d  movsxd  rdi, eax
0x180054e80  test    eax, eax
0x180054e82  jle     short loc_180054E21
0x180054e84  mov     r8, [rbx+8]
0x180054e88  movzx   r9d, word ptr [rsp+78h+arg_0]
0x180054e91  mov     rcx, [rbx+460h]
0x180054e98  mov     edx, [rcx+14h]
0x180054e9b  nop
0x180054e9c  shr     edx, 0Ch
0x180054e9f  test    dl, 1
0x180054ea2  jz      short loc_180054EB1
0x180054ea4  mov     rax, [rbx+460h]
0x180054eab  cmp     [rax+8], r13
0x180054eaf  jz      short loc_180054EC7
0x180054eb1  mov     rdx, [rbx+460h]
0x180054eb8  movzx   ecx, r9w
0x180054ebc  call    _fputwc_nolock_internal
0x180054ec1  cmp     ax, r12w
0x180054ec5  jz      short loc_180054ECC
0x180054ec7  inc     dword ptr [rbx+20h]
0x180054eca  jmp     short loc_180054ED0
0x180054ecc  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054ed0  add     r14, rdi
0x180054ed3  inc     ebp
0x180054ed5  cmp     ebp, [r15]
0x180054ed8  jnz     loc_180054E58
0x180054ede  jmp     short loc_180054F23
0x180054ee0  lea     r10, [rcx+460h]
0x180054ee7  mov     rdx, [rcx+8]
0x180054eeb  lea     r9, [rcx+20h]
0x180054eef  mov     r8d, [rdi]
0x180054ef2  mov     r11, [rcx+40h]
0x180054ef6  mov     rax, [r10]
0x180054ef9  mov     ecx, [rax+14h]
0x180054efc  nop
0x180054efd  shr     ecx, 0Ch
0x180054f00  test    cl, 1
0x180054f03  jz      short loc_180054F13
0x180054f05  mov     rax, [r10]
0x180054f08  cmp     [rax+8], r13
0x180054f0c  jnz     short loc_180054F13
0x180054f0e  add     [r9], r8d
0x180054f11  jmp     short loc_180054F23
0x180054f13  mov     [rsp+78h+var_58], rdx
0x180054f18  mov     rdx, r11
0x180054f1b  mov     rcx, r10
0x180054f1e  call    ?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x180054f23  mov     al, 1
0x180054f25  mov     rbx, [rsp+78h+arg_8]
0x180054f2d  add     rsp, 40h
0x180054f31  pop     r15
0x180054f33  pop     r14
0x180054f35  pop     r13
0x180054f37  pop     r12
0x180054f39  pop     rdi
0x180054f3a  pop     rsi
0x180054f3b  pop     rbp
0x180054f3c  retn
```
