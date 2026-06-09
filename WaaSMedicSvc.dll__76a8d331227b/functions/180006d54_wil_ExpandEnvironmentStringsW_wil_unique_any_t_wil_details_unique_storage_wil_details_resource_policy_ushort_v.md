# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180006d54`
- end: `0x180006f22`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006cfc`

## callees

- `0x180002200`
- `0x180002f7c`
- `0x180005984`
- `0x180006d54`
- `0x1800094c0`
- `0x18000b644`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ea4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006edd`

## string_xrefs

- `0x180006ec0`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
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
  v18[0] = &wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
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
0x180006d54  mov     [rsp-8+arg_0], rbx
0x180006d59  mov     [rsp-8+arg_10], rsi
0x180006d5e  push    rbp
0x180006d5f  push    rdi
0x180006d60  push    r14
0x180006d62  lea     rbp, [rsp-1D0h]
0x180006d6a  sub     rsp, 2D0h
0x180006d71  mov     rax, cs:__security_cookie
0x180006d78  xor     rax, rsp
0x180006d7b  mov     [rbp+1E0h+var_20], rax
0x180006d82  mov     r14, rdx
0x180006d85  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x180006d8c  mov     [rsp+2E0h+var_2B0], rax
0x180006d91  lea     rax, ??_7?$__func@V_lambda_ed01672e02d6682bf5b3b76f9b133eec_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180006d98  mov     [rsp+2E0h+var_298], rax
0x180006d9d  lea     rax, [rsp+2E0h+var_2B0]
0x180006da2  mov     [rsp+2E0h+var_290], rax
0x180006da7  lea     rax, [rsp+2E0h+var_298]
0x180006dac  mov     [rbp+1E0h+var_230], rax
0x180006db0  mov     [rsp+2E0h+pv], 0; int
0x180006db9  xor     edx, edx; Val
0x180006dbb  mov     r8d, 200h; Size
0x180006dc1  lea     rcx, [rbp+1E0h+var_220]; void *
0x180006dc5  call    memset_0
0x180006dca  mov     [rsp+2E0h+var_2B8], 0
0x180006dd3  lea     r9, [rsp+2E0h+var_2B8]
0x180006dd8  mov     ebx, 100h
0x180006ddd  mov     r8d, ebx
0x180006de0  lea     rdx, [rbp+1E0h+var_220]
0x180006de4  lea     rcx, [rsp+2E0h+var_2A0]
0x180006de9  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006dee  mov     edi, eax
0x180006df0  test    eax, eax
0x180006df2  js      loc_180006EE4
0x180006df8  mov     rax, [rsp+2E0h+var_2B8]
0x180006dfd  cmp     rax, rbx
0x180006e00  ja      short loc_180006E29
0x180006e02  lea     r8, [rax-1]
0x180006e06  lea     rdx, [rbp+1E0h+var_220]
0x180006e0a  lea     rcx, [rsp+2E0h+pv]
0x180006e0f  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180006e14  mov     edi, eax
0x180006e16  test    eax, eax
0x180006e18  jns     short loc_180006E22
0x180006e1a  lea     edx, [rbx+6Fh]
0x180006e1d  jmp     loc_180006EBD
0x180006e22  mov     rbx, [rsp+2E0h+pv]
0x180006e27  jmp     short loc_180006E6C
0x180006e29  mov     rsi, rax
0x180006e2c  lea     r8, [rax-1]
0x180006e30  xor     edx, edx
0x180006e32  lea     rcx, [rsp+2E0h+pv]
0x180006e37  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x180006e3c  mov     edi, eax
0x180006e3e  test    eax, eax
0x180006e40  js      short loc_180006EB8
0x180006e42  lea     r9, [rsp+2E0h+var_2B8]
0x180006e47  mov     r8, rsi
0x180006e4a  mov     rbx, [rsp+2E0h+pv]
0x180006e4f  mov     rdx, rbx
0x180006e52  lea     rcx, [rsp+2E0h+var_2A0]
0x180006e57  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x180006e5c  mov     edi, eax
0x180006e5e  test    eax, eax
0x180006e60  js      short loc_180006EAE
0x180006e62  mov     rax, [rsp+2E0h+var_2B8]
0x180006e67  cmp     rax, rsi
0x180006e6a  ja      short loc_180006E29
0x180006e6c  lea     rax, [rsp+2E0h+var_2A8]
0x180006e71  cmp     r14, rax
0x180006e74  jz      short loc_180006E9C
0x180006e76  mov     rsi, [r14]
0x180006e79  test    rsi, rsi
0x180006e7c  jz      short loc_180006E97
0x180006e7e  call    cs:__imp_GetLastError
0x180006e84  mov     edi, eax
0x180006e86  mov     rcx, rsi; pv
0x180006e89  call    cs:__imp_CoTaskMemFree
0x180006e8f  mov     ecx, edi; dwErrCode
0x180006e91  call    cs:__imp_SetLastError
0x180006e97  mov     [r14], rbx
0x180006e9a  jmp     short loc_180006EAA
0x180006e9c  test    rbx, rbx
0x180006e9f  jz      short loc_180006EAA
0x180006ea1  mov     rcx, rbx; pv
0x180006ea4  call    cs:__imp_CoTaskMemFree
0x180006eaa  xor     edi, edi
0x180006eac  jmp     short loc_180006EE4
0x180006eae  test    rbx, rbx
0x180006eb1  jz      short loc_180006EE4
0x180006eb3  mov     rcx, rbx
0x180006eb6  jmp     short loc_180006EDD
0x180006eb8  mov     edx, 17Ah; void *
0x180006ebd  mov     r9d, eax; char *
0x180006ec0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006ec7  mov     rcx, [rbp+1E8h]; this
0x180006ece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ed3  mov     rcx, [rsp+2E0h+pv]; pv
0x180006ed8  test    rcx, rcx
0x180006edb  jz      short loc_180006EE4
0x180006edd  call    cs:__imp_CoTaskMemFree
0x180006ee3  nop
0x180006ee4  mov     rcx, [rbp+1E0h+var_230]
0x180006ee8  test    rcx, rcx
0x180006eeb  jz      short loc_180006EF9
0x180006eed  mov     rdx, [rcx]
0x180006ef0  mov     rax, [rdx+18h]
0x180006ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef9  mov     eax, edi
0x180006efb  mov     rcx, [rbp+1E0h+var_20]
0x180006f02  xor     rcx, rsp; StackCookie
0x180006f05  call    __security_check_cookie
0x180006f0a  lea     r11, [rsp+2E0h+var_10]
0x180006f12  mov     rbx, [r11+20h]
0x180006f16  mov     rsi, [r11+30h]
0x180006f1a  mov     rsp, r11
0x180006f1d  pop     r14
0x180006f1f  pop     rdi
0x180006f20  pop     rbp
0x180006f21  retn
```
