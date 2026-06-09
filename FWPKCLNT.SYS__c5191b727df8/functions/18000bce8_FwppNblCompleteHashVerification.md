# FwppNblCompleteHashVerification

- ea: `0x18000bce8`
- end: `0x18000be41`
- name: `FwppNblCompleteHashVerification`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180007fd0`

## callees

- `0x180004904`
- `0x180008190`
- `0x18000bce8`
- `0x18000be48`
- `0x18000becc`
- `0x18000bf9c`
- `0x18000bffc`
- `0x18001ebd0`
- `0x18001f8e4`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x18000bdad`
- `ntoskrnl!DbgPrintEx` at `0x18000bdf7`
- `ntoskrnl!DbgPrintEx` at `0x18000bdad`
- `ntoskrnl!DbgPrintEx` at `0x18000bdf7`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18000bd96`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18000bde0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000be27`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000be27`

## string_xrefs

- `0x18000bd18`: `FwppInjectComplete`
- `0x18000bdec`: `Special Pool Hash Verification, found a corruption in the injected nbl Clone. This means during stream injection an immutable part of the nbl was modified after being injected with the FwpsStreamInjectAsync API.`
- `0x18000bda2`: `Special Pool Hash Verification, Found a corruption in the original Special Pool nbl Clone. This means another function acted on the nbl clone while the clone was being process by Stream. Use !stacks to see what other threads could be acting on the nbl clone.`

## pseudocode

```c
void __fastcall FwppNblCompleteHashVerification(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  v2 = 0;
  v12 = 0;
  v13 = 0;
  v4 = FwppSpecialPoolRemoveFromHashList();
  v7 = v4;
  if ( v4 )
  {
    v8 = *(_QWORD *)(v4 + 16);
    if ( v8 )
    {
      FwppComputeHashForNbl(v8, &v12);
      v1 = v12;
    }
    if ( a1 )
    {
      FwppComputeHashForNbl(a1, &v13);
      v2 = v13;
    }
    WfpReportSpecialPoolHashTrace(v8, v5, *(_QWORD *)(v7 + 32), *(_QWORD *)(v7 + 40), v1, v2);
    if ( *(_QWORD *)(v7 + 32) != v1 )
    {
      WfpReportSpecialPoolNblsTrace(v9, *(_QWORD *)(v7 + 16), a1, *(_QWORD *)(a1 + 24));
      if ( *(_QWORD *)(v7 + 32) != v1 )
        MicrosoftTelemetryAssertTriggeredArgsKM(v10, *(unsigned int *)(v7 + 32), (unsigned int)v1);
      if ( !(_BYTE)KdDebuggerNotPresent )
      {
        DbgPrintEx(
          0,
          0,
          "Special Pool Hash Verification, Found a corruption in the original Special Pool nbl Clone. This means another "
          "function acted on the nbl clone while the clone was being process by Stream. Use !stacks to see what other thr"
          "eads could be acting on the nbl clone.");
        __debugbreak();
      }
      WfpNblVerifierBreak(v10, *(_QWORD *)(v7 + 16), a1, *(_QWORD *)(a1 + 24));
    }
    if ( *(_QWORD *)(v7 + 40) != v2 )
    {
      WfpReportSpecialPoolNblsTrace(v9, *(_QWORD *)(v7 + 24), a1, *(_QWORD *)(a1 + 24));
      if ( !(_BYTE)KdDebuggerNotPresent )
      {
        DbgPrintEx(
          0,
          0,
          "Special Pool Hash Verification, found a corruption in the injected nbl Clone. This means during stream injecti"
          "on an immutable part of the nbl was modified after being injected with the FwpsStreamInjectAsync API.");
        __debugbreak();
      }
      WfpNblVerifierBreak(v11, *(_QWORD *)(v7 + 24), a1, *(_QWORD *)(a1 + 24));
    }
    FwpsDiscardClonedStreamData0(*(NET_BUFFER_LIST **)(v7 + 16), 0, 1u);
    ExFreePoolWithTag((PVOID)v7, 0);
  }
  else
  {
    WfpReportSysErrorAsNtStatus(v6, (int)"FwppInjectComplete", -1073741801);
  }
}

