# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x180021600`
- end: `0x180021664`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002241c`
- `0x1800237bc`

## callees

- `0x18000ca90`
- `0x180021318`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180021630`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180021630`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  GUID v3; // [rsp+20h] [rbp-38h] BYREF
  GUID pguid; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)(a1 + 152) = 64;
  pguid = 0;
  CoCreateGuid(&pguid);
  v3 = pguid;
  TraceLoggingCorrelationVector::CreateCvFromGuid<12>(a1, &v3);
  return a1;
}

```

## disassembly

```asm
0x180021600  push    rbx
0x180021602  sub     rsp, 50h
0x180021606  mov     rax, cs:__security_cookie
0x18002160d  xor     rax, rsp
0x180021610  mov     [rsp+58h+var_18], rax
0x180021615  mov     rbx, rcx
0x180021618  mov     qword ptr [rcx+98h], 40h ; '@'
0x180021623  xorps   xmm0, xmm0
0x180021626  lea     rcx, [rsp+58h+pguid]; pguid
0x18002162b  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x180021630  call    cs:__imp_CoCreateGuid
0x180021636  movaps  xmm0, xmmword ptr [rsp+58h+pguid.Data1]
0x18002163b  lea     rdx, [rsp+58h+var_38]
0x180021640  mov     rcx, rbx
0x180021643  movdqa  [rsp+58h+var_38], xmm0
0x180021649  call    ??$CreateCvFromGuid@$0M@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<12>(_GUID)
0x18002164e  mov     rax, rbx
0x180021651  mov     rcx, [rsp+58h+var_18]
0x180021656  xor     rcx, rsp; StackCookie
0x180021659  call    __security_check_cookie
0x18002165e  add     rsp, 50h
0x180021662  pop     rbx
0x180021663  retn
```
