# BthEnumQueryProtocol

- ea: `0x14001d7d8`
- end: `0x14001d952`
- name: `BthEnumQueryProtocol`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001cf90`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x14001d7d8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001d876`
- `ntoskrnl!IofCallDriver` at `0x14001d876`
- `ntoskrnl!KeInitializeEvent` at `0x14001d811`
- `ntoskrnl!KeInitializeEvent` at `0x14001d811`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14001d854`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14001d854`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d89e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d89e`

## pseudocode

```c
__int64 __fastcall BthEnumQueryProtocol(__int64 a1)
{
  __int64 v1; // rbx
  IRP *v2; // rax
  NTSTATUS v4; // eax
  int v5; // edx
  __int64 OutputBufferLength; // [rsp+28h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-30h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-20h] BYREF
  int OutputBuffer; // [rsp+90h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  OutputBuffer = 0;
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v2 = IoBuildDeviceIoControlRequest(
         0x12008Cu,
         *(PDEVICE_OBJECT *)(v1 + 24),
         0,
         0,
         &OutputBuffer,
         4u,
         1u,
         &Event,
         &IoStatusBlock);
  if ( !v2 )
    return 3221225626LL;
  v4 = IofCallDriver(*(PDEVICE_OBJECT *)(v1 + 24), v2);
  if ( v4 == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  else if ( v4 < 0 )
  {
LABEL_10:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        3,
        13,
        (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
    *(_DWORD *)(v1 + 208) = 0;
    return 0;
  }
  if ( IoStatusBlock.Status < 0 )
    goto LABEL_10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(OutputBufferLength) = OutputBuffer;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      12,
      (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids,
      OutputBufferLength);
  }
  *(_DWORD *)(v1 + 208) = OutputBuffer;
  return 0;
}

```

## disassembly

```asm
0x14001d7d8  mov     [rsp-8+arg_8], rbx
0x14001d7dd  push    rbp
0x14001d7de  mov     rbp, rsp
0x14001d7e1  sub     rsp, 80h
0x14001d7e8  mov     rbx, [rcx+40h]
0x14001d7ec  xor     eax, eax
0x14001d7ee  xorps   xmm0, xmm0
0x14001d7f1  mov     [rbp+arg_0], 0
0x14001d7f8  xorps   xmm1, xmm1
0x14001d7fb  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14001d7ff  xor     r8d, r8d; State
0x14001d802  lea     rcx, [rbp+Event]; Event
0x14001d806  lea     edx, [rax+1]; Type
0x14001d809  movups  xmmword ptr [rbp+var_30.___u0], xmm0
0x14001d80d  movups  xmmword ptr [rbp+Event.Header.___u0], xmm1
0x14001d811  call    cs:__imp_KeInitializeEvent
0x14001d818  nop     dword ptr [rax+rax+00h]
0x14001d81d  mov     rdx, [rbx+18h]; DeviceObject
0x14001d821  lea     rax, [rbp+var_30]
0x14001d825  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x14001d82a  xor     r9d, r9d; InputBufferLength
0x14001d82d  lea     rax, [rbp+Event]
0x14001d831  xor     r8d, r8d; InputBuffer
0x14001d834  mov     [rsp+80h+var_48], rax; Event
0x14001d839  mov     ecx, 12008Ch; IoControlCode
0x14001d83e  mov     [rsp+80h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x14001d843  lea     rax, [rbp+arg_0]
0x14001d847  mov     dword ptr [rsp+80h+OutputBufferLength], 4; OutputBufferLength
0x14001d84f  mov     [rsp+80h+OutputBuffer], rax; OutputBuffer
0x14001d854  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14001d85b  nop     dword ptr [rax+rax+00h]
0x14001d860  test    rax, rax
0x14001d863  jnz     short loc_14001D86F
0x14001d865  mov     eax, 0C000009Ah
0x14001d86a  jmp     loc_14001D940
0x14001d86f  mov     rcx, [rbx+18h]; DeviceObject
0x14001d873  mov     rdx, rax; Irp
0x14001d876  call    cs:__imp_IofCallDriver
0x14001d87d  nop     dword ptr [rax+rax+00h]
0x14001d882  cmp     eax, 103h
0x14001d887  jnz     short loc_14001D8AC
0x14001d889  xor     r9d, r9d; Alertable
0x14001d88c  mov     [rsp+80h+OutputBuffer], 0; Timeout
0x14001d895  xor     r8d, r8d; WaitMode
0x14001d898  lea     rcx, [rbp+Event]; Object
0x14001d89c  xor     edx, edx; WaitReason
0x14001d89e  call    cs:__imp_KeWaitForSingleObject
0x14001d8a5  nop     dword ptr [rax+rax+00h]
0x14001d8aa  jmp     short loc_14001D8B0
0x14001d8ac  test    eax, eax
0x14001d8ae  js      short loc_14001D8FE
0x14001d8b0  cmp     dword ptr [rbp+var_30.___u0], 0
0x14001d8b4  jl      short loc_14001D8FE
0x14001d8b6  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d8bd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d8c4  jz      short loc_14001D8F3
0x14001d8c6  mov     eax, [rbp+arg_0]
0x14001d8c9  mov     r9d, 0Ch
0x14001d8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d8d6  mov     dword ptr [rsp+80h+OutputBufferLength], eax
0x14001d8da  lea     rax, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001d8e1  mov     [rsp+80h+OutputBuffer], rax
0x14001d8e6  lea     r8d, [r9-9]
0x14001d8ea  mov     rcx, [rcx+40h]
0x14001d8ee  call    WPP_RECORDER_SF_d
0x14001d8f3  mov     eax, [rbp+arg_0]
0x14001d8f6  mov     [rbx+0D0h], eax
0x14001d8fc  jmp     short loc_14001D93E
0x14001d8fe  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d905  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d90c  jz      short loc_14001D934
0x14001d90e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d915  lea     rax, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001d91c  mov     r9d, 0Dh
0x14001d922  mov     [rsp+80h+OutputBuffer], rax
0x14001d927  mov     rcx, [rcx+40h]
0x14001d92b  lea     r8d, [r9-0Ah]
0x14001d92f  call    WPP_RECORDER_SF_
0x14001d934  mov     dword ptr [rbx+0D0h], 0
0x14001d93e  xor     eax, eax
0x14001d940  mov     rbx, [rsp+80h+arg_8]
0x14001d948  add     rsp, 80h
0x14001d94f  pop     rbp
0x14001d950  retn
```
