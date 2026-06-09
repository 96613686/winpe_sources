# UserService::CDPInitialize(void)

- ea: `0x18000e1d8`
- end: `0x18000e2c9`
- name: `?CDPInitialize@UserService@@AEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(UserService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d288`

## callees

- `0x180006494`
- `0x18000e1d8`
- `0x18000e978`
- `0x18001f54c`
- `0x180057438`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18000e2b9`
- `msvcp_win!_Mtx_unlock` at `0x18000e2b9`
- `cdp!CDPInitializeForService` at `0x18000e239`
- `cdp!CDPInitializeForService` at `0x18000e239`
- `cdp!CDPGetLogger` at `0x18000e277`
- `cdp!CDPGetLogger` at `0x18000e277`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18000e1e6`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18000e1e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserService::CDPInitialize(UserService *this)
{
  int IsRelayEnabled; // eax
  bool *v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r9
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned int v10; // ebx
  _QWORD v11[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+28h] BYREF
  int v13; // [rsp+70h] [rbp+30h] BYREF
  void *v14; // [rsp+78h] [rbp+38h]

  IsRelayEnabled = UseEdgeBrowserComponentsForProcess();
  if ( IsRelayEnabled < 0 )
  {
    v13 = 383;
LABEL_3:
    v12 = IsRelayEnabled;
    Log<long &,char const (&)[19],int>(
      v4,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      &v12,
      v5,
      &v13);
    return v12;
  }
  IsRelayEnabled = RelayPolicyHelper::GetIsRelayEnabled((UserService *)((char *)this + 232), v3);
  if ( IsRelayEnabled < 0 )
  {
    v13 = 385;
    goto LABEL_3;
  }
  IsRelayEnabled = CDPInitializeForService(2);
  if ( IsRelayEnabled < 0 )
  {
    v13 = 387;
    goto LABEL_3;
  }
  v14 = &g_loggerMutex;
  std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
  v11[0] = 0;
  v11[1] = &g_logger;
  v7 = CDPGetLogger(v11);
  cdp::detail::address_of<ICDPLogger>::~address_of<ICDPLogger>(v11);
  if ( v7 >= 0 )
  {
    v10 = 0;
  }
  else
  {
    v12 = v7;
    v13 = 390;
    Log<long &,char const (&)[19],int>(
      v8,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      &v12,
      v9,
      &v13);
    v10 = v12;
  }
  _Mtx_unlock((_Mtx_t)&g_loggerMutex);
  return v10;
}

```

## disassembly

```asm
0x18000e1d8  push    rbp
0x18000e1da  push    rbx
0x18000e1db  push    rdi
0x18000e1dc  mov     rbp, rsp
0x18000e1df  sub     rsp, 40h
0x18000e1e3  mov     rbx, rcx
0x18000e1e6  call    cs:__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ; UseEdgeBrowserComponentsForProcess(void)
0x18000e1ec  test    eax, eax
0x18000e1ee  jns     short loc_18000E21B
0x18000e1f0  mov     [rbp+arg_10], 17Fh
0x18000e1f7  mov     [rbp+arg_8], eax
0x18000e1fa  lea     rax, [rbp+arg_10]
0x18000e1fe  mov     [rsp+40h+var_20], rax
0x18000e203  lea     r8, [rbp+arg_8]
0x18000e207  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18000e20e  call    ??$Log@AEAJAEAY0BD@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BD@$$CBD$$QEAH@Z; Log<long &,char const (&)[19],int>(CDPLogLevel,char const *,long &,char const (&)[19],int &&)
0x18000e213  mov     eax, [rbp+arg_8]
0x18000e216  jmp     loc_18000E2C1
0x18000e21b  lea     rcx, [rbx+0E8h]; this
0x18000e222  call    ?GetIsRelayEnabled@RelayPolicyHelper@@YAJAEA_N@Z; RelayPolicyHelper::GetIsRelayEnabled(bool &)
0x18000e227  test    eax, eax
0x18000e229  jns     short loc_18000E234
0x18000e22b  mov     [rbp+arg_10], 181h
0x18000e232  jmp     short loc_18000E1F7
0x18000e234  mov     ecx, 2
0x18000e239  call    cs:__imp_CDPInitializeForService
0x18000e23f  test    eax, eax
0x18000e241  jns     short loc_18000E24C
0x18000e243  mov     [rbp+arg_10], 183h
0x18000e24a  jmp     short loc_18000E1F7
0x18000e24c  lea     rdi, ?g_loggerMutex@@3Vmutex@std@@A; std::mutex g_loggerMutex
0x18000e253  mov     [rbp+arg_18], rdi
0x18000e257  mov     rcx, rdi; this
0x18000e25a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18000e25f  nop
0x18000e260  mov     [rbp+var_10], 0
0x18000e268  lea     rax, ?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x18000e26f  mov     [rbp+var_8], rax
0x18000e273  lea     rcx, [rbp+var_10]
0x18000e277  call    cs:__imp_CDPGetLogger
0x18000e27d  mov     ebx, eax
0x18000e27f  lea     rcx, [rbp+var_10]
0x18000e283  call    ??1?$address_of@VICDPLogger@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPLogger>::~address_of<ICDPLogger>(void)
0x18000e288  test    ebx, ebx
0x18000e28a  jns     short loc_18000E2B4
0x18000e28c  mov     [rbp+arg_8], ebx
0x18000e28f  mov     [rbp+arg_10], 186h
0x18000e296  lea     rax, [rbp+arg_10]
0x18000e29a  mov     [rsp+40h+var_20], rax
0x18000e29f  lea     r8, [rbp+arg_8]
0x18000e2a3  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18000e2aa  call    ??$Log@AEAJAEAY0BD@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BD@$$CBD$$QEAH@Z; Log<long &,char const (&)[19],int>(CDPLogLevel,char const *,long &,char const (&)[19],int &&)
0x18000e2af  mov     ebx, [rbp+arg_8]
0x18000e2b2  jmp     short loc_18000E2B6
0x18000e2b4  xor     ebx, ebx
0x18000e2b6  mov     rcx, rdi; _Mtx_t
0x18000e2b9  call    cs:__imp__Mtx_unlock
0x18000e2bf  mov     eax, ebx
0x18000e2c1  add     rsp, 40h
0x18000e2c5  pop     rdi
0x18000e2c6  pop     rbx
0x18000e2c7  pop     rbp
0x18000e2c8  retn
```
