# CDtcConfig::GetTraceSettings(_DTC_TRACE_SETTINGS *)

- ea: `0x18001ca30`
- end: `0x18001ce17`
- name: `?GetTraceSettings@CDtcConfig@@UEAAJPEAU_DTC_TRACE_SETTINGS@@@Z`
- size: `999`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this, struct _DTC_TRACE_SETTINGS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800141a8`
- `0x180018ba0`
- `0x18001ca30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cc00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ccd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cc00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ccd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cda9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cda9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cdd5`

## string_xrefs

- `0x18001ca60`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001cc0c`: `Failed to open options key`
- `0x18001cce1`: `Failed to open transactions key`
- `0x18001cb7d`: `Failed to open modules key`
- `0x18001ca7a`: `CDtcConfig::GetTraceSettings`
- `0x18001cb8f`: `CDtcConfig::GetTraceSettings`
- `0x18001cc1e`: `CDtcConfig::GetTraceSettings`
- `0x18001cd99`: `CDtcConfig::GetTraceSettings`
- `0x18001cc9f`: `Failed to read the session-up value`

## pseudocode

```c
__int64 __fastcall CDtcConfig::GetTraceSettings(CDtcConfig *this, struct _DTC_TRACE_SETTINGS *a2)
{
  HKEY v2; // rsi
  int HKLM; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r9
  int v8; // r15d
  LSTATUS v9; // eax
  CDtcConfig *v10; // rcx
  const wchar_t *v11; // rax
  __int64 v12; // r9
  CDtcConfig *v13; // rcx
  const wchar_t *v14; // rax
  __int64 v15; // r9
  CDtcConfig *v16; // rcx
  CDtcConfig *v17; // rcx
  CDtcConfig *v18; // rcx
  int v19; // eax
  __int128 v20; // xmm1
  __int64 v22; // [rsp+28h] [rbp-48h]
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v25[28]; // [rsp+50h] [rbp-20h]
  unsigned int v26; // [rsp+B8h] [rbp+48h] BYREF
  HKEY v27; // [rsp+C0h] [rbp+50h] BYREF
  HKEY v28; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  phkResult = 0;
  v27 = 0;
  v28 = 0;
  v26 = 0;
  hKey = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1448,
    L"CDtcConfig::GetTraceSettings",
    0,
    L"In");
  if ( !a2 )
  {
    HKLM = -2147024809;
    v6 = L"Invalid arguments.";
    v7 = 1453;
LABEL_3:
    LODWORD(v22) = HKLM;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v7,
      L"CDtcConfig::GetTraceSettings",
      v22,
      v6);
    goto LABEL_37;
  }
  if ( !*((_DWORD *)this + 7) )
  {
    HKLM = -2147024846;
    v6 = L"GetTraceSettings is not supported on a remote host.";
    v7 = 1460;
    goto LABEL_3;
  }
  *(_QWORD *)&v25[8] = 0;
  v8 = 0;
  HKLM = CDtcConfig::GetHKLM(this, &hKey);
  if ( HKLM < 0 )
  {
    LODWORD(v22) = HKLM;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      1468,
      L"CDtcConfig::GetTraceSettings",
      v22,
      L"GetHKLM failed.");
    v2 = hKey;
    goto LABEL_37;
  }
  v2 = hKey;
  v9 = RegOpenKeyExW(
         hKey,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\Modules",
         0,
         1u,
         &phkResult);
  HKLM = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      HKLM = (unsigned __int16)v9 | 0x80070000;
    v11 = L"Failed to open modules key";
    v12 = 1480;
    goto LABEL_12;
  }
  HKLM = CDtcConfig::ReadRegDWORD(v10, phkResult, L"Active", &v26);
  if ( HKLM < 0 )
  {
    v11 = L"Failed to get active value (mod)";
    v12 = 1487;
LABEL_12:
    LODWORD(v22) = HKLM;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v12,
      L"CDtcConfig::GetTraceSettings",
      v22,
      v11);
    goto LABEL_37;
  }
  *(_DWORD *)v25 = v26 != 0;
  HKLM = RegOpenKeyExW(
           v2,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\LoggingOptions",
           0,
           1u,
           &v27);
  if ( HKLM )
  {
    v14 = L"Failed to open options key";
    v15 = 1500;
    goto LABEL_17;
  }
  HKLM = CDtcConfig::ReadRegDWORD(v13, v27, L"MaxBuffers", &v26);
  if ( HKLM < 0 )
  {
    v11 = L"Failed to get max buffer count";
    v12 = 1508;
    goto LABEL_12;
  }
  *(_DWORD *)&v25[24] = v26;
  HKLM = CDtcConfig::ReadRegDWORD(v16, v27, L"RequestSessionUp", &v26);
  if ( HKLM < 0 )
  {
    v11 = L"Failed to read the session-up value";
    v12 = 1516;
    goto LABEL_12;
  }
  *(_DWORD *)&v25[20] = v26 != 0;
  HKLM = RegOpenKeyExW(
           v2,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\Modules\\Transaction_Transitions",
           0,
           1u,
           &v28);
  if ( HKLM )
  {
    v14 = L"Failed to open transactions key";
    v15 = 1529;
LABEL_17:
    LODWORD(v22) = HKLM;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v15,
      L"CDtcConfig::GetTraceSettings",
      v22,
      v14);
    if ( HKLM > 0 )
      HKLM = (unsigned __int16)HKLM | 0x80070000;
    goto LABEL_37;
  }
  HKLM = CDtcConfig::ReadRegDWORD(v17, v28, L"Active", &v26);
  if ( HKLM < 0 )
  {
    v11 = L"Failed to get the active value (xact)";
    v12 = 1537;
    goto LABEL_12;
  }
  *(_DWORD *)&v25[4] = v26 != 0;
  HKLM = CDtcConfig::ReadRegDWORD(v18, v28, L"ControlFlags", &v26);
  if ( HKLM < 0 )
  {
    v11 = L"Failed to get the control flags";
    v12 = 1546;
    goto LABEL_12;
  }
  if ( (v26 & 0xFFFFFF) == 0xFFFFFF )
  {
    *(_QWORD *)&v25[8] = 0x100000001LL;
    *(_DWORD *)&v25[16] = 1;
  }
  else
  {
    v19 = *(_DWORD *)&v25[12];
    if ( (v26 & 1) != 0 )
      v19 = 1;
    *(_DWORD *)&v25[12] = v19;
    if ( (v26 & 2) != 0 )
      v8 = 1;
    *(_DWORD *)&v25[16] = v8;
  }
  v20 = *(_OWORD *)&v25[12];
  *(_OWORD *)a2 = *(_OWORD *)v25;
  *(_OWORD *)((char *)a2 + 12) = v20;
LABEL_37:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v27 )
    RegCloseKey(v27);
  if ( v28 )
    RegCloseKey(v28);
  if ( v2 )
    RegCloseKey(v2);
  LODWORD(v22) = HKLM;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1577,
    L"CDtcConfig::GetTraceSettings",
    v22,
    L"Out");
  return (unsigned int)HKLM;
}

```

