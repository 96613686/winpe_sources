# McGenEventWrite_EventWriteTransfer

- ea: `0x18000a160`
- end: `0x18000a1b2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `51`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800015e0`
- `0x180002c30`
- `0x180003f00`
- `0x1800043f0`
- `0x180004dc0`
- `0x180005490`
- `0x180005b78`
- `0x180005d70`
- `0x18000624c`
- `0x180006540`
- `0x180006eb0`
- `0x1800075c4`
- `0x180007870`
- `0x180007a70`
- `0x180007cf0`
- `0x180007ef0`
- `0x180008140`
- `0x180009740`
- `0x1800097d0`
- `0x1800098f0`
- `0x180009990`
- `0x180009dd0`
- `0x18000a0a0`
- `0x18000a740`
- `0x18000aa90`
- `0x18000add0`
- `0x18000bab4`
- `0x18000be70`
- `0x18000c3f0`
- `0x18000c820`
- `0x18000cae0`
- `0x18000d970`
- `0x18000f150`
- `0x18000f920`
- `0x18000fd90`
- `0x1800134f0`
- `0x180013a1c`
- `0x180013ab0`
- `0x180014430`
- `0x180014ab0`
- `0x180014ed8`
- `0x180014f80`
- `0x180015164`
- `0x1800152d0`
- `0x180017c4c`
- `0x180018d40`
- `0x180019470`
- `0x18001bb24`
- `0x18002063c`
- `0x180026aa0`

## callees

- `0x18000a160`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a199`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a199`

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

  v5 = (unsigned __int16 *)qword_18004D028;
  if ( qword_18004D028 )
  {
    UserData->Ptr = qword_18004D028;
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
  return EventWriteTransfer(NetworkConnectionBrokerEtwProviderGuid_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000a160  sub     rsp, 38h
0x18000a164  mov     rcx, cs:qword_18004D028
0x18000a16b  mov     rax, [rsp+38h+arg_20]
0x18000a170  test    rcx, rcx
0x18000a173  jnz     short loc_18000A1A4
0x18000a175  mov     [rax], rcx
0x18000a178  xor     r8d, r8d
0x18000a17b  mov     [rax+8], ecx
0x18000a17e  mov     [rax+0Ch], r8d
0x18000a182  xor     r8d, r8d; ActivityId
0x18000a185  mov     rcx, cs:NetworkConnectionBrokerEtwProviderGuid_Context; RegHandle
0x18000a18c  mov     [rsp+38h+UserData], rax; UserData
0x18000a191  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000a196  xor     r9d, r9d; RelatedActivityId
0x18000a199  call    cs:__imp_EventWriteTransfer
0x18000a19f  add     rsp, 38h
0x18000a1a3  retn
0x18000a1a4  mov     [rax], rcx
0x18000a1a7  mov     r8d, 2
0x18000a1ad  movzx   ecx, word ptr [rcx]
0x18000a1b0  jmp     short loc_18000A17B
```
