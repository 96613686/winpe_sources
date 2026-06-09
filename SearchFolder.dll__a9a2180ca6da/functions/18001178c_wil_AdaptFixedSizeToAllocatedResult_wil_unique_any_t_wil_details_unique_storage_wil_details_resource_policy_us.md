# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x18001178c`
- end: `0x180011908`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018d80`

## callees

- `0x1800033d0`
- `0x180005ffc`
- `0x180006218`
- `0x180006900`
- `0x1800076dc`
- `0x18001178c`
- `0x180013014`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800118aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800118d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800118aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800118d9`

## string_xrefs

- `0x1800118bc`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v4; // rax
  int v5; // ebx
  __int64 v6; // rdx
  void *v7; // rbx
  unsigned __int64 v8; // rdi
  int v9; // esi
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v11; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v12[512]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  pv = 0;
  memset_0(v12, 0, sizeof(v12));
  v11 = 0;
  result = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v12, 256, &v11);
  if ( (int)result >= 0 )
  {
    v4 = v11;
    if ( v11 > 0x100 )
    {
      while ( 1 )
      {
        v8 = v4;
        v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v4 - 1);
        if ( v5 < 0 )
        {
          v6 = 378;
          goto LABEL_16;
        }
        v7 = pv;
        v9 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v8, &v11);
        if ( v9 < 0 )
          break;
        v4 = v11;
        if ( v11 <= v8 )
          goto LABEL_9;
      }
      if ( v7 )
        CoTaskMemFree(v7);
      return (unsigned int)v9;
    }
    else
    {
      v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
             &pv,
             v12,
             v11 - 1);
      if ( v5 >= 0 )
      {
        v7 = pv;
LABEL_9:
        pv = v7;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &qword_18006A6C8,
          &pv);
        if ( pv )
          CoTaskMemFree(pv);
        return 0;
      }
      else
      {
        v6 = 367;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
          (const char *)(unsigned int)v5,
          (int)pv);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001178c  mov     [rsp-8+arg_0], rbx
0x180011791  mov     [rsp-8+arg_10], rsi
0x180011796  push    rbp
0x180011797  push    rdi
0x180011798  push    r14
0x18001179a  lea     rbp, [rsp-140h]
0x1800117a2  sub     rsp, 240h
0x1800117a9  mov     rax, cs:__security_cookie
0x1800117b0  xor     rax, rsp
0x1800117b3  mov     [rbp+150h+var_20], rax
0x1800117ba  mov     r14, rdx
0x1800117bd  mov     [rsp+250h+pv], 0; int
0x1800117c6  xor     edx, edx; Val
0x1800117c8  mov     r8d, 200h; Size
0x1800117ce  lea     rcx, [rsp+250h+var_220]; void *
0x1800117d3  call    memset_0
0x1800117d8  mov     [rsp+250h+var_228], 0
0x1800117e1  lea     r9, [rsp+250h+var_228]
0x1800117e6  mov     ebx, 100h
0x1800117eb  mov     r8d, ebx
0x1800117ee  lea     rdx, [rsp+250h+var_220]
0x1800117f3  mov     rcx, r14
0x1800117f6  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1800117fb  test    eax, eax
0x1800117fd  js      loc_1800118E1
0x180011803  mov     rax, [rsp+250h+var_228]
0x180011808  cmp     rax, rbx
0x18001180b  ja      short loc_180011837
0x18001180d  lea     r8, [rax-1]
0x180011811  lea     rdx, [rsp+250h+var_220]
0x180011816  lea     rcx, [rsp+250h+pv]
0x18001181b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180011820  mov     ebx, eax
0x180011822  test    eax, eax
0x180011824  jns     short loc_180011830
0x180011826  mov     edx, 16Fh
0x18001182b  jmp     loc_1800118B9
0x180011830  mov     rbx, [rsp+250h+pv]
0x180011835  jmp     short loc_180011878
0x180011837  mov     rdi, rax
0x18001183a  lea     r8, [rax-1]
0x18001183e  xor     edx, edx
0x180011840  lea     rcx, [rsp+250h+pv]
0x180011845  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18001184a  mov     ebx, eax
0x18001184c  test    eax, eax
0x18001184e  js      short loc_1800118B4
0x180011850  lea     r9, [rsp+250h+var_228]
0x180011855  mov     r8, rdi
0x180011858  mov     rbx, [rsp+250h+pv]
0x18001185d  mov     rdx, rbx
0x180011860  mov     rcx, r14
0x180011863  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180011868  mov     esi, eax
0x18001186a  test    eax, eax
0x18001186c  js      short loc_1800118A2
0x18001186e  mov     rax, [rsp+250h+var_228]
0x180011873  cmp     rax, rdi
0x180011876  ja      short loc_180011837
0x180011878  mov     [rsp+250h+pv], rbx
0x18001187d  lea     rdx, [rsp+250h+pv]
0x180011882  lea     rcx, qword_18006A6C8
0x180011889  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001188e  mov     rcx, [rsp+250h+pv]; pv
0x180011893  test    rcx, rcx
0x180011896  jz      short loc_18001189E
0x180011898  call    cs:__imp_CoTaskMemFree
0x18001189e  xor     eax, eax
0x1800118a0  jmp     short loc_1800118E1
0x1800118a2  test    rbx, rbx
0x1800118a5  jz      short loc_1800118B0
0x1800118a7  mov     rcx, rbx; pv
0x1800118aa  call    cs:__imp_CoTaskMemFree
0x1800118b0  mov     eax, esi
0x1800118b2  jmp     short loc_1800118E1
0x1800118b4  mov     edx, 17Ah; void *
0x1800118b9  mov     r9d, ebx; char *
0x1800118bc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800118c3  mov     rcx, [rbp+158h]; this
0x1800118ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118cf  mov     rcx, [rsp+250h+pv]; pv
0x1800118d4  test    rcx, rcx
0x1800118d7  jz      short loc_1800118DF
0x1800118d9  call    cs:__imp_CoTaskMemFree
0x1800118df  mov     eax, ebx
0x1800118e1  mov     rcx, [rbp+150h+var_20]
0x1800118e8  xor     rcx, rsp; StackCookie
0x1800118eb  call    __security_check_cookie
0x1800118f0  lea     r11, [rsp+250h+var_10]
0x1800118f8  mov     rbx, [r11+20h]
0x1800118fc  mov     rsi, [r11+30h]
0x180011900  mov     rsp, r11
0x180011903  pop     r14
0x180011905  pop     rdi
0x180011906  pop     rbp
0x180011907  retn
```
