# AfdSocketTransferEnd

- ea: `0x140048c00`
- end: `0x140048e42`
- name: `AfdSocketTransferEnd`
- size: `578`
- prototype: `__int64 __fastcall(PIRP Irp)`
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
- `0x140048c00`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140048d49`
- `ntoskrnl!KeInitializeEvent` at `0x140048d49`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048dc1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140048dc1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048c62`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048c62`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140048c89`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140048c89`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048c56`
- `ntoskrnl!RtlInitUnicodeString` at `0x140048c56`
- `ntoskrnl!IofCompleteRequest` at `0x140048e26`
- `ntoskrnl!IofCompleteRequest` at `0x140048e26`
- `ntoskrnl!IofCallDriver` at `0x140048d96`
- `ntoskrnl!IofCallDriver` at `0x140048d96`

## string_xrefs

- `0x140048c4a`: `\Device\BTHMS_RFCOMM`

## pseudocode

```c
__int64 __fastcall AfdSocketTransferEnd(PIRP Irp, __int64 a2)
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
          *(_WORD *)&v12[-1].MajorFunction = 21007;
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
0x140048c00  push    rbx
0x140048c02  push    rbp
0x140048c03  push    rsi
0x140048c04  push    rdi
0x140048c05  push    r14
0x140048c07  push    r15
0x140048c09  sub     rsp, 68h
0x140048c0d  mov     rax, [rdx+30h]
0x140048c11  xor     edi, edi
0x140048c13  mov     rbp, rcx
0x140048c16  mov     rbx, [rax+18h]
0x140048c1a  mov     eax, [rbx+8]
0x140048c1d  bt      eax, 8
0x140048c21  jb      loc_140048E16
0x140048c27  mov     rax, [rbx+110h]
0x140048c2e  xorps   xmm0, xmm0
0x140048c31  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140048c36  test    rax, rax
0x140048c39  jz      loc_140048E11
0x140048c3f  mov     al, [rax+18h]
0x140048c42  test    al, al
0x140048c44  jz      loc_140048E11
0x140048c4a  lea     rdx, aDeviceBthmsRfc; "\\Device\\BTHMS_RFCOMM"
0x140048c51  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140048c56  call    cs:__imp_RtlInitUnicodeString
0x140048c5d  nop     dword ptr [rax+rax+00h]
0x140048c62  call    cs:__imp_KeGetCurrentIrql
0x140048c69  nop     dword ptr [rax+rax+00h]
0x140048c6e  test    al, al
0x140048c70  jnz     loc_140048E16
0x140048c76  mov     rdx, [rbx+110h]
0x140048c7d  lea     rcx, [rsp+98h+DestinationString]; String1
0x140048c82  add     rdx, 20h ; ' '; String2
0x140048c86  mov     r8b, 1; CaseInSensitive
0x140048c89  call    cs:__imp_RtlEqualUnicodeString
0x140048c90  nop     dword ptr [rax+rax+00h]
0x140048c95  test    al, al
0x140048c97  jz      loc_140048E16
0x140048c9d  xorps   xmm0, xmm0
0x140048ca0  xor     eax, eax
0x140048ca2  xor     r15b, r15b
0x140048ca5  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x140048caa  mov     rcx, rbx
0x140048cad  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x140048cb2  call    AfdGetConnectionReferenceFromEndpoint
0x140048cb7  mov     rsi, rax
0x140048cba  movzx   eax, word ptr [rbx]
0x140048cbd  mov     ecx, 0AFD1h
0x140048cc2  cmp     ax, cx
0x140048cc5  jz      short loc_140048D03
0x140048cc7  mov     ecx, 1AFDh
0x140048ccc  cmp     ax, cx
0x140048ccf  jz      short loc_140048D03
0x140048cd1  test    byte ptr [rbx+5], 10h
0x140048cd5  jz      short loc_140048CDD
0x140048cd7  test    byte ptr [rbx+6], 1
0x140048cdb  jnz     short loc_140048D03
0x140048cdd  mov     eax, [rbx+8]
0x140048ce0  test    al, 1
0x140048ce2  jnz     short loc_140048D03
0x140048ce4  cmp     byte ptr [rbx+2], 4
0x140048ce8  jz      short loc_140048D03
0x140048cea  mov     rcx, rbx
0x140048ced  call    AfdPreventUnbind
0x140048cf2  test    al, al
0x140048cf4  jnz     short loc_140048D00
0x140048cf6  mov     edi, 0C0000184h
0x140048cfb  jmp     loc_140048DD7
0x140048d00  mov     r15b, 1
0x140048d03  test    rsi, rsi
0x140048d06  jz      short loc_140048D12
0x140048d08  mov     rdi, [rsi+18h]
0x140048d0c  mov     r14, [rsi+10h]
0x140048d10  jmp     short loc_140048D1A
0x140048d12  mov     rdi, [rbx+28h]
0x140048d16  mov     r14, [rbx+18h]
0x140048d1a  test    rdi, rdi
0x140048d1d  jz      loc_140048DD2
0x140048d23  test    r14, r14
0x140048d26  jz      loc_140048DD2
0x140048d2c  mov     al, [rbx+2]
0x140048d2f  cmp     al, 1
0x140048d31  jz      loc_140048DD2
0x140048d37  cmp     al, 6
0x140048d39  jz      loc_140048DD2
0x140048d3f  xor     r8d, r8d; State
0x140048d42  lea     rcx, [rsp+98h+Event]; Event
0x140048d47  xor     edx, edx; Type
0x140048d49  call    cs:__imp_KeInitializeEvent
0x140048d50  nop     dword ptr [rax+rax+00h]
0x140048d55  mov     rax, [rbp+0B8h]
0x140048d5c  lea     rcx, AfdTdiSocketTransferComplete
0x140048d63  mov     [rax-10h], rcx
0x140048d67  lea     rcx, [rsp+98h+Event]
0x140048d6c  mov     [rax-8], rcx
0x140048d70  mov     byte ptr [rax-45h], 0E0h
0x140048d74  mov     rax, [rbp+0B8h]
0x140048d7b  mov     word ptr [rax-48h], 520Fh
0x140048d81  mov     [rax-20h], rdi
0x140048d85  mov     [rax-18h], r14
0x140048d89  lock inc dword ptr [rbx+0F8h]
0x140048d90  mov     rdx, rbp; Irp
0x140048d93  mov     rcx, rdi; DeviceObject
0x140048d96  call    cs:__imp_IofCallDriver
0x140048d9d  nop     dword ptr [rax+rax+00h]
0x140048da2  mov     edi, eax
0x140048da4  cmp     eax, 103h
0x140048da9  jnz     short loc_140048DD7
0x140048dab  xor     r9d, r9d; Alertable
0x140048dae  mov     [rsp+98h+Timeout], 0; Timeout
0x140048db7  xor     r8d, r8d; WaitMode
0x140048dba  lea     rcx, [rsp+98h+Event]; Object
0x140048dbf  xor     edx, edx; WaitReason
0x140048dc1  call    cs:__imp_KeWaitForSingleObject
0x140048dc8  nop     dword ptr [rax+rax+00h]
0x140048dcd  mov     edi, [rbp+30h]
0x140048dd0  jmp     short loc_140048DD7
0x140048dd2  mov     edi, 0C000000Dh
0x140048dd7  test    rsi, rsi
0x140048dda  jz      short loc_140048E02
0x140048ddc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140048de0  lock xadd [rsi+30h], rax
0x140048de6  sub     rax, 1
0x140048dea  jg      short loc_140048E02
0x140048dec  test    rax, rax
0x140048def  jz      short loc_140048DFA
0x140048df1  mov     ecx, 0Eh
0x140048df6  int     29h; Win8: RtlFailFast(ecx)
0x140048df8  jmp     short loc_140048E02
0x140048dfa  mov     rcx, rsi
0x140048dfd  call    AfdCloseConnection
0x140048e02  test    r15b, r15b
0x140048e05  jz      short loc_140048E16
0x140048e07  mov     rcx, rbx
0x140048e0a  call    AfdReallowUnbind
0x140048e0f  jmp     short loc_140048E16
0x140048e11  mov     edi, 0C000000Dh
0x140048e16  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140048e1c  mov     rcx, rbp; Irp
0x140048e1f  movsxd  rax, edi
0x140048e22  mov     [rbp+38h], rax
0x140048e26  call    cs:__imp_IofCompleteRequest
0x140048e2d  nop     dword ptr [rax+rax+00h]
0x140048e32  mov     eax, edi
0x140048e34  add     rsp, 68h
0x140048e38  pop     r15
0x140048e3a  pop     r14
0x140048e3c  pop     rdi
0x140048e3d  pop     rsi
0x140048e3e  pop     rbp
0x140048e3f  pop     rbx
0x140048e40  retn
```
