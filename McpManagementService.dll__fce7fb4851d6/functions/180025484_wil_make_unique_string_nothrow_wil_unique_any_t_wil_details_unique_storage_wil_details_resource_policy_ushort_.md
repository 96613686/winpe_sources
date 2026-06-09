# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180025484`
- end: `0x18002553a`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `182`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800268a0`

## callees

- `0x180004552`
- `0x1800045c0`
- `0x1800045d8`
- `0x18000e0f4`
- `0x180025484`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025511`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800254df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800254df`

## string_xrefs

- `0x1800254a4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v6;
  }
  while ( v6 );
  v8 = 2 * ((v7 - a2) >> 1);
  v9 = v8 + 2;
  v10 = (char *)CoTaskMemAlloc(v8 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( v8 )
    {
      if ( v9 < v8 )
      {
        memset_0(v10, 0, v9);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, a2, v8);
      }
    }
    *(_WORD *)&v11[v8] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x180025484  push    rbx
0x180025486  push    rbp
0x180025487  push    rsi
0x180025488  push    rdi
0x180025489  push    r14
0x18002548b  push    r15
0x18002548d  sub     rsp, 28h
0x180025491  xor     r15d, r15d
0x180025494  mov     rsi, rdx
0x180025497  mov     r14, rcx
0x18002549a  test    rdx, rdx
0x18002549d  jnz     short loc_1800254B6
0x18002549f  mov     rcx, [rsp+58h]; this
0x1800254a4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800254ab  mov     edx, 0F89h; void *
0x1800254b0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800254b6  mov     ecx, 7FFFFFFFh
0x1800254bb  mov     rax, rsi
0x1800254be  cmp     [rax], r15w
0x1800254c2  jz      short loc_1800254CE
0x1800254c4  add     rax, 2
0x1800254c8  sub     rcx, 1
0x1800254cc  jnz     short loc_1800254BE
0x1800254ce  sub     rax, rsi
0x1800254d1  sar     rax, 1
0x1800254d4  lea     rbx, [rax+rax]
0x1800254d8  lea     rbp, [rbx+2]
0x1800254dc  mov     rcx, rbp; cb
0x1800254df  call    cs:__imp_CoTaskMemAlloc
0x1800254e5  mov     rdi, rax
0x1800254e8  test    rax, rax
0x1800254eb  jz      short loc_180025527
0x1800254ed  test    rbx, rbx
0x1800254f0  jz      short loc_180025522
0x1800254f2  mov     rcx, rax; void *
0x1800254f5  cmp     rbp, rbx
0x1800254f8  jb      short loc_180025507
0x1800254fa  mov     r8, rbx; Size
0x1800254fd  mov     rdx, rsi; Src
0x180025500  call    memcpy_0
0x180025505  jmp     short loc_180025522
0x180025507  mov     r8, rbp; Size
0x18002550a  xor     edx, edx; Val
0x18002550c  call    memset_0
0x180025511  call    cs:__imp__o__errno
0x180025517  mov     dword ptr [rax], 22h ; '"'
0x18002551d  call    _invalid_parameter_noinfo
0x180025522  mov     [rbx+rdi], r15w
0x180025527  mov     [r14], rdi
0x18002552a  mov     rax, r14
0x18002552d  add     rsp, 28h
0x180025531  pop     r15
0x180025533  pop     r14
0x180025535  pop     rdi
0x180025536  pop     rsi
0x180025537  pop     rbp
0x180025538  pop     rbx
0x180025539  retn
```
