# ServiceHandler

- ea: `0x18000dc40`
- end: `0x18000dcf8`
- name: `ServiceHandler`
- size: `184`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000dbb0`
- `0x18000dc40`
- `0x18001af7c`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000dc94`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x18000dc94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dcaa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dccf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dccf`

## pseudocode

```c
void __fastcall ServiceHandler(DWORD dwControl)
{
  DWORD v1; // ecx
  DWORD dwCurrentState; // ecx
  CGPRPCServerBase *v3; // rbx
  int v4; // edx
  __int64 v5; // rcx
  int v6; // edx
  __int64 v7; // rcx
  int v8; // edi

  v1 = dwControl - 1;
  if ( v1 )
  {
    if ( v1 != 3 )
      return;
    dwCurrentState = ServiceStatus.dwCurrentState;
    goto LABEL_14;
  }
  v3 = CRPCServiceManager::_pSingletonManager;
  if ( CRPCServiceManager::_pSingletonManager )
  {
    UpdateState(3u);
    LogTime(v5, v4);
    v8 = 0;
    if ( *((_DWORD *)v3 + 3) )
    {
      if ( GPRpcInterfaceGroupCreated )
      {
        v8 = RpcServerInterfaceGroupClose(GPRpcInterfaceGroup);
        GPRpcInterfaceGroupCreated = 0;
      }
      LocalFree(*((HLOCAL *)v3 + 3));
      if ( !v8 )
        *((_DWORD *)v3 + 3) = 0;
    }
    CGPRPCServerBase::m_instance = 0;
    LogTime(v7, v6);
    if ( v8 || !SetEvent(*((HANDLE *)v3 + 8)) && GetLastError() )
    {
      dwCurrentState = 4;
LABEL_14:
      UpdateState(dwCurrentState);
    }
  }
}

```

## disassembly

```asm
0x18000dc40  mov     [rsp+arg_0], rbx
0x18000dc45  push    rdi
0x18000dc46  sub     rsp, 20h
0x18000dc4a  sub     ecx, 1
0x18000dc4d  jz      short loc_18000DC63
0x18000dc4f  cmp     ecx, 3
0x18000dc52  jnz     loc_18000DCED
0x18000dc58  mov     ecx, cs:ServiceStatus.dwCurrentState
0x18000dc5e  jmp     loc_18000DCE8
0x18000dc63  mov     rbx, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x18000dc6a  test    rbx, rbx
0x18000dc6d  jz      short loc_18000DCED
0x18000dc6f  mov     ecx, 3; unsigned int
0x18000dc74  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18000dc79  call    ?LogTime@@YAXXZ; LogTime(void)
0x18000dc7e  xor     edi, edi
0x18000dc80  cmp     [rbx+0Ch], edi
0x18000dc83  jz      short loc_18000DCB7
0x18000dc85  cmp     cs:?GPRpcInterfaceGroupCreated@@3HA, edi; int GPRpcInterfaceGroupCreated
0x18000dc8b  jz      short loc_18000DCA6
0x18000dc8d  mov     rcx, cs:?GPRpcInterfaceGroup@@3PEAXEA; void * GPRpcInterfaceGroup
0x18000dc94  call    cs:__imp_RpcServerInterfaceGroupClose
0x18000dc9a  mov     edi, eax
0x18000dc9c  mov     cs:?GPRpcInterfaceGroupCreated@@3HA, 0; int GPRpcInterfaceGroupCreated
0x18000dca6  mov     rcx, [rbx+18h]; hMem
0x18000dcaa  call    cs:__imp_LocalFree
0x18000dcb0  test    edi, edi
0x18000dcb2  jnz     short loc_18000DCB7
0x18000dcb4  mov     [rbx+0Ch], edi
0x18000dcb7  mov     cs:?m_instance@CGPRPCServerBase@@1PEAV1@EA, 0; CGPRPCServerBase * CGPRPCServerBase::m_instance
0x18000dcc2  call    ?LogTime@@YAXXZ; LogTime(void)
0x18000dcc7  test    edi, edi
0x18000dcc9  jnz     short loc_18000DCE3
0x18000dccb  mov     rcx, [rbx+40h]; hEvent
0x18000dccf  call    cs:__imp_SetEvent
0x18000dcd5  test    eax, eax
0x18000dcd7  jnz     short loc_18000DCED
0x18000dcd9  call    cs:__imp_GetLastError
0x18000dcdf  test    eax, eax
0x18000dce1  jz      short loc_18000DCED
0x18000dce3  mov     ecx, 4; unsigned int
0x18000dce8  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18000dced  mov     rbx, [rsp+28h+arg_0]
0x18000dcf2  add     rsp, 20h
0x18000dcf6  pop     rdi
0x18000dcf7  retn
```
