# Windows::ApplicationModel::Resources::Core::CResourceContext::put_Languages(Windows::Foundation::Collections::IVectorView<HSTRING__ *> *)

- ea: `0x180065c40`
- end: `0x180065f41`
- name: `?put_Languages@CResourceContext@Core@Resources@ApplicationModel@Windows@@UEAAJPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@5@@Z`
- size: `769`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000892c`
- `0x18002c8d0`
- `0x180045d4c`
- `0x180065c40`
- `0x18006997c`
- `0x1800862f0`
- `0x1800afa34`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c412d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c412d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180065e62`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180065e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180065d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180065d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065dc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065dc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c4116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c4116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180065db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180065db2`

## string_xrefs

- `0x180065cf0`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x180065e6f`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x180065e8c`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x180065ec3`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x180065f08`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800c4152`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800c41aa`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800c41f3`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800c4239`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceContext::put_Languages(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v13; // eax
  HSTRING v14; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // [rsp+20h] [rbp-39h] BYREF
  __int64 v23; // [rsp+28h] [rbp-31h] BYREF
  __int64 v24; // [rsp+30h] [rbp-29h] BYREF
  __int64 v25; // [rsp+38h] [rbp-21h] BYREF
  HSTRING string; // [rsp+40h] [rbp-19h] BYREF
  BOOL hasEmbedNull; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !a2 )
  {
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)L"languages";
    *(_DWORD *)&hstringHeader.Reserved.Reserved2[16] = *(_DWORD *)L"s";
    v6 = -2147024809;
    RoOriginateErrorW(2147942487LL, 9, &hstringHeader);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)0x80070057LL,
      v22);
    return v6;
  }
  string = 0;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[1])(a2);
  v24 = 0;
  v4 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
  v5 = v4(a2, &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e, &v24);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)v5,
      v22);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
LABEL_38:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    return v6;
  }
  v23 = 0;
  v7 = v24;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v23);
  v9 = v8(v7, &v23);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)v9,
      v22);
    v10 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
    return v6;
  }
  LOBYTE(v22) = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 56LL))(v23, &v22);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)v13,
      v22);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
    goto LABEL_38;
  }
  while ( (_BYTE)v22 )
  {
    v25 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 48LL))(v23, &v25);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)(unsigned int)v18,
        v22);
      Windows::Internal::String::~String((Windows::Internal::String *)&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
      goto LABEL_38;
    }
    v19 = Windows::Internal::String::Concat(
            (Windows::Internal::String *)&string,
            (const struct Windows::Internal::String *)&v25,
            (struct Windows::Internal::String *)&string);
    v6 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)(unsigned int)v19,
        v22);
      Windows::Internal::String::~String((Windows::Internal::String *)&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
      goto LABEL_38;
    }
    v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 64LL))(v23, &v22);
    v6 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x167,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)(unsigned int)v20,
        v22);
      Windows::Internal::String::~String((Windows::Internal::String *)&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
      goto LABEL_38;
    }
    if ( (_BYTE)v22 )
    {
      if ( WindowsCreateStringReference(
             L";",
             1u,
             (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
             (HSTRING *)&hstringHeader) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v21 = Windows::Internal::String::Concat(
              (Windows::Internal::String *)&string,
              (const struct Windows::Internal::String *)&hstringHeader,
              (struct Windows::Internal::String *)&string);
      v6 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
          (const char *)(unsigned int)v21,
          v22);
        Windows::Internal::String::~String((Windows::Internal::String *)&v25);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v23);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
        goto LABEL_38;
      }
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&v25);
  }
  v14 = string;
  if ( WindowsGetStringLen(string) )
  {
    hasEmbedNull = 0;
    WindowsStringHasEmbeddedNull(v14, &hasEmbedNull);
    if ( hasEmbedNull )
    {
      v6 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)0x80070057LL,
        v22);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v24);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
      goto LABEL_38;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v14, 0);
    Windows::ApplicationModel::Resources::Core::CQualifierEvent::UpdateQualifierIfChanged(
      *(_QWORD *)(a1 + 88),
      L"Language",
      StringRawBuffer,
      0);
  }
  v16 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a2)[2])(a2);
  if ( v14 )
    WindowsDeleteString(v14);
  return 0;
}

```

## disassembly

