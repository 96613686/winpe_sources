# WinStoreAuth::AuthenticationInternal::GetAllXTokens(HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800a5984`
- end: `0x1800a5bc1`
- name: `?GetAllXTokens@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@0@Z`
- size: `573`
- prototype: `__int64 __fastcall(HSTRING *string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bf58`

## callees

- `0x180004738`
- `0x18000aba8`
- `0x18002aae8`
- `0x180044dcc`
- `0x180061c04`
- `0x18006ea74`
- `0x1800a5984`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a5b27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a5b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a5b27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a5b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5a72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5a72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a59c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a59c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5ba2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a5a1e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a5a1e`

## string_xrefs

- `0x1800a5a94`: `x-xbl-contract-version:2\nAccept:application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetAllXTokens(HSTRING *string, HSTRING *a2, HSTRING *a3)
{
  int SlsValue; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, const WCHAR *, _QWORD, const unsigned __int16 *); // rbx
  HRESULT v11; // eax
  __int64 v12; // rdx
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  int ppvb; // [rsp+20h] [rbp-60h]
  LPVOID v16; // [rsp+60h] [rbp-20h] BYREF
  HSTRING stringa; // [rsp+68h] [rbp-18h] BYREF
  UINT32 length[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  PCNZWCH v20; // [rsp+C0h] [rbp+40h] BYREF
  PCNZWCH sourceString; // [rsp+C8h] [rbp+48h] BYREF

  if ( !WinStoreAuth::AuthenticationInternal::IsPlatformXbox((WinStoreAuth::AuthenticationInternal *)string) )
    return 2147500033LL;
  *string = 0;
  *a2 = 0;
  WindowsDeleteString(0);
  stringa = 0;
  SlsValue = WinStoreAuth::GetSlsValue(6, &stringa);
  v7 = SlsValue;
  if ( SlsValue >= 0 )
  {
    v16 = 0;
    v8 = CoCreateInstance(
           &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
           0,
           0x17u,
           &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
           &v16);
    v7 = v8;
    if ( v8 >= 0 )
    {
      sourceString = 0;
      v20 = 0;
      v9 = v16;
      v10 = *(__int64 (__fastcall **)(LPVOID, const WCHAR *, _QWORD, const unsigned __int16 *))(*(_QWORD *)v16 + 104LL);
      v20 = 0;
      sourceString = 0;
      ppvb = (unsigned int)WindowsGetStringRawBuffer(stringa, 0);
      v11 = v10(v9, L"*", 0, L"GET");
      v7 = v11;
      if ( v11 >= 0 )
      {
        *(_QWORD *)length = 0;
        v11 = StringCchLengthW(sourceString, 0x7FFFFFFFu, (unsigned __int64 *)length);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v11 = WindowsCreateString(sourceString, length[0], string);
          v7 = v11;
          if ( v11 >= 0 )
          {
            *(_QWORD *)length = 0;
            v11 = StringCchLengthW(v20, 0x7FFFFFFFu, (unsigned __int64 *)length);
            v7 = v11;
            if ( v11 >= 0 )
            {
              v11 = WindowsCreateString(v20, length[0], a2);
              v7 = v11;
              if ( v11 >= 0 )
              {
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v20);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
                v7 = 0;
                goto LABEL_20;
              }
              v12 = 1169;
            }
            else
            {
              v12 = 1168;
            }
          }
          else
          {
            v12 = 1165;
          }
        }
        else
        {
          v12 = 1164;
        }
      }
      else
      {
        v12 = 1161;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v11,
        ppvb);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v20);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v8,
        ppva);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x479,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)SlsValue,
      ppv);
  }
LABEL_20:
  WindowsDeleteString(stringa);
  return v7;
}

