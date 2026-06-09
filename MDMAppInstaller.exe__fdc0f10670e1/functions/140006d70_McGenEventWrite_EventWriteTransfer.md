# McGenEventWrite_EventWriteTransfer

- ea: `0x140006d70`
- end: `0x140006dc2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140006dc8`
- `0x140007c64`
- `0x140012e98`
- `0x140012f38`
- `0x140012fe0`
- `0x14001309c`
- `0x140013170`
- `0x14001326c`

## callees

- `0x140006d70`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x140006db7`
- `ADVAPI32!EventWriteTransfer` at `0x140006db7`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_14002B008;
  if ( qword_14002B008 )
  {
    UserData->Ptr = qword_14002B008;
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
  return EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140006d70  sub     rsp, 38h
0x140006d74  mov     rcx, cs:qword_14002B008
0x140006d7b  mov     rax, [rsp+38h+arg_20]
0x140006d80  test    rcx, rcx
0x140006d83  jnz     short loc_140006D8D
0x140006d85  mov     [rax], rcx
0x140006d88  xor     r8d, r8d
0x140006d8b  jmp     short loc_140006D99
0x140006d8d  mov     [rax], rcx
0x140006d90  mov     r8d, 2
0x140006d96  movzx   ecx, word ptr [rcx]
0x140006d99  mov     [rax+8], ecx
0x140006d9c  mov     [rax+0Ch], r8d
0x140006da0  xor     r8d, r8d; ActivityId
0x140006da3  mov     rcx, cs:MDM_ENTERPRISE_DIAGNOSTICS_Context; RegHandle
0x140006daa  mov     [rsp+38h+UserData], rax; UserData
0x140006daf  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140006db4  xor     r9d, r9d; RelatedActivityId
0x140006db7  call    cs:__imp_EventWriteTransfer
0x140006dbd  add     rsp, 38h
0x140006dc1  retn
```
