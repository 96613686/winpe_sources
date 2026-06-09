# Windows::ApplicationModel::Resources::CResourceLoader::_RuntimeClassInitialize(Windows::ApplicationModel::Resources::Core::IResourceContext *,HSTRING__ *)

- ea: `0x180008cac`
- end: `0x1800091a3`
- name: `?_RuntimeClassInitialize@CResourceLoader@Resources@ApplicationModel@Windows@@AEAAJPEAUIResourceContext@Core@234@PEAUHSTRING__@@@Z`
- size: `1271`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::CResourceLoader *__hidden this, struct Windows::ApplicationModel::Resources::Core::IResourceContext *, HSTRING)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008bd8`
- `0x180053770`
- `0x1800ab484`

## callees

- `0x18000892c`
- `0x180008cac`
- `0x1800092c4`
- `0x18002c8d0`
- `0x1800794b8`
- `0x1800862f0`
- `0x1800867dc`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000903d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000903d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008f20`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008f20`

## string_xrefs

- `0x180008f2d`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x180008f8e`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x180008fd6`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x18000904a`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x1800090ab`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x18000911b`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x18000915d`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::ApplicationModel::Resources::CResourceLoader::_RuntimeClassInitialize(
        Windows::ApplicationModel::Resources::CResourceLoader *this,
        struct Windows::ApplicationModel::Resources::Core::IResourceContext *a2,
        HSTRING a3)
{
  Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  Windows::ApplicationModel::Resources::CResourceLoader *v11; // rcx
  unsigned int v12; // ebx
  struct Windows::ApplicationModel::Resources::Core::IResourceContext *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int DefaultResourceContext; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // [rsp+20h] [rbp-60h] BYREF
  __int64 v35; // [rsp+28h] [rbp-58h] BYREF
  __int64 v36; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::ApplicationModel::Resources::Core::IResourceContext *v37; // [rsp+38h] [rbp-48h] BYREF
  __int64 v38; // [rsp+40h] [rbp-40h]
  Windows::ApplicationModel::Resources::CResourceLoader *v39; // [rsp+48h] [rbp-38h]
  char v40; // [rsp+50h] [rbp-30h]
  _OWORD v41[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v39 = this;
  v40 = 1;
  v37 = a2;
  v38 = 0;
  v6 = (Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *)operator new(
                                                                                0x68u,
                                                                                (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
  {
    v7 = Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::CResourceManagerFactory(v6);
    v38 = v7;
    v8 = v7;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  if ( !v7 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
      (const char *)0x8007000ELL,
      v34);
    goto LABEL_29;
  }
  v34 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v8 + 40) + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v34);
  v10 = v9(v8 + 40, &v34);
  v12 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
      (const char *)(unsigned int)v10,
      v34);
    v29 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    goto LABEL_28;
  }
  if ( !a2 )
  {
    DefaultResourceContext = Windows::ApplicationModel::Resources::CResourceLoader::_GetDefaultResourceContext(
                               v11,
                               &v37);
    v12 = DefaultResourceContext;
    if ( DefaultResourceContext < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
        (const char *)(unsigned int)DefaultResourceContext,
        v34);
      v28 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
LABEL_28:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_29:
      *((_DWORD *)this + 22) = 2;
      return v12;
    }
  }
  v13 = v37;
  if ( !v37 )
  {
    v41[0] = *(_OWORD *)L"context failure";
    v41[1] = *(_OWORD *)L"failure";
    v12 = -2147467260;
    RoOriginateErrorW(2147500036LL, 15, v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
      (const char *)0x80004004LL,
      v34);
    v30 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_28;
  }
  if ( *((struct Windows::ApplicationModel::Resources::Core::IResourceContext **)this + 10) != v37 )
  {
    (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceContext *))(*(_QWORD *)v37 + 8LL))(v37);
    v14 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v13;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v35 = 0;
  v15 = v34;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v35);
  v17 = v16(v15, &v35);
  v12 = v17;
  if ( v17 < 0 )
  {
    if ( v17 != -2147009761 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
        (const char *)(unsigned int)v17,
        v34);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v34);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      goto LABEL_29;
    }
    v32 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_28;
  }
  if ( a3 )
  {
    v36 = 0;
    v18 = v35;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v35 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v36);
    v20 = v19(v18, a3, &v36);
    v12 = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -2147009761 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
          (const char *)(unsigned int)v20,
          v34);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v34);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        goto LABEL_29;
      }
      v24 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v25 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      goto LABEL_28;
    }
    if ( !v36 )
    {
      RoOriginateError(2147957535LL);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
        (const char *)0x80073B1FLL,
        v34);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v34);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      v12 = -2147009761;
      goto LABEL_29;
    }
    *((_QWORD *)this + 9) = v36;
    v21 = v35;
  }
  else
  {
    v31 = v35;
    v21 = 0;
    v35 = 0;
    *((_QWORD *)this + 9) = v31;
  }
  v40 = 0;
  *((_DWORD *)this + 22) = 1;
  if ( v21 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return 0;
}

```

