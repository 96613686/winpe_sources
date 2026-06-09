# ShouldIncludeRegionNameIfAmbiguous(ushort const *)

- ea: `0x1800195b0`
- end: `0x180019801`
- name: `?ShouldIncludeRegionNameIfAmbiguous@@YA_NPEBG@Z`
- size: `593`
- prototype: `bool __fastcall(PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015030`

## callees

- `0x180002380`
- `0x18000f724`
- `0x18000fa14`
- `0x180011ac4`
- `0x1800195b0`
- `0x18001b4e4`
- `0x18001d564`
- `0x18001ddf4`
- `0x18001de84`
- `0x18001e9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800195f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800195f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800196db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800196db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019645`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019709`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019645`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019709`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800197ab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800197ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019658`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001971c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180019658`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001971c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019789`
- `Bcp47Langs!Bcp47GetNeutralForm` at `0x180019679`
- `Bcp47Langs!Bcp47GetNeutralForm` at `0x18001973d`
- `Bcp47Langs!Bcp47GetNeutralForm` at `0x180019679`
- `Bcp47Langs!Bcp47GetNeutralForm` at `0x18001973d`

## string_xrefs

- `0x18001974e`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180019763`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall ShouldIncludeRegionNameIfAmbiguous(PCWSTR sourceString)
{
  __int64 v2; // rdi
  __int64 v3; // r14
  __int64 v4; // rax
  const WCHAR *v5; // rsi
  unsigned __int64 v6; // rbx
  int NeutralForm; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v9; // rbx
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdi
  __int64 v13; // rsi
  const WCHAR *v14; // rax
  LPCWCH v15; // r8
  int v16; // eax
  int v17; // ecx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-99h]
  HSTRING v20; // [rsp+30h] [rbp-89h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v22[4]; // [rsp+40h] [rbp-79h] BYREF
  HSTRING string; // [rsp+60h] [rbp-59h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v25[32]; // [rsp+80h] [rbp-39h] BYREF
  HSTRING v26; // [rsp+A0h] [rbp-19h] BYREF
  HSTRING_HEADER v27; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  std::vector<bond::blob>::vector<bond::blob>(v22);
  v22[3] = &stru_180032FB8;
  AcquireSRWLockShared(&stru_180032FB8);
  v2 = qword_180032FA0;
  v3 = qword_180032FA8;
  while ( v2 != v3 )
  {
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v5 = (const WCHAR *)v4;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v4 + 2 * v6) );
    if ( v6 > 0xFFFFFFFF )
    {
      LODWORD(v6) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v5, v6, &hstringHeader, &string);
    v20 = 0;
    WindowsDeleteString(0);
    v20 = 0;
    NeutralForm = Bcp47GetNeutralForm(string, &v20);
    if ( NeutralForm < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)NeutralForm,
        bIgnoreCase);
    StringRawBuffer = WindowsGetStringRawBuffer(v20, 0);
    std::wstring::wstring((__int64)v25, (__int64)StringRawBuffer);
    std::vector<std::wstring>::push_back(v22, v25);
    std::wstring::_Tidy_deallocate(v25);
    Windows::Internal::String::~String(&v20);
    v2 += 32;
  }
  ReleaseSRWLockShared(&stru_180032FB8);
  v9 = -1;
  do
    ++v9;
  while ( sourceString[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    LODWORD(v9) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(sourceString, v9, &v27, &v26);
  v21 = 0;
  WindowsDeleteString(0);
  v21 = 0;
  v10 = Bcp47GetNeutralForm(v26, &v21);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
  v11 = 0;
  v12 = v22[0];
  v13 = v22[1];
  while ( v12 != v13 )
  {
    WindowsGetStringRawBuffer(v21, 0);
    v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v16 = CompareStringOrdinal(v14, -1, v15, -1, 1);
    v17 = v11 + 1;
    if ( v16 != 2 )
      v17 = v11;
    v11 = v17;
    v12 += 32;
  }
  Windows::Internal::String::~String(&v21);
  std::vector<std::wstring>::_Tidy(v22);
  return v11 > 1;
}

```

