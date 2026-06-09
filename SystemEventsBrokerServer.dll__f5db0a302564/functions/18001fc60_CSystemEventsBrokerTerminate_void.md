# CSystemEventsBrokerTerminate(void)

- ea: `0x18001fc60`
- end: `0x18001fd45`
- name: `?CSystemEventsBrokerTerminate@@YAXXZ`
- size: `229`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a830`
- `0x18001db70`
- `0x18001fb20`

## callees

- `0x180005a50`
- `0x1800186b8`
- `0x180018a08`
- `0x18001fc60`
- `0x180020910`
- `0x180022170`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x18001fca5`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18001fca5`

## pseudocode

```c
void CSystemEventsBrokerTerminate(void)
{
  _QWORD *v0; // rcx

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  CBroker::SebPublisher::DeleteEventsState();
  byte_180036E80 = 0;
  RpcServerUnregisterIfEx(qword_1800287D0, 0, 1);
  std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::reset(&qword_180036EB8);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  std::shared_ptr<CBroker::SebBroker>::reset();
  TlgUnregisterAggregateProvider(&qword_180035088);
  v0 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v0 + 28) & 8) != 0 && *((_BYTE *)v0 + 25) >= 4u )
    WPP_SF_(v0[2], 38, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
}

```

## disassembly

```asm
0x18001fc60  sub     rsp, 28h
0x18001fc64  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc6b  test    byte ptr [rcx+1Ch], 8
0x18001fc6f  jz      short loc_18001FC8C
0x18001fc71  cmp     byte ptr [rcx+19h], 4
0x18001fc75  jb      short loc_18001FC8C
0x18001fc77  mov     rcx, [rcx+10h]
0x18001fc7b  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18001fc82  mov     edx, 25h ; '%'
0x18001fc87  call    WPP_SF_
0x18001fc8c  call    ?DeleteEventsState@SebPublisher@CBroker@@CAXXZ; CBroker::SebPublisher::DeleteEventsState(void)
0x18001fc91  xor     edx, edx; MgrTypeUuid
0x18001fc93  mov     cs:byte_180036E80, 0
0x18001fc9a  lea     rcx, qword_1800287D0; IfSpec
0x18001fca1  lea     r8d, [rdx+1]; RundownContextHandles
0x18001fca5  call    cs:__imp_RpcServerUnregisterIfEx
0x18001fcab  lea     rcx, qword_180036EB8
0x18001fcb2  call    ?reset@?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAAXXZ; std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>::reset(void)
0x18001fcb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcbe  test    byte ptr [rcx+1Ch], 1
0x18001fcc2  jz      short loc_18001FCDF
0x18001fcc4  cmp     byte ptr [rcx+19h], 4
0x18001fcc8  jb      short loc_18001FCDF
0x18001fcca  mov     rcx, [rcx+10h]
0x18001fcce  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001fcd5  mov     edx, 0Ah
0x18001fcda  call    WPP_SF_
0x18001fcdf  call    ?reset@?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAXXZ; std::shared_ptr<CBroker::SebBroker>::reset(void)
0x18001fce4  lea     rcx, qword_180035088
0x18001fceb  call    TlgUnregisterAggregateProvider
0x18001fcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcf7  test    byte ptr [rcx+1Ch], 1
0x18001fcfb  jz      short loc_18001FD1F
0x18001fcfd  cmp     byte ptr [rcx+19h], 4
0x18001fd01  jb      short loc_18001FD1F
0x18001fd03  mov     rcx, [rcx+10h]
0x18001fd07  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001fd0e  mov     edx, 0Bh
0x18001fd13  call    WPP_SF_
0x18001fd18  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd1f  test    byte ptr [rcx+1Ch], 8
0x18001fd23  jz      short loc_18001FD40
0x18001fd25  cmp     byte ptr [rcx+19h], 4
0x18001fd29  jb      short loc_18001FD40
0x18001fd2b  mov     rcx, [rcx+10h]
0x18001fd2f  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18001fd36  mov     edx, 26h ; '&'
0x18001fd3b  call    WPP_SF_
0x18001fd40  add     rsp, 28h
0x18001fd44  retn
```
