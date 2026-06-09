# CPeerTable::DoesPeerMatch(_WFC_PEER_TABLE_ENTRY *,ushort,_WDI_MAC_ADDRESS *)

- ea: `0x14004ee14`
- end: `0x14004ee74`
- name: `?DoesPeerMatch@CPeerTable@@AEAAEPEAU_WFC_PEER_TABLE_ENTRY@@GPEAU_WDI_MAC_ADDRESS@@@Z`
- size: `96`
- prototype: `unsigned __int8(CPeerTable *__hidden this, struct _WFC_PEER_TABLE_ENTRY *, unsigned __int16, struct _WDI_MAC_ADDRESS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14004eb74`

## callees

- `0x14004ee14`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14004ee2f`
- `ntoskrnl!RtlCompareMemory` at `0x14004ee2f`

## pseudocode

```c
bool __fastcall CPeerTable::DoesPeerMatch(
        CPeerTable *this,
        struct _WFC_PEER_TABLE_ENTRY *a2,
        __int16 a3,
        struct _WDI_MAC_ADDRESS *a4)
{
  char v4; // cl
  _WDI_MAC_ADDRESS *p_PeerAddr; // r10

  v4 = 1;
  p_PeerAddr = &a2->PeerAddr;
  if ( (a4->Address[0] & 1) == 0 )
    return RtlCompareMemory(p_PeerAddr, a4, 6u) == 6;
  if ( p_PeerAddr->Address[0] != 0xFF
    || a2->PeerAddr.Address[1] != 0xFF
    || a2->PeerAddr.Address[2] != 0xFF
    || a2->PeerAddr.Address[3] != 0xFF
    || a2->PeerAddr.Address[4] != 0xFF
    || a2->PeerAddr.Address[5] != 0xFF
    || a2->PortId != a3 )
  {
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x14004ee14  sub     rsp, 28h
0x14004ee18  mov     cl, 1
0x14004ee1a  lea     r10, [rdx+4]
0x14004ee1e  test    [r9], cl
0x14004ee21  jnz     short loc_14004EE4A
0x14004ee23  mov     r8d, 6; Length
0x14004ee29  mov     rdx, r9; Source2
0x14004ee2c  mov     rcx, r10; Source1
0x14004ee2f  call    cs:__imp_RtlCompareMemory
0x14004ee36  nop     dword ptr [rax+rax+00h]
0x14004ee3b  cmp     rax, 6
0x14004ee3f  setz    cl
0x14004ee42  mov     al, cl
0x14004ee44  add     rsp, 28h
0x14004ee48  retn
0x14004ee4a  mov     al, 0FFh
0x14004ee4c  cmp     [r10], al
0x14004ee4f  jnz     short loc_14004EE70
0x14004ee51  cmp     [rdx+5], al
0x14004ee54  jnz     short loc_14004EE70
0x14004ee56  cmp     [rdx+6], al
0x14004ee59  jnz     short loc_14004EE70
0x14004ee5b  cmp     [rdx+7], al
0x14004ee5e  jnz     short loc_14004EE70
0x14004ee60  cmp     [rdx+8], al
0x14004ee63  jnz     short loc_14004EE70
0x14004ee65  cmp     [rdx+9], al
0x14004ee68  jnz     short loc_14004EE70
0x14004ee6a  cmp     [rdx], r8w
0x14004ee6e  jz      short loc_14004EE42
0x14004ee70  xor     cl, cl
0x14004ee72  jmp     short loc_14004EE42
```
