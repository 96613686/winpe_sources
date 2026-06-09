# RemoteEpmpServerSecurityCallback

- ea: `0x180004f50`
- end: `0x180004f8c`
- name: `RemoteEpmpServerSecurityCallback`
- size: `60`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004f50`
- `0x180006fa8`

## import_xrefs

- `RPCRT4!I_RpcServerCheckClientRestriction` at `0x180004f67`
- `RPCRT4!I_RpcServerCheckClientRestriction` at `0x180004f67`

## pseudocode

```c
__int64 __fastcall RemoteEpmpServerSecurityCallback(__int64 a1, void *a2)
{
  __int64 result; // rax

  if ( g_fOpenEpmpInterface || !I_RpcServerCheckClientRestriction(a2) )
    return 0;
  result = InitializeAllowAnonymousEPMStateIfNecessary();
  if ( !(_DWORD)result )
    return EPMAllowAnonymous != 3 ? 5 : 0;
  return result;
}

```

## disassembly

```asm
0x180004f50  sub     rsp, 28h
0x180004f54  cmp     cs:g_fOpenEpmpInterface, 0
0x180004f5b  jz      short loc_180004F64
0x180004f5d  xor     eax, eax
0x180004f5f  add     rsp, 28h
0x180004f63  retn
0x180004f64  mov     rcx, rdx; Context
0x180004f67  call    cs:__imp_I_RpcServerCheckClientRestriction
0x180004f6d  test    eax, eax
0x180004f6f  jz      short loc_180004F5D
0x180004f71  call    InitializeAllowAnonymousEPMStateIfNecessary
0x180004f76  test    eax, eax
0x180004f78  jnz     short loc_180004F5F
0x180004f7a  mov     eax, cs:EPMAllowAnonymous
0x180004f80  sub     eax, 3
0x180004f83  neg     eax
0x180004f85  sbb     eax, eax
0x180004f87  and     eax, 5
0x180004f8a  jmp     short loc_180004F5F
```
