# __crt_stdio_output::output_processor<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>,__crt_stdio_output::standard_base<wchar_t,__crt_stdio_output::string_output_adapter<wchar_t>>>::type_case_s_compute_narrow_string_length(int,wchar_t)

- ea: `0x140010578`
- end: `0x140010638`
- name: `?type_case_s_compute_narrow_string_length@?$output_processor@_WV?$string_output_adapter@_W@__crt_stdio_output@@V?$standard_base@_WV?$string_output_adapter@_W@__crt_stdio_output@@@2@@__crt_stdio_output@@AEAAHH_W@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400104dc`

## callees

- `0x14000c750`
- `0x140010578`
- `0x140015448`

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
0x140010578  push    rdi
0x14001057a  sub     rsp, 30h
0x14001057e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140010587  mov     [rsp+38h+arg_0], rbx
0x14001058c  mov     [rsp+38h+arg_8], rsi
0x140010591  mov     esi, edx
0x140010593  mov     rdi, rcx
0x140010596  mov     rbx, [rcx+8]
0x14001059a  cmp     byte ptr [rbx+28h], 0
0x14001059e  jnz     short loc_1400105A8
0x1400105a0  mov     rcx, rbx; this
0x1400105a3  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1400105a8  mov     r9, [rbx+18h]
0x1400105ac  mov     rbx, [rdi+40h]
0x1400105b0  cmp     dword ptr [r9+0Ch], 0FDE9h
0x1400105b8  jnz     short loc_1400105F7
0x1400105ba  xor     edi, edi
0x1400105bc  test    esi, esi
0x1400105be  jle     short loc_1400105F3
0x1400105c0  cmp     byte ptr [rbx], 0
0x1400105c3  jz      short loc_1400105F3
0x1400105c5  mov     rcx, rbx; this
0x1400105c8  call    ?__mblen_utf8@__crt_mbstring@@YAHPEBD@Z; __crt_mbstring::__mblen_utf8(char const *)
0x1400105cd  movsxd  rdx, eax
0x1400105d0  lea     eax, [rdx-1]
0x1400105d3  cmp     eax, 3
0x1400105d6  mov     rax, rdx
0x1400105d9  jbe     short loc_1400105E0
0x1400105db  mov     eax, 1
0x1400105e0  lea     ecx, [rdi+1]
0x1400105e3  cmp     edx, 4
0x1400105e6  cmovnz  ecx, edi
0x1400105e9  lea     edi, [rcx+1]
0x1400105ec  add     rbx, rax
0x1400105ef  cmp     edi, esi
0x1400105f1  jl      short loc_1400105C0
0x1400105f3  mov     eax, edi
0x1400105f5  jmp     short loc_140010628
0x1400105f7  xor     r8d, r8d
0x1400105fa  test    esi, esi
0x1400105fc  jle     short loc_140010625
0x1400105fe  cmp     byte ptr [rbx], 0
0x140010601  jz      short loc_140010625
0x140010603  movzx   ecx, byte ptr [rbx]
0x140010606  mov     rax, [r9]
0x140010609  movzx   edx, word ptr [rax+rcx*2]
0x14001060d  bt      edx, 0Fh
0x140010611  lea     rcx, [rbx+1]
0x140010615  cmovnb  rcx, rbx
0x140010619  lea     rbx, [rcx+1]
0x14001061d  inc     r8d
0x140010620  cmp     r8d, esi
0x140010623  jl      short loc_1400105FE
0x140010625  mov     eax, r8d
0x140010628  mov     rbx, [rsp+38h+arg_0]
0x14001062d  mov     rsi, [rsp+38h+arg_8]
0x140010632  add     rsp, 30h
0x140010636  pop     rdi
0x140010637  retn
```
