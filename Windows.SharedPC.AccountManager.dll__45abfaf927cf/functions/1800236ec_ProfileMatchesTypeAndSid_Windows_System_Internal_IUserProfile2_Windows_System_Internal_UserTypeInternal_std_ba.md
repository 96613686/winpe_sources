# ProfileMatchesTypeAndSid(Windows::System::Internal::IUserProfile2 *,Windows::System::Internal::UserTypeInternal,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800236ec`
- end: `0x1800237ea`
- name: `?ProfileMatchesTypeAndSid@@YA_NPEAUIUserProfile2@Internal@System@Windows@@W4UserTypeInternal@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `254`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022f60`
- `0x1800230a8`

## callees

- `0x18000ccd4`
- `0x180013dcc`
- `0x1800236ec`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800237c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800237c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800237a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800237a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800237ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800237ce`

## string_xrefs

- `0x180023728`: `shellcommon\shell\sharedpc\accountmanager\lib\util\specialaccountsutils.cpp`
- `0x180023783`: `shellcommon\shell\sharedpc\accountmanager\lib\util\specialaccountsutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall ProfileMatchesTypeAndSid(__int64 a1, int a2)
{
  int v4; // eax
  bool result; // al
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  const WCHAR *v8; // rbx
  const WCHAR *StringRawBuffer; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v12; // [rsp+40h] [rbp+8h] BYREF
  HSTRING string; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 48LL))(a1, &v12);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x20,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\specialaccountsutils.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
  result = 0;
  if ( v12 == a2 )
  {
    string = 0;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v7 = v6(a1, &string);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x25,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\specialaccountsutils.cpp",
        (const char *)(unsigned int)v7,
        bIgnoreCase);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    LODWORD(v8) = CompareStringOrdinal(StringRawBuffer, -1, v8, -1, 1);
    WindowsDeleteString(string);
    return (_DWORD)v8 == 2;
  }
  return result;
}

```

## disassembly

```asm
0x1800236ec  mov     [rsp+arg_8], rbx
0x1800236f1  mov     [rsp+arg_10], rsi
0x1800236f6  push    rdi
0x1800236f7  sub     rsp, 30h
0x1800236fb  mov     rsi, r8
0x1800236fe  mov     ebx, edx
0x180023700  mov     rdi, rcx
0x180023703  mov     [rsp+38h+arg_0], 0
0x18002370b  mov     rax, [rcx]
0x18002370e  lea     rdx, [rsp+38h+arg_0]
0x180023713  mov     rax, [rax+30h]
0x180023717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002371c  mov     rcx, [rsp+38h]; this
0x180023721  test    eax, eax
0x180023723  jns     short loc_18002373A
0x180023725  mov     r9d, eax; char *
0x180023728  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002372f  mov     edx, 20h ; ' '; void *
0x180023734  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002373a  xor     al, al
0x18002373c  cmp     [rsp+38h+arg_0], ebx
0x180023740  jnz     loc_1800237DA
0x180023746  mov     [rsp+38h+string], 0
0x18002374f  mov     rax, [rdi]
0x180023752  mov     rbx, [rax+38h]
0x180023756  xor     ecx, ecx; string
0x180023758  call    cs:__imp_WindowsDeleteString
0x18002375e  mov     [rsp+38h+string], 0
0x180023767  lea     rdx, [rsp+38h+string]
0x18002376c  mov     rcx, rdi
0x18002376f  mov     rax, rbx
0x180023772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023777  mov     rcx, [rsp+38h]; this
0x18002377c  test    eax, eax
0x18002377e  jns     short loc_180023795
0x180023780  mov     r9d, eax; char *
0x180023783  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\sharedpc\\accountma"...
0x18002378a  mov     edx, 25h ; '%'; void *
0x18002378f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023795  mov     rcx, rsi
0x180023798  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002379d  mov     rbx, rax
0x1800237a0  xor     edx, edx; length
0x1800237a2  mov     rcx, [rsp+38h+string]; string
0x1800237a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800237ad  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800237b5  or      edx, 0FFFFFFFFh; cchCount1
0x1800237b8  mov     r9d, edx; cchCount2
0x1800237bb  mov     r8, rbx; lpString2
0x1800237be  mov     rcx, rax; lpString1
0x1800237c1  call    cs:__imp_CompareStringOrdinal
0x1800237c7  mov     ebx, eax
0x1800237c9  mov     rcx, [rsp+38h+string]; string
0x1800237ce  call    cs:__imp_WindowsDeleteString
0x1800237d4  cmp     ebx, 2
0x1800237d7  setz    al
0x1800237da  mov     rbx, [rsp+38h+arg_8]
0x1800237df  mov     rsi, [rsp+38h+arg_10]
0x1800237e4  add     rsp, 30h
0x1800237e8  pop     rdi
0x1800237e9  retn
```
