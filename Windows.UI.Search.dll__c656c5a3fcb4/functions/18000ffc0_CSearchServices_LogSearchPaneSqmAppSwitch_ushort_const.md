# CSearchServices::LogSearchPaneSqmAppSwitch(ushort const *)

- ea: `0x18000ffc0`
- end: `0x1800100b4`
- name: `?LogSearchPaneSqmAppSwitch@CSearchServices@@UEAAJPEBG@Z`
- size: `244`
- prototype: `__int64 __fastcall(CSearchServices *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x18000ffc0`
- `0x180015464`
- `0x180015c04`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010024`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001006e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010024`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001006e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchServices::LogSearchPaneSqmAppSwitch(CSearchServices *this, const unsigned __int16 *a2)
{
  BOOL v4; // esi
  int (__fastcall *v5)(CSearchServices *, _QWORD, GUID *, __int64 *); // rbx
  __int64 v7; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-18h]

  v4 = 0;
  v7 = 0;
  v5 = *(int (__fastcall **)(CSearchServices *, _QWORD, GUID *, __int64 *))(*(_QWORD *)this + 40LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v7);
  if ( v5(this, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v7) >= 0 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v10 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"QueryText", 0xAu, 9u);
    v4 = (int)GetKeyFromMapAsString(v7, v10, &string) >= 0 && string;
    WindowsDeleteString(string);
  }
  LogSqmPointForSearchScopeSelection(0, 0, a2, 1, v4);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v7);
  return 0;
}

```

## disassembly

```asm
0x18000ffc0  mov     [rsp-18h+arg_10], rbx
0x18000ffc5  mov     [rsp-18h+arg_18], rsi
0x18000ffca  push    rbp
0x18000ffcb  push    rdi
0x18000ffcc  push    r14
0x18000ffce  mov     rbp, rsp
0x18000ffd1  sub     rsp, 70h
0x18000ffd5  mov     rax, cs:__security_cookie
0x18000ffdc  xor     rax, rsp
0x18000ffdf  mov     [rbp+var_10], rax
0x18000ffe3  mov     r14, rdx
0x18000ffe6  mov     rdi, rcx
0x18000ffe9  xor     esi, esi
0x18000ffeb  mov     [rbp+var_40], rsi
0x18000ffef  mov     rax, [rcx]
0x18000fff2  mov     rbx, [rax+28h]
0x18000fff6  lea     rcx, [rbp+var_40]
0x18000fffa  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18000ffff  lea     r9, [rbp+var_40]
0x180010003  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001000a  xor     edx, edx
0x18001000c  mov     rcx, rdi
0x18001000f  mov     rax, rbx
0x180010012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010017  lea     ebx, [rsi+1]
0x18001001a  test    eax, eax
0x18001001c  js      short loc_180010074
0x18001001e  mov     [rbp+string], rsi
0x180010022  xor     ecx, ecx; string
0x180010024  call    cs:__imp_WindowsDeleteString
0x18001002a  mov     [rbp+string], rsi
0x18001002e  mov     [rbp+var_18], rsi
0x180010032  lea     r9d, [rsi+9]; unsigned int
0x180010036  lea     r8d, [rsi+0Ah]; unsigned int
0x18001003a  lea     rdx, aQuerytext; "QueryText"
0x180010041  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180010045  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001004a  lea     r8, [rbp+string]
0x18001004e  mov     rdx, [rbp+var_18]
0x180010052  mov     rcx, [rbp+var_40]
0x180010056  call    GetKeyFromMapAsString
0x18001005b  mov     rcx, [rbp+string]; string
0x18001005f  test    eax, eax
0x180010061  js      short loc_18001006C
0x180010063  test    rcx, rcx
0x180010066  jz      short loc_18001006C
0x180010068  mov     esi, ebx
0x18001006a  jmp     short loc_18001006E
0x18001006c  xor     esi, esi
0x18001006e  call    cs:__imp_WindowsDeleteString
0x180010074  mov     [rsp+70h+var_50], esi
0x180010078  mov     r9d, ebx
0x18001007b  mov     r8, r14
0x18001007e  xor     edx, edx
0x180010080  xor     ecx, ecx
0x180010082  call    LogSqmPointForSearchScopeSelection
0x180010087  nop
0x180010088  lea     rcx, [rbp+var_40]
0x18001008c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180010091  xor     eax, eax
0x180010093  mov     rcx, [rbp+var_10]
0x180010097  xor     rcx, rsp; StackCookie
0x18001009a  call    __security_check_cookie
0x18001009f  lea     r11, [rsp+70h+var_s0]
0x1800100a4  mov     rbx, [r11+30h]
0x1800100a8  mov     rsi, [r11+38h]
0x1800100ac  mov     rsp, r11
0x1800100af  pop     r14
0x1800100b1  pop     rdi
0x1800100b2  pop     rbp
0x1800100b3  retn
```
