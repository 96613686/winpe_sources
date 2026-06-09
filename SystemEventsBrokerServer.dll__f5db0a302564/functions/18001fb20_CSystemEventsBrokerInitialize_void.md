# CSystemEventsBrokerInitialize(void)

- ea: `0x18001fb20`
- end: `0x18001fc58`
- name: `?CSystemEventsBrokerInitialize@@YAKXZ`
- size: `312`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a830`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x180017120`
- `0x18001c4d8`
- `0x18001fa54`
- `0x18001fb20`
- `0x18001fc60`
- `0x180020bac`

## pseudocode

```c
__int64 CSystemEventsBrokerInitialize(void)
{
  __int64 v0; // rdx
  __int64 *v1; // rax
  unsigned int v2; // ebx
  __int64 result; // rax
  int v4; // [rsp+20h] [rbp-78h]
  int v5; // [rsp+28h] [rbp-70h]
  int v6; // [rsp+30h] [rbp-68h]
  __int64 v7; // [rsp+50h] [rbp-48h] BYREF
  std::_Ref_count_base *v8; // [rsp+58h] [rbp-40h]
  void **v9; // [rsp+60h] [rbp-38h] BYREF
  _DWORD v10[12]; // [rsp+68h] [rbp-30h] BYREF
  unsigned int v11; // [rsp+A0h] [rbp+8h] BYREF
  int (*v12)(void *, void *); // [rsp+A8h] [rbp+10h] BYREF
  struct _GUID *v13; // [rsp+B0h] [rbp+18h] BYREF
  struct _GUID *v14; // [rsp+B8h] [rbp+20h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    CBroker::SebBroker::CreateInstance();
    v12 = 0;
    v11 = -1;
    v13 = 0;
    v14 = 0;
    v1 = std::make_shared<Broker::RpcServerRegistration,void * &,std::nullptr_t,std::nullptr_t,unsigned short const (&)[15],unsigned short const (&)[8],unsigned short const (&)[15],unsigned long,std::nullptr_t>(
           &v7,
           v0,
           &v14,
           &v13,
           v4,
           v5,
           v6,
           &v11,
           &v12);
    std::shared_ptr<CBroker::SebBroker>::operator=(&qword_180036EB8, v1);
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v11 = 14;
      v2 = v11;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001FC13);
      goto LABEL_13;
    }
    if ( __eh34_catch_type(0, &Broker::BILayer::Failure `RTTI Type Descriptor', 0) )
    {
      v11 = 1359;
      v2 = v11;
      __eh34_try_continuation(0, &Broker::BILayer::Failure `RTTI Type Descriptor', &loc_18001FC1C);
LABEL_13:
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
      CSystemEventsBrokerTerminate();
LABEL_7:
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
      result = v2;
    }
    if ( __eh34_catch_type(0, &Broker::Win32Error `RTTI Type Descriptor', (Broker::Win32Error *)&v9) )
    {
      v11 = v10[6];
      v9 = &std::exception::`vftable';
      o___std_exception_destroy_0(v10);
      __eh34_try_continuation(0, &Broker::Win32Error `RTTI Type Descriptor', &loc_18001FC1E);
      v2 = v11;
      if ( v11 )
        goto LABEL_13;
    }
  }
  v2 = CBroker::SebPublisher::CSebPublishRpcServerInit();
  goto LABEL_7;
}

```

## disassembly

```asm
0x18001fb20  push    rbx
0x18001fb22  sub     rsp, 90h
0x18001fb29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb30  test    byte ptr [rcx+1Ch], 8
0x18001fb34  jz      short loc_18001FB52
0x18001fb36  cmp     byte ptr [rcx+19h], 4
0x18001fb3a  jb      short loc_18001FB52
0x18001fb3c  mov     edx, 27h ; '''
0x18001fb41  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18001fb48  mov     rcx, [rcx+10h]
0x18001fb4c  call    WPP_SF_
0x18001fb51  nop
0x18001fb52  call    ?CreateInstance@SebBroker@CBroker@@SAXXZ; CBroker::SebBroker::CreateInstance(void)
0x18001fb57  mov     [rsp+98h+arg_8], 0
0x18001fb63  mov     [rsp+98h+arg_0], 0FFFFFFFFh
0x18001fb6e  mov     [rsp+98h+arg_10], 0
0x18001fb7a  mov     [rsp+98h+arg_18], 0
0x18001fb86  lea     rax, [rsp+98h+arg_8]
0x18001fb8e  mov     [rsp+98h+var_58], rax
0x18001fb93  lea     rax, [rsp+98h+arg_0]
0x18001fb9b  mov     [rsp+98h+var_60], rax
0x18001fba0  lea     r9, [rsp+98h+arg_10]
0x18001fba8  lea     r8, [rsp+98h+arg_18]
0x18001fbb0  lea     rcx, [rsp+98h+var_48]
0x18001fbb5  call    ??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0P@$$CBGAEAY07$$CBGAEAY0P@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0P@$$CBGAEAY07$$CBG2$$QEAK1@Z
0x18001fbba  mov     rdx, rax
0x18001fbbd  lea     rcx, qword_180036EB8
0x18001fbc4  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x18001fbc9  mov     rcx, [rsp+98h+var_40]; this
0x18001fbce  test    rcx, rcx
0x18001fbd1  jz      short loc_18001FBD9
0x18001fbd3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001fbd8  nop
0x18001fbd9  call    ?CSebPublishRpcServerInit@SebPublisher@CBroker@@SAJXZ; CBroker::SebPublisher::CSebPublishRpcServerInit(void)
0x18001fbde  mov     ebx, eax
0x18001fbe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbe7  test    byte ptr [rcx+1Ch], 8
0x18001fbeb  jz      short loc_18001FC08
0x18001fbed  cmp     byte ptr [rcx+19h], 4
0x18001fbf1  jb      short loc_18001FC08
0x18001fbf3  mov     edx, 29h ; ')'
0x18001fbf8  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18001fbff  mov     rcx, [rcx+10h]
0x18001fc03  call    WPP_SF_
0x18001fc08  mov     eax, ebx
0x18001fc0a  add     rsp, 90h
0x18001fc11  pop     rbx
0x18001fc12  retn
0x18001fc13  mov     ebx, [rsp+98h+arg_0]
0x18001fc1a  jmp     short loc_18001FC29
0x18001fc1c  jmp     short loc_18001FC13
0x18001fc1e  mov     ebx, [rsp+98h+arg_0]
0x18001fc25  test    ebx, ebx
0x18001fc27  jz      short loc_18001FBD9
0x18001fc29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc30  test    byte ptr [rcx+1Ch], 8
0x18001fc34  jz      short loc_18001FC51
0x18001fc36  cmp     byte ptr [rcx+19h], 2
0x18001fc3a  jb      short loc_18001FC51
0x18001fc3c  mov     edx, 28h ; '('
0x18001fc41  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18001fc48  mov     rcx, [rcx+10h]
0x18001fc4c  call    WPP_SF_
0x18001fc51  call    ?CSystemEventsBrokerTerminate@@YAXXZ; CSystemEventsBrokerTerminate(void)
0x18001fc56  jmp     short loc_18001FBE0
```
