# McGenEventWrite_EtwWriteTransfer

- ea: `0x18000fcb4`
- end: `0x18000fd0d`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: `NTSTATUS __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const GUID *, ULONG, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fd14`
- `0x18000fd5c`
- `0x18000fdc0`

## callees

- `0x18000fcb4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x18000fcfa`
- `ntoskrnl!EtwWriteTransfer` at `0x18000fcfa`

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
0x18000fcb4  push    rbx
0x18000fcb6  sub     rsp, 30h
0x18000fcba  mov     r10, [rcx+8]
0x18000fcbe  mov     ebx, r9d
0x18000fcc1  mov     rax, [rsp+38h+arg_20]
0x18000fcc6  xor     r9d, r9d
0x18000fcc9  test    r10, r10
0x18000fccc  jnz     short loc_18000FCD6
0x18000fcce  mov     [rax], r9
0x18000fcd1  mov     r11d, r9d
0x18000fcd4  jmp     short loc_18000FCE3
0x18000fcd6  mov     [rax], r10
0x18000fcd9  mov     r11d, 2
0x18000fcdf  movzx   r9d, word ptr [r10]
0x18000fce3  mov     [rax+8], r9d
0x18000fce7  xor     r9d, r9d; RelatedActivityId
0x18000fcea  mov     [rax+0Ch], r11d
0x18000fcee  mov     rcx, [rcx]; RegHandle
0x18000fcf1  mov     [rsp+38h+UserData], rax; UserData
0x18000fcf6  mov     [rsp+38h+UserDataCount], ebx; UserDataCount
0x18000fcfa  call    cs:__imp_EtwWriteTransfer
0x18000fd01  nop     dword ptr [rax+rax+00h]
0x18000fd06  add     rsp, 30h
0x18000fd0a  pop     rbx
0x18000fd0b  retn
```
