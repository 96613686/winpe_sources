# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x1800145b0`
- end: `0x1800146a2`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800146a8`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x18000cb8c`
- `0x1800145b0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001463e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014674`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001463e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014674`

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
  _BYTE v15[32]; // [rsp+30h] [rbp-30h] BYREF

  string = (HSTRING)a1;
  *a3 = 0;
  v14 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v15, &string);
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
0x1800145b0  mov     [rsp-18h+arg_18], rbx
0x1800145b5  push    rbp
0x1800145b6  push    rsi
0x1800145b7  push    rdi
0x1800145b8  mov     rbp, rsp
0x1800145bb  sub     rsp, 60h
0x1800145bf  mov     rax, cs:__security_cookie
0x1800145c6  xor     rax, rsp
0x1800145c9  mov     [rbp+var_10], rax
0x1800145cd  mov     rsi, r8
0x1800145d0  mov     rdi, rdx
0x1800145d3  mov     [rbp+string], rcx
0x1800145d7  mov     qword ptr [r8], 0
0x1800145de  mov     [rbp+var_38], 0
0x1800145e6  mov     rax, [rdx]
0x1800145e9  mov     rbx, [rax+38h]
0x1800145ed  lea     rcx, [rbp+var_38]
0x1800145f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800145f6  lea     rdx, [rbp+string]
0x1800145fa  lea     rcx, [rbp+var_30]
0x1800145fe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180014603  nop
0x180014604  lea     r8, [rbp+var_38]
0x180014608  mov     rdx, [rax+18h]
0x18001460c  mov     rcx, rdi
0x18001460f  mov     rax, rbx
0x180014612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014617  mov     ebx, eax
0x180014619  test    eax, eax
0x18001461b  js      short loc_18001467B
0x18001461d  mov     rbx, [rbp+var_38]
0x180014621  test    rbx, rbx
0x180014624  jnz     short loc_18001462D
0x180014626  mov     ebx, 80070003h
0x18001462b  jmp     short loc_18001467B
0x18001462d  mov     [rbp+string], 0
0x180014635  mov     rax, [rbx]
0x180014638  mov     rdi, [rax+50h]
0x18001463c  xor     ecx, ecx; string
0x18001463e  call    cs:__imp_WindowsDeleteString
0x180014644  mov     [rbp+string], 0
0x18001464c  lea     rdx, [rbp+string]
0x180014650  mov     rcx, rbx
0x180014653  mov     rax, rdi
0x180014656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001465b  mov     ebx, eax
0x18001465d  test    eax, eax
0x18001465f  js      short loc_180014670
0x180014661  mov     rax, [rbp+string]
0x180014665  xor     ecx, ecx
0x180014667  mov     [rbp+string], rcx
0x18001466b  mov     [rsi], rax
0x18001466e  jmp     short loc_180014674
0x180014670  mov     rcx, [rbp+string]; string
0x180014674  call    cs:__imp_WindowsDeleteString
0x18001467a  nop
0x18001467b  lea     rcx, [rbp+var_38]
0x18001467f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014684  mov     eax, ebx
0x180014686  mov     rcx, [rbp+var_10]
0x18001468a  xor     rcx, rsp; StackCookie
0x18001468d  call    __security_check_cookie
0x180014692  mov     rbx, [rsp+60h+arg_18]
0x18001469a  add     rsp, 60h
0x18001469e  pop     rdi
0x18001469f  pop     rsi
0x1800146a0  pop     rbp
0x1800146a1  retn
```
