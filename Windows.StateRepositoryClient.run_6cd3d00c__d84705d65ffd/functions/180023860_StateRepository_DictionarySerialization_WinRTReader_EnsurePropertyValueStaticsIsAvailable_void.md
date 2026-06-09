# StateRepository::DictionarySerialization::WinRTReader::EnsurePropertyValueStaticsIsAvailable(void)

- ea: `0x180023860`
- end: `0x180023907`
- name: `?EnsurePropertyValueStaticsIsAvailable@WinRTReader@DictionarySerialization@StateRepository@@AEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(StateRepository::DictionarySerialization::WinRTReader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021718`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180023860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800238b4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800238b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002389b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002389b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800238c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800238c9`

## string_xrefs

- `0x1800238da`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::WinRTReader::EnsurePropertyValueStaticsIsAvailable(
        StateRepository::DictionarySerialization::WinRTReader *this)
{
  int ActivationFactory; // eax
  unsigned int v3; // ebx
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( *(_QWORD *)this )
    return 0;
  *(_QWORD *)this = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, this);
  v3 = ActivationFactory;
  if ( ActivationFactory >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x255,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)string);
  return v3;
}

```

## disassembly

```asm
0x180023860  push    rbx
0x180023862  sub     rsp, 50h
0x180023866  mov     rax, cs:__security_cookie
0x18002386d  xor     rax, rsp
0x180023870  mov     [rsp+58h+var_18], rax
0x180023875  cmp     qword ptr [rcx], 0
0x180023879  mov     rbx, rcx
0x18002387c  jnz     short loc_1800238F2
0x18002387e  mov     qword ptr [rcx], 0
0x180023885  lea     r9, [rsp+58h+string]; string
0x18002388a  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x180023891  mov     edx, 20h ; ' '; length
0x180023896  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18002389b  call    cs:__imp_WindowsCreateStringReference
0x1800238a1  test    eax, eax
0x1800238a3  jns     short loc_1800238BA
0x1800238a5  xor     r9d, r9d; lpArguments
0x1800238a8  xor     r8d, r8d; nNumberOfArguments
0x1800238ab  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800238b0  lea     edx, [r9+1]; dwExceptionFlags
0x1800238b4  call    cs:__imp_RaiseException
0x1800238ba  mov     rcx, [rsp+58h+string]
0x1800238bf  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800238c6  mov     r8, rbx
0x1800238c9  call    cs:__imp_RoGetActivationFactory
0x1800238cf  mov     ebx, eax
0x1800238d1  test    eax, eax
0x1800238d3  jns     short loc_1800238F2
0x1800238d5  mov     rcx, [rsp+58h]; this
0x1800238da  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1800238e1  mov     r9d, eax; char *
0x1800238e4  mov     edx, 255h; void *
0x1800238e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238ee  mov     eax, ebx
0x1800238f0  jmp     short loc_1800238F4
0x1800238f2  xor     eax, eax
0x1800238f4  mov     rcx, [rsp+58h+var_18]
0x1800238f9  xor     rcx, rsp; StackCookie
0x1800238fc  call    __security_check_cookie
0x180023901  add     rsp, 50h
0x180023905  pop     rbx
0x180023906  retn
```
