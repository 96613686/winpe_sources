# CSelectedInputMethodsData::RemoveInput(ushort const *)

- ea: `0x180242a18`
- end: `0x180242b8f`
- name: `?RemoveInput@CSelectedInputMethodsData@@QEAAJPEBG@Z`
- size: `375`
- prototype: `int(CSelectedInputMethodsData *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800fb914`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18004ff08`
- `0x18005958c`
- `0x1800f3eb8`
- `0x180242a18`
- `0x1802430e4`
- `0x1802437b0`
- `0x180256ba8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180242a56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180242a56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180242ac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180242afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180242b36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180242ac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180242afe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180242b36`
- `Bcp47Langs!RemoveUserLanguageInputMethods` at `0x180242b4d`
- `Bcp47Langs!RemoveUserLanguageInputMethods` at `0x180242b4d`
- `Input!__imp_InstallLayoutOrTip` at `0x180242b12`
- `Input!__imp_InstallLayoutOrTip` at `0x180242b12`

## string_xrefs

- `0x180242af0`: `shellcommondesktopbase\languagedatalib\selectedinputmethodsdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSelectedInputMethodsData::RemoveInput(CSelectedInputMethodsData *this, const unsigned __int16 *a2)
{
  char *v5; // rsi
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned __int16 *StringRawBuffer; // rax
  __int64 v11; // r9
  PCWSTR v12; // rax
  PCWSTR v13; // rax
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v15[4]; // [rsp+28h] [rbp-50h] BYREF
  _QWORD v16[4]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !*(_BYTE *)this )
    return 2147500033LL;
  WindowsDeleteString(0);
  string = 0;
  v5 = (char *)this + 2;
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v15,
    (const unsigned __int16 *)this + 1);
  v6 = v15[0];
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v16, a2);
  v7 = TransformInputMethodsForLanguage(v16[0], v6, &string);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KSOD>::GetImpl'::`2'::impl) )
    {
      StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
      v7 = EnableInputMethods(StringRawBuffer, 1u);
      v8 = v7;
      if ( v7 < 0 )
      {
        v9 = 123;
        goto LABEL_8;
      }
    }
    else
    {
      v12 = WindowsGetStringRawBuffer(string, 0);
      if ( !(unsigned int)InstallLayoutOrTip(v12, 1) )
      {
        v8 = -2147467259;
        v11 = 2147500037LL;
        v9 = 127;
        goto LABEL_9;
      }
    }
    v13 = WindowsGetStringRawBuffer(string, 0);
    RemoveUserLanguageInputMethods(v5, 59, v13);
    CheckAndResetOverrideInputMethod(a2);
    v8 = 0;
    goto LABEL_13;
  }
  v9 = 119;
LABEL_8:
  v11 = (unsigned int)v7;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shellcommondesktopbase\\languagedatalib\\selectedinputmethodsdata.cpp",
    (const char *)v11,
    (int)string);
LABEL_13:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v8;
}

