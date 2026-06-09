# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x180021530`
- end: `0x1800215c3`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800217c8`

## callees

- `0x180004170`
- `0x180005140`
- `0x180021368`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002155c`
- `RPCRT4!UuidCreate` at `0x18002155c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  __int64 result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *(_BYTE *)(a1 + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(_BYTE *)(a1 + 129) = 17;
  *(_QWORD *)(a1 + 136) = 0x1300000000LL;
  memset_0((void *)a1, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 12, a1);
  result = a1;
  *(_WORD *)(a1 + 16) = 46;
  return result;
}

```

## disassembly

```asm
0x180021530  push    rbx
0x180021532  sub     rsp, 40h
0x180021536  mov     rax, cs:__security_cookie
0x18002153d  xor     rax, rsp
0x180021540  mov     [rsp+48h+var_18], rax
0x180021545  mov     rbx, rcx
0x180021548  mov     byte ptr [rcx+82h], 41h ; 'A'
0x18002154f  xorps   xmm0, xmm0
0x180021552  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180021557  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18002155c  call    cs:__imp_UuidCreate
0x180021562  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180021567  mov     rax, 1300000000h
0x180021571  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180021577  xor     edx, edx; Val
0x180021579  mov     byte ptr [rbx+81h], 11h
0x180021580  mov     r8d, 81h; Size
0x180021586  mov     rcx, rbx; void *
0x180021589  mov     [rbx+88h], rax
0x180021590  call    memset_0
0x180021595  mov     r8, rbx
0x180021598  lea     rcx, [rsp+48h+Uuid]
0x18002159d  mov     edx, 0Ch
0x1800215a2  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800215a7  mov     rax, rbx
0x1800215aa  mov     word ptr [rbx+10h], 2Eh ; '.'
0x1800215b0  mov     rcx, [rsp+48h+var_18]
0x1800215b5  xor     rcx, rsp; StackCookie
0x1800215b8  call    __security_check_cookie
0x1800215bd  add     rsp, 40h
0x1800215c1  pop     rbx
0x1800215c2  retn
```
