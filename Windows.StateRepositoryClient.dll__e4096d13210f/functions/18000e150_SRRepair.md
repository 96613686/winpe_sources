# SRRepair

- ea: `0x18000e150`
- end: `0x18000e399`
- name: `SRRepair`
- size: `585`
- prototype: `__int64 __fastcall(PCWSTR sourceString, unsigned int, _DWORD *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800018f8`
- `0x180002980`
- `0x18000719c`
- `0x1800075e4`
- `0x180008b00`
- `0x180008bd4`
- `0x18000b348`
- `0x18000c408`
- `0x18000e150`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e2fc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e2fc`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000e19c`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000e19c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e310`

## pseudocode

```c
__int64 __fastcall SRRepair(PCWSTR sourceString, unsigned int a2, _DWORD *a3, int *a4)
{
  unsigned __int64 v6; // rdi
  HRESULT ApartmentType; // eax
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  const wchar_t *v17; // rcx
  _QWORD *v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  _QWORD *v21; // r12
  const WCHAR *v22; // rbx
  __int64 v23; // rax
  __int64 (__fastcall *v24)(_QWORD *, HSTRING, _QWORD, int *); // r13
  int *v26; // [rsp+20h] [rbp-79h]
  APTTYPE pAptType; // [rsp+50h] [rbp-49h] BYREF
  UINT32 length; // [rsp+54h] [rbp-45h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v30; // [rsp+5Ch] [rbp-3Dh] BYREF
  int v31; // [rsp+60h] [rbp-39h] BYREF
  int v32; // [rsp+64h] [rbp-35h] BYREF
  APTTYPE v33; // [rsp+68h] [rbp-31h] BYREF
  _QWORD *v34; // [rsp+70h] [rbp-29h] BYREF
  __int64 v35; // [rsp+78h] [rbp-21h] BYREF
  const wchar_t *v36; // [rsp+80h] [rbp-19h] BYREF
  HSTRING string; // [rsp+88h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v30 = a2;
  v6 = -1;
  pAptType = APTTYPE_CURRENT;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  v11 = ApartmentType;
  if ( ApartmentType >= 0 )
  {
    if ( (pAptType != APTTYPE_MTA || pAptQualifier)
      && (pAptType != APTTYPE_NA || pAptQualifier != APTTYPEQUALIFIER_NA_ON_MTA) )
    {
      v14 = StateRepository::Tracing::Client::Provider();
      if ( *(_DWORD *)v14 > 3u )
      {
        length = pAptQualifier;
        v33 = pAptType;
        v17 = L"<machine>";
        if ( sourceString )
          v17 = sourceString;
        v35 = 0x1000000;
        v36 = v17;
        v30 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (_DWORD)v14,
          (unsigned int)word_1800300BA,
          v15,
          v16,
          (__int64)&v36,
          (__int64)&v30,
          (__int64)&v33,
          (__int64)&length,
          (__int64)&v35);
      }
      v11 = -2147019873;
      v12 = 136;
      goto LABEL_3;
    }
    v34 = 0;
    v18 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[62])v10);
    v19 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(
            *v18,
            &v34);
    v11 = v19;
    if ( v19 >= 0 )
    {
      v21 = v34;
      v22 = &dword_18002C434;
      v31 = 0;
      v32 = 0;
      if ( sourceString )
        v22 = sourceString;
      v23 = *v34;
      length = 0;
      v24 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD, int *))(v23 + 104);
      do
        ++v6;
      while ( v22[v6] );
      if ( (int)ULongLongToUInt(v6, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(v22, length, &hstringHeader, &string);
      v26 = &v32;
      v19 = v24(v21, string, v30, &v31);
      v11 = v19;
      if ( v19 >= 0 )
      {
        if ( a3 )
          *a3 = v31;
        if ( a4 )
          *a4 = v32;
        v11 = 0;
        goto LABEL_32;
      }
      v20 = 153;
    }
    else
    {
      v20 = 149;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)v19,
      (int)v26);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v34);
    return v11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
    (const char *)(unsigned int)ApartmentType,
    (int)v26);
  v12 = 124;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
    (const char *)v11,
    (int)v26);
  return v11;
}

