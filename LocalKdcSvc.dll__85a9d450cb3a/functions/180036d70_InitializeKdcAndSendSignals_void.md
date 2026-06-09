# InitializeKdcAndSendSignals(void)

- ea: `0x180036d70`
- end: `0x180036e9b`
- name: `?InitializeKdcAndSendSignals@@YAJXZ`
- size: `299`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006d200`

## callees

- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x180036d70`
- `0x180072288`

## import_xrefs

- `Kerberos!KerbKdcCallBack` at `0x180036d81`
- `Kerberos!KerbKdcCallBack` at `0x180036d81`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036e3e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e5a`
- `NETLOGON!I_NetLogonSetServiceBits` at `0x180036ddd`
- `NETLOGON!I_NetLogonSetServiceBits` at `0x180036ddd`

## string_xrefs

- `0x180036d90`: `kdcsvc.dll`

## pseudocode

```c
__int64 InitializeKdcAndSendSignals(void)
{
  int v0; // eax
  unsigned int v1; // edi
  CSecurityData *v2; // rcx
  __int64 v3; // rdx
  DWORD LastError; // eax

  v0 = KerbKdcCallBack(&KdcGlobalKerbKdcCallInfo);
  v1 = v0;
  if ( v0 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs("kdcsvc.dll", (unsigned int)v0, 0);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v1;
    v3 = 17;
LABEL_5:
    WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v1);
    return v1;
  }
  v1 = I_NetLogonSetServiceBits(131104, 131104);
  if ( (v1 & 0x80000000) != 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v1;
    v3 = 18;
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
  if ( SetEvent(hKdcKerbReadyEvent) )
    return 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
      LastError,
      -1073741595);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x180036d70  mov     [rsp+arg_0], rbx
0x180036d75  push    rdi
0x180036d76  sub     rsp, 30h
0x180036d7a  lea     rcx, ?KdcGlobalKerbKdcCallInfo@@3U_KERB_KDC_CALL_INFO@@A; _KERB_KDC_CALL_INFO KdcGlobalKerbKdcCallInfo
0x180036d81  call    cs:__imp_KerbKdcCallBack
0x180036d87  mov     edi, eax
0x180036d89  test    eax, eax
0x180036d8b  jns     short loc_180036DD6
0x180036d8d  xor     r8d, r8d
0x180036d90  lea     rcx, aKdcsvcDll; "kdcsvc.dll"
0x180036d97  mov     edx, eax
0x180036d99  call    MicrosoftTelemetryAssertTriggeredArgs
0x180036d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036da5  lea     rbx, WPP_GLOBAL_Control
0x180036dac  cmp     rcx, rbx
0x180036daf  jz      short loc_180036DCF
0x180036db1  test    byte ptr [rcx+1Ch], 1
0x180036db5  jz      short loc_180036DCF
0x180036db7  mov     edx, 11h
0x180036dbc  mov     rcx, [rcx+10h]
0x180036dc0  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180036dc7  mov     r9d, edi
0x180036dca  call    WPP_SF_d
0x180036dcf  mov     eax, edi
0x180036dd1  jmp     loc_180036E90
0x180036dd6  mov     ecx, 20020h
0x180036ddb  mov     edx, ecx
0x180036ddd  call    cs:__imp_I_NetLogonSetServiceBits
0x180036de3  mov     edi, eax
0x180036de5  test    eax, eax
0x180036de7  jns     short loc_180036E09
0x180036de9  mov     rcx, cs:WPP_GLOBAL_Control
0x180036df0  lea     rbx, WPP_GLOBAL_Control
0x180036df7  cmp     rcx, rbx
0x180036dfa  jz      short loc_180036DCF
0x180036dfc  test    byte ptr [rcx+1Ch], 1
0x180036e00  jz      short loc_180036DCF
0x180036e02  mov     edx, 12h
0x180036e07  jmp     short loc_180036DBC
0x180036e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e10  lea     rbx, WPP_GLOBAL_Control
0x180036e17  cmp     rcx, rbx
0x180036e1a  jz      short loc_180036E37
0x180036e1c  test    byte ptr [rcx+1Ch], 4
0x180036e20  jz      short loc_180036E37
0x180036e22  mov     rcx, [rcx+10h]
0x180036e26  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180036e2d  mov     edx, 13h
0x180036e32  call    WPP_SF_
0x180036e37  mov     rcx, cs:?hKdcKerbReadyEvent@@3PEAXEA; hEvent
0x180036e3e  call    cs:__imp_SetEvent
0x180036e44  test    eax, eax
0x180036e46  jnz     short loc_180036E8E
0x180036e48  mov     rax, cs:WPP_GLOBAL_Control
0x180036e4f  cmp     rax, rbx
0x180036e52  jz      short loc_180036E87
0x180036e54  test    byte ptr [rax+1Ch], 4
0x180036e58  jz      short loc_180036E87
0x180036e5a  call    cs:__imp_GetLastError
0x180036e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e67  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180036e6e  mov     edx, 14h
0x180036e73  mov     [rsp+38h+var_18], 0C00000E5h
0x180036e7b  mov     r9d, eax
0x180036e7e  mov     rcx, [rcx+10h]
0x180036e82  call    WPP_SF_Dd
0x180036e87  mov     eax, 0C00000E5h
0x180036e8c  jmp     short loc_180036E90
0x180036e8e  xor     eax, eax
0x180036e90  mov     rbx, [rsp+38h+arg_0]
0x180036e95  add     rsp, 30h
0x180036e99  pop     rdi
0x180036e9a  retn
```
