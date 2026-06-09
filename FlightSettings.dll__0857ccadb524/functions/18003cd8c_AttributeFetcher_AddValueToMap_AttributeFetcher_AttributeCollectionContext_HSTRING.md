# AttributeFetcher::AddValueToMap(AttributeFetcher::AttributeCollectionContext *,HSTRING__ *)

- ea: `0x18003cd8c`
- end: `0x18003cf6e`
- name: `?AddValueToMap@AttributeFetcher@@AEAAJPEAVAttributeCollectionContext@1@PEAUHSTRING__@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(AttributeFetcher *__hidden this, struct AttributeFetcher::AttributeCollectionContext *, HSTRING string)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bb84`
- `0x18003c5fc`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18003cc2c`
- `0x18003cd8c`
- `0x18003e3f4`
- `0x18003f670`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ce3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ceeb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ce3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003ceeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ce53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ceff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ce53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003ceff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ce86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cf42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ce86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003cf42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cdbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cdeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cdbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003cdeb`

## string_xrefs

- `0x18003cf28`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AttributeFetcher::AddValueToMap(
        AttributeFetcher *this,
        struct AttributeFetcher::AttributeCollectionContext *a2,
        HSTRING string)
{
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rax
  const WCHAR *v10; // rsi
  __int64 v11; // r12
  int (__fastcall *v12)(__int64, HSTRING, char *); // r13
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  const ULONG_PTR *v15; // r9
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING, HSTRING, _BYTE *); // r15
  HSTRING v18; // r14
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-50h]
  char v22; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v23[3]; // [rsp+31h] [rbp-3Fh] BYREF
  UINT32 length; // [rsp+34h] [rbp-3Ch] BYREF
  HSTRING v25; // [rsp+38h] [rbp-38h] BYREF
  HSTRING stringa; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( *StringRawBuffer == 43 )
    return AttributeFetcher::AddGroupToMap(this, a2, StringRawBuffer + 1, 0);
  v8 = WindowsGetStringRawBuffer(string, 0);
  v9 = AttributeFetcher::ParseNamespace(v8, 0);
  v10 = v9;
  v22 = 0;
  v11 = *((_QWORD *)a2 + 2);
  v12 = *(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v11 + 64LL);
  length = 0;
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( v9[v14] );
  if ( (int)ULongLongToUInt(v14, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v15);
  WindowsCreateStringReference(v10, length, &hstringHeader, &stringa);
  if ( v12(v11, stringa, &v22) >= 0 && v22 )
    return 0;
  v25 = 0;
  WindowsDeleteString(0);
  v25 = 0;
  if ( (int)AttributeFetcher::GetValueWithFallback((LARGE_INTEGER *)this, *((_QWORD *)a2 + 3), string, &v25) < 0 )
    goto LABEL_17;
  v23[0] = 0;
  v16 = *((_QWORD *)a2 + 2);
  v17 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v16 + 80LL);
  v18 = v25;
  length = 0;
  do
    ++v13;
  while ( v10[v13] );
  if ( (int)ULongLongToUInt(v13, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(v10, length, &hstringHeader, &stringa);
  v19 = v17(v16, stringa, v18, v23);
  v20 = v19;
  if ( v19 >= 0 )
LABEL_17:
    v20 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32B,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)(unsigned int)v19,
      v21);
  WindowsDeleteString(v25);
  return v20;
}

