# McGenEventWrite_EventWriteTransfer

- ea: `0x18000d96c`
- end: `0x18000d9be`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d9c4`
- `0x180019464`
- `0x180019540`
- `0x1800195e0`

## callees

- `0x18000d96c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d9b3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d9b3`

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

  v5 = (unsigned __int16 *)qword_180039058;
  if ( qword_180039058 )
  {
    UserData->Ptr = qword_180039058;
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
  return EventWriteTransfer(Microsoft_Windows_DeviceGuard_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000d96c  sub     rsp, 38h
0x18000d970  mov     rcx, cs:qword_180039058
0x18000d977  mov     rax, [rsp+38h+arg_20]
0x18000d97c  test    rcx, rcx
0x18000d97f  jnz     short loc_18000D989
0x18000d981  mov     [rax], rcx
0x18000d984  xor     r8d, r8d
0x18000d987  jmp     short loc_18000D995
0x18000d989  mov     [rax], rcx
0x18000d98c  mov     r8d, 2
0x18000d992  movzx   ecx, word ptr [rcx]
0x18000d995  mov     [rax+8], ecx
0x18000d998  mov     [rax+0Ch], r8d
0x18000d99c  xor     r8d, r8d; ActivityId
0x18000d99f  mov     rcx, cs:Microsoft_Windows_DeviceGuard_Context; RegHandle
0x18000d9a6  mov     [rsp+38h+UserData], rax; UserData
0x18000d9ab  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000d9b0  xor     r9d, r9d; RelatedActivityId
0x18000d9b3  call    cs:__imp_EventWriteTransfer
0x18000d9b9  add     rsp, 38h
0x18000d9bd  retn
```
