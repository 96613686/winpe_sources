# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::_Tidy(void)

- ea: `0x180005cb0`
- end: `0x180005d7f`
- name: `?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAXXZ`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180005420`
- `0x180005aa0`

## callees

- `0x180002c74`
- `0x180005cb0`
- `0x18001da30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005d78`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005d78`

## pseudocode

```c
__int64 __fastcall std::vector<std::pair<std::wstring,web::json::value>>::_Tidy(_QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *i; // rsi
  __int64 v4; // rcx
  _QWORD *v5; // r8
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 result; // rax

  v1 = (_QWORD *)*a1;
  if ( *a1 )
  {
    for ( i = (_QWORD *)a1[1]; v1 != i; v1 += 5 )
    {
      v4 = v1[4];
      if ( v4 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 192LL))(v4, 1);
      std::wstring::_Tidy_deallocate(v1);
    }
    v5 = (_QWORD *)*a1;
    v6 = 40 * ((a1[2] - *a1) / 40LL);
    if ( v6 >= 0x1000 )
    {
      v7 = *(v5 - 1);
      v8 = v6 + 39;
      if ( (unsigned __int64)v5 - v7 - 8 > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v7, v8);
        JUMPOUT(0x180005D7ELL);
      }
      v5 = (_QWORD *)*(v5 - 1);
    }
    operator delete(v5);
    result = 0;
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005cb0  mov     [rsp+arg_8], rbx
0x180005cb5  push    rdi
0x180005cb6  sub     rsp, 20h
0x180005cba  mov     rbx, [rcx]
0x180005cbd  mov     rdi, rcx
0x180005cc0  test    rbx, rbx
0x180005cc3  jz      loc_180005D6D
0x180005cc9  mov     [rsp+28h+arg_0], rsi
0x180005cce  mov     rsi, [rcx+8]
0x180005cd2  cmp     rbx, rsi
0x180005cd5  jz      short loc_180005D05
0x180005cd7  mov     rcx, [rbx+20h]
0x180005cdb  test    rcx, rcx
0x180005cde  jz      short loc_180005CF4
0x180005ce0  mov     rax, [rcx]
0x180005ce3  mov     edx, 1
0x180005ce8  mov     rax, [rax+0C0h]
0x180005cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf4  mov     rcx, rbx
0x180005cf7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180005cfc  add     rbx, 28h ; '('
0x180005d00  cmp     rbx, rsi
0x180005d03  jnz     short loc_180005CD7
0x180005d05  mov     r8, [rdi]
0x180005d08  mov     rax, 6666666666666667h
0x180005d12  mov     rcx, [rdi+10h]
0x180005d16  mov     rsi, [rsp+28h+arg_0]
0x180005d1b  sub     rcx, r8
0x180005d1e  imul    rcx
0x180005d21  sar     rdx, 4
0x180005d25  mov     rax, rdx
0x180005d28  shr     rax, 3Fh
0x180005d2c  add     rdx, rax
0x180005d2f  lea     rdx, [rdx+rdx*4]
0x180005d33  shl     rdx, 3
0x180005d37  cmp     rdx, 1000h
0x180005d3e  jb      short loc_180005D58
0x180005d40  mov     rcx, [r8-8]
0x180005d44  add     rdx, 27h ; '''; unsigned __int64
0x180005d48  sub     r8, rcx
0x180005d4b  lea     rax, [r8-8]
0x180005d4f  cmp     rax, 1Fh
0x180005d53  ja      short loc_180005D78
0x180005d55  mov     r8, rcx
0x180005d58  mov     rcx, r8; void *
0x180005d5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005d60  xor     eax, eax
0x180005d62  mov     [rdi], rax
0x180005d65  mov     [rdi+8], rax
0x180005d69  mov     [rdi+10h], rax
0x180005d6d  mov     rbx, [rsp+28h+arg_8]
0x180005d72  add     rsp, 20h
0x180005d76  pop     rdi
0x180005d77  retn
0x180005d78  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
```
