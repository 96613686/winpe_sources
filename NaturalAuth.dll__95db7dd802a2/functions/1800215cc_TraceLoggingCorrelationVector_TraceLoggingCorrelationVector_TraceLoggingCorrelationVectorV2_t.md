# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x1800215cc`
- end: `0x18002165f`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
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

- `RPCRT4!UuidCreate` at `0x1800215f8`
- `RPCRT4!UuidCreate` at `0x1800215f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(__int64 a1)
{
  __int64 result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *(_BYTE *)(a1 + 130) = -127;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(_BYTE *)(a1 + 129) = 23;
  *(_QWORD *)(a1 + 136) = 0x1900000000LL;
  memset_0((void *)a1, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, 16, a1);
  result = a1;
  *(_WORD *)(a1 + 22) = 46;
  return result;
}

```

## disassembly

```asm
0x1800215cc  push    rbx
0x1800215ce  sub     rsp, 40h
0x1800215d2  mov     rax, cs:__security_cookie
0x1800215d9  xor     rax, rsp
0x1800215dc  mov     [rsp+48h+var_18], rax
0x1800215e1  mov     rbx, rcx
0x1800215e4  mov     byte ptr [rcx+82h], 81h
0x1800215eb  xorps   xmm0, xmm0
0x1800215ee  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800215f3  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800215f8  call    cs:__imp_UuidCreate
0x1800215fe  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180021603  mov     rax, 1900000000h
0x18002160d  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180021613  xor     edx, edx; Val
0x180021615  mov     byte ptr [rbx+81h], 17h
0x18002161c  mov     r8d, 81h; Size
0x180021622  mov     rcx, rbx; void *
0x180021625  mov     [rbx+88h], rax
0x18002162c  call    memset_0
0x180021631  mov     r8, rbx
0x180021634  lea     rcx, [rsp+48h+Uuid]
0x180021639  mov     edx, 10h
0x18002163e  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180021643  mov     rax, rbx
0x180021646  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18002164c  mov     rcx, [rsp+48h+var_18]
0x180021651  xor     rcx, rsp; StackCookie
0x180021654  call    __security_check_cookie
0x180021659  add     rsp, 40h
0x18002165d  pop     rbx
0x18002165e  retn
```
