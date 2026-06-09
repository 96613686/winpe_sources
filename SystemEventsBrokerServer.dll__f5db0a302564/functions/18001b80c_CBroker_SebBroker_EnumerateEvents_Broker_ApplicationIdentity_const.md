# CBroker::SebBroker::EnumerateEvents(Broker::ApplicationIdentity const &)

- ea: `0x18001b80c`
- end: `0x18001b90b`
- name: `?EnumerateEvents@SebBroker@CBroker@@QEAA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEBUApplicationIdentity@Broker@@@Z`
- size: `255`
- prototype: `_QWORD *__fastcall(struct _RTL_SRWLOCK *, _QWORD *, PSID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b5d0`

## callees

- `0x18000b168`
- `0x180013820`
- `0x180013920`
- `0x1800171bc`
- `0x18001b80c`
- `0x180020220`

## pseudocode

```c
_QWORD *__fastcall CBroker::SebBroker::EnumerateEvents(struct _RTL_SRWLOCK *a1, _QWORD *a2, PSID *a3)
{
  _BYTE v7[24]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v8[4]; // [rsp+50h] [rbp-28h] BYREF

  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v7, a1 + 1, 1);
  std::vector<_GUID>::vector<_GUID>(a2);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), *a3);
  v8[0] = a1;
  v8[1] = a3;
  v8[2] = a2;
  Broker::BrokerEventTable_CBroker::SebEvent_::ForEach__lambda_1f13a272e36841c663cc19eb81071f3b___(&a1[2], v8);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), *a3);
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v7);
  return a2;
}

```

## disassembly

```asm
0x18001b80c  mov     rax, rsp
0x18001b80f  mov     [rax+8], rbx
0x18001b813  mov     [rax+18h], rsi
0x18001b817  mov     [rax+10h], rdx
0x18001b81b  push    rdi
0x18001b81c  sub     rsp, 70h
0x18001b820  mov     rbx, r8
0x18001b823  mov     rdi, rdx
0x18001b826  mov     rsi, rcx
0x18001b829  mov     dword ptr [rax-48h], 0
0x18001b830  lea     rdx, [rcx+8]; struct _RTL_SRWLOCK *
0x18001b834  mov     r8b, 1; bool
0x18001b837  lea     rcx, [rax-40h]; this
0x18001b83b  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001b840  nop
0x18001b841  mov     rcx, rdi
0x18001b844  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001b849  mov     [rsp+78h+var_48], 1
0x18001b851  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b858  test    byte ptr [rcx+1Ch], 1
0x18001b85c  jz      short loc_18001B88F
0x18001b85e  cmp     byte ptr [rcx+19h], 4
0x18001b862  jb      short loc_18001B88F
0x18001b864  mov     rax, [rbx]
0x18001b867  lea     r9, [rbx+38h]
0x18001b86b  cmp     qword ptr [r9+18h], 7
0x18001b870  jbe     short loc_18001B875
0x18001b872  mov     r9, [r9]
0x18001b875  mov     edx, 25h ; '%'
0x18001b87a  mov     [rsp+78h+pSid], rax; pSid
0x18001b87f  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001b886  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b88a  call    WPP_SF_S_sid_
0x18001b88f  mov     [rsp+78h+var_28], rsi
0x18001b894  mov     [rsp+78h+var_20], rbx
0x18001b899  mov     [rsp+78h+var_18], rdi
0x18001b89e  lea     rcx, [rsi+10h]
0x18001b8a2  lea     rdx, [rsp+78h+var_28]
0x18001b8a7  call    Broker__BrokerEventTable_CBroker__SebEvent___ForEach__lambda_1f13a272e36841c663cc19eb81071f3b___
0x18001b8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8b3  test    byte ptr [rcx+1Ch], 1
0x18001b8b7  jz      short loc_18001B8EB
0x18001b8b9  cmp     byte ptr [rcx+19h], 4
0x18001b8bd  jb      short loc_18001B8EB
0x18001b8bf  mov     rax, [rbx]
0x18001b8c2  lea     r9, [rbx+38h]
0x18001b8c6  cmp     qword ptr [r9+18h], 7
0x18001b8cb  jbe     short loc_18001B8D0
0x18001b8cd  mov     r9, [r9]
0x18001b8d0  mov     edx, 26h ; '&'
0x18001b8d5  mov     [rsp+78h+pSid], rax; pSid
0x18001b8da  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001b8e1  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b8e5  call    WPP_SF_S_sid_
0x18001b8ea  nop
0x18001b8eb  lea     rcx, [rsp+78h+var_40]; this
0x18001b8f0  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18001b8f5  mov     rax, rdi
0x18001b8f8  lea     r11, [rsp+78h+var_8]
0x18001b8fd  mov     rbx, [r11+10h]
0x18001b901  mov     rsi, [r11+20h]
0x18001b905  mov     rsp, r11
0x18001b908  pop     rdi
0x18001b909  retn
```
