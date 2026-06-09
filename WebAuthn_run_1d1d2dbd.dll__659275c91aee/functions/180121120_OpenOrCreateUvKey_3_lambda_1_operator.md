# _OpenOrCreateUvKey_::_3_::_lambda_1_::operator()

- ea: `0x180121120`
- end: `0x18012127e`
- name: `_OpenOrCreateUvKey_::_3_::_lambda_1_::operator()`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022718`

## callees

- `0x180020614`
- `0x180036da4`
- `0x180121120`
- `0x18013c064`

## import_xrefs

- `ncrypt!NCryptFinalizeKey` at `0x180121258`
- `ncrypt!NCryptFinalizeKey` at `0x180121258`
- `ncrypt!NCryptCreatePersistedKey` at `0x180121166`
- `ncrypt!NCryptCreatePersistedKey` at `0x180121166`
- `ncrypt!NCryptSetProperty` at `0x1801211ca`
- `ncrypt!NCryptSetProperty` at `0x1801211fd`
- `ncrypt!NCryptSetProperty` at `0x180121239`
- `ncrypt!NCryptSetProperty` at `0x1801211ca`
- `ncrypt!NCryptSetProperty` at `0x1801211fd`
- `ncrypt!NCryptSetProperty` at `0x180121239`

## string_xrefs

- `0x18012117c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180121224`: `PinCacheIsGestureRequired`

## pseudocode

```c
__int64 __fastcall OpenOrCreateUvKey_::_3_::_lambda_1_::operator()(__int64 a1, const WCHAR *a2)
{
  NCRYPT_KEY_HANDLE *v3; // rdi
  const WCHAR *v5; // rbx
  SECURITY_STATUS PersistedKey; // ebx
  __int64 v7; // rdx
  NCRYPT_HANDLE *v8; // rcx
  NCRYPT_HANDLE *v9; // rcx
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int pbInput; // [rsp+50h] [rbp+8h] BYREF
  int v14; // [rsp+60h] [rbp+18h] BYREF

  v3 = *(NCRYPT_KEY_HANDLE **)(a1 + 8);
  v5 = **(const WCHAR ***)(a1 + 16);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    v3,
    0);
  PersistedKey = NCryptCreatePersistedKey(**(_QWORD **)a1, v3, a2, v5, 0, 0x80u);
  if ( PersistedKey < 0 )
  {
    v7 = 173;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)PersistedKey,
      dwLegacyKeySpec);
    return (unsigned int)PersistedKey;
  }
  if ( !wcscmp_0(a2, L"RSA") )
  {
    v8 = *(NCRYPT_HANDLE **)(a1 + 8);
    pbInput = 2048;
    PersistedKey = NCryptSetProperty(*v8, L"Length", (PBYTE)&pbInput, 4u, 0);
    if ( PersistedKey < 0 )
    {
      v7 = 182;
      goto LABEL_3;
    }
  }
  PersistedKey = NCryptSetProperty(**(_QWORD **)(a1 + 8), L"HWND Handle", *(PBYTE *)(a1 + 24), 8u, 0);
  if ( PersistedKey < 0 )
  {
    v7 = 190;
    goto LABEL_3;
  }
  v9 = *(NCRYPT_HANDLE **)(a1 + 8);
  v14 = 1;
  PersistedKey = NCryptSetProperty(*v9, L"PinCacheIsGestureRequired", (PBYTE)&v14, 4u, 0);
  if ( PersistedKey < 0 )
  {
    v7 = 198;
    goto LABEL_3;
  }
  PersistedKey = NCryptFinalizeKey(**(_QWORD **)(a1 + 8), 0);
  if ( PersistedKey )
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      *(_QWORD *)(a1 + 8),
      0);
  return (unsigned int)PersistedKey;
}

