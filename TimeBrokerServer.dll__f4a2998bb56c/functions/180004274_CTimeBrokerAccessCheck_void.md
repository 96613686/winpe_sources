# CTimeBrokerAccessCheck(void)

- ea: `0x180004274`
- end: `0x1800042b2`
- name: `?CTimeBrokerAccessCheck@@YAJXZ`
- size: `62`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003ac0`
- `0x180004be0`
- `0x1800149d0`

## callees

- `0x180003cac`
- `0x180004000`
- `0x180004218`
- `0x180004274`

## pseudocode

```c
__int64 CTimeBrokerAccessCheck(void)
{
  const unsigned __int16 *v0; // rdx
  Broker::Win32Error *v2; // [rsp+20h] [rbp-28h] BYREF
  HANDLE v3[4]; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v4; // [rsp+50h] [rbp+8h]

  v4 = 0;
  try
  {
    Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v3);
    Broker::RpcClientToken::AccessCheck(v3, v0);
    Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)v3);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( Broker::AccessDenied )
  {
    return 5;
  }
  catch ( Broker::Win32Error *v2 )
  {
    return *((unsigned int *)v2 + 8);
  }
  catch ( ... )
  {
    return 1359;
  }
  return v4;
}

```

## disassembly

```asm
0x180004274  sub     rsp, 48h
0x180004278  mov     [rsp+48h+arg_0], 0
0x180004280  lea     rcx, [rsp+48h+var_20]; this
0x180004285  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x18000428a  nop
0x18000428b  lea     rcx, [rsp+48h+var_20]; this
0x180004290  call    ?AccessCheck@RpcClientToken@Broker@@QEAAXPEBGK@Z; Broker::RpcClientToken::AccessCheck(ushort const *,ulong)
0x180004295  nop
0x180004296  lea     rcx, [rsp+48h+var_20]; this
0x18000429b  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x1800042a0  nop
0x1800042a1  jmp     short loc_1800042A9
0x1800042a3  jmp     short loc_1800042A9
0x1800042a5  jmp     short loc_1800042A9
0x1800042a7  jmp     short $+2
0x1800042a9  mov     eax, [rsp+48h+arg_0]
0x1800042ad  add     rsp, 48h
0x1800042b1  retn
```
