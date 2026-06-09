# CallNotifyUILanguageChange(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,bool)

- ea: `0x180013210`
- end: `0x180013345`
- name: `?CallNotifyUILanguageChange@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@_N@Z`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800190bc`

## callees

- `0x180002380`
- `0x180003618`
- `0x180009d24`
- `0x180013210`
- `0x180016134`
- `0x18001d564`
- `0x18001de84`

## import_xrefs

- `ext-ms-win-kernel32-localization-l1-1-0!NotifyUILanguageChange` at `0x1800132ad`
- `ext-ms-win-kernel32-localization-l1-1-0!NotifyUILanguageChange` at `0x1800132ad`

## string_xrefs

- `0x1800132fa`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallNotifyUILanguageChange(__int64 a1, _QWORD *a2, char a3)
{
  __int64 result; // rax
  const WCHAR *v6; // rax
  PCWSTR v7; // rdx
  __int64 v8; // rax
  int v9; // edx
  const char *v10; // r9
  DWORD v11; // [rsp+38h] [rbp-60h]
  DWORD pdwStatusRtrn; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v13[32]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v14[32]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  result = IsNotifyUILanguageChangePresent();
  if ( (_BYTE)result )
  {
    DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(
      v14,
      *a2,
      a2[1],
      0);
    DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(
      v13,
      *a2,
      a2[1],
      59);
    pdwStatusRtrn = 0;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    NotifyUILanguageChange(a3 != 0 ? 32 : 1, v7, v6, 0, &pdwStatusRtrn);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v11 = pdwStatusRtrn;
    wil::details::in1diag3::Log_GetLastErrorIfMsg(
      retaddr,
      (void *)0x36A,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(v9 == 0),
      (bool)"new lang: %ws, prev lang: %ws, callbacks return: %lu",
      v10,
      v8,
      v11);
    std::wstring::_Tidy_deallocate(v13);
    return std::wstring::_Tidy_deallocate(v14);
  }
  return result;
}

```

## disassembly

```asm
0x180013210  mov     [rsp+arg_8], rbx
0x180013215  mov     [rsp+arg_10], rsi
0x18001321a  push    rdi
0x18001321b  sub     rsp, 90h
0x180013222  mov     rax, cs:__security_cookie
0x180013229  xor     rax, rsp
0x18001322c  mov     [rsp+98h+var_10], rax
0x180013234  mov     dil, r8b
0x180013237  mov     rbx, rdx
0x18001323a  mov     rsi, rcx
0x18001323d  call    IsNotifyUILanguageChangePresent
0x180013242  test    al, al
0x180013244  jz      loc_180013320
0x18001324a  xor     r9d, r9d
0x18001324d  mov     r8, [rbx+8]
0x180013251  mov     rdx, [rbx]
0x180013254  lea     rcx, [rsp+98h+var_30]
0x180013259  call    ??$DelimitedStringFromItems@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x18001325e  nop
0x18001325f  mov     r9d, 3Bh ; ';'
0x180013265  mov     r8, [rbx+8]
0x180013269  mov     rdx, [rbx]
0x18001326c  lea     rcx, [rsp+98h+var_50]
0x180013271  call    ??$DelimitedStringFromItems@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,ushort)
0x180013276  mov     [rsp+98h+var_58], 0
0x18001327e  mov     rcx, rsi
0x180013281  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013286  mov     rdx, rax
0x180013289  lea     rcx, [rsp+98h+var_30]
0x18001328e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013293  mov     r8, rax; pcwstrPreviousLanguage
0x180013296  neg     dil
0x180013299  sbb     ecx, ecx
0x18001329b  and     ecx, 1Fh
0x18001329e  inc     ecx; dwFlags
0x1800132a0  lea     rax, [rsp+98h+var_58]
0x1800132a5  mov     [rsp+98h+pdwStatusRtrn], rax; pdwStatusRtrn
0x1800132aa  xor     r9d, r9d; dwReserved
0x1800132ad  call    cs:__imp_NotifyUILanguageChange
0x1800132b3  mov     edx, eax
0x1800132b5  mov     rcx, rsi
0x1800132b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800132bd  mov     r9, rax
0x1800132c0  lea     rcx, [rsp+98h+var_50]
0x1800132c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800132ca  test    edx, edx
0x1800132cc  setz    r8b
0x1800132d0  mov     rcx, [rsp+98h]; this
0x1800132d8  mov     edx, [rsp+98h+var_58]
0x1800132dc  mov     [rsp+98h+var_60], edx
0x1800132e0  mov     [rsp+98h+var_68], rax
0x1800132e5  mov     [rsp+98h+var_70], r9; char *
0x1800132ea  lea     rax, aNewLangWsPrevL; "new lang: %ws, prev lang: %ws, callback"...
0x1800132f1  mov     [rsp+98h+pdwStatusRtrn], rax; bool
0x1800132f6  movzx   r9d, r8b; char *
0x1800132fa  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180013301  mov     edx, 36Ah; void *
0x180013306  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001330b  lea     rcx, [rsp+98h+var_50]
0x180013310  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013315  nop
0x180013316  lea     rcx, [rsp+98h+var_30]
0x18001331b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013320  mov     rcx, [rsp+98h+var_10]
0x180013328  xor     rcx, rsp; StackCookie
0x18001332b  call    __security_check_cookie
0x180013330  lea     r11, [rsp+98h+var_8]
0x180013338  mov     rbx, [r11+18h]
0x18001333c  mov     rsi, [r11+20h]
0x180013340  mov     rsp, r11
0x180013343  pop     rdi
0x180013344  retn
```
