# USBSTOR_PdoQueryCapabilities

- ea: `0x140024cf4`
- end: `0x140024e2c`
- name: `USBSTOR_PdoQueryCapabilities`
- size: `312`
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
- `0x140024cf4`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140024d6b`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140024d6b`
- `ntoskrnl!IofCompleteRequest` at `0x140024dce`
- `ntoskrnl!IofCompleteRequest` at `0x140024dce`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoQueryCapabilities(__int64 a1, IRP *a2)
{
  __int64 v4; // rbp
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  int Status; // ebx

  v4 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL) + 64LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1346589008, a1, a2, 0);
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v4 + 24), a2) )
  {
    Status = a2->IoStatus.Status;
    if ( Status >= 0 )
    {
      if ( !*(_QWORD *)(v4 + 72) )
        HIDWORD(SecurityContext->SecurityQos) &= ~0x40u;
      HIDWORD(SecurityContext->SecurityQos) &= 0xFFFFFCEF;
      goto LABEL_15;
    }
  }
  else
  {
    Status = -1073741823;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 145, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
LABEL_15:
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1885565296, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140024cf4  push    rbx
0x140024cf6  push    rbp
0x140024cf7  push    rsi
0x140024cf8  push    rdi
0x140024cf9  push    r12
0x140024cfb  sub     rsp, 20h
0x140024cff  mov     rax, [rcx+40h]
0x140024d03  mov     rsi, rdx
0x140024d06  mov     rbx, rcx
0x140024d09  mov     r8, [rax+10h]
0x140024d0d  mov     rbp, [r8+40h]
0x140024d11  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d18  lea     r12, WPP_GLOBAL_Control
0x140024d1f  cmp     rcx, r12
0x140024d22  jz      short loc_140024D46
0x140024d24  mov     eax, [rcx+2Ch]
0x140024d27  test    al, 2
0x140024d29  jz      short loc_140024D46
0x140024d2b  cmp     byte ptr [rcx+29h], 4
0x140024d2f  jb      short loc_140024D46
0x140024d31  mov     rcx, [rcx+18h]
0x140024d35  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024d3c  mov     edx, 90h
0x140024d41  call    WPP_SF_
0x140024d46  xor     r9d, r9d
0x140024d49  mov     r8, rsi
0x140024d4c  mov     rdx, rbx
0x140024d4f  mov     ecx, 50435150h
0x140024d54  call    USBSTOR_LogEntry
0x140024d59  mov     rax, [rsi+0B8h]
0x140024d60  mov     rdx, rsi; Irp
0x140024d63  mov     rcx, [rbp+18h]; DeviceObject
0x140024d67  mov     rdi, [rax+8]
0x140024d6b  call    cs:__imp_IoForwardIrpSynchronously
0x140024d72  nop     dword ptr [rax+rax+00h]
0x140024d77  test    al, al
0x140024d79  jz      short loc_140024D96
0x140024d7b  mov     ebx, [rsi+30h]
0x140024d7e  test    ebx, ebx
0x140024d80  js      short loc_140024D9B
0x140024d82  cmp     qword ptr [rbp+48h], 0
0x140024d87  jnz     short loc_140024D8D
0x140024d89  and     dword ptr [rdi+4], 0FFFFFFBFh
0x140024d8d  and     dword ptr [rdi+4], 0FFFFFCEFh
0x140024d94  jmp     short loc_140024DC9
0x140024d96  mov     ebx, 0C0000001h
0x140024d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024da2  cmp     rcx, r12
0x140024da5  jz      short loc_140024DC9
0x140024da7  mov     eax, [rcx+2Ch]
0x140024daa  test    al, 2
0x140024dac  jz      short loc_140024DC9
0x140024dae  cmp     byte ptr [rcx+29h], 2
0x140024db2  jb      short loc_140024DC9
0x140024db4  mov     rcx, [rcx+18h]
0x140024db8  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024dbf  mov     edx, 91h
0x140024dc4  call    WPP_SF_
0x140024dc9  xor     edx, edx; PriorityBoost
0x140024dcb  mov     rcx, rsi; Irp
0x140024dce  call    cs:__imp_IofCompleteRequest
0x140024dd5  nop     dword ptr [rax+rax+00h]
0x140024dda  mov     rcx, cs:WPP_GLOBAL_Control
0x140024de1  cmp     rcx, r12
0x140024de4  jz      short loc_140024E0B
0x140024de6  mov     eax, [rcx+2Ch]
0x140024de9  test    al, 2
0x140024deb  jz      short loc_140024E0B
0x140024ded  cmp     byte ptr [rcx+29h], 4
0x140024df1  jb      short loc_140024E0B
0x140024df3  mov     rcx, [rcx+18h]
0x140024df7  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024dfe  mov     edx, 92h
0x140024e03  mov     r9d, ebx
0x140024e06  call    WPP_SF_d
0x140024e0b  movsxd  rdx, ebx
0x140024e0e  xor     r9d, r9d
0x140024e11  xor     r8d, r8d
0x140024e14  mov     ecx, 70637170h
0x140024e19  call    USBSTOR_LogEntry
0x140024e1e  mov     eax, ebx
0x140024e20  add     rsp, 20h
0x140024e24  pop     r12
0x140024e26  pop     rdi
0x140024e27  pop     rsi
0x140024e28  pop     rbp
0x140024e29  pop     rbx
0x140024e2a  retn
```
