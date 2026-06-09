# Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc(void)

- ea: `0x1800c4b1c`
- end: `0x1800c4d60`
- name: `?InitializeRpc@WinRtHost@Service@Inventory@Compat@Windows@@CAXXZ`
- size: `580`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c3c20`

## callees

- `0x18000fc68`
- `0x1800152d0`
- `0x1800c4b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c4b8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c4b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4b74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4b74`
- `RPCRT4!RpcBindingVectorFree` at `0x1800c4b86`
- `RPCRT4!RpcBindingVectorFree` at `0x1800c4c3e`
- `RPCRT4!RpcBindingVectorFree` at `0x1800c4b86`
- `RPCRT4!RpcBindingVectorFree` at `0x1800c4c3e`
- `RPCRT4!RpcServerListen` at `0x1800c4bfe`
- `RPCRT4!RpcServerListen` at `0x1800c4bfe`
- `RPCRT4!RpcEpRegisterW` at `0x1800c4bc4`
- `RPCRT4!RpcEpRegisterW` at `0x1800c4bc4`
- `RPCRT4!RpcServerInqBindings` at `0x1800c4ba2`
- `RPCRT4!RpcServerInqBindings` at `0x1800c4ba2`
- `RPCRT4!RpcServerRegisterIf` at `0x1800c4b5a`
- `RPCRT4!RpcServerRegisterIf` at `0x1800c4b5a`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800c4b3e`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800c4b3e`

## string_xrefs

- `0x1800c4c7e`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c4cb6`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c4cee`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c4d1f`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c4d50`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c4bcc`: `Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc`
- `0x1800c4c06`: `Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc`
- `0x1800c4c67`: `Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc`
- `0x1800c4c9f`: `Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc`
- `0x1800c4cd7`: `Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc`

## pseudocode

```c
void Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc(void)
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  RPC_BINDING_VECTOR *v4; // rdi
  DWORD LastError; // ebx
  RPC_STATUS v6; // eax
  unsigned int v7; // ebx
  RPC_STATUS v8; // eax
  unsigned int v9; // ebx
  RPC_STATUS v10; // eax
  unsigned int v11; // ebx
  const char *v12; // rax
  const char *v13; // rax
  unsigned int v14; // [rsp+20h] [rbp-28h]
  unsigned int v15; // [rsp+20h] [rbp-28h]
  unsigned int v16; // [rsp+20h] [rbp-28h]
  unsigned int v17; // [rsp+20h] [rbp-28h]
  unsigned int v18; // [rsp+20h] [rbp-28h]
  wil::ResultException *v19; // [rsp+30h] [rbp-18h] BYREF
  std::exception *v20; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  RPC_BINDING_VECTOR *v22; // [rsp+50h] [rbp+8h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+58h] [rbp+10h] BYREF

  v22 = 0;
  v0 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0x4D2u, 0);
  try
  {
    v1 = v0;
    if ( v0 )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc", 105, "failed [%#x]", v0);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
        (const char *)v1,
        v14);
    }
    v2 = RpcServerRegisterIf(qword_1800D50C0, 0, 0);
    v3 = v2;
    if ( v2 )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc", 107, "failed [%#x]", v2);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
        (const char *)v3,
        v15);
    }
    v4 = v22;
    if ( v22 )
    {
      LastError = GetLastError();
      BindingVector = v4;
      RpcBindingVectorFree(&BindingVector);
      SetLastError(LastError);
    }
    v22 = 0;
    v6 = RpcServerInqBindings(&v22);
    v7 = v6;
    if ( v6 )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc", 109, "failed [%#x]", v6);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
        (const char *)v7,
        v16);
    }
    v8 = RpcEpRegisterW(qword_1800D50C0, v22, 0, 0);
    v9 = v8;
    if ( v8 )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc", 111, "failed [%#x]", v8);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
        (const char *)v9,
        v17);
    }
    AslLogCallPrintf(3, "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc", 113, "Calling RpcServerListen");
    v10 = RpcServerListen(1u, 0x4D2u, 0);
    v11 = v10;
    if ( v10 )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc", 114, "failed [%#x]", v10);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
        (const char *)v11,
        v18);
    }
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc",
      115,
      "RpcServerListen returned");
    if ( v22 )
    {
      BindingVector = v22;
      RpcBindingVectorFree(&BindingVector);
    }
  }
  catch ( wil::ResultException *v19 )
  {
    v12 = (const char *)(*(__int64 (__fastcall **)(wil::ResultException *))(*(_QWORD *)v19 + 8LL))(v19);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc",
      119,
      "Exception caught: %s",
      v12);
    return;
  }
  catch ( std::exception *v20 )
  {
    v13 = (const char *)(*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v20 + 8LL))(v20);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc",
      123,
      "Exception caught: %s",
      v13);
    return;
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::InitializeRpc", 127, "Unknown exception");
  }
}

```

