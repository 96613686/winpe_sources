# telemetryutil::etl::TelemetrySession::Create(ushort const *,telemetryutil::etl::TelemetrySessionSettings const &,long (*)(void),telemetryutil::etl::TelemetrySession * *)

- ea: `0x18000ff50`
- end: `0x18001009d`
- name: `?Create@TelemetrySession@etl@telemetryutil@@SAJPEBGAEBUTelemetrySessionSettings@23@P6AJXZPEAPEAV123@@Z`
- size: `333`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const struct telemetryutil::etl::TelemetrySessionSettings *, int (*)(void), struct telemetryutil::etl::TelemetrySession **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18000a4f0`

## callees

- `0x180001d68`
- `0x18000bbd0`
- `0x18000ece8`
- `0x18000fbc0`
- `0x18000fe60`
- `0x18000ff50`
- `0x1800100a4`
- `0x180010488`
- `0x1800105fc`
- `0x180010792`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180010090`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180010090`

## pseudocode

```c
__int64 __fastcall telemetryutil::etl::TelemetrySession::Create(
        LPCWSTR lpFileName,
        const struct telemetryutil::etl::TelemetrySessionSettings *a2,
        int (*a3)(void),
        struct telemetryutil::etl::TelemetrySession **a4)
{
  __int64 result; // rax
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rcx
  telemetryutil::etl::TelemetrySession *v8; // rax
  const struct telemetryutil::etl::TelemetrySessionSettings *v9; // rdx
  TRACEHANDLE v10; // rbx
  telemetryutil::etl::TelemetrySession *v11; // rax
  TRACEHANDLE TraceHandle[2]; // [rsp+30h] [rbp-828h] BYREF
  unsigned __int16 v13[1024]; // [rsp+40h] [rbp-818h] BYREF

  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    return 2147942450LL;
  qword_18001BFA8 = 0;
  if ( !lpFileName )
    return 2147500035LL;
  result = PITRTelemetryInitialize();
  if ( (int)result >= 0 )
  {
    if ( telemetryutil::etl::EnsureDirectoryExists(lpFileName, v6) < 0 )
      return 0;
    memset_0(v13, 0, sizeof(v13));
    result = telemetryutil::etl::TelemetrySession::BuildTraceFilePath(lpFileName, off_18001B188, v13);
    if ( (int)result < 0 )
      return result;
    anonymous_namespace_::StopFileTrace(&InstanceName, -1);
    TraceHandle[0] = -1;
    if ( (int)anonymous_namespace_::StartFileTrace(v7, v13, TraceHandle) < 0 )
      return 0;
    v8 = (telemetryutil::etl::TelemetrySession *)operator new(0x1050u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = TraceHandle[0];
    if ( v8 )
    {
      v11 = (telemetryutil::etl::TelemetrySession *)telemetryutil::etl::TelemetrySession::TelemetrySession(
                                                      v8,
                                                      v9,
                                                      lpFileName,
                                                      v13,
                                                      TraceHandle[0]);
      if ( v11 )
      {
        qword_18001BFA8 = v11;
        return 0;
      }
    }
    if ( v10 != -1 )
    {
      anonymous_namespace_::StopFileTrace(&InstanceName, v10);
      CloseTrace(v10);
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ff50  mov     [rsp+arg_8], rbx
0x18000ff55  push    rdi
0x18000ff56  sub     rsp, 850h
0x18000ff5d  mov     rax, cs:__security_cookie
0x18000ff64  xor     rax, rsp
0x18000ff67  mov     [rsp+858h+var_18], rax
0x18000ff6f  mov     rdi, rcx
0x18000ff72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000ff79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000ff7e  test    al, al
0x18000ff80  jnz     short loc_18000FF8C
0x18000ff82  mov     eax, 80070032h
0x18000ff87  jmp     loc_180010057
0x18000ff8c  mov     cs:qword_18001BFA8, 0
0x18000ff97  test    rdi, rdi
0x18000ff9a  jnz     short loc_18000FFA6
0x18000ff9c  mov     eax, 80004003h
0x18000ffa1  jmp     loc_180010057
0x18000ffa6  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x18000ffab  test    eax, eax
0x18000ffad  js      loc_180010057
0x18000ffb3  mov     rcx, rdi; lpFileName
0x18000ffb6  call    ?EnsureDirectoryExists@etl@telemetryutil@@YAJPEBG@Z; telemetryutil::etl::EnsureDirectoryExists(ushort const *)
0x18000ffbb  test    eax, eax
0x18000ffbd  js      loc_180010055
0x18000ffc3  xor     edx, edx; Val
0x18000ffc5  lea     rcx, [rsp+858h+var_818]; void *
0x18000ffca  mov     r8d, 800h; Size
0x18000ffd0  call    memset_0
0x18000ffd5  mov     rdx, cs:off_18001B188; unsigned __int16 *
0x18000ffdc  lea     r8, [rsp+858h+var_818]; unsigned __int16 *
0x18000ffe1  mov     rcx, rdi; unsigned __int16 *
0x18000ffe4  call    ?BuildTraceFilePath@TelemetrySession@etl@telemetryutil@@CAJPEBG0PEAG_K@Z; telemetryutil::etl::TelemetrySession::BuildTraceFilePath(ushort const *,ushort const *,ushort *,unsigned __int64)
0x18000ffe9  test    eax, eax
0x18000ffeb  js      short loc_180010057
0x18000ffed  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000fff1  lea     rcx, InstanceName
0x18000fff8  call    _anonymous_namespace___StopFileTrace
0x18000fffd  lea     r8, [rsp+858h+TraceHandle]
0x180010002  mov     [rsp+858h+TraceHandle], 0FFFFFFFFFFFFFFFFh
0x18001000b  lea     rdx, [rsp+858h+var_818]
0x180010010  call    _anonymous_namespace___StartFileTrace
0x180010015  test    eax, eax
0x180010017  js      short loc_180010055
0x180010019  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010020  mov     ecx, 1050h; unsigned __int64
0x180010025  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001002a  mov     rbx, [rsp+858h+TraceHandle]
0x18001002f  test    rax, rax
0x180010032  jz      short loc_180010078
0x180010034  lea     r9, [rsp+858h+var_818]; unsigned __int16 *
0x180010039  mov     [rsp+858h+var_838], rbx; unsigned __int64
0x18001003e  mov     r8, rdi; unsigned __int16 *
0x180010041  mov     rcx, rax; this
0x180010044  call    ??0TelemetrySession@etl@telemetryutil@@AEAA@AEBUTelemetrySessionSettings@12@PEBG1_K@Z; telemetryutil::etl::TelemetrySession::TelemetrySession(telemetryutil::etl::TelemetrySessionSettings const &,ushort const *,ushort const *,unsigned __int64)
0x180010049  test    rax, rax
0x18001004c  jz      short loc_180010078
0x18001004e  mov     cs:qword_18001BFA8, rax
0x180010055  xor     eax, eax
0x180010057  mov     rcx, [rsp+858h+var_18]
0x18001005f  xor     rcx, rsp; StackCookie
0x180010062  call    __security_check_cookie
0x180010067  mov     rbx, [rsp+858h+arg_8]
0x18001006f  add     rsp, 850h
0x180010076  pop     rdi
0x180010077  retn
0x180010078  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001007c  jz      short loc_180010096
0x18001007e  mov     rdx, rbx
0x180010081  lea     rcx, InstanceName
0x180010088  call    _anonymous_namespace___StopFileTrace
0x18001008d  mov     rcx, rbx; TraceHandle
0x180010090  call    cs:__imp_CloseTrace
0x180010096  mov     eax, 8007000Eh
0x18001009b  jmp     short loc_180010057
```
