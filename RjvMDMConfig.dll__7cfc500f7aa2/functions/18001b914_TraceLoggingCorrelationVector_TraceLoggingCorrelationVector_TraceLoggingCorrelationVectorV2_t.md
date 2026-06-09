# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x18001b914`
- end: `0x18001b97b`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c220`

## callees

- `0x180001c60`
- `0x18001b8a0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001b940`
- `RPCRT4!UuidCreate` at `0x18001b940`

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
0x18001b914  push    rbx
0x18001b916  sub     rsp, 50h
0x18001b91a  mov     rax, cs:__security_cookie
0x18001b921  xor     rax, rsp
0x18001b924  mov     [rsp+58h+var_18], rax
0x18001b929  mov     rbx, rcx
0x18001b92c  mov     byte ptr [rcx+82h], 81h
0x18001b933  xorps   xmm0, xmm0
0x18001b936  lea     rcx, [rsp+58h+Uuid]; Uuid
0x18001b93b  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x18001b940  call    cs:__imp_UuidCreate
0x18001b947  nop     dword ptr [rax+rax+00h]
0x18001b94c  movaps  xmm0, xmmword ptr [rsp+58h+Uuid.Data1]
0x18001b951  lea     rdx, [rsp+58h+var_38]
0x18001b956  mov     rcx, rbx
0x18001b959  movdqa  [rsp+58h+var_38], xmm0
0x18001b95f  call    ??$CreateCvFromGuid@$0BA@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<16>(_GUID)
0x18001b964  mov     rax, rbx
0x18001b967  mov     rcx, [rsp+58h+var_18]
0x18001b96c  xor     rcx, rsp; StackCookie
0x18001b96f  call    __security_check_cookie
0x18001b974  add     rsp, 50h
0x18001b978  pop     rbx
0x18001b979  retn
```
