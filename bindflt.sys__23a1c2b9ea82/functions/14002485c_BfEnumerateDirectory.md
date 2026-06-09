# BfEnumerateDirectory

- ea: `0x14002485c`
- end: `0x14002494f`
- name: `BfEnumerateDirectory`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140024958`

## callees

- `0x14002485c`

## import_xrefs

- `FLTMGR!FltPerformSynchronousIo` at `0x14002490d`
- `FLTMGR!FltPerformSynchronousIo` at `0x14002490d`
- `FLTMGR!FltFreeCallbackData` at `0x140024937`
- `FLTMGR!FltFreeCallbackData` at `0x140024937`
- `FLTMGR!FltAllocateCallbackData` at `0x14002487a`
- `FLTMGR!FltAllocateCallbackData` at `0x14002487a`

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
  if ( v12 )
    FltFreeCallbackData(v12);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14002485c  push    rbp
0x14002485e  push    rbx
0x14002485f  push    rsi
0x140024860  push    rdi
0x140024861  mov     rbp, rsp
0x140024864  sub     rsp, 38h
0x140024868  mov     esi, r8d
0x14002486b  mov     [rbp+RetNewCallbackData], 0
0x140024873  lea     r8, [rbp+RetNewCallbackData]; RetNewCallbackData
0x140024877  mov     rdi, r9
0x14002487a  call    cs:__imp_FltAllocateCallbackData
0x140024881  nop     dword ptr [rax+rax+00h]
0x140024886  mov     ebx, eax
0x140024888  test    eax, eax
0x14002488a  js      loc_14002492B
0x140024890  mov     rax, [rbp+RetNewCallbackData]
0x140024894  mov     rcx, [rax+10h]
0x140024898  mov     byte ptr [rcx+4], 0Ch
0x14002489c  mov     rax, [rbp+RetNewCallbackData]
0x1400248a0  mov     rcx, [rax+10h]
0x1400248a4  mov     byte ptr [rcx+5], 1
0x1400248a8  mov     rax, [rbp+RetNewCallbackData]
0x1400248ac  mov     rcx, [rax+10h]
0x1400248b0  mov     eax, [rbp+arg_30]
0x1400248b3  mov     [rcx+18h], eax
0x1400248b6  mov     rax, [rbp+RetNewCallbackData]
0x1400248ba  mov     rcx, [rax+10h]
0x1400248be  mov     [rcx+28h], esi
0x1400248c1  mov     rax, [rbp+RetNewCallbackData]
0x1400248c5  mov     rcx, [rax+10h]
0x1400248c9  mov     [rcx+20h], rdi
0x1400248cd  mov     rax, [rbp+RetNewCallbackData]
0x1400248d1  mov     rcx, [rax+10h]
0x1400248d5  mov     eax, [rbp+arg_20]
0x1400248d8  mov     [rcx+30h], eax
0x1400248db  mov     rax, [rbp+RetNewCallbackData]
0x1400248df  mov     rcx, [rax+10h]
0x1400248e3  mov     rax, [rbp+arg_38]
0x1400248e7  mov     [rcx+38h], rax
0x1400248eb  mov     rax, [rbp+RetNewCallbackData]
0x1400248ef  mov     rcx, [rax+10h]
0x1400248f3  mov     qword ptr [rcx+40h], 0
0x1400248fb  mov     rax, [rbp+RetNewCallbackData]
0x1400248ff  mov     rcx, [rax+10h]
0x140024903  mov     al, [rbp+arg_28]
0x140024906  mov     [rcx+6], al
0x140024909  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x14002490d  call    cs:__imp_FltPerformSynchronousIo
0x140024914  nop     dword ptr [rax+rax+00h]
0x140024919  mov     rdx, [rbp+RetNewCallbackData]
0x14002491d  mov     rax, [rbp+arg_40]
0x140024921  mov     ebx, [rdx+18h]
0x140024924  mov     ecx, [rdx+20h]
0x140024927  mov     [rax], ecx
0x140024929  jmp     short loc_14002492F
0x14002492b  mov     rdx, [rbp+RetNewCallbackData]
0x14002492f  test    rdx, rdx
0x140024932  jz      short loc_140024943
0x140024934  mov     rcx, rdx; CallbackData
0x140024937  call    cs:__imp_FltFreeCallbackData
0x14002493e  nop     dword ptr [rax+rax+00h]
0x140024943  mov     eax, ebx
0x140024945  add     rsp, 38h
0x140024949  pop     rdi
0x14002494a  pop     rsi
0x14002494b  pop     rbx
0x14002494c  pop     rbp
0x14002494d  retn
```
