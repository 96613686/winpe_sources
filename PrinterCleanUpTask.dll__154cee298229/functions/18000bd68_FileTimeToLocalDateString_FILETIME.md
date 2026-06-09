# FileTimeToLocalDateString(_FILETIME)

- ea: `0x18000bd68`
- end: `0x18000bec3`
- name: `?FileTimeToLocalDateString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64, FILETIME)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000d424`

## callees

- `0x180002020`
- `0x180009abc`
- `0x18000bd68`
- `0x18000f0d0`
- `0x18000f118`
- `0x18000ff2c`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000bddb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x18000bddb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000bdac`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000bdac`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18000be25`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18000be72`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18000be25`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18000be72`

## string_xrefs

- `0x18000bdba`: `printscan\print\shared\printercleanuptask\lib\util.h`
- `0x18000bde9`: `printscan\print\shared\printercleanuptask\lib\util.h`
- `0x18000be80`: `printscan\print\shared\printercleanuptask\lib\util.h`

## pseudocode

```c
__int64 __fastcall FileTimeToLocalDateString(__int64 a1, FILETIME a2)
{
  const char *v3; // r9
  const char *v4; // r9
  int DateFormat; // edi
  WCHAR *lpDateStr; // rax
  const char *v7; // r9
  FILETIME FileTime; // [rsp+48h] [rbp-38h] BYREF
  __int64 v10; // [rsp+50h] [rbp-30h]
  struct _SYSTEMTIME LocalTime; // [rsp+58h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v10 = a1;
  FileTime = a2;
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\util.h",
      v3);
  LocalTime = 0;
  if ( !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x23,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\util.h",
      v4);
  DateFormat = GetDateFormatEx(&LocaleName, 1u, &LocalTime, 0, 0, 0, 0);
  std::wstring::wstring(a1, DateFormat);
  lpDateStr = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( !GetDateFormatEx(&LocaleName, 1u, &LocalTime, 0, lpDateStr, *(_DWORD *)(a1 + 16), 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x28,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\util.h",
      v7);
  std::wstring::resize(a1, DateFormat - 1);
  return a1;
}

```

## disassembly

```asm
0x18000bd68  mov     [rsp-8+arg_10], rbx
0x18000bd6d  mov     [rsp-8+arg_18], rdi
0x18000bd72  push    rbp
0x18000bd73  mov     rbp, rsp
0x18000bd76  sub     rsp, 80h
0x18000bd7d  mov     rax, cs:__security_cookie
0x18000bd84  xor     rax, rsp
0x18000bd87  mov     [rbp+var_8], rax
0x18000bd8b  mov     rbx, rcx
0x18000bd8e  mov     [rbp+var_30], rcx
0x18000bd92  mov     qword ptr [rbp+FileTime.dwLowDateTime], rdx
0x18000bd96  mov     [rbp+var_40], 0
0x18000bd9d  xorps   xmm0, xmm0
0x18000bda0  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000bda4  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18000bda8  lea     rcx, [rbp+FileTime]; lpFileTime
0x18000bdac  call    cs:__imp_FileTimeToSystemTime
0x18000bdb2  mov     rcx, [rbp+8]; this
0x18000bdb6  test    eax, eax
0x18000bdb8  jnz     short loc_18000BDCA
0x18000bdba  lea     r8, aPrintscanPrint_3; "printscan\\print\\shared\\printercleanu"...
0x18000bdc1  lea     edx, [rax+20h]; void *
0x18000bdc4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000bdca  xorps   xmm0, xmm0
0x18000bdcd  movups  xmmword ptr [rbp+LocalTime.wYear], xmm0
0x18000bdd1  lea     r8, [rbp+LocalTime]; lpLocalTime
0x18000bdd5  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x18000bdd9  xor     ecx, ecx; lpTimeZoneInformation
0x18000bddb  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18000bde1  mov     rcx, [rbp+8]; this
0x18000bde5  test    eax, eax
0x18000bde7  jnz     short loc_18000BDF9
0x18000bde9  lea     r8, aPrintscanPrint_3; "printscan\\print\\shared\\printercleanu"...
0x18000bdf0  lea     edx, [rax+23h]; void *
0x18000bdf3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000bdf9  mov     [rsp+80h+lpCalendar], 0; lpCalendar
0x18000be02  mov     [rsp+80h+cchDate], 0; cchDate
0x18000be0a  mov     [rsp+80h+lpDateStr], 0; lpDateStr
0x18000be13  xor     r9d, r9d; lpFormat
0x18000be16  lea     r8, [rbp+LocalTime]; lpDate
0x18000be1a  lea     edx, [r9+1]; dwFlags
0x18000be1e  lea     rcx, LocaleName; lpLocaleName
0x18000be25  call    cs:__imp_GetDateFormatEx
0x18000be2b  movsxd  rdi, eax
0x18000be2e  mov     rdx, rdi
0x18000be31  mov     rcx, rbx
0x18000be34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18000be39  mov     [rbp+var_40], 1
0x18000be40  mov     rcx, rbx
0x18000be43  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000be48  mov     r8, rax
0x18000be4b  mov     [rsp+80h+lpCalendar], 0; lpCalendar
0x18000be54  mov     eax, [rbx+10h]
0x18000be57  mov     [rsp+80h+cchDate], eax; cchDate
0x18000be5b  mov     [rsp+80h+lpDateStr], r8; lpDateStr
0x18000be60  xor     r9d, r9d; lpFormat
0x18000be63  lea     r8, [rbp+LocalTime]; lpDate
0x18000be67  lea     edx, [r9+1]; dwFlags
0x18000be6b  lea     rcx, LocaleName; lpLocaleName
0x18000be72  call    cs:__imp_GetDateFormatEx
0x18000be78  test    eax, eax
0x18000be7a  jnz     short loc_18000BE90
0x18000be7c  mov     rcx, [rbp+8]; this
0x18000be80  lea     r8, aPrintscanPrint_3; "printscan\\print\\shared\\printercleanu"...
0x18000be87  lea     edx, [rax+28h]; void *
0x18000be8a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000be90  lea     ecx, [rdi-1]
0x18000be93  movsxd  rdx, ecx
0x18000be96  mov     rcx, rbx
0x18000be99  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000be9e  mov     rax, rbx
0x18000bea1  mov     rcx, [rbp+var_8]
0x18000bea5  xor     rcx, rsp; StackCookie
0x18000bea8  call    __security_check_cookie
0x18000bead  lea     r11, [rsp+80h+var_s0]
0x18000beb5  mov     rbx, [r11+20h]
0x18000beb9  mov     rdi, [r11+28h]
0x18000bebd  mov     rsp, r11
0x18000bec0  pop     rbp
0x18000bec1  retn
```
