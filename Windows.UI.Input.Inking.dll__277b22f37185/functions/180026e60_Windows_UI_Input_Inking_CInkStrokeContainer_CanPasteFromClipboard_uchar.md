# Windows::UI::Input::Inking::CInkStrokeContainer::CanPasteFromClipboard(uchar *)

- ea: `0x180026e60`
- end: `0x180026fe9`
- name: `?CanPasteFromClipboard@CInkStrokeContainer@Inking@Input@UI@Windows@@UEAAJPEAE@Z`
- size: `393`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkStrokeContainer *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001332c`
- `0x18001f73c`
- `0x18001f9a4`
- `0x180020774`
- `0x180026e60`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026f7d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026f7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f91`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkStrokeContainer::CanPasteFromClipboard(
        Windows::UI::Input::Inking::CInkStrokeContainer *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rax
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdi
  unsigned __int64 v11; // rcx
  __int64 (__fastcall *v12)(__int64, HSTRING, const unsigned __int16 *); // r14
  __int64 v14; // [rsp+20h] [rbp-48h] BYREF
  UINT32 length; // [rsp+28h] [rbp-40h] BYREF
  __int64 v16; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  if ( a2 )
  {
    *(_BYTE *)a2 = 0;
    v16 = 0;
    v4 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[48])a2);
    v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>(
           *v4,
           &v16);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v6 = v16;
      v14 = 0;
      v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      v8 = v7(v6, &v14);
      v3 = v8;
      if ( v8 >= 0 )
      {
        v10 = v14;
        v11 = -1;
        length = 0;
        v12 = *(__int64 (__fastcall **)(__int64, HSTRING, const unsigned __int16 *))(*(_QWORD *)v14 + 80LL);
        do
          ++v11;
        while ( aInkSerializedF[v11] );
        if ( (int)ULongLongToUInt(v11, &length) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        WindowsCreateStringReference(L"Ink Serialized Format", length, &hstringHeader, &string);
        v8 = v12(v10, string, a2);
        v3 = v8;
        if ( v8 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
          v3 = 0;
          goto LABEL_15;
        }
        v9 = 2590;
      }
      else
      {
        v9 = 2587;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v8,
        v14);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA19,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
        (const char *)(unsigned int)v5,
        v14);
    }
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    return v3;
  }
  v3 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA13,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
    (const char *)0x80004003LL,
    v14);
  return v3;
}

```

## disassembly

```asm
0x180026e60  push    rbp
0x180026e62  push    rbx
0x180026e63  push    rsi
0x180026e64  push    rdi
0x180026e65  push    r14
0x180026e67  push    r15
0x180026e69  mov     rbp, rsp
0x180026e6c  sub     rsp, 68h
0x180026e70  mov     rax, cs:__security_cookie
0x180026e77  xor     rax, rsp
0x180026e7a  mov     [rbp+var_10], rax
0x180026e7e  xor     r15d, r15d
0x180026e81  mov     rsi, rdx
0x180026e84  test    rdx, rdx
0x180026e87  jnz     short loc_180026EAB
0x180026e89  mov     rcx, [rbp+30h]; this
0x180026e8d  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180026e94  mov     ebx, 80004003h
0x180026e99  mov     edx, 0A13h; void *
0x180026e9e  mov     r9d, ebx; char *
0x180026ea1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ea6  jmp     loc_180026FCE
0x180026eab  lea     rcx, [rbp+string]; string
0x180026eaf  mov     [rdx], r15b
0x180026eb2  mov     [rbp+var_38], r15
0x180026eb6  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x180026ebb  lea     rdx, [rbp+var_38]
0x180026ebf  mov     rcx, [rax]
0x180026ec2  call    ??$GetActivationFactory@V?$ComPtr@UIClipboardStatics@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIClipboardStatics@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::DataTransfer::IClipboardStatics>>)
0x180026ec7  mov     ebx, eax
0x180026ec9  test    eax, eax
0x180026ecb  jns     short loc_180026EEA
0x180026ecd  mov     rcx, [rbp+30h]; this
0x180026ed1  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180026ed8  mov     r9d, eax; char *
0x180026edb  mov     edx, 0A19h; void *
0x180026ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ee5  jmp     loc_180026FC5
0x180026eea  mov     rdi, [rbp+var_38]
0x180026eee  lea     rcx, [rbp+var_48]
0x180026ef2  mov     [rbp+var_48], r15
0x180026ef6  mov     rax, [rdi]
0x180026ef9  mov     rbx, [rax+30h]
0x180026efd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026f02  lea     rdx, [rbp+var_48]
0x180026f06  mov     rcx, rdi
0x180026f09  mov     rax, rbx
0x180026f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f11  mov     ebx, eax
0x180026f13  test    eax, eax
0x180026f15  jns     short loc_180026F3D
0x180026f17  mov     edx, 0A1Bh; void *
0x180026f1c  mov     rcx, [rbp+30h]; this
0x180026f20  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180026f27  mov     r9d, eax; char *
0x180026f2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f2f  lea     rcx, [rbp+var_48]
0x180026f33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026f38  jmp     loc_180026FC5
0x180026f3d  mov     rdi, [rbp+var_48]
0x180026f41  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026f45  mov     rbx, cs:sourceString
0x180026f4c  mov     [rbp+length], r15d
0x180026f50  mov     rax, [rdi]
0x180026f53  mov     r14, [rax+50h]
0x180026f57  inc     rcx; unsigned __int64
0x180026f5a  cmp     [rbx+rcx*2], r15w
0x180026f5f  jnz     short loc_180026F57
0x180026f61  lea     rdx, [rbp+length]; unsigned int *
0x180026f65  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180026f6a  test    eax, eax
0x180026f6c  jns     short loc_180026F83
0x180026f6e  xor     r9d, r9d; lpArguments
0x180026f71  xor     r8d, r8d; nNumberOfArguments
0x180026f74  mov     ecx, 0C000000Dh; dwExceptionCode
0x180026f79  lea     edx, [r9+1]; dwExceptionFlags
0x180026f7d  call    cs:__imp_RaiseException
0x180026f83  mov     edx, [rbp+length]; length
0x180026f86  lea     r9, [rbp+string]; string
0x180026f8a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180026f8e  mov     rcx, rbx; sourceString
0x180026f91  call    cs:__imp_WindowsCreateStringReference
0x180026f97  mov     rdx, [rbp+string]
0x180026f9b  mov     r8, rsi
0x180026f9e  mov     rcx, rdi
0x180026fa1  mov     rax, r14
0x180026fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fa9  mov     ebx, eax
0x180026fab  test    eax, eax
0x180026fad  jns     short loc_180026FB9
0x180026faf  mov     edx, 0A1Eh
0x180026fb4  jmp     loc_180026F1C
0x180026fb9  lea     rcx, [rbp+var_48]
0x180026fbd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026fc2  mov     ebx, r15d
0x180026fc5  lea     rcx, [rbp+var_38]
0x180026fc9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026fce  mov     eax, ebx
0x180026fd0  mov     rcx, [rbp+var_10]
0x180026fd4  xor     rcx, rsp; StackCookie
0x180026fd7  call    __security_check_cookie
0x180026fdc  add     rsp, 68h
0x180026fe0  pop     r15
0x180026fe2  pop     r14
0x180026fe4  pop     rdi
0x180026fe5  pop     rsi
0x180026fe6  pop     rbx
0x180026fe7  pop     rbp
0x180026fe8  retn
```
