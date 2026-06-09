# Container::Manager::Rpc::Server::Shutdown(void)

- ea: `0x18000ef48`
- end: `0x18000eff6`
- name: `?Shutdown@Server@Rpc@Manager@Container@@QEAAXXZ`
- size: `174`
- prototype: `void __fastcall(Container::Manager::Rpc::Server *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008a78`
- `0x18000ef04`

## callees

- `0x18000ef48`
- `0x18000effc`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000ef96`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000ef96`
- `RPCRT4!RpcEpUnregister` at `0x18000ef64`
- `RPCRT4!RpcEpUnregister` at `0x18000ef64`
- `RPCRT4!RpcBindingVectorFree` at `0x18000efc3`
- `RPCRT4!RpcBindingVectorFree` at `0x18000efc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efd1`

## string_xrefs

- `0x18000ef79`: `onecore\base\gendrv\silos\clem\rpc\common\rpcutilities.cpp`

## pseudocode

```c
void __fastcall Container::Manager::Rpc::Server::Shutdown(Container::Manager::Rpc::Server *this)
{
  unsigned int v2; // eax
  RPC_BINDING_VECTOR *v3; // rsi
  DWORD LastError; // eax
  DWORD v5; // ebx
  unsigned int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+30h] [rbp+8h] BYREF

  v2 = RpcEpUnregister(*(RPC_IF_HANDLE *)this, *((RPC_BINDING_VECTOR **)this + 1), 0);
  if ( v2 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\rpc\\common\\rpcutilities.cpp",
      (const char *)v2,
      v6);
  RpcServerUnregisterIfEx(*(RPC_IF_HANDLE *)this, 0, 1);
  v3 = (RPC_BINDING_VECTOR *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    LastError = GetLastError();
    BindingVector = v3;
    v5 = LastError;
    RpcBindingVectorFree(&BindingVector);
    SetLastError(v5);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000ef48  mov     [rsp+arg_8], rbx
0x18000ef4d  mov     [rsp+arg_10], rsi
0x18000ef52  push    rdi; unsigned int
0x18000ef53  sub     rsp, 20h
0x18000ef57  mov     rdx, [rcx+8]; BindingVector
0x18000ef5b  mov     rdi, rcx
0x18000ef5e  mov     rcx, [rcx]; IfSpec
0x18000ef61  xor     r8d, r8d; UuidVector
0x18000ef64  call    cs:__imp_RpcEpUnregister
0x18000ef6b  nop     dword ptr [rax+rax+00h]
0x18000ef70  test    eax, eax
0x18000ef72  jz      short loc_18000EF8D
0x18000ef74  mov     rcx, [rsp+28h]; this
0x18000ef79  lea     r8, aOnecoreBaseGen_9; "onecore\\base\\gendrv\\silos\\clem\\rpc"...
0x18000ef80  mov     r9d, eax; char *
0x18000ef83  mov     edx, 0E5h; void *
0x18000ef88  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000ef8d  mov     rcx, [rdi]; IfSpec
0x18000ef90  xor     edx, edx; MgrTypeUuid
0x18000ef92  lea     r8d, [rdx+1]; RundownContextHandles
0x18000ef96  call    cs:__imp_RpcServerUnregisterIfEx
0x18000ef9d  nop     dword ptr [rax+rax+00h]
0x18000efa2  mov     rsi, [rdi+8]
0x18000efa6  test    rsi, rsi
0x18000efa9  jz      short loc_18000EFDD
0x18000efab  call    cs:__imp_GetLastError
0x18000efb2  nop     dword ptr [rax+rax+00h]
0x18000efb7  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18000efbc  mov     [rsp+28h+BindingVector], rsi
0x18000efc1  mov     ebx, eax
0x18000efc3  call    cs:__imp_RpcBindingVectorFree
0x18000efca  nop     dword ptr [rax+rax+00h]
0x18000efcf  mov     ecx, ebx; dwErrCode
0x18000efd1  call    cs:__imp_SetLastError
0x18000efd8  nop     dword ptr [rax+rax+00h]
0x18000efdd  mov     rbx, [rsp+28h+arg_8]
0x18000efe2  mov     rsi, [rsp+28h+arg_10]
0x18000efe7  mov     qword ptr [rdi+8], 0
0x18000efef  add     rsp, 20h
0x18000eff3  pop     rdi
0x18000eff4  retn
```