```

## disassembly

```asm
0x180121120  mov     [rsp+arg_8], rbx
0x180121125  push    rbp
0x180121126  push    rsi
0x180121127  push    rdi
0x180121128  sub     rsp, 30h
0x18012112c  mov     rax, [rcx+10h]
0x180121130  mov     rbp, rdx
0x180121133  mov     rdi, [rcx+8]
0x180121137  mov     rsi, rcx
0x18012113a  xor     edx, edx
0x18012113c  mov     rcx, rdi
0x18012113f  mov     rbx, [rax]
0x180121142  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180121147  mov     rcx, [rsi]
0x18012114a  mov     r9, rbx; pszKeyName
0x18012114d  mov     [rsp+48h+dwFlags], 80h; dwFlags
0x180121155  mov     r8, rbp; pszAlgId
0x180121158  mov     rdx, rdi; phKey
0x18012115b  mov     [rsp+48h+dwLegacyKeySpec], 0; int
0x180121163  mov     rcx, [rcx]; hProvider
0x180121166  call    cs:__imp_NCryptCreatePersistedKey
0x18012116c  mov     ebx, eax
0x18012116e  test    eax, eax
0x180121170  jns     short loc_180121190
0x180121172  mov     edx, 0ADh; void *
0x180121177  mov     rcx, [rsp+48h]; this
0x18012117c  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180121183  mov     r9d, ebx; char *
0x180121186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012118b  jmp     loc_18012126F
0x180121190  lea     rdx, aRsa; "RSA"
0x180121197  mov     rcx, rbp; String1
0x18012119a  call    wcscmp_0
0x18012119f  mov     edi, 4
0x1801211a4  test    eax, eax
0x1801211a6  jnz     short loc_1801211DD
0x1801211a8  mov     rcx, [rsi+8]
0x1801211ac  lea     r8, [rsp+48h+pbInput]; pbInput
0x1801211b1  mov     [rsp+48h+pbInput], 800h
0x1801211b9  lea     rdx, aLength; "Length"
0x1801211c0  mov     r9d, edi; cbInput
0x1801211c3  mov     [rsp+48h+dwLegacyKeySpec], eax; dwFlags
0x1801211c7  mov     rcx, [rcx]; hObject
0x1801211ca  call    cs:__imp_NCryptSetProperty
0x1801211d0  mov     ebx, eax
0x1801211d2  test    eax, eax
0x1801211d4  jns     short loc_1801211DD
0x1801211d6  mov     edx, 0B6h
0x1801211db  jmp     short loc_180121177
0x1801211dd  mov     rcx, [rsi+8]
0x1801211e1  lea     rdx, aHwndHandle; "HWND Handle"
0x1801211e8  mov     r8, [rsi+18h]; pbInput
0x1801211ec  mov     r9d, 8; cbInput
0x1801211f2  mov     [rsp+48h+dwLegacyKeySpec], 0; dwFlags
0x1801211fa  mov     rcx, [rcx]; hObject
0x1801211fd  call    cs:__imp_NCryptSetProperty
0x180121203  mov     ebx, eax
0x180121205  test    eax, eax
0x180121207  jns     short loc_180121213
0x180121209  mov     edx, 0BEh
0x18012120e  jmp     loc_180121177
0x180121213  mov     rcx, [rsi+8]
0x180121217  lea     r8, [rsp+48h+arg_10]; pbInput
0x18012121c  mov     [rsp+48h+arg_10], 1
0x180121224  lea     rdx, aPincacheisgest; "PinCacheIsGestureRequired"
0x18012122b  mov     r9d, edi; cbInput
0x18012122e  mov     [rsp+48h+dwLegacyKeySpec], 0; dwFlags
0x180121236  mov     rcx, [rcx]; hObject
0x180121239  call    cs:__imp_NCryptSetProperty
0x18012123f  mov     ebx, eax
0x180121241  test    eax, eax
0x180121243  jns     short loc_18012124F
0x180121245  mov     edx, 0C6h
0x18012124a  jmp     loc_180121177
0x18012124f  mov     rcx, [rsi+8]
0x180121253  xor     edx, edx; dwFlags
0x180121255  mov     rcx, [rcx]; hKey
0x180121258  call    cs:__imp_NCryptFinalizeKey
0x18012125e  mov     ebx, eax
0x180121260  test    eax, eax
0x180121262  jz      short loc_18012126F
0x180121264  mov     rcx, [rsi+8]
0x180121268  xor     edx, edx
0x18012126a  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18012126f  mov     eax, ebx
0x180121271  mov     rbx, [rsp+48h+arg_8]
0x180121276  add     rsp, 30h
0x18012127a  pop     rdi
0x18012127b  pop     rsi
0x18012127c  pop     rbp
0x18012127d  retn
```
