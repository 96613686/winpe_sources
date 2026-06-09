# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x1400176f4`
- end: `0x140017754`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018060`

## callees

- `0x140002930`
- `0x140017680`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140017720`
- `RPCRT4!UuidCreate` at `0x140017720`

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
  TraceLoggingCorrelationVector::CreateCvFromGuid<16>(a1, (__int128 *)&v3);
  return a1;
}

```

## disassembly

```asm
0x1400176f4  push    rbx
0x1400176f6  sub     rsp, 50h
0x1400176fa  mov     rax, cs:__security_cookie
0x140017701  xor     rax, rsp
0x140017704  mov     [rsp+58h+var_18], rax
0x140017709  mov     rbx, rcx
0x14001770c  mov     byte ptr [rcx+82h], 81h
0x140017713  xorps   xmm0, xmm0
0x140017716  lea     rcx, [rsp+58h+Uuid]; Uuid
0x14001771b  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x140017720  call    cs:__imp_UuidCreate
0x140017726  movaps  xmm0, xmmword ptr [rsp+58h+Uuid.Data1]
0x14001772b  lea     rdx, [rsp+58h+var_38]
0x140017730  mov     rcx, rbx
0x140017733  movdqa  [rsp+58h+var_38], xmm0
0x140017739  call    ??$CreateCvFromGuid@$0BA@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<16>(_GUID)
0x14001773e  mov     rax, rbx
0x140017741  mov     rcx, [rsp+58h+var_18]
0x140017746  xor     rcx, rsp; StackCookie
0x140017749  call    __security_check_cookie
0x14001774e  add     rsp, 50h
0x140017752  pop     rbx
0x140017753  retn
```
