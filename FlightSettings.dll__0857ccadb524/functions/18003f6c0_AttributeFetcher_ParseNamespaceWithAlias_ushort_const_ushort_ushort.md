# AttributeFetcher::ParseNamespaceWithAlias(ushort const *,ushort * *,ushort * *)

- ea: `0x18003f6c0`
- end: `0x18003f9ae`
- name: `?ParseNamespaceWithAlias@AttributeFetcher@@AEAAJPEBGPEAPEAG1@Z`
- size: `750`
- prototype: `__int64 __fastcall(AttributeFetcher *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e3f4`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800107b0`
- `0x18001c6f4`
- `0x18001ce88`
- `0x18001ec48`
- `0x18001ec78`
- `0x18003f670`
- `0x18003f6c0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18003f807`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18003f807`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f879`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f879`

## string_xrefs

- `0x18003f7d9`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003f8b7`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003f90c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003f97c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AttributeFetcher::ParseNamespaceWithAlias(
        AttributeFetcher *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  __int64 v8; // rdx
  unsigned __int64 v9; // rax
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  LPWSTR *p_lpsz; // rcx
  LPWSTR v16; // rbx
  __int64 v17; // rsi
  int (__fastcall *v18)(__int64, _QWORD, HSTRING *); // rdi
  __int64 v19; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v21; // rax
  int v22; // eax
  int v23; // eax
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rax
  unsigned __int16 v27[4]; // [rsp+20h] [rbp-49h] BYREF
  HSTRING string; // [rsp+28h] [rbp-41h] BYREF
  LPWSTR v29; // [rsp+30h] [rbp-39h] BYREF
  LPWSTR lpsz; // [rsp+38h] [rbp-31h] BYREF
  DWORD cchLength[2]; // [rsp+40h] [rbp-29h]
  __int64 v32; // [rsp+48h] [rbp-21h]
  unsigned __int16 *v33; // [rsp+58h] [rbp-11h] BYREF
  __int64 v34; // [rsp+60h] [rbp-9h]
  __int64 v35; // [rsp+68h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_QWORD *)v27 = a2;
  if ( !a2 || !*a2 )
  {
    v8 = 953;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    v8 = 954;
LABEL_28:
    v14 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)0x80070057LL,
      *(int *)v27);
    return v14;
  }
  if ( !a4 )
  {
    v8 = 955;
    goto LABEL_28;
  }
  *a3 = 0;
  *a4 = 0;
  string = 0;
  if ( !*a2 )
    goto LABEL_13;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( v9 >= 2 && a2[1] == 58 )
  {
    Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v27);
  }
  else
  {
LABEL_13:
    v10 = *(_QWORD *)(*((_QWORD *)this + 2) + 120LL);
    v11 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v10 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&lpsz, v27);
    if ( v11(v10, *(_QWORD *)(v12 + 24), &string) < 0 )
    {
      lpsz = 0;
      *(_QWORD *)cchLength = 0;
      v32 = 0;
      v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &lpsz,
              a2,
              -1);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D2,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v13,
          *(int *)v27);
        p_lpsz = &lpsz;
        goto LABEL_22;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      v16 = lpsz;
      CharLowerBuffW(lpsz, cchLength[0]);
      v17 = *(_QWORD *)(*((_QWORD *)this + 2) + 120LL);
      v18 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v17 + 80LL);
      WindowsDeleteString(string);
      string = 0;
      v29 = v16;
      v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v33, &v29);
      if ( v18(v17, *(_QWORD *)(v19 + 24), &string) < 0 )
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v27);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
    }
  }
  v27[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v21 = AttributeFetcher::ParseNamespace(StringRawBuffer, v27);
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&v33, v21, -1);
  v14 = v22;
  if ( v22 >= 0 )
  {
    v27[1] = 0;
    lpsz = 0;
    *(_QWORD *)cchLength = 0;
    v32 = 0;
    v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &lpsz,
            v27,
            -1);
    v14 = v23;
    if ( v23 >= 0 )
    {
      v24 = v33;
      v33 = 0;
      v35 = 0;
      v34 = 0;
      *a3 = v24;
      v25 = lpsz;
      lpsz = 0;
      v32 = 0;
      *(_QWORD *)cchLength = 0;
      *a4 = v25;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
      v14 = 0;
      goto LABEL_26;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)(unsigned int)v23,
      *(int *)v27);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
      (const char *)(unsigned int)v22,
      *(int *)v27);
  }
  p_lpsz = &v33;
LABEL_22:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(p_lpsz);
LABEL_26:
  WindowsDeleteString(string);
  return v14;
}

```

## disassembly

