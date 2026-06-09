# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x18002ea78`
- end: `0x18002ec1e`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015580`
- `0x1800156e0`

## callees

- `0x18000a384`
- `0x1800149f8`
- `0x180015064`
- `0x180024b88`
- `0x18002ea78`
- `0x180031960`
- `0x1800327f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002eb3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ebef`

## string_xrefs

- `0x18002eb1e`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x18002ebd3`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rbx
  unsigned __int64 v9; // rdi
  int v10; // eax
  int v11; // esi
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v14[512]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  pv = 0;
  memset_0(v14, 0, sizeof(v14));
  v13 = 0;
  result = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v14, 256, &v13);
  if ( (int)result >= 0 )
  {
    v5 = v13;
    if ( v13 > 0x100 )
    {
      while ( 1 )
      {
        v9 = v5;
        v10 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
                &pv,
                0,
                v5 - 1);
        v7 = v10;
        if ( v10 < 0 )
          break;
        v8 = pv;
        v11 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v9, &v13);
        if ( v11 < 0 )
        {
          if ( v8 )
            CoTaskMemFree(v8);
          return (unsigned int)v11;
        }
        v5 = v13;
        if ( v13 <= v9 )
          goto LABEL_11;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v10,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      return v7;
    }
    v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
           &pv,
           v14,
           v13 - 1);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v6,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      return v7;
    }
    v8 = pv;
LABEL_11:
    pv = v8;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002ea78  mov     [rsp-8+arg_10], rbx
0x18002ea7d  push    rbp
0x18002ea7e  push    rsi
0x18002ea7f  push    rdi
0x18002ea80  push    r14
0x18002ea82  push    r15
0x18002ea84  lea     rbp, [rsp-140h]
0x18002ea8c  sub     rsp, 240h
0x18002ea93  mov     rax, cs:__security_cookie
0x18002ea9a  xor     rax, rsp
0x18002ea9d  mov     [rbp+160h+var_30], rax
0x18002eaa4  mov     r14, rdx
0x18002eaa7  mov     r15, rcx
0x18002eaaa  mov     [rsp+260h+pv], 0; int
0x18002eab3  xor     edx, edx; Val
0x18002eab5  mov     r8d, 200h; Size
0x18002eabb  lea     rcx, [rsp+260h+var_230]; void *
0x18002eac0  call    memset_0
0x18002eac5  mov     [rsp+260h+var_238], 0
0x18002eace  lea     r9, [rsp+260h+var_238]
0x18002ead3  mov     ebx, 100h
0x18002ead8  mov     r8d, ebx
0x18002eadb  lea     rdx, [rsp+260h+var_230]
0x18002eae0  mov     rcx, r14
0x18002eae3  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18002eae8  test    eax, eax
0x18002eaea  jns     short loc_18002EAF1
0x18002eaec  jmp     loc_18002EBF8
0x18002eaf1  mov     rax, [rsp+260h+var_238]
0x18002eaf6  cmp     rax, rbx
0x18002eaf9  ja      short loc_18002EB4D
0x18002eafb  lea     r8, [rax-1]
0x18002eaff  lea     rdx, [rsp+260h+var_230]
0x18002eb04  lea     rcx, [rsp+260h+pv]
0x18002eb09  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18002eb0e  mov     ebx, eax
0x18002eb10  test    eax, eax
0x18002eb12  jns     short loc_18002EB46
0x18002eb14  mov     rcx, [rbp+168h]; this
0x18002eb1b  mov     r9d, eax; char *
0x18002eb1e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002eb25  mov     edx, 16Fh; void *
0x18002eb2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eb2f  nop
0x18002eb30  mov     rcx, [rsp+260h+pv]; pv
0x18002eb35  test    rcx, rcx
0x18002eb38  jz      short loc_18002EB41
0x18002eb3a  call    cs:__imp_CoTaskMemFree
0x18002eb40  nop
0x18002eb41  jmp     loc_18002EBF6
0x18002eb46  mov     rbx, [rsp+260h+pv]
0x18002eb4b  jmp     short loc_18002EB8E
0x18002eb4d  mov     rdi, rax
0x18002eb50  lea     r8, [rax-1]
0x18002eb54  xor     edx, edx
0x18002eb56  lea     rcx, [rsp+260h+pv]
0x18002eb5b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18002eb60  mov     ebx, eax
0x18002eb62  test    eax, eax
0x18002eb64  js      short loc_18002EBC9
0x18002eb66  lea     r9, [rsp+260h+var_238]
0x18002eb6b  mov     r8, rdi
0x18002eb6e  mov     rbx, [rsp+260h+pv]
0x18002eb73  mov     rdx, rbx
0x18002eb76  mov     rcx, r14
0x18002eb79  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18002eb7e  mov     esi, eax
0x18002eb80  test    eax, eax
0x18002eb82  js      short loc_18002EBB6
0x18002eb84  mov     rax, [rsp+260h+var_238]
0x18002eb89  cmp     rax, rdi
0x18002eb8c  ja      short loc_18002EB4D
0x18002eb8e  mov     [rsp+260h+pv], rbx
0x18002eb93  lea     rdx, [rsp+260h+pv]
0x18002eb98  mov     rcx, r15
0x18002eb9b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002eba0  nop
0x18002eba1  mov     rcx, [rsp+260h+pv]; pv
0x18002eba6  test    rcx, rcx
0x18002eba9  jz      short loc_18002EBB2
0x18002ebab  call    cs:__imp_CoTaskMemFree
0x18002ebb1  nop
0x18002ebb2  xor     eax, eax
0x18002ebb4  jmp     short loc_18002EBF8
0x18002ebb6  test    rbx, rbx
0x18002ebb9  jz      short loc_18002EBC5
0x18002ebbb  mov     rcx, rbx; pv
0x18002ebbe  call    cs:__imp_CoTaskMemFree
0x18002ebc4  nop
0x18002ebc5  mov     eax, esi
0x18002ebc7  jmp     short loc_18002EBF8
0x18002ebc9  mov     rcx, [rbp+168h]; this
0x18002ebd0  mov     r9d, ebx; char *
0x18002ebd3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ebda  mov     edx, 17Ah; void *
0x18002ebdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ebe4  nop
0x18002ebe5  mov     rcx, [rsp+260h+pv]; pv
0x18002ebea  test    rcx, rcx
0x18002ebed  jz      short loc_18002EBF6
0x18002ebef  call    cs:__imp_CoTaskMemFree
0x18002ebf5  nop
0x18002ebf6  mov     eax, ebx
0x18002ebf8  mov     rcx, [rbp+160h+var_30]
0x18002ebff  xor     rcx, rsp; StackCookie
0x18002ec02  call    __security_check_cookie
0x18002ec07  mov     rbx, [rsp+260h+arg_10]
0x18002ec0f  add     rsp, 240h
0x18002ec16  pop     r15
0x18002ec18  pop     r14
0x18002ec1a  pop     rdi
0x18002ec1b  pop     rsi
0x18002ec1c  pop     rbp
0x18002ec1d  retn
```
