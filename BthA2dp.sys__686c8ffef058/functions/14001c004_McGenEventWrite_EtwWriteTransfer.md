# McGenEventWrite_EtwWriteTransfer

- ea: `0x14001c004`
- end: `0x14001c05d`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14001be60`
- `0x14001bed0`
- `0x14001bf14`
- `0x14001bf6c`
- `0x14003484c`
- `0x14003b29c`
- `0x14003b2fc`
- `0x14003b35c`
- `0x14003b3dc`
- `0x14003b444`

## callees

- `0x14001c004`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001c04b`
- `ntoskrnl!EtwWriteTransfer` at `0x14001c04b`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_14006F008;
  if ( qword_14006F008 )
  {
    UserData->Ptr = qword_14006F008;
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
  return EtwWriteTransfer(BTHAudClassDrv_ETW_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14001c004  sub     rsp, 38h
0x14001c008  mov     rcx, cs:qword_14006F008
0x14001c00f  mov     rax, [rsp+38h+arg_20]
0x14001c014  test    rcx, rcx
0x14001c017  jnz     short loc_14001C021
0x14001c019  mov     [rax], rcx
0x14001c01c  xor     r8d, r8d
0x14001c01f  jmp     short loc_14001C02D
0x14001c021  mov     [rax], rcx
0x14001c024  mov     r8d, 2
0x14001c02a  movzx   ecx, word ptr [rcx]
0x14001c02d  mov     [rax+8], ecx
0x14001c030  mov     [rax+0Ch], r8d
0x14001c034  xor     r8d, r8d; ActivityId
0x14001c037  mov     rcx, cs:BTHAudClassDrv_ETW_PROVIDER_Context; RegHandle
0x14001c03e  mov     [rsp+38h+UserData], rax; UserData
0x14001c043  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14001c048  xor     r9d, r9d; RelatedActivityId
0x14001c04b  call    cs:__imp_EtwWriteTransfer
0x14001c052  nop     dword ptr [rax+rax+00h]
0x14001c057  add     rsp, 38h
0x14001c05b  retn
```
