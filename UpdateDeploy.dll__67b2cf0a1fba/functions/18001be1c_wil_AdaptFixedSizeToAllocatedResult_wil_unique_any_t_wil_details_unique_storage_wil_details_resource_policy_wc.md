# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18001be1c`
- end: `0x18001c00c`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c110`

## callees

- `0x180003180`
- `0x18001bc58`
- `0x18001bdb8`
- `0x18001be1c`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bf84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bfc9`

## string_xrefs

- `0x18001bfac`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
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
  _BYTE v21[512]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  pv = 0;
  memset(v21, 0, sizeof(v21));
  v20[0] = 0;
  v4 = wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v21, 256, v20);
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
  if ( v20[0] > 0x100u )
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
0x18001be1c  mov     [rsp-8+arg_10], rbx
0x18001be21  push    rbp
0x18001be22  push    rsi
0x18001be23  push    rdi
0x18001be24  push    r14
0x18001be26  push    r15
0x18001be28  lea     rbp, [rsp-150h]
0x18001be30  sub     rsp, 250h
0x18001be37  mov     rax, cs:__security_cookie
0x18001be3e  xor     rax, rsp
0x18001be41  mov     [rbp+170h+var_30], rax
0x18001be48  mov     rsi, rdx
0x18001be4b  mov     r15, rcx
0x18001be4e  mov     [rsp+270h+pv], 0; int
0x18001be57  xor     edx, edx; Val
0x18001be59  mov     r8d, 200h; Size
0x18001be5f  lea     rcx, [rsp+270h+var_230]; void *
0x18001be64  call    memset
0x18001be69  mov     [rsp+270h+var_240], 0
0x18001be72  lea     r9, [rsp+270h+var_240]
0x18001be77  mov     edi, 100h
0x18001be7c  mov     r8d, edi
0x18001be7f  lea     rdx, [rsp+270h+var_230]
0x18001be84  mov     rcx, rsi
0x18001be87  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18001be8c  mov     ebx, eax
0x18001be8e  test    eax, eax
0x18001be90  jns     short loc_18001BEAB
0x18001be92  mov     rcx, [rsi+70h]
0x18001be96  test    rcx, rcx
0x18001be99  jz      loc_18001BFE4
0x18001be9f  mov     rdx, [rcx]
0x18001bea2  mov     rax, [rdx+18h]
0x18001bea6  jmp     loc_18001BFDF
0x18001beab  mov     rax, [rsp+270h+var_240]
0x18001beb0  cmp     rax, rdi
0x18001beb3  ja      short loc_18001BEDF
0x18001beb5  lea     r8, [rax-1]
0x18001beb9  lea     rdx, [rsp+270h+var_230]
0x18001bebe  lea     rcx, [rsp+270h+pv]
0x18001bec3  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18001bec8  mov     ebx, eax
0x18001beca  test    eax, eax
0x18001becc  jns     short loc_18001BED8
0x18001bece  mov     edx, 15Fh
0x18001bed3  jmp     loc_18001BFA9
0x18001bed8  mov     rbx, [rsp+270h+pv]
0x18001bedd  jmp     short loc_18001BF25
0x18001bedf  mov     rdi, rax
0x18001bee2  lea     r8, [rax-1]
0x18001bee6  xor     edx, edx
0x18001bee8  lea     rcx, [rsp+270h+pv]
0x18001beed  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18001bef2  mov     ebx, eax
0x18001bef4  test    eax, eax
0x18001bef6  js      loc_18001BFA4
0x18001befc  lea     r9, [rsp+270h+var_240]
0x18001bf01  mov     r8, rdi
0x18001bf04  mov     rbx, [rsp+270h+pv]
0x18001bf09  mov     rdx, rbx
0x18001bf0c  mov     rcx, rsi
0x18001bf0f  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18001bf14  mov     r14d, eax
0x18001bf17  test    eax, eax
0x18001bf19  js      short loc_18001BF7C
0x18001bf1b  mov     rax, [rsp+270h+var_240]
0x18001bf20  cmp     rax, rdi
0x18001bf23  ja      short loc_18001BEDF
0x18001bf25  lea     rax, [rsp+270h+var_248]
0x18001bf2a  cmp     r15, rax
0x18001bf2d  jz      short loc_18001BF55
0x18001bf2f  mov     r14, [r15]
0x18001bf32  test    r14, r14
0x18001bf35  jz      short loc_18001BF50
0x18001bf37  call    cs:__imp_GetLastError
0x18001bf3d  mov     edi, eax
0x18001bf3f  mov     rcx, r14; pv
0x18001bf42  call    cs:__imp_CoTaskMemFree
0x18001bf48  mov     ecx, edi; dwErrCode
0x18001bf4a  call    cs:__imp_SetLastError
0x18001bf50  mov     [r15], rbx
0x18001bf53  jmp     short loc_18001BF63
0x18001bf55  test    rbx, rbx
0x18001bf58  jz      short loc_18001BF63
0x18001bf5a  mov     rcx, rbx; pv
0x18001bf5d  call    cs:__imp_CoTaskMemFree
0x18001bf63  mov     rcx, [rsi+70h]
0x18001bf67  test    rcx, rcx
0x18001bf6a  jz      short loc_18001BF78
0x18001bf6c  mov     rax, [rcx]
0x18001bf6f  mov     rax, [rax+18h]
0x18001bf73  call    _guard_dispatch_icall
0x18001bf78  xor     eax, eax
0x18001bf7a  jmp     short loc_18001BFE6
0x18001bf7c  test    rbx, rbx
0x18001bf7f  jz      short loc_18001BF8A
0x18001bf81  mov     rcx, rbx; pv
0x18001bf84  call    cs:__imp_CoTaskMemFree
0x18001bf8a  mov     rcx, [rsi+70h]
0x18001bf8e  test    rcx, rcx
0x18001bf91  jz      short loc_18001BF9F
0x18001bf93  mov     rax, [rcx]
0x18001bf96  mov     rax, [rax+18h]
0x18001bf9a  call    _guard_dispatch_icall
0x18001bf9f  mov     eax, r14d
0x18001bfa2  jmp     short loc_18001BFE6
0x18001bfa4  mov     edx, 16Ah; void *
0x18001bfa9  mov     r9d, ebx; char *
0x18001bfac  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001bfb3  mov     rcx, [rbp+178h]; this
0x18001bfba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bfbf  mov     rcx, [rsp+270h+pv]; pv
0x18001bfc4  test    rcx, rcx
0x18001bfc7  jz      short loc_18001BFCF
0x18001bfc9  call    cs:__imp_CoTaskMemFree
0x18001bfcf  mov     rcx, [rsi+70h]
0x18001bfd3  test    rcx, rcx
0x18001bfd6  jz      short loc_18001BFE4
0x18001bfd8  mov     rax, [rcx]
0x18001bfdb  mov     rax, [rax+18h]
0x18001bfdf  call    _guard_dispatch_icall
0x18001bfe4  mov     eax, ebx
0x18001bfe6  mov     rcx, [rbp+170h+var_30]
0x18001bfed  xor     rcx, rsp; StackCookie
0x18001bff0  call    __security_check_cookie
0x18001bff5  mov     rbx, [rsp+270h+arg_10]
0x18001bffd  add     rsp, 250h
0x18001c004  pop     r15
0x18001c006  pop     r14
0x18001c008  pop     rdi
0x18001c009  pop     rsi
0x18001c00a  pop     rbp
0x18001c00b  retn
```
