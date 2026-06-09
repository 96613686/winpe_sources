# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x180060464`
- end: `0x18006060a`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800105d4`
- `0x180011150`

## callees

- `0x180012930`
- `0x1800326e0`
- `0x18004789c`
- `0x18005d488`
- `0x180060464`
- `0x18006c000`
- `0x18006cad0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060526`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060526`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800605db`

## string_xrefs

- `0x18006050a`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x1800605bf`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

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
0x180060464  mov     [rsp-8+arg_10], rbx
0x180060469  push    rbp
0x18006046a  push    rsi
0x18006046b  push    rdi
0x18006046c  push    r14
0x18006046e  push    r15
0x180060470  lea     rbp, [rsp-140h]
0x180060478  sub     rsp, 240h
0x18006047f  mov     rax, cs:__security_cookie
0x180060486  xor     rax, rsp
0x180060489  mov     [rbp+160h+var_30], rax
0x180060490  mov     r14, rdx
0x180060493  mov     r15, rcx
0x180060496  mov     [rsp+260h+pv], 0; int
0x18006049f  xor     edx, edx; Val
0x1800604a1  mov     r8d, 200h; Size
0x1800604a7  lea     rcx, [rsp+260h+var_230]; void *
0x1800604ac  call    memset_0
0x1800604b1  mov     [rsp+260h+var_238], 0
0x1800604ba  lea     r9, [rsp+260h+var_238]
0x1800604bf  mov     ebx, 100h
0x1800604c4  mov     r8d, ebx
0x1800604c7  lea     rdx, [rsp+260h+var_230]
0x1800604cc  mov     rcx, r14
0x1800604cf  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1800604d4  test    eax, eax
0x1800604d6  jns     short loc_1800604DD
0x1800604d8  jmp     loc_1800605E4
0x1800604dd  mov     rax, [rsp+260h+var_238]
0x1800604e2  cmp     rax, rbx
0x1800604e5  ja      short loc_180060539
0x1800604e7  lea     r8, [rax-1]
0x1800604eb  lea     rdx, [rsp+260h+var_230]
0x1800604f0  lea     rcx, [rsp+260h+pv]
0x1800604f5  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x1800604fa  mov     ebx, eax
0x1800604fc  test    eax, eax
0x1800604fe  jns     short loc_180060532
0x180060500  mov     rcx, [rbp+168h]; this
0x180060507  mov     r9d, eax; char *
0x18006050a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180060511  mov     edx, 16Fh; void *
0x180060516  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006051b  nop
0x18006051c  mov     rcx, [rsp+260h+pv]; pv
0x180060521  test    rcx, rcx
0x180060524  jz      short loc_18006052D
0x180060526  call    cs:__imp_CoTaskMemFree
0x18006052c  nop
0x18006052d  jmp     loc_1800605E2
0x180060532  mov     rbx, [rsp+260h+pv]
0x180060537  jmp     short loc_18006057A
0x180060539  mov     rdi, rax
0x18006053c  lea     r8, [rax-1]
0x180060540  xor     edx, edx
0x180060542  lea     rcx, [rsp+260h+pv]
0x180060547  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18006054c  mov     ebx, eax
0x18006054e  test    eax, eax
0x180060550  js      short loc_1800605B5
0x180060552  lea     r9, [rsp+260h+var_238]
0x180060557  mov     r8, rdi
0x18006055a  mov     rbx, [rsp+260h+pv]
0x18006055f  mov     rdx, rbx
0x180060562  mov     rcx, r14
0x180060565  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18006056a  mov     esi, eax
0x18006056c  test    eax, eax
0x18006056e  js      short loc_1800605A2
0x180060570  mov     rax, [rsp+260h+var_238]
0x180060575  cmp     rax, rdi
0x180060578  ja      short loc_180060539
0x18006057a  mov     [rsp+260h+pv], rbx
0x18006057f  lea     rdx, [rsp+260h+pv]
0x180060584  mov     rcx, r15
0x180060587  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18006058c  nop
0x18006058d  mov     rcx, [rsp+260h+pv]; pv
0x180060592  test    rcx, rcx
0x180060595  jz      short loc_18006059E
0x180060597  call    cs:__imp_CoTaskMemFree
0x18006059d  nop
0x18006059e  xor     eax, eax
0x1800605a0  jmp     short loc_1800605E4
0x1800605a2  test    rbx, rbx
0x1800605a5  jz      short loc_1800605B1
0x1800605a7  mov     rcx, rbx; pv
0x1800605aa  call    cs:__imp_CoTaskMemFree
0x1800605b0  nop
0x1800605b1  mov     eax, esi
0x1800605b3  jmp     short loc_1800605E4
0x1800605b5  mov     rcx, [rbp+168h]; this
0x1800605bc  mov     r9d, ebx; char *
0x1800605bf  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800605c6  mov     edx, 17Ah; void *
0x1800605cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800605d0  nop
0x1800605d1  mov     rcx, [rsp+260h+pv]; pv
0x1800605d6  test    rcx, rcx
0x1800605d9  jz      short loc_1800605E2
0x1800605db  call    cs:__imp_CoTaskMemFree
0x1800605e1  nop
0x1800605e2  mov     eax, ebx
0x1800605e4  mov     rcx, [rbp+160h+var_30]
0x1800605eb  xor     rcx, rsp; StackCookie
0x1800605ee  call    __security_check_cookie
0x1800605f3  mov     rbx, [rsp+260h+arg_10]
0x1800605fb  add     rsp, 240h
0x180060602  pop     r15
0x180060604  pop     r14
0x180060606  pop     rdi
0x180060607  pop     rsi
0x180060608  pop     rbp
0x180060609  retn
```
