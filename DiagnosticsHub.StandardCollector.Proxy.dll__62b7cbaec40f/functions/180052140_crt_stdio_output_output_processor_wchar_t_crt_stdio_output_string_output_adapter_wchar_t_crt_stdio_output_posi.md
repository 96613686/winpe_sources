# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x180052140`
- end: `0x180052200`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180051ca8`

## callees

- `0x18001512c`
- `0x180021428`
- `0x180052140`

## pseudocode

```c
__int64 __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(
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
0x180052140  push    rdi
0x180052142  sub     rsp, 30h
0x180052146  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18005214f  mov     [rsp+38h+arg_0], rbx
0x180052154  mov     [rsp+38h+arg_8], rsi
0x180052159  mov     esi, edx
0x18005215b  mov     rdi, rcx
0x18005215e  mov     rbx, [rcx+8]
0x180052162  cmp     byte ptr [rbx+28h], 0
0x180052166  jnz     short loc_180052170
0x180052168  mov     rcx, rbx; this
0x18005216b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180052170  mov     r9, [rbx+18h]
0x180052174  mov     rbx, [rdi+40h]
0x180052178  cmp     dword ptr [r9+0Ch], 0FDE9h
0x180052180  jnz     short loc_1800521BF
0x180052182  xor     edi, edi
0x180052184  test    esi, esi
0x180052186  jle     short loc_1800521BB
0x180052188  cmp     byte ptr [rbx], 0
0x18005218b  jz      short loc_1800521BB
0x18005218d  mov     rcx, rbx; this
0x180052190  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180052195  movsxd  rdx, eax
0x180052198  lea     eax, [rdx-1]
0x18005219b  cmp     eax, 3
0x18005219e  mov     rax, rdx
0x1800521a1  jbe     short loc_1800521A8
0x1800521a3  mov     eax, 1
0x1800521a8  lea     ecx, [rdi+1]
0x1800521ab  cmp     edx, 4
0x1800521ae  cmovnz  ecx, edi
0x1800521b1  lea     edi, [rcx+1]
0x1800521b4  add     rbx, rax
0x1800521b7  cmp     edi, esi
0x1800521b9  jl      short loc_180052188
0x1800521bb  mov     eax, edi
0x1800521bd  jmp     short loc_1800521F0
0x1800521bf  xor     r8d, r8d
0x1800521c2  test    esi, esi
0x1800521c4  jle     short loc_1800521ED
0x1800521c6  cmp     byte ptr [rbx], 0
0x1800521c9  jz      short loc_1800521ED
0x1800521cb  movzx   ecx, byte ptr [rbx]
0x1800521ce  mov     rax, [r9]
0x1800521d1  movzx   edx, word ptr [rax+rcx*2]
0x1800521d5  bt      edx, 0Fh
0x1800521d9  lea     rcx, [rbx+1]
0x1800521dd  cmovnb  rcx, rbx
0x1800521e1  lea     rbx, [rcx+1]
0x1800521e5  inc     r8d
0x1800521e8  cmp     r8d, esi
0x1800521eb  jl      short loc_1800521C6
0x1800521ed  mov     eax, r8d
0x1800521f0  mov     rbx, [rsp+38h+arg_0]
0x1800521f5  mov     rsi, [rsp+38h+arg_8]
0x1800521fa  add     rsp, 30h
0x1800521fe  pop     rdi
0x1800521ff  retn
```
