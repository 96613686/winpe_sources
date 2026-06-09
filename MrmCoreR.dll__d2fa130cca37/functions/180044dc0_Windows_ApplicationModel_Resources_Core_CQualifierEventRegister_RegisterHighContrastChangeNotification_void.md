# Windows::ApplicationModel::Resources::Core::CQualifierEventRegister::RegisterHighContrastChangeNotification(void)

- ea: `0x180044dc0`
- end: `0x1800450b0`
- name: `?RegisterHighContrastChangeNotification@CQualifierEventRegister@Core@Resources@ApplicationModel@Windows@@QEAAJXZ`
- size: `752`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::Core::CQualifierEventRegister *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b7cc`
- `0x180044ce0`

## callees

- `0x180017960`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x180035110`
- `0x180044dc0`
- `0x18004555c`
- `0x180045638`
- `0x1800862f0`
- `0x1800867dc`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045071`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180045071`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e0f`

## string_xrefs

- `0x180045033`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`
- `0x180045098`: `onecoreuap\base\mrt\runtime\com\winrt\core\contextmanager.cpp`
- `0x180044e08`: `Windows.UI.ViewManagement.AccessibilitySettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CQualifierEventRegister::RegisterHighContrastChangeNotification(
        Windows::ApplicationModel::Resources::Core::CQualifierEventRegister *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  void *v5; // rax
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // rcx
  HSTRING *p_string; // rax
  __int64 v12; // rdx
  int Length; // eax
  __int64 v14; // r11
  __int64 v15; // rcx
  __int64 v16; // rax
  _WORD *v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  signed __int64 v20[2]; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( *((_BYTE *)this + 24) )
    return 0;
  if ( !*((_QWORD *)this + 1) )
  {
    v20[0] = 0;
    if ( WindowsCreateStringReference(
           L"Windows.UI.ViewManagement.AccessibilitySettings",
           0x2Fu,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v2 = Windows::Foundation::ActivateInstance<Windows::UI::ViewManagement::IAccessibilitySettings>(string, v20);
    v3 = v2;
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
        (const char *)(unsigned int)v2,
        v20[0]);
      return v3;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, v20[0], 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v20[0] + 16LL))(v20[0]);
  }
  if ( !*((_QWORD *)this + 1) )
    return 0;
  v20[0] = (signed __int64)this;
  v20[1] = (signed __int64)Windows::ApplicationModel::Resources::Core::CQualifierEventRegister::OnHighContrastChanged;
  v5 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
    v6 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::ViewManagement::AccessibilitySettings *,Windows::UI::ViewManagement::IAccessibilitySettings *>,IInspectable *>::*)(Windows::UI::ViewManagement::IAccessibilitySettings *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,_lambda_accb89ac4a9bb8ee501b31e5f36133e9_,-1,Windows::UI::ViewManagement::IAccessibilitySettings *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,_lambda_accb89ac4a9bb8ee501b31e5f36133e9_,-1,Windows::UI::ViewManagement::IAccessibilitySettings *,IInspectable *>(
           v5,
           v20);
  else
    v6 = 0;
  v20[0] = v6;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 1) + 64LL))(
         *((_QWORD *)this + 1),
         v6,
         (char *)this + 16);
  v8 = v7;
  if ( v7 >= 0 )
  {
    *((_BYTE *)this + 24) = 1;
    v9 = *((_QWORD *)this + 8);
    v10 = 60;
    p_string = &string;
    do
    {
      *(_BYTE *)p_string = 0;
      p_string = (HSTRING *)((char *)p_string + 1);
      --v10;
    }
    while ( v10 );
    if ( !*(_BYTE *)(v9 + 8) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x117,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
        (const char *)0x80070015LL,
        v20[0]);
      goto LABEL_23;
    }
    DefStringResult_InitBuf(&hstringHeader);
    string = (HSTRING)&hstringHeader;
    if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, HSTRING *))(**(_QWORD **)(v12 + 24) + 72LL))(
           *(_QWORD *)(v12 + 24),
           L"Contrast",
           &string) >= 0 )
    {
      v20[0] = 0;
      Length = DefStringResult_GetLength(string);
      if ( Length < 0 )
      {
        v18 = (unsigned int)Length;
        v19 = 296;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
          (const char *)v18,
          v20[0]);
        goto LABEL_41;
      }
      v15 = 30;
      if ( (unsigned __int64)(v20[0] + 1) <= 0x1E )
      {
        if ( v14 && (*(_QWORD *)v14 || !*(_DWORD *)(v14 + 8)) && (*(_DWORD *)(v14 + 8) || !*(_QWORD *)v14) )
        {
          v16 = 2147483646;
          v17 = *(_WORD **)(v14 + 16);
          do
          {
            if ( !v16 )
              break;
            if ( !*v17 )
              break;
            ++v17;
            --v16;
            --v15;
          }
          while ( v15 );
          v18 = v15 == 0 ? 0x8007007A : 0;
          if ( v15 )
            goto LABEL_41;
          v19 = 310;
        }
        else
        {
          v18 = 2147942487LL;
          v19 = 308;
        }
        goto LABEL_40;
      }
    }
LABEL_41:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&string);
LABEL_23:
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return 0;
  }
  if ( v7 != -2147023728 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\contextmanager.cpp",
      (const char *)(unsigned int)v7,
      v20[0]);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v8;
}

```

