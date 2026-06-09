# McGenEventWrite_EventWriteTransfer

- ea: `0x180004d70`
- end: `0x180004dbd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fc0`
- `0x180005758`
- `0x180006904`
- `0x180007380`
- `0x18000bd60`
- `0x18000bdec`
- `0x18000beac`
- `0x18000d060`
- `0x18000d9f4`
- `0x18000dabc`
- `0x180011878`

## callees

- `0x180004d70`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180004db2`
- `ADVAPI32!EventWriteTransfer` at `0x180004db2`

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
0x180004d70  sub     rsp, 38h
0x180004d74  mov     r8, [rcx+8]
0x180004d78  mov     rax, [rsp+38h+arg_20]
0x180004d7d  test    r8, r8
0x180004d80  jnz     short loc_180004D8A
0x180004d82  mov     [rax], r8
0x180004d85  xor     r10d, r10d
0x180004d88  jmp     short loc_180004D97
0x180004d8a  mov     [rax], r8
0x180004d8d  mov     r10d, 2
0x180004d93  movzx   r8d, word ptr [r8]
0x180004d97  mov     [rax+8], r8d
0x180004d9b  xor     r8d, r8d; ActivityId
0x180004d9e  mov     [rsp+38h+UserData], rax; UserData
0x180004da3  mov     [rax+0Ch], r10d
0x180004da7  mov     rcx, [rcx]; RegHandle
0x180004daa  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180004daf  xor     r9d, r9d; RelatedActivityId
0x180004db2  call    cs:__imp_EventWriteTransfer
0x180004db8  add     rsp, 38h
0x180004dbc  retn
```
