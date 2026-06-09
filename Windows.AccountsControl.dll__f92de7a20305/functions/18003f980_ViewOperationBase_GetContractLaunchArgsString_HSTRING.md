# ViewOperationBase::GetContractLaunchArgsString(HSTRING__ * *)

- ea: `0x18003f980`
- end: `0x18003fba3`
- name: `?GetContractLaunchArgsString@ViewOperationBase@@AEAAJPEAPEAUHSTRING__@@@Z`
- size: `547`
- prototype: `int(ViewOperationBase *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800411d0`

## callees

- `0x180006eac`
- `0x18000a084`
- `0x180011ffc`
- `0x18003e050`
- `0x18003f980`
- `0x18004301c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003fb3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003fb3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ViewOperationBase::GetContractLaunchArgsString(ViewOperationBase *this, HSTRING *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  _QWORD *v13; // rax
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v18; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  int v20; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v21 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 17);
  v4 = **v3;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v5 = v4(v3, &GUID_1bc9f723_8ef1_4a51_a63a_fe711eeab607, &v21);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v18 = 0;
    v7 = v21;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    v9 = v8(v7, &v18);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v20 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 48LL))(v18, &v20);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v24 = 7;
        v23[2] = 0;
        LOWORD(v23[0]) = 0;
        v22[0] = v23;
        v22[1] = &v20;
        v11 = wil::ResultFromException__lambda_d8084d62c6edac922af6ec80c2313c23___(v22);
        v6 = v11;
        if ( v11 >= 0 )
        {
          string = 0;
          v13 = v23;
          if ( v24 >= 8 )
            v13 = (_QWORD *)v23[0];
          v22[0] = v13;
          v14 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v22);
          v6 = v14;
          if ( v14 >= 0 )
          {
            v14 = WindowsDuplicateString(string, a2);
            v6 = v14;
            if ( v14 >= 0 )
            {
              WindowsDeleteString(string);
              string = 0;
              LOBYTE(v16) = 1;
              std::wstring::_Tidy(v23, v16, 0);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
              v6 = 0;
              goto LABEL_20;
            }
            v15 = 493;
          }
          else
          {
            v15 = 492;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
            (const char *)(unsigned int)v14,
            v18);
          WindowsDeleteString(string);
          string = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E9,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
            (const char *)(unsigned int)v11,
            v18);
        }
        LOBYTE(v12) = 1;
        std::wstring::_Tidy(v23, v12, 0);
        goto LABEL_6;
      }
      v10 = 482;
    }
    else
    {
      v10 = 480;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
      (const char *)(unsigned int)v9,
      v18);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1DE,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
    (const char *)(unsigned int)v5,
    v18);
LABEL_20:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  return v6;
}

```

## disassembly

