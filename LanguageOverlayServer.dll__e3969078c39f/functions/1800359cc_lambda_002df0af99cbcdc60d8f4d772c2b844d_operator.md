# _lambda_002df0af99cbcdc60d8f4d772c2b844d_::operator()

- ea: `0x1800359cc`
- end: `0x180035b02`
- name: `_lambda_002df0af99cbcdc60d8f4d772c2b844d_::operator()`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180034990`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180014ed0`
- `0x1800359cc`
- `0x1800387d0`
- `0x180060df4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a35`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180035a35`
- `ext-ms-win-resources-languageoverlay-l1-1-7!GetLanguageInstallationState` at `0x180035a69`
- `ext-ms-win-resources-languageoverlay-l1-1-7!GetLanguageInstallationState` at `0x180035a69`

## string_xrefs

- `0x180035a80`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180035ac3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
__int64 __fastcall lambda_002df0af99cbcdc60d8f4d772c2b844d_::operator()(
        __int64 a1,
        int **a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rax
  int *v7; // rcx
  int v8; // ebx
  const char *v9; // r9
  int LanguageInstallationState; // eax
  unsigned int v11; // ebx
  __int64 result; // rax
  int v13; // [rsp+20h] [rbp-78h]
  char *v14[4]; // [rsp+38h] [rbp-60h] BYREF
  int v15[4]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v16; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_QWORD *)v15 = a3;
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  try
  {
    *(_QWORD *)&v15[2] = v5;
    v6 = bcp47::ConvertToMuiForm(v14);
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    v7 = *a2;
    if ( *((_QWORD *)*a2 + 3) > 7u )
      v7 = *(int **)v7;
    v8 = _o__wcsicmp(v7, v6);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v14);
    if ( v8
      || (*(_OWORD *)v15 = 0,
          v16 = 0,
          LanguageInstallationState = GetLanguageInstallationState(a3, 1, v15),
          v11 = LanguageInstallationState,
          LanguageInstallationState >= 0)
      && (LanguageInstallationState = UpdateMergedLanguageInstallationResults(a3, 1, *a2[1], 1, v15[2]),
          v11 = LanguageInstallationState,
          LanguageInstallationState >= 0) )
    {
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A2,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)(unsigned int)LanguageInstallationState,
        v13);
      result = v11;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2A2,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\language"
                                         "providerutils.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800359cc  mov     [rsp+arg_0], rbx
0x1800359d1  push    rsi
0x1800359d2  push    rdi
0x1800359d3  push    r14
0x1800359d5  sub     rsp, 80h
0x1800359dc  mov     rax, cs:__security_cookie
0x1800359e3  xor     rax, rsp
0x1800359e6  mov     [rsp+98h+var_28], rax
0x1800359eb  mov     rdi, r8
0x1800359ee  mov     rsi, rdx
0x1800359f1  mov     qword ptr [rsp+98h+var_40], r8
0x1800359f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800359fa  xor     r14d, r14d
0x1800359fd  inc     rax
0x180035a00  cmp     [r8+rax*2], r14w
0x180035a05  jnz     short loc_1800359FD
0x180035a07  mov     qword ptr [rsp+98h+var_40+8], rax
0x180035a0c  lea     rdx, [rsp+98h+var_40]
0x180035a11  lea     rcx, [rsp+98h+var_60]
0x180035a16  call    ?ConvertToMuiForm@bcp47@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z; bcp47::ConvertToMuiForm(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)
0x180035a1b  cmp     qword ptr [rax+18h], 7
0x180035a20  jbe     short loc_180035A25
0x180035a22  mov     rax, [rax]
0x180035a25  mov     rcx, [rsi]
0x180035a28  cmp     qword ptr [rcx+18h], 7
0x180035a2d  jbe     short loc_180035A32
0x180035a2f  mov     rcx, [rcx]
0x180035a32  mov     rdx, rax
0x180035a35  call    cs:__imp__o__wcsicmp
0x180035a3b  mov     ebx, eax
0x180035a3d  lea     rcx, [rsp+98h+var_60]; void *
0x180035a42  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180035a47  test    ebx, ebx
0x180035a49  jnz     loc_180035AD8
0x180035a4f  xorps   xmm0, xmm0
0x180035a52  xor     eax, eax
0x180035a54  movups  xmmword ptr [rsp+98h+var_40], xmm0
0x180035a59  mov     [rsp+98h+var_30], rax
0x180035a5e  lea     r8, [rsp+98h+var_40]
0x180035a63  lea     edx, [rbx+1]
0x180035a66  mov     rcx, rdi
0x180035a69  call    cs:__imp_GetLanguageInstallationState
0x180035a6f  mov     ebx, eax
0x180035a71  test    eax, eax
0x180035a73  jns     short loc_180035A95
0x180035a75  mov     rcx, [rsp+98h]; this
0x180035a7d  mov     r9d, eax; char *
0x180035a80  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035a87  mov     edx, 2A2h; void *
0x180035a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a91  mov     eax, ebx
0x180035a93  jmp     short loc_180035AE0
0x180035a95  mov     eax, [rsp+98h+var_40+8]
0x180035a99  mov     r8, [rsi+8]
0x180035a9d  mov     [rsp+98h+var_78], eax; int
0x180035aa1  mov     r9b, 1; bool
0x180035aa4  mov     r8d, [r8]; int
0x180035aa7  mov     dl, r9b; bool
0x180035aaa  mov     rcx, rdi; unsigned __int16 *
0x180035aad  call    ?UpdateMergedLanguageInstallationResults@@YAJPEBG_NJ1J@Z; UpdateMergedLanguageInstallationResults(ushort const *,bool,long,bool,long)
0x180035ab2  mov     ebx, eax
0x180035ab4  test    eax, eax
0x180035ab6  jns     short loc_180035AD8
0x180035ab8  mov     rcx, [rsp+98h]; this
0x180035ac0  mov     r9d, eax; char *
0x180035ac3  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035aca  mov     edx, 2A2h; void *
0x180035acf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ad4  mov     eax, ebx
0x180035ad6  jmp     short loc_180035AE0
0x180035ad8  xor     eax, eax
0x180035ada  jmp     short loc_180035AE0
0x180035adc  mov     eax, [rsp+98h+var_68]
0x180035ae0  mov     rcx, [rsp+98h+var_28]
0x180035ae5  xor     rcx, rsp; StackCookie
0x180035ae8  call    __security_check_cookie
0x180035aed  mov     rbx, [rsp+98h+arg_0]
0x180035af5  add     rsp, 80h
0x180035afc  pop     r14
0x180035afe  pop     rdi
0x180035aff  pop     rsi
0x180035b00  retn
```
