# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x18000ed18`
- end: `0x18000ee83`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000ee8c`

## callees

- `0x180001ed0`
- `0x180002878`
- `0x18000940c`
- `0x18000ed18`
- `0x18000f000`
- `0x18000f020`
- `0x18000f0ec`
- `0x18000f53c`

## string_xrefs

- `0x18000ee47`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
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
  _BYTE v16[256]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *(_QWORD *)v13 = 0;
  memset_0(v16, 0, sizeof(v16));
  v14 = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v16, 128, &v14);
  if ( v4 < 0 )
    goto LABEL_13;
  v5 = v14;
  if ( v14 > 0x80 )
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
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
0x18000ed18  mov     [rsp-8+arg_10], rbx
0x18000ed1d  mov     [rsp-8+arg_18], rsi
0x18000ed22  push    rbp
0x18000ed23  push    rdi
0x18000ed24  push    r14
0x18000ed26  lea     rbp, [rsp-50h]
0x18000ed2b  sub     rsp, 150h
0x18000ed32  mov     rax, cs:__security_cookie
0x18000ed39  xor     rax, rsp
0x18000ed3c  mov     [rbp+60h+var_20], rax
0x18000ed40  mov     rsi, rdx
0x18000ed43  mov     qword ptr [rsp+160h+var_140], 0; int
0x18000ed4c  mov     r14, rcx
0x18000ed4f  xor     edx, edx; Val
0x18000ed51  lea     rcx, [rsp+160h+var_120]; void *
0x18000ed56  mov     r8d, 100h; Size
0x18000ed5c  call    memset_0
0x18000ed61  mov     edi, 80h
0x18000ed66  mov     [rsp+160h+var_138], 0
0x18000ed6f  mov     r8d, edi
0x18000ed72  lea     r9, [rsp+160h+var_138]
0x18000ed77  lea     rdx, [rsp+160h+var_120]
0x18000ed7c  mov     rcx, rsi
0x18000ed7f  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000ed84  mov     ebx, eax
0x18000ed86  test    eax, eax
0x18000ed88  js      loc_18000EE53
0x18000ed8e  mov     rax, [rsp+160h+var_138]
0x18000ed93  cmp     rax, rdi
0x18000ed96  ja      short loc_18000EDC5
0x18000ed98  lea     r8, [rax-1]
0x18000ed9c  lea     rdx, [rsp+160h+var_120]
0x18000eda1  lea     rcx, [rsp+160h+var_140]
0x18000eda6  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000edab  mov     ebx, eax
0x18000edad  test    eax, eax
0x18000edaf  jns     short loc_18000EDBE
0x18000edb1  mov     r9d, eax
0x18000edb4  mov     edx, 16Fh
0x18000edb9  jmp     loc_18000EE43
0x18000edbe  mov     rbx, qword ptr [rsp+160h+var_140]
0x18000edc3  jmp     short loc_18000EE04
0x18000edc5  lea     r8, [rax-1]
0x18000edc9  xor     edx, edx
0x18000edcb  lea     rcx, [rsp+160h+var_140]
0x18000edd0  mov     rdi, rax
0x18000edd3  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000edd8  mov     ebx, eax
0x18000edda  test    eax, eax
0x18000eddc  js      short loc_18000EE3B
0x18000edde  mov     rbx, qword ptr [rsp+160h+var_140]
0x18000ede3  lea     r9, [rsp+160h+var_138]
0x18000ede8  mov     rdx, rbx
0x18000edeb  mov     r8, rdi
0x18000edee  mov     rcx, rsi
0x18000edf1  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000edf6  test    eax, eax
0x18000edf8  js      short loc_18000EE37
0x18000edfa  mov     rax, [rsp+160h+var_138]
0x18000edff  cmp     rax, rdi
0x18000ee02  ja      short loc_18000EDC5
0x18000ee04  lea     rdx, [rsp+160h+var_130]
0x18000ee09  mov     [rsp+160h+var_130], rbx
0x18000ee0e  mov     rcx, r14
0x18000ee11  mov     qword ptr [rsp+160h+var_140], 0
0x18000ee1a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000ee1f  lea     rcx, [rsp+160h+var_130]
0x18000ee24  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ee29  lea     rcx, [rsp+160h+var_140]
0x18000ee2e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ee33  xor     eax, eax
0x18000ee35  jmp     short loc_18000EE5F
0x18000ee37  mov     ebx, eax
0x18000ee39  jmp     short loc_18000EE53
0x18000ee3b  mov     r9d, ebx; char *
0x18000ee3e  mov     edx, 17Ah; void *
0x18000ee43  mov     rcx, [rbp+68h]; this
0x18000ee47  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ee4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee53  lea     rcx, [rsp+160h+var_140]
0x18000ee58  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ee5d  mov     eax, ebx
0x18000ee5f  mov     rcx, [rbp+60h+var_20]
0x18000ee63  xor     rcx, rsp; StackCookie
0x18000ee66  call    __security_check_cookie
0x18000ee6b  lea     r11, [rsp+160h+var_10]
0x18000ee73  mov     rbx, [r11+30h]
0x18000ee77  mov     rsi, [r11+38h]
0x18000ee7b  mov     rsp, r11
0x18000ee7e  pop     r14
0x18000ee80  pop     rdi
0x18000ee81  pop     rbp
0x18000ee82  retn
```
