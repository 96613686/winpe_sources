# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18002e0c8`
- end: `0x18002e2ac`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e3dc`

## callees

- `0x180007804`
- `0x18002e0c8`
- `0x18002f990`
- `0x18002faf0`
- `0x180056500`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e1f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e1f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e22a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e26c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e1e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e22a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e26c`

## string_xrefs

- `0x18002e252`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
        char *a1,
        __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  void (*v6)(void); // rax
  unsigned __int64 v7; // rax
  __int64 v8; // rdx
  void *v9; // rbx
  unsigned __int64 v10; // rdi
  int v11; // r14d
  void *v12; // r14
  DWORD LastError; // edi
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  char v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[256]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  pv = 0;
  memset(v21, 0, sizeof(v21));
  v20[0] = 0;
  v4 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v21, 128, v20);
  if ( v4 < 0 )
  {
    v5 = *(_QWORD *)(a2 + 112);
    if ( !v5 )
      return (unsigned int)v4;
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 24LL);
LABEL_30:
    v6();
    return (unsigned int)v4;
  }
  v7 = v20[0];
  if ( v20[0] > 0x80u )
  {
    while ( 1 )
    {
      v10 = v7;
      v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
             &pv,
             0,
             v7 - 1);
      if ( v4 < 0 )
      {
        v8 = 362;
        goto LABEL_26;
      }
      v9 = pv;
      v11 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, pv, v10, v20);
      if ( v11 < 0 )
        break;
      v7 = v20[0];
      if ( v20[0] <= v10 )
        goto LABEL_11;
    }
    if ( v9 )
      CoTaskMemFree(v9);
    v16 = *(_QWORD *)(a2 + 112);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
    return (unsigned int)v11;
  }
  else
  {
    v4 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
           &pv,
           v21,
           v20[0] - 1LL);
    if ( v4 < 0 )
    {
      v8 = 351;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v4,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      v17 = *(_QWORD *)(a2 + 112);
      if ( !v17 )
        return (unsigned int)v4;
      v6 = *(void (**)(void))(*(_QWORD *)v17 + 24LL);
      goto LABEL_30;
    }
    v9 = pv;
LABEL_11:
    if ( a1 == &v19 )
    {
      if ( v9 )
        CoTaskMemFree(v9);
    }
    else
    {
      v12 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v12);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = v9;
    }
    v14 = *(_QWORD *)(a2 + 112);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    return 0;
  }
}

