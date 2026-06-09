# USBSTOR_FdoCancelStopRemoveDevice

- ea: `0x14001fb7c`
- end: `0x14001fca1`
- name: `USBSTOR_FdoCancelStopRemoveDevice`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x14001fb7c`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001fbec`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001fbec`
- `ntoskrnl!IofCompleteRequest` at `0x14001fc3d`
- `ntoskrnl!IofCompleteRequest` at `0x14001fc3d`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoCancelStopRemoveDevice(__int64 a1, IRP *a2)
{
  __int64 v4; // rcx
  int Status; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1146245955, a1, a2, 0);
  v4 = *(_QWORD *)(a1 + 64);
  a2->IoStatus.Status = 0;
  if ( IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v4 + 24), a2) )
  {
    Status = a2->IoStatus.Status;
    if ( Status >= 0 )
      goto LABEL_13;
  }
  else
  {
    Status = -1073741823;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
LABEL_13:
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1685222243, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001fb7c  mov     [rsp+arg_0], rbx
0x14001fb81  mov     [rsp+arg_8], rdi
0x14001fb86  push    r14
0x14001fb88  sub     rsp, 20h
0x14001fb8c  mov     rdi, rdx
0x14001fb8f  mov     rbx, rcx
0x14001fb92  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb99  lea     r14, WPP_GLOBAL_Control
0x14001fba0  cmp     rcx, r14
0x14001fba3  jz      short loc_14001FBC7
0x14001fba5  mov     eax, [rcx+2Ch]
0x14001fba8  test    al, 2
0x14001fbaa  jz      short loc_14001FBC7
0x14001fbac  cmp     byte ptr [rcx+29h], 4
0x14001fbb0  jb      short loc_14001FBC7
0x14001fbb2  mov     rcx, [rcx+18h]
0x14001fbb6  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001fbbd  mov     edx, 65h ; 'e'
0x14001fbc2  call    WPP_SF_
0x14001fbc7  xor     r9d, r9d
0x14001fbca  mov     r8, rdi
0x14001fbcd  mov     rdx, rbx
0x14001fbd0  mov     ecx, 44525343h
0x14001fbd5  call    USBSTOR_LogEntry
0x14001fbda  mov     rcx, [rbx+40h]
0x14001fbde  mov     rdx, rdi; Irp
0x14001fbe1  mov     dword ptr [rdi+30h], 0
0x14001fbe8  mov     rcx, [rcx+18h]; DeviceObject
0x14001fbec  call    cs:__imp_IoForwardIrpSynchronously
0x14001fbf3  nop     dword ptr [rax+rax+00h]
0x14001fbf8  test    al, al
0x14001fbfa  jz      short loc_14001FC05
0x14001fbfc  mov     ebx, [rdi+30h]
0x14001fbff  test    ebx, ebx
0x14001fc01  jns     short loc_14001FC38
0x14001fc03  jmp     short loc_14001FC0A
0x14001fc05  mov     ebx, 0C0000001h
0x14001fc0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc11  cmp     rcx, r14
0x14001fc14  jz      short loc_14001FC38
0x14001fc16  mov     eax, [rcx+2Ch]
0x14001fc19  test    al, 2
0x14001fc1b  jz      short loc_14001FC38
0x14001fc1d  cmp     byte ptr [rcx+29h], 2
0x14001fc21  jb      short loc_14001FC38
0x14001fc23  mov     rcx, [rcx+18h]
0x14001fc27  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001fc2e  mov     edx, 66h ; 'f'
0x14001fc33  call    WPP_SF_
0x14001fc38  xor     edx, edx; PriorityBoost
0x14001fc3a  mov     rcx, rdi; Irp
0x14001fc3d  call    cs:__imp_IofCompleteRequest
0x14001fc44  nop     dword ptr [rax+rax+00h]
0x14001fc49  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc50  cmp     rcx, r14
0x14001fc53  jz      short loc_14001FC7A
0x14001fc55  mov     eax, [rcx+2Ch]
0x14001fc58  test    al, 2
0x14001fc5a  jz      short loc_14001FC7A
0x14001fc5c  cmp     byte ptr [rcx+29h], 4
0x14001fc60  jb      short loc_14001FC7A
0x14001fc62  mov     rcx, [rcx+18h]
0x14001fc66  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001fc6d  mov     edx, 67h ; 'g'
0x14001fc72  mov     r9d, ebx
0x14001fc75  call    WPP_SF_d
0x14001fc7a  movsxd  rdx, ebx
0x14001fc7d  xor     r9d, r9d
0x14001fc80  xor     r8d, r8d
0x14001fc83  mov     ecx, 64727363h
0x14001fc88  call    USBSTOR_LogEntry
0x14001fc8d  mov     rdi, [rsp+28h+arg_8]
0x14001fc92  mov     eax, ebx
0x14001fc94  mov     rbx, [rsp+28h+arg_0]
0x14001fc99  add     rsp, 20h
0x14001fc9d  pop     r14
0x14001fc9f  retn
```
