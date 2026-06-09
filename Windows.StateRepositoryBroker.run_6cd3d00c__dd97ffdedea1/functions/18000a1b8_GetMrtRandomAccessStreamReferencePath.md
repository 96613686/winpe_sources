# GetMrtRandomAccessStreamReferencePath

- ea: `0x18000a1b8`
- end: `0x18000a3ce`
- name: `GetMrtRandomAccessStreamReferencePath`
- size: `534`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000a54c`

## callees

- `0x180001d60`
- `0x180002154`
- `0x180002bdc`
- `0x180006224`
- `0x1800064f8`
- `0x180009874`
- `0x180009900`
- `0x18000a158`
- `0x18000a1b8`
- `0x18000a61c`
- `0x18000a678`

## import_xrefs

- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18000a27c`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18000a2eb`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18000a27c`
- `ext-ms-win-mrmcorer-resmanager-l1-1-0!ResourceManagerQueueGetString` at `0x18000a2eb`

## string_xrefs

- `0x18000a2fc`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x18000a380`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`

## pseudocode

```c
__int64 __fastcall GetMrtRandomAccessStreamReferencePath(unsigned __int16 *a1, __int64 a2, __int64 *a3)
{
  float v3; // xmm7_4
  float v5; // xmm6_4
  const unsigned __int16 *v7; // r15
  int v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  int String; // edi
  unsigned __int64 v12; // rax
  _BYTE *v13; // rbx
  _BYTE *v14; // r14
  void *v15; // rcx
  __int64 v17; // rdx
  int v18; // [rsp+28h] [rbp-E0h]
  int v19; // [rsp+28h] [rbp-E0h]
  __int64 v20; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 v21[16]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v22[528]; // [rsp+68h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D0h] [rbp+1C8h]

  v3 = *(float *)&a2;
  v5 = *((float *)&a2 + 1);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a3,
    0);
  v7 = FileUriToFilenameIfNecessary(a1);
  v8 = StringCchPrintfW(v21, 0xBu, L"%u", (unsigned int)(int)fmaxf(v3, v5));
  if ( v8 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v9, v10, (const char *)(unsigned int)v8, v18);
  v19 = 260;
  String = ResourceManagerQueueGetString(v7, L"TargetSize", v21, v22);
  if ( String == -2147024774 )
  {
    v12 = 0;
    if ( !is_mul_ok(0, 2u) )
      v12 = -1;
    v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v13 )
    {
      String = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
        (const char *)0x8007000ELL,
        260);
      v15 = 0;
LABEL_9:
      operator delete(v15);
      return (unsigned int)String;
    }
    operator delete(0);
    v19 = 0;
    v14 = v13;
    String = ResourceManagerQueueGetString(v7, L"TargetSize", v21, v13);
  }
  else
  {
    v13 = 0;
    v14 = v22;
  }
  if ( String < 0 )
  {
    v17 = 181;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
      (const char *)(unsigned int)String,
      v19);
    v15 = v13;
    goto LABEL_9;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v20,
    v14);
  if ( a3 != &v20 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a3,
      v20);
    v20 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  if ( !*a3 )
  {
    String = -2147024882;
    v17 = 184;
    goto LABEL_17;
  }
  operator delete(v13);
  return 0;
}

```

## disassembly

