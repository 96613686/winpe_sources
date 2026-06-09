# TransformAttribute::GetTokenValue(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18004d4e0`
- end: `0x18004d870`
- name: `?GetTokenValue@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `912`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e2c8`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180032370`
- `0x18004d4e0`
- `0x18004d878`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d556`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d60f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d69c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d718`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d556`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d60f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d69c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d56a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d623`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d72c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d56a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d623`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d72c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d5d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d81f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d5d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d81f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d646`

## string_xrefs

- `0x18004d5a9`: `onecore\base\flighting\flightsettings\broker\libs\ctac\transformattribute.cpp`
- `0x18004d85a`: `onecore\base\flighting\flightsettings\broker\libs\ctac\transformattribute.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TransformAttribute::GetTokenValue(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, HSTRING, double *); // r14
  unsigned __int64 v6; // rcx
  int v8; // r12d
  unsigned int v9; // ebx
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, HSTRING, HSTRING *); // r14
  unsigned __int64 v12; // rcx
  const unsigned __int16 *StringRawBuffer; // r14
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, HSTRING, char *); // r15
  unsigned __int64 v16; // rcx
  const ULONG_PTR *v17; // r9
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, HSTRING, int *); // rsi
  unsigned __int64 v20; // rcx
  char v21; // si
  char v22; // al
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rbx
  unsigned __int16 v28; // cx
  __int64 v29; // r8
  char v30; // r10
  int v31; // r11d
  int v32; // [rsp+20h] [rbp-40h] BYREF
  UINT32 length; // [rsp+24h] [rbp-3Ch] BYREF
  HSTRING v34; // [rsp+28h] [rbp-38h] BYREF
  double v35; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v35 = 0.0;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = *(int (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)v4 + 88LL);
  length = 0;
  v6 = -1;
  do
    ++v6;
  while ( TransformAttribute::s_pszJsonTagToken[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(TransformAttribute::s_pszJsonTagToken, length, &hstringHeader, &string);
  if ( v5(v4, string, &v35) < 0 )
    return 1;
  v8 = (int)v35;
  if ( (int)v35 )
  {
    v34 = 0;
    v10 = *(_QWORD *)(a1 + 16);
    v11 = *(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v10 + 80LL);
    WindowsDeleteString(0);
    v34 = 0;
    length = 0;
    v12 = -1;
    do
      ++v12;
    while ( TransformAttribute::s_pszJsonTagDelimiters[v12] );
    if ( (int)ULongLongToUInt(v12, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(TransformAttribute::s_pszJsonTagDelimiters, length, &hstringHeader, &string);
    if ( v11(v10, string, &v34) < 0 )
      StringRawBuffer = L" ";
    else
      StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
    BYTE1(v32) = 0;
    v14 = *(_QWORD *)(a1 + 16);
    v15 = *(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v14 + 96LL);
    length = 0;
    v16 = -1;
    do
      ++v16;
    while ( TransformAttribute::s_pszJsonTagIsLast[v16] );
    if ( (int)ULongLongToUInt(v16, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v17);
    WindowsCreateStringReference(TransformAttribute::s_pszJsonTagIsLast, length, &hstringHeader, &string);
    if ( v15(v14, string, (char *)&v32 + 1) < 0 )
      BYTE1(v32) = 0;
    LOBYTE(v32) = 0;
    v18 = *(_QWORD *)(a1 + 16);
    v19 = *(int (__fastcall **)(__int64, HSTRING, int *))(*(_QWORD *)v18 + 96LL);
    length = 0;
    v20 = -1;
    do
      ++v20;
    while ( TransformAttribute::s_pszJsonTagIgnoreEmpty[v20] );
    if ( (int)ULongLongToUInt(v20, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(TransformAttribute::s_pszJsonTagIgnoreEmpty, length, &hstringHeader, &string);
    if ( v19(v18, string, &v32) < 0 )
      LOBYTE(v32) = 0;
    v21 = BYTE1(v32);
    if ( v8 == 1 )
    {
      v22 = 1;
      if ( BYTE1(v32) )
      {
        v9 = -2147024809;
        v23 = 254;
LABEL_51:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\transformattribute.cpp",
          (const char *)v9,
          v32);
LABEL_47:
        WindowsDeleteString(v34);
        return v9;
      }
    }
    else
    {
      v22 = 0;
    }
    v24 = *a2;
    v25 = 0;
    v26 = 0;
    v27 = *a2 & -(__int64)(v22 != 0);
    while ( 1 )
    {
      v28 = *(_WORD *)(v24 + 2 * v26);
      if ( !v28 )
        break;
      if ( TransformAttribute::IsCharInString(v28, StringRawBuffer) )
      {
        if ( v30 )
        {
          while ( TransformAttribute::IsCharInString(*(_WORD *)(v24 + 2 * v29 + 2), StringRawBuffer) )
            ++v29;
        }
        if ( v31 + 1 >= v8 )
        {
          if ( v27 )
          {
            v25 = v24 + 2 * v29;
            goto LABEL_44;
          }
          v27 = v24 + 2 * v29 + 2;
          if ( v21 )
            break;
        }
      }
      v26 = v29 + 1;
    }
    if ( !v27 )
    {
      v9 = -2147483637;
      v23 = 310;
      goto LABEL_51;
    }
LABEL_44:
    if ( v25 )
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_RemoveAt(
        a2,
        (v25 - v24) >> 1,
        -1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_RemoveAt(
      a2,
      0,
      (v27 - v24) >> 1);
    v9 = 0;
    goto LABEL_47;
  }
  v9 = -2147015330;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE1,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\transformattribute.cpp",
    (const char *)0x8007255ELL,
    v32);
  return v9;
}

```

## disassembly

```asm
0x18004d4e0  mov     [rsp-38h+arg_10], rbx
0x18004d4e5  push    rbp
0x18004d4e6  push    rsi
0x18004d4e7  push    rdi
0x18004d4e8  push    r12
0x18004d4ea  push    r13
0x18004d4ec  push    r14
0x18004d4ee  push    r15
0x18004d4f0  mov     rbp, rsp
0x18004d4f3  sub     rsp, 60h
0x18004d4f7  mov     rax, cs:__security_cookie
0x18004d4fe  xor     rax, rsp
0x18004d501  mov     [rbp+var_8], rax
0x18004d505  mov     r13, rdx
0x18004d508  mov     rsi, rcx
0x18004d50b  xorps   xmm0, xmm0
0x18004d50e  movsd   [rbp+var_30], xmm0
0x18004d513  mov     rdi, [rcx+10h]
0x18004d517  mov     rax, [rdi]
0x18004d51a  mov     r14, [rax+58h]
0x18004d51e  mov     rbx, cs:?s_pszJsonTagToken@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagToken
0x18004d525  xor     r15d, r15d
0x18004d528  mov     [rbp+length], r15d
0x18004d52c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d530  inc     rcx; unsigned __int64
0x18004d533  cmp     [rbx+rcx*2], r15w
0x18004d538  jnz     short loc_18004D530
0x18004d53a  lea     rdx, [rbp+length]; unsigned int *
0x18004d53e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004d543  test    eax, eax
0x18004d545  jns     short loc_18004D55C
0x18004d547  xor     r9d, r9d; lpArguments
0x18004d54a  xor     r8d, r8d; nNumberOfArguments
0x18004d54d  lea     edx, [r9+1]; dwExceptionFlags
0x18004d551  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d556  call    cs:__imp_RaiseException
0x18004d55c  lea     r9, [rbp+string]; string
0x18004d560  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004d564  mov     edx, [rbp+length]; length
0x18004d567  mov     rcx, rbx; sourceString
0x18004d56a  call    cs:__imp_WindowsCreateStringReference
0x18004d570  lea     r8, [rbp+var_30]
0x18004d574  mov     rdx, [rbp+string]
0x18004d578  mov     rcx, rdi
0x18004d57b  mov     rax, r14
0x18004d57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d583  test    eax, eax
0x18004d585  jns     short loc_18004D591
0x18004d587  mov     eax, 1
0x18004d58c  jmp     loc_18004D827
0x18004d591  cvttsd2si r12d, [rbp+var_30]
0x18004d597  cmp     r12d, 1
0x18004d59b  jnb     short loc_18004D5BF
0x18004d59d  mov     rcx, [rbp+38h]; this
0x18004d5a1  mov     ebx, 8007255Eh
0x18004d5a6  mov     r9d, ebx; char *
0x18004d5a9  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\flightsetting"...
0x18004d5b0  mov     edx, 0E1h; void *
0x18004d5b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d5ba  jmp     loc_18004D825
0x18004d5bf  mov     [rbp+var_38], r15
0x18004d5c3  mov     rdi, [rsi+10h]
0x18004d5c7  mov     rax, [rdi]
0x18004d5ca  mov     r14, [rax+50h]
0x18004d5ce  xor     ecx, ecx; string
0x18004d5d0  call    cs:__imp_WindowsDeleteString
0x18004d5d6  mov     [rbp+var_38], r15
0x18004d5da  mov     rbx, cs:?s_pszJsonTagDelimiters@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagDelimiters
0x18004d5e1  mov     [rbp+length], r15d
0x18004d5e5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d5e9  inc     rcx; unsigned __int64
0x18004d5ec  cmp     [rbx+rcx*2], r15w
0x18004d5f1  jnz     short loc_18004D5E9
0x18004d5f3  lea     rdx, [rbp+length]; unsigned int *
0x18004d5f7  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004d5fc  test    eax, eax
0x18004d5fe  jns     short loc_18004D615
0x18004d600  xor     r9d, r9d; lpArguments
0x18004d603  xor     r8d, r8d; nNumberOfArguments
0x18004d606  lea     edx, [r9+1]; dwExceptionFlags
0x18004d60a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d60f  call    cs:__imp_RaiseException
0x18004d615  lea     r9, [rbp+string]; string
0x18004d619  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004d61d  mov     edx, [rbp+length]; length
0x18004d620  mov     rcx, rbx; sourceString
0x18004d623  call    cs:__imp_WindowsCreateStringReference
0x18004d629  lea     r8, [rbp+var_38]
0x18004d62d  mov     rdx, [rbp+string]
0x18004d631  mov     rcx, rdi
0x18004d634  mov     rax, r14
0x18004d637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d63c  test    eax, eax
0x18004d63e  js      short loc_18004D651
0x18004d640  xor     edx, edx; length
0x18004d642  mov     rcx, [rbp+var_38]; string
0x18004d646  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d64c  mov     r14, rax
0x18004d64f  jmp     short loc_18004D658
0x18004d651  lea     r14, asc_1800D8ED0; " "
0x18004d658  mov     [rbp+var_3F], r15b
0x18004d65c  mov     rdi, [rsi+10h]
0x18004d660  mov     rax, [rdi]
0x18004d663  mov     r15, [rax+60h]
0x18004d667  mov     rbx, cs:?s_pszJsonTagIsLast@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagIsLast
0x18004d66e  xor     r9d, r9d
0x18004d671  mov     [rbp+length], r9d
0x18004d675  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d679  inc     rcx; unsigned __int64
0x18004d67c  cmp     [rbx+rcx*2], r9w
0x18004d681  jnz     short loc_18004D679
0x18004d683  lea     rdx, [rbp+length]; unsigned int *
0x18004d687  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004d68c  test    eax, eax
0x18004d68e  jns     short loc_18004D6A2
0x18004d690  xor     r8d, r8d; nNumberOfArguments
0x18004d693  lea     edx, [r8+1]; dwExceptionFlags
0x18004d697  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d69c  call    cs:__imp_RaiseException
0x18004d6a2  lea     r9, [rbp+string]; string
0x18004d6a6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004d6aa  mov     edx, [rbp+length]; length
0x18004d6ad  mov     rcx, rbx; sourceString
0x18004d6b0  call    cs:__imp_WindowsCreateStringReference
0x18004d6b6  lea     r8, [rbp+var_3F]
0x18004d6ba  mov     rdx, [rbp+string]
0x18004d6be  mov     rcx, rdi
0x18004d6c1  mov     rax, r15
0x18004d6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6c9  xor     r15d, r15d
0x18004d6cc  test    eax, eax
0x18004d6ce  jns     short loc_18004D6D4
0x18004d6d0  mov     [rbp+var_3F], r15b
0x18004d6d4  mov     [rbp+var_40], r15b
0x18004d6d8  mov     rdi, [rsi+10h]
0x18004d6dc  mov     rax, [rdi]
0x18004d6df  mov     rsi, [rax+60h]
0x18004d6e3  mov     rbx, cs:?s_pszJsonTagIgnoreEmpty@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagIgnoreEmpty
0x18004d6ea  mov     [rbp+length], r15d
0x18004d6ee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d6f2  inc     rcx; unsigned __int64
0x18004d6f5  cmp     [rbx+rcx*2], r15w
0x18004d6fa  jnz     short loc_18004D6F2
0x18004d6fc  lea     rdx, [rbp+length]; unsigned int *
0x18004d700  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004d705  test    eax, eax
0x18004d707  jns     short loc_18004D71E
0x18004d709  xor     r9d, r9d; lpArguments
0x18004d70c  xor     r8d, r8d; nNumberOfArguments
0x18004d70f  lea     edx, [r9+1]; dwExceptionFlags
0x18004d713  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d718  call    cs:__imp_RaiseException
0x18004d71e  lea     r9, [rbp+string]; string
0x18004d722  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004d726  mov     edx, [rbp+length]; length
0x18004d729  mov     rcx, rbx; sourceString
0x18004d72c  call    cs:__imp_WindowsCreateStringReference
0x18004d732  lea     r8, [rbp+var_40]
0x18004d736  mov     rdx, [rbp+string]
0x18004d73a  mov     rcx, rdi
0x18004d73d  mov     rax, rsi
0x18004d740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d745  test    eax, eax
0x18004d747  jns     short loc_18004D752
0x18004d749  mov     r10b, r15b
0x18004d74c  mov     [rbp+var_40], r15b
0x18004d750  jmp     short loc_18004D756
0x18004d752  mov     r10b, [rbp+var_40]
0x18004d756  mov     sil, [rbp+var_3F]
0x18004d75a  cmp     r12d, 1
0x18004d75e  jnz     short loc_18004D777
0x18004d760  mov     al, r12b
0x18004d763  test    sil, sil
0x18004d766  jz      short loc_18004D77A
0x18004d768  mov     ebx, 80070057h
0x18004d76d  mov     edx, 0FEh
0x18004d772  jmp     loc_18004D85A
0x18004d777  mov     al, r15b
0x18004d77a  mov     rdi, [r13+0]
0x18004d77e  mov     r9, r15
0x18004d781  mov     r11d, 1
0x18004d787  mov     r8, r15
0x18004d78a  neg     al
0x18004d78c  sbb     rbx, rbx
0x18004d78f  and     rbx, rdi
0x18004d792  movzx   ecx, word ptr [rdi+r8*2]; unsigned __int16
0x18004d797  cmp     r15w, cx
0x18004d79b  jz      loc_18004D84B
0x18004d7a1  mov     rdx, r14; unsigned __int16 *
0x18004d7a4  call    ?IsCharInString@TransformAttribute@@CA_NGPEBG@Z; TransformAttribute::IsCharInString(ushort,ushort const *)
0x18004d7a9  test    al, al
0x18004d7ab  jz      short loc_18004D7E3
0x18004d7ad  test    r10b, r10b
0x18004d7b0  jz      short loc_18004D7C9
0x18004d7b2  jmp     short loc_18004D7B7
0x18004d7b4  inc     r8
0x18004d7b7  mov     rdx, r14; unsigned __int16 *
0x18004d7ba  movzx   ecx, word ptr [rdi+r8*2+2]; unsigned __int16
0x18004d7c0  call    ?IsCharInString@TransformAttribute@@CA_NGPEBG@Z; TransformAttribute::IsCharInString(ushort,ushort const *)
0x18004d7c5  test    al, al
0x18004d7c7  jnz     short loc_18004D7B4
0x18004d7c9  inc     r11d
0x18004d7cc  cmp     r11d, r12d
0x18004d7cf  jl      short loc_18004D7E3
0x18004d7d1  lea     rax, [rdi+r8*2]
0x18004d7d5  test    rbx, rbx
0x18004d7d8  jnz     short loc_18004D7E8
0x18004d7da  lea     rbx, [rax+2]
0x18004d7de  test    sil, sil
0x18004d7e1  jnz     short loc_18004D84B
0x18004d7e3  inc     r8
0x18004d7e6  jmp     short loc_18004D792
0x18004d7e8  mov     r9, rax
0x18004d7eb  test    r9, r9
0x18004d7ee  jz      short loc_18004D805
0x18004d7f0  sub     r9, rdi
0x18004d7f3  sar     r9, 1
0x18004d7f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004d7fa  mov     rdx, r9
0x18004d7fd  mov     rcx, r13
0x18004d800  call    ?_RemoveAt@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAA_N_K0@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_RemoveAt(unsigned __int64,unsigned __int64)
0x18004d805  sub     rbx, rdi
0x18004d808  sar     rbx, 1
0x18004d80b  mov     r8, rbx
0x18004d80e  xor     edx, edx
0x18004d810  mov     rcx, r13
0x18004d813  call    ?_RemoveAt@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAA_N_K0@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_RemoveAt(unsigned __int64,unsigned __int64)
0x18004d818  mov     ebx, r15d
0x18004d81b  mov     rcx, [rbp+var_38]; string
0x18004d81f  call    cs:__imp_WindowsDeleteString
0x18004d825  mov     eax, ebx
0x18004d827  mov     rcx, [rbp+var_8]
0x18004d82b  xor     rcx, rsp; StackCookie
0x18004d82e  call    __security_check_cookie
0x18004d833  mov     rbx, [rsp+60h+arg_10]
0x18004d83b  add     rsp, 60h
0x18004d83f  pop     r15
0x18004d841  pop     r14
0x18004d843  pop     r13
0x18004d845  pop     r12
0x18004d847  pop     rdi
0x18004d848  pop     rsi
0x18004d849  pop     rbp
0x18004d84a  retn
0x18004d84b  test    rbx, rbx
0x18004d84e  jnz     short loc_18004D7EB
0x18004d850  mov     ebx, 8000000Bh
0x18004d855  mov     edx, 136h; void *
0x18004d85a  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\flightsetting"...
0x18004d861  mov     r9d, ebx; char *
0x18004d864  mov     rcx, [rbp+38h]; this
0x18004d868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d86d  jmp     short loc_18004D81B
```
