# VfsWriteWorker

- ea: `0x14000b1f0`
- end: `0x14000b29e`
- name: `VfsWriteWorker`
- size: `174`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64, PFILE_OBJECT *, char, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140001690`
- `0x1400017e0`
- `0x14000aca0`

## callees

- `0x14000aefc`
- `0x14000b1f0`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltSetCallbackDataDirty` at `0x14000b266`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000b266`

## string_xrefs

- `0x14000b227`: `VfsWriteWorker() - Failed to delay copy file. Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsWriteWorker(PFLT_CALLBACK_DATA Data, __int64 a2, PFILE_OBJECT *a3, char a4, char a5)
{
  __int64 v5; // rdx
  __int64 v9; // rsi
  int v10; // eax
  NTSTATUS v11; // edi
  __int64 result; // rax

  v5 = *(_QWORD *)(a2 + 32);
  v9 = *(_QWORD *)(v5 + 32);
  if ( (*(_DWORD *)(v9 + 4) & 4) != 0
    && (v10 = VfsDelayedCopy((__int64)Data, *(_QWORD *)(v5 + 24), v9), v11 = v10, v10 < 0) )
  {
    LogWrite(1, 0, L"VfsWriteWorker() - Failed to delay copy file. Status: 0x%08X", (unsigned int)v10);
    result = 4;
    Data->IoStatus.Status = v11;
    Data->IoStatus.Information = 0;
  }
  else
  {
    Data->Iopb->TargetFileObject = *(PFILE_OBJECT *)(v9 + 72);
    Data->Iopb->TargetInstance = *(PFLT_INSTANCE *)(v9 + 64);
    FltSetCallbackDataDirty(Data);
    if ( a4 )
    {
      result = a5 != 0 ? 5 : 0;
      *a3 = Data->Iopb->TargetFileObject;
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b1f0  push    rbx
0x14000b1f2  push    rbp
0x14000b1f3  push    rsi
0x14000b1f4  push    rdi
0x14000b1f5  push    r14
0x14000b1f7  sub     rsp, 20h
0x14000b1fb  mov     rdx, [rdx+20h]
0x14000b1ff  mov     bpl, r9b
0x14000b202  mov     r14, r8
0x14000b205  mov     rbx, rcx
0x14000b208  mov     rsi, [rdx+20h]
0x14000b20c  mov     eax, [rsi+4]
0x14000b20f  test    al, 4
0x14000b211  jz      short loc_14000B24B
0x14000b213  mov     rdx, [rdx+18h]
0x14000b217  mov     r8, rsi
0x14000b21a  call    VfsDelayedCopy
0x14000b21f  mov     edi, eax
0x14000b221  test    eax, eax
0x14000b223  jns     short loc_14000B24B
0x14000b225  xor     edx, edx
0x14000b227  lea     r8, aVfswriteworker; "VfsWriteWorker() - Failed to delay copy"...
0x14000b22e  mov     r9d, eax
0x14000b231  lea     ecx, [rdx+1]
0x14000b234  call    LogWrite
0x14000b239  mov     eax, 4
0x14000b23e  mov     [rbx+18h], edi
0x14000b241  mov     qword ptr [rbx+20h], 0
0x14000b249  jmp     short loc_14000B292
0x14000b24b  mov     rcx, [rbx+10h]
0x14000b24f  mov     rax, [rsi+48h]
0x14000b253  mov     [rcx+8], rax
0x14000b257  mov     rcx, [rbx+10h]
0x14000b25b  mov     rax, [rsi+40h]
0x14000b25f  mov     [rcx+10h], rax
0x14000b263  mov     rcx, rbx; Data
0x14000b266  call    cs:__imp_FltSetCallbackDataDirty
0x14000b26d  nop     dword ptr [rax+rax+00h]
0x14000b272  test    bpl, bpl
0x14000b275  jz      short loc_14000B28D
0x14000b277  mov     rax, [rbx+10h]
0x14000b27b  neg     [rsp+48h+arg_20]
0x14000b27f  mov     rcx, [rax+8]
0x14000b283  sbb     eax, eax
0x14000b285  and     eax, 5
0x14000b288  mov     [r14], rcx
0x14000b28b  jmp     short loc_14000B292
0x14000b28d  mov     eax, 1
0x14000b292  add     rsp, 20h
0x14000b296  pop     r14
0x14000b298  pop     rdi
0x14000b299  pop     rsi
0x14000b29a  pop     rbp
0x14000b29b  pop     rbx
0x14000b29c  retn
```
