# wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>)

- ea: `0x18002fb54`
- end: `0x18002fd44`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@V?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fe60`

## callees

- `0x180007804`
- `0x18002f990`
- `0x18002faf0`
- `0x18002fb54`
- `0x180056500`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fcbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fd01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fc95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fcbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fd01`

## string_xrefs

- `0x18002fce4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

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
0x18002fb54  mov     [rsp-8+arg_10], rbx
0x18002fb59  push    rbp
0x18002fb5a  push    rsi
0x18002fb5b  push    rdi
0x18002fb5c  push    r14
0x18002fb5e  push    r15
0x18002fb60  lea     rbp, [rsp-150h]
0x18002fb68  sub     rsp, 250h
0x18002fb6f  mov     rax, cs:__security_cookie
0x18002fb76  xor     rax, rsp
0x18002fb79  mov     [rbp+170h+var_30], rax
0x18002fb80  mov     rsi, rdx
0x18002fb83  mov     r15, rcx
0x18002fb86  mov     [rsp+270h+pv], 0; int
0x18002fb8f  xor     edx, edx; Val
0x18002fb91  mov     r8d, 200h; Size
0x18002fb97  lea     rcx, [rsp+270h+var_230]; void *
0x18002fb9c  call    memset
0x18002fba1  mov     [rsp+270h+var_240], 0
0x18002fbaa  lea     r9, [rsp+270h+var_240]
0x18002fbaf  mov     edi, 100h
0x18002fbb4  mov     r8d, edi
0x18002fbb7  lea     rdx, [rsp+270h+var_230]
0x18002fbbc  mov     rcx, rsi
0x18002fbbf  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18002fbc4  mov     ebx, eax
0x18002fbc6  test    eax, eax
0x18002fbc8  jns     short loc_18002FBE3
0x18002fbca  mov     rcx, [rsi+70h]
0x18002fbce  test    rcx, rcx
0x18002fbd1  jz      loc_18002FD1C
0x18002fbd7  mov     rdx, [rcx]
0x18002fbda  mov     rax, [rdx+18h]
0x18002fbde  jmp     loc_18002FD17
0x18002fbe3  mov     rax, [rsp+270h+var_240]
0x18002fbe8  cmp     rax, rdi
0x18002fbeb  ja      short loc_18002FC17
0x18002fbed  lea     r8, [rax-1]
0x18002fbf1  lea     rdx, [rsp+270h+var_230]
0x18002fbf6  lea     rcx, [rsp+270h+pv]
0x18002fbfb  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18002fc00  mov     ebx, eax
0x18002fc02  test    eax, eax
0x18002fc04  jns     short loc_18002FC10
0x18002fc06  mov     edx, 15Fh
0x18002fc0b  jmp     loc_18002FCE1
0x18002fc10  mov     rbx, [rsp+270h+pv]
0x18002fc15  jmp     short loc_18002FC5D
0x18002fc17  mov     rdi, rax
0x18002fc1a  lea     r8, [rax-1]
0x18002fc1e  xor     edx, edx
0x18002fc20  lea     rcx, [rsp+270h+pv]
0x18002fc25  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)
0x18002fc2a  mov     ebx, eax
0x18002fc2c  test    eax, eax
0x18002fc2e  js      loc_18002FCDC
0x18002fc34  lea     r9, [rsp+270h+var_240]
0x18002fc39  mov     r8, rdi
0x18002fc3c  mov     rbx, [rsp+270h+pv]
0x18002fc41  mov     rdx, rbx
0x18002fc44  mov     rcx, rsi
0x18002fc47  call    ??R?$function@$$A6AJPEA_W_KPEA_K@Z@wistd@@QEBAJPEA_W_KPEA_K@Z; wistd::function<long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t *,unsigned __int64,unsigned __int64 *)
0x18002fc4c  mov     r14d, eax
0x18002fc4f  test    eax, eax
0x18002fc51  js      short loc_18002FCB4
0x18002fc53  mov     rax, [rsp+270h+var_240]
0x18002fc58  cmp     rax, rdi
0x18002fc5b  ja      short loc_18002FC17
0x18002fc5d  lea     rax, [rsp+270h+var_248]
0x18002fc62  cmp     r15, rax
0x18002fc65  jz      short loc_18002FC8D
0x18002fc67  mov     r14, [r15]
0x18002fc6a  test    r14, r14
0x18002fc6d  jz      short loc_18002FC88
0x18002fc6f  call    cs:__imp_GetLastError
0x18002fc75  mov     edi, eax
0x18002fc77  mov     rcx, r14; pv
0x18002fc7a  call    cs:__imp_CoTaskMemFree
0x18002fc80  mov     ecx, edi; dwErrCode
0x18002fc82  call    cs:__imp_SetLastError
0x18002fc88  mov     [r15], rbx
0x18002fc8b  jmp     short loc_18002FC9B
0x18002fc8d  test    rbx, rbx
0x18002fc90  jz      short loc_18002FC9B
0x18002fc92  mov     rcx, rbx; pv
0x18002fc95  call    cs:__imp_CoTaskMemFree
0x18002fc9b  mov     rcx, [rsi+70h]
0x18002fc9f  test    rcx, rcx
0x18002fca2  jz      short loc_18002FCB0
0x18002fca4  mov     rax, [rcx]
0x18002fca7  mov     rax, [rax+18h]
0x18002fcab  call    _guard_dispatch_icall
0x18002fcb0  xor     eax, eax
0x18002fcb2  jmp     short loc_18002FD1E
0x18002fcb4  test    rbx, rbx
0x18002fcb7  jz      short loc_18002FCC2
0x18002fcb9  mov     rcx, rbx; pv
0x18002fcbc  call    cs:__imp_CoTaskMemFree
0x18002fcc2  mov     rcx, [rsi+70h]
0x18002fcc6  test    rcx, rcx
0x18002fcc9  jz      short loc_18002FCD7
0x18002fccb  mov     rax, [rcx]
0x18002fcce  mov     rax, [rax+18h]
0x18002fcd2  call    _guard_dispatch_icall
0x18002fcd7  mov     eax, r14d
0x18002fcda  jmp     short loc_18002FD1E
0x18002fcdc  mov     edx, 16Ah; void *
0x18002fce1  mov     r9d, ebx; char *
0x18002fce4  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18002fceb  mov     rcx, [rbp+178h]; this
0x18002fcf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fcf7  mov     rcx, [rsp+270h+pv]; pv
0x18002fcfc  test    rcx, rcx
0x18002fcff  jz      short loc_18002FD07
0x18002fd01  call    cs:__imp_CoTaskMemFree
0x18002fd07  mov     rcx, [rsi+70h]
0x18002fd0b  test    rcx, rcx
0x18002fd0e  jz      short loc_18002FD1C
0x18002fd10  mov     rax, [rcx]
0x18002fd13  mov     rax, [rax+18h]
0x18002fd17  call    _guard_dispatch_icall
0x18002fd1c  mov     eax, ebx
0x18002fd1e  mov     rcx, [rbp+170h+var_30]
0x18002fd25  xor     rcx, rsp; StackCookie
0x18002fd28  call    __security_check_cookie
0x18002fd2d  mov     rbx, [rsp+270h+arg_10]
0x18002fd35  add     rsp, 250h
0x18002fd3c  pop     r15
0x18002fd3e  pop     r14
0x18002fd40  pop     rdi
0x18002fd41  pop     rsi
0x18002fd42  pop     rbp
0x18002fd43  retn
```
