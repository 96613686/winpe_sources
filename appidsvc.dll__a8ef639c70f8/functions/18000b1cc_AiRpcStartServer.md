# AiRpcStartServer

- ea: `0x18000b1cc`
- end: `0x18000b2ec`
- name: `AiRpcStartServer`
- size: `288`
- prototype: `int()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003c80`

## callees

- `0x18000b1cc`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18000b2e0`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b2e0`
- `RPCRT4!RpcBindingVectorFree` at `0x18000b2bd`
- `RPCRT4!RpcBindingVectorFree` at `0x18000b2bd`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000b2a6`
- `RPCRT4!RpcServerUnregisterIf` at `0x18000b2a6`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000b269`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000b269`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000b210`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000b210`
- `RPCRT4!RpcEpRegisterW` at `0x18000b28d`
- `RPCRT4!RpcEpRegisterW` at `0x18000b28d`
- `RPCRT4!RpcServerInqBindings` at `0x18000b227`
- `RPCRT4!RpcServerInqBindings` at `0x18000b227`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b2d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000b1ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000b1ee`

## pseudocode

```c
int AiRpcStartServer()
{
  RPC_STATUS v0; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GR;;;AN)(A;;GR;;;WD)(A;;GR;;;RC)(A;;GA;;;BA)(A;;GA;;;SY)(A;;GR;;;AC)(A;;GR;;;S-1-15-2-2)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v0 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
    if ( !v0 )
    {
      v0 = RpcServerInqBindings(&g_BindingVector);
      if ( !v0 )
      {
        v0 = RpcServerRegisterIf3(qword_18000F630, 0, 0, 41, 1234, -1, &AiRpcpSecurityCallback, SecurityDescriptor);
        if ( !v0 )
        {
          v0 = RpcEpRegisterW(qword_18000F630, g_BindingVector, 0, (RPC_WSTR)L"AppIDSvc");
          if ( !v0 )
            goto LABEL_10;
          RpcServerUnregisterIf(qword_18000F630, 0, 1u);
        }
      }
    }
  }
  else
  {
    v0 = 1766;
  }
  if ( g_BindingVector )
  {
    RpcBindingVectorFree(&g_BindingVector);
    g_BindingVector = 0;
  }
LABEL_10:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return I_RpcMapWin32Status(v0);
}

```

## disassembly

```asm
0x18000b1cc  push    rbx
0x18000b1ce  sub     rsp, 40h
0x18000b1d2  xor     r9d, r9d; SecurityDescriptorSize
0x18000b1d5  mov     [rsp+48h+SecurityDescriptor], 0
0x18000b1de  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x18000b1e3  lea     rcx, aDAGrAnAGrWdAGr; "D:(A;;GR;;;AN)(A;;GR;;;WD)(A;;GR;;;RC)("...
0x18000b1ea  lea     edx, [r9+1]; StringSDRevision
0x18000b1ee  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000b1f4  test    eax, eax
0x18000b1f6  jnz     short loc_18000B202
0x18000b1f8  mov     ebx, 6E6h
0x18000b1fd  jmp     loc_18000B2AC
0x18000b202  xor     r8d, r8d; SecurityDescriptor
0x18000b205  lea     rcx, Protseq; "ncalrpc"
0x18000b20c  lea     edx, [r8+0Ah]; MaxCalls
0x18000b210  call    cs:__imp_RpcServerUseProtseqW
0x18000b216  mov     ebx, eax
0x18000b218  test    eax, eax
0x18000b21a  jnz     loc_18000B2AC
0x18000b220  lea     rcx, g_BindingVector; BindingVector
0x18000b227  call    cs:__imp_RpcServerInqBindings
0x18000b22d  mov     ebx, eax
0x18000b22f  test    eax, eax
0x18000b231  jnz     short loc_18000B2AC
0x18000b233  mov     rax, [rsp+48h+SecurityDescriptor]
0x18000b238  lea     r9d, [rbx+29h]
0x18000b23c  mov     [rsp+48h+var_10], rax
0x18000b241  lea     rcx, qword_18000F630
0x18000b248  lea     rax, AiRpcpSecurityCallback
0x18000b24f  xor     r8d, r8d
0x18000b252  mov     [rsp+48h+var_18], rax
0x18000b257  xor     edx, edx
0x18000b259  mov     [rsp+48h+var_20], 0FFFFFFFFh
0x18000b261  mov     [rsp+48h+var_28], 4D2h
0x18000b269  call    cs:__imp_RpcServerRegisterIf3
0x18000b26f  mov     ebx, eax
0x18000b271  test    eax, eax
0x18000b273  jnz     short loc_18000B2AC
0x18000b275  mov     rdx, cs:g_BindingVector; BindingVector
0x18000b27c  lea     r9, Annotation; "AppIDSvc"
0x18000b283  xor     r8d, r8d; UuidVector
0x18000b286  lea     rcx, qword_18000F630; IfSpec
0x18000b28d  call    cs:__imp_RpcEpRegisterW
0x18000b293  mov     ebx, eax
0x18000b295  test    eax, eax
0x18000b297  jz      short loc_18000B2CE
0x18000b299  xor     edx, edx; MgrTypeUuid
0x18000b29b  lea     rcx, qword_18000F630; IfSpec
0x18000b2a2  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18000b2a6  call    cs:__imp_RpcServerUnregisterIf
0x18000b2ac  cmp     cs:g_BindingVector, 0
0x18000b2b4  jz      short loc_18000B2CE
0x18000b2b6  lea     rcx, g_BindingVector; BindingVector
0x18000b2bd  call    cs:__imp_RpcBindingVectorFree
0x18000b2c3  mov     cs:g_BindingVector, 0
0x18000b2ce  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x18000b2d3  test    rcx, rcx
0x18000b2d6  jz      short loc_18000B2DE
0x18000b2d8  call    cs:__imp_LocalFree
0x18000b2de  mov     ecx, ebx; Status
0x18000b2e0  call    cs:__imp_I_RpcMapWin32Status
0x18000b2e6  add     rsp, 40h
0x18000b2ea  pop     rbx
0x18000b2eb  retn
```
