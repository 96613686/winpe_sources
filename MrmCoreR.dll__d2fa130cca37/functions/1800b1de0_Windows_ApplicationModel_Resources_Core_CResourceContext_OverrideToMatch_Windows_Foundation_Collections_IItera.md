# Windows::ApplicationModel::Resources::Core::CResourceContext::OverrideToMatch(Windows::Foundation::Collections::IIterable<Windows::ApplicationModel::Resources::Core::ResourceQualifier *> *)

- ea: `0x1800b1de0`
- end: `0x1800b20a5`
- name: `?OverrideToMatch@CResourceContext@Core@Resources@ApplicationModel@Windows@@UEAAJPEAU?$IIterable@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@5@@Z`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000892c`
- `0x18002c8d0`
- `0x180045d4c`
- `0x18006997c`
- `0x180074ef0`
- `0x1800862f0`
- `0x1800b1de0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800b1e37`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800b1e37`

## string_xrefs

- `0x1800b1e41`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b1eb5`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b2017`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b2035`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800b2058`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceContext::OverrideToMatch(
        __int64 a1,
        __int64 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64 *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  char v9; // al
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  int Lpcwstr; // eax
  unsigned __int16 *v15; // rdi
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-40h] BYREF
  __int64 v19; // [rsp+28h] [rbp-38h] BYREF
  HSTRING v20; // [rsp+30h] [rbp-30h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-28h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-18h] BYREF
  int v24; // [rsp+50h] [rbp-10h]
  wchar_t v25; // [rsp+54h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( a2 )
  {
    v5 = *a2;
    v22 = 0;
    v6 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v5 + 48);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v22);
    v7 = v6(a2, &v22);
    v4 = v7;
    if ( v7 >= 0 )
    {
      LOBYTE(v18) = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 56LL))(v22, &v18);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v9 = v18;
        if ( (_BYTE)v18 )
        {
          v19 = 0;
          while ( v9 )
          {
            v10 = v22;
            v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v19);
            v12 = v11(v10, &v19);
            v4 = v12;
            if ( v12 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x101,
                (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                (const char *)(unsigned int)v12,
                v18);
              goto LABEL_30;
            }
            v20 = 0;
            v13 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 48LL))(v19, &v20);
            v4 = v13;
            if ( v13 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x104,
                (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                (const char *)(unsigned int)v13,
                v18);
              goto LABEL_28;
            }
            v21 = 0;
            Lpcwstr = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 56LL))(v19, &v21);
            v4 = Lpcwstr;
            if ( Lpcwstr < 0 )
            {
              v16 = 263;
LABEL_26:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v16,
                (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
                (const char *)(unsigned int)Lpcwstr,
                v18);
              Windows::Internal::String::~String(&v21);
LABEL_28:
              Windows::Internal::String::~String(&v20);
LABEL_30:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v19);
              goto LABEL_33;
            }
            v23 = 0;
            Lpcwstr = Windows::Internal::String::GetLpcwstr(
                        (Windows::Internal::String *)&v20,
                        (const unsigned __int16 **)&v23);
            v4 = Lpcwstr;
            if ( Lpcwstr < 0 )
            {
              v16 = 266;
              goto LABEL_26;
            }
            v15 = v23;
            if ( v23 )
            {
              v23 = 0;
              Lpcwstr = Windows::Internal::String::GetLpcwstr(
                          (Windows::Internal::String *)&v21,
                          (const unsigned __int16 **)&v23);
              v4 = Lpcwstr;
              if ( Lpcwstr < 0 )
              {
                v16 = 271;
                goto LABEL_26;
              }
              if ( v23 )
              {
                Lpcwstr = Windows::ApplicationModel::Resources::Core::CQualifierEvent::UpdateQualifierIfChanged(
                            *(_QWORD *)(a1 + 88),
                            v15,
                            v23,
                            0);
                v4 = Lpcwstr;
                if ( Lpcwstr < 0 )
                {
                  v16 = 277;
                  goto LABEL_26;
                }
              }
            }
            Lpcwstr = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 64LL))(v22, &v18);
            v4 = Lpcwstr;
            if ( Lpcwstr < 0 )
            {
              v16 = 281;
              goto LABEL_26;
            }
            Windows::Internal::String::~String(&v21);
            Windows::Internal::String::~String(&v20);
            v9 = v18;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v19);
        }
        v4 = 0;
        goto LABEL_33;
      }
      v8 = 251;
    }
    else
    {
      v8 = 248;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)v7,
      v18);
LABEL_33:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v22);
    return v4;
  }
  v24 = *(_DWORD *)L"lt";
  v4 = -2147024809;
  v25 = aResult[6];
  v23 = *(unsigned __int16 **)L"result";
  RoOriginateErrorW(2147942487LL, 6, &v23);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF4,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
    (const char *)0x80070057LL,
    v18);
  return v4;
}

