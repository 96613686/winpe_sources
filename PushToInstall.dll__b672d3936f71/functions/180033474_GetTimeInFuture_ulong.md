# GetTimeInFuture(ulong)

- ea: `0x180033474`
- end: `0x180033519`
- name: `?GetTimeInFuture@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800338b4`

## callees

- `0x1800026b0`
- `0x180030a68`
- `0x180033474`
- `0x1800337e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003349f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003349f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800334d5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800334d5`

## string_xrefs

- `0x180033507`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`

## pseudocode

```c
BSTR *__fastcall GetTimeInFuture(BSTR *a1)
{
  const char *v2; // r9
  FILETIME FileTime; // [rsp+20h] [rbp-38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  FileTime = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 6048000000000LL);
  SystemTime = 0;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x25,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      v2);
  SystemTimeToBstr(a1, &SystemTime.wYear);
  return a1;
}

```

## disassembly

```asm
0x180033474  push    rbx
0x180033476  sub     rsp, 50h
0x18003347a  mov     rax, cs:__security_cookie
0x180033481  xor     rax, rsp
0x180033484  mov     [rsp+58h+var_10], rax
0x180033489  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], rcx
0x18003348e  mov     rbx, rcx
0x180033491  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180033496  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003349f  call    cs:__imp_GetSystemTimeAsFileTime
0x1800334a5  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x1800334aa  lea     rdx, [rsp+58h+SystemTime]; lpSystemTime
0x1800334af  mov     rcx, 58028E44000h
0x1800334b9  xorps   xmm0, xmm0
0x1800334bc  add     rax, rcx
0x1800334bf  lea     rcx, [rsp+58h+FileTime]; lpFileTime
0x1800334c4  mov     [rsp+58h+FileTime.dwLowDateTime], eax
0x1800334c8  shr     rax, 20h
0x1800334cc  mov     [rsp+58h+FileTime.dwHighDateTime], eax
0x1800334d0  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x1800334d5  call    cs:__imp_FileTimeToSystemTime
0x1800334db  test    eax, eax
0x1800334dd  jz      short loc_180033502
0x1800334df  lea     rdx, [rsp+58h+SystemTime]
0x1800334e4  mov     rcx, rbx
0x1800334e7  call    ?SystemTimeToBstr@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_SYSTEMTIME@@@Z; SystemTimeToBstr(_SYSTEMTIME &)
0x1800334ec  mov     rax, rbx
0x1800334ef  mov     rcx, [rsp+58h+var_10]
0x1800334f4  xor     rcx, rsp; StackCookie
0x1800334f7  call    __security_check_cookie
0x1800334fc  add     rsp, 50h
0x180033500  pop     rbx
0x180033501  retn
0x180033502  mov     rcx, [rsp+58h]; this
0x180033507  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003350e  mov     edx, 25h ; '%'; void *
0x180033513  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
