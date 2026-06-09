# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x180005398`
- end: `0x180005426`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `142`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800052d4`

## callees

- `0x180003fc0`
- `0x180004b78`
- `0x180005234`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800053c4`
- `RPCRT4!UuidCreate` at `0x1800053c4`

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
0x180005398  push    rbx
0x18000539a  sub     rsp, 40h
0x18000539e  mov     rax, cs:__security_cookie
0x1800053a5  xor     rax, rsp
0x1800053a8  mov     [rsp+48h+var_18], rax
0x1800053ad  mov     rbx, rcx
0x1800053b0  mov     byte ptr [rcx+82h], 41h ; 'A'
0x1800053b7  xorps   xmm0, xmm0
0x1800053ba  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800053bf  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800053c4  call    cs:__imp_UuidCreate
0x1800053ca  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800053cf  mov     rax, 1300000000h
0x1800053d9  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800053df  xor     edx, edx; Val
0x1800053e1  mov     byte ptr [rbx+81h], 11h
0x1800053e8  mov     r8d, 81h; Size
0x1800053ee  mov     rcx, rbx; void *
0x1800053f1  mov     [rbx+88h], rax
0x1800053f8  call    memset_0
0x1800053fd  mov     r8, rbx
0x180005400  lea     rcx, [rsp+48h+Uuid]
0x180005405  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18000540a  mov     rax, rbx
0x18000540d  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180005413  mov     rcx, [rsp+48h+var_18]
0x180005418  xor     rcx, rsp; StackCookie
0x18000541b  call    __security_check_cookie
0x180005420  add     rsp, 40h
0x180005424  pop     rbx
0x180005425  retn
```
