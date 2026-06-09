# StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(unsigned __int64,void const *,Windows::Foundation::Collections::IPropertySet * *,unsigned __int64 *)

- ea: `0x180023728`
- end: `0x180023858`
- name: `?DeserializeAsPropertySet@WinRTReader@DictionarySerialization@StateRepository@@QEAAJ_KPEBXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEA_K@Z`
- size: `304`
- prototype: `__int64 __fastcall(StateRepository::DictionarySerialization::WinRTReader *__hidden this, unsigned __int64, const void *, struct Windows::Foundation::Collections::IPropertySet **, struct IInspectable *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d050`

## callees

- `0x1800075e4`
- `0x18000b348`
- `0x180023484`
- `0x180023728`
- `0x180027010`

## string_xrefs

- `0x180023752`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x1800237a9`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x1800237ff`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(
        StateRepository::DictionarySerialization::WinRTReader *this,
        unsigned __int64 a2,
        unsigned int *a3,
        struct Windows::Foundation::Collections::IPropertySet **a4,
        struct IInspectable *a5)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax
  struct IInspectable *v9; // rbx
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rdi
  int v11; // eax
  int v13; // [rsp+20h] [rbp-18h]
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct Windows::Foundation::Collections::IPropertySet *v16; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 && !a3 )
  {
    v6 = 66;
LABEL_4:
    v7 = -2147467261;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)v7,
      v13);
    return v7;
  }
  if ( !a4 )
  {
    v6 = 67;
    goto LABEL_4;
  }
  if ( *a4 )
  {
    v7 = -2147024809;
    v6 = 68;
    goto LABEL_5;
  }
  a5 = 0;
  v8 = StateRepository::DictionarySerialization::WinRTReader::Deserialize(this, a2, a3, &a5, 0);
  v7 = v8;
  if ( v8 >= 0 )
  {
    v9 = a5;
    v16 = 0;
    QueryInterface = a5->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v16);
    v11 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, struct Windows::Foundation::Collections::IPropertySet **))QueryInterface)(
            v9,
            &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
            &v16);
    v7 = v11;
    if ( v11 >= 0 )
    {
      *a4 = v16;
      v16 = 0;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v16);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)(unsigned int)v11,
        v14);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v16);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)(unsigned int)v8,
      v14);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&a5);
  return v7;
}

```

## disassembly

```asm
0x180023728  mov     [rsp+arg_0], rbx
0x18002372d  mov     [rsp+arg_10], rsi
0x180023732  push    rdi
0x180023733  sub     rsp, 30h
0x180023737  mov     rsi, r9
0x18002373a  test    rdx, rdx
0x18002373d  jz      short loc_180023766
0x18002373f  test    r8, r8
0x180023742  jnz     short loc_180023766
0x180023744  lea     edx, [r8+42h]; void *
0x180023748  mov     ebx, 80004003h
0x18002374d  mov     rcx, [rsp+38h]; this
0x180023752  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180023759  mov     r9d, ebx; char *
0x18002375c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023761  jmp     loc_180023846
0x180023766  test    rsi, rsi
0x180023769  jnz     short loc_180023770
0x18002376b  lea     edx, [rsi+43h]
0x18002376e  jmp     short loc_180023748
0x180023770  cmp     qword ptr [r9], 0
0x180023774  jz      short loc_180023782
0x180023776  mov     ebx, 80070057h
0x18002377b  mov     edx, 44h ; 'D'; unsigned __int64
0x180023780  jmp     short loc_18002374D
0x180023782  lea     r9, [rsp+38h+arg_20]; struct IInspectable **
0x180023787  mov     [rsp+38h+arg_20], 0
0x180023790  mov     qword ptr [rsp+38h+var_18], 0; int
0x180023799  call    ?Deserialize@WinRTReader@DictionarySerialization@StateRepository@@QEAAJ_KPEBXPEAPEAUIInspectable@@PEA_K@Z; StateRepository::DictionarySerialization::WinRTReader::Deserialize(unsigned __int64,void const *,IInspectable * *,unsigned __int64 *)
0x18002379e  mov     ebx, eax
0x1800237a0  test    eax, eax
0x1800237a2  jns     short loc_1800237BF
0x1800237a4  mov     rcx, [rsp+38h]; this
0x1800237a9  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1800237b0  mov     r9d, eax; char *
0x1800237b3  mov     edx, 47h ; 'G'; void *
0x1800237b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800237bd  jmp     short loc_18002383C
0x1800237bf  mov     rbx, [rsp+38h+arg_20]
0x1800237c4  lea     rcx, [rsp+38h+arg_8]
0x1800237c9  mov     [rsp+38h+arg_8], 0
0x1800237d2  mov     rax, [rbx]
0x1800237d5  mov     rdi, [rax]
0x1800237d8  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800237dd  lea     r8, [rsp+38h+arg_8]
0x1800237e2  mov     rcx, rbx
0x1800237e5  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x1800237ec  mov     rax, rdi
0x1800237ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f4  mov     ebx, eax
0x1800237f6  test    eax, eax
0x1800237f8  jns     short loc_18002381F
0x1800237fa  mov     rcx, [rsp+38h]; this
0x1800237ff  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180023806  mov     r9d, eax; char *
0x180023809  mov     edx, 49h ; 'I'; void *
0x18002380e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023813  lea     rcx, [rsp+38h+arg_8]
0x180023818  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18002381d  jmp     short loc_18002383C
0x18002381f  mov     rax, [rsp+38h+arg_8]
0x180023824  lea     rcx, [rsp+38h+arg_8]
0x180023829  mov     [rsi], rax
0x18002382c  mov     [rsp+38h+arg_8], 0
0x180023835  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18002383a  xor     ebx, ebx
0x18002383c  lea     rcx, [rsp+38h+arg_20]
0x180023841  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180023846  mov     rsi, [rsp+38h+arg_10]
0x18002384b  mov     eax, ebx
0x18002384d  mov     rbx, [rsp+38h+arg_0]
0x180023852  add     rsp, 30h
0x180023856  pop     rdi
0x180023857  retn
```
