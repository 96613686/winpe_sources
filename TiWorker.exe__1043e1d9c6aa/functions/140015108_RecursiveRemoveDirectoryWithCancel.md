# RecursiveRemoveDirectoryWithCancel

- ea: `0x140015108`
- end: `0x140015221`
- name: `RecursiveRemoveDirectoryWithCancel`
- size: `281`
- prototype: `__int64 __fastcall(__int64, wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000e728`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14000d910`
- `0x1400150ac`
- `0x140015108`

## string_xrefs

- `0x14001513c`: `No directory specified`
- `0x1400151c0`: `Failed to delete {}`

## pseudocode

```c
__int64 __fastcall RecursiveRemoveDirectoryWithCancel(__int64 a1, wchar_t *a2)
{
  unsigned int v2; // ebx
  int v3; // edx
  __int64 v4; // rdx
  int v6; // eax
  int v7; // edx
  int v8; // [rsp+20h] [rbp-38h]
  int v9[2]; // [rsp+30h] [rbp-28h] BYREF
  wchar_t *v10; // [rsp+38h] [rbp-20h] BYREF
  int v11; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v10 = a2;
  if ( !a2 )
  {
    v2 = -2147024809;
    v11 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No directory specified");
      *(_QWORD *)v9 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v9);
    }
    v4 = 619;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v2,
      v8);
    return v2;
  }
  v6 = RecursiveRemoveDirectoryEx(2u, a2);
  v2 = v6;
  if ( v6 < 0 )
  {
    v11 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to delete {}",
        (__int64)&v10);
      *(_QWORD *)v9 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)v9);
    }
    v4 = 624;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x140015108  push    rbx
0x14001510a  sub     rsp, 50h
0x14001510e  mov     rax, cs:__security_cookie
0x140015115  xor     rax, rsp
0x140015118  mov     [rsp+58h+var_10], rax
0x14001511d  mov     [rsp+58h+var_20], rdx
0x140015122  test    rdx, rdx
0x140015125  jnz     short loc_140015196
0x140015127  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001512e  mov     ebx, 80070057h
0x140015133  mov     [rsp+58h+var_18], ebx
0x140015137  test    rcx, rcx
0x14001513a  jz      short loc_140015179
0x14001513c  lea     r9, aNoDirectorySpe; "No directory specified"
0x140015143  lea     r8d, [rdx+3]
0x140015147  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001514c  lea     rcx, [rsp+58h+var_28]
0x140015151  mov     r8d, 3
0x140015157  mov     qword ptr [rsp+58h+var_38], rcx; int
0x14001515c  lea     rax, [rsp+58h+var_18]
0x140015161  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140015168  lea     r9, asc_140030534; ": {}"
0x14001516f  mov     qword ptr [rsp+58h+var_28], rax
0x140015174  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140015179  mov     edx, 26Bh; void *
0x14001517e  mov     rcx, [rsp+58h]; this
0x140015183  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001518a  mov     r9d, ebx; char *
0x14001518d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015192  mov     eax, ebx
0x140015194  jmp     short loc_14001520E
0x140015196  mov     r9, rcx
0x140015199  mov     ecx, 2; unsigned int
0x14001519e  call    RecursiveRemoveDirectoryEx
0x1400151a3  mov     ebx, eax
0x1400151a5  test    eax, eax
0x1400151a7  jns     short loc_14001520C
0x1400151a9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400151b0  mov     [rsp+58h+var_18], eax
0x1400151b4  test    rcx, rcx
0x1400151b7  jz      short loc_140015202
0x1400151b9  xor     edx, edx
0x1400151bb  lea     rax, [rsp+58h+var_20]
0x1400151c0  lea     r9, aFailedToDelete_2; "Failed to delete {}"
0x1400151c7  mov     qword ptr [rsp+58h+var_38], rax
0x1400151cc  lea     r8d, [rdx+3]
0x1400151d0  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400151d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400151dc  lea     rax, [rsp+58h+var_18]
0x1400151e1  mov     qword ptr [rsp+58h+var_28], rax
0x1400151e6  lea     r9, asc_140030534; ": {}"
0x1400151ed  lea     rax, [rsp+58h+var_28]
0x1400151f2  mov     r8d, 3
0x1400151f8  mov     qword ptr [rsp+58h+var_38], rax
0x1400151fd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140015202  mov     edx, 270h
0x140015207  jmp     loc_14001517E
0x14001520c  xor     eax, eax
0x14001520e  mov     rcx, [rsp+58h+var_10]
0x140015213  xor     rcx, rsp; StackCookie
0x140015216  call    __security_check_cookie
0x14001521b  add     rsp, 50h
0x14001521f  pop     rbx
0x140015220  retn
```
