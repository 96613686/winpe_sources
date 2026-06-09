# McGenEventWrite_EventWriteTransfer

- ea: `0x180013520`
- end: `0x180013579`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cb38`
- `0x180012ab0`
- `0x180013580`
- `0x180013618`
- `0x18001369c`
- `0x1800168c0`
- `0x18001eaa8`
- `0x180022dd4`
- `0x1800238cc`

## callees

- `0x180013520`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013567`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013567`

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

  v5 = (unsigned __int16 *)qword_180043068;
  if ( qword_180043068 )
  {
    UserData->Ptr = qword_180043068;
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
0x180013520  sub     rsp, 38h
0x180013524  mov     rcx, cs:qword_180043068
0x18001352b  mov     rax, [rsp+38h+arg_20]
0x180013530  test    rcx, rcx
0x180013533  jnz     short loc_18001353D
0x180013535  mov     [rax], rcx
0x180013538  xor     r8d, r8d
0x18001353b  jmp     short loc_180013549
0x18001353d  mov     [rax], rcx
0x180013540  mov     r8d, 2
0x180013546  movzx   ecx, word ptr [rcx]
0x180013549  mov     [rax+8], ecx
0x18001354c  mov     [rax+0Ch], r8d
0x180013550  xor     r8d, r8d; ActivityId
0x180013553  mov     rcx, cs:MODERNDEPLOYMENT_DIAGNOSTICS_Context; RegHandle
0x18001355a  mov     [rsp+38h+UserData], rax; UserData
0x18001355f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180013564  xor     r9d, r9d; RelatedActivityId
0x180013567  call    cs:__imp_EventWriteTransfer
0x18001356e  nop     dword ptr [rax+rax+00h]
0x180013573  add     rsp, 38h
0x180013577  retn
```
