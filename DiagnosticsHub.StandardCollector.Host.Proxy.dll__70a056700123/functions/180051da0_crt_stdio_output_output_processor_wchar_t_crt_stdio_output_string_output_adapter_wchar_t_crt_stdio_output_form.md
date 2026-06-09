# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x180051da0`
- end: `0x180051e60`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005192c`

## callees

- `0x1800149cc`
- `0x180020cc8`
- `0x180051da0`

## pseudocode

```c
__int64 __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(
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
0x180051da0  push    rdi
0x180051da2  sub     rsp, 30h
0x180051da6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180051daf  mov     [rsp+38h+arg_0], rbx
0x180051db4  mov     [rsp+38h+arg_8], rsi
0x180051db9  mov     esi, edx
0x180051dbb  mov     rdi, rcx
0x180051dbe  mov     rbx, [rcx+8]
0x180051dc2  cmp     byte ptr [rbx+28h], 0
0x180051dc6  jnz     short loc_180051DD0
0x180051dc8  mov     rcx, rbx; this
0x180051dcb  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180051dd0  mov     r9, [rbx+18h]
0x180051dd4  mov     rbx, [rdi+40h]
0x180051dd8  cmp     dword ptr [r9+0Ch], 0FDE9h
0x180051de0  jnz     short loc_180051E1F
0x180051de2  xor     edi, edi
0x180051de4  test    esi, esi
0x180051de6  jle     short loc_180051E1B
0x180051de8  cmp     byte ptr [rbx], 0
0x180051deb  jz      short loc_180051E1B
0x180051ded  mov     rcx, rbx; this
0x180051df0  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180051df5  movsxd  rdx, eax
0x180051df8  lea     eax, [rdx-1]
0x180051dfb  cmp     eax, 3
0x180051dfe  mov     rax, rdx
0x180051e01  jbe     short loc_180051E08
0x180051e03  mov     eax, 1
0x180051e08  lea     ecx, [rdi+1]
0x180051e0b  cmp     edx, 4
0x180051e0e  cmovnz  ecx, edi
0x180051e11  lea     edi, [rcx+1]
0x180051e14  add     rbx, rax
0x180051e17  cmp     edi, esi
0x180051e19  jl      short loc_180051DE8
0x180051e1b  mov     eax, edi
0x180051e1d  jmp     short loc_180051E50
0x180051e1f  xor     r8d, r8d
0x180051e22  test    esi, esi
0x180051e24  jle     short loc_180051E4D
0x180051e26  cmp     byte ptr [rbx], 0
0x180051e29  jz      short loc_180051E4D
0x180051e2b  movzx   ecx, byte ptr [rbx]
0x180051e2e  mov     rax, [r9]
0x180051e31  movzx   edx, word ptr [rax+rcx*2]
0x180051e35  bt      edx, 0Fh
0x180051e39  lea     rcx, [rbx+1]
0x180051e3d  cmovnb  rcx, rbx
0x180051e41  lea     rbx, [rcx+1]
0x180051e45  inc     r8d
0x180051e48  cmp     r8d, esi
0x180051e4b  jl      short loc_180051E26
0x180051e4d  mov     eax, r8d
0x180051e50  mov     rbx, [rsp+38h+arg_0]
0x180051e55  mov     rsi, [rsp+38h+arg_8]
0x180051e5a  add     rsp, 30h
0x180051e5e  pop     rdi
0x180051e5f  retn
```