```

## disassembly

```asm
0x18002e0c8  mov     [rsp-8+arg_10], rbx
0x18002e0cd  push    rbp
0x18002e0ce  push    rsi
0x18002e0cf  push    rdi
0x18002e0d0  push    r14
0x18002e0d2  push    r15
0x18002e0d4  lea     rbp, [rsp-50h]
0x18002e0d9  sub     rsp, 150h
0x18002e0e0  mov     rax, cs:__security_cookie
0x18002e0e7  xor     rax, rsp
0x18002e0ea  mov     [rbp+70h+var_30], rax
0x18002e0ee  mov     rsi, rdx
0x18002e0f1  mov     r15, rcx
0x18002e0f4  mov     [rsp+170h+pv], 0; int
0x18002e0fd  xor     edx, edx; Val
0x18002e0ff  mov     r8d, 100h; Size
0x18002e105  lea     rcx, [rsp+170h+var_130]; void *
0x18002e10a  call    memset
0x18002e10f  mov     [rsp+170h+var_140], 0
0x18002e118  lea     r9, [rsp+170h+var_140]
0x18002e11d  mov     edi, 80h
0x18002e122  mov     r8d, edi
0x18002e125  lea     rdx, [rsp+170h+var_130]
0x18002e12a  mov     rcx, rsi
0x18002e12d  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18002e132  mov     ebx, eax
0x18002e134  test    eax, eax
0x18002e136  jns     short loc_18002E151
0x18002e138  mov     rcx, [rsi+70h]
0x18002e13c  test    rcx, rcx
0x18002e13f  jz      loc_18002E287
0x18002e145  mov     rdx, [rcx]
0x18002e148  mov     rax, [rdx+18h]
0x18002e14c  jmp     loc_18002E282
0x18002e151  mov     rax, [rsp+170h+var_140]
0x18002e156  cmp     rax, rdi
0x18002e159  ja      short loc_18002E185
0x18002e15b  lea     r8, [rax-1]
0x18002e15f  lea     rdx, [rsp+170h+var_130]
0x18002e164  lea     rcx, [rsp+170h+pv]
0x18002e169  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18002e16e  mov     ebx, eax
0x18002e170  test    eax, eax
0x18002e172  jns     short loc_18002E17E
0x18002e174  mov     edx, 15Fh
0x18002e179  jmp     loc_18002E24F
0x18002e17e  mov     rbx, [rsp+170h+pv]
0x18002e183  jmp     short loc_18002E1CB
0x18002e185  mov     rdi, rax
0x18002e188  lea     r8, [rax-1]
0x18002e18c  xor     edx, edx
0x18002e18e  lea     rcx, [rsp+170h+pv]
0x18002e193  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18002e198  mov     ebx, eax
0x18002e19a  test    eax, eax
0x18002e19c  js      loc_18002E24A
0x18002e1a2  lea     r9, [rsp+170h+var_140]
0x18002e1a7  mov     r8, rdi
0x18002e1aa  mov     rbx, [rsp+170h+pv]
0x18002e1af  mov     rdx, rbx
0x18002e1b2  mov     rcx, rsi
0x18002e1b5  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18002e1ba  mov     r14d, eax
0x18002e1bd  test    eax, eax
0x18002e1bf  js      short loc_18002E222
0x18002e1c1  mov     rax, [rsp+170h+var_140]
0x18002e1c6  cmp     rax, rdi
0x18002e1c9  ja      short loc_18002E185
0x18002e1cb  lea     rax, [rsp+170h+var_148]
0x18002e1d0  cmp     r15, rax
0x18002e1d3  jz      short loc_18002E1FB
0x18002e1d5  mov     r14, [r15]
0x18002e1d8  test    r14, r14
0x18002e1db  jz      short loc_18002E1F6
0x18002e1dd  call    cs:__imp_GetLastError
0x18002e1e3  mov     edi, eax
0x18002e1e5  mov     rcx, r14; pv
0x18002e1e8  call    cs:__imp_CoTaskMemFree
0x18002e1ee  mov     ecx, edi; dwErrCode
0x18002e1f0  call    cs:__imp_SetLastError
0x18002e1f6  mov     [r15], rbx
0x18002e1f9  jmp     short loc_18002E209
0x18002e1fb  test    rbx, rbx
0x18002e1fe  jz      short loc_18002E209
0x18002e200  mov     rcx, rbx; pv
0x18002e203  call    cs:__imp_CoTaskMemFree
0x18002e209  mov     rcx, [rsi+70h]
0x18002e20d  test    rcx, rcx
0x18002e210  jz      short loc_18002E21E
0x18002e212  mov     rax, [rcx]
0x18002e215  mov     rax, [rax+18h]
0x18002e219  call    _guard_dispatch_icall
0x18002e21e  xor     eax, eax
0x18002e220  jmp     short loc_18002E289
0x18002e222  test    rbx, rbx
0x18002e225  jz      short loc_18002E230
0x18002e227  mov     rcx, rbx; pv
0x18002e22a  call    cs:__imp_CoTaskMemFree
0x18002e230  mov     rcx, [rsi+70h]
0x18002e234  test    rcx, rcx
0x18002e237  jz      short loc_18002E245
0x18002e239  mov     rax, [rcx]
0x18002e23c  mov     rax, [rax+18h]
0x18002e240  call    _guard_dispatch_icall
0x18002e245  mov     eax, r14d
0x18002e248  jmp     short loc_18002E289
0x18002e24a  mov     edx, 16Ah; void *
0x18002e24f  mov     r9d, ebx; char *
0x18002e252  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002e259  mov     rcx, [rbp+78h]; this
0x18002e25d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e262  mov     rcx, [rsp+170h+pv]; pv
0x18002e267  test    rcx, rcx
0x18002e26a  jz      short loc_18002E272
0x18002e26c  call    cs:__imp_CoTaskMemFree
0x18002e272  mov     rcx, [rsi+70h]
0x18002e276  test    rcx, rcx
0x18002e279  jz      short loc_18002E287
0x18002e27b  mov     rax, [rcx]
0x18002e27e  mov     rax, [rax+18h]
0x18002e282  call    _guard_dispatch_icall
0x18002e287  mov     eax, ebx
0x18002e289  mov     rcx, [rbp+70h+var_30]
0x18002e28d  xor     rcx, rsp; StackCookie
0x18002e290  call    __security_check_cookie
0x18002e295  mov     rbx, [rsp+170h+arg_10]
0x18002e29d  add     rsp, 150h
0x18002e2a4  pop     r15
0x18002e2a6  pop     r14
0x18002e2a8  pop     rdi
0x18002e2a9  pop     rsi
0x18002e2aa  pop     rbp
0x18002e2ab  retn
```
