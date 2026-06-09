# TransformAttribute::Contains(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18004d3a4`
- end: `0x18004d4d8`
- name: `?Contains@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18004e2c8`

## callees

- `0x180004b80`
- `0x1800168c8`
- `0x18001ec48`
- `0x18001ec78`
- `0x18004d3a4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d424`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d424`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrNIW` at `0x18004d47f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrNIW` at `0x18004d47f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d3e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d3e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d4ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d461`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TransformAttribute::Contains(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  int (__fastcall *v4)(__int64, HSTRING, HSTRING *); // r15
  unsigned __int64 v5; // rcx
  unsigned int v6; // ebx
  PCWSTR v7; // r9
  PCWSTR v8; // r10
  UINT32 length; // [rsp+20h] [rbp-40h] BYREF
  HSTRING v11; // [rsp+28h] [rbp-38h] BYREF
  UINT32 v12; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  v11 = 0;
  v3 = *(_QWORD *)(a1 + 16);
  v4 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v3 + 80LL);
  WindowsDeleteString(0);
  v11 = 0;
  length = 0;
  v5 = -1;
  do
    ++v5;
  while ( TransformAttribute::s_pszJsonTagContains[v5] );
  v6 = 1;
  if ( (int)ULongLongToUInt(v5, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(TransformAttribute::s_pszJsonTagContains, length, &hstringHeader, &string);
  if ( v4(v3, string, &v11) >= 0 )
  {
    v12 = 0;
    WindowsGetStringRawBuffer(v11, &v12);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a2);
    if ( StrStrNIW(v8, v7, *(_DWORD *)(a2 + 8)) )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(a2, L"1", -1);
      v6 = 0;
    }
    else
    {
      v6 = -2147024883;
    }
  }
  WindowsDeleteString(v11);
  return v6;
}

```

## disassembly

```asm
0x18004d3a4  mov     [rsp-28h+arg_10], rbx
0x18004d3a9  mov     [rsp-28h+arg_18], rsi
0x18004d3ae  push    rbp
0x18004d3af  push    rdi
0x18004d3b0  push    r12
0x18004d3b2  push    r14
0x18004d3b4  push    r15
0x18004d3b6  mov     rbp, rsp
0x18004d3b9  sub     rsp, 60h
0x18004d3bd  mov     rax, cs:__security_cookie
0x18004d3c4  xor     rax, rsp
0x18004d3c7  mov     [rbp+var_8], rax
0x18004d3cb  mov     rdi, rdx
0x18004d3ce  xor     r12d, r12d
0x18004d3d1  mov     [rbp+var_38], r12
0x18004d3d5  mov     r14, [rcx+10h]
0x18004d3d9  mov     rax, [r14]
0x18004d3dc  mov     r15, [rax+50h]
0x18004d3e0  xor     ecx, ecx; string
0x18004d3e2  call    cs:__imp_WindowsDeleteString
0x18004d3e8  mov     [rbp+var_38], r12
0x18004d3ec  mov     rsi, cs:?s_pszJsonTagContains@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagContains
0x18004d3f3  mov     [rbp+length], r12d
0x18004d3f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d3fb  inc     rcx; unsigned __int64
0x18004d3fe  cmp     [rsi+rcx*2], r12w
0x18004d403  jnz     short loc_18004D3FB
0x18004d405  lea     rdx, [rbp+length]; unsigned int *
0x18004d409  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004d40e  mov     ebx, 1
0x18004d413  test    eax, eax
0x18004d415  jns     short loc_18004D42A
0x18004d417  xor     r9d, r9d; lpArguments
0x18004d41a  xor     r8d, r8d; nNumberOfArguments
0x18004d41d  mov     edx, ebx; dwExceptionFlags
0x18004d41f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d424  call    cs:__imp_RaiseException
0x18004d42a  lea     r9, [rbp+string]; string
0x18004d42e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004d432  mov     edx, [rbp+length]; length
0x18004d435  mov     rcx, rsi; sourceString
0x18004d438  call    cs:__imp_WindowsCreateStringReference
0x18004d43e  lea     r8, [rbp+var_38]
0x18004d442  mov     rdx, [rbp+string]
0x18004d446  mov     rcx, r14
0x18004d449  mov     rax, r15
0x18004d44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d451  test    eax, eax
0x18004d453  js      short loc_18004D4A7
0x18004d455  mov     [rbp+var_30], r12d
0x18004d459  lea     rdx, [rbp+var_30]; length
0x18004d45d  mov     rcx, [rbp+var_38]; string
0x18004d461  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d467  mov     r9, rax
0x18004d46a  mov     r10, [rdi]
0x18004d46d  mov     rcx, rdi
0x18004d470  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004d475  mov     r8d, [rdi+8]; cchMax
0x18004d479  mov     rdx, r9; pszSrch
0x18004d47c  mov     rcx, r10; pszFirst
0x18004d47f  call    cs:__imp_StrStrNIW
0x18004d485  test    rax, rax
0x18004d488  jz      short loc_18004D4A2
0x18004d48a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004d48e  lea     rdx, a1; "1"
0x18004d495  mov     rcx, rdi
0x18004d498  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004d49d  mov     ebx, r12d
0x18004d4a0  jmp     short loc_18004D4A7
0x18004d4a2  mov     ebx, 8007000Dh
0x18004d4a7  mov     rcx, [rbp+var_38]; string
0x18004d4ab  call    cs:__imp_WindowsDeleteString
0x18004d4b1  mov     eax, ebx
0x18004d4b3  mov     rcx, [rbp+var_8]
0x18004d4b7  xor     rcx, rsp; StackCookie
0x18004d4ba  call    __security_check_cookie
0x18004d4bf  lea     r11, [rsp+60h+var_s0]
0x18004d4c4  mov     rbx, [r11+40h]
0x18004d4c8  mov     rsi, [r11+48h]
0x18004d4cc  mov     rsp, r11
0x18004d4cf  pop     r15
0x18004d4d1  pop     r14
0x18004d4d3  pop     r12
0x18004d4d5  pop     rdi
0x18004d4d6  pop     rbp
0x18004d4d7  retn
```
