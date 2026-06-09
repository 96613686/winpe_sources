# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x140006614`
- end: `0x1400067e2`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, char *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400065bc`
- `0x14000a678`

## callees

- `0x140002120`
- `0x140002c58`
- `0x140005454`
- `0x140006614`
- `0x140008c00`
- `0x14000a3e8`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006751`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000673e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000673e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000679d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000679d`

## string_xrefs

- `0x140006780`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

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
0x140006614  mov     [rsp-8+arg_0], rbx
0x140006619  mov     [rsp-8+arg_10], rsi
0x14000661e  push    rbp
0x14000661f  push    rdi
0x140006620  push    r14
0x140006622  lea     rbp, [rsp-1D0h]
0x14000662a  sub     rsp, 2D0h
0x140006631  mov     rax, cs:__security_cookie
0x140006638  xor     rax, rsp
0x14000663b  mov     [rbp+1E0h+var_20], rax
0x140006642  mov     r14, rdx
0x140006645  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x14000664c  mov     [rsp+2E0h+var_2B0], rax
0x140006651  lea     rax, ??_7?$__func@V_lambda_ed01672e02d6682bf5b3b76f9b133eec_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_ed01672e02d6682bf5b3b76f9b133eec_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x140006658  mov     [rsp+2E0h+var_298], rax
0x14000665d  lea     rax, [rsp+2E0h+var_2B0]
0x140006662  mov     [rsp+2E0h+var_290], rax
0x140006667  lea     rax, [rsp+2E0h+var_298]
0x14000666c  mov     [rbp+1E0h+var_230], rax
0x140006670  mov     [rsp+2E0h+pv], 0; int
0x140006679  xor     edx, edx; Val
0x14000667b  mov     r8d, 200h; Size
0x140006681  lea     rcx, [rbp+1E0h+var_220]; void *
0x140006685  call    memset_0
0x14000668a  mov     [rsp+2E0h+var_2B8], 0
0x140006693  lea     r9, [rsp+2E0h+var_2B8]
0x140006698  mov     ebx, 100h
0x14000669d  mov     r8d, ebx
0x1400066a0  lea     rdx, [rbp+1E0h+var_220]
0x1400066a4  lea     rcx, [rsp+2E0h+var_2A0]
0x1400066a9  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1400066ae  mov     edi, eax
0x1400066b0  test    eax, eax
0x1400066b2  js      loc_1400067A4
0x1400066b8  mov     rax, [rsp+2E0h+var_2B8]
0x1400066bd  cmp     rax, rbx
0x1400066c0  ja      short loc_1400066E9
0x1400066c2  lea     r8, [rax-1]
0x1400066c6  lea     rdx, [rbp+1E0h+var_220]
0x1400066ca  lea     rcx, [rsp+2E0h+pv]
0x1400066cf  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x1400066d4  mov     edi, eax
0x1400066d6  test    eax, eax
0x1400066d8  jns     short loc_1400066E2
0x1400066da  lea     edx, [rbx+6Fh]
0x1400066dd  jmp     loc_14000677D
0x1400066e2  mov     rbx, [rsp+2E0h+pv]
0x1400066e7  jmp     short loc_14000672C
0x1400066e9  mov     rsi, rax
0x1400066ec  lea     r8, [rax-1]
0x1400066f0  xor     edx, edx
0x1400066f2  lea     rcx, [rsp+2E0h+pv]
0x1400066f7  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x1400066fc  mov     edi, eax
0x1400066fe  test    eax, eax
0x140006700  js      short loc_140006778
0x140006702  lea     r9, [rsp+2E0h+var_2B8]
0x140006707  mov     r8, rsi
0x14000670a  mov     rbx, [rsp+2E0h+pv]
0x14000670f  mov     rdx, rbx
0x140006712  lea     rcx, [rsp+2E0h+var_2A0]
0x140006717  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x14000671c  mov     edi, eax
0x14000671e  test    eax, eax
0x140006720  js      short loc_14000676E
0x140006722  mov     rax, [rsp+2E0h+var_2B8]
0x140006727  cmp     rax, rsi
0x14000672a  ja      short loc_1400066E9
0x14000672c  lea     rax, [rsp+2E0h+var_2A8]
0x140006731  cmp     r14, rax
0x140006734  jz      short loc_14000675C
0x140006736  mov     rsi, [r14]
0x140006739  test    rsi, rsi
0x14000673c  jz      short loc_140006757
0x14000673e  call    cs:__imp_GetLastError
0x140006744  mov     edi, eax
0x140006746  mov     rcx, rsi; pv
0x140006749  call    cs:__imp_CoTaskMemFree
0x14000674f  mov     ecx, edi; dwErrCode
0x140006751  call    cs:__imp_SetLastError
0x140006757  mov     [r14], rbx
0x14000675a  jmp     short loc_14000676A
0x14000675c  test    rbx, rbx
0x14000675f  jz      short loc_14000676A
0x140006761  mov     rcx, rbx; pv
0x140006764  call    cs:__imp_CoTaskMemFree
0x14000676a  xor     edi, edi
0x14000676c  jmp     short loc_1400067A4
0x14000676e  test    rbx, rbx
0x140006771  jz      short loc_1400067A4
0x140006773  mov     rcx, rbx
0x140006776  jmp     short loc_14000679D
0x140006778  mov     edx, 17Ah; void *
0x14000677d  mov     r9d, eax; char *
0x140006780  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006787  mov     rcx, [rbp+1E8h]; this
0x14000678e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006793  mov     rcx, [rsp+2E0h+pv]; pv
0x140006798  test    rcx, rcx
0x14000679b  jz      short loc_1400067A4
0x14000679d  call    cs:__imp_CoTaskMemFree
0x1400067a3  nop
0x1400067a4  mov     rcx, [rbp+1E0h+var_230]
0x1400067a8  test    rcx, rcx
0x1400067ab  jz      short loc_1400067B9
0x1400067ad  mov     rdx, [rcx]
0x1400067b0  mov     rax, [rdx+18h]
0x1400067b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067b9  mov     eax, edi
0x1400067bb  mov     rcx, [rbp+1E0h+var_20]
0x1400067c2  xor     rcx, rsp; StackCookie
0x1400067c5  call    __security_check_cookie
0x1400067ca  lea     r11, [rsp+2E0h+var_10]
0x1400067d2  mov     rbx, [r11+20h]
0x1400067d6  mov     rsi, [r11+30h]
0x1400067da  mov     rsp, r11
0x1400067dd  pop     r14
0x1400067df  pop     rdi
0x1400067e0  pop     rbp
0x1400067e1  retn
```
