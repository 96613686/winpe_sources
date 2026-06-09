# USBSTOR_PdoQueryDeviceRelations

- ea: `0x140024370`
- end: `0x1400244d8`
- name: `USBSTOR_PdoQueryDeviceRelations`
- size: `360`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140024370`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400243de`
- `ntoskrnl!ExAllocatePool2` at `0x1400243de`
- `ntoskrnl!ObfReferenceObject` at `0x140024403`
- `ntoskrnl!ObfReferenceObject` at `0x140024403`
- `ntoskrnl!IofCompleteRequest` at `0x140024422`
- `ntoskrnl!IofCompleteRequest` at `0x140024422`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoQueryDeviceRelations(PVOID Object, PIRP Irp)
{
  __int64 Length; // rdi
  __int64 Pool2; // rax
  ULONG_PTR v6; // r14
  NTSTATUS Status; // edi

  Length = (int)Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1380208976, Object, Irp, Length);
  if ( (_DWORD)Length == 4 )
  {
    Pool2 = ExAllocatePool2(256, 16, 1396788565);
    v6 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = 1;
      *(_QWORD *)(Pool2 + 8) = Object;
      ObfReferenceObject(Object);
      Status = 0;
      Irp->IoStatus.Information = v6;
    }
    else
    {
      Status = -1073741670;
      Irp->IoStatus.Information = 0;
    }
    Irp->IoStatus.Status = Status;
  }
  else
  {
    Status = Irp->IoStatus.Status;
  }
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1919185264, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140024370  push    rdi
0x140024372  sub     rsp, 20h
0x140024376  mov     rax, [rdx+0B8h]
0x14002437d  mov     [rsp+28h+arg_0], rbx
0x140024382  mov     rbx, rdx
0x140024385  mov     [rsp+28h+arg_8], rbp
0x14002438a  mov     [rsp+28h+arg_10], rsi
0x14002438f  mov     rsi, rcx
0x140024392  movsxd  rdi, dword ptr [rax+8]
0x140024396  mov     rcx, cs:WPP_GLOBAL_Control
0x14002439d  lea     rbp, WPP_GLOBAL_Control
0x1400243a4  cmp     rcx, rbp
0x1400243a7  jnz     loc_140024465
0x1400243ad  mov     r9, rdi
0x1400243b0  mov     r8, rbx
0x1400243b3  mov     rdx, rsi
0x1400243b6  mov     ecx, 52445150h
0x1400243bb  call    USBSTOR_LogEntry
0x1400243c0  cmp     edi, 4
0x1400243c3  jnz     loc_1400244BE
0x1400243c9  mov     edx, 10h
0x1400243ce  mov     [rsp+28h+arg_18], r14
0x1400243d3  mov     ecx, 100h
0x1400243d8  mov     r8d, 53414D55h
0x1400243de  call    cs:__imp_ExAllocatePool2
0x1400243e5  nop     dword ptr [rax+rax+00h]
0x1400243ea  mov     r14, rax
0x1400243ed  test    rax, rax
0x1400243f0  jz      loc_1400244C6
0x1400243f6  mov     rcx, rsi; Object
0x1400243f9  mov     dword ptr [rax], 1
0x1400243ff  mov     [rax+8], rsi
0x140024403  call    cs:__imp_ObfReferenceObject
0x14002440a  nop     dword ptr [rax+rax+00h]
0x14002440f  xor     edi, edi
0x140024411  mov     [rbx+38h], r14
0x140024415  mov     r14, [rsp+28h+arg_18]
0x14002441a  mov     [rbx+30h], edi
0x14002441d  xor     edx, edx; PriorityBoost
0x14002441f  mov     rcx, rbx; Irp
0x140024422  call    cs:__imp_IofCompleteRequest
0x140024429  nop     dword ptr [rax+rax+00h]
0x14002442e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024435  mov     rsi, [rsp+28h+arg_10]
0x14002443a  cmp     rcx, rbp
0x14002443d  mov     rbp, [rsp+28h+arg_8]
0x140024442  mov     rbx, [rsp+28h+arg_0]
0x140024447  jnz     short loc_140024497
0x140024449  movsxd  rdx, edi
0x14002444c  xor     r9d, r9d
0x14002444f  xor     r8d, r8d
0x140024452  mov     ecx, 72647170h
0x140024457  call    USBSTOR_LogEntry
0x14002445c  mov     eax, edi
0x14002445e  add     rsp, 20h
0x140024462  pop     rdi
0x140024463  retn
0x140024465  mov     eax, [rcx+2Ch]
0x140024468  test    al, 2
0x14002446a  jz      loc_1400243AD
0x140024470  cmp     byte ptr [rcx+29h], 4
0x140024474  jb      loc_1400243AD
0x14002447a  mov     rcx, [rcx+18h]
0x14002447e  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024485  mov     edx, 8Eh
0x14002448a  mov     r9d, edi
0x14002448d  call    WPP_SF_d
0x140024492  jmp     loc_1400243AD
0x140024497  mov     eax, [rcx+2Ch]
0x14002449a  test    al, 2
0x14002449c  jz      short loc_140024449
0x14002449e  cmp     byte ptr [rcx+29h], 4
0x1400244a2  jb      short loc_140024449
0x1400244a4  mov     rcx, [rcx+18h]
0x1400244a8  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400244af  mov     edx, 8Fh
0x1400244b4  mov     r9d, edi
0x1400244b7  call    WPP_SF_d
0x1400244bc  jmp     short loc_140024449
0x1400244be  mov     edi, [rbx+30h]
0x1400244c1  jmp     loc_14002441D
0x1400244c6  mov     edi, 0C000009Ah
0x1400244cb  mov     qword ptr [rbx+38h], 0
0x1400244d3  jmp     loc_140024415
```
