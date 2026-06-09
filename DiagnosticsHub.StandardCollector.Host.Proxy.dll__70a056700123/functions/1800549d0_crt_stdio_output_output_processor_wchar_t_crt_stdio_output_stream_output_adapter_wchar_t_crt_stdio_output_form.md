# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x1800549d0`
- end: `0x180054c5d`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800149cc`
- `0x18001b18c`
- `0x18001b4b0`
- `0x1800549d0`
- `0x180055a88`
- `0x1800585c8`

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
0x1800549d0  mov     rax, rsp
0x1800549d3  push    rbp
0x1800549d4  push    rsi
0x1800549d5  push    rdi
0x1800549d6  push    r12
0x1800549d8  push    r13
0x1800549da  push    r14
0x1800549dc  push    r15
0x1800549de  sub     rsp, 40h
0x1800549e2  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800549ea  mov     [rax+10h], rbx
0x1800549ee  mov     rbx, rcx
0x1800549f1  lea     rdi, [rcx+48h]
0x1800549f5  xor     r13d, r13d
0x1800549f8  cmp     [rcx+4Ch], r13b
0x1800549fc  jnz     loc_180054C00
0x180054a02  cmp     [rdi], r13d
0x180054a05  jle     loc_180054C00
0x180054a0b  mov     rsi, [rcx+8]
0x180054a0f  mov     rbp, rdi
0x180054a12  cmp     [rsi+28h], r13b
0x180054a16  jnz     short loc_180054A24
0x180054a18  mov     rcx, rsi; this
0x180054a1b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054a20  lea     rbp, [rbx+48h]
0x180054a24  mov     rax, [rsi+18h]
0x180054a28  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180054a2f  jnz     loc_180054B4A
0x180054a35  mov     rax, [rbx+40h]
0x180054a39  mov     [rsp+78h+arg_18], rax
0x180054a41  mov     [rsp+78h+arg_10], r13
0x180054a49  mov     esi, r13d
0x180054a4c  cmp     [rdi], r13d
0x180054a4f  jz      loc_180054C43
0x180054a55  mov     r12d, 0FFFFh
0x180054a5b  mov     [rsp+78h+arg_0], r13d
0x180054a63  mov     rax, [rbx+8]
0x180054a67  mov     [rsp+78h+var_58], rax; struct _Mbstatet *
0x180054a6c  lea     r9, [rsp+78h+arg_10]; unsigned __int64
0x180054a74  mov     r8d, 2; char **
0x180054a7a  lea     rdx, [rsp+78h+arg_18]; wchar_t *
0x180054a82  lea     rcx, [rsp+78h+arg_0]; this
0x180054a8a  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180054a8f  mov     rbp, rax
0x180054a92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054a96  jz      loc_180054B41
0x180054a9c  mov     r8, [rbx+8]
0x180054aa0  movzx   ecx, word ptr [rsp+78h+arg_0]
0x180054aa8  mov     rax, [rbx+460h]
0x180054aaf  mov     edx, [rax+14h]
0x180054ab2  nop
0x180054ab3  shr     edx, 0Ch
0x180054ab6  test    dl, 1
0x180054ab9  jz      short loc_180054AC8
0x180054abb  mov     rax, [rbx+460h]
0x180054ac2  cmp     [rax+8], r13
0x180054ac6  jz      short loc_180054ADA
0x180054ac8  mov     rdx, [rbx+460h]
0x180054acf  call    _fputwc_nolock_internal
0x180054ad4  cmp     ax, r12w
0x180054ad8  jz      short loc_180054ADF
0x180054ada  inc     dword ptr [rbx+20h]
0x180054add  jmp     short loc_180054AE3
0x180054adf  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054ae3  cmp     rbp, 2
0x180054ae7  jnz     short loc_180054B32
0x180054ae9  mov     r8, [rbx+8]
0x180054aed  movzx   ecx, word ptr [rsp+78h+arg_0+2]
0x180054af5  mov     rax, [rbx+460h]
0x180054afc  mov     edx, [rax+14h]
0x180054aff  nop
0x180054b00  shr     edx, 0Ch
0x180054b03  test    dl, 1
0x180054b06  jz      short loc_180054B15
0x180054b08  mov     rax, [rbx+460h]
0x180054b0f  cmp     [rax+8], r13
0x180054b13  jz      short loc_180054B27
0x180054b15  mov     rdx, [rbx+460h]
0x180054b1c  call    _fputwc_nolock_internal
0x180054b21  cmp     ax, r12w
0x180054b25  jz      short loc_180054B2C
0x180054b27  inc     dword ptr [rbx+20h]
0x180054b2a  jmp     short loc_180054B30
0x180054b2c  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054b30  inc     esi
0x180054b32  inc     esi
0x180054b34  cmp     esi, [rdi]
0x180054b36  jnz     loc_180054A5B
0x180054b3c  jmp     loc_180054C43
0x180054b41  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054b45  jmp     loc_180054C43
0x180054b4a  mov     rsi, [rbx+8]
0x180054b4e  mov     r15, rdi
0x180054b51  cmp     [rsi+28h], r13b
0x180054b55  jnz     short loc_180054B62
0x180054b57  mov     rcx, rsi; this
0x180054b5a  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180054b5f  mov     r15, rbp
0x180054b62  mov     r14, [rbx+40h]
0x180054b66  mov     ebp, r13d
0x180054b69  cmp     [rdi], r13d
0x180054b6c  jz      loc_180054C43
0x180054b72  mov     r12d, 0FFFFh
0x180054b78  mov     word ptr [rsp+78h+arg_0], r13w
0x180054b81  mov     rax, [rsi+18h]
0x180054b85  movsxd  r8, dword ptr [rax+8]; char *
0x180054b89  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x180054b8d  mov     rdx, r14; wchar_t *
0x180054b90  lea     rcx, [rsp+78h+arg_0]; this
0x180054b98  call    _mbtowc_internal
0x180054b9d  movsxd  rdi, eax
0x180054ba0  test    eax, eax
0x180054ba2  jle     short loc_180054B41
0x180054ba4  mov     r8, [rbx+8]
0x180054ba8  movzx   r9d, word ptr [rsp+78h+arg_0]
0x180054bb1  mov     rcx, [rbx+460h]
0x180054bb8  mov     edx, [rcx+14h]
0x180054bbb  nop
0x180054bbc  shr     edx, 0Ch
0x180054bbf  test    dl, 1
0x180054bc2  jz      short loc_180054BD1
0x180054bc4  mov     rax, [rbx+460h]
0x180054bcb  cmp     [rax+8], r13
0x180054bcf  jz      short loc_180054BE7
0x180054bd1  mov     rdx, [rbx+460h]
0x180054bd8  movzx   ecx, r9w
0x180054bdc  call    _fputwc_nolock_internal
0x180054be1  cmp     ax, r12w
0x180054be5  jz      short loc_180054BEC
0x180054be7  inc     dword ptr [rbx+20h]
0x180054bea  jmp     short loc_180054BF0
0x180054bec  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180054bf0  add     r14, rdi
0x180054bf3  inc     ebp
0x180054bf5  cmp     ebp, [r15]
0x180054bf8  jnz     loc_180054B78
0x180054bfe  jmp     short loc_180054C43
0x180054c00  lea     r10, [rcx+460h]
0x180054c07  mov     rdx, [rcx+8]
0x180054c0b  lea     r9, [rcx+20h]
0x180054c0f  mov     r8d, [rdi]
0x180054c12  mov     r11, [rcx+40h]
0x180054c16  mov     rax, [r10]
0x180054c19  mov     ecx, [rax+14h]
0x180054c1c  nop
0x180054c1d  shr     ecx, 0Ch
0x180054c20  test    cl, 1
0x180054c23  jz      short loc_180054C33
0x180054c25  mov     rax, [r10]
0x180054c28  cmp     [rax+8], r13
0x180054c2c  jnz     short loc_180054C33
0x180054c2e  add     [r9], r8d
0x180054c31  jmp     short loc_180054C43
0x180054c33  mov     [rsp+78h+var_58], rdx
0x180054c38  mov     rdx, r11
0x180054c3b  mov     rcx, r10
0x180054c3e  call    ?write_string_impl@?$output_adapter_common@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@__crt_stdio_output@@IEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::output_adapter_common<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>::write_string_impl(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x180054c43  mov     al, 1
0x180054c45  mov     rbx, [rsp+78h+arg_8]
0x180054c4d  add     rsp, 40h
0x180054c51  pop     r15
0x180054c53  pop     r14
0x180054c55  pop     r13
0x180054c57  pop     r12
0x180054c59  pop     rdi
0x180054c5a  pop     rsi
0x180054c5b  pop     rbp
0x180054c5c  retn
```
