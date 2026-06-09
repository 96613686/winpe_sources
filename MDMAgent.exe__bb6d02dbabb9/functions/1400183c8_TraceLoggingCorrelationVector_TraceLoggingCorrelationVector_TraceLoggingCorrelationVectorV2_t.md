# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x1400183c8`
- end: `0x14001842f`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018d74`

## callees

- `0x1400029c0`
- `0x140018354`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1400183f4`
- `RPCRT4!UuidCreate` at `0x1400183f4`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  UUID v3; // [rsp+20h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF

  *(_BYTE *)(a1 + 130) = -127;
  Uuid = 0;
  UuidCreate(&Uuid);
  v3 = Uuid;
  TraceLoggingCorrelationVector::CreateCvFromGuid<16>(a1, &v3);
  return a1;
}

```

## disassembly

```asm
0x1400183c8  push    rbx
0x1400183ca  sub     rsp, 50h
0x1400183ce  mov     rax, cs:__security_cookie
0x1400183d5  xor     rax, rsp
0x1400183d8  mov     [rsp+58h+var_18], rax
0x1400183dd  mov     rbx, rcx
0x1400183e0  mov     byte ptr [rcx+82h], 81h
0x1400183e7  xorps   xmm0, xmm0
0x1400183ea  lea     rcx, [rsp+58h+Uuid]; Uuid
0x1400183ef  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x1400183f4  call    cs:__imp_UuidCreate
0x1400183fb  nop     dword ptr [rax+rax+00h]
0x140018400  movaps  xmm0, xmmword ptr [rsp+58h+Uuid.Data1]
0x140018405  lea     rdx, [rsp+58h+var_38]
0x14001840a  mov     rcx, rbx
0x14001840d  movdqa  [rsp+58h+var_38], xmm0
0x140018413  call    ??$CreateCvFromGuid@$0BA@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<16>(_GUID)
0x140018418  mov     rax, rbx
0x14001841b  mov     rcx, [rsp+58h+var_18]
0x140018420  xor     rcx, rsp; StackCookie
0x140018423  call    __security_check_cookie
0x140018428  add     rsp, 50h
0x14001842c  pop     rbx
0x14001842d  retn
```
