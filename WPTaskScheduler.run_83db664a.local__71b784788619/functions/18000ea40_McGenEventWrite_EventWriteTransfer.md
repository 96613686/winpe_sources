# McGenEventWrite_EventWriteTransfer

- ea: `0x18000ea40`
- end: `0x18000ea92`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `69`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002150`
- `0x1800025b0`
- `0x180003fa0`
- `0x180005440`
- `0x180005e40`
- `0x180006380`
- `0x180006410`
- `0x1800068b0`
- `0x180006db0`
- `0x180007410`
- `0x1800074e0`
- `0x180009740`
- `0x18000a160`
- `0x18000c770`
- `0x18000d840`
- `0x18000e970`
- `0x18000e9c8`
- `0x18000f634`
- `0x180015544`
- `0x180015b08`
- `0x180017370`
- `0x1800173c0`
- `0x1800175f0`
- `0x180017680`
- `0x180017710`
- `0x180017a74`
- `0x180018208`
- `0x180018314`
- `0x180018498`
- `0x180018560`
- `0x1800187f0`
- `0x1800188cc`
- `0x180018a04`
- `0x180018dac`
- `0x18001910c`
- `0x18001939c`
- `0x180019544`
- `0x180019610`
- `0x1800196e0`
- `0x1800197f8`
- `0x18001996c`
- `0x1800199c4`
- `0x180019a34`
- `0x180019a9c`
- `0x180019b28`
- `0x180019bc4`
- `0x180019c80`
- `0x180019cec`
- `0x18001aba0`
- `0x18001af50`

## callees

- `0x18000ea40`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ea87`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ea87`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180030018;
  if ( qword_180030018 )
  {
    UserData->Ptr = qword_180030018;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(MICROSOFT_WINDOWSPHONE_TASKSCHEDULER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000ea40  sub     rsp, 38h
0x18000ea44  mov     rcx, cs:qword_180030018
0x18000ea4b  mov     rax, [rsp+38h+arg_20]
0x18000ea50  test    rcx, rcx
0x18000ea53  jnz     short loc_18000EA5D
0x18000ea55  mov     [rax], rcx
0x18000ea58  xor     r8d, r8d
0x18000ea5b  jmp     short loc_18000EA69
0x18000ea5d  mov     [rax], rcx
0x18000ea60  mov     r8d, 2
0x18000ea66  movzx   ecx, word ptr [rcx]
0x18000ea69  mov     [rax+8], ecx
0x18000ea6c  mov     [rax+0Ch], r8d
0x18000ea70  xor     r8d, r8d; ActivityId
0x18000ea73  mov     rcx, cs:MICROSOFT_WINDOWSPHONE_TASKSCHEDULER_Context; RegHandle
0x18000ea7a  mov     [rsp+38h+UserData], rax; UserData
0x18000ea7f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000ea84  xor     r9d, r9d; RelatedActivityId
0x18000ea87  call    cs:__imp_EventWriteTransfer
0x18000ea8d  add     rsp, 38h
0x18000ea91  retn
```
