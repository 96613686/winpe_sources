# AppxAllUserStore::BasicLogFile::GetDateTimeString(Common::StringBuffer &)

- ea: `0x180032eb4`
- end: `0x1800330c0`
- name: `?GetDateTimeString@BasicLogFile@AppxAllUserStore@@AEAAJAEAVStringBuffer@Common@@@Z`
- size: `524`
- prototype: `int(AppxAllUserStore::BasicLogFile *__hidden this, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017cd0`

## callees

- `0x180008db0`
- `0x18000ae80`
- `0x180018248`
- `0x18001a324`
- `0x18001a56c`
- `0x18001a6a0`
- `0x180032eb4`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlSystemTimeToLocalTime` at `0x180032f1f`
- `ntdll!RtlSystemTimeToLocalTime` at `0x180032f1f`
- `ntdll!NtQuerySystemTime` at `0x180032ee8`
- `ntdll!NtQuerySystemTime` at `0x180032ee8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180032f70`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180032f70`

## string_xrefs

- `0x180032ef9`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180032f3b`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180032f81`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x18003302d`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x18003307e`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`

## pseudocode

```c
int __fastcall AppxAllUserStore::BasicLogFile::GetDateTimeString(
        AppxAllUserStore::BasicLogFile *this,
        struct Common::StringBuffer *a2)
{
  NTSTATUS v3; // eax
  int v5; // ebx
  const char *v6; // r9
  int v7; // esi
  int v8; // [rsp+20h] [rbp-E0h]
  char *v9; // [rsp+28h] [rbp-D8h]
  __int64 v10; // [rsp+30h] [rbp-D0h]
  __int64 v11; // [rsp+38h] [rbp-C8h]
  __int64 v12; // [rsp+40h] [rbp-C0h]
  __int64 v13; // [rsp+48h] [rbp-B8h]
  union _LARGE_INTEGER LocalTime; // [rsp+60h] [rbp-A0h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+68h] [rbp-98h] BYREF
  FILETIME FileTime; // [rsp+70h] [rbp-90h] BYREF
  _SYSTEMTIME v17; // [rsp+78h] [rbp-88h] BYREF
  char v18[2]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  SystemTime.QuadPart = 0;
  v3 = NtQuerySystemTime(&SystemTime);
  if ( v3 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x63,
             (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
             (const char *)(unsigned int)v3,
             v8);
  LocalTime.QuadPart = 0;
  RtlSystemTimeToLocalTime(&SystemTime, &LocalTime);
  if ( !LocalTime.QuadPart )
  {
    v5 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)0x8000FFFFLL,
      v8);
    return v5;
  }
  FileTime = (FILETIME)LocalTime.QuadPart;
  v17 = 0;
  if ( !FileTimeToSystemTime(&FileTime, &v17) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6E,
             (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
             v6);
  v7 = StringCchPrintfW(
         (unsigned __int16 *)v18,
         0x104u,
         L"%04u/%02u/%02u %02u:%02u:%02u.%03u",
         v17.wYear,
         v17.wMonth,
         v17.wDay,
         v17.wHour,
         v17.wMinute,
         v17.wSecond,
         v17.wMilliseconds);
  if ( v7 >= 0 )
  {
    v5 = Common::StringBuffer::SetValueFromString(a2, (const unsigned __int16 *)v18);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
        (const char *)(unsigned int)v5,
        (int)"Date/time %ws.",
        v18);
      return v5;
    }
    return 0;
  }
  else
  {
    LODWORD(v13) = v17.wMinute;
    LODWORD(v12) = v17.wHour;
    LODWORD(v11) = v17.wDay;
    LODWORD(v10) = v17.wMonth;
    LODWORD(v9) = v17.wYear;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)(unsigned int)v7,
      (int)"%u %u %u %u %u %u %u.",
      v9,
      v10,
      v11,
      v12,
      v13,
      v17.wSecond,
      v17.wMilliseconds);
    return v7;
  }
}

