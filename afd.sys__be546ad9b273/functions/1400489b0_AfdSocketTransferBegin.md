# AfdSocketTransferBegin

- ea: `0x1400489b0`
- end: `0x140048bf2`
- name: `AfdSocketTransferBegin`
- size: `578`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14001c708`
- `0x14001e7e0`
- `0x140032798`
- `0x140033bfc`
- `0x1400489b0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140048af9`
- `ntoskrnl!KeInitializeEvent` at `0x140048af9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048b71`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048b71`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048a12`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048a12`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140048a39`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140048a39`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048a06`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048a06`
- `ntoskrnl!IofCompleteRequest` at `0x140048bd6`
- `ntoskrnl!IofCompleteRequest` at `0x140048bd6`
- `ntoskrnl!IofCallDriver` at `0x140048b46`
- `ntoskrnl!IofCallDriver` at `0x140048b46`

## string_xrefs

- `0x1400489fa`: `\Device\BTHMS_RFCOMM`

## pseudocode

```c
__int64 __fastcall AfdSocketTransferBegin(PIRP Irp, __int64 a2)
{
  NTSTATUS Status; // edi
  __int64 v4; // rbx
  __int64 v5; // rax
  char v6; // r15
  __int64 ConnectionReferenceFromEndpoint; // rsi
  struct _DEVICE_OBJECT *v8; // rdi
  struct _FILE_OBJECT *v9; // r14
  char v10; // al
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v12; // rax
  signed __int64 v13; // rax
  bool v14; // cc
  signed __int64 v15; // rax
  CCHAR v16; // dl
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
      goto LABEL_33;
    }
    RtlInitUnicodeString(&DestinationString, L"\\Device\\BTHMS_RFCOMM");
    if ( !KeGetCurrentIrql() )
    {
      if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(*(_QWORD *)(v4 + 272) + 32LL), 1u) )
      {
        v6 = 0;
        memset(&Event, 0, sizeof(Event));
        ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v4);
        if ( *(_WORD *)v4 != 0xAFD1
          && *(_WORD *)v4 != 6909
          && ((*(_BYTE *)(v4 + 5) & 0x10) == 0 || (*(_BYTE *)(v4 + 6) & 1) == 0)
          && (*(_DWORD *)(v4 + 8) & 1) == 0
          && *(_BYTE *)(v4 + 2) != 4 )
        {
          if ( !(unsigned __int8)AfdPreventUnbind(v4) )
          {
            Status = -1073741436;
LABEL_25:
            if ( ConnectionReferenceFromEndpoint )
            {
              v13 = _InterlockedExchangeAdd64(
                      (volatile signed __int64 *)(ConnectionReferenceFromEndpoint + 48),
                      0xFFFFFFFFFFFFFFFFuLL);
              v14 = v13 <= 1;
              v15 = v13 - 1;
              if ( v14 )
              {
                if ( v15 )
                  __fastfail(0xEu);
                AfdCloseConnection(ConnectionReferenceFromEndpoint);
              }
            }
            if ( v6 )
              AfdReallowUnbind(v4);
            goto LABEL_33;
          }
          v6 = 1;
        }
        if ( ConnectionReferenceFromEndpoint )
        {
          v8 = *(struct _DEVICE_OBJECT **)(ConnectionReferenceFromEndpoint + 24);
          v9 = *(struct _FILE_OBJECT **)(ConnectionReferenceFromEndpoint + 16);
        }
        else
        {
          v8 = *(struct _DEVICE_OBJECT **)(v4 + 40);
          v9 = *(struct _FILE_OBJECT **)(v4 + 24);
        }
        if ( !v8 || !v9 || (v10 = *(_BYTE *)(v4 + 2), v10 == 1) || v10 == 6 )
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
          v12 = Irp->Tail.Overlay.CurrentStackLocation;
          *(_WORD *)&v12[-1].MajorFunction = 20751;
          v12[-1].DeviceObject = v8;
          v12[-1].FileObject = v9;
          _InterlockedIncrement((volatile signed __int32 *)(v4 + 248));
          Status = IofCallDriver(v8, Irp);
          if ( Status == 259 )
          {
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
            Status = Irp->IoStatus.Status;
          }
        }
        goto LABEL_25;
      }
    }
  }
LABEL_33:
  v16 = AfdPriorityBoost;
  Irp->IoStatus.Information = Status;
  IofCompleteRequest(Irp, v16);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400489b0  push    rbx
0x1400489b2  push    rbp
0x1400489b3  push    rsi
0x1400489b4  push    rdi
0x1400489b5  push    r14
0x1400489b7  push    r15
0x1400489b9  sub     rsp, 68h
0x1400489bd  mov     rax, [rdx+30h]
0x1400489c1  xor     edi, edi
0x1400489c3  mov     rbp, rcx
0x1400489c6  mov     rbx, [rax+18h]
0x1400489ca  mov     eax, [rbx+8]
0x1400489cd  bt      eax, 8
0x1400489d1  jb      loc_140048BC6
0x1400489d7  mov     rax, [rbx+110h]
0x1400489de  xorps   xmm0, xmm0
0x1400489e1  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1400489e6  test    rax, rax
0x1400489e9  jz      loc_140048BC1
0x1400489ef  mov     al, [rax+18h]
0x1400489f2  test    al, al
0x1400489f4  jz      loc_140048BC1
0x1400489fa  lea     rdx, aDeviceBthmsRfc; "\\Device\\BTHMS_RFCOMM"
0x140048a01  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140048a06  call    cs:__imp_RtlInitUnicodeString
0x140048a0d  nop     dword ptr [rax+rax+00h]
0x140048a12  call    cs:__imp_KeGetCurrentIrql
0x140048a19  nop     dword ptr [rax+rax+00h]
0x140048a1e  test    al, al
0x140048a20  jnz     loc_140048BC6
0x140048a26  mov     rdx, [rbx+110h]
0x140048a2d  lea     rcx, [rsp+98h+DestinationString]; String1
0x140048a32  add     rdx, 20h ; ' '; String2
0x140048a36  mov     r8b, 1; CaseInSensitive
0x140048a39  call    cs:__imp_RtlEqualUnicodeString
0x140048a40  nop     dword ptr [rax+rax+00h]
0x140048a45  test    al, al
0x140048a47  jz      loc_140048BC6
0x140048a4d  xorps   xmm0, xmm0
0x140048a50  xor     eax, eax
0x140048a52  xor     r15b, r15b
0x140048a55  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x140048a5a  mov     rcx, rbx
0x140048a5d  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x140048a62  call    AfdGetConnectionReferenceFromEndpoint
0x140048a67  mov     rsi, rax
0x140048a6a  movzx   eax, word ptr [rbx]
0x140048a6d  mov     ecx, 0AFD1h
0x140048a72  cmp     ax, cx
0x140048a75  jz      short loc_140048AB3
0x140048a77  mov     ecx, 1AFDh
0x140048a7c  cmp     ax, cx
0x140048a7f  jz      short loc_140048AB3
0x140048a81  test    byte ptr [rbx+5], 10h
0x140048a85  jz      short loc_140048A8D
0x140048a87  test    byte ptr [rbx+6], 1
0x140048a8b  jnz     short loc_140048AB3
0x140048a8d  mov     eax, [rbx+8]
0x140048a90  test    al, 1
0x140048a92  jnz     short loc_140048AB3
0x140048a94  cmp     byte ptr [rbx+2], 4
0x140048a98  jz      short loc_140048AB3
0x140048a9a  mov     rcx, rbx
0x140048a9d  call    AfdPreventUnbind
0x140048aa2  test    al, al
0x140048aa4  jnz     short loc_140048AB0
0x140048aa6  mov     edi, 0C0000184h
0x140048aab  jmp     loc_140048B87
0x140048ab0  mov     r15b, 1
0x140048ab3  test    rsi, rsi
0x140048ab6  jz      short loc_140048AC2
0x140048ab8  mov     rdi, [rsi+18h]
0x140048abc  mov     r14, [rsi+10h]
0x140048ac0  jmp     short loc_140048ACA
0x140048ac2  mov     rdi, [rbx+28h]
0x140048ac6  mov     r14, [rbx+18h]
0x140048aca  test    rdi, rdi
0x140048acd  jz      loc_140048B82
0x140048ad3  test    r14, r14
0x140048ad6  jz      loc_140048B82
0x140048adc  mov     al, [rbx+2]
0x140048adf  cmp     al, 1
0x140048ae1  jz      loc_140048B82
0x140048ae7  cmp     al, 6
0x140048ae9  jz      loc_140048B82
0x140048aef  xor     r8d, r8d; State
0x140048af2  lea     rcx, [rsp+98h+Event]; Event
0x140048af7  xor     edx, edx; Type
0x140048af9  call    cs:__imp_KeInitializeEvent
0x140048b00  nop     dword ptr [rax+rax+00h]
0x140048b05  mov     rax, [rbp+0B8h]
0x140048b0c  lea     rcx, AfdTdiSocketTransferComplete
0x140048b13  mov     [rax-10h], rcx
0x140048b17  lea     rcx, [rsp+98h+Event]
0x140048b1c  mov     [rax-8], rcx
0x140048b20  mov     byte ptr [rax-45h], 0E0h
0x140048b24  mov     rax, [rbp+0B8h]
0x140048b2b  mov     word ptr [rax-48h], 510Fh
0x140048b31  mov     [rax-20h], rdi
0x140048b35  mov     [rax-18h], r14
0x140048b39  lock inc dword ptr [rbx+0F8h]
0x140048b40  mov     rdx, rbp; Irp
0x140048b43  mov     rcx, rdi; DeviceObject
0x140048b46  call    cs:__imp_IofCallDriver
0x140048b4d  nop     dword ptr [rax+rax+00h]
0x140048b52  mov     edi, eax
0x140048b54  cmp     eax, 103h
0x140048b59  jnz     short loc_140048B87
0x140048b5b  xor     r9d, r9d; Alertable
0x140048b5e  mov     [rsp+98h+Timeout], 0; Timeout
0x140048b67  xor     r8d, r8d; WaitMode
0x140048b6a  lea     rcx, [rsp+98h+Event]; Object
0x140048b6f  xor     edx, edx; WaitReason
0x140048b71  call    cs:__imp_KeWaitForSingleObject
0x140048b78  nop     dword ptr [rax+rax+00h]
0x140048b7d  mov     edi, [rbp+30h]
0x140048b80  jmp     short loc_140048B87
0x140048b82  mov     edi, 0C000000Dh
0x140048b87  test    rsi, rsi
0x140048b8a  jz      short loc_140048BB2
0x140048b8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140048b90  lock xadd [rsi+30h], rax
0x140048b96  sub     rax, 1
0x140048b9a  jg      short loc_140048BB2
0x140048b9c  test    rax, rax
0x140048b9f  jz      short loc_140048BAA
0x140048ba1  mov     ecx, 0Eh
0x140048ba6  int     29h; Win8: RtlFailFast(ecx)
0x140048ba8  jmp     short loc_140048BB2
0x140048baa  mov     rcx, rsi
0x140048bad  call    AfdCloseConnection
0x140048bb2  test    r15b, r15b
0x140048bb5  jz      short loc_140048BC6
0x140048bb7  mov     rcx, rbx
0x140048bba  call    AfdReallowUnbind
0x140048bbf  jmp     short loc_140048BC6
0x140048bc1  mov     edi, 0C000000Dh
0x140048bc6  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140048bcc  mov     rcx, rbp; Irp
0x140048bcf  movsxd  rax, edi
0x140048bd2  mov     [rbp+38h], rax
0x140048bd6  call    cs:__imp_IofCompleteRequest
0x140048bdd  nop     dword ptr [rax+rax+00h]
0x140048be2  mov     eax, edi
0x140048be4  add     rsp, 68h
0x140048be8  pop     r15
0x140048bea  pop     r14
0x140048bec  pop     rdi
0x140048bed  pop     rsi
0x140048bee  pop     rbp
0x140048bef  pop     rbx
0x140048bf0  retn
```
