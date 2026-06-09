# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x1800122f0`
- end: `0x18001237e`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `142`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011f80`

## callees

- `0x180003a60`
- `0x1800045d8`
- `0x18000f9f8`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001231c`
- `RPCRT4!UuidCreate` at `0x18001231c`

## pseudocode

```c
TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(
        TraceLoggingCorrelationVector *this)
{
  __int64 v2; // rdx
  TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *((_BYTE *)this + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  *((_BYTE *)this + 129) = 17;
  *((_QWORD *)this + 17) = 0x1300000000LL;
  memset_0(this, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, v2, this);
  result = this;
  *((_WORD *)this + 8) = 46;
  return result;
}

```

## disassembly

```asm
0x1800122f0  push    rbx
0x1800122f2  sub     rsp, 40h
0x1800122f6  mov     rax, cs:__security_cookie
0x1800122fd  xor     rax, rsp
0x180012300  mov     [rsp+48h+var_18], rax
0x180012305  mov     rbx, rcx
0x180012308  mov     byte ptr [rcx+82h], 41h ; 'A'
0x18001230f  xorps   xmm0, xmm0
0x180012312  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180012317  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18001231c  call    cs:__imp_UuidCreate
0x180012322  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180012327  mov     rax, 1300000000h
0x180012331  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180012337  xor     edx, edx; Val
0x180012339  mov     byte ptr [rbx+81h], 11h
0x180012340  mov     r8d, 81h; Size
0x180012346  mov     rcx, rbx; void *
0x180012349  mov     [rbx+88h], rax
0x180012350  call    memset_0
0x180012355  mov     r8, rbx
0x180012358  lea     rcx, [rsp+48h+Uuid]
0x18001235d  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180012362  mov     rax, rbx
0x180012365  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18001236b  mov     rcx, [rsp+48h+var_18]
0x180012370  xor     rcx, rsp; StackCookie
0x180012373  call    __security_check_cookie
0x180012378  add     rsp, 40h
0x18001237c  pop     rbx
0x18001237d  retn
```
