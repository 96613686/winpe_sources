# McGenEventWrite_EtwWriteTransfer

- ea: `0x140001030`
- end: `0x140001089`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: `NTSTATUS __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001090`
- `0x140001500`
- `0x140001544`

## callees

- `0x140001030`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001077`
- `ntoskrnl!EtwWriteTransfer` at `0x140001077`

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

  v5 = (unsigned __int16 *)qword_140007008;
  if ( qword_140007008 )
  {
    UserData->Ptr = qword_140007008;
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
  return EtwWriteTransfer(UevAgentDriver_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140001030  sub     rsp, 38h
0x140001034  mov     rcx, cs:qword_140007008
0x14000103b  mov     rax, [rsp+38h+arg_20]
0x140001040  test    rcx, rcx
0x140001043  jnz     short loc_14000104D
0x140001045  mov     [rax], rcx
0x140001048  xor     r8d, r8d
0x14000104b  jmp     short loc_140001059
0x14000104d  mov     [rax], rcx
0x140001050  mov     r8d, 2
0x140001056  movzx   ecx, word ptr [rcx]
0x140001059  mov     [rax+8], ecx
0x14000105c  mov     [rax+0Ch], r8d
0x140001060  xor     r8d, r8d; ActivityId
0x140001063  mov     rcx, cs:UevAgentDriver_Context; RegHandle
0x14000106a  mov     [rsp+38h+UserData], rax; UserData
0x14000106f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140001074  xor     r9d, r9d; RelatedActivityId
0x140001077  call    cs:__imp_EtwWriteTransfer
0x14000107e  nop     dword ptr [rax+rax+00h]
0x140001083  add     rsp, 38h
0x140001087  retn
```
