# SetStartingUserDisplayLanguageValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180019454`
- end: `0x1800194ed`
- name: `?SetStartingUserDisplayLanguageValue@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `153`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800190bc`

## callees

- `0x180008294`
- `0x180011ac4`
- `0x180019454`
- `0x18001d564`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180019498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180019498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001946c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001946c`
- `Bcp47Langs!GetStartingUserDisplayLanguage` at `0x180019480`
- `Bcp47Langs!GetStartingUserDisplayLanguage` at `0x180019480`
- `Bcp47Langs!SetStartingUserDisplayLanguage` at `0x1800194ad`
- `Bcp47Langs!SetStartingUserDisplayLanguage` at `0x1800194ad`

## string_xrefs

- `0x1800194c3`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 SetStartingUserDisplayLanguageValue()
{
  int StartingUserDisplayLanguage; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  StartingUserDisplayLanguage = GetStartingUserDisplayLanguage(&string);
  v1 = StartingUserDisplayLanguage;
  if ( StartingUserDisplayLanguage >= 0 )
  {
    if ( !WindowsIsStringEmpty(string)
      || (v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(),
          StartingUserDisplayLanguage = SetStartingUserDisplayLanguage(v3),
          v1 = StartingUserDisplayLanguage,
          StartingUserDisplayLanguage >= 0) )
    {
      v1 = 0;
      goto LABEL_8;
    }
    v2 = 587;
  }
  else
  {
    v2 = 584;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
    (const char *)(unsigned int)StartingUserDisplayLanguage,
    v5);
LABEL_8:
  Windows::Internal::String::~String(&string);
  return v1;
}

```

## disassembly

```asm
0x180019454  mov     [rsp+arg_0], rbx
0x180019459  push    rdi; int
0x18001945a  sub     rsp, 20h
0x18001945e  mov     rdi, rcx
0x180019461  mov     [rsp+28h+string], 0
0x18001946a  xor     ecx, ecx; string
0x18001946c  call    cs:__imp_WindowsDeleteString
0x180019472  lea     rcx, [rsp+28h+string]
0x180019477  mov     [rsp+28h+string], 0
0x180019480  call    cs:__imp_GetStartingUserDisplayLanguage
0x180019486  mov     ebx, eax
0x180019488  test    eax, eax
0x18001948a  jns     short loc_180019493
0x18001948c  mov     edx, 248h
0x180019491  jmp     short loc_1800194BE
0x180019493  mov     rcx, [rsp+28h+string]; string
0x180019498  call    cs:__imp_WindowsIsStringEmpty
0x18001949e  test    eax, eax
0x1800194a0  jz      short loc_1800194D4
0x1800194a2  mov     rcx, rdi
0x1800194a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800194aa  mov     rcx, rax
0x1800194ad  call    cs:__imp_SetStartingUserDisplayLanguage
0x1800194b3  mov     ebx, eax
0x1800194b5  test    eax, eax
0x1800194b7  jns     short loc_1800194D4
0x1800194b9  mov     edx, 24Bh; void *
0x1800194be  mov     rcx, [rsp+28h]; this
0x1800194c3  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800194ca  mov     r9d, eax; char *
0x1800194cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194d2  jmp     short loc_1800194D6
0x1800194d4  xor     ebx, ebx
0x1800194d6  lea     rcx, [rsp+28h+string]; this
0x1800194db  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800194e0  mov     eax, ebx
0x1800194e2  mov     rbx, [rsp+28h+arg_0]
0x1800194e7  add     rsp, 20h
0x1800194eb  pop     rdi
0x1800194ec  retn
```
