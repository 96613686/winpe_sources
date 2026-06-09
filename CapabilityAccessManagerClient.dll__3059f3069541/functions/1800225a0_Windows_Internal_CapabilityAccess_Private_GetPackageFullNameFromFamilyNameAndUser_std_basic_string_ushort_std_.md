# Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800225a0`
- end: `0x18002271f`
- name: `?GetPackageFullNameFromFamilyNameAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002e5e4`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000c6c8`
- `0x1800142f8`
- `0x18001b218`
- `0x18001b444`
- `0x18001b5ac`
- `0x18002056c`
- `0x1800215f4`
- `0x1800225a0`
- `0x180022a4c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002266b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002266b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800226b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800226b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022605`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022605`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // r14
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  __int64 v8; // rbx
  _QWORD *SrUserFromSid; // rax
  __int64 v10; // rsi
  void (__fastcall *v11)(__int64, __int64, HSTRING, HSTRING *); // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  const unsigned __int16 *v15; // rax
  PCWSTR StringRawBuffer; // rdx
  int v18; // [rsp+20h] [rbp-98h]
  HSTRING string; // [rsp+30h] [rbp-88h] BYREF
  __int64 v20; // [rsp+38h] [rbp-80h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+50h] [rbp-68h] BYREF
  __int64 v23; // [rsp+58h] [rbp-60h]
  HSTRING v24[4]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v5 = a1;
  v23 = a1;
  v20 = 0;
  v6 = *Windows::Internal::StringReference::StringReference(v24, L"Windows.Internal.StateRepository.PackageUser");
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6, &v20);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
  v8 = 0;
  v21[0] = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    SrUserFromSid = Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(&v22, a2);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser>::operator=(v21, SrUserFromSid);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    v8 = v21[0];
  }
  string = 0;
  v10 = v20;
  v11 = *(void (__fastcall **)(__int64, __int64, HSTRING, HSTRING *))(*(_QWORD *)v20 + 312LL);
  WindowsDeleteString(0);
  string = 0;
  v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v12, v13, v14);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v24, v15);
  try
  {
    v11(v10, v8, v24[0], &string);
  }
  catch ( ... )
  {
    v5 = v23;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v5, (__int64)StringRawBuffer);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v21);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  return v5;
}

```

## disassembly

```asm
0x1800225a0  push    rbx
0x1800225a2  push    rsi
0x1800225a3  push    rdi
0x1800225a4  push    r14
0x1800225a6  push    r15
0x1800225a8  sub     rsp, 90h
0x1800225af  mov     rax, cs:__security_cookie
0x1800225b6  xor     rax, rsp
0x1800225b9  mov     [rsp+0B8h+var_38], rax
0x1800225c1  mov     r15, r8
0x1800225c4  mov     rdi, rdx
0x1800225c7  mov     r14, rcx
0x1800225ca  mov     [rsp+0B8h+var_60], rcx
0x1800225cf  mov     [rsp+0B8h+var_80], 0
0x1800225d8  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUser@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800225df  lea     rcx, [rsp+0B8h+var_58]; string
0x1800225e4  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800225e9  mov     rbx, [rax]
0x1800225ec  lea     rcx, [rsp+0B8h+var_80]
0x1800225f1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800225f6  lea     r8, [rsp+0B8h+var_80]
0x1800225fb  lea     rdx, _GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6
0x180022602  mov     rcx, rbx
0x180022605  call    cs:__imp_RoGetActivationFactory
0x18002260b  mov     rcx, [rsp+0B8h]; this
0x180022613  test    eax, eax
0x180022615  js      loc_18002270A
0x18002261b  xor     ebx, ebx
0x18002261d  mov     [rsp+0B8h+var_78], rbx
0x180022622  cmp     [rdi+10h], rbx
0x180022626  jz      short loc_180022651
0x180022628  mov     rdx, rdi
0x18002262b  lea     rcx, [rsp+0B8h+var_68]
0x180022630  call    ?GetSrUserFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetSrUserFromSid(std::wstring const &)
0x180022635  mov     rdx, rax
0x180022638  lea     rcx, [rsp+0B8h+var_78]
0x18002263d  call    ??4?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser> &&)
0x180022642  lea     rcx, [rsp+0B8h+var_68]
0x180022647  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002264c  mov     rbx, [rsp+0B8h+var_78]
0x180022651  mov     [rsp+0B8h+string], 0
0x18002265a  mov     rsi, [rsp+0B8h+var_80]
0x18002265f  mov     rax, [rsi]
0x180022662  mov     rdi, [rax+138h]
0x180022669  xor     ecx, ecx; string
0x18002266b  call    cs:__imp_WindowsDeleteString
0x180022671  mov     [rsp+0B8h+string], 0
0x18002267a  mov     rcx, r15
0x18002267d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022682  mov     rdx, rax; unsigned __int16 *
0x180022685  lea     rcx, [rsp+0B8h+var_58]; this
0x18002268a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18002268f  lea     r9, [rsp+0B8h+string]
0x180022694  mov     r8, [rsp+0B8h+var_58]
0x180022699  mov     rdx, rbx
0x18002269c  mov     rcx, rsi
0x18002269f  mov     rax, rdi
0x1800226a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226a7  nop
0x1800226a8  jmp     short loc_1800226AF
0x1800226aa  mov     r14, [rsp+0B8h+var_60]
0x1800226af  xor     edx, edx; length
0x1800226b1  mov     rcx, [rsp+0B8h+string]; string
0x1800226b6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800226bc  mov     rdx, rax
0x1800226bf  mov     rcx, r14
0x1800226c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800226c7  nop
0x1800226c8  lea     rcx, [rsp+0B8h+string]; this
0x1800226cd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800226d2  nop
0x1800226d3  lea     rcx, [rsp+0B8h+var_78]
0x1800226d8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800226dd  nop
0x1800226de  lea     rcx, [rsp+0B8h+var_80]
0x1800226e3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800226e8  mov     rax, r14
0x1800226eb  mov     rcx, [rsp+0B8h+var_38]
0x1800226f3  xor     rcx, rsp; StackCookie
0x1800226f6  call    __security_check_cookie
0x1800226fb  add     rsp, 90h
0x180022702  pop     r15
0x180022704  pop     r14
0x180022706  pop     rdi
0x180022707  pop     rsi
0x180022708  pop     rbx
0x180022709  retn
0x18002270a  mov     r9d, eax; char *
0x18002270d  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x180022714  mov     edx, 27Dh; void *
0x180022719  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
