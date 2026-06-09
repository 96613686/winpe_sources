# CDsmControl::Refresh(ushort const *,DSM_REFRESH_TYPE)

- ea: `0x18000b000`
- end: `0x18000b0a8`
- name: `?Refresh@CDsmControl@@UEAAJPEBGW4DSM_REFRESH_TYPE@@@Z`
- size: `168`
- prototype: `HRESULT __fastcall(__int64, const OLECHAR *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800017c0`
- `0x18000b000`
- `0x18000d524`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b068`
- `RPCRT4!NdrClientCall3` at `0x18000b068`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b02c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b02c`

## pseudocode

```c
HRESULT __fastcall CDsmControl::Refresh(__int64 a1, const OLECHAR *a2, int a3)
{
  HRESULT result; // eax
  HRESULT v5; // [rsp+30h] [rbp-38h]
  GUID pclsid; // [rsp+40h] [rbp-28h] BYREF

  pclsid = 0;
  result = CLSIDFromString(a2, &pclsid);
  v5 = result;
  if ( result >= 0 )
  {
    StartDsmService();
    return (unsigned int)NdrClientCall3(
                           (MIDL_STUBLESS_PROXY_INFO *)&stru_1800116C0,
                           1u,
                           0,
                           DsmRpcControl_v1_0_c_ifspec,
                           &pclsid,
                           a3,
                           v5,
                           0).Pointer;
  }
  return result;
}

```

## disassembly

```asm
0x18000b000  mov     [rsp+arg_0], rbx
0x18000b005  push    rdi
0x18000b006  sub     rsp, 60h
0x18000b00a  mov     rax, cs:__security_cookie
0x18000b011  xor     rax, rsp
0x18000b014  mov     [rsp+68h+var_18], rax
0x18000b019  mov     edi, r8d
0x18000b01c  mov     rcx, rdx; lpsz
0x18000b01f  xorps   xmm0, xmm0
0x18000b022  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x18000b027  lea     rdx, [rsp+68h+pclsid]; pclsid
0x18000b02c  call    cs:__imp_CLSIDFromString
0x18000b032  mov     [rsp+68h+var_38], eax
0x18000b036  test    eax, eax
0x18000b038  js      short loc_18000B090
0x18000b03a  call    ?StartDsmService@@YAJXZ; StartDsmService(void)
0x18000b03f  xor     ebx, ebx
0x18000b041  mov     [rsp+68h+var_30], rbx
0x18000b046  mov     [rsp+68h+var_40], edi
0x18000b04a  lea     rax, [rsp+68h+pclsid]
0x18000b04f  mov     [rsp+68h+var_48], rax
0x18000b054  mov     r9, cs:DsmRpcControl_v1_0_c_ifspec
0x18000b05b  xor     r8d, r8d; pReturnValue
0x18000b05e  lea     edx, [rbx+1]; nProcNum
0x18000b061  lea     rcx, stru_1800116C0; pProxyInfo
0x18000b068  call    cs:__imp_NdrClientCall3
0x18000b06e  mov     [rsp+68h+var_30], rax
0x18000b073  mov     [rsp+68h+var_38], eax
0x18000b077  jmp     short loc_18000B07F
0x18000b079  mov     ebx, eax
0x18000b07b  mov     eax, [rsp+68h+var_38]
0x18000b07f  test    ebx, ebx
0x18000b081  jz      short loc_18000B090
0x18000b083  jle     short loc_18000B08E
0x18000b085  movzx   ebx, bx
0x18000b088  or      ebx, 80070000h
0x18000b08e  mov     eax, ebx
0x18000b090  mov     rcx, [rsp+68h+var_18]
0x18000b095  xor     rcx, rsp; StackCookie
0x18000b098  call    __security_check_cookie
0x18000b09d  mov     rbx, [rsp+68h+arg_0]
0x18000b0a2  add     rsp, 60h
0x18000b0a6  pop     rdi
0x18000b0a7  retn
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
