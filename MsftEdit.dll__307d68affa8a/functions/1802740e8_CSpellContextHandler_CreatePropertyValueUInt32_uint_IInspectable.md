# CSpellContextHandler::CreatePropertyValueUInt32(uint,IInspectable * *)

- ea: `0x1802740e8`
- end: `0x1802741a4`
- name: `?CreatePropertyValueUInt32@CSpellContextHandler@@AEAAJIPEAPEAUIInspectable@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this, unsigned int, struct IInspectable **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180273cc4`

## callees

- `0x180048d5c`
- `0x18013bad0`
- `0x1801f5a90`
- `0x1802740e8`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180274148`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180274148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18027412f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18027412f`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::CreatePropertyValueUInt32(
        CSpellContextHandler *this,
        unsigned int a2,
        struct IInspectable **a3)
{
  int v5; // ebx
  __int64 v7; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER v9; // [rsp+30h] [rbp-28h] BYREF

  *a3 = 0;
  v7 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &v9, &v8) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
         v8,
         &v7);
  if ( v5 >= 0 )
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IInspectable **))(*(_QWORD *)v7 + 88LL))(v7, a2, a3);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1802740e8  mov     r11, rsp
0x1802740eb  mov     [r11+8], rbx
0x1802740ef  mov     [r11+20h], rsi
0x1802740f3  push    rdi
0x1802740f4  sub     rsp, 50h
0x1802740f8  mov     rax, cs:__security_cookie
0x1802740ff  xor     rax, rsp
0x180274102  mov     [rsp+58h+var_10], rax
0x180274107  mov     rdi, r8
0x18027410a  mov     qword ptr [r8], 0
0x180274111  mov     esi, edx
0x180274113  mov     qword ptr [r11-38h], 0
0x18027411b  lea     r8, [r11-28h]; hstringHeader
0x18027411f  mov     edx, 20h ; ' '; length
0x180274124  lea     r9, [r11-30h]; string
0x180274128  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18027412f  call    cs:__imp_WindowsCreateStringReference
0x180274135  test    eax, eax
0x180274137  jns     short loc_18027414E
0x180274139  xor     r9d, r9d; lpArguments
0x18027413c  xor     r8d, r8d; nNumberOfArguments
0x18027413f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180274144  lea     edx, [r9+1]; dwExceptionFlags
0x180274148  call    cs:__imp_RaiseException
0x18027414e  mov     rcx, [rsp+58h+var_30]
0x180274153  lea     rdx, [rsp+58h+var_38]
0x180274158  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18027415d  mov     ebx, eax
0x18027415f  test    eax, eax
0x180274161  js      short loc_18027417B
0x180274163  mov     rcx, [rsp+58h+var_38]
0x180274168  mov     r8, rdi
0x18027416b  mov     edx, esi
0x18027416d  mov     rax, [rcx]
0x180274170  mov     rax, [rax+58h]
0x180274174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274179  mov     ebx, eax
0x18027417b  lea     rcx, [rsp+58h+var_38]
0x180274180  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180274185  mov     eax, ebx
0x180274187  mov     rcx, [rsp+58h+var_10]
0x18027418c  xor     rcx, rsp; StackCookie
0x18027418f  call    __security_check_cookie
0x180274194  mov     rbx, [rsp+58h+arg_0]
0x180274199  mov     rsi, [rsp+58h+arg_18]
0x18027419e  add     rsp, 50h
0x1802741a2  pop     rdi
0x1802741a3  retn
```
