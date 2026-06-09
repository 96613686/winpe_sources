# AfdSocketTransferEnd

- ea: `0x140048b70`
- end: `0x140048da9`
- name: `AfdSocketTransferEnd`
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
- `0x140048b70`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140048cb0`
- `ntoskrnl!KeInitializeEvent` at `0x140048cb0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048d28`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048d28`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048bd2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048bd2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140048bf9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140048bf9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048bc6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048bc6`
- `ntoskrnl!IofCompleteRequest` at `0x140048d8d`
- `ntoskrnl!IofCompleteRequest` at `0x140048d8d`
- `ntoskrnl!IofCallDriver` at `0x140048cfd`
- `ntoskrnl!IofCallDriver` at `0x140048cfd`

## string_xrefs

- `0x140048bba`: `\Device\BTHMS_RFCOMM`

## pseudocode

```c
__int64 __fastcall AfdSocketTransferEnd(PIRP Irp, __int64 a2)
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
          *(_WORD *)&v13[-1].MajorFunction = 21007;
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
0x140048b70  push    rbx
0x140048b72  push    rbp
0x140048b73  push    rsi
0x140048b74  push    rdi
0x140048b75  push    r14
0x140048b77  push    r15
0x140048b79  sub     rsp, 68h
0x140048b7d  mov     rax, [rdx+30h]
0x140048b81  xor     edi, edi
0x140048b83  mov     rbp, rcx
0x140048b86  mov     rbx, [rax+18h]
0x140048b8a  mov     eax, [rbx+8]
0x140048b8d  bt      eax, 8
0x140048b91  jb      loc_140048D7D
0x140048b97  mov     rax, [rbx+110h]
0x140048b9e  xorps   xmm0, xmm0
0x140048ba1  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140048ba6  test    rax, rax
0x140048ba9  jz      loc_140048D78
0x140048baf  mov     al, [rax+18h]
0x140048bb2  test    al, al
0x140048bb4  jz      loc_140048D78
0x140048bba  lea     rdx, aDeviceBthmsRfc; "\\Device\\BTHMS_RFCOMM"
0x140048bc1  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140048bc6  call    cs:__imp_RtlInitUnicodeString
0x140048bcd  nop     dword ptr [rax+rax+00h]
0x140048bd2  call    cs:__imp_KeGetCurrentIrql
0x140048bd9  nop     dword ptr [rax+rax+00h]
0x140048bde  test    al, al
0x140048be0  jnz     loc_140048D7D
0x140048be6  mov     rdx, [rbx+110h]
0x140048bed  lea     rcx, [rsp+98h+DestinationString]; String1
0x140048bf2  add     rdx, 20h ; ' '; String2
0x140048bf6  mov     r8b, 1; CaseInSensitive
0x140048bf9  call    cs:__imp_RtlEqualUnicodeString
0x140048c00  nop     dword ptr [rax+rax+00h]
0x140048c05  test    al, al
0x140048c07  jz      loc_140048D7D
0x140048c0d  xorps   xmm0, xmm0
0x140048c10  xor     eax, eax
0x140048c12  mov     rcx, rbx
0x140048c15  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x140048c1a  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x140048c1f  xor     r14b, r14b
0x140048c22  call    AfdGetConnectionReferenceFromEndpoint
0x140048c27  mov     rsi, rax
0x140048c2a  test    rax, rax
0x140048c2d  jz      short loc_140048C39
0x140048c2f  mov     rdi, [rax+18h]
0x140048c33  mov     r15, [rax+10h]
0x140048c37  jmp     short loc_140048C41
0x140048c39  mov     rdi, [rbx+28h]
0x140048c3d  mov     r15, [rbx+18h]
0x140048c41  movzx   eax, word ptr [rbx]
0x140048c44  mov     ecx, 0AFD1h
0x140048c49  cmp     ax, cx
0x140048c4c  jz      short loc_140048C8A
0x140048c4e  mov     ecx, 1AFDh
0x140048c53  cmp     ax, cx
0x140048c56  jz      short loc_140048C8A
0x140048c58  test    byte ptr [rbx+5], 10h
0x140048c5c  jz      short loc_140048C64
0x140048c5e  test    byte ptr [rbx+6], 1
0x140048c62  jnz     short loc_140048C8A
0x140048c64  mov     eax, [rbx+8]
0x140048c67  test    al, 1
0x140048c69  jnz     short loc_140048C8A
0x140048c6b  cmp     byte ptr [rbx+2], 4
0x140048c6f  jz      short loc_140048C8A
0x140048c71  mov     rcx, rbx
0x140048c74  call    AfdPreventUnbind
0x140048c79  test    al, al
0x140048c7b  jnz     short loc_140048C87
0x140048c7d  mov     edi, 0C0000184h
0x140048c82  jmp     loc_140048D7D
0x140048c87  mov     r14b, 1
0x140048c8a  test    rdi, rdi
0x140048c8d  jz      loc_140048D64
0x140048c93  mov     al, [rbx+2]
0x140048c96  cmp     al, 1
0x140048c98  jz      loc_140048D64
0x140048c9e  cmp     al, 6
0x140048ca0  jz      loc_140048D64
0x140048ca6  xor     r8d, r8d; State
0x140048ca9  lea     rcx, [rsp+98h+Event]; Event
0x140048cae  xor     edx, edx; Type
0x140048cb0  call    cs:__imp_KeInitializeEvent
0x140048cb7  nop     dword ptr [rax+rax+00h]
0x140048cbc  mov     rax, [rbp+0B8h]
0x140048cc3  lea     rcx, AfdTdiSocketTransferComplete
0x140048cca  mov     [rax-10h], rcx
0x140048cce  lea     rcx, [rsp+98h+Event]
0x140048cd3  mov     [rax-8], rcx
0x140048cd7  mov     byte ptr [rax-45h], 0E0h
0x140048cdb  mov     rax, [rbp+0B8h]
0x140048ce2  mov     word ptr [rax-48h], 520Fh
0x140048ce8  mov     [rax-20h], rdi
0x140048cec  mov     [rax-18h], r15
0x140048cf0  lock inc dword ptr [rbx+0F8h]
0x140048cf7  mov     rdx, rbp; Irp
0x140048cfa  mov     rcx, rdi; DeviceObject
0x140048cfd  call    cs:__imp_IofCallDriver
0x140048d04  nop     dword ptr [rax+rax+00h]
0x140048d09  mov     edi, eax
0x140048d0b  cmp     eax, 103h
0x140048d10  jnz     short loc_140048D37
0x140048d12  xor     r9d, r9d; Alertable
0x140048d15  mov     [rsp+98h+Timeout], 0; Timeout
0x140048d1e  xor     r8d, r8d; WaitMode
0x140048d21  lea     rcx, [rsp+98h+Event]; Object
0x140048d26  xor     edx, edx; WaitReason
0x140048d28  call    cs:__imp_KeWaitForSingleObject
0x140048d2f  nop     dword ptr [rax+rax+00h]
0x140048d34  mov     edi, [rbp+30h]
0x140048d37  test    rsi, rsi
0x140048d3a  jz      short loc_140048D69
0x140048d3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140048d40  lock xadd [rsi+30h], rax
0x140048d46  sub     rax, 1
0x140048d4a  jg      short loc_140048D69
0x140048d4c  test    rax, rax
0x140048d4f  jz      short loc_140048D5A
0x140048d51  mov     ecx, 0Eh
0x140048d56  int     29h; Win8: RtlFailFast(ecx)
0x140048d58  jmp     short loc_140048D69
0x140048d5a  mov     rcx, rsi
0x140048d5d  call    AfdCloseConnection
0x140048d62  jmp     short loc_140048D69
0x140048d64  mov     edi, 0C000000Dh
0x140048d69  test    r14b, r14b
0x140048d6c  jz      short loc_140048D7D
0x140048d6e  mov     rcx, rbx
0x140048d71  call    AfdReallowUnbind
0x140048d76  jmp     short loc_140048D7D
0x140048d78  mov     edi, 0C000000Dh
0x140048d7d  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140048d83  mov     rcx, rbp; Irp
0x140048d86  movsxd  rax, edi
0x140048d89  mov     [rbp+38h], rax
0x140048d8d  call    cs:__imp_IofCompleteRequest
0x140048d94  nop     dword ptr [rax+rax+00h]
0x140048d99  mov     eax, edi
0x140048d9b  add     rsp, 68h
0x140048d9f  pop     r15
0x140048da1  pop     r14
0x140048da3  pop     rdi
0x140048da4  pop     rsi
0x140048da5  pop     rbp
0x140048da6  pop     rbx
0x140048da7  retn
```
