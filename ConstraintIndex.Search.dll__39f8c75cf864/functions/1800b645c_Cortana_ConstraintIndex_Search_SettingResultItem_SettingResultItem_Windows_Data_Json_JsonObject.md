# Cortana::ConstraintIndex::Search::SettingResultItem::SettingResultItem(Windows::Data::Json::JsonObject *)

- ea: `0x1800b645c`
- end: `0x1800b6700`
- name: `??0SettingResultItem@Search@ConstraintIndex@Cortana@@QE$AAA@PE$AAVJsonObject@Json@Data@Windows@@@Z`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b6d80`
- `0x1800c3e68`

## callees

- `0x1800049e0`
- `0x18000616e`
- `0x18000617a`
- `0x18000619e`
- `0x18003a724`
- `0x18003b2f4`
- `0x18003fd04`
- `0x18003feb4`
- `0x180094048`
- `0x1800941f8`
- `0x1800b645c`
- `0x1800b7418`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6577`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b6577`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1800b6494`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1800b6494`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 *__fastcall Cortana::ConstraintIndex::Search::SettingResultItem::SettingResultItem(__int64 *a1, __int64 a2)
{
  HSTRING v4; // rdi
  const WCHAR *StringRawBuffer_0; // rax
  __int64 v6; // rcx
  char v7; // bl
  __int64 v8; // r13
  HSTRING v9; // r15
  HRESULT v10; // eax
  HSTRING v11; // rdi
  HRESULT v12; // eax
  HSTRING v13; // rbx
  HSTRING v15; // [rsp+30h] [rbp-50h]
  HSTRING UserSettingsLocation; // [rsp+38h] [rbp-48h]
  HSTRING SystemSettingsLocation; // [rsp+38h] [rbp-48h]
  HSTRING v18; // [rsp+40h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  Platform::Object::Object(a1 + 4);
  *a1 = (__int64)&Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::__ISettingResultItemPublicNonVirtuals'};
  a1[1] = (__int64)&Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::ISettingResultItem'};
  a1[2] = (__int64)&Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::ICloneableItem<Cortana::ConstraintIndex::Search::SettingResultItem __gc *>'};
  a1[3] = (__int64)&Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::IRankableItem'};
  a1[4] = (__int64)&Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Platform::Object'};
  a1[5] = (__int64)&Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `__abi_IUnknown'};
  a1[6] = (__int64)&Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  __abi_FTMWeakRefData::__abi_FTMWeakRefData(a1 + 24);
  a1[23] = __abi_winrt_ptr_ctor(a2);
  (*(void (__fastcall **)(__int64 *, __int64))(a1[3] + 72))(a1 + 3, 1000);
  Cortana::ConstraintIndex::Search::SettingResultItem::ParseAllJsonProperties(a1, a2);
  v4 = (HSTRING)(*(__int64 (__fastcall **)(__int64 *))(a1[1] + 272))(a1 + 1);
  string = v4;
  StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v4, 0);
  v6 = -1;
  do
    ++v6;
  while ( StringRawBuffer_0[v6] );
  if ( (int)v6 < 18 || (v7 = 1, CompareStringOrdinal(StringRawBuffer_0, 18, L"NameSpace_Classic_", 18, 1) != 2) )
    v7 = 0;
  WindowsDeleteString_0(v4);
  v8 = *a1;
  v9 = (HSTRING)(*(__int64 (__fastcall **)(__int64 *))(a1[1] + 272))(a1 + 1);
  if ( v7 )
  {
    string = 0;
    v10 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
    if ( v10 < 0 )
      __abi_WinRTraiseException(v10);
    UserSettingsLocation = (HSTRING)Cortana::ConstraintIndex::Search::GetUserSettingsLocation();
    v11 = (HSTRING)Platform::String::Concat(UserSettingsLocation, string);
    string = v11;
    v18 = (HSTRING)Platform::String::Concat(v11, v9);
    (*(void (__fastcall **)(__int64 *, HSTRING))(v8 + 136))(a1, v18);
    WindowsDeleteString_0(v18);
    WindowsDeleteString_0(v11);
    WindowsDeleteString_0(UserSettingsLocation);
  }
  else
  {
    string = 0;
    v12 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
    if ( v12 < 0 )
      __abi_WinRTraiseException(v12);
    SystemSettingsLocation = (HSTRING)Cortana::ConstraintIndex::Search::GetSystemSettingsLocation();
    v15 = (HSTRING)Platform::String::Concat(SystemSettingsLocation, string);
    v13 = (HSTRING)Platform::String::Concat(v15, v9);
    string = v13;
    (*(void (__fastcall **)(__int64 *, HSTRING))(v8 + 136))(a1, v13);
    WindowsDeleteString_0(v13);
    WindowsDeleteString_0(v15);
    WindowsDeleteString_0(SystemSettingsLocation);
  }
  WindowsDeleteString_0(v9);
  return a1;
}

