# USBSTOR_FdoQueryCapabilities

- ea: `0x1400244e0`
- end: `0x14002460d`
- name: `USBSTOR_FdoQueryCapabilities`
- size: `301`
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
- `0x1400244e0`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002454f`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14002454f`
- `ntoskrnl!IofCompleteRequest` at `0x1400245af`
- `ntoskrnl!IofCompleteRequest` at `0x1400245af`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoQueryCapabilities(__int64 a1, IRP *a2)
{
  __int64 v2; // rbp
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  int Status; // ebx

  v2 = *(_QWORD *)(a1 + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1346588998, a1, a2, 0);
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v2 + 24), a2) )
  {
    Status = a2->IoStatus.Status;
    if ( Status >= 0 )
    {
      if ( *(_DWORD *)(v2 + 124) )
        HIDWORD(SecurityContext->SecurityQos) &= ~0x10u;
      HIDWORD(SecurityContext->SecurityQos) |= 0x200u;
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
LABEL_15:
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1885565286, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400244e0  push    rbx
0x1400244e2  push    rbp
0x1400244e3  push    rsi
0x1400244e4  push    rdi
0x1400244e5  push    r12
0x1400244e7  sub     rsp, 20h
0x1400244eb  mov     rbp, [rcx+40h]
0x1400244ef  mov     rsi, rdx
0x1400244f2  mov     rbx, rcx
0x1400244f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400244fc  lea     r12, WPP_GLOBAL_Control
0x140024503  cmp     rcx, r12
0x140024506  jz      short loc_14002452A
0x140024508  mov     eax, [rcx+2Ch]
0x14002450b  test    al, 2
0x14002450d  jz      short loc_14002452A
0x14002450f  cmp     byte ptr [rcx+29h], 4
0x140024513  jb      short loc_14002452A
0x140024515  mov     rcx, [rcx+18h]
0x140024519  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024520  mov     edx, 6Bh ; 'k'
0x140024525  call    WPP_SF_
0x14002452a  xor     r9d, r9d
0x14002452d  mov     r8, rsi
0x140024530  mov     rdx, rbx
0x140024533  mov     ecx, 50435146h
0x140024538  call    USBSTOR_LogEntry
0x14002453d  mov     rax, [rsi+0B8h]
0x140024544  mov     rdx, rsi; Irp
0x140024547  mov     rcx, [rbp+18h]; DeviceObject
0x14002454b  mov     rdi, [rax+8]
0x14002454f  call    cs:__imp_IoForwardIrpSynchronously
0x140024556  nop     dword ptr [rax+rax+00h]
0x14002455b  test    al, al
0x14002455d  jz      short loc_140024577
0x14002455f  mov     ebx, [rsi+30h]
0x140024562  test    ebx, ebx
0x140024564  js      short loc_14002457C
0x140024566  cmp     dword ptr [rbp+7Ch], 0
0x14002456a  jz      short loc_140024570
0x14002456c  and     dword ptr [rdi+4], 0FFFFFFEFh
0x140024570  bts     dword ptr [rdi+4], 9
0x140024575  jmp     short loc_1400245AA
0x140024577  mov     ebx, 0C0000001h
0x14002457c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024583  cmp     rcx, r12
0x140024586  jz      short loc_1400245AA
0x140024588  mov     eax, [rcx+2Ch]
0x14002458b  test    al, 2
0x14002458d  jz      short loc_1400245AA
0x14002458f  cmp     byte ptr [rcx+29h], 2
0x140024593  jb      short loc_1400245AA
0x140024595  mov     rcx, [rcx+18h]
0x140024599  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400245a0  mov     edx, 6Ch ; 'l'
0x1400245a5  call    WPP_SF_
0x1400245aa  xor     edx, edx; PriorityBoost
0x1400245ac  mov     rcx, rsi; Irp
0x1400245af  call    cs:__imp_IofCompleteRequest
0x1400245b6  nop     dword ptr [rax+rax+00h]
0x1400245bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400245c2  cmp     rcx, r12
0x1400245c5  jz      short loc_1400245EC
0x1400245c7  mov     eax, [rcx+2Ch]
0x1400245ca  test    al, 2
0x1400245cc  jz      short loc_1400245EC
0x1400245ce  cmp     byte ptr [rcx+29h], 4
0x1400245d2  jb      short loc_1400245EC
0x1400245d4  mov     rcx, [rcx+18h]
0x1400245d8  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400245df  mov     edx, 6Dh ; 'm'
0x1400245e4  mov     r9d, ebx
0x1400245e7  call    WPP_SF_d
0x1400245ec  movsxd  rdx, ebx
0x1400245ef  xor     r9d, r9d
0x1400245f2  xor     r8d, r8d
0x1400245f5  mov     ecx, 70637166h
0x1400245fa  call    USBSTOR_LogEntry
0x1400245ff  mov     eax, ebx
0x140024601  add     rsp, 20h
0x140024605  pop     r12
0x140024607  pop     rdi
0x140024608  pop     rsi
0x140024609  pop     rbp
0x14002460a  pop     rbx
0x14002460b  retn
```
