# McGenEventWrite_EventWriteTransfer

- ea: `0x1800083e0`
- end: `0x18000842d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033b0`
- `0x180008360`
- `0x18000f120`

## callees

- `0x1800083e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008422`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008422`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800083e0  sub     rsp, 38h
0x1800083e4  mov     r8, [rcx+8]
0x1800083e8  mov     rax, [rsp+38h+arg_20]
0x1800083ed  test    r8, r8
0x1800083f0  jnz     short loc_1800083FA
0x1800083f2  mov     [rax], r8
0x1800083f5  xor     r10d, r10d
0x1800083f8  jmp     short loc_180008407
0x1800083fa  mov     [rax], r8
0x1800083fd  mov     r10d, 2
0x180008403  movzx   r8d, word ptr [r8]
0x180008407  mov     [rax+8], r8d
0x18000840b  xor     r8d, r8d; ActivityId
0x18000840e  mov     [rsp+38h+UserData], rax; UserData
0x180008413  mov     [rax+0Ch], r10d
0x180008417  mov     rcx, [rcx]; RegHandle
0x18000841a  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000841f  xor     r9d, r9d; RelatedActivityId
0x180008422  call    cs:__imp_EventWriteTransfer
0x180008428  add     rsp, 38h
0x18000842c  retn
```