```asm
0x180065c40  push    rbp
0x180065c42  push    rbx
0x180065c43  push    rsi
0x180065c44  push    rdi
0x180065c45  push    r14
0x180065c47  push    r15
0x180065c49  lea     rbp, [rsp-2Fh]
0x180065c4e  sub     rsp, 88h
0x180065c55  mov     rax, cs:__security_cookie
0x180065c5c  xor     rax, rsp
0x180065c5f  mov     [rbp+57h+var_40], rax
0x180065c63  mov     rsi, rdx
0x180065c66  mov     r14, rcx
0x180065c69  xor     r15d, r15d
0x180065c6c  test    rdx, rdx
0x180065c6f  jz      loc_180065E3E
0x180065c75  mov     [rbp+57h+string], r15
0x180065c79  mov     rax, [rdx]
0x180065c7c  mov     rcx, rdx
0x180065c7f  mov     rax, [rax+8]
0x180065c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c88  nop
0x180065c89  mov     [rbp+57h+var_80], r15
0x180065c8d  mov     rax, [rsi]
0x180065c90  mov     rbx, [rax]
0x180065c93  lea     rcx, [rbp+57h+var_80]
0x180065c97  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180065c9c  lea     r8, [rbp+57h+var_80]
0x180065ca0  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x180065ca7  mov     rcx, rsi
0x180065caa  mov     rax, rbx
0x180065cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cb2  mov     ebx, eax
0x180065cb4  test    eax, eax
0x180065cb6  js      loc_180065E85
0x180065cbc  mov     [rbp+57h+var_88], r15
0x180065cc0  mov     rdi, [rbp+57h+var_80]
0x180065cc4  mov     rax, [rdi]
0x180065cc7  mov     rbx, [rax+30h]
0x180065ccb  lea     rcx, [rbp+57h+var_88]
0x180065ccf  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180065cd4  lea     rdx, [rbp+57h+var_88]
0x180065cd8  mov     rcx, rdi
0x180065cdb  mov     rax, rbx
0x180065cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ce3  mov     ebx, eax
0x180065ce5  test    eax, eax
0x180065ce7  jns     short loc_180065D64
0x180065ce9  mov     rcx, [rbp+5Fh]; this
0x180065ced  mov     r9d, eax; char *
0x180065cf0  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180065cf7  mov     edx, 15Ch; void *
0x180065cfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065d01  nop
0x180065d02  mov     rcx, [rbp+57h+var_88]
0x180065d06  test    rcx, rcx
0x180065d09  jz      short loc_180065D1C
0x180065d0b  mov     [rbp+57h+var_88], r15
0x180065d0f  mov     rax, [rcx]
0x180065d12  mov     rax, [rax+10h]
0x180065d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d1b  nop
0x180065d1c  mov     rcx, [rbp+57h+var_80]
0x180065d20  test    rcx, rcx
0x180065d23  jz      short loc_180065D36
0x180065d25  mov     [rbp+57h+var_80], r15
0x180065d29  mov     rax, [rcx]
0x180065d2c  mov     rax, [rax+10h]
0x180065d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d35  nop
0x180065d36  mov     rax, [rsi]
0x180065d39  mov     rcx, rsi
0x180065d3c  mov     rax, [rax+10h]
0x180065d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d45  nop
0x180065d46  mov     eax, ebx
0x180065d48  mov     rcx, [rbp+57h+var_40]
0x180065d4c  xor     rcx, rsp; StackCookie
0x180065d4f  call    __security_check_cookie
0x180065d54  add     rsp, 88h
0x180065d5b  pop     r15
0x180065d5d  pop     r14
0x180065d5f  pop     rdi
0x180065d60  pop     rsi
0x180065d61  pop     rbx
0x180065d62  pop     rbp
0x180065d63  retn
0x180065d64  mov     byte ptr [rbp+57h+var_90], r15b
0x180065d68  mov     rcx, [rbp+57h+var_88]
0x180065d6c  mov     rax, [rcx]
0x180065d6f  lea     rdx, [rbp+57h+var_90]
0x180065d73  mov     rax, [rax+38h]
0x180065d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d7c  mov     ebx, eax
0x180065d7e  test    eax, eax
0x180065d80  js      loc_180065EBC
0x180065d86  mov     edi, 1
0x180065d8b  cmp     byte ptr [rbp+57h+var_90], r15b
0x180065d8f  jnz     loc_1800C40A0
0x180065d95  mov     rbx, [rbp+57h+string]
0x180065d99  mov     rcx, rbx; string
0x180065d9c  call    cs:__imp_WindowsGetStringLen
0x180065da2  nop
0x180065da3  test    eax, eax
0x180065da5  jz      short loc_180065DE4
0x180065da7  mov     [rbp+57h+hasEmbedNull], r15d
0x180065dab  lea     rdx, [rbp+57h+hasEmbedNull]; hasEmbedNull
0x180065daf  mov     rcx, rbx; string
0x180065db2  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180065db8  cmp     [rbp+57h+hasEmbedNull], r15d
0x180065dbc  jnz     loc_180065EFC
0x180065dc2  xor     edx, edx; length
0x180065dc4  mov     rcx, rbx; string
0x180065dc7  call    cs:__imp_WindowsGetStringRawBuffer
0x180065dcd  xor     r9d, r9d
0x180065dd0  mov     r8, rax
0x180065dd3  lea     rdx, aLanguage; "Language"
0x180065dda  mov     rcx, [r14+58h]
0x180065dde  call    ?UpdateQualifierIfChanged@CQualifierEvent@Core@Resources@ApplicationModel@Windows@@QEAAJPEBG0W4_SetQualifierFlags@Runtime@3Microsoft@@@Z; Windows::ApplicationModel::Resources::Core::CQualifierEvent::UpdateQualifierIfChanged(ushort const *,ushort const *,Microsoft::Resources::Runtime::_SetQualifierFlags)
0x180065de3  nop
0x180065de4  mov     rcx, [rbp+57h+var_88]
0x180065de8  test    rcx, rcx
0x180065deb  jz      short loc_180065DFE
0x180065ded  mov     [rbp+57h+var_88], r15
0x180065df1  mov     rax, [rcx]
0x180065df4  mov     rax, [rax+10h]
0x180065df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065dfd  nop
0x180065dfe  mov     rcx, [rbp+57h+var_80]
0x180065e02  test    rcx, rcx
0x180065e05  jz      short loc_180065E18
0x180065e07  mov     [rbp+57h+var_80], r15
0x180065e0b  mov     rax, [rcx]
0x180065e0e  mov     rax, [rax+10h]
0x180065e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e17  nop
0x180065e18  mov     rax, [rsi]
0x180065e1b  mov     rcx, rsi
0x180065e1e  mov     rax, [rax+10h]
0x180065e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e27  nop
0x180065e28  test    rbx, rbx
0x180065e2b  jz      short loc_180065E37
0x180065e2d  mov     rcx, rbx; string
0x180065e30  call    cs:__imp_WindowsDeleteString
0x180065e36  nop
0x180065e37  xor     eax, eax
0x180065e39  jmp     loc_180065D48
0x180065e3e  movups  xmm0, xmmword ptr cs:aLanguages; "languages"
0x180065e45  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180065e49  mov     eax, dword ptr cs:aLanguages+10h; "s"
0x180065e4f  mov     dword ptr [rbp+57h+hstringHeader.Reserved+10h], eax
0x180065e52  lea     r8, [rbp+57h+hstringHeader]
0x180065e56  mov     edx, 9
0x180065e5b  mov     ebx, 80070057h
0x180065e60  mov     ecx, ebx
0x180065e62  call    cs:__imp_RoOriginateErrorW
0x180065e68  mov     rcx, [rbp+5Fh]; this
0x180065e6c  mov     r9d, ebx; char *
0x180065e6f  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180065e76  mov     edx, 153h; void *
0x180065e7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065e80  jmp     loc_180065D46
0x180065e85  mov     rcx, [rbp+5Fh]; this
0x180065e89  mov     r9d, eax; char *
0x180065e8c  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180065e93  mov     edx, 159h; void *
0x180065e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065e9d  lea     rcx, [rbp+57h+var_80]
0x180065ea1  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180065ea6  nop
0x180065ea7  mov     rax, [rsi]
0x180065eaa  mov     rcx, rsi
0x180065ead  mov     rax, [rax+10h]
0x180065eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065eb6  nop
0x180065eb7  jmp     loc_1800C4276
0x180065ebc  mov     rcx, [rbp+5Fh]; this
0x180065ec0  mov     r9d, eax; char *
0x180065ec3  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180065eca  mov     edx, 15Fh; void *
0x180065ecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065ed4  lea     rcx, [rbp+57h+var_88]
0x180065ed8  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180065edd  lea     rcx, [rbp+57h+var_80]
0x180065ee1  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180065ee6  nop
0x180065ee7  mov     rax, [rsi]
0x180065eea  mov     rcx, rsi
0x180065eed  mov     rax, [rax+10h]
0x180065ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ef6  nop
0x180065ef7  jmp     loc_1800C4276
0x180065efc  mov     rcx, [rbp+5Fh]; this
0x180065f00  mov     ebx, 80070057h
0x180065f05  mov     r9d, ebx; char *
0x180065f08  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180065f0f  mov     edx, 171h; void *
0x180065f14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065f19  lea     rcx, [rbp+57h+var_88]
0x180065f1d  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180065f22  lea     rcx, [rbp+57h+var_80]
0x180065f26  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180065f2b  nop
0x180065f2c  mov     rax, [rsi]
0x180065f2f  mov     rcx, rsi
0x180065f32  mov     rax, [rax+10h]
0x180065f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f3b  nop
0x180065f3c  jmp     loc_1800C4276
0x1800c40a0  mov     [rbp+57h+var_78], r15
0x1800c40a4  mov     rcx, [rbp+57h+var_88]
0x1800c40a8  mov     rax, [rcx]
0x1800c40ab  lea     rdx, [rbp+57h+var_78]
0x1800c40af  mov     rax, [rax+30h]
0x1800c40b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c40b8  mov     ebx, eax
0x1800c40ba  test    eax, eax
0x1800c40bc  js      loc_1800C4232
0x1800c40c2  lea     r8, [rbp+57h+string]; struct Windows::Internal::String *
0x1800c40c6  lea     rdx, [rbp+57h+var_78]; struct Windows::Internal::String *
0x1800c40ca  lea     rcx, [rbp+57h+string]; this
0x1800c40ce  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800c40d3  mov     ebx, eax
0x1800c40d5  test    eax, eax
0x1800c40d7  js      loc_1800C41EC
0x1800c40dd  mov     rcx, [rbp+57h+var_88]
0x1800c40e1  mov     rax, [rcx]
0x1800c40e4  lea     rdx, [rbp+57h+var_90]
0x1800c40e8  mov     rax, [rax+40h]
0x1800c40ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c40f1  mov     ebx, eax
0x1800c40f3  test    eax, eax
0x1800c40f5  js      loc_1800C41A3
0x1800c40fb  cmp     byte ptr [rbp+57h+var_90], r15b
0x1800c40ff  jz      loc_1800C4194
0x1800c4105  lea     r9, [rbp+57h+hstringHeader]; string
0x1800c4109  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x1800c410d  mov     edx, edi; length
0x1800c410f  lea     rcx, asc_1800E6F9C; ";"
0x1800c4116  call    cs:__imp_WindowsCreateStringReference
0x1800c411c  test    eax, eax
0x1800c411e  jns     short loc_1800C4134
0x1800c4120  xor     r9d, r9d; lpArguments
0x1800c4123  xor     r8d, r8d; nNumberOfArguments
0x1800c4126  mov     edx, edi; dwExceptionFlags
0x1800c4128  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c412d  call    cs:__imp_RaiseException
0x1800c4133  nop
0x1800c4134  lea     r8, [rbp+57h+string]; struct Windows::Internal::String *
0x1800c4138  lea     rdx, [rbp+57h+hstringHeader]; struct Windows::Internal::String *
0x1800c413c  lea     rcx, [rbp+57h+string]; this
0x1800c4140  call    ?Concat@String@Internal@Windows@@QEBAJAEBV123@PEAV123@@Z; Windows::Internal::String::Concat(Windows::Internal::String const &,Windows::Internal::String *)
0x1800c4145  mov     ebx, eax
0x1800c4147  test    eax, eax
0x1800c4149  jns     short loc_1800C4194
0x1800c414b  mov     rcx, [rbp+5Fh]; this
0x1800c414f  mov     r9d, eax; char *
0x1800c4152  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800c4159  mov     edx, 16Ah; void *
0x1800c415e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4163  lea     rcx, [rbp+57h+var_78]; this
0x1800c4167  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c416c  lea     rcx, [rbp+57h+var_88]
0x1800c4170  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800c4175  lea     rcx, [rbp+57h+var_80]
0x1800c4179  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800c417e  nop
0x1800c417f  mov     rax, [rsi]
0x1800c4182  mov     rcx, rsi
0x1800c4185  mov     rax, [rax+10h]
0x1800c4189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c418e  nop
0x1800c418f  jmp     loc_1800C4276
0x1800c4194  lea     rcx, [rbp+57h+var_78]; this
0x1800c4198  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c419d  nop
0x1800c419e  jmp     loc_180065D8B
0x1800c41a3  mov     rcx, [rbp+5Fh]; this
0x1800c41a7  mov     r9d, eax; char *
0x1800c41aa  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800c41b1  mov     edx, 167h; void *
0x1800c41b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c41bb  lea     rcx, [rbp+57h+var_78]; this
0x1800c41bf  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c41c4  lea     rcx, [rbp+57h+var_88]
0x1800c41c8  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800c41cd  lea     rcx, [rbp+57h+var_80]
0x1800c41d1  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800c41d6  nop
0x1800c41d7  mov     rax, [rsi]
0x1800c41da  mov     rcx, rsi
0x1800c41dd  mov     rax, [rax+10h]
0x1800c41e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c41e6  nop
0x1800c41e7  jmp     loc_1800C4276
0x1800c41ec  mov     rcx, [rbp+5Fh]; this
0x1800c41f0  mov     r9d, eax; char *
0x1800c41f3  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800c41fa  mov     edx, 165h; void *
  ... truncated ...
```
