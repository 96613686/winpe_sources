# SmartCardCertsNotifyService

- ea: `0x18002cc98`
- end: `0x18002ce28`
- name: `SmartCardCertsNotifyService`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012fa0`

## callees

- `0x18002cc98`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ccfb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cd13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cd2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ccfb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cd13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002cd2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ccd1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ccd1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ce0a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002ce0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cce4`
- `RPCRT4!NdrClientCall3` at `0x18002cdad`
- `RPCRT4!NdrClientCall3` at `0x18002cdad`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002daf8`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002daf8`

## string_xrefs

- `0x18002ccca`: `rpcrt4.dll`
- `0x18002ccf1`: `RpcBindingCreateW`

## pseudocode

```c
__int64 __fastcall SmartCardCertsNotifyService(__int64 a1)
{
  FARPROC v2; // rsi
  HMODULE Library; // rax
  HMODULE v4; // rdi
  DWORD Pointer; // ebx
  FARPROC ProcAddress; // rbx
  FARPROC v7; // r14
  CLIENT_CALL_RETURN v8; // rax
  __int64 v10; // [rsp+78h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v11; // [rsp+80h] [rbp+18h]

  v10 = 0;
  v2 = 0;
  Library = LoadLibraryExA("rpcrt4.dll", 0, 0);
  v4 = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "RpcBindingCreateW")) != 0
    && (v7 = GetProcAddress(v4, "RpcBindingBind")) != 0
    && (v2 = GetProcAddress(v4, "RpcBindingFree")) != 0 )
  {
    Pointer = ((__int64 (__fastcall *)(struct _RPC_BINDING_HANDLE_TEMPLATE_V1_W *, struct _RPC_BINDING_HANDLE_SECURITY_V1_W *, struct _RPC_BINDING_HANDLE_OPTIONS_V1 *, __int64 *))ProcAddress)(
                &ROOTRPC_Template,
                &ROOTRPC_Security,
                &ROOTRPC_Options,
                &v10);
    if ( !Pointer )
    {
      Pointer = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))v7)(0, v10, qword_18002FE80);
      if ( !Pointer )
      {
        v11.Simple = 0;
        v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v10, a1).Pointer;
        Pointer = (DWORD)v8.Pointer;
        v11.Pointer = v8.Pointer;
      }
    }
  }
  else
  {
    Pointer = GetLastError();
  }
  if ( v10 )
  {
    ((void (__fastcall *)(__int64 *))v2)(&v10);
    if ( v10 )
      ((void (__fastcall *)(__int64 *))v2)(&v10);
  }
  if ( v4 )
    FreeLibrary(v4);
  return Pointer;
}

```

## disassembly