## disassembly

```asm
0x180008cac  mov     [rsp-38h+arg_10], rbx
0x180008cb1  push    rbp
0x180008cb2  push    rsi
0x180008cb3  push    rdi
0x180008cb4  push    r12
0x180008cb6  push    r13
0x180008cb8  push    r14
0x180008cba  push    r15
0x180008cbc  mov     rbp, rsp
0x180008cbf  sub     rsp, 80h
0x180008cc6  mov     rax, cs:__security_cookie
0x180008ccd  xor     rax, rsp
0x180008cd0  mov     [rbp+var_8], rax
0x180008cd4  mov     r12, r8
0x180008cd7  mov     r15, rdx
0x180008cda  mov     r14, rcx
0x180008cdd  mov     [rbp+var_38], rcx
0x180008ce1  mov     [rbp+var_30], 1
0x180008ce5  mov     [rbp+var_48], rdx
0x180008ce9  xor     r13d, r13d
0x180008cec  mov     [rbp+var_40], r13
0x180008cf0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008cf7  lea     ecx, [r13+68h]; unsigned __int64
0x180008cfb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008d00  test    rax, rax
0x180008d03  jz      loc_180008E70
0x180008d09  mov     rcx, rax; this
0x180008d0c  call    ??0CResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@QEAA@XZ; Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::CResourceManagerFactory(void)
0x180008d11  mov     rsi, rax
0x180008d14  mov     [rbp+var_40], rax
0x180008d18  mov     rdi, rax
0x180008d1b  test    rsi, rsi
0x180008d1e  jz      loc_18000909F
0x180008d24  mov     [rbp+var_60], r13
0x180008d28  mov     rax, [rdi+28h]
0x180008d2c  mov     rbx, [rax+30h]
0x180008d30  lea     rcx, [rbp+var_60]
0x180008d34  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180008d39  lea     rdx, [rbp+var_60]
0x180008d3d  lea     rcx, [rdi+28h]
0x180008d41  mov     rax, rbx
0x180008d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d49  mov     ebx, eax
0x180008d4b  test    eax, eax
0x180008d4d  js      loc_180008FCF
0x180008d53  test    r15, r15
0x180008d56  jz      loc_180008F74
0x180008d5c  mov     rbx, [rbp+var_48]
0x180008d60  test    rbx, rbx
0x180008d63  jz      loc_180009017
0x180008d69  cmp     [r14+50h], rbx
0x180008d6d  jz      short loc_180008D9E
0x180008d6f  test    rbx, rbx
0x180008d72  jz      short loc_180008D84
0x180008d74  mov     rax, [rbx]
0x180008d77  mov     rcx, rbx
0x180008d7a  mov     rax, [rax+8]
0x180008d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d83  nop
0x180008d84  mov     rcx, [r14+50h]
0x180008d88  mov     [r14+50h], rbx
0x180008d8c  test    rcx, rcx
0x180008d8f  jz      short loc_180008D9E
0x180008d91  mov     rax, [rcx]
0x180008d94  mov     rax, [rax+10h]
0x180008d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d9d  nop
0x180008d9e  mov     [rbp+var_58], r13
0x180008da2  mov     rdi, [rbp+var_60]
0x180008da6  mov     rax, [rdi]
0x180008da9  mov     rbx, [rax+30h]
0x180008dad  lea     rcx, [rbp+var_58]
0x180008db1  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180008db6  lea     rdx, [rbp+var_58]
0x180008dba  mov     rcx, rdi
0x180008dbd  mov     rax, rbx
0x180008dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dc5  mov     ebx, eax
0x180008dc7  test    eax, eax
0x180008dc9  js      loc_1800090C2
0x180008dcf  test    r12, r12
0x180008dd2  jz      loc_18000908B
0x180008dd8  mov     [rbp+var_50], r13
0x180008ddc  mov     rdi, [rbp+var_58]
0x180008de0  mov     rax, [rdi]
0x180008de3  mov     rbx, [rax+48h]
0x180008de7  lea     rcx, [rbp+var_50]
0x180008deb  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180008df0  lea     r8, [rbp+var_50]
0x180008df4  mov     rdx, r12
0x180008df7  mov     rcx, rdi
0x180008dfa  mov     rax, rbx
0x180008dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e02  mov     ebx, eax
0x180008e04  test    eax, eax
0x180008e06  js      short loc_180008E7B
0x180008e08  mov     rax, [rbp+var_50]
0x180008e0c  test    rax, rax
0x180008e0f  jz      loc_180008F17
0x180008e15  mov     [r14+48h], rax
0x180008e19  mov     rcx, [rbp+var_58]
0x180008e1d  mov     [rbp+var_30], r13b
0x180008e21  mov     dword ptr [r14+58h], 1
0x180008e29  test    rcx, rcx
0x180008e2c  jz      short loc_180008E3F
0x180008e2e  mov     [rbp+var_58], r13
0x180008e32  mov     rax, [rcx]
0x180008e35  mov     rax, [rax+10h]
0x180008e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e3e  nop
0x180008e3f  mov     rcx, [rbp+var_60]
0x180008e43  test    rcx, rcx
0x180008e46  jz      short loc_180008E59
0x180008e48  mov     [rbp+var_60], r13
0x180008e4c  mov     rax, [rcx]
0x180008e4f  mov     rax, [rax+10h]
0x180008e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e58  nop
0x180008e59  mov     rax, [rsi]
0x180008e5c  mov     rcx, rsi
0x180008e5f  mov     rax, [rax+10h]
0x180008e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e68  nop
0x180008e69  xor     eax, eax
0x180008e6b  jmp     loc_180008EF0
0x180008e70  mov     rsi, r13
0x180008e73  mov     rdi, r13
0x180008e76  jmp     loc_180008D1B
0x180008e7b  mov     edi, 80073B1Fh
0x180008e80  cmp     ebx, edi
0x180008e82  jnz     loc_180009156
0x180008e88  mov     rcx, [rbp+var_50]
0x180008e8c  test    rcx, rcx
0x180008e8f  jz      short loc_180008EA2
0x180008e91  mov     [rbp+var_50], r13
0x180008e95  mov     rax, [rcx]
0x180008e98  mov     rax, [rax+10h]
0x180008e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ea1  nop
0x180008ea2  mov     rcx, [rbp+var_58]
0x180008ea6  test    rcx, rcx
0x180008ea9  jz      short loc_180008EBC
0x180008eab  mov     [rbp+var_58], r13
0x180008eaf  mov     rax, [rcx]
0x180008eb2  mov     rax, [rax+10h]
0x180008eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ebb  nop
0x180008ebc  mov     rcx, [rbp+var_60]
0x180008ec0  test    rcx, rcx
0x180008ec3  jz      short loc_180008ED6
0x180008ec5  mov     [rbp+var_60], r13
0x180008ec9  mov     rax, [rcx]
0x180008ecc  mov     rax, [rax+10h]
0x180008ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed5  nop
0x180008ed6  mov     rax, [rsi]
0x180008ed9  mov     rcx, rsi
0x180008edc  mov     rax, [rax+10h]
0x180008ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ee5  nop
0x180008ee6  mov     dword ptr [r14+58h], 2
0x180008eee  mov     eax, ebx
0x180008ef0  mov     rcx, [rbp+var_8]
0x180008ef4  xor     rcx, rsp; StackCookie
0x180008ef7  call    __security_check_cookie
0x180008efc  mov     rbx, [rsp+80h+arg_10]
0x180008f04  add     rsp, 80h
0x180008f0b  pop     r15
0x180008f0d  pop     r14
0x180008f0f  pop     r13
0x180008f11  pop     r12
0x180008f13  pop     rdi
0x180008f14  pop     rsi
0x180008f15  pop     rbp
0x180008f16  retn
0x180008f17  xor     edx, edx
0x180008f19  mov     edi, 80073B1Fh
0x180008f1e  mov     ecx, edi
0x180008f20  call    cs:__imp_RoOriginateError
0x180008f26  mov     rcx, [rbp+38h]; this
0x180008f2a  mov     r9d, edi; char *
0x180008f2d  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180008f34  mov     edx, 75h ; 'u'; void *
0x180008f39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f3e  nop
0x180008f3f  lea     rcx, [rbp+var_50]
0x180008f43  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180008f48  nop
0x180008f49  lea     rcx, [rbp+var_58]
0x180008f4d  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180008f52  nop
0x180008f53  lea     rcx, [rbp+var_60]
0x180008f57  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180008f5c  nop
0x180008f5d  mov     rax, [rsi]
0x180008f60  mov     rcx, rsi
0x180008f63  mov     rax, [rax+10h]
0x180008f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f6c  nop
0x180008f6d  mov     ebx, edi
0x180008f6f  jmp     loc_180008EE6
0x180008f74  lea     rdx, [rbp+var_48]; struct Windows::ApplicationModel::Resources::Core::IResourceContext **
0x180008f78  call    ?_GetDefaultResourceContext@CResourceLoader@Resources@ApplicationModel@Windows@@AEAAJPEAPEAUIResourceContext@Core@234@@Z; Windows::ApplicationModel::Resources::CResourceLoader::_GetDefaultResourceContext(Windows::ApplicationModel::Resources::Core::IResourceContext * *)
0x180008f7d  mov     ebx, eax
0x180008f7f  test    eax, eax
0x180008f81  jns     loc_180008D5C
0x180008f87  mov     rcx, [rbp+38h]; this
0x180008f8b  mov     r9d, eax; char *
0x180008f8e  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180008f95  mov     edx, 59h ; 'Y'; void *
0x180008f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f9f  nop
0x180008fa0  mov     rcx, [rbp+var_60]
0x180008fa4  test    rcx, rcx
0x180008fa7  jz      short loc_180008FBA
0x180008fa9  mov     [rbp+var_60], r13
0x180008fad  mov     rax, [rcx]
0x180008fb0  mov     rax, [rax+10h]
0x180008fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fb9  nop
0x180008fba  mov     rax, [rsi]
0x180008fbd  mov     rcx, rsi
0x180008fc0  mov     rax, [rax+10h]
0x180008fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc9  nop
0x180008fca  jmp     loc_180008EE6
0x180008fcf  mov     rcx, [rbp+38h]; this
0x180008fd3  mov     r9d, eax; char *
0x180008fd6  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180008fdd  mov     edx, 53h ; 'S'; void *
0x180008fe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fe7  nop
0x180008fe8  mov     rcx, [rbp+var_60]
0x180008fec  test    rcx, rcx
0x180008fef  jz      short loc_180009002
0x180008ff1  mov     [rbp+var_60], r13
0x180008ff5  mov     rax, [rcx]
0x180008ff8  mov     rax, [rax+10h]
0x180008ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009001  nop
0x180009002  mov     rax, [rsi]
0x180009005  mov     rcx, rsi
0x180009008  mov     rax, [rax+10h]
0x18000900c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009011  nop
0x180009012  jmp     loc_180008EE6
0x180009017  movups  xmm0, xmmword ptr cs:aContextFailure; "context failure"
0x18000901e  movups  [rbp+var_28], xmm0
0x180009022  movups  xmm1, xmmword ptr cs:aContextFailure+10h; "failure"
0x180009029  movups  [rbp+var_18], xmm1
0x18000902d  lea     r8, [rbp+var_28]
0x180009031  mov     edx, 0Fh
0x180009036  mov     ebx, 80004004h
0x18000903b  mov     ecx, ebx
0x18000903d  call    cs:__imp_RoOriginateErrorW
0x180009043  mov     rcx, [rbp+38h]; this
0x180009047  mov     r9d, ebx; char *
0x18000904a  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180009051  mov     edx, 60h ; '`'; void *
0x180009056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000905b  nop
0x18000905c  mov     rcx, [rbp+var_60]
0x180009060  test    rcx, rcx
0x180009063  jz      short loc_180009076
0x180009065  mov     [rbp+var_60], r13
0x180009069  mov     rax, [rcx]
0x18000906c  mov     rax, [rax+10h]
0x180009070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009075  nop
0x180009076  mov     rcx, [rsi]
0x180009079  mov     rax, [rcx+10h]
0x18000907d  mov     rcx, rsi
0x180009080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009085  nop
0x180009086  jmp     loc_180008EE6
0x18000908b  mov     rax, [rbp+var_58]
0x18000908f  mov     rcx, r13
0x180009092  mov     [rbp+var_58], rcx
0x180009096  mov     [r14+48h], rax
0x18000909a  jmp     loc_180008E1D
0x18000909f  mov     rcx, [rbp+38h]; this
0x1800090a3  mov     ebx, 8007000Eh
0x1800090a8  mov     r9d, ebx; char *
0x1800090ab  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800090b2  mov     edx, 50h ; 'P'; void *
0x1800090b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090bc  nop
0x1800090bd  jmp     loc_180008EE6
0x1800090c2  mov     edi, 80073B1Fh
0x1800090c7  cmp     eax, edi
0x1800090c9  jnz     short loc_180009114
0x1800090cb  mov     rcx, [rbp+var_58]
0x1800090cf  test    rcx, rcx
0x1800090d2  jz      short loc_1800090E5
0x1800090d4  mov     [rbp+var_58], r13
0x1800090d8  mov     rax, [rcx]
0x1800090db  mov     rax, [rax+10h]
0x1800090df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e4  nop
0x1800090e5  mov     rcx, [rbp+var_60]
  ... truncated ...
```
