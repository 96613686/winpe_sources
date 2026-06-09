# CKeyboardHandler::GetAllInstalledKeyboardLanguages(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180007594`
- end: `0x180007b06`
- name: `?GetAllInstalledKeyboardLanguages@CKeyboardHandler@@QEAAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1394`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017e84`

## callees

- `0x180003520`
- `0x1800046e8`
- `0x180005954`
- `0x180005a14`
- `0x180005c60`
- `0x180006380`
- `0x1800074c4`
- `0x180007594`
- `0x1800092a4`
- `0x180027b54`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800075e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007600`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007629`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800075e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007600`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800077e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000789b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000793e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800077e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000789b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000793e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007821`

## string_xrefs

- `0x180007664`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x1800076bd`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x18000772d`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x180007923`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x1800079b9`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x180007a3f`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x180007aad`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
__int64 __fastcall CKeyboardHandler::GetAllInstalledKeyboardLanguages(__int64 a1, _QWORD *a2)
{
  void **v4; // rbx
  void *v5; // rbx
  DWORD v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  __int64 v9; // rcx
  void **v10; // rax
  void *v11; // rcx
  DWORD v12; // eax
  __int64 v13; // r8
  const char *v14; // r9
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // esi
  __m128i si128; // xmm6
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v32; // r8
  _OWORD *v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // [rsp+28h] [rbp-39h] BYREF
  __int128 v51; // [rsp+30h] [rbp-31h] BYREF
  __m128i v52; // [rsp+40h] [rbp-21h]
  __int64 v53; // [rsp+50h] [rbp-11h] BYREF
  __int64 v54; // [rsp+58h] [rbp-9h] BYREF
  __int64 v55; // [rsp+60h] [rbp-1h] BYREF
  unsigned int v56; // [rsp+68h] [rbp+7h] BYREF
  HSTRING string; // [rsp+70h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v4 = *(void ***)(a1 + 32);
  if ( v4 )
    v5 = *v4;
  else
    v5 = 0;
  v6 = WaitForSingleObjectEx(v5, 0, 0);
  if ( v6 == 258 )
  {
    v10 = *(void ***)(a1 + 32);
    if ( v10 )
      v11 = *v10;
    else
      v11 = 0;
    v12 = WaitForSingleObjectEx(v11, 0xEA60u, 0);
    if ( v12 == 258 )
    {
      v16 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
        (const char *)0x80004005LL,
        v50);
      return v16;
    }
    if ( v12 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v13, v14);
  }
  else if ( v6 || WaitForSingleObjectEx(v5, 0, 0) )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v7, v8);
  }
  if ( !*(_QWORD *)(a1 + 8) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  v50 = 0;
  v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>>(
          v9,
          &v50);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)v15,
      v50);
    v17 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v16;
  }
  v53 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 160LL))(*(_QWORD *)(a1 + 8), &v53);
  v16 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)v18,
      v50);
    v19 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v16;
  }
  v56 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v53 + 56LL))(v53, &v56);
  v16 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)v21,
      v50);
    v22 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v16;
  }
  v24 = 0;
  if ( v56 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v54 = 0;
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 48LL))(v53, v24, &v54);
      v16 = v26;
      if ( v26 < 0 )
        break;
      v55 = 0;
      v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 56LL))(v54, &v55);
      v16 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
          (const char *)(unsigned int)v27,
          v50);
        v43 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        v44 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
        v45 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        }
        v46 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        }
        return v16;
      }
      string = 0;
      v28 = v55;
      v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v55 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v30 = v29(v28, &string);
      v16 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
          (const char *)(unsigned int)v30,
          v50);
        if ( string )
          WindowsDeleteString(string);
        v39 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        }
        v40 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        }
        v41 = v53;
        if ( v53 )
        {
          v53 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        }
        v42 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        }
        return v16;
      }
      if ( !(unsigned __int8)std::any_of_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_66b8c4f79f3bf798e0a4948ec80e691d___(
                               *a2,
                               a2[1],
                               &string) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v51 = 0;
        v52 = 0;
        v32 = -1;
        do
          ++v32;
        while ( StringRawBuffer[v32] );
        std::wstring::_Construct<1,unsigned short const *>((__int64)&v51, StringRawBuffer, v32);
        v33 = (_OWORD *)a2[1];
        if ( v33 == (_OWORD *)a2[2] )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a2, (__int64)v33, &v51);
        }
        else
        {
          *v33 = v51;
          v33[1] = v52;
          v52 = si128;
          LOWORD(v51) = 0;
          a2[1] += 32LL;
        }
        std::wstring::~wstring((char **)&v51);
      }
      if ( string )
        WindowsDeleteString(string);
      v34 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v35 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      if ( ++v24 >= v56 )
        goto LABEL_50;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)v26,
      v50);
    v47 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    v49 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    return v16;
  }
LABEL_50:
  v36 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return 0;
}

```

