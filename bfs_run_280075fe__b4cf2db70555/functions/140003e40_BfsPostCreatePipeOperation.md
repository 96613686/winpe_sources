# BfsPostCreatePipeOperation

- ea: `0x140003e40`
- end: `0x140004113`
- name: `BfsPostCreatePipeOperation`
- size: `723`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001008`
- `0x140003e40`
- `0x14000b4c4`
- `0x14000bd0c`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14000408d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000408d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004028`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004039`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000404b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000405d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000406e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004028`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004039`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000404b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000405d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000406e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000407a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000407a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004099`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004099`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400040c9`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400040c9`
- `FLTMGR!FltReleaseContext` at `0x140004008`
- `FLTMGR!FltReleaseContext` at `0x140004008`
- `FLTMGR!FltAllocateContext` at `0x140003f6d`
- `FLTMGR!FltAllocateContext` at `0x140003f6d`
- `FLTMGR!FltSetStreamHandleContext` at `0x140003fba`
- `FLTMGR!FltSetStreamHandleContext` at `0x140003fba`
- `FLTMGR!FltCancelFileOpen` at `0x1400040dd`
- `FLTMGR!FltCancelFileOpen` at `0x1400040dd`

## pseudocode

```c
__int64 __fastcall BfsPostCreatePipeOperation(PFLT_CALLBACK_DATA Data, __int64 a2, PVOID *a3, __int64 a4)
{
  __int64 v7; // r14
  int Status; // ebx
  char v9; // r12
  PVOID *v10; // rdi
  int inserted; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int ReturnedContext; // [rsp+20h] [rbp-59h]
  int ReturnedContexta; // [rsp+20h] [rbp-59h]
  int ReturnedContextb; // [rsp+20h] [rbp-59h]
  int v22; // [rsp+44h] [rbp-35h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+48h] [rbp-31h] BYREF
  __int64 v24; // [rsp+50h] [rbp-29h]
  PFLT_CONTEXT OldContext; // [rsp+58h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+60h] [rbp-19h] BYREF
  int *v27; // [rsp+80h] [rbp+7h]
  __int64 v28; // [rsp+88h] [rbp+Fh]

  OldContext = 0;
  v7 = 0;
  v24 = 0;
  Status = Data->IoStatus.Status;
  NewContext = 0;
  if ( Status < 0 )
  {
    v9 = 0;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v22 = Status;
      v27 = &v22;
      v28 = 4;
      tlgWriteTransfer_EtwWriteTransfer(0, (unsigned __int8 *)&byte_140016D91, (__int64)a3, a4, ReturnedContext, &v26);
    }
    v10 = a3 + 1;
    goto LABEL_17;
  }
  if ( !a3 )
    return 0;
  v9 = 1;
  v10 = a3 + 1;
  ReturnedContexta = (_DWORD)a3 + 32;
  inserted = BfsInsertNamedPipeMapping(&gBfsPipeMappingTable, *a3, a3[1], a3 + 2);
  Status = inserted;
  if ( inserted >= 0 )
  {
    Status = FltAllocateContext(*(PFLT_FILTER *)(a2 + 8), 0x10u, 0x10u, PagedPool, &NewContext);
    if ( Status >= 0 )
    {
      v7 = v24;
      *(_DWORD *)NewContext = 1;
      *((_QWORD *)NewContext + 1) = v7;
      Status = FltSetStreamHandleContext(
                 *(PFLT_INSTANCE *)(a2 + 24),
                 *(PFILE_OBJECT *)(a2 + 32),
                 FLT_SET_CONTEXT_REPLACE_IF_EXISTS,
                 NewContext,
                 &OldContext);
      if ( Status < 0 && (unsigned int)dword_140019000 > 3 )
      {
        v22 = Status;
        v27 = &v22;
        v28 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v16, v17, ReturnedContextb, &v26);
      }
      goto LABEL_17;
    }
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_10;
    v22 = Status;
    goto LABEL_9;
  }
  v14 = (unsigned int)dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v22 = inserted;
LABEL_9:
    v28 = 4;
    v27 = &v22;
    tlgWriteTransfer_EtwWriteTransfer(v14, (unsigned __int8 *)&byte_140016D91, v12, v13, ReturnedContexta, &v26);
  }
LABEL_10:
  v7 = v24;
