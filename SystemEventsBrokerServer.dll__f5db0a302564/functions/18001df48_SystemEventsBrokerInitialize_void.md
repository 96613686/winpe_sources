# SystemEventsBrokerInitialize(void)

- ea: `0x18001df48`
- end: `0x18001e054`
- name: `?SystemEventsBrokerInitialize@@YAKXZ`
- size: `268`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a830`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x1800076a0`
- `0x180017120`
- `0x18001c100`
- `0x18001ddf0`
- `0x18001df48`
- `0x18001e05c`

## pseudocode

```c
__int64 SystemEventsBrokerInitialize(void)
{
  unsigned int v0; // ebx
  unsigned __int16 *v1; // rcx
  __int64 v2; // rdx
  __int64 *v3; // rax
  int v5; // [rsp+20h] [rbp-78h]
  int v6; // [rsp+28h] [rbp-70h]
  int v7; // [rsp+30h] [rbp-68h]
  __int64 v8; // [rsp+50h] [rbp-48h] BYREF
  std::_Ref_count_base *v9; // [rsp+58h] [rbp-40h]
  void **v10; // [rsp+60h] [rbp-38h] BYREF
  _DWORD v11[12]; // [rsp+68h] [rbp-30h] BYREF
  unsigned int v12; // [rsp+A0h] [rbp+8h] BYREF
  int (*v13)(void *, void *); // [rsp+A8h] [rbp+10h] BYREF
  struct _GUID *v14; // [rsp+B0h] [rbp+18h] BYREF
  struct _GUID *v15; // [rsp+B8h] [rbp+20h] BYREF

  v0 = 0;
  v1 = (unsigned __int16 *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_d34cd5f9e0b33b2ffc5d7ce5dd7036bf_Traceguids);
  try
  {
    Broker::SebBroker::CreateInstance(v1);
    v13 = 0;
    v12 = -1;
    v14 = 0;
    v15 = 0;
    v3 = std::make_shared<Broker::RpcServerRegistration,void * &,std::nullptr_t,std::nullptr_t,unsigned short const (&)[27],unsigned short const (&)[8],unsigned short const (&)[27],unsigned long,std::nullptr_t>(
           &v8,
           v2,
           &v15,
           &v14,
           v5,
           v6,
           v7,
           &v12,
           &v13);
    std::shared_ptr<CBroker::SebBroker>::operator=(&qword_180036E98, v3);
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
  }
  catch ( std::bad_alloc )
  {
    v12 = 14;
    v0 = v12;
    goto LABEL_8;
  }
  catch ( Broker::BILayer::Failure )
  {
    v12 = 1359;
    v0 = v12;
    goto LABEL_8;
  }
  catch ( Broker::Win32Error v10 )
  {
    v12 = v11[6];
    v10 = &std::exception::`vftable';
    o___std_exception_destroy_0(v11);
    v0 = v12;
    if ( v12 )
    {
LABEL_8:
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d34cd5f9e0b33b2ffc5d7ce5dd7036bf_Traceguids, v0);
      SystemEventsBrokerTerminate();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001df48  push    rbx
0x18001df4a  sub     rsp, 90h
0x18001df51  xor     ebx, ebx
0x18001df53  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df5a  test    byte ptr [rcx+1Ch], 1
0x18001df5e  jz      short loc_18001DF7A
0x18001df60  cmp     byte ptr [rcx+19h], 4
0x18001df64  jb      short loc_18001DF7A
0x18001df66  lea     edx, [rbx+10h]
0x18001df69  lea     r8, WPP_d34cd5f9e0b33b2ffc5d7ce5dd7036bf_Traceguids
0x18001df70  mov     rcx, [rcx+10h]
0x18001df74  call    WPP_SF_
0x18001df79  nop
0x18001df7a  call    ?CreateInstance@SebBroker@Broker@@SAXPEAG@Z; Broker::SebBroker::CreateInstance(ushort *)
0x18001df7f  mov     [rsp+98h+arg_8], 0
0x18001df8b  mov     [rsp+98h+arg_0], 0FFFFFFFFh
0x18001df96  mov     [rsp+98h+arg_10], 0
0x18001dfa2  mov     [rsp+98h+arg_18], 0
0x18001dfae  lea     rax, [rsp+98h+arg_8]
0x18001dfb6  mov     [rsp+98h+var_58], rax
0x18001dfbb  lea     rax, [rsp+98h+arg_0]
0x18001dfc3  mov     [rsp+98h+var_60], rax
0x18001dfc8  lea     r9, [rsp+98h+arg_10]
0x18001dfd0  lea     r8, [rsp+98h+arg_18]
0x18001dfd8  lea     rcx, [rsp+98h+var_48]
0x18001dfdd  call    ??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0BL@$$CBGAEAY07$$CBGAEAY0BL@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0BL@$$CBGAEAY07$$CBG2$$QEAK1@Z
0x18001dfe2  mov     rdx, rax
0x18001dfe5  lea     rcx, qword_180036E98
0x18001dfec  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x18001dff1  mov     rcx, [rsp+98h+var_40]; this
0x18001dff6  test    rcx, rcx
0x18001dff9  jz      short loc_18001E001
0x18001dffb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e000  nop
0x18001e001  jmp     short loc_18001E049
0x18001e003  mov     ebx, [rsp+98h+arg_0]
0x18001e00a  jmp     short loc_18001E019
0x18001e00c  jmp     short loc_18001E003
0x18001e00e  mov     ebx, [rsp+98h+arg_0]
0x18001e015  test    ebx, ebx
0x18001e017  jz      short loc_18001E049
0x18001e019  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e020  test    byte ptr [rcx+1Ch], 1
0x18001e024  jz      short loc_18001E044
0x18001e026  cmp     byte ptr [rcx+19h], 2
0x18001e02a  jb      short loc_18001E044
0x18001e02c  mov     edx, 11h
0x18001e031  mov     r9d, ebx
0x18001e034  lea     r8, WPP_d34cd5f9e0b33b2ffc5d7ce5dd7036bf_Traceguids
0x18001e03b  mov     rcx, [rcx+10h]
0x18001e03f  call    WPP_SF_d
0x18001e044  call    ?SystemEventsBrokerTerminate@@YAXXZ; SystemEventsBrokerTerminate(void)
0x18001e049  mov     eax, ebx
0x18001e04b  add     rsp, 90h
0x18001e052  pop     rbx
0x18001e053  retn
```