```

## disassembly

```asm
0x18000e150  push    rbp
0x18000e152  push    rbx
0x18000e153  push    rsi
0x18000e154  push    rdi
0x18000e155  push    r12
0x18000e157  push    r13
0x18000e159  push    r14
0x18000e15b  push    r15
0x18000e15d  lea     rbp, [rsp-1Fh]
0x18000e162  sub     rsp, 0B8h
0x18000e169  mov     rax, cs:__security_cookie
0x18000e170  xor     rax, rsp
0x18000e173  mov     [rbp+57h+var_48], rax
0x18000e177  mov     r12d, edx
0x18000e17a  mov     [rbp+57h+var_94], edx
0x18000e17d  mov     r14, rcx
0x18000e180  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18000e184  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e188  lea     rcx, [rbp+57h+pAptType]; pAptType
0x18000e18c  xor     r13d, r13d
0x18000e18f  mov     [rbp+57h+pAptType], edi
0x18000e192  mov     [rbp+57h+pAptQualifier], r13d
0x18000e196  mov     rsi, r9
0x18000e199  mov     r15, r8
0x18000e19c  call    cs:__imp_CoGetApartmentType
0x18000e1a2  mov     ebx, eax
0x18000e1a4  test    eax, eax
0x18000e1a6  jns     short loc_18000E1D9
0x18000e1a8  mov     rcx, [rbp+5Fh]; this
0x18000e1ac  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000e1b3  mov     r9d, eax; char *
0x18000e1b6  lea     edx, [rdi+29h]; void *
0x18000e1b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1be  lea     edx, [rdi+7Dh]; void *
0x18000e1c1  mov     rcx, [rbp+5Fh]; this
0x18000e1c5  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000e1cc  mov     r9d, ebx; char *
0x18000e1cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1d4  jmp     loc_18000E377
0x18000e1d9  cmp     [rbp+57h+pAptType], 1
0x18000e1dd  mov     eax, [rbp+57h+pAptQualifier]
0x18000e1e0  jnz     short loc_18000E1E6
0x18000e1e2  test    eax, eax
0x18000e1e4  jz      short loc_18000E1F1
0x18000e1e6  cmp     [rbp+57h+pAptType], 2
0x18000e1ea  jnz     short loc_18000E1F5
0x18000e1ec  cmp     eax, 2
0x18000e1ef  jnz     short loc_18000E1F5
0x18000e1f1  mov     al, 1
0x18000e1f3  jmp     short loc_18000E1F8
0x18000e1f5  mov     al, r13b
0x18000e1f8  test    al, al
0x18000e1fa  jnz     loc_18000E281
0x18000e200  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x18000e205  mov     ecx, [rax]
0x18000e207  cmp     ecx, 3
0x18000e20a  jbe     short loc_18000E272
0x18000e20c  mov     ecx, [rbp+57h+pAptQualifier]
0x18000e20f  lea     rdx, word_1800300BA
0x18000e216  mov     [rbp+57h+length], ecx
0x18000e219  test    r14, r14
0x18000e21c  mov     ecx, [rbp+57h+pAptType]
0x18000e21f  mov     [rbp+57h+var_88], ecx
0x18000e222  lea     rcx, aMachine; "<machine>"
0x18000e229  cmovnz  rcx, r14
0x18000e22d  mov     [rbp+57h+var_78], 1000000h
0x18000e235  mov     [rbp+57h+var_70], rcx
0x18000e239  lea     rcx, [rbp+57h+var_78]
0x18000e23d  mov     [rsp+0F0h+var_B0], rcx
0x18000e242  lea     rcx, [rbp+57h+length]
0x18000e246  mov     [rsp+0F0h+var_B8], rcx
0x18000e24b  lea     rcx, [rbp+57h+var_88]
0x18000e24f  mov     [rsp+0F0h+var_C0], rcx
0x18000e254  lea     rcx, [rbp+57h+var_94]
0x18000e258  mov     [rsp+0F0h+var_C8], rcx
0x18000e25d  lea     rcx, [rbp+57h+var_70]
0x18000e261  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x18000e266  mov     rcx, rax
0x18000e269  mov     [rbp+57h+var_94], r12d
0x18000e26d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000e272  mov     ebx, 8007139Fh
0x18000e277  mov     edx, 88h
0x18000e27c  jmp     loc_18000E1C1
0x18000e281  lea     rcx, [rbp+57h+string]; string
0x18000e285  mov     [rbp+57h+var_80], r13
0x18000e289  call    ??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[62])
0x18000e28e  lea     rdx, [rbp+57h+var_80]
0x18000e292  mov     rcx, [rax]
0x18000e295  call    ??$ActivateInstance@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>)
0x18000e29a  mov     ebx, eax
0x18000e29c  test    eax, eax
0x18000e29e  jns     short loc_18000E2AA
0x18000e2a0  mov     edx, 95h
0x18000e2a5  jmp     loc_18000E341
0x18000e2aa  mov     r12, [rbp+57h+var_80]
0x18000e2ae  lea     rbx, dword_18002C434
0x18000e2b5  mov     [rbp+57h+var_90], r13d
0x18000e2b9  test    r14, r14
0x18000e2bc  mov     [rbp+57h+var_8C], r13d
0x18000e2c0  cmovnz  rbx, r14
0x18000e2c4  xor     r14d, r14d
0x18000e2c7  mov     rax, [r12]
0x18000e2cb  mov     [rbp+57h+length], r14d
0x18000e2cf  mov     r13, [rax+68h]
0x18000e2d3  inc     rdi
0x18000e2d6  cmp     [rbx+rdi*2], r14w
0x18000e2db  jnz     short loc_18000E2D3
0x18000e2dd  lea     rdx, [rbp+57h+length]; unsigned int *
0x18000e2e1  mov     rcx, rdi; unsigned __int64
0x18000e2e4  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18000e2e9  test    eax, eax
0x18000e2eb  jns     short loc_18000E302
0x18000e2ed  xor     r9d, r9d; lpArguments
0x18000e2f0  xor     r8d, r8d; nNumberOfArguments
0x18000e2f3  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000e2f8  lea     edx, [r9+1]; dwExceptionFlags
0x18000e2fc  call    cs:__imp_RaiseException
0x18000e302  mov     edx, [rbp+57h+length]; length
0x18000e305  lea     r9, [rbp+57h+string]; string
0x18000e309  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000e30d  mov     rcx, rbx; sourceString
0x18000e310  call    cs:__imp_WindowsCreateStringReference
0x18000e316  mov     r8d, [rbp+57h+var_94]
0x18000e31a  lea     rax, [rbp+57h+var_8C]
0x18000e31e  mov     rdx, [rbp+57h+string]
0x18000e322  lea     r9, [rbp+57h+var_90]
0x18000e326  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18000e32b  mov     rcx, r12
0x18000e32e  mov     rax, r13
0x18000e331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e336  mov     ebx, eax
0x18000e338  test    eax, eax
0x18000e33a  jns     short loc_18000E356
0x18000e33c  mov     edx, 99h; void *
0x18000e341  mov     rcx, [rbp+5Fh]; this
0x18000e345  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000e34c  mov     r9d, eax; char *
0x18000e34f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e354  jmp     short loc_18000E36E
0x18000e356  test    r15, r15
0x18000e359  jz      short loc_18000E361
0x18000e35b  mov     eax, [rbp+57h+var_90]
0x18000e35e  mov     [r15], eax
0x18000e361  test    rsi, rsi
0x18000e364  jz      short loc_18000E36B
0x18000e366  mov     eax, [rbp+57h+var_8C]
0x18000e369  mov     [rsi], eax
0x18000e36b  mov     ebx, r14d
0x18000e36e  lea     rcx, [rbp+57h+var_80]
0x18000e372  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000e377  mov     eax, ebx
0x18000e379  mov     rcx, [rbp+57h+var_48]
0x18000e37d  xor     rcx, rsp; StackCookie
0x18000e380  call    __security_check_cookie
0x18000e385  add     rsp, 0B8h
0x18000e38c  pop     r15
0x18000e38e  pop     r14
0x18000e390  pop     r13
0x18000e392  pop     r12
0x18000e394  pop     rdi
0x18000e395  pop     rsi
0x18000e396  pop     rbx
0x18000e397  pop     rbp
0x18000e398  retn
```