LABEL_17:
  if ( NewContext )
    FltReleaseContext(NewContext);
  if ( a3 )
  {
    ExFreePoolWithTag(*a3, 0);
    ExFreePoolWithTag(*v10, 0);
    ExFreePoolWithTag(a3[3], 0);
    ExFreePoolWithTag(a3[5], 0);
    ExFreePoolWithTag(a3, 0);
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  if ( Status < 0 )
  {
    if ( v7 )
      BfsReleaseNamedPipeMapping(&gBfsPipeMappingTable, v7);
    if ( v9 )
    {
      Data->IoStatus.Status = Status;
      FltSetCallbackDataDirty(Data);
      FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140003e40  mov     [rsp-8+arg_18], rbx
0x140003e45  push    rbp
0x140003e46  push    rsi
0x140003e47  push    rdi
0x140003e48  push    r12
0x140003e4a  push    r13
0x140003e4c  push    r14
0x140003e4e  push    r15
0x140003e50  lea     rbp, [rsp-27h]
0x140003e55  sub     rsp, 0A0h
0x140003e5c  mov     rax, cs:__security_cookie
0x140003e63  xor     rax, rsp
0x140003e66  mov     [rbp+57h+var_40], rax
0x140003e6a  mov     r13, rcx
0x140003e6d  mov     rsi, r8
0x140003e70  xor     ecx, ecx; int
0x140003e72  mov     r15, rdx
0x140003e75  mov     [rbp+57h+OldContext], rcx
0x140003e79  mov     r14d, ecx
0x140003e7c  mov     [rbp+57h+var_80], rcx
0x140003e80  mov     ebx, [r13+18h]
0x140003e84  mov     [rbp+57h+var_90], cl
0x140003e87  mov     [rbp+57h+NewContext], rcx
0x140003e8b  test    ebx, ebx
0x140003e8d  jns     short loc_140003ECE
0x140003e8f  mov     eax, cs:dword_140019000
0x140003e95  mov     r12b, cl
0x140003e98  cmp     eax, 3
0x140003e9b  jbe     short loc_140003EC5
0x140003e9d  lea     rax, [rbp+57h+var_8C]
0x140003ea1  mov     [rbp+57h+var_8C], ebx
0x140003ea4  mov     [rbp+57h+var_50], rax
0x140003ea8  lea     rdx, byte_140016D91; int
0x140003eaf  lea     rax, [rbp+57h+var_70]
0x140003eb3  mov     [rbp+57h+var_48], 4
0x140003ebb  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x140003ec0  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003ec5  lea     rdi, [rsi+8]
0x140003ec9  jmp     loc_140003FFF
0x140003ece  test    rsi, rsi
0x140003ed1  jz      loc_1400040E9
0x140003ed7  mov     rdx, [rsi]
0x140003eda  lea     rax, [r8+20h]
0x140003ede  lea     rcx, [rbp+57h+var_80]
0x140003ee2  mov     r12d, 1
0x140003ee8  mov     [rsp+0D0h+var_A0], rcx
0x140003eed  lea     rdi, [r8+8]
0x140003ef1  lea     rcx, [rbp+57h+var_90]
0x140003ef5  mov     [rsp+0D0h+var_A8], rcx
0x140003efa  lea     r9, [r8+10h]
0x140003efe  mov     r8, [rdi]
0x140003f01  lea     rcx, gBfsPipeMappingTable
0x140003f08  mov     [rsp+0D0h+ReturnedContext], rax; int
0x140003f0d  call    BfsInsertNamedPipeMapping
0x140003f12  mov     ebx, eax
0x140003f14  test    eax, eax
0x140003f16  jns     short loc_140003F54
0x140003f18  mov     ecx, cs:dword_140019000; int
0x140003f1e  cmp     ecx, 3
0x140003f21  jbe     short loc_140003F4B
0x140003f23  mov     [rbp+57h+var_8C], eax
0x140003f26  lea     rax, [rbp+57h+var_8C]
0x140003f2a  mov     [rbp+57h+var_48], 4
0x140003f32  mov     [rbp+57h+var_50], rax
0x140003f36  lea     rdx, byte_140016D91; int
0x140003f3d  lea     rax, [rbp+57h+var_70]
0x140003f41  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x140003f46  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003f4b  mov     r14, [rbp+57h+var_80]
0x140003f4f  jmp     loc_140003FFF
0x140003f54  mov     rcx, [r15+8]; Filter
0x140003f58  lea     rax, [rbp+57h+NewContext]
0x140003f5c  mov     r8d, 10h; ContextSize
0x140003f62  mov     [rsp+0D0h+ReturnedContext], rax; ReturnedContext
0x140003f67  mov     edx, r8d; ContextType
0x140003f6a  mov     r9d, r12d; PoolType
0x140003f6d  call    cs:__imp_FltAllocateContext
0x140003f74  nop     dword ptr [rax+rax+00h]
0x140003f79  mov     ebx, eax
0x140003f7b  test    eax, eax
0x140003f7d  jns     short loc_140003F8F
0x140003f7f  mov     eax, cs:dword_140019000
0x140003f85  cmp     eax, 3
0x140003f88  jbe     short loc_140003F4B
0x140003f8a  mov     [rbp+57h+var_8C], ebx
0x140003f8d  jmp     short loc_140003F26
0x140003f8f  mov     rax, [rbp+57h+NewContext]
0x140003f93  xor     r8d, r8d; Operation
0x140003f96  mov     r14, [rbp+57h+var_80]
0x140003f9a  mov     [rax], r12d
0x140003f9d  mov     rax, [rbp+57h+NewContext]
0x140003fa1  mov     [rax+8], r14
0x140003fa5  lea     rax, [rbp+57h+OldContext]
0x140003fa9  mov     r9, [rbp+57h+NewContext]; NewContext
0x140003fad  mov     rdx, [r15+20h]; FileObject
0x140003fb1  mov     rcx, [r15+18h]; Instance
0x140003fb5  mov     [rsp+0D0h+ReturnedContext], rax; int
0x140003fba  call    cs:__imp_FltSetStreamHandleContext
0x140003fc1  nop     dword ptr [rax+rax+00h]
0x140003fc6  mov     ebx, eax
0x140003fc8  test    eax, eax
0x140003fca  jns     short loc_140003FFF
0x140003fcc  mov     eax, cs:dword_140019000
0x140003fd2  cmp     eax, 3
0x140003fd5  jbe     short loc_140003FFF
0x140003fd7  lea     rax, [rbp+57h+var_8C]
0x140003fdb  mov     [rbp+57h+var_8C], ebx
0x140003fde  mov     [rbp+57h+var_50], rax
0x140003fe2  lea     rdx, byte_140016D91; int
0x140003fe9  lea     rax, [rbp+57h+var_70]
0x140003fed  mov     [rbp+57h+var_48], 4
0x140003ff5  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x140003ffa  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003fff  mov     rcx, [rbp+57h+NewContext]; Context
0x140004003  test    rcx, rcx
0x140004006  jz      short loc_140004014
0x140004008  call    cs:__imp_FltReleaseContext
0x14000400f  nop     dword ptr [rax+rax+00h]
0x140004014  test    rsi, rsi
0x140004017  jz      loc_1400040A5
0x14000401d  cmp     [rbp+57h+var_90], 0
0x140004021  jnz     short loc_140004069
0x140004023  mov     rcx, [rsi]; P
0x140004026  xor     edx, edx; Tag
0x140004028  call    cs:__imp_ExFreePoolWithTag
0x14000402f  nop     dword ptr [rax+rax+00h]
0x140004034  mov     rcx, [rdi]; P
0x140004037  xor     edx, edx; Tag
0x140004039  call    cs:__imp_ExFreePoolWithTag
0x140004040  nop     dword ptr [rax+rax+00h]
0x140004045  mov     rcx, [rsi+18h]; P
0x140004049  xor     edx, edx; Tag
0x14000404b  call    cs:__imp_ExFreePoolWithTag
0x140004052  nop     dword ptr [rax+rax+00h]
0x140004057  mov     rcx, [rsi+28h]; P
0x14000405b  xor     edx, edx; Tag
0x14000405d  call    cs:__imp_ExFreePoolWithTag
0x140004064  nop     dword ptr [rax+rax+00h]
0x140004069  xor     edx, edx; Tag
0x14000406b  mov     rcx, rsi; P
0x14000406e  call    cs:__imp_ExFreePoolWithTag
0x140004075  nop     dword ptr [rax+rax+00h]
0x14000407a  call    cs:__imp_KeEnterCriticalRegion
0x140004081  nop     dword ptr [rax+rax+00h]
0x140004086  lea     rcx, gBfsRundownProtection; RunRef
0x14000408d  call    cs:__imp_ExReleaseRundownProtection
0x140004094  nop     dword ptr [rax+rax+00h]
0x140004099  call    cs:__imp_KeLeaveCriticalRegion
0x1400040a0  nop     dword ptr [rax+rax+00h]
0x1400040a5  test    ebx, ebx
0x1400040a7  jns     short loc_1400040E9
0x1400040a9  test    r14, r14
0x1400040ac  jz      short loc_1400040BD
0x1400040ae  mov     rdx, r14
0x1400040b1  lea     rcx, gBfsPipeMappingTable
0x1400040b8  call    BfsReleaseNamedPipeMapping
0x1400040bd  test    r12b, r12b
0x1400040c0  jz      short loc_1400040E9
0x1400040c2  mov     rcx, r13; Data
0x1400040c5  mov     [r13+18h], ebx
0x1400040c9  call    cs:__imp_FltSetCallbackDataDirty
0x1400040d0  nop     dword ptr [rax+rax+00h]
0x1400040d5  mov     rdx, [r15+20h]; FileObject
0x1400040d9  mov     rcx, [r15+18h]; Instance
0x1400040dd  call    cs:__imp_FltCancelFileOpen
0x1400040e4  nop     dword ptr [rax+rax+00h]
0x1400040e9  xor     eax, eax
0x1400040eb  mov     rcx, [rbp+57h+var_40]
0x1400040ef  xor     rcx, rsp; StackCookie
0x1400040f2  call    __security_check_cookie
0x1400040f7  mov     rbx, [rsp+0D0h+arg_18]
0x1400040ff  add     rsp, 0A0h
0x140004106  pop     r15
0x140004108  pop     r14
0x14000410a  pop     r13
0x14000410c  pop     r12
0x14000410e  pop     rdi
0x14000410f  pop     rsi
0x140004110  pop     rbp
0x140004111  retn
```
