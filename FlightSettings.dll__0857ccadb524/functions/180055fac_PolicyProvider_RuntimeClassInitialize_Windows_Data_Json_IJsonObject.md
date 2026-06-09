# PolicyProvider::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *)

- ea: `0x180055fac`
- end: `0x180056304`
- name: `?RuntimeClassInitialize@PolicyProvider@@QEAAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(PolicyProvider *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800473a0`

## callees

- `0x180004b80`
- `0x1800063fc`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180041c44`
- `0x180055b40`
- `0x180055fac`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056029`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560e3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056184`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056220`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005629f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056029`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800560e3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056184`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180056220`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005629f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005603d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800560f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180056198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180056234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800562b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005603d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800560f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180056198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180056234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800562b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800561e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800561e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056062`

## string_xrefs

- `0x180056085`: `onecore\base\flighting\flightsettings\broker\libs\ctac\policyprovider.cpp`
- `0x1800561bf`: `onecore\base\flighting\flightsettings\broker\libs\ctac\policyprovider.cpp`

## pseudocode

```c
int __fastcall PolicyProvider::RuntimeClassInitialize(HSTRING *this, struct Windows::Data::Json::IJsonObject *a2)
{
  HSTRING *v2; // rdi
  int (__fastcall *v5)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r12
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int64 v9; // rdx
  const unsigned __int16 *const *v10; // rcx
  unsigned __int64 v11; // r9
  __int64 v13; // rax
  int (__fastcall *v14)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *); // r15
  bool v15; // sf
  int v16; // eax
  __int64 (__fastcall *v17)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r12
  unsigned __int64 v18; // rcx
  int v19; // edi
  __int64 v20; // rdx
  __int64 (__fastcall *v21)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r12
  unsigned __int64 v22; // rcx
  __int64 v23; // rax
  int (__fastcall *v24)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *); // r15
  int v25; // eax
  UINT32 length; // [rsp+20h] [rbp-40h] BYREF
  double v27; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v2 = this + 2;
  v5 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(this[2]);
  v6 = -1;
  *v2 = 0;
  v7 = -1;
  length = 0;
  do
    ++v7;
  while ( PolicyProvider::s_pszJsonTagLocUri[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(PolicyProvider::s_pszJsonTagLocUri, length, &hstringHeader, &string);
  if ( v5(a2, string, v2) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*v2, 0);
    v11 = -1;
    do
      ++v11;
    while ( StringRawBuffer[v11] );
    if ( !PathRestrictions::FindInList(v10, v9, StringRawBuffer, v11) )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x37,
               (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\policyprovider.cpp",
               (const char *)5,
               length);
    v13 = *(_QWORD *)a2;
    v27 = 0.0;
    length = 0;
    v14 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *))(v13 + 88);
    do
      ++v6;
    while ( PolicyProvider::s_pszJsonTagVariantFlags[v6] );
    if ( (int)ULongLongToUInt(v6, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(PolicyProvider::s_pszJsonTagVariantFlags, length, &hstringHeader, &string);
    v15 = v14(a2, string, &v27) < 0;
    v16 = (int)v27;
    if ( v15 )
      LOWORD(v16) = 0;
    *((_WORD *)this + 12) = v16;
    return 0;
  }
  if ( !(unsigned __int8)IsPolicyManager_GetPolicyPresent() )
    return -2147024846;
  v17 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(this[4]);
  this[4] = 0;
  v18 = -1;
  length = 0;
  do
    ++v18;
  while ( PolicyProvider::s_pszJsonTagPolicyArea[v18] );
  if ( (int)ULongLongToUInt(v18, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(PolicyProvider::s_pszJsonTagPolicyArea, length, &hstringHeader, &string);
  v19 = v17(a2, string, this + 4);
  if ( v19 < 0 )
  {
    v20 = 74;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\policyprovider.cpp",
      (const char *)(unsigned int)v19,
      length);
    return v19;
  }
  v21 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
  WindowsDeleteString(this[5]);
  this[5] = 0;
  v22 = -1;
  length = 0;
  do
    ++v22;
  while ( PolicyProvider::s_pszJsonTagPolicyName[v22] );
  if ( (int)ULongLongToUInt(v22, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(PolicyProvider::s_pszJsonTagPolicyName, length, &hstringHeader, &string);
  v19 = v21(a2, string, this + 5);
  if ( v19 < 0 )
  {
    v20 = 76;
    goto LABEL_25;
  }
  v23 = *(_QWORD *)a2;
  v27 = 0.0;
  length = 0;
  v24 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *))(v23 + 88);
  do
    ++v6;
  while ( PolicyProvider::s_pszJsonTagPolicyFlags[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(PolicyProvider::s_pszJsonTagPolicyFlags, length, &hstringHeader, &string);
  v15 = v24(a2, string, &v27) < 0;
  v25 = (int)v27;
  if ( v15 )
    v25 = 2;
  *((_DWORD *)this + 12) = v25;
  return 0;
}

```

