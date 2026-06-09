# SystemEventsBrokerTerminate(void)

- ea: `0x18001e05c`
- end: `0x18001e0d1`
- name: `?SystemEventsBrokerTerminate@@YAXXZ`
- size: `117`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001a830`
- `0x18001db70`
- `0x18001df48`

## callees

- `0x180005a50`
- `0x180018a08`
- `0x18001e05c`
- `0x18001f1c0`
- `0x180022170`

## pseudocode

```c
void SystemEventsBrokerTerminate(void)
{
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d34cd5f9e0b33b2ffc5d7ce5dd7036bf_Traceguids);
  std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::reset(&qword_180036E98);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  std::shared_ptr<Broker::SebBroker>::reset();
  TlgUnregisterAggregateProvider(&dword_180035050);
}

```

## disassembly

```asm
0x18001e05c  sub     rsp, 28h
0x18001e060  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e067  test    byte ptr [rcx+1Ch], 1
0x18001e06b  jz      short loc_18001E088
0x18001e06d  cmp     byte ptr [rcx+19h], 4
0x18001e071  jb      short loc_18001E088
0x18001e073  mov     rcx, [rcx+10h]
0x18001e077  lea     r8, WPP_d34cd5f9e0b33b2ffc5d7ce5dd7036bf_Traceguids
0x18001e07e  mov     edx, 0Fh
0x18001e083  call    WPP_SF_
0x18001e088  lea     rcx, qword_180036E98
0x18001e08f  call    ?reset@?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAXXZ; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::reset(void)
0x18001e094  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e09b  test    byte ptr [rcx+1Ch], 1
0x18001e09f  jz      short loc_18001E0BC
0x18001e0a1  cmp     byte ptr [rcx+19h], 4
0x18001e0a5  jb      short loc_18001E0BC
0x18001e0a7  mov     rcx, [rcx+10h]
0x18001e0ab  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001e0b2  mov     edx, 0Ah
0x18001e0b7  call    WPP_SF_
0x18001e0bc  call    ?reset@?$shared_ptr@VSebBroker@Broker@@@std@@QEAAXXZ; std::shared_ptr<Broker::SebBroker>::reset(void)
0x18001e0c1  lea     rcx, dword_180035050
0x18001e0c8  add     rsp, 28h
0x18001e0cc  jmp     TlgUnregisterAggregateProvider
```
