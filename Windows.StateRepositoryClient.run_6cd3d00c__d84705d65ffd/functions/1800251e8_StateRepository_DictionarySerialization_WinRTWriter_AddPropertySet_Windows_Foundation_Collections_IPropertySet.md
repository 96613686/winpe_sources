# StateRepository::DictionarySerialization::WinRTWriter::AddPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1800251e8`
- end: `0x180025452`
- name: `?AddPropertySet@WinRTWriter@DictionarySerialization@StateRepository@@AEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(StateRepository::DictionarySerialization::WinRTWriter *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e010`
- `0x180024170`

## callees

- `0x1800075e4`
- `0x18000b348`
- `0x180024150`
- `0x180024170`
- `0x1800251e8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025375`

## string_xrefs

- `0x18002524c`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x18002529a`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x1800253c3`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x1800253f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x18002540b`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::WinRTWriter::AddPropertySet(
        StateRepository::DictionarySerialization::WinRTWriter *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  int i; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, struct IInspectable **); // rbx
  int v17; // eax
  struct IInspectable *v18; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v20; // rdx
  struct IInspectable *v22; // [rsp+20h] [rbp-20h] BYREF
  HSTRING string; // [rsp+28h] [rbp-18h] BYREF
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v25; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  char v27; // [rsp+68h] [rbp+28h] BYREF
  __int64 v28; // [rsp+70h] [rbp+30h] BYREF
  __int64 v29; // [rsp+78h] [rbp+38h] BYREF

  v25 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)a2 + 8LL))(a2);
  v24 = 0;
  v4 = **(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *))a2;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v24);
  v5 = v4(a2, &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204, &v24);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v24;
    v28 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v28);
    v9 = v8(v7, &v28);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v27 = 0;
      for ( i = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v28 + 56LL))(v28, &v27);
            ;
            i = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v28 + 64LL))(v28, &v27) )
      {
        v6 = i;
        if ( i < 0 || !v27 )
          goto LABEL_22;
        v11 = v28;
        v29 = 0;
        v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
        v13 = v12(v11, &v29);
        v6 = v13;
        if ( v13 < 0 )
          break;
        string = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 48LL))(v29, &string);
        v6 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5A,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
            (const char *)(unsigned int)v14,
            (int)v22);
          goto LABEL_17;
        }
        v15 = v29;
        v22 = 0;
        v16 = *(__int64 (__fastcall **)(__int64, struct IInspectable **))(*(_QWORD *)v29 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v22);
        v17 = v16(v15, &v22);
        v6 = v17;
        if ( v17 < 0 )
        {
          v20 = 93;
LABEL_16:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
            (const char *)(unsigned int)v17,
            (int)v22);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v22);
LABEL_17:
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
LABEL_21:
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
          goto LABEL_22;
        }
        v18 = v22;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v17 = StateRepository::DictionarySerialization::WinRTWriter::AddKeyValue(this, StringRawBuffer, v18);
        v6 = v17;
        if ( v17 < 0 )
        {
          v20 = 94;
          goto LABEL_16;
        }
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v22);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
        (const char *)(unsigned int)v13,
        (int)v22);
      goto LABEL_21;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
      (const char *)(unsigned int)v9,
      (int)v22);
LABEL_22:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v28);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
      (const char *)(unsigned int)v5,
      (int)v22);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v25);
  return v6;
}

```

## disassembly

