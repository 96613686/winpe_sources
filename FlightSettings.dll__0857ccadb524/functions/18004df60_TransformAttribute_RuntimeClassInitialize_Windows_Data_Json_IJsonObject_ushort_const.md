# TransformAttribute::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *,ushort const *)

- ea: `0x18004df60`
- end: `0x18004e108`
- name: `?RuntimeClassInitialize@TransformAttribute@@QEAAJPEAUIJsonObject@Json@Data@Windows@@PEBG@Z`
- size: `424`
- prototype: `int(TransformAttribute *__hidden this, struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b6c4`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x18004df60`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004dfdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e0a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004dfdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e0a3`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18004e061`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18004e061`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e0b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e0b7`

## string_xrefs

- `0x18004e038`: `onecore\base\flighting\flightsettings\broker\libs\ctac\transformattribute.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TransformAttribute::RuntimeClassInitialize(
        TransformAttribute *this,
        struct Windows::Data::Json::IJsonObject *a2,
        const unsigned __int16 *a3)
{
  int (__fastcall *v6)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *); // r15
  char *v7; // r14
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  const WCHAR *v12; // rbx
  __int64 (__fastcall *v13)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *); // r15
  int v14; // eax
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v18; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER v19; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( !a2 )
    return 2147500035LL;
  v6 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *))(*(_QWORD *)a2 + 64LL);
  v7 = (char *)this + 16;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 16);
  length = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  if ( (int)ULongLongToUInt(v9, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a3, length, &hstringHeader, &string);
  if ( v6(a2, string, v7) < 0 )
  {
    string = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
    v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &string,
            a3,
            -1);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\transformattribute.cpp",
        (const char *)(unsigned int)v10,
        length);
