# FindElementByName(IInspectable *,ushort const *,_GUID const &,void * *)

- ea: `0x180030ba0`
- end: `0x180030cce`
- name: `?FindElementByName@@YAJPEAUIInspectable@@PEBGAEBU_GUID@@PEAPEAX@Z`
- size: `302`
- prototype: `int(struct IInspectable *, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800224e0`
- `0x18002e89c`

## callees

- `0x180007b3c`
- `0x180015ab8`
- `0x180030ba0`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030c4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030c4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030c62`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FindElementByName(
        struct IInspectable *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v9; // ebx
  __int64 v10; // rbx
  void (__fastcall *v11)(__int64, HSTRING, __int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **)); // rdi
  unsigned __int64 v12; // rcx
  UINT32 length; // [rsp+20h] [rbp-40h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, const struct _GUID *, void **); // [rsp+28h] [rbp-38h] BYREF
  __int64 v16; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  *a4 = 0;
  v16 = 0;
  QueryInterface = a1->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
  v9 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a1,
         &GUID_a391d09b_4a99_4b7c_9d8d_6fa5d01f6fbf,
         &v16);
  if ( v9 >= 0 )
  {
    v15 = 0;
    v10 = v16;
    v11 = *(void (__fastcall **)(__int64, HSTRING, __int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **)))(*(_QWORD *)v16 + 408LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
    length = 0;
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    if ( (int)ULongLongToULong(v12, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a2, length, &hstringHeader, &string);
    v11(v10, string, &v15);
    if ( v15 )
      v9 = (**v15)(v15, a3, a4);
    else
      v9 = -2147467262;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180030ba0  push    rbp
0x180030ba2  push    rbx
0x180030ba3  push    rsi
0x180030ba4  push    rdi
0x180030ba5  push    r12
0x180030ba7  push    r14
0x180030ba9  push    r15
0x180030bab  mov     rbp, rsp
0x180030bae  sub     rsp, 60h
0x180030bb2  mov     rax, cs:__security_cookie
0x180030bb9  xor     rax, rsp
0x180030bbc  mov     [rbp+var_8], rax
0x180030bc0  mov     r14, r9
0x180030bc3  mov     r15, r8
0x180030bc6  mov     rsi, rdx
0x180030bc9  mov     rdi, rcx
0x180030bcc  xor     r12d, r12d
0x180030bcf  mov     [r9], r12
0x180030bd2  mov     [rbp+var_30], r12
0x180030bd6  mov     rax, [rcx]
0x180030bd9  mov     rbx, [rax]
0x180030bdc  lea     rcx, [rbp+var_30]
0x180030be0  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030be5  lea     r8, [rbp+var_30]
0x180030be9  lea     rdx, _GUID_a391d09b_4a99_4b7c_9d8d_6fa5d01f6fbf
0x180030bf0  mov     rcx, rdi
0x180030bf3  mov     rax, rbx
0x180030bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bfb  mov     ebx, eax
0x180030bfd  test    eax, eax
0x180030bff  js      loc_180030CA8
0x180030c05  mov     [rbp+var_38], r12
0x180030c09  mov     rbx, [rbp+var_30]
0x180030c0d  mov     rax, [rbx]
0x180030c10  mov     rdi, [rax+198h]
0x180030c17  lea     rcx, [rbp+var_38]
0x180030c1b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030c20  mov     [rbp+length], r12d
0x180030c24  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180030c28  inc     rcx; unsigned __int64
0x180030c2b  cmp     [rsi+rcx*2], r12w
0x180030c30  jnz     short loc_180030C28
0x180030c32  lea     rdx, [rbp+length]; unsigned int *
0x180030c36  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180030c3b  test    eax, eax
0x180030c3d  jns     short loc_180030C54
0x180030c3f  xor     r9d, r9d; lpArguments
0x180030c42  xor     r8d, r8d; nNumberOfArguments
0x180030c45  lea     edx, [r9+1]; dwExceptionFlags
0x180030c49  mov     ecx, 0C000000Dh; dwExceptionCode
0x180030c4e  call    cs:__imp_RaiseException
0x180030c54  lea     r9, [rbp+string]; string
0x180030c58  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180030c5c  mov     edx, [rbp+length]; length
0x180030c5f  mov     rcx, rsi; sourceString
0x180030c62  call    cs:__imp_WindowsCreateStringReference
0x180030c68  lea     r8, [rbp+var_38]
0x180030c6c  mov     rdx, [rbp+string]
0x180030c70  mov     rcx, rbx
0x180030c73  mov     rax, rdi
0x180030c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c7b  mov     rcx, [rbp+var_38]
0x180030c7f  test    rcx, rcx
0x180030c82  jnz     short loc_180030C8B
0x180030c84  mov     ebx, 80004002h
0x180030c89  jmp     short loc_180030C9E
0x180030c8b  mov     rax, [rcx]
0x180030c8e  mov     r8, r14
0x180030c91  mov     rdx, r15
0x180030c94  mov     rax, [rax]
0x180030c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c9c  mov     ebx, eax
0x180030c9e  lea     rcx, [rbp+var_38]
0x180030ca2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030ca7  nop
0x180030ca8  lea     rcx, [rbp+var_30]
0x180030cac  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030cb1  mov     eax, ebx
0x180030cb3  mov     rcx, [rbp+var_8]
0x180030cb7  xor     rcx, rsp; StackCookie
0x180030cba  call    __security_check_cookie
0x180030cbf  add     rsp, 60h
0x180030cc3  pop     r15
0x180030cc5  pop     r14
0x180030cc7  pop     r12
0x180030cc9  pop     rdi
0x180030cca  pop     rsi
0x180030ccb  pop     rbx
0x180030ccc  pop     rbp
0x180030ccd  retn
```
