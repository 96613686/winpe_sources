# Windows::Internal::Spelling::RoamingDictionary::get_RoamingState(Windows::Internal::Spelling::RoamingState *)

- ea: `0x180047480`
- end: `0x180047721`
- name: `?get_RoamingState@RoamingDictionary@Spelling@Internal@Windows@@UEAAJPEAW4RoamingState@234@@Z`
- size: `673`
- prototype: `__int64 __fastcall(Windows::Internal::Spelling::RoamingDictionary *__hidden this, enum Windows::Internal::Spelling::RoamingState *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001ee7c`
- `0x1800202e4`
- `0x1800383c4`
- `0x180040cc4`
- `0x1800425a8`
- `0x1800431c0`
- `0x180047480`
- `0x180047728`
- `0x180047b18`
- `0x180047c78`
- `0x180061320`
- `0x180070530`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004769d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004769d`

## string_xrefs

- `0x1800474b8`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x1800474e0`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x18004753e`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x1800475b4`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x18004761b`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180047685`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Internal::Spelling::RoamingDictionary::get_RoamingState(
        Windows::Internal::Spelling::RoamingDictionary *this,
        enum Windows::Internal::Spelling::RoamingState *a2)
{
  int v4; // eax
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, int *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, int *); // rbx
  int v12; // eax
  __int64 (__fastcall *v13)(Windows::Internal::Spelling::RoamingDictionary *, HSTRING *); // rbx
  int v14; // eax
  WCHAR *StringRawBuffer; // rax
  unsigned __int64 FileSizeFromName; // rbx
  int v18; // [rsp+20h] [rbp-78h]
  int v19; // [rsp+30h] [rbp-68h] BYREF
  int v20; // [rsp+34h] [rbp-64h] BYREF
  __int64 v21; // [rsp+38h] [rbp-60h] BYREF
  HSTRING string; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v23; // [rsp+48h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-48h] BYREF
  __int64 v25; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
      (const char *)0x80070057LL,
      v18);
  v4 = Windows::Internal::Spelling::RoamingDictionary::EnsureInitialized(this);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
      (const char *)(unsigned int)v4,
      v18);
  *(_DWORD *)a2 = 0;
  wil::GetActivationFactory<Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicyFactory>((const WCHAR *)&v23);
  v21 = 0;
  v5 = *v23;
  v21 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 *))(v5 + 48))(v23, 0, 0, &v21);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
      (const char *)(unsigned int)v6,
      v18);
  v20 = 0;
  v19 = 0;
  v7 = v21;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v21 + 64LL);
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Microsoft", 0xAu, 9u);
  v9 = v8(v7, v25, &v20);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
      (const char *)(unsigned int)v9,
      v18);
  v10 = v21;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v21 + 64LL);
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Microsoft.Language", 0x13u, 0x12u);
  v12 = v11(v10, v25, &v19);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
      (const char *)(unsigned int)v12,
      v18);
  if ( v20 || v19 )
    *(_DWORD *)a2 = 1;
  if ( !*(_DWORD *)a2 )
  {
    string = 0;
    v13 = *(__int64 (__fastcall **)(Windows::Internal::Spelling::RoamingDictionary *, HSTRING *))(*(_QWORD *)this + 48LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v14 = v13(this, &string);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCF,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
        (const char *)(unsigned int)v14,
        v18);
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring((char **)&hstringHeader, StringRawBuffer);
    FileSizeFromName = Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(&hstringHeader);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    if ( FileSizeFromName >= 0x100000 )
      *(_DWORD *)a2 = 2;
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  return 0;
}

