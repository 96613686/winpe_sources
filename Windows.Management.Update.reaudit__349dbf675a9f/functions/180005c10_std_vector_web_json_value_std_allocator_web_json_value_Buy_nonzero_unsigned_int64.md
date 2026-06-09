# std::vector<web::json::value,std::allocator<web::json::value>>::_Buy_nonzero(unsigned __int64)

- ea: `0x180005c10`
- end: `0x180005c9f`
- name: `?_Buy_nonzero@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_K@Z`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005e60`
- `0x180006230`

## callees

- `0x180002cac`
- `0x180005c10`
- `0x180005e40`
- `0x18001da08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005c62`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005c62`

## pseudocode

```c
char *__fastcall std::vector<web::json::value>::_Buy_nonzero(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  void *v4; // rax
  __int64 v5; // rdx
  void *v6; // rcx
  _QWORD *v7; // rax
  char *result; // rax

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v3 = 8 * a2;
  if ( 8 * a2 < 0x1000 )
  {
    if ( v3 )
      v7 = operator new(8 * a2);
    else
      v7 = 0;
  }
  else
  {
    if ( v3 + 39 < v3 )
      __scrt_throw_std_bad_array_new_length();
    v4 = operator new(v3 + 39);
    v6 = v4;
    if ( !v4 )
    {
      _o__invalid_parameter_noinfo_noreturn(0, v5);
      __debugbreak();
    }
    v7 = (_QWORD *)(((unsigned __int64)v4 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v7 - 1) = v6;
  }
  *a1 = v7;
  a1[1] = v7;
  result = (char *)&v7[v3 / 8];
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x180005c10  push    rdi
0x180005c12  sub     rsp, 20h
0x180005c16  mov     rax, 1FFFFFFFFFFFFFFFh
0x180005c20  mov     rdi, rcx
0x180005c23  cmp     rdx, rax
0x180005c26  ja      short loc_180005C93
0x180005c28  mov     [rsp+28h+arg_0], rbx
0x180005c2d  lea     rbx, ds:0[rdx*8]
0x180005c35  cmp     rbx, 1000h
0x180005c3c  jb      short loc_180005C69
0x180005c3e  lea     rcx, [rbx+27h]; Size
0x180005c42  cmp     rcx, rbx
0x180005c45  jbe     short loc_180005C99
0x180005c47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c4c  mov     rcx, rax
0x180005c4f  test    rax, rax
0x180005c52  jz      short loc_180005C62
0x180005c54  add     rax, 27h ; '''
0x180005c58  and     rax, 0FFFFFFFFFFFFFFE0h
0x180005c5c  mov     [rax-8], rcx
0x180005c60  jmp     short loc_180005C7A
0x180005c62  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180005c68  int     3; Trap to Debugger
0x180005c69  test    rbx, rbx
0x180005c6c  jz      short loc_180005C78
0x180005c6e  mov     rcx, rbx; Size
0x180005c71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c76  jmp     short loc_180005C7A
0x180005c78  xor     eax, eax
0x180005c7a  mov     [rdi], rax
0x180005c7d  mov     [rdi+8], rax
0x180005c81  add     rax, rbx
0x180005c84  mov     rbx, [rsp+28h+arg_0]
0x180005c89  mov     [rdi+10h], rax
0x180005c8d  add     rsp, 20h
0x180005c91  pop     rdi
0x180005c92  retn
0x180005c93  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x180005c99  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
