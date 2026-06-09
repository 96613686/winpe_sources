# TransformAttribute::Regex(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18004d9b4`
- end: `0x18004df59`
- name: `?Regex@TransformAttribute@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `1445`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task`

## callers

- `0x18004e2c8`

## callees

- `0x180004b80`
- `0x1800168c8`
- `0x1800190b4`
- `0x180019390`
- `0x18001ec78`
- `0x1800226d0`
- `0x180022718`
- `0x180022c0c`
- `0x180023fa8`
- `0x1800240a0`
- `0x1800240f0`
- `0x180024350`
- `0x18004a110`
- `0x18004a54c`
- `0x18004b620`
- `0x18004ca84`
- `0x18004d898`
- `0x18004d9b4`
- `0x180052adc`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004da41`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004daf7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004da41`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004daf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004db14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004da5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004db14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004deb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004df0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004df21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004deb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004df0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004df21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004da9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004db3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004da9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004db3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall TransformAttribute::Regex(__int64 a1, _QWORD *a2)
{
  int v4; // r14d
  __int64 v5; // r15
  int (__fastcall *v6)(__int64, PVOID, HSTRING *); // r12
  unsigned __int64 v7; // rcx
  __int64 result; // rax
  PCWSTR StringRawBuffer; // r15
  __int64 v10; // rsi
  int (__fastcall *v11)(__int64, PVOID, HSTRING *); // r12
  unsigned __int64 v12; // rcx
  PCWSTR v13; // rax
  __int64 v14; // rax
  __int128 i; // rdi
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-1D8h]
  HSTRING v26; // [rsp+30h] [rbp-1C8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-1C0h] BYREF
  UINT32 length[2]; // [rsp+40h] [rbp-1B8h] BYREF
  __int64 v29; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v30; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-198h] BYREF
  char v32; // [rsp+68h] [rbp-190h]
  __int128 v33; // [rsp+70h] [rbp-188h] BYREF
  __int64 v34; // [rsp+80h] [rbp-178h]
  __int64 v35; // [rsp+88h] [rbp-170h]
  __int64 v36; // [rsp+90h] [rbp-168h]
  char v37; // [rsp+98h] [rbp-160h]
  __int128 v38; // [rsp+A0h] [rbp-158h] BYREF
  char v39; // [rsp+B0h] [rbp-148h]
  __int64 v40; // [rsp+B8h] [rbp-140h]
  __int64 v41; // [rsp+C0h] [rbp-138h]
  char v42; // [rsp+C8h] [rbp-130h]
  _BYTE v43[40]; // [rsp+D8h] [rbp-120h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp-F8h] BYREF
  _BYTE v45[16]; // [rsp+120h] [rbp-D8h] BYREF
  __int64 v46; // [rsp+130h] [rbp-C8h]
  _BYTE v47[32]; // [rsp+140h] [rbp-B8h] BYREF
  _BYTE v48[32]; // [rsp+160h] [rbp-98h] BYREF
  _BYTE v49[32]; // [rsp+180h] [rbp-78h] BYREF
  _BYTE v50[32]; // [rsp+1A0h] [rbp-58h] BYREF

  v4 = 0;
  length[0] = 0;
  string = 0;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = *(int (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v5 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  length[0] = 0;
  v7 = -1;
  do
    ++v7;
  while ( TransformAttribute::s_pszJsonTagRegex[v7] );
  if ( (int)ULongLongToUInt(v7, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(
    TransformAttribute::s_pszJsonTagRegex,
    length[0],
    (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
    (HSTRING *)&hstringHeader);
  if ( v6(v5, hstringHeader.Reserved.Reserved1, &string) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v26 = 0;
    v10 = *(_QWORD *)(a1 + 16);
    v11 = *(int (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v10 + 80LL);
    WindowsDeleteString(0);
    v26 = 0;
    length[0] = 0;
    v12 = -1;
    do
      ++v12;
    while ( TransformAttribute::s_pszJsonTagRegexDelimiter[v12] );
    if ( (int)ULongLongToUInt(v12, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(
      TransformAttribute::s_pszJsonTagRegexDelimiter,
      length[0],
      (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
      (HSTRING *)&hstringHeader);
    if ( v11(v10, hstringHeader.Reserved.Reserved1, &v26) < 0 )
      v13 = L",";
    else
      v13 = WindowsGetStringRawBuffer(v26, 0);
    std::wstring::wstring(v49, v13);
    std::wstring::wstring(v48, StringRawBuffer);
    std::wstring::wstring(v45, *a2);
    std::vector<unsigned __int64>::vector<unsigned __int64>(&v29);
    try
    {
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        v43,
        v48);
      v31 = 0;
      v32 = 0;
      std::vector<unsigned __int64>::vector<unsigned __int64>(&v33);
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      while ( 1 )
      {
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45, v17, v18, v19);
        if ( !(unsigned __int8)std::_Regex_search2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                                 v14,
                                 (int)v14 + 2 * (int)v46,
                                 (unsigned int)&v31,
                                 (unsigned int)v43,
                                 v25,
                                 v14) )
          break;
        for ( i = v33; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 24 )
        {
          hstringHeader = *(HSTRING_HEADER *)i;
          std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
            &hstringHeader,
            v47);
          v4 |= 1u;
          std::vector<std::wstring>::push_back(&v29, v47);
          std::wstring::_Tidy_deallocate(v47);
        }
        v16 = std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
                &v38,
                v47);
        std::wstring::operator=(v45, v16);
        std::wstring::_Tidy_deallocate(v47);
      }
      if ( v30 == v29 )
      {
        if ( (_QWORD)v33 )
        {
          std::_Deallocate<16>((_QWORD *)v33, (const struct std::nothrow_t *)(8 * ((v34 - (__int64)v33) >> 3)));
          v33 = 0;
          v34 = 0;
        }
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v43);
        std::vector<std::wstring>::_Tidy(&v29);
        std::wstring::_Tidy_deallocate(v45);
        std::wstring::_Tidy_deallocate(v48);
        std::wstring::_Tidy_deallocate(v49);
        WindowsDeleteString(v26);
        v26 = 0;
        WindowsDeleteString(string);
        string = 0;
        result = 2147943569LL;
      }
      else
      {
        *(_QWORD *)length = v47;
        v20 = std::wstring::wstring(v47, v49);
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        std::vector<std::wstring>::_Construct_n<std::wstring * const &,std::wstring * const &>(
          &hstringHeader,
          (v30 - v29) >> 5,
          &v29,
          &v30);
        TransformAttribute::JoinList(v50, &hstringHeader, v20);
        v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50, v21, v22, v23);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(a2, v24, -1);
        std::wstring::_Tidy_deallocate(v50);
        if ( (_QWORD)v33 )
        {
          std::_Deallocate<16>((_QWORD *)v33, (const struct std::nothrow_t *)(8 * ((v34 - (__int64)v33) >> 3)));
          v33 = 0;
          v34 = 0;
        }
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v43);
        std::vector<std::wstring>::_Tidy(&v29);
        std::wstring::_Tidy_deallocate(v45);
        std::wstring::_Tidy_deallocate(v48);
        std::wstring::_Tidy_deallocate(v49);
        WindowsDeleteString(v26);
        v26 = 0;
        WindowsDeleteString(string);
        string = 0;
        result = 0;
      }
    }
    catch ( ... )
    {
      std::vector<std::wstring>::_Tidy(&v29);
      std::wstring::_Tidy_deallocate(v45);
      std::wstring::_Tidy_deallocate(v48);
      std::wstring::_Tidy_deallocate(v49);
      WindowsDeleteString(v26);
      v26 = 0;
      WindowsDeleteString(string);
      return 2147942413LL;
    }
  }
  else
  {
    WindowsDeleteString(string);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18004d9b4  mov     [rsp+arg_10], rbx
0x18004d9b9  mov     [rsp+arg_18], rsi
0x18004d9be  push    rdi
0x18004d9bf  push    r12
0x18004d9c1  push    r13
0x18004d9c3  push    r14
0x18004d9c5  push    r15
0x18004d9c7  sub     rsp, 1D0h
0x18004d9ce  mov     rax, cs:__security_cookie
0x18004d9d5  xor     rax, rsp
0x18004d9d8  mov     [rsp+1F8h+var_38], rax
0x18004d9e0  mov     r13, rdx
0x18004d9e3  mov     rsi, rcx
0x18004d9e6  xor     ebx, ebx
0x18004d9e8  mov     r14d, ebx
0x18004d9eb  mov     [rsp+1F8h+length], ebx
0x18004d9ef  mov     [rsp+1F8h+string], rbx
0x18004d9f4  mov     r15, [rcx+10h]
0x18004d9f8  mov     rax, [r15]
0x18004d9fb  mov     r12, [rax+50h]
0x18004d9ff  xor     ecx, ecx; string
0x18004da01  call    cs:__imp_WindowsDeleteString
0x18004da07  mov     [rsp+1F8h+string], rbx
0x18004da0c  mov     rdi, cs:?s_pszJsonTagRegex@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagRegex
0x18004da13  mov     [rsp+1F8h+length], ebx
0x18004da17  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004da1b  inc     rcx; unsigned __int64
0x18004da1e  cmp     [rdi+rcx*2], bx
0x18004da22  jnz     short loc_18004DA1B
0x18004da24  lea     rdx, [rsp+1F8h+length]; unsigned int *
0x18004da29  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004da2e  test    eax, eax
0x18004da30  jns     short loc_18004DA47
0x18004da32  xor     r9d, r9d; lpArguments
0x18004da35  xor     r8d, r8d; nNumberOfArguments
0x18004da38  lea     edx, [r9+1]; dwExceptionFlags
0x18004da3c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004da41  call    cs:__imp_RaiseException
0x18004da47  lea     r9, [rsp+1F8h+hstringHeader]; string
0x18004da4f  lea     r8, [rsp+1F8h+hstringHeader.Reserved+8]; hstringHeader
0x18004da57  mov     edx, [rsp+1F8h+length]; length
0x18004da5b  mov     rcx, rdi; sourceString
0x18004da5e  call    cs:__imp_WindowsCreateStringReference
0x18004da64  lea     r8, [rsp+1F8h+string]
0x18004da69  mov     rdx, qword ptr [rsp+1F8h+hstringHeader.Reserved]
0x18004da71  mov     rcx, r15
0x18004da74  mov     rax, r12
0x18004da77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da7c  test    eax, eax
0x18004da7e  jns     short loc_18004DA95
0x18004da80  mov     rcx, [rsp+1F8h+string]; string
0x18004da85  call    cs:__imp_WindowsDeleteString
0x18004da8b  mov     eax, 1
0x18004da90  jmp     loc_18004DF2C
0x18004da95  xor     edx, edx; length
0x18004da97  mov     rcx, [rsp+1F8h+string]; string
0x18004da9c  call    cs:__imp_WindowsGetStringRawBuffer
0x18004daa2  mov     r15, rax
0x18004daa5  mov     [rsp+1F8h+var_1C8], rbx
0x18004daaa  mov     rsi, [rsi+10h]
0x18004daae  mov     rcx, [rsi]
0x18004dab1  mov     r12, [rcx+50h]
0x18004dab5  xor     ecx, ecx; string
0x18004dab7  call    cs:__imp_WindowsDeleteString
0x18004dabd  mov     [rsp+1F8h+var_1C8], rbx
0x18004dac2  mov     rdi, cs:?s_pszJsonTagRegexDelimiter@TransformAttribute@@0QEBGEB; ushort const * const TransformAttribute::s_pszJsonTagRegexDelimiter
0x18004dac9  mov     [rsp+1F8h+length], ebx
0x18004dacd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004dad1  inc     rcx; unsigned __int64
0x18004dad4  cmp     [rdi+rcx*2], bx
0x18004dad8  jnz     short loc_18004DAD1
0x18004dada  lea     rdx, [rsp+1F8h+length]; unsigned int *
0x18004dadf  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004dae4  test    eax, eax
0x18004dae6  jns     short loc_18004DAFD
0x18004dae8  xor     r9d, r9d; lpArguments
0x18004daeb  xor     r8d, r8d; nNumberOfArguments
0x18004daee  lea     edx, [r9+1]; dwExceptionFlags
0x18004daf2  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004daf7  call    cs:__imp_RaiseException
0x18004dafd  lea     r9, [rsp+1F8h+hstringHeader]; string
0x18004db05  lea     r8, [rsp+1F8h+hstringHeader.Reserved+8]; hstringHeader
0x18004db0d  mov     edx, [rsp+1F8h+length]; length
0x18004db11  mov     rcx, rdi; sourceString
0x18004db14  call    cs:__imp_WindowsCreateStringReference
0x18004db1a  lea     r8, [rsp+1F8h+var_1C8]
0x18004db1f  mov     rdx, qword ptr [rsp+1F8h+hstringHeader.Reserved]
0x18004db27  mov     rcx, rsi
0x18004db2a  mov     rax, r12
0x18004db2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db32  test    eax, eax
0x18004db34  js      short loc_18004DB45
0x18004db36  xor     edx, edx; length
0x18004db38  mov     rcx, [rsp+1F8h+var_1C8]; string
0x18004db3d  call    cs:__imp_WindowsGetStringRawBuffer
0x18004db43  jmp     short loc_18004DB4C
0x18004db45  lea     rax, asc_1800D904C; ","
0x18004db4c  mov     rdx, rax
0x18004db4f  lea     rcx, [rsp+1F8h+var_78]
0x18004db57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004db5c  nop
0x18004db5d  mov     rdx, r15
0x18004db60  lea     rcx, [rsp+1F8h+var_98]
0x18004db68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004db6d  nop
0x18004db6e  mov     rdx, [r13+0]
0x18004db72  lea     rcx, [rsp+1F8h+var_D8]
0x18004db7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004db7f  nop
0x18004db80  lea     rcx, [rsp+1F8h+var_1B0]
0x18004db85  call    ??0?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::vector<unsigned __int64>(void)
0x18004db8a  nop
0x18004db8b  lea     rdx, [rsp+1F8h+var_98]
0x18004db93  lea     rcx, [rsp+1F8h+var_120]
0x18004db9b  call    ??$?0U?$char_traits@G@std@@V?$allocator@G@1@@?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(std::wstring const &,std::regex_constants::syntax_option_type)
0x18004dba0  nop
0x18004dba1  mov     [rsp+1F8h+var_198], rbx
0x18004dba6  mov     [rsp+1F8h+var_190], bl
0x18004dbaa  lea     rcx, [rsp+1F8h+var_188]
0x18004dbaf  call    ??0?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::vector<unsigned __int64>(void)
0x18004dbb4  mov     [rsp+1F8h+var_170], rbx
0x18004dbbc  mov     [rsp+1F8h+var_168], rbx
0x18004dbc4  mov     [rsp+1F8h+var_160], bl
0x18004dbcb  xorps   xmm0, xmm0
0x18004dbce  movdqa  [rsp+1F8h+var_158], xmm0
0x18004dbd7  mov     [rsp+1F8h+var_148], bl
0x18004dbde  mov     [rsp+1F8h+var_140], rbx
0x18004dbe6  mov     [rsp+1F8h+var_138], rbx
0x18004dbee  mov     [rsp+1F8h+var_130], bl
0x18004dbf5  lea     rcx, [rsp+1F8h+var_D8]
0x18004dbfd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004dc02  mov     rcx, [rsp+1F8h+var_C8]
0x18004dc0a  lea     rdx, [rax+rcx*2]
0x18004dc0e  mov     [rsp+1F8h+var_1D0], rax
0x18004dc13  lea     r9, [rsp+1F8h+var_120]
0x18004dc1b  lea     r8, [rsp+1F8h+var_198]
0x18004dc20  mov     rcx, rax
0x18004dc23  call    ??$_Regex_search2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@V12@@std@@YA_NV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@0PEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@0@Z; std::_Regex_search2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x18004dc28  test    al, al
0x18004dc2a  jz      loc_18004DCC6
0x18004dc30  mov     rdi, qword ptr [rsp+1F8h+var_188]
0x18004dc35  mov     rsi, qword ptr [rsp+1F8h+var_188+8]
0x18004dc3a  lea     rdx, [rsp+1F8h+var_B8]
0x18004dc42  cmp     rdi, rsi
0x18004dc45  jz      short loc_18004DC97
0x18004dc47  movups  xmm0, xmmword ptr [rdi]
0x18004dc4a  movups  xmmword ptr [rsp+1F8h+hstringHeader.Reserved], xmm0
0x18004dc52  movsd   xmm1, qword ptr [rdi+10h]
0x18004dc57  movsd   qword ptr [rsp+1F8h+hstringHeader.Reserved+10h], xmm1
0x18004dc60  lea     rcx, [rsp+1F8h+hstringHeader]
0x18004dc68  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18004dc6d  or      r14d, 1
0x18004dc71  lea     rdx, [rsp+1F8h+var_B8]
0x18004dc79  lea     rcx, [rsp+1F8h+var_1B0]
0x18004dc7e  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004dc83  nop
0x18004dc84  lea     rcx, [rsp+1F8h+var_B8]
0x18004dc8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dc91  add     rdi, 18h
0x18004dc95  jmp     short loc_18004DC3A
0x18004dc97  lea     rcx, [rsp+1F8h+var_158]
0x18004dc9f  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18004dca4  mov     rdx, rax
0x18004dca7  lea     rcx, [rsp+1F8h+var_D8]
0x18004dcaf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004dcb4  lea     rcx, [rsp+1F8h+var_B8]
0x18004dcbc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dcc1  jmp     loc_18004DBF5
0x18004dcc6  mov     rax, [rsp+1F8h+var_1A8]
0x18004dccb  cmp     rax, [rsp+1F8h+var_1B0]
0x18004dcd0  jnz     loc_18004DD88
0x18004dcd6  mov     rcx, qword ptr [rsp+1F8h+var_188]
0x18004dcdb  test    rcx, rcx
0x18004dcde  jz      short loc_18004DD1B
0x18004dce0  mov     rax, [rsp+1F8h+var_178]
0x18004dce8  sub     rax, rcx
0x18004dceb  sar     rax, 3
0x18004dcef  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18004dcf9  imul    rax, rdx
0x18004dcfd  lea     rdx, [rax+rax*2]
0x18004dd01  shl     rdx, 3
0x18004dd05  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004dd0a  xorps   xmm0, xmm0
0x18004dd0d  movdqa  [rsp+1F8h+var_188], xmm0
0x18004dd13  mov     [rsp+1F8h+var_178], rbx
0x18004dd1b  lea     rcx, [rsp+1F8h+var_120]
0x18004dd23  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18004dd28  nop
0x18004dd29  lea     rcx, [rsp+1F8h+var_1B0]
0x18004dd2e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004dd33  nop
0x18004dd34  lea     rcx, [rsp+1F8h+var_D8]
0x18004dd3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dd41  nop
0x18004dd42  lea     rcx, [rsp+1F8h+var_98]
0x18004dd4a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dd4f  nop
0x18004dd50  lea     rcx, [rsp+1F8h+var_78]
0x18004dd58  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dd5d  nop
0x18004dd5e  mov     rcx, [rsp+1F8h+var_1C8]; string
0x18004dd63  call    cs:__imp_WindowsDeleteString
0x18004dd69  mov     [rsp+1F8h+var_1C8], rbx
0x18004dd6e  mov     rcx, [rsp+1F8h+string]; string
0x18004dd73  call    cs:__imp_WindowsDeleteString
0x18004dd79  mov     [rsp+1F8h+string], rbx
0x18004dd7e  mov     eax, 80070491h
0x18004dd83  jmp     loc_18004DF2C
0x18004dd88  lea     rax, [rsp+1F8h+var_B8]
0x18004dd90  mov     qword ptr [rsp+1F8h+length], rax
0x18004dd95  lea     rdx, [rsp+1F8h+var_78]
0x18004dd9d  lea     rcx, [rsp+1F8h+var_B8]
0x18004dda5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ddaa  mov     rdi, rax
0x18004ddad  xorps   xmm0, xmm0
0x18004ddb0  movdqu  xmmword ptr [rsp+1F8h+hstringHeader.Reserved], xmm0
0x18004ddb9  mov     qword ptr [rsp+1F8h+hstringHeader.Reserved+10h], rbx
0x18004ddc1  mov     rdx, [rsp+1F8h+var_1A8]
0x18004ddc6  sub     rdx, [rsp+1F8h+var_1B0]
0x18004ddcb  sar     rdx, 5
0x18004ddcf  lea     r9, [rsp+1F8h+var_1A8]
0x18004ddd4  lea     r8, [rsp+1F8h+var_1B0]
0x18004ddd9  lea     rcx, [rsp+1F8h+hstringHeader]
0x18004dde1  call    ??$_Construct_n@AEBQEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAV12@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAX_KAEBQEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@1@Z; std::vector<std::wstring>::_Construct_n<std::wstring * const &,std::wstring * const &>(unsigned __int64,std::wstring * const &,std::wstring * const &)
0x18004dde6  nop
0x18004dde7  mov     r8, rdi
0x18004ddea  lea     rdx, [rsp+1F8h+hstringHeader]
0x18004ddf2  lea     rcx, [rsp+1F8h+var_58]
0x18004ddfa  call    ?JoinList@TransformAttribute@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@V23@@Z; TransformAttribute::JoinList(std::vector<std::wstring>,std::wstring)
0x18004ddff  lea     rcx, [rsp+1F8h+var_58]
0x18004de07  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004de0c  mov     rdx, rax
0x18004de0f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004de13  mov     rcx, r13
0x18004de16  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004de1b  lea     rcx, [rsp+1F8h+var_58]
0x18004de23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004de28  nop
0x18004de29  mov     rcx, qword ptr [rsp+1F8h+var_188]
0x18004de2e  test    rcx, rcx
0x18004de31  jz      short loc_18004DE6E
0x18004de33  mov     rax, [rsp+1F8h+var_178]
0x18004de3b  sub     rax, rcx
0x18004de3e  sar     rax, 3
0x18004de42  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18004de4c  imul    rax, rdx
0x18004de50  lea     rdx, [rax+rax*2]
0x18004de54  shl     rdx, 3
0x18004de58  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004de5d  xorps   xmm0, xmm0
0x18004de60  movdqa  [rsp+1F8h+var_188], xmm0
0x18004de66  mov     [rsp+1F8h+var_178], rbx
0x18004de6e  lea     rcx, [rsp+1F8h+var_120]
0x18004de76  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18004de7b  nop
0x18004de7c  lea     rcx, [rsp+1F8h+var_1B0]
0x18004de81  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004de86  nop
0x18004de87  lea     rcx, [rsp+1F8h+var_D8]
0x18004de8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004de94  nop
0x18004de95  lea     rcx, [rsp+1F8h+var_98]
0x18004de9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004dea2  nop
0x18004dea3  lea     rcx, [rsp+1F8h+var_78]
0x18004deab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004deb0  nop
0x18004deb1  mov     rcx, [rsp+1F8h+var_1C8]; string
0x18004deb6  call    cs:__imp_WindowsDeleteString
0x18004debc  mov     [rsp+1F8h+var_1C8], rbx
0x18004dec1  mov     rcx, [rsp+1F8h+string]; string
0x18004dec6  call    cs:__imp_WindowsDeleteString
0x18004decc  mov     [rsp+1F8h+string], rbx
0x18004ded1  xor     eax, eax
0x18004ded3  jmp     short loc_18004DF2C
0x18004ded5  lea     rcx, [rsp+1F8h+var_1B0]
0x18004deda  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004dedf  nop
0x18004dee0  lea     rcx, [rsp+1F8h+var_D8]
0x18004dee8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004deed  nop
0x18004deee  lea     rcx, [rsp+1F8h+var_98]
0x18004def6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004defb  nop
0x18004defc  lea     rcx, [rsp+1F8h+var_78]
0x18004df04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004df09  nop
0x18004df0a  mov     rcx, [rsp+1F8h+var_1C8]; string
0x18004df0f  call    cs:__imp_WindowsDeleteString
0x18004df15  xor     ebx, ebx
0x18004df17  mov     [rsp+1F8h+var_1C8], rbx
0x18004df1c  mov     rcx, [rsp+1F8h+string]; string
0x18004df21  call    cs:__imp_WindowsDeleteString
0x18004df27  mov     eax, 8007000Dh
0x18004df2c  mov     rcx, [rsp+1F8h+var_38]
0x18004df34  xor     rcx, rsp; StackCookie
0x18004df37  call    __security_check_cookie
0x18004df3c  lea     r11, [rsp+1F8h+var_28]
0x18004df44  mov     rbx, [r11+40h]
0x18004df48  mov     rsi, [r11+48h]
  ... truncated ...
```