```

## disassembly

```asm
0x180032eb4  push    rbp
0x180032eb6  push    rbx
0x180032eb7  push    rsi
0x180032eb8  push    rdi
0x180032eb9  lea     rbp, [rsp-1B8h]
0x180032ec1  sub     rsp, 2B8h
0x180032ec8  mov     rax, cs:__security_cookie
0x180032ecf  xor     rax, rsp
0x180032ed2  mov     [rbp+1D0h+var_30], rax
0x180032ed9  xor     edi, edi
0x180032edb  lea     rcx, [rsp+2D0h+SystemTime]; SystemTime
0x180032ee0  mov     qword ptr [rsp+2D0h+SystemTime], rdi
0x180032ee5  mov     rbx, rdx
0x180032ee8  call    cs:__imp_NtQuerySystemTime
0x180032eee  test    eax, eax
0x180032ef0  jns     short loc_180032F10
0x180032ef2  mov     rcx, [rbp+1D8h]; this
0x180032ef9  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180032f00  mov     r9d, eax; char *
0x180032f03  lea     edx, [rdi+63h]; void *
0x180032f06  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180032f0b  jmp     loc_1800330A5
0x180032f10  lea     rdx, [rsp+2D0h+LocalTime]; LocalTime
0x180032f15  mov     qword ptr [rsp+2D0h+LocalTime], rdi
0x180032f1a  lea     rcx, [rsp+2D0h+SystemTime]; SystemTime
0x180032f1f  call    cs:__imp_RtlSystemTimeToLocalTime
0x180032f25  mov     rax, qword ptr [rsp+2D0h+LocalTime]
0x180032f2a  test    eax, eax
0x180032f2c  jnz     short loc_180032F59
0x180032f2e  cmp     dword ptr [rsp+2D0h+LocalTime+4], edi
0x180032f32  jnz     short loc_180032F59
0x180032f34  mov     rcx, [rbp+1D8h]; this
0x180032f3b  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180032f42  mov     ebx, 8000FFFFh
0x180032f47  lea     edx, [rax+67h]; void *
0x180032f4a  mov     r9d, ebx; char *
0x180032f4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032f52  mov     eax, ebx
0x180032f54  jmp     loc_1800330A5
0x180032f59  xorps   xmm0, xmm0
0x180032f5c  mov     qword ptr [rsp+2D0h+FileTime.dwLowDateTime], rax
0x180032f61  lea     rdx, [rsp+2D0h+var_258]; lpSystemTime
0x180032f66  lea     rcx, [rsp+2D0h+FileTime]; lpFileTime
0x180032f6b  movups  xmmword ptr [rsp+2D0h+var_258.wYear], xmm0
0x180032f70  call    cs:__imp_FileTimeToSystemTime
0x180032f76  test    eax, eax
0x180032f78  jnz     short loc_180032F95
0x180032f7a  mov     rcx, [rbp+1D8h]; this
0x180032f81  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180032f88  lea     edx, [rax+6Eh]; void *
0x180032f8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032f90  jmp     loc_1800330A5
0x180032f95  movzx   ecx, [rbp+1D0h+var_258.wSecond]
0x180032f99  movzx   edx, [rbp+1D0h+var_258.wMinute]
0x180032f9d  movzx   r8d, [rbp+1D0h+var_258.wHour]
0x180032fa2  movzx   eax, [rbp+1D0h+var_258.wMilliseconds]
0x180032fa6  movzx   r10d, [rsp+2D0h+var_258.wDay]
0x180032fac  movzx   r11d, [rsp+2D0h+var_258.wMonth]
0x180032fb2  movzx   r9d, [rsp+2D0h+var_258.wYear]
0x180032fb8  mov     dword ptr [rsp+2D0h+var_288], eax
0x180032fbc  mov     dword ptr [rsp+2D0h+var_290], ecx
0x180032fc0  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x180032fc4  mov     dword ptr [rsp+2D0h+var_298], edx
0x180032fc8  mov     edx, 104h; unsigned __int64
0x180032fcd  mov     dword ptr [rsp+2D0h+var_2A0], r8d
0x180032fd2  lea     r8, a04u02u02u02u02; "%04u/%02u/%02u %02u:%02u:%02u.%03u"
0x180032fd9  mov     dword ptr [rsp+2D0h+var_2A8], r10d
0x180032fde  mov     [rsp+2D0h+var_2B0], r11d
0x180032fe3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032fe8  mov     esi, eax
0x180032fea  test    eax, eax
0x180032fec  jns     short loc_18003305C
0x180032fee  movzx   edx, [rbp+1D0h+var_258.wMilliseconds]
0x180032ff2  lea     rax, aUUUUUUU; "%u %u %u %u %u %u %u."
0x180032ff9  movzx   r8d, [rbp+1D0h+var_258.wSecond]
0x180032ffe  movzx   r9d, [rbp+1D0h+var_258.wMinute]
0x180033003  movzx   r10d, [rbp+1D0h+var_258.wHour]
0x180033008  movzx   r11d, [rsp+2D0h+var_258.wDay]
0x18003300e  movzx   ebx, [rsp+2D0h+var_258.wMonth]
0x180033013  movzx   edi, [rsp+2D0h+var_258.wYear]
0x180033018  mov     rcx, [rbp+1D8h]; this
0x18003301f  mov     [rsp+2D0h+var_278], edx
0x180033023  mov     edx, 76h ; 'v'; void *
0x180033028  mov     [rsp+2D0h+var_280], r8d
0x18003302d  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033034  mov     dword ptr [rsp+2D0h+var_288], r9d
0x180033039  mov     r9d, esi; char *
0x18003303c  mov     dword ptr [rsp+2D0h+var_290], r10d
0x180033041  mov     dword ptr [rsp+2D0h+var_298], r11d
0x180033046  mov     dword ptr [rsp+2D0h+var_2A0], ebx
0x18003304a  mov     dword ptr [rsp+2D0h+var_2A8], edi; char *
0x18003304e  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x180033053  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033058  mov     eax, esi
0x18003305a  jmp     short loc_1800330A5
0x18003305c  lea     rdx, [rbp+1D0h+var_240]; Src
0x180033060  mov     rcx, rbx; this
0x180033063  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180033068  mov     ebx, eax
0x18003306a  test    eax, eax
0x18003306c  jns     short loc_1800330A3
0x18003306e  mov     rcx, [rbp+1D8h]; this
0x180033075  lea     rax, [rbp+1D0h+var_240]
0x180033079  mov     [rsp+2D0h+var_2A8], rax; char *
0x18003307e  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033085  lea     rax, aDateTimeWs; "Date/time %ws."
0x18003308c  mov     r9d, ebx; char *
0x18003308f  mov     edx, 78h ; 'x'; void *
0x180033094  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x180033099  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003309e  jmp     loc_180032F52
0x1800330a3  xor     eax, eax
0x1800330a5  mov     rcx, [rbp+1D0h+var_30]
0x1800330ac  xor     rcx, rsp; StackCookie
0x1800330af  call    __security_check_cookie
0x1800330b4  add     rsp, 2B8h
0x1800330bb  pop     rdi
0x1800330bc  pop     rsi
0x1800330bd  pop     rbx
0x1800330be  pop     rbp
0x1800330bf  retn
```
