# _lambda_5c71d807dceb9d902ac043f3fc6b18e9_::operator()

- ea: `0x18007e76c`
- end: `0x18007e8fa`
- name: `_lambda_5c71d807dceb9d902ac043f3fc6b18e9_::operator()`
- size: `398`
- prototype: `char __fastcall(__int64, struct Windows::Foundation::IExtensionRegistration *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a778`

## callees

- `0x180011590`
- `0x180056208`
- `0x180057494`
- `0x18007dd90`
- `0x18007e76c`
- `0x18007ef20`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e7e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007e7e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007e8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e7cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007e7cf`

## string_xrefs

- `0x18007e8be`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x18007e8d3`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x18007e8e8`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`

## pseudocode

```c
char __fastcall lambda_5c71d807dceb9d902ac043f3fc6b18e9_::operator()(
        __int64 a1,
        struct Windows::Foundation::IExtensionRegistration *a2)
{
  int AppIdForExtensionRegistration; // eax
  char v5; // di
  const WCHAR *v6; // rbx
  const WCHAR *StringRawBuffer; // rax
  HSTRING v8; // r8
  __int64 (__fastcall *v9)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v10; // rbx
  int v11; // eax
  __int64 (__fastcall *v12)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *); // rdi
  HSTRING *v13; // rbx
  int v14; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-58h]
  PCWSTR psz1; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HSTRING string; // [rsp+90h] [rbp+18h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  AppIdForExtensionRegistration = GetAppIdForExtensionRegistration(a2, &string, 0);
  if ( AppIdForExtensionRegistration < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
      (const char *)(unsigned int)AppIdForExtensionRegistration,
      bIgnoreCase);
  v5 = 1;
  v6 = **(const WCHAR ***)a1;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, v6, -1, 1) == 2 )
  {
    v8 = **(HSTRING **)(a1 + 8);
    if ( v8 )
    {
      DeserializeExtensionPropertyValue(&psz1, (__int64)a2, v8);
      if ( (unsigned __int8)std::any_of_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_039a2f2bebb10ee393c83a48618d25d2___(psz1) )
      {
        v12 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 72LL);
        v13 = *(HSTRING **)(a1 + 16);
        WindowsDeleteString(*v13);
        *v13 = 0;
        v14 = v12(a2, v13);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x95,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
            (const char *)(unsigned int)v14,
            bIgnoreCasea);
        v5 = 0;
      }
      std::vector<std::wstring>::_Tidy(&psz1);
    }
    else
    {
      v9 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, HSTRING *))(*(_QWORD *)a2 + 72LL);
      v10 = *(HSTRING **)(a1 + 16);
      WindowsDeleteString(*v10);
      *v10 = 0;
      v11 = v9(a2, v10);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
          (const char *)(unsigned int)v11,
          bIgnoreCasea);
      v5 = 0;
    }
  }
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x18007e76c  mov     rax, rsp
0x18007e76f  push    rbx
0x18007e770  push    rsi
0x18007e771  push    rdi
0x18007e772  push    r14
0x18007e774  sub     rsp, 58h
0x18007e778  mov     rsi, rdx
0x18007e77b  mov     r14, rcx
0x18007e77e  mov     qword ptr [rax+18h], 0
0x18007e786  xor     ecx, ecx; string
0x18007e788  call    cs:__imp_WindowsDeleteString
0x18007e78e  mov     [rsp+78h+string], 0
0x18007e79a  xor     r8d, r8d; HSTRING *
0x18007e79d  lea     rdx, [rsp+78h+string]; HSTRING *
0x18007e7a5  mov     rcx, rsi; struct Windows::Foundation::IExtensionRegistration *
0x18007e7a8  call    ?GetAppIdForExtensionRegistration@@YAJPEAUIExtensionRegistration@Foundation@Windows@@PEAPEAUHSTRING__@@1@Z; GetAppIdForExtensionRegistration(Windows::Foundation::IExtensionRegistration *,HSTRING__ * *,HSTRING__ * *)
0x18007e7ad  mov     rcx, [rsp+78h]; this
0x18007e7b2  test    eax, eax
0x18007e7b4  js      loc_18007E8D0
0x18007e7ba  mov     edi, 1
0x18007e7bf  mov     rax, [r14]
0x18007e7c2  mov     rbx, [rax]
0x18007e7c5  xor     edx, edx; length
0x18007e7c7  mov     rcx, [rsp+78h+string]; string
0x18007e7cf  call    cs:__imp_WindowsGetStringRawBuffer
0x18007e7d5  mov     [rsp+78h+bIgnoreCase], edi; int
0x18007e7d9  or      edx, 0FFFFFFFFh; cchCount1
0x18007e7dc  mov     r9d, edx; cchCount2
0x18007e7df  mov     r8, rbx; lpString2
0x18007e7e2  mov     rcx, rax; lpString1
0x18007e7e5  call    cs:__imp_CompareStringOrdinal
0x18007e7eb  cmp     eax, 2
0x18007e7ee  jnz     loc_18007E8A0
0x18007e7f4  mov     rax, [r14+8]
0x18007e7f8  mov     r8, [rax]
0x18007e7fb  test    r8, r8
0x18007e7fe  jnz     short loc_18007E83B
0x18007e800  mov     rax, [rsi]
0x18007e803  mov     rdi, [rax+48h]
0x18007e807  mov     rbx, [r14+10h]
0x18007e80b  mov     rcx, [rbx]; string
0x18007e80e  call    cs:__imp_WindowsDeleteString
0x18007e814  mov     qword ptr [rbx], 0
0x18007e81b  mov     rdx, rbx
0x18007e81e  mov     rcx, rsi
0x18007e821  mov     rax, rdi
0x18007e824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e829  mov     rcx, [rsp+78h]; this
0x18007e82e  test    eax, eax
0x18007e830  js      loc_18007E8E5
0x18007e836  xor     dil, dil
0x18007e839  jmp     short loc_18007E8A0
0x18007e83b  mov     rdx, rsi
0x18007e83e  lea     rcx, [rsp+78h+psz1]
0x18007e843  call    DeserializeExtensionPropertyValue
0x18007e848  nop
0x18007e849  mov     r8, [r14+18h]
0x18007e84d  mov     rdx, [rsp+78h+var_40]
0x18007e852  mov     rcx, [rsp+78h+psz1]; psz1
0x18007e857  call    std__any_of_std___Vector_const_iterator_std___Vector_val_std___Simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_039a2f2bebb10ee393c83a48618d25d2___
0x18007e85c  test    al, al
0x18007e85e  jz      short loc_18007E895
0x18007e860  mov     rax, [rsi]
0x18007e863  mov     rdi, [rax+48h]
0x18007e867  mov     rbx, [r14+10h]
0x18007e86b  mov     rcx, [rbx]; string
0x18007e86e  call    cs:__imp_WindowsDeleteString
0x18007e874  mov     qword ptr [rbx], 0
0x18007e87b  mov     rdx, rbx
0x18007e87e  mov     rcx, rsi
0x18007e881  mov     rax, rdi
0x18007e884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e889  mov     rcx, [rsp+78h]; this
0x18007e88e  test    eax, eax
0x18007e890  js      short loc_18007E8BB
0x18007e892  xor     dil, dil
0x18007e895  lea     rcx, [rsp+78h+psz1]
0x18007e89a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18007e89f  nop
0x18007e8a0  mov     rcx, [rsp+78h+string]; string
0x18007e8a8  call    cs:__imp_WindowsDeleteString
0x18007e8ae  mov     al, dil
0x18007e8b1  add     rsp, 58h
0x18007e8b5  pop     r14
0x18007e8b7  pop     rdi
0x18007e8b8  pop     rsi
0x18007e8b9  pop     rbx
0x18007e8ba  retn
0x18007e8bb  mov     r9d, eax; char *
0x18007e8be  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007e8c5  mov     edx, 95h; void *
0x18007e8ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e8d0  mov     r9d, eax; char *
0x18007e8d3  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007e8da  mov     edx, 80h; void *
0x18007e8df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e8e5  mov     r9d, eax; char *
0x18007e8e8  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007e8ef  mov     edx, 86h; void *
0x18007e8f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
