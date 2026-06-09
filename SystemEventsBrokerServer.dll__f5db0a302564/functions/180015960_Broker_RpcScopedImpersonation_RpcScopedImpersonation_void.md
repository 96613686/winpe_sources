# Broker::RpcScopedImpersonation::~RpcScopedImpersonation(void)

- ea: `0x180015960`
- end: `0x18001599d`
- name: `??1RpcScopedImpersonation@Broker@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(Broker::RpcScopedImpersonation *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023620`
- `0x180023640`
- `0x180023b60`
- `0x180024220`
- `0x1800245f0`

## callees

- `0x180005a50`
- `0x180015960`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180015964`
- `RPCRT4!RpcRevertToSelf` at `0x180015964`

## pseudocode

```c
void __fastcall Broker::RpcScopedImpersonation::~RpcScopedImpersonation(Broker::RpcScopedImpersonation *this)
{
  if ( RpcRevertToSelf() && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids);
}

```

## disassembly

```asm
0x180015960  sub     rsp, 28h
0x180015964  call    cs:__imp_RpcRevertToSelf
0x18001596a  test    eax, eax
0x18001596c  jnz     short loc_180015973
0x18001596e  add     rsp, 28h
0x180015972  retn
0x180015973  mov     rcx, cs:WPP_GLOBAL_Control
0x18001597a  test    byte ptr [rcx+1Ch], 8
0x18001597e  jz      short loc_18001596E
0x180015980  cmp     byte ptr [rcx+19h], 2
0x180015984  jb      short loc_18001596E
0x180015986  mov     rcx, [rcx+10h]
0x18001598a  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180015991  mov     edx, 0Bh
0x180015996  call    WPP_SF_
0x18001599b  jmp     short loc_18001596E
```
