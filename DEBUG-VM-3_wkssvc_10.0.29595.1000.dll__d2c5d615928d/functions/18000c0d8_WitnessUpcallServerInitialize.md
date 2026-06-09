# WitnessUpcallServerInitialize

- ea: `0x18000c0d8`
- end: `0x18000c302`
- name: `WitnessUpcallServerInitialize`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000beb4`

## callees

- `0x18000c0d8`
- `0x180022b7c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000c113`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c113`
- `ntdll!RtlReleaseResource` at `0x18000c2c7`
- `ntdll!RtlReleaseResource` at `0x18000c2c7`
- `ntdll!RtlDeleteResource` at `0x18000c2d8`
- `ntdll!RtlDeleteResource` at `0x18000c2d8`
- `ntdll!RtlInitializeResource` at `0x18000c0fe`
- `ntdll!RtlInitializeResource` at `0x18000c0fe`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18000c1a1`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18000c1a1`
- `RPCRT4!RpcEpRegisterW` at `0x18000c22a`
- `RPCRT4!RpcEpRegisterW` at `0x18000c22a`
- `RPCRT4!RpcServerInqBindings` at `0x18000c1e4`
- `RPCRT4!RpcServerInqBindings` at `0x18000c1e4`
- `RPCRT4!RpcBindingVectorFree` at `0x18000c2ba`
- `RPCRT4!RpcBindingVectorFree` at `0x18000c2ba`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000c279`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000c279`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000c129`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18000c129`

## pseudocode

```c
__int64 __fastcall WitnessUpcallServerInitialize(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+40h] [rbp+8h] BYREF

  pUpcallDispatch = a1;
  BindingVector = 0;
  RtlInitializeResource(&UpcallServerResource);
  RtlAcquireResourceExclusive(&UpcallServerResource, 1u);
  v1 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, 0, 0);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v4 = 14;
LABEL_6:
      WPP_SF_d(v3[2], v4, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v1);
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  v1 = RpcServerRegisterIfEx(
         qword_1800350C0,
         0,
         0,
         0xB1u,
         0x4D2u,
         (RPC_IF_CALLBACK_FN *)WitnessUpcallServerSecurityCallback);
  v2 = v1;
  if ( !v1 )
  {
    v5 = RpcServerInqBindings(&BindingVector);
    if ( v5 )
    {
      v6 = WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control == &WPP_witness_GLOBAL_Control
        || (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
LABEL_23:
        v1 = RpcServerUnregisterIf(qword_1800350C0, 0, 1u);
        v2 = v1;
        if ( v1 )
        {
          v3 = WPP_witness_GLOBAL_Control;
          if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
            && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
          {
            v4 = 19;
            goto LABEL_6;
          }
        }
        goto LABEL_29;
      }
      v7 = 16;
    }
    else
    {
      v5 = RpcEpRegisterW(qword_1800350C0, BindingVector, 0, (RPC_WSTR)L"Witness Client Upcall Server");
      v2 = v5;
      if ( !v5 )
      {
        UpcallServerState = 1;
        goto LABEL_29;
      }
      v6 = WPP_witness_GLOBAL_Control;
      if ( WPP_witness_GLOBAL_Control == &WPP_witness_GLOBAL_Control
        || (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) == 0
        || !*((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        goto LABEL_23;
      }
      v7 = 17;
    }
    WPP_SF_d(v6[2], v7, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v5);
    goto LABEL_23;
  }
  v3 = WPP_witness_GLOBAL_Control;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    v4 = 15;
    goto LABEL_6;
  }
LABEL_29:
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  RtlReleaseResource(&UpcallServerResource);
  if ( v2 )
  {
    RtlDeleteResource(&UpcallServerResource);
    UpcallServerState = 2;
  }
  else
  {
    UpcallServerResourceInitialized = 1;
  }
  return v2;
}

```

## disassembly