## disassembly

```asm
0x1800195b0  push    rbp
0x1800195b2  push    rbx
0x1800195b3  push    rsi
0x1800195b4  push    rdi
0x1800195b5  push    r12
0x1800195b7  push    r13
0x1800195b9  push    r14
0x1800195bb  push    r15
0x1800195bd  lea     rbp, [rsp-1Fh]
0x1800195c2  sub     rsp, 0D8h
0x1800195c9  mov     rax, cs:__security_cookie
0x1800195d0  xor     rax, rsp
0x1800195d3  mov     [rbp+57h+var_50], rax
0x1800195d7  mov     r15, rcx
0x1800195da  lea     rcx, [rbp+57h+var_D0]
0x1800195de  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x1800195e3  nop
0x1800195e4  lea     rax, stru_180032FB8
0x1800195eb  mov     [rbp+57h+var_B8], rax
0x1800195ef  mov     rcx, rax; SRWLock
0x1800195f2  call    cs:__imp_AcquireSRWLockShared
0x1800195f8  nop
0x1800195f9  mov     rdi, cs:qword_180032FA0
0x180019600  mov     r14, cs:qword_180032FA8
0x180019607  xor     r12d, r12d
0x18001960a  mov     r13d, 0FFFFFFFFh
0x180019610  jmp     loc_1800196CB
0x180019615  mov     rcx, rdi
0x180019618  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001961d  mov     rsi, rax
0x180019620  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019624  inc     rbx
0x180019627  cmp     [rax+rbx*2], r12w
0x18001962c  jnz     short loc_180019624
0x18001962e  cmp     rbx, r13
0x180019631  jbe     short loc_18001964B
0x180019633  mov     ebx, r13d
0x180019636  xor     r9d, r9d; lpArguments
0x180019639  xor     r8d, r8d; nNumberOfArguments
0x18001963c  lea     edx, [r9+1]; dwExceptionFlags
0x180019640  mov     ecx, 0C000000Dh; dwExceptionCode
0x180019645  call    cs:__imp_RaiseException
0x18001964b  lea     r9, [rbp+57h+string]; string
0x18001964f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180019653  mov     edx, ebx; length
0x180019655  mov     rcx, rsi; sourceString
0x180019658  call    cs:__imp_WindowsCreateStringReference
0x18001965e  mov     [rsp+110h+var_E0], r12
0x180019663  xor     ecx, ecx; string
0x180019665  call    cs:__imp_WindowsDeleteString
0x18001966b  mov     [rsp+110h+var_E0], r12
0x180019670  lea     rdx, [rsp+110h+var_E0]
0x180019675  mov     rcx, [rbp+57h+string]
0x180019679  call    cs:__imp_Bcp47GetNeutralForm
0x18001967f  mov     rcx, [rbp+5Fh]; this
0x180019683  test    eax, eax
0x180019685  js      loc_180019760
0x18001968b  xor     edx, edx; length
0x18001968d  mov     rcx, [rsp+110h+var_E0]; string
0x180019692  call    cs:__imp_WindowsGetStringRawBuffer
0x180019698  mov     rdx, rax
0x18001969b  lea     rcx, [rbp+57h+var_90]
0x18001969f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800196a4  nop
0x1800196a5  lea     rdx, [rbp+57h+var_90]
0x1800196a9  lea     rcx, [rbp+57h+var_D0]
0x1800196ad  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800196b2  nop
0x1800196b3  lea     rcx, [rbp+57h+var_90]
0x1800196b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196bc  nop
0x1800196bd  lea     rcx, [rsp+110h+var_E0]; this
0x1800196c2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800196c7  add     rdi, 20h ; ' '
0x1800196cb  cmp     rdi, r14
0x1800196ce  jnz     loc_180019615
0x1800196d4  lea     rcx, stru_180032FB8; SRWLock
0x1800196db  call    cs:__imp_ReleaseSRWLockShared
0x1800196e1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800196e5  mov     rbx, r14
0x1800196e8  inc     rbx
0x1800196eb  cmp     [r15+rbx*2], r12w
0x1800196f0  jnz     short loc_1800196E8
0x1800196f2  cmp     rbx, r13
0x1800196f5  jbe     short loc_18001970F
0x1800196f7  mov     ebx, r13d
0x1800196fa  xor     r9d, r9d; lpArguments
0x1800196fd  xor     r8d, r8d; nNumberOfArguments
0x180019700  lea     edx, [r9+1]; dwExceptionFlags
0x180019704  mov     ecx, 0C000000Dh; dwExceptionCode
0x180019709  call    cs:__imp_RaiseException
0x18001970f  lea     r9, [rbp+57h+var_70]; string
0x180019713  lea     r8, [rbp+57h+var_68]; hstringHeader
0x180019717  mov     edx, ebx; length
0x180019719  mov     rcx, r15; sourceString
0x18001971c  call    cs:__imp_WindowsCreateStringReference
0x180019722  mov     [rsp+110h+var_D8], r12
0x180019727  xor     ecx, ecx; string
0x180019729  call    cs:__imp_WindowsDeleteString
0x18001972f  mov     [rsp+110h+var_D8], r12
0x180019734  lea     rdx, [rsp+110h+var_D8]
0x180019739  mov     rcx, [rbp+57h+var_70]
0x18001973d  call    cs:__imp_Bcp47GetNeutralForm
0x180019743  mov     rcx, [rbp+5Fh]; this
0x180019747  test    eax, eax
0x180019749  jns     short loc_180019775
0x18001974b  mov     r9d, eax; char *
0x18001974e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180019755  mov     edx, 0D7h; void *
0x18001975a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019760  mov     r9d, eax; char *
0x180019763  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001976a  mov     edx, 0CDh; void *
0x18001976f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019775  mov     ebx, r12d
0x180019778  mov     rdi, [rbp+57h+var_D0]
0x18001977c  mov     rsi, [rbp+57h+var_C8]
0x180019780  jmp     short loc_1800197C0
0x180019782  xor     edx, edx; length
0x180019784  mov     rcx, [rsp+110h+var_D8]; string
0x180019789  call    cs:__imp_WindowsGetStringRawBuffer
0x18001978f  mov     r8, rax
0x180019792  mov     rcx, rdi
0x180019795  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001979a  mov     [rsp+110h+bIgnoreCase], 1; bIgnoreCase
0x1800197a2  mov     r9d, r14d; cchCount2
0x1800197a5  mov     edx, r14d; cchCount1
0x1800197a8  mov     rcx, rax; lpString1
0x1800197ab  call    cs:__imp_CompareStringOrdinal
0x1800197b1  lea     ecx, [rbx+1]
0x1800197b4  cmp     eax, 2
0x1800197b7  cmovnz  ecx, ebx
0x1800197ba  mov     ebx, ecx
0x1800197bc  add     rdi, 20h ; ' '
0x1800197c0  cmp     rdi, rsi
0x1800197c3  jnz     short loc_180019782
0x1800197c5  cmp     ebx, 1
0x1800197c8  setnle  bl
0x1800197cb  lea     rcx, [rsp+110h+var_D8]; this
0x1800197d0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800197d5  nop
0x1800197d6  lea     rcx, [rbp+57h+var_D0]
0x1800197da  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800197df  mov     al, bl
0x1800197e1  mov     rcx, [rbp+57h+var_50]
0x1800197e5  xor     rcx, rsp; StackCookie
0x1800197e8  call    __security_check_cookie
0x1800197ed  add     rsp, 0D8h
0x1800197f4  pop     r15
0x1800197f6  pop     r14
0x1800197f8  pop     r13
0x1800197fa  pop     r12
0x1800197fc  pop     rdi
0x1800197fd  pop     rsi
0x1800197fe  pop     rbx
0x1800197ff  pop     rbp
0x180019800  retn
```
