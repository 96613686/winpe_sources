# GetTokenBrokerPluginSID(void * *)

- ea: `0x18002a910`
- end: `0x18002a9a1`
- name: `?GetTokenBrokerPluginSID@@YAJPEAPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(PSID *Sid)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024314`
- `0x180024910`
- `0x180024f54`

## callees

- `0x18002a910`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a92c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a92c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a940`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002a922`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002a922`

## pseudocode

```c
__int64 __fastcall GetTokenBrokerPluginSID(PSID *Sid)
{
  signed int LastError; // ebx
  signed int v3; // [rsp+20h] [rbp-38h]
  int v4; // [rsp+30h] [rbp-28h]

  LastError = 0;
  if ( !ConvertStringSidToSidW(
          L"S-1-15-2-1910091885-1573563583-1104941280-2418270861-3411158377-2822700936-2990310272",
          Sid) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    if ( LastError < 0 )
    {
      v4 = 2652;
      v3 = LastError;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v3, "login.cpp", v4, "NTSTATUS", &base);
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002a910  push    rbx
0x18002a912  sub     rsp, 50h
0x18002a916  mov     rdx, rcx; Sid
0x18002a919  xor     ebx, ebx
0x18002a91b  lea     rcx, StringSid; "S-1-15-2-1910091885-1573563583-11049412"...
0x18002a922  call    cs:__imp_ConvertStringSidToSidW
0x18002a928  test    eax, eax
0x18002a92a  jnz     short loc_18002A999
0x18002a92c  call    cs:__imp_GetLastError
0x18002a932  test    eax, eax
0x18002a934  jg      short loc_18002A940
0x18002a936  call    cs:__imp_GetLastError
0x18002a93c  mov     ebx, eax
0x18002a93e  jmp     short loc_18002A94F
0x18002a940  call    cs:__imp_GetLastError
0x18002a946  movzx   ebx, ax
0x18002a949  or      ebx, 0C0070000h
0x18002a94f  test    ebx, ebx
0x18002a951  jns     short loc_18002A999
0x18002a953  lea     rax, base
0x18002a95a  mov     ecx, 2
0x18002a95f  mov     [rsp+58h+var_18], rax
0x18002a964  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18002a96b  lea     rax, aNtstatus; "NTSTATUS"
0x18002a972  mov     r9d, ecx
0x18002a975  mov     [rsp+58h+var_20], rax
0x18002a97a  xor     edx, edx
0x18002a97c  lea     rax, aOnecoreuapDsEx_25+21h; "login.cpp"
0x18002a983  mov     [rsp+58h+var_28], 0A5Ch
0x18002a98b  mov     [rsp+58h+var_30], rax
0x18002a990  mov     [rsp+58h+var_38], ebx
0x18002a994  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002a999  mov     eax, ebx
0x18002a99b  add     rsp, 50h
0x18002a99f  pop     rbx
0x18002a9a0  retn
```
