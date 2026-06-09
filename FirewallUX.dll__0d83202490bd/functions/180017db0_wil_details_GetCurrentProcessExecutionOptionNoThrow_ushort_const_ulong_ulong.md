# wil::details::GetCurrentProcessExecutionOptionNoThrow(ushort const *,ulong,ulong *)

- ea: `0x180017db0`
- end: `0x180017fb4`
- name: `?GetCurrentProcessExecutionOptionNoThrow@details@wil@@YAJPEBGKPEAK@Z`
- size: `516`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800184dc`

## callees

- `0x1800021c0`
- `0x180009544`
- `0x180015284`
- `0x180015608`
- `0x180017db0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180017e7f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180017e7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017e65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017f88`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017f62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017f62`

## string_xrefs

- `0x180017e47`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x180017eea`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::details::GetCurrentProcessExecutionOptionNoThrow(
        wil::details *this,
        const unsigned __int16 *a2,
        _DWORD *a3,
        unsigned int *a4)
{
  int v5; // ebx
  void *v7; // rbx
  wchar_t *v8; // rax
  void *v9; // r8
  wchar_t *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // edi
  WCHAR *v14; // rdi
  int pdwType; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 pvData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v20[13]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v21; // [rsp+C8h] [rbp-38h]
  _QWORD v22[6]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  v20[0] = wistd::__function::Z::$$A6AJPEAG_KPEA_K::Z::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>'::`2'::_lambda_1_,AJPEAXPEAUHINSTANCE__,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &>::`vftable';
  *a3 = 0;
  v20[1] = &lpSubKey;
  pv = 0;
  v20[2] = &pvData;
  pvData = 0;
  v21 = v20;
  lpSubKey = 0;
  v5 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
         (char *)&pv,
         (__int64)v19);
  if ( v21 )
    (*(void (__fastcall **)(_QWORD *))(*v21 + 24LL))(v21);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      (const char *)(unsigned int)v5,
      pdwType);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v5;
  }
  v7 = pv;
  v8 = wcsrchr((const wchar_t *)pv, 0x5Cu);
  if ( v8 )
  {
    v10 = v8 + 1;
    lpSubKey = 0;
    if ( v8 == (wchar_t *)-2LL )
    {
      v11 = 0;
    }
    else
    {
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
    }
    v22[4] = v10;
    v22[2] = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\";
    v22[0] = 0;
    v22[1] = 0;
    v22[3] = 74;
    v22[5] = v11;
    v12 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (int *)&lpSubKey,
            (__int64)v22,
            v9);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AD,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
        (const char *)(unsigned int)v12,
        pdwType);
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
      if ( v7 )
        CoTaskMemFree(v7);
      return v13;
    }
    v14 = (WCHAR *)lpSubKey;
    LODWORD(pvData) = 0;
    LODWORD(pv) = 4;
    if ( !RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"WaitForDebuggerPresent", 0x10010u, 0, &pvData, (LPDWORD)&pv) )
      *a3 = pvData;
    if ( v14 )
      CoTaskMemFree(v14);
  }
  if ( v7 )
    CoTaskMemFree(v7);
  return 0;
}

