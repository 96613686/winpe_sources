# USBSTOR_InitializeEmergencyWorkerThread

- ea: `0x140012d0c`
- end: `0x140012e40`
- name: `USBSTOR_InitializeEmergencyWorkerThread`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001fca8`

## callees

- `0x140012d0c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140012e23`
- `ntoskrnl!KeSetEvent` at `0x140012e23`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012d44`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012d44`
- `ntoskrnl!ZwClose` at `0x140012e0b`
- `ntoskrnl!ZwClose` at `0x140012e0b`
- `ntoskrnl!KeInitializeQueue` at `0x140012d66`
- `ntoskrnl!KeInitializeQueue` at `0x140012d66`
- `ntoskrnl!PsCreateSystemThread` at `0x140012db3`
- `ntoskrnl!PsCreateSystemThread` at `0x140012db3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012dee`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012dee`

## pseudocode

```c
__int64 USBSTOR_InitializeEmergencyWorkerThread()
{
  NTSTATUS v0; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ThreadHandle; // [rsp+80h] [rbp+10h] BYREF
  PVOID Object; // [rsp+88h] [rbp+18h] BYREF

  v0 = 0;
  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  KeWaitForSingleObject(&EmergencyWorkerThreadEvent, Executive, 0, 0, 0);
  if ( !EmergencyWorkerThread )
  {
    KeInitializeQueue(&EmergencyWorkQueue, 0);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v0 = PsCreateSystemThread(&ThreadHandle, 0, &ObjectAttributes, 0, 0, USBSTOR_WorkerStart, 0);
    if ( v0 >= 0 )
    {
      Object = 0;
      v0 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
      EmergencyWorkerThread = Object;
      ZwClose(ThreadHandle);
    }
  }
  KeSetEvent(&EmergencyWorkerThreadEvent, 0, 0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140012d0c  mov     [rsp-8+arg_10], rbx
0x140012d11  push    rbp
0x140012d12  mov     rbp, rsp
0x140012d15  sub     rsp, 70h
0x140012d19  xorps   xmm0, xmm0
0x140012d1c  lea     rcx, EmergencyWorkerThreadEvent; Object
0x140012d23  xor     eax, eax
0x140012d25  xor     ebx, ebx
0x140012d27  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140012d2b  xor     r9d, r9d; Alertable
0x140012d2e  mov     [rbp+ThreadHandle], rbx
0x140012d32  xor     r8d, r8d; WaitMode
0x140012d35  mov     [rsp+70h+Timeout], rax; Timeout
0x140012d3a  xor     edx, edx; WaitReason
0x140012d3c  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012d40  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012d44  call    cs:__imp_KeWaitForSingleObject
0x140012d4b  nop     dword ptr [rax+rax+00h]
0x140012d50  cmp     cs:EmergencyWorkerThread, rbx
0x140012d57  jnz     loc_140012E17
0x140012d5d  xor     edx, edx; Count
0x140012d5f  lea     rcx, EmergencyWorkQueue; Queue
0x140012d66  call    cs:__imp_KeInitializeQueue
0x140012d6d  nop     dword ptr [rax+rax+00h]
0x140012d72  lea     rax, USBSTOR_WorkerStart
0x140012d79  mov     [rsp+70h+StartContext], rbx; StartContext
0x140012d7e  xorps   xmm0, xmm0
0x140012d81  mov     [rsp+70h+StartRoutine], rax; StartRoutine
0x140012d86  xor     r9d, r9d; ProcessHandle
0x140012d89  mov     [rsp+70h+Timeout], rbx; ClientId
0x140012d8e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012d92  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012d99  xor     edx, edx; DesiredAccess
0x140012d9b  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x140012d9f  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x140012da3  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140012daa  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x140012dae  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012db3  call    cs:__imp_PsCreateSystemThread
0x140012dba  nop     dword ptr [rax+rax+00h]
0x140012dbf  mov     ebx, eax
0x140012dc1  test    eax, eax
0x140012dc3  js      short loc_140012E17
0x140012dc5  mov     rcx, [rbp+ThreadHandle]; Handle
0x140012dc9  lea     rax, [rbp+Object]
0x140012dcd  mov     [rsp+70h+StartRoutine], 0; HandleInformation
0x140012dd6  xor     r9d, r9d; AccessMode
0x140012dd9  xor     r8d, r8d; ObjectType
0x140012ddc  mov     [rsp+70h+Timeout], rax; Object
0x140012de1  mov     edx, 1FFFFFh; DesiredAccess
0x140012de6  mov     [rbp+Object], 0
0x140012dee  call    cs:__imp_ObReferenceObjectByHandle
0x140012df5  nop     dword ptr [rax+rax+00h]
0x140012dfa  mov     rcx, [rbp+ThreadHandle]; Handle
0x140012dfe  mov     ebx, eax
0x140012e00  mov     rax, [rbp+Object]
0x140012e04  mov     cs:EmergencyWorkerThread, rax
0x140012e0b  call    cs:__imp_ZwClose
0x140012e12  nop     dword ptr [rax+rax+00h]
0x140012e17  xor     r8d, r8d; Wait
0x140012e1a  lea     rcx, EmergencyWorkerThreadEvent; Event
0x140012e21  xor     edx, edx; Increment
0x140012e23  call    cs:__imp_KeSetEvent
0x140012e2a  nop     dword ptr [rax+rax+00h]
0x140012e2f  mov     eax, ebx
0x140012e31  mov     rbx, [rsp+70h+arg_10]
0x140012e39  add     rsp, 70h
0x140012e3d  pop     rbp
0x140012e3e  retn
```
