# TimeBrokerInitialize(void)

- ea: `0x180011ea8`
- end: `0x180012022`
- name: `?TimeBrokerInitialize@@YAKXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013ca0`

## callees

- `0x180004e18`
- `0x180005b30`
- `0x180011ea8`
- `0x180012028`
- `0x1800120f4`
- `0x180014224`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011f7d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011f7d`

## string_xrefs

- `0x180011f6f`: `SYSTEM\CurrentControlSet\Services\TimeBrokerSvc\Parameters`

## pseudocode

```c
__int64 TimeBrokerInitialize(void)
{
  int v0; // edx
  __int64 v1; // rax
  int v2; // edx
  int v3; // eax
  __int64 v4; // rax
  int pdwType; // [rsp+20h] [rbp-88h]
  int pvData; // [rsp+28h] [rbp-80h]
  int pcbData; // [rsp+30h] [rbp-78h]
  __int64 v9; // [rsp+50h] [rbp-58h] BYREF
  __int64 v10; // [rsp+58h] [rbp-50h] BYREF
  __int64 v11; // [rsp+60h] [rbp-48h] BYREF
  char v12; // [rsp+68h] [rbp-40h] BYREF
  std::_Ref_count_base *v13; // [rsp+70h] [rbp-38h]
  void **v14; // [rsp+78h] [rbp-30h] BYREF
  _DWORD v15[10]; // [rsp+80h] [rbp-28h] BYREF
  unsigned int v16; // [rsp+B0h] [rbp+8h]
  int v17; // [rsp+B8h] [rbp+10h] BYREF
  int v18; // [rsp+C0h] [rbp+18h] BYREF
  DWORD v19; // [rsp+C8h] [rbp+20h] BYREF

  v16 = 0;
  v17 = 0;
  v19 = 4;
  try
  {
    Broker::TimeBroker::CreateInstance();
    v9 = 0;
    v18 = -1;
    v10 = 0;
    v11 = 0;
    v1 = std::make_shared<Broker::RpcServerRegistration,void * &,std::nullptr_t,std::nullptr_t,unsigned short const (&)[27],unsigned short const (&)[8],unsigned short const (&)[27],unsigned long,std::nullptr_t>(
           (unsigned int)&v12,
           v0,
           (unsigned int)&v11,
           (unsigned int)&v10);
    std::shared_ptr<Broker::SystemTimer>::operator=(&RpcServer, v1);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\TimeBrokerSvc\\Parameters",
           L"EnableUnsafeTestHook",
           0x18u,
           0,
           &v17,
           &v19) )
    {
      v3 = 0;
      v17 = 0;
    }
    else
    {
      v3 = v17;
    }
    if ( v3 )
    {
      v11 = 0;
      v18 = -1;
      v10 = 0;
      v9 = 0;
      v4 = std::make_shared<Broker::RpcServerRegistration,void * &,std::nullptr_t,std::nullptr_t,unsigned short const (&)[15],unsigned short const (&)[8],unsigned short const (&)[15],unsigned long,std::nullptr_t>(
             (unsigned int)&v12,
             v2,
             (unsigned int)&v9,
             (unsigned int)&v10,
             pdwType,
             pvData,
             pcbData,
             (__int64)&v18,
             (__int64)&v11);
      std::shared_ptr<Broker::SystemTimer>::operator=(&RpcServerTestHook, v4);
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
    }
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( Broker::BILayer::Failure )
  {
    return 1359;
  }
  catch ( Broker::Win32Error v14 )
  {
    v16 = v15[6];
    v14 = &std::exception::`vftable';
    o___std_exception_destroy_0(v15);
  }
  Broker::TimeBroker::CreateInstance();
}

```

## disassembly

```asm
0x180011ea8  mov     rax, rsp
0x180011eab  sub     rsp, 0A8h
0x180011eb2  mov     [rsp+0A8h+arg_0], 0
0x180011ebd  mov     dword ptr [rax+10h], 0
0x180011ec4  mov     dword ptr [rax+20h], 4
0x180011ecb  call    ?CreateInstance@TimeBroker@Broker@@SAXXZ; Broker::TimeBroker::CreateInstance(void)
0x180011ed0  mov     [rsp+0A8h+var_58], 0
0x180011ed9  mov     [rsp+0A8h+arg_10], 0FFFFFFFFh
0x180011ee4  mov     [rsp+0A8h+var_50], 0
0x180011eed  mov     [rsp+0A8h+var_48], 0
0x180011ef6  lea     rax, [rsp+0A8h+var_58]
0x180011efb  mov     [rsp+0A8h+var_68], rax
0x180011f00  lea     rax, [rsp+0A8h+arg_10]
0x180011f08  mov     [rsp+0A8h+var_70], rax
0x180011f0d  lea     r9, [rsp+0A8h+var_50]
0x180011f12  lea     r8, [rsp+0A8h+var_48]
0x180011f17  lea     rcx, [rsp+0A8h+var_40]
0x180011f1c  call    ??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0BL@$$CBGAEAY07$$CBGAEAY0BL@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0BL@$$CBGAEAY07$$CBG2$$QEAK1@Z
0x180011f21  mov     rdx, rax
0x180011f24  lea     rcx, ?RpcServer@@3V?$shared_ptr@VRpcServerRegistration@Broker@@@std@@A; std::shared_ptr<Broker::RpcServerRegistration> RpcServer
0x180011f2b  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x180011f30  mov     rcx, [rsp+0A8h+var_38]; this
0x180011f35  test    rcx, rcx
0x180011f38  jz      short loc_180011F3F
0x180011f3a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011f3f  lea     rax, [rsp+0A8h+arg_18]
0x180011f47  mov     [rsp+0A8h+pcbData], rax; pcbData
0x180011f4c  lea     rax, [rsp+0A8h+arg_8]
0x180011f54  mov     [rsp+0A8h+pvData], rax; pvData
0x180011f59  mov     [rsp+0A8h+pdwType], 0; pdwType
0x180011f62  mov     r9d, 18h; dwFlags
0x180011f68  lea     r8, aEnableunsafete; "EnableUnsafeTestHook"
0x180011f6f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ti"...
0x180011f76  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180011f7d  call    cs:__imp_RegGetValueW
0x180011f83  test    eax, eax
0x180011f85  jz      short loc_180011F92
0x180011f87  xor     eax, eax
0x180011f89  mov     [rsp+0A8h+arg_8], eax
0x180011f90  jmp     short loc_180011F99
0x180011f92  mov     eax, [rsp+0A8h+arg_8]
0x180011f99  test    eax, eax
0x180011f9b  jz      short loc_18001200D
0x180011f9d  mov     [rsp+0A8h+var_48], 0
0x180011fa6  mov     [rsp+0A8h+arg_10], 0FFFFFFFFh
0x180011fb1  mov     [rsp+0A8h+var_50], 0
0x180011fba  mov     [rsp+0A8h+var_58], 0
0x180011fc3  lea     rax, [rsp+0A8h+var_48]
0x180011fc8  mov     [rsp+0A8h+var_68], rax
0x180011fcd  lea     rax, [rsp+0A8h+arg_10]
0x180011fd5  mov     [rsp+0A8h+var_70], rax
0x180011fda  lea     r9, [rsp+0A8h+var_50]
0x180011fdf  lea     r8, [rsp+0A8h+var_58]
0x180011fe4  lea     rcx, [rsp+0A8h+var_40]
0x180011fe9  call    ??$make_shared@VRpcServerRegistration@Broker@@AEAPEAX$$T$$TAEAY0P@$$CBGAEAY07$$CBGAEAY0P@$$CBGK$$T@std@@YA?AV?$shared_ptr@VRpcServerRegistration@Broker@@@0@AEAPEAX$$QEA$$T1AEAY0P@$$CBGAEAY07$$CBG2$$QEAK1@Z
0x180011fee  mov     rdx, rax
0x180011ff1  lea     rcx, ?RpcServerTestHook@@3V?$shared_ptr@VRpcServerRegistration@Broker@@@std@@A; std::shared_ptr<Broker::RpcServerRegistration> RpcServerTestHook
0x180011ff8  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x180011ffd  mov     rcx, [rsp+0A8h+var_38]; this
0x180012002  test    rcx, rcx
0x180012005  jz      short loc_18001200D
0x180012007  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001200c  nop
0x18001200d  jmp     short loc_180012013
0x18001200f  jmp     short loc_180012013
0x180012011  jmp     short $+2
0x180012013  mov     eax, [rsp+0A8h+arg_0]
0x18001201a  add     rsp, 0A8h
0x180012021  retn
```
