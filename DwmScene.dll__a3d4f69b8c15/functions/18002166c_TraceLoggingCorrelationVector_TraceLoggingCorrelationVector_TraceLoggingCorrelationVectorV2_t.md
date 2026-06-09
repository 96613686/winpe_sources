# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x18002166c`
- end: `0x1800216d0`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
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
- `0x18002129c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002169c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002169c`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  GUID v3; // [rsp+20h] [rbp-38h] BYREF
  GUID pguid; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)(a1 + 152) = 127;
  pguid = 0;
  CoCreateGuid(&pguid);
  v3 = pguid;
  TraceLoggingCorrelationVector::CreateCvFromGuid<16>(a1, &v3);
  return a1;
}

```

## disassembly

```asm
0x18002166c  push    rbx
0x18002166e  sub     rsp, 50h
0x180021672  mov     rax, cs:__security_cookie
0x180021679  xor     rax, rsp
0x18002167c  mov     [rsp+58h+var_18], rax
0x180021681  mov     rbx, rcx
0x180021684  mov     qword ptr [rcx+98h], 7Fh
0x18002168f  xorps   xmm0, xmm0
0x180021692  lea     rcx, [rsp+58h+pguid]; pguid
0x180021697  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x18002169c  call    cs:__imp_CoCreateGuid
0x1800216a2  movaps  xmm0, xmmword ptr [rsp+58h+pguid.Data1]
0x1800216a7  lea     rdx, [rsp+58h+var_38]
0x1800216ac  mov     rcx, rbx
0x1800216af  movdqa  [rsp+58h+var_38], xmm0
0x1800216b5  call    ??$CreateCvFromGuid@$0BA@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<16>(_GUID)
0x1800216ba  mov     rax, rbx
0x1800216bd  mov     rcx, [rsp+58h+var_18]
0x1800216c2  xor     rcx, rsp; StackCookie
0x1800216c5  call    __security_check_cookie
0x1800216ca  add     rsp, 50h
0x1800216ce  pop     rbx
0x1800216cf  retn
```
