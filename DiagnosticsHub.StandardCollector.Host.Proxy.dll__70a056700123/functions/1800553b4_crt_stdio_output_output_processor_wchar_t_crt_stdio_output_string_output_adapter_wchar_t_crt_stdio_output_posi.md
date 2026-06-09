# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x1800553b4`
- end: `0x1800555e5`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800149cc`
- `0x18001b18c`
- `0x18001b4b0`
- `0x1800553b4`
- `0x180055910`

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
0x1800553b4  push    rbp
0x1800553b6  push    rsi
0x1800553b7  push    rdi
0x1800553b8  push    r14
0x1800553ba  push    r15
0x1800553bc  sub     rsp, 40h
0x1800553c0  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800553c9  mov     [rsp+68h+arg_8], rbx
0x1800553ce  mov     rbx, rcx
0x1800553d1  lea     rdi, [rcx+48h]
0x1800553d5  xor     r15d, r15d
0x1800553d8  cmp     [rcx+4Ch], r15b
0x1800553dc  jnz     loc_1800555B2
0x1800553e2  cmp     [rdi], r15d
0x1800553e5  jle     loc_1800555B2
0x1800553eb  mov     rsi, [rcx+8]
0x1800553ef  cmp     [rsi+28h], r15b
0x1800553f3  jnz     short loc_1800553FD
0x1800553f5  mov     rcx, rsi; this
0x1800553f8  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800553fd  mov     rax, [rsi+18h]
0x180055401  cmp     dword ptr [rax+0Ch], 0FDE9h
0x180055408  jnz     loc_180055517
0x18005540e  mov     rax, [rbx+40h]
0x180055412  mov     [rsp+68h+arg_18], rax
0x18005541a  mov     [rsp+68h+arg_10], r15
0x180055422  mov     esi, r15d
0x180055425  cmp     [rdi], r15d
0x180055428  jz      loc_1800555D2
0x18005542e  mov     [rsp+68h+arg_0], r15d
0x180055433  mov     rax, [rbx+8]
0x180055437  mov     [rsp+68h+var_48], rax; struct _Mbstatet *
0x18005543c  lea     r9, [rsp+68h+arg_10]; unsigned __int64
0x180055444  mov     r8d, 2; char **
0x18005544a  lea     rdx, [rsp+68h+arg_18]; wchar_t *
0x180055452  lea     rcx, [rsp+68h+arg_0]; this
0x180055457  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18005545c  mov     rdx, rax
0x18005545f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055463  jz      loc_18005550E
0x180055469  movzx   r8d, word ptr [rsp+68h+arg_0]
0x18005546f  mov     rcx, [rbx+460h]
0x180055476  mov     rax, [rcx+8]
0x18005547a  cmp     [rcx+10h], rax
0x18005547e  jnz     short loc_180055491
0x180055480  cmp     [rcx+18h], r15b
0x180055484  jz      short loc_18005548B
0x180055486  inc     dword ptr [rbx+20h]
0x180055489  jmp     short loc_1800554B1
0x18005548b  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005548f  jmp     short loc_1800554B1
0x180055491  inc     dword ptr [rbx+20h]
0x180055494  inc     qword ptr [rcx+10h]
0x180055498  mov     rax, [rbx+460h]
0x18005549f  mov     rcx, [rax]
0x1800554a2  mov     [rcx], r8w
0x1800554a6  mov     rax, [rbx+460h]
0x1800554ad  add     qword ptr [rax], 2
0x1800554b1  cmp     rdx, 2
0x1800554b5  jnz     short loc_1800554FF
0x1800554b7  movzx   edx, word ptr [rsp+68h+arg_0+2]
0x1800554bc  mov     rcx, [rbx+460h]
0x1800554c3  mov     rax, [rcx+8]
0x1800554c7  cmp     [rcx+10h], rax
0x1800554cb  jnz     short loc_1800554DE
0x1800554cd  cmp     [rcx+18h], r15b
0x1800554d1  jz      short loc_1800554D8
0x1800554d3  inc     dword ptr [rbx+20h]
0x1800554d6  jmp     short loc_1800554FD
0x1800554d8  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800554dc  jmp     short loc_1800554FD
0x1800554de  inc     dword ptr [rbx+20h]
0x1800554e1  inc     qword ptr [rcx+10h]
0x1800554e5  mov     rax, [rbx+460h]
0x1800554ec  mov     rcx, [rax]
0x1800554ef  mov     [rcx], dx
0x1800554f2  mov     rax, [rbx+460h]
0x1800554f9  add     qword ptr [rax], 2
0x1800554fd  inc     esi
0x1800554ff  inc     esi
0x180055501  cmp     esi, [rdi]
0x180055503  jnz     loc_18005542E
0x180055509  jmp     loc_1800555D2
0x18005550e  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055512  jmp     loc_1800555D2
0x180055517  mov     rsi, [rbx+8]
0x18005551b  cmp     [rsi+28h], r15b
0x18005551f  jnz     short loc_180055529
0x180055521  mov     rcx, rsi; this
0x180055524  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180055529  mov     r14, [rbx+40h]
0x18005552d  mov     ebp, r15d
0x180055530  cmp     [rdi], r15d
0x180055533  jz      loc_1800555D2
0x180055539  mov     word ptr [rsp+68h+arg_0], r15w
0x18005553f  mov     rax, [rsi+18h]
0x180055543  movsxd  r8, dword ptr [rax+8]; char *
0x180055547  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x18005554b  mov     rdx, r14; wchar_t *
0x18005554e  lea     rcx, [rsp+68h+arg_0]; this
0x180055553  call    _mbtowc_internal
0x180055558  movsxd  r8, eax
0x18005555b  test    eax, eax
0x18005555d  jle     short loc_18005550E
0x18005555f  movzx   r9d, word ptr [rsp+68h+arg_0]
0x180055565  mov     rdx, [rbx+460h]
0x18005556c  mov     rcx, [rdx+8]
0x180055570  cmp     [rdx+10h], rcx
0x180055574  jnz     short loc_180055587
0x180055576  cmp     [rdx+18h], r15b
0x18005557a  jz      short loc_180055581
0x18005557c  inc     dword ptr [rbx+20h]
0x18005557f  jmp     short loc_1800555A7
0x180055581  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055585  jmp     short loc_1800555A7
0x180055587  inc     dword ptr [rbx+20h]
0x18005558a  inc     qword ptr [rdx+10h]
0x18005558e  mov     rax, [rbx+460h]
0x180055595  mov     rcx, [rax]
0x180055598  mov     [rcx], r9w
0x18005559c  mov     rax, [rbx+460h]
0x1800555a3  add     qword ptr [rax], 2
0x1800555a7  add     r14, r8
0x1800555aa  inc     ebp
0x1800555ac  cmp     ebp, [rdi]
0x1800555ae  jnz     short loc_180055539
0x1800555b0  jmp     short loc_1800555D2
0x1800555b2  add     rcx, 460h
0x1800555b9  lea     r9, [rbx+20h]
0x1800555bd  mov     rax, [rbx+8]
0x1800555c1  mov     [rsp+68h+var_48], rax
0x1800555c6  mov     r8d, [rdi]
0x1800555c9  mov     rdx, [rbx+40h]
0x1800555cd  call    ?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x1800555d2  mov     al, 1
0x1800555d4  mov     rbx, [rsp+68h+arg_8]
0x1800555d9  add     rsp, 40h
0x1800555dd  pop     r15
0x1800555df  pop     r14
0x1800555e1  pop     rdi
0x1800555e2  pop     rsi
0x1800555e3  pop     rbp
0x1800555e4  retn
```