```

## disassembly

```asm
0x180047480  mov     [rsp+arg_10], rbx
0x180047485  push    rsi
0x180047486  push    rdi
0x180047487  push    r14
0x180047489  sub     rsp, 80h
0x180047490  mov     rax, cs:__security_cookie
0x180047497  xor     rax, rsp
0x18004749a  mov     [rsp+98h+var_28], rax
0x18004749f  mov     rsi, rdx
0x1800474a2  mov     r14, rcx
0x1800474a5  mov     rcx, [rsp+98h]; this
0x1800474ad  test    rdx, rdx
0x1800474b0  jnz     short loc_1800474C9
0x1800474b2  mov     r9d, 80070057h; char *
0x1800474b8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800474bf  mov     edx, 0B1h; void *
0x1800474c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800474c9  mov     rcx, r14; this
0x1800474cc  call    ?EnsureInitialized@RoamingDictionary@Spelling@Internal@Windows@@AEAAJXZ; Windows::Internal::Spelling::RoamingDictionary::EnsureInitialized(void)
0x1800474d1  mov     rcx, [rsp+98h]; this
0x1800474d9  test    eax, eax
0x1800474db  jns     short loc_1800474F1
0x1800474dd  mov     r9d, eax; char *
0x1800474e0  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800474e7  mov     edx, 0B2h; void *
0x1800474ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800474f1  mov     dword ptr [rsi], 0
0x1800474f7  lea     rcx, [rsp+98h+var_50]
0x1800474fc  call    ??$GetActivationFactory@UICloudStorePolicyFactory@Policy@Cloud@Storage@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UICloudStorePolicyFactory@Policy@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicyFactory>(ushort const *)
0x180047501  nop
0x180047502  mov     [rsp+98h+var_60], 0
0x18004750b  mov     rcx, [rsp+98h+var_50]
0x180047510  mov     rax, [rcx]
0x180047513  mov     [rsp+98h+var_60], 0
0x18004751c  lea     r9, [rsp+98h+var_60]
0x180047521  xor     r8d, r8d
0x180047524  xor     edx, edx
0x180047526  mov     rax, [rax+30h]
0x18004752a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004752f  mov     rcx, [rsp+98h]; this
0x180047537  test    eax, eax
0x180047539  jns     short loc_18004754F
0x18004753b  mov     r9d, eax; char *
0x18004753e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180047545  mov     edx, 0BFh; void *
0x18004754a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004754f  mov     [rsp+98h+var_64], 0
0x180047557  mov     [rsp+98h+var_68], 0
0x18004755f  mov     rdi, [rsp+98h+var_60]
0x180047564  mov     rax, [rdi]
0x180047567  mov     rbx, [rax+40h]
0x18004756b  mov     [rsp+98h+var_30], 0
0x180047574  mov     r9d, 9; unsigned int
0x18004757a  lea     r8d, [r9+1]; unsigned int
0x18004757e  lea     rdx, aMicrosoft; "Microsoft"
0x180047585  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x18004758a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004758f  nop
0x180047590  lea     r8, [rsp+98h+var_64]
0x180047595  mov     rdx, [rsp+98h+var_30]
0x18004759a  mov     rcx, rdi
0x18004759d  mov     rax, rbx
0x1800475a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475a5  mov     rcx, [rsp+98h]; this
0x1800475ad  test    eax, eax
0x1800475af  jns     short loc_1800475C6
0x1800475b1  mov     r9d, eax; char *
0x1800475b4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800475bb  mov     edx, 0C4h; void *
0x1800475c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800475c6  mov     rdi, [rsp+98h+var_60]
0x1800475cb  mov     rax, [rdi]
0x1800475ce  mov     rbx, [rax+40h]
0x1800475d2  mov     [rsp+98h+var_30], 0
0x1800475db  mov     r9d, 12h; unsigned int
0x1800475e1  lea     r8d, [r9+1]; unsigned int
0x1800475e5  lea     rdx, aMicrosoftLangu; "Microsoft.Language"
0x1800475ec  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x1800475f1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800475f6  nop
0x1800475f7  lea     r8, [rsp+98h+var_68]
0x1800475fc  mov     rdx, [rsp+98h+var_30]
0x180047601  mov     rcx, rdi
0x180047604  mov     rax, rbx
0x180047607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004760c  mov     rcx, [rsp+98h]; this
0x180047614  test    eax, eax
0x180047616  jns     short loc_18004762D
0x180047618  mov     r9d, eax; char *
0x18004761b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180047622  mov     edx, 0C5h; void *
0x180047627  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004762d  cmp     [rsp+98h+var_64], 0
0x180047632  jnz     short loc_18004763B
0x180047634  cmp     [rsp+98h+var_68], 0
0x180047639  jz      short loc_180047641
0x18004763b  mov     dword ptr [rsi], 1
0x180047641  cmp     dword ptr [rsi], 0
0x180047644  jnz     loc_1800476E2
0x18004764a  mov     [rsp+98h+string], 0
0x180047653  mov     rax, [r14]
0x180047656  mov     rbx, [rax+30h]
0x18004765a  xor     edx, edx
0x18004765c  lea     rcx, [rsp+98h+string]
0x180047661  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180047666  lea     rdx, [rsp+98h+string]
0x18004766b  mov     rcx, r14
0x18004766e  mov     rax, rbx
0x180047671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047676  mov     rcx, [rsp+98h]; this
0x18004767e  test    eax, eax
0x180047680  jns     short loc_180047696
0x180047682  mov     r9d, eax; char *
0x180047685  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x18004768c  mov     edx, 0CFh; void *
0x180047691  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180047696  xor     edx, edx; length
0x180047698  mov     rcx, [rsp+98h+string]; string
0x18004769d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800476a3  mov     rdx, rax
0x1800476a6  lea     rcx, [rsp+98h+hstringHeader]
0x1800476ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800476b0  nop
0x1800476b1  lea     rcx, [rsp+98h+hstringHeader]
0x1800476b6  call    ?GetFileSizeFromName@UserDictionaries@Spelling@Globalization@Windows@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(std::wstring const &)
0x1800476bb  mov     rbx, rax
0x1800476be  lea     rcx, [rsp+98h+hstringHeader]
0x1800476c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800476c8  cmp     rbx, 100000h
0x1800476cf  jb      short loc_1800476D7
0x1800476d1  mov     dword ptr [rsi], 2
0x1800476d7  lea     rcx, [rsp+98h+string]; this
0x1800476dc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800476e1  nop
0x1800476e2  lea     rcx, [rsp+98h+var_60]
0x1800476e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800476ec  nop
0x1800476ed  lea     rcx, [rsp+98h+var_50]
0x1800476f2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800476f7  xor     eax, eax
0x1800476f9  jmp     short loc_1800476FF
0x1800476fb  mov     eax, [rsp+98h+var_68]
0x1800476ff  mov     rcx, [rsp+98h+var_28]
0x180047704  xor     rcx, rsp; StackCookie
0x180047707  call    __security_check_cookie
0x18004770c  mov     rbx, [rsp+98h+arg_10]
0x180047714  add     rsp, 80h
0x18004771b  pop     r14
0x18004771d  pop     rdi
0x18004771e  pop     rsi
0x18004771f  retn
```
