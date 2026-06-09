# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x180051c20`
- end: `0x180051ce0`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800517dc`

## callees

- `0x1800149cc`
- `0x180020cc8`
- `0x180051c20`

## pseudocode

```c
__int64 __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(
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
0x180051c20  push    rdi
0x180051c22  sub     rsp, 30h
0x180051c26  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180051c2f  mov     [rsp+38h+arg_0], rbx
0x180051c34  mov     [rsp+38h+arg_8], rsi
0x180051c39  mov     esi, edx
0x180051c3b  mov     rdi, rcx
0x180051c3e  mov     rbx, [rcx+8]
0x180051c42  cmp     byte ptr [rbx+28h], 0
0x180051c46  jnz     short loc_180051C50
0x180051c48  mov     rcx, rbx; this
0x180051c4b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180051c50  mov     r9, [rbx+18h]
0x180051c54  mov     rbx, [rdi+40h]
0x180051c58  cmp     dword ptr [r9+0Ch], 0FDE9h
0x180051c60  jnz     short loc_180051C9F
0x180051c62  xor     edi, edi
0x180051c64  test    esi, esi
0x180051c66  jle     short loc_180051C9B
0x180051c68  cmp     byte ptr [rbx], 0
0x180051c6b  jz      short loc_180051C9B
0x180051c6d  mov     rcx, rbx; this
0x180051c70  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180051c75  movsxd  rdx, eax
0x180051c78  lea     eax, [rdx-1]
0x180051c7b  cmp     eax, 3
0x180051c7e  mov     rax, rdx
0x180051c81  jbe     short loc_180051C88
0x180051c83  mov     eax, 1
0x180051c88  lea     ecx, [rdi+1]
0x180051c8b  cmp     edx, 4
0x180051c8e  cmovnz  ecx, edi
0x180051c91  lea     edi, [rcx+1]
0x180051c94  add     rbx, rax
0x180051c97  cmp     edi, esi
0x180051c99  jl      short loc_180051C68
0x180051c9b  mov     eax, edi
0x180051c9d  jmp     short loc_180051CD0
0x180051c9f  xor     r8d, r8d
0x180051ca2  test    esi, esi
0x180051ca4  jle     short loc_180051CCD
0x180051ca6  cmp     byte ptr [rbx], 0
0x180051ca9  jz      short loc_180051CCD
0x180051cab  movzx   ecx, byte ptr [rbx]
0x180051cae  mov     rax, [r9]
0x180051cb1  movzx   edx, word ptr [rax+rcx*2]
0x180051cb5  bt      edx, 0Fh
0x180051cb9  lea     rcx, [rbx+1]
0x180051cbd  cmovnb  rcx, rbx
0x180051cc1  lea     rbx, [rcx+1]
0x180051cc5  inc     r8d
0x180051cc8  cmp     r8d, esi
0x180051ccb  jl      short loc_180051CA6
0x180051ccd  mov     eax, r8d
0x180051cd0  mov     rbx, [rsp+38h+arg_0]
0x180051cd5  mov     rsi, [rsp+38h+arg_8]
0x180051cda  add     rsp, 30h
0x180051cde  pop     rdi
0x180051cdf  retn
```
