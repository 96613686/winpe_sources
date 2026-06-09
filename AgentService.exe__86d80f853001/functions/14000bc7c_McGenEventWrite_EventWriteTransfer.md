# McGenEventWrite_EventWriteTransfer

- ea: `0x14000bc7c`
- end: `0x14000bcc9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b0a0`
- `0x14000b2e0`
- `0x14000b8cc`
- `0x14000bcd0`
- `0x14000bd18`
- `0x14000c078`
- `0x14000c124`
- `0x14000d950`
- `0x140015224`
- `0x140019190`
- `0x1400380d4`
- `0x14003b0a0`
- `0x140045ea8`
- `0x140048198`
- `0x14008a6fc`
- `0x14008d008`
- `0x14008d0c8`
- `0x14008db8c`
- `0x140098751`

## callees

- `0x14000bc7c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x14000bcbe`
- `ADVAPI32!EventWriteTransfer` at `0x14000bcbe`

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
0x14000bc7c  sub     rsp, 38h
0x14000bc80  mov     r8, [rcx+8]
0x14000bc84  mov     rax, [rsp+38h+arg_20]
0x14000bc89  test    r8, r8
0x14000bc8c  jnz     short loc_14000BC96
0x14000bc8e  mov     [rax], r8
0x14000bc91  xor     r10d, r10d
0x14000bc94  jmp     short loc_14000BCA3
0x14000bc96  mov     [rax], r8
0x14000bc99  mov     r10d, 2
0x14000bc9f  movzx   r8d, word ptr [r8]
0x14000bca3  mov     [rax+8], r8d
0x14000bca7  xor     r8d, r8d; ActivityId
0x14000bcaa  mov     [rsp+38h+UserData], rax; UserData
0x14000bcaf  mov     [rax+0Ch], r10d
0x14000bcb3  mov     rcx, [rcx]; RegHandle
0x14000bcb6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000bcbb  xor     r9d, r9d; RelatedActivityId
0x14000bcbe  call    cs:__imp_EventWriteTransfer
0x14000bcc4  add     rsp, 38h
0x14000bcc8  retn
```
