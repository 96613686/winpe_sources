# USBSTOR_FdoQueryStopRemoveDevice

- ea: `0x140020670`
- end: `0x140020774`
- name: `USBSTOR_FdoQueryStopRemoveDevice`
- size: `260`
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
- `0x140020670`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002070e`
- `ntoskrnl!IofCallDriver` at `0x14002070e`
- `ntoskrnl!IofCompleteRequest` at `0x1400206e3`
- `ntoskrnl!IofCompleteRequest` at `0x1400206e3`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoQueryStopRemoveDevice(__int64 a1, IRP *a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1146245969, a1, a2, 0);
  if ( (*(_DWORD *)(a1 + 48) & 0x2000) != 0 )
  {
    v5 = *(_QWORD *)(a1 + 64);
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    a2->IoStatus.Status = 0;
    v4 = IofCallDriver(*(PDEVICE_OBJECT *)(v5 + 24), a2);
  }
  else
  {
    v4 = -1073741823;
    a2->IoStatus.Status = -1073741823;
    IofCompleteRequest(a2, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1685222257, v4, 0, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140020670  mov     [rsp+arg_0], rbx
0x140020675  mov     [rsp+arg_8], rsi
0x14002067a  push    rdi
0x14002067b  sub     rsp, 20h
0x14002067f  mov     rdi, rdx
0x140020682  mov     rbx, rcx
0x140020685  mov     rcx, cs:WPP_GLOBAL_Control
0x14002068c  lea     rsi, WPP_GLOBAL_Control
0x140020693  cmp     rcx, rsi
0x140020696  jz      short loc_1400206BA
0x140020698  mov     eax, [rcx+2Ch]
0x14002069b  test    al, 2
0x14002069d  jz      short loc_1400206BA
0x14002069f  cmp     byte ptr [rcx+29h], 4
0x1400206a3  jb      short loc_1400206BA
0x1400206a5  mov     rcx, [rcx+18h]
0x1400206a9  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400206b0  mov     edx, 63h ; 'c'
0x1400206b5  call    WPP_SF_
0x1400206ba  xor     r9d, r9d
0x1400206bd  mov     r8, rdi
0x1400206c0  mov     rdx, rbx
0x1400206c3  mov     ecx, 44525351h
0x1400206c8  call    USBSTOR_LogEntry
0x1400206cd  test    dword ptr [rbx+30h], 2000h
0x1400206d4  jnz     short loc_1400206F1
0x1400206d6  mov     ebx, 0C0000001h
0x1400206db  xor     edx, edx; PriorityBoost
0x1400206dd  mov     rcx, rdi; Irp
0x1400206e0  mov     [rdi+30h], ebx
0x1400206e3  call    cs:__imp_IofCompleteRequest
0x1400206ea  nop     dword ptr [rax+rax+00h]
0x1400206ef  jmp     short loc_14002071C
0x1400206f1  mov     rcx, [rbx+40h]
0x1400206f5  mov     rdx, rdi; Irp
0x1400206f8  inc     byte ptr [rdi+43h]
0x1400206fb  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140020703  mov     dword ptr [rdi+30h], 0
0x14002070a  mov     rcx, [rcx+18h]; DeviceObject
0x14002070e  call    cs:__imp_IofCallDriver
0x140020715  nop     dword ptr [rax+rax+00h]
0x14002071a  mov     ebx, eax
0x14002071c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020723  cmp     rcx, rsi
0x140020726  jz      short loc_14002074E
0x140020728  mov     edx, [rcx+2Ch]
0x14002072b  test    dl, 2
0x14002072e  jz      short loc_14002074E
0x140020730  cmp     byte ptr [rcx+29h], 4
0x140020734  jb      short loc_14002074E
0x140020736  mov     rcx, [rcx+18h]
0x14002073a  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140020741  mov     edx, 64h ; 'd'
0x140020746  mov     r9d, ebx
0x140020749  call    WPP_SF_d
0x14002074e  movsxd  rdx, ebx
0x140020751  xor     r9d, r9d
0x140020754  xor     r8d, r8d
0x140020757  mov     ecx, 64727371h
0x14002075c  call    USBSTOR_LogEntry
0x140020761  mov     rsi, [rsp+28h+arg_8]
0x140020766  mov     eax, ebx
0x140020768  mov     rbx, [rsp+28h+arg_0]
0x14002076d  add     rsp, 20h
0x140020771  pop     rdi
0x140020772  retn
```
