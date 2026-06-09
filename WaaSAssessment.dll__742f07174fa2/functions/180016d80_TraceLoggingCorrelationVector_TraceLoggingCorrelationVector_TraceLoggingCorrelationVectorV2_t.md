# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)

- ea: `0x180016d80`
- end: `0x180016e13`
- name: `??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z`
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

- `RPCRT4!UuidCreate` at `0x180016dac`
- `RPCRT4!UuidCreate` at `0x180016dac`

## pseudocode

```c
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
0x180016d80  push    rbx
0x180016d82  sub     rsp, 40h
0x180016d86  mov     rax, cs:__security_cookie
0x180016d8d  xor     rax, rsp
0x180016d90  mov     [rsp+48h+var_18], rax
0x180016d95  mov     rbx, rcx
0x180016d98  mov     byte ptr [rcx+82h], 81h
0x180016d9f  xorps   xmm0, xmm0
0x180016da2  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180016da7  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180016dac  call    cs:__imp_UuidCreate
0x180016db2  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180016db7  mov     rax, 1900000000h
0x180016dc1  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180016dc7  xor     edx, edx; Val
0x180016dc9  mov     byte ptr [rbx+81h], 17h
0x180016dd0  mov     r8d, 81h; Size
0x180016dd6  mov     rcx, rbx; void *
0x180016dd9  mov     [rbx+88h], rax
0x180016de0  call    memset_0
0x180016de5  mov     r8, rbx
0x180016de8  lea     rcx, [rsp+48h+Uuid]
0x180016ded  mov     edx, 10h
0x180016df2  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180016df7  mov     rax, rbx
0x180016dfa  mov     word ptr [rbx+16h], 2Eh ; '.'
0x180016e00  mov     rcx, [rsp+48h+var_18]
0x180016e05  xor     rcx, rsp; StackCookie
0x180016e08  call    __security_check_cookie
0x180016e0d  add     rsp, 40h
0x180016e11  pop     rbx
0x180016e12  retn
```
