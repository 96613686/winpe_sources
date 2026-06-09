# SRAddOrUpdateUupProduct

- ea: `0x18000c790`
- end: `0x18000ccd8`
- name: `SRAddOrUpdateUupProduct`
- size: `1352`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180002980`
- `0x180002e50`
- `0x180003d04`
- `0x1800075e4`
- `0x180008ab4`
- `0x180008d28`
- `0x18000b348`
- `0x18000c298`
- `0x18000c2e4`
- `0x18000c408`
- `0x18000c790`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cbbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cbbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c8f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ca8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cbd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c8f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ca8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000cbd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c98b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cadb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c84e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c98b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cadb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cb65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc7f`

## pseudocode

```c
__int64 __fastcall SRAddOrUpdateUupProduct(
        const WCHAR *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        const unsigned __int16 **a7)
{
  unsigned int v7; // esi
  unsigned __int64 v9; // r15
  _QWORD *v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rax
  HSTRING_HEADER *v16; // rbx
  unsigned __int64 v17; // rax
  HSTRING *v18; // r14
  unsigned int v19; // edi
  HRESULT v20; // esi
  __int64 v21; // r11
  HSTRING v22; // rcx
  HSTRING *v23; // rdi
  int v24; // r13d
  __int64 v25; // rdx
  HRESULT StringReference; // r14d
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // rax
  HSTRING_HEADER *v29; // rsi
  unsigned __int64 v30; // rax
  HSTRING *v31; // r15
  __int64 v32; // r11
  HSTRING *v33; // r14
  __int64 v34; // rdx
  __int64 v35; // r13
  int v36; // eax
  int v37; // r15d
  int v39; // [rsp+20h] [rbp-81h]
  int v40; // [rsp+20h] [rbp-81h]
  HSTRING string; // [rsp+40h] [rbp-61h] BYREF
  UINT32 length[2]; // [rsp+48h] [rbp-59h] BYREF
  int v43; // [rsp+50h] [rbp-51h]
  const unsigned __int16 **v44; // [rsp+58h] [rbp-49h]
  unsigned int v45; // [rsp+60h] [rbp-41h]
  __int64 v46; // [rsp+68h] [rbp-39h] BYREF
  PCWSTR sourceString; // [rsp+70h] [rbp-31h]
  HSTRING *p_string; // [rsp+78h] [rbp-29h]
  HSTRING v49; // [rsp+80h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]

  v7 = a6;
  v9 = a3;
  sourceString = a1;
  v45 = a3;
  v44 = a7;
  v46 = 0;
  v43 = a6;
  v10 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v49, (const unsigned __int16 (*)[51])a2);
  v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUupProductPackageStatics>>(
          *v10,
          &v46);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)v11,
      v39);
    goto LABEL_70;
  }
  string = 0;
  v13 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, &word_18002C434, 0);
  v12 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)v13,
      v39);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_70;
  }
  v14 = -1;
  if ( !(_DWORD)v9 )
  {
    v24 = 0;
    v16 = 0;
    v23 = 0;
    WindowsDeleteString(string);
    v22 = 0;
    string = 0;
    p_string = &string;
LABEL_25:
    if ( !v7 )
    {
      v29 = 0;
      v33 = 0;
      WindowsDeleteString(v22);
      string = 0;
LABEL_47:
      v35 = v46;
      length[0] = 0;
      v44 = *(const unsigned __int16 ***)(*(_QWORD *)v46 + 160LL);
      do
        ++v14;
      while ( sourceString[v14] );
      if ( (int)ULongLongToUInt(v14, length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(sourceString, length[0], &hstringHeader, &v49);
      v40 = v43;
      v36 = ((__int64 (__fastcall *)(__int64, HSTRING, _QWORD, HSTRING *))v44)(v35, v49, v45, p_string);
      v37 = v36;
      if ( v36 >= 0 )
      {
        if ( v33 )
          operator delete(v33);
        if ( v29 )
          operator delete(v29);
        WindowsDeleteString(string);
        string = 0;
        if ( v23 )
          operator delete(v23);
        if ( v16 )
          operator delete(v16);
        v12 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
          (const char *)(unsigned int)v36,
          v40);
        if ( v33 )
          operator delete(v33);
        if ( v29 )
          operator delete(v29);
        WindowsDeleteString(string);
        string = 0;
        if ( v23 )
          operator delete(v23);
        if ( v16 )
          operator delete(v16);
        v12 = v37;
      }
      goto LABEL_70;
    }
    v27 = v7;
    v28 = 24LL * v7;
    if ( !is_mul_ok(v7, 0x18u) )
      v28 = -1;
    v29 = (HSTRING_HEADER *)operator new[](v28, (const struct std::nothrow_t *)&std::nothrow);
    if ( v29 )
    {
      v30 = 8 * v27;
      if ( !is_mul_ok(v27, 8u) )
        v30 = -1;
      v31 = (HSTRING *)operator new[](v30, (const struct std::nothrow_t *)&std::nothrow);
      if ( v31 )
      {
        while ( 1 )
        {
          *(_QWORD *)length = 0;
          StringReference = StringCchLengthW(v44[v24], 0x7Fu, (unsigned __int64 *)length);
          if ( StringReference < 0 )
            break;
          StringReference = WindowsCreateStringReference(v44[v32], length[0], &v29[v32], &v31[v32]);
          if ( StringReference < 0 )
          {
            v34 = 491;
            goto LABEL_37;
          }
          if ( ++v24 >= (unsigned int)v43 )
          {
            v33 = v31;
            goto LABEL_47;
          }
        }
        v34 = 490;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
          (const char *)(unsigned int)StringReference,
          v39);
        operator delete(v31);
        operator delete(v29);
        WindowsDeleteString(string);
        string = 0;
LABEL_42:
        if ( v23 )
          operator delete(v23);
        if ( !v16 )
          goto LABEL_23;
        goto LABEL_21;
      }
      StringReference = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E5,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
        (const char *)0x8007000ELL,
        v39);
      operator delete(v29);
    }
    else
    {
      StringReference = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E2,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
        (const char *)0x8007000ELL,
        v39);
    }
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_42;
  }
  v15 = 24 * v9;
  if ( !is_mul_ok(v9, 0x18u) )
    v15 = -1;
  v16 = (HSTRING_HEADER *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v16 )
  {
    StringReference = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)0x8007000ELL,
      v39);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_23;
  }
  v17 = 8 * v9;
  if ( !is_mul_ok(v9, 8u) )
    v17 = -1;
  p_string = (HSTRING *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
  v18 = p_string;
  if ( !p_string )
  {
    StringReference = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)0x8007000ELL,
      v39);
    WindowsDeleteString(string);
    string = 0;
LABEL_21:
    operator delete(v16);
LABEL_23:
    v12 = StringReference;
    goto LABEL_70;
  }
  v19 = 0;
  while ( 1 )
  {
    *(_QWORD *)length = 0;
    v20 = StringCchLengthW(*(const unsigned __int16 **)(a4 + 8LL * v19), 0x7Fu, (unsigned __int64 *)length);
    if ( v20 < 0 )
      break;
    v20 = WindowsCreateStringReference(*(PCWSTR *)(a4 + 8 * v21), length[0], &v16[v21], &v18[v21]);
    if ( v20 < 0 )
    {
      v25 = 468;
      goto LABEL_19;
    }
    if ( ++v19 >= (unsigned int)v9 )
    {
      v22 = string;
      v23 = v18;
      v7 = v43;
      v24 = 0;
      goto LABEL_25;
    }
  }
  v25 = 467;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
    (const char *)(unsigned int)v20,
    v39);
  WindowsDeleteString(string);
  string = 0;
  operator delete(v18);
  operator delete(v16);
  v12 = v20;
LABEL_70:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v46);
  return v12;
}

```