```asm
0x18000c0d8  mov     [rsp+arg_8], rbx
0x18000c0dd  mov     [rsp+arg_10], rsi
0x18000c0e2  push    rdi
0x18000c0e3  sub     rsp, 30h
0x18000c0e7  mov     cs:pUpcallDispatch, rcx
0x18000c0ee  lea     rcx, UpcallServerResource; Resource
0x18000c0f5  mov     [rsp+38h+BindingVector], 0
0x18000c0fe  call    cs:__imp_RtlInitializeResource
0x18000c104  mov     esi, 1
0x18000c109  lea     rcx, UpcallServerResource; Resource
0x18000c110  mov     dl, sil; Wait
0x18000c113  call    cs:__imp_RtlAcquireResourceExclusive
0x18000c119  xor     r9d, r9d; SecurityDescriptor
0x18000c11c  lea     edx, [rsi+9]; MaxCalls
0x18000c11f  xor     r8d, r8d; Endpoint
0x18000c122  lea     rcx, String2; "ncalrpc"
0x18000c129  call    cs:__imp_RpcServerUseProtseqEpW
0x18000c12f  mov     ebx, eax
0x18000c131  test    eax, eax
0x18000c133  jz      short loc_18000C17B
0x18000c135  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c13c  lea     rdi, WPP_witness_GLOBAL_Control
0x18000c143  cmp     rcx, rdi
0x18000c146  jz      loc_18000C2AD
0x18000c14c  test    [rcx+1Ch], sil
0x18000c150  jz      loc_18000C2AD
0x18000c156  cmp     [rcx+19h], sil
0x18000c15a  jb      loc_18000C2AD
0x18000c160  lea     edx, [rsi+0Dh]
0x18000c163  mov     rcx, [rcx+10h]
0x18000c167  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000c16e  mov     r9d, eax
0x18000c171  call    WPP_SF_d
0x18000c176  jmp     loc_18000C2AD
0x18000c17b  lea     rax, WitnessUpcallServerSecurityCallback
0x18000c182  mov     r9d, 0B1h; Flags
0x18000c188  mov     [rsp+38h+IfCallback], rax; IfCallback
0x18000c18d  lea     rcx, qword_1800350C0; IfSpec
0x18000c194  xor     r8d, r8d; MgrEpv
0x18000c197  mov     [rsp+38h+MaxCalls], 4D2h; MaxCalls
0x18000c19f  xor     edx, edx; MgrTypeUuid
0x18000c1a1  call    cs:__imp_RpcServerRegisterIfEx
0x18000c1a7  mov     ebx, eax
0x18000c1a9  test    eax, eax
0x18000c1ab  jz      short loc_18000C1DF
0x18000c1ad  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c1b4  lea     rdi, WPP_witness_GLOBAL_Control
0x18000c1bb  cmp     rcx, rdi
0x18000c1be  jz      loc_18000C2AD
0x18000c1c4  test    [rcx+1Ch], sil
0x18000c1c8  jz      loc_18000C2AD
0x18000c1ce  cmp     [rcx+19h], sil
0x18000c1d2  jb      loc_18000C2AD
0x18000c1d8  mov     edx, 0Fh
0x18000c1dd  jmp     short loc_18000C163
0x18000c1df  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x18000c1e4  call    cs:__imp_RpcServerInqBindings
0x18000c1ea  test    eax, eax
0x18000c1ec  jz      short loc_18000C214
0x18000c1ee  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c1f5  lea     rdi, WPP_witness_GLOBAL_Control
0x18000c1fc  cmp     rcx, rdi
0x18000c1ff  jz      short loc_18000C26D
0x18000c201  test    [rcx+1Ch], sil
0x18000c205  jz      short loc_18000C26D
0x18000c207  cmp     [rcx+19h], sil
0x18000c20b  jb      short loc_18000C26D
0x18000c20d  mov     edx, 10h
0x18000c212  jmp     short loc_18000C25A
0x18000c214  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x18000c219  lea     r9, aWitnessClientU; "Witness Client Upcall Server"
0x18000c220  xor     r8d, r8d; UuidVector
0x18000c223  lea     rcx, qword_1800350C0; IfSpec
0x18000c22a  call    cs:__imp_RpcEpRegisterW
0x18000c230  mov     ebx, eax
0x18000c232  test    eax, eax
0x18000c234  jz      short loc_18000C2A7
0x18000c236  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c23d  lea     rdi, WPP_witness_GLOBAL_Control
0x18000c244  cmp     rcx, rdi
0x18000c247  jz      short loc_18000C26D
0x18000c249  test    [rcx+1Ch], sil
0x18000c24d  jz      short loc_18000C26D
0x18000c24f  cmp     [rcx+19h], sil
0x18000c253  jb      short loc_18000C26D
0x18000c255  mov     edx, 11h
0x18000c25a  mov     rcx, [rcx+10h]
0x18000c25e  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x18000c265  mov     r9d, eax
0x18000c268  call    WPP_SF_d
0x18000c26d  mov     r8d, esi; WaitForCallsToComplete
0x18000c270  lea     rcx, qword_1800350C0; IfSpec
0x18000c277  xor     edx, edx; MgrTypeUuid
0x18000c279  call    cs:__imp_RpcServerUnregisterIf
0x18000c27f  mov     ebx, eax
0x18000c281  test    eax, eax
0x18000c283  jz      short loc_18000C2AD
0x18000c285  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c28c  cmp     rcx, rdi
0x18000c28f  jz      short loc_18000C2AD
0x18000c291  test    [rcx+1Ch], sil
0x18000c295  jz      short loc_18000C2AD
0x18000c297  cmp     [rcx+19h], sil
0x18000c29b  jb      short loc_18000C2AD
0x18000c29d  mov     edx, 13h
0x18000c2a2  jmp     loc_18000C163
0x18000c2a7  mov     cs:UpcallServerState, esi
0x18000c2ad  cmp     [rsp+38h+BindingVector], 0
0x18000c2b3  jz      short loc_18000C2C0
0x18000c2b5  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x18000c2ba  call    cs:__imp_RpcBindingVectorFree
0x18000c2c0  lea     rcx, UpcallServerResource; Resource
0x18000c2c7  call    cs:__imp_RtlReleaseResource
0x18000c2cd  test    ebx, ebx
0x18000c2cf  jz      short loc_18000C2EA
0x18000c2d1  lea     rcx, UpcallServerResource; Resource
0x18000c2d8  call    cs:__imp_RtlDeleteResource
0x18000c2de  mov     cs:UpcallServerState, 2
0x18000c2e8  jmp     short loc_18000C2F0
0x18000c2ea  mov     cs:UpcallServerResourceInitialized, esi
0x18000c2f0  mov     rsi, [rsp+38h+arg_10]
0x18000c2f5  mov     eax, ebx
0x18000c2f7  mov     rbx, [rsp+38h+arg_8]
0x18000c2fc  add     rsp, 30h
0x18000c300  pop     rdi
0x18000c301  retn
```
