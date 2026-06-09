# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x1400021bc`
- end: `0x140002332`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140002338`

## callees

- `0x1400021bc`
- `0x140003450`
- `0x1400036c0`
- `0x140003770`
- `0x1400065e4`
- `0x14000812c`
- `0x140009cc6`
- `0x140009d00`

## string_xrefs

- `0x1400022eb`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rax
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rbx
  unsigned __int64 v10; // rdi
  int v11; // eax
  int v13[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *(_QWORD *)v13 = 0;
  memset_0(v16, 0, sizeof(v16));
  v14 = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v16, 256, &v14);
  if ( v4 < 0 )
    goto LABEL_13;
  v5 = v14;
  if ( v14 > 0x100 )
  {
    while ( 1 )
    {
      v10 = v5;
      v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             v13,
             0,
             v5 - 1);
      if ( v4 < 0 )
        break;
      v9 = *(_QWORD *)v13;
      v11 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
              a2,
              *(_QWORD *)v13,
              v10,
              &v14);
      if ( v11 < 0 )
      {
        v4 = v11;
        goto LABEL_13;
      }
      v5 = v14;
      if ( v14 <= v10 )
        goto LABEL_9;
    }
    v7 = (unsigned int)v4;
    v8 = 378;
    goto LABEL_12;
  }
  v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         v13,
         v16,
         v14 - 1);
  v4 = v6;
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 367;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)v7,
      v13[0]);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
    return (unsigned int)v4;
  }
  v9 = *(_QWORD *)v13;
LABEL_9:
  v15[0] = v9;
  *(_QWORD *)v13 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
  return 0;
}

```

## disassembly

```asm
0x1400021bc  mov     [rsp-8+arg_10], rbx
0x1400021c1  mov     [rsp-8+arg_18], rsi
0x1400021c6  push    rbp
0x1400021c7  push    rdi
0x1400021c8  push    r14
0x1400021ca  lea     rbp, [rsp-150h]
0x1400021d2  sub     rsp, 250h
0x1400021d9  mov     rax, cs:__security_cookie
0x1400021e0  xor     rax, rsp
0x1400021e3  mov     [rbp+160h+var_20], rax
0x1400021ea  mov     rsi, rdx
0x1400021ed  mov     r14, rcx
0x1400021f0  mov     qword ptr [rsp+260h+var_240], 0; int
0x1400021f9  xor     edx, edx; Val
0x1400021fb  mov     r8d, 200h; Size
0x140002201  lea     rcx, [rsp+260h+var_220]; void *
0x140002206  call    memset_0
0x14000220b  mov     [rsp+260h+var_238], 0
0x140002214  lea     r9, [rsp+260h+var_238]
0x140002219  mov     edi, 100h
0x14000221e  mov     r8d, edi
0x140002221  lea     rdx, [rsp+260h+var_220]
0x140002226  mov     rcx, rsi
0x140002229  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14000222e  mov     ebx, eax
0x140002230  test    eax, eax
0x140002232  js      loc_1400022FE
0x140002238  mov     rax, [rsp+260h+var_238]
0x14000223d  cmp     rax, rdi
0x140002240  ja      short loc_14000226D
0x140002242  lea     r8, [rax-1]
0x140002246  lea     rdx, [rsp+260h+var_220]
0x14000224b  lea     rcx, [rsp+260h+var_240]
0x140002250  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140002255  mov     ebx, eax
0x140002257  test    eax, eax
0x140002259  jns     short loc_140002266
0x14000225b  mov     r9d, eax
0x14000225e  lea     edx, [rdi+6Fh]
0x140002261  jmp     loc_1400022EB
0x140002266  mov     rbx, qword ptr [rsp+260h+var_240]
0x14000226b  jmp     short loc_1400022AC
0x14000226d  mov     rdi, rax
0x140002270  lea     r8, [rax-1]
0x140002274  xor     edx, edx
0x140002276  lea     rcx, [rsp+260h+var_240]
0x14000227b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140002280  mov     ebx, eax
0x140002282  test    eax, eax
0x140002284  js      short loc_1400022E3
0x140002286  lea     r9, [rsp+260h+var_238]
0x14000228b  mov     r8, rdi
0x14000228e  mov     rbx, qword ptr [rsp+260h+var_240]
0x140002293  mov     rdx, rbx
0x140002296  mov     rcx, rsi
0x140002299  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14000229e  test    eax, eax
0x1400022a0  js      short loc_1400022DF
0x1400022a2  mov     rax, [rsp+260h+var_238]
0x1400022a7  cmp     rax, rdi
0x1400022aa  ja      short loc_14000226D
0x1400022ac  mov     [rsp+260h+var_230], rbx
0x1400022b1  mov     qword ptr [rsp+260h+var_240], 0
0x1400022ba  lea     rdx, [rsp+260h+var_230]
0x1400022bf  mov     rcx, r14
0x1400022c2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1400022c7  lea     rcx, [rsp+260h+var_230]
0x1400022cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400022d1  lea     rcx, [rsp+260h+var_240]
0x1400022d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400022db  xor     eax, eax
0x1400022dd  jmp     short loc_14000230A
0x1400022df  mov     ebx, eax
0x1400022e1  jmp     short loc_1400022FE
0x1400022e3  mov     r9d, ebx; char *
0x1400022e6  mov     edx, 17Ah; void *
0x1400022eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400022f2  mov     rcx, [rbp+168h]; this
0x1400022f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400022fe  lea     rcx, [rsp+260h+var_240]
0x140002303  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140002308  mov     eax, ebx
0x14000230a  mov     rcx, [rbp+160h+var_20]
0x140002311  xor     rcx, rsp; StackCookie
0x140002314  call    __security_check_cookie
0x140002319  lea     r11, [rsp+260h+var_10]
0x140002321  mov     rbx, [r11+30h]
0x140002325  mov     rsi, [r11+38h]
0x140002329  mov     rsp, r11
0x14000232c  pop     r14
0x14000232e  pop     rdi
0x14000232f  pop     rbp
0x140002330  retn
```
