# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001550c`
- end: `0x1800155ff`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `243`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a8bc`
- `0x1800296c0`

## callees

- `0x180002b9a`
- `0x180002c04`
- `0x180003da9`
- `0x18001550c`
- `0x180019390`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800155b2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800155b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001557b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001557b`

## string_xrefs

- `0x1800155ed`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x18001550c  push    rbx
0x18001550e  push    rbp
0x18001550f  push    rsi
0x180015510  push    rdi
0x180015511  push    r12
0x180015513  push    r14
0x180015515  push    r15
0x180015517  sub     rsp, 20h
0x18001551b  xor     r12d, r12d
0x18001551e  mov     rbx, r8
0x180015521  mov     rbp, rdx
0x180015524  mov     r15, rcx
0x180015527  test    rdx, rdx
0x18001552a  jnz     short loc_18001553B
0x18001552c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180015530  jz      loc_1800155E8
0x180015536  mov     rdi, rbx
0x180015539  jmp     short loc_180015570
0x18001553b  mov     ecx, 7FFFFFFFh
0x180015540  mov     rax, rbx
0x180015543  cmp     rbx, rcx
0x180015546  mov     rdi, rbp
0x180015549  cmovnb  rax, rcx
0x18001554d  test    rax, rax
0x180015550  jz      short loc_180015562
0x180015552  cmp     [rdi], r12w
0x180015556  jz      short loc_180015562
0x180015558  add     rdi, 2
0x18001555c  sub     rax, 1
0x180015560  jnz     short loc_180015552
0x180015562  sub     rdi, rbp
0x180015565  sar     rdi, 1
0x180015568  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001556c  cmovz   rbx, rdi
0x180015570  lea     r14, ds:2[rbx*2]
0x180015578  mov     rcx, r14; cb
0x18001557b  call    cs:__imp_CoTaskMemAlloc
0x180015581  mov     rsi, rax
0x180015584  test    rax, rax
0x180015587  jz      short loc_1800155D3
0x180015589  test    rbp, rbp
0x18001558c  jz      short loc_1800155CA
0x18001558e  add     rdi, rdi
0x180015591  jz      short loc_1800155C3
0x180015593  mov     rcx, rax; void *
0x180015596  cmp     r14, rdi
0x180015599  jb      short loc_1800155A8
0x18001559b  mov     r8, rdi; Size
0x18001559e  mov     rdx, rbp; Src
0x1800155a1  call    memcpy_0
0x1800155a6  jmp     short loc_1800155C3
0x1800155a8  mov     r8, r14; Size
0x1800155ab  xor     edx, edx; Val
0x1800155ad  call    memset_0
0x1800155b2  call    cs:__imp__o__errno
0x1800155b8  mov     dword ptr [rax], 22h ; '"'
0x1800155be  call    _invalid_parameter_noinfo
0x1800155c3  mov     [rdi+rsi], r12w
0x1800155c8  jmp     short loc_1800155CE
0x1800155ca  mov     [rax], r12w
0x1800155ce  mov     [rsi+rbx*2], r12w
0x1800155d3  mov     [r15], rsi
0x1800155d6  mov     rax, r15
0x1800155d9  add     rsp, 20h
0x1800155dd  pop     r15
0x1800155df  pop     r14
0x1800155e1  pop     r12
0x1800155e3  pop     rdi
0x1800155e4  pop     rsi
0x1800155e5  pop     rbp
0x1800155e6  pop     rbx
0x1800155e7  retn
0x1800155e8  mov     rcx, [rsp+58h]; this
0x1800155ed  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800155f4  mov     edx, 0F89h; void *
0x1800155f9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
