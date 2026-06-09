# TransformAttribute::SubString(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18004e110`
- end: `0x18004e2c0`
- name: `?SubString@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18004e2c8`

## callees

- `0x180004b80`
- `0x1800168c8`
- `0x18001ec48`
- `0x180032370`
- `0x18004d224`
- `0x18004e110`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e198`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e22b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e198`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e22b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e23f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e23f`

## pseudocode

```c
__int64 __fastcall TransformAttribute::SubString(__int64 a1, __int64 a2)
{
  __int64 *v4; // rsi
  __int64 v5; // rcx
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  __int64 v8; // rax
  int (__fastcall *v9)(__int64 *, HSTRING, double *); // r15
  unsigned __int64 v10; // rdi
  char v11; // si
  __int64 v12; // r12
  unsigned __int64 v13; // rcx
  int (__fastcall *v14)(__int64, HSTRING, double *); // r13
  const ULONG_PTR *v15; // r9
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  double v18; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-38h] BYREF

  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a2);
  v4 = *(__int64 **)(a1 + 16);
  v6 = *(int *)(v5 + 8);
  v7 = -1;
  v18 = 0.0;
  v8 = *v4;
  length = 0;
  v9 = *(int (__fastcall **)(__int64 *, HSTRING, double *))(v8 + 88);
  do
    ++v7;
  while ( TransformAttribute::s_pszJsonTagSubStart[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(TransformAttribute::s_pszJsonTagSubStart, length, &hstringHeader, &string);
  if ( v9(v4, string, &v18) < 0 )
  {
    v10 = 0;
    v11 = 0;
  }
  else
  {
    v10 = TransformAttribute::AddIfNegative(v18, v6);
    v11 = 1;
  }
  v12 = *(_QWORD *)(a1 + 16);
  v13 = -1;
  v18 = 0.0;
  length = 0;
  v14 = *(int (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)v12 + 88LL);
  do
    ++v13;
  while ( TransformAttribute::s_pszJsonTagSubLen[v13] );
  if ( (int)ULongLongToUInt(v13, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v15);
  WindowsCreateStringReference(TransformAttribute::s_pszJsonTagSubLen, length, &hstringHeader, &string);
  if ( v14(v12, string, &v18) >= 0 )
  {
    v6 = TransformAttribute::AddIfNegative(v18, v6);
LABEL_14:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_RemoveAt(a2, v6 + v10, -1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_RemoveAt(a2, 0, v10);
    return 0;
  }
  if ( v11 )
    goto LABEL_14;
  return 1;
}

```

## disassembly

```asm
0x18004e110  mov     [rsp-38h+arg_10], rbx
0x18004e115  push    rbp
0x18004e116  push    rsi
0x18004e117  push    rdi
0x18004e118  push    r12
0x18004e11a  push    r13
0x18004e11c  push    r14
0x18004e11e  push    r15
0x18004e120  mov     rbp, rsp
0x18004e123  sub     rsp, 70h
0x18004e127  movaps  [rsp+70h+var_10], xmm6
0x18004e12c  mov     rax, cs:__security_cookie
0x18004e133  xor     rax, rsp
0x18004e136  mov     [rbp+var_20], rax
0x18004e13a  mov     r12, rcx
0x18004e13d  mov     r14, rdx
0x18004e140  mov     rcx, rdx
0x18004e143  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004e148  mov     rsi, [r12+10h]
0x18004e14d  xor     r13d, r13d
0x18004e150  movsxd  rbx, dword ptr [rcx+8]
0x18004e154  xorps   xmm6, xmm6
0x18004e157  mov     rdi, cs:?s_pszJsonTagSubStart@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagSubStart
0x18004e15e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004e162  movsd   [rbp+var_48], xmm6
0x18004e167  mov     rax, [rsi]
0x18004e16a  mov     [rbp+length], r13d
0x18004e16e  mov     r15, [rax+58h]
0x18004e172  inc     rcx; unsigned __int64
0x18004e175  cmp     [rdi+rcx*2], r13w
0x18004e17a  jnz     short loc_18004E172
0x18004e17c  lea     rdx, [rbp+length]; unsigned int *
0x18004e180  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004e185  test    eax, eax
0x18004e187  jns     short loc_18004E19E
0x18004e189  xor     r9d, r9d; lpArguments
0x18004e18c  xor     r8d, r8d; nNumberOfArguments
0x18004e18f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004e194  lea     edx, [r9+1]; dwExceptionFlags
0x18004e198  call    cs:__imp_RaiseException
0x18004e19e  mov     edx, [rbp+length]; length
0x18004e1a1  lea     r9, [rbp+string]; string
0x18004e1a5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004e1a9  mov     rcx, rdi; sourceString
0x18004e1ac  call    cs:__imp_WindowsCreateStringReference
0x18004e1b2  mov     rdx, [rbp+string]
0x18004e1b6  lea     r8, [rbp+var_48]
0x18004e1ba  mov     rcx, rsi
0x18004e1bd  mov     rax, r15
0x18004e1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1c5  test    eax, eax
0x18004e1c7  js      short loc_18004E1DE
0x18004e1c9  movsd   xmm0, [rbp+var_48]; double
0x18004e1ce  mov     rdx, rbx; unsigned __int64
0x18004e1d1  call    ?AddIfNegative@TransformAttribute@@CA_KN_K@Z; TransformAttribute::AddIfNegative(double,unsigned __int64)
0x18004e1d6  mov     rdi, rax
0x18004e1d9  mov     sil, 1
0x18004e1dc  jmp     short loc_18004E1E4
0x18004e1de  mov     rdi, r13
0x18004e1e1  mov     sil, r13b
0x18004e1e4  mov     r12, [r12+10h]
0x18004e1e9  xor     r9d, r9d
0x18004e1ec  mov     r15, cs:?s_pszJsonTagSubLen@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagSubLen
0x18004e1f3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004e1f7  movsd   [rbp+var_48], xmm6
0x18004e1fc  mov     [rbp+length], r9d
0x18004e200  mov     rax, [r12]
0x18004e204  mov     r13, [rax+58h]
0x18004e208  inc     rcx; unsigned __int64
0x18004e20b  cmp     [r15+rcx*2], r9w
0x18004e210  jnz     short loc_18004E208
0x18004e212  lea     rdx, [rbp+length]; unsigned int *
0x18004e216  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004e21b  test    eax, eax
0x18004e21d  jns     short loc_18004E231
0x18004e21f  xor     r8d, r8d; nNumberOfArguments
0x18004e222  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004e227  lea     edx, [r8+1]; dwExceptionFlags
0x18004e22b  call    cs:__imp_RaiseException
0x18004e231  mov     edx, [rbp+length]; length
0x18004e234  lea     r9, [rbp+string]; string
0x18004e238  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004e23c  mov     rcx, r15; sourceString
0x18004e23f  call    cs:__imp_WindowsCreateStringReference
0x18004e245  mov     rdx, [rbp+string]
0x18004e249  lea     r8, [rbp+var_48]
0x18004e24d  mov     rcx, r12
0x18004e250  mov     rax, r13
0x18004e253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e258  test    eax, eax
0x18004e25a  js      short loc_18004E2B4
0x18004e25c  movsd   xmm0, [rbp+var_48]; double
0x18004e261  mov     rdx, rbx; unsigned __int64
0x18004e264  call    ?AddIfNegative@TransformAttribute@@CA_KN_K@Z; TransformAttribute::AddIfNegative(double,unsigned __int64)
0x18004e269  mov     rbx, rax
0x18004e26c  lea     rdx, [rbx+rdi]
0x18004e270  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004e274  mov     rcx, r14
0x18004e277  call    ?_RemoveAt@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAA_N_K0@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_RemoveAt(unsigned __int64,unsigned __int64)
0x18004e27c  mov     r8, rdi
0x18004e27f  xor     edx, edx
0x18004e281  mov     rcx, r14
0x18004e284  call    ?_RemoveAt@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAA_N_K0@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_RemoveAt(unsigned __int64,unsigned __int64)
0x18004e289  xor     eax, eax
0x18004e28b  mov     rcx, [rbp+var_20]
0x18004e28f  xor     rcx, rsp; StackCookie
0x18004e292  call    __security_check_cookie
0x18004e297  mov     rbx, [rsp+70h+arg_10]
0x18004e29f  movaps  xmm6, [rsp+70h+var_10]
0x18004e2a4  add     rsp, 70h
0x18004e2a8  pop     r15
0x18004e2aa  pop     r14
0x18004e2ac  pop     r13
0x18004e2ae  pop     r12
0x18004e2b0  pop     rdi
0x18004e2b1  pop     rsi
0x18004e2b2  pop     rbp
0x18004e2b3  retn
0x18004e2b4  test    sil, sil
0x18004e2b7  jnz     short loc_18004E26C
0x18004e2b9  mov     eax, 1
0x18004e2be  jmp     short loc_18004E28B
```