```asm
0x18002cc98  mov     rax, rsp
0x18002cc9b  mov     [rax+8], rbx
0x18002cc9f  mov     [rax+20h], rsi
0x18002cca3  push    rdi
0x18002cca4  push    r14
0x18002cca6  push    r15
0x18002cca8  sub     rsp, 50h
0x18002ccac  mov     r15, rcx
0x18002ccaf  mov     qword ptr [rax+10h], 0
0x18002ccb7  mov     qword ptr [rax-30h], 0
0x18002ccbf  xor     esi, esi
0x18002ccc1  mov     [rax-28h], rsi
0x18002ccc5  xor     r8d, r8d; dwFlags
0x18002ccc8  xor     edx, edx; hFile
0x18002ccca  lea     rcx, LibFileName; "rpcrt4.dll"
0x18002ccd1  call    cs:__imp_LoadLibraryExA
0x18002ccd7  mov     rdi, rax
0x18002ccda  mov     [rsp+68h+var_30], rax
0x18002ccdf  test    rax, rax
0x18002cce2  jnz     short loc_18002CCF1
0x18002cce4  call    cs:__imp_GetLastError
0x18002ccea  mov     ebx, eax
0x18002ccec  jmp     loc_18002CDBE
0x18002ccf1  lea     rdx, aRpcbindingcrea; "RpcBindingCreateW"
0x18002ccf8  mov     rcx, rdi; hModule
0x18002ccfb  call    cs:__imp_GetProcAddress
0x18002cd01  mov     rbx, rax
0x18002cd04  test    rax, rax
0x18002cd07  jz      short loc_18002CCE4
0x18002cd09  lea     rdx, aRpcbindingbind; "RpcBindingBind"
0x18002cd10  mov     rcx, rdi; hModule
0x18002cd13  call    cs:__imp_GetProcAddress
0x18002cd19  mov     r14, rax
0x18002cd1c  test    rax, rax
0x18002cd1f  jz      short loc_18002CCE4
0x18002cd21  lea     rdx, aRpcbindingfree; "RpcBindingFree"
0x18002cd28  mov     rcx, rdi; hModule
0x18002cd2b  call    cs:__imp_GetProcAddress
0x18002cd31  mov     rsi, rax
0x18002cd34  mov     [rsp+68h+var_28], rax
0x18002cd39  test    rax, rax
0x18002cd3c  jz      short loc_18002CCE4
0x18002cd3e  lea     r9, [rsp+68h+arg_8]
0x18002cd43  lea     r8, ?ROOTRPC_Options@@3U_RPC_BINDING_HANDLE_OPTIONS_V1@@A; _RPC_BINDING_HANDLE_OPTIONS_V1 ROOTRPC_Options
0x18002cd4a  lea     rdx, ?ROOTRPC_Security@@3U_RPC_BINDING_HANDLE_SECURITY_V1_W@@A; _RPC_BINDING_HANDLE_SECURITY_V1_W ROOTRPC_Security
0x18002cd51  lea     rcx, ?ROOTRPC_Template@@3U_RPC_BINDING_HANDLE_TEMPLATE_V1_W@@A; _RPC_BINDING_HANDLE_TEMPLATE_V1_W ROOTRPC_Template
0x18002cd58  mov     rax, rbx
0x18002cd5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd60  mov     ebx, eax
0x18002cd62  mov     [rsp+68h+var_38], eax
0x18002cd66  test    eax, eax
0x18002cd68  jnz     short loc_18002CDC2
0x18002cd6a  lea     r8, qword_18002FE80
0x18002cd71  mov     rdx, [rsp+68h+arg_8]
0x18002cd76  xor     ecx, ecx
0x18002cd78  mov     rax, r14
0x18002cd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd80  mov     ebx, eax
0x18002cd82  mov     [rsp+68h+var_38], eax
0x18002cd86  test    eax, eax
0x18002cd88  jnz     short loc_18002CDC2
0x18002cd8a  mov     [rsp+68h+arg_10], 0
0x18002cd96  mov     [rsp+68h+var_48], r15
0x18002cd9b  mov     r9, [rsp+68h+arg_8]
0x18002cda0  xor     r8d, r8d; pReturnValue
0x18002cda3  lea     edx, [rax+1]; nProcNum
0x18002cda6  lea     rcx, pProxyInfo; pProxyInfo
0x18002cdad  call    cs:__imp_NdrClientCall3
0x18002cdb3  mov     rbx, rax
0x18002cdb6  mov     [rsp+68h+arg_10], rax
0x18002cdbe  mov     [rsp+68h+var_38], eax
0x18002cdc2  jmp     short loc_18002CDD4
0x18002cdc4  mov     ebx, eax
0x18002cdc6  mov     [rsp+68h+var_38], eax
0x18002cdca  mov     rdi, [rsp+68h+var_30]
0x18002cdcf  mov     rsi, [rsp+68h+var_28]
0x18002cdd4  mov     rax, [rsp+68h+arg_8]
0x18002cdd9  test    rax, rax
0x18002cddc  jz      short loc_18002CE02
0x18002cdde  lea     rcx, [rsp+68h+arg_8]
0x18002cde3  mov     rax, rsi
0x18002cde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdeb  mov     rax, [rsp+68h+arg_8]
0x18002cdf0  test    rax, rax
0x18002cdf3  jz      short loc_18002CE02
0x18002cdf5  lea     rcx, [rsp+68h+arg_8]
0x18002cdfa  mov     rax, rsi
0x18002cdfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce02  test    rdi, rdi
0x18002ce05  jz      short loc_18002CE10
0x18002ce07  mov     rcx, rdi; hLibModule
0x18002ce0a  call    cs:__imp_FreeLibrary
0x18002ce10  mov     eax, ebx
0x18002ce12  lea     r11, [rsp+68h+var_18]
0x18002ce17  mov     rbx, [r11+20h]
0x18002ce1b  mov     rsi, [r11+38h]
0x18002ce1f  mov     rsp, r11
0x18002ce22  pop     r15
0x18002ce24  pop     r14
0x18002ce26  pop     rdi
0x18002ce27  retn
0x18002daea  push    rbp
0x18002daec  sub     rsp, 30h
0x18002daf0  mov     rbp, rdx
0x18002daf3  mov     rcx, [rcx]
0x18002daf6  mov     ecx, [rcx]; ExceptionCode
0x18002daf8  call    cs:__imp_I_RpcExceptionFilter
0x18002dafe  nop
0x18002daff  add     rsp, 30h
0x18002db03  pop     rbp
0x18002db04  retn
```
