# _lambda_81b5c9811386bfc5ac6c3e5741e4c3a3_::_lambda_invoker_cdecl_

- ea: `0x18004ada0`
- end: `0x18004ae98`
- name: `_lambda_81b5c9811386bfc5ac6c3e5741e4c3a3_::_lambda_invoker_cdecl_`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180014720`
- `0x180014ed0`
- `0x18004ada0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004ae0e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004ae0e`
- `AppXDeploymentClient!__imp_AppxRemovePackageForAllUsers` at `0x18004ae3f`
- `AppXDeploymentClient!__imp_AppxRemovePackageForAllUsers` at `0x18004ae3f`

## string_xrefs

- `0x18004ae53`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`

## pseudocode

```c
__int64 __fastcall lambda_81b5c9811386bfc5ac6c3e5741e4c3a3_::_lambda_invoker_cdecl_(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5)
{
  bool v7; // di
  _QWORD *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  int v15[8]; // [rsp+20h] [rbp-48h] BYREF
  int v16; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = 1;
  *a5 = 1;
  v8 = (_QWORD *)std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
                   v15,
                   a3);
  v9 = v8[2];
  if ( v8[3] > 7u )
    v8 = (_QWORD *)*v8;
  v10 = a1[2];
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  if ( v10 == v9 )
  {
    if ( v10 )
      v7 = (unsigned int)_o__wcsnicmp(a1, v8) == 0;
  }
  else
  {
    v7 = 0;
  }
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v15);
  if ( !v7 )
    return 0;
  *a5 = 0;
  v16 = 0;
  v11 = AppxRemovePackageForAllUsers(a2, &v16);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( v16 )
    {
      v12 = -2147009286;
      v13 = 2147958010LL;
      goto LABEL_12;
    }
    return 0;
  }
  v13 = (unsigned int)v11;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1CE,
    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
    (const char *)v13,
    v15[0]);
  return v12;
}

```

## disassembly

```asm
0x18004ada0  mov     [rsp+arg_18], rbx
0x18004ada5  push    rbp
0x18004ada6  push    rsi
0x18004ada7  push    rdi
0x18004ada8  sub     rsp, 50h
0x18004adac  mov     rax, cs:__security_cookie
0x18004adb3  xor     rax, rsp
0x18004adb6  mov     [rsp+68h+var_20], rax
0x18004adbb  mov     rsi, [rsp+68h+arg_20]
0x18004adc3  mov     rbp, rdx
0x18004adc6  mov     rbx, rcx
0x18004adc9  mov     edi, 1
0x18004adce  mov     rdx, r8
0x18004add1  lea     rcx, [rsp+68h+var_48]
0x18004add6  mov     [rsi], edi
0x18004add8  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x18004addd  cmp     qword ptr [rax+18h], 7
0x18004ade2  mov     rcx, [rax+10h]
0x18004ade6  jbe     short loc_18004ADEB
0x18004ade8  mov     rax, [rax]
0x18004adeb  cmp     qword ptr [rbx+18h], 7
0x18004adf0  mov     r8, [rbx+10h]
0x18004adf4  jbe     short loc_18004ADF9
0x18004adf6  mov     rbx, [rbx]
0x18004adf9  cmp     r8, rcx
0x18004adfc  jz      short loc_18004AE03
0x18004adfe  xor     dil, dil
0x18004ae01  jmp     short loc_18004AE1A
0x18004ae03  test    r8, r8
0x18004ae06  jz      short loc_18004AE1A
0x18004ae08  mov     rdx, rax
0x18004ae0b  mov     rcx, rbx
0x18004ae0e  call    cs:__imp__o__wcsnicmp
0x18004ae14  test    eax, eax
0x18004ae16  setz    dil
0x18004ae1a  lea     rcx, [rsp+68h+var_48]; void *
0x18004ae1f  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18004ae24  test    dil, dil
0x18004ae27  jz      short loc_18004AE77
0x18004ae29  lea     rdx, [rsp+68h+var_28]
0x18004ae2e  mov     dword ptr [rsi], 0
0x18004ae34  mov     rcx, rbp
0x18004ae37  mov     [rsp+68h+var_28], 0
0x18004ae3f  call    cs:__imp_AppxRemovePackageForAllUsers
0x18004ae45  mov     ebx, eax
0x18004ae47  test    eax, eax
0x18004ae49  jns     short loc_18004AE66
0x18004ae4b  mov     r9d, eax; char *
0x18004ae4e  mov     rcx, [rsp+68h]; this
0x18004ae53  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004ae5a  mov     edx, 1CEh; void *
0x18004ae5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ae64  jmp     short loc_18004AE79
0x18004ae66  cmp     [rsp+68h+var_28], 0
0x18004ae6b  jz      short loc_18004AE77
0x18004ae6d  mov     ebx, 80073CFAh
0x18004ae72  mov     r9d, ebx
0x18004ae75  jmp     short loc_18004AE4E
0x18004ae77  xor     ebx, ebx
0x18004ae79  mov     eax, ebx
0x18004ae7b  mov     rcx, [rsp+68h+var_20]
0x18004ae80  xor     rcx, rsp; StackCookie
0x18004ae83  call    __security_check_cookie
0x18004ae88  mov     rbx, [rsp+68h+arg_18]
0x18004ae90  add     rsp, 50h
0x18004ae94  pop     rdi
0x18004ae95  pop     rsi
0x18004ae96  pop     rbp
0x18004ae97  retn
```