```

## disassembly

```asm
0x18000bce8  mov     [rsp+arg_0], rbx
0x18000bced  push    rbp
0x18000bcee  push    rsi
0x18000bcef  push    rdi
0x18000bcf0  sub     rsp, 30h
0x18000bcf4  xor     ebx, ebx
0x18000bcf6  xor     edi, edi
0x18000bcf8  mov     [rsp+48h+arg_8], rbx
0x18000bcfd  mov     rbp, rcx
0x18000bd00  mov     [rsp+48h+arg_10], rdi
0x18000bd05  call    FwppSpecialPoolRemoveFromHashList
0x18000bd0a  mov     rsi, rax
0x18000bd0d  test    rax, rax
0x18000bd10  jnz     short loc_18000BD29
0x18000bd12  mov     r8d, 0C0000017h
0x18000bd18  lea     rdx, aFwppinjectcomp; "FwppInjectComplete"
0x18000bd1f  call    WfpReportSysErrorAsNtStatus
0x18000bd24  jmp     loc_18000BE33
0x18000bd29  mov     rcx, [rax+10h]
0x18000bd2d  test    rcx, rcx
0x18000bd30  jz      short loc_18000BD41
0x18000bd32  lea     rdx, [rsp+48h+arg_8]
0x18000bd37  call    FwppComputeHashForNbl
0x18000bd3c  mov     rbx, [rsp+48h+arg_8]
0x18000bd41  test    rbp, rbp
0x18000bd44  jz      short loc_18000BD58
0x18000bd46  lea     rdx, [rsp+48h+arg_10]
0x18000bd4b  mov     rcx, rbp
0x18000bd4e  call    FwppComputeHashForNbl
0x18000bd53  mov     rdi, [rsp+48h+arg_10]
0x18000bd58  mov     r9, [rsi+28h]
0x18000bd5c  mov     r8, [rsi+20h]
0x18000bd60  mov     [rsp+48h+var_20], rdi
0x18000bd65  mov     [rsp+48h+var_28], rbx
0x18000bd6a  call    WfpReportSpecialPoolHashTrace
0x18000bd6f  cmp     [rsi+20h], rbx
0x18000bd73  jz      short loc_18000BDCA
0x18000bd75  mov     r9, [rbp+18h]
0x18000bd79  mov     r8, rbp
0x18000bd7c  mov     rdx, [rsi+10h]
0x18000bd80  call    WfpReportSpecialPoolNblsTrace
0x18000bd85  cmp     [rsi+20h], rbx
0x18000bd89  jz      short loc_18000BD96
0x18000bd8b  mov     edx, [rsi+20h]
0x18000bd8e  mov     r8d, ebx
0x18000bd91  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x18000bd96  mov     rax, cs:KdDebuggerNotPresent
0x18000bd9d  cmp     byte ptr [rax], 0
0x18000bda0  jnz     short loc_18000BDBA
0x18000bda2  lea     r8, Format; "Special Pool Hash Verification, Found a"...
0x18000bda9  xor     edx, edx; Level
0x18000bdab  xor     ecx, ecx; ComponentId
0x18000bdad  call    cs:__imp_DbgPrintEx
0x18000bdb4  nop     dword ptr [rax+rax+00h]
0x18000bdb9  int     3; Trap to Debugger
0x18000bdba  mov     r9, [rbp+18h]
0x18000bdbe  mov     r8, rbp
0x18000bdc1  mov     rdx, [rsi+10h]
0x18000bdc5  call    WfpNblVerifierBreak
0x18000bdca  cmp     [rsi+28h], rdi
0x18000bdce  jz      short loc_18000BE14
0x18000bdd0  mov     r9, [rbp+18h]
0x18000bdd4  mov     r8, rbp
0x18000bdd7  mov     rdx, [rsi+18h]
0x18000bddb  call    WfpReportSpecialPoolNblsTrace
0x18000bde0  mov     rax, cs:KdDebuggerNotPresent
0x18000bde7  cmp     byte ptr [rax], 0
0x18000bdea  jnz     short loc_18000BE04
0x18000bdec  lea     r8, aSpecialPoolHas; "Special Pool Hash Verification, found a"...
0x18000bdf3  xor     edx, edx; Level
0x18000bdf5  xor     ecx, ecx; ComponentId
0x18000bdf7  call    cs:__imp_DbgPrintEx
0x18000bdfe  nop     dword ptr [rax+rax+00h]
0x18000be03  int     3; Trap to Debugger
0x18000be04  mov     r9, [rbp+18h]
0x18000be08  mov     r8, rbp
0x18000be0b  mov     rdx, [rsi+18h]
0x18000be0f  call    WfpNblVerifierBreak
0x18000be14  mov     rcx, [rsi+10h]; netBufferListChain
0x18000be18  mov     r8b, 1; dispatchLevel
0x18000be1b  xor     edx, edx; allocateCloneFlags
0x18000be1d  call    FwpsDiscardClonedStreamData0
0x18000be22  xor     edx, edx; Tag
0x18000be24  mov     rcx, rsi; P
0x18000be27  call    cs:__imp_ExFreePoolWithTag
0x18000be2e  nop     dword ptr [rax+rax+00h]
0x18000be33  mov     rbx, [rsp+48h+arg_0]
0x18000be38  add     rsp, 30h
0x18000be3c  pop     rdi
0x18000be3d  pop     rsi
0x18000be3e  pop     rbp
0x18000be3f  retn
```
