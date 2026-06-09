# SmartCardCertsNotifyService

- ea: `0x1800aacb0`
- end: `0x1800aae40`
- name: `SmartCardCertsNotifyService`
- size: `400`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003f230`

## callees

- `0x1800aacb0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800aace9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800aace9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800aae22`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800aae22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aad13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aad2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aad43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aad13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aad2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aad43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aacfc`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800cbea5`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800cbea5`
- `RPCRT4!NdrClientCall3` at `0x1800aadc5`
- `RPCRT4!NdrClientCall3` at `0x1800aadc5`

## string_xrefs

- `0x1800aace2`: `rpcrt4.dll`
- `0x1800aad09`: `RpcBindingCreateW`

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
      Pointer = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))v7)(0, v10, qword_1800D3EF0);
      if ( !Pointer )
      {
        v11.Simple = 0;
        v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800D3FF0, 1u, 0, v10, a1).Pointer;
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
0x1800aacb0  mov     rax, rsp
0x1800aacb3  mov     [rax+8], rbx
0x1800aacb7  mov     [rax+20h], rsi
0x1800aacbb  push    rdi
0x1800aacbc  push    r14
0x1800aacbe  push    r15
0x1800aacc0  sub     rsp, 50h
0x1800aacc4  mov     r15, rcx
0x1800aacc7  mov     qword ptr [rax+10h], 0
0x1800aaccf  mov     qword ptr [rax-30h], 0
0x1800aacd7  xor     esi, esi
0x1800aacd9  mov     [rax-28h], rsi
0x1800aacdd  xor     r8d, r8d; dwFlags
0x1800aace0  xor     edx, edx; hFile
0x1800aace2  lea     rcx, LibFileName; "rpcrt4.dll"
0x1800aace9  call    cs:__imp_LoadLibraryExA
0x1800aacef  mov     rdi, rax
0x1800aacf2  mov     [rsp+68h+var_30], rax
0x1800aacf7  test    rax, rax
0x1800aacfa  jnz     short loc_1800AAD09
0x1800aacfc  call    cs:__imp_GetLastError
0x1800aad02  mov     ebx, eax
0x1800aad04  jmp     loc_1800AADD6
0x1800aad09  lea     rdx, aRpcbindingcrea_0; "RpcBindingCreateW"
0x1800aad10  mov     rcx, rdi; hModule
0x1800aad13  call    cs:__imp_GetProcAddress
0x1800aad19  mov     rbx, rax
0x1800aad1c  test    rax, rax
0x1800aad1f  jz      short loc_1800AACFC
0x1800aad21  lea     rdx, aRpcbindingbind_0; "RpcBindingBind"
0x1800aad28  mov     rcx, rdi; hModule
0x1800aad2b  call    cs:__imp_GetProcAddress
0x1800aad31  mov     r14, rax
0x1800aad34  test    rax, rax
0x1800aad37  jz      short loc_1800AACFC
0x1800aad39  lea     rdx, aRpcbindingfree_0; "RpcBindingFree"
0x1800aad40  mov     rcx, rdi; hModule
0x1800aad43  call    cs:__imp_GetProcAddress
0x1800aad49  mov     rsi, rax
0x1800aad4c  mov     [rsp+68h+var_28], rax
0x1800aad51  test    rax, rax
0x1800aad54  jz      short loc_1800AACFC
0x1800aad56  lea     r9, [rsp+68h+arg_8]
0x1800aad5b  lea     r8, ?ROOTRPC_Options@@3U_RPC_BINDING_HANDLE_OPTIONS_V1@@A; _RPC_BINDING_HANDLE_OPTIONS_V1 ROOTRPC_Options
0x1800aad62  lea     rdx, ?ROOTRPC_Security@@3U_RPC_BINDING_HANDLE_SECURITY_V1_W@@A; _RPC_BINDING_HANDLE_SECURITY_V1_W ROOTRPC_Security
0x1800aad69  lea     rcx, ?ROOTRPC_Template@@3U_RPC_BINDING_HANDLE_TEMPLATE_V1_W@@A; _RPC_BINDING_HANDLE_TEMPLATE_V1_W ROOTRPC_Template
0x1800aad70  mov     rax, rbx
0x1800aad73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aad78  mov     ebx, eax
0x1800aad7a  mov     [rsp+68h+var_38], eax
0x1800aad7e  test    eax, eax
0x1800aad80  jnz     short loc_1800AADDA
0x1800aad82  lea     r8, qword_1800D3EF0
0x1800aad89  mov     rdx, [rsp+68h+arg_8]
0x1800aad8e  xor     ecx, ecx
0x1800aad90  mov     rax, r14
0x1800aad93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aad98  mov     ebx, eax
0x1800aad9a  mov     [rsp+68h+var_38], eax
0x1800aad9e  test    eax, eax
0x1800aada0  jnz     short loc_1800AADDA
0x1800aada2  mov     [rsp+68h+arg_10], 0
0x1800aadae  mov     [rsp+68h+var_48], r15
0x1800aadb3  mov     r9, [rsp+68h+arg_8]
0x1800aadb8  xor     r8d, r8d; pReturnValue
0x1800aadbb  lea     edx, [rax+1]; nProcNum
0x1800aadbe  lea     rcx, stru_1800D3FF0; pProxyInfo
0x1800aadc5  call    cs:__imp_NdrClientCall3
0x1800aadcb  mov     rbx, rax
0x1800aadce  mov     [rsp+68h+arg_10], rax
0x1800aadd6  mov     [rsp+68h+var_38], eax
0x1800aadda  jmp     short loc_1800AADEC
0x1800aaddc  mov     ebx, eax
0x1800aadde  mov     [rsp+68h+var_38], eax
0x1800aade2  mov     rdi, [rsp+68h+var_30]
0x1800aade7  mov     rsi, [rsp+68h+var_28]
0x1800aadec  mov     rax, [rsp+68h+arg_8]
0x1800aadf1  test    rax, rax
0x1800aadf4  jz      short loc_1800AAE1A
0x1800aadf6  lea     rcx, [rsp+68h+arg_8]
0x1800aadfb  mov     rax, rsi
0x1800aadfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aae03  mov     rax, [rsp+68h+arg_8]
0x1800aae08  test    rax, rax
0x1800aae0b  jz      short loc_1800AAE1A
0x1800aae0d  lea     rcx, [rsp+68h+arg_8]
0x1800aae12  mov     rax, rsi
0x1800aae15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aae1a  test    rdi, rdi
0x1800aae1d  jz      short loc_1800AAE28
0x1800aae1f  mov     rcx, rdi; hLibModule
0x1800aae22  call    cs:__imp_FreeLibrary
0x1800aae28  mov     eax, ebx
0x1800aae2a  lea     r11, [rsp+68h+var_18]
0x1800aae2f  mov     rbx, [r11+20h]
0x1800aae33  mov     rsi, [r11+38h]
0x1800aae37  mov     rsp, r11
0x1800aae3a  pop     r15
0x1800aae3c  pop     r14
0x1800aae3e  pop     rdi
0x1800aae3f  retn
0x1800cbe97  push    rbp
0x1800cbe99  sub     rsp, 30h
0x1800cbe9d  mov     rbp, rdx
0x1800cbea0  mov     rcx, [rcx]
0x1800cbea3  mov     ecx, [rcx]; ExceptionCode
0x1800cbea5  call    cs:__imp_I_RpcExceptionFilter
0x1800cbeab  nop
0x1800cbeac  add     rsp, 30h
0x1800cbeb0  pop     rbp
0x1800cbeb1  retn
```
