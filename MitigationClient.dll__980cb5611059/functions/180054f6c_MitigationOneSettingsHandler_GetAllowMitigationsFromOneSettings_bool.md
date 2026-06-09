# MitigationOneSettingsHandler::GetAllowMitigationsFromOneSettings(bool &)

- ea: `0x180054f6c`
- end: `0x18005512b`
- name: `?GetAllowMitigationsFromOneSettings@MitigationOneSettingsHandler@@QEAAJAEA_N@Z`
- size: `447`
- prototype: `__int64 __fastcall(MitigationOneSettingsHandler *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180040c34`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x18001b6a0`
- `0x18002407c`
- `0x1800240b8`
- `0x1800253bc`
- `0x180054f6c`
- `0x1800552a0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800550e5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800550e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005505f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005505f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MitigationOneSettingsHandler::GetAllowMitigationsFromOneSettings(
        MitigationOneSettingsHandler *this,
        bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, HSTRING *); // rbx
  int v9; // eax
  unsigned int v10; // edi
  PCWSTR StringRawBuffer; // rax
  int v12; // eax
  __int64 v13; // rdx
  const WCHAR *Reserved1; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-40h]
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER lpString1; // [rsp+38h] [rbp-28h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( *((_BYTE *)this + 32) || (v4 = MitigationOneSettingsHandler::Initialize(this), v5 = v4, v4 >= 0) )
  {
    if ( !*((_BYTE *)this + 33) )
      return 2147943568LL;
    string = 0;
    v7 = *((_QWORD *)this + 2);
    v8 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v7 + 80LL);
    string = 0;
    v18 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&lpString1, L"ALLOWMITIGATIONS", 0x11u, 0x10u);
    v9 = v8(v7, v18, &string);
    v10 = v9;
    if ( v9 >= 0 )
    {
      memset(&lpString1, 0, sizeof(lpString1));
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &lpString1,
              StringRawBuffer,
              -1);
      v5 = v12;
      if ( v12 >= 0 )
      {
        LODWORD(v13) = *(_DWORD *)&lpString1.Reserved.Reserved2[8];
        if ( *(_QWORD *)&lpString1.Reserved.Reserved2[8] == -1 )
        {
          if ( lpString1.Reserved.Reserved1 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *((_WORD *)lpString1.Reserved.Reserved1 + v13) );
          }
          else
          {
            LODWORD(v13) = 0;
          }
        }
        Reserved1 = &String1;
        if ( lpString1.Reserved.Reserved1 )
          Reserved1 = (const WCHAR *)lpString1.Reserved.Reserved1;
        *a2 = CompareStringOrdinal(Reserved1, v13, L"true", -1, 1) == 2;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpString1);
        v5 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationonesettingshandler\\mitigationones"
                        "ettingshandler.cpp",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&lpString1);
      }
    }
    else
    {
      v5 = -2089484279;
      if ( v9 != -2089484279 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x114,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationonesettingshandler\\mitigationones"
                        "ettingshandler.cpp",
          (const char *)(unsigned int)v9,
          bIgnoreCase);
        v5 = v10;
      }
    }
    Windows::Internal::String::~String(&string);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationonesettingshandler\\mitigationonesettingshandler.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
  }
  return v5;
}

