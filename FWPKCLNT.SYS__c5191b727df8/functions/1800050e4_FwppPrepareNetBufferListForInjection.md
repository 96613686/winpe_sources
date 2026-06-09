# FwppPrepareNetBufferListForInjection

- ea: `0x1800050e4`
- end: `0x180005322`
- name: `FwppPrepareNetBufferListForInjection`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002dd8`

## callees

- `0x180004904`
- `0x180004a60`
- `0x1800050e4`
- `0x18000c9b4`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180005118`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800052e6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1800052e6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180005184`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800051c4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180005184`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800051c4`
- `NETIO!NetioDereferenceNetBufferList` at `0x180005311`
- `NETIO!NetioDereferenceNetBufferList` at `0x180005311`
- `NETIO!NetioInitializeNetBufferListContextPrimitive` at `0x180005236`
- `NETIO!NetioInitializeNetBufferListContextPrimitive` at `0x180005236`
- `NETIO!NetioInitializeNetBufferListContext` at `0x18000520c`
- `NETIO!NetioInitializeNetBufferListContext` at `0x18000520c`

## string_xrefs

- `0x18000527e`: `ExAllocateFromNPagedLookasideList`
- `0x1800052ad`: `ExAllocateFromNPagedLookasideList`
- `0x180005296`: `WfpAllocFromNPagedLookasideList`
- `0x1800052c5`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppPrepareNetBufferListForInjection(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v10; // r14
  char v11; // r15
  __int64 PacketInfo; // rax
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rax
  _BYTE *v16; // rsi
  __int64 v17; // rbx
  char v19; // al
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // r15
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax

  v10 = 0;
  v11 = 0;
  PacketInfo = FwppGetPacketInfo(a2);
  v14 = PacketInfo;
  if ( !PacketInfo || (PVOID)PacketInfo == MmBadPointer || *(_QWORD *)(PacketInfo + 328) )
  {
    v15 = WfpReportSysErrorAsNtStatus(v13, (int)"FwppPrepareNetBufferListForInjection", -1071513547);
    v16 = (_BYTE *)(v14 + 368);
    goto LABEL_5;
  }
  v16 = (_BYTE *)(PacketInfo + 368);
  v19 = *(_BYTE *)(PacketInfo + 368);
  *v16 = 1;
  if ( v19 == 1 )
  {
    v15 = WfpReportSysErrorAsNtStatus(v13, (int)"FwppPrepareNetBufferListForInjection", -1071513547);
LABEL_5:
    v17 = v15;
    if ( !v15 )
      return v17;
LABEL_22:
    if ( v10 )
      ExFreeToNPagedLookasideList(&stru_180048500, v10);
    if ( !v11 )
      goto LABEL_26;
    goto LABEL_25;
  }
  v10 = ExAllocateFromNPagedLookasideList(&stru_180048500);
  if ( !v10 )
  {
    v24 = WfpReportSysErrorAsNtStatus(v20, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
    v17 = v24;
    if ( v24 )
    {
      WfpReportError(v24, (int)"WfpAllocFromNPagedLookasideList");
LABEL_25:
      *v16 = 0;
LABEL_26:
      WfpReportError(v17, (int)"FwppPrepareNetBufferListForInjection");
      return v17;
    }
  }
  v10[2] = a4;
  v17 = 0;
  v10[3] = a5;
  *(_DWORD *)v10 = 1768978246;
  v22 = ExAllocateFromNPagedLookasideList(&stru_180048240);
  if ( !v22 )
  {
    v25 = WfpReportSysErrorAsNtStatus(v21, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
    v17 = v25;
    if ( v25 )
    {
      v11 = 1;
      WfpReportError(v25, (int)"WfpAllocFromNPagedLookasideList");
      goto LABEL_22;
    }
  }
  v22[1] = a6;
  v22[2] = a7;
  *v22 = a1;
  if ( *(_DWORD *)(v14 + 4) == 1 )
  {
    NetioInitializeNetBufferListContextPrimitive(a2, *(_QWORD *)(a2 + 24), FwppInjectComplete, v22);
    v23 = *(_QWORD *)(a2 + 24);
    if ( v23 )
      NetioDereferenceNetBufferList(v23, 0);
    if ( a3 )
      *(_QWORD *)(v14 + 336) = 0;
  }
  else
  {
    NetioInitializeNetBufferListContext(a2, 0, FwppInjectComplete, v22);
  }
  *(_DWORD *)(v14 + 176) = 1;
  v10[1] = v14;
  *(_QWORD *)(v14 + 328) = v10;
  return v17;
}

```

## disassembly

