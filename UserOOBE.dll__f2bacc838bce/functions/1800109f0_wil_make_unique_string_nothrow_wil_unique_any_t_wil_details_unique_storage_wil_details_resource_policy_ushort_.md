# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800109f0`
- end: `0x180010adf`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e6c`
- `0x18001bd7c`
- `0x180025ca0`
- `0x180026c00`

## callees

- `0x180004156`
- `0x1800041e8`
- `0x180004200`
- `0x18000e24c`
- `0x1800109f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010aa9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010aa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010a72`

## string_xrefs

- `0x180010a1b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800109f0  push    rbx
0x1800109f2  push    rbp
0x1800109f3  push    rsi
0x1800109f4  push    rdi
0x1800109f5  push    r12
0x1800109f7  push    r14
0x1800109f9  push    r15
0x1800109fb  sub     rsp, 20h
0x1800109ff  xor     r12d, r12d
0x180010a02  mov     rbx, r8
0x180010a05  mov     rbp, rdx
0x180010a08  mov     r15, rcx
0x180010a0b  test    rdx, rdx
0x180010a0e  jnz     short loc_180010A32
0x180010a10  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180010a14  jnz     short loc_180010A2D
0x180010a16  mov     rcx, [rsp+58h]; this
0x180010a1b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010a22  mov     edx, 0F89h; void *
0x180010a27  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010a2d  mov     rdi, rbx
0x180010a30  jmp     short loc_180010A67
0x180010a32  mov     ecx, 7FFFFFFFh
0x180010a37  mov     rax, rbx
0x180010a3a  cmp     rbx, rcx
0x180010a3d  mov     rdi, rbp
0x180010a40  cmovnb  rax, rcx
0x180010a44  test    rax, rax
0x180010a47  jz      short loc_180010A59
0x180010a49  cmp     [rdi], r12w
0x180010a4d  jz      short loc_180010A59
0x180010a4f  add     rdi, 2
0x180010a53  sub     rax, 1
0x180010a57  jnz     short loc_180010A49
0x180010a59  sub     rdi, rbp
0x180010a5c  sar     rdi, 1
0x180010a5f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180010a63  cmovz   rbx, rdi
0x180010a67  lea     r14, ds:2[rbx*2]
0x180010a6f  mov     rcx, r14; cb
0x180010a72  call    cs:__imp_CoTaskMemAlloc
0x180010a78  mov     rsi, rax
0x180010a7b  test    rax, rax
0x180010a7e  jz      short loc_180010ACA
0x180010a80  test    rbp, rbp
0x180010a83  jz      short loc_180010AC1
0x180010a85  add     rdi, rdi
0x180010a88  jz      short loc_180010ABA
0x180010a8a  mov     rcx, rax; void *
0x180010a8d  cmp     r14, rdi
0x180010a90  jb      short loc_180010A9F
0x180010a92  mov     r8, rdi; Size
0x180010a95  mov     rdx, rbp; Src
0x180010a98  call    memcpy_0
0x180010a9d  jmp     short loc_180010ABA
0x180010a9f  mov     r8, r14; Size
0x180010aa2  xor     edx, edx; Val
0x180010aa4  call    memset_0
0x180010aa9  call    cs:__imp__o__errno
0x180010aaf  mov     dword ptr [rax], 22h ; '"'
0x180010ab5  call    _invalid_parameter_noinfo
0x180010aba  mov     [rdi+rsi], r12w
0x180010abf  jmp     short loc_180010AC5
0x180010ac1  mov     [rax], r12w
0x180010ac5  mov     [rsi+rbx*2], r12w
0x180010aca  mov     [r15], rsi
0x180010acd  mov     rax, r15
0x180010ad0  add     rsp, 20h
0x180010ad4  pop     r15
0x180010ad6  pop     r14
0x180010ad8  pop     r12
0x180010ada  pop     rdi
0x180010adb  pop     rsi
0x180010adc  pop     rbp
0x180010add  pop     rbx
0x180010ade  retn
```
