# McGenEventWrite_EventWriteTransfer

- ea: `0x180017894`
- end: `0x1800178e1`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180013618`
- `0x180014094`
- `0x18001afa8`
- `0x18001cd24`
- `0x18001e2e8`
- `0x180020e44`
- `0x18002b9b4`

## callees

- `0x180017894`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800178d6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800178d6`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180017894  sub     rsp, 38h
0x180017898  mov     r8, [rcx+8]
0x18001789c  mov     rax, [rsp+38h+arg_20]
0x1800178a1  test    r8, r8
0x1800178a4  jnz     short loc_1800178AE
0x1800178a6  mov     [rax], r8
0x1800178a9  xor     r10d, r10d
0x1800178ac  jmp     short loc_1800178BB
0x1800178ae  mov     [rax], r8
0x1800178b1  mov     r10d, 2
0x1800178b7  movzx   r8d, word ptr [r8]
0x1800178bb  mov     [rax+8], r8d
0x1800178bf  xor     r8d, r8d; ActivityId
0x1800178c2  mov     [rsp+38h+UserData], rax; UserData
0x1800178c7  mov     [rax+0Ch], r10d
0x1800178cb  mov     rcx, [rcx]; RegHandle
0x1800178ce  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800178d3  xor     r9d, r9d; RelatedActivityId
0x1800178d6  call    cs:__imp_EventWriteTransfer
0x1800178dc  add     rsp, 38h
0x1800178e0  retn
```
