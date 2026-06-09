# IsWinDirHost(ushort const *,bool *)

- ea: `0x18001aeb0`
- end: `0x18001b03e`
- name: `?IsWinDirHost@@YAJPEBGPEA_N@Z`
- size: `398`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001b268`

## callees

- `0x1800049a4`
- `0x18000d92c`
- `0x18001aeb0`
- `0x180037344`
- `0x18004a350`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001af1c`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001af1c`
- `KERNEL32!GetLastError` at `0x18001af26`
- `KERNEL32!GetLastError` at `0x18001af68`
- `KERNEL32!GetLastError` at `0x18001af26`
- `KERNEL32!GetLastError` at `0x18001af68`

## string_xrefs

- `0x18001af4e`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001aff8`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall IsWinDirHost(const unsigned __int16 *a1, bool *a2)
{
  signed int result; // eax
  int v5; // ebx
  bool v6; // al
  signed int LastError; // eax
  bool v8; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( !a2 )
    return -2147024809;
  v8 = 0;
  if ( !a1 )
  {
    v5 = 0;
    v6 = 1;
    goto LABEL_13;
  }
  memset_0(Buffer, 0, 0x20Au);
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v10,
      (__int64)Buffer);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v9,
      (__int64)a1);
    v5 = PushButtonReset::Path::AreEqual(&v9, v10, &v8);
    ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v10[0] - 24LL));
    if ( v5 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "IsWinDirHost",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1302,
        L"Failed to check if input [%s] is the host Windows dir [%s]",
        a1,
        Buffer);
      return v5;
    }
    v6 = v8;
LABEL_13:
    *a2 = v6;
    return v5;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)LastError,
    "IsWinDirHost",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
    1296,
    L"Failed to get system Windows dir");
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001aeb0  mov     [rsp-8+arg_10], rbx
0x18001aeb5  push    rbp
0x18001aeb6  push    rsi
0x18001aeb7  push    rdi
0x18001aeb8  lea     rbp, [rsp-180h]
0x18001aec0  sub     rsp, 280h
0x18001aec7  mov     rax, cs:__security_cookie
0x18001aece  xor     rax, rsp
0x18001aed1  mov     [rbp+190h+var_20], rax
0x18001aed8  mov     rsi, rdx
0x18001aedb  mov     rdi, rcx
0x18001aede  test    rdx, rdx
0x18001aee1  jnz     short loc_18001AEED
0x18001aee3  mov     eax, 80070057h
0x18001aee8  jmp     loc_18001B01C
0x18001aeed  mov     [rsp+290h+var_250], 0
0x18001aef2  test    rdi, rdi
0x18001aef5  jnz     short loc_18001AF00
0x18001aef7  xor     ebx, ebx
0x18001aef9  mov     al, 1
0x18001aefb  jmp     loc_18001B018
0x18001af00  xor     edx, edx; Val
0x18001af02  mov     r8d, 20Ah; Size
0x18001af08  lea     rcx, [rsp+290h+Buffer]; void *
0x18001af0d  call    memset_0
0x18001af12  mov     edx, 104h; uSize
0x18001af17  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x18001af1c  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001af22  test    eax, eax
0x18001af24  jnz     short loc_18001AF80
0x18001af26  call    cs:__imp_GetLastError
0x18001af2c  mov     ebx, 80070000h
0x18001af31  test    eax, eax
0x18001af33  jle     short loc_18001AF3A
0x18001af35  movzx   eax, ax
0x18001af38  or      eax, ebx
0x18001af3a  lea     rcx, aFailedToGetSys; "Failed to get system Windows dir"
0x18001af41  mov     [rsp+290h+var_268], rcx
0x18001af46  mov     [rsp+290h+var_270], 510h
0x18001af4e  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001af55  lea     r8, aIswindirhost; "IsWinDirHost"
0x18001af5c  mov     edx, eax
0x18001af5e  mov     ecx, 2
0x18001af63  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001af68  call    cs:__imp_GetLastError
0x18001af6e  test    eax, eax
0x18001af70  jle     loc_18001B01C
0x18001af76  movzx   eax, ax
0x18001af79  or      eax, ebx
0x18001af7b  jmp     loc_18001B01C
0x18001af80  lea     rdx, [rsp+290h+Buffer]
0x18001af85  lea     rcx, [rsp+290h+var_240]
0x18001af8a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001af8f  nop
0x18001af90  mov     rdx, rdi
0x18001af93  lea     rcx, [rsp+290h+var_248]
0x18001af98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001af9d  nop
0x18001af9e  lea     r8, [rsp+290h+var_250]
0x18001afa3  lea     rdx, [rsp+290h+var_240]
0x18001afa8  lea     rcx, [rsp+290h+var_248]
0x18001afad  call    ?AreEqual@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_N@Z; PushButtonReset::Path::AreEqual(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)
0x18001afb2  mov     ebx, eax
0x18001afb4  mov     rcx, [rsp+290h+var_248]
0x18001afb9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001afbd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001afc2  nop
0x18001afc3  mov     rcx, [rsp+290h+var_240]
0x18001afc8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001afcc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001afd1  test    ebx, ebx
0x18001afd3  jns     short loc_18001B014
0x18001afd5  lea     rax, [rsp+290h+Buffer]
0x18001afda  mov     [rsp+290h+var_258], rax
0x18001afdf  mov     [rsp+290h+var_260], rdi
0x18001afe4  lea     rax, aFailedToCheckI_1; "Failed to check if input [%s] is the ho"...
0x18001afeb  mov     [rsp+290h+var_268], rax
0x18001aff0  mov     [rsp+290h+var_270], 516h
0x18001aff8  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001afff  lea     r8, aIswindirhost; "IsWinDirHost"
0x18001b006  mov     edx, ebx
0x18001b008  mov     ecx, 2
0x18001b00d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b012  jmp     short loc_18001B01A
0x18001b014  mov     al, [rsp+290h+var_250]
0x18001b018  mov     [rsi], al
0x18001b01a  mov     eax, ebx
0x18001b01c  mov     rcx, [rbp+190h+var_20]
0x18001b023  xor     rcx, rsp; StackCookie
0x18001b026  call    __security_check_cookie
0x18001b02b  mov     rbx, [rsp+290h+arg_10]
0x18001b033  add     rsp, 280h
0x18001b03a  pop     rdi
0x18001b03b  pop     rsi
0x18001b03c  pop     rbp
0x18001b03d  retn
```
