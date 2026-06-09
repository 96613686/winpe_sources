# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18003ca38`
- end: `0x18003cc06`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c9e0`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x18002dd7c`
- `0x18003ca38`
- `0x18003e2c0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cb75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cb75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cbc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cbc1`

## string_xrefs

- `0x18003cba4`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        __int64 a1,
        char *a2)
{
  int v3; // edi
  unsigned __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rdx
  void *v7; // rbx
  unsigned __int64 v8; // rsi
  void *v9; // rsi
  DWORD LastError; // edi
  void *v11; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v15; // [rsp+30h] [rbp-D0h] BYREF
  char v16; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[13]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v19; // [rsp+B0h] [rbp-50h]
  _BYTE v20[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v15 = L"%SystemRoot%\\uus";
  v18[0] = &wistd::__function::__func<_lambda_1f4a220c340983e6f1ea5f164cc797a5_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v18[1] = &v15;
  v19 = v18;
  pv = 0;
  memset_0(v20, 0, sizeof(v20));
  v14 = 0;
  v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, v20, 256, &v14);
  if ( v3 >= 0 )
  {
    v4 = v14;
    if ( v14 > 0x100 )
    {
      while ( 1 )
      {
        v8 = v4;
        v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
               &pv,
               0,
               v4 - 1);
        v3 = v5;
        if ( v5 < 0 )
        {
          v6 = 378;
          goto LABEL_19;
        }
        v7 = pv;
        v3 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(v17, pv, v8, &v14);
        if ( v3 < 0 )
          break;
        v4 = v14;
        if ( v14 <= v8 )
          goto LABEL_9;
      }
      if ( !v7 )
        goto LABEL_21;
      v11 = v7;
      goto LABEL_20;
    }
    v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
           &pv,
           v20,
           v14 - 1);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v7 = pv;
LABEL_9:
      if ( a2 == &v16 )
      {
        if ( v7 )
          CoTaskMemFree(v7);
      }
      else
      {
        v9 = *(void **)a2;
        if ( *(_QWORD *)a2 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v9);
          SetLastError(LastError);
        }
        *(_QWORD *)a2 = v7;
      }
      v3 = 0;
    }
    else
    {
      v6 = 367;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v5,
        (int)pv);
      v11 = pv;
      if ( pv )
LABEL_20:
        CoTaskMemFree(v11);
    }
  }
LABEL_21:
  if ( v19 )
    (*(void (__fastcall **)(_QWORD *))(*v19 + 24LL))(v19);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003ca38  mov     [rsp-8+arg_0], rbx
