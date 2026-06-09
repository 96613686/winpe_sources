# WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(HSTRING__ * *)

- ea: `0x1800a54ec`
- end: `0x1800a56fe`
- name: `?FetchXboxLiveAccountId@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(HSTRING *string, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bf58`

## callees

- `0x180004738`
- `0x18002aae8`
- `0x180061c04`
- `0x1800629dc`
- `0x180062a40`
- `0x18006ea74`
- `0x1800a3a88`
- `0x1800a54ec`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a56b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a56b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5645`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a5539`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a5539`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(HSTRING *string, HSTRING *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HRESULT v5; // eax
  __int64 v6; // rdx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, PCNZWCH *, LPVOID *); // r14
  void *v9; // rbx
  WCHAR *v10; // rbx
  int ppv; // [rsp+20h] [rbp-40h]
  UINT32 length[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v15; // [rsp+90h] [rbp+30h] BYREF
  PCNZWCH sourceString; // [rsp+98h] [rbp+38h] BYREF
  LPVOID v17; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF

  sourceString = 0;
  pv = 0;
  *string = 0;
  v17 = 0;
  v3 = CoCreateInstance(
         &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
         0,
         0x17u,
         &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
         &v17);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v15 = 0;
    v5 = Microsoft::WRL::ComPtr<IXblAuthManager>::As<IClientSecurity>(&v17, &v15);
    v4 = v5;
    if ( v5 >= 0 )
    {
      ppv = -1;
      v5 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64))(*(_QWORD *)v15 + 32LL))(
             v15,
             v17,
             0xFFFFFFFFLL,
             0xFFFFFFFFLL);
      v4 = v5;
      if ( v5 >= 0 )
      {
        v7 = v17;
        v8 = *(__int64 (__fastcall **)(LPVOID, PCNZWCH *, LPVOID *))(*(_QWORD *)v17 + 448LL);
        v9 = pv;
        if ( pv )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)length);
          CoTaskMemFree(v9);
          wil::last_error_context::~last_error_context((wil::last_error_context *)length);
        }
        pv = 0;
        v10 = (WCHAR *)sourceString;
        if ( sourceString )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)length);
          CoTaskMemFree(v10);
          wil::last_error_context::~last_error_context((wil::last_error_context *)length);
        }
        sourceString = 0;
        v5 = v8(v7, &sourceString, &pv);
        v4 = v5;
        if ( v5 >= 0 )
        {
          *(_QWORD *)length = 0;
          v5 = StringCchLengthW(sourceString, 0x7FFFFFFFu, (unsigned __int64 *)length);
          v4 = v5;
          if ( v5 >= 0 )
          {
            v5 = WindowsCreateString(sourceString, length[0], string);
            v4 = v5;
            if ( v5 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
              v4 = 0;
              goto LABEL_19;
            }
            v6 = 1479;
          }
          else
          {
            v6 = 1478;
          }
        }
        else
        {
          v6 = 1475;
        }
      }
      else
      {
        v6 = 1473;
      }
    }
    else
    {
      v6 = 1472;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  }
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
  return v4;
}

```

## disassembly

