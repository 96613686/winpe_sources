# IsPackageFamilyNameInList

- ea: `0x1801d27f8`
- end: `0x1801d29ab`
- name: `IsPackageFamilyNameInList`
- size: `435`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180084ce0`
- `0x1800853e0`
- `0x18014b0c0`

## callees

- `0x180003e54`
- `0x18001a9e0`
- `0x1801d27f8`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801d28f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801d28f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d28ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d28ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d2955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d28d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d28d5`

## string_xrefs

- `0x1801d2841`: `onecore\base\appmodel\staterepository\winrt\client\lib\windows.internal.staterepository.appurihandlerfactory-custom.cpp`
- `0x1801d293f`: `onecore\base\appmodel\staterepository\winrt\client\lib\windows.internal.staterepository.appurihandlerfactory-custom.cpp`
- `0x1801d296c`: `onecore\base\appmodel\staterepository\winrt\client\lib\windows.internal.staterepository.appurihandlerfactory-custom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsPackageFamilyNameInList(LPCWCH lpString1, __int64 a2, _BYTE *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int i; // esi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  const WCHAR *StringRawBuffer; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  _QWORD v17[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v19; // [rsp+78h] [rbp+38h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v19);
  v7 = v6;
  if ( v6 >= 0 )
  {
    for ( i = 0; i < v19; ++i )
    {
      v17[0] = 0;
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)a2 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
      v11 = v10(a2, i, v17);
      v7 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.a"
                        "ppurihandlerfactory-custom.cpp",
          (const char *)(unsigned int)v11,
          bIgnoreCase);
        goto LABEL_13;
      }
      string = 0;
      v12 = v17[0];
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17[0] + 104LL);
      WindowsDeleteString(0);
      string = 0;
      v14 = v13(v12, &string);
      v7 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.a"
                        "ppurihandlerfactory-custom.cpp",
          (const char *)(unsigned int)v14,
          bIgnoreCase);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_13;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(lpString1, -1, StringRawBuffer, -1, 1) == 2 )
      {
        *a3 = 1;
        WindowsDeleteString(string);
        string = 0;
        v7 = 0;
LABEL_13:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
        return v7;
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
    }
    *a3 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.appur"
                    "ihandlerfactory-custom.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
    return v7;
  }
}

```

## disassembly

