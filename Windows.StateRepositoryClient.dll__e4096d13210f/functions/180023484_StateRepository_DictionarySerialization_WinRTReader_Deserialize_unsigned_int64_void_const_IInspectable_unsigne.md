# StateRepository::DictionarySerialization::WinRTReader::Deserialize(unsigned __int64,void const *,IInspectable * *,unsigned __int64 *)

- ea: `0x180023484`
- end: `0x18002371f`
- name: `?Deserialize@WinRTReader@DictionarySerialization@StateRepository@@QEAAJ_KPEBXPEAPEAUIInspectable@@PEA_K@Z`
- size: `667`
- prototype: `__int64 __fastcall(StateRepository::DictionarySerialization::WinRTReader *this, unsigned __int64, unsigned int *, struct IInspectable **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021718`
- `0x180023728`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x18000b348`
- `0x1800214a4`
- `0x180021544`
- `0x180023484`
- `0x180023910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002353d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002353d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023524`

## string_xrefs

- `0x1800234d7`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x18002355a`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x18002359a`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023626`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x18002363c`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x1800236ab`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::WinRTReader::Deserialize(
        StateRepository::DictionarySerialization::WinRTReader *this,
        unsigned __int64 a2,
        unsigned int *a3,
        struct IInspectable **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 *v5; // r12
  __int64 v9; // rdx
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  int v16; // r9d
  __int64 v17; // rdx
  unsigned int v18; // r13d
  unsigned int i; // r14d
  int v20; // eax
  unsigned int v21; // r12d
  int v23; // [rsp+20h] [rbp-51h]
  int v24; // [rsp+20h] [rbp-51h]
  int v25; // [rsp+20h] [rbp-51h]
  int v26[2]; // [rsp+30h] [rbp-41h] BYREF
  struct IInspectable *v27; // [rsp+38h] [rbp-39h] BYREF
  __int64 v28; // [rsp+40h] [rbp-31h] BYREF
  StateRepository::DictionarySerialization::WinRTReader *v29; // [rsp+48h] [rbp-29h]
  unsigned __int64 *v30; // [rsp+50h] [rbp-21h]
  HSTRING string; // [rsp+58h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v5 = a5;
  v30 = a5;
  v29 = this;
  if ( !a2 || a3 )
  {
    if ( !a4 )
    {
      v9 = 25;
      goto LABEL_4;
    }
    if ( *a4 )
    {
      v10 = -2147024809;
      v9 = 26;
      goto LABEL_5;
    }
    v27 = 0;
    if ( WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
            string,
            &v27);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)(unsigned int)v11,
        v23);
LABEL_40:
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v27);
      return v10;
    }
    *(_QWORD *)v26 = 0;
    v12 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            &v27,
            v26);
    v10 = v12;
    if ( v12 < 0 )
    {
      v13 = (unsigned int)v12;
      v14 = 32;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)v13,
        v23);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v26);
      goto LABEL_40;
    }
    v15 = 0;
    if ( a2 )
    {
      if ( !a3 )
      {
        v10 = -2147467261;
        v14 = 37;
        v13 = 2147500035LL;
        goto LABEL_16;
      }
      v16 = 12;
      if ( a2 < 0xC )
      {
        v17 = 83;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
          (const char *)0x80670005LL,
          v23);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
          (const char *)0x80670005LL,
          v24);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v26);
        v10 = -2140733435;
        goto LABEL_40;
      }
      if ( *a3 != 826561107 )
      {
        v17 = 85;
        goto LABEL_30;
      }
      if ( a3[1] > 0x4400300C )
      {
        v17 = 86;
        goto LABEL_30;
      }
      v18 = a3[2];
      if ( v18 > 0x400 )
      {
        v17 = 87;
        goto LABEL_30;
      }
      v15 = a3[1];
      if ( v15 > a2 )
      {
        v17 = 88;
        goto LABEL_30;
      }
      for ( i = 0; i < v18; ++i )
      {
        v28 = 0;
        v20 = StateRepository::DictionarySerialization::WinRTReader::ProcessPair(
                (_DWORD)v29,
                a2,
                (_DWORD)a3,
                v16,
                *(__int64 *)v26,
                (__int64)&v28);
        v21 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)(unsigned int)v20,
            v25);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v26);
          v10 = v21;
          goto LABEL_40;
        }
        v16 = v28;
      }
      v5 = v30;
    }
    *a4 = v27;
    v27 = 0;
    if ( v5 )
      *v5 = v15;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v26);
    v10 = 0;
    goto LABEL_40;
  }
  v9 = 24;