0x18003ca3d  mov     [rsp-8+arg_10], rsi
0x18003ca42  push    rbp
0x18003ca43  push    rdi
0x18003ca44  push    r14
0x18003ca46  lea     rbp, [rsp-1D0h]
0x18003ca4e  sub     rsp, 2D0h
0x18003ca55  mov     rax, cs:__security_cookie
0x18003ca5c  xor     rax, rsp
0x18003ca5f  mov     [rbp+1E0h+var_20], rax
0x18003ca66  mov     r14, rdx
0x18003ca69  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x18003ca70  mov     [rsp+2E0h+var_2B0], rax
0x18003ca75  lea     rax, ??_7?$__func@V_lambda_1f4a220c340983e6f1ea5f164cc797a5_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_1f4a220c340983e6f1ea5f164cc797a5_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18003ca7c  mov     [rsp+2E0h+var_298], rax
0x18003ca81  lea     rax, [rsp+2E0h+var_2B0]
0x18003ca86  mov     [rsp+2E0h+var_290], rax
0x18003ca8b  lea     rax, [rsp+2E0h+var_298]
0x18003ca90  mov     [rbp+1E0h+var_230], rax
0x18003ca94  mov     [rsp+2E0h+pv], 0; int
0x18003ca9d  xor     edx, edx; Val
0x18003ca9f  mov     r8d, 200h; Size
0x18003caa5  lea     rcx, [rbp+1E0h+var_220]; void *
0x18003caa9  call    memset_0
0x18003caae  mov     [rsp+2E0h+var_2B8], 0
0x18003cab7  lea     r9, [rsp+2E0h+var_2B8]
0x18003cabc  mov     ebx, 100h
0x18003cac1  mov     r8d, ebx
0x18003cac4  lea     rdx, [rbp+1E0h+var_220]
0x18003cac8  lea     rcx, [rsp+2E0h+var_2A0]
0x18003cacd  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18003cad2  mov     edi, eax
0x18003cad4  test    eax, eax
0x18003cad6  js      loc_18003CBC8
0x18003cadc  mov     rax, [rsp+2E0h+var_2B8]
0x18003cae1  cmp     rax, rbx
0x18003cae4  ja      short loc_18003CB0D
0x18003cae6  lea     r8, [rax-1]
0x18003caea  lea     rdx, [rbp+1E0h+var_220]
0x18003caee  lea     rcx, [rsp+2E0h+pv]
0x18003caf3  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18003caf8  mov     edi, eax
0x18003cafa  test    eax, eax
0x18003cafc  jns     short loc_18003CB06
0x18003cafe  lea     edx, [rbx+6Fh]
0x18003cb01  jmp     loc_18003CBA1
0x18003cb06  mov     rbx, [rsp+2E0h+pv]
0x18003cb0b  jmp     short loc_18003CB50
0x18003cb0d  mov     rsi, rax
0x18003cb10  lea     r8, [rax-1]
0x18003cb14  xor     edx, edx
0x18003cb16  lea     rcx, [rsp+2E0h+pv]
0x18003cb1b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18003cb20  mov     edi, eax
0x18003cb22  test    eax, eax
0x18003cb24  js      short loc_18003CB9C
0x18003cb26  lea     r9, [rsp+2E0h+var_2B8]
0x18003cb2b  mov     r8, rsi
0x18003cb2e  mov     rbx, [rsp+2E0h+pv]
0x18003cb33  mov     rdx, rbx
0x18003cb36  lea     rcx, [rsp+2E0h+var_2A0]
0x18003cb3b  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18003cb40  mov     edi, eax
0x18003cb42  test    eax, eax
0x18003cb44  js      short loc_18003CB92
0x18003cb46  mov     rax, [rsp+2E0h+var_2B8]
0x18003cb4b  cmp     rax, rsi
0x18003cb4e  ja      short loc_18003CB0D
0x18003cb50  lea     rax, [rsp+2E0h+var_2A8]
0x18003cb55  cmp     r14, rax
0x18003cb58  jz      short loc_18003CB80
0x18003cb5a  mov     rsi, [r14]
0x18003cb5d  test    rsi, rsi
0x18003cb60  jz      short loc_18003CB7B
0x18003cb62  call    cs:__imp_GetLastError
0x18003cb68  mov     edi, eax
0x18003cb6a  mov     rcx, rsi; pv
0x18003cb6d  call    cs:__imp_CoTaskMemFree
0x18003cb73  mov     ecx, edi; dwErrCode
0x18003cb75  call    cs:__imp_SetLastError
0x18003cb7b  mov     [r14], rbx
0x18003cb7e  jmp     short loc_18003CB8E
0x18003cb80  test    rbx, rbx
0x18003cb83  jz      short loc_18003CB8E
0x18003cb85  mov     rcx, rbx; pv
0x18003cb88  call    cs:__imp_CoTaskMemFree
0x18003cb8e  xor     edi, edi
0x18003cb90  jmp     short loc_18003CBC8
0x18003cb92  test    rbx, rbx
0x18003cb95  jz      short loc_18003CBC8
0x18003cb97  mov     rcx, rbx
0x18003cb9a  jmp     short loc_18003CBC1
0x18003cb9c  mov     edx, 17Ah; void *
0x18003cba1  mov     r9d, eax; char *
0x18003cba4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003cbab  mov     rcx, [rbp+1E8h]; this
0x18003cbb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cbb7  mov     rcx, [rsp+2E0h+pv]; pv
0x18003cbbc  test    rcx, rcx
0x18003cbbf  jz      short loc_18003CBC8
0x18003cbc1  call    cs:__imp_CoTaskMemFree
0x18003cbc7  nop
0x18003cbc8  mov     rcx, [rbp+1E0h+var_230]
0x18003cbcc  test    rcx, rcx
0x18003cbcf  jz      short loc_18003CBDD
0x18003cbd1  mov     rdx, [rcx]
0x18003cbd4  mov     rax, [rdx+18h]
0x18003cbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbdd  mov     eax, edi
0x18003cbdf  mov     rcx, [rbp+1E0h+var_20]
0x18003cbe6  xor     rcx, rsp; StackCookie
0x18003cbe9  call    __security_check_cookie
0x18003cbee  lea     r11, [rsp+2E0h+var_10]
0x18003cbf6  mov     rbx, [r11+20h]
0x18003cbfa  mov     rsi, [r11+30h]
0x18003cbfe  mov     rsp, r11
0x18003cc01  pop     r14
0x18003cc03  pop     rdi
0x18003cc04  pop     rbp
0x18003cc05  retn
```
