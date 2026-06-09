# ParseJsonResultDynamicStatusArray

- ea: `0x180037a2c`
- end: `0x180038215`
- name: `ParseJsonResultDynamicStatusArray`
- size: `2025`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039968`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180013d4c`
- `0x18001438c`
- `0x1800143c8`
- `0x18001440c`
- `0x180018ac0`
- `0x180019188`
- `0x180019208`
- `0x1800192b4`
- `0x180019728`
- `0x180019d38`
- `0x180019ec8`
- `0x18001a048`
- `0x18001b6b8`
- `0x18001e00c`
- `0x1800233b8`
- `0x1800370d4`
- `0x180037a2c`
- `0x18003d15c`
- `0x18004abf8`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037f9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800380fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ebe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037f9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800380fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381a0`

## string_xrefs

- `0x180037da0`: `Windows.Data.Json.JsonArray`
- `0x180037abd`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180037b30`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180037b8a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180037c7f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180037cfe`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180037dd7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180037e8e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180038082`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ParseJsonResultDynamicStatusArray(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        _WORD *a3,
        __int64 a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 result; // rax
  unsigned int v11; // r14d
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  const char *v16; // r9
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, HSTRING *); // rbx
  _QWORD *v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // r8
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64 *); // rbx
  __int64 v32; // rax
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // ebx
  __int64 v36; // r8
  char **v37; // rdx
  __int64 v38; // r8
  _QWORD *v39; // rcx
  HSTRING string; // [rsp+20h] [rbp-108h] BYREF
  __int64 v41; // [rsp+28h] [rbp-100h] BYREF
  __int64 v42; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v43; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v44; // [rsp+40h] [rbp-E8h] BYREF
  void *v45; // [rsp+48h] [rbp-E0h] BYREF
  __int128 v46; // [rsp+50h] [rbp-D8h]
  unsigned int v47; // [rsp+60h] [rbp-C8h] BYREF
  char **v48; // [rsp+68h] [rbp-C0h] BYREF
  std::_Ref_count_base *v49; // [rsp+70h] [rbp-B8h]
  _QWORD *v50; // [rsp+78h] [rbp-B0h] BYREF
  _WORD *v51; // [rsp+80h] [rbp-A8h] BYREF
  char *v52[4]; // [rsp+88h] [rbp-A0h] BYREF
  _QWORD v53[4]; // [rsp+A8h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v51 = a3;
  v41 = 0;
  v7 = (**a2)(a2, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v41);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 6459;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    return v8;
  }
  v47 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 56LL))(v41, &v47);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 6463;
    goto LABEL_5;
  }
  v11 = 0;
  try
  {
    while ( 1 )
    {
      if ( v11 >= v47 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return 0;
      }
      v42 = 0;
      v12 = v41;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
      v14 = v13(v12, v11, &v42);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1947,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v14,
          (int)string);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return v15;
      }
      v43 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 96LL))(v42, &v43);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x194B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v17,
          (int)string);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return v18;
      }
      v19 = std::wstring::wstring((__int64)&hstringHeader, (__int64)a3);
      std::operator+<unsigned short>(v53, v19, L"Id");
      std::wstring::_Tidy_deallocate(&hstringHeader);
      string = 0;
      std::wstring::wstring((__int64)v52);
      v20 = v43;
      v21 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v43 + 80LL);
      WindowsDeleteString(string);
      string = 0;
      v22 = v53;
      if ( v53[3] > 7u )
        v22 = (_QWORD *)v53[0];
      v50 = v22;
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v50);
      v24 = v21(v20, *(_QWORD *)(v23 + 24), &string);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1951,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v24,
          (int)string);
        std::wstring::_Tidy_deallocate(v52);
        WindowsDeleteString(string);
        string = 0;
        std::wstring::_Tidy_deallocate(v53);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return v25;
      }
      if ( !string )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1955,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)0x80070057LL,
          0);
        std::wstring::_Tidy_deallocate(v52);
        WindowsDeleteString(string);
        string = 0;
        std::wstring::_Tidy_deallocate(v53);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return 2147942487LL;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v27 = -1;
      do
        ++v27;
      while ( StringRawBuffer[v27] );
      std::wstring::_Assign<unsigned short>(v52, StringRawBuffer, (char *)v27);
      v44 = 0;
      v55 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonArray",
        0x1Cu,
        0x1Bu);
      v28 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(v55, &v44);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x195A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v28,
          (int)string);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        std::wstring::_Tidy_deallocate(v52);
        WindowsDeleteString(string);
        string = 0;
        std::wstring::_Tidy_deallocate(v53);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return v29;
      }
      v30 = v43;
      v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 72LL);
      v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v51);
      v33 = v31(v30, *(_QWORD *)(v32 + 24), &v44);
      v34 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x195C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v33,
          (int)string);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        std::wstring::_Tidy_deallocate(v52);
        WindowsDeleteString(string);
        string = 0;
        std::wstring::_Tidy_deallocate(v53);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return v34;
      }
      std::vector<ConfigDoc>::vector<ConfigDoc>(&v45);
      v35 = ParseJsonResultStatusArray(a1, v44, &v45);
      std::make_shared<OsConfigSettingResult,>(&v48);
      if ( !v48 )
      {
        if ( v49 )
          std::_Ref_count_base::_Decref(v49);
        if ( v45 )
        {
          std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(v45, v46);
          std::_Deallocate<16>(v45, (*((_QWORD *)&v46 + 1) - (_QWORD)v45) & 0xFFFFFFFFFFFFFFF0uLL);
          v45 = 0;
          v46 = 0;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        std::wstring::_Tidy_deallocate(v52);
        WindowsDeleteString(string);
        string = 0;
        std::wstring::_Tidy_deallocate(v53);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        return 2147942414LL;
      }
      v36 = -1;
      do
        ++v36;
      while ( a3[v36] );
      std::wstring::_Assign<unsigned short>(v48, a3, (char *)v36);
      v37 = v52;
      if ( v52[3] > (char *)7 )
        v37 = (char **)v52[0];
      v38 = -1;
      do
        ++v38;
      while ( *((_WORD *)v37 + v38) );
      std::wstring::_Assign<unsigned short>(v48 + 39, v37, (char *)v38);
      std::vector<std::shared_ptr<OsConfigSettingResult>>::operator=(v48 + 36, &v45);
      v39 = *(_QWORD **)(a4 + 8);
      if ( v39 == *(_QWORD **)(a4 + 16) )
      {
        std::vector<std::shared_ptr<DCDSCNativeKeyValue>>::_Emplace_reallocate<std::shared_ptr<DCDSCNativeKeyValue> const &>(
          a4,
          *(_QWORD *)(a4 + 8),
          &v48);
      }
      else
      {
        std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v39, &v48);
        *(_QWORD *)(a4 + 8) += 16LL;
      }
      if ( v35 < 0 )
        break;
      if ( v49 )
        std::_Ref_count_base::_Decref(v49);
      if ( v45 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(v45, v46);
        std::_Deallocate<16>(v45, (*((_QWORD *)&v46 + 1) - (_QWORD)v45) & 0xFFFFFFFFFFFFFFF0uLL);
        v45 = 0;
        v46 = 0;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
      std::wstring::_Tidy_deallocate(v52);
      WindowsDeleteString(string);
      string = 0;
      std::wstring::_Tidy_deallocate(v53);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
      ++v11;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x196F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v35,
      (int)string);
    if ( v49 )
      std::_Ref_count_base::_Decref(v49);
    if ( v45 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<DCProviderOrchestration>>>(v45, v46);
      std::_Deallocate<16>(v45, (*((_QWORD *)&v46 + 1) - (_QWORD)v45) & 0xFFFFFFFFFFFFFFF0uLL);
      v45 = 0;
      v46 = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    std::wstring::_Tidy_deallocate(v52);
    WindowsDeleteString(string);
    string = 0;
    std::wstring::_Tidy_deallocate(v53);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    result = (unsigned int)v35;
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x1972,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                        v16);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x180037a2c  push    rbx
0x180037a2e  push    rsi
0x180037a2f  push    rdi
0x180037a30  push    r12
0x180037a32  push    r13
0x180037a34  push    r14
0x180037a36  push    r15
0x180037a38  sub     rsp, 0F0h
0x180037a3f  mov     rax, cs:__security_cookie
0x180037a46  xor     rax, rsp
0x180037a49  mov     [rsp+128h+var_40], rax
0x180037a51  mov     rsi, r9
0x180037a54  mov     r15, r8
0x180037a57  mov     r10, rdx
0x180037a5a  mov     r12, rcx
0x180037a5d  mov     [rsp+128h+var_A8], r8
0x180037a65  xor     r13d, r13d
0x180037a68  mov     [rsp+128h+var_100], r13
0x180037a6d  mov     rax, [rdx]
0x180037a70  lea     r8, [rsp+128h+var_100]
0x180037a75  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x180037a7c  mov     rcx, r10
0x180037a7f  mov     rax, [rax]
0x180037a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a87  mov     ebx, eax
0x180037a89  test    eax, eax
0x180037a8b  jns     short loc_180037A94
0x180037a8d  mov     edx, 193Bh
0x180037a92  jmp     short loc_180037ABA
0x180037a94  mov     [rsp+128h+var_C8], r13d
0x180037a99  mov     rcx, [rsp+128h+var_100]
0x180037a9e  mov     rax, [rcx]
0x180037aa1  lea     rdx, [rsp+128h+var_C8]
0x180037aa6  mov     rax, [rax+38h]
0x180037aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aaf  mov     ebx, eax
0x180037ab1  test    eax, eax
0x180037ab3  jns     short loc_180037AE3
0x180037ab5  mov     edx, 193Fh; void *
0x180037aba  mov     r9d, eax; char *
0x180037abd  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180037ac4  mov     rcx, [rsp+128h]; this
0x180037acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037ad1  nop
0x180037ad2  lea     rcx, [rsp+128h+var_100]
0x180037ad7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037adc  mov     eax, ebx
0x180037ade  jmp     loc_1800381F2
0x180037ae3  mov     r14d, r13d
0x180037ae6  cmp     r14d, [rsp+128h+var_C8]
0x180037aeb  jnb     loc_1800381D6
0x180037af1  mov     [rsp+128h+var_F8], r13
0x180037af6  mov     rdi, [rsp+128h+var_100]
0x180037afb  mov     rax, [rdi]
0x180037afe  mov     rbx, [rax+30h]
0x180037b02  lea     rcx, [rsp+128h+var_F8]
0x180037b07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037b0c  lea     r8, [rsp+128h+var_F8]
0x180037b11  mov     edx, r14d
0x180037b14  mov     rcx, rdi
0x180037b17  mov     rax, rbx
0x180037b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b1f  mov     ebx, eax
0x180037b21  test    eax, eax
0x180037b23  jns     short loc_180037B5E
0x180037b25  mov     rcx, [rsp+128h]; this
0x180037b2d  mov     r9d, eax; char *
0x180037b30  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180037b37  mov     edx, 1947h; void *
0x180037b3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037b41  nop
0x180037b42  lea     rcx, [rsp+128h+var_F8]
0x180037b47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037b4c  nop
0x180037b4d  lea     rcx, [rsp+128h+var_100]
0x180037b52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037b57  mov     eax, ebx
0x180037b59  jmp     loc_1800381F2
0x180037b5e  mov     [rsp+128h+var_F0], r13
0x180037b63  mov     rcx, [rsp+128h+var_F8]
0x180037b68  mov     rax, [rcx]
0x180037b6b  lea     rdx, [rsp+128h+var_F0]
0x180037b70  mov     rax, [rax+60h]
0x180037b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b79  mov     ebx, eax
0x180037b7b  test    eax, eax
0x180037b7d  jns     short loc_180037BC3
0x180037b7f  mov     rcx, [rsp+128h]; this
0x180037b87  mov     r9d, eax; char *
0x180037b8a  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180037b91  mov     edx, 194Bh; void *
0x180037b96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037b9b  nop
0x180037b9c  lea     rcx, [rsp+128h+var_F0]
0x180037ba1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037ba6  nop
0x180037ba7  lea     rcx, [rsp+128h+var_F8]
0x180037bac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037bb1  nop
0x180037bb2  lea     rcx, [rsp+128h+var_100]
0x180037bb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037bbc  mov     eax, ebx
0x180037bbe  jmp     loc_1800381F2
0x180037bc3  mov     rdx, r15
0x180037bc6  lea     rcx, [rsp+128h+hstringHeader]
0x180037bce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037bd3  nop
0x180037bd4  lea     r8, aId; "Id"
0x180037bdb  mov     rdx, rax
0x180037bde  lea     rcx, [rsp+128h+var_80]
0x180037be6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180037beb  nop
0x180037bec  lea     rcx, [rsp+128h+hstringHeader]
0x180037bf4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037bf9  mov     [rsp+128h+string], r13
0x180037bfe  lea     rcx, [rsp+128h+var_A0]
0x180037c06  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180037c0b  nop
0x180037c0c  mov     rdi, [rsp+128h+var_F0]
0x180037c11  mov     rax, [rdi]
0x180037c14  mov     rbx, [rax+50h]
0x180037c18  mov     rcx, [rsp+128h+string]; string
0x180037c1d  call    cs:__imp_WindowsDeleteString
0x180037c23  mov     [rsp+128h+string], r13; int
0x180037c28  lea     rdx, [rsp+128h+var_80]
0x180037c30  cmp     [rsp+128h+var_68], 7
0x180037c39  cmova   rdx, [rsp+128h+var_80]
0x180037c42  mov     [rsp+128h+var_B0], rdx
0x180037c47  lea     rdx, [rsp+128h+var_B0]
0x180037c4c  lea     rcx, [rsp+128h+hstringHeader]
0x180037c54  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037c59  nop
0x180037c5a  lea     r8, [rsp+128h+string]
0x180037c5f  mov     rdx, [rax+18h]
0x180037c63  mov     rcx, rdi
0x180037c66  mov     rax, rbx
0x180037c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c6e  mov     ebx, eax
0x180037c70  test    eax, eax
0x180037c72  jns     short loc_180037CE4
0x180037c74  mov     rcx, [rsp+128h]; this
0x180037c7c  mov     r9d, eax; char *
0x180037c7f  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180037c86  mov     edx, 1951h; void *
0x180037c8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c90  nop
0x180037c91  lea     rcx, [rsp+128h+var_A0]
0x180037c99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037c9e  nop
0x180037c9f  mov     rcx, [rsp+128h+string]; string
0x180037ca4  call    cs:__imp_WindowsDeleteString
0x180037caa  mov     [rsp+128h+string], r13
0x180037caf  lea     rcx, [rsp+128h+var_80]
0x180037cb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037cbc  nop
0x180037cbd  lea     rcx, [rsp+128h+var_F0]
0x180037cc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037cc7  nop
0x180037cc8  lea     rcx, [rsp+128h+var_F8]
0x180037ccd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037cd2  nop
0x180037cd3  lea     rcx, [rsp+128h+var_100]
0x180037cd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037cdd  mov     eax, ebx
0x180037cdf  jmp     loc_1800381F2
0x180037ce4  mov     rcx, [rsp+128h+string]; string
0x180037ce9  test    rcx, rcx
0x180037cec  jnz     short loc_180037D63
0x180037cee  mov     rcx, [rsp+128h]; this
0x180037cf6  mov     ebx, 80070057h
0x180037cfb  mov     r9d, ebx; char *
0x180037cfe  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180037d05  mov     edx, 1955h; void *
0x180037d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037d0f  nop
0x180037d10  lea     rcx, [rsp+128h+var_A0]
0x180037d18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037d1d  nop
0x180037d1e  mov     rcx, [rsp+128h+string]; string
0x180037d23  call    cs:__imp_WindowsDeleteString
0x180037d29  mov     [rsp+128h+string], r13
0x180037d2e  lea     rcx, [rsp+128h+var_80]
0x180037d36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037d3b  nop
0x180037d3c  lea     rcx, [rsp+128h+var_F0]
0x180037d41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037d46  nop
0x180037d47  lea     rcx, [rsp+128h+var_F8]
0x180037d4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037d51  nop
0x180037d52  lea     rcx, [rsp+128h+var_100]
0x180037d57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037d5c  mov     eax, ebx
0x180037d5e  jmp     loc_1800381F2
0x180037d63  xor     edx, edx; length
0x180037d65  call    cs:__imp_WindowsGetStringRawBuffer
0x180037d6b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037d6f  inc     r8
0x180037d72  cmp     [rax+r8*2], r13w
0x180037d77  jnz     short loc_180037D6F
0x180037d79  mov     rdx, rax
0x180037d7c  lea     rcx, [rsp+128h+var_A0]
0x180037d84  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180037d89  mov     [rsp+128h+var_E8], r13
0x180037d8e  mov     [rsp+128h+var_48], r13
0x180037d96  mov     r9d, 1Bh; unsigned int
0x180037d9c  lea     r8d, [r9+1]; unsigned int
0x180037da0  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x180037da7  lea     rcx, [rsp+128h+hstringHeader]; hstringHeader
0x180037daf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180037db4  lea     rdx, [rsp+128h+var_E8]
0x180037db9  mov     rcx, [rsp+128h+var_48]
0x180037dc1  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>>)
0x180037dc6  mov     ebx, eax
0x180037dc8  test    eax, eax
0x180037dca  jns     short loc_180037E47
0x180037dcc  mov     rcx, [rsp+128h]; this
0x180037dd4  mov     r9d, eax; char *
0x180037dd7  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180037dde  mov     edx, 195Ah; void *
0x180037de3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037de8  nop
0x180037de9  lea     rcx, [rsp+128h+var_E8]
0x180037dee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037df3  nop
0x180037df4  lea     rcx, [rsp+128h+var_A0]
0x180037dfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037e01  nop
0x180037e02  mov     rcx, [rsp+128h+string]; string
0x180037e07  call    cs:__imp_WindowsDeleteString
0x180037e0d  mov     [rsp+128h+string], r13
0x180037e12  lea     rcx, [rsp+128h+var_80]
0x180037e1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037e1f  nop
0x180037e20  lea     rcx, [rsp+128h+var_F0]
0x180037e25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037e2a  nop
0x180037e2b  lea     rcx, [rsp+128h+var_F8]
0x180037e30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037e35  nop
0x180037e36  lea     rcx, [rsp+128h+var_100]
0x180037e3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037e40  mov     eax, ebx
0x180037e42  jmp     loc_1800381F2
0x180037e47  mov     rdi, [rsp+128h+var_F0]
0x180037e4c  mov     rax, [rdi]
0x180037e4f  mov     rbx, [rax+48h]
0x180037e53  lea     rdx, [rsp+128h+var_A8]
0x180037e5b  lea     rcx, [rsp+128h+hstringHeader]
0x180037e63  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037e68  nop
0x180037e69  lea     r8, [rsp+128h+var_E8]
0x180037e6e  mov     rdx, [rax+18h]
0x180037e72  mov     rcx, rdi
0x180037e75  mov     rax, rbx
0x180037e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e7d  mov     ebx, eax
0x180037e7f  test    eax, eax
0x180037e81  jns     short loc_180037EFE
0x180037e83  mov     rcx, [rsp+128h]; this
0x180037e8b  mov     r9d, eax; char *
0x180037e8e  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180037e95  mov     edx, 195Ch; void *
0x180037e9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e9f  nop
0x180037ea0  lea     rcx, [rsp+128h+var_E8]
0x180037ea5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037eaa  nop
0x180037eab  lea     rcx, [rsp+128h+var_A0]
0x180037eb3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037eb8  nop
0x180037eb9  mov     rcx, [rsp+128h+string]; string
0x180037ebe  call    cs:__imp_WindowsDeleteString
0x180037ec4  mov     [rsp+128h+string], r13
0x180037ec9  lea     rcx, [rsp+128h+var_80]
0x180037ed1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037ed6  nop
0x180037ed7  lea     rcx, [rsp+128h+var_F0]
0x180037edc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037ee1  nop
0x180037ee2  lea     rcx, [rsp+128h+var_F8]
0x180037ee7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037eec  nop
0x180037eed  lea     rcx, [rsp+128h+var_100]
0x180037ef2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037ef7  mov     eax, ebx
0x180037ef9  jmp     loc_1800381F2
0x180037efe  lea     rcx, [rsp+128h+var_E0]
0x180037f03  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x180037f08  nop
0x180037f09  lea     r8, [rsp+128h+var_E0]
0x180037f0e  mov     rdx, [rsp+128h+var_E8]
0x180037f13  mov     rcx, r12
0x180037f16  call    ParseJsonResultStatusArray
0x180037f1b  mov     ebx, eax
0x180037f1d  lea     rcx, [rsp+128h+var_C0]
0x180037f22  call    ??$make_shared@VOsConfigSettingResult@@$$V@std@@YA?AV?$shared_ptr@VOsConfigSettingResult@@@0@XZ; std::make_shared<OsConfigSettingResult,>(void)
0x180037f27  nop
0x180037f28  mov     rcx, [rsp+128h+var_C0]
0x180037f2d  test    rcx, rcx
  ... truncated ...
```