```asm
0x18003f6c0  push    rbp
0x18003f6c2  push    rbx
0x18003f6c3  push    rsi
0x18003f6c4  push    rdi
0x18003f6c5  push    r12
0x18003f6c7  push    r13
0x18003f6c9  push    r14
0x18003f6cb  push    r15
0x18003f6cd  lea     rbp, [rsp-1Fh]
0x18003f6d2  sub     rsp, 88h
0x18003f6d9  mov     rax, cs:__security_cookie
0x18003f6e0  xor     rax, rsp
0x18003f6e3  mov     [rbp+57h+var_48], rax
0x18003f6e7  mov     r15, r9
0x18003f6ea  mov     r14, r8
0x18003f6ed  mov     rsi, rdx
0x18003f6f0  mov     r13, rcx
0x18003f6f3  mov     qword ptr [rbp+57h+var_A0], rdx
0x18003f6f7  xor     r12d, r12d
0x18003f6fa  test    rdx, rdx
0x18003f6fd  jz      loc_18003F96F
0x18003f703  cmp     [rdx], r12w
0x18003f707  jz      loc_18003F96F
0x18003f70d  test    r8, r8
0x18003f710  jnz     short loc_18003F71C
0x18003f712  mov     edx, 3BAh
0x18003f717  jmp     loc_18003F974
0x18003f71c  test    r15, r15
0x18003f71f  jnz     short loc_18003F72B
0x18003f721  mov     edx, 3BBh
0x18003f726  jmp     loc_18003F974
0x18003f72b  mov     [r8], r12
0x18003f72e  mov     [r9], r12
0x18003f731  mov     [rbp+57h+string], r12
0x18003f735  cmp     [rdx], r12w
0x18003f739  jz      short loc_18003F768
0x18003f73b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f73f  inc     rax
0x18003f742  cmp     [rdx+rax*2], r12w
0x18003f747  jnz     short loc_18003F73F
0x18003f749  cmp     rax, 2
0x18003f74d  jb      short loc_18003F768
0x18003f74f  cmp     word ptr [rdx+2], 3Ah ; ':'
0x18003f754  jnz     short loc_18003F768
0x18003f756  lea     rdx, [rbp+57h+var_A0]
0x18003f75a  lea     rcx, [rbp+57h+string]
0x18003f75e  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f763  jmp     loc_18003F86E
0x18003f768  mov     rax, [rcx+10h]
0x18003f76c  mov     rdi, [rax+78h]
0x18003f770  mov     rax, [rdi]
0x18003f773  mov     rbx, [rax+50h]
0x18003f777  xor     ecx, ecx; string
0x18003f779  call    cs:__imp_WindowsDeleteString
0x18003f77f  mov     [rbp+57h+string], r12
0x18003f783  lea     rdx, [rbp+57h+var_A0]
0x18003f787  lea     rcx, [rbp+57h+lpsz]
0x18003f78b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f790  nop
0x18003f791  lea     r8, [rbp+57h+string]
0x18003f795  mov     rdx, [rax+18h]
0x18003f799  mov     rcx, rdi
0x18003f79c  mov     rax, rbx
0x18003f79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7a4  nop
0x18003f7a5  shr     eax, 1Fh
0x18003f7a8  test    al, al
0x18003f7aa  jz      loc_18003F86E
0x18003f7b0  mov     [rbp+57h+lpsz], r12
0x18003f7b4  mov     qword ptr [rbp+57h+cchLength], r12
0x18003f7b8  mov     [rbp+57h+var_78], r12
0x18003f7bc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f7c0  mov     rdx, rsi
0x18003f7c3  lea     rcx, [rbp+57h+lpsz]
0x18003f7c7  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003f7cc  mov     ebx, eax
0x18003f7ce  test    eax, eax
0x18003f7d0  jns     short loc_18003F7F4
0x18003f7d2  mov     rcx, [rbp+5Fh]; this
0x18003f7d6  mov     r9d, eax; char *
0x18003f7d9  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003f7e0  mov     edx, 3D2h; void *
0x18003f7e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f7ea  nop
0x18003f7eb  lea     rcx, [rbp+57h+lpsz]
0x18003f7ef  jmp     loc_18003F8CC
0x18003f7f4  lea     rcx, [rbp+57h+lpsz]
0x18003f7f8  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003f7fd  mov     edx, [rbp+57h+cchLength]; cchLength
0x18003f800  mov     rbx, [rbp+57h+lpsz]
0x18003f804  mov     rcx, rbx; lpsz
0x18003f807  call    cs:__imp_CharLowerBuffW
0x18003f80d  mov     rax, [r13+10h]
0x18003f811  mov     rsi, [rax+78h]
0x18003f815  mov     rax, [rsi]
0x18003f818  mov     rdi, [rax+50h]
0x18003f81c  mov     rcx, [rbp+57h+string]; string
0x18003f820  call    cs:__imp_WindowsDeleteString
0x18003f826  mov     [rbp+57h+string], r12
0x18003f82a  mov     [rbp+57h+var_90], rbx
0x18003f82e  lea     rdx, [rbp+57h+var_90]
0x18003f832  lea     rcx, [rbp+57h+var_68]
0x18003f836  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f83b  nop
0x18003f83c  lea     r8, [rbp+57h+string]
0x18003f840  mov     rdx, [rax+18h]
0x18003f844  mov     rcx, rsi
0x18003f847  mov     rax, rdi
0x18003f84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f84f  nop
0x18003f850  shr     eax, 1Fh
0x18003f853  test    al, al
0x18003f855  jz      short loc_18003F865
0x18003f857  lea     rdx, [rbp+57h+var_A0]
0x18003f85b  lea     rcx, [rbp+57h+string]
0x18003f85f  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f864  nop
0x18003f865  lea     rcx, [rbp+57h+lpsz]
0x18003f869  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003f86e  mov     [rbp+57h+var_A0], r12w
0x18003f873  xor     edx, edx; length
0x18003f875  mov     rcx, [rbp+57h+string]; string
0x18003f879  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f87f  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18003f883  mov     rcx, rax; unsigned __int16 *
0x18003f886  call    ?ParseNamespace@AttributeFetcher@@CAPEBGPEBGPEAG@Z; AttributeFetcher::ParseNamespace(ushort const *,ushort *)
0x18003f88b  mov     [rbp+57h+var_68], r12
0x18003f88f  mov     [rbp+57h+var_60], r12
0x18003f893  mov     [rbp+57h+var_58], r12
0x18003f897  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003f89b  mov     r8, rdi
0x18003f89e  mov     rdx, rax
0x18003f8a1  lea     rcx, [rbp+57h+var_68]
0x18003f8a5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003f8aa  mov     ebx, eax
0x18003f8ac  test    eax, eax
0x18003f8ae  jns     short loc_18003F8D6
0x18003f8b0  mov     rcx, [rbp+5Fh]; this
0x18003f8b4  mov     r9d, eax; char *
0x18003f8b7  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003f8be  mov     edx, 3E1h; void *
0x18003f8c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f8c8  lea     rcx, [rbp+57h+var_68]
0x18003f8cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003f8d1  jmp     loc_18003F963
0x18003f8d6  movzx   eax, [rbp+57h+var_A0]
0x18003f8da  mov     [rbp+57h+var_A0], ax
0x18003f8de  mov     [rbp+57h+var_A0+2], r12w
0x18003f8e3  mov     [rbp+57h+lpsz], r12
0x18003f8e7  mov     qword ptr [rbp+57h+cchLength], r12
0x18003f8eb  mov     [rbp+57h+var_78], r12
0x18003f8ef  mov     r8, rdi
0x18003f8f2  lea     rdx, [rbp+57h+var_A0]
0x18003f8f6  lea     rcx, [rbp+57h+lpsz]
0x18003f8fa  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003f8ff  mov     ebx, eax
0x18003f901  test    eax, eax
0x18003f903  jns     short loc_18003F928
0x18003f905  mov     rcx, [rbp+5Fh]; this
0x18003f909  mov     r9d, eax; char *
0x18003f90c  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003f913  mov     edx, 3E5h; void *
0x18003f918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f91d  lea     rcx, [rbp+57h+lpsz]
0x18003f921  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003f926  jmp     short loc_18003F8C8
0x18003f928  mov     rax, [rbp+57h+var_68]
0x18003f92c  mov     [rbp+57h+var_68], r12
0x18003f930  mov     [rbp+57h+var_58], r12
0x18003f934  mov     [rbp+57h+var_60], r12
0x18003f938  mov     [r14], rax
0x18003f93b  mov     rax, [rbp+57h+lpsz]
0x18003f93f  mov     [rbp+57h+lpsz], r12
0x18003f943  mov     [rbp+57h+var_78], r12
0x18003f947  mov     qword ptr [rbp+57h+cchLength], r12
0x18003f94b  mov     [r15], rax
0x18003f94e  lea     rcx, [rbp+57h+lpsz]
0x18003f952  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003f957  lea     rcx, [rbp+57h+var_68]
0x18003f95b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003f960  mov     ebx, r12d
0x18003f963  mov     rcx, [rbp+57h+string]; string
0x18003f967  call    cs:__imp_WindowsDeleteString
0x18003f96d  jmp     short loc_18003F98C
0x18003f96f  mov     edx, 3B9h; void *
0x18003f974  mov     ebx, 80070057h
0x18003f979  mov     r9d, ebx; char *
0x18003f97c  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003f983  mov     rcx, [rbp+5Fh]; this
0x18003f987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f98c  mov     eax, ebx
0x18003f98e  mov     rcx, [rbp+57h+var_48]
0x18003f992  xor     rcx, rsp; StackCookie
0x18003f995  call    __security_check_cookie
0x18003f99a  add     rsp, 88h
0x18003f9a1  pop     r15
0x18003f9a3  pop     r14
0x18003f9a5  pop     r13
0x18003f9a7  pop     r12
0x18003f9a9  pop     rdi
0x18003f9aa  pop     rsi
0x18003f9ab  pop     rbx
0x18003f9ac  pop     rbp
0x18003f9ad  retn
```
