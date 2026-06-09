# CBroker::SebPublisher::CSebPublishRpcServerInit(void)

- ea: `0x180020bac`
- end: `0x180020cc9`
- name: `?CSebPublishRpcServerInit@SebPublisher@CBroker@@SAJXZ`
- size: `285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fb20`

## callees

- `0x1800076a0`
- `0x180012a80`
- `0x180017120`
- `0x180020bac`
- `0x180020cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c19`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180020c0f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180020c0f`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180020c39`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180020c39`
- `RPCRT4!RpcServerRegisterIf3` at `0x180020c84`
- `RPCRT4!RpcServerRegisterIf3` at `0x180020c84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ca1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ca1`

## pseudocode

```c
__int64 CBroker::SebPublisher::CSebPublishRpcServerInit(void)
{
  __int64 Instance; // rax
  unsigned int v1; // ebx
  DWORD LastError; // eax
  RPC_STATUS v3; // eax
  std::_Ref_count_base *v5[2]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v6[8]; // [rsp+50h] [rbp-18h] BYREF
  std::_Ref_count_base *v7; // [rsp+58h] [rbp-10h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+8h] BYREF

  *(_OWORD *)v5 = 0;
  SecurityDescriptor = 0;
  Instance = CBroker::SebBroker::GetInstance(v6);
  std::shared_ptr<CBroker::SebBroker>::operator=(v5, Instance);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  if ( !v5[0] )
  {
    v1 = 1359;
    goto LABEL_12;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GR;;;SY)(A;;GR;;;AC)(A;;GR;;;AU)(A;;GR;;;S-1-5-80-2226967063-754826275-1661302337-2802353169-2369347280)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
LABEL_11:
    v1 = LastError;
    goto LABEL_12;
  }
  v3 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"csebpub", SecurityDescriptor);
  v1 = v3;
  if ( !v3 || v3 == 1740 )
  {
    v1 = RpcServerRegisterIf3(
           qword_1800287D0,
           0,
           0,
           33,
           1234,
           -1,
           CBroker::SebPublisher::CSebPublisherCapabilityCheck,
           SecurityDescriptor);
    if ( !v1 )
    {
      LastError = CBroker::SebPublisher::CreateEventsState();
      goto LABEL_11;
    }
  }
LABEL_12:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( !v1 )
    byte_180036E80 = 1;
  if ( v5[1] )
    std::_Ref_count_base::_Decref(v5[1]);
  return v1;
}

```

## disassembly

```asm
0x180020bac  push    rbx
0x180020bae  sub     rsp, 60h
0x180020bb2  xorps   xmm0, xmm0
0x180020bb5  movdqu  xmmword ptr [rsp+68h+var_28], xmm0
0x180020bbb  mov     [rsp+68h+SecurityDescriptor], 0
0x180020bc4  lea     rcx, [rsp+68h+var_18]
0x180020bc9  call    ?GetInstance@SebBroker@CBroker@@SA?AV?$shared_ptr@VSebBroker@CBroker@@@std@@XZ; CBroker::SebBroker::GetInstance(void)
0x180020bce  mov     rdx, rax
0x180020bd1  lea     rcx, [rsp+68h+var_28]
0x180020bd6  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x180020bdb  mov     rcx, [rsp+68h+var_10]; this
0x180020be0  test    rcx, rcx
0x180020be3  jz      short loc_180020BEA
0x180020be5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020bea  cmp     [rsp+68h+var_28], 0
0x180020bf0  jnz     short loc_180020BFC
0x180020bf2  mov     ebx, 54Fh
0x180020bf7  jmp     loc_180020C97
0x180020bfc  xor     r9d, r9d; SecurityDescriptorSize
0x180020bff  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180020c04  lea     edx, [r9+1]; StringSDRevision
0x180020c08  lea     rcx, aDAGrSyAGrAcAGr; "D:(A;;GR;;;SY)(A;;GR;;;AC)(A;;GR;;;AU)("...
0x180020c0f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180020c15  test    eax, eax
0x180020c17  jnz     short loc_180020C21
0x180020c19  call    cs:__imp_GetLastError
0x180020c1f  jmp     short loc_180020C95
0x180020c21  mov     r9, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180020c26  lea     r8, Endpoint; "csebpub"
0x180020c2d  mov     edx, 0Ah; MaxCalls
0x180020c32  lea     rcx, Protseq; "ncalrpc"
0x180020c39  call    cs:__imp_RpcServerUseProtseqEpW
0x180020c3f  mov     ebx, eax
0x180020c41  test    eax, eax
0x180020c43  jz      short loc_180020C4C
0x180020c45  cmp     eax, 6CCh
0x180020c4a  jnz     short loc_180020C97
0x180020c4c  mov     rax, [rsp+68h+SecurityDescriptor]
0x180020c51  mov     [rsp+68h+var_30], rax
0x180020c56  lea     rax, ?CSebPublisherCapabilityCheck@SebPublisher@CBroker@@CAJPEAX0@Z; CBroker::SebPublisher::CSebPublisherCapabilityCheck(void *,void *)
0x180020c5d  mov     [rsp+68h+var_38], rax
0x180020c62  mov     [rsp+68h+var_40], 0FFFFFFFFh
0x180020c6a  mov     [rsp+68h+var_48], 4D2h
0x180020c72  mov     r9d, 21h ; '!'
0x180020c78  xor     r8d, r8d
0x180020c7b  xor     edx, edx
0x180020c7d  lea     rcx, qword_1800287D0
0x180020c84  call    cs:__imp_RpcServerRegisterIf3
0x180020c8a  mov     ebx, eax
0x180020c8c  test    eax, eax
0x180020c8e  jnz     short loc_180020C97
0x180020c90  call    ?CreateEventsState@SebPublisher@CBroker@@CAJXZ; CBroker::SebPublisher::CreateEventsState(void)
0x180020c95  mov     ebx, eax
0x180020c97  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x180020c9c  test    rcx, rcx
0x180020c9f  jz      short loc_180020CA7
0x180020ca1  call    cs:__imp_LocalFree
0x180020ca7  test    ebx, ebx
0x180020ca9  jnz     short loc_180020CB2
0x180020cab  mov     cs:byte_180036E80, 1
0x180020cb2  mov     rcx, [rsp+68h+var_28+8]; this
0x180020cb7  test    rcx, rcx
0x180020cba  jz      short loc_180020CC1
0x180020cbc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020cc1  mov     eax, ebx
0x180020cc3  add     rsp, 60h
0x180020cc7  pop     rbx
0x180020cc8  retn
```
