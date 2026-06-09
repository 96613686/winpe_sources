# Broker::TimeEvent::DueDateToUtcDueTime(_SYSTEMTIME const &,bool)

- ea: `0x18000a330`
- end: `0x18000a46e`
- name: `?DueDateToUtcDueTime@TimeEvent@Broker@@IEAA_JAEBU_SYSTEMTIME@@_N@Z`
- size: `318`
- prototype: `struct _FILETIME __fastcall(Broker::TimeEvent *this, const struct _SYSTEMTIME *, char)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009200`
- `0x1800169bc`
- `0x180016b40`
- `0x1800179fc`

## callees

- `0x180003800`
- `0x18000a330`
- `0x180011240`
- `0x18001181c`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a35a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a35a`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x18000a3f5`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x18000a3f5`

## pseudocode

```c
struct _FILETIME __fastcall Broker::TimeEvent::DueDateToUtcDueTime(
        Broker::TimeEvent *this,
        const struct _SYSTEMTIME *a2,
        char a3)
{
  _QWORD v5[3]; // [rsp+20h] [rbp-50h] BYREF
  int v6; // [rsp+38h] [rbp-38h]
  unsigned int v7; // [rsp+40h] [rbp-30h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-28h] BYREF
  int v9; // [rsp+60h] [rbp-10h]
  unsigned int v10; // [rsp+68h] [rbp-8h]
  struct _FILETIME FileTime; // [rsp+80h] [rbp+10h] BYREF
  FILETIME LocalFileTime; // [rsp+98h] [rbp+28h] BYREF

  FileTime = 0;
  LocalFileTime = 0;
  if ( !SystemTimeToFileTime(a2, &FileTime) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v5);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v7);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v5);
    v9 = v6;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v10 = v7;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  if ( a3 )
  {
    LocalFileTime = FileTime;
    if ( !LocalFileTimeToFileTime(&LocalFileTime, &FileTime) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v10);
      std::exception::exception((std::exception *)v5, (const struct std::exception *)pExceptionObject);
      v6 = v9;
      v5[0] = &Broker::Win32Error::`vftable';
      v7 = v10;
      throw (Broker::Win32Error *)v5;
    }
  }
  return FileTime;
}

```

## disassembly

```asm
0x18000a330  mov     [rsp-8+arg_8], rbx
0x18000a335  mov     qword ptr [rsp-8+FileTime.dwLowDateTime], rcx
0x18000a33a  push    rbp
0x18000a33b  mov     rbp, rsp
0x18000a33e  sub     rsp, 70h
0x18000a342  movzx   ebx, r8b
0x18000a346  mov     rax, rdx
0x18000a349  xor     ecx, ecx
0x18000a34b  mov     qword ptr [rbp+FileTime.dwLowDateTime], rcx
0x18000a34f  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], rcx
0x18000a353  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000a357  mov     rcx, rax; lpSystemTime
0x18000a35a  call    cs:__imp_SystemTimeToFileTime
0x18000a360  test    eax, eax
0x18000a362  jz      short loc_18000A37A
0x18000a364  test    bl, bl
0x18000a366  jnz     short loc_18000A3E5
0x18000a368  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x18000a36c  mov     rbx, [rsp+70h+arg_8]
0x18000a374  add     rsp, 70h
0x18000a378  pop     rbp
0x18000a379  retn
0x18000a37a  lea     rcx, [rbp+var_50]; this
0x18000a37e  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000a383  nop
0x18000a384  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a38b  test    byte ptr [rcx+1Ch], 40h
0x18000a38f  jz      short loc_18000A3B0
0x18000a391  cmp     byte ptr [rcx+19h], 2
0x18000a395  jb      short loc_18000A3B0
0x18000a397  mov     edx, 17h
0x18000a39c  mov     r9d, [rbp+var_30]
0x18000a3a0  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x18000a3a7  mov     rcx, [rcx+10h]
0x18000a3ab  call    WPP_SF_d
0x18000a3b0  lea     rdx, [rbp+var_50]; struct std::exception *
0x18000a3b4  lea     rcx, [rbp+pExceptionObject]; this
0x18000a3b8  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000a3bd  mov     eax, [rbp+var_38]
0x18000a3c0  mov     [rbp+var_10], eax
0x18000a3c3  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000a3ca  mov     [rbp+pExceptionObject], rax
0x18000a3ce  mov     eax, [rbp+var_30]
0x18000a3d1  mov     [rbp+var_8], eax
0x18000a3d4  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000a3db  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a3df  call    _CxxThrowException_0
0x18000a3e5  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x18000a3e9  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], rax
0x18000a3ed  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000a3f1  lea     rcx, [rbp+LocalFileTime]; lpLocalFileTime
0x18000a3f5  call    cs:__imp_LocalFileTimeToFileTime
0x18000a3fb  test    eax, eax
0x18000a3fd  jnz     loc_18000A368
0x18000a403  lea     rcx, [rbp+pExceptionObject]; this
0x18000a407  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000a40c  nop
0x18000a40d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a414  test    byte ptr [rcx+1Ch], 40h
0x18000a418  jz      short loc_18000A439
0x18000a41a  cmp     byte ptr [rcx+19h], 2
0x18000a41e  jb      short loc_18000A439
0x18000a420  mov     edx, 18h
0x18000a425  mov     r9d, [rbp+var_8]
0x18000a429  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x18000a430  mov     rcx, [rcx+10h]
0x18000a434  call    WPP_SF_d
0x18000a439  lea     rdx, [rbp+pExceptionObject]; struct std::exception *
0x18000a43d  lea     rcx, [rbp+var_50]; this
0x18000a441  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000a446  mov     eax, [rbp+var_10]
0x18000a449  mov     [rbp+var_38], eax
0x18000a44c  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000a453  mov     [rbp+var_50], rax
0x18000a457  mov     eax, [rbp+var_8]
0x18000a45a  mov     [rbp+var_30], eax
0x18000a45d  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000a464  lea     rcx, [rbp+var_50]; pExceptionObject
0x18000a468  call    _CxxThrowException_0
```