```asm
0x18000a1b8  mov     rax, rsp
0x18000a1bb  mov     [rax+20h], rbx
0x18000a1bf  push    rbp
0x18000a1c0  push    rsi
0x18000a1c1  push    rdi
0x18000a1c2  push    r14
0x18000a1c4  push    r15
0x18000a1c6  lea     rbp, [rax-1C8h]
0x18000a1cd  sub     rsp, 2A0h
0x18000a1d4  movaps  xmmword ptr [rax-38h], xmm6
0x18000a1d8  movaps  xmmword ptr [rax-48h], xmm7
0x18000a1dc  mov     rax, cs:__security_cookie
0x18000a1e3  xor     rax, rsp
0x18000a1e6  mov     [rbp+1C0h+var_50], rax
0x18000a1ed  movq    xmm7, rdx
0x18000a1f2  mov     rbx, rcx
0x18000a1f5  movsd   [rsp+2C0h+var_290], xmm7
0x18000a1fb  xor     edx, edx
0x18000a1fd  movss   xmm6, dword ptr [rsp+2C0h+var_290+4]
0x18000a203  mov     rcx, r8
0x18000a206  mov     rsi, r8
0x18000a209  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000a20e  mov     rcx, rbx; unsigned __int16 *
0x18000a211  call    ?FileUriToFilenameIfNecessary@@YAPEBGPEBG@Z; FileUriToFilenameIfNecessary(ushort const *)
0x18000a216  maxss   xmm7, xmm6
0x18000a21a  mov     edx, 0Bh; unsigned __int64
0x18000a21f  lea     r8, aU; "%u"
0x18000a226  mov     r15, rax
0x18000a229  lea     rcx, [rsp+2C0h+var_280]; unsigned __int16 *
0x18000a22e  cvttss2si r9, xmm7
0x18000a233  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a238  test    eax, eax
0x18000a23a  jns     short loc_18000A24C
0x18000a23c  mov     rcx, [rbp+1C8h]; this
0x18000a243  mov     r9d, eax; char *
0x18000a246  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a24c  lea     rax, [rsp+2C0h+var_290]
0x18000a251  mov     [rsp+2C0h+var_290], 0
0x18000a25a  mov     [rsp+2C0h+var_298], rax
0x18000a25f  lea     r9, [rsp+2C0h+var_260]
0x18000a264  lea     r8, [rsp+2C0h+var_280]
0x18000a269  mov     qword ptr [rsp+2C0h+var_2A0], 104h; int
0x18000a272  lea     rdx, aTargetsize; "TargetSize"
0x18000a279  mov     rcx, r15
0x18000a27c  call    cs:__imp_ResourceManagerQueueGetString
0x18000a282  mov     edi, eax
0x18000a284  cmp     eax, 8007007Ah
0x18000a289  jnz     loc_18000A320
0x18000a28f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a296  mov     eax, 2
0x18000a29b  mul     [rsp+2C0h+var_290]
0x18000a2a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a2a7  cmovb   rax, rcx
0x18000a2ab  mov     rcx, rax; unsigned __int64
0x18000a2ae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a2b3  mov     rbx, rax
0x18000a2b6  test    rax, rax
0x18000a2b9  jz      short loc_18000A2F5
0x18000a2bb  xor     ecx, ecx; Block
0x18000a2bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a2c2  lea     rax, [rsp+2C0h+var_290]
0x18000a2c7  mov     r9, rbx
0x18000a2ca  mov     [rsp+2C0h+var_298], rax
0x18000a2cf  lea     r8, [rsp+2C0h+var_280]
0x18000a2d4  mov     rax, [rsp+2C0h+var_290]
0x18000a2d9  lea     rdx, aTargetsize; "TargetSize"
0x18000a2e0  mov     rcx, r15
0x18000a2e3  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18000a2e8  mov     r14, rbx
0x18000a2eb  call    cs:__imp_ResourceManagerQueueGetString
0x18000a2f1  mov     edi, eax
0x18000a2f3  jmp     short loc_18000A327
0x18000a2f5  mov     rcx, [rbp+1C8h]; this
0x18000a2fc  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18000a303  mov     edi, 8007000Eh
0x18000a308  mov     edx, 0B1h; void *
0x18000a30d  mov     r9d, edi; char *
0x18000a310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a315  xor     ecx, ecx; Block
0x18000a317  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a31c  mov     eax, edi
0x18000a31e  jmp     short loc_18000A39E
0x18000a320  xor     ebx, ebx
0x18000a322  lea     r14, [rsp+2C0h+var_260]
0x18000a327  test    edi, edi
0x18000a329  jns     short loc_18000A332
0x18000a32b  mov     edx, 0B5h
0x18000a330  jmp     short loc_18000A379
0x18000a332  mov     rdx, r14
0x18000a335  lea     rcx, [rsp+2C0h+var_288]
0x18000a33a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000a33f  lea     rax, [rsp+2C0h+var_288]
0x18000a344  cmp     rsi, rax
0x18000a347  jz      short loc_18000A35F
0x18000a349  mov     rdx, [rsp+2C0h+var_288]
0x18000a34e  mov     rcx, rsi
0x18000a351  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000a356  mov     [rsp+2C0h+var_288], 0
0x18000a35f  lea     rcx, [rsp+2C0h+var_288]
0x18000a364  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000a369  cmp     qword ptr [rsi], 0
0x18000a36d  jnz     short loc_18000A394
0x18000a36f  mov     edi, 8007000Eh
0x18000a374  mov     edx, 0B8h; void *
0x18000a379  mov     rcx, [rbp+1C8h]; this
0x18000a380  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18000a387  mov     r9d, edi; char *
0x18000a38a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a38f  mov     rcx, rbx
0x18000a392  jmp     short loc_18000A317
0x18000a394  mov     rcx, rbx; Block
0x18000a397  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a39c  xor     eax, eax
0x18000a39e  mov     rcx, [rbp+1C0h+var_50]
0x18000a3a5  xor     rcx, rsp; StackCookie
0x18000a3a8  call    __security_check_cookie
0x18000a3ad  lea     r11, [rsp+2C0h+var_20]
0x18000a3b5  mov     rbx, [r11+48h]
0x18000a3b9  movaps  xmm6, xmmword ptr [r11-10h]
0x18000a3be  movaps  xmm7, xmmword ptr [r11-20h]
0x18000a3c3  mov     rsp, r11
0x18000a3c6  pop     r15
0x18000a3c8  pop     r14
0x18000a3ca  pop     rdi
0x18000a3cb  pop     rsi
0x18000a3cc  pop     rbp
0x18000a3cd  retn
```
