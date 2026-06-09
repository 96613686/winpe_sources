# CConfigureMemoryIntegrity::ConfigureMemoryIntegrity(void)

- ea: `0x18002edd8`
- end: `0x18002f13b`
- name: `?ConfigureMemoryIntegrity@CConfigureMemoryIntegrity@@AEAAJXZ`
- size: `867`
- prototype: `__int64 __fastcall(CConfigureMemoryIntegrity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f150`

## callees

- `0x180001090`
- `0x1800013a4`
- `0x18002d7b8`
- `0x18002edd8`
- `0x18004325c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ee18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f03b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f03b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ef91`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ef91`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002eecc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002eecc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f118`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f118`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f122`

## string_xrefs

- `0x18002efd8`: `RegCreateKeyEx REG_CONTROL_TSERVER failed`
- `0x18002ee60`: `ConfigureMemoryIntegrity`
- `0x18002ef06`: `ConfigureMemoryIntegrity`
- `0x18002efc6`: `ConfigureMemoryIntegrity`
- `0x18002f070`: `ConfigureMemoryIntegrity`
- `0x18002ee72`: `RegOpenKeyEx DEVICE_GUARD_KEY failed`
- `0x18002ef18`: `RegDeleteTreeW DEVICE_GUARD_KEY failed`
- `0x18002f082`: `RegSetValueEx REG_VALUE_MEMORY_INTEGRITY_MULTISESSION in REG_CONTROL_TSERVER failed`

## pseudocode

```c
__int64 __fastcall CConfigureMemoryIntegrity::ConfigureMemoryIntegrity(CConfigureMemoryIntegrity *this)
{
  unsigned int v1; // ebx
  LSTATUS v3; // eax
  char *v4; // rdx
  const char **v5; // rax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  const char **v10; // [rsp+38h] [rbp-38h]
  HKEY v11; // [rsp+50h] [rbp-20h] BYREF
  const char *v12; // [rsp+58h] [rbp-18h] BYREF
  const char *v13; // [rsp+60h] [rbp-10h] BYREF
  const char *v14; // [rsp+68h] [rbp-8h] BYREF
  int Data; // [rsp+98h] [rbp+28h] BYREF
  unsigned int v16; // [rsp+A0h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF

  v1 = 0;
  hKey = 0;
  v11 = 0;
  Data = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard", 0, 0x1000Bu, &hKey);
  if ( (v3 & 0xFFFFFFFD) != 0 && (v3 > 0 ? (v1 = (unsigned __int16)v3 | 0x80070000) : (v1 = v3), (v1 & 0x80000000) != 0) )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, v1, 0);
    if ( (unsigned int)dword_180084170 > 3 )
    {
      v12 = "ConfigureMemoryIntegrity";
      v4 = byte_180079CF1;
      v13 = "RegOpenKeyEx DEVICE_GUARD_KEY failed";
      v14 = "Warning HResult failed";
      v10 = &v12;
      v5 = &v14;
LABEL_8:
      v16 = v1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&dword_180084170,
        (__int64)v4,
        0,
        0,
        (const unsigned __int16 **)v5,
        (const unsigned __int16 **)&v13,
        (__int64)&v16,
        (const unsigned __int16 **)v10);
    }
  }
  else
  {
    v6 = RegDeleteTreeW(hKey, 0);
    if ( (v6 & 0xFFFFFFFD) != 0 )
    {
      v1 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
      if ( (v1 & 0x80000000) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(0, v1, 0);
        if ( (unsigned int)dword_180084170 <= 3 )
          goto LABEL_31;
        v14 = "ConfigureMemoryIntegrity";
        v4 = (char *)&unk_180079CA8;
        v13 = "RegDeleteTreeW DEVICE_GUARD_KEY failed";
        v12 = "Warning HResult failed";
        v10 = &v14;
        v5 = &v12;
        goto LABEL_8;
      }
    }
    v7 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server",
           0,
           0,
           0,
           0x20006u,
           0,
           &v11,
           0);
    if ( v7 )
    {
      if ( v7 > 0 )
        v1 = (unsigned __int16)v7 | 0x80070000;
      else
        v1 = v7;
      MicrosoftTelemetryAssertTriggeredArgs(0, v1, 0);
      if ( (unsigned int)dword_180084170 > 3 )
      {
        v14 = "ConfigureMemoryIntegrity";
        v4 = &byte_180079C5F;
        v13 = "RegCreateKeyEx REG_CONTROL_TSERVER failed";
        v12 = "Warning HResult failed";
        v10 = &v14;
        v5 = &v12;
        goto LABEL_8;
      }
    }
    else
    {
      Data = 1;
      v8 = RegSetValueExW(v11, L"MemoryIntegrityMultisession", 0, 4u, (const BYTE *)&Data, 4u);
      if ( v8 )
      {
        if ( v8 > 0 )
          v1 = (unsigned __int16)v8 | 0x80070000;
        else
          v1 = v8;
        MicrosoftTelemetryAssertTriggeredArgs(0, v1, 0);
        if ( (unsigned int)dword_180084170 > 3 )
        {
          v14 = "ConfigureMemoryIntegrity";
          v4 = (char *)&word_180079C16;
          v13 = "RegSetValueEx REG_VALUE_MEMORY_INTEGRITY_MULTISESSION in REG_CONTROL_TSERVER failed";
          v12 = "Warning HResult failed";
          v10 = &v14;
          v5 = &v12;
          goto LABEL_8;
        }
      }
      else
      {
        if ( (unsigned int)dword_180084170 > 5 )
        {
          v16 = Data;
          v14 = "marked the reg key REG_VALUE_MEMORY_INTEGRITY_MULTISESSION in REG_CONTROL_TSERVER";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (__int64)&dword_180084170,
            (__int64)&word_180079BDE,
            0,
            0,
            (const unsigned __int16 **)&v14,
            (__int64)&v16);
        }
        *((_DWORD *)this + 398) = 1;
      }
    }
  }
LABEL_31:
  TraceLoggingWriteConfigMemIntegrityEvent(v1);
  RegCloseKey(hKey);
  RegCloseKey(v11);
  return v1;
}

```

