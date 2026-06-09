# SetSddlOnLogDirectory(ITmInstance *,ushort *)

- ea: `0x180015f84`
- end: `0x1800161d1`
- name: `?SetSddlOnLogDirectory@@YAJPEAUITmInstance@@PEAG@Z`
- size: `589`
- prototype: `int(struct ITmInstance *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001664c`
- `0x180074200`
- `0x18007544c`

## callees

- `0x180003cf0`
- `0x180006054`
- `0x180015f84`
- `0x18001ce20`
- `0x18007168c`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016177`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160c1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800160b7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800160b7`
- `msvcrt!_wcsnicmp` at `0x1800160fa`
- `msvcrt!_wcsnicmp` at `0x1800160fa`

## string_xrefs

- `0x1800160d6`: `GetFullPathNameW(wszLogPath) failed`
- `0x180016010`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x18001608f`: `GetDtcLogPath failed`
- `0x180016017`: `SetSddlOnLogDirectory`
- `0x18001605e`: `StringCchCopyW failed`
- `0x180016123`: `TmInstance->GetNonDefaultLogPathSddl failed`
- `0x180016147`: `SetObjectSddl(wszLogPath) failed`

## pseudocode

```c
__int64 __fastcall SetSddlOnLogDirectory(struct ITmInstance *a1, unsigned __int16 *a2)
{
  signed int v4; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  signed int LastError; // eax
  const wchar_t *DefaultLogPath; // rax
  __int64 v10; // [rsp+28h] [rbp-D8h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[526]; // [rsp+52h] [rbp-AEh] BYREF
  WCHAR Buffer; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v16[526]; // [rsp+262h] [rbp+162h] BYREF

  FileName = 0;
  memset_0(v14, 0, 0x208u);
  Buffer = 0;
  memset_0(v16, 0, 0x208u);
  FilePart = 0;
  pv = 0;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    286,
    L"SetSddlOnLogDirectory",
    0,
    L"In");
  if ( a2 )
  {
    v4 = StringCchCopyW(&FileName, 0x105u, a2);
    if ( v4 < 0 )
    {
      v5 = L"StringCchCopyW failed";
      v6 = 292;
LABEL_15:
      LODWORD(v10) = v4;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
        v6,
        L"SetSddlOnLogDirectory",
        v10,
        v5);
      goto LABEL_16;
    }
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(struct ITmInstance *, __int64, WCHAR *))(*(_QWORD *)a1 + 96LL))(a1, 261, &FileName);
    if ( v4 < 0 )
    {
      v5 = L"GetDtcLogPath failed";
      v6 = 302;
      goto LABEL_15;
    }
  }
  if ( !GetFullPathNameW(&FileName, 0x105u, &Buffer, &FilePart) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = L"GetFullPathNameW(wszLogPath) failed";
    v6 = 309;
    goto LABEL_15;
  }
  DefaultLogPath = GetDefaultLogPath();
  if ( _wcsnicmp(&Buffer, DefaultLogPath, 0x105u) )
  {
    v4 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *))(*(_QWORD *)a1 + 80LL))(a1, &pv);
    if ( v4 < 0 )
    {
      v5 = L"TmInstance->GetNonDefaultLogPathSddl failed";
      v6 = 318;
      goto LABEL_15;
    }
    v4 = SetObjectSddl(&FileName, SE_FILE_OBJECT, (LPCWSTR)pv);
    if ( v4 < 0 )
    {
      v5 = L"SetObjectSddl(wszLogPath) failed";
      v6 = 325;
      goto LABEL_15;
    }
  }
LABEL_16:
  CoTaskMemFree(pv);
  LODWORD(v10) = v4;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    331,
    L"SetSddlOnLogDirectory",
    v10,
    L"Out");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015f84  mov     [rsp-8+arg_10], rbx
