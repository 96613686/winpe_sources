# USBSTOR_PdoQuiesceDevice

- ea: `0x14000c96c`
- end: `0x14000ca61`
- name: `USBSTOR_PdoQuiesceDevice`
- size: `245`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004ed0`

## callees

- `0x140003630`
- `0x14000c96c`
- `0x14000ca68`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000c9aa`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000c9aa`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_PdoQuiesceDevice(_QWORD *Object, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v5; // rbp
  NTSTATUS result; // eax
  struct _LIST_ENTRY *v7; // rdx

  v2 = Object[8];
  v5 = *(_QWORD *)(*(_QWORD *)(v2 + 16) + 64LL);
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 736), USBSTOR_QuiesceDeviceWorkItem, File, 1u, 0x20u);
  if ( result >= 0 )
  {
    USBSTOR_LogEntry(1146179920, Object, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    v7 = *(struct _LIST_ENTRY **)(v2 + 728);
    *(_QWORD *)(v2 + 688) = v2 + 368;
    *(_QWORD *)(v2 + 680) = a2;
    USBSTOR_QueueWorkItem(
      Object,
      v7,
      (PIO_WORKITEM_ROUTINE_EX)USBSTOR_QuiesceDeviceWorkItem,
      (PVOID)(v2 + 680),
      *(_BYTE *)(v5 + 1876) == 0);
    return 259;
  }
  return result;
}

```

## disassembly

```asm
0x14000c96c  push    rbx
0x14000c96e  push    rbp
0x14000c96f  push    rsi
0x14000c970  push    rdi
0x14000c971  sub     rsp, 38h
0x14000c975  mov     rbx, [rcx+40h]
0x14000c979  lea     r8, File; File
0x14000c980  mov     rsi, rdx
0x14000c983  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x14000c98b  mov     rdi, rcx
0x14000c98e  lea     rdx, USBSTOR_QuiesceDeviceWorkItem; Tag
0x14000c995  mov     r9d, 1; Line
0x14000c99b  mov     rax, [rbx+10h]
0x14000c99f  lea     rcx, [rbx+2E0h]; RemoveLock
0x14000c9a6  mov     rbp, [rax+40h]
0x14000c9aa  call    cs:__imp_IoAcquireRemoveLockEx
0x14000c9b1  nop     dword ptr [rax+rax+00h]
0x14000c9b6  test    eax, eax
0x14000c9b8  js      loc_14000CA57
0x14000c9be  xor     r9d, r9d
0x14000c9c1  xor     r8d, r8d
0x14000c9c4  mov     rdx, rdi
0x14000c9c7  mov     ecx, 44515150h
0x14000c9cc  call    USBSTOR_LogEntry
0x14000c9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9d8  lea     rax, WPP_GLOBAL_Control
0x14000c9df  cmp     rcx, rax
0x14000c9e2  jz      short loc_14000CA06
0x14000c9e4  mov     eax, [rcx+2Ch]
0x14000c9e7  test    al, 1
0x14000c9e9  jz      short loc_14000CA06
0x14000c9eb  cmp     byte ptr [rcx+29h], 5
0x14000c9ef  jb      short loc_14000CA06
0x14000c9f1  mov     rcx, [rcx+18h]
0x14000c9f5  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000c9fc  mov     edx, 7Fh
0x14000ca01  call    WPP_SF_
0x14000ca06  mov     rax, [rsi+0B8h]
0x14000ca0d  lea     rcx, [rbx+2A8h]
0x14000ca14  lea     r8, USBSTOR_QuiesceDeviceWorkItem; WorkerRoutine
0x14000ca1b  or      byte ptr [rax+3], 1
0x14000ca1f  lea     rax, [rbx+170h]
0x14000ca26  mov     rdx, [rbx+2D8h]; Entry
0x14000ca2d  mov     [rbx+2B0h], rax
0x14000ca34  mov     [rcx], rsi
0x14000ca37  cmp     byte ptr [rbp+754h], 0
0x14000ca3e  setz    al
0x14000ca41  mov     [rsp+58h+var_30], al; char
0x14000ca45  mov     qword ptr [rsp+58h+RemlockSize], rcx; Context
0x14000ca4a  mov     rcx, rdi; Object
0x14000ca4d  call    USBSTOR_QueueWorkItem
0x14000ca52  mov     eax, 103h
0x14000ca57  add     rsp, 38h
0x14000ca5b  pop     rdi
0x14000ca5c  pop     rsi
0x14000ca5d  pop     rbp
0x14000ca5e  pop     rbx
0x14000ca5f  retn
```
