# PrivilegedAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x18003cb50`
- end: `0x18003cce4`
- name: `?InitializeParameters@PrivilegedAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x1800240b8`
- `0x1800253bc`
- `0x180026930`
- `0x18003cb50`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cbf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cbf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cc7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cc7d`

## string_xrefs

- `0x18003cbc7`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`
- `0x18003cca1`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\privilegedaction.cpp`

## pseudocode

```c
__int64 __fastcall PrivilegedAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, _QWORD, _QWORD *); // rdi
  _QWORD *v6; // rbx
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64); // rdi
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v13; // rbx
  PCWSTR StringRawBuffer; // rax
  int v15; // eax
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v18[4]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)*a2 + 80LL);
  v6 = (_QWORD *)(a1 + 168);
  WindowsDeleteString(*(HSTRING *)(a1 + 168));
  *v6 = 0;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v18,
    PrivilegedAction::s_fileDcatDownloadUrlTag);
  v7 = v5(v4, v18[0], v6);
  if ( v7 < 0 )
  {
    v8 = 48;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
    return (unsigned int)v7;
  }
  v9 = *a2;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)*a2 + 80LL);
  WindowsDeleteString(*(HSTRING *)(a1 + 176));
  *(_QWORD *)(a1 + 176) = 0;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v18,
    PrivilegedAction::s_fileSha256HashTag);
  v7 = v10(v9, v18[0], a1 + 176);
  if ( v7 < 0 )
  {
    v8 = 49;
    goto LABEL_3;
  }
  string = 0;
  v11 = *a2;
  v12 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v18,
    PrivilegedAction::s_privilegedParameterTag);
  if ( v12(v11, v18[0], &string) < 0
    || (v13 = *(_QWORD *)(a1 + 152),
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
        v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v13 + 16,
                StringRawBuffer,
                -1),
        v7 = v15,
        v15 >= 0) )
  {
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\privilegedaction.cpp",
      (const char *)(unsigned int)v15,
      (int)string);
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003cb50  mov     [rsp+arg_10], rbx
0x18003cb55  mov     [rsp+arg_18], rbp
0x18003cb5a  push    rsi
0x18003cb5b  push    rdi
0x18003cb5c  push    r14
0x18003cb5e  sub     rsp, 50h
0x18003cb62  mov     rax, cs:__security_cookie
0x18003cb69  xor     rax, rsp
0x18003cb6c  mov     [rsp+68h+var_20], rax
0x18003cb71  mov     r14, rdx
0x18003cb74  mov     rbp, rcx
0x18003cb77  mov     rsi, [rdx]
0x18003cb7a  mov     rax, [rsi]
0x18003cb7d  mov     rdi, [rax+50h]
0x18003cb81  lea     rbx, [rcx+0A8h]
0x18003cb88  mov     rcx, [rbx]; string
0x18003cb8b  call    cs:__imp_WindowsDeleteString
0x18003cb91  mov     qword ptr [rbx], 0
0x18003cb98  mov     rdx, cs:?s_fileDcatDownloadUrlTag@PrivilegedAction@@0QEBGEB; unsigned __int16 *
0x18003cb9f  lea     rcx, [rsp+68h+var_40]; this
0x18003cba4  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003cba9  mov     r8, rbx
0x18003cbac  mov     rdx, [rsp+68h+var_40]
0x18003cbb1  mov     rcx, rsi
0x18003cbb4  mov     rax, rdi
0x18003cbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbbc  mov     ebx, eax
0x18003cbbe  test    eax, eax
0x18003cbc0  jns     short loc_18003CBE0
0x18003cbc2  mov     edx, 30h ; '0'; void *
0x18003cbc7  lea     r8, aOnecoreBaseDia_12; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003cbce  mov     r9d, ebx; char *
0x18003cbd1  mov     rcx, [rsp+68h]; this
0x18003cbd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cbdb  jmp     loc_18003CCC0
0x18003cbe0  mov     rsi, [r14]
0x18003cbe3  mov     rax, [rsi]
0x18003cbe6  mov     rdi, [rax+50h]
0x18003cbea  lea     rbx, [rbp+0B0h]
0x18003cbf1  mov     rcx, [rbx]; string
0x18003cbf4  call    cs:__imp_WindowsDeleteString
0x18003cbfa  mov     qword ptr [rbx], 0
0x18003cc01  mov     rdx, cs:?s_fileSha256HashTag@PrivilegedAction@@0QEBGEB; unsigned __int16 *
0x18003cc08  lea     rcx, [rsp+68h+var_40]; this
0x18003cc0d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003cc12  mov     r8, rbx
0x18003cc15  mov     rdx, [rsp+68h+var_40]
0x18003cc1a  mov     rcx, rsi
0x18003cc1d  mov     rax, rdi
0x18003cc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc25  mov     ebx, eax
0x18003cc27  test    eax, eax
0x18003cc29  jns     short loc_18003CC32
0x18003cc2b  mov     edx, 31h ; '1'
0x18003cc30  jmp     short loc_18003CBC7
0x18003cc32  mov     [rsp+68h+string], 0; int
0x18003cc3b  mov     rdi, [r14]
0x18003cc3e  mov     rax, [rdi]
0x18003cc41  mov     rbx, [rax+50h]
0x18003cc45  mov     rdx, cs:?s_privilegedParameterTag@PrivilegedAction@@0QEBGEB; unsigned __int16 *
0x18003cc4c  lea     rcx, [rsp+68h+var_40]; this
0x18003cc51  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18003cc56  lea     r8, [rsp+68h+string]
0x18003cc5b  mov     rdx, [rsp+68h+var_40]
0x18003cc60  mov     rcx, rdi
0x18003cc63  mov     rax, rbx
0x18003cc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc6b  test    eax, eax
0x18003cc6d  js      short loc_18003CCB4
0x18003cc6f  mov     rbx, [rbp+98h]
0x18003cc76  xor     edx, edx; length
0x18003cc78  mov     rcx, [rsp+68h+string]; string
0x18003cc7d  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cc83  lea     rcx, [rbx+10h]
0x18003cc87  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003cc8b  mov     rdx, rax
0x18003cc8e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003cc93  mov     ebx, eax
0x18003cc95  test    eax, eax
0x18003cc97  jns     short loc_18003CCB4
0x18003cc99  mov     rcx, [rsp+68h]; this
0x18003cc9e  mov     r9d, eax; char *
0x18003cca1  lea     r8, aOnecoreBaseDia_12; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003cca8  mov     edx, 37h ; '7'; void *
0x18003ccad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ccb2  jmp     short loc_18003CCB6
0x18003ccb4  xor     ebx, ebx
0x18003ccb6  lea     rcx, [rsp+68h+string]; this
0x18003ccbb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003ccc0  mov     eax, ebx
0x18003ccc2  mov     rcx, [rsp+68h+var_20]
0x18003ccc7  xor     rcx, rsp; StackCookie
0x18003ccca  call    __security_check_cookie
0x18003cccf  lea     r11, [rsp+68h+var_18]
0x18003ccd4  mov     rbx, [r11+30h]
0x18003ccd8  mov     rbp, [r11+38h]
0x18003ccdc  mov     rsp, r11
0x18003ccdf  pop     r14
0x18003cce1  pop     rdi
0x18003cce2  pop     rsi
0x18003cce3  retn
```