LABEL_4:
  v10 = -2147467261;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
    (const char *)v10,
    v23);
  return v10;
}

```

## disassembly

```asm
0x180023484  push    rbp
0x180023486  push    rbx
0x180023487  push    rsi
0x180023488  push    rdi
0x180023489  push    r12
0x18002348b  push    r13
0x18002348d  push    r14
0x18002348f  push    r15
0x180023491  lea     rbp, [rsp-17h]
0x180023496  sub     rsp, 88h
0x18002349d  mov     rax, cs:__security_cookie
0x1800234a4  xor     rax, rsp
0x1800234a7  mov     [rbp+4Fh+var_48], rax
0x1800234ab  mov     r12, [rbp+4Fh+arg_20]
0x1800234af  mov     r15, r9
0x1800234b2  mov     [rbp+4Fh+var_70], r12
0x1800234b6  mov     rdi, r8
0x1800234b9  mov     [rbp+4Fh+var_78], rcx
0x1800234bd  mov     rsi, rdx
0x1800234c0  test    rdx, rdx
0x1800234c3  jz      short loc_1800234EB
0x1800234c5  test    r8, r8
0x1800234c8  jnz     short loc_1800234EB
0x1800234ca  lea     edx, [r8+18h]; void *
0x1800234ce  mov     ebx, 80004003h
0x1800234d3  mov     rcx, [rbp+57h]; this
0x1800234d7  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1800234de  mov     r9d, ebx; char *
0x1800234e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800234e6  jmp     loc_1800236FD
0x1800234eb  test    r15, r15
0x1800234ee  jnz     short loc_1800234F6
0x1800234f0  lea     edx, [r15+19h]
0x1800234f4  jmp     short loc_1800234CE
0x1800234f6  cmp     qword ptr [r9], 0
0x1800234fa  jz      short loc_180023508
0x1800234fc  mov     ebx, 80070057h
0x180023501  mov     edx, 1Ah
0x180023506  jmp     short loc_1800234D3
0x180023508  lea     r9, [rbp+4Fh+string]; string
0x18002350c  mov     [rbp+4Fh+var_88], 0
0x180023514  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180023518  mov     edx, 2Ah ; '*'; length
0x18002351d  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180023524  call    cs:__imp_WindowsCreateStringReference
0x18002352a  test    eax, eax
0x18002352c  jns     short loc_180023543
0x18002352e  xor     r9d, r9d; lpArguments
0x180023531  xor     r8d, r8d; nNumberOfArguments
0x180023534  mov     ecx, 0C000000Dh; dwExceptionCode
0x180023539  lea     edx, [r9+1]; dwExceptionFlags
0x18002353d  call    cs:__imp_RaiseException
0x180023543  mov     rcx, [rbp+4Fh+string]
0x180023547  lea     rdx, [rbp+4Fh+var_88]
0x18002354b  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180023550  mov     ebx, eax
0x180023552  test    eax, eax
0x180023554  jns     short loc_180023573
0x180023556  mov     rcx, [rbp+57h]; this
0x18002355a  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180023561  mov     r9d, eax; char *
0x180023564  mov     edx, 1Dh; void *
0x180023569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002356e  jmp     loc_1800236F4
0x180023573  lea     rdx, [rbp+4Fh+var_90]
0x180023577  mov     qword ptr [rbp+4Fh+var_90], 0
0x18002357f  lea     rcx, [rbp+4Fh+var_88]
0x180023583  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180023588  mov     ebx, eax
0x18002358a  test    eax, eax
0x18002358c  jns     short loc_1800235B4
0x18002358e  mov     r9d, eax; char *
0x180023591  mov     edx, 20h ; ' '; void *
0x180023596  mov     rcx, [rbp+57h]; this
0x18002359a  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1800235a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800235a6  lea     rcx, [rbp+4Fh+var_90]
0x1800235aa  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800235af  jmp     loc_1800236F4
0x1800235b4  xor     ebx, ebx
0x1800235b6  test    rsi, rsi
0x1800235b9  jz      loc_1800236D1
0x1800235bf  test    rdi, rdi
0x1800235c2  jnz     short loc_1800235D1
0x1800235c4  mov     ebx, 80004003h
0x1800235c9  lea     edx, [rdi+25h]
0x1800235cc  mov     r9d, ebx
0x1800235cf  jmp     short loc_180023596
0x1800235d1  mov     r9d, 0Ch
0x1800235d7  cmp     rsi, r9
0x1800235da  jnb     short loc_1800235E2
0x1800235dc  lea     edx, [r9+47h]
0x1800235e0  jmp     short loc_180023622
0x1800235e2  cmp     dword ptr [rdi], 31445253h
0x1800235e8  jz      short loc_1800235F1
0x1800235ea  mov     edx, 55h ; 'U'
0x1800235ef  jmp     short loc_180023622
0x1800235f1  cmp     dword ptr [rdi+4], 4400300Ch
0x1800235f8  jbe     short loc_180023601
0x1800235fa  mov     edx, 56h ; 'V'
0x1800235ff  jmp     short loc_180023622
0x180023601  mov     r13d, [rdi+8]
0x180023605  cmp     r13d, 400h
0x18002360c  jbe     short loc_180023615
0x18002360e  mov     edx, 57h ; 'W'
0x180023613  jmp     short loc_180023622
0x180023615  mov     ebx, [rdi+4]
0x180023618  cmp     rbx, rsi
0x18002361b  jbe     short loc_180023666
0x18002361d  mov     edx, 58h ; 'X'; void *
0x180023622  mov     rcx, [rbp+57h]; this
0x180023626  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x18002362d  mov     r9d, 80670005h; char *
0x180023633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023638  mov     rcx, [rbp+57h]; this
0x18002363c  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180023643  mov     r9d, 80670005h; char *
0x180023649  mov     edx, 28h ; '('; void *
0x18002364e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023653  lea     rcx, [rbp+4Fh+var_90]
0x180023657  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18002365c  mov     ebx, 80670005h
0x180023661  jmp     loc_1800236F4
0x180023666  xor     r14d, r14d
0x180023669  cmp     r14d, r13d
0x18002366c  jnb     short loc_1800236CD
0x18002366e  mov     rcx, [rbp+4Fh+var_78]
0x180023672  lea     rax, [rbp+4Fh+var_80]
0x180023676  mov     [rsp+0C0h+var_98], rax
0x18002367b  mov     r8, rdi
0x18002367e  mov     rax, qword ptr [rbp+4Fh+var_90]
0x180023682  mov     rdx, rsi
0x180023685  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18002368a  mov     [rbp+4Fh+var_80], 0
0x180023692  call    ?ProcessPair@WinRTReader@DictionarySerialization@StateRepository@@AEAAJ_KPEBE_KPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEA_K@Z; StateRepository::DictionarySerialization::WinRTReader::ProcessPair(unsigned __int64,uchar const *,unsigned __int64,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,unsigned __int64 *)
0x180023697  mov     r12d, eax
0x18002369a  test    eax, eax
0x18002369c  js      short loc_1800236A7
0x18002369e  mov     r9, [rbp+4Fh+var_80]
0x1800236a2  inc     r14d
0x1800236a5  jmp     short loc_180023669
0x1800236a7  mov     rcx, [rbp+57h]; this
0x1800236ab  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1800236b2  mov     r9d, r12d; char *
0x1800236b5  mov     edx, 2Fh ; '/'; void *
0x1800236ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800236bf  lea     rcx, [rbp+4Fh+var_90]
0x1800236c3  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800236c8  mov     ebx, r12d
0x1800236cb  jmp     short loc_1800236F4
0x1800236cd  mov     r12, [rbp+4Fh+var_70]
0x1800236d1  mov     rax, [rbp+4Fh+var_88]
0x1800236d5  mov     [r15], rax
0x1800236d8  mov     [rbp+4Fh+var_88], 0
0x1800236e0  test    r12, r12
0x1800236e3  jz      short loc_1800236E9
0x1800236e5  mov     [r12], rbx
0x1800236e9  lea     rcx, [rbp+4Fh+var_90]
0x1800236ed  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800236f2  xor     ebx, ebx
0x1800236f4  lea     rcx, [rbp+4Fh+var_88]
0x1800236f8  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800236fd  mov     eax, ebx
0x1800236ff  mov     rcx, [rbp+4Fh+var_48]
0x180023703  xor     rcx, rsp; StackCookie
0x180023706  call    __security_check_cookie
0x18002370b  add     rsp, 88h
0x180023712  pop     r15
0x180023714  pop     r14
0x180023716  pop     r13
0x180023718  pop     r12
0x18002371a  pop     rdi
0x18002371b  pop     rsi
0x18002371c  pop     rbx
0x18002371d  pop     rbp
0x18002371e  retn
```
