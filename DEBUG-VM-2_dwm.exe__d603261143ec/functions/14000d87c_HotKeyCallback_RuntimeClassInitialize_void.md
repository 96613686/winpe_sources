# HotKeyCallback::RuntimeClassInitialize(void)

- ea: `0x14000d87c`
- end: `0x14000da18`
- name: `?RuntimeClassInitialize@HotKeyCallback@@QEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(HotKeyCallback *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c514`

## callees

- `0x140004a94`
- `0x140005530`
- `0x14000d804`
- `0x14000d87c`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000d910`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000d910`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000d935`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000d935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000d8fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000d8fa`
- `CoreMessaging!CoreUICreate` at `0x14000d8c2`
- `CoreMessaging!CoreUICreate` at `0x14000d8c2`

## pseudocode

```c
__int64 __fastcall HotKeyCallback::RuntimeClassInitialize(HotKeyCallback *this)
{
  _QWORD *v1; // rbx
  __int64 v3; // rcx
  int v4; // edi
  HRESULT v5; // eax
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // r14
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(_QWORD *, HotKeyCallback *, _QWORD, char *); // rbp
  int v14; // eax
  int v15; // esi
  int v17; // [rsp+20h] [rbp-58h]
  char v18; // [rsp+20h] [rbp-58h]
  _QWORD *v19; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = (_QWORD *)((char *)this + 40);
  v3 = *((_QWORD *)this + 5);
  *v1 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = CoreUICreate(v1);
  if ( v4 >= 0 )
  {
    v19 = 0;
    string = 0;
    v5 = WindowsCreateStringReference(L"Windows.UI.Internal.Text.HotKeyClient", 0x25u, &hstringHeader, &string);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      __debugbreak();
    }
    v6 = string;
    Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(&v19);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_85c277be_f4a0_4e27_b776_ebc75727e67a, &v19);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwm\\apphost\\hotkeycallback.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v17);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(&v19);
      return v8;
    }
    v9 = v19;
    v10 = (_QWORD *)((char *)this + 32);
    v11 = *((_QWORD *)this + 4);
    v12 = *v19;
    *((_QWORD *)this + 4) = 0;
    v13 = *(__int64 (__fastcall **)(_QWORD *, HotKeyCallback *, _QWORD, char *))(v12 + 48);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v14 = v13(v9, this, 0, (char *)this + 32);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwm\\apphost\\hotkeycallback.cpp",
        (const char *)(unsigned int)v14,
        v17);
      v8 = v15;
      goto LABEL_12;
    }
    v18 = 0;
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64, char))(*(_QWORD *)*v10 + 48LL))(*v10, 0, 16398, 66, v18);
    Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(&v19);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000d87c  mov     [rsp+arg_8], rbx
0x14000d881  mov     [rsp+arg_10], rbp
0x14000d886  push    rsi
0x14000d887  push    rdi
0x14000d888  push    r14
0x14000d88a  sub     rsp, 60h
0x14000d88e  mov     rax, cs:__security_cookie
0x14000d895  xor     rax, rsp
0x14000d898  mov     [rsp+78h+var_20], rax
0x14000d89d  lea     rbx, [rcx+28h]
0x14000d8a1  mov     rsi, rcx
0x14000d8a4  mov     rcx, [rbx]
0x14000d8a7  mov     qword ptr [rbx], 0
0x14000d8ae  test    rcx, rcx
0x14000d8b1  jz      short loc_14000D8BF
0x14000d8b3  mov     rax, [rcx]
0x14000d8b6  mov     rax, [rax+10h]
0x14000d8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d8bf  mov     rcx, rbx
0x14000d8c2  call    cs:__imp_CoreUICreate
0x14000d8c8  mov     edi, eax
0x14000d8ca  test    eax, eax
0x14000d8cc  js      loc_14000D9F4
0x14000d8d2  lea     r9, [rsp+78h+string]; string
0x14000d8d7  mov     [rsp+78h+var_48], 0
0x14000d8e0  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x14000d8e5  mov     [rsp+78h+string], 0
0x14000d8ee  mov     edx, 25h ; '%'; length
0x14000d8f3  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Text_HotKeyClient@@3QBGB; "Windows.UI.Internal.Text.HotKeyClient"
0x14000d8fa  call    cs:__imp_WindowsCreateStringReference
0x14000d900  test    eax, eax
0x14000d902  jns     short loc_14000D917
0x14000d904  xor     r9d, r9d; lpArguments
0x14000d907  xor     r8d, r8d; nNumberOfArguments
0x14000d90a  mov     ecx, eax; dwExceptionCode
0x14000d90c  lea     edx, [r9+1]; dwExceptionFlags
0x14000d910  call    cs:__imp_RaiseException
0x14000d916  int     3; Trap to Debugger
0x14000d917  mov     rbx, [rsp+78h+string]
0x14000d91c  lea     rcx, [rsp+78h+var_48]
0x14000d921  call    ?InternalRelease@?$ComPtr@UIHotKeyClientStatics@Text@Internal@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(void)
0x14000d926  lea     r8, [rsp+78h+var_48]
0x14000d92b  mov     rcx, rbx
0x14000d92e  lea     rdx, _GUID_85c277be_f4a0_4e27_b776_ebc75727e67a
0x14000d935  call    cs:__imp_RoGetActivationFactory
0x14000d93b  mov     ebx, eax
0x14000d93d  test    eax, eax
0x14000d93f  jns     short loc_14000D95C
0x14000d941  mov     rcx, [rsp+78h]; this
0x14000d946  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\dwm\\apphost"...
0x14000d94d  mov     r9d, eax; char *
0x14000d950  mov     edx, 17h; void *
0x14000d955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d95a  jmp     short loc_14000D9BC
0x14000d95c  mov     r14, [rsp+78h+var_48]
0x14000d961  lea     rbx, [rsi+20h]
0x14000d965  mov     rcx, [rbx]
0x14000d968  mov     rax, [r14]
0x14000d96b  mov     qword ptr [rbx], 0
0x14000d972  mov     rbp, [rax+30h]
0x14000d976  test    rcx, rcx
0x14000d979  jz      short loc_14000D987
0x14000d97b  mov     r8, [rcx]
0x14000d97e  mov     rax, [r8+10h]
0x14000d982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d987  mov     r9, rbx
0x14000d98a  xor     r8d, r8d
0x14000d98d  mov     rdx, rsi
0x14000d990  mov     rcx, r14
0x14000d993  mov     rax, rbp
0x14000d996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d99b  mov     esi, eax
0x14000d99d  test    eax, eax
0x14000d99f  jns     short loc_14000D9CA
0x14000d9a1  mov     rcx, [rsp+78h]; this
0x14000d9a6  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\dwm\\apphost"...
0x14000d9ad  mov     r9d, eax; char *
0x14000d9b0  mov     edx, 18h; void *
0x14000d9b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d9ba  mov     ebx, esi
0x14000d9bc  lea     rcx, [rsp+78h+var_48]
0x14000d9c1  call    ?InternalRelease@?$ComPtr@UIHotKeyClientStatics@Text@Internal@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(void)
0x14000d9c6  mov     eax, ebx
0x14000d9c8  jmp     short loc_14000D9F6
0x14000d9ca  mov     rcx, [rbx]
0x14000d9cd  xor     edx, edx
0x14000d9cf  mov     r8d, 400Eh
0x14000d9d5  mov     byte ptr [rsp+78h+var_58], 0
0x14000d9da  mov     rax, [rcx]
0x14000d9dd  lea     r9d, [rdx+42h]
0x14000d9e1  mov     rax, [rax+30h]
0x14000d9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9ea  lea     rcx, [rsp+78h+var_48]
0x14000d9ef  call    ?InternalRelease@?$ComPtr@UIHotKeyClientStatics@Text@Internal@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Internal::Text::IHotKeyClientStatics>::InternalRelease(void)
0x14000d9f4  mov     eax, edi
0x14000d9f6  mov     rcx, [rsp+78h+var_20]
0x14000d9fb  xor     rcx, rsp; StackCookie
0x14000d9fe  call    __security_check_cookie
0x14000da03  lea     r11, [rsp+78h+var_18]
0x14000da08  mov     rbx, [r11+28h]
0x14000da0c  mov     rbp, [r11+30h]
0x14000da10  mov     rsp, r11
0x14000da13  pop     r14
0x14000da15  pop     rdi
0x14000da16  pop     rsi
0x14000da17  retn
```
