# CCredentialCommandFactory::_IsIECredential(Windows::Security::Credentials::IPasswordCredential *,int *)

- ea: `0x180031d14`
- end: `0x180031e76`
- name: `?_IsIECredential@CCredentialCommandFactory@@CAJPEAUIPasswordCredential@Credentials@Security@Windows@@PEAH@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IPasswordCredential *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031620`
- `0x1800316f0`

## callees

- `0x180008218`
- `0x1800082b8`
- `0x180011ffc`
- `0x180031d14`
- `0x1800696e6`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031dae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031dae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031d95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031d95`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CCredentialCommandFactory::_IsIECredential(
        struct Windows::Security::Credentials::IPasswordCredential *a1,
        int *a2)
{
  int v3; // ebx
  __int64 v5; // [rsp+20h] [rbp-60h] BYREF
  __int64 v6; // [rsp+28h] [rbp-58h] BYREF
  __int64 v7; // [rsp+30h] [rbp-50h] BYREF
  __int64 v8; // [rsp+38h] [rbp-48h] BYREF
  __int128 Buf2; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = 0;
  v8 = 0;
  if ( (*(int (__fastcall **)(struct Windows::Security::Credentials::IPasswordCredential *, __int64 *))(*(_QWORD *)a1 + 104LL))(
         a1,
         &v8) >= 0 )
  {
    v7 = 0;
    v3 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v8,
           &v7);
    if ( v3 >= 0 )
    {
      v6 = 0;
      if ( WindowsCreateStringReference(L"applicationid", 0xDu, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      if ( (*(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v7 + 48LL))(v7, string, &v6) >= 0 )
      {
        v5 = 0;
        v3 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v6, &v5);
        if ( v3 >= 0 )
        {
          Buf2 = 0;
          if ( (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v5 + 160LL))(v5, &Buf2) >= 0 )
            *a2 = memcmp_0(IE_APP_ID, &Buf2, 0x10u) == 0;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v5);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v6);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180031d14  mov     [rsp-8+arg_10], rbx
0x180031d19  mov     [rsp-8+arg_18], rdi
0x180031d1e  push    rbp
0x180031d1f  mov     rbp, rsp
0x180031d22  sub     rsp, 80h
0x180031d29  mov     rax, cs:__security_cookie
0x180031d30  xor     rax, rsp
0x180031d33  mov     [rbp+var_10], rax
0x180031d37  mov     rdi, rdx
0x180031d3a  mov     dword ptr [rdx], 0
0x180031d40  xor     ebx, ebx
0x180031d42  mov     [rbp+var_48], rbx
0x180031d46  mov     rax, [rcx]
0x180031d49  lea     rdx, [rbp+var_48]
0x180031d4d  mov     rax, [rax+68h]
0x180031d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d56  test    eax, eax
0x180031d58  js      loc_180031E4A
0x180031d5e  mov     [rbp+var_50], rbx
0x180031d62  lea     rdx, [rbp+var_50]
0x180031d66  lea     rcx, [rbp+var_48]
0x180031d6a  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180031d6f  mov     ebx, eax
0x180031d71  test    eax, eax
0x180031d73  js      loc_180031E40
0x180031d79  mov     [rbp+var_58], 0
0x180031d81  lea     r9, [rbp+string]; string
0x180031d85  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180031d89  mov     edx, 0Dh; length
0x180031d8e  lea     rcx, aApplicationid; "applicationid"
0x180031d95  call    cs:__imp_WindowsCreateStringReference
0x180031d9b  test    eax, eax
0x180031d9d  jns     short loc_180031DB4
0x180031d9f  xor     r9d, r9d; lpArguments
0x180031da2  xor     r8d, r8d; nNumberOfArguments
0x180031da5  lea     edx, [r9+1]; dwExceptionFlags
0x180031da9  mov     ecx, 0C000000Dh; dwExceptionCode
0x180031dae  call    cs:__imp_RaiseException
0x180031db4  mov     rcx, [rbp+var_50]
0x180031db8  mov     rax, [rcx]
0x180031dbb  lea     r8, [rbp+var_58]
0x180031dbf  mov     rdx, [rbp+string]
0x180031dc3  mov     rax, [rax+30h]
0x180031dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031dcc  test    eax, eax
0x180031dce  js      short loc_180031E36
0x180031dd0  mov     [rbp+var_60], 0
0x180031dd8  lea     rdx, [rbp+var_60]
0x180031ddc  lea     rcx, [rbp+var_58]
0x180031de0  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x180031de5  mov     ebx, eax
0x180031de7  test    eax, eax
0x180031de9  js      short loc_180031E2C
0x180031deb  xorps   xmm0, xmm0
0x180031dee  movups  [rbp+Buf2], xmm0
0x180031df2  mov     rcx, [rbp+var_60]
0x180031df6  mov     rax, [rcx]
0x180031df9  lea     rdx, [rbp+Buf2]
0x180031dfd  mov     rax, [rax+0A0h]
0x180031e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e09  test    eax, eax
0x180031e0b  js      short loc_180031E2C
0x180031e0d  mov     r8d, 10h; Size
0x180031e13  lea     rdx, [rbp+Buf2]; Buf2
0x180031e17  lea     rcx, IE_APP_ID; Buf1
0x180031e1e  call    memcmp_0
0x180031e23  xor     ecx, ecx
0x180031e25  test    eax, eax
0x180031e27  setz    cl
0x180031e2a  mov     [rdi], ecx
0x180031e2c  lea     rcx, [rbp+var_60]
0x180031e30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180031e35  nop
0x180031e36  lea     rcx, [rbp+var_58]
0x180031e3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180031e3f  nop
0x180031e40  lea     rcx, [rbp+var_50]
0x180031e44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180031e49  nop
0x180031e4a  lea     rcx, [rbp+var_48]
0x180031e4e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180031e53  mov     eax, ebx
0x180031e55  mov     rcx, [rbp+var_10]
0x180031e59  xor     rcx, rsp; StackCookie
0x180031e5c  call    __security_check_cookie
0x180031e61  lea     r11, [rsp+80h+var_s0]
0x180031e69  mov     rbx, [r11+20h]
0x180031e6d  mov     rdi, [r11+28h]
0x180031e71  mov     rsp, r11
0x180031e74  pop     rbp
0x180031e75  retn
```
