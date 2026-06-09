# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x180051e40`
- end: `0x180051f00`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$stream_output_adapter@_W@__crt_stdio_output@@V?$format_validation_base@_WV?$stream_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180051a20`

## callees

- `0x18001512c`
- `0x180021428`
- `0x180051e40`

## pseudocode

```c
__int64 __fastcall __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>,__crt_stdio_output::format_validation_base<wchar_t,__crt_stdio_output::stream_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(
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
0x180051e40  push    rdi
0x180051e42  sub     rsp, 30h
0x180051e46  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180051e4f  mov     [rsp+38h+arg_0], rbx
0x180051e54  mov     [rsp+38h+arg_8], rsi
0x180051e59  mov     esi, edx
0x180051e5b  mov     rdi, rcx
0x180051e5e  mov     rbx, [rcx+8]
0x180051e62  cmp     byte ptr [rbx+28h], 0
0x180051e66  jnz     short loc_180051E70
0x180051e68  mov     rcx, rbx; this
0x180051e6b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180051e70  mov     r9, [rbx+18h]
0x180051e74  mov     rbx, [rdi+40h]
0x180051e78  cmp     dword ptr [r9+0Ch], 0FDE9h
0x180051e80  jnz     short loc_180051EBF
0x180051e82  xor     edi, edi
0x180051e84  test    esi, esi
0x180051e86  jle     short loc_180051EBB
0x180051e88  cmp     byte ptr [rbx], 0
0x180051e8b  jz      short loc_180051EBB
0x180051e8d  mov     rcx, rbx; this
0x180051e90  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180051e95  movsxd  rdx, eax
0x180051e98  lea     eax, [rdx-1]
0x180051e9b  cmp     eax, 3
0x180051e9e  mov     rax, rdx
0x180051ea1  jbe     short loc_180051EA8
0x180051ea3  mov     eax, 1
0x180051ea8  lea     ecx, [rdi+1]
0x180051eab  cmp     edx, 4
0x180051eae  cmovnz  ecx, edi
0x180051eb1  lea     edi, [rcx+1]
0x180051eb4  add     rbx, rax
0x180051eb7  cmp     edi, esi
0x180051eb9  jl      short loc_180051E88
0x180051ebb  mov     eax, edi
0x180051ebd  jmp     short loc_180051EF0
0x180051ebf  xor     r8d, r8d
0x180051ec2  test    esi, esi
0x180051ec4  jle     short loc_180051EED
0x180051ec6  cmp     byte ptr [rbx], 0
0x180051ec9  jz      short loc_180051EED
0x180051ecb  movzx   ecx, byte ptr [rbx]
0x180051ece  mov     rax, [r9]
0x180051ed1  movzx   edx, word ptr [rax+rcx*2]
0x180051ed5  bt      edx, 0Fh
0x180051ed9  lea     rcx, [rbx+1]
0x180051edd  cmovnb  rcx, rbx
0x180051ee1  lea     rbx, [rcx+1]
0x180051ee5  inc     r8d
0x180051ee8  cmp     r8d, esi
0x180051eeb  jl      short loc_180051EC6
0x180051eed  mov     eax, r8d
0x180051ef0  mov     rbx, [rsp+38h+arg_0]
0x180051ef5  mov     rsi, [rsp+38h+arg_8]
0x180051efa  add     rsp, 30h
0x180051efe  pop     rdi
0x180051eff  retn
```
