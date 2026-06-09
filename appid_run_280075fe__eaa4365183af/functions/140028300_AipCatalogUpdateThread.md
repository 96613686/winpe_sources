# AipCatalogUpdateThread

- ea: `0x140028300`
- end: `0x1400283ca`
- name: `AipCatalogUpdateThread`
- size: `202`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140028300`
- `0x140035d30`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140028365`
- `ntoskrnl!KeDelayExecutionThread` at `0x140028365`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14002837d`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14002837d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028399`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028399`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400283b3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400283b3`
- `ntoskrnl!ZwNotifyChangeDirectoryFile` at `0x14002834c`
- `ntoskrnl!ZwNotifyChangeDirectoryFile` at `0x14002834c`

## pseudocode

```c
void __fastcall AipCatalogUpdateThread(PVOID StartContext)
{
  NTSTATUS v1; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+78h] [rbp+10h] BYREF

  Interval.QuadPart = -600000000;
  while ( 1 )
  {
    IoStatusBlock = 0;
    v1 = ZwNotifyChangeDirectoryFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0, 0, 0x11u, 1u) >= 0
       ? ZwWaitForSingleObject(FileHandle, 1u, 0)
       : KeDelayExecutionThread(0, 1u, &Interval);
    if ( v1 == 257 )
      break;
    ExAcquirePushLockExclusiveEx(&qword_1400192E0, 0);
    AiGetCatalogLastWriteTime();
    ExReleasePushLockExclusiveEx(&qword_1400192E0, 0);
  }
}

```

## disassembly

```asm
0x140028300  sub     rsp, 68h
0x140028304  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFDC3CBA00h
0x14002830d  mov     rcx, cs:FileHandle; FileHandle
0x140028314  lea     rax, [rsp+68h+var_18]
0x140028319  mov     [rsp+68h+WatchTree], 1; WatchTree
0x14002831e  xorps   xmm0, xmm0
0x140028321  mov     [rsp+68h+CompletionFilter], 11h; CompletionFilter
0x140028329  xor     r9d, r9d; ApcContext
0x14002832c  mov     [rsp+68h+BufferSize], 0; BufferSize
0x140028334  xor     r8d, r8d; ApcRoutine
0x140028337  mov     [rsp+68h+Buffer], 0; Buffer
0x140028340  xor     edx, edx; Event
0x140028342  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140028347  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x14002834c  call    cs:__imp_ZwNotifyChangeDirectoryFile
0x140028353  nop     dword ptr [rax+rax+00h]
0x140028358  mov     dl, 1; Alertable
0x14002835a  test    eax, eax
0x14002835c  jns     short loc_140028373
0x14002835e  lea     r8, [rsp+68h+Interval]; Interval
0x140028363  xor     ecx, ecx; WaitMode
0x140028365  call    cs:__imp_KeDelayExecutionThread
0x14002836c  nop     dword ptr [rax+rax+00h]
0x140028371  jmp     short loc_140028389
0x140028373  mov     rcx, cs:FileHandle; Handle
0x14002837a  xor     r8d, r8d; Timeout
0x14002837d  call    cs:__imp_ZwWaitForSingleObject
0x140028384  nop     dword ptr [rax+rax+00h]
0x140028389  cmp     eax, 101h
0x14002838e  jz      short loc_1400283C4
0x140028390  xor     edx, edx
0x140028392  lea     rcx, qword_1400192E0
0x140028399  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400283a0  nop     dword ptr [rax+rax+00h]
0x1400283a5  call    AiGetCatalogLastWriteTime
0x1400283aa  xor     edx, edx
0x1400283ac  lea     rcx, qword_1400192E0
0x1400283b3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400283ba  nop     dword ptr [rax+rax+00h]
0x1400283bf  jmp     loc_14002830D
0x1400283c4  add     rsp, 68h
0x1400283c8  retn
```
