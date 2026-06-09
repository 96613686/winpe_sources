# IsCxhWebcamAccessAllowedByPolicy(HSTRING__ *,bool *)

- ea: `0x1800ccab8`
- end: `0x1800ccc5a`
- name: `?IsCxhWebcamAccessAllowedByPolicy@@YAJPEAUHSTRING__@@PEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(HSTRING string, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009b770`

## callees

- `0x1800052ac`
- `0x180010c8c`
- `0x180016634`
- `0x18001a540`
- `0x18001b004`
- `0x180022790`
- `0x1800cc254`
- `0x1800cc548`
- `0x1800cc674`
- `0x1800cc73c`
- `0x1800ccab8`
- `0x1800ccc60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ccb55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ccb55`
- `WINHTTP!WinHttpCrackUrl` at `0x1800ccb68`
- `WINHTTP!WinHttpCrackUrl` at `0x1800ccb68`

## string_xrefs

- `0x1800ccc24`: `onecore\ds\security\cfl\policy\lib\cxpolicy.cpp`
- `0x1800ccc39`: `onecore\ds\security\cfl\policy\lib\cxpolicy.cpp`
- `0x1800ccc49`: `onecore\ds\security\cfl\policy\lib\cxpolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsCxhWebcamAccessAllowedByPolicy(HSTRING string, bool *a2)
{
  const WCHAR *StringRawBuffer; // rax
  const char *v5; // r9
  _QWORD *v6; // rax
  const char *v7; // r9
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v10; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D8h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v13[32]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v14[32]; // [rsp+D0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\cxpolicy.cpp",
        (const char *)0x80004003LL,
        v9);
    if ( !string )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\cxpolicy.cpp",
        (const char *)0x80004003LL,
        v9);
    *a2 = 0;
    GetAllowedListDomains((__int64)v14);
    LowerString(v14);
    AllowedListToDomains(&v10, v14);
    memset_0(&UrlComponents, 0, sizeof(UrlComponents));
    UrlComponents.dwStructSize = 104;
    UrlComponents.dwHostNameLength = 1;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !WinHttpCrackUrl(StringRawBuffer, 0, 0, &UrlComponents) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\cxpolicy.cpp",
        v5);
    std::wstring::wstring(
      v13,
      UrlComponents.lpszHostName,
      &UrlComponents.lpszHostName[2 * UrlComponents.dwHostNameLength]);
    LowerString(v13);
    v6 = (_QWORD *)std::find<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(
                     &v9,
                     v10,
                     v11,
                     v13);
    *a2 = *v6 != v11;
    std::wstring::_Tidy_deallocate(v13);
    std::vector<std::wstring>::_Tidy(&v10);
    std::wstring::_Tidy_deallocate(v14);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x53,
                           (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\cxpolicy.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800ccab8  mov     [rsp+arg_10], rbx
0x1800ccabd  push    rdi
0x1800ccabe  sub     rsp, 100h
0x1800ccac5  mov     rax, cs:__security_cookie
0x1800ccacc  xor     rax, rsp
0x1800ccacf  mov     [rsp+108h+var_18], rax
0x1800ccad7  mov     rbx, rdx
0x1800ccada  mov     rdi, rcx
0x1800ccadd  mov     rcx, [rsp+108h]; this
0x1800ccae5  test    rdx, rdx
0x1800ccae8  jz      loc_1800CCC1E
0x1800ccaee  mov     rcx, [rsp+108h]; this
0x1800ccaf6  test    rdi, rdi
0x1800ccaf9  jz      loc_1800CCC33
0x1800ccaff  mov     byte ptr [rdx], 0
0x1800ccb02  lea     rcx, [rsp+108h+var_38]
0x1800ccb0a  call    GetAllowedListDomains
0x1800ccb0f  nop
0x1800ccb10  lea     rcx, [rsp+108h+var_38]
0x1800ccb18  call    LowerString
0x1800ccb1d  lea     rdx, [rsp+108h+var_38]
0x1800ccb25  lea     rcx, [rsp+108h+var_E0]
0x1800ccb2a  call    AllowedListToDomains
0x1800ccb2f  nop
0x1800ccb30  xor     edx, edx; Val
0x1800ccb32  lea     r8d, [rdx+68h]; Size
0x1800ccb36  lea     rcx, [rsp+108h+UrlComponents]; void *
0x1800ccb3b  call    memset_0
0x1800ccb40  mov     [rsp+108h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800ccb48  mov     [rsp+108h+UrlComponents.dwHostNameLength], 1
0x1800ccb50  xor     edx, edx; length
0x1800ccb52  mov     rcx, rdi; string
0x1800ccb55  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ccb5b  mov     rcx, rax; pwszUrl
0x1800ccb5e  lea     r9, [rsp+108h+UrlComponents]; lpUrlComponents
0x1800ccb63  xor     r8d, r8d; dwFlags
0x1800ccb66  xor     edx, edx; dwUrlLength
0x1800ccb68  call    cs:__imp_WinHttpCrackUrl
0x1800ccb6e  mov     rcx, [rsp+108h]; this
0x1800ccb76  test    eax, eax
0x1800ccb78  jz      loc_1800CCC49
0x1800ccb7e  mov     eax, [rsp+108h+UrlComponents.dwHostNameLength]
0x1800ccb82  mov     rdx, [rsp+108h+UrlComponents.lpszHostName]
0x1800ccb87  lea     r8, [rdx+rax*2]
0x1800ccb8b  lea     rcx, [rsp+108h+var_58]
0x1800ccb93  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800ccb98  nop
0x1800ccb99  lea     rcx, [rsp+108h+var_58]
0x1800ccba1  call    LowerString
0x1800ccba6  lea     r9, [rsp+108h+var_58]
0x1800ccbae  mov     r8, [rsp+108h+var_D8]
0x1800ccbb3  mov     rdx, [rsp+108h+var_E0]
0x1800ccbb8  lea     rcx, [rsp+108h+var_E8]
0x1800ccbbd  call    ??$find@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@V10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::find<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring const &)
0x1800ccbc2  mov     rcx, [rsp+108h+var_D8]
0x1800ccbc7  cmp     [rax], rcx
0x1800ccbca  setnz   al
0x1800ccbcd  mov     [rbx], al
0x1800ccbcf  lea     rcx, [rsp+108h+var_58]
0x1800ccbd7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccbdc  nop
0x1800ccbdd  lea     rcx, [rsp+108h+var_E0]
0x1800ccbe2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ccbe7  nop
0x1800ccbe8  lea     rcx, [rsp+108h+var_38]
0x1800ccbf0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccbf5  xor     eax, eax
0x1800ccbf7  jmp     short loc_1800CCBFD
0x1800ccbf9  mov     eax, [rsp+108h+var_E8]
0x1800ccbfd  mov     rcx, [rsp+108h+var_18]
0x1800ccc05  xor     rcx, rsp; StackCookie
0x1800ccc08  call    __security_check_cookie
0x1800ccc0d  mov     rbx, [rsp+108h+arg_10]
0x1800ccc15  add     rsp, 100h
0x1800ccc1c  pop     rdi
0x1800ccc1d  retn
0x1800ccc1e  mov     r9d, 80004003h; char *
0x1800ccc24  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800ccc2b  lea     edx, [rbx+3Dh]; void *
0x1800ccc2e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ccc33  mov     r9d, 80004003h; char *
0x1800ccc39  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800ccc40  lea     edx, [rdi+3Eh]; void *
0x1800ccc43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ccc49  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800ccc50  lea     edx, [rax+4Ah]; void *
0x1800ccc53  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
