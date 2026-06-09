# Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180042720`
- end: `0x18004289f`
- name: `?GetPackageFullNameFromFamilyNameAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z`
- size: `383`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fe74`
- `0x180041a88`
- `0x18005b050`
- `0x18006ae88`
- `0x180077aec`
- `0x18007b890`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001f5f4`
- `0x18002392c`
- `0x180029408`
- `0x18003e588`
- `0x18003f62c`
- `0x18003f6e4`
- `0x180042720`
- `0x1800430e8`
- `0x180045f78`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042785`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800427eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800427eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042836`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042836`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // r14
  __int64 v6; // rbx
  int ActivationFactory; // eax
  __int64 v8; // rbx
  __int64 SrUserFromSid; // rax
  __int64 v10; // rsi
  void (__fastcall *v11)(__int64, __int64, HSTRING, HSTRING *); // rdi
  const unsigned __int16 *v12; // rax
  PCWSTR StringRawBuffer; // rdx
  int v15; // [rsp+20h] [rbp-98h]
  HSTRING string; // [rsp+30h] [rbp-88h] BYREF
  __int64 v17; // [rsp+38h] [rbp-80h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v19[8]; // [rsp+50h] [rbp-68h] BYREF
  __int64 v20; // [rsp+58h] [rbp-60h]
  HSTRING v21[4]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v5 = a1;
  v20 = a1;
  v17 = 0;
  v6 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                    v21,
                    L"Windows.Internal.StateRepository.PackageUser");
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6, &v17);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v15);
  v8 = 0;
  v18[0] = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    SrUserFromSid = Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(v19, a2);
    Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(v18, SrUserFromSid);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v19);
    v8 = v18[0];
  }
  string = 0;
  v10 = v17;
  v11 = *(void (__fastcall **)(__int64, __int64, HSTRING, HSTRING *))(*(_QWORD *)v17 + 312LL);
  WindowsDeleteString(0);
  string = 0;
  v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v21, v12);
  try
  {
    v11(v10, v8, v21[0], &string);
  }
  catch ( ... )
  {
    v5 = v20;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v5, StringRawBuffer);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  return v5;
}

```

## disassembly

```asm
0x180042720  push    rbx
0x180042722  push    rsi
0x180042723  push    rdi
0x180042724  push    r14
0x180042726  push    r15
0x180042728  sub     rsp, 90h
0x18004272f  mov     rax, cs:__security_cookie
0x180042736  xor     rax, rsp
0x180042739  mov     [rsp+0B8h+var_38], rax
0x180042741  mov     r15, r8
0x180042744  mov     rdi, rdx
0x180042747  mov     r14, rcx
0x18004274a  mov     [rsp+0B8h+var_60], rcx
0x18004274f  mov     [rsp+0B8h+var_80], 0
0x180042758  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUser@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18004275f  lea     rcx, [rsp+0B8h+var_58]; string
0x180042764  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x180042769  mov     rbx, [rax]
0x18004276c  lea     rcx, [rsp+0B8h+var_80]
0x180042771  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042776  lea     r8, [rsp+0B8h+var_80]
0x18004277b  lea     rdx, _GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6
0x180042782  mov     rcx, rbx
0x180042785  call    cs:__imp_RoGetActivationFactory
0x18004278b  mov     rcx, [rsp+0B8h]; this
0x180042793  test    eax, eax
0x180042795  js      loc_18004288A
0x18004279b  xor     ebx, ebx
0x18004279d  mov     [rsp+0B8h+var_78], rbx
0x1800427a2  cmp     [rdi+10h], rbx
0x1800427a6  jz      short loc_1800427D1
0x1800427a8  mov     rdx, rdi
0x1800427ab  lea     rcx, [rsp+0B8h+var_68]
0x1800427b0  call    ?GetSrUserFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(std::wstring const &)
0x1800427b5  mov     rdx, rax
0x1800427b8  lea     rcx, [rsp+0B8h+var_78]
0x1800427bd  call    ??4?$ComPtr@UIHandlerCustomConsent@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IHandlerCustomConsent>::operator=(Microsoft::WRL::ComPtr<IHandlerCustomConsent> &&)
0x1800427c2  lea     rcx, [rsp+0B8h+var_68]
0x1800427c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800427cc  mov     rbx, [rsp+0B8h+var_78]
0x1800427d1  mov     [rsp+0B8h+string], 0
0x1800427da  mov     rsi, [rsp+0B8h+var_80]
0x1800427df  mov     rax, [rsi]
0x1800427e2  mov     rdi, [rax+138h]
0x1800427e9  xor     ecx, ecx; string
0x1800427eb  call    cs:__imp_WindowsDeleteString
0x1800427f1  mov     [rsp+0B8h+string], 0
0x1800427fa  mov     rcx, r15
0x1800427fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042802  mov     rdx, rax; unsigned __int16 *
0x180042805  lea     rcx, [rsp+0B8h+var_58]; this
0x18004280a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004280f  lea     r9, [rsp+0B8h+string]
0x180042814  mov     r8, [rsp+0B8h+var_58]
0x180042819  mov     rdx, rbx
0x18004281c  mov     rcx, rsi
0x18004281f  mov     rax, rdi
0x180042822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042827  nop
0x180042828  jmp     short loc_18004282F
0x18004282a  mov     r14, [rsp+0B8h+var_60]
0x18004282f  xor     edx, edx; length
0x180042831  mov     rcx, [rsp+0B8h+string]; string
0x180042836  call    cs:__imp_WindowsGetStringRawBuffer
0x18004283c  mov     rdx, rax
0x18004283f  mov     rcx, r14
0x180042842  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042847  nop
0x180042848  lea     rcx, [rsp+0B8h+string]; this
0x18004284d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180042852  nop
0x180042853  lea     rcx, [rsp+0B8h+var_78]
0x180042858  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004285d  nop
0x18004285e  lea     rcx, [rsp+0B8h+var_80]
0x180042863  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042868  mov     rax, r14
0x18004286b  mov     rcx, [rsp+0B8h+var_38]
0x180042873  xor     rcx, rsp; StackCookie
0x180042876  call    __security_check_cookie
0x18004287b  add     rsp, 90h
0x180042882  pop     r15
0x180042884  pop     r14
0x180042886  pop     rdi
0x180042887  pop     rsi
0x180042888  pop     rbx
0x180042889  retn
0x18004288a  mov     r9d, eax; char *
0x18004288d  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042894  mov     edx, 27Dh; void *
0x180042899  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
