# McGenEventWrite_EventWriteTransfer

- ea: `0x180029710`
- end: `0x180029762`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027c84`
- `0x180028018`
- `0x180028340`
- `0x1800289d0`
- `0x180028d3c`
- `0x180029768`

## callees

- `0x180029710`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029757`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029757`

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

  v5 = (unsigned __int16 *)qword_180048F28;
  if ( qword_180048F28 )
  {
    UserData->Ptr = qword_180048F28;
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
  return EventWriteTransfer(Microsoft_Windows_XPerfCore_ETWProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180029710  sub     rsp, 38h
0x180029714  mov     rcx, cs:qword_180048F28
0x18002971b  mov     rax, [rsp+38h+arg_20]
0x180029720  test    rcx, rcx
0x180029723  jnz     short loc_18002972D
0x180029725  mov     [rax], rcx
0x180029728  xor     r8d, r8d
0x18002972b  jmp     short loc_180029739
0x18002972d  mov     [rax], rcx
0x180029730  mov     r8d, 2
0x180029736  movzx   ecx, word ptr [rcx]
0x180029739  mov     [rax+8], ecx
0x18002973c  mov     [rax+0Ch], r8d
0x180029740  xor     r8d, r8d; ActivityId
0x180029743  mov     rcx, cs:Microsoft_Windows_XPerfCore_ETWProvider_Context; RegHandle
0x18002974a  mov     [rsp+38h+UserData], rax; UserData
0x18002974f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180029754  xor     r9d, r9d; RelatedActivityId
0x180029757  call    cs:__imp_EventWriteTransfer
0x18002975d  add     rsp, 38h
0x180029761  retn
```
