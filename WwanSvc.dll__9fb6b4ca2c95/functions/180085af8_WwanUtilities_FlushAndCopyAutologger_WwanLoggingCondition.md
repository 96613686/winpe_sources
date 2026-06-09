# WwanUtilities::FlushAndCopyAutologger(WwanLoggingCondition)

- ea: `0x180085af8`
- end: `0x180085d96`
- name: `?FlushAndCopyAutologger@WwanUtilities@@SAXW4WwanLoggingCondition@@@Z`
- size: `670`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002c7a8`
- `0x180062640`
- `0x18007b5a8`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x180085af8`
- `0x180085d9c`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085bd3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085d2a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180085c17`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180085c17`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180085c75`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180085cc2`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180085c75`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180085cc2`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180085d20`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180085d20`

## string_xrefs

- `0x180085b62`: `Entering FlushAndCopyAutologger with logging condition:%d`
- `0x180085bc2`: `WwanLogCopyProvComplete.etl`
- `0x180085b58`: `WwanUtilities::FlushAndCopyAutologger`
- `0x180085ba6`: `WwanLogCopyModemInitComplete.etl`
- `0x180085bb4`: `WwanLogCopyPowerStateWake.etl`
- `0x180085d03`: `Copying log file to new file: %ls`
- `0x180085d6a`: `FlushAndCopyAutologger finishing with status 0x%x`
- `0x180085d3b`: `Failed to copy autologger log file. Tried to copy file %ls to new file %ls. Error=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WwanUtilities::FlushAndCopyAutologger(unsigned int a1)
{
  DWORD LastError; // ebx
  const unsigned __int16 *v3; // r8
  __int64 v4; // rdx
  unsigned int AutoLoggerLogFileName; // eax
  __int64 v6; // rdi
  GUID v7; // xmm0
  ULONG v8; // eax
  const unsigned __int16 *v9; // r8
  TRACEHANDLE v10; // rcx
  unsigned int v11; // eax
  GUID pclsid; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v13[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR NewFileName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+460h] [rbp+360h] BYREF

  memset_0(ExistingFileName, 0, 0x208u);
  memset_0(v13, 0, 0x208u);
  memset_0(NewFileName, 0, 0x208u);
  pclsid = 0;
  WwanLog::Info(
    "WwanUtilities::FlushAndCopyAutologger",
    0,
    L"Entering FlushAndCopyAutologger with logging condition:%d",
    a1);
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v3 = L"WwanLogCopyPowerStateWake.etl";
      v4 = 30;
    }
    else
    {
      if ( a1 != 2 )
      {
        WwanLog::Error(
          "WwanUtilities::FlushAndCopyAutologger",
          0,
          L"WwanLoggingCondition parameter could not be matched to any expected value:%d",
          a1);
        LastError = 160;
        goto LABEL_24;
      }
      v3 = L"WwanLogCopyModemInitComplete.etl";
      v4 = 33;
    }
  }
  else
  {
    v3 = L"WwanLogCopyProvComplete.etl";
    v4 = 28;
  }
  _o_wcscpy_s(v13, v4, v3);
  AutoLoggerLogFileName = WwanUtilities::GetAutoLoggerLogFileName(L"Wifi.etl", ExistingFileName);
  LastError = AutoLoggerLogFileName;
  if ( AutoLoggerLogFileName )
  {
    WwanLog::Error(
      "WwanUtilities::FlushAndCopyAutologger",
      0,
      L"GetAutoLoggerLogFileName failed with error:0x%x",
      AutoLoggerLogFileName);
    goto LABEL_24;
  }
  CLSIDFromString(L"{76E684E4-194C-43B0-B890-8269646DE989}", &pclsid);
  v6 = WwanMemAlloc(0x1078u);
  memset_0((void *)(v6 + 4), 0, 0x1074u);
  *(_DWORD *)v6 = 4216;
  v7 = pclsid;
  *(_DWORD *)(v6 + 116) = 120;
  *(_DWORD *)(v6 + 112) = 2168;
  *(GUID *)(v6 + 24) = v7;
  WwanLog::Info("WwanUtilities::FlushAndCopyAutologger", 0, L"Trying to get handle of autologger session");
  v8 = ControlTraceW(0, L"WiFiSession", (PEVENT_TRACE_PROPERTIES)v6, 0);
  LastError = v8;
  if ( v8 )
  {
    v9 = L"Failed to query information about tracing session. Error: 0x%x";
  }
  else
  {
    v10 = *(_QWORD *)(v6 + 8);
    if ( !v10 )
    {
      WwanLog::Error(
        "WwanUtilities::FlushAndCopyAutologger",
        0,
        L"Invalid handle for tracing session. Unable to proceed");
      goto LABEL_22;
    }
    v8 = ControlTraceW(v10, 0, (PEVENT_TRACE_PROPERTIES)v6, 3u);
    LastError = v8;
    if ( !v8 )
    {
      v11 = WwanUtilities::GetAutoLoggerLogFileName(v13, NewFileName);
      LastError = v11;
      if ( v11 )
      {
        WwanLog::Error(
          "WwanUtilities::FlushAndCopyAutologger",
          0,
          L"GetAutoLoggerLogFileName failed with error:0x%x",
          v11);
      }
      else
      {
        WwanLog::Info("WwanUtilities::FlushAndCopyAutologger", 0, L"Copying log file to new file: %ls", NewFileName);
        if ( !CopyFileW(ExistingFileName, NewFileName, 0) )
        {
          LastError = GetLastError();
          WwanLog::Error(
            "WwanUtilities::FlushAndCopyAutologger",
            0,
            L"Failed to copy autologger log file. Tried to copy file %ls to new file %ls. Error=0x%x",
            ExistingFileName,
            NewFileName,
            LastError);
        }
      }
      goto LABEL_22;
    }
    v9 = L"Failed to buffers to log file. Error: 0x%x";
  }
  WwanLog::Error("WwanUtilities::FlushAndCopyAutologger", 0, v9, v8);
LABEL_22:
  if ( v6 )
    WwanMemFree(v6);
LABEL_24:
  WwanLog::Info(
    "WwanUtilities::FlushAndCopyAutologger",
    0,
    L"FlushAndCopyAutologger finishing with status 0x%x",
    LastError);
}

```