```asm
0x1801d27f8  mov     [rsp-28h+arg_0], rbx
0x1801d27fd  mov     [rsp-28h+arg_10], rsi
0x1801d2802  push    rbp
0x1801d2803  push    rdi
0x1801d2804  push    r12
0x1801d2806  push    r14
0x1801d2808  push    r15
0x1801d280a  mov     rbp, rsp
0x1801d280d  sub     rsp, 40h
0x1801d2811  mov     r14, r8
0x1801d2814  mov     r15, rdx
0x1801d2817  mov     r12, rcx
0x1801d281a  mov     [rbp+arg_8], 0
0x1801d2821  mov     rax, [rdx]
0x1801d2824  lea     rdx, [rbp+arg_8]
0x1801d2828  mov     rcx, r15
0x1801d282b  mov     rax, [rax+38h]
0x1801d282f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d2834  mov     ebx, eax
0x1801d2836  test    eax, eax
0x1801d2838  jns     short loc_1801D2859
0x1801d283a  mov     rcx, [rbp+28h]; this
0x1801d283e  mov     r9d, eax; char *
0x1801d2841  lea     r8, aOnecoreBaseApp_152; "onecore\\base\\appmodel\\staterepositor"...
0x1801d2848  mov     edx, 72h ; 'r'; void *
0x1801d284d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d2852  mov     eax, ebx
0x1801d2854  jmp     loc_1801D2992
0x1801d2859  xor     esi, esi
0x1801d285b  cmp     esi, [rbp+arg_8]
0x1801d285e  jnb     loc_1801D298C
0x1801d2864  mov     [rbp+var_10], 0
0x1801d286c  mov     rax, [r15]
0x1801d286f  mov     rbx, [rax+30h]
0x1801d2873  lea     rcx, [rbp+var_10]
0x1801d2877  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d287c  lea     r8, [rbp+var_10]
0x1801d2880  mov     edx, esi
0x1801d2882  mov     rcx, r15
0x1801d2885  mov     rax, rbx
0x1801d2888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d288d  mov     ebx, eax
0x1801d288f  test    eax, eax
0x1801d2891  js      loc_1801D2965
0x1801d2897  mov     [rbp+string], 0
0x1801d289f  mov     rdi, [rbp+var_10]
0x1801d28a3  mov     rax, [rdi]
0x1801d28a6  mov     rbx, [rax+68h]
0x1801d28aa  xor     ecx, ecx; string
0x1801d28ac  call    cs:__imp_WindowsDeleteString
0x1801d28b2  mov     [rbp+string], 0
0x1801d28ba  lea     rdx, [rbp+string]
0x1801d28be  mov     rcx, rdi
0x1801d28c1  mov     rax, rbx
0x1801d28c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d28c9  mov     ebx, eax
0x1801d28cb  test    eax, eax
0x1801d28cd  js      short loc_1801D2938
0x1801d28cf  xor     edx, edx; length
0x1801d28d1  mov     rcx, [rbp+string]; string
0x1801d28d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d28db  mov     r8, rax; lpString2
0x1801d28de  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x1801d28e6  or      ebx, 0FFFFFFFFh
0x1801d28e9  mov     r9d, ebx; cchCount2
0x1801d28ec  mov     edx, ebx; cchCount1
0x1801d28ee  mov     rcx, r12; lpString1
0x1801d28f1  call    cs:__imp_CompareStringOrdinal
0x1801d28f7  cmp     eax, 2
0x1801d28fa  jz      short loc_1801D291E
0x1801d28fc  mov     rcx, [rbp+string]; string
0x1801d2900  call    cs:__imp_WindowsDeleteString
0x1801d2906  mov     [rbp+string], 0
0x1801d290e  lea     rcx, [rbp+var_10]
0x1801d2912  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d2917  inc     esi
0x1801d2919  jmp     loc_1801D285B
0x1801d291e  mov     byte ptr [r14], 1
0x1801d2922  mov     rcx, [rbp+string]; string
0x1801d2926  call    cs:__imp_WindowsDeleteString
0x1801d292c  mov     [rbp+string], 0
0x1801d2934  xor     ebx, ebx
0x1801d2936  jmp     short loc_1801D297E
0x1801d2938  mov     rcx, [rbp+28h]; this
0x1801d293c  mov     r9d, eax; char *
0x1801d293f  lea     r8, aOnecoreBaseApp_152; "onecore\\base\\appmodel\\staterepositor"...
0x1801d2946  mov     edx, 78h ; 'x'; void *
0x1801d294b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d2950  nop
0x1801d2951  mov     rcx, [rbp+string]; string
0x1801d2955  call    cs:__imp_WindowsDeleteString
0x1801d295b  mov     [rbp+string], 0
0x1801d2963  jmp     short loc_1801D297E
0x1801d2965  mov     rcx, [rbp+28h]; this
0x1801d2969  mov     r9d, eax; char *
0x1801d296c  lea     r8, aOnecoreBaseApp_152; "onecore\\base\\appmodel\\staterepositor"...
0x1801d2973  mov     edx, 76h ; 'v'; void *
0x1801d2978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d297d  nop
0x1801d297e  lea     rcx, [rbp+var_10]
0x1801d2982  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d2987  jmp     loc_1801D2852
0x1801d298c  mov     byte ptr [r14], 0
0x1801d2990  xor     eax, eax
0x1801d2992  lea     r11, [rsp+40h+var_s0]
0x1801d2997  mov     rbx, [r11+30h]
0x1801d299b  mov     rsi, [r11+40h]
0x1801d299f  mov     rsp, r11
0x1801d29a2  pop     r15
0x1801d29a4  pop     r14
0x1801d29a6  pop     r12
0x1801d29a8  pop     rdi
0x1801d29a9  pop     rbp
0x1801d29aa  retn
```
