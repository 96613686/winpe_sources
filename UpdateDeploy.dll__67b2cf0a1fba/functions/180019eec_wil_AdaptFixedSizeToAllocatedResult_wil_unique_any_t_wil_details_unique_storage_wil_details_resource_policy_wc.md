# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x180019eec`
- end: `0x18001a0d0`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a1fc`

## callees

- `0x180003180`
- `0x180019eec`
- `0x18001bc58`
- `0x18001bdb8`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a014`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a00c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a04e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a00c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a04e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a090`

## string_xrefs

- `0x18001a076`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x180019eec  mov     [rsp-8+arg_10], rbx
0x180019ef1  push    rbp
0x180019ef2  push    rsi
0x180019ef3  push    rdi
0x180019ef4  push    r14
0x180019ef6  push    r15
0x180019ef8  lea     rbp, [rsp-50h]
0x180019efd  sub     rsp, 150h
0x180019f04  mov     rax, cs:__security_cookie
0x180019f0b  xor     rax, rsp
0x180019f0e  mov     [rbp+70h+var_30], rax
0x180019f12  mov     rsi, rdx
0x180019f15  mov     r15, rcx
0x180019f18  mov     [rsp+170h+pv], 0; int
0x180019f21  xor     edx, edx; Val
0x180019f23  mov     r8d, 100h; Size
0x180019f29  lea     rcx, [rsp+170h+var_130]; void *
0x180019f2e  call    memset
0x180019f33  mov     [rsp+170h+var_140], 0
0x180019f3c  lea     r9, [rsp+170h+var_140]
0x180019f41  mov     edi, 80h
0x180019f46  mov     r8d, edi
0x180019f49  lea     rdx, [rsp+170h+var_130]
0x180019f4e  mov     rcx, rsi
0x180019f51  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180019f56  mov     ebx, eax
0x180019f58  test    eax, eax
0x180019f5a  jns     short loc_180019F75
0x180019f5c  mov     rcx, [rsi+70h]
0x180019f60  test    rcx, rcx
0x180019f63  jz      loc_18001A0AB
0x180019f69  mov     rdx, [rcx]
0x180019f6c  mov     rax, [rdx+18h]
0x180019f70  jmp     loc_18001A0A6
0x180019f75  mov     rax, [rsp+170h+var_140]
0x180019f7a  cmp     rax, rdi
0x180019f7d  ja      short loc_180019FA9
0x180019f7f  lea     r8, [rax-1]
0x180019f83  lea     rdx, [rsp+170h+var_130]
0x180019f88  lea     rcx, [rsp+170h+pv]
0x180019f8d  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180019f92  mov     ebx, eax
0x180019f94  test    eax, eax
0x180019f96  jns     short loc_180019FA2
0x180019f98  mov     edx, 15Fh
0x180019f9d  jmp     loc_18001A073
0x180019fa2  mov     rbx, [rsp+170h+pv]
0x180019fa7  jmp     short loc_180019FEF
0x180019fa9  mov     rdi, rax
0x180019fac  lea     r8, [rax-1]
0x180019fb0  xor     edx, edx
0x180019fb2  lea     rcx, [rsp+170h+pv]
0x180019fb7  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x180019fbc  mov     ebx, eax
0x180019fbe  test    eax, eax
0x180019fc0  js      loc_18001A06E
0x180019fc6  lea     r9, [rsp+170h+var_140]
0x180019fcb  mov     r8, rdi
0x180019fce  mov     rbx, [rsp+170h+pv]
0x180019fd3  mov     rdx, rbx
0x180019fd6  mov     rcx, rsi
0x180019fd9  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x180019fde  mov     r14d, eax
0x180019fe1  test    eax, eax
0x180019fe3  js      short loc_18001A046
0x180019fe5  mov     rax, [rsp+170h+var_140]
0x180019fea  cmp     rax, rdi
0x180019fed  ja      short loc_180019FA9
0x180019fef  lea     rax, [rsp+170h+var_148]
0x180019ff4  cmp     r15, rax
0x180019ff7  jz      short loc_18001A01F
0x180019ff9  mov     r14, [r15]
0x180019ffc  test    r14, r14
0x180019fff  jz      short loc_18001A01A
0x18001a001  call    cs:__imp_GetLastError
0x18001a007  mov     edi, eax
0x18001a009  mov     rcx, r14; pv
0x18001a00c  call    cs:__imp_CoTaskMemFree
0x18001a012  mov     ecx, edi; dwErrCode
0x18001a014  call    cs:__imp_SetLastError
0x18001a01a  mov     [r15], rbx
0x18001a01d  jmp     short loc_18001A02D
0x18001a01f  test    rbx, rbx
0x18001a022  jz      short loc_18001A02D
0x18001a024  mov     rcx, rbx; pv
0x18001a027  call    cs:__imp_CoTaskMemFree
0x18001a02d  mov     rcx, [rsi+70h]
0x18001a031  test    rcx, rcx
0x18001a034  jz      short loc_18001A042
0x18001a036  mov     rax, [rcx]
0x18001a039  mov     rax, [rax+18h]
0x18001a03d  call    _guard_dispatch_icall
0x18001a042  xor     eax, eax
0x18001a044  jmp     short loc_18001A0AD
0x18001a046  test    rbx, rbx
0x18001a049  jz      short loc_18001A054
0x18001a04b  mov     rcx, rbx; pv
0x18001a04e  call    cs:__imp_CoTaskMemFree
0x18001a054  mov     rcx, [rsi+70h]
0x18001a058  test    rcx, rcx
0x18001a05b  jz      short loc_18001A069
0x18001a05d  mov     rax, [rcx]
0x18001a060  mov     rax, [rax+18h]
0x18001a064  call    _guard_dispatch_icall
0x18001a069  mov     eax, r14d
0x18001a06c  jmp     short loc_18001A0AD
0x18001a06e  mov     edx, 16Ah; void *
0x18001a073  mov     r9d, ebx; char *
0x18001a076  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001a07d  mov     rcx, [rbp+78h]; this
0x18001a081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a086  mov     rcx, [rsp+170h+pv]; pv
0x18001a08b  test    rcx, rcx
0x18001a08e  jz      short loc_18001A096
0x18001a090  call    cs:__imp_CoTaskMemFree
0x18001a096  mov     rcx, [rsi+70h]
0x18001a09a  test    rcx, rcx
0x18001a09d  jz      short loc_18001A0AB
0x18001a09f  mov     rax, [rcx]
0x18001a0a2  mov     rax, [rax+18h]
0x18001a0a6  call    _guard_dispatch_icall
0x18001a0ab  mov     eax, ebx
0x18001a0ad  mov     rcx, [rbp+70h+var_30]
0x18001a0b1  xor     rcx, rsp; StackCookie
0x18001a0b4  call    __security_check_cookie
0x18001a0b9  mov     rbx, [rsp+170h+arg_10]
0x18001a0c1  add     rsp, 150h
0x18001a0c8  pop     r15
0x18001a0ca  pop     r14
0x18001a0cc  pop     rdi
0x18001a0cd  pop     rsi
0x18001a0ce  pop     rbp
0x18001a0cf  retn
```