```

## disassembly

```asm
0x1800a5984  mov     [rsp-28h+arg_0], rbx
0x1800a5989  push    rbp
0x1800a598a  push    rsi
0x1800a598b  push    rdi
0x1800a598c  push    r14
0x1800a598e  push    r15
0x1800a5990  mov     rbp, rsp
0x1800a5993  sub     rsp, 80h
0x1800a599a  mov     r14, rdx
0x1800a599d  mov     rsi, rcx
0x1800a59a0  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x1800a59a5  xor     r15d, r15d
0x1800a59a8  test    al, al
0x1800a59aa  jnz     short loc_1800A59B6
0x1800a59ac  mov     eax, 80004001h
0x1800a59b1  jmp     loc_1800A5BAA
0x1800a59b6  mov     [rsi], r15
0x1800a59b9  mov     [r14], r15
0x1800a59bc  mov     [rbp+string], r15
0x1800a59c0  xor     ecx, ecx; string
0x1800a59c2  call    cs:__imp_WindowsDeleteString
0x1800a59c8  mov     [rbp+string], r15
0x1800a59cc  lea     rdx, [rbp+string]
0x1800a59d0  mov     ecx, 6
0x1800a59d5  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x1800a59da  mov     ebx, eax
0x1800a59dc  test    eax, eax
0x1800a59de  jns     short loc_1800A59FD
0x1800a59e0  mov     rcx, [rbp+28h]; this
0x1800a59e4  mov     r9d, eax; char *
0x1800a59e7  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a59ee  mov     edx, 479h; void *
0x1800a59f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a59f8  jmp     loc_1800A5B9E
0x1800a59fd  mov     [rbp+var_20], r15
0x1800a5a01  lea     rax, [rbp+var_20]
0x1800a5a05  mov     [rsp+80h+ppv], rax; int
0x1800a5a0a  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x1800a5a11  xor     edx, edx; pUnkOuter
0x1800a5a13  lea     r8d, [rdx+17h]; dwClsContext
0x1800a5a17  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x1800a5a1e  call    cs:__imp_CoCreateInstance
0x1800a5a24  mov     ebx, eax
0x1800a5a26  test    eax, eax
0x1800a5a28  jns     short loc_1800A5A51
0x1800a5a2a  mov     rcx, [rbp+28h]; this
0x1800a5a2e  mov     r9d, eax; char *
0x1800a5a31  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a5a38  mov     edx, 47Ch; void *
0x1800a5a3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5a42  nop
0x1800a5a43  lea     rcx, [rbp+var_20]
0x1800a5a47  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a5a4c  jmp     loc_1800A5B9E
0x1800a5a51  mov     [rbp+sourceString], r15
0x1800a5a55  mov     [rbp+arg_10], r15
0x1800a5a59  mov     rdi, [rbp+var_20]
0x1800a5a5d  mov     rax, [rdi]
0x1800a5a60  mov     rbx, [rax+68h]
0x1800a5a64  mov     [rbp+arg_10], r15
0x1800a5a68  mov     [rbp+sourceString], r15
0x1800a5a6c  xor     edx, edx; length
0x1800a5a6e  mov     rcx, [rbp+string]; string
0x1800a5a72  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a5a78  lea     rcx, [rbp+arg_10]
0x1800a5a7c  mov     [rsp+80h+var_38], rcx
0x1800a5a81  lea     rcx, [rbp+sourceString]
0x1800a5a85  mov     [rsp+80h+var_40], rcx
0x1800a5a8a  mov     [rsp+80h+var_48], r15d
0x1800a5a8f  mov     [rsp+80h+var_50], r15
0x1800a5a94  lea     rcx, aXXblContractVe; "x-xbl-contract-version:2\r\nAccept:appl"...
0x1800a5a9b  mov     [rsp+80h+var_58], rcx
0x1800a5aa0  mov     [rsp+80h+ppv], rax; int
0x1800a5aa5  lea     r9, aGet; "GET"
0x1800a5aac  xor     r8d, r8d
0x1800a5aaf  lea     rdx, asc_1800D00D4; "*"
0x1800a5ab6  mov     rcx, rdi
0x1800a5ab9  mov     rax, rbx
0x1800a5abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5ac1  mov     ebx, eax
0x1800a5ac3  test    eax, eax
0x1800a5ac5  jns     short loc_1800A5AF8
0x1800a5ac7  mov     edx, 489h; void *
0x1800a5acc  mov     rcx, [rbp+28h]; this
0x1800a5ad0  mov     r9d, eax; char *
0x1800a5ad3  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a5ada  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5adf  nop
0x1800a5ae0  lea     rcx, [rbp+arg_10]
0x1800a5ae4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a5ae9  nop
0x1800a5aea  lea     rcx, [rbp+sourceString]
0x1800a5aee  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a5af3  jmp     loc_1800A5A43
0x1800a5af8  mov     qword ptr [rbp+length], r15
0x1800a5afc  lea     r8, [rbp+length]; unsigned __int64 *
0x1800a5b00  mov     edi, 7FFFFFFFh
0x1800a5b05  mov     edx, edi; unsigned __int64
0x1800a5b07  mov     rcx, [rbp+sourceString]; unsigned __int16 *
0x1800a5b0b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a5b10  mov     ebx, eax
0x1800a5b12  test    eax, eax
0x1800a5b14  jns     short loc_1800A5B1D
0x1800a5b16  mov     edx, 48Ch
0x1800a5b1b  jmp     short loc_1800A5ACC
0x1800a5b1d  mov     r8, rsi; string
0x1800a5b20  mov     edx, [rbp+length]; length
0x1800a5b23  mov     rcx, [rbp+sourceString]; sourceString
0x1800a5b27  call    cs:__imp_WindowsCreateString
0x1800a5b2d  mov     ebx, eax
0x1800a5b2f  test    eax, eax
0x1800a5b31  jns     short loc_1800A5B3A
0x1800a5b33  mov     edx, 48Dh
0x1800a5b38  jmp     short loc_1800A5ACC
0x1800a5b3a  mov     qword ptr [rbp+length], r15
0x1800a5b3e  lea     r8, [rbp+length]; unsigned __int64 *
0x1800a5b42  mov     rdx, rdi; unsigned __int64
0x1800a5b45  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x1800a5b49  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a5b4e  mov     ebx, eax
0x1800a5b50  test    eax, eax
0x1800a5b52  jns     short loc_1800A5B5E
0x1800a5b54  mov     edx, 490h
0x1800a5b59  jmp     loc_1800A5ACC
0x1800a5b5e  mov     r8, r14; string
0x1800a5b61  mov     edx, [rbp+length]; length
0x1800a5b64  mov     rcx, [rbp+arg_10]; sourceString
0x1800a5b68  call    cs:__imp_WindowsCreateString
0x1800a5b6e  mov     ebx, eax
0x1800a5b70  test    eax, eax
0x1800a5b72  jns     short loc_1800A5B7E
0x1800a5b74  mov     edx, 491h
0x1800a5b79  jmp     loc_1800A5ACC
0x1800a5b7e  lea     rcx, [rbp+arg_10]
0x1800a5b82  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a5b87  nop
0x1800a5b88  lea     rcx, [rbp+sourceString]
0x1800a5b8c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a5b91  nop
0x1800a5b92  lea     rcx, [rbp+var_20]
0x1800a5b96  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a5b9b  mov     ebx, r15d
0x1800a5b9e  mov     rcx, [rbp+string]; string
0x1800a5ba2  call    cs:__imp_WindowsDeleteString
0x1800a5ba8  mov     eax, ebx
0x1800a5baa  mov     rbx, [rsp+80h+arg_0]
0x1800a5bb2  add     rsp, 80h
0x1800a5bb9  pop     r15
0x1800a5bbb  pop     r14
0x1800a5bbd  pop     rdi
0x1800a5bbe  pop     rsi
0x1800a5bbf  pop     rbp
0x1800a5bc0  retn
```
