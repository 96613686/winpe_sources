# CSpellContextHandler::CreateCommandSeparator(void)

- ea: `0x180273efc`
- end: `0x180273fa8`
- name: `?CreateCommandSeparator@CSpellContextHandler@@AEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(CSpellContextHandler *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180274678`
- `0x18027494c`

## callees

- `0x180048d5c`
- `0x18013bad0`
- `0x1802734bc`
- `0x180273efc`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180273f4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180273f4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180273f36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180273f36`

## string_xrefs

- `0x180273f22`: `Windows.UI.Popups.UICommandSeparator`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::CreateCommandSeparator(CSpellContextHandler *this)
{
  int v2; // ebx
  __int64 v4; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v5; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER v6; // [rsp+30h] [rbp-28h] BYREF

  v4 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Popups.UICommandSeparator", 0x24u, &v6, &v5) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(v5, &v4);
  if ( v2 >= 0 )
    v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 18) + 104LL))(*((_QWORD *)this + 18), v4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180273efc  mov     r11, rsp
0x180273eff  mov     [r11+10h], rbx
0x180273f03  push    rdi
0x180273f04  sub     rsp, 50h
0x180273f08  mov     rax, cs:__security_cookie
0x180273f0f  xor     rax, rsp
0x180273f12  mov     [rsp+58h+var_10], rax
0x180273f17  mov     rdi, rcx
0x180273f1a  mov     qword ptr [r11-38h], 0
0x180273f22  lea     rcx, ?RuntimeClass_Windows_UI_Popups_UICommandSeparator@@3QBGB; "Windows.UI.Popups.UICommandSeparator"
0x180273f29  mov     edx, 24h ; '$'; length
0x180273f2e  lea     r9, [r11-30h]; string
0x180273f32  lea     r8, [r11-28h]; hstringHeader
0x180273f36  call    cs:__imp_WindowsCreateStringReference
0x180273f3c  test    eax, eax
0x180273f3e  jns     short loc_180273F55
0x180273f40  xor     r9d, r9d; lpArguments
0x180273f43  xor     r8d, r8d; nNumberOfArguments
0x180273f46  mov     ecx, 0C000000Dh; dwExceptionCode
0x180273f4b  lea     edx, [r9+1]; dwExceptionFlags
0x180273f4f  call    cs:__imp_RaiseException
0x180273f55  mov     rcx, [rsp+58h+var_30]
0x180273f5a  lea     rdx, [rsp+58h+var_38]
0x180273f5f  call    ??$ActivateInstance@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUICommand@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IUICommand>>)
0x180273f64  mov     ebx, eax
0x180273f66  test    eax, eax
0x180273f68  js      short loc_180273F84
0x180273f6a  mov     rcx, [rdi+90h]
0x180273f71  mov     rdx, [rsp+58h+var_38]
0x180273f76  mov     rax, [rcx]
0x180273f79  mov     rax, [rax+68h]
0x180273f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273f82  mov     ebx, eax
0x180273f84  lea     rcx, [rsp+58h+var_38]
0x180273f89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180273f8e  mov     eax, ebx
0x180273f90  mov     rcx, [rsp+58h+var_10]
0x180273f95  xor     rcx, rsp; StackCookie
0x180273f98  call    __security_check_cookie
0x180273f9d  mov     rbx, [rsp+58h+arg_8]
0x180273fa2  add     rsp, 50h
0x180273fa6  pop     rdi
0x180273fa7  retn
```
