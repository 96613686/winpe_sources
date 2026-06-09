# PrjfEnumerateDirectory

- ea: `0x14003a4d0`
- end: `0x14003a5c6`
- name: `PrjfEnumerateDirectory`
- size: `246`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140025734`
- `0x1400377c4`
- `0x140043b24`

## callees

- `0x14003a4d0`

## import_xrefs

- `FLTMGR!FltFreeCallbackData` at `0x14003a5ac`
- `FLTMGR!FltFreeCallbackData` at `0x14003a5ac`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003a58e`
- `FLTMGR!FltPerformSynchronousIo` at `0x14003a58e`
- `FLTMGR!FltAllocateCallbackData` at `0x14003a4fa`
- `FLTMGR!FltAllocateCallbackData` at `0x14003a4fa`

## pseudocode

```c
__int64 __fastcall PrjfEnumerateDirectory(
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
  struct _FLT_CALLBACK_DATA *v12; // rcx
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+20h] [rbp-10h] BYREF

  RetNewCallbackData = 0;
  *a9 = 0;
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
0x14003a4d0  push    rbp
0x14003a4d2  push    rbx
0x14003a4d3  push    rsi
0x14003a4d4  push    rdi
0x14003a4d5  push    r14
0x14003a4d7  mov     rbp, rsp
0x14003a4da  sub     rsp, 30h
0x14003a4de  mov     rdi, [rbp+arg_40]
0x14003a4e2  mov     r14d, r8d
0x14003a4e5  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14003a4e9  mov     [rbp+RetNewCallbackData], 0
0x14003a4f1  mov     rsi, r9
0x14003a4f4  mov     dword ptr [rdi], 0
0x14003a4fa  call    cs:__imp_FltAllocateCallbackData
0x14003a501  nop     dword ptr [rax+rax+00h]
0x14003a506  mov     ebx, eax
0x14003a508  test    eax, eax
0x14003a50a  js      loc_14003A5A8
0x14003a510  mov     rax, [rbp+RetNewCallbackData]
0x14003a514  mov     rcx, [rax+10h]
0x14003a518  mov     byte ptr [rcx+4], 0Ch
0x14003a51c  mov     rax, [rbp+RetNewCallbackData]
0x14003a520  mov     rcx, [rax+10h]
0x14003a524  mov     byte ptr [rcx+5], 1
0x14003a528  mov     rax, [rbp+RetNewCallbackData]
0x14003a52c  mov     rcx, [rax+10h]
0x14003a530  mov     eax, [rbp+arg_30]
0x14003a533  mov     [rcx+18h], eax
0x14003a536  mov     rax, [rbp+RetNewCallbackData]
0x14003a53a  mov     rcx, [rax+10h]
0x14003a53e  mov     [rcx+28h], r14d
0x14003a542  mov     rax, [rbp+RetNewCallbackData]
0x14003a546  mov     rcx, [rax+10h]
0x14003a54a  mov     [rcx+20h], rsi
0x14003a54e  mov     rax, [rbp+RetNewCallbackData]
0x14003a552  mov     rcx, [rax+10h]
0x14003a556  mov     eax, [rbp+arg_20]
0x14003a559  mov     [rcx+30h], eax
0x14003a55c  mov     rax, [rbp+RetNewCallbackData]
0x14003a560  mov     rcx, [rax+10h]
0x14003a564  mov     rax, [rbp+arg_38]
0x14003a568  mov     [rcx+38h], rax
0x14003a56c  mov     rax, [rbp+RetNewCallbackData]
0x14003a570  mov     rcx, [rax+10h]
0x14003a574  mov     qword ptr [rcx+40h], 0
0x14003a57c  mov     rax, [rbp+RetNewCallbackData]
0x14003a580  mov     rcx, [rax+10h]
0x14003a584  mov     al, [rbp+arg_28]
0x14003a587  mov     [rcx+6], al
0x14003a58a  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14003a58e  call    cs:__imp_FltPerformSynchronousIo
0x14003a595  nop     dword ptr [rax+rax+00h]
0x14003a59a  mov     rcx, [rbp+RetNewCallbackData]
0x14003a59e  mov     ebx, [rcx+18h]
0x14003a5a1  mov     eax, [rcx+20h]
0x14003a5a4  mov     [rdi], eax
0x14003a5a6  jmp     short loc_14003A5AC
0x14003a5a8  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14003a5ac  call    cs:__imp_FltFreeCallbackData
0x14003a5b3  nop     dword ptr [rax+rax+00h]
0x14003a5b8  mov     eax, ebx
0x14003a5ba  add     rsp, 30h
0x14003a5be  pop     r14
0x14003a5c0  pop     rdi
0x14003a5c1  pop     rsi
0x14003a5c2  pop     rbx
0x14003a5c3  pop     rbp
0x14003a5c4  retn
```
