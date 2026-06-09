# GetProfileMatchingLanguages(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180053e18`
- end: `0x180053fad`
- name: `?GetProfileMatchingLanguages@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180053d58`

## callees

- `0x18001e2e4`
- `0x18001e668`
- `0x18001e6e0`
- `0x18001ee7c`
- `0x1800202e4`
- `0x1800431c0`
- `0x180053e18`
- `0x180053fb4`
- `0x180054298`
- `0x18005464c`
- `0x180061320`
- `0x180062344`
- `0x18008fbd8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180053e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e54`
- `Bcp47Langs!GetUserLanguages` at `0x180053e65`
- `Bcp47Langs!GetUserLanguages` at `0x180053e65`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall GetProfileMatchingLanguages(_QWORD *a1, _QWORD *a2)
{
  int UserLanguages; // eax
  WCHAR *StringRawBuffer; // rax
  char **v6; // rax
  __int64 v7; // rsi
  PCWSTR v8; // rdi
  const WCHAR *v9; // r13
  int v10; // r12d
  __int64 v11; // rbx
  const WCHAR *v12; // rdx
  int LanguagesClosenessScore; // eax
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rdx
  int pExceptionObject; // [rsp+20h] [rbp-49h] BYREF
  HSTRING string; // [rsp+28h] [rbp-41h] BYREF
  int v20; // [rsp+30h] [rbp-39h]
  PCWSTR v21; // [rsp+38h] [rbp-31h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h]
  _QWORD *v23; // [rsp+50h] [rbp-19h]
  char *v24[4]; // [rsp+58h] [rbp-11h] BYREF

  v23 = a1;
  v20 = 0;
  WindowsDeleteString(0);
  string = 0;
  UserLanguages = GetUserLanguages(59, &string);
  if ( UserLanguages < 0 )
  {
    pExceptionObject = UserLanguages;
    throw (long *)&pExceptionObject;
  }
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
  v6 = std::wstring::wstring(v24, StringRawBuffer);
  WstringContainerFromDelimitedString<std::vector<std::wstring>>(&v21, v6);
  std::wstring::_Tidy_deallocate(v24);
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v20 = 7;
  v7 = v22;
  while ( 1 )
  {
    v8 = v21;
    v9 = a2[3] <= 7u ? (const WCHAR *)a2 : (const WCHAR *)*a2;
    v10 = 74;
    v11 = v7;
    while ( v8 != (PCWSTR)v7 )
    {
      pExceptionObject = v10;
      if ( *((_QWORD *)v8 + 3) <= 7u )
        v12 = v8;
      else
        v12 = *(const WCHAR **)v8;
      LanguagesClosenessScore = GetLanguagesClosenessScore(v9, v12);
      v14 = LanguagesClosenessScore;
      if ( LanguagesClosenessScore > v10 )
        v10 = LanguagesClosenessScore;
      v15 = (__int64)v8;
      if ( v14 <= pExceptionObject )
        v15 = v11;
      v11 = v15;
      v8 += 16;
    }
    if ( v11 == v22 )
      break;
    v16 = a1[1];
    if ( v16 == a1[2] )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v16, v11);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(a1, v11);
    std::_Move_unchecked<std::wstring *,std::wstring *>(v11 + 32, v22, v11);
    std::wstring::`scalar deleting destructor'((void *)(v22 - 32));
    v7 = v22 - 32;
    v22 -= 32;
  }
  std::vector<std::wstring>::_Tidy(&v21);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return a1;
}

```

## disassembly

```asm
0x180053e18  push    rbp
0x180053e1a  push    rbx
0x180053e1b  push    rsi
0x180053e1c  push    rdi
0x180053e1d  push    r12
0x180053e1f  push    r13
0x180053e21  push    r14
0x180053e23  push    r15
0x180053e25  lea     rbp, [rsp-1Fh]
0x180053e2a  sub     rsp, 88h
0x180053e31  mov     rax, cs:__security_cookie
0x180053e38  xor     rax, rsp
0x180053e3b  mov     [rbp+57h+var_48], rax
0x180053e3f  mov     r15, rdx
0x180053e42  mov     r14, rcx
0x180053e45  mov     [rbp+57h+var_70], rcx
0x180053e49  xor     ebx, ebx
0x180053e4b  mov     [rbp+57h+var_90], ebx
0x180053e4e  mov     [rbp+57h+string], rbx
0x180053e52  xor     ecx, ecx; string
0x180053e54  call    cs:__imp_WindowsDeleteString
0x180053e5a  mov     [rbp+57h+string], rbx
0x180053e5e  lea     ecx, [rbx+3Bh]
0x180053e61  lea     rdx, [rbp+57h+string]
0x180053e65  call    cs:__imp_GetUserLanguages
0x180053e6b  test    eax, eax
0x180053e6d  jns     short loc_180053E83
0x180053e6f  mov     [rbp+57h+pExceptionObject], eax
0x180053e72  lea     rdx, _TI1J; pThrowInfo
0x180053e79  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180053e7d  call    _CxxThrowException_0
0x180053e83  xor     edx, edx; length
0x180053e85  mov     rcx, [rbp+57h+string]; string
0x180053e89  call    cs:__imp_WindowsGetStringRawBuffer
0x180053e8f  mov     rdx, rax
0x180053e92  lea     rcx, [rbp+57h+var_68]
0x180053e96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180053e9b  nop
0x180053e9c  mov     rdx, rax
0x180053e9f  lea     rcx, [rbp+57h+var_88]
0x180053ea3  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(std::wstring const &,ushort)
0x180053ea8  nop
0x180053ea9  lea     rcx, [rbp+57h+var_68]
0x180053ead  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180053eb2  nop
0x180053eb3  mov     [r14], rbx
0x180053eb6  mov     [r14+8], rbx
0x180053eba  mov     [r14+10h], rbx
0x180053ebe  mov     [rbp+57h+var_90], 7
0x180053ec5  mov     rsi, [rbp+57h+var_80]
0x180053ec9  mov     rdi, [rbp+57h+var_88]
0x180053ecd  cmp     qword ptr [r15+18h], 7
0x180053ed2  jbe     short loc_180053ED9
0x180053ed4  mov     r13, [r15]
0x180053ed7  jmp     short loc_180053EDC
0x180053ed9  mov     r13, r15
0x180053edc  mov     r12d, 4Ah ; 'J'
0x180053ee2  mov     rbx, rsi
0x180053ee5  cmp     rdi, rsi
0x180053ee8  jz      short loc_180053F21
0x180053eea  mov     [rbp+57h+pExceptionObject], r12d
0x180053eee  cmp     qword ptr [rdi+18h], 7
0x180053ef3  jbe     short loc_180053EFA
0x180053ef5  mov     rdx, [rdi]
0x180053ef8  jmp     short loc_180053EFD
0x180053efa  mov     rdx, rdi; PCWSTR
0x180053efd  mov     rcx, r13; sourceString
0x180053f00  call    ?GetLanguagesClosenessScore@@YAHQEBG0@Z; GetLanguagesClosenessScore(ushort const * const,ushort const * const)
0x180053f05  mov     ecx, eax
0x180053f07  cmp     eax, r12d
0x180053f0a  cmovg   r12d, eax
0x180053f0e  mov     rax, rdi
0x180053f11  cmp     ecx, [rbp+57h+pExceptionObject]
0x180053f14  cmovle  rax, rbx
0x180053f18  mov     rbx, rax
0x180053f1b  add     rdi, 20h ; ' '
0x180053f1f  jmp     short loc_180053EE5
0x180053f21  cmp     rbx, [rbp+57h+var_80]
0x180053f25  jz      short loc_180053F76
0x180053f27  mov     rdx, [r14+8]
0x180053f2b  mov     rcx, r14
0x180053f2e  cmp     rdx, [r14+10h]
0x180053f32  jz      short loc_180053F3E
0x180053f34  mov     rdx, rbx
0x180053f37  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x180053f3c  jmp     short loc_180053F46
0x180053f3e  mov     r8, rbx
0x180053f41  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180053f46  lea     rcx, [rbx+20h]
0x180053f4a  mov     r8, rbx
0x180053f4d  mov     rdx, [rbp+57h+var_80]
0x180053f51  call    ??$_Move_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00@Z; std::_Move_unchecked<std::wstring *,std::wstring *>(std::wstring *,std::wstring *,std::wstring *)
0x180053f56  mov     rcx, [rbp+57h+var_80]
0x180053f5a  add     rcx, 0FFFFFFFFFFFFFFE0h; void *
0x180053f5e  xor     edx, edx
0x180053f60  call    ??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x180053f65  mov     rsi, [rbp+57h+var_80]
0x180053f69  sub     rsi, 20h ; ' '
0x180053f6d  mov     [rbp+57h+var_80], rsi
0x180053f71  jmp     loc_180053EC9
0x180053f76  lea     rcx, [rbp+57h+var_88]
0x180053f7a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180053f7f  nop
0x180053f80  lea     rcx, [rbp+57h+string]; this
0x180053f84  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180053f89  mov     rax, r14
0x180053f8c  mov     rcx, [rbp+57h+var_48]
0x180053f90  xor     rcx, rsp; StackCookie
0x180053f93  call    __security_check_cookie
0x180053f98  add     rsp, 88h
0x180053f9f  pop     r15
0x180053fa1  pop     r14
0x180053fa3  pop     r13
0x180053fa5  pop     r12
0x180053fa7  pop     rdi
0x180053fa8  pop     rsi
0x180053fa9  pop     rbx
0x180053faa  pop     rbp
0x180053fab  retn
```