## disassembly

```asm
0x180055fac  mov     [rsp-38h+arg_10], rbx
0x180055fb1  push    rbp
0x180055fb2  push    rsi
0x180055fb3  push    rdi
0x180055fb4  push    r12
0x180055fb6  push    r13
0x180055fb8  push    r14
0x180055fba  push    r15
0x180055fbc  mov     rbp, rsp
0x180055fbf  sub     rsp, 60h
0x180055fc3  mov     rax, cs:__security_cookie
0x180055fca  xor     rax, rsp
0x180055fcd  mov     [rbp+var_10], rax
0x180055fd1  mov     rax, [rdx]
0x180055fd4  lea     rdi, [rcx+10h]
0x180055fd8  mov     r14, rcx
0x180055fdb  mov     rsi, rdx
0x180055fde  mov     rcx, [rdi]; string
0x180055fe1  mov     r12, [rax+50h]
0x180055fe5  call    cs:__imp_WindowsDeleteString
0x180055feb  xor     r13d, r13d
0x180055fee  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180055ff2  mov     [rdi], r13
0x180055ff5  mov     r15, cs:?s_pszJsonTagLocUri@PolicyProvider@@0QEBGEB; ushort const * const PolicyProvider::s_pszJsonTagLocUri
0x180055ffc  mov     rcx, rbx
0x180055fff  mov     [rbp+length], r13d
0x180056003  inc     rcx; unsigned __int64
0x180056006  cmp     [r15+rcx*2], r13w
0x18005600b  jnz     short loc_180056003
0x18005600d  lea     rdx, [rbp+length]; unsigned int *
0x180056011  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180056016  test    eax, eax
0x180056018  jns     short loc_18005602F
0x18005601a  xor     r9d, r9d; lpArguments
0x18005601d  xor     r8d, r8d; nNumberOfArguments
0x180056020  mov     ecx, 0C000000Dh; dwExceptionCode
0x180056025  lea     edx, [r9+1]; dwExceptionFlags
0x180056029  call    cs:__imp_RaiseException
0x18005602f  mov     edx, [rbp+length]; length
0x180056032  lea     r9, [rbp+string]; string
0x180056036  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005603a  mov     rcx, r15; sourceString
0x18005603d  call    cs:__imp_WindowsCreateStringReference
0x180056043  mov     rdx, [rbp+string]
0x180056047  mov     r8, rdi
0x18005604a  mov     rcx, rsi
0x18005604d  mov     rax, r12
0x180056050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056055  test    eax, eax
0x180056057  js      loc_180056126
0x18005605d  mov     rcx, [rdi]; string
0x180056060  xor     edx, edx; length
0x180056062  call    cs:__imp_WindowsGetStringRawBuffer
0x180056068  mov     r9, rbx
0x18005606b  inc     r9; unsigned __int64
0x18005606e  cmp     [rax+r9*2], r13w
0x180056073  jnz     short loc_18005606B
0x180056075  mov     r8, rax; unsigned __int16 *
0x180056078  call    ?FindInList@PathRestrictions@@SA_NQEBQEBG_KPEBG1@Z; PathRestrictions::FindInList(ushort const * const * const,unsigned __int64,ushort const *,unsigned __int64)
0x18005607d  test    al, al
0x18005607f  jnz     short loc_1800560A0
0x180056081  mov     rcx, [rbp+38h]; this
0x180056085  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\flightsetting"...
0x18005608c  mov     r9d, 5; char *
0x180056092  lea     edx, [r9+32h]; void *
0x180056096  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005609b  jmp     loc_1800562E0
0x1800560a0  mov     rax, [rsi]
0x1800560a3  xorps   xmm0, xmm0
0x1800560a6  mov     rdi, cs:?s_pszJsonTagVariantFlags@PolicyProvider@@0QEBGEB; ushort const * const PolicyProvider::s_pszJsonTagVariantFlags
0x1800560ad  movsd   [rbp+var_38], xmm0
0x1800560b2  mov     [rbp+length], r13d
0x1800560b6  mov     r15, [rax+58h]
0x1800560ba  inc     rbx
0x1800560bd  cmp     [rdi+rbx*2], r13w
0x1800560c2  jnz     short loc_1800560BA
0x1800560c4  lea     rdx, [rbp+length]; unsigned int *
0x1800560c8  mov     rcx, rbx; unsigned __int64
0x1800560cb  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800560d0  test    eax, eax
0x1800560d2  jns     short loc_1800560E9
0x1800560d4  xor     r9d, r9d; lpArguments
0x1800560d7  xor     r8d, r8d; nNumberOfArguments
0x1800560da  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800560df  lea     edx, [r9+1]; dwExceptionFlags
0x1800560e3  call    cs:__imp_RaiseException
0x1800560e9  mov     edx, [rbp+length]; length
0x1800560ec  lea     r9, [rbp+string]; string
0x1800560f0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800560f4  mov     rcx, rdi; sourceString
0x1800560f7  call    cs:__imp_WindowsCreateStringReference
0x1800560fd  mov     rdx, [rbp+string]
0x180056101  lea     r8, [rbp+var_38]
0x180056105  mov     rcx, rsi
0x180056108  mov     rax, r15
0x18005610b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056110  test    eax, eax
0x180056112  cvttsd2si eax, [rbp+var_38]
0x180056117  jns     short loc_18005611C
0x180056119  mov     eax, r13d
0x18005611c  mov     [r14+18h], ax
0x180056121  jmp     loc_1800562DE
0x180056126  call    IsPolicyManager_GetPolicyPresent
0x18005612b  test    al, al
0x18005612d  jnz     short loc_180056139
0x18005612f  mov     eax, 80070032h
0x180056134  jmp     loc_1800562E0
0x180056139  mov     rax, [rsi]
0x18005613c  lea     rdi, [r14+20h]
0x180056140  mov     rcx, [rdi]; string
0x180056143  mov     r12, [rax+50h]
0x180056147  call    cs:__imp_WindowsDeleteString
0x18005614d  mov     [rdi], r13
0x180056150  mov     rcx, rbx
0x180056153  mov     r15, cs:?s_pszJsonTagPolicyArea@PolicyProvider@@0QEBGEB; ushort const * const PolicyProvider::s_pszJsonTagPolicyArea
0x18005615a  mov     [rbp+length], r13d
0x18005615e  inc     rcx; unsigned __int64
0x180056161  cmp     [r15+rcx*2], r13w
0x180056166  jnz     short loc_18005615E
0x180056168  lea     rdx, [rbp+length]; unsigned int *
0x18005616c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180056171  test    eax, eax
0x180056173  jns     short loc_18005618A
0x180056175  xor     r9d, r9d; lpArguments
0x180056178  xor     r8d, r8d; nNumberOfArguments
0x18005617b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180056180  lea     edx, [r9+1]; dwExceptionFlags
0x180056184  call    cs:__imp_RaiseException
0x18005618a  mov     edx, [rbp+length]; length
0x18005618d  lea     r9, [rbp+string]; string
0x180056191  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180056195  mov     rcx, r15; sourceString
0x180056198  call    cs:__imp_WindowsCreateStringReference
0x18005619e  mov     rdx, [rbp+string]
0x1800561a2  mov     r8, rdi
0x1800561a5  mov     rcx, rsi
0x1800561a8  mov     rax, r12
0x1800561ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561b0  mov     edi, eax
0x1800561b2  test    eax, eax
0x1800561b4  jns     short loc_1800561D5
0x1800561b6  mov     edx, 4Ah ; 'J'; void *
0x1800561bb  mov     rcx, [rbp+38h]; this
0x1800561bf  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\flightsetting"...
0x1800561c6  mov     r9d, edi; char *
0x1800561c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800561ce  mov     eax, edi
0x1800561d0  jmp     loc_1800562E0
0x1800561d5  mov     rax, [rsi]
0x1800561d8  lea     rdi, [r14+28h]
0x1800561dc  mov     rcx, [rdi]; string
0x1800561df  mov     r12, [rax+50h]
0x1800561e3  call    cs:__imp_WindowsDeleteString
0x1800561e9  mov     [rdi], r13
0x1800561ec  mov     rcx, rbx
0x1800561ef  mov     r15, cs:?s_pszJsonTagPolicyName@PolicyProvider@@0QEBGEB; ushort const * const PolicyProvider::s_pszJsonTagPolicyName
0x1800561f6  mov     [rbp+length], r13d
0x1800561fa  inc     rcx; unsigned __int64
0x1800561fd  cmp     [r15+rcx*2], r13w
0x180056202  jnz     short loc_1800561FA
0x180056204  lea     rdx, [rbp+length]; unsigned int *
0x180056208  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18005620d  test    eax, eax
0x18005620f  jns     short loc_180056226
0x180056211  xor     r9d, r9d; lpArguments
0x180056214  xor     r8d, r8d; nNumberOfArguments
0x180056217  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005621c  lea     edx, [r9+1]; dwExceptionFlags
0x180056220  call    cs:__imp_RaiseException
0x180056226  mov     edx, [rbp+length]; length
0x180056229  lea     r9, [rbp+string]; string
0x18005622d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180056231  mov     rcx, r15; sourceString
0x180056234  call    cs:__imp_WindowsCreateStringReference
0x18005623a  mov     rdx, [rbp+string]
0x18005623e  mov     r8, rdi
0x180056241  mov     rcx, rsi
0x180056244  mov     rax, r12
0x180056247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005624c  mov     edi, eax
0x18005624e  test    eax, eax
0x180056250  jns     short loc_18005625C
0x180056252  mov     edx, 4Ch ; 'L'
0x180056257  jmp     loc_1800561BB
0x18005625c  mov     rax, [rsi]
0x18005625f  xorps   xmm0, xmm0
0x180056262  mov     rdi, cs:?s_pszJsonTagPolicyFlags@PolicyProvider@@0QEBGEB; ushort const * const PolicyProvider::s_pszJsonTagPolicyFlags
0x180056269  movsd   [rbp+var_38], xmm0
0x18005626e  mov     [rbp+length], r13d
0x180056272  mov     r15, [rax+58h]
0x180056276  inc     rbx
0x180056279  cmp     [rdi+rbx*2], r13w
0x18005627e  jnz     short loc_180056276
0x180056280  lea     rdx, [rbp+length]; unsigned int *
0x180056284  mov     rcx, rbx; unsigned __int64
0x180056287  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18005628c  test    eax, eax
0x18005628e  jns     short loc_1800562A5
0x180056290  xor     r9d, r9d; lpArguments
0x180056293  xor     r8d, r8d; nNumberOfArguments
0x180056296  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005629b  lea     edx, [r9+1]; dwExceptionFlags
0x18005629f  call    cs:__imp_RaiseException
0x1800562a5  mov     edx, [rbp+length]; length
0x1800562a8  lea     r9, [rbp+string]; string
0x1800562ac  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800562b0  mov     rcx, rdi; sourceString
0x1800562b3  call    cs:__imp_WindowsCreateStringReference
0x1800562b9  mov     rdx, [rbp+string]
0x1800562bd  lea     r8, [rbp+var_38]
0x1800562c1  mov     rcx, rsi
0x1800562c4  mov     rax, r15
0x1800562c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800562cc  test    eax, eax
0x1800562ce  cvttsd2si eax, [rbp+var_38]
0x1800562d3  jns     short loc_1800562DA
0x1800562d5  mov     eax, 2
0x1800562da  mov     [r14+30h], eax
0x1800562de  xor     eax, eax
0x1800562e0  mov     rcx, [rbp+var_10]
0x1800562e4  xor     rcx, rsp; StackCookie
0x1800562e7  call    __security_check_cookie
0x1800562ec  mov     rbx, [rsp+60h+arg_10]
0x1800562f4  add     rsp, 60h
0x1800562f8  pop     r15
0x1800562fa  pop     r14
0x1800562fc  pop     r13
0x1800562fe  pop     r12
0x180056300  pop     rdi
0x180056301  pop     rsi
0x180056302  pop     rbp
0x180056303  retn
```
