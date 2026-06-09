# OOBETaskSchedulerHelper::GetBoundaryTimeAfterDelay(uint,ushort * *)

- ea: `0x1800248dc`
- end: `0x180024a79`
- name: `?GetBoundaryTimeAfterDelay@OOBETaskSchedulerHelper@@YAJIPEAPEAG@Z`
- size: `413`
- prototype: `__int64 __fastcall(OOBETaskSchedulerHelper *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180029b68`

## callees

- `0x1800032b0`
- `0x180007710`
- `0x18000e2a0`
- `0x18000e2bc`
- `0x180018c78`
- `0x18001cb3c`
- `0x18001cf50`
- `0x1800248dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180024907`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180024907`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180024920`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180024920`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180024982`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180024982`

## string_xrefs

- `0x180024932`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x180024994`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x1800249ff`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`
- `0x180024a32`: `shell\OOBE\User\inc\OOBETaskSchedulerHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBETaskSchedulerHelper::GetBoundaryTimeAfterDelay(
        OOBETaskSchedulerHelper *this,
        __int64 *a2,
        unsigned __int16 **a3)
{
  BOOL v4; // eax
  const char *v5; // r9
  const char *v6; // r9
  int v7; // eax
  const char *v8; // r9
  __int64 v9; // rax
  const char *v10; // r9
  __int64 result; // rax
  int wMonth; // [rsp+20h] [rbp-88h]
  struct _FILETIME FileTime; // [rsp+50h] [rbp-58h] BYREF
  __int64 v14; // [rsp+58h] [rbp-50h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-48h] BYREF
  unsigned __int16 v16[20]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  FileTime = 0;
  v4 = SystemTimeToFileTime(&SystemTime, &FileTime);
  try
  {
    if ( !v4 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x31,
        (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
        v5);
    v14 = *(_QWORD *)&FileTime + 6048000000000LL;
    *(_QWORD *)&FileTime += 6048000000000LL;
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3A,
        (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
        v6);
    wMonth = SystemTime.wMonth;
    v7 = StringCchPrintfW(v16, 0x14u, L"%04d-%02d-%02dT%02d:%02d:%02d", SystemTime.wYear);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
        (const char *)(unsigned int)v7,
        wMonth);
    wil::make_bstr_nothrow(&v14, v16);
    v9 = v14;
    if ( !v14 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x44,
        (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
        v8);
    v14 = 0;
    *a2 = v9;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x48,
                           (unsigned int)"shell\\OOBE\\User\\inc\\OOBETaskSchedulerHelper.h",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800248dc  push    rbx
0x1800248de  sub     rsp, 0A0h
0x1800248e5  mov     rax, cs:__security_cookie
0x1800248ec  xor     rax, rsp
0x1800248ef  mov     [rsp+0A8h+var_10], rax
0x1800248f7  mov     rbx, rdx
0x1800248fa  xorps   xmm0, xmm0
0x1800248fd  movups  xmmword ptr [rsp+0A8h+SystemTime.wYear], xmm0
0x180024902  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180024907  call    cs:__imp_GetLocalTime
0x18002490d  mov     qword ptr [rsp+0A8h+FileTime.dwLowDateTime], 0
0x180024916  lea     rdx, [rsp+0A8h+FileTime]; lpFileTime
0x18002491b  lea     rcx, [rsp+0A8h+SystemTime]; lpSystemTime
0x180024920  call    cs:__imp_SystemTimeToFileTime
0x180024926  mov     rcx, [rsp+0A8h]; this
0x18002492e  test    eax, eax
0x180024930  jnz     short loc_180024941
0x180024932  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180024939  lea     edx, [rax+31h]; void *
0x18002493c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180024941  mov     eax, [rsp+0A8h+FileTime.dwHighDateTime]
0x180024945  mov     dword ptr [rsp+0A8h+var_50+4], eax
0x180024949  mov     eax, [rsp+0A8h+FileTime.dwLowDateTime]
0x18002494d  mov     dword ptr [rsp+0A8h+var_50], eax
0x180024951  mov     rcx, 58028E44000h
0x18002495b  mov     rax, [rsp+0A8h+var_50]
0x180024960  add     rax, rcx
0x180024963  mov     [rsp+0A8h+var_50], rax
0x180024968  shr     rax, 20h
0x18002496c  mov     [rsp+0A8h+FileTime.dwHighDateTime], eax
0x180024970  mov     eax, dword ptr [rsp+0A8h+var_50]
0x180024974  mov     [rsp+0A8h+FileTime.dwLowDateTime], eax
0x180024978  lea     rdx, [rsp+0A8h+SystemTime]; lpSystemTime
0x18002497d  lea     rcx, [rsp+0A8h+FileTime]; lpFileTime
0x180024982  call    cs:__imp_FileTimeToSystemTime
0x180024988  mov     rcx, [rsp+0A8h]; this
0x180024990  test    eax, eax
0x180024992  jnz     short loc_1800249A3
0x180024994  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x18002499b  lea     edx, [rax+3Ah]; void *
0x18002499e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800249a3  movzx   eax, [rsp+0A8h+SystemTime.wSecond]
0x1800249a8  movzx   ecx, [rsp+0A8h+SystemTime.wMinute]
0x1800249ad  movzx   edx, [rsp+0A8h+SystemTime.wHour]
0x1800249b2  movzx   r8d, [rsp+0A8h+SystemTime.wDay]
0x1800249b8  movzx   r10d, [rsp+0A8h+SystemTime.wMonth]
0x1800249be  movzx   r9d, [rsp+0A8h+SystemTime.wYear]
0x1800249c4  mov     [rsp+0A8h+var_68], eax
0x1800249c8  mov     [rsp+0A8h+var_70], ecx
0x1800249cc  mov     [rsp+0A8h+var_78], edx
0x1800249d0  mov     [rsp+0A8h+var_80], r8d
0x1800249d5  mov     [rsp+0A8h+var_88], r10d; int
0x1800249da  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d"
0x1800249e1  mov     edx, 14h; unsigned __int64
0x1800249e6  lea     rcx, [rsp+0A8h+var_38]; unsigned __int16 *
0x1800249eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800249f0  mov     rcx, [rsp+0A8h]; this
0x1800249f8  test    eax, eax
0x1800249fa  jns     short loc_180024A10
0x1800249fc  mov     r9d, eax; char *
0x1800249ff  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180024a06  mov     edx, 42h ; 'B'; void *
0x180024a0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024a10  lea     rdx, [rsp+0A8h+var_38]
0x180024a15  lea     rcx, [rsp+0A8h+var_50]
0x180024a1a  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180024a1f  nop
0x180024a20  mov     rcx, [rsp+0A8h]; this
0x180024a28  mov     rax, [rsp+0A8h+var_50]
0x180024a2d  test    rax, rax
0x180024a30  jnz     short loc_180024A41
0x180024a32  lea     r8, aShellOobeUserI; "shell\\OOBE\\User\\inc\\OOBETaskSchedul"...
0x180024a39  lea     edx, [rax+44h]; void *
0x180024a3c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180024a41  mov     [rsp+0A8h+var_50], 0
0x180024a4a  mov     [rbx], rax
0x180024a4d  lea     rcx, [rsp+0A8h+var_50]
0x180024a52  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024a57  xor     eax, eax
0x180024a59  jmp     short loc_180024A5F
0x180024a5b  mov     eax, [rsp+0A8h+FileTime.dwLowDateTime]
0x180024a5f  mov     rcx, [rsp+0A8h+var_10]
0x180024a67  xor     rcx, rsp; StackCookie
0x180024a6a  call    __security_check_cookie
0x180024a6f  add     rsp, 0A0h
0x180024a76  pop     rbx
0x180024a77  retn
```