## disassembly

```asm
0x18001ca30  push    rbp
0x18001ca32  push    rbx
0x18001ca33  push    rsi
0x18001ca34  push    rdi
0x18001ca35  push    r13
0x18001ca37  push    r14
0x18001ca39  push    r15
0x18001ca3b  mov     rbp, rsp
0x18001ca3e  sub     rsp, 70h
0x18001ca42  xor     esi, esi
0x18001ca44  mov     [rbp+var_28], 0
0x18001ca4c  lea     rax, aIn_0; "In"
0x18001ca53  mov     [rbp+arg_10], 0
0x18001ca5b  mov     [rsp+70h+var_40], rax
0x18001ca60  lea     r13, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18001ca67  mov     r14, rdx
0x18001ca6a  mov     [rsp+70h+var_48], rsi
0x18001ca6f  mov     rbx, rcx
0x18001ca72  mov     [rbp+arg_18], 0
0x18001ca7a  lea     rdi, aCdtcconfigGett; "CDtcConfig::GetTraceSettings"
0x18001ca81  mov     [rbp+arg_8], 0
0x18001ca88  lea     edx, [rsi+6]
0x18001ca8b  mov     [rbp+hKey], rsi
0x18001ca8f  lea     ecx, [rsi+0Fh]
0x18001ca92  mov     [rsp+70h+phkResult], rdi
0x18001ca97  mov     r9d, 5A8h
0x18001ca9d  mov     r8, r13
0x18001caa0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001caa5  test    r14, r14
0x18001caa8  jnz     short loc_18001CADF
0x18001caaa  mov     ebx, 80070057h
0x18001caaf  lea     rax, aInvalidArgumen_4; "Invalid arguments."
0x18001cab6  mov     r9d, 5ADh
0x18001cabc  mov     [rsp+70h+var_40], rax
0x18001cac1  mov     edx, 1
0x18001cac6  mov     dword ptr [rsp+70h+var_48], ebx
0x18001caca  mov     r8, r13
0x18001cacd  mov     [rsp+70h+phkResult], rdi
0x18001cad2  lea     ecx, [rdx+0Eh]
0x18001cad5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001cada  jmp     loc_18001CD99
0x18001cadf  cmp     [rbx+1Ch], esi
0x18001cae2  jnz     short loc_18001CAF8
0x18001cae4  mov     ebx, 80070032h
0x18001cae9  lea     rax, aGettracesettin; "GetTraceSettings is not supported on a "...
0x18001caf0  mov     r9d, 5B4h
0x18001caf6  jmp     short loc_18001CABC
0x18001caf8  lea     rdx, [rbp+hKey]; HKEY *
0x18001cafc  mov     qword ptr [rbp+var_20+8], rsi
0x18001cb00  mov     rcx, rbx; this
0x18001cb03  xor     r15d, r15d
0x18001cb06  call    ?GetHKLM@CDtcConfig@@AEAAJPEAPEAUHKEY__@@@Z; CDtcConfig::GetHKLM(HKEY__ * *)
0x18001cb0b  mov     ebx, eax
0x18001cb0d  test    eax, eax
0x18001cb0f  jns     short loc_18001CB44
0x18001cb11  lea     rax, aGethklmFailed_0; "GetHKLM failed."
0x18001cb18  mov     r9d, 5BCh
0x18001cb1e  mov     [rsp+70h+var_40], rax
0x18001cb23  lea     edx, [r15+1]
0x18001cb27  mov     dword ptr [rsp+70h+var_48], ebx
0x18001cb2b  lea     ecx, [rdx+0Eh]
0x18001cb2e  mov     r8, r13
0x18001cb31  mov     [rsp+70h+phkResult], rdi
0x18001cb36  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001cb3b  mov     rsi, [rbp+hKey]
0x18001cb3f  jmp     loc_18001CD99
0x18001cb44  mov     rsi, [rbp+hKey]
0x18001cb48  lea     rax, [rbp+var_28]
0x18001cb4c  mov     edi, 1
0x18001cb51  mov     [rsp+70h+phkResult], rax; phkResult
0x18001cb56  mov     r9d, edi; samDesired
0x18001cb59  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cb60  mov     rcx, rsi; hKey
0x18001cb63  xor     r8d, r8d; ulOptions
0x18001cb66  call    cs:__imp_RegOpenKeyExW
0x18001cb6c  mov     ebx, eax
0x18001cb6e  test    eax, eax
0x18001cb70  jz      short loc_18001CBB3
0x18001cb72  jle     short loc_18001CB7D
0x18001cb74  movzx   ebx, ax
0x18001cb77  or      ebx, 80070000h
0x18001cb7d  lea     rax, aFailedToOpenMo; "Failed to open modules key"
0x18001cb84  mov     r9d, 5C8h
0x18001cb8a  mov     [rsp+70h+var_40], rax
0x18001cb8f  lea     r14, aCdtcconfigGett; "CDtcConfig::GetTraceSettings"
0x18001cb96  mov     dword ptr [rsp+70h+var_48], ebx
0x18001cb9a  mov     r8, r13
0x18001cb9d  mov     edx, edi
0x18001cb9f  mov     [rsp+70h+phkResult], r14
0x18001cba4  mov     ecx, 0Fh
0x18001cba9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001cbae  jmp     loc_18001CDA0
0x18001cbb3  mov     rdx, [rbp+var_28]; HKEY
0x18001cbb7  lea     r9, [rbp+arg_8]; unsigned int *
0x18001cbbb  lea     r8, aActive; "Active"
0x18001cbc2  call    ?ReadRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; CDtcConfig::ReadRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18001cbc7  mov     ebx, eax
0x18001cbc9  test    eax, eax
0x18001cbcb  jns     short loc_18001CBDC
0x18001cbcd  lea     rax, aFailedToGetAct; "Failed to get active value (mod)"
0x18001cbd4  mov     r9d, 5CFh
0x18001cbda  jmp     short loc_18001CB8A
0x18001cbdc  xor     eax, eax
0x18001cbde  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001cbe5  cmp     [rbp+arg_8], eax
0x18001cbe8  mov     r9d, edi; samDesired
0x18001cbeb  mov     rcx, rsi; hKey
0x18001cbee  setnz   al
0x18001cbf1  xor     r8d, r8d; ulOptions
0x18001cbf4  mov     dword ptr [rbp+var_20], eax
0x18001cbf7  lea     rax, [rbp+arg_10]
0x18001cbfb  mov     [rsp+70h+phkResult], rax; phkResult
0x18001cc00  call    cs:__imp_RegOpenKeyExW
0x18001cc06  mov     ebx, eax
0x18001cc08  test    eax, eax
0x18001cc0a  jz      short loc_18001CC53
0x18001cc0c  lea     rax, aFailedToOpenOp; "Failed to open options key"
0x18001cc13  mov     r9d, 5DCh
0x18001cc19  mov     [rsp+70h+var_40], rax
0x18001cc1e  lea     r14, aCdtcconfigGett; "CDtcConfig::GetTraceSettings"
0x18001cc25  mov     dword ptr [rsp+70h+var_48], ebx
0x18001cc29  mov     r8, r13
0x18001cc2c  mov     edx, edi
0x18001cc2e  mov     [rsp+70h+phkResult], r14
0x18001cc33  mov     ecx, 0Fh
0x18001cc38  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001cc3d  test    ebx, ebx
0x18001cc3f  jle     loc_18001CDA0
0x18001cc45  movzx   ebx, bx
0x18001cc48  or      ebx, 80070000h
0x18001cc4e  jmp     loc_18001CDA0
0x18001cc53  mov     rdx, [rbp+arg_10]; HKEY
0x18001cc57  lea     r9, [rbp+arg_8]; unsigned int *
0x18001cc5b  lea     r8, aMaxbuffers; "MaxBuffers"
0x18001cc62  call    ?ReadRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; CDtcConfig::ReadRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18001cc67  mov     ebx, eax
0x18001cc69  test    eax, eax
0x18001cc6b  jns     short loc_18001CC7F
0x18001cc6d  lea     rax, aFailedToGetMax; "Failed to get max buffer count"
0x18001cc74  mov     r9d, 5E4h
0x18001cc7a  jmp     loc_18001CB8A
0x18001cc7f  mov     eax, [rbp+arg_8]
0x18001cc82  lea     r9, [rbp+arg_8]; unsigned int *
0x18001cc86  mov     rdx, [rbp+arg_10]; HKEY
0x18001cc8a  lea     r8, aRequestsession; "RequestSessionUp"
0x18001cc91  mov     [rbp+var_8], eax
0x18001cc94  call    ?ReadRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; CDtcConfig::ReadRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18001cc99  mov     ebx, eax
0x18001cc9b  test    eax, eax
0x18001cc9d  jns     short loc_18001CCB1
0x18001cc9f  lea     rax, aFailedToReadTh; "Failed to read the session-up value"
0x18001cca6  mov     r9d, 5ECh
0x18001ccac  jmp     loc_18001CB8A
0x18001ccb1  xor     eax, eax
0x18001ccb3  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001ccba  cmp     [rbp+arg_8], eax
0x18001ccbd  mov     r9d, edi; samDesired
0x18001ccc0  mov     rcx, rsi; hKey
0x18001ccc3  setnz   al
0x18001ccc6  xor     r8d, r8d; ulOptions
0x18001ccc9  mov     [rbp+var_C], eax
0x18001cccc  lea     rax, [rbp+arg_18]
0x18001ccd0  mov     [rsp+70h+phkResult], rax; phkResult
0x18001ccd5  call    cs:__imp_RegOpenKeyExW
0x18001ccdb  mov     ebx, eax
0x18001ccdd  test    eax, eax
0x18001ccdf  jz      short loc_18001CCF3
0x18001cce1  lea     rax, aFailedToOpenTr; "Failed to open transactions key"
0x18001cce8  mov     r9d, 5F9h
0x18001ccee  jmp     loc_18001CC19
0x18001ccf3  mov     rdx, [rbp+arg_18]; HKEY
0x18001ccf7  lea     r9, [rbp+arg_8]; unsigned int *
0x18001ccfb  lea     r8, aActive; "Active"
0x18001cd02  call    ?ReadRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; CDtcConfig::ReadRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18001cd07  mov     ebx, eax
0x18001cd09  test    eax, eax
0x18001cd0b  jns     short loc_18001CD1F
0x18001cd0d  lea     rax, aFailedToGetThe_5; "Failed to get the active value (xact)"
0x18001cd14  mov     r9d, 601h
0x18001cd1a  jmp     loc_18001CB8A
0x18001cd1f  mov     rdx, [rbp+arg_18]; HKEY
0x18001cd23  lea     r9, [rbp+arg_8]; unsigned int *
0x18001cd27  xor     eax, eax
0x18001cd29  lea     r8, aControlflags; "ControlFlags"
0x18001cd30  cmp     [rbp+arg_8], eax
0x18001cd33  setnz   al
0x18001cd36  mov     dword ptr [rbp+var_20+4], eax
0x18001cd39  call    ?ReadRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z; CDtcConfig::ReadRegDWORD(HKEY__ *,ushort const *,ulong *)
0x18001cd3e  mov     ebx, eax
0x18001cd40  test    eax, eax
0x18001cd42  jns     short loc_18001CD56
0x18001cd44  lea     rax, aFailedToGetThe; "Failed to get the control flags"
0x18001cd4b  mov     r9d, 60Ah
0x18001cd51  jmp     loc_18001CB8A
0x18001cd56  mov     ecx, [rbp+arg_8]
0x18001cd59  mov     edx, 0FFFFFFh
0x18001cd5e  mov     eax, ecx
0x18001cd60  and     eax, edx
0x18001cd62  cmp     eax, edx
0x18001cd64  jnz     short loc_18001CD71
0x18001cd66  mov     dword ptr [rbp+var_20+8], edi
0x18001cd69  mov     dword ptr [rbp+var_20+0Ch], edi
0x18001cd6c  mov     [rbp+var_10], edi
0x18001cd6f  jmp     short loc_18001CD88
0x18001cd71  mov     eax, dword ptr [rbp+var_20+0Ch]
0x18001cd74  test    dil, cl
0x18001cd77  cmovnz  eax, edi
0x18001cd7a  test    cl, 2
0x18001cd7d  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001cd80  cmovnz  r15d, edi
0x18001cd84  mov     [rbp+var_10], r15d
0x18001cd88  movups  xmm0, [rbp+var_20]
0x18001cd8c  movups  xmm1, [rbp+var_20+0Ch]
0x18001cd90  movups  xmmword ptr [r14], xmm0
0x18001cd94  movups  xmmword ptr [r14+0Ch], xmm1
0x18001cd99  lea     r14, aCdtcconfigGett; "CDtcConfig::GetTraceSettings"
0x18001cda0  mov     rcx, [rbp+var_28]; hKey
0x18001cda4  test    rcx, rcx
0x18001cda7  jz      short loc_18001CDAF
0x18001cda9  call    cs:__imp_RegCloseKey
0x18001cdaf  mov     rcx, [rbp+arg_10]; hKey
0x18001cdb3  test    rcx, rcx
0x18001cdb6  jz      short loc_18001CDBE
0x18001cdb8  call    cs:__imp_RegCloseKey
0x18001cdbe  mov     rcx, [rbp+arg_18]; hKey
0x18001cdc2  test    rcx, rcx
0x18001cdc5  jz      short loc_18001CDCD
0x18001cdc7  call    cs:__imp_RegCloseKey
0x18001cdcd  test    rsi, rsi
0x18001cdd0  jz      short loc_18001CDDB
0x18001cdd2  mov     rcx, rsi; hKey
0x18001cdd5  call    cs:__imp_RegCloseKey
0x18001cddb  mov     edx, 6
0x18001cde0  lea     rax, aOut; "Out"
0x18001cde7  mov     [rsp+70h+var_40], rax
0x18001cdec  mov     r9d, 629h
0x18001cdf2  mov     dword ptr [rsp+70h+var_48], ebx
0x18001cdf6  mov     r8, r13
0x18001cdf9  mov     [rsp+70h+phkResult], r14
0x18001cdfe  lea     ecx, [rdx+9]
0x18001ce01  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001ce06  mov     eax, ebx
0x18001ce08  add     rsp, 70h
0x18001ce0c  pop     r15
0x18001ce0e  pop     r14
0x18001ce10  pop     r13
0x18001ce12  pop     rdi
0x18001ce13  pop     rsi
0x18001ce14  pop     rbx
0x18001ce15  pop     rbp
0x18001ce16  retn
```