## disassembly

```asm
0x180007594  mov     rax, rsp
0x180007597  mov     [rax+18h], rbx
0x18000759b  push    rbp
0x18000759c  push    rsi
0x18000759d  push    rdi
0x18000759e  push    r14
0x1800075a0  push    r15
0x1800075a2  lea     rbp, [rax-5Fh]
0x1800075a6  sub     rsp, 90h
0x1800075ad  movaps  xmmword ptr [rax-38h], xmm6
0x1800075b1  mov     rax, cs:__security_cookie
0x1800075b8  xor     rax, rsp
0x1800075bb  mov     [rbp+57h+var_40], rax
0x1800075bf  mov     r14, rdx
0x1800075c2  mov     rdi, rcx
0x1800075c5  mov     rbx, [rcx+20h]
0x1800075c9  xor     r15d, r15d
0x1800075cc  test    rbx, rbx
0x1800075cf  jz      short loc_1800075D6
0x1800075d1  mov     rbx, [rbx]
0x1800075d4  jmp     short loc_1800075D9
0x1800075d6  mov     rbx, r15
0x1800075d9  xor     r8d, r8d; bAlertable
0x1800075dc  xor     edx, edx; dwMilliseconds
0x1800075de  mov     rcx, rbx; hHandle
0x1800075e1  call    cs:__imp_WaitForSingleObjectEx
0x1800075e7  mov     esi, 102h
0x1800075ec  cmp     eax, esi
0x1800075ee  jz      short loc_180007610
0x1800075f0  test    eax, eax
0x1800075f2  jnz     loc_180007AF7
0x1800075f8  xor     r8d, r8d; bAlertable
0x1800075fb  xor     edx, edx; dwMilliseconds
0x1800075fd  mov     rcx, rbx; hHandle
0x180007600  call    cs:__imp_WaitForSingleObjectEx
0x180007606  test    eax, eax
0x180007608  jnz     loc_180007AF7
0x18000760e  jmp     short loc_18000763F
0x180007610  mov     rax, [rdi+20h]
0x180007614  test    rax, rax
0x180007617  jz      short loc_18000761E
0x180007619  mov     rcx, [rax]
0x18000761c  jmp     short loc_180007621
0x18000761e  mov     rcx, r15; hHandle
0x180007621  xor     r8d, r8d; bAlertable
0x180007624  mov     edx, 0EA60h; dwMilliseconds
0x180007629  call    cs:__imp_WaitForSingleObjectEx
0x18000762f  cmp     eax, esi
0x180007631  jz      loc_180007AA1
0x180007637  test    eax, eax
0x180007639  jnz     loc_180007AE8
0x18000763f  cmp     [rdi+8], r15
0x180007643  jnz     short loc_18000764A
0x180007645  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000764a  mov     [rbp+57h+var_90], r15
0x18000764e  lea     rdx, [rbp+57h+var_90]
0x180007652  call    ??$CreateExternalObjectVector@VCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@V?$Vector@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@@4Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>> * *)
0x180007657  mov     ebx, eax
0x180007659  test    eax, eax
0x18000765b  jns     short loc_180007695
0x18000765d  mov     rcx, [rbp+5Fh]; this
0x180007661  mov     r9d, eax; char *
0x180007664  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000766b  mov     edx, 9Ah; void *
0x180007670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007675  nop
0x180007676  mov     rcx, [rbp+57h+var_90]
0x18000767a  test    rcx, rcx
0x18000767d  jz      short loc_180007690
0x18000767f  mov     [rbp+57h+var_90], r15
0x180007683  mov     rax, [rcx]
0x180007686  mov     rax, [rax+10h]
0x18000768a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000768f  nop
0x180007690  jmp     loc_180007ABE
0x180007695  mov     [rbp+57h+var_68], r15
0x180007699  mov     rcx, [rdi+8]
0x18000769d  mov     rax, [rcx]
0x1800076a0  lea     rdx, [rbp+57h+var_68]
0x1800076a4  mov     rax, [rax+0A0h]
0x1800076ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076b0  mov     ebx, eax
0x1800076b2  test    eax, eax
0x1800076b4  jns     short loc_180007708
0x1800076b6  mov     rcx, [rbp+5Fh]; this
0x1800076ba  mov     r9d, eax; char *
0x1800076bd  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x1800076c4  mov     edx, 9Dh; void *
0x1800076c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076ce  nop
0x1800076cf  mov     rcx, [rbp+57h+var_68]
0x1800076d3  test    rcx, rcx
0x1800076d6  jz      short loc_1800076E9
0x1800076d8  mov     [rbp+57h+var_68], r15
0x1800076dc  mov     rax, [rcx]
0x1800076df  mov     rax, [rax+10h]
0x1800076e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076e8  nop
0x1800076e9  mov     rcx, [rbp+57h+var_90]
0x1800076ed  test    rcx, rcx
0x1800076f0  jz      short loc_180007703
0x1800076f2  mov     [rbp+57h+var_90], r15
0x1800076f6  mov     rax, [rcx]
0x1800076f9  mov     rax, [rax+10h]
0x1800076fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007702  nop
0x180007703  jmp     loc_180007ABE
0x180007708  mov     [rbp+57h+var_50], r15d
0x18000770c  mov     rcx, [rbp+57h+var_68]
0x180007710  mov     rax, [rcx]
0x180007713  lea     rdx, [rbp+57h+var_50]
0x180007717  mov     rax, [rax+38h]
0x18000771b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007720  mov     ebx, eax
0x180007722  test    eax, eax
0x180007724  jns     short loc_180007778
0x180007726  mov     rcx, [rbp+5Fh]; this
0x18000772a  mov     r9d, eax; char *
0x18000772d  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180007734  mov     edx, 0A0h; void *
0x180007739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000773e  nop
0x18000773f  mov     rcx, [rbp+57h+var_68]
0x180007743  test    rcx, rcx
0x180007746  jz      short loc_180007759
0x180007748  mov     [rbp+57h+var_68], r15
0x18000774c  mov     rax, [rcx]
0x18000774f  mov     rax, [rax+10h]
0x180007753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007758  nop
0x180007759  mov     rcx, [rbp+57h+var_90]
0x18000775d  test    rcx, rcx
0x180007760  jz      short loc_180007773
0x180007762  mov     [rbp+57h+var_90], r15
0x180007766  mov     rax, [rcx]
0x180007769  mov     rax, [rax+10h]
0x18000776d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007772  nop
0x180007773  jmp     loc_180007ABE
0x180007778  mov     esi, r15d
0x18000777b  cmp     [rbp+57h+var_50], r15d
0x18000777f  jbe     loc_1800078E1
0x180007785  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000778d  mov     [rbp+57h+var_60], r15
0x180007791  mov     rcx, [rbp+57h+var_68]
0x180007795  mov     rax, [rcx]
0x180007798  lea     r8, [rbp+57h+var_60]
0x18000779c  mov     edx, esi
0x18000779e  mov     rax, [rax+30h]
0x1800077a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a7  mov     ebx, eax
0x1800077a9  test    eax, eax
0x1800077ab  js      loc_180007A38
0x1800077b1  mov     [rbp+57h+var_58], r15
0x1800077b5  mov     rcx, [rbp+57h+var_60]
0x1800077b9  mov     rax, [rcx]
0x1800077bc  lea     rdx, [rbp+57h+var_58]
0x1800077c0  mov     rax, [rax+38h]
0x1800077c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c9  mov     ebx, eax
0x1800077cb  test    eax, eax
0x1800077cd  js      loc_1800079B2
0x1800077d3  mov     [rbp+57h+string], r15
0x1800077d7  mov     rdi, [rbp+57h+var_58]
0x1800077db  mov     rax, [rdi]
0x1800077de  mov     rbx, [rax+30h]
0x1800077e2  xor     ecx, ecx; string
0x1800077e4  call    cs:__imp_WindowsDeleteString
0x1800077ea  mov     [rbp+57h+string], r15
0x1800077ee  lea     rdx, [rbp+57h+string]
0x1800077f2  mov     rcx, rdi
0x1800077f5  mov     rax, rbx
0x1800077f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077fd  mov     ebx, eax
0x1800077ff  test    eax, eax
0x180007801  js      loc_18000791C
0x180007807  lea     r8, [rbp+57h+string]
0x18000780b  mov     rdx, [r14+8]
0x18000780f  mov     rcx, [r14]
0x180007812  call    std__any_of_std___Vector_iterator_std___Vector_val_std___Simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_66b8c4f79f3bf798e0a4948ec80e691d___
0x180007817  test    al, al
0x180007819  jnz     short loc_180007892
0x18000781b  xor     edx, edx; length
0x18000781d  mov     rcx, [rbp+57h+string]; string
0x180007821  call    cs:__imp_WindowsGetStringRawBuffer
0x180007827  xorps   xmm0, xmm0
0x18000782a  movups  [rbp+57h+var_88], xmm0
0x18000782e  xorps   xmm1, xmm1
0x180007831  movdqu  [rbp+57h+var_78], xmm1
0x180007836  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000783a  inc     r8
0x18000783d  cmp     [rax+r8*2], r15w
0x180007842  jnz     short loc_18000783A
0x180007844  mov     rdx, rax
0x180007847  lea     rcx, [rbp+57h+var_88]
0x18000784b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180007850  nop
0x180007851  mov     rdx, [r14+8]
0x180007855  cmp     rdx, [r14+10h]
0x180007859  jz      short loc_18000787B
0x18000785b  movups  xmm0, [rbp+57h+var_88]
0x18000785f  movups  xmmword ptr [rdx], xmm0
0x180007862  movups  xmm1, [rbp+57h+var_78]
0x180007866  movups  xmmword ptr [rdx+10h], xmm1
0x18000786a  movdqu  [rbp+57h+var_78], xmm6
0x18000786f  mov     word ptr [rbp+57h+var_88], r15w
0x180007874  add     qword ptr [r14+8], 20h ; ' '
0x180007879  jmp     short loc_180007888
0x18000787b  lea     r8, [rbp+57h+var_88]
0x18000787f  mov     rcx, r14
0x180007882  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180007887  nop
0x180007888  lea     rcx, [rbp+57h+var_88]; void *
0x18000788c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007891  nop
0x180007892  mov     rcx, [rbp+57h+string]; string
0x180007896  test    rcx, rcx
0x180007899  jz      short loc_1800078A2
0x18000789b  call    cs:__imp_WindowsDeleteString
0x1800078a1  nop
0x1800078a2  mov     rcx, [rbp+57h+var_58]
0x1800078a6  test    rcx, rcx
0x1800078a9  jz      short loc_1800078BC
0x1800078ab  mov     [rbp+57h+var_58], r15
0x1800078af  mov     rax, [rcx]
0x1800078b2  mov     rax, [rax+10h]
0x1800078b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078bb  nop
0x1800078bc  mov     rcx, [rbp+57h+var_60]
0x1800078c0  test    rcx, rcx
0x1800078c3  jz      short loc_1800078D6
0x1800078c5  mov     [rbp+57h+var_60], r15
0x1800078c9  mov     rax, [rcx]
0x1800078cc  mov     rax, [rax+10h]
0x1800078d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078d5  nop
0x1800078d6  inc     esi
0x1800078d8  cmp     esi, [rbp+57h+var_50]
0x1800078db  jb      loc_18000778D
0x1800078e1  mov     rcx, [rbp+57h+var_68]
0x1800078e5  test    rcx, rcx
0x1800078e8  jz      short loc_1800078FB
0x1800078ea  mov     [rbp+57h+var_68], r15
0x1800078ee  mov     rax, [rcx]
0x1800078f1  mov     rax, [rax+10h]
0x1800078f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078fa  nop
0x1800078fb  mov     rcx, [rbp+57h+var_90]
0x1800078ff  test    rcx, rcx
0x180007902  jz      short loc_180007915
0x180007904  mov     [rbp+57h+var_90], r15
0x180007908  mov     rax, [rcx]
0x18000790b  mov     rax, [rax+10h]
0x18000790f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007914  nop
0x180007915  xor     eax, eax
0x180007917  jmp     loc_180007AC0
0x18000791c  mov     rcx, [rbp+5Fh]; this
0x180007920  mov     r9d, ebx; char *
0x180007923  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000792a  mov     edx, 0ABh; void *
0x18000792f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007934  nop
0x180007935  mov     rcx, [rbp+57h+string]; string
0x180007939  test    rcx, rcx
0x18000793c  jz      short loc_180007945
0x18000793e  call    cs:__imp_WindowsDeleteString
0x180007944  nop
0x180007945  mov     rcx, [rbp+57h+var_58]
0x180007949  test    rcx, rcx
0x18000794c  jz      short loc_18000795F
0x18000794e  mov     [rbp+57h+var_58], r15
0x180007952  mov     rax, [rcx]
0x180007955  mov     rax, [rax+10h]
0x180007959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000795e  nop
0x18000795f  mov     rcx, [rbp+57h+var_60]
0x180007963  test    rcx, rcx
0x180007966  jz      short loc_180007979
0x180007968  mov     [rbp+57h+var_60], r15
0x18000796c  mov     rax, [rcx]
0x18000796f  mov     rax, [rax+10h]
0x180007973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007978  nop
0x180007979  mov     rcx, [rbp+57h+var_68]
0x18000797d  test    rcx, rcx
0x180007980  jz      short loc_180007993
0x180007982  mov     [rbp+57h+var_68], r15
0x180007986  mov     rax, [rcx]
0x180007989  mov     rax, [rax+10h]
0x18000798d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007992  nop
0x180007993  mov     rcx, [rbp+57h+var_90]
0x180007997  test    rcx, rcx
0x18000799a  jz      short loc_1800079AD
0x18000799c  mov     [rbp+57h+var_90], r15
0x1800079a0  mov     rax, [rcx]
0x1800079a3  mov     rax, [rax+10h]
0x1800079a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ac  nop
  ... truncated ...
```
