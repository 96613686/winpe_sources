# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x180064a40`
- end: `0x180064b32`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800647e0`

## callees

- `0x180007f68`
- `0x180011ffc`
- `0x180064a40`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064b04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064b04`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetResourceStringById(
        unsigned __int16 *a1,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap *a2,
        HSTRING *a3)
{
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *); // rbx
  __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rdi
  HSTRING v10; // rax
  HSTRING v11; // rcx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF

  string = (HSTRING)a1;
  *a3 = 0;
  v14 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader);
  v7 = v5(a2, *(_QWORD *)(v6 + 24), &v14);
  if ( v7 >= 0 )
  {
    v8 = v14;
    if ( v14 )
    {
      string = 0;
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 80LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v9(v8, &string);
      if ( v7 < 0 )
      {
        v11 = string;
      }
      else
      {
        v10 = string;
        v11 = 0;
        string = 0;
        *a3 = v10;
      }
      WindowsDeleteString(v11);
    }
    else
    {
      v7 = -2147024893;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180064a40  mov     [rsp-18h+arg_18], rbx
0x180064a45  push    rbp
0x180064a46  push    rsi
0x180064a47  push    rdi
0x180064a48  mov     rbp, rsp
0x180064a4b  sub     rsp, 60h
0x180064a4f  mov     rax, cs:__security_cookie
0x180064a56  xor     rax, rsp
0x180064a59  mov     [rbp+var_10], rax
0x180064a5d  mov     rsi, r8
0x180064a60  mov     rdi, rdx
0x180064a63  mov     [rbp+string], rcx
0x180064a67  mov     qword ptr [r8], 0
0x180064a6e  mov     [rbp+var_38], 0
0x180064a76  mov     rax, [rdx]
0x180064a79  mov     rbx, [rax+38h]
0x180064a7d  lea     rcx, [rbp+var_38]
0x180064a81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064a86  lea     rdx, [rbp+string]
0x180064a8a  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180064a8e  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x180064a93  nop
0x180064a94  lea     r8, [rbp+var_38]
0x180064a98  mov     rdx, [rax+18h]
0x180064a9c  mov     rcx, rdi
0x180064a9f  mov     rax, rbx
0x180064aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064aa7  mov     ebx, eax
0x180064aa9  test    eax, eax
0x180064aab  js      short loc_180064B0B
0x180064aad  mov     rbx, [rbp+var_38]
0x180064ab1  test    rbx, rbx
0x180064ab4  jnz     short loc_180064ABD
0x180064ab6  mov     ebx, 80070003h
0x180064abb  jmp     short loc_180064B0B
0x180064abd  mov     [rbp+string], 0
0x180064ac5  mov     rax, [rbx]
0x180064ac8  mov     rdi, [rax+50h]
0x180064acc  xor     ecx, ecx; string
0x180064ace  call    cs:__imp_WindowsDeleteString
0x180064ad4  mov     [rbp+string], 0
0x180064adc  lea     rdx, [rbp+string]
0x180064ae0  mov     rcx, rbx
0x180064ae3  mov     rax, rdi
0x180064ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064aeb  mov     ebx, eax
0x180064aed  test    eax, eax
0x180064aef  js      short loc_180064B00
0x180064af1  mov     rax, [rbp+string]
0x180064af5  xor     ecx, ecx
0x180064af7  mov     [rbp+string], rcx
0x180064afb  mov     [rsi], rax
0x180064afe  jmp     short loc_180064B04
0x180064b00  mov     rcx, [rbp+string]; string
0x180064b04  call    cs:__imp_WindowsDeleteString
0x180064b0a  nop
0x180064b0b  lea     rcx, [rbp+var_38]
0x180064b0f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064b14  mov     eax, ebx
0x180064b16  mov     rcx, [rbp+var_10]
0x180064b1a  xor     rcx, rsp; StackCookie
0x180064b1d  call    __security_check_cookie
0x180064b22  mov     rbx, [rsp+60h+arg_18]
0x180064b2a  add     rsp, 60h
0x180064b2e  pop     rdi
0x180064b2f  pop     rsi
0x180064b30  pop     rbp
0x180064b31  retn
```
