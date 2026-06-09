# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x140004a78`
- end: `0x140004bed`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140006028`

## callees

- `0x140003620`
- `0x1400042c4`
- `0x140004a78`
- `0x1400090a8`
- `0x14000991c`
- `0x140009fd8`
- `0x1400136fc`
- `0x14001a788`

## string_xrefs

- `0x140004bae`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
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
      v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
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
  v6 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
    return (unsigned int)v4;
  }
  v9 = *(_QWORD *)v13;
LABEL_9:
  v15[0] = v9;
  *(_QWORD *)v13 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
  return 0;
}

```

## disassembly

```asm
0x140004a78  mov     [rsp-8+arg_10], rbx
0x140004a7d  mov     [rsp-8+arg_18], rsi
0x140004a82  push    rbp
0x140004a83  push    rdi
0x140004a84  push    r14
0x140004a86  lea     rbp, [rsp-150h]
0x140004a8e  sub     rsp, 250h
0x140004a95  mov     rax, cs:__security_cookie
0x140004a9c  xor     rax, rsp
0x140004a9f  mov     [rbp+160h+var_20], rax
0x140004aa6  mov     rsi, rdx
0x140004aa9  mov     qword ptr [rsp+260h+var_240], 0; int
0x140004ab2  mov     r14, rcx
0x140004ab5  xor     edx, edx; Val
0x140004ab7  lea     rcx, [rsp+260h+var_220]; void *
0x140004abc  mov     r8d, 200h; Size
0x140004ac2  call    memset_0
0x140004ac7  mov     edi, 100h
0x140004acc  mov     [rsp+260h+var_238], 0
0x140004ad5  mov     r8d, edi
0x140004ad8  lea     r9, [rsp+260h+var_238]
0x140004add  lea     rdx, [rsp+260h+var_220]
0x140004ae2  mov     rcx, rsi
0x140004ae5  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x140004aea  mov     ebx, eax
0x140004aec  test    eax, eax
0x140004aee  js      loc_140004BBA
0x140004af4  mov     rax, [rsp+260h+var_238]
0x140004af9  cmp     rax, rdi
0x140004afc  ja      short loc_140004B29
0x140004afe  lea     r8, [rax-1]
0x140004b02  lea     rdx, [rsp+260h+var_220]
0x140004b07  lea     rcx, [rsp+260h+var_240]
0x140004b0c  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140004b11  mov     ebx, eax
0x140004b13  test    eax, eax
0x140004b15  jns     short loc_140004B22
0x140004b17  mov     r9d, eax
0x140004b1a  lea     edx, [rdi+6Fh]
0x140004b1d  jmp     loc_140004BA7
0x140004b22  mov     rbx, qword ptr [rsp+260h+var_240]
0x140004b27  jmp     short loc_140004B68
0x140004b29  lea     r8, [rax-1]
0x140004b2d  xor     edx, edx
0x140004b2f  lea     rcx, [rsp+260h+var_240]
0x140004b34  mov     rdi, rax
0x140004b37  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140004b3c  mov     ebx, eax
0x140004b3e  test    eax, eax
0x140004b40  js      short loc_140004B9F
0x140004b42  mov     rbx, qword ptr [rsp+260h+var_240]
0x140004b47  lea     r9, [rsp+260h+var_238]
0x140004b4c  mov     rdx, rbx
0x140004b4f  mov     r8, rdi
0x140004b52  mov     rcx, rsi
0x140004b55  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x140004b5a  test    eax, eax
0x140004b5c  js      short loc_140004B9B
0x140004b5e  mov     rax, [rsp+260h+var_238]
0x140004b63  cmp     rax, rdi
0x140004b66  ja      short loc_140004B29
0x140004b68  lea     rdx, [rsp+260h+var_230]
0x140004b6d  mov     [rsp+260h+var_230], rbx
0x140004b72  mov     rcx, r14
0x140004b75  mov     qword ptr [rsp+260h+var_240], 0
0x140004b7e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x140004b83  lea     rcx, [rsp+260h+var_230]
0x140004b88  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004b8d  lea     rcx, [rsp+260h+var_240]
0x140004b92  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004b97  xor     eax, eax
0x140004b99  jmp     short loc_140004BC6
0x140004b9b  mov     ebx, eax
0x140004b9d  jmp     short loc_140004BBA
0x140004b9f  mov     r9d, ebx; char *
0x140004ba2  mov     edx, 17Ah; void *
0x140004ba7  mov     rcx, [rbp+168h]; this
0x140004bae  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004bb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004bba  lea     rcx, [rsp+260h+var_240]
0x140004bbf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004bc4  mov     eax, ebx
0x140004bc6  mov     rcx, [rbp+160h+var_20]
0x140004bcd  xor     rcx, rsp; StackCookie
0x140004bd0  call    __security_check_cookie
0x140004bd5  lea     r11, [rsp+260h+var_10]
0x140004bdd  mov     rbx, [r11+30h]
0x140004be1  mov     rsi, [r11+38h]
0x140004be5  mov     rsp, r11
0x140004be8  pop     r14
0x140004bea  pop     rdi
0x140004beb  pop     rbp
0x140004bec  retn
```
