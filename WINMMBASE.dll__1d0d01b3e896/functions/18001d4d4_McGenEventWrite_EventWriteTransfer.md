# McGenEventWrite_EventWriteTransfer

- ea: `0x18001d4d4`
- end: `0x18001d526`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800048e0`
- `0x180005030`
- `0x18001d52c`

## callees

- `0x18001d4d4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d51b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d51b`

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

  v5 = (unsigned __int16 *)qword_18002C058;
  if ( qword_18002C058 )
  {
    UserData->Ptr = qword_18002C058;
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
  return EventWriteTransfer(WINMM_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001d4d4  sub     rsp, 38h
0x18001d4d8  mov     rcx, cs:qword_18002C058
0x18001d4df  mov     rax, [rsp+38h+arg_20]
0x18001d4e4  test    rcx, rcx
0x18001d4e7  jnz     short loc_18001D4F1
0x18001d4e9  mov     [rax], rcx
0x18001d4ec  xor     r8d, r8d
0x18001d4ef  jmp     short loc_18001D4FD
0x18001d4f1  mov     [rax], rcx
0x18001d4f4  mov     r8d, 2
0x18001d4fa  movzx   ecx, word ptr [rcx]
0x18001d4fd  mov     [rax+8], ecx
0x18001d500  mov     [rax+0Ch], r8d
0x18001d504  xor     r8d, r8d; ActivityId
0x18001d507  mov     rcx, cs:WINMM_PROVIDER_Context; RegHandle
0x18001d50e  mov     [rsp+38h+UserData], rax; UserData
0x18001d513  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001d518  xor     r9d, r9d; RelatedActivityId
0x18001d51b  call    cs:__imp_EventWriteTransfer
0x18001d521  add     rsp, 38h
0x18001d525  retn
```