## disassembly

```asm
0x1800c4b1c  mov     [rsp+arg_10], rbx
0x1800c4b21  push    rdi
0x1800c4b22  sub     rsp, 40h
0x1800c4b26  mov     [rsp+48h+arg_0], 0
0x1800c4b2f  xor     r8d, r8d; SecurityDescriptor
0x1800c4b32  mov     edx, 4D2h; MaxCalls
0x1800c4b37  lea     rcx, Protseq; "ncalrpc"
0x1800c4b3e  call    cs:__imp_RpcServerUseProtseqW
0x1800c4b44  mov     ebx, eax
0x1800c4b46  test    eax, eax
0x1800c4b48  jnz     loc_1800C4C54
0x1800c4b4e  xor     r8d, r8d; MgrEpv
0x1800c4b51  xor     edx, edx; MgrTypeUuid
0x1800c4b53  lea     rcx, qword_1800D50C0; IfSpec
0x1800c4b5a  call    cs:__imp_RpcServerRegisterIf
0x1800c4b60  mov     ebx, eax
0x1800c4b62  test    eax, eax
0x1800c4b64  jnz     loc_1800C4C8C
0x1800c4b6a  mov     rdi, [rsp+48h+arg_0]
0x1800c4b6f  test    rdi, rdi
0x1800c4b72  jz      short loc_1800C4B94
0x1800c4b74  call    cs:__imp_GetLastError
0x1800c4b7a  mov     ebx, eax
0x1800c4b7c  mov     [rsp+48h+BindingVector], rdi
0x1800c4b81  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x1800c4b86  call    cs:__imp_RpcBindingVectorFree
0x1800c4b8c  mov     ecx, ebx; dwErrCode
0x1800c4b8e  call    cs:__imp_SetLastError
0x1800c4b94  mov     [rsp+48h+arg_0], 0
0x1800c4b9d  lea     rcx, [rsp+48h+arg_0]; BindingVector
0x1800c4ba2  call    cs:__imp_RpcServerInqBindings
0x1800c4ba8  mov     ebx, eax
0x1800c4baa  test    eax, eax
0x1800c4bac  jnz     loc_1800C4CC4
0x1800c4bb2  xor     r9d, r9d; Annotation
0x1800c4bb5  xor     r8d, r8d; UuidVector
0x1800c4bb8  mov     rdx, [rsp+48h+arg_0]; BindingVector
0x1800c4bbd  lea     rcx, qword_1800D50C0; IfSpec
0x1800c4bc4  call    cs:__imp_RpcEpRegisterW
0x1800c4bca  mov     ebx, eax
0x1800c4bcc  lea     rdx, aWindowsCompatI_83; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4bd3  test    eax, eax
0x1800c4bd5  jnz     loc_1800C4CFC
0x1800c4bdb  lea     r9, aCallingRpcserv; "Calling RpcServerListen"
0x1800c4be2  mov     r8d, 71h ; 'q'
0x1800c4be8  lea     edi, [r8-6Eh]
0x1800c4bec  mov     ecx, edi
0x1800c4bee  call    AslLogCallPrintf
0x1800c4bf3  xor     r8d, r8d; DontWait
0x1800c4bf6  mov     edx, 4D2h; MaxCalls
0x1800c4bfb  lea     ecx, [rdi-2]; MinimumCallThreads
0x1800c4bfe  call    cs:__imp_RpcServerListen
0x1800c4c04  mov     ebx, eax
0x1800c4c06  lea     rdx, aWindowsCompatI_83; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4c0d  test    eax, eax
0x1800c4c0f  jnz     loc_1800C4D2D
0x1800c4c15  lea     r9, aRpcserverliste; "RpcServerListen returned"
0x1800c4c1c  mov     r8d, 73h ; 's'
0x1800c4c22  mov     ecx, edi
0x1800c4c24  call    AslLogCallPrintf
0x1800c4c29  nop
0x1800c4c2a  mov     rax, [rsp+48h+arg_0]
0x1800c4c2f  test    rax, rax
0x1800c4c32  jz      short loc_1800C4C45
0x1800c4c34  mov     [rsp+48h+BindingVector], rax
0x1800c4c39  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x1800c4c3e  call    cs:__imp_RpcBindingVectorFree
0x1800c4c44  nop
0x1800c4c45  mov     rbx, [rsp+48h+arg_10]
0x1800c4c4a  add     rsp, 40h
0x1800c4c4e  pop     rdi
0x1800c4c4f  retn
0x1800c4c50  jmp     short loc_1800C4C45
0x1800c4c52  jmp     short loc_1800C4C45
0x1800c4c54  mov     [rsp+48h+var_28], eax; unsigned int
0x1800c4c58  lea     r9, aFailedX; "failed [%#x]"
0x1800c4c5f  mov     edi, 69h ; 'i'
0x1800c4c64  mov     r8d, edi
0x1800c4c67  lea     rdx, aWindowsCompatI_83; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4c6e  lea     ecx, [rdi-68h]
0x1800c4c71  call    AslLogCallPrintf
0x1800c4c76  mov     rcx, [rsp+48h]; this
0x1800c4c7b  mov     r9d, ebx; char *
0x1800c4c7e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c4c85  mov     edx, edi; void *
0x1800c4c87  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800c4c8c  mov     [rsp+48h+var_28], eax; unsigned int
0x1800c4c90  lea     r9, aFailedX; "failed [%#x]"
0x1800c4c97  mov     edi, 6Bh ; 'k'
0x1800c4c9c  mov     r8d, edi
0x1800c4c9f  lea     rdx, aWindowsCompatI_83; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4ca6  lea     ecx, [rdi-6Ah]
0x1800c4ca9  call    AslLogCallPrintf
0x1800c4cae  mov     rcx, [rsp+48h]; this
0x1800c4cb3  mov     r9d, ebx; char *
0x1800c4cb6  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c4cbd  mov     edx, edi; void *
0x1800c4cbf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800c4cc4  mov     [rsp+48h+var_28], eax; unsigned int
0x1800c4cc8  lea     r9, aFailedX; "failed [%#x]"
0x1800c4ccf  mov     edi, 6Dh ; 'm'
0x1800c4cd4  mov     r8d, edi
0x1800c4cd7  lea     rdx, aWindowsCompatI_83; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4cde  lea     ecx, [rdi-6Ch]
0x1800c4ce1  call    AslLogCallPrintf
0x1800c4ce6  mov     rcx, [rsp+48h]; this
0x1800c4ceb  mov     r9d, ebx; char *
0x1800c4cee  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c4cf5  mov     edx, edi; void *
0x1800c4cf7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800c4cfc  mov     [rsp+48h+var_28], eax; unsigned int
0x1800c4d00  lea     r9, aFailedX; "failed [%#x]"
0x1800c4d07  mov     edi, 6Fh ; 'o'
0x1800c4d0c  mov     r8d, edi
0x1800c4d0f  lea     ecx, [rdi-6Eh]
0x1800c4d12  call    AslLogCallPrintf
0x1800c4d17  mov     rcx, [rsp+48h]; this
0x1800c4d1c  mov     r9d, ebx; char *
0x1800c4d1f  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c4d26  mov     edx, edi; void *
0x1800c4d28  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800c4d2d  mov     [rsp+48h+var_28], eax; unsigned int
0x1800c4d31  lea     r9, aFailedX; "failed [%#x]"
0x1800c4d38  mov     edi, 72h ; 'r'
0x1800c4d3d  mov     r8d, edi
0x1800c4d40  lea     ecx, [rdi-71h]
0x1800c4d43  call    AslLogCallPrintf
0x1800c4d48  mov     rcx, [rsp+48h]; this
0x1800c4d4d  mov     r9d, ebx; char *
0x1800c4d50  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c4d57  mov     edx, edi; void *
0x1800c4d59  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
