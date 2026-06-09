# McGenEventWrite_EventWriteTransfer

- ea: `0x180018910`
- end: `0x180018962`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016e84`
- `0x180017214`
- `0x18001753c`
- `0x180017bd0`
- `0x180017f3c`
- `0x180018968`

## callees

- `0x180018910`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018957`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018957`

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

  v5 = (unsigned __int16 *)qword_1800368B8;
  if ( qword_1800368B8 )
  {
    UserData->Ptr = qword_1800368B8;
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
  return EventWriteTransfer(Microsoft_Windows_XPerfCore_ETWProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180018910  sub     rsp, 38h
0x180018914  mov     rcx, cs:qword_1800368B8
0x18001891b  mov     rax, [rsp+38h+arg_20]
0x180018920  test    rcx, rcx
0x180018923  jnz     short loc_18001892D
0x180018925  mov     [rax], rcx
0x180018928  xor     r8d, r8d
0x18001892b  jmp     short loc_180018939
0x18001892d  mov     [rax], rcx
0x180018930  mov     r8d, 2
0x180018936  movzx   ecx, word ptr [rcx]
0x180018939  mov     [rax+8], ecx
0x18001893c  mov     [rax+0Ch], r8d
0x180018940  xor     r8d, r8d; ActivityId
0x180018943  mov     rcx, cs:Microsoft_Windows_XPerfCore_ETWProvider_Context; RegHandle
0x18001894a  mov     [rsp+38h+UserData], rax; UserData
0x18001894f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180018954  xor     r9d, r9d; RelatedActivityId
0x180018957  call    cs:__imp_EventWriteTransfer
0x18001895d  add     rsp, 38h
0x180018961  retn
```