```

## disassembly

```asm
0x1800b645c  mov     [rsp-28h+arg_10], rbx
0x1800b6461  mov     [rsp-28h+arg_18], rsi
0x1800b6466  push    rbp
0x1800b6467  push    rdi
0x1800b6468  push    r13
0x1800b646a  push    r14
0x1800b646c  push    r15
0x1800b646e  mov     rbp, rsp
0x1800b6471  sub     rsp, 80h
0x1800b6478  mov     rax, cs:__security_cookie
0x1800b647f  xor     rax, rsp
0x1800b6482  mov     [rbp+var_10], rax
0x1800b6486  mov     rsi, rdx
0x1800b6489  mov     r14, rcx
0x1800b648c  mov     [rbp+var_38], rcx
0x1800b6490  add     rcx, 20h ; ' '
0x1800b6494  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x1800b649a  lea     rax, ??_7SettingResultItem@Search@ConstraintIndex@Cortana@@6B__ISettingResultItemPublicNonVirtuals@123@@; const Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::__ISettingResultItemPublicNonVirtuals'}
0x1800b64a1  mov     [r14], rax
0x1800b64a4  lea     r15, [r14+8]
0x1800b64a8  lea     rax, ??_7SettingResultItem@Search@ConstraintIndex@Cortana@@6BISettingResultItem@123@@; const Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::ISettingResultItem'}
0x1800b64af  mov     [r15], rax
0x1800b64b2  lea     rax, ??_7SettingResultItem@Search@ConstraintIndex@Cortana@@6B?$ICloneableItem@PE$AAVSettingResultItem@Search@ConstraintIndex@Cortana@@@123@@; const Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::ICloneableItem<Cortana::ConstraintIndex::Search::SettingResultItem *>'}
0x1800b64b9  mov     [r14+10h], rax
0x1800b64bd  lea     rdi, [r14+18h]
0x1800b64c1  lea     rax, ??_7SettingResultItem@Search@ConstraintIndex@Cortana@@6BIRankableItem@123@@; const Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Cortana::ConstraintIndex::Search::IRankableItem'}
0x1800b64c8  mov     [rdi], rax
0x1800b64cb  lea     rax, ??_7SettingResultItem@Search@ConstraintIndex@Cortana@@6BObject@Platform@@@; const Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Platform::Object'}
0x1800b64d2  mov     [r14+20h], rax
0x1800b64d6  lea     rax, ??_7SettingResultItem@Search@ConstraintIndex@Cortana@@6B__abi_IUnknown@@@; const Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `__abi_IUnknown'}
0x1800b64dd  mov     [r14+28h], rax
0x1800b64e1  lea     rax, ??_7SettingResultItem@Search@ConstraintIndex@Cortana@@6BObject@Platform@@IWeakReferenceSource@Details@5@@; const Cortana::ConstraintIndex::Search::SettingResultItem::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x1800b64e8  mov     [r14+30h], rax
0x1800b64ec  lea     rcx, [r14+0C0h]
0x1800b64f3  call    ??0__abi_FTMWeakRefData@@QEAA@PE$AAVObject@Platform@@W4CallbackContext@2@@Z; __abi_FTMWeakRefData::__abi_FTMWeakRefData(Platform::Object *,Platform::CallbackContext)
0x1800b64f8  nop
0x1800b64f9  mov     rcx, rsi
0x1800b64fc  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800b6501  mov     [r14+0B8h], rax
0x1800b6508  mov     rax, [rdi]
0x1800b650b  mov     edx, 3E8h
0x1800b6510  mov     rcx, rdi
0x1800b6513  mov     rax, [rax+48h]
0x1800b6517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b651c  mov     rdx, rsi
0x1800b651f  mov     rcx, r14
0x1800b6522  call    ?ParseAllJsonProperties@SettingResultItem@Search@ConstraintIndex@Cortana@@AE$AAAXPE$AAVJsonObject@Json@Data@Windows@@@Z; Cortana::ConstraintIndex::Search::SettingResultItem::ParseAllJsonProperties(Windows::Data::Json::JsonObject *)
0x1800b6527  mov     rax, [r15]
0x1800b652a  mov     rcx, r15
0x1800b652d  mov     rax, [rax+110h]
0x1800b6534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6539  mov     rdi, rax
0x1800b653c  mov     [rbp+string], rax
0x1800b6540  xor     edx, edx; length
0x1800b6542  mov     rcx, rax; string
0x1800b6545  call    WindowsGetStringRawBuffer_0
0x1800b654a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b654e  xor     esi, esi
0x1800b6550  inc     rcx
0x1800b6553  cmp     [rax+rcx*2], si
0x1800b6557  jnz     short loc_1800B6550
0x1800b6559  mov     edx, 12h; cchCount1
0x1800b655e  cmp     ecx, edx
0x1800b6560  jl      short loc_1800B6584
0x1800b6562  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x1800b656a  mov     r9d, edx; cchCount2
0x1800b656d  lea     r8, String2; "NameSpace_Classic_"
0x1800b6574  mov     rcx, rax; lpString1
0x1800b6577  call    cs:__imp_CompareStringOrdinal
0x1800b657d  cmp     eax, 2
0x1800b6580  mov     bl, 1
0x1800b6582  jz      short loc_1800B6587
0x1800b6584  mov     bl, sil
0x1800b6587  mov     rcx, rdi; string
0x1800b658a  call    WindowsDeleteString_0
0x1800b658f  mov     rax, [r15]
0x1800b6592  mov     r13, [r14]
0x1800b6595  mov     rcx, r15
0x1800b6598  mov     rax, [rax+110h]
0x1800b659f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b65a4  mov     r15, rax
0x1800b65a7  test    bl, bl
0x1800b65a9  jz      loc_1800B6640
0x1800b65af  mov     [rbp+var_50], rax
0x1800b65b3  mov     [rbp+string], rsi
0x1800b65b7  lea     r9, [rbp+string]; string
0x1800b65bb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800b65bf  mov     edx, 1; length
0x1800b65c4  lea     rcx, asc_180104F88; "\\"
0x1800b65cb  call    WindowsCreateStringReference_0
0x1800b65d0  test    eax, eax
0x1800b65d2  jns     short loc_1800B65DC
0x1800b65d4  mov     ecx, eax; int
0x1800b65d6  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800b65dc  call    ?GetUserSettingsLocation@Search@ConstraintIndex@Cortana@@YAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::GetUserSettingsLocation(void)
0x1800b65e1  mov     rsi, rax
0x1800b65e4  mov     [rbp+var_48], rax
0x1800b65e8  mov     rdx, [rbp+string]
0x1800b65ec  mov     rcx, rax
0x1800b65ef  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800b65f4  mov     rdi, rax
0x1800b65f7  mov     [rbp+string], rax
0x1800b65fb  mov     rdx, r15
0x1800b65fe  mov     rcx, rax
0x1800b6601  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800b6606  mov     rbx, rax
0x1800b6609  mov     [rbp+var_40], rax
0x1800b660d  mov     rdx, rax
0x1800b6610  mov     rcx, r14
0x1800b6613  mov     rax, [r13+88h]
0x1800b661a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b661f  nop
0x1800b6620  mov     rcx, rbx; string
0x1800b6623  call    WindowsDeleteString_0
0x1800b6628  nop
0x1800b6629  mov     rcx, rdi; string
0x1800b662c  call    WindowsDeleteString_0
0x1800b6631  nop
0x1800b6632  mov     rcx, rsi; string
0x1800b6635  call    WindowsDeleteString_0
0x1800b663a  nop
0x1800b663b  jmp     loc_1800B66CC
0x1800b6640  mov     [rbp+var_40], r15
0x1800b6644  mov     [rbp+string], rsi
0x1800b6648  lea     r9, [rbp+string]; string
0x1800b664c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800b6650  mov     edx, 1; length
0x1800b6655  lea     rcx, asc_180104F88; "\\"
0x1800b665c  call    WindowsCreateStringReference_0
0x1800b6661  test    eax, eax
0x1800b6663  jns     short loc_1800B666D
0x1800b6665  mov     ecx, eax; int
0x1800b6667  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800b666d  call    ?GetSystemSettingsLocation@Search@ConstraintIndex@Cortana@@YAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::GetSystemSettingsLocation(void)
0x1800b6672  mov     rsi, rax
0x1800b6675  mov     [rbp+var_48], rax
0x1800b6679  mov     rdx, [rbp+string]
0x1800b667d  mov     rcx, rax
0x1800b6680  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800b6685  mov     rdi, rax
0x1800b6688  mov     [rbp+var_50], rax
0x1800b668c  mov     rdx, r15
0x1800b668f  mov     rcx, rax
0x1800b6692  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800b6697  mov     rbx, rax
0x1800b669a  mov     [rbp+string], rax
0x1800b669e  mov     rdx, rax
0x1800b66a1  mov     rcx, r14
0x1800b66a4  mov     rax, [r13+88h]
0x1800b66ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b66b0  nop
0x1800b66b1  mov     rcx, rbx; string
0x1800b66b4  call    WindowsDeleteString_0
0x1800b66b9  nop
0x1800b66ba  mov     rcx, rdi; string
0x1800b66bd  call    WindowsDeleteString_0
0x1800b66c2  nop
0x1800b66c3  mov     rcx, rsi; string
0x1800b66c6  call    WindowsDeleteString_0
0x1800b66cb  nop
0x1800b66cc  mov     rcx, r15; string
0x1800b66cf  call    WindowsDeleteString_0
0x1800b66d4  nop
0x1800b66d5  mov     rax, r14
0x1800b66d8  mov     rcx, [rbp+var_10]
0x1800b66dc  xor     rcx, rsp; StackCookie
0x1800b66df  call    __security_check_cookie
0x1800b66e4  lea     r11, [rsp+80h+var_s0]
0x1800b66ec  mov     rbx, [r11+40h]
0x1800b66f0  mov     rsi, [r11+48h]
0x1800b66f4  mov     rsp, r11
0x1800b66f7  pop     r15
0x1800b66f9  pop     r14
0x1800b66fb  pop     r13
0x1800b66fd  pop     rdi
0x1800b66fe  pop     rbp
0x1800b66ff  retn
```
