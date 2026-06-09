# McGenEventWrite_EventWriteTransfer

- ea: `0x18000a154`
- end: `0x18000a1a1`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `69`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c40`
- `0x1800091b0`
- `0x180019344`
- `0x18001a8c8`
- `0x180024270`
- `0x1800249d8`
- `0x18002f230`
- `0x18002f5c4`
- `0x18003175c`
- `0x180031918`
- `0x180032958`
- `0x180035004`
- `0x180038cd4`
- `0x18003af80`
- `0x180048c30`
- `0x180048e94`
- `0x180048f00`
- `0x180048f6c`
- `0x180048fd8`
- `0x180049044`
- `0x18004a1b0`
- `0x18004a214`
- `0x18004a278`
- `0x18004a2dc`
- `0x18004ac00`
- `0x18004afc0`
- `0x180056fac`
- `0x1800570f0`
- `0x180057244`
- `0x180057734`
- `0x1800577a0`
- `0x18005780c`
- `0x180057b20`
- `0x180057b84`
- `0x180057be8`
- `0x180057c4c`
- `0x180057cb0`
- `0x180058e54`
- `0x18005b310`
- `0x18005ec50`
- `0x18005ed4c`
- `0x18005ffe8`
- `0x1800600a0`
- `0x1800601d4`
- `0x1800605b4`
- `0x180060620`
- `0x180060684`
- `0x1800606e8`
- `0x18006074c`
- `0x180061f90`

## callees

- `0x18000a154`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a187`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a187`

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
0x18000a154  sub     rsp, 38h
0x18000a158  mov     r8, [rcx+8]
0x18000a15c  mov     rax, [rsp+38h+arg_20]
0x18000a161  test    r8, r8
0x18000a164  jnz     short loc_18000A192
0x18000a166  mov     [rax], r8
0x18000a169  xor     r10d, r10d
0x18000a16c  mov     [rax+8], r8d
0x18000a170  xor     r8d, r8d; ActivityId
0x18000a173  mov     [rsp+38h+UserData], rax; UserData
0x18000a178  mov     [rax+0Ch], r10d
0x18000a17c  mov     rcx, [rcx]; RegHandle
0x18000a17f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000a184  xor     r9d, r9d; RelatedActivityId
0x18000a187  call    cs:__imp_EventWriteTransfer
0x18000a18d  add     rsp, 38h
0x18000a191  retn
0x18000a192  mov     [rax], r8
0x18000a195  mov     r10d, 2
0x18000a19b  movzx   r8d, word ptr [r8]
0x18000a19f  jmp     short loc_18000A16C
```
