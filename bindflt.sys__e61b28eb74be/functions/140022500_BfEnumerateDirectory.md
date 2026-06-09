# BfEnumerateDirectory

- ea: `0x140022500`
- end: `0x1400225ee`
- name: `BfEnumerateDirectory`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002494c`

## callees

- `0x140022500`

## import_xrefs

- `FLTMGR!FltPerformSynchronousIo` at `0x1400225b1`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400225b1`
- `FLTMGR!FltFreeCallbackData` at `0x1400225d0`
- `FLTMGR!FltFreeCallbackData` at `0x1400225d0`
- `FLTMGR!FltAllocateCallbackData` at `0x14002251e`
- `FLTMGR!FltAllocateCallbackData` at `0x14002251e`

## pseudocode

```c
__int64 __fastcall BfEnumerateDirectory(
        struct _FLT_INSTANCE *a1,
        struct _FILE_OBJECT *a2,
        DWORD a3,
        void *a4,
        ULONG a5,
        UCHAR a6,
        ULONG a7,
        void *a8,
        _DWORD *a9)
{
  NTSTATUS Status; // ebx
  struct _FLT_CALLBACK_DATA *v12; // rdx
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+20h] [rbp-18h] BYREF

  RetNewCallbackData = 0;
  Status = FltAllocateCallbackData(a1, a2, &RetNewCallbackData);
  if ( Status < 0 )
  {
    v12 = RetNewCallbackData;
  }
  else
  {
    RetNewCallbackData->Iopb->MajorFunction = 12;
    RetNewCallbackData->Iopb->MinorFunction = 1;
    RetNewCallbackData->Iopb->Parameters.Read.Length = a7;
    RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = a3;
    RetNewCallbackData->Iopb->Parameters.QueryEa.EaList = a4;
    RetNewCallbackData->Iopb->Parameters.Create.EaLength = a5;
    RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = a8;
    RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
    RetNewCallbackData->Iopb->OperationFlags = a6;
    FltPerformSynchronousIo(RetNewCallbackData);
    v12 = RetNewCallbackData;
    Status = RetNewCallbackData->IoStatus.Status;
    *a9 = RetNewCallbackData->IoStatus.Information;
  }
  FltFreeCallbackData(v12);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140022500  push    rbp
0x140022502  push    rbx
0x140022503  push    rsi
0x140022504  push    rdi
0x140022505  mov     rbp, rsp
0x140022508  sub     rsp, 38h
0x14002250c  mov     esi, r8d
0x14002250f  mov     [rbp+RetNewCallbackData], 0
0x140022517  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14002251b  mov     rdi, r9
0x14002251e  call    cs:__imp_FltAllocateCallbackData
0x140022525  nop     dword ptr [rax+rax+00h]
0x14002252a  mov     ebx, eax
0x14002252c  test    eax, eax
0x14002252e  js      loc_1400225E8
0x140022534  mov     rax, [rbp+RetNewCallbackData]
0x140022538  mov     rcx, [rax+10h]
0x14002253c  mov     byte ptr [rcx+4], 0Ch
0x140022540  mov     rax, [rbp+RetNewCallbackData]
0x140022544  mov     rcx, [rax+10h]
0x140022548  mov     byte ptr [rcx+5], 1
0x14002254c  mov     rax, [rbp+RetNewCallbackData]
0x140022550  mov     rcx, [rax+10h]
0x140022554  mov     eax, [rbp+arg_30]
0x140022557  mov     [rcx+18h], eax
0x14002255a  mov     rax, [rbp+RetNewCallbackData]
0x14002255e  mov     rcx, [rax+10h]
0x140022562  mov     [rcx+28h], esi
0x140022565  mov     rax, [rbp+RetNewCallbackData]
0x140022569  mov     rcx, [rax+10h]
0x14002256d  mov     [rcx+20h], rdi
0x140022571  mov     rax, [rbp+RetNewCallbackData]
0x140022575  mov     rcx, [rax+10h]
0x140022579  mov     eax, [rbp+arg_20]
0x14002257c  mov     [rcx+30h], eax
0x14002257f  mov     rax, [rbp+RetNewCallbackData]
0x140022583  mov     rcx, [rax+10h]
0x140022587  mov     rax, [rbp+arg_38]
0x14002258b  mov     [rcx+38h], rax
0x14002258f  mov     rax, [rbp+RetNewCallbackData]
0x140022593  mov     rcx, [rax+10h]
0x140022597  mov     qword ptr [rcx+40h], 0
0x14002259f  mov     rax, [rbp+RetNewCallbackData]
0x1400225a3  mov     rcx, [rax+10h]
0x1400225a7  mov     al, [rbp+arg_28]
0x1400225aa  mov     [rcx+6], al
0x1400225ad  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x1400225b1  call    cs:__imp_FltPerformSynchronousIo
0x1400225b8  nop     dword ptr [rax+rax+00h]
0x1400225bd  mov     rdx, [rbp+RetNewCallbackData]
0x1400225c1  mov     rax, [rbp+arg_40]
0x1400225c5  mov     ebx, [rdx+18h]
0x1400225c8  mov     ecx, [rdx+20h]
0x1400225cb  mov     [rax], ecx
0x1400225cd  mov     rcx, rdx; CallbackData
0x1400225d0  call    cs:__imp_FltFreeCallbackData
0x1400225d7  nop     dword ptr [rax+rax+00h]
0x1400225dc  mov     eax, ebx
0x1400225de  add     rsp, 38h
0x1400225e2  pop     rdi
0x1400225e3  pop     rsi
0x1400225e4  pop     rbx
0x1400225e5  pop     rbp
0x1400225e6  retn
0x1400225e8  mov     rdx, [rbp+RetNewCallbackData]
0x1400225ec  jmp     short loc_1400225CD
```
