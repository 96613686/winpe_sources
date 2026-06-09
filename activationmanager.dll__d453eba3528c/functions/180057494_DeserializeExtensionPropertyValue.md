# DeserializeExtensionPropertyValue

- ea: `0x180057494`
- end: `0x18005767d`
- name: `DeserializeExtensionPropertyValue`
- size: `489`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, HSTRING)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007e76c`

## callees

- `0x180011328`
- `0x18002a380`
- `0x180032820`
- `0x180034430`
- `0x180037824`
- `0x180045174`
- `0x180056208`
- `0x180057494`
- `0x18005ae90`
- `0x18007ed90`
- `0x18007ef20`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800575a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800575a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180057640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800575e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800575e3`

## string_xrefs

- `0x18005750c`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x1800575cb`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`

## pseudocode

```c
_QWORD *__fastcall DeserializeExtensionPropertyValue(_QWORD *a1, __int64 a2, HSTRING a3)
{
  __int64 v5; // rdx
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  unsigned int (__fastcall *v9)(__int64, _QWORD, struct IInspectable **); // rbx
  __int64 v10; // rax
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v13; // rbx
  HSTRING string; // [rsp+20h] [rbp-29h] BYREF
  __int64 v16; // [rsp+28h] [rbp-21h] BYREF
  int v17; // [rsp+30h] [rbp-19h]
  RoVariant *v18; // [rsp+38h] [rbp-11h] BYREF
  struct IInspectable *v19; // [rsp+40h] [rbp-9h] BYREF
  RoVariant *v20; // [rsp+50h] [rbp+7h] BYREF
  int v21; // [rsp+58h] [rbp+Fh]
  _QWORD *v22; // [rsp+60h] [rbp+17h]
  _BYTE v23[24]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v24; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v22 = a1;
  string = a3;
  std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>(a1);
  v17 = 1;
  v16 = 0;
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 128LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  v7 = v6(a2, &v16);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
  v20 = 0;
  v21 = 0;
  v8 = v16;
  v9 = *(unsigned int (__fastcall **)(__int64, _QWORD, struct IInspectable **))(*(_QWORD *)v16 + 48LL);
  v18 = (RoVariant *)&v20;
  v19 = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v23, &string);
  LODWORD(v9) = v9(v8, *(_QWORD *)(v10 + 24), &v19) >> 31;
  v24 = 0;
  RoVariant::Attach(v18, v19);
  if ( (unsigned __int8)v9 != 1 )
  {
    string = 0;
    v18 = v20;
    LODWORD(v19) = v21;
    WindowsDeleteString(0);
    string = 0;
    v11 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v18, &string);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
        (const char *)(unsigned int)v11,
        (int)string);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = (_QWORD *)SplitString(&v18, StringRawBuffer);
    if ( a1 != v13 )
    {
      std::vector<std::wstring>::_Tidy(a1);
      *a1 = *v13;
      a1[1] = v13[1];
      a1[2] = v13[2];
      *v13 = 0;
      v13[1] = 0;
      v13[2] = 0;
    }
    std::vector<std::wstring>::_Tidy(&v18);
    WindowsDeleteString(string);
  }
  RoVariant::~RoVariant((RoVariant *)&v20);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  return a1;
}

```

## disassembly

