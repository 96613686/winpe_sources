# McGenEventWrite_EventWriteTransfer

- ea: `0x18000afcc`
- end: `0x18000b01d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020ef0`

## callees

- `0x18000afcc`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18000b012`
- `ADVAPI32!EventWriteTransfer` at `0x18000b012`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r10
  int v6; // eax
  ULONG v8; // r9d

  v5 = (unsigned __int16 *)a1[1];
  v6 = 0;
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
    v6 = 2;
    v8 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v8 = 0;
  }
  UserData->Size = v8;
  UserData->Reserved = v6;
  return EventWriteTransfer(*a1, a2, 0, 0, a4, UserData);
}

```

## disassembly

```asm
0x18000afcc  sub     rsp, 38h
0x18000afd0  mov     r10, [rcx+8]
0x18000afd4  xor     eax, eax
0x18000afd6  mov     r8, [rsp+38h+arg_20]
0x18000afdb  mov     r11d, r9d
0x18000afde  test    r10, r10
0x18000afe1  jnz     short loc_18000AFEB
0x18000afe3  mov     [r8], rax
0x18000afe6  mov     r9d, eax
0x18000afe9  jmp     short loc_18000AFF7
0x18000afeb  mov     [r8], r10
0x18000afee  mov     eax, 2
0x18000aff3  movzx   r9d, word ptr [r10]
0x18000aff7  mov     [r8+8], r9d
0x18000affb  xor     r9d, r9d; RelatedActivityId
0x18000affe  mov     [r8+0Ch], eax
0x18000b002  mov     rcx, [rcx]; RegHandle
0x18000b005  mov     [rsp+38h+UserData], r8; UserData
0x18000b00a  xor     r8d, r8d; ActivityId
0x18000b00d  mov     [rsp+38h+UserDataCount], r11d; UserDataCount
0x18000b012  call    cs:__imp_EventWriteTransfer
0x18000b018  add     rsp, 38h
0x18000b01c  retn
```
