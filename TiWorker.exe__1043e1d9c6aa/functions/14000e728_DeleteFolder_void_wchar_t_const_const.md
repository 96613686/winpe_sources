# DeleteFolder(void * *,wchar_t const * const)

- ea: `0x14000e728`
- end: `0x14000e81d`
- name: `?DeleteFolder@@YAJPEAPEAXQEB_W@Z`
- size: `245`
- prototype: `__int64 __fastcall(void **, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000e550`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008ef4`
- `0x14000d910`
- `0x14000e728`
- `0x140014c94`
- `0x140015108`

## string_xrefs

- `0x14000e7bb`: `Failed to delete CBSTemp delete directory - '{}'.`

## pseudocode

```c
__int64 __fastcall DeleteFolder(void **a1, const wchar_t *a2)
{
  int v3; // edx
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // edx
  int v8; // [rsp+20h] [rbp-38h]
  int v9[2]; // [rsp+30h] [rbp-28h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v10 = a2;
  if ( !(unsigned __int8)DoesDirectoryExist(a2) )
  {
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        1,
        (unsigned int)"No content found - '{}'",
        (__int64)&v10);
    }
    return 0;
  }
  v5 = RecursiveRemoveDirectoryWithCancel(*a1, v10);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  v11 = v5;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to delete CBSTemp delete directory - '{}'.",
      (__int64)&v10);
    *(_QWORD *)v9 = &v11;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v7,
      3,
      (unsigned int)": {}",
      (__int64)v9);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x224,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
    (const char *)v6,
    v8);
  return v6;
}

```

## disassembly

```asm
0x14000e728  push    rbx
0x14000e72a  sub     rsp, 50h
0x14000e72e  mov     rax, cs:__security_cookie
0x14000e735  xor     rax, rsp
0x14000e738  mov     [rsp+58h+var_10], rax
0x14000e73d  mov     rbx, rcx
0x14000e740  mov     [rsp+58h+var_20], rdx
0x14000e745  mov     rcx, rdx
0x14000e748  call    DoesDirectoryExist
0x14000e74d  test    al, al
0x14000e74f  jnz     short loc_14000E791
0x14000e751  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000e758  test    rcx, rcx
0x14000e75b  jz      short loc_14000E77C
0x14000e75d  mov     r8d, 1
0x14000e763  lea     rax, [rsp+58h+var_20]
0x14000e768  mov     dl, r8b
0x14000e76b  mov     qword ptr [rsp+58h+var_38], rax
0x14000e770  lea     r9, aNoContentFound; "No content found - '{}'"
0x14000e777  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000e77c  xor     eax, eax
0x14000e77e  mov     rcx, [rsp+58h+var_10]
0x14000e783  xor     rcx, rsp; StackCookie
0x14000e786  call    __security_check_cookie
0x14000e78b  add     rsp, 50h
0x14000e78f  pop     rbx
0x14000e790  retn
0x14000e791  mov     rdx, [rsp+58h+var_20]
0x14000e796  mov     rcx, [rbx]
0x14000e799  call    RecursiveRemoveDirectoryWithCancel
0x14000e79e  mov     ebx, eax
0x14000e7a0  test    eax, eax
0x14000e7a2  jns     short loc_14000E77C
0x14000e7a4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000e7ab  mov     [rsp+58h+var_18], eax
0x14000e7af  test    rcx, rcx
0x14000e7b2  jz      short loc_14000E7FD
0x14000e7b4  xor     edx, edx
0x14000e7b6  lea     rax, [rsp+58h+var_20]
0x14000e7bb  lea     r9, aFailedToDelete_0; "Failed to delete CBSTemp delete directo"...
0x14000e7c2  mov     qword ptr [rsp+58h+var_38], rax
0x14000e7c7  lea     r8d, [rdx+3]
0x14000e7cb  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14000e7d0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000e7d7  lea     rax, [rsp+58h+var_18]
0x14000e7dc  mov     qword ptr [rsp+58h+var_28], rax
0x14000e7e1  lea     r9, asc_140030534; ": {}"
0x14000e7e8  lea     rax, [rsp+58h+var_28]
0x14000e7ed  mov     r8d, 3
0x14000e7f3  mov     qword ptr [rsp+58h+var_38], rax; int
0x14000e7f8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000e7fd  mov     rcx, [rsp+58h]; this
0x14000e802  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x14000e809  mov     r9d, ebx; char *
0x14000e80c  mov     edx, 224h; void *
0x14000e811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e816  mov     eax, ebx
0x14000e818  jmp     loc_14000E77E
```
