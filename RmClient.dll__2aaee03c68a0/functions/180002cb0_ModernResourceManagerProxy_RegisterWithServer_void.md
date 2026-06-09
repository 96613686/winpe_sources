# ModernResourceManagerProxy::RegisterWithServer(void)

- ea: `0x180002cb0`
- end: `0x180002e05`
- name: `?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(ModernResourceManagerProxy *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800010a4`
- `0x180001f68`
- `0x180001ff0`
- `0x180002320`
- `0x180002860`

## callees

- `0x180002cb0`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180002d03`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180002dae`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180002d03`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180002dae`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180002dd2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180002de8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180002dd2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180002de8`
- `RPCRT4!NdrClientCall3` at `0x180002d48`
- `RPCRT4!NdrClientCall3` at `0x180002d48`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001b06e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001b06e`

## pseudocode

```c
__int64 __fastcall ModernResourceManagerProxy::RegisterWithServer(ModernResourceManagerProxy *this)
{
  _QWORD *v2; // rsi
  int v3; // eax
  int Pointer; // ebx
  int v6; // [rsp+40h] [rbp-28h]

  v2 = (_QWORD *)((char *)this + 56);
  if ( *((_QWORD *)this + 7) )
    return 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_18001D000,
                            0,
                            0,
                            *((_QWORD *)this + 2),
                            (char *)this + 40,
                            (char *)this + 48).Pointer;
  if ( Pointer >= 0 )
  {
    v3 = RtlSubscribeWnfStateChangeNotification(
           v2,
           *((_QWORD *)this + 5),
           0,
           ModernResourceManagerProxy::CommitMemoryLevelChangeCallback,
           this,
           0,
           0,
           0,
           Pointer);
    if ( v3 >= 0 )
    {
      v3 = RtlSubscribeWnfStateChangeNotification(
             (char *)this + 64,
             *((_QWORD *)this + 6),
             0,
             ModernResourceManagerProxy::CommitMemoryLimitChangeCallback,
             this,
             0,
             0,
             0,
             v6);
      if ( v3 >= 0 )
        return 0;
    }
    Pointer = v3 | 0x10000000;
  }
  if ( *v2 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *v2 = 0;
  }
  if ( *((_QWORD *)this + 8) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 8) = 0;
  }
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002cb0  mov     [rsp+arg_0], rcx
0x180002cb5  push    rbx
0x180002cb6  push    rsi
0x180002cb7  push    rdi
0x180002cb8  sub     rsp, 50h
0x180002cbc  mov     rdi, rcx
0x180002cbf  lea     rsi, [rcx+38h]
0x180002cc3  mov     [rsp+68h+arg_10], rsi
0x180002ccb  cmp     qword ptr [rsi], 0
0x180002ccf  jz      short loc_180002D1D
0x180002cd1  jmp     short loc_180002D11
0x180002cd3  lea     rcx, [rdi+40h]
0x180002cd7  mov     [rsp+68h+var_30], 0
0x180002cdf  mov     [rsp+68h+var_38], 0
0x180002ce7  mov     [rsp+68h+var_40], 0
0x180002cf0  mov     [rsp+68h+var_48], rdi
0x180002cf5  lea     r9, ?CommitMemoryLimitChangeCallback@ModernResourceManagerProxy@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ModernResourceManagerProxy::CommitMemoryLimitChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180002cfc  xor     r8d, r8d
0x180002cff  mov     rdx, [rdi+30h]
0x180002d03  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180002d09  test    eax, eax
0x180002d0b  js      loc_180002DBC
0x180002d11  xor     ebx, ebx
0x180002d13  mov     eax, ebx
0x180002d15  add     rsp, 50h
0x180002d19  pop     rdi
0x180002d1a  pop     rsi
0x180002d1b  pop     rbx
0x180002d1c  retn
0x180002d1d  mov     [rsp+68h+arg_8], 0
0x180002d26  lea     rax, [rcx+30h]
0x180002d2a  add     rcx, 28h ; '('
0x180002d2e  mov     [rsp+68h+var_40], rax
0x180002d33  mov     [rsp+68h+var_48], rcx
0x180002d38  mov     r9, [rdi+10h]
0x180002d3c  xor     r8d, r8d; pReturnValue
0x180002d3f  xor     edx, edx; nProcNum
0x180002d41  lea     rcx, stru_18001D000; pProxyInfo
0x180002d48  call    cs:__imp_NdrClientCall3
0x180002d4e  mov     rbx, rax
0x180002d51  mov     [rsp+68h+arg_8], rax
0x180002d56  mov     [rsp+68h+var_28], eax
0x180002d5a  jmp     short loc_180002D7B
0x180002d5c  test    eax, eax
0x180002d5e  jle     short loc_180002D68
0x180002d60  movzx   eax, ax
0x180002d63  or      eax, 80070000h
0x180002d68  mov     ebx, eax
0x180002d6a  mov     [rsp+68h+var_28], eax
0x180002d6e  mov     rdi, [rsp+68h+arg_0]
0x180002d73  mov     rsi, [rsp+68h+arg_10]
0x180002d7b  test    ebx, ebx
0x180002d7d  js      short loc_180002DCA
0x180002d7f  mov     [rsp+68h+var_30], 0
0x180002d87  mov     [rsp+68h+var_38], 0
0x180002d8f  mov     [rsp+68h+var_40], 0
0x180002d98  mov     [rsp+68h+var_48], rdi
0x180002d9d  lea     r9, ?CommitMemoryLevelChangeCallback@ModernResourceManagerProxy@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ModernResourceManagerProxy::CommitMemoryLevelChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180002da4  xor     r8d, r8d
0x180002da7  mov     rdx, [rdi+28h]
0x180002dab  mov     rcx, rsi
0x180002dae  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180002db4  test    eax, eax
0x180002db6  jns     loc_180002CD3
0x180002dbc  bts     eax, 1Ch
0x180002dc0  mov     ebx, eax
0x180002dc2  test    eax, eax
0x180002dc4  jns     loc_180002D13
0x180002dca  mov     rcx, [rsi]
0x180002dcd  test    rcx, rcx
0x180002dd0  jz      short loc_180002DDF
0x180002dd2  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180002dd8  mov     qword ptr [rsi], 0
0x180002ddf  mov     rcx, [rdi+40h]
0x180002de3  test    rcx, rcx
0x180002de6  jz      short loc_180002DF6
0x180002de8  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180002dee  mov     qword ptr [rdi+40h], 0
0x180002df6  xor     eax, eax
0x180002df8  mov     [rdi+28h], rax
0x180002dfc  mov     [rdi+30h], rax
0x180002e00  jmp     loc_180002D13
0x18001b060  push    rbp
0x18001b062  sub     rsp, 40h
0x18001b066  mov     rbp, rdx
0x18001b069  mov     rcx, [rcx]
0x18001b06c  mov     ecx, [rcx]; ExceptionCode
0x18001b06e  call    cs:__imp_I_RpcExceptionFilter
0x18001b074  nop
0x18001b075  add     rsp, 40h
0x18001b079  pop     rbp
0x18001b07a  retn
```
