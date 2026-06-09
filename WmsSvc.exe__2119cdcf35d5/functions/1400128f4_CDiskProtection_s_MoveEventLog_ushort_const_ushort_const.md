# CDiskProtection::s_MoveEventLog(ushort const *,ushort const *)

- ea: `0x1400128f4`
- end: `0x140012b7f`
- name: `?s_MoveEventLog@CDiskProtection@@KAJPEBG0@Z`
- size: `651`
- prototype: `__int64 __fastcall(LPCWSTR ChannelPath, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140012b88`

## callees

- `0x1400128f4`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140012936`
- `KERNEL32!GetLastError` at `0x140012a0f`
- `KERNEL32!GetLastError` at `0x140012adc`
- `KERNEL32!GetLastError` at `0x140012936`
- `KERNEL32!GetLastError` at `0x140012a0f`
- `KERNEL32!GetLastError` at `0x140012adc`
- `KERNEL32!IsDebuggerPresent` at `0x140012991`
- `KERNEL32!IsDebuggerPresent` at `0x140012a66`
- `KERNEL32!IsDebuggerPresent` at `0x140012b33`
- `KERNEL32!IsDebuggerPresent` at `0x140012991`
- `KERNEL32!IsDebuggerPresent` at `0x140012a66`
- `KERNEL32!IsDebuggerPresent` at `0x140012b33`
- `wevtapi!EvtSetChannelConfigProperty` at `0x140012a01`
- `wevtapi!EvtSetChannelConfigProperty` at `0x140012a01`
- `wevtapi!EvtSaveChannelConfig` at `0x140012ad2`
- `wevtapi!EvtSaveChannelConfig` at `0x140012ad2`
- `wevtapi!EvtClose` at `0x140012b6a`
- `wevtapi!EvtClose` at `0x140012b6a`
- `wevtapi!EvtOpenChannelConfig` at `0x140012924`
- `wevtapi!EvtOpenChannelConfig` at `0x140012924`

## string_xrefs

- `0x140012970`: `hEvtChannelConfig != 0`
- `0x140012959`: `CDiskProtection::s_MoveEventLog`
- `0x140012a32`: `CDiskProtection::s_MoveEventLog`
- `0x140012aff`: `CDiskProtection::s_MoveEventLog`
- `0x140012b55`: `CDiskProtection::s_MoveEventLog - Moved event log %s to %s\n`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_MoveEventLog(LPCWSTR ChannelPath, const unsigned __int16 *a2)
{
  EVT_HANDLE v4; // rax
  void *v5; // r14
  signed int v6; // eax
  signed int v7; // ebx
  signed int v8; // eax
  __int64 v9; // r9
  __int64 v10; // r8
  signed int LastError; // eax
  _EVT_VARIANT PropertyValue; // [rsp+40h] [rbp-48h] BYREF

  PropertyValue.Int64Val = (INT64)a2;
  PropertyValue.Count = 0;
  PropertyValue.Type = 1;
  v4 = EvtOpenChannelConfig(0, ChannelPath, 0);
  v5 = v4;
  if ( v4 )
  {
    if ( EvtSetChannelConfigProperty(v4, EvtChannelLoggingConfigLogFilePath, 0, &PropertyValue) )
    {
      if ( EvtSaveChannelConfig(v5, 0) )
      {
        v7 = 0;
        DEBUGMSG(L"CDiskProtection::s_MoveEventLog - Moved event log %s to %s\n", ChannelPath, a2);
        goto LABEL_28;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x19E0u,
        L"CDiskProtection::s_MoveEventLog",
        L"CBRAEx",
        L"fSuccess",
        v7);
      if ( IsDebuggerPresent() )
      {
        v9 = 6624;
        goto LABEL_16;
      }
      v10 = 6624;
    }
    else
    {
      v8 = GetLastError();
      v7 = v8;
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        0x19DDu,
        L"CDiskProtection::s_MoveEventLog",
        L"CBRAEx",
        L"fSuccess",
        v7);
      if ( IsDebuggerPresent() )
      {
        v9 = 6621;
LABEL_16:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v9,
          L"CDiskProtection::s_MoveEventLog",
          L"CBRAEx",
          L"fSuccess",
          v7,
          PropertyValue.Int64Val,
          *(_QWORD *)&PropertyValue.Count);
LABEL_28:
        EvtClose(v5);
        return (unsigned int)v7;
      }
      v10 = 6621;
    }
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v10,
      L"CDiskProtection::s_MoveEventLog",
      L"CBRAEx",
      L"fSuccess",
      v7);
    goto LABEL_28;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
    v7 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
    0x19D7u,
    L"CDiskProtection::s_MoveEventLog",
    L"CBRAEx",
    L"hEvtChannelConfig != 0",
    v7);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      6615,
      L"CDiskProtection::s_MoveEventLog",
      L"CBRAEx",
      L"hEvtChannelConfig != 0",
      v7,
      PropertyValue.Int64Val,
      *(_QWORD *)&PropertyValue.Count);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      6615,
      L"CDiskProtection::s_MoveEventLog",
      L"CBRAEx",
      L"hEvtChannelConfig != 0",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400128f4  push    rbx
0x1400128f6  push    rbp
0x1400128f7  push    rsi
0x1400128f8  push    rdi
0x1400128f9  push    r14
0x1400128fb  push    r15
0x1400128fd  sub     rsp, 58h
0x140012901  mov     rdi, rdx
0x140012904  mov     qword ptr [rsp+88h+PropertyValue], rdx
0x140012909  mov     rdx, rcx; ChannelPath
0x14001290c  mov     [rsp+88h+PropertyValue.Count], 0
0x140012914  mov     rsi, rcx
0x140012917  mov     [rsp+88h+PropertyValue.Type], 1
0x14001291f  xor     ecx, ecx; Session
0x140012921  xor     r8d, r8d; Flags
0x140012924  call    cs:__imp_EvtOpenChannelConfig
0x14001292a  mov     r14, rax
0x14001292d  test    rax, rax
0x140012930  jnz     loc_1400129F2
0x140012936  call    cs:__imp_GetLastError
0x14001293c  mov     ebx, eax
0x14001293e  test    eax, eax
0x140012940  jle     short loc_14001294B
0x140012942  movzx   ebx, ax
0x140012945  or      ebx, 80070000h
0x14001294b  mov     eax, 80004005h
0x140012950  lea     rbp, aCbraex; "CBRAEx"
0x140012957  test    ebx, ebx
0x140012959  lea     rsi, aCdiskprotectio_1; "CDiskProtection::s_MoveEventLog"
0x140012960  mov     r14d, 19D7h
0x140012966  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14001296d  cmovns  ebx, eax
0x140012970  lea     r15, aHevtchannelcon; "hEvtChannelConfig != 0"
0x140012977  mov     [rsp+88h+var_60], ebx; int
0x14001297b  mov     r9, rbp; unsigned __int16 *
0x14001297e  mov     r8, rsi; unsigned __int16 *
0x140012981  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140012986  mov     edx, r14d; unsigned int
0x140012989  mov     rcx, rdi; unsigned __int16 *
0x14001298c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140012991  call    cs:__imp_IsDebuggerPresent
0x140012997  test    eax, eax
0x140012999  jz      short loc_1400129CA
0x14001299b  mov     [rsp+88h+var_50], ebx
0x14001299f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400129a6  mov     [rsp+88h+var_58], r15
0x1400129ab  mov     r9d, r14d
0x1400129ae  mov     qword ptr [rsp+88h+var_60], rbp
0x1400129b3  mov     r8, rdi
0x1400129b6  mov     ecx, 2; unsigned __int8
0x1400129bb  mov     [rsp+88h+var_68], rsi
0x1400129c0  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400129c5  jmp     loc_140012B70
0x1400129ca  mov     dword ptr [rsp+88h+var_58], ebx
0x1400129ce  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400129d5  mov     qword ptr [rsp+88h+var_60], r15
0x1400129da  mov     r9, rsi
0x1400129dd  mov     r8d, r14d
0x1400129e0  mov     [rsp+88h+var_68], rbp
0x1400129e5  mov     rdx, rdi
0x1400129e8  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400129ed  jmp     loc_140012B70
0x1400129f2  xor     r8d, r8d; Flags
0x1400129f5  lea     r9, [rsp+88h+PropertyValue]; PropertyValue
0x1400129fa  mov     rcx, r14; ChannelConfig
0x1400129fd  lea     edx, [r8+9]; PropertyId
0x140012a01  call    cs:__imp_EvtSetChannelConfigProperty
0x140012a07  test    eax, eax
0x140012a09  jnz     loc_140012ACD
0x140012a0f  call    cs:__imp_GetLastError
0x140012a15  mov     ebx, eax
0x140012a17  test    eax, eax
0x140012a19  jle     short loc_140012A24
0x140012a1b  movzx   ebx, ax
0x140012a1e  or      ebx, 80070000h
0x140012a24  mov     eax, 80004005h
0x140012a29  lea     rbp, aCbraex; "CBRAEx"
0x140012a30  test    ebx, ebx
0x140012a32  lea     rsi, aCdiskprotectio_1; "CDiskProtection::s_MoveEventLog"
0x140012a39  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140012a40  mov     r9, rbp; unsigned __int16 *
0x140012a43  cmovns  ebx, eax
0x140012a46  lea     r15, aFsuccess; "fSuccess"
0x140012a4d  mov     [rsp+88h+var_60], ebx; int
0x140012a51  mov     r8, rsi; unsigned __int16 *
0x140012a54  mov     edx, 19DDh; unsigned int
0x140012a59  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140012a5e  mov     rcx, rdi; unsigned __int16 *
0x140012a61  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140012a66  call    cs:__imp_IsDebuggerPresent
0x140012a6c  test    eax, eax
0x140012a6e  jz      short loc_140012AA2
0x140012a70  mov     r9d, 19DDh
0x140012a76  mov     [rsp+88h+var_50], ebx
0x140012a7a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140012a81  mov     [rsp+88h+var_58], r15
0x140012a86  mov     r8, rdi
0x140012a89  mov     qword ptr [rsp+88h+var_60], rbp
0x140012a8e  mov     ecx, 2; unsigned __int8
0x140012a93  mov     [rsp+88h+var_68], rsi
0x140012a98  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140012a9d  jmp     loc_140012B67
0x140012aa2  mov     r8d, 19DDh
0x140012aa8  mov     dword ptr [rsp+88h+var_58], ebx
0x140012aac  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140012ab3  mov     qword ptr [rsp+88h+var_60], r15
0x140012ab8  mov     r9, rsi
0x140012abb  mov     rdx, rdi
0x140012abe  mov     [rsp+88h+var_68], rbp
0x140012ac3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140012ac8  jmp     loc_140012B67
0x140012acd  xor     edx, edx; Flags
0x140012acf  mov     rcx, r14; ChannelConfig
0x140012ad2  call    cs:__imp_EvtSaveChannelConfig
0x140012ad8  test    eax, eax
0x140012ada  jnz     short loc_140012B53
0x140012adc  call    cs:__imp_GetLastError
0x140012ae2  mov     ebx, eax
0x140012ae4  test    eax, eax
0x140012ae6  jle     short loc_140012AF1
0x140012ae8  movzx   ebx, ax
0x140012aeb  or      ebx, 80070000h
0x140012af1  mov     eax, 80004005h
0x140012af6  lea     rbp, aCbraex; "CBRAEx"
0x140012afd  test    ebx, ebx
0x140012aff  lea     rsi, aCdiskprotectio_1; "CDiskProtection::s_MoveEventLog"
0x140012b06  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140012b0d  mov     r9, rbp; unsigned __int16 *
0x140012b10  cmovns  ebx, eax
0x140012b13  lea     r15, aFsuccess; "fSuccess"
0x140012b1a  mov     [rsp+88h+var_60], ebx; int
0x140012b1e  mov     r8, rsi; unsigned __int16 *
0x140012b21  mov     edx, 19E0h; unsigned int
0x140012b26  mov     [rsp+88h+var_68], r15; unsigned __int16 *
0x140012b2b  mov     rcx, rdi; unsigned __int16 *
0x140012b2e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140012b33  call    cs:__imp_IsDebuggerPresent
0x140012b39  test    eax, eax
0x140012b3b  jz      short loc_140012B48
0x140012b3d  mov     r9d, 19E0h
0x140012b43  jmp     loc_140012A76
0x140012b48  mov     r8d, 19E0h
0x140012b4e  jmp     loc_140012AA8
0x140012b53  xor     ebx, ebx
0x140012b55  lea     rcx, aCdiskprotectio_6; "CDiskProtection::s_MoveEventLog - Moved"...
0x140012b5c  mov     r8, rdi
0x140012b5f  mov     rdx, rsi
0x140012b62  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140012b67  mov     rcx, r14; Object
0x140012b6a  call    cs:__imp_EvtClose
0x140012b70  mov     eax, ebx
0x140012b72  add     rsp, 58h
0x140012b76  pop     r15
0x140012b78  pop     r14
0x140012b7a  pop     rdi
0x140012b7b  pop     rsi
0x140012b7c  pop     rbp
0x140012b7d  pop     rbx
0x140012b7e  retn
```