## disassembly

```asm
0x180044dc0  mov     [rsp-18h+arg_8], rbx
0x180044dc5  mov     [rsp-18h+arg_10], rsi
0x180044dca  push    rbp
0x180044dcb  push    rdi
0x180044dcc  push    r14
0x180044dce  mov     rbp, rsp
0x180044dd1  sub     rsp, 80h
0x180044dd8  mov     rax, cs:__security_cookie
0x180044ddf  xor     rax, rsp
0x180044de2  mov     [rbp+var_10], rax
0x180044de6  mov     rdi, rcx
0x180044de9  xor     r14d, r14d
0x180044dec  cmp     [rcx+18h], r14b
0x180044df0  jnz     short loc_180044E4C
0x180044df2  cmp     [rcx+8], r14
0x180044df6  jnz     short loc_180044E46
0x180044df8  mov     [rbp+var_60], r14
0x180044dfc  lea     r9, [rbp+string]; string
0x180044e00  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180044e04  lea     edx, [r14+2Fh]; length
0x180044e08  lea     rcx, ?RuntimeClass_Windows_UI_ViewManagement_AccessibilitySettings@@3QBGB; "Windows.UI.ViewManagement.Accessibility"...
0x180044e0f  call    cs:__imp_WindowsCreateStringReference
0x180044e15  test    eax, eax
0x180044e17  js      loc_180045062
0x180044e1d  lea     rdx, [rbp+var_60]
0x180044e21  mov     rcx, [rbp+string]
0x180044e25  call    ??$ActivateInstance@UIAccessibilitySettings@ViewManagement@UI@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAccessibilitySettings@ViewManagement@UI@1@@Z; Windows::Foundation::ActivateInstance<Windows::UI::ViewManagement::IAccessibilitySettings>(HSTRING__ *,Windows::UI::ViewManagement::IAccessibilitySettings * *)
0x180044e2a  mov     ebx, eax
0x180044e2c  test    eax, eax
0x180044e2e  js      loc_18004502C
0x180044e34  mov     rcx, [rbp+var_60]
0x180044e38  xor     eax, eax
0x180044e3a  lock cmpxchg [rdi+8], rcx
0x180044e40  jnz     loc_18004507C
0x180044e46  cmp     [rdi+8], r14
0x180044e4a  jnz     short loc_180044E72
0x180044e4c  xor     eax, eax
0x180044e4e  mov     rcx, [rbp+var_10]
0x180044e52  xor     rcx, rsp; StackCookie
0x180044e55  call    __security_check_cookie
0x180044e5a  lea     r11, [rsp+80h+var_s0]
0x180044e62  mov     rbx, [r11+28h]
0x180044e66  mov     rsi, [r11+30h]
0x180044e6a  mov     rsp, r11
0x180044e6d  pop     r14
0x180044e6f  pop     rdi
0x180044e70  pop     rbp
0x180044e71  retn
0x180044e72  mov     [rbp+var_60], rdi
0x180044e76  lea     rax, ?OnHighContrastChanged@CQualifierEventRegister@Core@Resources@ApplicationModel@Windows@@QEAAJPEAUIAccessibilitySettings@ViewManagement@UI@5@PEAUIInspectable@@@Z; Windows::ApplicationModel::Resources::Core::CQualifierEventRegister::OnHighContrastChanged(Windows::UI::ViewManagement::IAccessibilitySettings *,IInspectable *)
0x180044e7d  mov     [rbp+var_58], rax
0x180044e81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044e88  mov     ecx, 20h ; ' '; unsigned __int64
0x180044e8d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044e92  test    rax, rax
0x180044e95  jz      short loc_180044EEE
0x180044e97  lea     rdx, [rbp+var_60]
0x180044e9b  mov     rcx, rax
0x180044e9e  call    ??0?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@V_lambda_accb89ac4a9bb8ee501b31e5f36133e9_@@$0?0PEAUIAccessibilitySettings@ViewManagement@UI@3@PEAUIInspectable@@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIAccessibilitySettings@234@@Internal@Foundation@Windows@@PEAUIInspectable@@@Foundation@Windows@@EAAJPEAUIAccessibilitySettings@ViewManagement@UI@3@PEAUIInspectable@@@Z@Details@WRL@Microsoft@@QEAA@$$QEAV_lambda_accb89ac4a9bb8ee501b31e5f36133e9_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::ViewManagement::AccessibilitySettings *,Windows::UI::ViewManagement::IAccessibilitySettings *>,IInspectable *>::*)(Windows::UI::ViewManagement::IAccessibilitySettings *,IInspectable *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,_lambda_accb89ac4a9bb8ee501b31e5f36133e9_,-1,Windows::UI::ViewManagement::IAccessibilitySettings *,IInspectable *>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,_lambda_accb89ac4a9bb8ee501b31e5f36133e9_,-1,Windows::UI::ViewManagement::IAccessibilitySettings *,IInspectable *>(_lambda_accb89ac4a9bb8ee501b31e5f36133e9_ &&)
0x180044ea3  mov     rbx, rax
0x180044ea6  mov     [rbp+var_60], rbx
0x180044eaa  mov     rcx, [rdi+8]
0x180044eae  mov     rax, [rcx]
0x180044eb1  lea     r8, [rdi+10h]
0x180044eb5  mov     rdx, rbx
0x180044eb8  mov     rax, [rax+40h]
0x180044ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ec1  mov     esi, eax
0x180044ec3  test    eax, eax
0x180044ec5  jns     short loc_180044EF3
0x180044ec7  cmp     eax, 80070490h
0x180044ecc  jnz     loc_180045091
0x180044ed2  test    rbx, rbx
0x180044ed5  jz      short loc_180044EE7
0x180044ed7  mov     rax, [rbx]
0x180044eda  mov     rcx, rbx
0x180044edd  mov     rax, [rax+10h]
0x180044ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ee6  nop
0x180044ee7  mov     eax, esi
0x180044ee9  jmp     loc_180044E4E
0x180044eee  mov     rbx, r14
0x180044ef1  jmp     short loc_180044EA6
0x180044ef3  mov     byte ptr [rdi+18h], 1
0x180044ef7  mov     rdx, [rdi+40h]
0x180044efb  mov     ecx, 3Ch ; '<'
0x180044f00  lea     rax, [rbp+string]
0x180044f04  mov     [rax], r14b
0x180044f07  inc     rax
0x180044f0a  sub     rcx, 1
0x180044f0e  jnz     short loc_180044F04
0x180044f10  cmp     [rdx+8], r14b
0x180044f14  jnz     short loc_180044F4C
0x180044f16  mov     rcx, [rbp+18h]; this
0x180044f1a  mov     r9d, 80070015h; char *
0x180044f20  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\mrt\\runtime\\src\\cc"...
0x180044f27  mov     edx, 117h; void *
0x180044f2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044f31  nop
0x180044f32  test    rbx, rbx
0x180044f35  jz      short loc_180044F47
0x180044f37  mov     rax, [rbx]
0x180044f3a  mov     rcx, rbx
0x180044f3d  mov     rax, [rax+10h]
0x180044f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f46  nop
0x180044f47  jmp     loc_180044E4C
0x180044f4c  lea     rcx, [rbp+hstringHeader]
0x180044f50  call    DefStringResult_InitBuf
0x180044f55  lea     rcx, [rbp+hstringHeader]
0x180044f59  mov     [rbp+string], rcx
0x180044f5d  mov     rcx, [rdx+18h]
0x180044f61  mov     rax, [rcx]
0x180044f64  lea     r8, [rbp+string]
0x180044f68  lea     rdx, aContrast_0; "Contrast"
0x180044f6f  mov     rax, [rax+48h]
0x180044f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f78  test    eax, eax
0x180044f7a  js      loc_18004501E
0x180044f80  mov     [rbp+var_60], r14
0x180044f84  lea     rdx, [rbp+var_60]
0x180044f88  mov     r11, [rbp+string]
0x180044f8c  mov     rcx, r11
0x180044f8f  call    DefStringResult_GetLength
0x180044f94  test    eax, eax
0x180044f96  js      loc_180045058
0x180044f9c  mov     rax, [rbp+var_60]
0x180044fa0  inc     rax
0x180044fa3  mov     ecx, 1Eh
0x180044fa8  cmp     rax, rcx
0x180044fab  ja      short loc_18004501E
0x180044fad  test    r11, r11
0x180044fb0  jz      loc_18004504B
0x180044fb6  cmp     [r11], r14
0x180044fb9  jnz     short loc_180044FC5
0x180044fbb  cmp     [r11+8], r14d
0x180044fbf  ja      loc_18004504B
0x180044fc5  cmp     [r11+8], r14d
0x180044fc9  jnz     short loc_180044FD0
0x180044fcb  cmp     [r11], r14
0x180044fce  jnz     short loc_18004504B
0x180044fd0  mov     eax, 7FFFFFFEh
0x180044fd5  mov     rdx, [r11+10h]
0x180044fd9  test    rax, rax
0x180044fdc  jz      short loc_180044FF1
0x180044fde  cmp     [rdx], r14w
0x180044fe2  jz      short loc_180044FF1
0x180044fe4  add     rdx, 2
0x180044fe8  dec     rax
0x180044feb  sub     rcx, 1
0x180044fef  jnz     short loc_180044FD9
0x180044ff1  mov     rax, rcx
0x180044ff4  neg     rax
0x180044ff7  sbb     r9d, r9d
0x180044ffa  not     r9d
0x180044ffd  and     r9d, 8007007Ah; char *
0x180045004  test    rcx, rcx
0x180045007  jnz     short loc_18004501E
0x180045009  mov     edx, 136h; void *
0x18004500e  mov     rcx, [rbp+18h]; this
0x180045012  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\mrt\\runtime\\src\\cc"...
0x180045019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004501e  lea     rcx, [rbp+string]; this
0x180045022  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180045027  jmp     loc_180044F32
0x18004502c  mov     rcx, [rbp+18h]; this
0x180045030  mov     r9d, ebx; char *
0x180045033  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18004503a  mov     edx, 0EDh; void *
0x18004503f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045044  mov     eax, ebx
0x180045046  jmp     loc_180044E4E
0x18004504b  mov     r9d, 80070057h
0x180045051  mov     edx, 134h
0x180045056  jmp     short loc_18004500E
0x180045058  mov     r9d, eax
0x18004505b  mov     edx, 128h
0x180045060  jmp     short loc_18004500E
0x180045062  xor     r9d, r9d; lpArguments
0x180045065  xor     r8d, r8d; nNumberOfArguments
0x180045068  lea     edx, [r9+1]; dwExceptionFlags
0x18004506c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180045071  call    cs:__imp_RaiseException
0x180045077  jmp     loc_180044E1D
0x18004507c  mov     rcx, [rbp+var_60]
0x180045080  mov     rax, [rcx]
0x180045083  mov     rax, [rax+10h]
0x180045087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004508c  jmp     loc_180044E46
0x180045091  mov     rcx, [rbp+18h]; this
0x180045095  mov     r9d, esi; char *
0x180045098  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18004509f  mov     edx, 0FBh; void *
0x1800450a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800450a9  nop
0x1800450aa  jmp     loc_180044ED2
```
