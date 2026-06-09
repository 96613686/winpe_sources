# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::write_stored_string_tchar(wchar_t)

- ea: `0x180055180`
- end: `0x1800553b1`
- name: `?write_stored_string_tchar@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAA_N_W@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800149cc`
- `0x18001b18c`
- `0x18001b4b0`
- `0x180055180`
- `0x180055910`

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
0x180055180  push    rbp
0x180055182  push    rsi
0x180055183  push    rdi
0x180055184  push    r14
0x180055186  push    r15
0x180055188  sub     rsp, 40h
0x18005518c  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x180055195  mov     [rsp+68h+arg_8], rbx
0x18005519a  mov     rbx, rcx
0x18005519d  lea     rdi, [rcx+48h]
0x1800551a1  xor     r15d, r15d
0x1800551a4  cmp     [rcx+4Ch], r15b
0x1800551a8  jnz     loc_18005537E
0x1800551ae  cmp     [rdi], r15d
0x1800551b1  jle     loc_18005537E
0x1800551b7  mov     rsi, [rcx+8]
0x1800551bb  cmp     [rsi+28h], r15b
0x1800551bf  jnz     short loc_1800551C9
0x1800551c1  mov     rcx, rsi; this
0x1800551c4  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800551c9  mov     rax, [rsi+18h]
0x1800551cd  cmp     dword ptr [rax+0Ch], 0FDE9h
0x1800551d4  jnz     loc_1800552E3
0x1800551da  mov     rax, [rbx+40h]
0x1800551de  mov     [rsp+68h+arg_18], rax
0x1800551e6  mov     [rsp+68h+arg_10], r15
0x1800551ee  mov     esi, r15d
0x1800551f1  cmp     [rdi], r15d
0x1800551f4  jz      loc_18005539E
0x1800551fa  mov     [rsp+68h+arg_0], r15d
0x1800551ff  mov     rax, [rbx+8]
0x180055203  mov     [rsp+68h+var_48], rax; struct _Mbstatet *
0x180055208  lea     r9, [rsp+68h+arg_10]; unsigned __int64
0x180055210  mov     r8d, 2; char **
0x180055216  lea     rdx, [rsp+68h+arg_18]; wchar_t *
0x18005521e  lea     rcx, [rsp+68h+arg_0]; this
0x180055223  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x180055228  mov     rdx, rax
0x18005522b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005522f  jz      loc_1800552DA
0x180055235  movzx   r8d, word ptr [rsp+68h+arg_0]
0x18005523b  mov     rcx, [rbx+460h]
0x180055242  mov     rax, [rcx+8]
0x180055246  cmp     [rcx+10h], rax
0x18005524a  jnz     short loc_18005525D
0x18005524c  cmp     [rcx+18h], r15b
0x180055250  jz      short loc_180055257
0x180055252  inc     dword ptr [rbx+20h]
0x180055255  jmp     short loc_18005527D
0x180055257  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x18005525b  jmp     short loc_18005527D
0x18005525d  inc     dword ptr [rbx+20h]
0x180055260  inc     qword ptr [rcx+10h]
0x180055264  mov     rax, [rbx+460h]
0x18005526b  mov     rcx, [rax]
0x18005526e  mov     [rcx], r8w
0x180055272  mov     rax, [rbx+460h]
0x180055279  add     qword ptr [rax], 2
0x18005527d  cmp     rdx, 2
0x180055281  jnz     short loc_1800552CB
0x180055283  movzx   edx, word ptr [rsp+68h+arg_0+2]
0x180055288  mov     rcx, [rbx+460h]
0x18005528f  mov     rax, [rcx+8]
0x180055293  cmp     [rcx+10h], rax
0x180055297  jnz     short loc_1800552AA
0x180055299  cmp     [rcx+18h], r15b
0x18005529d  jz      short loc_1800552A4
0x18005529f  inc     dword ptr [rbx+20h]
0x1800552a2  jmp     short loc_1800552C9
0x1800552a4  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800552a8  jmp     short loc_1800552C9
0x1800552aa  inc     dword ptr [rbx+20h]
0x1800552ad  inc     qword ptr [rcx+10h]
0x1800552b1  mov     rax, [rbx+460h]
0x1800552b8  mov     rcx, [rax]
0x1800552bb  mov     [rcx], dx
0x1800552be  mov     rax, [rbx+460h]
0x1800552c5  add     qword ptr [rax], 2
0x1800552c9  inc     esi
0x1800552cb  inc     esi
0x1800552cd  cmp     esi, [rdi]
0x1800552cf  jnz     loc_1800551FA
0x1800552d5  jmp     loc_18005539E
0x1800552da  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x1800552de  jmp     loc_18005539E
0x1800552e3  mov     rsi, [rbx+8]
0x1800552e7  cmp     [rsi+28h], r15b
0x1800552eb  jnz     short loc_1800552F5
0x1800552ed  mov     rcx, rsi; this
0x1800552f0  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800552f5  mov     r14, [rbx+40h]
0x1800552f9  mov     ebp, r15d
0x1800552fc  cmp     [rdi], r15d
0x1800552ff  jz      loc_18005539E
0x180055305  mov     word ptr [rsp+68h+arg_0], r15w
0x18005530b  mov     rax, [rsi+18h]
0x18005530f  movsxd  r8, dword ptr [rax+8]; char *
0x180055313  mov     r9, [rbx+8]; __crt_cached_ptd_host *
0x180055317  mov     rdx, r14; wchar_t *
0x18005531a  lea     rcx, [rsp+68h+arg_0]; this
0x18005531f  call    _mbtowc_internal
0x180055324  movsxd  r8, eax
0x180055327  test    eax, eax
0x180055329  jle     short loc_1800552DA
0x18005532b  movzx   r9d, word ptr [rsp+68h+arg_0]
0x180055331  mov     rdx, [rbx+460h]
0x180055338  mov     rcx, [rdx+8]
0x18005533c  cmp     [rdx+10h], rcx
0x180055340  jnz     short loc_180055353
0x180055342  cmp     [rdx+18h], r15b
0x180055346  jz      short loc_18005534D
0x180055348  inc     dword ptr [rbx+20h]
0x18005534b  jmp     short loc_180055373
0x18005534d  or      dword ptr [rbx+20h], 0FFFFFFFFh
0x180055351  jmp     short loc_180055373
0x180055353  inc     dword ptr [rbx+20h]
0x180055356  inc     qword ptr [rdx+10h]
0x18005535a  mov     rax, [rbx+460h]
0x180055361  mov     rcx, [rax]
0x180055364  mov     [rcx], r9w
0x180055368  mov     rax, [rbx+460h]
0x18005536f  add     qword ptr [rax], 2
0x180055373  add     r14, r8
0x180055376  inc     ebp
0x180055378  cmp     ebp, [rdi]
0x18005537a  jnz     short loc_180055305
0x18005537c  jmp     short loc_18005539E
0x18005537e  add     rcx, 460h
0x180055385  lea     r9, [rbx+20h]
0x180055389  mov     rax, [rbx+8]
0x18005538d  mov     [rsp+68h+var_48], rax
0x180055392  mov     r8d, [rdi]
0x180055395  mov     rdx, [rbx+40h]
0x180055399  call    ?write_string@?$string_output_adapter@_W@__crt_stdio_output@@QEBAXQEB_WHQEAHAEAV__crt_cached_ptd_host@@@Z; __crt_stdio_output::string_output_adapter<wchar_t>::write_string(wchar_t const * const,int,int * const,__crt_cached_ptd_host &)
0x18005539e  mov     al, 1
0x1800553a0  mov     rbx, [rsp+68h+arg_8]
0x1800553a5  add     rsp, 40h
0x1800553a9  pop     r15
0x1800553ab  pop     r14
0x1800553ad  pop     rdi
0x1800553ae  pop     rsi
0x1800553af  pop     rbp
0x1800553b0  retn
```
