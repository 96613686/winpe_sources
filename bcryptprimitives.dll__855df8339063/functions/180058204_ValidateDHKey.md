# ValidateDHKey

- ea: `0x180058204`
- end: `0x180058282`
- name: `ValidateDHKey`
- size: `126`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180058400`
- `0x1800680f0`
- `0x180068378`
- `0x180068ab8`

## callees

- `0x18000ecb0`
- `0x180058204`

## string_xrefs

- `0x180058255`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall ValidateDHKey(__int64 a1, int a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // r9

  v3 = 0;
  if ( !a1 || !a3 )
    return (unsigned int)-1073741811;
  if ( *(_DWORD *)(a1 + 4) != 1297304409
    || *(_DWORD *)(a1 + 8) != 196610
    || (unsigned int)(*(_DWORD *)(a1 + 12) - 64) > 0x1C0 )
  {
    v4 = 219;
    goto LABEL_11;
  }
  if ( a2 && !*(_BYTE *)(*(_QWORD *)(a1 + 32) + 4LL) )
  {
    v4 = 229;
LABEL_11:
    v3 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v4);
    return v3;
  }
  *a3 = a1;
  return v3;
}

```

## disassembly

```asm
0x180058204  push    rbx
0x180058206  sub     rsp, 20h
0x18005820a  xor     ebx, ebx
0x18005820c  test    rcx, rcx
0x18005820f  jz      short loc_180058274
0x180058211  test    r8, r8
0x180058214  jz      short loc_180058274
0x180058216  cmp     dword ptr [rcx+4], 4D534B59h
0x18005821d  jnz     short loc_18005824F
0x18005821f  cmp     dword ptr [rcx+8], 30002h
0x180058226  jnz     short loc_18005824F
0x180058228  mov     eax, [rcx+0Ch]
0x18005822b  sub     eax, 40h ; '@'
0x18005822e  cmp     eax, 1C0h
0x180058233  ja      short loc_18005824F
0x180058235  test    edx, edx
0x180058237  jz      short loc_18005824A
0x180058239  mov     rax, [rcx+20h]
0x18005823d  cmp     [rax+4], bl
0x180058240  jnz     short loc_18005824A
0x180058242  mov     r9d, 0E5h
0x180058248  jmp     short loc_180058255
0x18005824a  mov     [r8], rcx
0x18005824d  jmp     short loc_180058279
0x18005824f  mov     r9d, 0DBh
0x180058255  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005825c  mov     ecx, 0C000000Dh
0x180058261  lea     rdx, aStatus; "Status"
0x180058268  mov     ebx, 0C000000Dh
0x18005826d  call    DebugTraceError
0x180058272  jmp     short loc_180058279
0x180058274  mov     ebx, 0C000000Dh
0x180058279  mov     eax, ebx
0x18005827b  add     rsp, 20h
0x18005827f  pop     rbx
0x180058280  retn
```
