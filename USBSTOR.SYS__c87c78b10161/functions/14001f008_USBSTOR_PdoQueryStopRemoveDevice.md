# USBSTOR_PdoQueryStopRemoveDevice

- ea: `0x14001f008`
- end: `0x14001f0e4`
- name: `USBSTOR_PdoQueryStopRemoveDevice`
- size: `220`
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
- `0x14001f008`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001f081`
- `ntoskrnl!IofCompleteRequest` at `0x14001f081`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoQueryStopRemoveDevice(__int64 a1, IRP *a2)
{
  unsigned int v4; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 151, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1146310992, a1, a2, 0);
  v4 = (*(_DWORD *)(a1 + 48) & 0x2000) == 0 ? 0xC0000001 : 0;
  a2->IoStatus.Status = v4;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1685287280, (int)v4, 0, 0);
  return v4;
}

```

## disassembly

```asm
0x14001f008  mov     [rsp+arg_0], rbx
0x14001f00d  mov     [rsp+arg_8], rsi
0x14001f012  push    rdi
0x14001f013  sub     rsp, 20h
0x14001f017  mov     rdi, rdx
0x14001f01a  mov     rbx, rcx
0x14001f01d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f024  lea     rsi, WPP_GLOBAL_Control
0x14001f02b  cmp     rcx, rsi
0x14001f02e  jz      short loc_14001F052
0x14001f030  mov     eax, [rcx+2Ch]
0x14001f033  test    al, 2
0x14001f035  jz      short loc_14001F052
0x14001f037  cmp     byte ptr [rcx+29h], 4
0x14001f03b  jb      short loc_14001F052
0x14001f03d  mov     rcx, [rcx+18h]
0x14001f041  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001f048  mov     edx, 97h
0x14001f04d  call    WPP_SF_
0x14001f052  xor     r9d, r9d
0x14001f055  mov     r8, rdi
0x14001f058  mov     rdx, rbx
0x14001f05b  mov     ecx, 44535150h
0x14001f060  call    USBSTOR_LogEntry
0x14001f065  mov     eax, [rbx+30h]
0x14001f068  mov     rcx, rdi; Irp
0x14001f06b  and     eax, 2000h
0x14001f070  neg     eax
0x14001f072  sbb     ebx, ebx
0x14001f074  xor     edx, edx; PriorityBoost
0x14001f076  not     ebx
0x14001f078  and     ebx, 0C0000001h
0x14001f07e  mov     [rdi+30h], ebx
0x14001f081  call    cs:__imp_IofCompleteRequest
0x14001f088  nop     dword ptr [rax+rax+00h]
0x14001f08d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f094  cmp     rcx, rsi
0x14001f097  jz      short loc_14001F0BE
0x14001f099  mov     eax, [rcx+2Ch]
0x14001f09c  test    al, 2
0x14001f09e  jz      short loc_14001F0BE
0x14001f0a0  cmp     byte ptr [rcx+29h], 4
0x14001f0a4  jb      short loc_14001F0BE
0x14001f0a6  mov     rcx, [rcx+18h]
0x14001f0aa  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001f0b1  mov     edx, 98h
0x14001f0b6  mov     r9d, ebx
0x14001f0b9  call    WPP_SF_d
0x14001f0be  movsxd  rdx, ebx
0x14001f0c1  xor     r9d, r9d
0x14001f0c4  xor     r8d, r8d
0x14001f0c7  mov     ecx, 64737170h
0x14001f0cc  call    USBSTOR_LogEntry
0x14001f0d1  mov     rsi, [rsp+28h+arg_8]
0x14001f0d6  mov     eax, ebx
0x14001f0d8  mov     rbx, [rsp+28h+arg_0]
0x14001f0dd  add     rsp, 20h
0x14001f0e1  pop     rdi
0x14001f0e2  retn
```
