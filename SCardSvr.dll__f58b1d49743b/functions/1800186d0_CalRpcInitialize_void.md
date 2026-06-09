# CalRpcInitialize(void)

- ea: `0x1800186d0`
- end: `0x1800188f4`
- name: `?CalRpcInitialize@@YAKXZ`
- size: `548`
- prototype: `__int64 __fastcall(struct _SERVICE_THREAD_SECURITY_INFO **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180010f50`

## callees

- `0x180015604`
- `0x1800186d0`
- `0x1800188fc`
- `0x18002f96c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800188e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800188e2`
- `RPCRT4!RpcServerInqBindings` at `0x1800187b9`
- `RPCRT4!RpcServerInqBindings` at `0x1800187b9`
- `RPCRT4!RpcServerListen` at `0x18001881a`
- `RPCRT4!RpcServerListen` at `0x18001881a`
- `RPCRT4!RpcEpUnregister` at `0x18001884c`
- `RPCRT4!RpcEpUnregister` at `0x180018867`
- `RPCRT4!RpcEpUnregister` at `0x18001884c`
- `RPCRT4!RpcEpUnregister` at `0x180018867`
- `RPCRT4!RpcEpRegisterW` at `0x1800187dd`
- `RPCRT4!RpcEpRegisterW` at `0x180018803`
- `RPCRT4!RpcEpRegisterW` at `0x1800187dd`
- `RPCRT4!RpcEpRegisterW` at `0x180018803`
- `RPCRT4!RpcBindingVectorFree` at `0x1800188a6`
- `RPCRT4!RpcBindingVectorFree` at `0x1800188a6`
- `RPCRT4!RpcServerRegisterIf3` at `0x180018757`
- `RPCRT4!RpcServerRegisterIf3` at `0x18001879b`
- `RPCRT4!RpcServerRegisterIf3` at `0x180018757`
- `RPCRT4!RpcServerRegisterIf3` at `0x18001879b`
- `RPCRT4!RpcServerUnregisterIf` at `0x180018879`
- `RPCRT4!RpcServerUnregisterIf` at `0x18001888f`
- `RPCRT4!RpcServerUnregisterIf` at `0x180018879`
- `RPCRT4!RpcServerUnregisterIf` at `0x18001888f`
- `RPCRT4!RpcServerUseProtseqW` at `0x180018715`
- `RPCRT4!RpcServerUseProtseqW` at `0x180018715`

## pseudocode

```c
__int64 __fastcall CalRpcInitialize(struct _SERVICE_THREAD_SECURITY_INFO **a1)
{
  unsigned int v1; // ebx
  int v2; // esi
  int v3; // edi
  RPC_STATUS v4; // eax
  void *SecurityDescriptor; // [rsp+70h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  v1 = InitializeServiceThreadSecurityInfo(a1);
  if ( v1
    || (v1 = CalRpcCreateAppContainerRpcSD(&SecurityDescriptor)) != 0
    || (v1 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor)) != 0
    || (v1 = RpcServerRegisterIf3(qword_180039C20, 0, 0, 9, 1234, 0, CalRpcSCardSecurityCallback, SecurityDescriptor)) != 0 )
  {
LABEL_16:
    if ( BindingVector )
    {
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
    if ( qword_18004BFA0 )
    {
      FreeServiceThreadSecurityInfo(&qword_18004BFA0);
      qword_18004BFA0 = 0;
    }
    goto LABEL_20;
  }
  v2 = 0;
  v1 = RpcServerRegisterIf3(qword_180039630, 0, 0, 8, 1234, 0, CalRpcCacheSecurityCallback, SecurityDescriptor);
  if ( v1
    || (v2 = 1, (v1 = RpcServerInqBindings(&BindingVector)) != 0)
    || (v1 = RpcEpRegisterW(qword_180039C20, BindingVector, 0, 0)) != 0 )
  {
LABEL_14:
    RpcServerUnregisterIf(qword_180039C20, 0, 1u);
    if ( v2 )
      RpcServerUnregisterIf(qword_180039630, 0, 1u);
    goto LABEL_16;
  }
  v3 = 0;
  v1 = RpcEpRegisterW(qword_180039630, BindingVector, 0, 0);
  if ( v1 )
    goto LABEL_12;
  v4 = RpcServerListen(1u, 0x4D2u, 1u);
  v1 = v4;
  if ( v4 == 1713 )
  {
    v1 = 0;
    goto LABEL_20;
  }
  v3 = 1;
  if ( v4 )
  {
LABEL_12:
    RpcEpUnregister(qword_180039C20, BindingVector, 0);
    if ( v3 )
      RpcEpUnregister(qword_180039630, BindingVector, 0);
    goto LABEL_14;
  }
LABEL_20:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v1;
}

```

