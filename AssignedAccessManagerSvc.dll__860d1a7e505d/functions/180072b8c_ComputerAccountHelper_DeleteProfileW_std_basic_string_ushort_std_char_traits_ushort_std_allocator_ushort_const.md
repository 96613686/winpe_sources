# ComputerAccountHelper::DeleteProfileW(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180072b8c`
- end: `0x180072c45`
- name: `?DeleteProfileW@ComputerAccountHelper@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a020`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000dc5c`
- `0x18000f62c`
- `0x180010c98`
- `0x18002001c`
- `0x18007240c`
- `0x180072b8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072bf8`
- `USERENV!DeleteProfileW` at `0x180072bee`
- `USERENV!DeleteProfileW` at `0x180072bee`

## string_xrefs

- `0x180072bc6`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\computeraccounthelper.cpp`
- `0x180072c0c`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\computeraccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComputerAccountHelper::DeleteProfileW(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  int UserSid; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // rax
  DWORD LastError; // eax
  unsigned int v8[8]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  std::wstring::wstring(v8, a2, a2);
  UserSid = GetUserSid(v2, v8);
  v4 = UserSid;
  if ( UserSid >= 0 )
  {
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
    if ( DeleteProfileW(v5, 0, 0) || (LastError = GetLastError(), LastError == 2) || !LastError )
      v4 = 0;
    else
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x56,
             (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\computeraccounthelper.cpp",
             (const char *)LastError,
             v8[0]);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\computeraccounthelper.cpp",
      (const char *)(unsigned int)UserSid,
      v8[0]);
  }
  std::wstring::_Tidy_deallocate(v8);
  return v4;
}

```

## disassembly

```asm
0x180072b8c  push    rbx
0x180072b8e  sub     rsp, 50h
0x180072b92  mov     rax, cs:__security_cookie
0x180072b99  xor     rax, rsp
0x180072b9c  mov     [rsp+58h+var_18], rax
0x180072ba1  lea     rcx, [rsp+58h+var_38]
0x180072ba6  mov     r8, rdx
0x180072ba9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180072bae  lea     rdx, [rsp+58h+var_38]
0x180072bb3  mov     rcx, r8
0x180072bb6  call    GetUserSid
0x180072bbb  mov     ebx, eax
0x180072bbd  test    eax, eax
0x180072bbf  jns     short loc_180072BDC
0x180072bc1  mov     rcx, [rsp+58h]; this
0x180072bc6  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072bcd  mov     r9d, eax; char *
0x180072bd0  mov     edx, 4Fh ; 'O'; void *
0x180072bd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072bda  jmp     short loc_180072C26
0x180072bdc  lea     rcx, [rsp+58h+var_38]
0x180072be1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180072be6  mov     rcx, rax; lpSidString
0x180072be9  xor     r8d, r8d; lpComputerName
0x180072bec  xor     edx, edx; lpProfilePath
0x180072bee  call    cs:__imp_DeleteProfileW
0x180072bf4  test    eax, eax
0x180072bf6  jnz     short loc_180072C24
0x180072bf8  call    cs:__imp_GetLastError
0x180072bfe  cmp     eax, 2
0x180072c01  jz      short loc_180072C24
0x180072c03  test    eax, eax
0x180072c05  jz      short loc_180072C24
0x180072c07  mov     rcx, [rsp+58h]; this
0x180072c0c  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180072c13  mov     r9d, eax; char *
0x180072c16  mov     edx, 56h ; 'V'; void *
0x180072c1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180072c20  mov     ebx, eax
0x180072c22  jmp     short loc_180072C26
0x180072c24  xor     ebx, ebx
0x180072c26  lea     rcx, [rsp+58h+var_38]
0x180072c2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180072c30  mov     eax, ebx
0x180072c32  mov     rcx, [rsp+58h+var_18]
0x180072c37  xor     rcx, rsp; StackCookie
0x180072c3a  call    __security_check_cookie
0x180072c3f  add     rsp, 50h
0x180072c43  pop     rbx
0x180072c44  retn
```
