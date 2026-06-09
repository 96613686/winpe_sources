# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x180052200`
- end: `0x1800522c0`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180051d5c`

## callees

- `0x18001512c`
- `0x180021428`
- `0x180052200`

## pseudocode

```c
__int64 __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(
        __int64 a1,
        const char *a2)
{
  int v2; // esi
  __int64 v4; // rbx
  __int64 v5; // r9
  __crt_mbstring *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rax
  unsigned int v9; // ecx
  int i; // r8d
  __crt_mbstring *v12; // rcx

  v2 = (int)a2;
  v4 = *(_QWORD *)(a1 + 8);
  if ( !*(_BYTE *)(v4 + 40) )
    __crt_cached_ptd_host::update_locale_slow(*(__crt_cached_ptd_host **)(a1 + 8));
  v5 = *(_QWORD *)(v4 + 24);
  v6 = *(__crt_mbstring **)(a1 + 64);
  if ( *(_DWORD *)(v5 + 12) == 65001 )
  {
    v7 = 0;
    if ( v2 > 0 )
    {
      do
      {
        if ( !*(_BYTE *)v6 )
          break;
        LODWORD(v8) = __crt_mbstring::__mblen_utf8(v6, a2);
        a2 = (const char *)(int)v8;
        v8 = (int)v8;
        if ( (unsigned int)(v8 - 1) > 3 )
          v8 = 1;
        v9 = v7 + 1;
        if ( (_DWORD)a2 != 4 )
          v9 = v7;
        v7 = v9 + 1;
        v6 = (__crt_mbstring *)((char *)v6 + v8);
      }
      while ( (int)(v9 + 1) < v2 );
    }
    return v7;
  }
  else
  {
    for ( i = 0; i < v2; ++i )
    {
      if ( !*(_BYTE *)v6 )
        break;
      v12 = (__crt_mbstring *)((char *)v6 + 1);
      if ( (*(_WORD *)(*(_QWORD *)v5 + 2LL * *(unsigned __int8 *)v6) & 0x8000) == 0 )
        v12 = v6;
      v6 = (__crt_mbstring *)((char *)v12 + 1);
    }
    return (unsigned int)i;
  }
}

```

## disassembly

```asm
0x180052200  push    rdi
0x180052202  sub     rsp, 30h
0x180052206  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18005220f  mov     [rsp+38h+arg_0], rbx
0x180052214  mov     [rsp+38h+arg_8], rsi
0x180052219  mov     esi, edx
0x18005221b  mov     rdi, rcx
0x18005221e  mov     rbx, [rcx+8]
0x180052222  cmp     byte ptr [rbx+28h], 0
0x180052226  jnz     short loc_180052230
0x180052228  mov     rcx, rbx; this
0x18005222b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180052230  mov     r9, [rbx+18h]
0x180052234  mov     rbx, [rdi+40h]
0x180052238  cmp     dword ptr [r9+0Ch], 0FDE9h
0x180052240  jnz     short loc_18005227F
0x180052242  xor     edi, edi
0x180052244  test    esi, esi
0x180052246  jle     short loc_18005227B
0x180052248  cmp     byte ptr [rbx], 0
0x18005224b  jz      short loc_18005227B
0x18005224d  mov     rcx, rbx; this
0x180052250  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180052255  movsxd  rdx, eax
0x180052258  lea     eax, [rdx-1]
0x18005225b  cmp     eax, 3
0x18005225e  mov     rax, rdx
0x180052261  jbe     short loc_180052268
0x180052263  mov     eax, 1
0x180052268  lea     ecx, [rdi+1]
0x18005226b  cmp     edx, 4
0x18005226e  cmovnz  ecx, edi
0x180052271  lea     edi, [rcx+1]
0x180052274  add     rbx, rax
0x180052277  cmp     edi, esi
0x180052279  jl      short loc_180052248
0x18005227b  mov     eax, edi
0x18005227d  jmp     short loc_1800522B0
0x18005227f  xor     r8d, r8d
0x180052282  test    esi, esi
0x180052284  jle     short loc_1800522AD
0x180052286  cmp     byte ptr [rbx], 0
0x180052289  jz      short loc_1800522AD
0x18005228b  movzx   ecx, byte ptr [rbx]
0x18005228e  mov     rax, [r9]
0x180052291  movzx   edx, word ptr [rax+rcx*2]
0x180052295  bt      edx, 0Fh
0x180052299  lea     rcx, [rbx+1]
0x18005229d  cmovnb  rcx, rbx
0x1800522a1  lea     rbx, [rcx+1]
0x1800522a5  inc     r8d
0x1800522a8  cmp     r8d, esi
0x1800522ab  jl      short loc_180052286
0x1800522ad  mov     eax, r8d
0x1800522b0  mov     rbx, [rsp+38h+arg_0]
0x1800522b5  mov     rsi, [rsp+38h+arg_8]
0x1800522ba  add     rsp, 30h
0x1800522be  pop     rdi
0x1800522bf  retn
```
