# McGenEventWrite_EventWriteTransfer

- ea: `0x140017708`
- end: `0x14001775a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140011b70`
- `0x1400127dc`
- `0x140015ff0`
- `0x14001a270`
- `0x14001b328`
- `0x1400243e8`
- `0x140025870`

## callees

- `0x140017708`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001774f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001774f`

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

  v5 = (unsigned __int16 *)qword_14004C0D8;
  if ( qword_14004C0D8 )
  {
    UserData->Ptr = qword_14004C0D8;
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
  return EventWriteTransfer(TIERENGINE_EVENT_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140017708  sub     rsp, 38h
0x14001770c  mov     rcx, cs:qword_14004C0D8
0x140017713  mov     rax, [rsp+38h+arg_20]
0x140017718  test    rcx, rcx
0x14001771b  jnz     short loc_140017725
0x14001771d  mov     [rax], rcx
0x140017720  xor     r8d, r8d
0x140017723  jmp     short loc_140017731
0x140017725  mov     [rax], rcx
0x140017728  mov     r8d, 2
0x14001772e  movzx   ecx, word ptr [rcx]
0x140017731  mov     [rax+8], ecx
0x140017734  mov     [rax+0Ch], r8d
0x140017738  xor     r8d, r8d; ActivityId
0x14001773b  mov     rcx, cs:TIERENGINE_EVENT_PROVIDER_Context; RegHandle
0x140017742  mov     [rsp+38h+UserData], rax; UserData
0x140017747  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14001774c  xor     r9d, r9d; RelatedActivityId
0x14001774f  call    cs:__imp_EventWriteTransfer
0x140017755  add     rsp, 38h
0x140017759  retn
```
