# OnDemandBrokerServerProxy::OdbFtCancelBackgroundTask(void *,ulong,_GUID,bool,_BI_CANCEL_REASON_INTERNAL)

- ea: `0x180004db0`
- end: `0x180004e8f`
- name: `?OdbFtCancelBackgroundTask@OnDemandBrokerServerProxy@@UEAAJPEAXKU_GUID@@_NW4_BI_CANCEL_REASON_INTERNAL@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(__int64, void *, int, _OWORD *, unsigned __int8, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800019d0`
- `0x180004db0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180004e7a`
- `RPCRT4!RpcBindingFree` at `0x180004e7a`
- `RPCRT4!NdrClientCall3` at `0x180004e47`
- `RPCRT4!NdrClientCall3` at `0x180004e47`
- `RPCRT4!I_RpcExceptionFilter` at `0x180006a7d`
- `RPCRT4!I_RpcExceptionFilter` at `0x180006a7d`
- `ntdll!RtlLengthSid` at `0x180004ded`
- `ntdll!RtlLengthSid` at `0x180004ded`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::OdbFtCancelBackgroundTask(
        __int64 a1,
        void *a2,
        int a3,
        _OWORD *a4,
        unsigned __int8 a5,
        int a6)
{
  int Pointer; // ebx
  ULONG v10; // eax
  CLIENT_CALL_RETURN v11; // rax
  ULONG v13; // [rsp+20h] [rbp-88h]
  int v14; // [rsp+30h] [rbp-78h]
  int v15; // [rsp+40h] [rbp-68h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+60h] [rbp-48h]
  _OWORD v19[3]; // [rsp+70h] [rbp-38h] BYREF

  Binding = 0;
  Pointer = OdbpCreateRpcBinding(qword_180008210, &Binding);
  if ( Pointer >= 0 )
  {
    v10 = RtlLengthSid(a2);
    v18.Simple = 0;
    v19[0] = *a4;
    v15 = a5;
    v14 = a3;
    v13 = v10;
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, Binding, v13, a2, v14, v19, v15, a6).Pointer;
    Pointer = (int)v11.Pointer;
    v18.Pointer = v11.Pointer;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180004db0  push    rbx
0x180004db2  push    rsi
0x180004db3  push    rdi
0x180004db4  push    r14
0x180004db6  sub     rsp, 88h
0x180004dbd  mov     rsi, r9
0x180004dc0  mov     r14d, r8d
0x180004dc3  mov     rdi, rdx
0x180004dc6  mov     [rsp+0A8h+Binding], 0
0x180004dcf  lea     rdx, [rsp+0A8h+Binding]; void **
0x180004dd4  lea     rcx, qword_180008210; IfSpec
0x180004ddb  call    ?OdbpCreateRpcBinding@@YAJPEAXPEAPEAX@Z; OdbpCreateRpcBinding(void *,void * *)
0x180004de0  mov     ebx, eax
0x180004de2  test    eax, eax
0x180004de4  js      loc_180004E6D
0x180004dea  mov     rcx, rdi; Sid
0x180004ded  call    cs:__imp_RtlLengthSid
0x180004df3  mov     [rsp+0A8h+var_48], 0
0x180004dfc  movups  xmm0, xmmword ptr [rsi]
0x180004dff  movdqu  [rsp+0A8h+var_38], xmm0
0x180004e05  movzx   edx, [rsp+0A8h+arg_20]
0x180004e0d  mov     ecx, [rsp+0A8h+arg_28]
0x180004e14  mov     [rsp+0A8h+var_60], ecx
0x180004e18  mov     [rsp+0A8h+var_68], edx
0x180004e1c  lea     rcx, [rsp+0A8h+var_38]
0x180004e21  mov     [rsp+0A8h+var_70], rcx
0x180004e26  mov     [rsp+0A8h+var_78], r14d
0x180004e2b  mov     [rsp+0A8h+var_80], rdi
0x180004e30  mov     [rsp+0A8h+var_88], eax
0x180004e34  mov     r9, [rsp+0A8h+Binding]
0x180004e39  xor     r8d, r8d; pReturnValue
0x180004e3c  lea     edx, [r8+3]; nProcNum
0x180004e40  lea     rcx, pProxyInfo; pProxyInfo
0x180004e47  call    cs:__imp_NdrClientCall3
0x180004e4d  mov     rbx, rax
0x180004e50  mov     [rsp+0A8h+var_48], rax
0x180004e55  mov     [rsp+0A8h+var_58], eax
0x180004e59  jmp     short loc_180004E6D
0x180004e5b  test    eax, eax
0x180004e5d  jle     short loc_180004E67
0x180004e5f  movzx   eax, ax
0x180004e62  or      eax, 80070000h
0x180004e67  mov     ebx, eax
0x180004e69  mov     [rsp+0A8h+var_58], eax
0x180004e6d  cmp     [rsp+0A8h+Binding], 0
0x180004e73  jz      short loc_180004E80
0x180004e75  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180004e7a  call    cs:__imp_RpcBindingFree
0x180004e80  mov     eax, ebx
0x180004e82  add     rsp, 88h
0x180004e89  pop     r14
0x180004e8b  pop     rdi
0x180004e8c  pop     rsi
0x180004e8d  pop     rbx
0x180004e8e  retn
0x180006a6f  push    rbp
0x180006a71  sub     rsp, 50h
0x180006a75  mov     rbp, rdx
0x180006a78  mov     rcx, [rcx]
0x180006a7b  mov     ecx, [rcx]; ExceptionCode
0x180006a7d  call    cs:__imp_I_RpcExceptionFilter
0x180006a83  nop
0x180006a84  add     rsp, 50h
0x180006a88  pop     rbp
0x180006a89  retn
```
