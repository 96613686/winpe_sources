# Cortana::ConstraintIndex::Search::DEInputFileWriter::AddItem(Platform::String *,int,Platform::String *,Platform::String *,int,int)

- ea: `0x18009b864`
- end: `0x18009ba26`
- name: `?AddItem@DEInputFileWriter@Search@ConstraintIndex@Cortana@@QEAAXPE$AAVString@Platform@@H00HH@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009dfe0`

## callees

- `0x1800049e0`
- `0x18000619e`
- `0x18000c840`
- `0x18000cdb0`
- `0x18003e940`
- `0x180040b20`
- `0x18009b574`
- `0x18009b864`
- `0x18009ba2c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009b8fb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009b95a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009b8fb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009b95a`

## string_xrefs

- `0x18009b905`: `shellcommon\shell\cortana\constraintindex\src\Search\DEInputFileWriter.cpp`
- `0x18009b964`: `shellcommon\shell\cortana\constraintindex\src\Search\DEInputFileWriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Cortana::ConstraintIndex::Search::DEInputFileWriter::AddItem(
        __int64 a1,
        HSTRING a2,
        unsigned int a3,
        HSTRING a4,
        HSTRING string,
        unsigned int a6,
        int a7)
{
  PCWSTR StringRawBuffer_0; // rax
  const WCHAR *v12; // rax
  const char *v13; // r9
  const WCHAR *v14; // rax
  const char *v15; // r9
  CHAR *v16; // rax
  CHAR *v17; // rdx
  CHAR v18; // cl
  __int64 v19; // rax
  _BYTE v21[32]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR v22[32]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR lpMultiByteStr[272]; // [rsp+80h] [rbp-80h] BYREF
  CHAR MultiByteStr[272]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v25[1024]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  StringRawBuffer_0 = WindowsGetStringRawBuffer_0(string, 0);
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(
    a1,
    v22,
    StringRawBuffer_0);
  v12 = WindowsGetStringRawBuffer_0(a2, 0);
  if ( !WideCharToMultiByte(0xFDE9u, 0, v12, -1, MultiByteStr, 260, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\DEInputFileWriter.cpp",
      v13);
  v14 = WindowsGetStringRawBuffer_0(a4, 0);
  if ( !WideCharToMultiByte(0xFDE9u, 0, v14, -1, lpMultiByteStr, 260, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x81,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\DEInputFileWriter.cpp",
      v15);
  v16 = v25;
  v17 = lpMultiByteStr;
  do
  {
    v18 = *v17;
    if ( !*v17 )
      break;
    if ( v18 == 92 )
      *v16++ = 92;
    *v16++ = v18;
    ++v17;
  }
  while ( v17 );
  *v16 = 0;
  v19 = std::_String_val<std::_Simple_types<char>>::_Myptr(v22);
  Cortana::Common::string_printf<char *,int,char *,char const *,int,int>(v21, a6, MultiByteStr, a3, v25, v19, a6, a7);
  Cortana::ConstraintIndex::Search::DEInputFileWriter::AddLine(a1, v21);
  std::string::_Tidy_deallocate(v21);
  return std::string::_Tidy_deallocate(v22);
}

```

## disassembly