```

## disassembly

```asm
0x180054f6c  mov     [rsp-18h+arg_10], rbx
0x180054f71  mov     [rsp-18h+arg_18], rsi
0x180054f76  push    rbp
0x180054f77  push    rdi
0x180054f78  push    r14
0x180054f7a  mov     rbp, rsp
0x180054f7d  sub     rsp, 60h
0x180054f81  mov     rax, cs:__security_cookie
0x180054f88  xor     rax, rsp
0x180054f8b  mov     [rbp+var_8], rax
0x180054f8f  mov     rsi, rdx
0x180054f92  mov     rdi, rcx
0x180054f95  xor     r14d, r14d
0x180054f98  cmp     [rcx+20h], r14b
0x180054f9c  jnz     short loc_180054FC6
0x180054f9e  call    ?Initialize@MitigationOneSettingsHandler@@AEAAJXZ; MitigationOneSettingsHandler::Initialize(void)
0x180054fa3  mov     ebx, eax
0x180054fa5  test    eax, eax
0x180054fa7  jns     short loc_180054FC6
0x180054fa9  mov     rcx, [rbp+18h]; this
0x180054fad  mov     r9d, eax; char *
0x180054fb0  lea     r8, aOnecoreBaseDia_44; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180054fb7  mov     edx, 10Bh; void *
0x180054fbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054fc1  jmp     loc_180055108
0x180054fc6  cmp     [rdi+21h], r14b
0x180054fca  jnz     short loc_180054FD6
0x180054fcc  mov     eax, 80070490h
0x180054fd1  jmp     loc_18005510A
0x180054fd6  mov     [rbp+string], r14
0x180054fda  mov     rdi, [rdi+10h]
0x180054fde  mov     rax, [rdi]
0x180054fe1  mov     rbx, [rax+50h]
0x180054fe5  mov     [rbp+string], r14
0x180054fe9  mov     [rbp+var_10], r14
0x180054fed  mov     r9d, 10h; unsigned int
0x180054ff3  lea     r8d, [r9+1]; unsigned int
0x180054ff7  lea     rdx, aAllowmitigatio; "ALLOWMITIGATIONS"
0x180054ffe  lea     rcx, [rbp+lpString1]; hstringHeader
0x180055002  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180055007  nop
0x180055008  lea     r8, [rbp+string]
0x18005500c  mov     rdx, [rbp+var_10]
0x180055010  mov     rcx, rdi
0x180055013  mov     rax, rbx
0x180055016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005501b  mov     edi, eax
0x18005501d  test    eax, eax
0x18005501f  jns     short loc_18005504D
0x180055021  mov     ebx, 83750009h
0x180055026  cmp     eax, ebx
0x180055028  jz      loc_1800550FF
0x18005502e  mov     rcx, [rbp+18h]; this
0x180055032  mov     r9d, eax; char *
0x180055035  lea     r8, aOnecoreBaseDia_44; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18005503c  mov     edx, 114h; void *
0x180055041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055046  mov     ebx, edi
0x180055048  jmp     loc_1800550FF
0x18005504d  mov     [rbp+lpString1], r14
0x180055051  mov     [rbp+var_20], r14
0x180055055  mov     [rbp+var_18], r14
0x180055059  xor     edx, edx; length
0x18005505b  mov     rcx, [rbp+string]; string
0x18005505f  call    cs:__imp_WindowsGetStringRawBuffer
0x180055065  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180055069  mov     r8, rdi
0x18005506c  mov     rdx, rax
0x18005506f  lea     rcx, [rbp+lpString1]
0x180055073  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180055078  mov     ebx, eax
0x18005507a  test    eax, eax
0x18005507c  jns     short loc_1800550A1
0x18005507e  mov     rcx, [rbp+18h]; this
0x180055082  mov     r9d, eax; char *
0x180055085  lea     r8, aOnecoreBaseDia_44; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18005508c  mov     edx, 117h; void *
0x180055091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055096  lea     rcx, [rbp+lpString1]
0x18005509a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005509f  jmp     short loc_1800550FF
0x1800550a1  mov     rdx, [rbp+var_20]
0x1800550a5  mov     rax, [rbp+lpString1]
0x1800550a9  cmp     rdx, rdi
0x1800550ac  jnz     short loc_1800550C5
0x1800550ae  test    rax, rax
0x1800550b1  jz      short loc_1800550C2
0x1800550b3  mov     rdx, rdi
0x1800550b6  inc     rdx
0x1800550b9  cmp     [rax+rdx*2], r14w
0x1800550be  jnz     short loc_1800550B6
0x1800550c0  jmp     short loc_1800550C5
0x1800550c2  mov     rdx, r14; cchCount1
0x1800550c5  lea     rcx, String1
0x1800550cc  test    rax, rax
0x1800550cf  cmovnz  rcx, rax; lpString1
0x1800550d3  mov     [rsp+60h+bIgnoreCase], 1; bIgnoreCase
0x1800550db  mov     r9d, edi; cchCount2
0x1800550de  lea     r8, aTrue; "true"
0x1800550e5  call    cs:__imp_CompareStringOrdinal
0x1800550eb  cmp     eax, 2
0x1800550ee  setz    al
0x1800550f1  mov     [rsi], al
0x1800550f3  lea     rcx, [rbp+lpString1]
0x1800550f7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800550fc  mov     ebx, r14d
0x1800550ff  lea     rcx, [rbp+string]; this
0x180055103  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180055108  mov     eax, ebx
0x18005510a  mov     rcx, [rbp+var_8]
0x18005510e  xor     rcx, rsp; StackCookie
0x180055111  call    __security_check_cookie
0x180055116  lea     r11, [rsp+60h+var_s0]
0x18005511b  mov     rbx, [r11+30h]
0x18005511f  mov     rsi, [r11+38h]
0x180055123  mov     rsp, r11
0x180055126  pop     r14
0x180055128  pop     rdi
0x180055129  pop     rbp
0x18005512a  retn
```
