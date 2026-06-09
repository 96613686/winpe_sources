# sub_14000BFFC

- ea: `0x14000bffc`
- end: `0x14000c04d`
- name: `sub_14000BFFC`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `66`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c1b0`
- `0x14000c370`
- `0x14000ed8c`
- `0x14000efc0`
- `0x140012eb4`
- `0x140013100`
- `0x140014950`
- `0x140015468`
- `0x140015550`
- `0x1400156a0`
- `0x140015d10`
- `0x140016b18`
- `0x140017390`
- `0x140018b1c`
- `0x140019010`
- `0x140019530`
- `0x1400196c0`
- `0x140019d90`
- `0x14001a350`
- `0x14001af00`
- `0x14001b170`
- `0x14001b2a0`
- `0x14001bc70`
- `0x14001bd18`
- `0x14001bdc8`
- `0x14001bef0`
- `0x14001c0e0`
- `0x14001c580`
- `0x14001cc00`
- `0x140020830`
- `0x140020958`
- `0x140021ed4`
- `0x140022190`
- `0x140022220`
- `0x140022320`
- `0x140022400`
- `0x140024238`
- `0x140024f50`
- `0x1400250c0`
- `0x140025e10`
- `0x140025f30`
- `0x140027320`
- `0x140027460`
- `0x140027a74`
- `0x1400283a0`
- `0x1400285e0`
- `0x1400288d0`
- `0x140028ab4`
- `0x140028f00`
- `0x1400314d4`

## callees

- `0x14000bffc`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x14000c042`
- `ADVAPI32!EventWriteTransfer` at `0x14000c042`

## pseudocode

```c
ULONG __fastcall sub_14000BFFC(
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
0x14000bffc  sub     rsp, 38h
0x14000c000  mov     r10, [rcx+8]
0x14000c004  xor     eax, eax
0x14000c006  mov     r8, [rsp+38h+arg_20]
0x14000c00b  mov     r11d, r9d
0x14000c00e  test    r10, r10
0x14000c011  jnz     short loc_14000C01B
0x14000c013  mov     [r8], rax
0x14000c016  mov     r9d, eax
0x14000c019  jmp     short loc_14000C027
0x14000c01b  mov     [r8], r10
0x14000c01e  mov     eax, 2
0x14000c023  movzx   r9d, word ptr [r10]
0x14000c027  mov     [r8+8], r9d
0x14000c02b  xor     r9d, r9d; RelatedActivityId
0x14000c02e  mov     [r8+0Ch], eax
0x14000c032  mov     rcx, [rcx]; RegHandle
0x14000c035  mov     [rsp+38h+UserData], r8; UserData
0x14000c03a  xor     r8d, r8d; ActivityId
0x14000c03d  mov     [rsp+38h+UserDataCount], r11d; UserDataCount
0x14000c042  call    cs:EventWriteTransfer
0x14000c048  add     rsp, 38h
0x14000c04c  retn
```
