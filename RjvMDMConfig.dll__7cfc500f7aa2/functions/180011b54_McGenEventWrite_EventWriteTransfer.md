# McGenEventWrite_EventWriteTransfer

- ea: `0x180011b54`
- end: `0x180011ba8`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb90`
- `0x180011bb0`
- `0x180011c10`
- `0x180011ce4`
- `0x180011d68`
- `0x180011e0c`
- `0x180011eb4`
- `0x180011f74`

## callees

- `0x180011b54`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011b96`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011b96`

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
0x180011b54  sub     rsp, 38h
0x180011b58  mov     r8, [rcx+8]
0x180011b5c  mov     rax, [rsp+38h+arg_20]
0x180011b61  test    r8, r8
0x180011b64  jnz     short loc_180011B6E
0x180011b66  mov     [rax], r8
0x180011b69  xor     r10d, r10d
0x180011b6c  jmp     short loc_180011B7B
0x180011b6e  mov     [rax], r8
0x180011b71  mov     r10d, 2
0x180011b77  movzx   r8d, word ptr [r8]
0x180011b7b  mov     [rax+8], r8d
0x180011b7f  xor     r8d, r8d; ActivityId
0x180011b82  mov     [rsp+38h+UserData], rax; UserData
0x180011b87  mov     [rax+0Ch], r10d
0x180011b8b  mov     rcx, [rcx]; RegHandle
0x180011b8e  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180011b93  xor     r9d, r9d; RelatedActivityId
0x180011b96  call    cs:__imp_EventWriteTransfer
0x180011b9d  nop     dword ptr [rax+rax+00h]
0x180011ba2  add     rsp, 38h
0x180011ba6  retn
```
