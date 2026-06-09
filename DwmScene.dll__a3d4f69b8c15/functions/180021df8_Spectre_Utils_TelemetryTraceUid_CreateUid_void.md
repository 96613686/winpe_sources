# Spectre::Utils::TelemetryTraceUid::CreateUid(void)

- ea: `0x180021df8`
- end: `0x180021eca`
- name: `?CreateUid@TelemetryTraceUid@Utils@Spectre@@SA?AV123@XZ`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800213a8`

## callees

- `0x18000ca90`
- `0x18001c290`
- `0x18001daf4`
- `0x1800215bc`
- `0x180021d18`
- `0x180021df8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180021e28`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180021e28`

## pseudocode

```c
Spectre::Utils::TelemetryTraceUid *__fastcall Spectre::Utils::TelemetryTraceUid::CreateUid(
        Spectre::Utils::TelemetryTraceUid *a1)
{
  GUID *v2; // rax
  GUID pguid; // [rsp+28h] [rbp-58h] BYREF
  GUID rguid; // [rsp+38h] [rbp-48h] BYREF
  GUID v6; // [rsp+48h] [rbp-38h]
  GUID v7; // [rsp+58h] [rbp-28h]
  __int64 v8; // [rsp+68h] [rbp-18h]

  pguid = 0;
  if ( CoCreateGuid(&pguid) )
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsCoreUtils_TelemetryTracing,
      4,
      "Unable to generate a valid, globally unique, GUID");
    Spectre::Utils::TelemetryTraceUid::TelemetryTraceUid(a1);
  }
  else
  {
    v8 = 0;
    rguid = pguid;
    v6 = 0;
    v7 = 0;
    Spectre::Utils::TelemetryTraceUid::Impl::ConvertToCharArray(&rguid);
    v2 = (GUID *)operator new(0x38u);
    if ( v2 )
    {
      *v2 = rguid;
      v2[1] = v6;
      v2[2] = v7;
      *(_QWORD *)&v2[3].Data1 = v8;
    }
    *(_QWORD *)a1 = v2;
  }
  return a1;
}

```

## disassembly

```asm
0x180021df8  mov     [rsp-8+arg_8], rbx
0x180021dfd  push    rbp
0x180021dfe  mov     rbp, rsp
0x180021e01  sub     rsp, 80h
0x180021e08  mov     rax, cs:__security_cookie
0x180021e0f  xor     rax, rsp
0x180021e12  mov     [rbp+var_10], rax
0x180021e16  mov     qword ptr [rbp+pguid.Data1], rcx
0x180021e1a  mov     rbx, rcx
0x180021e1d  xorps   xmm0, xmm0
0x180021e20  lea     rcx, [rbp+pguid]; pguid
0x180021e24  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x180021e28  call    cs:__imp_CoCreateGuid
0x180021e2e  test    eax, eax
0x180021e30  jnz     short loc_180021E8A
0x180021e32  movups  xmm0, xmmword ptr [rbp+pguid.Data1]
0x180021e36  lea     rcx, [rbp+rguid]; rguid
0x180021e3a  xor     eax, eax
0x180021e3c  xorps   xmm1, xmm1
0x180021e3f  mov     [rbp+var_18], rax
0x180021e43  movdqu  xmmword ptr [rbp+rguid.Data1], xmm0
0x180021e48  movups  [rbp+var_38], xmm1
0x180021e4c  movups  [rbp+var_28], xmm1
0x180021e50  call    ?ConvertToCharArray@Impl@TelemetryTraceUid@Utils@Spectre@@AEBAXXZ; Spectre::Utils::TelemetryTraceUid::Impl::ConvertToCharArray(void)
0x180021e55  mov     ecx, 38h ; '8'; unsigned __int64
0x180021e5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021e5f  test    rax, rax
0x180021e62  jz      short loc_180021E85
0x180021e64  movups  xmm0, xmmword ptr [rbp+rguid.Data1]
0x180021e68  movups  xmmword ptr [rax], xmm0
0x180021e6b  movups  xmm1, [rbp+var_38]
0x180021e6f  movups  xmmword ptr [rax+10h], xmm1
0x180021e73  movups  xmm0, [rbp+var_28]
0x180021e77  movups  xmmword ptr [rax+20h], xmm0
0x180021e7b  movsd   xmm1, [rbp+var_18]
0x180021e80  movsd   qword ptr [rax+30h], xmm1
0x180021e85  mov     [rbx], rax
0x180021e88  jmp     short loc_180021EAA
0x180021e8a  lea     r8, aUnableToGenera; "Unable to generate a valid, globally un"...
0x180021e91  mov     edx, 4
0x180021e96  lea     rcx, ?gTraceLevelsCoreUtils_TelemetryTracing@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsCoreUtils_TelemetryTracing
0x180021e9d  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180021ea2  mov     rcx, rbx; this
0x180021ea5  call    ??0TelemetryTraceUid@Utils@Spectre@@AEAA@XZ; Spectre::Utils::TelemetryTraceUid::TelemetryTraceUid(void)
0x180021eaa  mov     rax, rbx
0x180021ead  mov     rcx, [rbp+var_10]
0x180021eb1  xor     rcx, rsp; StackCookie
0x180021eb4  call    __security_check_cookie
0x180021eb9  mov     rbx, [rsp+80h+arg_8]
0x180021ec1  add     rsp, 80h
0x180021ec8  pop     rbp
0x180021ec9  retn
```
