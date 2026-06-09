# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV1_t)

- ea: `0x180016ce4`
- end: `0x180016d77`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV1_t@@@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016e1c`
- `0x180017a98`

## callees

- `0x180016b60`
- `0x18001972e`
- `0x180019760`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180016d10`
- `RPCRT4!UuidCreate` at `0x180016d10`

## pseudocode

```c
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
0x180016ce4  push    rbx
0x180016ce6  sub     rsp, 40h
0x180016cea  mov     rax, cs:__security_cookie
0x180016cf1  xor     rax, rsp
0x180016cf4  mov     [rsp+48h+var_18], rax
0x180016cf9  mov     rbx, rcx
0x180016cfc  mov     byte ptr [rcx+82h], 41h ; 'A'
0x180016d03  xorps   xmm0, xmm0
0x180016d06  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180016d0b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180016d10  call    cs:__imp_UuidCreate
0x180016d16  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180016d1b  mov     rax, 1300000000h
0x180016d25  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180016d2b  xor     edx, edx; Val
0x180016d2d  mov     byte ptr [rbx+81h], 11h
0x180016d34  mov     r8d, 81h; Size
0x180016d3a  mov     rcx, rbx; void *
0x180016d3d  mov     [rbx+88h], rax
0x180016d44  call    memset_0
0x180016d49  mov     r8, rbx
0x180016d4c  lea     rcx, [rsp+48h+Uuid]
0x180016d51  mov     edx, 0Ch
0x180016d56  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180016d5b  mov     rax, rbx
0x180016d5e  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180016d64  mov     rcx, [rsp+48h+var_18]
0x180016d69  xor     rcx, rsp; StackCookie
0x180016d6c  call    __security_check_cookie
0x180016d71  add     rsp, 40h
0x180016d75  pop     rbx
0x180016d76  retn
```