```asm
0x1800a54ec  push    rbp
0x1800a54ee  push    rbx
0x1800a54ef  push    rsi
0x1800a54f0  push    rdi
0x1800a54f1  push    r14
0x1800a54f3  mov     rbp, rsp
0x1800a54f6  sub     rsp, 60h
0x1800a54fa  mov     rsi, rcx
0x1800a54fd  mov     [rbp+sourceString], 0
0x1800a5505  mov     [rbp+pv], 0
0x1800a550d  mov     qword ptr [rcx], 0
0x1800a5514  mov     [rbp+arg_10], 0
0x1800a551c  lea     rax, [rbp+arg_10]
0x1800a5520  mov     [rsp+60h+ppv], rax; int
0x1800a5525  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x1800a552c  xor     edx, edx; pUnkOuter
0x1800a552e  lea     r8d, [rdx+17h]; dwClsContext
0x1800a5532  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x1800a5539  call    cs:__imp_CoCreateInstance
0x1800a553f  mov     ebx, eax
0x1800a5541  test    eax, eax
0x1800a5543  jns     short loc_1800A5562
0x1800a5545  mov     rcx, [rbp+28h]; this
0x1800a5549  mov     r9d, eax; char *
0x1800a554c  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a5553  mov     edx, 5BCh; void *
0x1800a5558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a555d  jmp     loc_1800A56D4
0x1800a5562  mov     [rbp+arg_0], 0
0x1800a556a  lea     rdx, [rbp+arg_0]
0x1800a556e  lea     rcx, [rbp+arg_10]
0x1800a5572  call    ??$As@UIClientSecurity@@@?$ComPtr@UIXblAuthManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIClientSecurity@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXblAuthManager>::As<IClientSecurity>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClientSecurity>>)
0x1800a5577  mov     ebx, eax
0x1800a5579  test    eax, eax
0x1800a557b  jns     short loc_1800A55A4
0x1800a557d  mov     edx, 5C0h; void *
0x1800a5582  mov     rcx, [rbp+28h]; this
0x1800a5586  mov     r9d, eax; char *
0x1800a5589  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a5590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5595  nop
0x1800a5596  lea     rcx, [rbp+arg_0]
0x1800a559a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a559f  jmp     loc_1800A56D4
0x1800a55a4  mov     rcx, [rbp+arg_0]
0x1800a55a8  mov     rax, [rcx]
0x1800a55ab  mov     [rsp+60h+var_20], 40h ; '@'
0x1800a55b3  mov     [rsp+60h+var_28], 0
0x1800a55bc  mov     [rsp+60h+var_30], 3
0x1800a55c4  mov     [rsp+60h+var_38], 0
0x1800a55cc  mov     [rsp+60h+ppv], 0FFFFFFFFFFFFFFFFh
0x1800a55d5  or      r8d, 0FFFFFFFFh
0x1800a55d9  mov     r9d, r8d
0x1800a55dc  mov     rdx, [rbp+arg_10]
0x1800a55e0  mov     rax, [rax+20h]
0x1800a55e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a55e9  mov     ebx, eax
0x1800a55eb  test    eax, eax
0x1800a55ed  jns     short loc_1800A55F6
0x1800a55ef  mov     edx, 5C1h
0x1800a55f4  jmp     short loc_1800A5582
0x1800a55f6  mov     rdi, [rbp+arg_10]
0x1800a55fa  mov     rax, [rdi]
0x1800a55fd  mov     r14, [rax+1C0h]
0x1800a5604  mov     rbx, [rbp+pv]
0x1800a5608  test    rbx, rbx
0x1800a560b  jz      short loc_1800A5628
0x1800a560d  lea     rcx, [rbp+length]; this
0x1800a5611  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a5616  mov     rcx, rbx; pv
0x1800a5619  call    cs:__imp_CoTaskMemFree
0x1800a561f  lea     rcx, [rbp+length]; this
0x1800a5623  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a5628  mov     [rbp+pv], 0
0x1800a5630  mov     rbx, [rbp+sourceString]
0x1800a5634  test    rbx, rbx
0x1800a5637  jz      short loc_1800A5654
0x1800a5639  lea     rcx, [rbp+length]; this
0x1800a563d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a5642  mov     rcx, rbx; pv
0x1800a5645  call    cs:__imp_CoTaskMemFree
0x1800a564b  lea     rcx, [rbp+length]; this
0x1800a564f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a5654  mov     [rbp+sourceString], 0
0x1800a565c  lea     r8, [rbp+pv]
0x1800a5660  lea     rdx, [rbp+sourceString]
0x1800a5664  mov     rcx, rdi
0x1800a5667  mov     rax, r14
0x1800a566a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a566f  mov     ebx, eax
0x1800a5671  test    eax, eax
0x1800a5673  jns     short loc_1800A567F
0x1800a5675  mov     edx, 5C3h
0x1800a567a  jmp     loc_1800A5582
0x1800a567f  mov     qword ptr [rbp+length], 0
0x1800a5687  lea     r8, [rbp+length]; unsigned __int64 *
0x1800a568b  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800a5690  mov     rcx, [rbp+sourceString]; unsigned __int16 *
0x1800a5694  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a5699  mov     ebx, eax
0x1800a569b  test    eax, eax
0x1800a569d  jns     short loc_1800A56A9
0x1800a569f  mov     edx, 5C6h
0x1800a56a4  jmp     loc_1800A5582
0x1800a56a9  mov     r8, rsi; string
0x1800a56ac  mov     edx, [rbp+length]; length
0x1800a56af  mov     rcx, [rbp+sourceString]; sourceString
0x1800a56b3  call    cs:__imp_WindowsCreateString
0x1800a56b9  mov     ebx, eax
0x1800a56bb  test    eax, eax
0x1800a56bd  jns     short loc_1800A56C9
0x1800a56bf  mov     edx, 5C7h
0x1800a56c4  jmp     loc_1800A5582
0x1800a56c9  lea     rcx, [rbp+arg_0]
0x1800a56cd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a56d2  xor     ebx, ebx
0x1800a56d4  lea     rcx, [rbp+arg_10]
0x1800a56d8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a56dd  nop
0x1800a56de  lea     rcx, [rbp+pv]
0x1800a56e2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a56e7  nop
0x1800a56e8  lea     rcx, [rbp+sourceString]
0x1800a56ec  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a56f1  mov     eax, ebx
0x1800a56f3  add     rsp, 60h
0x1800a56f7  pop     r14
0x1800a56f9  pop     rdi
0x1800a56fa  pop     rsi
0x1800a56fb  pop     rbx
0x1800a56fc  pop     rbp
0x1800a56fd  retn
```