```asm
0x180057494  mov     [rsp-8+arg_18], rbx
0x180057499  push    rbp
0x18005749a  push    rsi
0x18005749b  push    rdi
0x18005749c  lea     rbp, [rsp-47h]
0x1800574a1  sub     rsp, 90h
0x1800574a8  mov     rax, cs:__security_cookie
0x1800574af  xor     rax, rsp
0x1800574b2  mov     [rbp+57h+var_18], rax
0x1800574b6  mov     rdi, rdx
0x1800574b9  mov     rsi, rcx
0x1800574bc  mov     [rbp+57h+var_40], rcx
0x1800574c0  mov     [rbp+57h+string], r8
0x1800574c4  mov     [rbp+57h+var_70], 0
0x1800574cb  call    ??0?$vector@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@V?$allocator@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>(void)
0x1800574d0  mov     [rbp+57h+var_70], 1
0x1800574d7  mov     [rbp+57h+var_78], 0
0x1800574df  mov     rax, [rdx]
0x1800574e2  mov     rbx, [rax+80h]
0x1800574e9  lea     rcx, [rbp+57h+var_78]
0x1800574ed  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800574f2  lea     rdx, [rbp+57h+var_78]
0x1800574f6  mov     rcx, rdi
0x1800574f9  mov     rax, rbx
0x1800574fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057501  mov     rcx, [rbp+5Fh]; this
0x180057505  test    eax, eax
0x180057507  jns     short loc_18005751E
0x180057509  mov     r9d, eax; char *
0x18005750c  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180057513  mov     edx, 3Ah ; ':'; void *
0x180057518  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005751e  mov     [rbp+57h+var_50], 0
0x180057526  mov     [rbp+57h+var_48], 0
0x18005752d  mov     rdi, [rbp+57h+var_78]
0x180057531  mov     rax, [rdi]
0x180057534  mov     rbx, [rax+30h]
0x180057538  lea     rax, [rbp+57h+var_50]
0x18005753c  mov     [rbp+57h+var_68], rax
0x180057540  mov     [rbp+57h+var_60], 0
0x180057548  lea     rdx, [rbp+57h+string]
0x18005754c  lea     rcx, [rbp+57h+var_38]
0x180057550  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180057555  nop
0x180057556  lea     r8, [rbp+57h+var_60]
0x18005755a  mov     rdx, [rax+18h]
0x18005755e  mov     rcx, rdi
0x180057561  mov     rax, rbx
0x180057564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057569  mov     ebx, eax
0x18005756b  shr     ebx, 1Fh
0x18005756e  mov     [rbp+57h+var_20], 0
0x180057576  mov     rdx, [rbp+57h+var_60]; struct IInspectable *
0x18005757a  mov     rcx, [rbp+57h+var_68]; this
0x18005757e  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x180057583  nop
0x180057584  xor     bl, 1
0x180057587  jz      loc_180057647
0x18005758d  mov     [rbp+57h+string], 0
0x180057595  mov     rax, [rbp+57h+var_50]
0x180057599  mov     [rbp+57h+var_68], rax
0x18005759d  mov     eax, [rbp+57h+var_48]
0x1800575a0  mov     dword ptr [rbp+57h+var_60], eax
0x1800575a3  xor     ecx, ecx; string
0x1800575a5  call    cs:__imp_WindowsDeleteString
0x1800575ab  mov     [rbp+57h+string], 0
0x1800575b3  lea     rdx, [rbp+57h+string]; HSTRING *
0x1800575b7  lea     rcx, [rbp+57h+var_68]; this
0x1800575bb  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x1800575c0  mov     rcx, [rbp+5Fh]; this
0x1800575c4  test    eax, eax
0x1800575c6  jns     short loc_1800575DD
0x1800575c8  mov     r9d, eax; char *
0x1800575cb  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800575d2  mov     edx, 40h ; '@'; void *
0x1800575d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800575dd  xor     edx, edx; length
0x1800575df  mov     rcx, [rbp+57h+string]; string
0x1800575e3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800575e9  mov     rdx, rax
0x1800575ec  lea     rcx, [rbp+57h+var_68]
0x1800575f0  call    SplitString
0x1800575f5  mov     rbx, rax
0x1800575f8  cmp     rsi, rax
0x1800575fb  jz      short loc_180057632
0x1800575fd  mov     rcx, rsi
0x180057600  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180057605  mov     rax, [rbx]
0x180057608  mov     [rsi], rax
0x18005760b  mov     rax, [rbx+8]
0x18005760f  mov     [rsi+8], rax
0x180057613  mov     rax, [rbx+10h]
0x180057617  mov     [rsi+10h], rax
0x18005761b  mov     qword ptr [rbx], 0
0x180057622  mov     qword ptr [rbx+8], 0
0x18005762a  mov     qword ptr [rbx+10h], 0
0x180057632  lea     rcx, [rbp+57h+var_68]
0x180057636  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005763b  nop
0x18005763c  mov     rcx, [rbp+57h+string]; string
0x180057640  call    cs:__imp_WindowsDeleteString
0x180057646  nop
0x180057647  lea     rcx, [rbp+57h+var_50]; this
0x18005764b  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180057650  nop
0x180057651  lea     rcx, [rbp+57h+var_78]
0x180057655  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005765a  mov     rax, rsi
0x18005765d  mov     rcx, [rbp+57h+var_18]
0x180057661  xor     rcx, rsp; StackCookie
0x180057664  call    __security_check_cookie
0x180057669  mov     rbx, [rsp+0A0h+arg_18]
0x180057671  add     rsp, 90h
0x180057678  pop     rdi
0x180057679  pop     rsi
0x18005767a  pop     rbp
0x18005767b  retn
```
