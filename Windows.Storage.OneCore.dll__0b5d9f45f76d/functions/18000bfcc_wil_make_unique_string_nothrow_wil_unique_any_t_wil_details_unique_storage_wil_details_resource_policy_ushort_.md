# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000bfcc`
- end: `0x18000c0bb`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bf7c`
- `0x18000ca78`
- `0x180011c44`
- `0x180011f68`
- `0x180013284`

## callees

- `0x18000373a`
- `0x1800037c8`
- `0x18000953c`
- `0x18000bfcc`
- `0x180023190`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c085`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c04e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c04e`

## string_xrefs

- `0x18000bff7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000bfcc  push    rbx
0x18000bfce  push    rbp
0x18000bfcf  push    rsi
0x18000bfd0  push    rdi
0x18000bfd1  push    r12
0x18000bfd3  push    r14
0x18000bfd5  push    r15
0x18000bfd7  sub     rsp, 20h
0x18000bfdb  xor     r12d, r12d
0x18000bfde  mov     rbx, r8
0x18000bfe1  mov     rbp, rdx
0x18000bfe4  mov     r15, rcx
0x18000bfe7  test    rdx, rdx
0x18000bfea  jnz     short loc_18000C00E
0x18000bfec  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000bff0  jnz     short loc_18000C009
0x18000bff2  mov     rcx, [rsp+58h]; this
0x18000bff7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bffe  mov     edx, 0F89h; void *
0x18000c003  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000c009  mov     rdi, rbx
0x18000c00c  jmp     short loc_18000C043
0x18000c00e  mov     ecx, 7FFFFFFFh
0x18000c013  mov     rax, rbx
0x18000c016  cmp     rbx, rcx
0x18000c019  mov     rdi, rbp
0x18000c01c  cmovnb  rax, rcx
0x18000c020  test    rax, rax
0x18000c023  jz      short loc_18000C035
0x18000c025  cmp     [rdi], r12w
0x18000c029  jz      short loc_18000C035
0x18000c02b  add     rdi, 2
0x18000c02f  sub     rax, 1
0x18000c033  jnz     short loc_18000C025
0x18000c035  sub     rdi, rbp
0x18000c038  sar     rdi, 1
0x18000c03b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c03f  cmovz   rbx, rdi
0x18000c043  lea     r14, ds:2[rbx*2]
0x18000c04b  mov     rcx, r14; cb
0x18000c04e  call    cs:__imp_CoTaskMemAlloc
0x18000c054  mov     rsi, rax
0x18000c057  test    rax, rax
0x18000c05a  jz      short loc_18000C0A6
0x18000c05c  test    rbp, rbp
0x18000c05f  jz      short loc_18000C09D
0x18000c061  add     rdi, rdi
0x18000c064  jz      short loc_18000C096
0x18000c066  mov     rcx, rax; void *
0x18000c069  cmp     r14, rdi
0x18000c06c  jb      short loc_18000C07B
0x18000c06e  mov     r8, rdi; Size
0x18000c071  mov     rdx, rbp; Src
0x18000c074  call    memcpy_0
0x18000c079  jmp     short loc_18000C096
0x18000c07b  mov     r8, r14; Size
0x18000c07e  xor     edx, edx; Val
0x18000c080  call    memset_0
0x18000c085  call    cs:__imp__o__errno
0x18000c08b  mov     dword ptr [rax], 22h ; '"'
0x18000c091  call    _invalid_parameter_noinfo
0x18000c096  mov     [rdi+rsi], r12w
0x18000c09b  jmp     short loc_18000C0A1
0x18000c09d  mov     [rax], r12w
0x18000c0a1  mov     [rsi+rbx*2], r12w
0x18000c0a6  mov     [r15], rsi
0x18000c0a9  mov     rax, r15
0x18000c0ac  add     rsp, 20h
0x18000c0b0  pop     r15
0x18000c0b2  pop     r14
0x18000c0b4  pop     r12
0x18000c0b6  pop     rdi
0x18000c0b7  pop     rsi
0x18000c0b8  pop     rbp
0x18000c0b9  pop     rbx
0x18000c0ba  retn
```