```

## disassembly

```asm
0x18003cd8c  mov     [rsp-38h+arg_18], rbx
0x18003cd91  push    rbp
0x18003cd92  push    rsi
0x18003cd93  push    rdi
0x18003cd94  push    r12
0x18003cd96  push    r13
0x18003cd98  push    r14
0x18003cd9a  push    r15
0x18003cd9c  mov     rbp, rsp
0x18003cd9f  sub     rsp, 70h
0x18003cda3  mov     rax, cs:__security_cookie
0x18003cdaa  xor     rax, rsp
0x18003cdad  mov     [rbp+var_10], rax
0x18003cdb1  mov     r14, r8
0x18003cdb4  mov     rdi, rdx
0x18003cdb7  mov     r15, rcx
0x18003cdba  xor     edx, edx; length
0x18003cdbc  mov     rcx, r8; string
0x18003cdbf  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cdc5  mov     ecx, 2Bh ; '+'
0x18003cdca  cmp     cx, [rax]
0x18003cdcd  jnz     short loc_18003CDE6
0x18003cdcf  lea     r8, [rax+2]; unsigned __int16 *
0x18003cdd3  xor     r9d, r9d; bool *
0x18003cdd6  mov     rdx, rdi; struct AttributeFetcher::AttributeCollectionContext *
0x18003cdd9  mov     rcx, r15; this
0x18003cddc  call    ?AddGroupToMap@AttributeFetcher@@AEAAJPEAVAttributeCollectionContext@1@PEBGPEA_N@Z; AttributeFetcher::AddGroupToMap(AttributeFetcher::AttributeCollectionContext *,ushort const *,bool *)
0x18003cde1  jmp     loc_18003CF4A
0x18003cde6  xor     edx, edx; length
0x18003cde8  mov     rcx, r14; string
0x18003cdeb  call    cs:__imp_WindowsGetStringRawBuffer
0x18003cdf1  mov     rcx, rax; unsigned __int16 *
0x18003cdf4  xor     edx, edx; unsigned __int16 *
0x18003cdf6  call    ?ParseNamespace@AttributeFetcher@@CAPEBGPEBGPEAG@Z; AttributeFetcher::ParseNamespace(ushort const *,ushort *)
0x18003cdfb  mov     rsi, rax
0x18003cdfe  xor     r9d, r9d
0x18003ce01  mov     [rbp+var_40], r9b
0x18003ce05  mov     r12, [rdi+10h]
0x18003ce09  mov     rcx, [r12]
0x18003ce0d  mov     r13, [rcx+40h]
0x18003ce11  mov     [rbp+length], r9d
0x18003ce15  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003ce19  mov     rcx, rbx
0x18003ce1c  inc     rcx; unsigned __int64
0x18003ce1f  cmp     [rax+rcx*2], r9w
0x18003ce24  jnz     short loc_18003CE1C
0x18003ce26  lea     rdx, [rbp+length]; unsigned int *
0x18003ce2a  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003ce2f  test    eax, eax
0x18003ce31  jns     short loc_18003CE45
0x18003ce33  xor     r8d, r8d; nNumberOfArguments
0x18003ce36  lea     edx, [r8+1]; dwExceptionFlags
0x18003ce3a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003ce3f  call    cs:__imp_RaiseException
0x18003ce45  lea     r9, [rbp+string]; string
0x18003ce49  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003ce4d  mov     edx, [rbp+length]; length
0x18003ce50  mov     rcx, rsi; sourceString
0x18003ce53  call    cs:__imp_WindowsCreateStringReference
0x18003ce59  lea     r8, [rbp+var_40]
0x18003ce5d  mov     rdx, [rbp+string]
0x18003ce61  mov     rcx, r12
0x18003ce64  mov     rax, r13
0x18003ce67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce6c  xor     r12d, r12d
0x18003ce6f  test    eax, eax
0x18003ce71  js      short loc_18003CE80
0x18003ce73  cmp     [rbp+var_40], r12b
0x18003ce77  jz      short loc_18003CE80
0x18003ce79  xor     eax, eax
0x18003ce7b  jmp     loc_18003CF4A
0x18003ce80  mov     [rbp+var_38], r12
0x18003ce84  xor     ecx, ecx; string
0x18003ce86  call    cs:__imp_WindowsDeleteString
0x18003ce8c  mov     [rbp+var_38], r12
0x18003ce90  lea     r9, [rbp+var_38]
0x18003ce94  mov     r8, r14
0x18003ce97  mov     rdx, [rdi+18h]
0x18003ce9b  mov     rcx, r15; this
0x18003ce9e  call    ?GetValueWithFallback@AttributeFetcher@@AEAAJPEAU?$IMap@PEAUHSTRING__@@H@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAPEAU6@@Z; AttributeFetcher::GetValueWithFallback(Windows::Foundation::Collections::IMap<HSTRING__ *,int> *,HSTRING__ *,HSTRING__ * *)
0x18003cea3  test    eax, eax
0x18003cea5  js      loc_18003CF3B
0x18003ceab  mov     [rbp+var_3F], r12b
0x18003ceaf  mov     rdi, [rdi+10h]
0x18003ceb3  mov     rax, [rdi]
0x18003ceb6  mov     r15, [rax+50h]
0x18003ceba  mov     r14, [rbp+var_38]
0x18003cebe  mov     [rbp+length], r12d
0x18003cec2  inc     rbx
0x18003cec5  cmp     [rsi+rbx*2], r12w
0x18003ceca  jnz     short loc_18003CEC2
0x18003cecc  lea     rdx, [rbp+length]; unsigned int *
0x18003ced0  mov     rcx, rbx; unsigned __int64
0x18003ced3  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003ced8  test    eax, eax
0x18003ceda  jns     short loc_18003CEF1
0x18003cedc  xor     r9d, r9d; lpArguments
0x18003cedf  xor     r8d, r8d; nNumberOfArguments
0x18003cee2  lea     edx, [r9+1]; dwExceptionFlags
0x18003cee6  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003ceeb  call    cs:__imp_RaiseException
0x18003cef1  lea     r9, [rbp+string]; string
0x18003cef5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003cef9  mov     edx, [rbp+length]; length
0x18003cefc  mov     rcx, rsi; sourceString
0x18003ceff  call    cs:__imp_WindowsCreateStringReference
0x18003cf05  lea     r9, [rbp+var_3F]
0x18003cf09  mov     r8, r14
0x18003cf0c  mov     rdx, [rbp+string]
0x18003cf10  mov     rcx, rdi
0x18003cf13  mov     rax, r15
0x18003cf16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf1b  mov     ebx, eax
0x18003cf1d  test    eax, eax
0x18003cf1f  jns     short loc_18003CF3B
0x18003cf21  mov     rcx, [rbp+38h]; this
0x18003cf25  mov     r9d, eax; char *
0x18003cf28  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003cf2f  mov     edx, 32Bh; void *
0x18003cf34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf39  jmp     short loc_18003CF3E
0x18003cf3b  mov     ebx, r12d
0x18003cf3e  mov     rcx, [rbp+var_38]; string
0x18003cf42  call    cs:__imp_WindowsDeleteString
0x18003cf48  mov     eax, ebx
0x18003cf4a  mov     rcx, [rbp+var_10]
0x18003cf4e  xor     rcx, rsp; StackCookie
0x18003cf51  call    __security_check_cookie
0x18003cf56  mov     rbx, [rsp+70h+arg_18]
0x18003cf5e  add     rsp, 70h
0x18003cf62  pop     r15
0x18003cf64  pop     r14
0x18003cf66  pop     r13
0x18003cf68  pop     r12
0x18003cf6a  pop     rdi
0x18003cf6b  pop     rsi
0x18003cf6c  pop     rbp
0x18003cf6d  retn
```
