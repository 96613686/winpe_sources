# Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18000b680`
- end: `0x18000b7ce`
- name: `?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(char *, __int64, LPVOID *, const char *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ab90`
- `0x18000b1f4`
- `0x18000c400`

## callees

- `0x180001620`
- `0x180006804`
- `0x18000ad54`
- `0x18000b020`
- `0x18000b680`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b78e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b78e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b796`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b783`

## string_xrefs

- `0x18000b74a`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\persistentlocationhelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
        char *a1,
        __int64 a2,
        LPVOID *a3,
        const char *a4)
{
  LPVOID v5; // r14
  void *v6; // rsi
  DWORD LastError; // ebx
  void *v8; // rcx
  int v9; // ebx
  LPVOID pv; // [rsp+20h] [rbp-69h] BYREF
  void *v12; // [rsp+28h] [rbp-61h] BYREF
  char *v13; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v14[8]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v15[13]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD *v16; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  __int64 v18; // [rsp+F8h] [rbp+6Fh] BYREF

  v18 = a2;
  v13 = a1;
  if ( !a2 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v12,
      a1,
      0xFFFFFFFFFFFFFFFFuLL,
      a4);
    if ( a3 == &v12 )
    {
      v8 = v12;
LABEL_18:
      if ( v8 )
        CoTaskMemFree(v8);
      return 0;
    }
    v5 = v12;
    v6 = *a3;
    if ( !*a3 )
    {
LABEL_16:
      *a3 = v5;
      v8 = 0;
      goto LABEL_18;
    }
    LastError = GetLastError();
LABEL_15:
    CoTaskMemFree(v6);
    SetLastError(LastError);
    goto LABEL_16;
  }
  pv = 0;
  v15[0] = &wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v15[1] = &v13;
  v15[2] = &v18;
  v16 = v15;
  v9 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         (char *)&pv,
         (__int64)v14);
  if ( v16 )
    (*(void (__fastcall **)(_QWORD *))(*v16 + 24LL))(v16);
  if ( v9 >= 0 )
  {
    if ( a3 == &pv )
    {
      v8 = pv;
      goto LABEL_18;
    }
    v5 = pv;
    v6 = *a3;
    if ( !*a3 )
      goto LABEL_16;
    LastError = GetLastError();
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F,
    (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\persistentlocationhelper.h",
    (const char *)(unsigned int)v9,
    (int)pv);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b680  mov     [rsp-8+arg_8], rdx
0x18000b685  push    rbp
0x18000b686  push    rbx
0x18000b687  push    rsi
0x18000b688  push    rdi
0x18000b689  push    r14
0x18000b68b  lea     rbp, [rsp-37h]
0x18000b690  sub     rsp, 0C0h
0x18000b697  mov     rax, cs:__security_cookie
0x18000b69e  xor     rax, rsp
0x18000b6a1  mov     [rbp+57h+var_28], rax
0x18000b6a5  mov     rdi, r8
0x18000b6a8  mov     [rbp+57h+var_B0], rcx
0x18000b6ac  test    rdx, rdx
0x18000b6af  jnz     short loc_18000B6F0
0x18000b6b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b6b5  mov     rdx, rcx
0x18000b6b8  lea     rcx, [rbp+57h+var_B8]
0x18000b6bc  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000b6c1  lea     rax, [rbp+57h+var_B8]
0x18000b6c5  cmp     rdi, rax
0x18000b6c8  jz      short loc_18000B6E7
0x18000b6ca  mov     r14, [rbp+57h+var_B8]
0x18000b6ce  mov     rsi, [rdi]
0x18000b6d1  test    rsi, rsi
0x18000b6d4  jz      loc_18000B79C
0x18000b6da  call    cs:__imp_GetLastError
0x18000b6e0  mov     ebx, eax
0x18000b6e2  jmp     loc_18000B78B
0x18000b6e7  mov     rcx, [rbp+57h+var_B8]
0x18000b6eb  jmp     loc_18000B7A7
0x18000b6f0  mov     [rbp+57h+pv], 0
0x18000b6f8  lea     rax, ??_7?$__func@V_lambda_42d7dced1872ed24a4c1197da8e68253_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000b6ff  mov     [rbp+57h+var_98], rax
0x18000b703  lea     rax, [rbp+57h+var_B0]
0x18000b707  mov     [rbp+57h+var_90], rax
0x18000b70b  lea     rax, [rbp+57h+arg_8]
0x18000b70f  mov     [rbp+57h+var_88], rax
0x18000b713  lea     rax, [rbp+57h+var_98]
0x18000b717  mov     [rbp+57h+var_30], rax
0x18000b71b  lea     rdx, [rbp+57h+var_A0]
0x18000b71f  lea     rcx, [rbp+57h+pv]
0x18000b723  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18000b728  mov     ebx, eax
0x18000b72a  mov     rcx, [rbp+57h+var_30]
0x18000b72e  test    rcx, rcx
0x18000b731  jz      short loc_18000B73F
0x18000b733  mov     rdx, [rcx]
0x18000b736  mov     rax, [rdx+18h]
0x18000b73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b73f  test    ebx, ebx
0x18000b741  jns     short loc_18000B76E
0x18000b743  mov     rcx, [rbp+5Fh]; this
0x18000b747  mov     r9d, ebx; char *
0x18000b74a  lea     r8, aShellcommondes; "shellcommondesktopbase\\base\\embedded"...
0x18000b751  mov     edx, 1Fh; void *
0x18000b756  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b75b  mov     rcx, [rbp+57h+pv]; pv
0x18000b75f  test    rcx, rcx
0x18000b762  jz      short loc_18000B76A
0x18000b764  call    cs:__imp_CoTaskMemFree
0x18000b76a  mov     eax, ebx
0x18000b76c  jmp     short loc_18000B7B4
0x18000b76e  lea     rax, [rbp+57h+pv]
0x18000b772  cmp     rdi, rax
0x18000b775  jz      short loc_18000B7A3
0x18000b777  mov     r14, [rbp+57h+pv]
0x18000b77b  mov     rsi, [rdi]
0x18000b77e  test    rsi, rsi
0x18000b781  jz      short loc_18000B79C
0x18000b783  call    cs:__imp_GetLastError
0x18000b789  mov     ebx, eax
0x18000b78b  mov     rcx, rsi; pv
0x18000b78e  call    cs:__imp_CoTaskMemFree
0x18000b794  mov     ecx, ebx; dwErrCode
0x18000b796  call    cs:__imp_SetLastError
0x18000b79c  mov     [rdi], r14
0x18000b79f  xor     ecx, ecx
0x18000b7a1  jmp     short loc_18000B7A7
0x18000b7a3  mov     rcx, [rbp+57h+pv]; pv
0x18000b7a7  test    rcx, rcx
0x18000b7aa  jz      short loc_18000B7B2
0x18000b7ac  call    cs:__imp_CoTaskMemFree
0x18000b7b2  xor     eax, eax
0x18000b7b4  mov     rcx, [rbp+57h+var_28]
0x18000b7b8  xor     rcx, rsp; StackCookie
0x18000b7bb  call    __security_check_cookie
0x18000b7c0  add     rsp, 0C0h
0x18000b7c7  pop     r14
0x18000b7c9  pop     rdi
0x18000b7ca  pop     rsi
0x18000b7cb  pop     rbx
0x18000b7cc  pop     rbp
0x18000b7cd  retn
```
