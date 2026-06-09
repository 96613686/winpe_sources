# USBSTOR_PdoQueryPnpDeviceState

- ea: `0x140024fd8`
- end: `0x1400250b1`
- name: `USBSTOR_PdoQueryPnpDeviceState`
- size: `217`
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
- `0x140024fd8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002504f`
- `ntoskrnl!IofCompleteRequest` at `0x14002504f`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoQueryPnpDeviceState(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 149, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1396986192, a1, a2, 0);
  if ( (*(_DWORD *)(a1 + 48) & 0x2000) == 0 )
    a2->IoStatus.Information |= 0x20uLL;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 150, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1935962480, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140024fd8  mov     [rsp+arg_0], rbx
0x140024fdd  mov     [rsp+arg_8], rsi
0x140024fe2  push    rdi
0x140024fe3  sub     rsp, 20h
0x140024fe7  mov     rbx, rdx
0x140024fea  mov     rdi, rcx
0x140024fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ff4  lea     rsi, WPP_GLOBAL_Control
0x140024ffb  cmp     rcx, rsi
0x140024ffe  jz      short loc_140025022
0x140025000  mov     eax, [rcx+2Ch]
0x140025003  test    al, 2
0x140025005  jz      short loc_140025022
0x140025007  cmp     byte ptr [rcx+29h], 4
0x14002500b  jb      short loc_140025022
0x14002500d  mov     rcx, [rcx+18h]
0x140025011  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140025018  mov     edx, 95h
0x14002501d  call    WPP_SF_
0x140025022  xor     r9d, r9d
0x140025025  mov     r8, rbx
0x140025028  mov     rdx, rdi
0x14002502b  mov     ecx, 53445150h
0x140025030  call    USBSTOR_LogEntry
0x140025035  test    dword ptr [rdi+30h], 2000h
0x14002503c  jnz     short loc_140025043
0x14002503e  or      qword ptr [rbx+38h], 20h
0x140025043  xor     edx, edx; PriorityBoost
0x140025045  mov     dword ptr [rbx+30h], 0
0x14002504c  mov     rcx, rbx; Irp
0x14002504f  call    cs:__imp_IofCompleteRequest
0x140025056  nop     dword ptr [rax+rax+00h]
0x14002505b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025062  cmp     rcx, rsi
0x140025065  jz      short loc_14002508C
0x140025067  mov     eax, [rcx+2Ch]
0x14002506a  test    al, 2
0x14002506c  jz      short loc_14002508C
0x14002506e  cmp     byte ptr [rcx+29h], 4
0x140025072  jb      short loc_14002508C
0x140025074  mov     rcx, [rcx+18h]
0x140025078  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14002507f  mov     edx, 96h
0x140025084  xor     r9d, r9d
0x140025087  call    WPP_SF_d
0x14002508c  xor     r9d, r9d
0x14002508f  xor     r8d, r8d
0x140025092  xor     edx, edx
0x140025094  mov     ecx, 73647170h
0x140025099  call    USBSTOR_LogEntry
0x14002509e  mov     rbx, [rsp+28h+arg_0]
0x1400250a3  xor     eax, eax
0x1400250a5  mov     rsi, [rsp+28h+arg_8]
0x1400250aa  add     rsp, 20h
0x1400250ae  pop     rdi
0x1400250af  retn
```
