# CProcessStateManager::get_LangID(ushort *)

- ea: `0x180040310`
- end: `0x18004054f`
- name: `?get_LangID@CProcessStateManager@@UEAAJPEAG@Z`
- size: `575`
- prototype: `__int64 __fastcall(CProcessStateManager *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004c00`
- `0x1800171a0`
- `0x18002bc20`
- `0x18002eb4c`
- `0x1800328e0`
- `0x18003bec0`
- `0x180040310`
- `0x180040558`
- `0x18005d488`
- `0x180064208`
- `0x18006c000`
- `0x18006cad0`

## import_xrefs

- `KERNEL32!GetSystemPreferredUILanguages` at `0x180040364`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x1800403ff`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x180040364`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x1800403ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800404b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800404e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800404b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800404e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800403b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800403b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040545`
- `Bcp47Langs!LcidFromBcp47` at `0x18004048f`
- `Bcp47Langs!LcidFromBcp47` at `0x18004048f`
- `Bcp47Langs!Bcp47Normalize` at `0x180040470`
- `Bcp47Langs!Bcp47Normalize` at `0x180040470`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProcessStateManager::get_LangID(CProcessStateManager *this, unsigned __int16 *a2)
{
  unsigned __int16 SessionLangID; // ax
  int Error; // eax
  unsigned int v5; // ebx
  _WORD *v7; // rbx
  _WORD *v8; // rax
  size_t v9; // rax
  unsigned int v10; // edi
  BOOL SystemPreferredUILanguages; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  HSTRING string; // [rsp+20h] [rbp-60h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+28h] [rbp-58h] BYREF
  ULONG pulNumLanguages; // [rsp+2Ch] [rbp-54h] BYREF
  int v19; // [rsp+30h] [rbp-50h] BYREF
  void *v20; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  SessionLangID = CProcessStateManager::GetSessionLangID(this);
  *a2 = SessionLangID;
  if ( SessionLangID )
    return 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
  {
    Error = ResultFromKnownLastError();
    v5 = Error;
    if ( Error < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
        (const char *)(unsigned int)Error,
        (int)string);
      return v5;
    }
  }
  v7 = 0;
  v20 = 0;
  if ( !is_mul_ok(pcchLanguagesBuffer, 2u) )
  {
    v10 = -2147024362;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
      (const char *)v10,
      (int)string);
    CoTaskMemFree(v7);
    return v10;
  }
  v8 = CoTaskMemAlloc(2LL * pcchLanguagesBuffer);
  v7 = v8;
  v20 = v8;
  if ( v8 )
  {
    v9 = CTCoAllocPolicy::_CoTaskMemSize(v8);
    memset_0(v7, 0, v9);
    v10 = 0;
  }
  else
  {
    v10 = -2147024882;
  }
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_21;
  SystemPreferredUILanguages = GetSystemPreferredUILanguages(8u, &pulNumLanguages, v7, &pcchLanguagesBuffer);
  v12 = ResultFromWin32Bool(SystemPreferredUILanguages);
  v10 = v12;
  if ( v12 >= 0 )
  {
    memset(v21, 0, sizeof(v21));
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
      (__int64)v21,
      v7,
      0xFFFFFFFFFFFFFFFFuLL);
    WindowsDeleteString(0);
    string = 0;
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader);
    v14 = Bcp47Normalize(*(_QWORD *)(v13 + 24), &string);
    v10 = v14;
    if ( v14 < 0 )
    {
      v15 = 320;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
        (const char *)(unsigned int)v14,
        (int)string);
      WindowsDeleteString(string);
      string = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v21);
      goto LABEL_17;
    }
    v19 = 0;
    v14 = LcidFromBcp47(string, &v19);
    v10 = v14;
    if ( v14 < 0 )
    {
      v15 = 323;
      goto LABEL_16;
    }
    *a2 = v19;
    WindowsDeleteString(string);
    string = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v21);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v20);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x139,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
    (const char *)(unsigned int)v12,
    (int)string);
LABEL_17:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v20);
  return v10;
}

```

## disassembly

