# BfPostReadWrite

- ea: `0x140006260`
- end: `0x140006357`
- name: `BfPostReadWrite`
- size: `247`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006260`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14000629a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000629a`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x14000632a`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x14000632a`
- `FLTMGR!FltReleaseContext` at `0x140006339`
- `FLTMGR!FltReleaseContext` at `0x140006339`

## pseudocode

```c
__int64 __fastcall BfPostReadWrite(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        __int64 a3,
        FLT_POST_OPERATION_FLAGS a4)
{
  __int64 result; // rax
  struct _EX_RUNDOWN_REF *v8; // rsi
  PFILE_OBJECT FileObject; // rdi
  char v10; // bp
  ULONG_PTR Count; // r8
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+78h] [rbp+10h] BYREF

  result = 0;
  RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
  v8 = (struct _EX_RUNDOWN_REF *)(a3 & 0xFFFFFFFFFFFFFFFEuLL);
  if ( (a3 & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    FileObject = FltObjects->FileObject;
    v10 = a3 & 1;
    if ( (a3 & 1) != 0 )
      ExReleaseRundownProtection(v8 + 3);
    if ( FileObject )
    {
      Count = v8[1].Count;
      if ( Count )
      {
        if ( (FileObject->Flags & 0x4000) == 0 && (Data->Iopb->IrpFlags & 1) == 0 )
          FileObject->PrivateCacheMap = *(PVOID *)(Count + 48);
        if ( Data->IoStatus.Status >= 0 )
        {
          if ( (*(_DWORD *)(Count + 80) & 2) != 0 && (Data->Iopb->IrpFlags & 2) == 0 && Data->IoStatus.Information )
            FileObject->CurrentByteOffset.QuadPart = *(_QWORD *)(Count + 104);
          if ( Data->Iopb->MajorFunction == 4 && !v10 )
            FltDoCompletionProcessingWhenSafe(
              Data,
              FltObjects,
              (PVOID)Count,
              a4,
              BfUpdateFileSizesWorker,
              &RetPostOperationStatus);
        }
      }
    }
    FltReleaseContext(v8);
    return (unsigned int)RetPostOperationStatus;
  }
  return result;
}

```

## disassembly

```asm
0x140006260  push    rbx
0x140006262  push    rbp
0x140006263  push    rsi
0x140006264  push    rdi
0x140006265  push    r14
0x140006267  push    r15
0x140006269  sub     rsp, 38h
0x14000626d  xor     eax, eax
0x14000626f  mov     rsi, r8
0x140006272  mov     [rsp+68h+arg_8], eax
0x140006276  mov     r15d, r9d
0x140006279  mov     rbp, r8
0x14000627c  mov     r14, rdx
0x14000627f  mov     rbx, rcx
0x140006282  and     rsi, 0FFFFFFFFFFFFFFFEh
0x140006286  jz      loc_140006349
0x14000628c  mov     rdi, [rdx+20h]
0x140006290  and     bpl, 1
0x140006294  jz      short loc_1400062A6
0x140006296  lea     rcx, [rsi+18h]; RunRef
0x14000629a  call    cs:__imp_ExReleaseRundownProtection
0x1400062a1  nop     dword ptr [rax+rax+00h]
0x1400062a6  test    rdi, rdi
0x1400062a9  jz      loc_140006336
0x1400062af  mov     r8, [rsi+8]; CompletionContext
0x1400062b3  test    r8, r8
0x1400062b6  jz      short loc_140006336
0x1400062b8  test    dword ptr [rdi+50h], 4000h
0x1400062bf  jnz     short loc_1400062D4
0x1400062c1  mov     rax, [rbx+10h]
0x1400062c5  mov     ecx, [rax]
0x1400062c7  test    cl, 1
0x1400062ca  jnz     short loc_1400062D4
0x1400062cc  mov     rax, [r8+30h]
0x1400062d0  mov     [rdi+30h], rax
0x1400062d4  cmp     dword ptr [rbx+18h], 0
0x1400062d8  jl      short loc_140006336
0x1400062da  mov     eax, [r8+50h]
0x1400062de  test    al, 2
0x1400062e0  jz      short loc_1400062FC
0x1400062e2  mov     rax, [rbx+10h]
0x1400062e6  mov     ecx, [rax]
0x1400062e8  test    cl, 2
0x1400062eb  jnz     short loc_1400062FC
0x1400062ed  cmp     qword ptr [rbx+20h], 0
0x1400062f2  jbe     short loc_1400062FC
0x1400062f4  mov     rax, [r8+68h]
0x1400062f8  mov     [rdi+68h], rax
0x1400062fc  mov     rax, [rbx+10h]
0x140006300  cmp     byte ptr [rax+4], 4
0x140006304  jnz     short loc_140006336
0x140006306  test    bpl, bpl
0x140006309  jnz     short loc_140006336
0x14000630b  lea     rax, [rsp+68h+arg_8]
0x140006310  mov     r9d, r15d; Flags
0x140006313  mov     [rsp+68h+RetPostOperationStatus], rax; RetPostOperationStatus
0x140006318  mov     rdx, r14; FltObjects
0x14000631b  lea     rax, BfUpdateFileSizesWorker
0x140006322  mov     rcx, rbx; Data
0x140006325  mov     [rsp+68h+SafePostCallback], rax; SafePostCallback
0x14000632a  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x140006331  nop     dword ptr [rax+rax+00h]
0x140006336  mov     rcx, rsi; Context
0x140006339  call    cs:__imp_FltReleaseContext
0x140006340  nop     dword ptr [rax+rax+00h]
0x140006345  mov     eax, [rsp+68h+arg_8]
0x140006349  add     rsp, 38h
0x14000634d  pop     r15
0x14000634f  pop     r14
0x140006351  pop     rdi
0x140006352  pop     rsi
0x140006353  pop     rbp
0x140006354  pop     rbx
0x140006355  retn
```
