# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)

- ea: `0x1400374b0`
- end: `0x1400375b4`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z`
- size: `260`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003689c`
- `0x1400370fc`
- `0x14003f96c`
- `0x140044068`

## callees

- `0x140015b64`
- `0x1400374b0`
- `0x140045963`
- `0x1400459ab`
- `0x14004cd80`
- `0x14004d140`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003752d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003752d`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  _QWORD *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
  v7 = a3;
  if ( a2 )
  {
    v8 = 0x7FFFFFFF;
    v9 = a2;
    if ( a3 < 0x7FFFFFFF )
      v8 = a3;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
  }
  if ( a3 == -1 )
    v4 = v7;
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
          memset(v10, 0, 2 * v4 + 2);
          *(_DWORD *)o__errno_0() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memmove(v10, a2, v12);
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
  result = a1;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x1400374b0  mov     rax, rsp
0x1400374b3  mov     [rax+8], rbx
0x1400374b7  mov     [rax+10h], rbp
0x1400374bb  mov     [rax+18h], rsi
0x1400374bf  mov     [rax+20h], rdi
0x1400374c3  push    r12
0x1400374c5  push    r14
0x1400374c7  push    r15
0x1400374c9  sub     rsp, 20h
0x1400374cd  xor     r12d, r12d
0x1400374d0  mov     rsi, r8
0x1400374d3  mov     rbp, rdx
0x1400374d6  mov     r14, rcx
0x1400374d9  test    rdx, rdx
0x1400374dc  jnz     short loc_1400374E8
0x1400374de  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400374e2  jz      loc_1400375A9
0x1400374e8  mov     rbx, rsi
0x1400374eb  test    rbp, rbp
0x1400374ee  jz      short loc_14003751A
0x1400374f0  mov     eax, 7FFFFFFFh
0x1400374f5  mov     rbx, rbp
0x1400374f8  cmp     rsi, rax
0x1400374fb  cmovb   rax, rsi
0x1400374ff  test    rax, rax
0x140037502  jz      short loc_140037514
0x140037504  cmp     [rbx], r12w
0x140037508  jz      short loc_140037514
0x14003750a  add     rbx, 2
0x14003750e  sub     rax, 1
0x140037512  jnz     short loc_140037504
0x140037514  sub     rbx, rbp
0x140037517  sar     rbx, 1
0x14003751a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14003751e  cmovz   rsi, rbx
0x140037522  lea     r15, ds:2[rsi*2]
0x14003752a  mov     rcx, r15; cb
0x14003752d  call    cs:__imp_CoTaskMemAlloc
0x140037533  mov     rdi, rax
0x140037536  test    rax, rax
0x140037539  jz      short loc_140037584
0x14003753b  test    rbp, rbp
0x14003753e  jz      short loc_14003757B
0x140037540  add     rbx, rbx
0x140037543  jz      short loc_140037574
0x140037545  mov     rcx, rax; void *
0x140037548  cmp     r15, rbx
0x14003754b  jb      short loc_14003755A
0x14003754d  mov     r8, rbx; Size
0x140037550  mov     rdx, rbp; Src
0x140037553  call    memmove
0x140037558  jmp     short loc_140037574
0x14003755a  mov     r8, r15; Size
0x14003755d  xor     edx, edx; Val
0x14003755f  call    memset
0x140037564  call    _o__errno_0
0x140037569  mov     dword ptr [rax], 22h ; '"'
0x14003756f  call    _invalid_parameter_noinfo
0x140037574  mov     [rbx+rdi], r12w
0x140037579  jmp     short loc_14003757F
0x14003757b  mov     [rax], r12w
0x14003757f  mov     [rdi+rsi*2], r12w
0x140037584  mov     rbx, [rsp+38h+arg_0]
0x140037589  mov     rax, r14
0x14003758c  mov     rbp, [rsp+38h+arg_8]
0x140037591  mov     rsi, [rsp+38h+arg_10]
0x140037596  mov     [r14], rdi
0x140037599  mov     rdi, [rsp+38h+arg_18]
0x14003759e  add     rsp, 20h
0x1400375a2  pop     r15
0x1400375a4  pop     r14
0x1400375a6  pop     r12
0x1400375a8  retn
0x1400375a9  mov     rcx, [rsp+38h]; this
0x1400375ae  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
