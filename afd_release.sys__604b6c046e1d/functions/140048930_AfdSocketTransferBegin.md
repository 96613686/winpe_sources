# AfdSocketTransferBegin

- ea: `0x140048930`
- end: `0x140048b69`
- name: `AfdSocketTransferBegin`
- size: `569`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14001c708`
- `0x14001e7e0`
- `0x140032778`
- `0x140033bdc`
- `0x140048930`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140048a70`
- `ntoskrnl!KeInitializeEvent` at `0x140048a70`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048ae8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048ae8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048992`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048992`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400489b9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400489b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048986`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048986`
- `ntoskrnl!IofCompleteRequest` at `0x140048b4d`
- `ntoskrnl!IofCompleteRequest` at `0x140048b4d`
- `ntoskrnl!IofCallDriver` at `0x140048abd`
- `ntoskrnl!IofCallDriver` at `0x140048abd`

## string_xrefs

- `0x14004897a`: `\Device\BTHMS_RFCOMM`

## pseudocode

```c
__int64 __fastcall AfdSocketTransferBegin(PIRP Irp, __int64 a2)
{
  NTSTATUS Status; // edi
  __int64 v4; // rbx
  __int64 v5; // rax
  char v6; // r14
  __int64 ConnectionReferenceFromEndpoint; // rax
  __int64 v8; // rsi
  struct _DEVICE_OBJECT *v9; // rdi
  struct _FILE_OBJECT *v10; // r15
  char v11; // al
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v13; // rax
  signed __int64 v14; // rax
  bool v15; // cc
  signed __int64 v16; // rax
  CCHAR v17; // dl
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+40h] [rbp-58h] BYREF

  Status = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0 )
  {
    v5 = *(_QWORD *)(v4 + 272);
    DestinationString = 0;
    if ( !v5 || !*(_BYTE *)(v5 + 24) )
    {
      Status = -1073741811;
      goto LABEL_32;
    }
    RtlInitUnicodeString(&DestinationString, L"\\Device\\BTHMS_RFCOMM");
    if ( !KeGetCurrentIrql() )
    {
      if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(*(_QWORD *)(v4 + 272) + 32LL), 1u) )
      {
        memset(&Event, 0, sizeof(Event));
        v6 = 0;
        ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v4);
        v8 = ConnectionReferenceFromEndpoint;
        if ( ConnectionReferenceFromEndpoint )
        {
          v9 = *(struct _DEVICE_OBJECT **)(ConnectionReferenceFromEndpoint + 24);
          v10 = *(struct _FILE_OBJECT **)(ConnectionReferenceFromEndpoint + 16);
        }
        else
        {
          v9 = *(struct _DEVICE_OBJECT **)(v4 + 40);
          v10 = *(struct _FILE_OBJECT **)(v4 + 24);
        }
        if ( *(_WORD *)v4 != 0xAFD1
          && *(_WORD *)v4 != 6909
          && ((*(_BYTE *)(v4 + 5) & 0x10) == 0 || (*(_BYTE *)(v4 + 6) & 1) == 0)
          && (*(_DWORD *)(v4 + 8) & 1) == 0
          && *(_BYTE *)(v4 + 2) != 4 )
        {
          if ( !(unsigned __int8)AfdPreventUnbind(v4) )
          {
            Status = -1073741436;
            goto LABEL_32;
          }
          v6 = 1;
        }
        if ( !v9 || (v11 = *(_BYTE *)(v4 + 2), v11 == 1) || v11 == 6 )
        {
          Status = -1073741811;
        }
        else
        {
          KeInitializeEvent(&Event, NotificationEvent, 0);
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdTdiSocketTransferComplete;
          CurrentStackLocation[-1].Context = &Event;
          CurrentStackLocation[-1].Control = -32;
          v13 = Irp->Tail.Overlay.CurrentStackLocation;
          *(_WORD *)&v13[-1].MajorFunction = 20751;
          v13[-1].DeviceObject = v9;
          v13[-1].FileObject = v10;
          _InterlockedIncrement((volatile signed __int32 *)(v4 + 248));
          Status = IofCallDriver(v9, Irp);
          if ( Status == 259 )
          {
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
            Status = Irp->IoStatus.Status;
          }
          if ( v8 )
          {
            v14 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v8 + 48), 0xFFFFFFFFFFFFFFFFuLL);
            v15 = v14 <= 1;
            v16 = v14 - 1;
            if ( v15 )
            {
              if ( v16 )
                __fastfail(0xEu);
              AfdCloseConnection(v8);
            }
          }
        }
        if ( v6 )
          AfdReallowUnbind(v4);
      }
    }
  }
LABEL_32:
  v17 = AfdPriorityBoost;
  Irp->IoStatus.Information = Status;
  IofCompleteRequest(Irp, v17);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140048930  push    rbx
0x140048932  push    rbp
0x140048933  push    rsi
0x140048934  push    rdi
0x140048935  push    r14
0x140048937  push    r15
0x140048939  sub     rsp, 68h
0x14004893d  mov     rax, [rdx+30h]
0x140048941  xor     edi, edi
0x140048943  mov     rbp, rcx
0x140048946  mov     rbx, [rax+18h]
0x14004894a  mov     eax, [rbx+8]
0x14004894d  bt      eax, 8
0x140048951  jb      loc_140048B3D
0x140048957  mov     rax, [rbx+110h]
0x14004895e  xorps   xmm0, xmm0
0x140048961  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140048966  test    rax, rax
0x140048969  jz      loc_140048B38
0x14004896f  mov     al, [rax+18h]
0x140048972  test    al, al
0x140048974  jz      loc_140048B38
0x14004897a  lea     rdx, aDeviceBthmsRfc; "\\Device\\BTHMS_RFCOMM"
0x140048981  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140048986  call    cs:__imp_RtlInitUnicodeString
0x14004898d  nop     dword ptr [rax+rax+00h]
0x140048992  call    cs:__imp_KeGetCurrentIrql
0x140048999  nop     dword ptr [rax+rax+00h]
0x14004899e  test    al, al
0x1400489a0  jnz     loc_140048B3D
0x1400489a6  mov     rdx, [rbx+110h]
0x1400489ad  lea     rcx, [rsp+98h+DestinationString]; String1
0x1400489b2  add     rdx, 20h ; ' '; String2
0x1400489b6  mov     r8b, 1; CaseInSensitive
0x1400489b9  call    cs:__imp_RtlEqualUnicodeString
0x1400489c0  nop     dword ptr [rax+rax+00h]
0x1400489c5  test    al, al
0x1400489c7  jz      loc_140048B3D
0x1400489cd  xorps   xmm0, xmm0
0x1400489d0  xor     eax, eax
0x1400489d2  mov     rcx, rbx
0x1400489d5  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x1400489da  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x1400489df  xor     r14b, r14b
0x1400489e2  call    AfdGetConnectionReferenceFromEndpoint
0x1400489e7  mov     rsi, rax
0x1400489ea  test    rax, rax
0x1400489ed  jz      short loc_1400489F9
0x1400489ef  mov     rdi, [rax+18h]
0x1400489f3  mov     r15, [rax+10h]
0x1400489f7  jmp     short loc_140048A01
0x1400489f9  mov     rdi, [rbx+28h]
0x1400489fd  mov     r15, [rbx+18h]
0x140048a01  movzx   eax, word ptr [rbx]
0x140048a04  mov     ecx, 0AFD1h
0x140048a09  cmp     ax, cx
0x140048a0c  jz      short loc_140048A4A
0x140048a0e  mov     ecx, 1AFDh
0x140048a13  cmp     ax, cx
0x140048a16  jz      short loc_140048A4A
0x140048a18  test    byte ptr [rbx+5], 10h
0x140048a1c  jz      short loc_140048A24
0x140048a1e  test    byte ptr [rbx+6], 1
0x140048a22  jnz     short loc_140048A4A
0x140048a24  mov     eax, [rbx+8]
0x140048a27  test    al, 1
0x140048a29  jnz     short loc_140048A4A
0x140048a2b  cmp     byte ptr [rbx+2], 4
0x140048a2f  jz      short loc_140048A4A
0x140048a31  mov     rcx, rbx
0x140048a34  call    AfdPreventUnbind
0x140048a39  test    al, al
0x140048a3b  jnz     short loc_140048A47
0x140048a3d  mov     edi, 0C0000184h
0x140048a42  jmp     loc_140048B3D
0x140048a47  mov     r14b, 1
0x140048a4a  test    rdi, rdi
0x140048a4d  jz      loc_140048B24
0x140048a53  mov     al, [rbx+2]
0x140048a56  cmp     al, 1
0x140048a58  jz      loc_140048B24
0x140048a5e  cmp     al, 6
0x140048a60  jz      loc_140048B24
0x140048a66  xor     r8d, r8d; State
0x140048a69  lea     rcx, [rsp+98h+Event]; Event
0x140048a6e  xor     edx, edx; Type
0x140048a70  call    cs:__imp_KeInitializeEvent
0x140048a77  nop     dword ptr [rax+rax+00h]
0x140048a7c  mov     rax, [rbp+0B8h]
0x140048a83  lea     rcx, AfdTdiSocketTransferComplete
0x140048a8a  mov     [rax-10h], rcx
0x140048a8e  lea     rcx, [rsp+98h+Event]
0x140048a93  mov     [rax-8], rcx
0x140048a97  mov     byte ptr [rax-45h], 0E0h
0x140048a9b  mov     rax, [rbp+0B8h]
0x140048aa2  mov     word ptr [rax-48h], 510Fh
0x140048aa8  mov     [rax-20h], rdi
0x140048aac  mov     [rax-18h], r15
0x140048ab0  lock inc dword ptr [rbx+0F8h]
0x140048ab7  mov     rdx, rbp; Irp
0x140048aba  mov     rcx, rdi; DeviceObject
0x140048abd  call    cs:__imp_IofCallDriver
0x140048ac4  nop     dword ptr [rax+rax+00h]
0x140048ac9  mov     edi, eax
0x140048acb  cmp     eax, 103h
0x140048ad0  jnz     short loc_140048AF7
0x140048ad2  xor     r9d, r9d; Alertable
0x140048ad5  mov     [rsp+98h+Timeout], 0; Timeout
0x140048ade  xor     r8d, r8d; WaitMode
0x140048ae1  lea     rcx, [rsp+98h+Event]; Object
0x140048ae6  xor     edx, edx; WaitReason
0x140048ae8  call    cs:__imp_KeWaitForSingleObject
0x140048aef  nop     dword ptr [rax+rax+00h]
0x140048af4  mov     edi, [rbp+30h]
0x140048af7  test    rsi, rsi
0x140048afa  jz      short loc_140048B29
0x140048afc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140048b00  lock xadd [rsi+30h], rax
0x140048b06  sub     rax, 1
0x140048b0a  jg      short loc_140048B29
0x140048b0c  test    rax, rax
0x140048b0f  jz      short loc_140048B1A
0x140048b11  mov     ecx, 0Eh
0x140048b16  int     29h; Win8: RtlFailFast(ecx)
0x140048b18  jmp     short loc_140048B29
0x140048b1a  mov     rcx, rsi
0x140048b1d  call    AfdCloseConnection
0x140048b22  jmp     short loc_140048B29
0x140048b24  mov     edi, 0C000000Dh
0x140048b29  test    r14b, r14b
0x140048b2c  jz      short loc_140048B3D
0x140048b2e  mov     rcx, rbx
0x140048b31  call    AfdReallowUnbind
0x140048b36  jmp     short loc_140048B3D
0x140048b38  mov     edi, 0C000000Dh
0x140048b3d  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140048b43  mov     rcx, rbp; Irp
0x140048b46  movsxd  rax, edi
0x140048b49  mov     [rbp+38h], rax
0x140048b4d  call    cs:__imp_IofCompleteRequest
0x140048b54  nop     dword ptr [rax+rax+00h]
0x140048b59  mov     eax, edi
0x140048b5b  add     rsp, 68h
0x140048b5f  pop     r15
0x140048b61  pop     r14
0x140048b63  pop     rdi
0x140048b64  pop     rsi
0x140048b65  pop     rbp
0x140048b66  pop     rbx
0x140048b67  retn
```