```

## disassembly

```asm
0x180242a18  mov     [rsp+arg_10], rbx
0x180242a1d  mov     [rsp+arg_18], rsi
0x180242a22  push    rdi
0x180242a23  sub     rsp, 70h
0x180242a27  mov     rax, cs:__security_cookie
0x180242a2e  xor     rax, rsp
0x180242a31  mov     [rsp+78h+var_10], rax
0x180242a36  mov     rdi, rdx
0x180242a39  mov     rbx, rcx
0x180242a3c  cmp     byte ptr [rcx], 0
0x180242a3f  jnz     short loc_180242A4B
0x180242a41  mov     eax, 80004001h
0x180242a46  jmp     loc_180242B6F
0x180242a4b  mov     [rsp+78h+string], 0
0x180242a54  xor     ecx, ecx; string
0x180242a56  call    cs:__imp_WindowsDeleteString
0x180242a5d  nop     dword ptr [rax+rax+00h]
0x180242a62  mov     [rsp+78h+string], 0; int
0x180242a6b  lea     rsi, [rbx+2]
0x180242a6f  mov     rdx, rsi; unsigned __int16 *
0x180242a72  lea     rcx, [rsp+78h+var_50]; this
0x180242a77  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180242a7c  mov     rbx, [rsp+78h+var_50]
0x180242a81  mov     rdx, rdi; unsigned __int16 *
0x180242a84  lea     rcx, [rsp+78h+var_30]; this
0x180242a89  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180242a8e  lea     r8, [rsp+78h+string]
0x180242a93  mov     rdx, rbx
0x180242a96  mov     rcx, [rsp+78h+var_30]
0x180242a9b  call    TransformInputMethodsForLanguage
0x180242aa0  mov     ebx, eax
0x180242aa2  test    eax, eax
0x180242aa4  jns     short loc_180242AAD
0x180242aa6  mov     edx, 77h ; 'w'
0x180242aab  jmp     short loc_180242AE8
0x180242aad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KSOD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KSOD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD> `wil::Feature<__WilFeatureTraits_Feature_KSOD>::GetImpl(void)'::`2'::impl
0x180242ab4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KSOD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD>::__private_IsEnabled(void)
0x180242ab9  xor     edx, edx; length
0x180242abb  mov     rcx, [rsp+78h+string]; string
0x180242ac0  test    al, al
0x180242ac2  jz      short loc_180242AFE
0x180242ac4  call    cs:__imp_WindowsGetStringRawBuffer
0x180242acb  nop     dword ptr [rax+rax+00h]
0x180242ad0  mov     edx, 1
0x180242ad5  mov     rcx, rax
0x180242ad8  call    EnableInputMethods
0x180242add  mov     ebx, eax
0x180242adf  test    eax, eax
0x180242ae1  jns     short loc_180242B2F
0x180242ae3  mov     edx, 7Bh ; '{'; void *
0x180242ae8  mov     r9d, eax; char *
0x180242aeb  mov     rcx, [rsp+78h]; this
0x180242af0  lea     r8, aShellcommondes_5; "shellcommondesktopbase\\languagedatalib"...
0x180242af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180242afc  jmp     short loc_180242B63
0x180242afe  call    cs:__imp_WindowsGetStringRawBuffer
0x180242b05  nop     dword ptr [rax+rax+00h]
0x180242b0a  mov     edx, 1
0x180242b0f  mov     rcx, rax
0x180242b12  call    cs:__imp_InstallLayoutOrTip
0x180242b19  nop     dword ptr [rax+rax+00h]
0x180242b1e  test    eax, eax
0x180242b20  jnz     short loc_180242B2F
0x180242b22  mov     ebx, 80004005h
0x180242b27  mov     r9d, ebx
0x180242b2a  lea     edx, [rax+7Fh]
0x180242b2d  jmp     short loc_180242AEB
0x180242b2f  xor     edx, edx; length
0x180242b31  mov     rcx, [rsp+78h+string]; string
0x180242b36  call    cs:__imp_WindowsGetStringRawBuffer
0x180242b3d  nop     dword ptr [rax+rax+00h]
0x180242b42  mov     edx, 3Bh ; ';'
0x180242b47  mov     r8, rax
0x180242b4a  mov     rcx, rsi
0x180242b4d  call    cs:__imp_RemoveUserLanguageInputMethods
0x180242b54  nop     dword ptr [rax+rax+00h]
0x180242b59  mov     rcx, rdi; lpString1
0x180242b5c  call    ?CheckAndResetOverrideInputMethod@@YAJPEBG@Z; CheckAndResetOverrideInputMethod(ushort const *)
0x180242b61  xor     ebx, ebx
0x180242b63  lea     rcx, [rsp+78h+string]; this
0x180242b68  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180242b6d  mov     eax, ebx
0x180242b6f  mov     rcx, [rsp+78h+var_10]
0x180242b74  xor     rcx, rsp; StackCookie
0x180242b77  call    __security_check_cookie
0x180242b7c  lea     r11, [rsp+78h+var_8]
0x180242b81  mov     rbx, [r11+20h]
0x180242b85  mov     rsi, [r11+28h]
0x180242b89  mov     rsp, r11
0x180242b8c  pop     rdi
0x180242b8d  retn
```