## disassembly

```asm
0x18002edd8  mov     [rsp-18h+arg_0], rbx
0x18002eddd  push    rbp
0x18002edde  push    rdi
0x18002eddf  push    r14
0x18002ede1  mov     rbp, rsp
0x18002ede4  sub     rsp, 70h
0x18002ede8  xor     ebx, ebx
0x18002edea  lea     rax, [rbp+hKey]
0x18002edee  mov     rdi, rcx
0x18002edf1  mov     [rbp+hKey], rbx
0x18002edf5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002edfc  mov     [rbp+var_20], rbx
0x18002ee00  mov     r9d, 1000Bh; samDesired
0x18002ee06  mov     [rbp+Data], ebx
0x18002ee09  xor     r8d, r8d; ulOptions
0x18002ee0c  mov     [rsp+70h+phkResult], rax; phkResult
0x18002ee11  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x18002ee18  call    cs:__imp_RegOpenKeyExW
0x18002ee1e  mov     r14d, 80070000h
0x18002ee24  test    eax, 0FFFFFFFDh
0x18002ee29  jz      loc_18002EEC6
0x18002ee2f  test    eax, eax
0x18002ee31  jg      short loc_18002EE37
0x18002ee33  mov     ebx, eax
0x18002ee35  jmp     short loc_18002EE3D
0x18002ee37  movzx   ebx, ax
0x18002ee3a  or      ebx, r14d
0x18002ee3d  test    ebx, ebx
0x18002ee3f  jns     loc_18002EEC6
0x18002ee45  xor     r8d, r8d
0x18002ee48  mov     edx, ebx
0x18002ee4a  xor     ecx, ecx
0x18002ee4c  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002ee51  mov     eax, cs:dword_180084170
0x18002ee57  cmp     eax, 3
0x18002ee5a  jbe     loc_18002F10D
0x18002ee60  lea     rax, aConfigurememor; "ConfigureMemoryIntegrity"
0x18002ee67  mov     [rbp+var_18], rax
0x18002ee6b  lea     rdx, byte_180079CF1
0x18002ee72  lea     rax, aRegopenkeyexDe; "RegOpenKeyEx DEVICE_GUARD_KEY failed"
0x18002ee79  mov     [rbp+var_10], rax
0x18002ee7d  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002ee84  mov     [rbp+var_8], rax
0x18002ee88  lea     rax, [rbp+var_18]
0x18002ee8c  mov     [rsp+70h+var_38], rax
0x18002ee91  lea     rax, [rbp+arg_10]
0x18002ee95  mov     [rsp+70h+lpSecurityAttributes], rax
0x18002ee9a  lea     rax, [rbp+var_10]
0x18002ee9e  mov     qword ptr [rsp+70h+samDesired], rax
0x18002eea3  lea     rax, [rbp+var_8]
0x18002eea7  xor     r9d, r9d
0x18002eeaa  mov     [rsp+70h+phkResult], rax
0x18002eeaf  xor     r8d, r8d
0x18002eeb2  mov     [rbp+arg_10], ebx
0x18002eeb5  lea     rcx, dword_180084170
0x18002eebc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002eec1  jmp     loc_18002F10D
0x18002eec6  mov     rcx, [rbp+hKey]; hKey
0x18002eeca  xor     edx, edx; lpSubKey
0x18002eecc  call    cs:__imp_RegDeleteTreeW
0x18002eed2  test    eax, 0FFFFFFFDh
0x18002eed7  jz      short loc_18002EF52
0x18002eed9  test    eax, eax
0x18002eedb  jg      short loc_18002EEE1
0x18002eedd  mov     ebx, eax
0x18002eedf  jmp     short loc_18002EEE7
0x18002eee1  movzx   ebx, ax
0x18002eee4  or      ebx, r14d
0x18002eee7  test    ebx, ebx
0x18002eee9  jns     short loc_18002EF52
0x18002eeeb  xor     r8d, r8d
0x18002eeee  mov     edx, ebx
0x18002eef0  xor     ecx, ecx
0x18002eef2  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002eef7  mov     eax, cs:dword_180084170
0x18002eefd  cmp     eax, 3
0x18002ef00  jbe     loc_18002F10D
0x18002ef06  lea     rax, aConfigurememor; "ConfigureMemoryIntegrity"
0x18002ef0d  mov     [rbp+var_8], rax
0x18002ef11  lea     rdx, unk_180079CA8
0x18002ef18  lea     rax, aRegdeletetreew; "RegDeleteTreeW DEVICE_GUARD_KEY failed"
0x18002ef1f  mov     [rbp+var_10], rax
0x18002ef23  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002ef2a  mov     [rbp+var_18], rax
0x18002ef2e  lea     rax, [rbp+var_8]
0x18002ef32  mov     [rsp+70h+var_38], rax
0x18002ef37  lea     rax, [rbp+arg_10]
0x18002ef3b  mov     [rsp+70h+lpSecurityAttributes], rax
0x18002ef40  lea     rax, [rbp+var_10]
0x18002ef44  mov     qword ptr [rsp+70h+samDesired], rax
0x18002ef49  lea     rax, [rbp+var_18]
0x18002ef4d  jmp     loc_18002EEA7
0x18002ef52  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18002ef5b  lea     rax, [rbp+var_20]
0x18002ef5f  mov     [rsp+70h+var_38], rax; phkResult
0x18002ef64  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18002ef6b  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002ef74  xor     r9d, r9d; lpClass
0x18002ef77  mov     [rsp+70h+samDesired], 20006h; samDesired
0x18002ef7f  xor     r8d, r8d; Reserved
0x18002ef82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ef89  mov     dword ptr [rsp+70h+phkResult], 0; dwOptions
0x18002ef91  call    cs:__imp_RegCreateKeyExW
0x18002ef97  test    eax, eax
0x18002ef99  jz      short loc_18002F012
0x18002ef9b  jg      short loc_18002EFA1
0x18002ef9d  mov     ebx, eax
0x18002ef9f  jmp     short loc_18002EFA7
0x18002efa1  movzx   ebx, ax
0x18002efa4  or      ebx, r14d
0x18002efa7  test    ebx, ebx
0x18002efa9  jns     short loc_18002F012
0x18002efab  xor     r8d, r8d
0x18002efae  mov     edx, ebx
0x18002efb0  xor     ecx, ecx
0x18002efb2  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002efb7  mov     eax, cs:dword_180084170
0x18002efbd  cmp     eax, 3
0x18002efc0  jbe     loc_18002F10D
0x18002efc6  lea     rax, aConfigurememor; "ConfigureMemoryIntegrity"
0x18002efcd  mov     [rbp+var_8], rax
0x18002efd1  lea     rdx, byte_180079C5F
0x18002efd8  lea     rax, aRegcreatekeyex; "RegCreateKeyEx REG_CONTROL_TSERVER fail"...
0x18002efdf  mov     [rbp+var_10], rax
0x18002efe3  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002efea  mov     [rbp+var_18], rax
0x18002efee  lea     rax, [rbp+var_8]
0x18002eff2  mov     [rsp+70h+var_38], rax
0x18002eff7  lea     rax, [rbp+arg_10]
0x18002effb  mov     [rsp+70h+lpSecurityAttributes], rax
0x18002f000  lea     rax, [rbp+var_10]
0x18002f004  mov     qword ptr [rsp+70h+samDesired], rax
0x18002f009  lea     rax, [rbp+var_18]
0x18002f00d  jmp     loc_18002EEA7
0x18002f012  mov     rcx, [rbp+var_20]; hKey
0x18002f016  lea     rax, [rbp+Data]
0x18002f01a  mov     r9d, 4; dwType
0x18002f020  mov     [rbp+Data], 1
0x18002f027  mov     [rsp+70h+samDesired], r9d; cbData
0x18002f02c  lea     rdx, aMemoryintegrit; "MemoryIntegrityMultisession"
0x18002f033  xor     r8d, r8d; Reserved
0x18002f036  mov     [rsp+70h+phkResult], rax; lpData
0x18002f03b  call    cs:__imp_RegSetValueExW
0x18002f041  test    eax, eax
0x18002f043  jz      short loc_18002F0BC
0x18002f045  jg      short loc_18002F04B
0x18002f047  mov     ebx, eax
0x18002f049  jmp     short loc_18002F051
0x18002f04b  movzx   ebx, ax
0x18002f04e  or      ebx, r14d
0x18002f051  test    ebx, ebx
0x18002f053  jns     short loc_18002F0BC
0x18002f055  xor     r8d, r8d
0x18002f058  mov     edx, ebx
0x18002f05a  xor     ecx, ecx
0x18002f05c  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002f061  mov     eax, cs:dword_180084170
0x18002f067  cmp     eax, 3
0x18002f06a  jbe     loc_18002F10D
0x18002f070  lea     rax, aConfigurememor; "ConfigureMemoryIntegrity"
0x18002f077  mov     [rbp+var_8], rax
0x18002f07b  lea     rdx, word_180079C16
0x18002f082  lea     rax, aRegsetvalueexR_0; "RegSetValueEx REG_VALUE_MEMORY_INTEGRIT"...
0x18002f089  mov     [rbp+var_10], rax
0x18002f08d  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002f094  mov     [rbp+var_18], rax
0x18002f098  lea     rax, [rbp+var_8]
0x18002f09c  mov     [rsp+70h+var_38], rax
0x18002f0a1  lea     rax, [rbp+arg_10]
0x18002f0a5  mov     [rsp+70h+lpSecurityAttributes], rax
0x18002f0aa  lea     rax, [rbp+var_10]
0x18002f0ae  mov     qword ptr [rsp+70h+samDesired], rax
0x18002f0b3  lea     rax, [rbp+var_18]
0x18002f0b7  jmp     loc_18002EEA7
0x18002f0bc  mov     eax, cs:dword_180084170
0x18002f0c2  cmp     eax, 5
0x18002f0c5  jbe     short loc_18002F103
0x18002f0c7  mov     eax, [rbp+Data]
0x18002f0ca  lea     rdx, word_180079BDE
0x18002f0d1  mov     [rbp+arg_10], eax
0x18002f0d4  lea     rcx, dword_180084170
0x18002f0db  lea     rax, aMarkedTheRegKe_0; "marked the reg key REG_VALUE_MEMORY_INT"...
0x18002f0e2  xor     r9d, r9d
0x18002f0e5  mov     [rbp+var_8], rax
0x18002f0e9  xor     r8d, r8d
0x18002f0ec  lea     rax, [rbp+arg_10]
0x18002f0f0  mov     qword ptr [rsp+70h+samDesired], rax
0x18002f0f5  lea     rax, [rbp+var_8]
0x18002f0f9  mov     [rsp+70h+phkResult], rax
0x18002f0fe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002f103  mov     dword ptr [rdi+638h], 1
0x18002f10d  mov     ecx, ebx; unsigned int
0x18002f10f  call    ?TraceLoggingWriteConfigMemIntegrityEvent@@YAXK@Z; TraceLoggingWriteConfigMemIntegrityEvent(ulong)
0x18002f114  mov     rcx, [rbp+hKey]; hKey
0x18002f118  call    cs:__imp_RegCloseKey
0x18002f11e  mov     rcx, [rbp+var_20]; hKey
0x18002f122  call    cs:__imp_RegCloseKey
0x18002f128  mov     eax, ebx
0x18002f12a  mov     rbx, [rsp+70h+arg_0]
0x18002f132  add     rsp, 70h
0x18002f136  pop     r14
0x18002f138  pop     rdi
0x18002f139  pop     rbp
0x18002f13a  retn
```