0x180015f89  push    rbp
0x180015f8a  push    rsi
0x180015f8b  push    r12
0x180015f8d  push    r13
0x180015f8f  push    r15
0x180015f91  lea     rbp, [rsp-380h]
0x180015f99  sub     rsp, 480h
0x180015fa0  mov     rax, cs:__security_cookie
0x180015fa7  xor     rax, rsp
0x180015faa  mov     [rbp+3A0h+var_30], rax
0x180015fb1  mov     rbx, rdx
0x180015fb4  mov     rsi, rcx
0x180015fb7  xor     eax, eax
0x180015fb9  lea     rcx, [rsp+4A0h+var_44E]; void *
0x180015fbe  xor     edx, edx; Val
0x180015fc0  mov     [rsp+4A0h+FileName], ax
0x180015fc5  mov     r8d, 208h; Size
0x180015fcb  call    memset_0
0x180015fd0  xor     eax, eax
0x180015fd2  lea     rcx, [rbp+3A0h+var_23E]; void *
0x180015fd9  xor     edx, edx; Val
0x180015fdb  mov     [rbp+3A0h+Buffer], ax
0x180015fe2  mov     r8d, 208h; Size
0x180015fe8  call    memset_0
0x180015fed  mov     edx, 6
0x180015ff2  mov     [rsp+4A0h+FilePart], 0
0x180015ffb  lea     rax, aIn_0; "In"
0x180016002  mov     [rsp+4A0h+pv], 0
0x18001600b  mov     [rsp+4A0h+var_470], rax
0x180016010  lea     r15, aComComplusDtcS_12; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x180016017  lea     r13, aSetsddlonlogdi; "SetSddlOnLogDirectory"
0x18001601e  mov     [rsp+4A0h+var_478], 0
0x180016027  lea     r12d, [rdx+1]
0x18001602b  mov     [rsp+4A0h+var_480], r13
0x180016030  mov     ecx, r12d
0x180016033  mov     r9d, 11Eh
0x180016039  mov     r8, r15
0x18001603c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016041  test    rbx, rbx
0x180016044  jz      short loc_180016070
0x180016046  mov     r8, rbx; unsigned __int16 *
0x180016049  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18001604e  mov     edx, 105h; unsigned __int64
0x180016053  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016058  mov     ebx, eax
0x18001605a  test    eax, eax
0x18001605c  jns     short loc_1800160A1
0x18001605e  lea     rax, aStringcchcopyw; "StringCchCopyW failed"
0x180016065  mov     r9d, 124h
0x18001606b  jmp     loc_180016154
0x180016070  mov     rax, [rsi]
0x180016073  lea     r8, [rsp+4A0h+FileName]
0x180016078  mov     edx, 105h
0x18001607d  mov     rcx, rsi
0x180016080  mov     rax, [rax+60h]
0x180016084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016089  mov     ebx, eax
0x18001608b  test    eax, eax
0x18001608d  jns     short loc_1800160A1
0x18001608f  lea     rax, aGetdtclogpathF; "GetDtcLogPath failed"
0x180016096  mov     r9d, 12Eh
0x18001609c  jmp     loc_180016154
0x1800160a1  lea     r9, [rsp+4A0h+FilePart]; lpFilePart
0x1800160a6  mov     edx, 105h; nBufferLength
0x1800160ab  lea     r8, [rbp+3A0h+Buffer]; lpBuffer
0x1800160b2  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x1800160b7  call    cs:__imp_GetFullPathNameW
0x1800160bd  test    eax, eax
0x1800160bf  jnz     short loc_1800160E5
0x1800160c1  call    cs:__imp_GetLastError
0x1800160c7  mov     ebx, eax
0x1800160c9  test    eax, eax
0x1800160cb  jle     short loc_1800160D6
0x1800160cd  movzx   ebx, ax
0x1800160d0  or      ebx, 80070000h
0x1800160d6  lea     rax, aGetfullpathnam; "GetFullPathNameW(wszLogPath) failed"
0x1800160dd  mov     r9d, 135h
0x1800160e3  jmp     short loc_180016154
0x1800160e5  call    ?GetDefaultLogPath@@YAPEAGXZ; GetDefaultLogPath(void)
0x1800160ea  mov     rdx, rax; String2
0x1800160ed  lea     rcx, [rbp+3A0h+Buffer]; String1
0x1800160f4  mov     r8d, 105h; MaxCount
0x1800160fa  call    cs:__imp__wcsnicmp
0x180016100  test    eax, eax
0x180016102  jz      short loc_180016172
0x180016104  mov     rax, [rsi]
0x180016107  lea     rdx, [rsp+4A0h+pv]
0x18001610c  mov     rcx, rsi
0x18001610f  mov     rax, [rax+50h]
0x180016113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016118  mov     ebx, eax
0x18001611a  mov     edx, 1; ObjectType
0x18001611f  test    eax, eax
0x180016121  jns     short loc_180016132
0x180016123  lea     rax, aTminstanceGetn; "TmInstance->GetNonDefaultLogPathSddl fa"...
0x18001612a  mov     r9d, 13Eh
0x180016130  jmp     short loc_180016159
0x180016132  mov     r8, [rsp+4A0h+pv]; StringSecurityDescriptor
0x180016137  lea     rcx, [rsp+4A0h+FileName]; pObjectName
0x18001613c  call    ?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z; SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x180016141  mov     ebx, eax
0x180016143  test    eax, eax
0x180016145  jns     short loc_180016172
0x180016147  lea     rax, aSetobjectsddlW_4; "SetObjectSddl(wszLogPath) failed"
0x18001614e  mov     r9d, 145h
0x180016154  mov     edx, 1
0x180016159  mov     [rsp+4A0h+var_470], rax
0x18001615e  mov     r8, r15
0x180016161  mov     dword ptr [rsp+4A0h+var_478], ebx
0x180016165  mov     ecx, r12d
0x180016168  mov     [rsp+4A0h+var_480], r13
0x18001616d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180016172  mov     rcx, [rsp+4A0h+pv]; pv
0x180016177  call    cs:__imp_CoTaskMemFree
0x18001617d  lea     rax, aOut; "Out"
0x180016184  mov     r9d, 14Bh
0x18001618a  mov     [rsp+4A0h+var_470], rax
0x18001618f  mov     r8, r15
0x180016192  mov     dword ptr [rsp+4A0h+var_478], ebx
0x180016196  mov     edx, 6
0x18001619b  mov     ecx, r12d
0x18001619e  mov     [rsp+4A0h+var_480], r13
0x1800161a3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800161a8  mov     eax, ebx
0x1800161aa  mov     rcx, [rbp+3A0h+var_30]
0x1800161b1  xor     rcx, rsp; StackCookie
0x1800161b4  call    __security_check_cookie
0x1800161b9  mov     rbx, [rsp+4A0h+arg_10]
0x1800161c1  add     rsp, 480h
0x1800161c8  pop     r15
0x1800161ca  pop     r13
0x1800161cc  pop     r12
0x1800161ce  pop     rsi
0x1800161cf  pop     rbp
0x1800161d0  retn
```
