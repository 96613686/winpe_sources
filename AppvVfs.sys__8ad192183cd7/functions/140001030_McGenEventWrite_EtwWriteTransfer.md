# McGenEventWrite_EtwWriteTransfer

- ea: `0x140001030`
- end: `0x140001089`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: `NTSTATUS __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const GUID *, ULONG, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001090`
- `0x140012fa0`

## callees

- `0x140001030`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001076`
- `ntoskrnl!EtwWriteTransfer` at `0x140001076`

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
0x140001030  push    rbx
0x140001032  sub     rsp, 30h
0x140001036  mov     r10, [rcx+8]
0x14000103a  mov     ebx, r9d
0x14000103d  mov     rax, [rsp+38h+arg_20]
0x140001042  xor     r9d, r9d
0x140001045  test    r10, r10
0x140001048  jnz     short loc_140001052
0x14000104a  mov     [rax], r9
0x14000104d  mov     r11d, r9d
0x140001050  jmp     short loc_14000105F
0x140001052  mov     [rax], r10
0x140001055  mov     r11d, 2
0x14000105b  movzx   r9d, word ptr [r10]
0x14000105f  mov     [rax+8], r9d
0x140001063  xor     r9d, r9d; RelatedActivityId
0x140001066  mov     [rax+0Ch], r11d
0x14000106a  mov     rcx, [rcx]; RegHandle
0x14000106d  mov     [rsp+38h+UserData], rax; UserData
0x140001072  mov     [rsp+38h+UserDataCount], ebx; UserDataCount
0x140001076  call    cs:__imp_EtwWriteTransfer
0x14000107d  nop     dword ptr [rax+rax+00h]
0x140001082  add     rsp, 30h
0x140001086  pop     rbx
0x140001087  retn
```
