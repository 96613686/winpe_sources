# CDsmControl::SetInstallBehavior(DSM_DEVICE_OBJECT_TYPE,ushort const *,DSM_INSTALL_BEHAVIOR_FLAGS)

- ea: `0x18000b4c0`
- end: `0x18000b5aa`
- name: `?SetInstallBehavior@CDsmControl@@UEAAJW4DSM_DEVICE_OBJECT_TYPE@@PEBGW4DSM_INSTALL_BEHAVIOR_FLAGS@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, __int64, const OLECHAR *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180009d20`
- `0x18000b4c0`
- `0x18000d524`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18000e6d9`
- `RPCRT4!RpcExceptionFilter` at `0x18000e6e1`
- `RPCRT4!RpcExceptionFilter` at `0x18000e6d9`
- `RPCRT4!RpcExceptionFilter` at `0x18000e6e1`
- `RPCRT4!NdrClientCall3` at `0x18000b52f`
- `RPCRT4!NdrClientCall3` at `0x18000b52f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b4f1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b4f1`

## pseudocode

```c
__int64 __fastcall CDsmControl::SetInstallBehavior(__int64 a1, __int64 a2, const OLECHAR *a3, int a4)
{
  HRESULT Pointer; // ebx
  GUID pclsid; // [rsp+40h] [rbp-28h] BYREF

  pclsid = 0;
  Pointer = CLSIDFromString(a3, &pclsid);
  if ( Pointer >= 0 )
  {
    StartDsmService();
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_1800116C0,
                              2u,
                              0,
                              DsmRpcControl_v1_0_c_ifspec,
                              &pclsid,
                              a4,
                              Pointer,
                              0).Pointer;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_6c51682e99e93bfa9299cbf564496992_Traceguids,
      (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000b4c0  mov     [rsp+arg_0], rbx
0x18000b4c5  mov     [rsp+arg_8], rsi
0x18000b4ca  push    rdi
0x18000b4cb  sub     rsp, 60h
0x18000b4cf  mov     rax, cs:__security_cookie
0x18000b4d6  xor     rax, rsp
0x18000b4d9  mov     [rsp+68h+var_18], rax
0x18000b4de  mov     esi, r9d
0x18000b4e1  xorps   xmm0, xmm0
0x18000b4e4  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x18000b4e9  lea     rdx, [rsp+68h+pclsid]; pclsid
0x18000b4ee  mov     rcx, r8; lpsz
0x18000b4f1  call    cs:__imp_CLSIDFromString
0x18000b4f7  mov     ebx, eax
0x18000b4f9  mov     [rsp+68h+var_38], eax
0x18000b4fd  test    eax, eax
0x18000b4ff  js      short loc_18000B55A
0x18000b501  call    ?StartDsmService@@YAJXZ; StartDsmService(void)
0x18000b506  xor     edi, edi
0x18000b508  mov     [rsp+68h+var_30], rdi
0x18000b50d  mov     [rsp+68h+var_40], esi
0x18000b511  lea     rax, [rsp+68h+pclsid]
0x18000b516  mov     [rsp+68h+var_48], rax
0x18000b51b  mov     r9, cs:DsmRpcControl_v1_0_c_ifspec
0x18000b522  xor     r8d, r8d; pReturnValue
0x18000b525  lea     edx, [rdi+2]; nProcNum
0x18000b528  lea     rcx, stru_1800116C0; pProxyInfo
0x18000b52f  call    cs:__imp_NdrClientCall3
0x18000b535  mov     rbx, rax
0x18000b538  mov     [rsp+68h+var_30], rax
0x18000b53d  mov     [rsp+68h+var_38], eax
0x18000b541  jmp     short loc_18000B549
0x18000b543  mov     edi, eax
0x18000b545  mov     ebx, [rsp+68h+var_38]
0x18000b549  test    edi, edi
0x18000b54b  jz      short loc_18000B55A
0x18000b54d  jle     short loc_18000B558
0x18000b54f  movzx   edi, di
0x18000b552  or      edi, 80070000h
0x18000b558  mov     ebx, edi
0x18000b55a  lea     rax, WPP_GLOBAL_Control
0x18000b561  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b568  cmp     rcx, rax
0x18000b56b  jz      short loc_18000B58B
0x18000b56d  test    byte ptr [rcx+1Ch], 1
0x18000b571  jz      short loc_18000B58B
0x18000b573  mov     edx, 0Bh
0x18000b578  mov     r9d, ebx
0x18000b57b  lea     r8, WPP_6c51682e99e93bfa9299cbf564496992_Traceguids
0x18000b582  mov     rcx, [rcx+10h]
0x18000b586  call    WPP_SF_D
0x18000b58b  mov     eax, ebx
0x18000b58d  mov     rcx, [rsp+68h+var_18]
0x18000b592  xor     rcx, rsp; StackCookie
0x18000b595  call    __security_check_cookie
0x18000b59a  mov     rbx, [rsp+68h+arg_0]
0x18000b59f  mov     rsi, [rsp+68h+arg_8]
0x18000b5a4  add     rsp, 60h
0x18000b5a8  pop     rdi
0x18000b5a9  retn
0x18000e6cb  push    rbp
0x18000e6cd  sub     rsp, 30h
0x18000e6d1  mov     rbp, rdx
0x18000e6d4  mov     rcx, [rcx]
0x18000e6d7  mov     ecx, [rcx]; ExceptionCode
0x18000e6d9  call    cs:__imp_RpcExceptionFilter
0x18000e6df  mov     ecx, eax; ExceptionCode
0x18000e6e1  call    cs:__imp_RpcExceptionFilter
0x18000e6e7  nop
0x18000e6e8  add     rsp, 30h
0x18000e6ec  pop     rbp
0x18000e6ed  retn
```