## disassembly

```asm
0x180085af8  push    rbp
0x180085afa  push    rbx
0x180085afb  push    rsi
0x180085afc  push    rdi
0x180085afd  lea     rbp, [rsp-588h]
0x180085b05  sub     rsp, 688h
0x180085b0c  mov     rax, cs:__security_cookie
0x180085b13  xor     rax, rsp
0x180085b16  mov     [rbp+5A0h+var_30], rax
0x180085b1d  mov     ebx, ecx
0x180085b1f  mov     edi, 208h
0x180085b24  mov     r8d, edi; Size
0x180085b27  lea     rcx, [rbp+5A0h+ExistingFileName]; void *
0x180085b2e  xor     edx, edx; Val
0x180085b30  call    memset_0
0x180085b35  mov     r8d, edi; Size
0x180085b38  lea     rcx, [rsp+6A0h+var_660]; void *
0x180085b3d  xor     edx, edx; Val
0x180085b3f  call    memset_0
0x180085b44  mov     r8d, edi; Size
0x180085b47  lea     rcx, [rbp+5A0h+NewFileName]; void *
0x180085b4e  xor     edx, edx; Val
0x180085b50  call    memset_0
0x180085b55  xorps   xmm0, xmm0
0x180085b58  lea     rsi, aWwanutilitiesF; "WwanUtilities::FlushAndCopyAutologger"
0x180085b5f  mov     rcx, rsi; char *
0x180085b62  lea     r8, aEnteringFlusha; "Entering FlushAndCopyAutologger with lo"...
0x180085b69  mov     r9d, ebx
0x180085b6c  xor     edx, edx; struct _GUID *
0x180085b6e  movups  xmmword ptr [rsp+6A0h+pclsid.Data1], xmm0
0x180085b73  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180085b78  mov     ecx, ebx
0x180085b7a  test    ebx, ebx
0x180085b7c  jz      short loc_180085BC2
0x180085b7e  sub     ecx, 1
0x180085b81  jz      short loc_180085BB4
0x180085b83  cmp     ecx, 1
0x180085b86  jz      short loc_180085BA6
0x180085b88  mov     r9d, ebx
0x180085b8b  lea     r8, aWwanloggingcon; "WwanLoggingCondition parameter could no"...
0x180085b92  xor     edx, edx; struct _GUID *
0x180085b94  mov     rcx, rsi; char *
0x180085b97  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180085b9c  mov     ebx, 0A0h
0x180085ba1  jmp     loc_180085D67
0x180085ba6  lea     r8, aWwanlogcopymod; "WwanLogCopyModemInitComplete.etl"
0x180085bad  mov     edx, 21h ; '!'
0x180085bb2  jmp     short loc_180085BCE
0x180085bb4  lea     r8, aWwanlogcopypow; "WwanLogCopyPowerStateWake.etl"
0x180085bbb  mov     edx, 1Eh
0x180085bc0  jmp     short loc_180085BCE
0x180085bc2  lea     r8, aWwanlogcopypro; "WwanLogCopyProvComplete.etl"
0x180085bc9  mov     edx, 1Ch
0x180085bce  lea     rcx, [rsp+6A0h+var_660]
0x180085bd3  call    cs:__imp__o_wcscpy_s
0x180085bd9  lea     rdx, [rbp+5A0h+ExistingFileName]; unsigned __int16 *
0x180085be0  lea     rcx, aWifiEtl; "Wifi.etl"
0x180085be7  call    ?GetAutoLoggerLogFileName@WwanUtilities@@CAKPEBGPEAG@Z; WwanUtilities::GetAutoLoggerLogFileName(ushort const *,ushort *)
0x180085bec  mov     ebx, eax
0x180085bee  test    eax, eax
0x180085bf0  jz      short loc_180085C0B
0x180085bf2  mov     r9d, eax
0x180085bf5  lea     r8, aGetautologgerl; "GetAutoLoggerLogFileName failed with er"...
0x180085bfc  xor     edx, edx; struct _GUID *
0x180085bfe  mov     rcx, rsi; char *
0x180085c01  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180085c06  jmp     loc_180085D67
0x180085c0b  lea     rdx, [rsp+6A0h+pclsid]; pclsid
0x180085c10  lea     rcx, sz; "{76E684E4-194C-43B0-B890-8269646DE989}"
0x180085c17  call    cs:__imp_CLSIDFromString
0x180085c1d  mov     ebx, 1078h
0x180085c22  mov     ecx, ebx; Size
0x180085c24  call    WwanMemAlloc
0x180085c29  xor     edx, edx; Val
0x180085c2b  lea     r8d, [rbx-4]; Size
0x180085c2f  mov     rdi, rax
0x180085c32  lea     rcx, [rax+4]; void *
0x180085c36  call    memset_0
0x180085c3b  mov     [rdi], ebx
0x180085c3d  lea     r8, aTryingToGetHan; "Trying to get handle of autologger sess"...
0x180085c44  movups  xmm0, xmmword ptr [rsp+6A0h+pclsid.Data1]
0x180085c49  xor     edx, edx; struct _GUID *
0x180085c4b  mov     dword ptr [rdi+74h], 78h ; 'x'
0x180085c52  mov     rcx, rsi; char *
0x180085c55  mov     dword ptr [rdi+70h], 878h
0x180085c5c  movdqu  xmmword ptr [rdi+18h], xmm0
0x180085c61  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180085c66  xor     r9d, r9d; ControlCode
0x180085c69  lea     rdx, InstanceName; "WiFiSession"
0x180085c70  mov     r8, rdi; Properties
0x180085c73  xor     ecx, ecx; TraceHandle
0x180085c75  call    cs:__imp_ControlTraceW
0x180085c7b  mov     ebx, eax
0x180085c7d  test    eax, eax
0x180085c7f  jz      short loc_180085C9A
0x180085c81  lea     r8, aFailedToQueryI_0; "Failed to query information about traci"...
0x180085c88  xor     edx, edx; struct _GUID *
0x180085c8a  mov     rcx, rsi; char *
0x180085c8d  mov     r9d, eax
0x180085c90  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180085c95  jmp     loc_180085D5A
0x180085c9a  mov     rcx, [rdi+8]; TraceHandle
0x180085c9e  xor     edx, edx; struct _GUID *
0x180085ca0  test    rcx, rcx
0x180085ca3  jnz     short loc_180085CB9
0x180085ca5  lea     r8, aInvalidHandleF; "Invalid handle for tracing session. Una"...
0x180085cac  mov     rcx, rsi; char *
0x180085caf  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180085cb4  jmp     loc_180085D5A
0x180085cb9  mov     r9d, 3; ControlCode
0x180085cbf  mov     r8, rdi; Properties
0x180085cc2  call    cs:__imp_ControlTraceW
0x180085cc8  mov     ebx, eax
0x180085cca  test    eax, eax
0x180085ccc  jz      short loc_180085CD7
0x180085cce  lea     r8, aFailedToBuffer; "Failed to buffers to log file. Error: 0"...
0x180085cd5  jmp     short loc_180085C88
0x180085cd7  lea     rdx, [rbp+5A0h+NewFileName]; unsigned __int16 *
0x180085cde  lea     rcx, [rsp+6A0h+var_660]; unsigned __int16 *
0x180085ce3  call    ?GetAutoLoggerLogFileName@WwanUtilities@@CAKPEBGPEAG@Z; WwanUtilities::GetAutoLoggerLogFileName(ushort const *,ushort *)
0x180085ce8  xor     edx, edx; struct _GUID *
0x180085cea  mov     ebx, eax
0x180085cec  mov     rcx, rsi; char *
0x180085cef  test    eax, eax
0x180085cf1  jz      short loc_180085CFC
0x180085cf3  lea     r8, aGetautologgerl; "GetAutoLoggerLogFileName failed with er"...
0x180085cfa  jmp     short loc_180085C8D
0x180085cfc  lea     r9, [rbp+5A0h+NewFileName]
0x180085d03  lea     r8, aCopyingLogFile; "Copying log file to new file: %ls"
0x180085d0a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180085d0f  xor     r8d, r8d; bFailIfExists
0x180085d12  lea     rdx, [rbp+5A0h+NewFileName]; lpNewFileName
0x180085d19  lea     rcx, [rbp+5A0h+ExistingFileName]; lpExistingFileName
0x180085d20  call    cs:__imp_CopyFileW
0x180085d26  test    eax, eax
0x180085d28  jnz     short loc_180085D5A
0x180085d2a  call    cs:__imp_GetLastError
0x180085d30  mov     [rsp+6A0h+var_678], eax
0x180085d34  lea     r9, [rbp+5A0h+ExistingFileName]
0x180085d3b  lea     r8, aFailedToCopyAu; "Failed to copy autologger log file. Tri"...
0x180085d42  xor     edx, edx; struct _GUID *
0x180085d44  mov     ebx, eax
0x180085d46  mov     rcx, rsi; char *
0x180085d49  lea     rax, [rbp+5A0h+NewFileName]
0x180085d50  mov     [rsp+6A0h+var_680], rax
0x180085d55  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180085d5a  test    rdi, rdi
0x180085d5d  jz      short loc_180085D67
0x180085d5f  mov     rcx, rdi
0x180085d62  call    WwanMemFree
0x180085d67  mov     r9d, ebx
0x180085d6a  lea     r8, aFlushandcopyau; "FlushAndCopyAutologger finishing with s"...
0x180085d71  xor     edx, edx; struct _GUID *
0x180085d73  mov     rcx, rsi; char *
0x180085d76  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180085d7b  mov     rcx, [rbp+5A0h+var_30]
0x180085d82  xor     rcx, rsp; StackCookie
0x180085d85  call    __security_check_cookie
0x180085d8a  add     rsp, 688h
0x180085d91  pop     rdi
0x180085d92  pop     rsi
0x180085d93  pop     rbx
0x180085d94  pop     rbp
0x180085d95  retn
```
