# McGenEventWrite_EventWriteTransfer

- ea: `0x18002bba0`
- end: `0x18002bbed`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18002bbf4`
- `0x18003111c`
- `0x180037100`
- `0x18004f52c`
- `0x180055914`

## callees

- `0x18002bba0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bbe2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bbe2`

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
0x18002bba0  sub     rsp, 38h
0x18002bba4  mov     r8, [rcx+8]
0x18002bba8  mov     rax, [rsp+38h+arg_20]
0x18002bbad  test    r8, r8
0x18002bbb0  jnz     short loc_18002BBBA
0x18002bbb2  mov     [rax], r8
0x18002bbb5  xor     r10d, r10d
0x18002bbb8  jmp     short loc_18002BBC7
0x18002bbba  mov     [rax], r8
0x18002bbbd  mov     r10d, 2
0x18002bbc3  movzx   r8d, word ptr [r8]
0x18002bbc7  mov     [rax+8], r8d
0x18002bbcb  xor     r8d, r8d; ActivityId
0x18002bbce  mov     [rsp+38h+UserData], rax; UserData
0x18002bbd3  mov     [rax+0Ch], r10d
0x18002bbd7  mov     rcx, [rcx]; RegHandle
0x18002bbda  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18002bbdf  xor     r9d, r9d; RelatedActivityId
0x18002bbe2  call    cs:__imp_EventWriteTransfer
0x18002bbe8  add     rsp, 38h
0x18002bbec  retn
```
