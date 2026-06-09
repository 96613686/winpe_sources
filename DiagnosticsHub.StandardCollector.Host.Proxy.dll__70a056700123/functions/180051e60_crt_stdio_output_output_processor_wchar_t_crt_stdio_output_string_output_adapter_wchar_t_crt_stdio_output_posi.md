# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::positional_parameter_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x180051e60`
- end: `0x180051f20`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$positional_parameter_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800519c8`

## callees

- `0x1800149cc`
- `0x180020cc8`
- `0x180051e60`

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
0x180051e60  push    rdi
0x180051e62  sub     rsp, 30h
0x180051e66  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180051e6f  mov     [rsp+38h+arg_0], rbx
0x180051e74  mov     [rsp+38h+arg_8], rsi
0x180051e79  mov     esi, edx
0x180051e7b  mov     rdi, rcx
0x180051e7e  mov     rbx, [rcx+8]
0x180051e82  cmp     byte ptr [rbx+28h], 0
0x180051e86  jnz     short loc_180051E90
0x180051e88  mov     rcx, rbx; this
0x180051e8b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180051e90  mov     r9, [rbx+18h]
0x180051e94  mov     rbx, [rdi+40h]
0x180051e98  cmp     dword ptr [r9+0Ch], 0FDE9h
0x180051ea0  jnz     short loc_180051EDF
0x180051ea2  xor     edi, edi
0x180051ea4  test    esi, esi
0x180051ea6  jle     short loc_180051EDB
0x180051ea8  cmp     byte ptr [rbx], 0
0x180051eab  jz      short loc_180051EDB
0x180051ead  mov     rcx, rbx; this
0x180051eb0  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180051eb5  movsxd  rdx, eax
0x180051eb8  lea     eax, [rdx-1]
0x180051ebb  cmp     eax, 3
0x180051ebe  mov     rax, rdx
0x180051ec1  jbe     short loc_180051EC8
0x180051ec3  mov     eax, 1
0x180051ec8  lea     ecx, [rdi+1]
0x180051ecb  cmp     edx, 4
0x180051ece  cmovnz  ecx, edi
0x180051ed1  lea     edi, [rcx+1]
0x180051ed4  add     rbx, rax
0x180051ed7  cmp     edi, esi
0x180051ed9  jl      short loc_180051EA8
0x180051edb  mov     eax, edi
0x180051edd  jmp     short loc_180051F10
0x180051edf  xor     r8d, r8d
0x180051ee2  test    esi, esi
0x180051ee4  jle     short loc_180051F0D
0x180051ee6  cmp     byte ptr [rbx], 0
0x180051ee9  jz      short loc_180051F0D
0x180051eeb  movzx   ecx, byte ptr [rbx]
0x180051eee  mov     rax, [r9]
0x180051ef1  movzx   edx, word ptr [rax+rcx*2]
0x180051ef5  bt      edx, 0Fh
0x180051ef9  lea     rcx, [rbx+1]
0x180051efd  cmovnb  rcx, rbx
0x180051f01  lea     rbx, [rcx+1]
0x180051f05  inc     r8d
0x180051f08  cmp     r8d, esi
0x180051f0b  jl      short loc_180051EE6
0x180051f0d  mov     eax, r8d
0x180051f10  mov     rbx, [rsp+38h+arg_0]
0x180051f15  mov     rsi, [rsp+38h+arg_8]
0x180051f1a  add     rsp, 30h
0x180051f1e  pop     rdi
0x180051f1f  retn
```
