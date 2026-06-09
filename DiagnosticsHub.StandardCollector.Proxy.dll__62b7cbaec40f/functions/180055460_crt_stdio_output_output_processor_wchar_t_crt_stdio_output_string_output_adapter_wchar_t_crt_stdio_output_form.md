# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x180055460`
- end: `0x180055691`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18001512c`
- `0x18001b8ec`
- `0x18001bc10`
- `0x180055460`
- `0x180055bf0`

## pseudocode

```c
char __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(
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
0x180055460  push    rbp
0x180055462  push    rsi
0x180055463  push    rdi
0x180055464  push    r14
0x180055466  push    r15
0x180055468  sub     rsp, 40h
0x18005546c  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x180055475  mov     [rsp+68h+arg_8], rbx
0x18005547a  mov     rbx, rcx
0x18005547d  lea     rdi, [rcx+48h]
0x180055481  xor     r15d, r15d
0x180055484  cmp     [rcx+4Ch], r15b
0x180055488  jnz     loc_18005565E
0x18005548e  cmp     [rdi], r15d
0x180055491  jle     loc_18005565E
0x180055497  mov     rsi, [rcx+8]
0x18005549b  cmp     [rsi+28h], r15b
0x18005549f  jnz     short loc_1800554A9
0x1800554a1  mov     rcx, rsi; this
0x1800554a4  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800554a9  mov     rax, [rsi+18h]
0x1800554ad  cmp     dword ptr [rax+0Ch], 0FDE9h
0x1800554b4  jnz     loc_1800555C3
0x1800554ba  mov     rax, [rbx+40h]
0x1800554be  mov     [rsp+68h+arg_18], rax
0x1800554c6  mov     [rsp+68h+arg_10], r15
0x1800554ce  mov     esi, r15d
0x1800554d1  cmp     [rdi], r15d
0x1800554d4  jz      loc_18005567E
0x1800554da  mov     [rsp+68h+arg_0], r15d
0x1800554df  mov     rax, [rbx+8]
0x1800554e3  mov     [rsp+68h+var_48], rax; struct _Mbstatet *
0x1800554e8  lea     r9, [rsp+68h+arg_10]; unsigned __int64
0x1800554f0  mov     r8d, 2; char **
0x1800554f6  lea     rdx, [rsp+68h+arg_18]; wchar_t *
0x1800554fe  lea     rcx, [rsp+68h+arg_0]; this
0x180055503  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180055508  mov     rdx, rax
0x18005550b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005550f  jz      loc_1800555BA
0x180055515  movzx   r8d, word ptr [rsp+68h+arg_0]
0x18005551b  mov     rcx, [rbx+460h]
0x180055522  mov     rax, [rcx+8]
0x180055526  cmp     [rcx+10h], rax
0x18005552a  jnz     short loc_18005553D
0x18005552c  cmp     [rcx+18h], r15b
0x180055530  jz      short loc_180055537
0x180055532  inc     dword ptr [rbx+20h]
0x180055535  jmp     short loc_18005555D
0x180055537  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005553b  jmp     short loc_18005555D
0x18005553d  inc     dword ptr [rbx+20h]
0x180055540  inc     qword ptr [rcx+10h]
0x180055544  mov     rax, [rbx+460h]
0x18005554b  mov     rcx, [rax]
0x18005554e  mov     [rcx], r8w
0x180055552  mov     rax, [rbx+460h]
0x180055559  add     qword ptr [rax], 2
0x18005555d  cmp     rdx, 2
0x180055561  jnz     short loc_1800555AB
0x180055563  movzx   edx, word ptr [rsp+68h+arg_0+2]
0x180055568  mov     rcx, [rbx+460h]
0x18005556f  mov     rax, [rcx+8]
0x180055573  cmp     [rcx+10h], rax
0x180055577  jnz     short loc_18005558A
0x180055579  cmp     [rcx+18h], r15b
0x18005557d  jz      short loc_180055584
0x18005557f  inc     dword ptr [rbx+20h]
0x180055582  jmp     short loc_1800555A9
0x180055584  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055588  jmp     short loc_1800555A9
0x18005558a  inc     dword ptr [rbx+20h]
0x18005558d  inc     qword ptr [rcx+10h]
0x180055591  mov     rax, [rbx+460h]
0x180055598  mov     rcx, [rax]
0x18005559b  mov     [rcx], dx
0x18005559e  mov     rax, [rbx+460h]
0x1800555a5  add     qword ptr [rax], 2
0x1800555a9  inc     esi
0x1800555ab  inc     esi
0x1800555ad  cmp     esi, [rdi]
0x1800555af  jnz     loc_1800554DA
0x1800555b5  jmp     loc_18005567E
0x1800555ba  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800555be  jmp     loc_18005567E
0x1800555c3  mov     rsi, [rbx+8]
0x1800555c7  cmp     [rsi+28h], r15b
0x1800555cb  jnz     short loc_1800555D5
0x1800555cd  mov     rcx, rsi; this
0x1800555d0  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800555d5  mov     r14, [rbx+40h]
0x1800555d9  mov     ebp, r15d
0x1800555dc  cmp     [rdi], r15d
0x1800555df  jz      loc_18005567E
0x1800555e5  mov     word ptr [rsp+68h+arg_0], r15w
0x1800555eb  mov     rax, [rsi+18h]
0x1800555ef  movsxd  r8, dword ptr [rax+8]; char *
0x1800555f3  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x1800555f7  mov     rdx, r14; wchar_t *
0x1800555fa  lea     rcx, [rsp+68h+arg_0]; this
0x1800555ff  call    _mbtowc_internal
0x180055604  movsxd  r8, eax
0x180055607  test    eax, eax
0x180055609  jle     short loc_1800555BA
0x18005560b  movzx   r9d, word ptr [rsp+68h+arg_0]
0x180055611  mov     rdx, [rbx+460h]
0x180055618  mov     rcx, [rdx+8]
0x18005561c  cmp     [rdx+10h], rcx
0x180055620  jnz     short loc_180055633
0x180055622  cmp     [rdx+18h], r15b
0x180055626  jz      short loc_18005562D
0x180055628  inc     dword ptr [rbx+20h]
0x18005562b  jmp     short loc_180055653
0x18005562d  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055631  jmp     short loc_180055653
0x180055633  inc     dword ptr [rbx+20h]
0x180055636  inc     qword ptr [rdx+10h]
0x18005563a  mov     rax, [rbx+460h]
0x180055641  mov     rcx, [rax]
0x180055644  mov     [rcx], r9w
0x180055648  mov     rax, [rbx+460h]
0x18005564f  add     qword ptr [rax], 2
0x180055653  add     r14, r8
0x180055656  inc     ebp
0x180055658  cmp     ebp, [rdi]
0x18005565a  jnz     short loc_1800555E5
0x18005565c  jmp     short loc_18005567E
0x18005565e  add     rcx, 460h
0x180055665  lea     r9, [rbx+20h]
0x180055669  mov     rax, [rbx+8]
0x18005566d  mov     [rsp+68h+var_48], rax
0x180055672  mov     r8d, [rdi]
0x180055675  mov     rdx, [rbx+40h]
0x180055679  call    ?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x18005567e  mov     al, 1
0x180055680  mov     rbx, [rsp+68h+arg_8]
0x180055685  add     rsp, 40h
0x180055689  pop     r15
0x18005568b  pop     r14
0x18005568d  pop     rdi
0x18005568e  pop     rsi
0x18005568f  pop     rbp
0x180055690  retn
```