## disassembly

```asm
0x1800186d0  push    rbx
0x1800186d2  push    rsi
0x1800186d3  push    rdi
0x1800186d4  push    r14
0x1800186d6  sub     rsp, 48h
0x1800186da  mov     [rsp+68h+SecurityDescriptor], 0
0x1800186e3  call    ?InitializeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z; InitializeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)
0x1800186e8  mov     ebx, eax
0x1800186ea  test    eax, eax
0x1800186ec  jnz     loc_180018895
0x1800186f2  lea     rcx, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x1800186f7  call    ?CalRpcCreateAppContainerRpcSD@@YAKPEAPEAX@Z; CalRpcCreateAppContainerRpcSD(void * *)
0x1800186fc  mov     ebx, eax
0x1800186fe  test    eax, eax
0x180018700  jnz     loc_180018895
0x180018706  mov     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x18001870b  lea     edx, [rax+0Ah]; MaxCalls
0x18001870e  lea     rcx, Protseq; "ncalrpc"
0x180018715  call    cs:__imp_RpcServerUseProtseqW
0x18001871b  mov     ebx, eax
0x18001871d  test    eax, eax
0x18001871f  jnz     loc_180018895
0x180018725  mov     rax, [rsp+68h+SecurityDescriptor]
0x18001872a  lea     r9d, [rbx+9]
0x18001872e  mov     [rsp+68h+var_30], rax
0x180018733  lea     rcx, qword_180039C20
0x18001873a  lea     rax, ?CalRpcSCardSecurityCallback@@YAJPEAX0@Z; CalRpcSCardSecurityCallback(void *,void *)
0x180018741  xor     r8d, r8d
0x180018744  mov     [rsp+68h+var_38], rax
0x180018749  xor     edx, edx
0x18001874b  mov     [rsp+68h+var_40], ebx
0x18001874f  mov     [rsp+68h+var_48], 4D2h
0x180018757  call    cs:__imp_RpcServerRegisterIf3
0x18001875d  mov     ebx, eax
0x18001875f  test    eax, eax
0x180018761  jnz     loc_180018895
0x180018767  mov     rax, [rsp+68h+SecurityDescriptor]
0x18001876c  lea     r9d, [rbx+8]
0x180018770  mov     [rsp+68h+var_30], rax
0x180018775  lea     rcx, qword_180039630
0x18001877c  lea     rax, ?CalRpcCacheSecurityCallback@@YAJPEAX0@Z; CalRpcCacheSecurityCallback(void *,void *)
0x180018783  xor     esi, esi
0x180018785  mov     [rsp+68h+var_38], rax
0x18001878a  xor     r8d, r8d
0x18001878d  mov     [rsp+68h+var_40], esi
0x180018791  xor     edx, edx
0x180018793  mov     [rsp+68h+var_48], 4D2h
0x18001879b  call    cs:__imp_RpcServerRegisterIf3
0x1800187a1  lea     r14d, [rsi+1]
0x1800187a5  mov     ebx, eax
0x1800187a7  test    eax, eax
0x1800187a9  jnz     loc_18001886D
0x1800187af  lea     rcx, BindingVector; BindingVector
0x1800187b6  mov     esi, r14d
0x1800187b9  call    cs:__imp_RpcServerInqBindings
0x1800187bf  mov     ebx, eax
0x1800187c1  test    eax, eax
0x1800187c3  jnz     loc_18001886D
0x1800187c9  mov     rdx, cs:BindingVector; BindingVector
0x1800187d0  lea     rcx, qword_180039C20; IfSpec
0x1800187d7  xor     r9d, r9d; Annotation
0x1800187da  xor     r8d, r8d; UuidVector
0x1800187dd  call    cs:__imp_RpcEpRegisterW
0x1800187e3  mov     ebx, eax
0x1800187e5  test    eax, eax
0x1800187e7  jnz     loc_18001886D
0x1800187ed  mov     rdx, cs:BindingVector; BindingVector
0x1800187f4  lea     rcx, qword_180039630; IfSpec
0x1800187fb  xor     r9d, r9d; Annotation
0x1800187fe  xor     r8d, r8d; UuidVector
0x180018801  xor     edi, edi
0x180018803  call    cs:__imp_RpcEpRegisterW
0x180018809  mov     ebx, eax
0x18001880b  test    eax, eax
0x18001880d  jnz     short loc_18001883B
0x18001880f  mov     r8d, r14d; DontWait
0x180018812  mov     edx, 4D2h; MaxCalls
0x180018817  mov     ecx, r14d; MinimumCallThreads
0x18001881a  call    cs:__imp_RpcServerListen
0x180018820  mov     ebx, eax
0x180018822  cmp     eax, 6B1h
0x180018827  jnz     short loc_180018830
0x180018829  xor     ebx, ebx
0x18001882b  jmp     loc_1800188D8
0x180018830  mov     edi, r14d
0x180018833  test    eax, eax
0x180018835  jz      loc_1800188D8
0x18001883b  mov     rdx, cs:BindingVector; BindingVector
0x180018842  lea     rcx, qword_180039C20; IfSpec
0x180018849  xor     r8d, r8d; UuidVector
0x18001884c  call    cs:__imp_RpcEpUnregister
0x180018852  test    edi, edi
0x180018854  jz      short loc_18001886D
0x180018856  mov     rdx, cs:BindingVector; BindingVector
0x18001885d  lea     rcx, qword_180039630; IfSpec
0x180018864  xor     r8d, r8d; UuidVector
0x180018867  call    cs:__imp_RpcEpUnregister
0x18001886d  mov     r8d, r14d; WaitForCallsToComplete
0x180018870  lea     rcx, qword_180039C20; IfSpec
0x180018877  xor     edx, edx; MgrTypeUuid
0x180018879  call    cs:__imp_RpcServerUnregisterIf
0x18001887f  test    esi, esi
0x180018881  jz      short loc_180018895
0x180018883  mov     r8d, r14d; WaitForCallsToComplete
0x180018886  lea     rcx, qword_180039630; IfSpec
0x18001888d  xor     edx, edx; MgrTypeUuid
0x18001888f  call    cs:__imp_RpcServerUnregisterIf
0x180018895  cmp     cs:BindingVector, 0
0x18001889d  jz      short loc_1800188B7
0x18001889f  lea     rcx, BindingVector; BindingVector
0x1800188a6  call    cs:__imp_RpcBindingVectorFree
0x1800188ac  mov     cs:BindingVector, 0
0x1800188b7  cmp     cs:qword_18004BFA0, 0
0x1800188bf  jz      short loc_1800188D8
0x1800188c1  lea     rcx, qword_18004BFA0; struct _SERVICE_THREAD_SECURITY_INFO **
0x1800188c8  call    ?FreeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z; FreeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)
0x1800188cd  mov     cs:qword_18004BFA0, 0
0x1800188d8  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x1800188dd  test    rcx, rcx
0x1800188e0  jz      short loc_1800188E8
0x1800188e2  call    cs:__imp_LocalFree
0x1800188e8  mov     eax, ebx
0x1800188ea  add     rsp, 48h
0x1800188ee  pop     r14
0x1800188f0  pop     rdi
0x1800188f1  pop     rsi
0x1800188f2  pop     rbx
0x1800188f3  retn
```