```asm
0x1800050e4  mov     [rsp+arg_18], r9
0x1800050e9  push    rbx
0x1800050ea  push    rbp
0x1800050eb  push    rsi
0x1800050ec  push    rdi
0x1800050ed  push    r12
0x1800050ef  push    r13
0x1800050f1  push    r14
0x1800050f3  push    r15
0x1800050f5  sub     rsp, 28h
0x1800050f9  mov     r13, rcx
0x1800050fc  mov     r12b, r8b
0x1800050ff  mov     rcx, rdx
0x180005102  mov     rbp, rdx
0x180005105  xor     r14d, r14d
0x180005108  xor     r15b, r15b
0x18000510b  call    FwppGetPacketInfo
0x180005110  mov     rdi, rax
0x180005113  test    rax, rax
0x180005116  jz      short loc_18000512D
0x180005118  mov     r8, cs:MmBadPointer
0x18000511f  cmp     rax, [r8]
0x180005122  jz      short loc_18000512D
0x180005124  cmp     [rax+148h], r14
0x18000512b  jz      short loc_180005167
0x18000512d  mov     r8d, 0C0220035h
0x180005133  lea     rdx, aFwpppreparenet; "FwppPrepareNetBufferListForInjection"
0x18000513a  call    WfpReportSysErrorAsNtStatus
0x18000513f  lea     rsi, [rdi+170h]
0x180005146  mov     rbx, rax
0x180005149  test    rax, rax
0x18000514c  jnz     loc_1800052D7
0x180005152  mov     rax, rbx
0x180005155  add     rsp, 28h
0x180005159  pop     r15
0x18000515b  pop     r14
0x18000515d  pop     r13
0x18000515f  pop     r12
0x180005161  pop     rdi
0x180005162  pop     rsi
0x180005163  pop     rbp
0x180005164  pop     rbx
0x180005165  retn
0x180005167  lea     rsi, [rax+170h]
0x18000516e  mov     eax, 1
0x180005173  xchg    al, [rsi]
0x180005175  cmp     al, 1
0x180005177  jz      loc_180005261
0x18000517d  lea     rcx, stru_180048500; Lookaside
0x180005184  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000518b  nop     dword ptr [rax+rax+00h]
0x180005190  mov     r14, rax
0x180005193  test    rax, rax
0x180005196  jz      loc_180005278
0x18000519c  mov     rax, [rsp+68h+arg_18]
0x1800051a4  lea     rcx, stru_180048240; Lookaside
0x1800051ab  mov     [r14+10h], rax
0x1800051af  xor     ebx, ebx
0x1800051b1  mov     rax, [rsp+68h+arg_20]
0x1800051b9  mov     [r14+18h], rax
0x1800051bd  mov     dword ptr [r14], 69707746h
0x1800051c4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1800051cb  nop     dword ptr [rax+rax+00h]
0x1800051d0  mov     r15, rax
0x1800051d3  test    rax, rax
0x1800051d6  jz      loc_1800052A7
0x1800051dc  mov     rax, [rsp+68h+arg_28]
0x1800051e4  lea     r8, FwppInjectComplete
0x1800051eb  mov     [r15+8], rax
0x1800051ef  mov     r9, r15
0x1800051f2  mov     rax, [rsp+68h+arg_30]
0x1800051fa  mov     rcx, rbp
0x1800051fd  mov     [r15+10h], rax
0x180005201  mov     [r15], r13
0x180005204  cmp     dword ptr [rdi+4], 1
0x180005208  jz      short loc_180005232
0x18000520a  xor     edx, edx
0x18000520c  call    cs:__imp_NetioInitializeNetBufferListContext
0x180005213  nop     dword ptr [rax+rax+00h]
0x180005218  mov     dword ptr [rdi+0B0h], 1
0x180005222  mov     [r14+8], rdi
0x180005226  mov     [rdi+148h], r14
0x18000522d  jmp     loc_180005152
0x180005232  mov     rdx, [rbp+18h]
0x180005236  call    cs:__imp_NetioInitializeNetBufferListContextPrimitive
0x18000523d  nop     dword ptr [rax+rax+00h]
0x180005242  mov     rcx, [rbp+18h]
0x180005246  test    rcx, rcx
0x180005249  jnz     loc_18000530F
0x18000524f  test    r12b, r12b
0x180005252  jz      short loc_180005218
0x180005254  mov     qword ptr [rdi+150h], 0
0x18000525f  jmp     short loc_180005218
0x180005261  mov     r8d, 0C0220035h
0x180005267  lea     rdx, aFwpppreparenet; "FwppPrepareNetBufferListForInjection"
0x18000526e  call    WfpReportSysErrorAsNtStatus
0x180005273  jmp     loc_180005146
0x180005278  mov     r8d, 0C0000017h
0x18000527e  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180005285  call    WfpReportSysErrorAsNtStatus
0x18000528a  mov     rbx, rax
0x18000528d  test    rax, rax
0x180005290  jz      loc_18000519C
0x180005296  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x18000529d  mov     rcx, rax
0x1800052a0  call    WfpReportError
0x1800052a5  jmp     short loc_1800052F7
0x1800052a7  mov     r8d, 0C0000017h
0x1800052ad  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x1800052b4  call    WfpReportSysErrorAsNtStatus
0x1800052b9  mov     rbx, rax
0x1800052bc  test    rax, rax
0x1800052bf  jz      loc_1800051DC
0x1800052c5  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x1800052cc  mov     rcx, rax
0x1800052cf  mov     r15b, 1
0x1800052d2  call    WfpReportError
0x1800052d7  test    r14, r14
0x1800052da  jz      short loc_1800052F2
0x1800052dc  mov     rdx, r14; Entry
0x1800052df  lea     rcx, stru_180048500; Lookaside
0x1800052e6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1800052ed  nop     dword ptr [rax+rax+00h]
0x1800052f2  test    r15b, r15b
0x1800052f5  jz      short loc_1800052FB
0x1800052f7  xor     eax, eax
0x1800052f9  xchg    al, [rsi]
0x1800052fb  lea     rdx, aFwpppreparenet; "FwppPrepareNetBufferListForInjection"
0x180005302  mov     rcx, rbx
0x180005305  call    WfpReportError
0x18000530a  jmp     loc_180005152
0x18000530f  xor     edx, edx
0x180005311  call    cs:__imp_NetioDereferenceNetBufferList
0x180005318  nop     dword ptr [rax+rax+00h]
0x18000531d  jmp     loc_18000524F
```