## disassembly

```asm
0x18000c790  mov     [rsp-8+arg_8], rbx
0x18000c795  push    rbp
0x18000c796  push    rsi
0x18000c797  push    rdi
0x18000c798  push    r12
0x18000c79a  push    r13
0x18000c79c  push    r14
0x18000c79e  push    r15
0x18000c7a0  lea     rbp, [rsp-0Fh]
0x18000c7a5  sub     rsp, 0B0h
0x18000c7ac  mov     rax, cs:__security_cookie
0x18000c7b3  xor     rax, rsp
0x18000c7b6  mov     [rbp+3Fh+var_40], rax
0x18000c7ba  mov     rax, [rbp+3Fh+arg_30]
0x18000c7be  xor     r14d, r14d
0x18000c7c1  mov     esi, [rbp+3Fh+arg_28]
0x18000c7c4  mov     r13, r9
0x18000c7c7  mov     r15d, r8d
0x18000c7ca  mov     [rbp+3Fh+sourceString], rcx
0x18000c7ce  lea     rcx, [rbp+3Fh+var_60]; string
0x18000c7d2  mov     [rbp+3Fh+var_80], r15d
0x18000c7d6  mov     [rbp+3Fh+var_88], rax
0x18000c7da  mov     [rbp+3Fh+var_78], r14
0x18000c7de  mov     [rbp+3Fh+var_90], esi
0x18000c7e1  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18000c7e6  lea     rdx, [rbp+3Fh+var_78]
0x18000c7ea  mov     rcx, [rax]
0x18000c7ed  call    ??$GetActivationFactory@V?$ComPtr@UIUupProductPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUupProductPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUupProductPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUupProductPackageStatics>>)
0x18000c7f2  mov     ebx, eax
0x18000c7f4  test    eax, eax
0x18000c7f6  jns     short loc_18000C815
0x18000c7f8  mov     rcx, [rbp+47h]; this
0x18000c7fc  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c803  mov     r9d, eax; char *
0x18000c806  mov     edx, 1BFh; void *
0x18000c80b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c810  jmp     loc_18000CCA6
0x18000c815  xor     r8d, r8d; unsigned int
0x18000c818  mov     [rbp+3Fh+string], r14
0x18000c81c  lea     rdx, word_18002C434; unsigned __int16 *
0x18000c823  lea     rcx, [rbp+3Fh+string]; this
0x18000c827  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18000c82c  mov     ebx, eax
0x18000c82e  test    eax, eax
0x18000c830  jns     short loc_18000C85D
0x18000c832  mov     rcx, [rbp+47h]; this
0x18000c836  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c83d  mov     r9d, eax; char *
0x18000c840  mov     edx, 1C7h; void *
0x18000c845  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c84a  mov     rcx, [rbp+3Fh+string]; string
0x18000c84e  call    cs:__imp_WindowsDeleteString
0x18000c854  mov     [rbp+3Fh+string], r14
0x18000c858  jmp     loc_18000CCA6
0x18000c85d  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000c861  test    r15d, r15d
0x18000c864  jz      loc_18000C9D7
0x18000c86a  lea     eax, [r12+19h]
0x18000c86f  mov     rdi, r15
0x18000c872  mul     r15
0x18000c875  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c87c  cmovb   rax, r12
0x18000c880  mov     rcx, rax; unsigned __int64
0x18000c883  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c888  mov     rbx, rax
0x18000c88b  test    rax, rax
0x18000c88e  jz      loc_18000C99F
0x18000c894  lea     eax, [r12+9]
0x18000c899  mul     rdi
0x18000c89c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c8a3  cmovb   rax, r12
0x18000c8a7  mov     rcx, rax; unsigned __int64
0x18000c8aa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c8af  xor     esi, esi
0x18000c8b1  mov     [rbp+3Fh+var_68], rax
0x18000c8b5  mov     r14, rax
0x18000c8b8  test    rax, rax
0x18000c8bb  jz      loc_18000C969
0x18000c8c1  mov     edi, esi
0x18000c8c3  mov     r11d, edi
0x18000c8c6  lea     r8, [rbp+3Fh+length]; unsigned __int64 *
0x18000c8ca  mov     edx, 7Fh; unsigned __int64
0x18000c8cf  mov     qword ptr [rbp+3Fh+length], rsi
0x18000c8d3  mov     rcx, [r13+r11*8+0]; unsigned __int16 *
0x18000c8d8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c8dd  mov     esi, eax
0x18000c8df  test    eax, eax
0x18000c8e1  js      short loc_18000C928
0x18000c8e3  mov     edx, [rbp+3Fh+length]; length
0x18000c8e6  lea     rax, [r11+r11*2]
0x18000c8ea  mov     rcx, [r13+r11*8+0]; sourceString
0x18000c8ef  lea     r8, [rbx+rax*8]; hstringHeader
0x18000c8f3  lea     r9, [r14+r11*8]; string
0x18000c8f7  call    cs:__imp_WindowsCreateStringReference
0x18000c8fd  mov     esi, eax
0x18000c8ff  test    eax, eax
0x18000c901  js      short loc_18000C921
0x18000c903  inc     edi
0x18000c905  mov     esi, 0
0x18000c90a  cmp     edi, r15d
0x18000c90d  jb      short loc_18000C8C3
0x18000c90f  mov     rcx, [rbp+3Fh+string]
0x18000c913  mov     rdi, r14
0x18000c916  mov     esi, [rbp+3Fh+var_90]
0x18000c919  xor     r13d, r13d
0x18000c91c  jmp     loc_18000C9F9
0x18000c921  mov     edx, 1D4h
0x18000c926  jmp     short loc_18000C92D
0x18000c928  mov     edx, 1D3h; void *
0x18000c92d  mov     rcx, [rbp+47h]; this
0x18000c931  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c938  mov     r9d, esi; char *
0x18000c93b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c940  mov     rcx, [rbp+3Fh+string]; string
0x18000c944  call    cs:__imp_WindowsDeleteString
0x18000c94a  mov     rcx, r14; Block
0x18000c94d  mov     [rbp+3Fh+string], 0
0x18000c955  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c95a  mov     rcx, rbx; Block
0x18000c95d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c962  mov     ebx, esi
0x18000c964  jmp     loc_18000CCA6
0x18000c969  mov     rcx, [rbp+47h]; this
0x18000c96d  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c974  mov     r14d, 8007000Eh
0x18000c97a  mov     edx, 1CEh; void *
0x18000c97f  mov     r9d, r14d; char *
0x18000c982  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c987  mov     rcx, [rbp+3Fh+string]; string
0x18000c98b  call    cs:__imp_WindowsDeleteString
0x18000c991  mov     [rbp+3Fh+string], rsi
0x18000c995  mov     rcx, rbx; Block
0x18000c998  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c99d  jmp     short loc_18000C9CF
0x18000c99f  mov     rcx, [rbp+47h]; this
0x18000c9a3  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c9aa  mov     r14d, 8007000Eh
0x18000c9b0  mov     edx, 1CBh; void *
0x18000c9b5  mov     r9d, r14d; char *
0x18000c9b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9bd  mov     rcx, [rbp+3Fh+string]; string
0x18000c9c1  call    cs:__imp_WindowsDeleteString
0x18000c9c7  mov     [rbp+3Fh+string], 0
0x18000c9cf  mov     ebx, r14d
0x18000c9d2  jmp     loc_18000CCA6
0x18000c9d7  mov     rcx, [rbp+3Fh+string]; string
0x18000c9db  xor     r13d, r13d
0x18000c9de  mov     ebx, r13d
0x18000c9e1  mov     edi, r13d
0x18000c9e4  call    cs:__imp_WindowsDeleteString
0x18000c9ea  mov     ecx, r13d; string
0x18000c9ed  lea     rax, [rbp+3Fh+string]
0x18000c9f1  mov     [rbp+3Fh+string], rcx
0x18000c9f5  mov     [rbp+3Fh+var_68], rax
0x18000c9f9  test    esi, esi
0x18000c9fb  jz      loc_18000CB5F
0x18000ca01  mov     r14d, esi
0x18000ca04  mov     eax, 18h
0x18000ca09  mul     r14
0x18000ca0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ca13  cmovb   rax, r12
0x18000ca17  mov     rcx, rax; unsigned __int64
0x18000ca1a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ca1f  mov     rsi, rax
0x18000ca22  test    rax, rax
0x18000ca25  jz      loc_18000CB18
0x18000ca2b  mov     eax, 8
0x18000ca30  mul     r14
0x18000ca33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ca3a  cmovb   rax, r12
0x18000ca3e  mov     rcx, rax; unsigned __int64
0x18000ca41  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ca46  mov     r15, rax
0x18000ca49  test    rax, rax
0x18000ca4c  jz      loc_18000CAF0
0x18000ca52  xor     ecx, ecx
0x18000ca54  mov     qword ptr [rbp+3Fh+length], rcx
0x18000ca58  lea     r8, [rbp+3Fh+length]; unsigned __int64 *
0x18000ca5c  mov     rcx, [rbp+3Fh+var_88]
0x18000ca60  mov     edx, 7Fh; unsigned __int64
0x18000ca65  mov     r11d, r13d
0x18000ca68  mov     rcx, [rcx+r11*8]; unsigned __int16 *
0x18000ca6c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ca71  mov     r14d, eax
0x18000ca74  test    eax, eax
0x18000ca76  js      short loc_18000CAE9
0x18000ca78  mov     edx, [rbp+3Fh+length]; length
0x18000ca7b  lea     rax, [r11+r11*2]
0x18000ca7f  lea     r8, [rsi+rax*8]; hstringHeader
0x18000ca83  mov     rax, [rbp+3Fh+var_88]
0x18000ca87  lea     r9, [r15+r11*8]; string
0x18000ca8b  mov     rcx, [rax+r11*8]; sourceString
0x18000ca8f  call    cs:__imp_WindowsCreateStringReference
0x18000ca95  xor     ecx, ecx
0x18000ca97  mov     r14d, eax
0x18000ca9a  test    eax, eax
0x18000ca9c  js      short loc_18000CAAF
0x18000ca9e  inc     r13d
0x18000caa1  cmp     r13d, [rbp+3Fh+var_90]
0x18000caa5  jb      short loc_18000CA54
0x18000caa7  mov     r14, r15
0x18000caaa  jmp     loc_18000CB75
0x18000caaf  mov     edx, 1EBh; void *
0x18000cab4  mov     rcx, [rbp+47h]; this
0x18000cab8  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000cabf  mov     r9d, r14d; char *
0x18000cac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cac7  mov     rcx, r15; Block
0x18000caca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cacf  mov     rcx, rsi; Block
0x18000cad2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cad7  mov     rcx, [rbp+3Fh+string]; string
0x18000cadb  call    cs:__imp_WindowsDeleteString
0x18000cae1  xor     esi, esi
0x18000cae3  mov     [rbp+3Fh+string], rsi
0x18000cae7  jmp     short loc_18000CB44
0x18000cae9  mov     edx, 1EAh
0x18000caee  jmp     short loc_18000CAB4
0x18000caf0  mov     rcx, [rbp+47h]; this
0x18000caf4  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000cafb  mov     r14d, 8007000Eh
0x18000cb01  mov     edx, 1E5h; void *
0x18000cb06  mov     r9d, r14d; char *
0x18000cb09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb0e  mov     rcx, rsi; Block
0x18000cb11  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb16  jmp     short loc_18000CB36
0x18000cb18  mov     rcx, [rbp+47h]; this
0x18000cb1c  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000cb23  mov     r14d, 8007000Eh
0x18000cb29  mov     edx, 1E2h; void *
0x18000cb2e  mov     r9d, r14d; char *
0x18000cb31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb36  mov     rcx, [rbp+3Fh+string]; string
0x18000cb3a  call    cs:__imp_WindowsDeleteString
0x18000cb40  mov     [rbp+3Fh+string], r13
0x18000cb44  test    rdi, rdi
0x18000cb47  jz      short loc_18000CB51
0x18000cb49  mov     rcx, rdi; Block
0x18000cb4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb51  test    rbx, rbx
0x18000cb54  jz      loc_18000C9CF
0x18000cb5a  jmp     loc_18000C995
0x18000cb5f  mov     rsi, r13
0x18000cb62  mov     r14, r13
0x18000cb65  call    cs:__imp_WindowsDeleteString
0x18000cb6b  xor     ecx, ecx
0x18000cb6d  mov     [rbp+3Fh+string], r13
0x18000cb71  lea     r15, [rbp+3Fh+string]
0x18000cb75  mov     r13, [rbp+3Fh+var_78]
0x18000cb79  mov     [rbp+3Fh+length], ecx
0x18000cb7c  mov     rax, [r13+0]
0x18000cb80  mov     rax, [rax+0A0h]
0x18000cb87  mov     [rbp+3Fh+var_88], rax
0x18000cb8b  mov     rax, [rbp+3Fh+sourceString]
0x18000cb8f  inc     r12
0x18000cb92  cmp     [rax+r12*2], cx
0x18000cb97  jnz     short loc_18000CB8F
0x18000cb99  lea     rdx, [rbp+3Fh+length]; unsigned int *
0x18000cb9d  mov     rcx, r12; unsigned __int64
0x18000cba0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18000cba5  xor     r12d, r12d
0x18000cba8  test    eax, eax
0x18000cbaa  jns     short loc_18000CBC2
0x18000cbac  xor     r9d, r9d; lpArguments
0x18000cbaf  lea     edx, [r12+1]; dwExceptionFlags
0x18000cbb4  xor     r8d, r8d; nNumberOfArguments
0x18000cbb7  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000cbbc  call    cs:__imp_RaiseException
0x18000cbc2  mov     edx, [rbp+3Fh+length]; length
0x18000cbc5  lea     r9, [rbp+3Fh+var_60]; string
0x18000cbc9  mov     rcx, [rbp+3Fh+sourceString]; sourceString
0x18000cbcd  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18000cbd1  call    cs:__imp_WindowsCreateStringReference
0x18000cbd7  mov     eax, [rbp+3Fh+var_90]
0x18000cbda  mov     rcx, r13
0x18000cbdd  mov     r9, [rbp+3Fh+var_68]
0x18000cbe1  mov     r8d, [rbp+3Fh+var_80]
0x18000cbe5  mov     rdx, [rbp+3Fh+var_60]
0x18000cbe9  mov     [rsp+0E0h+var_B8], r15
0x18000cbee  mov     [rsp+0E0h+var_C0], eax; int
0x18000cbf2  mov     rax, [rbp+3Fh+var_88]
0x18000cbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbfb  mov     r15d, eax
0x18000cbfe  test    eax, eax
0x18000cc00  jns     short loc_18000CC61
0x18000cc02  mov     rcx, [rbp+47h]; this
0x18000cc06  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000cc0d  mov     r9d, eax; char *
0x18000cc10  mov     edx, 1F4h; void *
0x18000cc15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc1a  test    r14, r14
0x18000cc1d  jz      short loc_18000CC27
0x18000cc1f  mov     rcx, r14; Block
0x18000cc22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc27  test    rsi, rsi
0x18000cc2a  jz      short loc_18000CC34
0x18000cc2c  mov     rcx, rsi; Block
0x18000cc2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc34  mov     rcx, [rbp+3Fh+string]; string
  ... truncated ...
```
