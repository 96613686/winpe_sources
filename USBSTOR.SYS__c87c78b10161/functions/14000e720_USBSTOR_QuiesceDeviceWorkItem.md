# USBSTOR_QuiesceDeviceWorkItem

- ea: `0x14000e720`
- end: `0x14000e7ab`
- name: `USBSTOR_QuiesceDeviceWorkItem`
- size: `139`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000e7b4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000e76e`
- `ntoskrnl!IofCompleteRequest` at `0x14000e76e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e78e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e78e`

## pseudocode

```c
void __fastcall USBSTOR_QuiesceDeviceWorkItem(_QWORD *IoObject, _QWORD *Context, PIO_WORKITEM IoWorkItem)
{
  struct _IO_REMOVE_LOCK *v4; // rdi
  __int64 v5; // rbx
  int v6; // eax
  char v7; // cl

  v4 = (struct _IO_REMOVE_LOCK *)IoObject[8];
  v5 = *(_QWORD *)(*(_QWORD *)(*Context + 184LL) + 8LL);
  v6 = USBSTOR_WaitForQuiesce(Context[1], *(unsigned int *)(v5 + 20), IoWorkItem);
  v7 = 9;
  if ( v6 != 258 )
    v7 = 1;
  *(_BYTE *)(v5 + 3) = v7;
  *(_DWORD *)(*Context + 48LL) = v6;
  IofCompleteRequest((PIRP)*Context, 0);
  IoReleaseRemoveLockEx(v4 + 23, USBSTOR_QuiesceDeviceWorkItem, 0x20u);
}

```

## disassembly

```asm
0x14000e720  mov     [rsp+arg_0], rbx
0x14000e725  mov     [rsp+arg_8], rsi
0x14000e72a  push    rdi
0x14000e72b  sub     rsp, 20h
0x14000e72f  mov     rax, [rdx]
0x14000e732  mov     rsi, rdx
0x14000e735  mov     rdi, [rcx+40h]
0x14000e739  mov     rcx, [rax+0B8h]
0x14000e740  mov     rbx, [rcx+8]
0x14000e744  mov     rcx, [rsi+8]
0x14000e748  mov     edx, [rbx+14h]
0x14000e74b  call    USBSTOR_WaitForQuiesce
0x14000e750  mov     ecx, 9
0x14000e755  cmp     eax, 102h
0x14000e75a  lea     edx, [rcx-8]
0x14000e75d  cmovnz  ecx, edx
0x14000e760  xor     edx, edx; PriorityBoost
0x14000e762  mov     [rbx+3], cl
0x14000e765  mov     rcx, [rsi]
0x14000e768  mov     [rcx+30h], eax
0x14000e76b  mov     rcx, [rsi]; Irp
0x14000e76e  call    cs:__imp_IofCompleteRequest
0x14000e775  nop     dword ptr [rax+rax+00h]
0x14000e77a  lea     rcx, [rdi+2E0h]; RemoveLock
0x14000e781  mov     r8d, 20h ; ' '; RemlockSize
0x14000e787  lea     rdx, USBSTOR_QuiesceDeviceWorkItem; Tag
0x14000e78e  call    cs:__imp_IoReleaseRemoveLockEx
0x14000e795  nop     dword ptr [rax+rax+00h]
0x14000e79a  mov     rbx, [rsp+28h+arg_0]
0x14000e79f  mov     rsi, [rsp+28h+arg_8]
0x14000e7a4  add     rsp, 20h
0x14000e7a8  pop     rdi
0x14000e7a9  retn
```
