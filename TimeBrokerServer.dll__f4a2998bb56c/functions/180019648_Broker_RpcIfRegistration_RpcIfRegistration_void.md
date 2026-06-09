# Broker::RpcIfRegistration::~RpcIfRegistration(void)

- ea: `0x180019648`
- end: `0x180019693`
- name: `??1RpcIfRegistration@Broker@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(Broker::RpcIfRegistration *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001969c`

## callees

- `0x180003800`
- `0x180019648`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x180019659`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180019659`

## pseudocode

```c
void __fastcall Broker::RpcIfRegistration::~RpcIfRegistration(Broker::RpcIfRegistration *this)
{
  unsigned int v1; // eax

  v1 = RpcServerUnregisterIfEx(*(RPC_IF_HANDLE *)this, (UUID *)((char *)this + 8), 1);
  if ( v1 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, v1);
}

```

## disassembly

```asm
0x180019648  sub     rsp, 28h
0x18001964c  lea     rdx, [rcx+8]; MgrTypeUuid
0x180019650  mov     r8d, 1; RundownContextHandles
0x180019656  mov     rcx, [rcx]; IfSpec
0x180019659  call    cs:__imp_RpcServerUnregisterIfEx
0x18001965f  test    eax, eax
0x180019661  jz      short loc_18001968E
0x180019663  mov     rcx, cs:WPP_GLOBAL_Control
0x18001966a  test    byte ptr [rcx+1Ch], 8
0x18001966e  jz      short loc_18001968E
0x180019670  cmp     byte ptr [rcx+19h], 2
0x180019674  jb      short loc_18001968E
0x180019676  mov     rcx, [rcx+10h]
0x18001967a  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180019681  mov     edx, 0Dh
0x180019686  mov     r9d, eax
0x180019689  call    WPP_SF_d
0x18001968e  add     rsp, 28h
0x180019692  retn
```
