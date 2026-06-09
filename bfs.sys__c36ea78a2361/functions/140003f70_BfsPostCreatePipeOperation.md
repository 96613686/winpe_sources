# BfsPostCreatePipeOperation

- ea: `0x140003f70`
- end: `0x140004243`
- name: `BfsPostCreatePipeOperation`
- size: `723`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, PVOID *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001008`
- `0x140003f70`
- `0x14000b654`
- `0x14000be9c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400041bd`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400041bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004158`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004169`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000417b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000418d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000419e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004158`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004169`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000417b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000418d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000419e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400041aa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400041aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400041c9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400041c9`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400041f9`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400041f9`
- `FLTMGR!FltReleaseContext` at `0x140004138`
- `FLTMGR!FltReleaseContext` at `0x140004138`
- `FLTMGR!FltAllocateContext` at `0x14000409d`
- `FLTMGR!FltAllocateContext` at `0x14000409d`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400040ea`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400040ea`
- `FLTMGR!FltCancelFileOpen` at `0x14000420d`
- `FLTMGR!FltCancelFileOpen` at `0x14000420d`

## pseudocode

```c
__int64 __fastcall BfsPostCreatePipeOperation(PFLT_CALLBACK_DATA Data, __int64 a2, PVOID *a3, int a4)
{
  __int64 v7; // r14
  int Status; // ebx
  char v9; // r12
  PVOID *v10; // rdi
  int inserted; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
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
      tlgWriteTransfer_EtwWriteTransfer(0, (int)&byte_140016D91, (int)a3, a4, ReturnedContext, &v26);
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
        tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v16, v17, ReturnedContextb, &v26);
      }
      goto LABEL_17;
    }
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_10;
    v22 = Status;
    goto LABEL_9;
  }
  v14 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v22 = inserted;
LABEL_9:
    v28 = 4;
    v27 = &v22;
    tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140016D91, v12, v13, ReturnedContexta, &v26);
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
0x140003f70  mov     [rsp-8+arg_18], rbx
0x140003f75  push    rbp
0x140003f76  push    rsi
0x140003f77  push    rdi
0x140003f78  push    r12
0x140003f7a  push    r13
0x140003f7c  push    r14
0x140003f7e  push    r15
0x140003f80  lea     rbp, [rsp-27h]
0x140003f85  sub     rsp, 0A0h
0x140003f8c  mov     rax, cs:__security_cookie
0x140003f93  xor     rax, rsp
0x140003f96  mov     [rbp+57h+var_40], rax
0x140003f9a  mov     r13, rcx
0x140003f9d  mov     rsi, r8
0x140003fa0  xor     ecx, ecx; int
0x140003fa2  mov     r15, rdx
0x140003fa5  mov     [rbp+57h+OldContext], rcx
0x140003fa9  mov     r14d, ecx
0x140003fac  mov     [rbp+57h+var_80], rcx
0x140003fb0  mov     ebx, [r13+18h]
0x140003fb4  mov     [rbp+57h+var_90], cl
0x140003fb7  mov     [rbp+57h+NewContext], rcx
0x140003fbb  test    ebx, ebx
0x140003fbd  jns     short loc_140003FFE
0x140003fbf  mov     eax, cs:dword_140019000
0x140003fc5  mov     r12b, cl
0x140003fc8  cmp     eax, 3
0x140003fcb  jbe     short loc_140003FF5
0x140003fcd  lea     rax, [rbp+57h+var_8C]
0x140003fd1  mov     [rbp+57h+var_8C], ebx
0x140003fd4  mov     [rbp+57h+var_50], rax
0x140003fd8  lea     rdx, byte_140016D91; int
0x140003fdf  lea     rax, [rbp+57h+var_70]
0x140003fe3  mov     [rbp+57h+var_48], 4
0x140003feb  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x140003ff0  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003ff5  lea     rdi, [rsi+8]
0x140003ff9  jmp     loc_14000412F
0x140003ffe  test    rsi, rsi
0x140004001  jz      loc_140004219
0x140004007  mov     rdx, [rsi]
0x14000400a  lea     rax, [r8+20h]
0x14000400e  lea     rcx, [rbp+57h+var_80]
0x140004012  mov     r12d, 1
0x140004018  mov     [rsp+0D0h+var_A0], rcx
0x14000401d  lea     rdi, [r8+8]
0x140004021  lea     rcx, [rbp+57h+var_90]
0x140004025  mov     [rsp+0D0h+var_A8], rcx
0x14000402a  lea     r9, [r8+10h]
0x14000402e  mov     r8, [rdi]
0x140004031  lea     rcx, gBfsPipeMappingTable
0x140004038  mov     [rsp+0D0h+ReturnedContext], rax; int
0x14000403d  call    BfsInsertNamedPipeMapping
0x140004042  mov     ebx, eax
0x140004044  test    eax, eax
0x140004046  jns     short loc_140004084
0x140004048  mov     ecx, cs:dword_140019000; int
0x14000404e  cmp     ecx, 3
0x140004051  jbe     short loc_14000407B
0x140004053  mov     [rbp+57h+var_8C], eax
0x140004056  lea     rax, [rbp+57h+var_8C]
0x14000405a  mov     [rbp+57h+var_48], 4
0x140004062  mov     [rbp+57h+var_50], rax
0x140004066  lea     rdx, byte_140016D91; int
0x14000406d  lea     rax, [rbp+57h+var_70]
0x140004071  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x140004076  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000407b  mov     r14, [rbp+57h+var_80]
0x14000407f  jmp     loc_14000412F
0x140004084  mov     rcx, [r15+8]; Filter
0x140004088  lea     rax, [rbp+57h+NewContext]
0x14000408c  mov     r8d, 10h; ContextSize
0x140004092  mov     [rsp+0D0h+ReturnedContext], rax; ReturnedContext
0x140004097  mov     edx, r8d; ContextType
0x14000409a  mov     r9d, r12d; PoolType
0x14000409d  call    cs:__imp_FltAllocateContext
0x1400040a4  nop     dword ptr [rax+rax+00h]
0x1400040a9  mov     ebx, eax
0x1400040ab  test    eax, eax
0x1400040ad  jns     short loc_1400040BF
0x1400040af  mov     eax, cs:dword_140019000
0x1400040b5  cmp     eax, 3
0x1400040b8  jbe     short loc_14000407B
0x1400040ba  mov     [rbp+57h+var_8C], ebx
0x1400040bd  jmp     short loc_140004056
0x1400040bf  mov     rax, [rbp+57h+NewContext]
0x1400040c3  xor     r8d, r8d; Operation
0x1400040c6  mov     r14, [rbp+57h+var_80]
0x1400040ca  mov     [rax], r12d
0x1400040cd  mov     rax, [rbp+57h+NewContext]
0x1400040d1  mov     [rax+8], r14
0x1400040d5  lea     rax, [rbp+57h+OldContext]
0x1400040d9  mov     r9, [rbp+57h+NewContext]; NewContext
0x1400040dd  mov     rdx, [r15+20h]; FileObject
0x1400040e1  mov     rcx, [r15+18h]; Instance
0x1400040e5  mov     [rsp+0D0h+ReturnedContext], rax; int
0x1400040ea  call    cs:__imp_FltSetStreamHandleContext
0x1400040f1  nop     dword ptr [rax+rax+00h]
0x1400040f6  mov     ebx, eax
0x1400040f8  test    eax, eax
0x1400040fa  jns     short loc_14000412F
0x1400040fc  mov     eax, cs:dword_140019000
0x140004102  cmp     eax, 3
0x140004105  jbe     short loc_14000412F
0x140004107  lea     rax, [rbp+57h+var_8C]
0x14000410b  mov     [rbp+57h+var_8C], ebx
0x14000410e  mov     [rbp+57h+var_50], rax
0x140004112  lea     rdx, byte_140016D91; int
0x140004119  lea     rax, [rbp+57h+var_70]
0x14000411d  mov     [rbp+57h+var_48], 4
0x140004125  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000412a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000412f  mov     rcx, [rbp+57h+NewContext]; Context
0x140004133  test    rcx, rcx
0x140004136  jz      short loc_140004144
0x140004138  call    cs:__imp_FltReleaseContext
0x14000413f  nop     dword ptr [rax+rax+00h]
0x140004144  test    rsi, rsi
0x140004147  jz      loc_1400041D5
0x14000414d  cmp     [rbp+57h+var_90], 0
0x140004151  jnz     short loc_140004199
0x140004153  mov     rcx, [rsi]; P
0x140004156  xor     edx, edx; Tag
0x140004158  call    cs:__imp_ExFreePoolWithTag
0x14000415f  nop     dword ptr [rax+rax+00h]
0x140004164  mov     rcx, [rdi]; P
0x140004167  xor     edx, edx; Tag
0x140004169  call    cs:__imp_ExFreePoolWithTag
0x140004170  nop     dword ptr [rax+rax+00h]
0x140004175  mov     rcx, [rsi+18h]; P
0x140004179  xor     edx, edx; Tag
0x14000417b  call    cs:__imp_ExFreePoolWithTag
0x140004182  nop     dword ptr [rax+rax+00h]
0x140004187  mov     rcx, [rsi+28h]; P
0x14000418b  xor     edx, edx; Tag
0x14000418d  call    cs:__imp_ExFreePoolWithTag
0x140004194  nop     dword ptr [rax+rax+00h]
0x140004199  xor     edx, edx; Tag
0x14000419b  mov     rcx, rsi; P
0x14000419e  call    cs:__imp_ExFreePoolWithTag
0x1400041a5  nop     dword ptr [rax+rax+00h]
0x1400041aa  call    cs:__imp_KeEnterCriticalRegion
0x1400041b1  nop     dword ptr [rax+rax+00h]
0x1400041b6  lea     rcx, gBfsRundownProtection; RunRef
0x1400041bd  call    cs:__imp_ExReleaseRundownProtection
0x1400041c4  nop     dword ptr [rax+rax+00h]
0x1400041c9  call    cs:__imp_KeLeaveCriticalRegion
0x1400041d0  nop     dword ptr [rax+rax+00h]
0x1400041d5  test    ebx, ebx
0x1400041d7  jns     short loc_140004219
0x1400041d9  test    r14, r14
0x1400041dc  jz      short loc_1400041ED
0x1400041de  mov     rdx, r14
0x1400041e1  lea     rcx, gBfsPipeMappingTable
0x1400041e8  call    BfsReleaseNamedPipeMapping
0x1400041ed  test    r12b, r12b
0x1400041f0  jz      short loc_140004219
0x1400041f2  mov     rcx, r13; Data
0x1400041f5  mov     [r13+18h], ebx
0x1400041f9  call    cs:__imp_FltSetCallbackDataDirty
0x140004200  nop     dword ptr [rax+rax+00h]
0x140004205  mov     rdx, [r15+20h]; FileObject
0x140004209  mov     rcx, [r15+18h]; Instance
0x14000420d  call    cs:__imp_FltCancelFileOpen
0x140004214  nop     dword ptr [rax+rax+00h]
0x140004219  xor     eax, eax
0x14000421b  mov     rcx, [rbp+57h+var_40]
0x14000421f  xor     rcx, rsp; StackCookie
0x140004222  call    __security_check_cookie
0x140004227  mov     rbx, [rsp+0D0h+arg_18]
0x14000422f  add     rsp, 0A0h
0x140004236  pop     r15
0x140004238  pop     r14
0x14000423a  pop     r13
0x14000423c  pop     r12
0x14000423e  pop     rdi
0x14000423f  pop     rsi
0x140004240  pop     rbp
0x140004241  retn
```
