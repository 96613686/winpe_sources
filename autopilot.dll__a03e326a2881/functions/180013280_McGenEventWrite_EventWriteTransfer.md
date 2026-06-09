# McGenEventWrite_EventWriteTransfer

- ea: `0x180013280`
- end: `0x1800132d2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ca98`
- `0x180012870`
- `0x1800132d8`
- `0x180013370`
- `0x1800133f0`
- `0x180016420`
- `0x18001e260`
- `0x18002230c`
- `0x180022d84`

## callees

- `0x180013280`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800132c7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800132c7`

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

  v5 = (unsigned __int16 *)qword_180042068;
  if ( qword_180042068 )
  {
    UserData->Ptr = qword_180042068;
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
  return EventWriteTransfer(MODERNDEPLOYMENT_DIAGNOSTICS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180013280  sub     rsp, 38h
0x180013284  mov     rcx, cs:qword_180042068
0x18001328b  mov     rax, [rsp+38h+arg_20]
0x180013290  test    rcx, rcx
0x180013293  jnz     short loc_18001329D
0x180013295  mov     [rax], rcx
0x180013298  xor     r8d, r8d
0x18001329b  jmp     short loc_1800132A9
0x18001329d  mov     [rax], rcx
0x1800132a0  mov     r8d, 2
0x1800132a6  movzx   ecx, word ptr [rcx]
0x1800132a9  mov     [rax+8], ecx
0x1800132ac  mov     [rax+0Ch], r8d
0x1800132b0  xor     r8d, r8d; ActivityId
0x1800132b3  mov     rcx, cs:MODERNDEPLOYMENT_DIAGNOSTICS_Context; RegHandle
0x1800132ba  mov     [rsp+38h+UserData], rax; UserData
0x1800132bf  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800132c4  xor     r9d, r9d; RelatedActivityId
0x1800132c7  call    cs:__imp_EventWriteTransfer
0x1800132cd  add     rsp, 38h
0x1800132d1  retn
```
