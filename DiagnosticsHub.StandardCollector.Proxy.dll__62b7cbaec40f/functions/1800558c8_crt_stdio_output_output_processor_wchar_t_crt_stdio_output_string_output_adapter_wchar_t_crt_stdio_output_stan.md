# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x1800558c8`
- end: `0x180055af9`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18001512c`
- `0x18001b8ec`
- `0x18001bc10`
- `0x1800558c8`
- `0x180055bf0`

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
0x1800558c8  push    rbp
0x1800558ca  push    rsi
0x1800558cb  push    rdi
0x1800558cc  push    r14
0x1800558ce  push    r15
0x1800558d0  sub     rsp, 40h
0x1800558d4  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800558dd  mov     [rsp+68h+arg_8], rbx
0x1800558e2  mov     rbx, rcx
0x1800558e5  lea     rdi, [rcx+48h]
0x1800558e9  xor     r15d, r15d
0x1800558ec  cmp     [rcx+4Ch], r15b
0x1800558f0  jnz     loc_180055AC6
0x1800558f6  cmp     [rdi], r15d
0x1800558f9  jle     loc_180055AC6
0x1800558ff  mov     rsi, [rcx+8]
0x180055903  cmp     [rsi+28h], r15b
0x180055907  jnz     short loc_180055911
0x180055909  mov     rcx, rsi; this
0x18005590c  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180055911  mov     rax, [rsi+18h]
0x180055915  cmp     dword ptr [rax+0Ch], 0FDE9h
0x18005591c  jnz     loc_180055A2B
0x180055922  mov     rax, [rbx+40h]
0x180055926  mov     [rsp+68h+arg_18], rax
0x18005592e  mov     [rsp+68h+arg_10], r15
0x180055936  mov     esi, r15d
0x180055939  cmp     [rdi], r15d
0x18005593c  jz      loc_180055AE6
0x180055942  mov     [rsp+68h+arg_0], r15d
0x180055947  mov     rax, [rbx+8]
0x18005594b  mov     [rsp+68h+var_48], rax; struct _Mbstatet *
0x180055950  lea     r9, [rsp+68h+arg_10]; unsigned __int64
0x180055958  mov     r8d, 2; char **
0x18005595e  lea     rdx, [rsp+68h+arg_18]; wchar_t *
0x180055966  lea     rcx, [rsp+68h+arg_0]; this
0x18005596b  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180055970  mov     rdx, rax
0x180055973  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055977  jz      loc_180055A22
0x18005597d  movzx   r8d, word ptr [rsp+68h+arg_0]
0x180055983  mov     rcx, [rbx+460h]
0x18005598a  mov     rax, [rcx+8]
0x18005598e  cmp     [rcx+10h], rax
0x180055992  jnz     short loc_1800559A5
0x180055994  cmp     [rcx+18h], r15b
0x180055998  jz      short loc_18005599F
0x18005599a  inc     dword ptr [rbx+20h]
0x18005599d  jmp     short loc_1800559C5
0x18005599f  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800559a3  jmp     short loc_1800559C5
0x1800559a5  inc     dword ptr [rbx+20h]
0x1800559a8  inc     qword ptr [rcx+10h]
0x1800559ac  mov     rax, [rbx+460h]
0x1800559b3  mov     rcx, [rax]
0x1800559b6  mov     [rcx], r8w
0x1800559ba  mov     rax, [rbx+460h]
0x1800559c1  add     qword ptr [rax], 2
0x1800559c5  cmp     rdx, 2
0x1800559c9  jnz     short loc_180055A13
0x1800559cb  movzx   edx, word ptr [rsp+68h+arg_0+2]
0x1800559d0  mov     rcx, [rbx+460h]
0x1800559d7  mov     rax, [rcx+8]
0x1800559db  cmp     [rcx+10h], rax
0x1800559df  jnz     short loc_1800559F2
0x1800559e1  cmp     [rcx+18h], r15b
0x1800559e5  jz      short loc_1800559EC
0x1800559e7  inc     dword ptr [rbx+20h]
0x1800559ea  jmp     short loc_180055A11
0x1800559ec  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800559f0  jmp     short loc_180055A11
0x1800559f2  inc     dword ptr [rbx+20h]
0x1800559f5  inc     qword ptr [rcx+10h]
0x1800559f9  mov     rax, [rbx+460h]
0x180055a00  mov     rcx, [rax]
0x180055a03  mov     [rcx], dx
0x180055a06  mov     rax, [rbx+460h]
0x180055a0d  add     qword ptr [rax], 2
0x180055a11  inc     esi
0x180055a13  inc     esi
0x180055a15  cmp     esi, [rdi]
0x180055a17  jnz     loc_180055942
0x180055a1d  jmp     loc_180055AE6
0x180055a22  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055a26  jmp     loc_180055AE6
0x180055a2b  mov     rsi, [rbx+8]
0x180055a2f  cmp     [rsi+28h], r15b
0x180055a33  jnz     short loc_180055A3D
0x180055a35  mov     rcx, rsi; this
0x180055a38  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180055a3d  mov     r14, [rbx+40h]
0x180055a41  mov     ebp, r15d
0x180055a44  cmp     [rdi], r15d
0x180055a47  jz      loc_180055AE6
0x180055a4d  mov     word ptr [rsp+68h+arg_0], r15w
0x180055a53  mov     rax, [rsi+18h]
0x180055a57  movsxd  r8, dword ptr [rax+8]; char *
0x180055a5b  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x180055a5f  mov     rdx, r14; wchar_t *
0x180055a62  lea     rcx, [rsp+68h+arg_0]; this
0x180055a67  call    _mbtowc_internal
0x180055a6c  movsxd  r8, eax
0x180055a6f  test    eax, eax
0x180055a71  jle     short loc_180055A22
0x180055a73  movzx   r9d, word ptr [rsp+68h+arg_0]
0x180055a79  mov     rdx, [rbx+460h]
0x180055a80  mov     rcx, [rdx+8]
0x180055a84  cmp     [rdx+10h], rcx
0x180055a88  jnz     short loc_180055A9B
0x180055a8a  cmp     [rdx+18h], r15b
0x180055a8e  jz      short loc_180055A95
0x180055a90  inc     dword ptr [rbx+20h]
0x180055a93  jmp     short loc_180055ABB
0x180055a95  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055a99  jmp     short loc_180055ABB
0x180055a9b  inc     dword ptr [rbx+20h]
0x180055a9e  inc     qword ptr [rdx+10h]
0x180055aa2  mov     rax, [rbx+460h]
0x180055aa9  mov     rcx, [rax]
0x180055aac  mov     [rcx], r9w
0x180055ab0  mov     rax, [rbx+460h]
0x180055ab7  add     qword ptr [rax], 2
0x180055abb  add     r14, r8
0x180055abe  inc     ebp
0x180055ac0  cmp     ebp, [rdi]
0x180055ac2  jnz     short loc_180055A4D
0x180055ac4  jmp     short loc_180055AE6
0x180055ac6  add     rcx, 460h
0x180055acd  lea     r9, [rbx+20h]
0x180055ad1  mov     rax, [rbx+8]
0x180055ad5  mov     [rsp+68h+var_48], rax
0x180055ada  mov     r8d, [rdi]
0x180055add  mov     rdx, [rbx+40h]
0x180055ae1  call    ?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x180055ae6  mov     al, 1
0x180055ae8  mov     rbx, [rsp+68h+arg_8]
0x180055aed  add     rsp, 40h
0x180055af1  pop     r15
0x180055af3  pop     r14
0x180055af5  pop     rdi
0x180055af6  pop     rsi
0x180055af7  pop     rbp
0x180055af8  retn
```
