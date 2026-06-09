# Cortana::ConstraintIndex::Search::GetUserSettingsDirectoryLanguage(void)

- ea: `0x1800940f8`
- end: `0x1800941f0`
- name: `?GetUserSettingsDirectoryLanguage@Search@ConstraintIndex@Cortana@@YAPE$AAVString@Platform@@XZ`
- size: `248`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800941f8`
- `0x1800a5448`
- `0x1800c38e0`
- `0x1800cd570`

## callees

- `0x1800049e0`
- `0x180005250`
- `0x18000617a`
- `0x18001c0dc`
- `0x18003a5f4`
- `0x18003e940`
- `0x18003ff8c`
- `0x1800940f8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x18009412b`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180094183`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x18009412b`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180094183`

## string_xrefs

- `0x18009413a`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexHelpers.cpp`
- `0x180094192`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 Cortana::ConstraintIndex::Search::GetUserSettingsDirectoryLanguage()
{
  const char *v0; // r9
  WCHAR *v1; // rbx
  const char *v2; // r9
  __int64 v3; // rbx
  HSTRING v5; // [rsp+20h] [rbp-28h]
  ULONG pcchLanguagesBuffer; // [rsp+28h] [rbp-20h] BYREF
  ULONG pulNumLanguages; // [rsp+2Ch] [rbp-1Ch] BYREF
  WCHAR *v8; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetUserPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x34,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexHelpers.cpp",
      v0);
  v1 = (WCHAR *)operator new[](saturated_mul(pcchLanguagesBuffer, 2u));
  v8 = v1;
  if ( !GetUserPreferredUILanguages(8u, &pulNumLanguages, v1, &pcchLanguagesBuffer) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexHelpers.cpp",
      v2);
  v5 = (HSTRING)Platform::String::String(retaddr, v1);
  v3 = __abi_winrt_ptrto_string_ctor(v5);
  WindowsDeleteString_0(v5);
  std::unique_ptr<char const [0]>::~unique_ptr<char const [0]>(&v8);
  return v3;
}

```

## disassembly

```asm
0x1800940f8  mov     [rsp+arg_0], rbx
0x1800940fd  push    rdi
0x1800940fe  sub     rsp, 40h
0x180094102  mov     rax, cs:__security_cookie
0x180094109  xor     rax, rsp
0x18009410c  mov     [rsp+48h+var_10], rax
0x180094111  xor     edi, edi
0x180094113  mov     [rsp+48h+pulNumLanguages], edi
0x180094117  mov     [rsp+48h+pcchLanguagesBuffer], edi
0x18009411b  lea     r9, [rsp+48h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180094120  xor     r8d, r8d; pwszLanguagesBuffer
0x180094123  lea     rdx, [rsp+48h+pulNumLanguages]; pulNumLanguages
0x180094128  lea     ecx, [rdi+8]; dwFlags
0x18009412b  call    cs:__imp_GetUserPreferredUILanguages
0x180094131  mov     rcx, [rsp+48h]; this
0x180094136  test    eax, eax
0x180094138  jnz     short loc_18009414A
0x18009413a  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\cortana\\constraint"...
0x180094141  lea     edx, [rdi+34h]; void *
0x180094144  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009414a  mov     edx, [rsp+48h+pcchLanguagesBuffer]
0x18009414e  mov     eax, 2
0x180094153  mul     rdx
0x180094156  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18009415d  cmovb   rax, rdx
0x180094161  mov     rcx, rax; unsigned __int64
0x180094164  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180094169  mov     rbx, rax
0x18009416c  mov     [rsp+48h+var_18], rax
0x180094171  lea     r9, [rsp+48h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180094176  mov     r8, rax; pwszLanguagesBuffer
0x180094179  lea     rdx, [rsp+48h+pulNumLanguages]; pulNumLanguages
0x18009417e  mov     ecx, 8; dwFlags
0x180094183  call    cs:__imp_GetUserPreferredUILanguages
0x180094189  mov     rcx, [rsp+48h]; this
0x18009418e  test    eax, eax
0x180094190  jnz     short loc_1800941A2
0x180094192  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\cortana\\constraint"...
0x180094199  lea     edx, [rax+37h]; void *
0x18009419c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800941a2  mov     [rsp+48h+var_28], rdi
0x1800941a7  mov     rdx, rbx
0x1800941aa  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x1800941af  mov     rdi, rax
0x1800941b2  mov     [rsp+48h+var_28], rax
0x1800941b7  mov     rcx, rax
0x1800941ba  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800941bf  mov     rbx, rax
0x1800941c2  mov     rcx, rdi; string
0x1800941c5  call    WindowsDeleteString_0
0x1800941ca  nop
0x1800941cb  lea     rcx, [rsp+48h+var_18]
0x1800941d0  call    ??1?$unique_ptr@$$BY0A@$$CBDU?$default_delete@$$BY0A@$$CBD@std@@@std@@QEAA@XZ; std::unique_ptr<char const [0]>::~unique_ptr<char const [0]>(void)
0x1800941d5  mov     rax, rbx
0x1800941d8  mov     rcx, [rsp+48h+var_10]
0x1800941dd  xor     rcx, rsp; StackCookie
0x1800941e0  call    __security_check_cookie
0x1800941e5  mov     rbx, [rsp+48h+arg_0]
0x1800941ea  add     rsp, 40h
0x1800941ee  pop     rdi
0x1800941ef  retn
```
