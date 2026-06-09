# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x14004415c`
- end: `0x14004434c`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140044450`

## callees

- `0x140008de4`
- `0x140044068`
- `0x1400440f8`
- `0x14004415c`
- `0x140045dc0`
- `0x14004cd00`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004428a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004428a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004429d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400442c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004429d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400442c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044309`

## string_xrefs

- `0x1400442ec`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
0x14004415c  mov     [rsp-8+arg_10], rbx
0x140044161  push    rbp
0x140044162  push    rsi
0x140044163  push    rdi
0x140044164  push    r14
0x140044166  push    r15
0x140044168  lea     rbp, [rsp-150h]
0x140044170  sub     rsp, 250h
0x140044177  mov     rax, cs:__security_cookie
0x14004417e  xor     rax, rsp
0x140044181  mov     [rbp+170h+var_30], rax
0x140044188  mov     rsi, rdx
0x14004418b  mov     r15, rcx
0x14004418e  mov     [rsp+270h+pv], 0; int
0x140044197  xor     edx, edx; Val
0x140044199  mov     r8d, 200h; Size
0x14004419f  lea     rcx, [rsp+270h+var_230]; void *
0x1400441a4  call    memset
0x1400441a9  mov     [rsp+270h+var_240], 0
0x1400441b2  lea     r9, [rsp+270h+var_240]
0x1400441b7  mov     edi, 100h
0x1400441bc  mov     r8d, edi
0x1400441bf  lea     rdx, [rsp+270h+var_230]
0x1400441c4  mov     rcx, rsi
0x1400441c7  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x1400441cc  mov     ebx, eax
0x1400441ce  test    eax, eax
0x1400441d0  jns     short loc_1400441EB
0x1400441d2  mov     rcx, [rsi+70h]
0x1400441d6  test    rcx, rcx
0x1400441d9  jz      loc_140044324
0x1400441df  mov     rdx, [rcx]
0x1400441e2  mov     rax, [rdx+18h]
0x1400441e6  jmp     loc_14004431F
0x1400441eb  mov     rax, [rsp+270h+var_240]
0x1400441f0  cmp     rax, rdi
0x1400441f3  ja      short loc_14004421F
0x1400441f5  lea     r8, [rax-1]
0x1400441f9  lea     rdx, [rsp+270h+var_230]
0x1400441fe  lea     rcx, [rsp+270h+pv]
0x140044203  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x140044208  mov     ebx, eax
0x14004420a  test    eax, eax
0x14004420c  jns     short loc_140044218
0x14004420e  mov     edx, 15Fh
0x140044213  jmp     loc_1400442E9
0x140044218  mov     rbx, [rsp+270h+pv]
0x14004421d  jmp     short loc_140044265
0x14004421f  mov     rdi, rax
0x140044222  lea     r8, [rax-1]
0x140044226  xor     edx, edx
0x140044228  lea     rcx, [rsp+270h+pv]
0x14004422d  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x140044232  mov     ebx, eax
0x140044234  test    eax, eax
0x140044236  js      loc_1400442E4
0x14004423c  lea     r9, [rsp+270h+var_240]
0x140044241  mov     r8, rdi
0x140044244  mov     rbx, [rsp+270h+pv]
0x140044249  mov     rdx, rbx
0x14004424c  mov     rcx, rsi
0x14004424f  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x140044254  mov     r14d, eax
0x140044257  test    eax, eax
0x140044259  js      short loc_1400442BC
0x14004425b  mov     rax, [rsp+270h+var_240]
0x140044260  cmp     rax, rdi
0x140044263  ja      short loc_14004421F
0x140044265  lea     rax, [rsp+270h+var_248]
0x14004426a  cmp     r15, rax
0x14004426d  jz      short loc_140044295
0x14004426f  mov     r14, [r15]
0x140044272  test    r14, r14
0x140044275  jz      short loc_140044290
0x140044277  call    cs:__imp_GetLastError
0x14004427d  mov     edi, eax
0x14004427f  mov     rcx, r14; pv
0x140044282  call    cs:__imp_CoTaskMemFree
0x140044288  mov     ecx, edi; dwErrCode
0x14004428a  call    cs:__imp_SetLastError
0x140044290  mov     [r15], rbx
0x140044293  jmp     short loc_1400442A3
0x140044295  test    rbx, rbx
0x140044298  jz      short loc_1400442A3
0x14004429a  mov     rcx, rbx; pv
0x14004429d  call    cs:__imp_CoTaskMemFree
0x1400442a3  mov     rcx, [rsi+70h]
0x1400442a7  test    rcx, rcx
0x1400442aa  jz      short loc_1400442B8
0x1400442ac  mov     rax, [rcx]
0x1400442af  mov     rax, [rax+18h]
0x1400442b3  call    _guard_dispatch_icall
0x1400442b8  xor     eax, eax
0x1400442ba  jmp     short loc_140044326
0x1400442bc  test    rbx, rbx
0x1400442bf  jz      short loc_1400442CA
0x1400442c1  mov     rcx, rbx; pv
0x1400442c4  call    cs:__imp_CoTaskMemFree
0x1400442ca  mov     rcx, [rsi+70h]
0x1400442ce  test    rcx, rcx
0x1400442d1  jz      short loc_1400442DF
0x1400442d3  mov     rax, [rcx]
0x1400442d6  mov     rax, [rax+18h]
0x1400442da  call    _guard_dispatch_icall
0x1400442df  mov     eax, r14d
0x1400442e2  jmp     short loc_140044326
0x1400442e4  mov     edx, 16Ah; void *
0x1400442e9  mov     r9d, ebx; char *
0x1400442ec  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400442f3  mov     rcx, [rbp+178h]; this
0x1400442fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400442ff  mov     rcx, [rsp+270h+pv]; pv
0x140044304  test    rcx, rcx
0x140044307  jz      short loc_14004430F
0x140044309  call    cs:__imp_CoTaskMemFree
0x14004430f  mov     rcx, [rsi+70h]
0x140044313  test    rcx, rcx
0x140044316  jz      short loc_140044324
0x140044318  mov     rax, [rcx]
0x14004431b  mov     rax, [rax+18h]
0x14004431f  call    _guard_dispatch_icall
0x140044324  mov     eax, ebx
0x140044326  mov     rcx, [rbp+170h+var_30]
0x14004432d  xor     rcx, rsp; StackCookie
0x140044330  call    __security_check_cookie
0x140044335  mov     rbx, [rsp+270h+arg_10]
0x14004433d  add     rsp, 250h
0x140044344  pop     r15
0x140044346  pop     r14
0x140044348  pop     rdi
0x140044349  pop     rsi
0x14004434a  pop     rbp
0x14004434b  retn
```
