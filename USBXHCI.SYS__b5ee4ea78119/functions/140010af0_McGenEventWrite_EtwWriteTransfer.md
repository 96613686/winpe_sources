# McGenEventWrite_EtwWriteTransfer

- ea: `0x140010af0`
- end: `0x140010b46`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f00`
- `0x140004dbc`
- `0x140004e68`
- `0x1400050ac`
- `0x140010960`
- `0x1400109f0`
- `0x140010a90`
- `0x14001c4d4`
- `0x14001c554`
- `0x140021eb4`
- `0x1400227a8`
- `0x14002e028`
- `0x1400304c0`
- `0x14003204c`
- `0x14003242c`
- `0x1400327a4`
- `0x140033bcc`
- `0x140034218`
- `0x14003582c`
- `0x140035fcc`
- `0x140044d30`
- `0x140044df4`
- `0x140044e98`
- `0x140044f08`
- `0x140044fb4`
- `0x140050da8`
- `0x140050fac`
- `0x1400511bc`
- `0x14005125c`
- `0x1400514a8`

## callees

- `0x140010af0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140010b26`
- `ntoskrnl!EtwWriteTransfer` at `0x140010b26`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_14006BF48;
  if ( qword_14006BF48 )
  {
    UserData->Ptr = qword_14006BF48;
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
  return EtwWriteTransfer(MS_USBXHCI_ETW_PROVIDER_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140010af0  sub     rsp, 38h
0x140010af4  mov     rcx, cs:qword_14006BF48
0x140010afb  mov     rax, [rsp+38h+arg_20]
0x140010b00  test    rcx, rcx
0x140010b03  jnz     short loc_140010B38
0x140010b05  mov     [rax], rcx
0x140010b08  xor     r10d, r10d
0x140010b0b  mov     [rax+8], ecx
0x140010b0e  mov     [rsp+38h+UserData], rax; UserData
0x140010b13  mov     [rax+0Ch], r10d
0x140010b17  mov     rcx, cs:MS_USBXHCI_ETW_PROVIDER_Context; RegHandle
0x140010b1e  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140010b23  xor     r9d, r9d; RelatedActivityId
0x140010b26  call    cs:__imp_EtwWriteTransfer
0x140010b2d  nop     dword ptr [rax+rax+00h]
0x140010b32  add     rsp, 38h
0x140010b36  retn
0x140010b38  mov     [rax], rcx
0x140010b3b  mov     r10d, 2
0x140010b41  movzx   ecx, word ptr [rcx]
0x140010b44  jmp     short loc_140010B0B
```