```asm
0x18003f980  mov     [rsp-18h+arg_10], rbx
0x18003f985  push    rbp
0x18003f986  push    rsi
0x18003f987  push    rdi
0x18003f988  mov     rbp, rsp
0x18003f98b  sub     rsp, 80h
0x18003f992  mov     rax, cs:__security_cookie
0x18003f999  xor     rax, rsp
0x18003f99c  mov     [rbp+var_10], rax
0x18003f9a0  mov     rsi, rdx
0x18003f9a3  mov     [rbp+var_48], 0
0x18003f9ab  mov     rdi, [rcx+88h]
0x18003f9b2  mov     rax, [rdi]
0x18003f9b5  mov     rbx, [rax]
0x18003f9b8  lea     rcx, [rbp+var_48]
0x18003f9bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f9c1  lea     r8, [rbp+var_48]
0x18003f9c5  lea     rdx, _GUID_1bc9f723_8ef1_4a51_a63a_fe711eeab607
0x18003f9cc  mov     rcx, rdi
0x18003f9cf  mov     rax, rbx
0x18003f9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9d7  mov     ebx, eax
0x18003f9d9  test    eax, eax
0x18003f9db  jns     short loc_18003F9FA
0x18003f9dd  mov     rcx, [rbp+18h]; this
0x18003f9e1  mov     r9d, eax; char *
0x18003f9e4  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x18003f9eb  mov     edx, 1DEh; void *
0x18003f9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f9f5  jmp     loc_18003FB79
0x18003f9fa  mov     [rbp+var_60], 0
0x18003fa02  mov     rdi, [rbp+var_48]
0x18003fa06  mov     rax, [rdi]
0x18003fa09  mov     rbx, [rax+30h]
0x18003fa0d  lea     rcx, [rbp+var_60]
0x18003fa11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003fa16  lea     rdx, [rbp+var_60]
0x18003fa1a  mov     rcx, rdi
0x18003fa1d  mov     rax, rbx
0x18003fa20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa25  mov     ebx, eax
0x18003fa27  test    eax, eax
0x18003fa29  jns     short loc_18003FA52
0x18003fa2b  mov     edx, 1E0h; void *
0x18003fa30  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x18003fa37  mov     r9d, eax; char *
0x18003fa3a  mov     rcx, [rbp+18h]; this
0x18003fa3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa43  nop
0x18003fa44  lea     rcx, [rbp+var_60]
0x18003fa48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003fa4d  jmp     loc_18003FB79
0x18003fa52  mov     [rbp+var_50], 0
0x18003fa59  mov     rcx, [rbp+var_60]
0x18003fa5d  mov     rax, [rcx]
0x18003fa60  lea     rdx, [rbp+var_50]
0x18003fa64  mov     rax, [rax+30h]
0x18003fa68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa6d  mov     ebx, eax
0x18003fa6f  test    eax, eax
0x18003fa71  jns     short loc_18003FA7A
0x18003fa73  mov     edx, 1E2h
0x18003fa78  jmp     short loc_18003FA30
0x18003fa7a  mov     [rbp+var_18], 7
0x18003fa82  mov     [rbp+var_20], 0
0x18003fa8a  xor     eax, eax
0x18003fa8c  mov     word ptr [rbp+var_30], ax
0x18003fa90  lea     rax, [rbp+var_30]
0x18003fa94  mov     [rbp+var_40], rax
0x18003fa98  lea     rax, [rbp+var_50]
0x18003fa9c  mov     [rbp+var_38], rax
0x18003faa0  lea     rcx, [rbp+var_40]
0x18003faa4  call    wil__ResultFromException__lambda_d8084d62c6edac922af6ec80c2313c23___
0x18003faa9  mov     ebx, eax
0x18003faab  test    eax, eax
0x18003faad  jns     short loc_18003FADA
0x18003faaf  mov     rcx, [rbp+18h]; this
0x18003fab3  mov     r9d, eax; char *
0x18003fab6  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x18003fabd  mov     edx, 1E9h; void *
0x18003fac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fac7  xor     r8d, r8d
0x18003faca  mov     dl, 1
0x18003facc  lea     rcx, [rbp+var_30]
0x18003fad0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003fad5  jmp     loc_18003FA44
0x18003fada  mov     [rbp+string], 0
0x18003fae2  lea     rax, [rbp+var_30]
0x18003fae6  cmp     [rbp+var_18], 8
0x18003faeb  cmovnb  rax, [rbp+var_30]
0x18003faf0  mov     [rbp+var_40], rax
0x18003faf4  lea     rdx, [rbp+var_40]
0x18003faf8  lea     rcx, [rbp+string]
0x18003fafc  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003fb01  mov     ebx, eax
0x18003fb03  test    eax, eax
0x18003fb05  jns     short loc_18003FB33
0x18003fb07  mov     edx, 1ECh; void *
0x18003fb0c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x18003fb13  mov     r9d, eax; char *
0x18003fb16  mov     rcx, [rbp+18h]; this
0x18003fb1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb1f  mov     rcx, [rbp+string]; string
0x18003fb23  call    cs:__imp_WindowsDeleteString
0x18003fb29  mov     [rbp+string], 0
0x18003fb31  jmp     short loc_18003FAC7
0x18003fb33  mov     rdx, rsi; newString
0x18003fb36  mov     rcx, [rbp+string]; string
0x18003fb3a  call    cs:__imp_WindowsDuplicateString
0x18003fb40  mov     ebx, eax
0x18003fb42  test    eax, eax
0x18003fb44  jns     short loc_18003FB4D
0x18003fb46  mov     edx, 1EDh
0x18003fb4b  jmp     short loc_18003FB0C
0x18003fb4d  mov     rcx, [rbp+string]; string
0x18003fb51  call    cs:__imp_WindowsDeleteString
0x18003fb57  mov     [rbp+string], 0
0x18003fb5f  xor     r8d, r8d
0x18003fb62  mov     dl, 1
0x18003fb64  lea     rcx, [rbp+var_30]
0x18003fb68  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003fb6d  nop
0x18003fb6e  lea     rcx, [rbp+var_60]
0x18003fb72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003fb77  xor     ebx, ebx
0x18003fb79  lea     rcx, [rbp+var_48]
0x18003fb7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003fb82  mov     eax, ebx
0x18003fb84  mov     rcx, [rbp+var_10]
0x18003fb88  xor     rcx, rsp; StackCookie
0x18003fb8b  call    __security_check_cookie
0x18003fb90  mov     rbx, [rsp+80h+arg_10]
0x18003fb98  add     rsp, 80h
0x18003fb9f  pop     rdi
0x18003fba0  pop     rsi
0x18003fba1  pop     rbp
0x18003fba2  retn
```
