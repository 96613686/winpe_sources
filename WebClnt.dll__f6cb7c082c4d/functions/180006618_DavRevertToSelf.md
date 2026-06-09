# DavRevertToSelf

- ea: `0x180006618`
- end: `0x180006663`
- name: `DavRevertToSelf`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003458`
- `0x180003a9c`
- `0x180003cbc`
- `0x1800049bc`
- `0x180005568`
- `0x1800056f4`
- `0x180005844`
- `0x180005de4`
- `0x180006d20`
- `0x180007e10`
- `0x1800099d0`
- `0x18000a770`

## callees

- `0x180006618`
- `0x18000b7dc`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18000661e`
- `RPCRT4!RpcRevertToSelf` at `0x18000661e`

## pseudocode

```c
__int64 DavRevertToSelf()
{
  unsigned int v0; // ebx

  v0 = RpcRevertToSelf();
  if ( v0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xE6u, (__int64)WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x180006618  push    rbx
0x18000661a  sub     rsp, 20h
0x18000661e  call    cs:__imp_RpcRevertToSelf
0x180006624  mov     ebx, eax
0x180006626  test    eax, eax
0x180006628  jz      short loc_18000665B
0x18000662a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006631  lea     rax, WPP_GLOBAL_Control
0x180006638  cmp     rcx, rax
0x18000663b  jz      short loc_18000665B
0x18000663d  test    byte ptr [rcx+1Ch], 1
0x180006641  jz      short loc_18000665B
0x180006643  mov     rcx, [rcx+10h]
0x180006647  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000664e  mov     edx, 0E6h
0x180006653  mov     r9d, ebx
0x180006656  call    WPP_SF_d
0x18000665b  mov     eax, ebx
0x18000665d  add     rsp, 20h
0x180006661  pop     rbx
0x180006662  retn
```