```

## disassembly

```asm
0x180017db0  mov     [rsp-8+arg_0], rbx
0x180017db5  mov     [rsp-8+arg_8], rsi
0x180017dba  push    rbp
0x180017dbb  push    rdi
0x180017dbc  push    r14
0x180017dbe  lea     rbp, [rsp-10h]
0x180017dc3  sub     rsp, 110h
0x180017dca  mov     rax, cs:__security_cookie
0x180017dd1  xor     rax, rsp
0x180017dd4  mov     [rbp+20h+var_20], rax
0x180017dd8  xor     r14d, r14d
0x180017ddb  lea     rax, ??_7?$__func@V_lambda_1_@?1???$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180017de2  mov     [rsp+120h+var_C0], rax
0x180017de7  lea     rdx, [rsp+120h+var_C8]
0x180017dec  lea     rax, [rsp+120h+lpSubKey]
0x180017df1  mov     [r8], r14d
0x180017df4  mov     [rsp+120h+var_B8], rax
0x180017df9  lea     rcx, [rsp+120h+pv]
0x180017dfe  lea     rax, [rsp+120h+var_D0]
0x180017e03  mov     [rsp+120h+pv], r14
0x180017e08  mov     [rsp+120h+var_B0], rax
0x180017e0d  mov     rsi, r8
0x180017e10  lea     rax, [rsp+120h+var_C0]
0x180017e15  mov     [rsp+120h+var_D0], r14
0x180017e1a  mov     [rbp+20h+var_58], rax
0x180017e1e  mov     [rsp+120h+lpSubKey], r14
0x180017e23  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x180017e28  mov     rcx, [rbp+20h+var_58]
0x180017e2c  mov     ebx, eax
0x180017e2e  test    rcx, rcx
0x180017e31  jz      short loc_180017E3F
0x180017e33  mov     rdx, [rcx]
0x180017e36  mov     rax, [rdx+18h]
0x180017e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e3f  test    ebx, ebx
0x180017e41  jns     short loc_180017E72
0x180017e43  mov     rcx, [rbp+28h]; this
0x180017e47  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017e4e  mov     r9d, ebx; char *
0x180017e51  mov     edx, 2A7h; void *
0x180017e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e5b  mov     rcx, [rsp+120h+pv]; pv
0x180017e60  test    rcx, rcx
0x180017e63  jz      short loc_180017E6B
0x180017e65  call    cs:__imp_CoTaskMemFree
0x180017e6b  mov     eax, ebx
0x180017e6d  jmp     loc_180017F90
0x180017e72  mov     rbx, [rsp+120h+pv]
0x180017e77  mov     edx, 5Ch ; '\'; Ch
0x180017e7c  mov     rcx, rbx; Str
0x180017e7f  call    cs:__imp_wcsrchr
0x180017e85  test    rax, rax
0x180017e88  jz      loc_180017F80
0x180017e8e  lea     rcx, [rax+2]
0x180017e92  mov     [rsp+120h+lpSubKey], r14
0x180017e97  test    rcx, rcx
0x180017e9a  jz      short loc_180017EAC
0x180017e9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017ea0  inc     rax
0x180017ea3  cmp     [rcx+rax*2], r14w
0x180017ea8  jnz     short loc_180017EA0
0x180017eaa  jmp     short loc_180017EAF
0x180017eac  mov     rax, r14
0x180017eaf  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180017eb6  mov     [rbp+20h+var_30], rcx
0x180017eba  mov     [rbp+20h+var_40], rdx
0x180017ebe  lea     rcx, [rsp+120h+lpSubKey]
0x180017ec3  lea     rdx, [rbp+20h+var_50]
0x180017ec7  mov     [rbp+20h+var_50], r14
0x180017ecb  mov     [rbp+20h+var_48], r14
0x180017ecf  mov     [rbp+20h+var_38], 4Ah ; 'J'
0x180017ed7  mov     [rbp+20h+var_28], rax
0x180017edb  call    ??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z; wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)
0x180017ee0  mov     edi, eax
0x180017ee2  test    eax, eax
0x180017ee4  jns     short loc_180017F20
0x180017ee6  mov     rcx, [rbp+28h]; this
0x180017eea  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017ef1  mov     r9d, eax; char *
0x180017ef4  mov     edx, 2ADh; void *
0x180017ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017efe  mov     rcx, [rsp+120h+lpSubKey]; pv
0x180017f03  test    rcx, rcx
0x180017f06  jz      short loc_180017F0E
0x180017f08  call    cs:__imp_CoTaskMemFree
0x180017f0e  test    rbx, rbx
0x180017f11  jz      short loc_180017F1C
0x180017f13  mov     rcx, rbx; pv
0x180017f16  call    cs:__imp_CoTaskMemFree
0x180017f1c  mov     eax, edi
0x180017f1e  jmp     short loc_180017F90
0x180017f20  mov     rdi, [rsp+120h+lpSubKey]
0x180017f25  lea     rax, [rsp+120h+pv]
0x180017f2a  mov     [rsp+120h+pcbData], rax; pcbData
0x180017f2f  lea     r8, Value; "WaitForDebuggerPresent"
0x180017f36  lea     rax, [rsp+120h+var_D0]
0x180017f3b  mov     dword ptr [rsp+120h+var_D0], r14d
0x180017f40  mov     [rsp+120h+pvData], rax; pvData
0x180017f45  mov     r9d, 10010h; dwFlags
0x180017f4b  mov     rdx, rdi; lpSubKey
0x180017f4e  mov     [rsp+120h+pdwType], r14; pdwType
0x180017f53  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180017f5a  mov     dword ptr [rsp+120h+pv], 4
0x180017f62  call    cs:__imp_RegGetValueW
0x180017f68  test    eax, eax
0x180017f6a  jnz     short loc_180017F72
0x180017f6c  mov     eax, dword ptr [rsp+120h+var_D0]
0x180017f70  mov     [rsi], eax
0x180017f72  test    rdi, rdi
0x180017f75  jz      short loc_180017F80
0x180017f77  mov     rcx, rdi; pv
0x180017f7a  call    cs:__imp_CoTaskMemFree
0x180017f80  test    rbx, rbx
0x180017f83  jz      short loc_180017F8E
0x180017f85  mov     rcx, rbx; pv
0x180017f88  call    cs:__imp_CoTaskMemFree
0x180017f8e  xor     eax, eax
0x180017f90  mov     rcx, [rbp+20h+var_20]
0x180017f94  xor     rcx, rsp; StackCookie
0x180017f97  call    __security_check_cookie
0x180017f9c  lea     r11, [rsp+120h+var_10]
0x180017fa4  mov     rbx, [r11+20h]
0x180017fa8  mov     rsi, [r11+28h]
0x180017fac  mov     rsp, r11
0x180017faf  pop     r14
0x180017fb1  pop     rdi
0x180017fb2  pop     rbp
0x180017fb3  retn
```
