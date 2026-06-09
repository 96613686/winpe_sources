# wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18000db78`
- end: `0x18000dd46`
- name: `??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000db20`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000bbd4`
- `0x18000db78`
- `0x1800111f4`
- `0x18001da80`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd01`

## string_xrefs

- `0x18000dce4`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

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
0x18000db78  mov     [rsp-8+arg_0], rbx
0x18000db7d  mov     [rsp-8+arg_10], rsi
0x18000db82  push    rbp
0x18000db83  push    rdi
0x18000db84  push    r14
0x18000db86  lea     rbp, [rsp-1D0h]
0x18000db8e  sub     rsp, 2D0h
0x18000db95  mov     rax, cs:__security_cookie
0x18000db9c  xor     rax, rsp
0x18000db9f  mov     [rbp+1E0h+var_20], rax
0x18000dba6  mov     r14, rdx
0x18000dba9  lea     rax, aSystemrootUus; "%SystemRoot%\\uus"
0x18000dbb0  mov     [rsp+2E0h+var_2B0], rax
0x18000dbb5  lea     rax, ??_7?$__func@V_lambda_1f4a220c340983e6f1ea5f164cc797a5_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_1f4a220c340983e6f1ea5f164cc797a5_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000dbbc  mov     [rsp+2E0h+var_298], rax
0x18000dbc1  lea     rax, [rsp+2E0h+var_2B0]
0x18000dbc6  mov     [rsp+2E0h+var_290], rax
0x18000dbcb  lea     rax, [rsp+2E0h+var_298]
0x18000dbd0  mov     [rbp+1E0h+var_230], rax
0x18000dbd4  mov     [rsp+2E0h+pv], 0; int
0x18000dbdd  xor     edx, edx; Val
0x18000dbdf  mov     r8d, 200h; Size
0x18000dbe5  lea     rcx, [rbp+1E0h+var_220]; void *
0x18000dbe9  call    memset_0
0x18000dbee  mov     [rsp+2E0h+var_2B8], 0
0x18000dbf7  lea     r9, [rsp+2E0h+var_2B8]
0x18000dbfc  mov     ebx, 100h
0x18000dc01  mov     r8d, ebx
0x18000dc04  lea     rdx, [rbp+1E0h+var_220]
0x18000dc08  lea     rcx, [rsp+2E0h+var_2A0]
0x18000dc0d  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000dc12  mov     edi, eax
0x18000dc14  test    eax, eax
0x18000dc16  js      loc_18000DD08
0x18000dc1c  mov     rax, [rsp+2E0h+var_2B8]
0x18000dc21  cmp     rax, rbx
0x18000dc24  ja      short loc_18000DC4D
0x18000dc26  lea     r8, [rax-1]
0x18000dc2a  lea     rdx, [rbp+1E0h+var_220]
0x18000dc2e  lea     rcx, [rsp+2E0h+pv]
0x18000dc33  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000dc38  mov     edi, eax
0x18000dc3a  test    eax, eax
0x18000dc3c  jns     short loc_18000DC46
0x18000dc3e  lea     edx, [rbx+6Fh]
0x18000dc41  jmp     loc_18000DCE1
0x18000dc46  mov     rbx, [rsp+2E0h+pv]
0x18000dc4b  jmp     short loc_18000DC90
0x18000dc4d  mov     rsi, rax
0x18000dc50  lea     r8, [rax-1]
0x18000dc54  xor     edx, edx
0x18000dc56  lea     rcx, [rsp+2E0h+pv]
0x18000dc5b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18000dc60  mov     edi, eax
0x18000dc62  test    eax, eax
0x18000dc64  js      short loc_18000DCDC
0x18000dc66  lea     r9, [rsp+2E0h+var_2B8]
0x18000dc6b  mov     r8, rsi
0x18000dc6e  mov     rbx, [rsp+2E0h+pv]
0x18000dc73  mov     rdx, rbx
0x18000dc76  lea     rcx, [rsp+2E0h+var_2A0]
0x18000dc7b  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000dc80  mov     edi, eax
0x18000dc82  test    eax, eax
0x18000dc84  js      short loc_18000DCD2
0x18000dc86  mov     rax, [rsp+2E0h+var_2B8]
0x18000dc8b  cmp     rax, rsi
0x18000dc8e  ja      short loc_18000DC4D
0x18000dc90  lea     rax, [rsp+2E0h+var_2A8]
0x18000dc95  cmp     r14, rax
0x18000dc98  jz      short loc_18000DCC0
0x18000dc9a  mov     rsi, [r14]
0x18000dc9d  test    rsi, rsi
0x18000dca0  jz      short loc_18000DCBB
0x18000dca2  call    cs:__imp_GetLastError
0x18000dca8  mov     edi, eax
0x18000dcaa  mov     rcx, rsi; pv
0x18000dcad  call    cs:__imp_CoTaskMemFree
0x18000dcb3  mov     ecx, edi; dwErrCode
0x18000dcb5  call    cs:__imp_SetLastError
0x18000dcbb  mov     [r14], rbx
0x18000dcbe  jmp     short loc_18000DCCE
0x18000dcc0  test    rbx, rbx
0x18000dcc3  jz      short loc_18000DCCE
0x18000dcc5  mov     rcx, rbx; pv
0x18000dcc8  call    cs:__imp_CoTaskMemFree
0x18000dcce  xor     edi, edi
0x18000dcd0  jmp     short loc_18000DD08
0x18000dcd2  test    rbx, rbx
0x18000dcd5  jz      short loc_18000DD08
0x18000dcd7  mov     rcx, rbx
0x18000dcda  jmp     short loc_18000DD01
0x18000dcdc  mov     edx, 17Ah; void *
0x18000dce1  mov     r9d, eax; char *
0x18000dce4  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dceb  mov     rcx, [rbp+1E8h]; this
0x18000dcf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcf7  mov     rcx, [rsp+2E0h+pv]; pv
0x18000dcfc  test    rcx, rcx
0x18000dcff  jz      short loc_18000DD08
0x18000dd01  call    cs:__imp_CoTaskMemFree
0x18000dd07  nop
0x18000dd08  mov     rcx, [rbp+1E0h+var_230]
0x18000dd0c  test    rcx, rcx
0x18000dd0f  jz      short loc_18000DD1D
0x18000dd11  mov     rdx, [rcx]
0x18000dd14  mov     rax, [rdx+18h]
0x18000dd18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd1d  mov     eax, edi
0x18000dd1f  mov     rcx, [rbp+1E0h+var_20]
0x18000dd26  xor     rcx, rsp; StackCookie
0x18000dd29  call    __security_check_cookie
0x18000dd2e  lea     r11, [rsp+2E0h+var_10]
0x18000dd36  mov     rbx, [r11+20h]
0x18000dd3a  mov     rsi, [r11+30h]
0x18000dd3e  mov     rsp, r11
0x18000dd41  pop     r14
0x18000dd43  pop     rdi
0x18000dd44  pop     rbp
0x18000dd45  retn
```
