# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x140002168`
- end: `0x1400022dd`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400022e4`

## callees

- `0x140002168`
- `0x1400033f8`
- `0x14000362c`
- `0x1400036d8`
- `0x140006244`
- `0x140007cf4`
- `0x140009696`
- `0x1400096d0`

## string_xrefs

- `0x140002297`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

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
0x140002168  mov     [rsp-8+arg_10], rbx
0x14000216d  mov     [rsp-8+arg_18], rsi
0x140002172  push    rbp
0x140002173  push    rdi
0x140002174  push    r14
0x140002176  lea     rbp, [rsp-150h]
0x14000217e  sub     rsp, 250h
0x140002185  mov     rax, cs:__security_cookie
0x14000218c  xor     rax, rsp
0x14000218f  mov     [rbp+160h+var_20], rax
0x140002196  mov     rsi, rdx
0x140002199  mov     r14, rcx
0x14000219c  mov     qword ptr [rsp+260h+var_240], 0; int
0x1400021a5  xor     edx, edx; Val
0x1400021a7  mov     r8d, 200h; Size
0x1400021ad  lea     rcx, [rsp+260h+var_220]; void *
0x1400021b2  call    memset_0
0x1400021b7  mov     [rsp+260h+var_238], 0
0x1400021c0  lea     r9, [rsp+260h+var_238]
0x1400021c5  mov     edi, 100h
0x1400021ca  mov     r8d, edi
0x1400021cd  lea     rdx, [rsp+260h+var_220]
0x1400021d2  mov     rcx, rsi
0x1400021d5  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1400021da  mov     ebx, eax
0x1400021dc  test    eax, eax
0x1400021de  js      loc_1400022AA
0x1400021e4  mov     rax, [rsp+260h+var_238]
0x1400021e9  cmp     rax, rdi
0x1400021ec  ja      short loc_140002219
0x1400021ee  lea     r8, [rax-1]
0x1400021f2  lea     rdx, [rsp+260h+var_220]
0x1400021f7  lea     rcx, [rsp+260h+var_240]
0x1400021fc  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140002201  mov     ebx, eax
0x140002203  test    eax, eax
0x140002205  jns     short loc_140002212
0x140002207  mov     r9d, eax
0x14000220a  lea     edx, [rdi+6Fh]
0x14000220d  jmp     loc_140002297
0x140002212  mov     rbx, qword ptr [rsp+260h+var_240]
0x140002217  jmp     short loc_140002258
0x140002219  mov     rdi, rax
0x14000221c  lea     r8, [rax-1]
0x140002220  xor     edx, edx
0x140002222  lea     rcx, [rsp+260h+var_240]
0x140002227  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x14000222c  mov     ebx, eax
0x14000222e  test    eax, eax
0x140002230  js      short loc_14000228F
0x140002232  lea     r9, [rsp+260h+var_238]
0x140002237  mov     r8, rdi
0x14000223a  mov     rbx, qword ptr [rsp+260h+var_240]
0x14000223f  mov     rdx, rbx
0x140002242  mov     rcx, rsi
0x140002245  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14000224a  test    eax, eax
0x14000224c  js      short loc_14000228B
0x14000224e  mov     rax, [rsp+260h+var_238]
0x140002253  cmp     rax, rdi
0x140002256  ja      short loc_140002219
0x140002258  mov     [rsp+260h+var_230], rbx
0x14000225d  mov     qword ptr [rsp+260h+var_240], 0
0x140002266  lea     rdx, [rsp+260h+var_230]
0x14000226b  mov     rcx, r14
0x14000226e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x140002273  lea     rcx, [rsp+260h+var_230]
0x140002278  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000227d  lea     rcx, [rsp+260h+var_240]
0x140002282  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140002287  xor     eax, eax
0x140002289  jmp     short loc_1400022B6
0x14000228b  mov     ebx, eax
0x14000228d  jmp     short loc_1400022AA
0x14000228f  mov     r9d, ebx; char *
0x140002292  mov     edx, 17Ah; void *
0x140002297  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000229e  mov     rcx, [rbp+168h]; this
0x1400022a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400022aa  lea     rcx, [rsp+260h+var_240]
0x1400022af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400022b4  mov     eax, ebx
0x1400022b6  mov     rcx, [rbp+160h+var_20]
0x1400022bd  xor     rcx, rsp; StackCookie
0x1400022c0  call    __security_check_cookie
0x1400022c5  lea     r11, [rsp+260h+var_10]
0x1400022cd  mov     rbx, [r11+30h]
0x1400022d1  mov     rsi, [r11+38h]
0x1400022d5  mov     rsp, r11
0x1400022d8  pop     r14
0x1400022da  pop     rdi
0x1400022db  pop     rbp
0x1400022dc  retn
```