```

## disassembly

```asm
0x1800b1de0  mov     [rsp-18h+arg_10], rbx
0x1800b1de5  push    rbp
0x1800b1de6  push    rsi
0x1800b1de7  push    rdi
0x1800b1de8  mov     rbp, rsp
0x1800b1deb  sub     rsp, 60h
0x1800b1def  mov     rax, cs:__security_cookie
0x1800b1df6  xor     rax, rsp
0x1800b1df9  mov     [rbp+var_8], rax
0x1800b1dfd  mov     rdi, rdx
0x1800b1e00  mov     rsi, rcx
0x1800b1e03  test    rdx, rdx
0x1800b1e06  jnz     short loc_1800B1E5A
0x1800b1e08  mov     eax, dword ptr cs:aResult+8; "lt"
0x1800b1e0e  lea     r8, [rbp+var_18]
0x1800b1e12  movsd   xmm0, qword ptr cs:aResult; "result"
0x1800b1e1a  lea     edx, [rdi+6]
0x1800b1e1d  mov     [rbp+var_10], eax
0x1800b1e20  mov     ebx, 80070057h
0x1800b1e25  movzx   eax, word ptr cs:aResult+0Ch; ""
0x1800b1e2c  mov     ecx, ebx
0x1800b1e2e  mov     [rbp+var_C], ax
0x1800b1e32  movsd   [rbp+var_18], xmm0
0x1800b1e37  call    cs:__imp_RoOriginateErrorW
0x1800b1e3d  mov     rcx, [rbp+18h]; this
0x1800b1e41  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800b1e48  mov     r9d, ebx; char *
0x1800b1e4b  mov     edx, 0F4h; void *
0x1800b1e50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1e55  jmp     loc_1800B2087
0x1800b1e5a  mov     rax, [rdx]
0x1800b1e5d  lea     rcx, [rbp+var_20]
0x1800b1e61  mov     [rbp+var_20], 0
0x1800b1e69  mov     rbx, [rax+30h]
0x1800b1e6d  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b1e72  lea     rdx, [rbp+var_20]
0x1800b1e76  mov     rcx, rdi
0x1800b1e79  mov     rax, rbx
0x1800b1e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1e81  mov     ebx, eax
0x1800b1e83  test    eax, eax
0x1800b1e85  jns     short loc_1800B1E8E
0x1800b1e87  mov     edx, 0F8h
0x1800b1e8c  jmp     short loc_1800B1EB1
0x1800b1e8e  mov     rcx, [rbp+var_20]
0x1800b1e92  lea     rdx, [rbp+var_40]
0x1800b1e96  mov     byte ptr [rbp+var_40], 0
0x1800b1e9a  mov     rax, [rcx]
0x1800b1e9d  mov     rax, [rax+38h]
0x1800b1ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ea6  mov     ebx, eax
0x1800b1ea8  test    eax, eax
0x1800b1eaa  jns     short loc_1800B1EC9
0x1800b1eac  mov     edx, 0FBh; void *
0x1800b1eb1  mov     rcx, [rbp+18h]; this
0x1800b1eb5  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800b1ebc  mov     r9d, eax; char *
0x1800b1ebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1ec4  jmp     loc_1800B207E
0x1800b1ec9  mov     al, byte ptr [rbp+var_40]
0x1800b1ecc  test    al, al
0x1800b1ece  jz      loc_1800B207C
0x1800b1ed4  mov     [rbp+var_38], 0
0x1800b1edc  lea     rcx, [rbp+var_38]
0x1800b1ee0  test    al, al
0x1800b1ee2  jz      loc_1800B2077
0x1800b1ee8  mov     rdi, [rbp+var_20]
0x1800b1eec  mov     rax, [rdi]
0x1800b1eef  mov     rbx, [rax+30h]
0x1800b1ef3  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b1ef8  lea     rdx, [rbp+var_38]
0x1800b1efc  mov     rcx, rdi
0x1800b1eff  mov     rax, rbx
0x1800b1f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f07  mov     ebx, eax
0x1800b1f09  test    eax, eax
0x1800b1f0b  js      loc_1800B2054
0x1800b1f11  mov     rcx, [rbp+var_38]
0x1800b1f15  lea     rdx, [rbp+var_30]
0x1800b1f19  mov     [rbp+var_30], 0
0x1800b1f21  mov     rax, [rcx]
0x1800b1f24  mov     rax, [rax+30h]
0x1800b1f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f2d  mov     ebx, eax
0x1800b1f2f  test    eax, eax
0x1800b1f31  js      loc_1800B2031
0x1800b1f37  mov     rcx, [rbp+var_38]
0x1800b1f3b  lea     rdx, [rbp+var_28]
0x1800b1f3f  mov     [rbp+var_28], 0
0x1800b1f47  mov     rax, [rcx]
0x1800b1f4a  mov     rax, [rax+38h]
0x1800b1f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f53  mov     ebx, eax
0x1800b1f55  test    eax, eax
0x1800b1f57  js      loc_1800B200E
0x1800b1f5d  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x1800b1f61  mov     [rbp+var_18], 0
0x1800b1f69  lea     rcx, [rbp+var_30]; this
0x1800b1f6d  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x1800b1f72  mov     ebx, eax
0x1800b1f74  test    eax, eax
0x1800b1f76  js      loc_1800B2007
0x1800b1f7c  mov     rdi, [rbp+var_18]
0x1800b1f80  test    rdi, rdi
0x1800b1f83  jz      short loc_1800B1FBE
0x1800b1f85  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x1800b1f89  mov     [rbp+var_18], 0
0x1800b1f91  lea     rcx, [rbp+var_28]; this
0x1800b1f95  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x1800b1f9a  mov     ebx, eax
0x1800b1f9c  test    eax, eax
0x1800b1f9e  js      short loc_1800B1FF9
0x1800b1fa0  mov     r8, [rbp+var_18]
0x1800b1fa4  test    r8, r8
0x1800b1fa7  jz      short loc_1800B1FBE
0x1800b1fa9  mov     rcx, [rsi+58h]
0x1800b1fad  xor     r9d, r9d
0x1800b1fb0  mov     rdx, rdi
0x1800b1fb3  call    ?UpdateQualifierIfChanged@CQualifierEvent@Core@Resources@ApplicationModel@Windows@@QEAAJPEBG0W4_SetQualifierFlags@Runtime@3Microsoft@@@Z; Windows::ApplicationModel::Resources::Core::CQualifierEvent::UpdateQualifierIfChanged(ushort const *,ushort const *,Microsoft::Resources::Runtime::_SetQualifierFlags)
0x1800b1fb8  mov     ebx, eax
0x1800b1fba  test    eax, eax
0x1800b1fbc  js      short loc_1800B1FF2
0x1800b1fbe  mov     rcx, [rbp+var_20]
0x1800b1fc2  lea     rdx, [rbp+var_40]
0x1800b1fc6  mov     rax, [rcx]
0x1800b1fc9  mov     rax, [rax+40h]
0x1800b1fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1fd2  mov     ebx, eax
0x1800b1fd4  test    eax, eax
0x1800b1fd6  js      short loc_1800B2000
0x1800b1fd8  lea     rcx, [rbp+var_28]; this
0x1800b1fdc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b1fe1  lea     rcx, [rbp+var_30]; this
0x1800b1fe5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b1fea  mov     al, byte ptr [rbp+var_40]
0x1800b1fed  jmp     loc_1800B1EDC
0x1800b1ff2  mov     edx, 115h
0x1800b1ff7  jmp     short loc_1800B2013
0x1800b1ff9  mov     edx, 10Fh
0x1800b1ffe  jmp     short loc_1800B2013
0x1800b2000  mov     edx, 119h
0x1800b2005  jmp     short loc_1800B2013
0x1800b2007  mov     edx, 10Ah
0x1800b200c  jmp     short loc_1800B2013
0x1800b200e  mov     edx, 107h; void *
0x1800b2013  mov     rcx, [rbp+18h]; this
0x1800b2017  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800b201e  mov     r9d, eax; char *
0x1800b2021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2026  lea     rcx, [rbp+var_28]; this
0x1800b202a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b202f  jmp     short loc_1800B2049
0x1800b2031  mov     rcx, [rbp+18h]; this
0x1800b2035  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800b203c  mov     r9d, eax; char *
0x1800b203f  mov     edx, 104h; void *
0x1800b2044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2049  lea     rcx, [rbp+var_30]; this
0x1800b204d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b2052  jmp     short loc_1800B206C
0x1800b2054  mov     rcx, [rbp+18h]; this
0x1800b2058  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800b205f  mov     r9d, eax; char *
0x1800b2062  mov     edx, 101h; void *
0x1800b2067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b206c  lea     rcx, [rbp+var_38]
0x1800b2070  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b2075  jmp     short loc_1800B207E
0x1800b2077  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b207c  xor     ebx, ebx
0x1800b207e  lea     rcx, [rbp+var_20]
0x1800b2082  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b2087  mov     eax, ebx
0x1800b2089  mov     rcx, [rbp+var_8]
0x1800b208d  xor     rcx, rsp; StackCookie
0x1800b2090  call    __security_check_cookie
0x1800b2095  mov     rbx, [rsp+60h+arg_10]
0x1800b209d  add     rsp, 60h
0x1800b20a1  pop     rdi
0x1800b20a2  pop     rsi
0x1800b20a3  pop     rbp
0x1800b20a4  retn
```
