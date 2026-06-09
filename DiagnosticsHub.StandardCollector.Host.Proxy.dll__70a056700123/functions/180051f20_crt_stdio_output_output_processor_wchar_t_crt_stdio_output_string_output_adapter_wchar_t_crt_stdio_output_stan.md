# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x180051f20`
- end: `0x180051fe0`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180051a7c`

## callees

- `0x1800149cc`
- `0x180020cc8`
- `0x180051f20`

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
0x180051f20  push    rdi
0x180051f22  sub     rsp, 30h
0x180051f26  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180051f2f  mov     [rsp+38h+arg_0], rbx
0x180051f34  mov     [rsp+38h+arg_8], rsi
0x180051f39  mov     esi, edx
0x180051f3b  mov     rdi, rcx
0x180051f3e  mov     rbx, [rcx+8]
0x180051f42  cmp     byte ptr [rbx+28h], 0
0x180051f46  jnz     short loc_180051F50
0x180051f48  mov     rcx, rbx; this
0x180051f4b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180051f50  mov     r9, [rbx+18h]
0x180051f54  mov     rbx, [rdi+40h]
0x180051f58  cmp     dword ptr [r9+0Ch], 0FDE9h
0x180051f60  jnz     short loc_180051F9F
0x180051f62  xor     edi, edi
0x180051f64  test    esi, esi
0x180051f66  jle     short loc_180051F9B
0x180051f68  cmp     byte ptr [rbx], 0
0x180051f6b  jz      short loc_180051F9B
0x180051f6d  mov     rcx, rbx; this
0x180051f70  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x180051f75  movsxd  rdx, eax
0x180051f78  lea     eax, [rdx-1]
0x180051f7b  cmp     eax, 3
0x180051f7e  mov     rax, rdx
0x180051f81  jbe     short loc_180051F88
0x180051f83  mov     eax, 1
0x180051f88  lea     ecx, [rdi+1]
0x180051f8b  cmp     edx, 4
0x180051f8e  cmovnz  ecx, edi
0x180051f91  lea     edi, [rcx+1]
0x180051f94  add     rbx, rax
0x180051f97  cmp     edi, esi
0x180051f99  jl      short loc_180051F68
0x180051f9b  mov     eax, edi
0x180051f9d  jmp     short loc_180051FD0
0x180051f9f  xor     r8d, r8d
0x180051fa2  test    esi, esi
0x180051fa4  jle     short loc_180051FCD
0x180051fa6  cmp     byte ptr [rbx], 0
0x180051fa9  jz      short loc_180051FCD
0x180051fab  movzx   ecx, byte ptr [rbx]
0x180051fae  mov     rax, [r9]
0x180051fb1  movzx   edx, word ptr [rax+rcx*2]
0x180051fb5  bt      edx, 0Fh
0x180051fb9  lea     rcx, [rbx+1]
0x180051fbd  cmovnb  rcx, rbx
0x180051fc1  lea     rbx, [rcx+1]
0x180051fc5  inc     r8d
0x180051fc8  cmp     r8d, esi
0x180051fcb  jl      short loc_180051FA6
0x180051fcd  mov     eax, r8d
0x180051fd0  mov     rbx, [rsp+38h+arg_0]
0x180051fd5  mov     rsi, [rsp+38h+arg_8]
0x180051fda  add     rsp, 30h
0x180051fde  pop     rdi
0x180051fdf  retn
```