```asm
0x1800251e8  mov     [rsp-18h+arg_0], rbx
0x1800251ed  push    rbp
0x1800251ee  push    rsi
0x1800251ef  push    rdi
0x1800251f0  mov     rbp, rsp
0x1800251f3  sub     rsp, 40h
0x1800251f7  mov     [rbp+var_8], rdx
0x1800251fb  mov     rdi, rdx
0x1800251fe  mov     rsi, rcx
0x180025201  test    rdx, rdx
0x180025204  jz      short loc_180025215
0x180025206  mov     rax, [rdx]
0x180025209  mov     rcx, rdx
0x18002520c  mov     rax, [rax+8]
0x180025210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025215  mov     [rbp+var_10], 0
0x18002521d  lea     rcx, [rbp+var_10]
0x180025221  mov     rax, [rdi]
0x180025224  mov     rbx, [rax]
0x180025227  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18002522c  lea     r8, [rbp+var_10]
0x180025230  mov     rcx, rdi
0x180025233  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x18002523a  mov     rax, rbx
0x18002523d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025242  mov     ebx, eax
0x180025244  test    eax, eax
0x180025246  jns     short loc_180025265
0x180025248  mov     rcx, [rbp+18h]; this
0x18002524c  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x180025253  mov     r9d, eax; char *
0x180025256  mov     edx, 4Dh ; 'M'; void *
0x18002525b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025260  jmp     loc_180025431
0x180025265  mov     rdi, [rbp+var_10]
0x180025269  lea     rcx, [rbp+arg_10]
0x18002526d  mov     [rbp+arg_10], 0
0x180025275  mov     rax, [rdi]
0x180025278  mov     rbx, [rax+30h]
0x18002527c  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180025281  lea     rdx, [rbp+arg_10]
0x180025285  mov     rcx, rdi
0x180025288  mov     rax, rbx
0x18002528b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025290  mov     ebx, eax
0x180025292  test    eax, eax
0x180025294  jns     short loc_1800252B3
0x180025296  mov     rcx, [rbp+18h]; this
0x18002529a  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x1800252a1  mov     r9d, eax; char *
0x1800252a4  mov     edx, 50h ; 'P'; void *
0x1800252a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800252ae  jmp     loc_180025428
0x1800252b3  mov     rcx, [rbp+arg_10]
0x1800252b7  mov     [rbp+arg_8], 0
0x1800252bb  mov     rax, [rcx]
0x1800252be  mov     rax, [rax+38h]
0x1800252c2  lea     rdx, [rbp+arg_8]
0x1800252c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252cb  mov     ebx, eax
0x1800252cd  test    eax, eax
0x1800252cf  js      loc_180025428
0x1800252d5  cmp     [rbp+arg_8], 0
0x1800252d9  jz      loc_180025428
0x1800252df  mov     rdi, [rbp+arg_10]
0x1800252e3  lea     rcx, [rbp+arg_18]
0x1800252e7  mov     [rbp+arg_18], 0
0x1800252ef  mov     rax, [rdi]
0x1800252f2  mov     rbx, [rax+30h]
0x1800252f6  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800252fb  lea     rdx, [rbp+arg_18]
0x1800252ff  mov     rcx, rdi
0x180025302  mov     rax, rbx
0x180025305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002530a  mov     ebx, eax
0x18002530c  test    eax, eax
0x18002530e  js      loc_180025407
0x180025314  mov     rcx, [rbp+arg_18]
0x180025318  lea     rdx, [rbp+string]
0x18002531c  mov     [rbp+string], 0
0x180025324  mov     rax, [rcx]
0x180025327  mov     rax, [rax+30h]
0x18002532b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025330  mov     ebx, eax
0x180025332  test    eax, eax
0x180025334  js      loc_1800253ED
0x18002533a  mov     rdi, [rbp+arg_18]
0x18002533e  lea     rcx, [rbp+var_20]
0x180025342  mov     [rbp+var_20], 0
0x18002534a  mov     rax, [rdi]
0x18002534d  mov     rbx, [rax+38h]
0x180025351  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180025356  lea     rdx, [rbp+var_20]
0x18002535a  mov     rcx, rdi
0x18002535d  mov     rax, rbx
0x180025360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025365  mov     ebx, eax
0x180025367  test    eax, eax
0x180025369  js      short loc_1800253E6
0x18002536b  mov     rcx, [rbp+string]; string
0x18002536f  xor     edx, edx; length
0x180025371  mov     rbx, [rbp+var_20]
0x180025375  call    cs:__imp_WindowsGetStringRawBuffer
0x18002537b  mov     r8, rbx; struct IInspectable *
0x18002537e  mov     rcx, rsi; this
0x180025381  mov     rdx, rax; unsigned __int16 *
0x180025384  call    ?AddKeyValue@WinRTWriter@DictionarySerialization@StateRepository@@AEAAJPEBGPEAUIInspectable@@@Z; StateRepository::DictionarySerialization::WinRTWriter::AddKeyValue(ushort const *,IInspectable *)
0x180025389  mov     ebx, eax
0x18002538b  test    eax, eax
0x18002538d  js      short loc_1800253BA
0x18002538f  lea     rcx, [rbp+var_20]
0x180025393  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180025398  lea     rcx, [rbp+string]; this
0x18002539c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800253a1  lea     rcx, [rbp+arg_18]
0x1800253a5  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800253aa  mov     rcx, [rbp+arg_10]
0x1800253ae  mov     rax, [rcx]
0x1800253b1  mov     rax, [rax+40h]
0x1800253b5  jmp     loc_1800252C2
0x1800253ba  mov     edx, 5Eh ; '^'; void *
0x1800253bf  mov     rcx, [rbp+18h]; this
0x1800253c3  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x1800253ca  mov     r9d, eax; char *
0x1800253cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800253d2  lea     rcx, [rbp+var_20]
0x1800253d6  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800253db  lea     rcx, [rbp+string]; this
0x1800253df  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800253e4  jmp     short loc_18002541F
0x1800253e6  mov     edx, 5Dh ; ']'
0x1800253eb  jmp     short loc_1800253BF
0x1800253ed  mov     rcx, [rbp+18h]; this
0x1800253f1  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x1800253f8  mov     r9d, eax; char *
0x1800253fb  mov     edx, 5Ah ; 'Z'; void *
0x180025400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025405  jmp     short loc_1800253DB
0x180025407  mov     rcx, [rbp+18h]; this
0x18002540b  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x180025412  mov     r9d, eax; char *
0x180025415  mov     edx, 57h ; 'W'; void *
0x18002541a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002541f  lea     rcx, [rbp+arg_18]
0x180025423  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180025428  lea     rcx, [rbp+arg_10]
0x18002542c  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180025431  lea     rcx, [rbp+var_10]
0x180025435  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18002543a  lea     rcx, [rbp+var_8]
0x18002543e  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180025443  mov     eax, ebx
0x180025445  mov     rbx, [rsp+40h+arg_0]
0x18002544a  add     rsp, 40h
0x18002544e  pop     rdi
0x18002544f  pop     rsi
0x180025450  pop     rbp
0x180025451  retn
```
