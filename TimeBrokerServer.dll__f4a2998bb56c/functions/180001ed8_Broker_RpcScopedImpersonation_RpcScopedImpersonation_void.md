# Broker::RpcScopedImpersonation::~RpcScopedImpersonation(void)

- ea: `0x180001ed8`
- end: `0x180001f17`
- name: `??1RpcScopedImpersonation@Broker@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(Broker::RpcScopedImpersonation *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a1b0`

## callees

- `0x180001ed8`
- `0x180003840`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180001edc`
- `RPCRT4!RpcRevertToSelf` at `0x180001edc`

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
0x180001ed8  sub     rsp, 28h
0x180001edc  call    cs:__imp_RpcRevertToSelf
0x180001ee2  test    eax, eax
0x180001ee4  jnz     short loc_180001EEB
0x180001ee6  add     rsp, 28h
0x180001eea  retn
0x180001eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ef2  test    byte ptr [rcx+1Ch], 8
0x180001ef6  jz      short loc_180001EE6
0x180001ef8  cmp     byte ptr [rcx+19h], 2
0x180001efc  jb      short loc_180001EE6
0x180001efe  mov     rcx, [rcx+10h]
0x180001f02  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180001f09  mov     edx, 0Bh
0x180001f0e  add     rsp, 28h
0x180001f12  jmp     WPP_SF_
```