```asm
0x180040310  mov     [rsp-18h+arg_0], rbx
0x180040315  mov     [rsp-18h+arg_10], rsi
0x18004031a  push    rbp
0x18004031b  push    rdi
0x18004031c  push    r14
0x18004031e  mov     rbp, rsp
0x180040321  sub     rsp, 80h
0x180040328  mov     rax, cs:__security_cookie
0x18004032f  xor     rax, rsp
0x180040332  mov     [rbp+var_8], rax
0x180040336  mov     rsi, rdx
0x180040339  call    ?GetSessionLangID@CProcessStateManager@@QEAAGXZ; CProcessStateManager::GetSessionLangID(void)
0x18004033e  mov     [rsi], ax
0x180040341  xor     r14d, r14d
0x180040344  test    ax, ax
0x180040347  jnz     loc_1800404FE
0x18004034d  mov     [rbp+pulNumLanguages], r14d
0x180040351  mov     [rbp+pcchLanguagesBuffer], r14d
0x180040355  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180040359  xor     r8d, r8d; pwszLanguagesBuffer
0x18004035c  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x180040360  lea     ecx, [r14+8]; dwFlags
0x180040364  call    cs:__imp_GetSystemPreferredUILanguages
0x18004036a  test    eax, eax
0x18004036c  jnz     short loc_180040398
0x18004036e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180040373  mov     ebx, eax
0x180040375  test    eax, eax
0x180040377  jns     short loc_180040398
0x180040379  mov     rcx, [rbp+18h]; this
0x18004037d  mov     r9d, eax; char *
0x180040380  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x180040387  mov     edx, 135h; void *
0x18004038c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040391  mov     eax, ebx
0x180040393  jmp     loc_180040500
0x180040398  mov     rbx, r14
0x18004039b  mov     [rbp+var_48], r14
0x18004039f  mov     ecx, [rbp+pcchLanguagesBuffer]
0x1800403a2  mov     eax, 2
0x1800403a7  mul     rcx
0x1800403aa  test    rdx, rdx
0x1800403ad  jnz     loc_180040524
0x1800403b3  mov     rcx, rax; cb
0x1800403b6  call    cs:__imp_CoTaskMemAlloc
0x1800403bc  mov     rbx, rax
0x1800403bf  mov     [rbp+var_48], rax
0x1800403c3  test    rax, rax
0x1800403c6  jz      short loc_1800403E2
0x1800403c8  mov     rcx, rax; void *
0x1800403cb  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x1800403d0  mov     r8, rax; Size
0x1800403d3  xor     edx, edx; Val
0x1800403d5  mov     rcx, rbx; void *
0x1800403d8  call    memset_0
0x1800403dd  mov     edi, r14d
0x1800403e0  jmp     short loc_1800403E7
0x1800403e2  mov     edi, 8007000Eh
0x1800403e7  test    edi, edi
0x1800403e9  js      loc_180040529
0x1800403ef  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800403f3  mov     r8, rbx; pwszLanguagesBuffer
0x1800403f6  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x1800403fa  mov     ecx, 8; dwFlags
0x1800403ff  call    cs:__imp_GetSystemPreferredUILanguages
0x180040405  mov     ecx, eax; int
0x180040407  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18004040c  mov     edi, eax
0x18004040e  test    eax, eax
0x180040410  jns     short loc_18004042F
0x180040412  mov     rcx, [rbp+18h]; this
0x180040416  mov     r9d, eax; char *
0x180040419  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x180040420  mov     edx, 139h; void *
0x180040425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004042a  jmp     loc_1800404CB
0x18004042f  mov     [rbp+var_40], r14
0x180040433  mov     [rbp+var_38], r14
0x180040437  mov     [rbp+var_30], r14
0x18004043b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004043f  mov     rdx, rbx
0x180040442  lea     rcx, [rbp+var_40]
0x180040446  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004044b  mov     [rbp+string], r14
0x18004044f  xor     ecx, ecx; string
0x180040451  call    cs:__imp_WindowsDeleteString
0x180040457  mov     [rbp+string], r14
0x18004045b  lea     rdx, [rbp+var_40]
0x18004045f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180040463  call    ??$?0V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x180040468  lea     rdx, [rbp+string]
0x18004046c  mov     rcx, [rax+18h]
0x180040470  call    cs:__imp_Bcp47Normalize
0x180040476  mov     edi, eax
0x180040478  test    eax, eax
0x18004047a  jns     short loc_180040483
0x18004047c  mov     edx, 140h
0x180040481  jmp     short loc_1800404A0
0x180040483  mov     [rbp+var_50], r14d
0x180040487  lea     rdx, [rbp+var_50]
0x18004048b  mov     rcx, [rbp+string]
0x18004048f  call    cs:__imp_LcidFromBcp47
0x180040495  mov     edi, eax
0x180040497  test    eax, eax
0x180040499  jns     short loc_1800404D6
0x18004049b  mov     edx, 143h; void *
0x1800404a0  mov     r9d, eax; char *
0x1800404a3  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800404aa  mov     rcx, [rbp+18h]; this
0x1800404ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800404b3  mov     rcx, [rbp+string]; string
0x1800404b7  call    cs:__imp_WindowsDeleteString
0x1800404bd  mov     [rbp+string], r14
0x1800404c1  lea     rcx, [rbp+var_40]
0x1800404c5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800404ca  nop
0x1800404cb  lea     rcx, [rbp+var_48]
0x1800404cf  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800404d4  jmp     short loc_18004054B
0x1800404d6  movzx   eax, word ptr [rbp+var_50]
0x1800404da  mov     [rsi], ax
0x1800404dd  mov     rcx, [rbp+string]; string
0x1800404e1  call    cs:__imp_WindowsDeleteString
0x1800404e7  mov     [rbp+string], r14
0x1800404eb  lea     rcx, [rbp+var_40]
0x1800404ef  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800404f4  nop
0x1800404f5  lea     rcx, [rbp+var_48]
0x1800404f9  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800404fe  xor     eax, eax
0x180040500  mov     rcx, [rbp+var_8]
0x180040504  xor     rcx, rsp; StackCookie
0x180040507  call    __security_check_cookie
0x18004050c  lea     r11, [rsp+80h+var_s0]
0x180040514  mov     rbx, [r11+20h]
0x180040518  mov     rsi, [r11+30h]
0x18004051c  mov     rsp, r11
0x18004051f  pop     r14
0x180040521  pop     rdi
0x180040522  pop     rbp
0x180040523  retn
0x180040524  mov     edi, 80070216h
0x180040529  mov     rcx, [rbp+18h]; this
0x18004052d  mov     r9d, edi; char *
0x180040530  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x180040537  mov     edx, 137h; void *
0x18004053c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040541  nop
0x180040542  mov     rcx, rbx; pv
0x180040545  call    cs:__imp_CoTaskMemFree
0x18004054b  mov     eax, edi
0x18004054d  jmp     short loc_180040500
```
