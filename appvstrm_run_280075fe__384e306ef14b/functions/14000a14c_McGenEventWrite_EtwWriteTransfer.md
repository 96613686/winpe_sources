# McGenEventWrite_EtwWriteTransfer

- ea: `0x14000a14c`
- end: `0x14000a1a5`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a1ac`
- `0x140015898`

## callees

- `0x14000a14c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000a192`
- `ntoskrnl!EtwWriteTransfer` at `0x14000a192`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r10
  ULONG v7; // r9d
  int v8; // r11d

  v5 = (unsigned __int16 *)a1[1];
  v7 = 0;
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
    v8 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v8 = 0;
  }
  UserData->Size = v7;
  UserData->Reserved = v8;
  return EtwWriteTransfer(*a1, a2, a3, 0, a4, UserData);
}

```

## disassembly

```asm
0x14000a14c  push    rbx
0x14000a14e  sub     rsp, 30h
0x14000a152  mov     r10, [rcx+8]
0x14000a156  mov     ebx, r9d
0x14000a159  mov     rax, [rsp+38h+arg_20]
0x14000a15e  xor     r9d, r9d
0x14000a161  test    r10, r10
0x14000a164  jnz     short loc_14000A16E
0x14000a166  mov     [rax], r9
0x14000a169  mov     r11d, r9d
0x14000a16c  jmp     short loc_14000A17B
0x14000a16e  mov     [rax], r10
0x14000a171  mov     r11d, 2
0x14000a177  movzx   r9d, word ptr [r10]
0x14000a17b  mov     [rax+8], r9d
0x14000a17f  xor     r9d, r9d; RelatedActivityId
0x14000a182  mov     [rax+0Ch], r11d
0x14000a186  mov     rcx, [rcx]; RegHandle
0x14000a189  mov     [rsp+38h+UserData], rax; UserData
0x14000a18e  mov     [rsp+38h+UserDataCount], ebx; UserDataCount
0x14000a192  call    cs:__imp_EtwWriteTransfer
0x14000a199  nop     dword ptr [rax+rax+00h]
0x14000a19e  add     rsp, 30h
0x14000a1a2  pop     rbx
0x14000a1a3  retn
```
