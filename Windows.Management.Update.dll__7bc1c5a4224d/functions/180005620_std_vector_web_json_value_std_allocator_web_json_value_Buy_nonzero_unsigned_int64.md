# std::vector<web::json::value,std::allocator<web::json::value>>::_Buy_nonzero(unsigned __int64)

- ea: `0x180005620`
- end: `0x1800056af`
- name: `?_Buy_nonzero@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_K@Z`
- size: `143`
- prototype: `char *__fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005880`
- `0x180005c40`

## callees

- `0x180002cfc`
- `0x180005620`
- `0x180005860`
- `0x18001c7f4`

## pseudocode

```c
char *__fastcall std::vector<web::json::value>::_Buy_nonzero(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  _QWORD *v4; // rax
  void *v5; // rax
  void *v6; // rcx
  char *result; // rax

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v3 = 8 * a2;
  if ( 8 * a2 )
  {
    if ( v3 < 0x1000 )
    {
      v4 = operator new(8 * a2);
    }
    else
    {
      if ( v3 + 39 < v3 )
        __scrt_throw_std_bad_array_new_length();
      v5 = operator new(v3 + 39);
      v6 = v5;
      if ( !v5 )
        __fastfail(5u);
      v4 = (_QWORD *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v4 - 1) = v6;
    }
  }
  else
  {
    v4 = 0;
  }
  *a1 = v4;
  a1[1] = v4;
  result = (char *)&v4[v3 / 8];
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x180005620  push    rdi
0x180005622  sub     rsp, 20h
0x180005626  mov     rax, 1FFFFFFFFFFFFFFFh
0x180005630  mov     rdi, rcx
0x180005633  cmp     rdx, rax
0x180005636  ja      short loc_1800056A3
0x180005638  mov     [rsp+28h+arg_0], rbx
0x18000563d  lea     rbx, ds:0[rdx*8]
0x180005645  test    rbx, rbx
0x180005648  jnz     short loc_18000564E
0x18000564a  xor     eax, eax
0x18000564c  jmp     short loc_18000568A
0x18000564e  cmp     rbx, 1000h
0x180005655  jb      short loc_180005682
0x180005657  lea     rcx, [rbx+27h]; Size
0x18000565b  cmp     rcx, rbx
0x18000565e  jbe     short loc_1800056A9
0x180005660  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005665  mov     rcx, rax
0x180005668  test    rax, rax
0x18000566b  jnz     short loc_180005674
0x18000566d  mov     ecx, 5
0x180005672  int     29h; Win8: RtlFailFast(ecx)
0x180005674  add     rax, 27h ; '''
0x180005678  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000567c  mov     [rax-8], rcx
0x180005680  jmp     short loc_18000568A
0x180005682  mov     rcx, rbx; Size
0x180005685  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000568a  mov     [rdi], rax
0x18000568d  mov     [rdi+8], rax
0x180005691  add     rax, rbx
0x180005694  mov     rbx, [rsp+28h+arg_0]
0x180005699  mov     [rdi+10h], rax
0x18000569d  add     rsp, 20h
0x1800056a1  pop     rdi
0x1800056a2  retn
0x1800056a3  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x1800056a9  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
