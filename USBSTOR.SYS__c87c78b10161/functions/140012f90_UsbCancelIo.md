# UsbCancelIo

- ea: `0x140012f90`
- end: `0x14001305b`
- name: `UsbCancelIo`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140010664`
- `0x140012f90`
- `0x140013154`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140013010`
- `ntoskrnl!IofCompleteRequest` at `0x140013010`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012fdd`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012fdd`

## pseudocode

```c
void __fastcall UsbCancelIo(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  IoReleaseCancelSpinLock(a2->CancelIrql);
  UsbQueueRemoveIrp(*(_QWORD *)(a1 + 64) + 368LL, a2);
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
}

```

## disassembly

```asm
0x140012f90  mov     [rsp+arg_0], rbx
0x140012f95  mov     [rsp+arg_8], rsi
0x140012f9a  push    rdi
0x140012f9b  sub     rsp, 20h
0x140012f9f  mov     rbx, rdx
0x140012fa2  mov     rdi, rcx
0x140012fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fac  lea     rsi, WPP_GLOBAL_Control
0x140012fb3  cmp     rcx, rsi
0x140012fb6  jz      short loc_140012FDA
0x140012fb8  mov     eax, [rcx+2Ch]
0x140012fbb  test    al, 20h
0x140012fbd  jz      short loc_140012FDA
0x140012fbf  cmp     byte ptr [rcx+29h], 4
0x140012fc3  jb      short loc_140012FDA
0x140012fc5  mov     rcx, [rcx+18h]
0x140012fc9  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140012fd0  mov     edx, 28h ; '('
0x140012fd5  call    WPP_SF_
0x140012fda  mov     cl, [rbx+45h]; Irql
0x140012fdd  call    cs:__imp_IoReleaseCancelSpinLock
0x140012fe4  nop     dword ptr [rax+rax+00h]
0x140012fe9  mov     rcx, [rdi+40h]
0x140012fed  mov     rdx, rbx
0x140012ff0  add     rcx, 170h
0x140012ff7  call    UsbQueueRemoveIrp
0x140012ffc  xor     edx, edx; PriorityBoost
0x140012ffe  mov     dword ptr [rbx+30h], 0C0000120h
0x140013005  mov     rcx, rbx; Irp
0x140013008  mov     qword ptr [rbx+38h], 0
0x140013010  call    cs:__imp_IofCompleteRequest
0x140013017  nop     dword ptr [rax+rax+00h]
0x14001301c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013023  cmp     rcx, rsi
0x140013026  jz      short loc_14001304A
0x140013028  mov     eax, [rcx+2Ch]
0x14001302b  test    al, 20h
0x14001302d  jz      short loc_14001304A
0x14001302f  cmp     byte ptr [rcx+29h], 4
0x140013033  jb      short loc_14001304A
0x140013035  mov     rcx, [rcx+18h]
0x140013039  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140013040  mov     edx, 29h ; ')'
0x140013045  call    WPP_SF_
0x14001304a  mov     rbx, [rsp+28h+arg_0]
0x14001304f  mov     rsi, [rsp+28h+arg_8]
0x140013054  add     rsp, 20h
0x140013058  pop     rdi
0x140013059  retn
```