LABEL_16:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
      return v11;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&string);
    v12 = (const WCHAR *)string;
    CharLowerBuffW((LPWSTR)string, (DWORD)hstringHeader.Reserved.Reserved1);
    v13 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *))(*(_QWORD *)a2 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v7);
    length = 0;
    do
      ++v8;
    while ( v12[v8] );
    if ( (int)ULongLongToUInt(v8, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(v12, length, &v19, &v18);
    v14 = v13(a2, v18, v7);
    if ( v14 < 0 )
    {
      v11 = v14;
      goto LABEL_16;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
  }
  return 0;
}

```

## disassembly

```asm
0x18004df60  push    rbp
0x18004df62  push    rbx
0x18004df63  push    rsi
0x18004df64  push    rdi
0x18004df65  push    r12
0x18004df67  push    r14
0x18004df69  push    r15
0x18004df6b  mov     rbp, rsp
0x18004df6e  sub     rsp, 70h
0x18004df72  mov     rax, cs:__security_cookie
0x18004df79  xor     rax, rsp
0x18004df7c  mov     [rbp+var_8], rax
0x18004df80  mov     rbx, r8
0x18004df83  mov     rsi, rdx
0x18004df86  xor     r12d, r12d
0x18004df89  test    rdx, rdx
0x18004df8c  jnz     short loc_18004DF98
0x18004df8e  mov     eax, 80004003h
0x18004df93  jmp     loc_18004E0ED
0x18004df98  mov     rax, [rdx]
0x18004df9b  mov     r15, [rax+40h]
0x18004df9f  lea     r14, [rcx+10h]
0x18004dfa3  mov     rcx, r14
0x18004dfa6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004dfab  mov     [rbp+length], r12d
0x18004dfaf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004dfb3  mov     rcx, rdi
0x18004dfb6  inc     rcx; unsigned __int64
0x18004dfb9  cmp     [rbx+rcx*2], r12w
0x18004dfbe  jnz     short loc_18004DFB6
0x18004dfc0  lea     rdx, [rbp+length]; unsigned int *
0x18004dfc4  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004dfc9  test    eax, eax
0x18004dfcb  jns     short loc_18004DFE2
0x18004dfcd  xor     r9d, r9d; lpArguments
0x18004dfd0  xor     r8d, r8d; nNumberOfArguments
0x18004dfd3  lea     edx, [r9+1]; dwExceptionFlags
0x18004dfd7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004dfdc  call    cs:__imp_RaiseException
0x18004dfe2  lea     r9, [rbp+string]; string
0x18004dfe6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004dfea  mov     edx, [rbp+length]; length
0x18004dfed  mov     rcx, rbx; sourceString
0x18004dff0  call    cs:__imp_WindowsCreateStringReference
0x18004dff6  mov     r8, r14
0x18004dff9  mov     rdx, [rbp+string]
0x18004dffd  mov     rcx, rsi
0x18004e000  mov     rax, r15
0x18004e003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e008  test    eax, eax
0x18004e00a  jns     loc_18004E0EB
0x18004e010  mov     [rbp+string], r12
0x18004e014  mov     qword ptr [rbp+hstringHeader.Reserved], r12
0x18004e018  mov     qword ptr [rbp+hstringHeader.Reserved+8], r12
0x18004e01c  mov     r8, rdi
0x18004e01f  mov     rdx, rbx
0x18004e022  lea     rcx, [rbp+string]
0x18004e026  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004e02b  mov     ebx, eax
0x18004e02d  test    eax, eax
0x18004e02f  jns     short loc_18004E04E
0x18004e031  mov     rcx, [rbp+38h]; this
0x18004e035  mov     r9d, eax; char *
0x18004e038  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\flightsetting"...
0x18004e03f  mov     edx, 42h ; 'B'; void *
0x18004e044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e049  jmp     loc_18004E0D5
0x18004e04e  lea     rcx, [rbp+string]
0x18004e052  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004e057  mov     edx, dword ptr [rbp+hstringHeader.Reserved]; cchLength
0x18004e05a  mov     rbx, [rbp+string]
0x18004e05e  mov     rcx, rbx; lpsz
0x18004e061  call    cs:__imp_CharLowerBuffW
0x18004e067  mov     rax, [rsi]
0x18004e06a  mov     r15, [rax+40h]
0x18004e06e  mov     rcx, r14
0x18004e071  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004e076  mov     [rbp+length], r12d
0x18004e07a  inc     rdi
0x18004e07d  cmp     [rbx+rdi*2], r12w
0x18004e082  jnz     short loc_18004E07A
0x18004e084  lea     rdx, [rbp+length]; unsigned int *
0x18004e088  mov     rcx, rdi; unsigned __int64
0x18004e08b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004e090  test    eax, eax
0x18004e092  jns     short loc_18004E0A9
0x18004e094  xor     r9d, r9d; lpArguments
0x18004e097  xor     r8d, r8d; nNumberOfArguments
0x18004e09a  lea     edx, [r9+1]; dwExceptionFlags
0x18004e09e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004e0a3  call    cs:__imp_RaiseException
0x18004e0a9  lea     r9, [rbp+var_28]; string
0x18004e0ad  lea     r8, [rbp+var_20]; hstringHeader
0x18004e0b1  mov     edx, [rbp+length]; length
0x18004e0b4  mov     rcx, rbx; sourceString
0x18004e0b7  call    cs:__imp_WindowsCreateStringReference
0x18004e0bd  mov     r8, r14
0x18004e0c0  mov     rdx, [rbp+var_28]
0x18004e0c4  mov     rcx, rsi
0x18004e0c7  mov     rax, r15
0x18004e0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0cf  test    eax, eax
0x18004e0d1  jns     short loc_18004E0E2
0x18004e0d3  mov     ebx, eax
0x18004e0d5  lea     rcx, [rbp+string]
0x18004e0d9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004e0de  mov     eax, ebx
0x18004e0e0  jmp     short loc_18004E0ED
0x18004e0e2  lea     rcx, [rbp+string]
0x18004e0e6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004e0eb  xor     eax, eax
0x18004e0ed  mov     rcx, [rbp+var_8]
0x18004e0f1  xor     rcx, rsp; StackCookie
0x18004e0f4  call    __security_check_cookie
0x18004e0f9  add     rsp, 70h
0x18004e0fd  pop     r15
0x18004e0ff  pop     r14
0x18004e101  pop     r12
0x18004e103  pop     rdi
0x18004e104  pop     rsi
0x18004e105  pop     rbx
0x18004e106  pop     rbp
0x18004e107  retn
```
