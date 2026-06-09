# McGenEventWrite_EventWriteTransfer

- ea: `0x140009340`
- end: `0x140009392`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400045f0`
- `0x140009398`
- `0x140009918`
- `0x14000ad18`

## callees

- `0x140009340`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140009387`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140009387`

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

  v5 = (unsigned __int16 *)qword_140017008;
  if ( qword_140017008 )
  {
    UserData->Ptr = qword_140017008;
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
  return EventWriteTransfer(PROVISIONING_DIAGNOSTICS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140009340  sub     rsp, 38h
0x140009344  mov     rcx, cs:qword_140017008
0x14000934b  mov     rax, [rsp+38h+arg_20]
0x140009350  test    rcx, rcx
0x140009353  jnz     short loc_14000935D
0x140009355  mov     [rax], rcx
0x140009358  xor     r8d, r8d
0x14000935b  jmp     short loc_140009369
0x14000935d  mov     [rax], rcx
0x140009360  mov     r8d, 2
0x140009366  movzx   ecx, word ptr [rcx]
0x140009369  mov     [rax+8], ecx
0x14000936c  mov     [rax+0Ch], r8d
0x140009370  xor     r8d, r8d; ActivityId
0x140009373  mov     rcx, cs:PROVISIONING_DIAGNOSTICS_Context; RegHandle
0x14000937a  mov     [rsp+38h+UserData], rax; UserData
0x14000937f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140009384  xor     r9d, r9d; RelatedActivityId
0x140009387  call    cs:__imp_EventWriteTransfer
0x14000938d  add     rsp, 38h
0x140009391  retn
```