```asm
0x18009b864  push    rbp
0x18009b866  push    rbx
0x18009b867  push    rsi
0x18009b868  push    rdi
0x18009b869  push    r14
0x18009b86b  lea     rbp, [rsp-5B0h]
0x18009b873  sub     rsp, 6B0h
0x18009b87a  mov     rax, cs:__security_cookie
0x18009b881  xor     rax, rsp
0x18009b884  mov     [rbp+5D0h+var_30], rax
0x18009b88b  mov     rdi, r9
0x18009b88e  mov     r14d, r8d
0x18009b891  mov     rbx, rdx
0x18009b894  mov     rsi, rcx
0x18009b897  mov     rcx, [rbp+5D0h+string]; string
0x18009b89e  xor     edx, edx; length
0x18009b8a0  call    WindowsGetStringRawBuffer_0
0x18009b8a5  mov     r8, rax
0x18009b8a8  lea     rdx, [rsp+6D0h+var_670]
0x18009b8ad  mov     rcx, rsi
0x18009b8b0  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEB_W@Z; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::to_bytes(wchar_t const *)
0x18009b8b5  nop
0x18009b8b6  xor     edx, edx; length
0x18009b8b8  mov     rcx, rbx; string
0x18009b8bb  call    WindowsGetStringRawBuffer_0
0x18009b8c0  mov     rbx, [rbp+5D8h]
0x18009b8c7  mov     [rsp+6D0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18009b8d0  mov     [rsp+6D0h+lpDefaultChar], 0; lpDefaultChar
0x18009b8d9  mov     [rsp+6D0h+cbMultiByte], 104h; cbMultiByte
0x18009b8e1  lea     rcx, [rbp+5D0h+MultiByteStr]
0x18009b8e8  mov     [rsp+6D0h+lpMultiByteStr], rcx; lpMultiByteStr
0x18009b8ed  or      r9d, 0FFFFFFFFh; cchWideChar
0x18009b8f1  mov     r8, rax; lpWideCharStr
0x18009b8f4  xor     edx, edx; dwFlags
0x18009b8f6  mov     ecx, 0FDE9h; CodePage
0x18009b8fb  call    cs:__imp_WideCharToMultiByte
0x18009b901  test    eax, eax
0x18009b903  jnz     short loc_18009B918
0x18009b905  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\cortana\\constraint"...
0x18009b90c  lea     edx, [rax+7Eh]; void *
0x18009b90f  mov     rcx, rbx; this
0x18009b912  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009b918  xor     edx, edx; length
0x18009b91a  mov     rcx, rdi; string
0x18009b91d  call    WindowsGetStringRawBuffer_0
0x18009b922  mov     rbx, [rbp+5D8h]
0x18009b929  mov     [rsp+6D0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18009b932  mov     [rsp+6D0h+lpDefaultChar], 0; lpDefaultChar
0x18009b93b  mov     [rsp+6D0h+cbMultiByte], 104h; cbMultiByte
0x18009b943  lea     rdx, [rbp+5D0h+var_650]
0x18009b947  mov     [rsp+6D0h+lpMultiByteStr], rdx; lpMultiByteStr
0x18009b94c  or      r9d, 0FFFFFFFFh; cchWideChar
0x18009b950  mov     r8, rax; lpWideCharStr
0x18009b953  xor     edx, edx; dwFlags
0x18009b955  mov     ecx, 0FDE9h; CodePage
0x18009b95a  call    cs:__imp_WideCharToMultiByte
0x18009b960  test    eax, eax
0x18009b962  jnz     short loc_18009B979
0x18009b964  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\cortana\\constraint"...
0x18009b96b  mov     edx, 81h; void *
0x18009b970  mov     rcx, rbx; this
0x18009b973  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009b979  lea     rax, [rbp+5D0h+var_430]
0x18009b980  lea     rdx, [rbp+5D0h+var_650]
0x18009b984  mov     cl, [rdx]
0x18009b986  test    cl, cl
0x18009b988  jz      short loc_18009B99F
0x18009b98a  cmp     cl, 5Ch ; '\'
0x18009b98d  jnz     short loc_18009B994
0x18009b98f  mov     [rax], cl
0x18009b991  inc     rax
0x18009b994  mov     [rax], cl
0x18009b996  inc     rax
0x18009b999  add     rdx, 1
0x18009b99d  jnz     short loc_18009B984
0x18009b99f  mov     byte ptr [rax], 0
0x18009b9a2  lea     rcx, [rsp+6D0h+var_670]
0x18009b9a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18009b9ac  mov     edx, [rbp+5D0h+arg_30]
0x18009b9b2  mov     dword ptr [rsp+6D0h+lpUsedDefaultChar], edx
0x18009b9b6  mov     edx, [rbp+5D0h+arg_28]
0x18009b9bc  mov     dword ptr [rsp+6D0h+lpDefaultChar], edx
0x18009b9c0  mov     qword ptr [rsp+6D0h+cbMultiByte], rax
0x18009b9c5  lea     rax, [rbp+5D0h+var_430]
0x18009b9cc  mov     [rsp+6D0h+lpMultiByteStr], rax
0x18009b9d1  mov     r9d, r14d
0x18009b9d4  lea     r8, [rbp+5D0h+MultiByteStr]
0x18009b9db  lea     rcx, [rsp+6D0h+var_690]
0x18009b9e0  call    ??$string_printf@PEADHPEADPEBDHH@Common@Cortana@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDPEADH10HH@Z; Cortana::Common::string_printf<char *,int,char *,char const *,int,int>(char const *,char *,int,char *,char const *,int,int)
0x18009b9e5  nop
0x18009b9e6  lea     rdx, [rsp+6D0h+var_690]
0x18009b9eb  mov     rcx, rsi
0x18009b9ee  call    ?AddLine@DEInputFileWriter@Search@ConstraintIndex@Cortana@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Cortana::ConstraintIndex::Search::DEInputFileWriter::AddLine(std::string const &)
0x18009b9f3  nop
0x18009b9f4  lea     rcx, [rsp+6D0h+var_690]
0x18009b9f9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009b9fe  nop
0x18009b9ff  lea     rcx, [rsp+6D0h+var_670]
0x18009ba04  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18009ba09  mov     rcx, [rbp+5D0h+var_30]
0x18009ba10  xor     rcx, rsp; StackCookie
0x18009ba13  call    __security_check_cookie
0x18009ba18  add     rsp, 6B0h
0x18009ba1f  pop     r14
0x18009ba21  pop     rdi
0x18009ba22  pop     rsi
0x18009ba23  pop     rbx
0x18009ba24  pop     rbp
0x18009ba25  retn
```
